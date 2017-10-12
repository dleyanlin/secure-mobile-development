# 隐藏帐号并使用令牌

## 详细信息

许多app在各种UI显示中存储完整的帐号。

## 建议

鉴于移动应用在公共场所的广泛使用，显示部分号码（例如***9881）可以帮助确保此信息的最大隐私。 除非需要在设备上存储完整的数字，否则存储部分隐藏的数字。 通常，帐号用于查询服务器端帐户数据; 该数据可以容易地从存储器中被盗取，或者在某些情况下被操纵以处理用户不应该具有访问权限的帐户。 建议将令牌(token)分配给每个帐户，并提供给客户端，而不是帐号。 这些令牌（不应由用户推断）具有到实际帐户的服务器端映射。 如果应用程序数据被盗，用户的帐号不会被暴露，攻击者必须首先确定映射回帐户的令牌，而不能直接查询帐号。

在iOS中，如果你意识到

```
> - (BOOL)textField:(UITextField *)textField

> shouldChangeCharactersInRange:(NSRange)range replacementString:(NSString *)string
```

作为文本字段的委托的一部分，您可以更改输入文本的可见性。

## CWE/OWASP

* [M2 - Insecure Data Storage](https://www.owasp.org/index.php/Mobile_Top_10_2016-M2-Insecure_Data_Storage)
