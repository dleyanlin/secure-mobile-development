# 2.8反序列化不可信数据时要小心

## 详细描述

开发人员通常将数据序列化（或“编组”）数据，以便在系统之间转移应用程序状态或将其存储以供以后使用。反序列化（或“解组”），序列化数据将重构数据，或在某些情况下重构应用程序逻辑。不幸的是，应用程序可能会认为反序列化的数据是有效的或可信赖的，即攻击者可以利用这种情况修改应用程序的常规执行流程。这种安全漏洞适用于iOS和Android应用程序（特别是Android中的Binder操作）。

## 建议

一般来说，您可以通过以下四种方式防止对不受信任数据进行反序列化所产生的漏洞：
1. 确定系统之间的信任边界，将外部来源的数据视为不可信
2. 避免来自不信任来源的数据反序列化
3. 消除反序列化数据（例如，仅允许已知的安全字符，对象，有限的功能）
4. 在反序列化之前验证和验证文件的来源和内容。

## 参考

### 一般
* [OWASP - 反序列化不可信数据]（https://www.owasp.org/index.php/Deserialization_of_untrusted_data）
* [OWASP反序列化手续表]（https://www.owasp.org/index.php/Deserialization_Cheat_Sheet）

### iOS
* [关于NSSecureCoding需要了解的一切]（http://nshipster.com/nssecurecoding/）
* [Java Deserialization Bug和NSSecureCoding]（https://mjtsai.com/blog/2015/11/08/the-java-deserialization-bug-and-nssecurecoding/）

### Android
* [CVE-2014-7911 - Android系统服务漏洞和利用的深度分析]（(http://researchcenter.paloaltonetworks.com/2015/01/cve-2014-7911-deep-dive-analysis-android-system-service-vulnerability-exploitation/)


## CWE/OWASP

* [M7 - Client Code Quality](https://www.owasp.org/index.php/Mobile_Top_10_2016-M7-Poor_Code_Quality)
* [CWE-502: Deserialization of Untrusted Data](http://cwe.mitre.org/data/definitions/502.html)
