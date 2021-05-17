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
description: 管理员可以了解如何在 EOP Exchange Online Protection (配置) 以允许或阻止来自电子邮件服务器的电子邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 2b940aadb4ff5f2c4676ac2411ea3e95a25c7855
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203807"
---
# <a name="configure-connection-filtering"></a>配置连接筛选

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)


如果你是在 Exchange Online 中拥有邮箱的 Microsoft 365 客户，或者没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 客户，请使用 EOP (中的连接筛选，特别是默认连接筛选器策略) 通过 IP 地址标识好或坏的源电子邮件服务器。 默认连接筛选器策略的关键组件包括：

- **IP 允许列表**：跳过对来自按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件的垃圾邮件筛选。 有关这些来源的邮件仍可能发生垃圾邮件筛选的方案，请参阅本文稍后介绍的从 [IP](#scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered) 允许列表来源筛选邮件的方案部分。 有关 IP 允许列表如何适合整体安全发件人策略的信息，请参阅在 EOP 中创建 [安全发件人列表](create-safe-sender-lists-in-office-365.md)。

- **IP 阻止列表**：阻止来自按 IP 地址或 IP 地址范围指定的源电子邮件服务器的所有传入邮件。 传入的邮件被拒绝，不会标记为垃圾邮件，并且不会进行其他筛选。 有关 IP 阻止列表如何适合整体阻止的发件人策略，请参阅在 EOP 中创建 [阻止发件人列表](create-block-sender-lists-in-office-365.md)。

- **保险箱列表**：安全 *列表是* Microsoft 数据中心中的动态允许列表，无需客户配置。 Microsoft 从订阅到各种第三方列表标识这些受信任的电子邮件源。 启用或禁用安全列表的使用;无法配置安全列表上的源电子邮件服务器。 对来自安全列表上的电子邮件服务器的传入邮件跳过垃圾邮件筛选。

本主题介绍如何 &在安全与合规中心或 PowerShell (Exchange Online PowerShell 中为邮箱位于 Exchange Online 中的 Microsoft 365 组织配置默认连接筛选器Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。 有关 EOP 如何使用连接筛选是组织整体反垃圾邮件设置的一部分，请参阅 [反垃圾邮件保护](anti-spam-protection.md)。

> [!NOTE]
> IP 允许列表、安全列表和 IP 阻止列表是允许或阻止组织中电子邮件的总体策略的一部分。 有关详细信息，请参阅创建[安全发件人列表和](create-safe-sender-lists-in-office-365.md)[创建阻止的发件人列表](create-block-sender-lists-in-office-365.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要修改默认连接筛选器策略，您必须是组织管理或 **安全管理员角色组** 的成员。 
  - 若要对默认连接筛选器策略进行只读访问，您需要是全局读取 **者** 角色组或安全读者 **角色组的成员** 。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：

  - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 若要查找要允许或阻止的电子邮件服务器的源 IP 地址 (发件人) ，可以检查邮件头中的连接 IP (**CIP**) 头字段。 若要查看各种电子邮件客户端中的邮件头，请参阅在电子邮件客户端中查看[Outlook。](https://support.microsoft.com/office/cd039382-dc6e-4264-ac74-c048563d212c)

- IP 允许列表优先于 IP 阻止列表 (两个列表上的地址不会) 。

- IP 允许列表和 IP 阻止列表最多支持 1273 个条目，其中条目是单个 IP 地址、IP 地址范围或无类别域际路由 (CIDR) IP。

## <a name="use-the-security--compliance-center-to-modify-the-default-connection-filter-policy"></a>使用安全&合规中心修改默认连接筛选器策略

1. 在安全&中心，转到"**威胁管理** \> **策略** \> **""反垃圾邮件"。**

2. 在"**反垃圾邮件设置"页上**，展开"**连接筛选器** 策略"，方法是单击"展开 ![ "图标， ](../../media/scc-expand-icon.png) 然后单击"编辑 **策略"。**

3. 在出现的 **"** 默认"飞出中，配置以下任一设置：

   - **说明**：输入可选的描述性文本。

   - **IP 允许列表：单击**"**编辑"。** 在出现的 **"IP 允许列表**"飞出框中，使用以下语法在"地址或地址范围"框中输入 IPV4 地址：

     - 单个 IP：例如，192.168.1.1。

     - IP 范围：例如，192.168.0.1-192.168.0.254。

     - CIDR IP：例如，192.168.0.1/25。 有效的网络掩码值为 /24 到 /32。 若要将 CIDR IP 掩码值 /1 的垃圾邮件筛选跳过为 /23，请参阅本文稍后在可用范围外跳过 [CIDR IP](#skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range) 的垃圾邮件筛选部分。

     若要添加 IP 地址或地址范围，请单击" **添加添加图标** ![ ](../../media/ITPro-EAC-AddIcon.png) "。 若要删除条目，请选择"允许的 **IP** 地址"中的条目，然后单击" **删除""删除** ![ ](../../media/scc-remove-icon.png) "。 完成后，单击“**保存**”。

   - **IP 阻止列表：** 单击"**编辑"。** 在出现的 **"IP 阻止列表**"飞出框中，在"地址或地址范围"框中输入单个 IP、IP 范围或 CIDR IP，如 **前面"IP 允许列表"设置** 中所述。 

     若要添加 IP 地址或地址范围，请单击" **添加添加图标** ![ ](../../media/ITPro-EAC-AddIcon.png) "。 若要删除条目，请选择"阻止的 **IP** 地址"中的条目，然后单击" **删除""删除** ![ ](../../media/scc-remove-icon.png) "。 完成后，单击“**保存**”。

   - **打开安全列表**：启用或禁用安全列表，以标识将跳过垃圾邮件筛选的已知、良好的发件人。

4. 完成后，单击“**保存**”。

## <a name="use-the-security--compliance-center-to-view-the-default-connection-filter-policy"></a>使用安全&中心查看默认连接筛选器策略

1. 在安全&中心，转到"**威胁管理** \> **策略** \> **""反垃圾邮件"。**

2. 在 **"反垃圾邮件设置"** 页上，单击名为"连接筛选器策略"的默认策略 **旁边的下拉列表**。

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

- 若要 *使用* 指定的值覆盖任何现有条目，请使用以下语法： `IPAddressOrRange1,IPAddressOrRange2,...,IPAddressOrRangeN` 。

- 若要 *添加或删除* IP 地址或地址范围而不影响其他现有条目，请使用以下语法： `@{Add="IPAddressOrRange1","IPAddressOrRange2",...,"IPAddressOrRangeN";Remove="IPAddressOrRange3","IPAddressOrRange4",...,"IPAddressOrRangeN"}` 。

- 若要清空 IP 允许列表或 IP 阻止列表，请使用值 `$null` 。

此示例使用指定的 IP 地址和地址范围配置 IP 允许列表和 IP 阻止列表。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList 192.168.1.10,192.168.1.23 -IPBlockList 10.10.10.0/25,172.17.17.0/24
```

此示例在 IP 允许列表中添加和删除指定的 IP 地址和地址范围。

```powershell
Set-HostedConnectionFilterPolicy -Identity Default -IPAllowList @{Add="192.168.2.10","192.169.3.0/24","192.168.4.1-192.168.4.5";Remove="192.168.1.10"}
```

有关语法和参数的详细信息，请参阅 [Set-HostedConnectionFilterPolicy](/powershell/module/exchange/set-hostedconnectionfilterpolicy)。

## <a name="how-do-you-know-this-worked"></a>如何知道操作成功？

若要验证是否成功修改了默认连接筛选器策略，请执行下列任一步骤：

- 在安全&合规中心，转到"威胁管理策略""反垃圾邮件"，单击"连接筛选器策略""始终打开 (旁边的下拉列表) 验证 \>  \>  \> 设置。 

- 在 Exchange Online PowerShell 或独立 EOP PowerShell 中，运行以下命令并验证设置：

  ```powershell
  Get-HostedConnectionFilterPolicy -Identity Default
  ```

- 从 IP 允许列表上的条目发送测试邮件。

## <a name="additional-considerations-for-the-ip-allow-list"></a>IP 允许列表的其他注意事项

以下各节确定了配置 IP 允许列表时您需要了解的其他项目。

### <a name="skip-spam-filtering-for-a-cidr-ip-outside-of-the-available-range"></a>跳过对可用范围之外的 CIDR IP 的垃圾邮件筛选

如本文前面所述，只能在 IP 允许列表中使用网络掩码为 /24 到 /32 的 CIDR IP。 若要跳过对来自 /1 到 /23 范围内源电子邮件服务器的邮件的垃圾邮件筛选，您需要使用 Exchange 邮件流规则 (也称为传输规则) 。 但是，我们建议你尽可能不要这样做，因为如果 /1 到 /23 CIDR IP 范围中的 IP 地址出现在任何 Microsoft 专有或第三方阻止列表中，邮件将被阻止。

现在，您完全意识到潜在问题，您至少可以使用以下设置 (创建邮件流规则) 以确保来自这些 IP 地址的邮件将跳过垃圾邮件筛选：

- 规则 **条件：** 如果发件人 IP 地址位于以下任一范围内或与输入 CIDR IP (\>  \>  \> /1 到 /23 网络掩码完全匹配，则应用此规则) 。

- 规则操作 **：修改邮件属性** 将垃圾邮件可信度设置为 \> **(SCL**) \> **绕过垃圾邮件筛选**。

您可以在特定时段内审核规则、测试规则、激活规则以及其他选择。 我们建议首先在一段时间内测试规则，然后再强制应用。 有关详细信息，请参阅管理[邮件流规则Exchange Online。](/Exchange/security-and-compliance/mail-flow-rules/manage-mail-flow-rules)

### <a name="skip-spam-filtering-on-selective-email-domains-from-the-same-source"></a>跳过来自同一来源的选择性电子邮件域的垃圾邮件筛选

通常，将 IP 地址或地址范围添加到 IP 允许列表意味着信任来自该电子邮件源的所有传入邮件。 但是，如果该源从多个域发送电子邮件，并且您希望跳过其中某些域（而非其他域）的垃圾邮件筛选，那又如何呢？ 不能单独使用 IP 允许列表来这样做，但可以将 IP 允许列表与邮件流规则结合使用。

例如，源电子邮件服务器 192.168.1.25 从 contoso.com、fabrikam.com 和 tailspintoys.com 域发送电子邮件，但您只想跳过对 fabrikam.com 中发件人的邮件的垃圾邮件筛选。 为此，请使用以下步骤：

1. 将 192.168.1.25 添加到 IP 允许列表。

2. 配置邮件流规则，至少 (以下) ：

   - 规则 **条件：** 如果发件人 IP 地址位于上述任一范围内或完全匹配 \>  \> 192.168.1.25 (则应用此规则，该 IP 地址或地址范围与在上一步骤) 中添加到 IP 允许列表的 IP 地址或地址范围完全匹配。 \>

   - 规则操作 **：修改邮件属性** 将垃圾邮件可信度设置为 \> **(SCL)** \> **0。**

   - 规则例外 **：发件人** 域 fabrikam.com (要跳过垃圾邮件筛选的一个或多个 \>  \>) 。

### <a name="scenarios-where-messages-from-sources-in-the-ip-allow-list-are-still-filtered"></a>仍筛选来自 IP 允许列表中的源的邮件的方案

在下列情况下，来自 IP 允许列表中电子邮件服务器的邮件仍受垃圾邮件筛选限制：

- IP 允许列表中的 IP 地址也在 Microsoft 365 (中任何租户的基于 IP 的入站内部部署连接器中配置，让我们调用此租户 A) ，租户 A 和首次遇到邮件的 EOP 服务器正好位于 Microsoft 数据中心中的同一 *Active* Directory 林中。 在此方案中 **，IPV：CAL** 将添加到邮件的反垃圾邮件邮件头 [ (](anti-spam-message-headers.md)指示邮件绕过了垃圾邮件筛选) ，但邮件仍受垃圾邮件筛选限制。

- 包含 IP 允许列表的租户和首次遇到邮件的 EOP 服务器都发生在 Microsoft 数据中心的不同 *Active* Directory 林中。 在这种情况下 **，IPV：CAL** *不会* 添加到邮件头，因此邮件仍受垃圾邮件筛选限制。

如果遇到上述任一情况，则至少可以使用以下设置 (创建邮件流规则) 以确保来自有问题的 IP 地址的邮件跳过垃圾邮件筛选：

- 规则条件 **：如果** 发件人 IP 地址位于以下任一范围内或与 IP 地址 (完全匹配，则应用此 \>  \>  \>) 。

- 规则操作 **：修改邮件属性** 将垃圾邮件可信度设置为 \> **(SCL**) \> **绕过垃圾邮件筛选**。

## <a name="new-to-microsoft-365"></a>是新Microsoft 365？

****

![LinkedIn Learning New ](../../media/eac8a413-9498-4220-8544-1e37d1aaea13.png) **to Microsoft 365？** 发现 LinkedIn Learning Microsoft 365为管理员 **和 IT** 专业人员提供的免费视频课程。