拆分视图 - Split Views
=====================

## 知识点

* 拆分视图 - Split Views
  + iPad
  + iPhone

## 实战演习

~~~swift
////////////////////////////////////
// 拆分视图 - Split Views
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct MenuView: View {
    @State private var selectedLink: Int? = nil
    var body: some View {
        VStack(alignment: .center, spacing: 20) {
            Text("菜单")
                .padding()
            NavigationLink(destination: View1(), tag: 1, selection: self.$selectedLink) {
                Text("View1")
            }
            NavigationLink(destination: View2(), tag: 2, selection: self.$selectedLink) {
                Text("View2")
            }
            NavigationLink(destination: View3(), tag: 3, selection: self.$selectedLink) {
                Text("View3")
            }
            Spacer()
        }
        .font(.title)
        .navigationBarTitle("系统菜单", displayMode: .inline)
    }
}
struct View1: View {
    var body: some View {
        ZStack {
            Color(.blue)
            Text("View1")
                .font(.largeTitle)
        }
        .navigationBarTitle("View1")
    }
}
struct View2: View {
    var body: some View {
        ZStack {
            Color(.green)
            Text("View2")
                .font(.largeTitle)
        }
        .navigationBarTitle("View2")
    }
}
struct View3: View {
    var body: some View {
        ZStack {
            Color(.yellow)
            Text("View3")
                .font(.largeTitle)
        }
        .navigationBarTitle("View3")
    }
}
struct ContentView: View {
    var body: some View {
        NavigationView {
            MenuView()
            Text("启动默认视图(iPad)")
            //EmptyView()
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com