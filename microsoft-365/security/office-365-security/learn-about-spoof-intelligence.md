---
title: 配置欺骗智能
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: 978c3173-3578-4286-aaf4-8a10951978bf
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解 Exchange Online Protection (EOP) 中的欺骗智能，您可以在其中允许或阻止特定的欺骗发件人。
ms.openlocfilehash: 603aeb35241f9808561593afa69b3b9ce7193fb0
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760526"
---
# <a name="configure-spoof-intelligence-in-eop"></a>在 EOP 中配置欺骗智能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在具有 Exchange Online 邮箱的 Microsoft 365 组织或独立 Exchange Online Protection (EOP) 组织中，自 2018 年 10 日起，入站电子邮件将自动受到 EOP 的欺骗保护。 EOP 使用欺骗智能作为组织抵御网络钓鱼的整体防御的一部分。 有关详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。

当发件人欺骗电子邮件地址时，他们可能是组织某个域中的用户，或者是向组织发送电子邮件的外部域中的用户。 需要阻止欺骗发件人发送垃圾邮件或网络钓鱼电子邮件的攻击者。 但在某些情况下，合法发件人是欺骗的。 例如：

- 欺骗内部域的合法方案：

  - 第三方发件人使用您的域向自己的员工发送批量邮件，进行公司投票。
  - 外部公司代表你生成并发送广告或产品更新。
  - 助理需要定期为组织内部的另一个人发送电子邮件。
  - 内部应用程序发送电子邮件通知。

- 欺骗外部域的合法方案：

  - 发件人位于一个邮件列表 (也称为讨论列表) ，邮件列表将原始发件人的电子邮件中继到邮件列表上的所有参与者。
  - 外部公司代表另一家公司发送电子邮件 (例如自动报告或软件即服务公司) 。

欺骗智能（特别是默认的 (和仅) 欺骗智能策略）有助于确保合法发件人发送的欺骗性电子邮件不会在 EOP 垃圾邮件筛选器或外部电子邮件系统中捕获，同时保护用户免受垃圾邮件或网络钓鱼攻击。

