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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 6ae78c12-7bbe-44fa-ab13-c3768387d0e3
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 配置连接筛选以允许或阻止来自电子邮件服务器的电子邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: c6ec8b4adcdda692ee561f7d50bacf0511642269
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290041"
---
# <a name="configure-connection-filtering"></a>配置连接筛选

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)


如果你是在 Exchange Online 中拥有邮箱的 Microsoft 365 客户，或者是没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，请使用 EOP (中的连接筛选，特别是默认连接筛选器策略) 通过 IP 地址标识好或坏的源电子邮件服务器。 默认连接筛选器策略的关键组件是：

- **IP 允许列表**：跳过通过 IP 地址或 IP 地址范围指定的源电子邮件服务器中所有传入邮件的垃圾邮件筛选。 有关这些源中的邮件仍可能发生垃圾邮件筛选的方案，请参阅本文稍后部分中的" [来自 IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 允许列表中的源的邮件仍然经过筛选的方案"部分。 有关 IP 允许列表如何适合整体安全发件人策略的信息，请参阅[EOP 中的"创建安全发件人列表"。](create-safe-sender-lists-in-office-365.md)

- **IP 阻止列表**：阻止来自按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件。 传入的邮件被拒绝，不会标记为垃圾邮件，并且不会发生其他筛选。 有关 IP 阻止列表如何适合整个阻止发件人策略的信息，请参阅 EOP 中的"创建[阻止发件人列表"。](create-block-sender-lists-in-office-365.md)

- **安全列表**： *安全列表是* Microsoft 数据中心中的动态允许列表，不需要客户配置。 Microsoft 从订阅到各种第三方列表标识这些受信任的电子邮件源。 启用或禁用安全列表的使用;无法配置安全列表中的源电子邮件服务器。 从安全列表上的电子邮件服务器传入的邮件上跳过垃圾邮件筛选。

