Xcode + SwiftUI 入门使用
=======================

## 知识点

* Xcode11的使用
* SwiftUI初体验

## 实战演习

~~~swift
import SwiftUI
struct ContentView: View {
    var body: some View {
        
        NavigationView {
            List(0 ..< 20) { item in
                NavigationLink(destination: Text("Detail")) {
                    Image(systemName: "heart")
                        .resizable()
                        .foregroundColor(.red)
                        .frame(width: 50.0, height: 50)
                    VStack(alignment: .leading, spacing: 0) {
                        Text("Hello, World!")
                        Text("Detail")
                    }
                }
            }
            .navigationBarTitle(Text("Navigation Bar"))
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
