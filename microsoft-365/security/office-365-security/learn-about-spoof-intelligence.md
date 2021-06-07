---
title: 欺骗智能见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 EOP Exchange Online Protection (中的欺骗智能) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 45ecbe68072441b40477d1b27953b957aeffa9e3
ms.sourcegitcommit: f3d1009840513703c38bab99a6e13a3656eae5ee
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/07/2021
ms.locfileid: "52793168"
---
# <a name="spoof-intelligence-insight-in-eop"></a>EOP 中的欺骗智能见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文中所述的功能在预览版中，可能会更改，并且并非在所有组织中都可用。 如果你的组织没有本文中所述的功能，请参阅使用 EOP 中的欺骗智能策略和欺骗智能见解管理欺骗发件人中的旧版欺骗 [管理体验](walkthrough-spoof-intelligence-insight.md)。

在Microsoft 365邮箱位于 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中Exchange Online，入站电子邮件将自动防止欺骗。 EOP **使用欺骗智能** 作为组织防御网络钓鱼的整体防御的一部分。 有关详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。

当发件人欺骗电子邮件地址时，他们显示为组织某个域中的用户，或者是向组织发送电子邮件的外部域中的用户。 需要阻止欺骗发件人发送垃圾邮件或钓鱼电子邮件的攻击者。 但在某些情况下，合法发件人存在欺骗行为。 例如：

- 欺骗内部域的合法方案：
  - 第三方发件人使用您的域向您自己的员工发送批量邮件，进行公司投票。
  - 外部公司代表你生成并发送广告或产品更新。
  - 助理需要定期为组织内部的另一个人发送电子邮件。
  - 内部应用程序发送电子邮件通知。

- 欺骗外部域的合法方案：
  - 发件人位于一个邮件列表 (也称为讨论列表) ，邮件列表将原始发件人的电子邮件中继到邮件列表上的所有参与者。
  - 外部公司代表另一家公司发送电子邮件 (例如自动报告或软件即服务公司) 。

