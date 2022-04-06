---
title: 模拟见解
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: overview
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解模拟见解的工作原理。 他们可以快速确定哪些发件人从没有通过 SPF、DKIM 或 DMARC 身份验证检查的域合法地将电子邮件 (其组织) 。
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: dbaf395f10eaac7ff508b03f6f079f94bdd6cebd
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475798"
---
# <a name="impersonation-insight-in-defender-for-office-365"></a>Defender for Office 365 中的模拟见解

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!NOTE]
> 本文中所述的功能在预览版中，可能会更改，并且并非在所有组织中都可用。

模拟是电子邮件发件人看起来与真实或预期的发件人电子邮件地址非常相似的地方。 攻击者经常在网络钓鱼或其他类型的攻击中模拟发件人电子邮件地址，以赢得收件人的信任。 基本上有两种类型的模拟：

- **域模拟**：将 lila@contoso.com 发件人的电子邮件地址，而不是 lila@ćóntoso.com。
- **用户模拟**：michelle@contoso.com，模拟发件人的电子邮件地址将 rnichell@contoso.com。

域模拟不同于域 [欺骗](anti-spoofing-protection.md)，因为模拟的域通常是真实注册的域。 来自模拟域中的发件人的邮件可以而且通常通过常规电子邮件身份验证检查，以识别 SPF、DKIM 和 DMARC (欺骗) 。

模拟保护是专用于 Microsoft Defender for Office 365 的反网络钓鱼策略设置的一Office 365。 有关这些设置详细信息，请参阅 Microsoft [Defender for Office 365 中的防钓鱼策略中的模拟Office 365](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)。

您可以使用模拟门户中的模拟见解Microsoft 365 Defender识别来自已配置为用于模拟保护的模拟发件人或发件人域的邮件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到" **防钓鱼"页面** ，请使用 <https://security.microsoft.com/antiphishing>。 若要直接转到模拟 **见解页面** ，请使用 <https://security.microsoft.com/impersonationinsight>。

- 您需在 Microsoft 365 Defender 门户中分配权限，然后才能执行本文中的过程：
  - **组织管理**
  - **安全管理员**
  - **安全读者**
  - **全局读取者**

  有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

  **注意**：将用户添加到 Microsoft 365 管理中心 中的相应 Azure Active Directory 角色会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

- 在 Microsoft Defender for Office 365 中的防钓鱼策略中启用和配置Office 365。 默认情况下不启用模拟保护。 有关详细信息，请参阅在 [Microsoft Defender](configure-mdo-anti-phishing-policies.md) 中为用户配置Office 365。

## <a name="open-the-impersonation-insight-in-the-microsoft-365-defender-portal"></a>在模拟门户中打开模拟Microsoft 365 Defender见解

1. In the Microsoft 365 Defender portal at <https://security.microsoft.com>， go to **Email & Collaboration** \> **Policies & Rules** \> **Threat policies** \> **Anti-phishing** in the **Policies** section. 若要直接转到" **防钓鱼"页面** ，请使用 <https://security.microsoft.com/antiphishing>。

2. 在 **"防钓鱼"** 页面上，模拟见解如下所示：

   :::image type="content" source="../../media/m365-sc-impersonation-and-spoof-intelligence-insight.png" alt-text="&quot;反网络钓鱼策略&quot;页上的模拟见解和欺骗智能" lightbox="../../media/m365-sc-impersonation-and-spoof-intelligence-insight.png":::

   见解有两种模式：

    - 见解模式：如果在任何防钓鱼策略中启用和配置了模拟保护，则此见解将显示过去七天内从模拟域和模拟用户 () 检测到的邮件数。 这是所有反网络钓鱼策略中所有检测到的模拟发件人总数。
    - 如果 **模式**：如果未在任何活动的反网络钓鱼策略中启用和配置模拟保护，则此见解将展示我们的模拟保护功能在过去七天内检测到的邮件数。

若要查看有关模拟检测的信息，请单击模拟见解 **中的** "查看模拟"。

   > [!NOTE]
   > 有关欺骗智能见解的信息，请参阅 [EOP 中的欺骗智能见解](learn-about-spoof-intelligence.md)。

## <a name="view-information-about-messages-from-senders-in-impersonated-domains"></a>查看有关来自模拟域中发件人的邮件的信息

在单击 **模拟见解** 中的"查看模拟"后出现的"模拟见解"页上，验证是否选择了"**域**"选项卡。 " **域** "选项卡包含以下信息：

- **发件人** 域：模拟域，用于发送电子邮件的域。
- **邮件计数**：过去 7 天内来自模拟发件人域的邮件数。
- **模拟类型**：此值显示模拟服务器检测到 (，例如， **Address)** 。
- **模拟 (域)**：模拟的域，它应非常类似于在反网络钓鱼策略中配置为进行模拟保护的域。
- **域类型**：此值是 **内部域** 的公司域或自定义 **域** 的自定义域。
- **策略**：检测到模拟域的防钓鱼策略。
- **允许模拟：** 下列值之一：
  - **是**：域已配置为受信任的域 (防钓鱼策略中) 的一个例外。 检测到来自模拟域中发件人的邮件，但允许。
  - **No**：域配置为在反网络钓鱼策略中提供模拟保护。 根据反网络钓鱼策略中模拟域的操作，检测到来自模拟域中的发件人的邮件，并基于这些操作执行这些邮件。

