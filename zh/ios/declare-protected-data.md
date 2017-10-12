# 6.7声明使用受保护的数据类

## 详细描述

为了帮助维护用户数据的隐私，iOS 10要求开发人员在应用程序的“Info.plist”文件中使用目的字符串键声明应用程序对受保护数据类的预期用途。如果未包含用途字符串键，则当该应用尝试访问受保护的数据时，该应用将退出。

## 建议

对于iOS 10.0或更高版本的应用程序，开发人员必须静态声明访问特定接口和受保护数据的意图，并在应用程序的“Info.plist”文件中包含相应的目的字符串，以获取以下密钥：
* `NSBluetoothPeripheralUsageDescription`
* `NSCalendarsUsageDescription`
* `NSCameraUsageDescription`
* `NSContactsUsageDescription`
* `NSHealthShareUsageDescriptionNSHomeKitUsageDescription`
* `NSLocationAlwaysUsageDescription`
* `NSLocationWhenInUseUsageDescription`
* `NSMicrophoneUsageDescription`
* `NSMotionUsageDescription`
* `NSPhotoLibraryUsageDescription`
* `NSRemindersUsageDescription`
* `NSSiriUsageDescription`
* `NSSpeechRecognitionUsageDescription`
* `NSAppleMusicUsageDescription`

指定的目的字符串将显示在用户提示中，请求访问相关的外围设备。没有目的字符串，应用程序将退出。


## 参考

 * Apple文档：[Cocoa Keys - Key Summary]（https://developer.apple.com/library/content/documentation/General/Reference/InfoPlistKeyReference/Articles/CocoaKeys.html#//apple_ref/doc/uid/TP40009251- SW35）

## CWE/OWASP

 * [M7 - Client Code Quality](https://www.owasp.org/index.php/Mobile_Top_10_2016-M7-Poor_Code_Quality)
 * [CWE-264: Permissions, Privileges, and Access Controls](http://cwe.mitre.org/data/definitions/264.html)
