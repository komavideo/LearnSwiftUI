数据绑定，传递结构
================

## 知识点

* 数据绑定，传递结构 - @Binding

## 实战演习

~~~swift
import SwiftUI
struct HeaderView: View {
    @Binding var title: String
    var counter: Int = 0
    
    init(title: Binding<String>) {
        self._title = title
        let sentence = self._title.wrappedValue
        counter = sentence.count
    }
    var body: some View {
        Text(self.title + "/\(counter)")
            .font(.title)
    }
}
struct ContentView: View {
    @State private var title: String = "App Title"
    var body: some View {
        VStack {
            HeaderView(title: self.$title)
            Button(action: {
                self.title = "New App Title"
            }) {
                Text("确定")
                    .font(.largeTitle)
                    .padding()
            }
        }
        .padding()
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
