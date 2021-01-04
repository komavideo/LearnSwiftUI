滑动调整图片大小 - Slider
=======================

## 知识点

* 调整图片大小 - Slider控件的使用

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
    @State private var imageWidth: CGFloat = UIScreen.main.bounds.width
    var body: some View {
        NavigationView {
            VStack {
                Slider(value: self.$imageWidth, in: 100...UIScreen.main.bounds.width * 3, step: 1)
                    .padding(10)
                    .frame(width: UIScreen.main.bounds.width - 20)
                VStack {
                    Spacer()
                    Image("trover")
                        .resizable()
                        .aspectRatio(contentMode: .fit)
                        .frame(width: self.imageWidth)
                    Spacer()
                }
            }
            .navigationBarTitle("图片调整", displayMode: .inline)
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com