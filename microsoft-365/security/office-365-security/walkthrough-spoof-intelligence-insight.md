---
title: 演练 - 欺骗智能见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 59a3ecaf-15ed-483b-b824-d98961d88bdd
ms.collection:
- M365-security-compliance
description: 管理员可以了解欺骗智能见解的工作原理。 他们可以快速确定哪些发件人从没有通过 SPF、DKIM 或 DMARC (电子邮件身份验证检查的域中合法地将电子邮件发送到) 。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8ca40e2cde08e5ea213d4c19366f038f1da19fa7
ms.sourcegitcommit: 070724118be25cd83418d2a56863da95582dae65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2021
ms.locfileid: "50407212"
---
# <a name="walkthrough---spoof-intelligence-insight-in-microsoft-defender-for-office-365"></a>演练 - Microsoft Defender for Office 365 中的欺骗智能见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

在具有适用于 Office 365 的 Defender 的 Microsoft 365 组织中，可以使用欺骗智能见解快速确定哪些外部发件人合法地从未通过 SPF、DKIM 或 DMARC 检查的域向您发送未经身份验证的电子邮件 (邮件) 。

通过允许已知外部发件人从已知位置发送欺骗邮件，可以减少误报 (标记为错误) 。 通过监视允许的欺骗发件人，您可以提供额外的安全层，以防止不安全的邮件到达组织。

有关报告和见解详细信息，请参阅安全与合规中心& [见解](reports-and-insights-in-security-and-compliance.md)。

