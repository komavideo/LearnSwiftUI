编程导航方式 - isActive
======================

## 知识点

* 使用 isActive 属性导航视图

## 实战演习

~~~swift
////////////////////////////////////
// 导航View的基础 - NavigationView
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct DetailView: View {
    @Binding var active: Bool
    var body: some View {
        VStack(spacing: 20) {
            Text("详细页面")
                .font(.title2)
            Button(action: {
                self.active = false
            }, label: {
                Text("关闭画面")
                    .font(.title2)
            })
        }
        .navigationBarTitle("详细")
        .navigationBarBackButtonHidden(true)
        .navigationBarItems(leading: Button(action: {
            self.active = false
        }, label: {
            Text("返回")
        }))
    }
}
struct ContentView: View {
    @State private var activeLink: Bool = false
    
    var body: some View {
        NavigationView {
            VStack(alignment: .center, spacing: 10) {
                Text("Hello, World!")
                NavigationLink("第二个画面", destination: DetailView(active: self.$activeLink), 
                    isActive: self.$activeLink)
                NavigationLink(
                    destination: DetailView(active: self.$activeLink),
                    isActive: self.$activeLink,
                    label: {
                        Button(action: {
                            self.activeLink = true
                        }, label: {
                            Text("编程导航").foregroundColor(Color.purple)
                        })
                    })
            }
            .padding()
            .navigationBarTitle("主画面", displayMode: .inline)
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com