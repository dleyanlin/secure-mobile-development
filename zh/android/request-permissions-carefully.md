# 小心请求Android权限

## 详细描述

Android使用权限来管理对数据和API的访问。

错误配置或超特权的应用程序有时可以通过授予无意的权限来打开攻击者的大门。

利用权限的许多例子之一是“混乱的副手”攻击。在困惑的副攻击中，没有明确许可访问文件的应用程序通过具有权限的另一个服务请求该文件。系统使用该服务的权限来允许访问该文件，尽管应用程序没有适当的访问权限。

## 建议

较新的Android版本支持运行时权限，允许开发人员在需要时从用户请求权限。这对安全性有一些积极的影响，包括延迟授予所谓的[危险许可]（https://developer.android.com/guide/topics/security/permissions.html#normal-dangerous）。

* 仅请求您的应用程序运行所需的权限。请注意，即使您要求最低权限，仍可能存在逻辑缺陷，如果被利用，可能会使您的应用程序变得混乱。
* 一般来说，最好只要求应用程式运作所需的权限，而且从Android 6.0（Marshmallow），[运行时权限]（https://developer.android.com/training/permissions/requesting.html）开始，被介绍以帮助用户和开发者达成可接受的权限。
* 确保向用户提供上下文关于运行时需要许可的原因。

虽然运行时权限可能使开发复杂化，但使用较新的Android版本，它们不是可选的。但是，可以使用第三方库和Java注释更方便地管理它们（请参阅[PermissionsDispatcher](https://github.com/hotchemi/PermissionsDispatcher)和[Dexter](https://github.com/Karumi/Dexter))。

对您的应用授予危险权限可以使其成为更多的目标。只有在用户实际需要功能的情况下才能请求/获得许可，可以帮助您减少应用程序的特定定位，否则可能会使攻击更难。

## CWE / OWASP

* [M1 - Improper Platform Usage](https://www.owasp.org/index.php/Mobile_Top_10_2016-M1-Improper_Platform_Usage)
* [CWE-441 - Unintended Proxy or Intermediary ('Confused Deputy')](https://cwe.mitre.org/data/definitions/441.html)