本演练是安全与合规中心&之一。 有关导航报告和见解的信息，请参阅"相关主题"部分 [中的演练](#related-topics) 。

> [!NOTE]
> 欺骗智能见解显示过去 7 天的数据。 Exchange [](learn-about-spoof-intelligence.md) Online PowerShell 中的欺骗智能策略和相应的[Get-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy) cmdlet 显示过去 30 天的数据。 [Get-SpoofMailReport](https://docs.microsoft.com/powershell/module/exchange/get-spoofmailreport)最多显示 90 天的数据。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **安全仪表板页面** ，请使用 <https://protection.office.com/searchandinvestigation/dashboard> 。

  可以从安全与合规中心中的多个仪表板查看&见解。 无论你正在查看哪个仪表板，见解都提供相同的详细信息，并允许你快速执行相同的任务。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - **组织管理**
  - **安全管理员**
  - **安全读者**
  - **全局阅读器**

  有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

  注意：将用户添加到 Microsoft 36 & 5 管理中心的相应 Azure Active Directory 角色会为用户提供安全与合规中心中所需的权限以及 Microsoft 365 中其他功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

- 在 Microsoft Defender for Office 365 中的反网络钓鱼策略中启用和禁用欺骗智能。 默认情况下启用欺骗智能。 有关详细信息，请参阅在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置防钓鱼策略。

- 若要使用欺骗智能监视和管理向您发送未经身份验证的邮件的发件人，请参阅 [在 Microsoft 365](learn-about-spoof-intelligence.md)中配置欺骗智能。

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>在安全与合规中心&欺骗智能见解

1. 在安全&合规中心，转到 **"威胁管理** \> **仪表板"。**

2. 在 **"Insights"** 行中，查找以下项目之一：

   - **过去七天内可能** 欺骗的域：此见解指示在默认情况下 (启用欺骗智能) 。
   - **启用欺骗** 保护：此见解指示已禁用欺骗智能，单击该见解可启用欺骗智能。

3. 仪表板上的见解显示如下所示的信息：

   ![欺骗智能见解的屏幕截图](../../media/28aeabac-c1a1-4d16-9fbe-14996f742a9a.png)

   此见解有两种模式：

   - **见解模式**：如果启用了欺骗智能，该见解将展示过去七天内我们的欺骗智能功能所影响的邮件数。
   - **如果模式：** 如果禁用欺骗智能，则见解将展示过去七天内我们的欺骗智能功能将影响的邮件数。

   无论使用哪种方式，在见解中显示的欺骗性域都分为两类： **可疑** 域 **和非可疑域**。

   - **可疑域** 包括：

     - 高可信度欺骗：根据历史发送模式和域信誉分数，我们高度确信这些域是欺骗的，并且来自这些域的邮件更有可能是恶意邮件。

     - 中等可信度欺骗：根据历史发送模式和域信誉分数，我们确信这些域是欺骗的，并且从这些域发送的邮件是合法的。 在此类别中，误报的可能性大于高可信度欺骗。

   **非可疑域**：域未通过显式电子邮件身份验证检查 [SPF、DKIM](how-office-365-uses-spf-to-prevent-spoofing.md)和 [DMARC](use-dmarc-to-validate-email.md)) 。 [](use-dkim-to-validate-outbound-email.md) 但是，域通过隐式电子邮件身份验证检查 ([复合身份验证](email-validation-and-authentication.md#composite-authentication)) 。 因此，未对邮件执行反欺骗操作。

### <a name="view-detailed-information-about-suspicious-domains-from-the-spoof-intelligence-insight"></a>从欺骗智能见解查看有关可疑域的详细信息

1. 在"欺骗智能见解"上，单击" **可疑** 域或非 **可疑** 域"以转到" **欺骗智能见解** "页。 " **欺骗智能见解** "页包含以下信息：

   - **欺骗域**：电子邮件客户端的"发送"框中显示的欺骗用户的域。  此地址也称为地址 `5322.From` 。
   - **基础结构**：也称为发送 _基础结构_。 反向 DNS 查找中的域 (PTR 记录) 源电子邮件服务器的 IP 地址。 如果源 IP 地址没有 PTR 记录，则发送基础结构标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。
   - **邮件计数**：过去 7 天内从发送基础结构发送到包含指定欺骗域的组织的邮件数。
   - **Last seen**： The last date when a message was received from the sending infrastructure that contains the spoofed domain.
   - **欺骗类型**：此值为 **External。**
   - **允许欺骗？：** 你在此处看到的值是：
     - **是**：允许来自欺骗用户域和发送基础结构组合的邮件，并且不会被视为欺骗电子邮件。
     - **否**：来自欺骗用户域和发送基础结构组合的邮件标记为欺骗邮件。 操作由默认防钓鱼策略或自定义防钓鱼策略控制， (默认值为"将邮件移动到垃圾邮件"文件夹) 。 

     有关详细信息，请参阅在 [Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置防钓鱼策略。

2. 在列表中选择一个项目，以查看有关在飞出中的域/发送基础结构对的详细信息。 这些信息包括：
   - 我们捕获此原因的原因。
   - 需要执行哪些工作。
   - 域摘要。
   - 有关发件人的 WhoIs 数据。
   - 我们在租户中看到的来自同一发件人的类似邮件。

   在此处，还可以选择从允许欺骗发件人允许列表中添加或删除域/发送基础结构对。  只需相应地设置切换。

   !["欺骗智能见解详细信息"窗格中域的屏幕截图](../../media/03ad3e6e-2010-4e8e-b92e-accc8bbebb79.png)

### <a name="adding-a-domain-to-the-allowed-to-spoof-list"></a>将域添加到允许欺骗列表

从欺骗智能见解向允许欺骗列表添加域仅允许欺骗域 *和发送基础结构* 的组合。 它不允许来自任何来源的欺骗域的电子邮件，也不允许来自任何域的发送基础结构的电子邮件。

例如，允许以下域进入允许欺骗列表：

- **域**：gmail.com
- **基础结构**：tms.mx.com

仅允许来自该域/发送基础结构对的电子邮件欺骗。 不允许其他发件人gmail.com欺骗邮件。 来自其他域中的邮件tms.mx.com欺骗智能进行检查。

## <a name="related-topics"></a>相关主题

[Microsoft 365 中的反欺骗保护](anti-spoofing-protection.md)
