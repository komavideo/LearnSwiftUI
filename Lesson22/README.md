弹出框 - popover
===============

## 知识点

* 弹出框 - popover for iPad

## 实战演习

~~~swift
////////////////////////////////////
// 弹出框 - popover
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct PopoView: View {
    @Environment(\.presentationMode) var presentation
    var body: some View {
        VStack {
            Button("X") {
                self.presentation.wrappedValue.dismiss()
            }
            .frame(minWidth: 0, maxWidth: .infinity, alignment: .trailing)
            .font(.title)
            Spacer()
            Text("弹出框页面")
                .font(.largeTitle)
                .padding(20)
            Spacer()
        }
        .padding()
    }
}
struct ContentView: View {
    @State private var showPopover: Bool = false
    var body: some View {
        Button("显示弹出框Popover") {
            self.showPopover = true
        }.popover(isPresented: self.$showPopover, arrowEdge: .top) {
            PopoView()
        }
        .font(.largeTitle)
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com