---
title: 配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到 SecOps 邮箱
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
ms.custom: ''
description: 管理员可以了解如何使用 Exchange Online Protection (EOP) 中的高级传递策略识别不应在支持的特定方案中筛选的邮件 (第三方网络钓鱼模拟和传递到安全操作 (SecOps) 邮箱的邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b8d5aba4974bf4ac179f88a08ae5f8c037fa0a71
ms.sourcegitcommit: be074f57e33c811bb3857043152825209bc8af07
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2021
ms.locfileid: "60335534"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>配置向用户传递第三方网络钓鱼模拟以及将未筛选邮件发送到 SecOps 邮箱

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

若要在默认情况下保证[](secure-by-default.md)组织安全，Exchange Online Protection (EOP) 不允许对标识为恶意软件或高可信度网络钓鱼的邮件进行安全列表或筛选绕过。 但是，有一些特定方案需要传递未筛选的邮件。 例如：

- **第三方网络钓鱼模拟**：模拟攻击可以帮助你在真实攻击影响组织之前识别易受攻击的用户。
- **SecOps (** 安全) ：安全团队用于收集和分析未筛选邮件的专用邮箱 (无论邮件好还是坏) 。

在邮件 _中，可以使用_ Microsoft 365策略来阻止筛选这些 _特定方案中的_ 入站邮件。 <sup>\*</sup>高级传递策略可确保这些方案中的邮件获得以下结果：

- EOP 和 Microsoft Defender 中的筛选器Office 365这些邮件不执行任何操作。<sup>\*</sup>
- [零时差清除 (对 ](zero-hour-auto-purge.md)) 和网络钓鱼的 ZAP 邮件不执行任何操作。<sup>\*</sup>
- [对于这些方案](/microsoft-365/compliance/alert-policies#default-alert-policies) ，不会触发默认系统警报。
- [AIR 和 Defender for Office 365](office-365-air.md)将忽略这些消息。
- 专用于第三方网络钓鱼模拟：
  - [管理员提交](admin-submission.md) 会生成自动响应，指出邮件是网络钓鱼模拟活动的一部分，不是真正的威胁。 不会触发警报和 AIR。 管理员提交体验将这些邮件作为模拟威胁显示。
  - 当用户使用报告网络钓鱼外接程序 for Outlook 报告网络钓鱼模拟邮件时，系统[不会](enable-the-report-message-add-in.md)生成警报、调查或事件。 邮件还会显示在提交页面的"用户报告的邮件"选项卡上。
  - [保险箱 Defender for Office 365](safe-links.md)中的链接不会在单击时阻止或触发这些邮件中专门标识的 URL。 URL 仍被封装，但不被阻止。
  - [保险箱 Defender for Office 365](safe-attachments.md)中的附件不会触发这些邮件中的附件。

<sup>\*</sup> 无法绕过恶意软件筛选或恶意软件的 ZAP。

由高级传递策略标识的邮件不是安全威胁，因此邮件使用系统替代进行标记。 由于网络钓鱼模拟系统覆盖或 **SecOps** 邮箱系统覆盖，管理员体验将显示这些邮件。 管理员可以在下列体验中筛选和分析这些系统替代：

- [威胁资源管理器/实时检测在 Defender for Office 365计划 2：](threat-explorer.md)管理员可以筛选系统替代源并选择 **网络钓鱼模拟** 或 **SecOps 邮箱**。
- 威胁资源管理器 [/](mdo-email-entity-page.md)实时检测中的电子邮件实体页面：管理员可以查看 **SecOps** 邮箱或"覆盖"部分中的"租户替代"下的网络钓鱼模拟 (组织策略 **) 的邮件。** 
- 威胁[防护状态报告](view-email-security-reports.md#threat-protection-status-report)：管理员可以在下拉菜单中按系统覆盖查看数据进行筛选，并选择查看由于网络钓鱼模拟系统覆盖而允许的邮件。 To see messages allowed by the SecOps mailbox override， you can select **chart breakdown by delivery location** in the chart breakdown by **reason** drop down menu.
- [Microsoft Defender for Endpoint 中的](../defender-endpoint/advanced-hunting-overview.md)高级搜寻：网络钓鱼模拟和 SecOps 邮箱系统覆盖在 EmailEvents 中的 OrgLevelPolicy 中将显示为选项。
- [Campaign Views](campaigns.md)： Admin can filter on **System override source** and select either **Phishing simulation** or **SecOps Mailbox**.

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到高级传递 **页面，** 请打开 <https://security.microsoft.com/advanceddelivery> 。

- 若要连接到安全与合规中心 PowerShell，请参阅[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

- 您需获得权限，然后才能执行本文中的过程：
  - 若要在高级传递策略中创建、修改或删除配置的设置，您需要是 Microsoft 365 Defender 门户中安全管理员角色组的成员以及 **Exchange Online** 中的组织管理角色 **组** 的成员。 
  - 若要对高级传递策略进行只读访问，你需要是全局读者或安全读者 **角色组** 的成员。

  有关详细信息，请参阅 Microsoft 365 Defender[门户中的权限](permissions-microsoft-365-security-center.md)和 Exchange Online 中[的权限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  > 将用户添加到相应的 Azure Active Directory 角色会为用户提供在 Microsoft 365 Defender _门户中_ 所需的权限，以及用户对 Microsoft 365 中其他功能Microsoft 365。 有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>使用Microsoft 365 Defender门户在高级传递策略中配置 SecOps 邮箱

1. 在 Microsoft 365 Defender 门户中，转到"规则"部分中的"电子邮件&协作策略& \> **规则** \> **威胁策略** 高级 \> 传递"。 

2. 在" **高级传递"** 页上，确认 **"SecOps** 邮箱"选项卡已选中，然后执行下列步骤之一：
   - 单击 ![ "编辑"图标。](../../media/m365-cc-sc-edit-icon.png) **编辑**。
   - 如果没有配置网络钓鱼模拟，请单击"添加 **"。**

3. 在打开的"编辑 **SecOps** 邮箱"飞出控件上，通过执行以下步骤之一输入要指定为 SecOps 邮箱的现有 Exchange Online 邮箱：
   - 在框中单击，让邮箱列表解析，然后选择邮箱。
   - 单击框中开始键入邮箱 (名称、显示名称、别名、电子邮件地址、帐户名等 ) 的标识符，然后从结果 (显示名称) 邮箱名称。

     根据需要重复执行此步骤（次数不限）。 不允许通讯组。

     若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

4. 完成后，单击“**保存**”。

您配置的 SecOps 邮箱条目显示在 **SecOps** 邮箱选项卡上。若要进行更改，请单击"编辑 ![ "图标。](../../media/m365-cc-sc-edit-icon.png) **在** 选项卡上编辑。

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>使用Microsoft 365 Defender门户在高级传递策略中配置第三方网络钓鱼模拟

1. 在 Microsoft 365 Defender 门户中，转到"规则"部分中的"电子邮件&协作策略& \> **规则** \> **威胁策略** 高级 \> 传递"。 

2. 在" **高级传递"** 页上，选择" **网络钓鱼模拟** "选项卡，然后执行下列步骤之一：
   - 单击 ![ "编辑"图标。](../../media/m365-cc-sc-edit-icon.png) **编辑**。
   - 如果没有配置网络钓鱼模拟，请单击"添加 **"。**

3. 在打开 **的"编辑第三方网络钓鱼** 模拟"飞出控件上，配置以下设置：

   - 域：展开此设置并输入至少一个电子邮件地址域 (例如，单击该框，输入值，然后按 Enter 或选择显示在框下方的值来输入 contoso.com) 。 根据需要重复执行此步骤（次数不限）。 您最多可以添加 20 个条目。

     > [!NOTE]
     > 使用地址 (也称为邮件发件人地址、P1 发件人或信封发件人) ，用于邮件的 SMTP 传输或由网络钓鱼模拟供应商指定的域密钥识别邮件 `5321.MailFrom` (DKIM) 域。 

   - **发送 IP：** 展开此设置并输入至少一个有效的 IPv4 地址，方法是单击框，输入值，然后按 Enter 或选择框下方显示的值。 根据需要重复执行此步骤（次数不限）。 您最多可以添加 10 个条目。 有效值包含:
     - 单个 IP：例如，192.168.1.1。
     - IP 范围：例如，192.168.0.1-192.168.0.254。
     - CIDR IP：例如，192.168.0.1/25。
   - 要允许的模拟 URL：展开此设置，并选择输入属于网络钓鱼模拟活动的一部分的特定 URL，这些 URL 不应被阻止或触发，方法是单击框，输入值，然后按 Enter 或选择框下方显示的值。 您最多可以添加 10 个条目。 有关 URL 语法格式，请参阅 [租户允许/阻止列表的 URL 语法](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list)。 这些 URL 在单击时封装，但不被阻止。

   若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

   > [!NOTE]
   > 若要在高级传递中配置第三方网络钓鱼模拟，需要提供以下信息：
   > 
   > - 至少来自 **以下任** 一源的一个域：
   >   - 地址 `5321.MailFrom` (MAIL FROM 地址、P1 发件人或信封发件人) 。
   >   - DKIM 域。
   > - 至少一个 **发送 IP**。
   > 
   > 可以选择包括模拟 **URL，以确保** 不会阻止模拟消息中的 URL。
   > 您可以为每个字段指定最多 10 个条目。
   > 在至少一个域和一个发送 **IP** 上必须存在匹配项，但不会维护值之间的关联。

4. 完成后，请执行下列步骤之一：
   - **第一次**：单击 **"添加"，** 然后单击"关闭 **"。**
   - **编辑现有**：单击"**保存"，** 然后单击"关闭 **"。**

您配置的第三方网络钓鱼模拟条目显示在"网络钓鱼模拟 **"选项卡上** 。若要进行更改，请单击"编辑 ![ "图标。](../../media/m365-cc-sc-edit-icon.png) **在** 选项卡上编辑。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>需要筛选旁路的其他方案

除了高级传递策略可以帮助你的两种方案之外，还有其他一些方案可能需要绕过筛选：

- **第三方筛选器**：如果你的域的 MX记录没有指向Office 365 (邮件将路由到其他位置) ，默认情况下，安全 [](secure-by-default.md)*不可用*。 如果要添加保护，则需要启用连接器的增强筛选 (也称为跳过 *列表) 。* 有关详细信息，请参阅[使用第三](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)方云服务管理邮件流Exchange Online。 如果您不希望增强连接器筛选，请使用邮件流规则 (也称为传输规则) ，以绕过 Microsoft 筛选已由第三方筛选评估的邮件。 有关详细信息，请参阅使用[邮件流规则设置邮件中的 SCL。](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl.md)

- 正在审查 **的** 误报：你可能希望暂时允许 Microsoft 通过管理员提交仍在分析的某些邮件报告被错误地标记为 [](admin-submission.md)对 Microsoft (误报) 。 与所有替代一样， **_我们强烈建议这些_** 允许是临时的。

## <a name="security--compliance-center-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>安全&高级传递策略中针对 SecOps 邮箱的 Security &-Compliance Center PowerShell 过程

在安全&合规中心 PowerShell 中，高级传递策略中 SecOps 邮箱的基本元素为：

- **SecOps 覆盖策略**：由 **\* -SecOpsOverridePolicy** cmdlet 控制。
- **SecOps 重写规则**：由 **\* -SecOpsOverrideRule** cmdlet 控制。

此行为具有以下结果：

- 首先创建策略，然后创建标识规则所适用的策略的规则。
- 从 PowerShell 中删除策略时，也会删除相应的规则。
- 从 PowerShell 中删除规则时，不会删除相应的策略。 需要手动删除相应的策略。

### <a name="use-powershell-to-configure-secops-mailboxes"></a>使用 PowerShell 配置 SecOps 邮箱

在 PowerShell 的高级传递策略中配置 SecOps 邮箱的过程包含两个步骤：

1. 创建 SecOps 覆盖策略。
2. 创建 SecOps 替代规则，该规则指定应用该规则的策略。

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>步骤 1：使用 PowerShell 创建 SecOps 覆盖策略

若要创建 SecOps 覆盖策略，请使用以下语法：

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

> [!NOTE]
> 无论您指定的 Name 值如何，策略名称都将为 _SecOpsOverridePolicy，_ 因此您可能还使用该值。

本示例将创建 SecOps 邮箱策略。

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

有关语法和参数的详细信息，请参阅 [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy)。

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>步骤 2：使用 PowerShell 创建 SecOps 替代规则

此示例使用指定的设置创建 SecOps 邮箱规则。

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

> [!NOTE]
> 无论指定 Name 值如何，规则名称将为 _SecOpsOverrideRule，_ 其中是唯一的 GUID 值 \<GUID\> (例如 \<GUID\> ，6fed4b63-3563-495d-a481-b24a311f8329) 。

有关语法和参数的详细信息，请参阅 [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule)。

### <a name="use-powershell-to-view-the-secops-override-policy"></a>使用 PowerShell 查看 SecOps 替代策略

此示例返回有关唯一一个 SecOps 邮箱策略的详细信息。

```powershell
Get-SecOpsOverridePolicy
```

有关语法和参数的详细信息，请参阅 [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy)。

### <a name="use-powershell-to-view-secops-override-rules"></a>使用 PowerShell 查看 SecOps 替代规则

此示例返回有关 SecOps 重写规则的详细信息。

```powershell
Get-SecOpsOverrideRule
```

尽管上一个命令只应返回一个规则，但结果中也可能包含任何等待删除的规则。

本示例标识一个规则 (规则) 无效的规则。

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

确定无效规则后，可以使用 **Remove-SecOpsOverrideRule** cmdlet 删除这些规则，如本文稍后 [所述](#use-powershell-to-remove-secops-override-rules)。

有关语法和参数的详细信息，请参阅 [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)。

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>使用 PowerShell 修改 SecOps 覆盖策略

若要修改 SecOps 覆盖策略，请使用以下语法：

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

此示例将 `secops2@contoso.com` 添加到 SecOps 替代策略。

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

> [!NOTE]
> 如果存在关联的有效 SecOps 替代规则，则规则中的电子邮件地址也将更新。

有关语法和参数的详细信息，请参阅 [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy)。

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>使用 PowerShell 修改 SecOps 替代规则

**Set-SecOpsOverrideRule** cmdlet 不会修改 SecOps 替代规则中的电子邮件地址。 若要修改 SecOps 替代规则中的电子邮件地址，请使用 **Set-SecOpsOverridePolicy** cmdlet。

有关语法和参数的详细信息，请参阅 [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule)。

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>使用 PowerShell 删除 SecOps 覆盖策略

本示例删除 SecOps 邮箱策略和相应的规则。

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

有关语法和参数的详细信息，请参阅 [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy)。

### <a name="use-powershell-to-remove-secops-override-rules"></a>使用 PowerShell 删除 SecOps 替代规则

若要删除 SecOps 替代规则，请使用以下语法：

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

本示例删除指定的 SecOps 重写规则。

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

有关语法和参数的详细信息，请参阅 [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule)。

## <a name="security--compliance-center-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>安全&高级传递策略中第三方网络钓鱼模拟的合规性中心 PowerShell 过程

在安全&合规中心 PowerShell 中，高级传递策略中第三方网络钓鱼模拟的基本元素为：

- **网络钓鱼模拟替代策略**：由 **\* -PhishSimOverridePolicy** cmdlet 控制。
- **网络钓鱼模拟替代规则**：由 **\* -PhishSimOverrideRule** cmdlet 控制。
- **允许的 (网络钓鱼) URL：** 由 **\* -TenantAllowBlockListItems** cmdlet 控制。

此行为具有以下结果：

- 首先创建策略，然后创建标识规则所适用的策略的规则。
- 您可以分别修改策略和规则中的设置。
- 从 PowerShell 中删除策略时，也会删除相应的规则。
- 从 PowerShell 中删除规则时，不会删除相应的策略。 需要手动删除相应的策略。

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>使用 PowerShell 配置第三方网络钓鱼模拟

在 PowerShell 中配置第三方网络钓鱼模拟是一个多步骤过程：

1. 创建网络钓鱼模拟替代策略。
2. 创建钓鱼模拟替代规则，该规则指定：
   - 规则应用于的策略。
   - 网络钓鱼模拟邮件的源 IP 地址。
3. （可选）标识应允许的网络钓鱼 (URL，即未阻止或扫描) 。

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>步骤 1：使用 PowerShell 创建网络钓鱼模拟覆盖策略

此示例创建网络钓鱼模拟替代策略。

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**注意**：无论指定 Name 值如何，策略名称将为 _PhishSimOverridePolicy，_ 因此您可能还使用该值。

有关语法和参数的详细信息，请参阅 [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy)。

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>步骤 2：使用 PowerShell 创建网络钓鱼模拟替代规则

使用以下语法：

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -Domains <Domain1>,<Domain2>,...<Domain10> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntry10>
```

无论指定 Name 值如何，规则名称都是 _PhishSimOverrideRule，_ 其中是唯一的 GUID 值 (例如 \<GUID\> \<GUID\> ，a0eae53e-d755-4a42-9320-b9c6b55c5011) 。

有效的 IP 地址条目是下列值之一：

- 单个 IP：例如，192.168.1.1。
- IP 范围：例如，192.168.0.1-192.168.0.254。
- CIDR IP：例如，192.168.0.1/25。

此示例使用指定的设置创建网络钓鱼模拟替代规则。

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -Domains fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

有关语法和参数的详细信息，请参阅 [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule)。

#### <a name="step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow"></a>步骤 3： (可选) 使用 PowerShell 标识要允许的网络钓鱼模拟 URL

使用以下语法：

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries "<URL1>","<URL2>",..."<URL10>" <[-NoExpiration] | [-ExpirationDate <DateTime>]>
```

有关 URL 语法的详细信息，请参阅 [租户允许/阻止列表的 URL 语法](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list)。

此示例为指定的第三方网络钓鱼模拟 URL 添加一个 URL 允许条目，没有过期时间。

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries *.fabrikam.com -NoExpiration
```

有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>使用 PowerShell 查看网络钓鱼模拟替代策略

此示例返回有关唯一网络钓鱼模拟替代策略的详细信息。

```powershell
Get-PhishSimOverridePolicy
```

有关语法和参数的详细信息，请参阅 [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy)。

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>使用 PowerShell 查看网络钓鱼模拟替代规则

此示例返回有关网络钓鱼模拟替代规则的详细信息。

```powershell
Get-PhishSimOverrideRule
```

尽管上一个命令只应返回一个规则，但结果中也可能包含任何等待删除的规则。

本示例标识一个规则 (规则) 无效的规则。

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

确定无效规则后，可以使用 **Remove-PhishSimOverrideRule** cmdlet 删除这些规则，如本文稍后 [所述](#use-powershell-to-remove-phishing-simulation-override-rules)。

有关语法和参数的详细信息，请参阅 [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule)。

### <a name="use-powershell-to-view-the-allowed-phishing-simulation-url-entries"></a>使用 PowerShell 查看允许的网络钓鱼模拟 URL 条目

若要查看允许的网络钓鱼模拟 URL，请运行以下命令：

```powershell
Get-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery
```

有关语法和参数的详细信息，请参阅 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>使用 PowerShell 修改网络钓鱼模拟替代策略

若要修改网络钓鱼模拟替代策略，请使用以下语法：

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

此示例禁用网络钓鱼模拟替代策略。

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

有关语法和参数的详细信息，请参阅 [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy)。

### <a name="use-powershell-to-modify-phishing-simulation-override-rules"></a>使用 PowerShell 修改网络钓鱼模拟替代规则

若要修改网络钓鱼模拟替代规则，请使用以下语法：

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

此示例使用下列设置修改指定的网络钓鱼模拟替代规则：

- 添加域条目 blueyonderairlines.com。
- 删除 IP 地址条目 192.168.1.55。

请注意，这些更改不会影响现有条目。

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

有关语法和参数的详细信息，请参阅 [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule)。

### <a name="use-powershell-to-modify-the-allowed-phishing-simulation-url-entries"></a>使用 PowerShell 修改允许的网络钓鱼模拟 URL 条目

不能直接修改 URL 值。 您可以[删除现有 URL 条目并](#use-powershell-to-remove-the-allowed-phishing-simulation-url-entries)[添加新的 URL](#step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow)条目，如本文所述。

若要修改允许的网络钓鱼模拟 URL 条目的其他 (例如到期日期或注释) ，请使用以下语法：

```powershell
Set-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery <[-NoExpiration] | [-ExpirationDate <DateTime>]> [-Notes <String>]
```

通过 _Entries_ 参数) 或 **Get-TenantAllowBlockListItems** cmdlet 的输出中的 Identity 值 (_Ids_ 参数) ，可以标识要修改的 (条目。

本示例修改了指定条目的到期日期。

```powershell
Set-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery –Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

有关语法和参数的详细信息，请参阅 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>使用 PowerShell 删除网络钓鱼模拟替代策略

此示例删除网络钓鱼模拟覆盖策略和相应的规则。

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

有关语法和参数的详细信息，请参阅 [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy)。

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>使用 PowerShell 删除网络钓鱼模拟替代规则

若要删除网络钓鱼模拟替代规则，请使用以下语法：

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

此示例删除指定的网络钓鱼模拟替代规则。

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

有关语法和参数的详细信息，请参阅 [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule)。

### <a name="use-powershell-to-remove-the-allowed-phishing-simulation-url-entries"></a>使用 PowerShell 删除允许的网络钓鱼模拟 URL 条目

若要删除现有的网络钓鱼模拟 URL 条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery
```

通过 _Entries_ 参数) 或 **Get-TenantAllowBlockListItems** cmdlet 的输出中的 Identity 值 (_Ids_ 参数) ，可以标识要修改的 (条目。

本示例修改了指定条目的到期日期。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery –Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

有关语法和参数的详细信息，请参阅 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。
