Tab标签组件 - TabView
====================

## 知识点

* 使用Tab标签组件实现多窗口效果

## SF Symbols 2

https://developer.apple.com/sf-symbols/

## 实战演习

~~~swift
////////////////////////////////////
// Tab标签组件 - TabView
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct ContentView: View {
    var body: some View {
        TabView {
            Text("Tab1")
                .tabItem({
                    Image(systemName: "house")
                    Text("主页")
                })
                .font(.title)
            Text("Tab2")
                .tabItem({
                    Image(systemName: "calendar")
                    Text("日历")
                })
                .font(.largeTitle)
            Text("Tab3")
                .tabItem({
                    Image(systemName: "car")
                    Text("服务")
                })
                .font(.caption)
            Text("Tab4")
                .tabItem({
                    Image(systemName: "gear")
                    Text("设置")
                })
                .font(.body)
        }
        //.tabViewStyle(PageTabViewStyle(indexDisplayMode: .always))
        //.background(Color.gray.opacity(0.5))
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com