弹出Sheet视图
============

## 知识点

* 弹出新的窗体视图 - sheet

## 实战演习

~~~swift
////////////////////////////////////
// 弹出新的窗体视图 - sheet
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct PopView: View {
    @Binding var showSheet: Bool
    var body: some View {
        VStack(alignment: .center, spacing: 20) {
            Button(action: {
                self.showSheet = false
            }) {
                Image(systemName: "x.circle").font(.title)
            }
            .frame(minWidth: 0, maxWidth: .infinity, alignment: .topTrailing)
            .padding()
            Spacer()
            Text("Pop View").font(.largeTitle)
            Button("关闭窗体") {
                self.showSheet = false
            }.font(.title)
            Spacer()
        }
    }
}
struct ContentView: View {
    @State private var showSheet: Bool = false
    var body: some View {
        Button("显示Pop窗体") {
            self.showSheet = true
        }
        .font(.title)
        .sheet(isPresented: self.$showSheet, content: {
            PopView(showSheet: self.$showSheet)
        })
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com