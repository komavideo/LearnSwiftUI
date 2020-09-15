数据绑定，改变标题 - @State
========================

## 知识点

* 状态保存，数据绑定方法 - @State

## 实战演习

~~~swift
import SwiftUI

struct ContentView: View {
    @State private var title: String = "Helo Title."
    @State private var textInput: String = ""
    var body: some View {
        VStack {
            Text(self.title)
                .font(.title)
            TextField("placeholder", text: self.$textInput)
                .font(.title)
                .frame(height: 50)
                .padding(.horizontal, 10)
                .textFieldStyle(RoundedBorderTextFieldStyle())
            Button(action: {
                print("action:", self.textInput)
                self.title = self.textInput
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
