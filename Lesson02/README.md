图片的缩放
==========

## 知识点

* 图片缩放处理
* @State状态管理

## 实战演习

~~~swift
import SwiftUI
struct ContentView: View {
    @State private var zoomed: Bool = false
    
    var body: some View {
        ZStack(alignment: self.zoomed ? .top : .topTrailing) {
            Image("trover")
                .resizable()
                .aspectRatio(contentMode: self.zoomed ? .fill : .fit)
                .navigationBarTitle(Text("崔佛"), displayMode: .inline)
                .onTapGesture {
                    withAnimation {
                        self.zoomed = !self.zoomed
                    }
            }
            Image("xiaoma")
                .resizable()
                .frame(width: 50, height: 50, alignment: .center)
                .padding(.all, 10)
        }
    }
}
struct ContentView_Previews: PreviewProvider {
    static var previews: some View {
        NavigationView {
            ContentView()
        }
    }
}
~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com
