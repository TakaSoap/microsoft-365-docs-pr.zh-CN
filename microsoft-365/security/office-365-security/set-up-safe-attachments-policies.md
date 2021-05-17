---
title: 在 Microsoft Defender 保险箱设置附件策略Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 了解如何定义附件保险箱保护你的组织免受电子邮件中的恶意文件的攻击。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: e96babff19ea981b953d35929813b1e08c000e32
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203831"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender 保险箱设置附件策略Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md)的企业客户。 如果你是一位家庭用户，正在查找有关电子邮件中的附件扫描Outlook，请参阅[Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

保险箱附件是 Microsoft [Defender for Office 365](whats-new-in-defender-for-office-365.md)中的一项功能，该功能使用虚拟环境在[Exchange Online Protection (EOP) ](anti-malware-protection.md)中经过反恶意软件保护扫描之后，在发送给收件人之前，使用虚拟环境检查入站电子邮件中的附件。 有关详细信息，请参阅 microsoft Defender 保险箱[中的附件Office 365。](safe-attachments.md)

附件策略没有内置或默认保险箱。 若要保险箱电子邮件附件的附件扫描，您需要创建一个或多个保险箱附件策略，如本文所述。

您可以在安全保险箱 &合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置附件Exchange Online;独立 EOP PowerShell，适用于Exchange Online邮箱，但使用 Defender for Office 365 加载项订阅的组织) 。

"附件"策略保险箱元素包括：

- 安全附件策略：指定未知恶意软件检测的操作、是否将带恶意软件附件的邮件发送到指定的电子邮件地址，以及是否传递保险箱附件扫描无法完成时传递邮件。
- **安全附件规则**：指定策略应用于 (的优先级和收件人) 。

在安全与合规中心内管理"附件保险箱策略时，这两个元素&不明显：

- 创建附件保险箱策略时，实际上是同时使用同一名称创建安全附件规则和相关的安全附件策略。
- 修改附件保险箱时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全附件规则。 所有其他设置修改关联的安全附件策略。
- 删除附件保险箱时，安全附件规则和相关的安全附件策略将被删除。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文稍后的使用 Exchange Online PowerShell 或独立[EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)配置 保险箱 附件策略一节。

