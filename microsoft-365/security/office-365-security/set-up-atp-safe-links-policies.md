---
title: 在 Microsoft Defender for Office 365 中设置安全链接策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for Office 365 中查看、创建、修改和删除安全链接策略和全局安全链接设置。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 29d777a7f351b9ab33232cb0136703ce3fa29842
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290149"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for Office 365 中设置安全链接策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)
- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender for Office 365](office-365-atp.md)的企业客户。 如果你是在 Outlook 中查找有关安全链接的信息，请参阅高级安全Outlook.com [信息](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全链接是 Microsoft [Defender for Office 365](office-365-atp.md) 中的一项功能，它提供对邮件流中入站电子邮件的 URL 扫描，以及电子邮件和其他位置中 URL 和链接的单击验证时间。 有关详细信息，请参阅 [Microsoft Defender for Office 365 中的安全链接](atp-safe-links.md)。

没有内置或默认安全链接策略。 若要获取 URL 的安全链接扫描，需要创建一个或多个安全链接策略，如本文中所述。

> [!NOTE]
> 在安全链接策略之外配置安全链接保护 **的全局** 设置。 有关说明，请参阅 [在 Microsoft Defender for Office 365](configure-global-settings-for-safe-links.md)中为安全链接配置全局设置。

可以在安全与合规中心& PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置安全链接策略;适用于没有 Exchange Online 邮箱，但具有 Microsoft Defender for Office 365 附加订阅的组织的独立 EOP PowerShell) 。

安全链接策略的基本元素包括：

- 安全链接策略：打开安全链接保护、启用实时 URL 扫描、指定是否等待实时扫描完成再传递邮件、打开对内部邮件的扫描、指定是否跟踪用户对 URL 的单击，并指定是否允许用户单击指向原始 URL 的 trough。
- **安全链接规则**：指定策略应用于 (的优先级和收件人) 。

在安全与合规中心内管理安全链接策略时，这两个元素&性：

- 创建安全链接策略时，实际上是同时使用同一名称创建安全链接规则和相关安全链接策略。
- 修改安全链接策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全链接规则。 所有其他设置修改关联的安全链接策略。
- 删除安全链接策略时，安全链接规则和相关的安全链接策略将被删除。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文稍后部分中的"使用 Exchange Online PowerShell 或独立 [EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 配置安全链接策略"部分。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到" **安全链接"** 页，请使用 <https://protection.office.com/safelinksv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您需获得权限，然后才能执行本文中的过程：
  - 若要创建、修改和删除安全链接策略，您需要是安全与合规中心内组织管理或安全管理员角色组的成员和 Exchange Online 中的组织管理角色组的成员。 & 
  - 若要对安全链接策略进行只读访问，你需要是全局读者或安全读者 **角色组的成员**。 

  有关详细信息，请参阅安全 [与合规&中](permissions-in-the-security-and-compliance-center.md) 的权限和 [Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  > 
  > - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  . - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) **中的**"仅查看组织管理"角色组还授予对该功能的只读访问权限。

- 有关安全链接策略的建议设置，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

- 允许应用新策略或更新策略的时间最多为 30 分钟。