可以在安全与合规 &中心或 PowerShell (Exchange Online PowerShell 中管理具有 Exchange Online 邮箱的 Microsoft 365 组织的欺骗智能;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。 若要直接转到" **防钓鱼"** 页面，请使用 <https://protection.office.com/antiphishing> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要修改欺骗智能策略或启用或禁用欺骗智能，你需要是组织 **管理或****安全** 管理员角色组的成员。
  - 若要对欺骗智能策略进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关我们推荐的欺骗智能设置，请参阅 [EOP 默认防钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>使用安全&合规中心管理欺骗性发件人

> [!NOTE]
> 如果你有 Microsoft 365 企业版 E5 订阅或单独购买了适用于 Office 365 的 Microsoft Defender 加载项，则还可以通过欺骗智能见解管理欺骗域的[发件人。](walkthrough-spoof-intelligence-insight.md)

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **"反垃圾邮件设置** "页上，单击 ![ "展开"图标 ](../../media/scc-expand-icon.png) 以展开 **欺骗智能策略**。

   ![选择欺骗智能策略](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 选择下列选项之一：

   - **查看新发件人**
   - **向我显示已审阅的发件人**

4. 在 **"确定是否允许这些** 发件人欺骗出现的用户飞出"中，选择以下选项卡之一：

   - **您的域**：发件人欺骗内部域中的用户。
   - **外部域**：发件人欺骗外部域中的用户。

5. 单击 ![ " ](../../media/scc-expand-icon.png) 允许欺骗 **？"列中的"展开"** 图标。 选择 **"** 是"以允许欺骗性发件人，或选择" **否** "将邮件标记为欺骗邮件。 该操作由默认防钓鱼策略或自定义防钓鱼策略控制， (默认值为"将邮件移动到垃圾邮件"文件夹) 。  有关详细信息，请参阅反 [网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

   ![显示欺骗性发件人飞出以及是否允许发件人欺骗的屏幕截图](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   您看到的列和值如下列表所示：

   - **欺骗用户**：被欺骗的用户帐户。 这是发件人地址中的邮件 (也称为) `5322.From` 客户端中显示的地址。 SPF 不检查此地址的有效性。

     - 在 **"域** "选项卡上，值包含单个电子邮件地址，或者如果源电子邮件服务器欺骗多个用户帐户，则它包含 **多个用户帐户**。

     - 在 **"外部域** "选项卡上，值包含欺骗用户的域，而不是完整电子邮件地址。

   - **发送基础结构**：在反向 DNS (PTR 记录) 源电子邮件服务器的 IP 地址的域。 如果源 IP 地址没有 PTR 记录，则发送基础结构标识为 \<source IP\> /24 (例如，192.168.100.100/24) 。

     有关邮件源和邮件发件人的信息，请参阅 [电子邮件标准概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

   - **邮件数**：过去 30 天内从发送基础结构发送到包含指定欺骗发件人或发件人的组织的邮件数。

   - **用户投诉数**：用户最近 30 天内针对此发件人提出投诉。 投诉通常采用向 Microsoft 提交垃圾邮件的形式。

   - **身份验证结果**：下列值之一：
      - **已通过**：发件人已通过 SPF 或 DKIM (发件人电子邮件) 。
      - **失败**：发件人未通过 EOP 发件人身份验证检查。
      - **未知**：这些检查的结果未知。

   - **决策集：** 显示谁确定发送基础结构是否允许欺骗用户：
       - **欺骗智能策略** (自动) 
       - **管理员** (手动) 

   - **上次看到** 时间：上次从包含欺骗用户的发送基础结构接收邮件的日期。

   - **允许欺骗？：** 你在此处看到的值是：
     - **是**：允许来自欺骗用户和发送基础结构组合的邮件，并且不会被视为欺骗电子邮件。
     - **否**：来自欺骗用户和发送基础结构组合的邮件被标记为欺骗邮件。 该操作由默认防钓鱼策略或自定义防钓鱼策略控制， (默认值为"将邮件移动到垃圾邮件"文件夹) 。  有关详细信息，请参阅下一节。

     - **某些用户****("** 域"选项卡) ：发送基础结构正在欺骗多个用户，其中一些欺骗用户被允许，另一些则不允许。 使用 **"详细** "选项卡查看特定地址。

6. 在页面底部，单击“保存”。

## <a name="use-powershell-to-manage-spoofed-senders"></a>使用 PowerShell 管理欺骗性发件人

若要查看欺骗智能中允许和阻止的发件人，请使用以下语法：

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

此示例返回有关允许欺骗域中用户的所有发件人的详细信息。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

有关语法和参数的详细信息，请参阅[Get-PhishFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)

若要在欺骗智能中配置允许和阻止的发件人，请按照以下步骤操作：

1. 将 **Get-PhishFilterPolicy** cmdlet 的输出写入 CSV 文件，捕获检测到的欺骗发件人的当前列表：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. 编辑 CSV 文件以添加或修改 **SpoofedUser** (电子邮件地址) **AllowedToSpoof** (是或否) 值。 保存文件、读取文件，将内容存储为名为 `$UpdateSpoofedSenders` ：

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 使用 `$UpdateSpoofedSenders` 变量配置欺骗智能策略：

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

有关语法和参数的详细信息，请参阅 [Set-PhishFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)。

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>使用安全&合规中心配置欺骗智能

反网络钓鱼策略中的欺骗设置中描述了欺骗 [智能的配置选项](set-up-anti-phishing-policies.md#spoof-settings)。

可以在默认反网络钓鱼策略和自定义策略中配置欺骗智能设置。 有关基于订阅的说明，请参阅下列主题之一：

- [在 EOP 中配置防钓鱼策略](configure-anti-phishing-policies-eop.md)。

- 在 Microsoft Defender for [Office 365 中配置防钓鱼策略](configure-atp-anti-phishing-policies.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已使用允许和不允许欺骗的发件人配置欺骗智能，以及是否配置了欺骗智能设置，请使用下列任一步骤：

- 在安全&合规中心，转到"威胁管理策略反 \>  \> **垃圾邮件** \>  \>  \> 展开欺骗智能策略"，选择"显示我审查的发件人"，选择"你的域或外部域"选项卡，并验证发件人的"允许欺骗？"值。

- 在 PowerShell 中，运行以下命令以查看允许和不允许欺骗的发件人：

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- 在 PowerShell 中，运行以下命令，将所有欺骗性发件人的列表导出到 CSV 文件：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- 在安全&合规中心，转到"**威胁** 管理策略防钓鱼"或"ATP 防钓鱼"，然后执行 \>  \> 下列任一步骤：   

  - 从列表中选择策略。 在出现的标注中，验证"欺骗" **部分** 的值。
  - 单机“**默认策略**”。 在出现的标注中，验证"欺骗" **部分** 的值。

- 在 Exchange Online PowerShell 中，替换为 Office365"默认反Phish"或自定义策略的名称，然后运行以下命令 \<Name\> 来验证设置：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableSpoofIntelligence,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>管理欺骗和网络钓鱼的其他方法

避免欺骗和网络钓鱼防护。 以下相关方法可检查发件人欺骗你的域，并有助于防止他们破坏组织：

- 检查 **欺骗邮件报告**。 你可以经常使用此报告来查看并帮助管理欺骗的发件人。 有关信息，请参阅 [欺骗检测报告](view-email-security-reports.md#spoof-detections-report)。

- 查看你的发件人策略框架 (SPF) 配置。 若要了解 SPF 的快速简介及其快速配置方法，请参阅[在 Microsoft 365 中设置 SPF 以防欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 有关 Office 365 如何使用 SPF 的更深入了解，或者有关故障排除或非标准部署（如混合部署）的信息，请开始阅读[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)。

- 查看你的域密钥标识的邮件 (DKIM) 配置。 除了使用 SPF 和 DMARC 外，还应使用 DKIM 来帮助阻止攻击者发送看起来好像来自你的域的邮件。 你可以使用 DKIM 将数字签名添加到电子邮件的邮件头中。 有关信息，请参阅 [使用 DKIM 验证从 Office 365](use-dkim-to-validate-outbound-email.md)中的自定义域发送的出站电子邮件。

- 查看基于域的邮件身份验证、报告和一致性 (DMARC) 配置。 实现使用 SPF 和 DKIM 的 DMARC 可以针对欺骗和钓鱼电子邮件提供额外的保护。 DMARC 可帮助接收邮件系统确定如何处理从你的域发送且未通过 SPF 或 DKIM 检查的邮件。 有关信息，请参阅 [使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。