> [!NOTE]
> 在"附件"设置的全局保险箱区域中，配置不依赖于"附件"保险箱的功能。 有关[说明，请参阅](turn-on-mdo-for-spo-odb-and-teams.md)在保险箱中打开SharePoint、OneDrive Microsoft Teams和保险箱[文档Microsoft 365 E5。](safe-docs.md)

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到"附件 **保险箱，** 请使用 <https://protection.office.com/safeattachmentv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您需获得权限，然后才能执行本文中的过程：
  - 若要创建、修改和删除 保险箱 附件策略，您需要是安全 & 合规中心内组织管理或安全管理员角色组的成员以及 Exchange Online 中的组织管理角色组的成员。  
  - 若要对附件策略保险箱只读访问权限，你需要是安全与合规中心内全局读者或安全读者角色&的成员。 

  有关详细信息，请参阅安全与[合规&中的权限](permissions-in-the-security-and-compliance-center.md)和[Exchange Online。](/exchange/permissions-exo/permissions-exo)

  **注意**：

  - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关我们针对附件策略保险箱设置，请参阅保险箱[附件设置。](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

- 最多允许应用新策略或更新策略 30 分钟。

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>使用安全&中心创建附件保险箱策略

在安全保险箱合规中心创建自定义附件策略&使用相同的名称同时创建安全附件规则和相关的安全附件策略。

1. 在安全与&中心，转到"**威胁管理** \> **策略** \> **ATP 保险箱附件"。**

2. 在 **"保险箱"页上**，单击"创建 **"。**

3. "**新建保险箱附件"策略** 向导将打开。 在" **命名策略"** 页上，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

   完成后，单击“下一步”。

4. 在 **设置** 页上，配置以下设置：

   - **保险箱附件未知恶意软件响应**：选择下列值之一：

     - **关闭**：通常，不建议使用此值。
     - **监视器**
     - **Block**：这是默认值，以及 Standard 和 Strict 预设安全策略 [中的建议值](preset-security-policies.md)。
     - **Replace**
     - **动态传递 (预览功能)**

     这些值在附件策略[保险箱中进行了介绍](safe-attachments.md#safe-attachments-policy-settings)。

   - 将附件发送到以下电子邮件地址：对于操作值 **Block** **、Monitor** 或 **Replace**，可以选择"启用重定向"，将包含恶意软件附件的邮件发送到指定的内部或外部电子邮件地址，以便进行分析和调查。

     对于"标准"和"严格"策略设置，建议启用重定向。 有关详细信息，请参阅附件[保险箱设置](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

   - 如果附件的 **恶意软件** 扫描次数或出现错误，则应用上述选择：即使 **保险箱** 附件扫描无法完成，保险箱 附件未知恶意软件响应也对邮件执行指定的操作。 如果选择此选项，请始终选择"已启用 **重定向"。** 否则，邮件可能会丢失。

   完成后，单击“下一步”。

5. 在 **出现的"应用于** "页上，标识策略应用于的内部收件人。

   只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   单击 **"添加条件"。** In the dropdown that appears， select a condition under **Applied if**：

   - **收件人为**：指定您的组织中的一个或多个邮箱、邮件用户或邮件联系人。
   - **收件人是 ：指定** 组织中一个或多个组的成员。
   - **收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。

   选择条件后，将显示相应的下拉列表，其中显示其中 **任何** 一个框。

   - 在框中单击并滚动要选择的值列表。
   - 在框中单击并开始键入以筛选列表并选择一个值。
   - 若要添加其他值，请单击框中的空白区域。
   - 若要删除单个条目，请单击值 **上的"** ![ 删除 ](../../media/scc-remove-icon.png) ""删除"图标。
   - 若要删除整个条件，请单击条件 ![ 上的"删除 ](../../media/scc-remove-icon.png) ""删除"图标。

   若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件 **"下的其余值**。

   若要添加例外，请单击" **添加条件"，** 然后选择"例外条件 **"下的例外**。 设置和行为与条件完全相同。

   完成后，单击“下一步”。

6. 在出现的 **"查看设置** "页上，查看设置。 可以单击每个 **设置** 上的"编辑"来修改它。

   完成后，单击"完成 **"。**

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>使用安全&中心查看附件保险箱策略

1. 在安全与&中心，转到"**威胁管理** \> **策略** \> **ATP 保险箱附件"。**

2. On the **保险箱 Attachments** page， select a policy from the list and click on it (don't select the check box) .

   策略详细信息以飞出方式显示

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>使用安全&合规中心修改保险箱附件策略

1. 在安全与&中心，转到"**威胁管理** \> **策略** \> **ATP 保险箱附件"。**

2. On the **保险箱 Attachments** page， select a policy from the list and click on it (don't select the check box) .

3. 在出现的策略详细信息飞出中，单击"编辑 **策略"。**

在飞出中显示可用的设置与使用安全与合规中心创建附件&[部分中保险箱的设置相同](#use-the-security--compliance-center-to-create-safe-attachments-policies)。

若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。

### <a name="enable-or-disable-safe-attachments-policies"></a>启用或禁用保险箱附件策略

1. 在安全与&中心，转到"**威胁管理** \> **策略** \> **ATP 保险箱附件"。**

2. 请注意"状态" **列中** 的值：

   - 将切换开关向左移动 ![关闭策略](../../media/scc-toggle-off.png) 禁用策略。

   - 将切换开关向右移动 ![打开策略](../../media/scc-toggle-on.png) 启用策略。

### <a name="set-the-priority-of-safe-attachments-policies"></a>设置"附件保险箱的优先级

默认情况下，保险箱附件策略的优先级基于它们在 (中的创建顺序，因此其优先级低于较旧策略) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

保险箱附件策略按其处理顺序显示 (优先级值为 0 的附件) 。 

**注意**：在安全&合规中心内，只能在创建附件策略保险箱更改策略的优先级。 在 PowerShell 中，您可以在创建可影响现有规则优先级的安全附件规则 (默认优先级。) 。

若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。

1. 在安全与&中心，转到"**威胁管理** \> **策略** \> **ATP 保险箱附件"。**

2. On the **保险箱 Attachments** page， select a policy from the list and click on it (don't select the check box) .

3. 在出现的策略详细信息飞出中，单击可用的优先级按钮。

   - 优先级保险箱 **0** 的"附件"策略仅提供"**减少优先级"** 按钮。

   - "保险箱优先级"值最低的"附件"策略 (例如 **，3**) "增加 **优先级"按钮** 可用。

   - 如果您有三个或多个"附件"保险箱，则优先级最高的值和最低优先级值之间的策略将同时具有"增加优先级"和"**减少优先级"** 按钮。

4. 单击 **"增加优先级** " **或"减少优先级** "可更改 **"优先级"** 值。

5. 完成后，单击“关闭”。

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>使用安全&合规中心删除保险箱附件策略

1. 在安全与&中心，转到"**威胁管理** \> **策略** \> **ATP 保险箱附件"。**

2. On the **保险箱 Attachments** page， select a policy from the list and click on it (don't select the check box) .

3. 在随即出现的策略详细信息飞出中，单击"删除 **策略**"，然后在出现的警告对话框中单击"是"。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置保险箱附件策略

如前所述，附件保险箱由安全附件策略和安全附件规则组成。

在 PowerShell 中，安全附件策略和安全附件规则的区别显而易见。 您可以使用 **\* -SafeAttachmentPolicy** cmdlet 管理安全附件策略，然后使用 **\* -SafeAttachmentRule** cmdlet 管理安全附件规则。

- 在 PowerShell 中，首先创建安全附件策略，然后创建用于标识该规则所适用的策略的安全附件规则。
- 在 PowerShell 中，分别修改安全附件策略和安全附件规则中的设置。
- 从 PowerShell 删除安全附件策略时，不会自动删除相应的安全附件规则，反之亦然。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>使用 PowerShell 创建保险箱附件策略

在 PowerShell 保险箱附件策略的过程包含两个步骤：

1. 创建安全附件策略。
2. 创建安全附件规则，该规则指定应用该规则的安全附件策略。

 **注意**：

- 可以创建新的安全附件规则，并为其分配现有的未关联的安全附件策略。 安全附件规则不能与多个安全附件策略关联。

- 可以在 PowerShell 中的新安全附件策略上配置以下设置，这些设置在安全与合规&中心不可用，除非创建策略：
  - 在 `$false` **New-SafeAttachmentRule** cmdlet (上创建禁用的新策略) 。
  - 在 _\<Number\>_ **New-SafeAttachmentRule** cmdlet (设置策略) 优先级) 。

- 在 PowerShell 中新建的安全附件策略在安全与合规中心&，除非将策略分配给安全附件规则。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>步骤 1：使用 PowerShell 创建安全附件策略

若要创建安全附件策略，请使用以下语法：

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

此示例创建一个名为 Contoso All 的安全附件策略，并具有以下值：

- 在未使用 _Action_ 参数保险箱文档扫描 (阻止发现包含恶意软件的邮件，默认值为 `Block`) 。
- 启用重定向，发现包含恶意软件的邮件将发送到 sec-ops@contoso.com 进行分析和调查。
- 如果保险箱附件扫描不可用或遇到错误，请不要传递邮件 (我们未使用 _ActionOnError_ 参数，默认值为 `$true`) 。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

有关语法和参数的详细信息，请参阅 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>步骤 2：使用 PowerShell 创建安全附件规则

若要创建安全附件规则，请使用以下语法：

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

本示例创建名为"Contoso All"的安全附件规则，并满足以下条件：

- 该规则与名为 Contoso All 的安全附件策略相关联。
- 该规则适用于域中的所有 contoso.com 收件人。
- 因为我们没有使用 _Priority_ 参数，所以使用默认优先级。
- 如果规则 (_Enabled_ 参数，则启用该规则，默认值为 `$true`) 。

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

有关语法和参数的详细信息，请参阅 [New-SafeAttachmentRule](/powershell/module/exchange/new-safeattachmentrule)。

### <a name="use-powershell-to-view-safe-attachment-policies"></a>使用 PowerShell 查看安全附件策略

若要查看现有安全附件策略，请使用以下语法：

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本示例返回所有安全附件策略的摘要列表。

```PowerShell
Get-SafeAttachmentPolicy
```

本示例返回名为 Contoso Executives 的安全附件策略的详细信息。

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

有关语法和参数的详细信息，请参阅 [Get-SafeAttachmentPolicy](/powershell/module/exchange/get-safeattachmentpolicy)。

### <a name="use-powershell-to-view-safe-attachment-rules"></a>使用 PowerShell 查看安全附件规则

若要查看现有安全附件规则，请使用以下语法：

```PowerShell
Get-SafeAttachmentRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本示例返回所有安全附件规则的摘要列表。

```PowerShell
Get-SafeAttachmentRule
```

若要按已启用或已禁用规则筛选列表，请运行以下命令：

```PowerShell
Get-SafeAttachmentRule -State Disabled
```

```PowerShell
Get-SafeAttachmentRule -State Enabled
```

本示例返回名为 Contoso Executives 的安全附件规则的详细信息。

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

有关语法和参数的详细信息，请参阅 [Get-SafeAttachmentRule](/powershell/module/exchange/get-safeattachmentrule)。

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>使用 PowerShell 修改安全附件策略

如果 **Set-SafeAttachmentPolicy** cmdlet 没有 _Name_ 参数，则 (PowerShell 中的安全附件策略) 。 在安全保险箱中心重命名"附件"&，只需重命名安全附件 _规则_。

否则，创建安全附件策略时可用的设置相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) 创建安全附件策略部分所述。

若要修改安全附件策略，请使用以下语法：

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy)。

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>使用 PowerShell 修改安全附件规则

在 PowerShell 中修改安全附件规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有安全附件规则，请参阅下一节。

否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-a-safe-attachment-rule) 创建安全附件规则部分中所述的设置相同。

若要修改安全附件规则，请使用以下语法：

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>使用 PowerShell 启用或禁用安全附件规则

在 PowerShell 中启用或禁用安全附件规则可启用或禁用整个 保险箱 附件策略 (安全附件规则以及分配的安全附件策略) 。

若要在 PowerShell 中启用或禁用安全附件规则，请使用以下语法：

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

本示例禁用名为"Marketing Department"的安全附件规则。

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[Enable-SafeAttachmentRule](/powershell/module/exchange/enable-safeattachmentrule)和[Disable-SafeAttachmentRule。](/powershell/module/exchange/disable-safeattachmentrule)

### <a name="use-powershell-to-set-the-priority-of-safe-attachment-rules"></a>使用 PowerShell 设置安全附件规则的优先级

可以设置的规则最高优先级值是 0。 可以设置的最小优先级值取决于规则的数量。 例如，如果有五个规则，则可以使用的优先级值为 0 到 4。 更改现有规则的优先级可对其他规则产生级联效应。 例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。

若要在 PowerShell 中设置安全附件规则的优先级，请使用以下语法：

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

下面的示例将名为“Marketing Department”的规则的优先级设置为 2。 优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。

```PowerShell
Set-SafeAttachmentRule -Identity "Marketing Department" -Priority 2
```

**注意**：若要在创建新规则的优先级时设置它，请改为对 **New-SafeAttachmentRule** cmdlet 使用 _Priority_ 参数。

有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentRule](/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>使用 PowerShell 删除安全附件策略

使用 PowerShell 删除安全附件策略时，不会删除相应的安全附件规则。

若要在 PowerShell 中删除安全附件策略，请使用以下语法：

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

本示例删除名为 Marketing Department 的安全附件策略。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-SafeAttachmentPolicy](/powershell/module/exchange/remove-safeattachmentpolicy)。

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>使用 PowerShell 删除安全附件规则

使用 PowerShell 删除安全附件规则时，不会删除相应的安全附件策略。

若要在 PowerShell 中删除安全附件规则，请使用以下语法：

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

本示例删除名为 Marketing Department 的安全附件规则。

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功创建、修改或删除附件保险箱，请执行下列任一步骤：

- 在安全与&中心，转到"**威胁管理** \> **策略** \> **ATP 保险箱附件"。** 验证策略列表、 **策略的 Status** 值及其 **Priority** 值。 若要查看更多详细信息，请从列表中选择策略，然后查看飞出中的详细信息。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将 替换为策略或规则的名称，运行以下命令并 \<Name\> 验证设置：

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

若要验证附件保险箱扫描邮件，请检查可用的 Defender，查看Office 365报告。 有关详细信息，请参阅查看[Defender for Office 365](view-reports-for-mdo.md)报告和在安全与合规&[使用资源管理器](threat-explorer.md)。
