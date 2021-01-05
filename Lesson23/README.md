警告框的使用
==========

## 知识点

* 警告框的使用 - Alert

## 实战演习

~~~swift
////////////////////////////////////
// 警告框 - alert
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct ContentView: View {
    @State private var showAlert: Bool = false
    var body: some View {
        VStack(alignment: .center, spacing: 20) {
            Text("警告框")
                .font(.largeTitle)
                .foregroundColor(.red)
            Button("按一下") {
                self.showAlert = true
            }
            .font(.largeTitle)
            .alert(isPresented: self.$showAlert, content: {
                Alert(title: Text("警告"), message: Text("官人，不可以。"), dismissButton: .cancel(Text("关闭")))
            })
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com