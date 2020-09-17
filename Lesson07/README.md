观察者数据绑定
==========

## 知识点

* 观察者数据绑定
  + ObservableObject
  + @Published
  + @ObservedObject

## 实战演习

### AppData.swift

~~~swift
import SwiftUI
class AppData: ObservableObject {
    @Published var AppTitle: String = "SwiftUI教学"
    @Published var Author: String = "koma"
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
    // Create the SwiftUI view that provides the window contents.
    let app = UIApplication.shared
    let delegate = app.delegate as! AppDelegate
    let contentView = ContentView(appData: delegate.appData)
...
~~~

### ContentView.swift

~~~swift
import SwiftUI

struct ContentView: View {
    @ObservedObject var appData: AppData
    
    var body: some View {
        VStack {
            Text(self.appData.AppTitle)
                .bold()
                .font(.largeTitle)
            Text(self.appData.Author)
                .bold()
                .font(.title)
                .foregroundColor(.gray)
            Divider()
            Button(action: {
                self.appData.Author = "xiaoma"
            }) {
                Text("更新")
                    .padding()
                    .font(.system(size: 30))
            }
        }
    }
}
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        ContentView(appData: AppData())
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com