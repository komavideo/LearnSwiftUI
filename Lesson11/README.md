按钮事件+数据绑定
===============

## 知识点

* 按钮事件
* 数据绑定

## 实战演习

~~~swift
import SwiftUI

struct ContentView: View {
    @State private var txtInput: String = ""
    @State private var message: String = ""
    
    var body: some View {
        VStack(alignment: .center, spacing: 20) {
            Text("我的APP")
                .font(.largeTitle)
            TextField("用户名", text: self.$txtInput)
                .padding()
                .textFieldStyle(DefaultTextFieldStyle())
                .border(Color.gray, width: 1)
                .autocapitalization(.none)
                .disableAutocorrection(true)
            Button(action: {
                self.message = self.txtInput
            }, label: {
                Text("确定")
                    .padding()
                    .background(Color.green)
                    .foregroundColor(.white)
                    .font(.system(size: 24))
            })
            Divider()
            Text(self.message)
                .frame(width: UIScreen.main.bounds.width - 20, height: 30, alignment: .leading)
                .background(Color(red: 230/255, green: 230/255, blue: 230/255), alignment: .leading)
                .foregroundColor(Color.gray)
        }
        .padding(10)
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com