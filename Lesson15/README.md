导航链接
==========

## 知识点

* 导航链接 - NavigationLink View

## 实战演习

~~~swift
////////////////////////////////////
// 导航View的基础 - NavigationView
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct DetailView: View {
    @Environment(\.presentationMode) var presentation
    var body: some View {
        VStack {
            Image(systemName: "heart.fill")
                .font(.largeTitle)
                .foregroundColor(.red)
            Text("I love u.")
                .font(.largeTitle)
        }
        .navigationBarTitle("详细")
        .navigationBarBackButtonHidden(true)
        .navigationBarItems(leading: Button("返回") {
            self.presentation.wrappedValue.dismiss()
        })
    }
}
struct ContentView: View {
    var body: some View {
        NavigationView {
            VStack(alignment: .center, spacing: 10) {
                Text("Hello, World!")
                NavigationLink("第二个画面", destination: Text("Text View"))
                NavigationLink("详细画面", destination: DetailView())
                NavigationLink(destination: Text("Other Text View")) {
                    Text("另一个画面")
                }
                Spacer()
            }
            .padding()
            .navigationBarTitle("主画面", displayMode: .inline)
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com