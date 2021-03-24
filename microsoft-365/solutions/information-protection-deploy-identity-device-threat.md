---
title: 使用标识、设备和威胁防护进行数据隐私管理
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
description: 使用 Microsoft 365 的身份、设备和威胁防护服务防止个人数据泄露。
ms.openlocfilehash: 145b8a59f7eafb95adf71dc24613ee15ef1c2cca
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51052346"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a>使用标识、设备和威胁防护进行数据隐私管理

Microsoft 365 提供了许多标识、设备和威胁防护功能，组织可以使用这些功能来帮助遵守与数据隐私相关的合规性法规。 本文介绍数据隐私法规在这些方面要求哪些内容，并提供相关 Microsoft 365 功能和服务列表以及指向可帮助你满足实现要求详细信息的链接。

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a>标识、设备和威胁防护与数据隐私法规如何关联

虽然数据隐私法规的特有性有所不同，但它们所要求的本质是，GDPR 第 5 (1)  (f) 条，其中规定：

- 个人数据的处理方式应可确保个人数据的适当安全性，包括防止未经授权的或非法处理，以及防止意外丢失、销毁或损坏，使用适当的技术或组织措施 (完整性和保密性) 。

因为个人数据泄露通常是由管理帐户或最终用户帐户泄露和恶意系统访问造成的。 例如，管理员帐户黑客攻击可能会导致客户信用卡号或其他个人信息的窃取。 应实施 Microsoft 365 中提供的所有可能提供的身份、设备和威胁防护，这些将反映在合规性分数中，可在合规性管理器中找到。

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a>使用评估工作和合规性管理器的结果

合规性管理器包括使用以下类别的标识、设备和威胁防护：

- Identity 对应于" **控制访问"** 类别
- 设备对应于 **"管理设备"** 类别
- 威胁防护对应于" **防范威胁"** 类别
 
如果在包含四个主要数据隐私法规的示例集合中选择了这些策略，合规性管理器会指定 90 项改进操作，其中大多数改进措施的分数为"27"。 由于合规性管理器针对这些类别调用了此类数量，因此此处列出了一些更常见的数字，仅供参考。

将 [Azure Active Directory (Azure AD](https://azure.microsoft.com/services/active-directory/)) 用于标识 **和控件** 访问类别，可以使用这些类别：

- 实施防重播的 (，以防止"中间人"攻击) 
- 阻止旧式身份验证。
- 配置用户风险和用户登录风险策略。
- 为管理员和非管理员启用 MFA (条件) 多重身份验证。
- 配置和强制实施密码策略。
- 使用 Azure AD Privileged Identity Management 限制对特权帐户的访问。
- 终止时禁用访问。
- 审核用户帐户和状态更改。
- 查看角色组和管理更改。

将 [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 用于设备和 **"管理设备"** 类别，通过该类别，你可以：

- 阻止已越狱且具有 root 权限的移动设备。
- 配置 Intune 进行移动设备管理。
- 为 Android、iOS、macOS 和 Windows 设备创建合规性策略。
- 为 Android、iOS、macOS 和 Windows 设备创建设备配置文件。
- 创建适用于 iOS 和 Windows 的应用保护策略。
- 使用锁屏界面隐藏信息。
- 为移动设备实施密码策略。
- 要求移动设备在处于非活动状态时锁定。
- 要求移动设备在多个登录失败时进行擦除。

将 [Exchange Online Protection 和 Microsoft Defender for Office 365](../security/defender-365-security/defender-for-office-365.md) 用于"抵御威胁 **"类别，** 通过这两种类别，可以：

- 启用 SPF (DMARC 和 DKIM 身份验证) 。
- 为 Office 365 设置 Microsoft Defender 防钓鱼策略。
- 实现安全附件。
- 实现安全链接。
- 实施恶意软件检测和响应策略。
- 实施出站和入站垃圾邮件策略。

### <a name="references"></a>引用：

- [常见标识和设备访问策略](../security/defender-365-security/identity-access-policies.md)
- [在 Office 365 中抵御威胁](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [安全附件](../security/defender-365-security/safe-attachments.md)
- [安全链接](../security/defender-365-security/safe-links.md)
- [安全文档](../security/defender-365-security/safe-docs.md)
