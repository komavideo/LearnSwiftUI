限制用户输入
==========

## 知识点

* 限制用户输入 - ObservableObject, Published, didSet, ObservedObject

## 实战演习

~~~swift
import SwiftUI
class ContentViewData: ObservableObject {
    @Published var txtInput: String = "" {
        didSet {
            // 8位以上输入限制
            if txtInput.trimmingCharacters(in: .whitespaces).count > 8 {
                self.txtInput = oldValue
            }
        }
    }
    @Published var message: String = "message"
}

struct ContentView: View {
    @ObservedObject var viewData: ContentViewData = ContentViewData()
    
    var body: some View {
        VStack(alignment: .center, spacing: 10) {
            Text("我的APP")
                .font(.title)
            TextField("输入用户名", text: self.$viewData.txtInput)
                .textFieldStyle(RoundedBorderTextFieldStyle())
                .disableAutocorrection(true)
            Button(action: {
                let temp = self.viewData.txtInput.trimmingCharacters(in: .whitespaces)
                if temp.isEmpty {
                    self.viewData.message = "用户名不能为空！"
                } else {
                    self.viewData.message = "干得不错"
                }
            }, label: {
                Text("确定")
                    .padding()
                    .background(Color.blue)
                    .foregroundColor(.white)
                    .cornerRadius(10)
            })
            Spacer()
            Text(self.viewData.message)
                .frame(width: UIScreen.main.bounds.width - 20, height: 60, alignment: .leading)
                .padding(.horizontal, 10)
                .background(Color.gray)
                .foregroundColor(Color.white)
        }
        .padding(0)
        .edgesIgnoringSafeArea(.bottom)
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com