您可以使用安全 &合规中心中的欺骗智能见解，从未通过 SPF、DKIM 或 DMARC 检查) 的域中快速识别合法向您发送未经身份验证的电子邮件 (邮件的欺骗性发件人，并手动允许这些发件人。

通过允许已知发件人从已知位置发送欺骗邮件，你可以减少误报 (标记为错误) 。 通过监视允许的欺骗发件人，你可以提供额外的安全层，以防止不安全的邮件到达你的组织。

同样，你可以查看欺骗智能允许的欺骗性发件人，并手动阻止这些发件人获得欺骗智能见解。

本文的其余部分介绍如何在安全与合规中心和 PowerShell & (Exchange Online PowerShell 中为邮箱位于 Exchange Online 中的 Microsoft 365 组织使用欺骗智能Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。

> [!NOTE]
>
> - 欺骗智能见解中只显示欺骗智能检测到的欺骗发件人。 当你替代见解中的允许或阻止裁定时，欺骗性发件人将成为一个手动允许或阻止条目，该条目仅出现在租户允许/阻止列表中的"欺骗"选项卡上。 还可以在欺骗智能检测到欺骗发件人之前，手动为这些发件人创建允许或阻止条目。 有关详细信息，请参阅[管理 EOP 中的租户允许/阻止列表](tenant-allow-block-list.md)。
>
> - 租户允许/阻止列表中的欺骗智能见解和"欺骗"选项卡取代了安全与合规中心的反垃圾邮件策略页面上提供的欺骗智能&功能。
>
>- 欺骗智能见解显示 7 天的数据。 **Get-SpoofIntelligenceInsight** cmdlet 显示 30 天的数据。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到" **防钓鱼"页面** ，请使用 <https://protection.office.com/antiphishing> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要修改欺骗智能策略或启用或禁用欺骗智能，你需要是组织管理或安全 **管理员****角色组** 的成员。
  - 若要对欺骗智能策略进行只读访问，你需要是全局读者或安全 **读者角色组** 的成员。 

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：

  - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 在 EOP 和 Microsoft Defender for Office 365 中启用和禁用反网络钓鱼策略中的欺骗Office 365。 默认情况下启用欺骗智能。 有关详细信息，请参阅在[EOP](configure-anti-phishing-policies-eop.md)中配置防钓鱼策略或在 Microsoft Defender 中配置防钓鱼策略[Office 365。](configure-atp-anti-phishing-policies.md)

- 有关建议的欺骗智能设置，请参阅 [EOP 防钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-phishing-policy-settings)。

## <a name="open-the-spoof-intelligence-insight-in-the-security--compliance-center"></a>在安全与合规中心内打开&见解

1. 在安全&合规中心，转到"**威胁管理** \> **策略** \> **""防钓鱼"。**

2. 在主要的 **"反网络钓鱼"页面上**，欺骗智能见解有两种模式：

   - **见解模式**：如果启用了欺骗智能，该见解将展示过去七天内欺骗智能检测到的邮件数。
   - **如果模式 ：** 如果禁用欺骗智能，则见解将显示过去七天内欺骗智能检测到的邮件数。

   无论使用哪种方式，见解中显示的欺骗性域都分为两类： **可疑** 域 **和非可疑域**。

   - **可疑域** 包括：

     - 高可信度欺骗：根据历史发送模式和域的信誉分数，我们高度确信这些域是欺骗，并且来自这些域的邮件更有可能是恶意邮件。

     - 中等可信度欺骗：根据历史发送模式和域的信誉分数，我们确信这些域是欺骗的，并且从这些域发送的邮件是合法的。 在此类别中，误报的可能性大于高可信度欺骗。

   **非可疑域**：域未通过显式电子邮件身份验证检查 [SPF、DKIM](how-office-365-uses-spf-to-prevent-spoofing.md)和 [DMARC](use-dmarc-to-validate-email.md)) 。 [](use-dkim-to-validate-outbound-email.md) 但是，域已通过隐式电子邮件身份验证检查， ([身份验证) 。](email-validation-and-authentication.md#composite-authentication) 因此，未对邮件执行反欺骗操作。

### <a name="view-information-about-spoofed-messages"></a>查看有关欺骗邮件的信息

在"欺骗智能见解"上，单击" **可疑** 域或非 **可疑** 域"以转到" **欺骗智能见解"** 页面。 页面包含以下信息：

- **欺骗性** 域：电子邮件客户端的"来源"框中显示的欺骗用户的域。  此地址也称为 `5322.From` 地址。
- **基础结构**：也称为发送 _基础结构_。 这将是以下值之一：
  - 反向 DNS 查找中的域 (源) IP 地址的 PTR 记录。
  - 如果源 IP 地址没有 PTR 记录，则发送基础结构标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。
- **邮件计数**：过去 7 天内从欺骗域和发送基础结构组合发送到组织的邮件数量。
- **上次看到** 时间：从包含欺骗域的发送基础结构接收邮件的最后日期。
- **欺骗类型**：下列值之一：
  - **内部**：欺骗性发件人位于组织所属的域中， ([接受的) 。](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
  - **外部**：欺骗性发件人位于外部域中。
- **允许欺骗**：值取决于你在见解上 **单击了"** 可疑域"还是 **"非可疑** 域"：
  - **可疑域**：**允许欺骗的值** 始终为 **"否"。** 来自欺骗性域和发送基础结构组合的邮件被欺骗智能标记为错误。 对欺骗邮件采取的操作由默认反网络钓鱼策略或自定义防钓鱼策略控制 (默认值为"将邮件移动到垃圾邮件文件夹") 。  有关详细信息，请参阅 Configure [anti-phishing policies in Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)。
  - **非可疑域**：**允许欺骗的值** 始终为 **"是"。** 来自欺骗性域和发送基础结构组合的邮件被欺骗智能标记为良好。

您可以单击所选列标题对结果进行排序。

若要筛选结果，可以使用以下选项：

- 使用 **"筛选欺骗域** "框输入以逗号分隔的欺骗域值列表以筛选结果。
- 使用 **"筛选器基础结构** "框输入以逗号分隔的基础结构值列表以筛选结果。
- 单击筛选器 **按钮** 以按欺骗类型 **筛选结果**。

### <a name="view-details-about-spoofed-messages"></a>查看有关欺骗邮件的详细信息

选择列表中的某个项以查看详细信息。 将出现一个包含以下信息和功能的飞出图：

- **允许欺骗**：使用此开关替代欺骗智能裁定：
  - 如果你最初在见解 **中选择了可疑****域，则**"允许欺骗"已关闭。 若要将其打开（它将条目从欺骗智能见解移动到租户允许/阻止列表作为欺骗允许条目）中，将开关滑动到"打开"： ![ 打开。 ](../../media/scc-toggle-on.png)
  - 如果你最初在 **见解中选择了"非可疑** 域 **"，则** "允许欺骗"将打开。 若要将其关闭，从而将条目从欺骗智能见解移到租户允许/阻止列表作为欺骗的阻止条目，将开关滑动到关闭： ![ 切换关闭 ](../../media/scc-toggle-off.png) 。

- 我们为什么捕获到此。
- 需要执行哪些工作。
- 包含主要欺骗智能页面中大部分相同信息的域摘要。
- WhoIs 有关发件人的数据。
- 我们在租户中看到的来自同一发件人的类似邮件。

### <a name="about-allowed-spoofed-senders"></a>关于允许的欺骗发件人

在欺骗智能见解的非可疑域中允许的欺骗发件人或手动更改为允许欺骗的可疑域中的阻止发件人仅允许来自欺骗域和发送基础结构组合的邮件。  它不允许来自任何来源的欺骗性域的电子邮件，也不允许来自任何域的发送基础结构的电子邮件。

例如，允许以下欺骗性发件人欺骗：

- **域**： gmail.com
- **基础结构**：tms.mx.com

仅允许来自该域/发送基础结构对的电子邮件欺骗。 不会自动允许其他发件人 gmail.com 欺骗邮件。 来自其他域中发件人的邮件 tms.mx.com 欺骗智能仍在检查，并且可能会阻止。

## <a name="use-the-spoof-intelligence-insight-in-exchange-online-powershell-or-standalone-eop-powershell"></a>在 PowerShell 或独立 EOP PowerShell Exchange Online欺骗智能见解

在 PowerShell 中，使用 **Get-SpoofIntelligenceInsight** cmdlet 查看欺骗智能检测到的允许和阻止的欺骗发件人。  若要手动允许或阻止欺骗的发件人，你需要使用 **New-TenantAllowBlockListSpoofItems** cmdlet。 有关详细信息，请参阅使用 [PowerShell 配置租户允许/阻止列表](tenant-allow-block-list.md#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-the-tenant-allowblock-list)。

若要查看欺骗智能见解中的信息，请运行以下命令：

```powershell
Get-SpoofIntelligenceInsight
```

有关语法和参数的详细信息，请参阅 [Get-SpoofIntelligenceInsight](/powershell/module/exchange/get-spoofintelligenceinsight)。

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>管理欺骗和网络钓鱼的其他方法

对于欺骗和网络钓鱼防护，要多下努力。 以下相关方法可检查欺骗你的域的发件人，并有助于防止他们破坏你的组织：

- 检查 **欺骗邮件报告**。 你可以经常使用此报告来查看并帮助管理欺骗性发件人。 有关信息，请参阅 [欺骗检测报告](view-email-security-reports.md#spoof-detections-report)。

- 查看你的发件人策略框架 (SPF) 配置。 若要了解 SPF 的快速简介及其快速配置方法，请参阅[在 Microsoft 365 中设置 SPF 以防欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 有关 Office 365 如何使用 SPF 的更深入了解，或者有关故障排除或非标准部署（如混合部署）的信息，请开始阅读[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)。

- 查看你的域密钥识别邮件 (DKIM) 配置。 除了 SPF 和 DMARC 之外，还应使用 DKIM 来帮助阻止攻击者发送看起来来自你的域的邮件。 你可以使用 DKIM 将数字签名添加到电子邮件的邮件头中。 有关信息，请参阅[使用 DKIM 验证从](use-dkim-to-validate-outbound-email.md)自定义域发送的出站Office 365。

- 查看基于域的邮件身份验证、报告和一致性 (DMARC) 配置。 实现使用 SPF 和 DKIM 的 DMARC 可以针对欺骗和钓鱼电子邮件提供额外的保护。 DMARC 可帮助接收邮件系统确定如何处理从你的域发送且未通过 SPF 或 DKIM 检查的邮件。 有关信息，请参阅[使用 DMARC 验证电子邮件Office 365。](use-dmarc-to-validate-email.md)
