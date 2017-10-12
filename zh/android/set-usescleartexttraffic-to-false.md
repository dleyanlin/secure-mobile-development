# 7.14将“usesCleartextTraffic”标志设置为false

## 详细描述

应用程序和任何后端服务之间的不安全的通信通道可以暴露它们之间传输的数据。类似于iOS中的应用程序传输安全（ATS）功能（另请参见最佳实践[6.5实施应用程序传输安全性]（https://books.nowsecure.com/secure-mobile-development/en/ios/implement-app-transport） -security.html）），Android 6.0及更高版本可以通过在Android Manifest中添加“android：usesCleartextTraffic”属性，从而更容易防止应用程序使用明文网络流量（例如HTTP和FTP，而不使用TLS）。

## 建议

在Android Manifest中将`usesCleartextTraffic`标志设置为false。这将导致应用程序要求平台和第三方库阻止应用程序使用明文流量。

* 并不是所有的API都会遵守标志，而开发人员/安全分析人员将需要确定哪些API将会或不会兑现该标志。

* 另请注意，WebView将不符合“usesCleartextTraffic”标志（如果您必须使用WebView，请参阅最佳实践[Follow WebView Best Practices](https://github.com/nowsecure/secure-mobile-development/blob/master/en/android/webview-best-practices.md))）。

* 如果应用程序使用的特定服务需要明文，开发人员可以使用网络安全配置功能（“android：networkSecurityConfig”）在绝对必要时手动添加异常。

## CWE/OWASP

* [M3 - Insecure Communication](https://www.owasp.org/index.php/Mobile_Top_10_2016-M3-Insecure_Communication)
* [CWE-319 - Cleartext Transmission of Sensitive Information](https://cwe.mitre.org/data/definitions/319.html)
