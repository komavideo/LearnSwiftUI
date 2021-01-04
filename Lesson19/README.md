定制TabView内容
==============

## 知识点

* 定制TabView显示内容
* 编程方式切换Tab内容

## 实战演习

~~~swift
////////////////////////////////////
// 定制TabView内容
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct View1: View {
    @Binding var selected: Int
    var body: some View {
        VStack {
            Text("主页").font(.title)
            Button("Go To 设置") {
                self.selected = 20
            }
        }
    }
}
struct View2: View {
    @Binding var selected: Int
    var body: some View {
        VStack {
            Text("设置").font(.title)
            Button("Go To 主页") {
                self.selected = 10
            }
        }
    }
}
struct ContentView: View {
    @State private var selectedViewIndex: Int = 10
    var body: some View {
        TabView(selection: self.$selectedViewIndex) {
            View1(selected: self.$selectedViewIndex)
                .tabItem({
                    Image(systemName: "house")
                    Text("主页")
                }).tag(10)
            View2(selected: self.$selectedViewIndex)
                .tabItem({
                    Image(systemName: "gear")
                    Text("设置")
                }).tag(20)
        }
        .font(.title)
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com