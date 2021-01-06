获取手机方向
==========

## 知识点

* 获取手机方向的方法 - UIDeviceOrientation

## 实战演习

~~~swift
////////////////////////////////////
// 获取手机方向的方法 - UIWindowScene
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI

struct ContentView: View {
    @State var orientation: UIDeviceOrientation = UIDevice.current.orientation
    
    var body: some View {
        VStack {
            Text(orientation.isLandscape ? "横屏" : "竖屏")
            .onReceive(NotificationCenter.Publisher(center: .default, name: UIDevice.orientationDidChangeNotification)) { _ in
                self.orientation = UIDevice.current.orientation
            }
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com