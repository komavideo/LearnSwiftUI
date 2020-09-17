取得系统数据
==========

## 知识点

* 取得系统数据 - @Environment

## EnvironmentValues

https://developer.apple.com/documentation/swiftui/environmentvalues

## 实战演习

~~~swift
////////////////////////////////////
// 取得系统数据 - @Environment
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI

struct ContentView: View {
    @Environment(\.colorScheme) var mode

    var body: some View {
        VStack {
            Text("Mode: \(mode == .dark ? "Dark" : "Light")")
            Text("Hello, World!")
                .padding(40)
                .background(mode == .dark ? Color.black : Color.yellow)
                .foregroundColor(mode == .dark ? Color.yellow : Color.black)
        }
    }
}
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView()
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com