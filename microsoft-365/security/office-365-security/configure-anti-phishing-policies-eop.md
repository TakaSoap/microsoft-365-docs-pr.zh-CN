---
title: 配置 EOP 中的默认防钓鱼策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何使用 Exchange Online 邮箱修改 Office 365 组织中的默认反网络钓鱼策略中提供的反欺骗设置。
ms.openlocfilehash: 1a8527a55796910e79fbf70b824de828ca48591b
ms.sourcegitcommit: db8702cf578b02c6fd6a2670c177b456efae4748
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2020
ms.locfileid: "43537529"
---
# <a name="configure-the-default-anti-phishing-policy-in-eop"></a>配置 EOP 中的默认防钓鱼策略

拥有 Exchange Online 邮箱和独立 Exchange Online Protection （EOP）组织（没有 Exchange Online 邮箱）的 Office 365 组织具有默认的反网络钓鱼策略。 此策略包含默认情况下启用的有限数量的反欺骗功能。 有关详细信息，请参阅[反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

使用 Exchange Online 邮箱的 office 365 组织可以修改 Office 365 安全性 & 合规性中心或 Exchange Online PowerShell 中的默认反网络钓鱼策略。 没有 Exchange Online 邮箱的独立 EOP 组织无法修改其默认的反网络钓鱼策略。

有关创建和修改 Office 365 高级威胁防护中提供的更高级 ATP 反钓鱼策略的信息，请参阅[在 office 365 中配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 "**反钓鱼**" 页面， <https://protection.office.com/antiphishing>请使用。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online/connect-to-exchange-online-powershell/connect-to-exchange-online-powershell)。

- 必须先分配有权限，然后才能执行这些过程。 若要添加、修改和删除反网络钓鱼策略，您必须是 "**组织管理**" 或 "**安全管理员**" 角色组的成员。 若要对反网络钓鱼策略进行只读访问，您需要是**安全读者**角色组的成员。 若要详细了解安全与合规中心内的角色组，请参阅 [Office 365 安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)。

- 有关默认反网络钓鱼策略的推荐设置，请参阅[EOP 默认反网络钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

- 允许应用更新后的策略最长为30分钟。

- 有关在筛选管道中应用反网络钓鱼策略的位置的信息，请参阅[Office 365 中的电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>使用安全 & 合规性中心修改默认的反网络钓鱼策略

默认的反网络钓鱼策略名为 Office365 AntiPhish Default，且不会出现在策略列表中。 若要修改默认的反网络钓鱼策略，请执行以下步骤：

1. 在安全 & 合规性中心中，转到 "**威胁管理** \> **策略** \> " "**反网络钓鱼**"。

2. 在 "**反钓鱼网站**" 页上，单击 "**默认策略**"。

3. 将显示 "**编辑您的策略 Office365 AntiPhish 默认**页"。 在 "**欺骗**" 部分，单击 "**编辑**"。

   请注意，这些设置与 ATP 反网络钓鱼策略中提供的欺骗设置相同。

   - **哄骗筛选器设置**：默认值为 **"开**"，我们建议您将其保留在中。 若要将其关闭，请将开关滑动到 "**关闭**"。 有关详细信息，请参阅[在 Office 365 中配置欺骗智能](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > 如果您的 MX 记录不指向 Office 365，则无需禁用反欺骗保护;可以改为对连接器启用增强的筛选。 有关说明，请参阅[增强的对 Exchange Online 中的连接器的筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   - **启用未经身份验证的发件人功能**：如果邮件失败电子邮件身份验证检查，则向发件人的照片添加问号。 有关详细信息，请参阅[反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。 默认值为“打开”****。 若要将其关闭，请将开关滑动到 "**关闭**"。

   - **操作**：指定对欺骗性智能邮件失败的邮件执行的操作：

     **如果电子邮件由不允许欺骗您的域的人发送**：

     - **将邮件移到收件人的 "垃圾邮件" 文件夹**（这是默认值。）
     - **隔离邮件**

   - **查看设置**：不是单击每个单独的步骤，而是在摘要中显示设置。

     - 您可以单击每个部分中的 "**编辑**" 以跳回到相关页面。
     - 您可以在此页面**上****直接切换**以下设置：

       - **启用 antispoofing 保护**
       - **启用未经身份验证的发件人功能**

   完成后，请单击任意页面上的 "**保存**"。

4. 返回到 "**编辑您的策略 Office365 AntiPhish 默认**页面"，查看您的设置，然后单击 "**关闭**"。

## <a name="use-the-security--compliance-center-to-view-the-default-anti-phishing-policy"></a>使用安全 & 合规性中心查看默认的反网络钓鱼策略

1. 在安全 & 合规性中心，并转到**威胁管理** \> **策略** \> **ATP 反网络钓鱼**。

2. 单击 "**默认策略**" 以查看默认的反网络钓鱼策略。

## <a name="use-exchange-online-powershell-to-configure-the-default-anti-phishing-policy"></a>使用 Exchange Online PowerShell 配置默认的反网络钓鱼策略

### <a name="use-powershell-to-view-the-default-anti-phish-policy"></a>使用 PowerShell 查看默认反网络钓鱼策略

若要查看默认的反网络钓鱼策略，请运行以下命令：

```PowerShell
Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
```

有关语法和参数的详细信息，请参阅[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-modify-the-default-anti-phish-policy"></a>使用 PowerShell 修改默认反网络钓鱼策略

若要修改默认的反网络钓鱼策略，请使用以下语法：

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableAntispoofEnforcement <$true | $false>] [-EnableUnauthenticatedSender <$true | $false>]
```

本示例将对未通过身份验证检查的欺骗性邮件的操作更改为 "隔离"。

```powershell
Set-AntiPhishPolicy -Identity "Office365 AntiPhish Default" -AuthenticationFailAction Quarantine
```

有关语法和参数的详细信息，请参阅[AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/advanced-threat-protection/Set-AntiPhishPolicy)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否已成功配置默认的反网络钓鱼策略，请执行以下任一步骤：

- 在安全 & 合规性中心中，转到 "**威胁管理** \> **策略** \> **反网络钓鱼** \> " 单击 "**默认策略**"，然后在浮出控件中查看详细信息。

- 在 Exchange Online PowerShell 中，运行以下命令并验证设置：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "Office365 AntiPhish Default"
  ```
