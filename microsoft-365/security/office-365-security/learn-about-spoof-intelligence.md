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
description: 管理员可以了解 Exchange Online Protection (EOP) 中的欺骗智能，您可以在其中允许或阻止特定的欺骗性发件人。
ms.openlocfilehash: 9168d43e6e5544ad3454729afc8140642deba0ef
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572725"
---
# <a name="configure-spoof-intelligence-in-eop"></a>在 EOP 中配置欺骗智能

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


在使用 Exchange Online 或独立 Exchange online Protection 中的邮箱的 Microsoft 365 组织中 (EOP) 不含 Exchange Online 邮箱的组织中，入站电子邮件将自动抵御 EOP 到10月2018的欺骗。 EOP 在组织对网络钓鱼的整体防护过程中使用欺骗智能。 有关详细信息，请参阅 [EOP 中的反欺骗保护](anti-spoofing-protection.md)。

当发件人假冒电子邮件地址时，它们似乎是组织的某个域中的用户，或者是外部域中向您的组织发送电子邮件的用户。 欺骗发件人以发送垃圾邮件或网络钓鱼电子邮件的攻击者需要阻止。 但在某些情况下，合法发件人是欺骗的。 例如：

- 欺骗性内部域的合法方案：

  - 第三方发件人使用您的域向您自己的员工发送批量邮件，以进行公司投票。
  - 外部公司代表你生成并发送广告或产品更新。
  - 助理定期需要为组织中的其他人发送电子邮件。
  - 内部应用程序发送电子邮件通知。

- 欺骗外部域的合法方案：

  - 发件人位于邮件列表中 (也称为讨论列表) ，并且邮件列表将电子邮件从原始发件人中继到邮件列表中的所有参与者。
  - 外部公司代表另一个公司发送电子邮件 (例如，自动报告或作为服务的软件公司) 。

欺骗智能，尤其是默认 (并且仅) 欺骗智能策略，可帮助确保由合法发件人发送的欺骗电子邮件不会在 EOP 垃圾邮件筛选器或外部电子邮件系统中受到攻击，同时保护您的用户免受垃圾邮件或网络钓鱼攻击。

您可以使用 Exchange Online 中的邮箱管理安全 & 合规中心或 PowerShell (Exchange Online PowerShell 中的 Microsoft 365 组织的欺骗智能;没有 Exchange Online 邮箱) 组织的独立 EOP PowerShell。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。 若要直接转到 " **反钓鱼** " 页面，请使用 <https://protection.office.com/antiphishing> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您需要在安全 & 合规性中心中分配权限，然后才能执行本文中的过程：
  - 若要修改欺骗性智能策略或启用或禁用欺骗智能，您需要是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。
  - 若要对欺骗智能策略进行只读访问，您需要是 **全局读取器** 或 **安全读者** 角色组的成员。

  有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 将用户添加到 Microsoft 365 管理中心中对应的 Azure Active Directory 角色，用户可为用户提供安全 & 合规性中心的必需权限 _以及_ Microsoft 365 中其他功能的权限。 有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 "**仅查看组织管理**" 角色组也提供了对功能的只读访问权限。

