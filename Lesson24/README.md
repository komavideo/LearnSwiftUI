上拉消息提示框 - ActionSheet
===========================

## 知识点

* 上拉消息提示框的基本使用方法

## 实战演习

~~~swift
////////////////////////////////////
// 消息提示框 - ActionSheet
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI

struct ContentView: View {
    @State private var title: String = "小马SwiftUI教学"
    @State private var message: String = "消息区"
    @State private var openSheet: Bool = false
    var body: some View {
        VStack(alignment: .center, spacing: 20) {
            Text(self.title)
                .font(.largeTitle)
            Text(self.message)
                .font(.body)
                .foregroundColor(Color.red)
                .frame(maxWidth: .infinity)
                .padding()
                .border(Color.gray, width: 1)
                
            Button("Open the window.") {
                self.openSheet = true
            }.font(.headline)
        }
        .actionSheet(isPresented: self.$openSheet) { () -> ActionSheet in
            ActionSheet(title: Text("Title"), message: Text("Message"), buttons: [
                .default(Text("Option1"), action: {
                    self.message = "Option1"
                }),
                .default(Text("Option2"), action: {
                    self.message = "Option2"
                }),
                .destructive(Text("Option3"), action: {
                    self.message = "Option3"
                }),
                .cancel(Text("Cancel"), action: {
                    self.message = "取消"
                })
            ])
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com