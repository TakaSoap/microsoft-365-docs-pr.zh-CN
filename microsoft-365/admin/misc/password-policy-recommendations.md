---
title: 密码策略建议
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: high
ms.collection:
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: 加强组织对密码攻击的防护，禁用常见密码并启用基于风险的多重身份验证。
ms.openlocfilehash: 46e6c4ba163df0693630896b8db17b4eefe9828a
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312572"
---
# <a name="password-policy-recommendations"></a>密码策略建议

作为组织的管理员，你负责为组织中的用户设置密码策略。 设置密码策略可能很复杂且令人困惑，因而本文提供了帮助组织更安全地抵御密码攻击的建议。

Microsoft 仅限云的帐户具有无法更改的预定义密码策略。 唯一可以更改的项目是密码过期的天数，以及密码是否过期。 
  
要决定 Microsoft 365 密码在你组织中过期的频率，请参阅[设置 Microsoft 365 的密码过期策略](../manage/set-password-expiration-policy.md)。

有关 Microsoft 365 密码的详细信息，请参阅：

[重置密码](../add-users/reset-passwords.md)（文章）

[将个人用户密码设置为永不过期](../add-users/set-password-to-never-expire.md)（文章）

[允许用户重置自己的密码](../add-users/let-users-reset-passwords.md)（文章）

[重新发送用户密码 - 管理员帮助](../add-users/resend-user-password.md)（文章）
  
## <a name="understanding-password-recommendations"></a>了解密码建议

好的密码实践分为下面几个大类：
  
- **抵御常见攻击**：这涉及到选择用户在何处输入密码（具有优秀的恶意软件检测的已知受信任设备，经过验证的网站），以及选择要选用哪个密码（密码长度和唯一性）。

- **包含成功攻击**：包含成功黑客攻击是指限制为仅向特定服务公开，或者在用户密码被盗的情况下完全阻止该项损失。 例如，确保社交网络凭据的泄露不会导致你的银行帐户易受攻击，也不会使防护较弱的帐户接受重要帐户的重置链接。

- **了解人的天性**：很多有效的密码实践都在面对自然的人类行为时失败。 了解人的天性至关重要，因为研究表明，你强加于你的用户的几乎每条规则够将导致密码质量的弱化。 长度要求、特殊字符要求和密码更改要求都会促使密码的标准化，而这会使攻击者更容易猜出或破解出密码。

## <a name="password-guidelines-for-administrators"></a>管理员密码准则

加强密码系统安全的首要目标是密码多样性。 你需要你的密码策略包含多个不同且很难猜出的密码。 下面是可帮助你的组织尽可能保障安全的一些建议。
  
- 保持 8 个字符的最小长度要求

