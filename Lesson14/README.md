导航View的基础
=============

## 知识点

* 导航View的基础 - NavigationView

## 实战演习

~~~swift
////////////////////////////////////
// 导航View的基础 - NavigationView
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct ContentView: View {
    @State private var setColor: Bool = false
    @State private var setBold: Bool = false
    var body: some View {
        NavigationView {
            VStack {
                Text("Hello, World!")
                    .foregroundColor(self.setColor ? Color.red : Color.blue
                )
                Spacer()
            }
            .padding(10)
            .font(self.setBold ? .largeTitle : .body)
            .border(Color.red, width: 6)
            
            .navigationBarTitle("Home Screen", displayMode: .inline)
            .navigationBarItems(leading: Button(action: {
                self.setBold.toggle()
            }, label: {
                Text("改变字体")
            }), trailing: Button(action: {
                self.setColor.toggle()
            }, label: {
                Text("改变颜色")
            }))
        }
        .border(Color.green, width: 3)
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com