# 限制使用UUID
## 详细描述

大多数移动设备具有在制造时为了识别目的而分配的唯一ID（也称为通用唯一标识符（UUID））。 例如，iOS设备分配了所谓的唯一设备标识符（UDID）。 唯一标识设备的能力对于获取，管理和保护数据通常很重要。 开发人员迅速采用UUID和UDID进行设备识别，从而使其成为许多系统的安全基础。

不幸的是，这种方法带来了几个隐私和安全问题。 首先，许多在线系统已将设备的UUID连接到单个用户，以便即使在用户未登录到应用时也能够跨应用进行跟踪。 这种跟踪用户的高级功能已经成为主要的隐私问题。

除此之外，通过UUID识别人员的应用程序有风险暴露设备的以前的所有者的数据到新的所有者。 在一个实例中，在重新设置iPhone之后，即使所有用户数据已被擦除，我们也可以访问先前用户的在线音乐服务的帐户。 这不仅是一个隐私问题，它的安全威胁，因为攻击者可以伪造一个UUID。

苹果已经认识到iOS的UDID的隐私和安全风险，并删除了开发者对它的访问。 在UDID不可用的情况下，一些开发人员应用涉及无线网络接口或OpenUDID的MAC地址的其他设备识别方法。 这些方法现在已在系统/ API级别被禁止，并且作为AppStore审查过程的一部分被标记和拒绝。

## 建议

我们建议开发人员避免使用任何设备提供的标识符来标识设备，特别是如果它是实施设备身份验证的一部分。 相反，我们建议在注册，安装或首次执行时创建应用程序唯一的“设备因子”。 然后可能需要将此应用程序唯一的设备因子与用户身份验证结合，以创建会话。 设备因子也可以用作加密例程中的附加因子。

由于它不依赖于可预测的，设备提供的数据，因此开发变得更加困难。 通过利用挑战 - 响应方法，服务器和设备可以在用户认证之前彼此认证。 要获得系统访问，攻击者必须利用这两个因素。 开发人员还可以实现在客户端或服务器端重置设备因素的功能，从而强制对用户和设备进行更严格的重新身份验证。

为了在保留广告功能的同时保护用户隐私，Apple建议使用advertisingIdentifier - 在系统中所有应用程序之间共享的唯一标识符。用户可以随时在设置 - >隐私 - >广告菜单中重置其设备上的advertisingIdentifier。

## 参考

 * [Unique Identifiers in iOS](https://possiblemobile.com/2013/04/unique-identifiers/)

## CWE/OWASP

* [M7 - Client Code Quality](https://www.owasp.org/index.php/Mobile_Top_10_2016-M7-Poor_Code_Quality)
* [CWE-200: Information Exposure](http://cwe.mitre.org/data/definitions/200.html)
