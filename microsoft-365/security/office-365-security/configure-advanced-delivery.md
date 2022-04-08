---
title: 配置向用户传递第三方网络钓鱼模拟以及向 SecOps 邮箱传递未经筛选的消息
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
description: 管理员可以了解如何在 Exchange Online Protection (EOP) 中使用高级传递策略来标识不应在特定受支持方案中筛选的消息， (第三方网络钓鱼模拟以及传递给安全操作的消息 (SecOps) 邮箱。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6ca3b62bba9a22d8c7c9f3f37dc191d1f458b523
ms.sourcegitcommit: 1c5f9d17a8b095cd88b23f4874539adc3ae021de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/08/2022
ms.locfileid: "64713902"
---
# <a name="configure-the-delivery-of-third-party-phishing-simulations-to-users-and-unfiltered-messages-to-secops-mailboxes"></a>配置向用户传递第三方网络钓鱼模拟以及向 SecOps 邮箱传递未经筛选的消息

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

为了[在默认情况下](secure-by-default.md)保护组织的安全，Exchange Online Protection (EOP) 不允许安全列表或筛选被标识为恶意软件或高可信度网络钓鱼的消息的旁路。 但是，有些特定方案需要传递未经筛选的消息。 例如：

- **第三方网络钓鱼模拟**：模拟攻击可以帮助你在实际攻击影响组织之前识别易受攻击的用户。
- **SecOps (安全操作) 邮箱**：安全团队用来收集和分析未筛选邮件的专用邮箱 (好坏) 。

在Microsoft 365中使用 _高级传递策略_ 可防止 _在这些特定方案中_ 筛选入站消息。<sup>\*</sup>高级传递策略可确保这些方案中的消息能够获得以下结果：

- EOP 中的筛选器和Microsoft Defender for Office 365不会对这些消息执行任何操作。<sup>\*</sup>
- [零小时清除 (用于 ](zero-hour-auto-purge.md) 垃圾邮件和网络钓鱼的 ZAP) 不会对这些消息执行任何操作。<sup>\*\*</sup>
- 对于这些方案，不会触发[默认系统警报](/microsoft-365/compliance/alert-policies#default-alert-policies)。
- [DEFENDER FOR OFFICE 365中的 AIR 和群集](office-365-air.md)会忽略这些消息。
- 专用于第三方网络钓鱼模拟：
  - [管理员提交](admin-submission.md) 会生成一个自动响应，指出该消息是网络钓鱼模拟活动的一部分，不是真正的威胁。 不会触发警报和 AIR。 管理员提交体验会将这些消息显示为模拟威胁。
  - 当用户使用 [报表消息或报表网络钓鱼加载项](enable-the-report-message-add-in.md)报告网络钓鱼模拟消息时，系统不会生成警报、调查或事件。 链接或文件不会被引爆，但消息也会显示在 **"提交**"页的 **"用户报告消息**"选项卡上。
  - [保险箱Defender for Office 365中的链接](safe-links.md)在单击时不会阻止或引爆这些消息中特别标识的 URL。 URL 仍被包装，但不会被阻止。
  - [保险箱Defender for Office 365中的附件](safe-attachments.md)不会在这些消息中引爆附件。

<sup>\*</sup> 无法绕过恶意软件筛选。

<sup>\*\*</sup> 可以通过为禁用 ZAP for 恶意软件的 ZAP 的 SecOps 邮箱创建反恶意软件策略来绕过 ZAP 处理恶意软件。 有关说明，请参阅 [EOP 中配置反恶意软件策略](configure-anti-malware-policies.md)。

由高级传递策略标识的消息不是安全威胁，因此消息会被系统覆盖标记。 管理员体验将显示这些邮件，因为网络 **钓鱼模拟** 系统被覆盖或 **SecOps 邮箱** 系统重写。 管理员可以在以下体验中筛选和分析这些系统替代：

- [Defender for Office 365计划 2 中的威胁资源管理器/实时检测](threat-explorer.md)：管理员可以筛选 **系统替代源**，并选择 **网络钓鱼模拟** 或 **SecOps 邮箱**。
- [威胁资源管理器/实时检测中的电子邮件实体页](mdo-email-entity-page.md)：管理员可以在 **"替代" (的)** 部分中查看由 **SecOps 邮箱** 或 **网络钓鱼模拟** 在 **租户覆盖** 下允许的组织策略允许的消息。
- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)：管理员可以通过在下拉菜单中 **按系统重写查看数据** 进行筛选，并选择查看因网络钓鱼模拟系统替代而允许的消息。 若要查看 SecOps 邮箱替代允许的消息，可按图表明细中的 **传递位置** 按原因下拉菜单选择 **图表明细** 。
- [Microsoft Defender for Endpoint中的高级搜寻](../defender-endpoint/advanced-hunting-overview.md)：网络钓鱼模拟和 SecOps 邮箱系统替代将显示为 EmailEvents 中 OrgLevelPolicy 中的选项。
- [市场活动视图](campaigns.md)：管理员可以筛选 **系统替代源** ，并选择 **网络钓鱼模拟** 或 **SecOps 邮箱**。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到 **"高级交付** "页，请打开 <https://security.microsoft.com/advanceddelivery>。

- 若要连接到安全与合规中心 PowerShell，请参阅[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

- 需要分配权限，然后才能执行本文中的过程：
  - 若要在高级交付策略中创建、修改或删除配置的设置，需要成为 **Microsoft 365 Defender门户** 中 **安全管理员** 角色组的成员，以及 **Exchange Online** 中的 **组织管理** 角色组的成员。
  - 若要对高级交付策略进行只读访问，需要成为 **全局读取者** 或 **安全读取者** 角色组的成员。

  有关详细信息，请参阅[Microsoft 365 Defender门户中的权限](permissions-microsoft-365-security-center.md)和[Exchange Online中的权限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  > 将用户添加到相应的Azure Active Directory角色可为用户提供Microsoft 365 Defender门户中所需的权限 _以及_ Microsoft 365中其他功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。

## <a name="use-the-microsoft-365-defender-portal-to-configure-secops-mailboxes-in-the-advanced-delivery-policy"></a>使用Microsoft 365 Defender门户在高级传递策略中配置 SecOps 邮箱

1. 在Microsoft 365 Defender门户中<https://security.microsoft.com>，转到"**规则**"部分 **中的"电子邮件&协作** \> **策略&规则** \> **威胁策略** \> **高级传递**。 若要直接转到 **"高级交付** "页，请使用 <https://security.microsoft.com/advanceddelivery>。

2. 在 **"高级传递** "页上，验证是否选择了 **SecOps 邮箱** 选项卡，然后执行以下步骤之一：
   - 单击 !["编辑"图标。](../../media/m365-cc-sc-edit-icon.png) **编辑**。
   - 如果没有配置的网络钓鱼模拟，请单击 **"添加**"。

3. 在打开 **的"编辑 SecOps"邮箱** 浮出控件中，输入要指定为 SecOps 邮箱的现有Exchange Online邮箱，执行以下步骤之一：
   - 单击框中，让邮箱列表解析，然后选择邮箱。
   - 单击框中，开始键入邮箱的标识符 (名称、显示名称、别名、电子邮件地址、帐户名称等) ，然后从结果中选择邮箱 (显示名称) 。

     根据需要重复执行此步骤（次数不限）。 不允许分发组。

     若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

4. 完成后，单击“**保存**”。

配置的 SecOps 邮箱条目显示在 **SecOps 邮箱** 选项卡上。若要进行更改，请单击 !["编辑"图标。](../../media/m365-cc-sc-edit-icon.png) **在** 选项卡上编辑。

## <a name="use-the-microsoft-365-defender-portal-to-configure-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>使用Microsoft 365 Defender门户在高级交付策略中配置第三方网络钓鱼模拟

1. 在Microsoft 365 Defender门户中<https://security.microsoft.com>，转到"**规则**"部分 **中的"电子邮件&协作** \> **策略&规则** \> **威胁策略** \> **高级传递**。 若要直接转到 **"高级交付** "页，请使用 <https://security.microsoft.com/advanceddelivery>。

2. 在 **"高级交付** "页上，选择 **"网络钓鱼模拟** "选项卡，然后执行以下步骤之一：
   - 单击 !["编辑"图标。](../../media/m365-cc-sc-edit-icon.png) **编辑**。
   - 如果没有配置的网络钓鱼模拟，请单击 **"添加**"。

3. 在打开 **的"编辑第三方网络钓鱼模拟** "浮出控件上，配置以下设置：

   - **域**：展开此设置并输入至少一个电子邮件地址域 (例如，contoso.com) 单击框中，输入值，然后按 Enter 或选择框下方显示的值。 根据需要重复执行此步骤（次数不限）。 最多可以添加 20 个条目。

     > [!NOTE]
     > 使用地址中的域 `5321.MailFrom` (也称为 **MAIL FROM** 地址、P1 发件人或信封发件人) ，这些发件人) 用于邮件的 SMTP 传输 **或** 网络钓鱼模拟供应商指定的 DomainKeys 识别邮件 (DKIM) 域。 

   - **发送 IP**：展开此设置并输入至少一个有效的 IPv4 地址，方法是单击框中，输入值，然后按 Enter 或选择框下方显示的值。 根据需要重复执行此步骤（次数不限）。 最多可以添加 10 个条目。 有效值为：
     - 单个 IP：例如 192.168.1.1。
     - IP 范围：例如 192.168.0.1-192.168.0.254。
     - CIDR IP：例如 192.168.0.1/25。
   - **模拟 URL 允许**：展开此设置，并选择输入特定 URL，这些 URL 是网络钓鱼模拟活动的一部分，不应阻止或引爆，方法是单击框中，输入值，然后按 Enter 或选择框下方显示的值。 最多可以添加 10 个条目。 有关 URL 语法格式，请参阅 [租户允许/阻止列表的 URL 语法](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list)。 这些 URL 在单击时包装，但不会被阻止。

   若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

   > [!NOTE]
   > 若要在高级交付中配置第三方网络钓鱼模拟，需要提供以下信息：
   > 
   > - 以下任一源中至少有一个 **域** ：
   >   - 地址 `5321.MailFrom` (也称为 MAIL FROM 地址、P1 发件人或信封发件人) 。
   >   - DKIM 域。
   > - 至少一个 **发送 IP**。
   > 
   > 可以选择性地包括 **模拟 URL，** 以确保不阻止模拟消息中的 URL。
   > 可以为每个字段指定最多 10 个条目。
   > 必须至少对一个 **域** 和一个 **发送 IP** 进行匹配，但不维护值之间的关联。

4. 完成后，请执行以下步骤之一：
   - **第一次**：单击 **"添加**"，然后单击 **"关闭**"。
   - **编辑现有** 内容：单击 **"保存** "，然后单击 **"关闭**"。

配置的第三方网络钓鱼模拟条目显示在 **网络钓鱼模拟** 选项卡上。若要进行更改，请单击 !["编辑"图标。](../../media/m365-cc-sc-edit-icon.png) **在** 选项卡上编辑。

## <a name="additional-scenarios-that-require-filtering-bypass"></a>需要绕过筛选的其他方案

除了高级交付策略可帮助你使用的两种方案外，还有其他一些方案可能需要你绕过筛选：

- **第三方筛选器**：如果域的 MX 记录 *不* 指向Office 365 (消息先路由到其他位置) ，则 [默认](secure-by-default.md)*情况下，安全不可用*。 如果要添加保护，则需要为连接器启用增强筛选 (也称为 *跳过列表*) 。 有关详细信息，请参阅[使用第三方云服务和Exchange Online管理邮件流](/exchange/mail-flow-best-practices/manage-mail-flow-using-third-party-cloud)。 如果不希望对连接器进行增强筛选，请使用邮件流规则 (也称为传输规则，) 绕过已由第三方筛选评估的消息的 Microsoft 筛选。 有关详细信息，请参阅 [使用邮件流规则在邮件中设置 SCL](/exchange/security-and-compliance/mail-flow-rules/use-rules-to-set-scl)。

- **正在审查的误报**：你可能希望暂时允许某些仍在由 Microsoft 通过 [管理员提交](admin-submission.md) 进行分析的消息报告已知的好消息，这些消息被错误地标记为对 Microsoft 有害 (误报) 。 与所有替代一样，我们 **_强烈建议_** 这些津贴是临时性的。

## <a name="security--compliance-center-powershell-procedures-for-secops-mailboxes-in-the-advanced-delivery-policy"></a>高级传送策略中 SecOps 邮箱的安全&合规中心 PowerShell 过程

在安全&合规中心 PowerShell 中，高级传递策略中 SecOps 邮箱的基本元素包括：

- **SecOps 替代策略**：由 **\*-SecOpsOverridePolicy** cmdlet 控制。
- **SecOps 替代规则**：由 **\*-SecOpsOverrideRule** cmdlet 控制。

此行为的结果如下：

- 首先创建策略，然后创建用于标识规则适用的策略的规则。
- 从 PowerShell 中删除策略时，也会删除相应的规则。
- 从 PowerShell 中删除规则时，不会删除相应的策略。 需要手动删除相应的策略。

### <a name="use-powershell-to-configure-secops-mailboxes"></a>使用 PowerShell 配置 SecOps 邮箱

在 PowerShell 中，在高级传递策略中配置 SecOps 邮箱是一个双重过程：

1. 创建 SecOps 替代策略。
2. 创建 SecOps 替代规则，该规则指定规则应用于的策略。

#### <a name="step-1-use-powershell-to-create-the-secops-override-policy"></a>步骤 1：使用 PowerShell 创建 SecOps 替代策略

若要创建 SecOps 替代策略，请使用以下语法：

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>
```

> [!NOTE]
> 无论指定的名称值如何，策略名称都将是 _SecOpsOverridePolicy_，因此不妨使用该值。

此示例创建 SecOps 邮箱策略。

```powershell
New-SecOpsOverridePolicy -Name SecOpsOverridePolicy -SentTo secops@contoso.com
```

有关详细语法和参数信息，请参阅 [New-SecOpsOverridePolicy](/powershell/module/exchange/new-secopsoverridepolicy)。

#### <a name="step-2-use-powershell-to-create-the-secops-override-rule"></a>步骤 2：使用 PowerShell 创建 SecOps 替代规则

此示例使用指定的设置创建 SecOps 邮箱规则。

```powershell
New-SecOpsOverrideRule -Name SecOpsOverrideRule -Policy SecOpsOverridePolicy
```

> [!NOTE]
> 无论指定的名称值如何，规则名称都将是 _SecOpsOverrideRule_\<GUID\> ，其中 \<GUID\> 唯一 GUID 值 (例如 6fed4b63-3563-495d-a481-b24a311f8329) 。

有关详细语法和参数信息，请参阅 [New-SecOpsOverrideRule](/powershell/module/exchange/new-secopsoverriderule)。

### <a name="use-powershell-to-view-the-secops-override-policy"></a>使用 PowerShell 查看 SecOps 替代策略

本示例返回有关一个和唯一的 SecOps 邮箱策略的详细信息。

```powershell
Get-SecOpsOverridePolicy
```

有关详细语法和参数信息，请参阅 [Get-SecOpsOverridePolicy](/powershell/module/exchange/get-secopsoverridepolicy)。

### <a name="use-powershell-to-view-secops-override-rules"></a>使用 PowerShell 查看 SecOps 替代规则

本示例返回有关 SecOps 替代规则的详细信息。

```powershell
Get-SecOpsOverrideRule
```

尽管上一个命令应只返回一个规则，但任何挂起删除的规则也可能包含在结果中。

此示例标识有效规则 (一个) 和任何无效的规则。

```powershell
Get-SecOpsOverrideRule | Format-Table Name,Mode
```

识别无效规则后，可以使用 **Remove-SecOpsOverrideRule** cmdlet 将其删除，如 [本文后面](#use-powershell-to-remove-secops-override-rules)所述。

有关详细语法和参数信息，请参阅 [Get-SecOpsOverrideRule](/powershell/module/exchange/get-secopsoverriderule)。

### <a name="use-powershell-to-modify-the-secops-override-policy"></a>使用 PowerShell 修改 SecOps 替代策略

若要修改 SecOps 替代策略，请使用以下语法：

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy [-AddSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>] [-RemoveSentTo <EmailAddress1>,<EmailAddress2>,...<EmailAddressN>]
```

此示例添加 `secops2@contoso.com` 到 SecOps 替代策略。

```powershell
Set-SecOpsOverridePolicy -Identity SecOpsOverridePolicy -AddSentTo secops2@contoso.com
```

> [!NOTE]
> 如果存在关联的有效 SecOps 替代规则，则也会更新规则中的电子邮件地址。

有关详细语法和参数信息，请参阅 [Set-SecOpsOverridePolicy](/powershell/module/exchange/set-secopsoverridepolicy)。

### <a name="use-powershell-to-modify-a-secops-override-rule"></a>使用 PowerShell 修改 SecOps 替代规则

**Set-SecOpsOverrideRule** cmdlet 不会修改 SecOps 替代规则中的电子邮件地址。 若要修改 SecOps 替代规则中的电子邮件地址，请使用 **Set-SecOpsOverridePolicy** cmdlet。

有关详细语法和参数信息，请参阅 [Set-SecOpsOverrideRule](/powershell/module/exchange/set-secopsoverriderule)。

### <a name="use-powershell-to-remove-the-secops-override-policy"></a>使用 PowerShell 删除 SecOps 替代策略

本示例删除 SecOps 邮箱策略和相应的规则。

```powershell
Remove-SecOpsOverridePolicy -Identity SecOpsOverridePolicy
```

有关详细语法和参数信息，请参阅 [Remove-SecOpsOverridePolicy](/powershell/module/exchange/remove-secopsoverridepolicy)。

### <a name="use-powershell-to-remove-secops-override-rules"></a>使用 PowerShell 删除 SecOps 替代规则

若要删除 SecOps 替代规则，请使用以下语法：

```powershell
Remove-SecOpsOverrideRule -Identity <RuleIdentity>
```

此示例删除指定的 SecOps 替代规则。

```powershell
Remove-SecOpsOverrideRule -Identity SecOpsOverrideRule6fed4b63-3563-495d-a481-b24a311f8329
```

有关详细语法和参数信息，请参阅 [Remove-SecOpsOverrideRule](/powershell/module/exchange/remove-secopsoverriderule)。

## <a name="security--compliance-center-powershell-procedures-for-third-party-phishing-simulations-in-the-advanced-delivery-policy"></a>高级交付策略中针对第三方网络钓鱼模拟的安全&合规中心 PowerShell 过程

在安全&合规中心 PowerShell 中，高级交付策略中第三方网络钓鱼模拟的基本元素包括：

- **网络钓鱼模拟替代策略**：由 **\*-PhishSimOverridePolicy** cmdlet 控制。
- **网络钓鱼模拟替代规则**：由 **\*-PhishSimOverrideRule** cmdlet 控制。
- **允许的 (解除阻止) 网络钓鱼模拟 URL**：由 **\*-TenantAllowBlockListItems** cmdlet 控制。

此行为的结果如下：

- 首先创建策略，然后创建用于标识规则适用的策略的规则。
- 可以单独修改策略和规则中的设置。
- 从 PowerShell 中删除策略时，也会删除相应的规则。
- 从 PowerShell 中删除规则时，不会删除相应的策略。 需要手动删除相应的策略。

### <a name="use-powershell-to-configure-third-party-phishing-simulations"></a>使用 PowerShell 配置第三方网络钓鱼模拟

在 PowerShell 中配置第三方网络钓鱼模拟是一个多步骤过程：

1. 创建网络钓鱼模拟替代策略。
2. 创建网络钓鱼模拟替代规则，该规则指定：
   - 规则适用的策略。
   - 网络钓鱼模拟消息的源 IP 地址。
3. （可选）标识应允许 (的网络钓鱼模拟 URL，而不是阻止或扫描的) 。

#### <a name="step-1-use-powershell-to-create-the-phishing-simulation-override-policy"></a>步骤 1：使用 PowerShell 创建网络钓鱼模拟替代策略

此示例创建网络钓鱼模拟替代策略。

```powershell
New-PhishSimOverridePolicy -Name PhishSimOverridePolicy
```

**注意**：无论指定的名称值如何，策略名称都将是 _PhishSimOverridePolicy_，因此不妨使用该值。

有关详细的语法和参数信息，请参阅 [New-PhishSimOverridePolicy](/powershell/module/exchange/new-phishsimoverridepolicy)。

#### <a name="step-2-use-powershell-to-create-the-phishing-simulation-override-rule"></a>步骤 2：使用 PowerShell 创建网络钓鱼模拟替代规则

使用以下语法:

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -Domains <Domain1>,<Domain2>,...<Domain10> -SenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntry10>
```

无论指定的名称值如何，规则名称都将是 _PhishSimOverrideRule_\<GUID\> ，其中 \<GUID\> 唯一的 GUID 值 (例如 a0eae53e-d755-4a42-9320-b9c6b555c5011) 。

有效的 IP 地址条目是以下值之一：

- 单个 IP：例如 192.168.1.1。
- IP 范围：例如 192.168.0.1-192.168.0.254。
- CIDR IP：例如 192.168.0.1/25。

此示例使用指定的设置创建网络钓鱼模拟替代规则。

```powershell
New-PhishSimOverrideRule -Name PhishSimOverrideRule -Policy PhishSimOverridePolicy -Domains fabrikam.com,wingtiptoys.com -SenderIpRanges 192.168.1.55
```

有关详细语法和参数信息，请参阅 [New-PhishSimOverrideRule](/powershell/module/exchange/new-phishsimoverriderule)。

#### <a name="step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow"></a>步骤 3： (可选) 使用 PowerShell 标识允许的网络钓鱼模拟 URL

使用以下语法:

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries "<URL1>","<URL2>",..."<URL10>" <[-NoExpiration] | [-ExpirationDate <DateTime>]>
```

有关 URL 语法的详细信息，请参阅 [租户允许/阻止列表的 URL 语法](tenant-allow-block-list.md#url-syntax-for-the-tenant-allowblock-list)。

本示例为指定的第三方网络钓鱼模拟 URL 添加 URL 允许条目，但不会过期。

```powershell
New-TenantAllowBlockListItems -Allow -ListType Url -ListSubType AdvancedDelivery -Entries *.fabrikam.com -NoExpiration
```

有关详细语法和参数信息，请参阅 [New-TenantAllowBlockListItems](/powershell/module/exchange/new-tenantallowblocklistitems)。

### <a name="use-powershell-to-view-the-phishing-simulation-override-policy"></a>使用 PowerShell 查看网络钓鱼模拟替代策略

本示例返回有关网络钓鱼模拟替代策略的详细信息。

```powershell
Get-PhishSimOverridePolicy
```

有关详细的语法和参数信息，请参阅 [Get-PhishSimOverridePolicy](/powershell/module/exchange/get-phishsimoverridepolicy)。

### <a name="use-powershell-to-view-phishing-simulation-override-rules"></a>使用 PowerShell 查看网络钓鱼模拟替代规则

本示例返回有关网络钓鱼模拟替代规则的详细信息。

```powershell
Get-PhishSimOverrideRule
```

尽管上一个命令应只返回一个规则，但任何挂起删除的规则也可能包含在结果中。

此示例标识有效规则 (一个) 和任何无效的规则。

```powershell
Get-PhishSimOverrideRule | Format-Table Name,Mode
```

识别无效规则后，可以使用 **Remove-PhishSimOverrideRule** cmdlet 将其删除，如 [本文后面](#use-powershell-to-remove-phishing-simulation-override-rules)所述。

有关详细语法和参数信息，请参阅 [Get-PhishSimOverrideRule](/powershell/module/exchange/get-phishsimoverriderule)。

### <a name="use-powershell-to-view-the-allowed-phishing-simulation-url-entries"></a>使用 PowerShell 查看允许的网络钓鱼模拟 URL 条目

若要查看允许的网络钓鱼模拟 URL，请运行以下命令：

```powershell
Get-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery
```

有关详细语法和参数信息，请参阅 [Get-TenantAllowBlockListItems](/powershell/module/exchange/get-tenantallowblocklistitems)。

### <a name="use-powershell-to-modify-the-phishing-simulation-override-policy"></a>使用 PowerShell 修改网络钓鱼模拟替代策略

若要修改网络钓鱼模拟替代策略，请使用以下语法：

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy [-Comment "<DescriptiveText>"] [-Enabled <$true | $false>]
```

此示例禁用网络钓鱼模拟替代策略。

```powershell
Set-PhishSimOverridePolicy -Identity PhishSimOverridePolicy -Enabled $false
```

有关详细语法和参数信息，请参阅 [Set-PhishSimOverridePolicy](/powershell/module/exchange/set-phishsimoverridepolicy)。

### <a name="use-powershell-to-modify-phishing-simulation-override-rules"></a>使用 PowerShell 修改网络钓鱼模拟替代规则

若要修改网络钓鱼模拟替代规则，请使用以下语法：

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 [-Comment "<DescriptiveText>"] [-AddSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-RemoveSenderDomainIs <DomainEntry1>,<DomainEntry2>,...<DomainEntryN>] [-AddSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>] [-RemoveSenderIpRanges <IPAddressEntry1>,<IPAddressEntry2>,...<IPAddressEntryN>]
```

本示例使用以下设置修改指定的网络钓鱼模拟替代规则：

- 添加域条目 blueyonderairlines.com。
- 删除 IP 地址条目 192.168.1.55。

请注意，这些更改不会影响现有条目。

```powershell
Set-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011 -AddSenderDomainIs blueyonderairlines.com -RemoveSenderIpRanges 192.168.1.55
```

有关详细语法和参数信息，请参阅 [Set-PhishSimOverrideRule](/powershell/module/exchange/set-phishsimoverriderule)。

### <a name="use-powershell-to-modify-the-allowed-phishing-simulation-url-entries"></a>使用 PowerShell 修改允许的网络钓鱼模拟 URL 条目

不能直接修改 URL 值。 可以 [删除现有 URL 条目](#use-powershell-to-remove-the-allowed-phishing-simulation-url-entries) 并 [添加新 URL 条目](#step-3-optional-use-powershell-to-identify-the-phishing-simulation-urls-to-allow) ，如本文所述。

若要修改允许的网络钓鱼模拟 URL 条目的其他属性 (例如过期日期或注释) ，请使用以下语法：

```powershell
Set-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery <[-NoExpiration] | [-ExpirationDate <DateTime>]> [-Notes <String>]
```

标识要修改的条目， (_Entry_ 参数) 或 **Get-TenantAllowBlockListItems** cmdlet 的输出中的标识值 (_Ids_ 参数) 。

本示例修改了指定条目的过期日期。

```powershell
Set-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery -Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

有关详细语法和参数信息，请参阅 [Set-TenantAllowBlockListItems](/powershell/module/exchange/set-tenantallowblocklistitems)。

### <a name="use-powershell-to-remove-a-phishing-simulation-override-policy"></a>使用 PowerShell 删除网络钓鱼模拟替代策略

本示例删除网络钓鱼模拟替代策略和相应的规则。

```powershell
Remove-PhishSimOverridePolicy -Identity PhishSimOverridePolicy
```

有关详细语法和参数信息，请参阅 [Remove-PhishSimOverridePolicy](/powershell/module/exchange/remove-phishsimoverridepolicy)。

### <a name="use-powershell-to-remove-phishing-simulation-override-rules"></a>使用 PowerShell 删除网络钓鱼模拟替代规则

若要删除网络钓鱼模拟替代规则，请使用以下语法：

```powershell
Remove-PhishSimOverrideRule -Identity <RuleIdentity>
```

本示例删除指定的网络钓鱼模拟替代规则。

```powershell
Remove-PhishSimOverrideRule -Identity PhishSimOverrideRulea0eae53e-d755-4a42-9320-b9c6b55c5011
```

有关详细语法和参数信息，请参阅 [Remove-PhishSimOverrideRule](/powershell/module/exchange/remove-phishsimoverriderule)。

### <a name="use-powershell-to-remove-the-allowed-phishing-simulation-url-entries"></a>使用 PowerShell 删除允许的网络钓鱼模拟 URL 条目

若要删除现有的网络钓鱼模拟 URL 条目，请使用以下语法：

```powershell
Remove-TenantAllowBlockListItems <-Entries "<URL1>","<URL2>",..."<URLN>" | -Ids <Identity>> -ListType URL -ListSubType AdvancedDelivery
```

标识要修改的条目， (_Entry_ 参数) 或 **Get-TenantAllowBlockListItems** cmdlet 的输出中的标识值 (_Ids_ 参数) 。

本示例修改了指定条目的过期日期。

```powershell
Remove-TenantAllowBlockListItems -ListType Url -ListSubType AdvancedDelivery -Entries "*.fabrikam.com" -ExpirationDate 9/11/2021
```

有关详细语法和参数信息，请参阅 [Remove-TenantAllowBlockListItems](/powershell/module/exchange/remove-tenantallowblocklistitems)。