- 有关我们推荐的欺骗性智能设置，请参阅 [EOP 默认反网络钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>使用安全 & 合规性中心管理欺骗性发件人

> [!NOTE]
> 如果你拥有 Microsoft 365 企业版 E5 订阅或单独购买了 Microsoft Defender for Office 365 加载项，则还可以管理通过 [欺骗智能洞察力](walkthrough-spoof-intelligence-insight.md)欺骗你的域的发件人。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 " **反垃圾邮件设置** " 页上，单击 " ![ 展开图标" ](../../media/scc-expand-icon.png) 以展开 " **欺骗智能策略**"。

   ![选择欺骗性智能策略](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 进行下列选择之一：

   - **查看新发件人**
   - **显示已审阅的发件人**

4. 在 **决定是否允许这些发件人哄骗** 出现的用户浮出控件时，选择下列选项卡之一：

   - **您的域**：发件人哄骗内部域中的用户。
   - **外部域**：发件人哄骗外部域中的用户。

5. 单击 ![ ](../../media/scc-expand-icon.png) " **允许欺骗"** 列中的 "展开图标"。 选择 **"是"** 允许欺骗发件人，或选择 " **否** " 将邮件标记为 "欺骗"。 该操作由默认的反网络钓鱼策略或自定义反网络钓鱼策略控制 (默认值为 " **将邮件移动到垃圾邮件" 文件夹**) 。 有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

   ![显示欺骗性发件人浮出控件以及是否允许发件人欺骗的屏幕截图](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   下表中说明了您看到的列和值：

   - **欺骗用户**：被欺骗的用户帐户。 这是发件人地址中的邮件发件人 (也称为 `5322.From` 在电子邮件客户端中显示的地址) 。 SPF 不会检查此地址的有效性。

     - 在 " **您的域** " 选项卡上，值包含一个电子邮件地址，或者如果源电子邮件服务器正在哄骗多个用户帐户，则它包含 **多** 个用户帐户。

     - 在 " **外部域** " 选项卡上，值包含欺骗用户的域，而不是完整的电子邮件地址。

   - **发送基础结构**：当源电子邮件服务器的 IP 地址的反向 DNS 查找 (PTR 记录) 中找到的域，或者如果源没有 PTR 记录，则为 IP 地址。

     有关邮件源和邮件发件人的详细信息，请参阅 [电子邮件标准概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

   - **邮件** 数：在最近30天内包含指定的欺骗发件人或发件人的组织的发送方结构中的邮件数。

   - **用户投诉**：在过去30天内，用户对此发件人存档的投诉。 投诉通常是提交给 Microsoft 的垃圾邮件的形式。

   - **身份验证结果**：下列值之一：

      - 已 **传递**：发件人的发件人电子邮件身份验证检查 (SPF 或 DKIM) 。
      - **失败**：发件人失败 EOP 发件人身份验证检查。
      - **未知**：这些检查的结果不是已知的结果。

   - **决策集依据**：显示确定是否允许发送基础结构欺骗用户的用户：

       - **欺骗性智能策略** (自动) 
       - **管理员** (手动) 

   - **上次查看** 时间：从包含欺骗用户的发送基础结构收到邮件的最后日期。

   - 是否 **允许欺骗？**：您在此处看到的值是：

     - **是**：允许欺骗用户和发送基础结构组合的邮件不会被视为欺骗电子邮件。

     - **否**：来自欺骗用户和发送基础结构组合的邮件被标记为欺骗。 该操作由默认的反网络钓鱼策略或自定义反网络钓鱼策略控制 (默认值为 " **将邮件移动到垃圾邮件" 文件夹**) 。 有关详细信息，请参阅下一节。

     - **有些用户** 只 (**域** 选项卡中) ：发送基础结构是哄骗多个用户，其中某些欺骗用户是允许的，其他是不允许的。 使用 " **详细信息** " 选项卡查看特定地址。

6. 在页面底部，单击“保存”。

## <a name="use-powershell-to-manage-spoofed-senders"></a>使用 PowerShell 管理欺骗性发件人

若要在欺骗智能中查看允许和阻止的发件人，请使用以下语法：

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

本示例返回有关允许在您的域中欺骗用户的所有发件人的详细信息。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

有关语法和参数的详细信息，请参阅 [将 get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)。

若要在欺骗智能中配置允许和阻止的发件人，请按照以下步骤操作：

1. 通过将 **将 get-phishfilterpolicy** cmdlet 的输出写入 CSV 文件，捕获当前检测到的欺骗发件人列表：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. 编辑 CSV 文件，以添加或修改 **SpoofedUser** (电子邮件地址) 和 **AllowedToSpoof** (是或否) 值。 保存文件，读取文件，并将内容存储为名为的变量 `$UpdateSpoofedSenders` ：

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 使用 `$UpdateSpoofedSenders` 变量配置欺骗性智能策略：

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

有关语法和参数的详细信息，请参阅 [将 get-phishfilterpolicy](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)。

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>使用安全 & 合规中心配置欺骗性智能

欺骗性智能的配置选项在 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)中进行了说明。

您可以在默认的反网络钓鱼策略中以及自定义策略中配置欺骗智能设置。 有关基于你的订阅的说明，请参阅以下主题之一：

- [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。

- [在 Microsoft Defender For Office 365 中配置反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已使用允许且不允许欺骗的发件人配置了欺骗智能，并且您已配置了欺骗性智能设置，请执行以下任一步骤：

- 在安全 & 合规性中心中，转 **到威胁管理** \> **策略** \> **反垃圾邮件** \> 展开 **欺骗智能策略** \> 选择 " **显示我已审阅的发件人** \> "。选中 " **您的域** 或 **外部域** " 选项卡，并验证发件人的 "是否 **允许欺骗？** " 值。

- 在 PowerShell 中，运行以下命令以查看允许且不允许欺骗的发件人：

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- 在 PowerShell 中，运行以下命令以将所有欺骗性发件人的列表导出到 CSV 文件：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- 在安全 & 合规性中心中，转到 "**威胁管理** \> **策略**" " \> **反网络钓鱼**" 或 " **ATP 反网络钓鱼**"，然后执行以下任一步骤：  

  - 从列表中选择一个策略。 在出现的浮出控件中，验证 **欺骗** 部分中的值。
  - 单击 " **默认策略**"。 在出现的浮出控件中，验证 **欺骗** 部分中的值。

- 在 Exchange Online PowerShell 中，将替换 \<Name\> 为 Office365 AntiPhish 默认值或自定义策略的名称，然后运行以下命令来验证设置：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>管理欺骗和网络钓鱼的其他方法

请这有关哄骗和网络钓鱼防护的信息。 下面是检查发件人欺骗你的域并帮助防止其损坏组织的相关方法：

- 检查 **欺骗邮件报告**。 您可以经常使用此报告查看和帮助管理欺骗性发件人。 有关信息，请参阅 [欺骗检测报告](view-email-security-reports.md#spoof-detections-report)。

- 查看您的发件人策略框架 (SPF) 配置。 若要了解 SPF 的快速简介及其快速配置方法，请参阅[在 Microsoft 365 中设置 SPF 以防欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 有关 Office 365 如何使用 SPF 的更深入了解，或者有关故障排除或非标准部署（如混合部署）的信息，请开始阅读[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)。

- 查看域密钥识别的邮件 (DKIM) 配置。 除了 SPF 和 DMARC，还应使用 DKIM，以帮助防止攻击者发送看上去来自您的域的邮件。 你可以使用 DKIM 将数字签名添加到电子邮件的邮件头中。 有关信息，请参阅 [使用 DKIM 验证从您的自定义域在 Office 365 中发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。

- 查看基于域的邮件身份验证、报告和一致性 (DMARC) 配置。 实现使用 SPF 和 DKIM 的 DMARC 可以针对欺骗和钓鱼电子邮件提供额外的保护。 DMARC 可帮助接收邮件系统确定如何处理从你的域发送且未通过 SPF 或 DKIM 检查的邮件。 有关信息，请参阅 [使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。
