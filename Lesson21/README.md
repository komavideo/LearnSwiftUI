弹出Sheet视图 - MVVM模式
=======================

## 知识点

* 采用MVVM模式, 循环数据并弹出Sheet视图

## 实战演习

### AppData.swift

~~~swift
////////////////////////////////////
// 弹出Sheet视图 - MVVM模式
//
// 小马视频频道
// http://komavideo.com
////////////////////////////////////
import SwiftUI
struct Hero {
    var name: String
    var showname: String
    var attack: Int
}
struct HeroViewModel: Identifiable {
    var id = UUID()
    var hero: Hero
    var desc: String {
        return "英文名：" + hero.name + "／攻击力：\(hero.attack)"
    }
}
class AppData: ObservableObject {
    @Published var heroes: [HeroViewModel]
    init() {
        self.heroes = [
            HeroViewModel(hero: Hero(name: "8bit", showname: "8比特", attack: 5)),
            HeroViewModel(hero: Hero(name: "barley", showname: "巴里", attack: 3)),
            HeroViewModel(hero: Hero(name: "bea", showname: "蜜蜂", attack: 5)),
            HeroViewModel(hero: Hero(name: "bibi", showname: "芘芘", attack: 4)),
        ]
    }
}
~~~

### ContentView.swift

~~~swift
import SwiftUI
struct HeroView: View {
    @Environment(\.presentationMode) var presentation
    let herovm: HeroViewModel
    var body: some View {
        VStack {
            Spacer()
            Text(herovm.hero.showname)
                .font(.largeTitle)
            Image(herovm.hero.name)
                .resizable()
                .frame(width: 330, height: 250)
                .cornerRadius(20)
            Text(herovm.desc)
            Spacer()
            Button("关闭") {
                self.presentation.wrappedValue.dismiss()
            }.font(.title)
        }
    }
}
struct ContentView: View {
    @EnvironmentObject var appData: AppData
    @State private var openSheet: HeroViewModel? = nil
    var body: some View {
        List {
            ForEach(self.appData.heroes) { vm in
                HStack {
                    Image(vm.hero.name)
                        .resizable()
                        .frame(width: 50, height: 50)
                        .cornerRadius(15)
                    Button(action: {
                        self.openSheet = vm
                    }, label: {
                        Text(vm.hero.showname)
                    })
                }
            }
        }
        .sheet(item: self.$openSheet) { vm in
            HeroView(herovm: vm)
        }
    }
}
~~~

### myappApp.swift

```swift
import SwiftUI

@main
struct myappApp: App {
    @StateObject var appData: AppData = AppData()
    var body: some Scene {
        WindowGroup {
            ContentView()
                .environmentObject(self.appData)
        }
    }
}
```

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com