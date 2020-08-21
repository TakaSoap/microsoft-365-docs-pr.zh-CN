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
description: 管理员可以了解 Exchange Online Protection 电子邮件中的欺骗 (EOP) ，您可在其中允许或阻止特定的欺骗性发件人。
ms.openlocfilehash: 66cfc419c3e2f3a5dd8ad45cdb9fe651b613679b
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826573"
---
# <a name="configure-spoof-intelligence-in-eop"></a>在 EOP 中配置欺骗智能

在具有 Exchange Online 邮箱的 Microsoft 365 组织中或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，从 2018 年 10 月起，EOP 将自动防止 EOP 欺骗。 EOP 使用欺骗智能作为组织整体防御网络钓鱼的一部分。 有关详细信息，请参阅 [EOP 中的防欺骗保护](anti-spoofing-protection.md)。

如果发件人欺骗了电子邮件地址，则显示为某个组织的域中的用户，或者是外部域中向您组织发送电子邮件的用户。 需要阻止欺骗发件人发送垃圾邮件或网络钓鱼电子邮件的攻击者。 但是，在某些场景中，合法发件人是欺骗性发件人。 例如：

- 欺骗内部域的合法情形：

  - 第三方发件人使用您的域向你自己的员工发送批量邮件，进行公司轮询。
  - 外部公司代表你生成和发送广告或产品更新。
  - 助理定期需要向组织内的其他人发送电子邮件。
  - 内部应用程序发送电子邮件通知。

- 欺骗外部域的合法方案：

  - 发件人位于邮件列表 (也称为讨论列表) ，同时将来自原始发件人的电子邮件中继到邮件列表上的所有参与者。
  - 外部公司代表其他公司代表其他公司 (例如，自动报告或软件即服务服务公司发送) 。

欺骗智能，特别是 (（特别是) ）智能策略，有助于确保由合法发件人发送的欺骗性电子邮件不会被 EOP 垃圾邮件筛选器或外部电子邮件系统中泄连，同时保护用户以防你的用户受到垃圾邮件或网络钓鱼攻击。

