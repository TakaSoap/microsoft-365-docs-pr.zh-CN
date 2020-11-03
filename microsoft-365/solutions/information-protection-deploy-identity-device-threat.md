---
title: 对数据隐私法规使用标识、设备和威胁防护
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 365 的标识、设备和威胁防护服务防止个人数据泄露。
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847174"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>对数据隐私法规使用标识、设备和威胁防护

Microsoft 365 提供了大量标识、设备和威胁防护功能，组织可以使用这些功能来帮助遵守与数据隐私相关的合规性管理法规。 本文介绍了这些方面的数据隐私法规所需的内容，并提供了相关 Microsoft 365 功能和服务的列表，并提供了可帮助您解决实现要求的详细信息的链接。

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>标识、设备和威胁防护与数据隐私法规的关系

尽管数据隐私条例的具体程度各不相同，但它们调用的内容的本质是在 GDPR 的文章 5 (1) # B2 f) 中体现，这表明： 

- 应以确保个人数据的适当安全性的方式处理个人数据，包括防止未经授权或非法处理的保护，以及防止意外丢失、损坏或损坏、使用适当的技术或组织措施 ( "完整性和机密性" ) 。

由于个人数据泄露通常是由管理或最终用户帐户泄露和恶意系统访问导致的。 例如，管理员帐户黑客攻击可能会导致 exfiltration 的客户信用卡号码或其他个人信息。 可能应实施 Microsoft 365 提供的所有通常建议的标识、设备和威胁防护，这将反映在合规性管理器中找到的合规性分数中。

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>使用评估工作和合规性管理器的结果

合规性管理器包括使用以下类别的标识、设备和威胁防护：

- 标识对应于 **控件访问** 类别
- 设备对应于 " **管理设备** " 类别
- 威胁防护对应于 " **针对威胁进行保护** " 类别
 
如果在我们的四个主要数据隐私法规的示例集中选择这些选项，合规性管理器将指定90改进操作，其中大多数被评分为 "27"。 由于这些类别的合规性管理器会调用此类较大的数字，因此在此处列出了一些较常见的数字，以供参考。

使用 [Azure Active Directory (AZURE AD)](https://azure.microsoft.com/services/active-directory/) for Identity And **Control Access** 类别，您可以：

- 实施不能重放的身份验证 (以防止 "中间人" 攻击) 
- 阻止旧式身份验证。
- 配置用户风险和用户登录风险策略。
- 为管理员和非管理员启用条件访问和多重身份验证 (MFA) 。
- 配置和强制实施密码策略。
- 使用 Azure AD 特权标识管理限制对特权帐户的访问。
- 终止时禁用访问。
- 审核用户帐户和状态更改。
- 审阅角色组和管理更改。

使用适用于设备的 [Microsoft 终结点管理器](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 和 " **管理设备** " 类别，您可以：

- 阻止越狱断开的和根的移动设备。
- 为移动设备管理配置 Intune。
- 为 Android、iOS、macOS 和 Windows 设备创建合规性策略。
- 为 Android、iOS、macOS 和 Windows 设备创建设备配置文件。
- 为 iOS 和 Windows 创建应用保护策略。
- 使用锁屏屏蔽信息。
- 为移动设备实施密码策略。
- 要求移动设备在不活动时锁定。
- 要求移动设备在出现多个登录失败时擦除。

使用 [Exchange Online Protection 和 Microsoft Defender For Office 365](../security/office-365-security/office-365-atp.md) For The **防御威胁** 类别，您可以：

- 启用 (SPF、DMARC 和 DKIM) 的发件人身份验证。
- 设置 Microsoft Defender for Office 365 反网络钓鱼策略。
- 实施安全附件。
- 实现安全链接。
- 实施恶意软件检测和响应策略。
- 实施出站和入站垃圾邮件策略。

### <a name="references"></a>参照

- [常见标识和设备访问策略](../security/office-365-security/identity-access-policies.md)
- [防御 Office 365 中的威胁](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [安全附件](../security/office-365-security/atp-safe-attachments.md)
- [安全链接](../security/office-365-security/atp-safe-links.md)
- [安全文档](../security/office-365-security/safe-docs.md)
