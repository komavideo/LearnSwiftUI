自定义按钮样式
============

## 知识点

* 自定义按钮样式 - ButtonStyle

## 实战演习

~~~swift
import SwiftUI

struct MyButtonStyle: ButtonStyle {
    func makeBody(configuration: Configuration) -> some View {
        let isPressed = configuration.isPressed
        return configuration.label
            .padding(20)
            .border(Color.green, width: 5)
            .background(isPressed ? Color.green : Color.white)
            .scaleEffect(isPressed ? 1.2 : 1.0)
    }
}

struct ContentView: View {
    var body: some View {
        VStack(alignment: .center, spacing: 20) {
            Button(action: {
            }, label: {
                Text("DefaultButtonStyle")
                    .font(.title)
            })
            .buttonStyle(DefaultButtonStyle())

            Button(action: {
            }, label: {
                Text("PlainButtonStyle")
                    .font(.title)
            })
            .buttonStyle(PlainButtonStyle())
            
            Button(action: {
            }, label: {
                Text("BorderlessButtonStyle")
                    .font(.title)
            })
            .buttonStyle(BorderlessButtonStyle())
            
            Button(action: {
            }, label: {
                Text("MyButtonStyle")
                    .font(.title)
            })
            .buttonStyle(MyButtonStyle())
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