- [新功能不断添加到 Microsoft Defender for Office 365。](office-365-atp.md#new-features-in-microsoft-defender-for-office-365) 添加新功能时，可能需要对现有安全链接策略进行调整。

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>使用安全&合规中心创建安全链接策略

在安全与合规中心&安全链接策略的同时，使用相同的名称创建安全链接规则和相关安全链接策略。

1. 在安全&，转到 **"威胁管理** \> **策略** \> **ATP 安全链接"。**

2. 在"**安全链接"** 页上，单击"**创建"。**

3. 将 **打开"新建安全链接策略** "向导。 在 **"为策略命名"** 页上，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

   完成后，单击“下一步”。

4. 在 **出现的** "设置"页上，配置以下设置：

   - **选择邮件中未知潜在恶意 URL** 的操作：选择 **"打开** "，为电子邮件中的链接启用安全链接保护。

   - **选择 Microsoft Teams 中** 未知或潜在恶意 URL 的操作：选择" **打开** "为 Teams 中的链接启用安全链接保护。

   - **对指向文件的** 可疑链接和链接应用实时 URL 扫描：选择此设置可启用电子邮件中链接实时扫描。

   - **等待 URL 扫描完成，然后再** 传递邮件：选择此设置等待实时 URL 扫描完成，然后再传递邮件。

   - **将安全链接** 应用于在组织内部发送的电子邮件：选择此设置将安全链接策略应用于内部发件人和内部收件人之间的邮件。

   - **不跟踪用户单击**：保留此设置为未选择，以启用跟踪用户单击电子邮件中的 URL。

   - **不允许用户单击到原始 URL：** 选择此设置可阻止用户单击警告页中的原始 [URL。](atp-safe-links.md#warning-pages-from-safe-links)

   - **不要重写以下 URL：** 允许访问安全链接将阻止的指定 URL。

     在框中，键入您想要的 URL 或值，然后单击 ![添加按钮图标](../../media/ITPro-EAC-AddIcon.png).

     若要删除现有条目，请选择它，然后单击 ![删除按钮图标](../../media/ITPro-EAC-DeleteIcon.png).

     有关条目语法，请参阅" [不重写以下 URL"列表的条目语法](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。

   有关这些设置的详细信息，请参阅电子邮件 [的安全链接设置](atp-safe-links.md#safe-links-settings-for-email-messages) 和 Microsoft Teams [的安全链接设置](atp-safe-links.md#safe-links-settings-for-microsoft-teams)。

   有关标准和严格策略设置的更多推荐值，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

   完成后，单击“下一步”。

5. 在 **出现的"应用于** "页上，标识策略应用于的内部收件人。

   只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   单击 **"添加条件"。** 在出现的下拉列表中，选择"应用" **下的条件（如果为**：

   - **收件人为**：指定您组织中一个或多个邮箱、邮件用户或邮件联系人。
   - **收件人是：** 指定组织中一个或多个组的成员。
   - **收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。

   选择条件后，将显示相应的下拉列表，其中任意 **一个** 框。

   - 在框中单击并滚动浏览要选择的值列表。
   - 在框中单击并开始键入以筛选列表并选择一个值。
   - 若要添加其他值，请单击框中的空白区域。
   - 若要删除单个条目 **，请单击值** ![ 上的" ](../../media/scc-remove-icon.png) 删除删除"图标。
   - 若要删除整个条件 **，请单击条件** 上的"删除 ![ ](../../media/scc-remove-icon.png) "图标。

   若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件"下的 **其余值**。

   若要添加例外，请单击 **"添加条件** "，然后选择"例外时 **除外"下的例外**。 设置和行为与条件完全相同。

   完成后，单击“下一步”。

6. 在 **出现的"查看设置** "页上，查看设置。 可以单击 **每个设置** 上的"编辑"来修改它。

   完成后，单击"完成 **"。**

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>使用安全&中心查看安全链接策略

1. 在安全&，转到 **"威胁管理** \> **策略** \> **ATP 安全链接"。**

2. 在 **"安全链接** "页上，从列表中选择一个策略， (不要选中"安全链接") 。

   策略详细信息以飞出方式显示

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>使用安全&合规中心修改安全链接策略

1. 在安全&，转到 **"威胁管理** \> **策略** \> **ATP 安全链接"。**

2. 在 **"安全链接** "页上，从列表中选择一个策略， (不要选中"安全链接") 。

3. 在出现的策略详细信息飞出中，单击 **"编辑策略"。**

"飞出"中的可用设置与"使用安全与合规中心&安全 [链接](#use-the-security--compliance-center-to-create-safe-links-policies) 策略"部分中所述的设置相同。

若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。

### <a name="enable-or-disable-safe-links-policies"></a>启用或禁用安全链接策略

1. 在安全&，转到 **"威胁管理** \> **策略** \> **ATP 安全链接"。**

2. 请注意" **状态"列中** 的值：

   - 将切换开关移动到左侧可禁用策略： ![关闭策略](../../media/scc-toggle-off.png).

   - 将切换开关移动到右侧可启用策略： ![打开策略](../../media/scc-toggle-on.png).

### <a name="set-the-priority-of-safe-links-policies"></a>设置安全链接策略的优先级

默认情况下，根据安全链接策略在较新策略中创建策略 (安全链接策略的优先级低于较旧策略) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

安全链接策略按处理策略的顺序显示 (优先级值为 0) 。 

> [!NOTE]
> 在安全&合规中心，只能在创建安全链接策略后更改其优先级。 在 PowerShell 中，可以在创建安全链接规则时替代默认优先级 (这会影响现有规则优先级) 。

若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。

1. 在安全&，转到 **"威胁管理** \> **策略** \> **ATP 安全链接"。**

2. 在 **"安全链接** "页上，从列表中选择一个策略， (不要选中"安全链接") 。

3. 在出现的策略详细信息飞出中，单击可用的优先级按钮：

   - 优先级值为 **0** **的安全链接** 策略只有"降低 **优先级"按钮** 可用。

   - 优先级值最低的安全链接策略 (例如 **，3**) 只有"增加优先级 **"** 按钮可用。

   - 如果你有三个或多个安全链接策略，则最高优先级值和最低优先级值之间的策略同时具有"增加 **优先级** "和" **降低优先级"** 按钮。

4. 单击 **"增加优先级** " **或"降低优先级** "可更改 **"优先级"** 值。

5. 完成后，单击“关闭”。

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>使用安全&合规中心删除安全链接策略

1. 在安全&，转到 **"威胁管理** \> **策略** \> **ATP 安全链接"。**

2. 在 **"安全链接** "页上，从列表中选择一个策略， (不要选中"安全链接") 。

3. 在出现的策略详细信息飞出中，单击"删除策略"，然后在出现的警告对话框中单击"是"。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全链接策略

如前所述，安全链接策略由安全链接策略和安全链接规则组成。

在 PowerShell 中，安全链接策略和安全链接规则的区别显而易见。 您可以使用 **\* -SafeLinksPolicy** cmdlet 管理安全链接策略，然后使用 **\* -SafeLinksRule** cmdlet 管理安全链接规则。

- 在 PowerShell 中，首先创建安全链接策略，然后创建用于标识规则所应用的策略的安全链接规则。
- 在 PowerShell 中，分别修改安全链接策略和安全链接规则中的设置。
- 从 PowerShell 中删除安全链接策略时，不会自动删除相应的安全链接规则，反之亦然。

### <a name="use-powershell-to-create-safe-links-policies"></a>使用 PowerShell 创建安全链接策略

在 PowerShell 中创建安全链接策略是一个包含两个步骤的过程：

1. 创建安全链接策略。
2. 创建安全链接规则，该规则指定应用于该规则的安全链接策略。

> [!NOTE]
> 
> - 你可以创建新的安全链接规则，并为其分配现有的未关联的安全链接策略。 安全链接规则不能与多个安全链接策略关联。
> 
> - 可以在 PowerShell 中的新安全链接策略上配置以下设置，这些策略在创建策略之前&安全与合规中心内不可用：
> 
>   - 在 `$false` **New-SafeLinksRule** cmdlet (上创建禁用的新) 。
>   - 在 _\<Number\>_ **New-SafeLinksRule** cmdlet (设置策略) 优先级) 。
> 
> - 在 PowerShell 中创建的新安全链接策略在安全与合规&中不可见，除非将策略分配给安全链接规则。

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>步骤 1：使用 PowerShell 创建安全链接策略

若要创建安全链接策略，请使用以下语法：

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
> 
> - 有关要用于 _DoNotRewriteUrls_ 参数的条目语法的详细信息，请参阅" [不重写以下 URL"](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)列表的条目语法。
> 
> - 有关在使用 **Set-SafeLinksPolicy** cmdlet 修改现有安全链接策略时可用于 _DoNotRewriteUrls_ 参数的其他语法，请参阅本文稍后的"使用 [PowerShell](#use-powershell-to-modify-safe-links-policies)修改安全链接策略"部分。

此示例创建一个名为 Contoso All 的安全链接策略，并具有以下值：

- 在电子邮件中打开 URL 扫描和重写。
- 在 Teams 中打开 URL 扫描 (点击预览) 。
- 打开单击的 URL（包括指向文件的单击链接）实时扫描。
- 等待 URL 扫描完成，然后再传递邮件。
- 打开内部邮件的 URL 扫描和重写。
- 跟踪与安全链接保护相关的用户单击 (我们未使用 _DoNotTrackUserClicks_ 参数，默认值为 $false，这意味着用户单击将跟踪) 。
- 不允许用户单击到原始 URL。

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

有关语法和参数的详细信息，请参阅 [New-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>步骤 2：使用 PowerShell 创建安全链接规则

若要创建安全链接规则，请使用以下语法：

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

本示例创建一个名为 Contoso All 的安全链接规则，并满足以下条件：

- 该规则与名为 Contoso All 的安全链接策略相关联。
- 该规则适用于域域中contoso.com收件人。
- 因为我们没有使用 _Priority_ 参数，所以使用默认优先级。
- 如果规则 (Enabled 参数，则启用该规则，默认值为 `$true`) 。

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

有关语法和参数的详细信息，请参阅[New-SafeLinksRule。](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)

### <a name="use-powershell-to-view-safe-links-policies"></a>使用 PowerShell 查看安全链接策略

若要查看现有安全链接策略，请使用以下语法：

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

此示例返回所有安全链接策略的摘要列表。

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

此示例返回名为 Contoso Executives 的安全链接策略的详细信息。

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅 [Get-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)。

### <a name="use-powershell-to-view-safe-links-rules"></a>使用 PowerShell 查看安全链接规则

若要查看现有安全链接规则，请使用以下语法：

```PowerShell
Get-SafeLinksRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本示例返回所有安全链接规则的摘要列表。

```PowerShell
Get-SafeLinksRule | Format-Table Name,State
```

若要按已启用或已禁用规则筛选列表，请运行以下命令：

```PowerShell
Get-SafeLinksRule -State Disabled
```

```PowerShell
Get-SafeLinksRule -State Enabled
```

此示例返回名为 Contoso Executives 的安全链接规则的详细信息。

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅[Get-SafeLinksRule。](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)

### <a name="use-powershell-to-modify-safe-links-policies"></a>使用 PowerShell 修改安全链接策略

如果 **Set-SafeLinksPolicy** cmdlet 没有 Name 参数，则 (PowerShell 中重命名安全链接) 。 在安全与合规中心&安全链接策略时，你仅重命名安全链接 _规则_。

在 PowerShell 中修改安全链接策略的唯一额外注意事项是 _DoNotRewriteUrls_ 参数的可用语法 ("不重写以下 [URL"](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 列表) ：

- 若要添加将替换任何现有条目的值，请使用以下 `"Entry1","Entry2,..."EntryN"` 语法：
- 若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

否则，当您创建安全链接策略时，可以使用如本文前面步骤 1 中所述的相同设置：使用 [PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) 创建安全链接策略部分。

若要修改安全链接策略，请使用以下语法：

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)。

### <a name="use-powershell-to-modify-safe-links-rules"></a>使用 PowerShell 修改安全链接规则

在 PowerShell 中修改安全链接规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有安全链接规则，请参阅下一节。

否则，当您创建规则时，如本文前面步骤 2 中所述，使用 [PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) 创建安全链接规则部分时，可以使用相同的设置。

若要修改安全链接规则，请使用以下语法：

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅[Set-SafeLinksRule。](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>使用 PowerShell 启用或禁用安全链接规则

在 PowerShell 中启用或禁用安全链接规则可启用或禁用整个安全链接策略 (安全链接规则以及分配的安全链接策略) 。

若要在 PowerShell 中启用或禁用安全链接规则，请使用以下语法：

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

本示例禁用名为"Marketing Department"的安全链接规则。

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule)和[Disable-SafeLinksRule。](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>使用 PowerShell 设置安全链接规则的优先级

可以设置的规则最高优先级值是 0。 可以设置的最小优先级值取决于规则的数量。 例如，如果有五个规则，则可以使用的优先级值为 0 到 4。 更改现有规则的优先级可对其他规则产生级联效应。 例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。

若要在 PowerShell 中设置安全链接规则的优先级，请使用以下语法：

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

下面的示例将名为“Marketing Department”的规则的优先级设置为 2。 优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> 若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-SafeLinksRule** cmdlet 上的 _Priority_ 参数。

有关语法和参数的详细信息，请参阅[Set-SafeLinksRule。](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)

### <a name="use-powershell-to-remove-safe-links-policies"></a>使用 PowerShell 删除安全链接策略

使用 PowerShell 删除安全链接策略时，不会删除相应的安全链接规则。

若要在 PowerShell 中删除安全链接策略，请使用以下语法：

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

此示例删除名为"Marketing Department"的安全链接策略。

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)。

### <a name="use-powershell-to-remove-safe-links-rules"></a>使用 PowerShell 删除安全链接规则

使用 PowerShell 删除安全链接规则时，不会删除相应的安全链接策略。

若要在 PowerShell 中删除安全链接规则，请使用以下语法：

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

此示例删除名为"Marketing Department"的安全链接规则。

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)。

若要验证安全链接是否正在扫描邮件，请检查可用的 Microsoft Defender for Office 365 报告。 有关详细信息，请参阅查看 [适用于 Office 365 的 Defender](view-reports-for-atp.md) 报告，以及使用安全与合规中心& [资源管理器](threat-explorer.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功创建、修改或删除安全链接策略，请执行下列任一步骤：

- 在安全&，转到 **"威胁管理** \> **策略** \> **ATP 安全链接"。** 验证策略列表、其 **状态** 值及其 **优先级** 值。 若要查看更多详细信息，请从列表中选择策略，并查看飞出中的详细信息。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，替换为策略或规则的名称，运行以下命令并 \<Name\> 验证设置：

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
