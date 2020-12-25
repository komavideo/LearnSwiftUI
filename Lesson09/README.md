MVVM模式 - Model-View-ViewModel
===============================

## 知识点

* MVVM模式 -> Model-Controller-ViewModel-View

## 实战演习

+ Book.swift
+ MyHomeViewModel.swift
+ MyHomeView.swift

### Book.swift

~~~swift
import SwiftUI
struct Book {
    var title: String
    var author: String
}
~~~

### MyHomeViewModel.swift

~~~swift
import SwiftUI
class MyHomeViewModel: ObservableObject {
    @Published var bookInfo: Book
    init() {
        self.bookInfo = Book(title: "SwiftUI入门教学", author: "小马")
    }
    var appTitle: String {
        return self.bookInfo.title + "(\(self.bookInfo.author))"
    }
}
~~~

### MyHomeView.swift

~~~swift
////////////////////////////////////
// MVVM模式 - Model-View-ViewModel
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct MyHomeView: View {
    @ObservedObject private var viewModel = MyHomeViewModel()
    var body: some View {
        Text(self.viewModel.appTitle)
            .padding()
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com