本主题介绍如何在安全与合规中心或 PowerShell & (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置默认连接筛选器策略;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。 有关 EOP 如何使用连接筛选是组织整体反垃圾邮件设置的一部分，请参阅["反垃圾邮件保护"。](anti-spam-protection.md)

> [!NOTE]
> IP 允许列表、安全列表和 IP 阻止列表是允许或阻止组织中电子邮件的总体策略的一部分。 有关详细信息，请参阅["创建安全发件人列表"和](create-safe-sender-lists-in-office-365.md)["创建阻止的发件人列表"。](create-block-sender-lists-in-office-365.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要修改默认连接筛选器策略，您必须是组织管理或 **安全管理员** 角色组的成员。
  - 若要对默认连接筛选器策略进行只读访问，你需要是全局阅读器或安全读者 **角色组** 的成员。

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 若要查找要允许或阻止的电子邮件服务器 (发件人) 的源 IP 地址，可以检查邮件头中的连接 IP (**CIP**) 头字段。 若要查看各种电子邮件客户端中的邮件头，请参阅 Outlook 中的["查看 Internet 邮件头"。](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- IP 允许列表优先于 IP 阻止列表 (两个列表上的地址不会) 。

- IP 允许列表和 IP 阻止列表最多支持 1273 个条目，其中条目是单个 IP 地址、IP 地址范围或无类别域间路由 (CIDR) IP。

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>使用安全&合规中心修改默认连接筛选器策略

1. 在安全&合规中心，转到 **"威胁管理** \> **策略** \> **反垃圾邮件"。**

2. 在 **"反垃圾邮件设置"页上**，通过单击"展开"图标展开"连接筛选器策略"， ![ ](../../media/scc-expand-icon.png) 然后单击"**编辑策略"。**

3. 在 **出现的"** 默认"飞出中，配置以下任一设置：

   - **说明**：输入可选的描述性文本。

   - **IP 允许列表**：单击"**编辑"。** 在 **出现的 IP 允许列表** 飞出框中，使用以下语法在地址 **或地址** 范围框中输入 IPV4 地址：

     - 单个 IP：例如，192.168.1.1。

     - IP 范围：例如，192.168.0.1-192.168.0.254。

     - CIDR IP：例如，192.168.0.1/25。 有效的网络掩码值为 /24 到 /32。 若要将 CIDR IP 掩码值 /1 的垃圾邮件筛选跳过到 /23，请参阅本文稍后部分之外的 [CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 跳过垃圾邮件筛选。

     若要添加 IP 地址或地址范围，请单击 **"添加图标** ![ ](../../media/ITPro-EAC-AddIcon.png) "。 若要删除条目，请选择"允许的 **IP** 地址"中的条目，然后单击" **删除** ![ ](../../media/scc-remove-icon.png) "。 完成时，请单击“保存”。

   - **IP 阻止列表**：单击"**编辑"。** 在 **出现的 IP 阻止列表** 飞出框中，在"地址或地址范围"框中输入单个 IP、IP 范围或 CIDR IP，如 **前面 IP** 允许列表设置中所述。 

     若要添加 IP 地址或地址范围，请单击 **"添加图标** ![ ](../../media/ITPro-EAC-AddIcon.png) "。 若要删除条目，请选择"阻止的 **IP** 地址"中的条目，然后单击" **删除** ![ ](../../media/scc-remove-icon.png) "。 完成时，请单击“保存”。

   - **打开安全列表**：启用或禁用安全列表，以标识将跳过垃圾邮件筛选的已知良好发件人。

4. 完成时，请单击“保存”。

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>使用安全&合规中心查看默认连接筛选器策略

1. 在安全&合规中心，转到 **"威胁管理** \> **策略** \> **反垃圾邮件"。**

2. 在 **"反垃圾邮件设置** "页上，单击名为"连接筛选器策略"的默认策略 **旁边的下拉列表**。

3. 策略设置显示在打开的下拉列表中。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-modify-the-default-connection-filter-policy"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 修改默认连接筛选器策略

使用以下语法：

```powershell
Set-HostedConnectionFilterPolicy -Identity Default [-AdminDisplayName <"Optional Comment">] [-EnableSafeList <$true | $false>] [-IPAllowList <IPAddressOrRange1,IPAddressOrRange2...>] [-IPBlockList <IPAddressOrRange1,IPAddressOrRange2...>]
```

**注意**：

- 有效的 IP 地址或地址范围值为：

  - 单个 IP：例如，192.168.1.1。

  - IP 范围：例如，192.168.0.1-192.168.0.254。

  - CIDR IP：例如，192.168.0.1/25。 有效的网络掩码值为 /24 到 /32。

- 若要 *用* 您指定的值覆盖任何现有条目，请使用以下 `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 语法：

- 若要 *在不影响* 其他现有条目的情况下添加或删除 IP 地址或地址范围，请使用以下 `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 语法：

- 若要清空 IP 允许列表或 IP 阻止列表，请使用值 `$null` 。

此示例使用指定的 IP 地址和地址范围配置 IP 允许列表和 IP 阻止列表。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

此示例从 IP 允许列表中添加和删除指定的 IP 地址和地址范围。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

有关语法和参数的详细信息，请参阅 [Set-HostedConnectionFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedconnectionfilterpolicy)。

## <a name="how-do-you-know-this-worked"></a>如何判断是否生效？

若要验证是否成功修改了默认连接筛选器策略，请执行下列任何步骤：

- 在安全&合规中心，转到"威胁管理策略反垃圾邮件"，单击"连接筛选器策略 ("旁边的下拉列表 \>  \>  \> **) 验证** 设置。

- 在 Exchange Online PowerShell 或独立 EOP PowerShell 中，运行以下命令并验证设置：

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- 从 IP 允许列表上的条目发送测试邮件。

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 允许列表的其他注意事项

以下各节确定了配置 IP 允许列表时需要知道的其他项目。

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>跳过对可用范围之外的 CIDR IP 的垃圾邮件筛选

如本文前面所述，只能在 IP 允许列表中使用具有网络掩码 /24 到 /32 的 CIDR IP。 若要跳过对来自 /1 范围内源电子邮件服务器的邮件进行垃圾邮件筛选到 /23 范围，您需要使用 Exchange 邮件流规则 (也称为传输规则) 。 但是，我们建议你尽可能不要这样做，因为如果 /1 到 /23 CIDR IP 范围中的 IP 地址出现在任何 Microsoft 专有或第三方阻止列表中，邮件将被阻止。

现在，已完全了解潜在问题，您至少可以使用以下设置 (创建一个邮件流规则) 以确保来自这些 IP 地址的邮件将跳过垃圾邮件筛选：

- 规则 **条件：** 如果发件人 IP 地址位于以下任一范围内或与输入的 CIDR IP 完全匹配 (则应用此规则，并输入 \>  \>  \> /1 到 /23 网络掩码) 。

- 规则操作 **：修改邮件属性** 设置垃圾邮件可信度 \> **(SCL)** \> **绕过垃圾邮件筛选**。

可以审核规则、测试规则、激活特定时间段的规则和其他选择。 我们建议首先在一段时间内测试规则，然后再强制应用。 有关详细信息，请参阅管理 [Exchange Online 中的邮件流规则](https://docs.microsoft.com/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)。

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>跳过来自同一源的选择性电子邮件域的垃圾邮件筛选

通常，将 IP 地址或地址范围添加到 IP 允许列表意味着信任来自该电子邮件源的所有传入邮件。 但是，如果该源从多个域发送电子邮件，并且您希望跳过其中一些域（而非其他域）的垃圾邮件筛选，那又如何呢？ 不能单独使用 IP 允许列表来这样做，但可以将 IP 允许列表与邮件流规则结合使用。

例如，源电子邮件服务器 192.168.1.25 从 contoso.com、fabrikam.com 和 tailspintoys.com 域发送电子邮件，但您只想跳过对 fabrikam.com 中发件人的邮件进行垃圾邮件筛选。 为此，请使用以下步骤：

1. 将 192.168.1.25 添加到 IP 允许列表。

2. 配置邮件流规则，并至少 (以下) ：

   - 规则 **条件：** 如果发件人 IP 地址位于以下任一范围内或与 \>  \> 192.168.1.25 (与在上一步骤) 中添加到 IP 允许列表的相同 IP 地址或地址范围匹配，则应用 \> 此规则。

   - 规则操作 **：修改邮件属性** \> **将垃圾邮件可信度设置为 (SCL)** \> **0。**

   - 规则例外： **发件人** \> **域fabrikam.com (** 要跳过垃圾邮件筛选的域或 \>) 。

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>仍筛选来自 IP 允许列表中的源的邮件的方案

在下列情况下，来自 IP 允许列表中的电子邮件服务器的邮件仍受垃圾邮件筛选限制：

- IP 允许列表中的 IP 地址也在 Microsoft 365 (任何租户中的基于IP 的本地入站连接器中配置 (让我们调用此租户 A) ，第一次遇到邮件的租户 A 和 EOP 服务器正好位于 Microsoft 数据中心中的同一 *Active* Directory 林中。 在此方案中 **，IPV：CAL** 将添加到邮件的反垃圾邮件邮件头 [ (](anti-spam-message-headers.md)指示邮件绕过了垃圾邮件筛选) ，但邮件仍受垃圾邮件筛选限制。

- 包含 IP 允许列表的租户和首次遇到邮件的 EOP 服务器都发生在 Microsoft 数据中心的不同 *Active* Directory 林中。 在这种情况下 **，IPV：CAL** *不会* 添加到邮件头，因此邮件仍受垃圾邮件筛选限制。

如果遇到上述任一情况，可以创建至少 (设置的邮件流规则) 以确保有问题的 IP 地址中的邮件跳过垃圾邮件筛选：

- 规则条件：**如果** 发件人 IP 地址位于以下任一范围内或与你的 IP 地址 (完全匹配，则应用此 \>  \>  \>) 。

- 规则操作 **：修改邮件属性** 设置垃圾邮件可信度 \> **(SCL)** \> **绕过垃圾邮件筛选**。

## <a name="new-to-microsoft-365"></a>是 Microsoft 365 的新增功能？

****

![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **到 Microsoft 365** 的简短图标 发现 LinkedIn Learning 为 **Microsoft 365** 管理员和 IT 专业人员提供的免费视频课程。
