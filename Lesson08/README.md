访问环境对象
==========

## 知识点

* 设置全局环境访问对象

## 实战演习

### AppData.swift

~~~swift
import SwiftUI
class AppData: ObservableObject {
    @Published var AppTitle: String = "SwiftUI教学"
    @Published var Author: String = "Koma"
}
~~~

### AppDelegate.swift

~~~swift
...
var appData: AppData!
func application(_ application: UIApplication, didFinishLaunchingWithOptions launchOptions: [UIApplication.LaunchOptionsKey: Any]?) -> Bool {
    self.appData = AppData()
    return true
}
...
~~~

### SceneDelegate.swift

~~~swift
func scene(_ scene: UIScene, willConnectTo session: UISceneSession, options connectionOptions: UIScene.ConnectionOptions) {
...
    let app = UIApplication.shared
    let delegate = app.delegate as! AppDelegate
    let contentView = ContentView()
        .environmentObject(delegate.appData)
...
~~~

### ContentView.swift

~~~swift
import SwiftUI
struct ContentView: View {
    @EnvironmentObject var appData: AppData
    
    var body: some View {
        VStack {
            Text(self.appData.AppTitle)
            Text(self.appData.Author)
        }
    }
}
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView().environmentObject(AppData())
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com