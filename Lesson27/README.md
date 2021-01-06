几何读取器
==========

## 知识点

* 父容器(View)几何读取器 - GeometryReader

## 实战演习

~~~swift
////////////////////////////////////
// 几何读取器 - GeometryReader
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct ContentView: View {
    var body: some View {
        VStack {
            Text("顶部")
            GeometryReader { geometry in
                HStack {
                    Spacer()
                    Text("父容器大小：\(Int(geometry.size.width)) * \(Int(geometry.size.height))" )
                        .font(.title)
                        .onTapGesture {
                            print("Global:",
                                  geometry.frame(in: .global).width,
                                  geometry.frame(in: .global).height,
                                  geometry.frame(in: .global).minX,
                                  geometry.frame(in: .global).minY
                                  )
                            print("Local:",
                                  geometry.frame(in: .local).width,
                                  geometry.frame(in: .local).height,
                                  geometry.frame(in: .local).minX,
                                  geometry.frame(in: .local).minY
                                  )
                        }
                    Spacer()
                }
            }
            .background(Color.black.opacity(0.1))
            Text("底部")
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com