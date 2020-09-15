属性包装器
==========

## 知识点

* 属性包装器的使用方法

## 实战演习

~~~swift
@propertyWrapper
struct ClamppedValue {
    private var storedValue: Int = 0

    var wrappedValue: Int {
        get {
            return self.storedValue
        }
        set {
            if newValue < 0 {
                self.storedValue = 0
            } else if newValue > 255 {
                self.storedValue = 255
            } else {
                self.storedValue = newValue
            }-
        }
    }

    init(wrappedValue initialValue: Int) {
        self.wrappedValue = initialValue
    }
}

struct MyColor {
    @ClamppedValue var red: Int
    @ClamppedValue var green: Int
    @ClamppedValue var blue: Int
}

let color: MyColor = MyColor(red: 50, green: 500, blue: 50)
print("color.red is \(color.red)")
print("color.green is \(color.green)")
print("color.blue is \(color.blue)")

~~~

## 课程文件

https://github.com/komavideo/LearnSwiftUI

## 小马视频频道

http://komavideo.com