你可以在安全& 合规中心，或在具有 Exchange Online 邮箱的 Microsoft 365 组织的 PowerShell (PowerShell 中管理欺骗智能;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。 若要直接转到 **"反网络钓鱼"页面，** 请使用 <https://protection.office.com/antiphishing> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 若要修改欺骗智能策略或者启用或禁用欺骗智能保护，你需要是以下角色组之一的成员：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 若要对欺骗智能策略进行只读访问，需要是以下角色之一的成员：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

- 有关我们推荐的欺骗智能设置， [请参阅 EOP 默认防钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

## <a name="use-the-security--compliance-center-to-manage-spoofed-senders"></a>使用安全&合规中心管理欺骗性发件人

> [!NOTE]
> 如果拥有 Microsoft 365 企业版 E5 订阅或已单独购买 Office 365 高级威胁防护 (Office 365 ATP) 加载项，则还可以通过欺骗智能见解来管理正在欺骗你的域的 [发件人](walkthrough-spoof-intelligence-insight.md)。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在" **反垃圾邮件设置"页面上** ，单击" ![ 展开"图标 ](../../media/scc-expand-icon.png) 以 **展开"欺骗"智能策略**。

   ![选择欺骗智能策略](../../media/anti-spam-settings-spoof-intelligence-policy.png)

3. 做出以下选择之一：

   - **查看新发件人**
   - **显示我已审阅的发件人**

4. 在 **"确定是否允许这些发件人"出现的** 浮出控件中，选择下列选项卡之一：

   - **您的域**：内部域中的发件人欺骗用户。
   - **外部域**：发件人欺骗外部域中的用户。

5. 单击 ![ "允许 ](../../media/scc-expand-icon.png) 欺骗 **"列中的"展开"** 图标。 选择 **"是** "允许欺骗性发件人，或者选择" **否** "将邮件标记为欺骗邮件。 此操作由默认的反网络钓鱼策略或自定义 ATP 反网络钓鱼策略 (默认值为将 **邮件移至垃圾邮件文件夹格式的**) 。 有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

   ![显示欺骗性发件人浮出控件以及是否允许发件人欺骗的屏幕截图](../../media/c0c062fd-f4a4-4d78-96f7-2c22009052bb.jpg)

   您看到的列和值如以下列表进行了说明：

   - **欺骗用户**：被欺骗的用户帐户。 这是在"发件人"地址中的邮件 (也称为 `5322.From` 电子邮件客户端) 中显示的地址。 SPF 不会检查此地址的有效性。

     - 在 **"域** "选项卡上，该值包含一个电子邮件地址，或者如果源电子邮件服务器正在欺骗多个用户帐户，则此地址 **包含多个用户帐户**。

     - 在" **外部域** "选项卡上，该值包含欺骗用户的域，而不是完整的电子邮件地址。

   - **发送基础结构**：在源电子邮件服务器的 IP 地址的反向 DNS 查找 (PTR 记录) 中找到的域，或者源没有 PTR 记录时则为 IP 地址。

     有关邮件来源和邮件发件人的更多信息， [请参阅电子邮件标准的概述](how-office-365-validates-the-from-address.md#an-overview-of-email-message-standards)。

   - **邮件数量**：来自发送基础结构的邮件数量，包含过去 30 天内包含指定的欺骗性发件人或发件人数量。

   - **用户复合的数量：** 用户在过去 30 天内针对此发件人进行处理。 商标通常以垃圾邮件的形式向 Microsoft 提交。

   - **身份验证结果**：以下值之一：

      - **已**传递：发件人通过了检查服务， (SPF 或 DKIM) 。
      - **失败**：发件人未通过 EOP 发件人身份验证检查。
      - **未**知：这些检查的结果未知。

   - **由以下方式**设置的决策：显示是否允许发送基础结构欺骗用户进行：

       - **自动设置的** (性) 
       - **管理员** (手动) 

   - **上次见**过：从包含欺骗性的用户的发送基础结构收到邮件时的上次日期。

   - **允许欺骗？**：你在此处看到的值如下：

     - **是**：允许来自欺骗用户和发送基础结构组合的邮件，但不会被视为欺骗性电子邮件。

     - **否**：欺骗用户和发送基础结构组合的消息标记为欺骗邮件。 此操作由默认的反网络钓鱼策略或自定义 ATP 反网络钓鱼策略 (默认值为将 **邮件移至垃圾邮件文件夹格式的**) 。 有关详细信息，请参阅下一节。

     - **Some users** (**Your Domains** tab only) ： A sending infrastructure is spoofing multiple users， where some spoofed users are allowed and others are not. 使用 **"详细** "选项卡查看特定地址。

6. 在页面底部，单击“保存”****。

## <a name="use-powershell-to-manage-spoofed-senders"></a>使用 PowerShell 管理欺骗性发件人

若要在欺骗智能中查看允许和阻止的发件人，请使用以下语法：

```powershell
Get-PhishFilterPolicy [-AllowedToSpoof <Yes | No | Partial>] [-ConfidenceLevel <Low | High>] [-DecisionBy <Admin | SpoofProtection>] [-Detailed] [-SpoofType <Internal | External>]
```

本示例返回有关允许您的域中的欺骗用户的所有发件人的详细信息。

```powershell
Get-PhishFilterPolicy -AllowedToSpoof Yes -Detailed -SpoofType Internal
```

有关语法和参数的详细信息，请参阅[Get-PhishFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/get-phishfilterpolicy)

若要在欺骗智能中配置允许和阻止的发件人，请按照以下步骤进行操作：

1. 通过将 **Get-PhishFilterPolicy** cmdlet 的输出写入 CSV 文件，捕获检测到的欺骗发件人的当前列表：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

2. 编辑 CSV 文件以添加或修改 **SpoofedUser** 以 (**或 AllowedToSpoof**)  (是"或"否") 值。 保存文件，阅读文件并将内容存储为名为： `$UpdateSpoofedSenders`

   ```powershell
   $UpdateSpoofedSenders = Get-Content -Raw "C:\My Documents\Spoofed Senders.csv"
   ```

3. 使用 `$UpdateSpoofedSenders` 变量配置欺骗智能策略：

   ```powershell
   Set-PhishFilterPolicy -Identity Default -SpoofAllowBlockList $UpdateSpoofedSenders
   ```

有关语法和参数的详细信息，请参阅[Set-PhishFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/set-phishfilterpolicy)

## <a name="use-the-security--compliance-center-to-configure-spoof-intelligence"></a>使用安全与&中心配置欺骗智能

在防钓鱼策略的欺骗设置中描述 [了欺骗智能配置选项](set-up-anti-phishing-policies.md#spoof-settings)。

可以在默认防钓鱼策略和自定义策略中配置欺骗智能设置。 有关基于您的订阅的说明，请参阅下列主题之一：

- [在 EOP 中配置反网络钓鱼策略](configure-anti-phishing-policies-eop.md)。

- [在 Microsoft 365 中配置 ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证你是否已通过允许或不允许欺骗的发件人以及是否配置伪信智能设置配置了欺骗智能保护，请按照以下任一步骤操作：

- 在安全 & 合规中心内，转至**威胁管理**策略反垃圾邮件，反垃圾邮件可展开"欺骗智能 \> **Policy** \> **Anti-spam** \> **"** \> 策略选择 **"向我我**已经审阅的发件人 \> " 选择**了'域'或****外部域"** 选项卡，然后验证**是否允许欺骗？** 此值适用于发件人。

- 在 PowerShell 中，运行以下命令来查看允许和不允许欺骗的发件人：

  ```powershell
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType Internal
  Get-PhishFilterPolicy -AllowedToSpoof Yes -SpoofType External
  Get-PhishFilterPolicy -AllowedToSpoof No -SpoofType External
  ```

- 在 PowerShell 中，运行以下命令，将所有欺骗性发件人列表导出为 CSV 文件：

   ```powershell
   Get-PhishFilterPolicy -Detailed | Export-CSV "C:\My Documents\Spoofed Senders.csv"
   ```

- 在安全与&合规中心内，**转到威** \> **胁**管理策略 \> **Anti-phishing**防钓鱼或 ATP 防**钓鱼**，并执行以下步骤之一：  

  - 从列表中选择一个策略。 在显示的浮出控件中，验证"欺骗 **"部分中的** 值。
  - 单击 **"默认策略"。** 在显示的浮出控件中，验证"欺骗 **"部分中的** 值。

- 在 Exchange Online PowerShell 中， \<Name\> 将 Office 365 AntiPhish Default 或自定义策略名称替换为自定义策略，然后运行以下命令来验证设置：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>" | Format-List EnableAntiSpoofEnforcement,EnableUnauthenticatedSender,AuthenticationFailAction
  ```

## <a name="other-ways-to-manage-spoofing-and-phishing"></a>管理欺骗和网络钓鱼的其他方法

关于欺骗和网络钓鱼防护的一定费用。 下面提供了检查发件人欺骗域的相关方法，以及防止它们充分分你的组织：

- 检查 **欺骗邮件报告**。 你可以经常使用此报告来查看和帮助管理欺骗性发件人。 有关信息，请参阅 [欺骗检测报告](view-email-security-reports.md#spoof-detections-report)。

- 查看 SPF 配置的 (策略) 框架。 若要了解 SPF 的快速简介及其快速配置方法，请参阅[在 Microsoft 365 中设置 SPF 以防欺骗](set-up-spf-in-office-365-to-help-prevent-spoofing.md)。 有关 Office 365 如何使用 SPF 的更深入了解，或者有关故障排除或非标准部署（如混合部署）的信息，请开始阅读[How Office 365 uses Sender Policy Framework (SPF) to prevent spoofing](how-office-365-uses-spf-to-prevent-spoofing.md)。

- 查看域密钥标识邮件， (DKIM 名称) 邮件。 除了使用 SPF 和 DMARC 之外，还应使用 DKIM，这样有助于防止攻击者发送看起来像自你的域中的邮件。 你可以使用 DKIM 将数字签名添加到电子邮件的邮件头中。 有关信息，请参阅" [使用 DKIM"在 Office 365 中验证从自定义域发送的出站电子邮件](use-dkim-to-validate-outbound-email.md)。

- 查看基于域的邮件身份验证、报告和一致性， (DMARC 测试) 配置。 实现使用 SPF 和 DKIM 的 DMARC 可以针对欺骗和钓鱼电子邮件提供额外的保护。 DMARC 可帮助接收邮件系统确定如何处理从你的域发送且未通过 SPF 或 DKIM 检查的邮件。 有关信息，请参阅 [使用 DMARC 验证 Office 365 中的电子邮件](use-dmarc-to-validate-email.md)。