您可以单击所选列标题对结果进行排序。

若要筛选结果，可以使用搜索 ![图标。](../../media/m365-cc-sc-search-icon.png) **用于** 输入以逗号分隔的值列表以筛选结果的搜索框。

### <a name="view-details-about-messages-from-senders-in-impersonated-domains"></a>查看有关来自模拟域中发件人的邮件的详细信息

在" **模拟** 见解 **"页上的** "域"选项卡上，选择一个可用的模拟检测。 显示的详细信息飞出包含以下信息和功能：

- **要修改的选择模拟策略**：选择要修改的受影响的防钓鱼策略。 只有策略中定义了模拟域的策略才可用。 参考上一页，查看哪个策略实际负责根据收件人 (以及策略的优先级来检测模拟) 。
- 添加到允许的模拟列表：使用此开关添加或删除所选防钓鱼策略的"受信任的发件人和 **域 (模拟**) 例外"中的发件人：
  - 如果 **此条目的"允许模拟** "值为 **"** 否"，则开关处于关闭状态。 若要通过模拟保护使此域中的所有发件人免于评估，将开关滑动到"打开"： ![切换打开](../../media/scc-toggle-on.png)。 该域将添加到反网络钓鱼策略的模拟保护设置中的"受信任的域"列表中。
  - 如果 **此条目的"允许模拟** "值为 **"是**"，则开关处于打开状态。 若要通过模拟保护使此域中的所有发件人返回评估，请切换为关闭： ![切换为关闭](../../media/scc-toggle-off.png)。 该域将从反 **网络钓鱼** 策略的模拟保护设置中的"受信任的域"列表中删除。
- 我们为什么捕获到此。
- 需要执行哪些工作。
- 列出模拟域的域摘要。
- WhoIs 有关发件人的数据。
- 打开威胁资源管理器 [以查看有关](threat-explorer.md) 发件人的其他详细信息的链接。
- 来自已传递到组织的同一发件人的类似邮件。

## <a name="view-information-about-messages-from-impersonated-senders"></a>查看有关来自模拟发件人的邮件的信息

在单击 **模拟见解** 中的"查看模拟"后出现的"模拟见解"页上，单击"用户 **"** 选项卡。"**用户**"选项卡包含以下信息：

- **发件人**：发送电子邮件的模拟发件人的电子邮件地址。
- **邮件计数**：最近 7 天内来自模拟发件人的邮件数。
- **模拟类型**：此值为 **用户显示名称**。
- **模拟 (** 用户) ：模拟发件人的电子邮件地址，该地址应该与在反网络钓鱼策略中配置为进行模拟保护的用户非常类似。
- **用户类型**：此值显示应用的保护类型 (例如，受保护的用户或 **邮箱**) 。 
- **策略**：检测到模拟发件人的防钓鱼策略。
- **允许模拟：** 下列值之一：
  - **是**：发件人配置为受信任用户 (防钓鱼策略中) 的模拟保护例外。 检测到但允许来自模拟发件人的邮件。
  - **No**：发件人配置为在反网络钓鱼策略中提供模拟保护。 根据反网络钓鱼策略中模拟用户的操作，检测到来自模拟发件人的邮件并据此操作。

您可以单击所选列标题对结果进行排序。

若要筛选结果，可以使用"筛选发件人"框输入以逗号分隔的值列表以筛选结果。

### <a name="view-details-about-messages-from-impersonated-senders"></a>查看有关来自模拟发件人的邮件的详细信息

在" **模拟** 见解 **"页上的** "用户"选项卡上，选择一个可用的模拟检测。 显示的详细信息飞出包含以下信息和功能：

- **要修改的选择模拟策略**：选择要修改的受影响的防钓鱼策略。 只有策略中定义了模拟发件人的策略才可用。 参考上一页，查看哪个策略实际负责根据收件人 (以及策略的优先级来检测) 。
- 添加到允许的模拟列表：使用此开关添加或删除所选防钓鱼策略的"受信任的发件人和 **域 (模拟**) 例外"中的发件人：
  - 如果 **此条目的"允许模拟** "值为 **"** 否"，则开关处于关闭状态。 若要通过模拟保护使发件人免于评估，将开关滑动到"打开"： ![切换为"打开"](../../media/scc-toggle-on.png)。 发件人将添加到反 **网络钓鱼** 策略的模拟保护设置中的"受信任的用户"列表中。
  - 如果 **此条目的"允许模拟** "值为 **"是**"，则开关处于打开状态。 若要通过模拟保护将发件人返回到评估，将切换开关切换为关闭： ![切换关闭](../../media/scc-toggle-off.png)。 发件人将从反网络钓鱼策略的模拟保护设置中的"受信任的用户"列表中删除。
- 我们为什么捕获到此。
- 需要执行哪些工作。
- 列出模拟发件人的发件人摘要。
- WhoIs 有关发件人的数据。
- 打开威胁资源管理器 [以查看有关](threat-explorer.md) 发件人的其他详细信息的链接。
- 来自已传递到组织的同一发件人的类似邮件。
