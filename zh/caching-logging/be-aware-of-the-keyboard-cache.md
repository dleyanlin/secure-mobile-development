# 注意键盘缓存

## 详细描述

iOS记录用户键入的内容，以便提供自定义自动更正和表单完成等功能，但敏感数据也可以存储。 几乎每个非数字字按照键入的顺序缓存在键盘缓存中; 缓存的内容超出了应用程序的管理权限，因此应用程序无法从缓存中删除数据。

## 建议

对任何敏感信息（而不仅仅是密码字段）禁用自动更正功能。 由于键盘缓存敏感信息，它可以恢复。 对于UITextField，查看将autocorrectionType属性设置为UITextAutocorrectionTypeNo以禁用缓存。 随着SDK更新，这些设置可能会随时间而变化，以确保其得到充分研究。 添加企业策略以定期清除键盘字典。 这可以由最终用户通过简单地去设置应用程序，通用>重置>重置键盘字典。

Android包含用户字典，用户输入的字词可以保存以供将来自动更正。 此用户字典可用于没有特殊权限的任何应用程序。 为了提高安全性，请考虑实施自定义键盘（以及可能的PIN输入），这可以禁用缓存，并提供针对恶意软件的额外保护。

## CWE/OWASP

 * [M7 - Client Code Quality](https://www.owasp.org/index.php/Mobile_Top_10_2016-M7-Poor_Code_Quality)
 * [CWE 200](http://cwe.mitre.org/data/definitions/200.html)
