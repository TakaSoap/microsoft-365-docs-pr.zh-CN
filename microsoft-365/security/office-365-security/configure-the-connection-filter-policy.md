---
title: 配置默认连接筛选器策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 Exchange Online (Protection 或 EOP) 配置连接筛选，以允许或阻止来自电子邮件服务器的电子邮件。
ms.openlocfilehash: 45213ff36c7efc76a83a2c520e0369211ffecf53
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46827841"
---
# <a name="configure-connection-filtering"></a>配置连接筛选

如果你是具有 Exchange Online 邮箱的 Microsoft 365 客户，或者没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，则在 EOP (中，可在专用连接筛选策略) 通过他们的 IP 地址识别出正常或不好的源电子邮件服务器。 默认连接筛选器策略的关键组件有：

- **IP 允许列表**：跳过对从您按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件的垃圾邮件筛选。 有关垃圾邮件筛选可能仍然发生在这些源发邮件上的情况，请参阅 [本主题后面](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 的"来自 IP 允许列表中来源的邮件仍需进行筛选的方案"部分。 有关 IP 允许列表应如何适应总体安全发件人策略的详细信息，请参阅 Create safe sender [lists in EOP](create-safe-sender-lists-in-office-365.md).

- **IP 阻止列表**：阻止来自您按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件。 传入的邮件将被拒绝，不会标记为垃圾邮件，且无需其他筛选。 有关如何将 IP 阻止列表放入其中的总体阻止发件人策略的详细信息，请参阅[EOP 中的"创建阻止发件人列表"。](create-block-sender-lists-in-office-365.md)

- **安全列表**： *安全列表是* Microsoft 数据中心中的动态允许列表，不要求任何客户配置。 Microsoft 从订阅到各种第三方列表的地址识别这些受信任的电子邮件来源。 可启用或禁用安全列表的使用;您不能在安全列表中配置源电子邮件服务器。 安全列表上电子邮件服务器中的传入邮件上的垃圾邮件筛选跳过。

本主题介绍如何在安全 & 合规中心或在具有 Exchange Online 邮箱的 Microsoft 365 (Exchange Online PowerShell 中配置默认连接筛选器策略;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。 有关 EOP 使用连接筛选是整个反垃圾邮件设置的一部分的详细信息，请参阅"[反垃圾邮件保护"。](anti-spam-protection.md)

> [!NOTE]
> IP 允许列表、安全列表和 IP 阻止列表是你总体策略的一部分，用于允许或阻止贵组织的电子邮件。 有关详细信息，请参阅创建安全[发件人列表和](create-safe-sender-lists-in-office-365.md)[创建阻止发件人列表](create-block-sender-lists-in-office-365.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 若要修改默认连接筛选器策略，你必须是以下角色组的成员之一：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 对于对默认连接筛选器策略的只读访问权限，你需要是以下角色组的成员之一：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

- 要查找电子邮件服务器的源 IP 地址 (要允许或阻止的发件人) 信息，可以检查邮件头中的"IP (**CIP**) 邮件头"字段。 若要查看各种电子邮件客户端中的邮件头，请参阅["在 Outlook 中查看 Internet 邮件头"。](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- IP 允许列表优先于包含两个列表 (列表上的地址的 IP) 。

- IP 允许列表和 IP 阻止列表支持最多 1273 个条目，每个条目为单 IP 地址、IP 地址范围或无类别域际路由 (CIDR) IP。

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>使用安全&安全中心修改默认连接筛选器策略

1. 在安全合 &中心内，转到威 **胁** \> **管理** \> **策略反垃圾邮件**。

2. 在"**反垃圾邮件设置"** 页上，单击 **"展开'图标"，** 然后单击"编辑 ![ 策略"，展开 ](../../media/scc-expand-icon.png) "连接**筛选策略"。**

3. 在 **随** 后出现的默认浮出控件中，配置以下任意设置：

   - **描述**：输入可选描述性文本。

   - **IP 允许列表：** 单击"**编辑"。** 在出现 **的 IP 允许** 列表浮出控件中，使用以下语法在地址或 **地址范围框中输入** IPV4 地址：

     - 单个 IP：例如，192.168.1.1。

     - IP 范围：例如，192.168.0.1-192.168.0.254。

     - CIDR IP：例如，192.168.0.1/25。 有效的网络掩码值为 /24 到 /32。 若要跳过对 CIDR IP 掩码值/1 到 /23 的垃圾邮件筛选，请参阅 [本主题稍后将为 CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 跳过垃圾邮件筛选。

     若要添加 IP 地址或地址范围，**Add**请单击添加 ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。 若要删除某个条目，请在允许 IP 地址 **中选择该条目，** 然后单击 **"删除** ![ ](../../media/scc-remove-icon.png) "。 完成时，请单击“保存”****。

   - **IP 阻止列表：** 单击"**编辑"。** 如**前文中的"IP**允许列表"设置中所述，在"地址范围"框中输入单个 IP、IP**范围或**CIDR IP。 **IP Allow List**

     若要添加 IP 地址或地址范围，**Add**请单击添加 ![ 图标 ](../../media/ITPro-EAC-AddIcon.png) 。 若要删除某个条目，请在"阻止的 IP 地址 **"中选择该条目，** 然后单击"删除**Remove** ![ ](../../media/scc-remove-icon.png) "。 完成时，请单击“保存”****。

   - **打开安全列表**：允许或禁止使用安全列表识别已知的良好发件人，这将导致垃圾邮件筛选跳过。

4. 完成时，请单击“保存”****。

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>使用安全与&合规中心查看默认连接筛选器策略

1. 在安全合 &中心内，转到威 **胁** \> **管理** \> **策略反垃圾邮件**。

2. 在" **反垃圾邮件设置"** 页面上，单击名为"连接筛选策略"的默认策略旁 **边的下拉列表**。

3. 策略设置显示在打开的下拉列表中。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 修改默认连接筛选器策略

使用以下语法：

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**注意**：

- 有效的 IP 地址或地址范围的值包括：

  - 单个 IP：例如，192.168.1.1。

  - IP 范围：例如，192.168.0.1-192.168.0.254。

  - CIDR IP：例如，192.168.0.1/25。 有效的网络掩码值为 /24 到 /32。

- 若要 *用指定的* 值覆盖任何现有条目，请使用以下语法 `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` ：

- 若要 *在不影响* 其他现有条目的情况下添加或删除 IP 地址或地址范围，请使用以下语法 `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` ：

- 若要清空 IP 允许列表或 IP 阻止列表，请使用该值 `$null` 。

本示例将使用指定的 IP 地址和地址范围配置 IP 允许列表和 IP 阻止列表。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

本示例在 IP 允许列表中添加和删除指定的 IP 地址和地址范围。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

若要详细了解语法和参数，请参阅["Set-HostedConnectionFilterPolicy"。](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否已成功修改默认连接筛选器策略，请执行以下任一步骤：

- 在安全与合规&中心内，转到 **"威胁管理** \> **策略** \> **反垃圾邮件** \> "，单击 **"连接筛选器策略"和" (始终启用") "** 旁边的下拉列表，然后验证设置。

- 在 Exchange Online PowerShell 或独立 EOP PowerShell 中，运行以下命令以确认设置：

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- 从 IP 允许列表上的条目发送测试邮件。

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 允许列表的其他注意事项

下列各节确定了在配置 IP 允许列表时需要了解的其他项目。

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>跳过可用范围之外的 CIDR IP 的垃圾邮件筛选

如本主题前面所述，您只能使用 CIDR IP 和 IP 允许列表中的网络掩码 /24 至 /32。 要跳过从 /1 到 /23 范围内源电子邮件服务器的邮件进行垃圾邮件筛选，需要使用 Exchange 邮件流规则 (也称为传输规则) 。 但是，建议您在所有可能时都不要这样做，因为如果 /1 到 /23 CIDR IP 范围内的 IP 地址在 Microsoft 的任何专有或第三方阻止列表中出现，这些邮件将被阻止。

至此，已完全认识到潜在的问题，可以使用下列设置 (最少) 创建邮件流规则，以确保来自这些 IP 地址的邮件将跳过垃圾邮件筛选：

- 规则条件 **：如果发件人 IP 地址处于这些**范围内或准确匹配的 \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> (输入你的 CIDR IP 与 /1 到 /23 网络掩码，则应用此) 规则。

- 规则操作： **修改邮件** \> **属性" 将垃圾邮件可信度设为s， (SCL) ** \> **筛选**。

您可以在特定时间内审核规则、测试规则及激活规则，其他操作会进行审核。 我们建议首先在一段时间内测试规则，然后再强制应用。 有关详细信息，请参阅 [在 Exchange Online 中管理邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>在来自同一源的选择性电子邮件域上跳过垃圾邮件筛选

通常，向 IP 允许列表添加 IP 地址或地址范围意味着您信任该电子邮件源的所有传入邮件。 但是，如果该源发送来自多个域的电子邮件，并且你希望跳过某些域的垃圾邮件筛选而非其他域，该怎办一点？ 您无法将 IP 允许列表与邮件流规则结合使用，但可以结合使用 IP 允许列表。

例如，源电子邮件服务器 192.168.1.25 发送来自域 contoso.com、fabrikam.com 和 tailspintoys.com 的电子邮件，但您只希望跳过对来自 fabrikam.com 中发件人的邮件进行垃圾邮件筛选的fabrikam.com。 为此，请执行下列步骤：

1. 向 IP 允许列表添加 192.168.1.25。

2. 使用以下设置配置邮件流规则 (此设置) ：

   - 规则条件 **：如果发件人 IP 地址处于这些**范围内，或准确匹配 \> **The sender** \> **IP address is in any of these ranges or exactly matches** \> 192.168.1.25 (与在上一步) 中的 IP 允许列表中添加的 IP 地址或地址范围相同，则应用此规则。

   - 规则操作：**修改邮件** \> **属性" 设置垃圾邮件可信度 (SCL) ** \> **0。**

   - 规则例外 **：发件人** \> **域仅** \> fabrikam.com (您想要跳过垃圾邮件筛选的一个或多个域，) 。

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>仍将筛选来自 IP 允许列表中的源的邮件的情况

在下列情况下，IP 允许列表中的电子邮件服务器的邮件仍受垃圾邮件筛选约对的约名制约：

- IP 允许列表中的 IP 地址也配置为本地的 IP 允许列表中的 IP 地址，可通过*any*Microsoft 365 (中的任何租户的基于 IP 的入站连接器呼叫此租户 A) 、**先遇到**此邮件的租户 A 和 EOP 服务器出现在 Microsoft 数据中心*的同一*个 Active Directory 林中。 在这种情况下 **，IPV：CAL***已添加到*邮件[的反垃圾邮件邮件头](anti-spam-message-headers.md) (以指示邮件绕过垃圾邮件筛选) ，但是邮件仍然受垃圾邮件筛选的约义。

- 包含 IP 允许列表的租户和先遇到邮件的 EOP 服务器都发生在 Microsoft *数据* 中心的不同 Active Directory 林中。 在这种情况下 **，IPV：CAL** *不会* 添加到邮件头，因此邮件仍需进行垃圾邮件筛选。

如果遇到上述任一情况，可以使用以下设置 (至少 创建邮件流规则) ，以确保有问题的 IP 地址的邮件将跳过垃圾邮件筛选：

- 规则条件 **：如果发件人**IP 地址处于这些范围内或完全匹配的 (\> **The sender** \> **IP address is in any of these ranges or exactly matches** \> IP 地址或地址表达式，则应用此) 。

- 规则操作： **修改邮件** \> **属性" 将垃圾邮件可信度设为s， (SCL) ** \> **筛选**。

## <a name="new-to-microsoft-365"></a>不新增了 Microsoft 365？

|<!-- a -->|
|---|
|![LinkedIn Learning New 到 ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **Microsoft 365 简短图标？** 发现 LinkedIn Learning **向管理员**和 IT 专业人提供的免费视频课程。|
|