- 不设定字符构成要求。 例如，\*&amp;(^%$

- 不要求定期对用户帐户进行强制性重置

- 禁用常见密码，使系统内部不存在易受攻击的密码

- 教育用户不要将其组织密码重复用于与工作无关的用途

- 强制注册使用[多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)

- 克服基于风险的多重身份验证挑战

### <a name="password-guidance-for-your-users"></a>用户密码准则

下面是针对组织内部用户的一些密码准则。请确保使你的用户了解这些建议并在组织级别上强制实施所建议的密码策略。
  
- 不要使用你在任何其他网站上所用的相同或相似密码

- 不要使用单个字词（例如 **password**）或常用短语（例如 **Iloveyou**）

- 使密码很难被猜出，即使是很熟悉你的人也很难猜出，例如不要设为你朋友或家人的姓名和生日、你喜欢的乐队以及你爱用的短语

## <a name="some-common-approaches-and-their-negative-impacts"></a>一些常见方法及其负面影响

下面是一些最常用的密码管理实践，但调查结果警示我们注意其负面影响。
  
### <a name="password-expiration-requirements-for-users"></a>用户密码过期要求

密码过期要求弊大于利，因为这些要求强制用户选择可预测的密码（即由彼此间紧密联系的有序单词和数字构成的密码）。 在这类情况下，可能会根据上一个密码预测出下一个密码。 密码过期要求没有提供任何控制优势，因为网络罪犯几乎始终在盗用凭据后立即使用这些凭据。 有关详细信息，请查看“[是时候重新思考强制密码更改了”](https://go.microsoft.com/fwlink/p/?linkid=861018)。
  
### <a name="requiring-long-passwords"></a>要求使用长密码

密码长度要求（大于约 10 个字符）可能会导致出现可预测且不必要的用户行为。 例如，必须具有 16 个字符密码的用户可能会选择 **fourfourfourfour** 或 **passwordpassword** 等满足字符长度但很容易被猜出的重复模式。 此外，长度要求增加了用户采取其他不安全做法的几率，例如记下其密码、重复使用密码或将密码以不加密方式存储在其文档中。 为鼓励用户考虑使用唯一密码，我们建议保持合理的 8 字符最低长度要求。
  
### <a name="requiring-the-use-of-multiple-character-sets"></a>需要使用多字符集

密码复杂性要求会缩减密钥空间，导致用户以可预测的方式行动，因此弊大于利。 大多数系统都会强制实施一定程度的密码复杂性要求。 例如，密码需要使用来自下面所有三个类别的字符：
  
- 大写字符

- 小写字符

- 非字母数字字符

大多数用户都会使用相似的模式，例如第一个位置使用大写字母，最后一位使用符号，倒数第二位使用数字。 而网络罪犯知道这一点，因此他们会使用最常见的替换来运行字典攻击，例如用“$”替换“s”、“@”替换“a”，“1”替换“l”。 强制用户选择大写、大小、数字、特殊字符的组合会产生负面影响。 某些复杂性要求甚至会阻止用户使用安全易记的密码，并迫使他们采用安全性更低、更难记住的密码。
  
## <a name="successful-patterns"></a>成功的模式

相比之下，下面是鼓励密码多样性的一些建议。
  
### <a name="ban-common-passwords"></a>禁用常见密码

创建密码时，应对用户采用的最重要的密码要求是禁用常见密码，以使你的组织更不容易受到暴力破解密码攻击。常见用户密码包括：“**abcdefg**”、“**password**”、“**monkey**”。
  
### <a name="educate-users-to-not-reuse-organization-passwords-anywhere-else"></a>指导用户不要在任何其他位置重复使用组织密码

要传达给组织内部用户的最重要的消息之一是不要在任何其他位置重复使用其组织密码。 在外部网站使用组织密码会大大增加网络罪犯盗用这些密码的可能性。
  
### <a name="enforce-multi-factor-authentication-registration"></a>强制进行多重身份验证注册

请确保你的用户更新联系人和安全信息，例如备用电子邮件地址、电话号码或注册接收推送通知的设备，以便他们能够应对安全挑战并收到安全事件通知。 更新后的联系人和安全信息可帮助用户在忘记自身密码时或者其他人试图接管其帐户时验证他们的身份。 它还在登录尝试或密码更改等安全事件的情况下提供一个带外通知渠道。 
  
要了解详细信息，请参阅[设置多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)
  
### <a name="enable-risk-based-multi-factor-authentication"></a>启用基于风险的多重身份验证

基于风险的多重身份验证可确保在我们的系统检测到可疑活动时，它能迫使用户确保其自身是合法的帐户所有者。 
  
## <a name="next-steps"></a>后续步骤

希望了解有关管理密码的详细信息？ 下面是一些推荐阅读：

- [忘记密码，无密码](https://www.microsoft.com/security/business/identity-access-management/passwordless-authentication)

- [Microsoft 密码指南](https://www.microsoft.com/research/wp-content/uploads/2016/06/Microsoft_Password_Guidance-1.pdf)

- [Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008)（强大的 Web 密码是否有用？）

- [Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014)（密码组合和有限努力的用户）

- [Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015)（通过阅读用户的思维来阻止安全性较弱的密码）

- [Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016)（选择安全的密码）

- [Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018)（是时候重新思考强制密码更改了）

- [Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)（2015 最差密码）

## <a name="related-content"></a>相关内容

[重置密码](../add-users/reset-passwords.md)（文章）\
[将个人用户密码设置为永不过期](../add-users/set-password-to-never-expire.md)（文章）\
[允许用户重置自己的密码](../add-users/let-users-reset-passwords.md)（文章）\
[重新发送用户密码 - 管理员帮助](../add-users/resend-user-password.md)（文章）
