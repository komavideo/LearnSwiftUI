json数据的读取
============

## 知识点

* json数据的读取 - JSONDecoder()

## 实战演习

### data.json

~~~json
{
    "list": [
        {
            "id": 1,
            "title": "Java",
            "subtitle": "一种编程语言"
        },
        {
            "id": 2,
            "title": "Apple",
            "subtitle": "一种可食用的水果"
        },
        {
            "id": 3,
            "title": "Corona",
            "subtitle": "一种可怕的病毒"
        },
        {
            "id": 4,
            "title": "Iris",
            "subtitle": "一种深度学习的花"
        },
    ]
}
~~~

### AppData.swift

~~~swift
import SwiftUI

struct Book: Codable, Identifiable {
    let id: Int
    let title: String
    let subtitle: String
}

struct AppData: Codable {
    var list: [Book]
}

func loadJsonData() -> [Book] {
    let filename: String = "data.json"
    guard let url = Bundle.main.url(forResource: filename, withExtension: nil) else {
        fatalError("Can not find \(filename) in main bundle")
    }
    guard let data = try? Data(contentsOf: url) else {
        fatalError("Can not load \(url)")
    }
    guard let appData = try? JSONDecoder().decode(AppData.self, from: data) else {
        fatalError("Can not parse post list json data")
    }
    return appData.list
}
~~~

### ContentView.swift

~~~swift
import SwiftUI

struct ContentView: View {
    let appData: AppData
    
    init() {
        self.appData = AppData(list: loadJsonData())
    }
    
    var body: some View {
        VStack(alignment: .leading, spacing: 0) {
            List(self.appData.list){ book in
                    Text(book.title)
                        .font(.title)
                    Text(book.subtitle)
                        .font(.subheadline)
                        .foregroundColor(.gray)
            }
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com