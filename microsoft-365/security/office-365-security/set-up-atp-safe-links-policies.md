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
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for Office 365 中查看、创建、修改和删除安全链接策略和全局安全链接设置。
ms.openlocfilehash: ed95c72c98e0c9d59b9860e89843c5f9b4970c8e
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48846432"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for Office 365 中设置安全链接策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender For Office 365](office-365-atp.md)的商业客户。 如果您是在 Outlook 中查找有关 Safelinks 的信息的家庭用户，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全链接是 [Microsoft Defender For Office 365](office-365-atp.md) 中的一项功能，用于在邮件流中提供入站电子邮件的 URL 扫描，以及单击电子邮件中的 url 和链接以及在其他位置中进行验证的时间。 有关详细信息，请参阅 [Microsoft Defender For Office 365 中的安全链接](atp-safe-links.md)。

没有内置的或默认的安全链接策略。 若要获取对 Url 的安全链接扫描，您需要创建一个或多个安全链接策略，如本文中所述。

您可以使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中配置安全链接策略，以获取符合 Exchange Online 中邮箱的符合条件的 Microsoft 365 组织;独立 EOP PowerShell for 不含 Exchange Online 邮箱的组织，但使用 Microsoft Defender for Office 365 附加订阅) 。

安全链接策略的基本元素为：

- **安全链接策略** ：启用 "安全链接保护"、"打开实时 URL 扫描"、"在传递邮件前是否等待实时扫描完成"、"为内部邮件启用扫描"、"指定是否跟踪用户单击" url，并指定是否允许用户单击 "trough" 以获取原始 URL。
- **安全链接规则** ：指定策略应用于) 的优先级和收件人筛选器 (。

当您在安全 & 合规中心中管理安全链接策略时，这两个元素之间的差异并不明显：

- 创建安全链接策略时，实际上是创建安全链接规则，同时为两者使用相同的名称创建关联的安全链接策略。
- 修改安全链接策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全链接规则。 所有其他设置修改关联的安全链接策略。
- 删除安全链接策略时，将删除安全链接规则和关联的安全链接策略。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文后面的 [使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全链接策略](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies) 一节。

> [!NOTE]
> 您可以在安全链接策略 **之外** 为安全链接保护配置全局设置。 有关说明，请参阅 [在 Microsoft Defender For Office 365 中配置安全链接的全局设置](configure-global-settings-for-safe-links.md)。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 " **安全链接** " 页面，请使用 <https://protection.office.com/safelinksv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 若要查看、创建、修改和删除安全链接策略，您必须是下列角色组之一的成员：

  - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“ **组织管理** ”或“ **安全管理员** ”。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 **组织管理** 。

- 有关安全链接策略的推荐设置，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

- 允许使用最长30分钟的时间来应用新的或更新的策略。

- [新功能将不断添加到 Microsoft Defender For Office 365](office-365-atp.md#new-features-in-microsoft-defender-for-office-365)中。 添加新功能时，您可能需要对现有安全链接策略进行调整。

## <a name="use-the-security--compliance-center-to-create-safe-links-policies"></a>使用安全 & 合规中心创建安全链接策略

在安全 & 合规中心中创建自定义安全链接策略将同时为两者创建安全链接规则和关联的安全链接策略，同时使用相同的名称。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "。

2. 在 " **安全链接** " 页上，单击 " **创建** "。

3. 将打开 " **新建安全链接策略** " 向导。 在 " **命名策略** " 页上，配置以下设置：

   - **名称** ：输入策略的唯一描述性名称。

   - **说明** ：输入策略的可选说明。

   完成后，单击“下一步”。

4. 在出现的 " **设置** " 页上，配置以下设置：

   - **选择邮件中未知的潜在恶意 url 的操作** ：选择 **"启用"** 以启用电子邮件中的链接的安全链接保护。

   - **为 Microsoft 团队中的未知或可能存在的恶意 Url 选择操作** ：选择 **"打开"** 以启用对团队中的链接的安全链接保护。

   - **对指向文件的可疑链接和链接应用实时 URL 扫描** ：选择此设置可启用对电子邮件中的链接的实时扫描。

   - **等待 URL 扫描完成后再传递邮件** ：选择此设置可等待实时 URL 扫描完成，然后再传递邮件。

   - **对在组织内发送的电子邮件应用安全链接** ：选择此设置可将安全链接策略应用于内部发件人和内部收件人之间的邮件。

   - 不 **跟踪用户单击** ：将此设置保留为未选中状态，以启用跟踪用户单击电子邮件中的 url。

   - **不允许用户单击到原始 url** ：选择此设置可阻止用户通过单击 [警告页面](atp-safe-links.md#warning-pages-from-safe-links)中的原始 url。

   - **请勿重写以下 url** ：允许访问安全链接将阻止的指定 url。

     在框中，键入所需的 URL 或值，然后单击 !["添加按钮" 图标](../../media/ITPro-EAC-AddIcon.png).

     若要删除现有条目，请选择该条目，然后单击 !["删除" 按钮图标](../../media/ITPro-EAC-DeleteIcon.png).

     有关条目语法，请参阅 ["不重写以下 url" 列表中的 "输入语法](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)"。

   有关这些设置的详细信息，请参阅 Microsoft 团队的 " [电子邮件安全链接设置](atp-safe-links.md#safe-links-settings-for-email-messages) " 和 " [安全链接设置](atp-safe-links.md#safe-links-settings-for-microsoft-teams)"。

   有关标准策略设置和严格策略设置的建议值，请参阅 [安全链接策略设置](recommended-settings-for-eop-and-office365-atp.md#safe-links-policy-settings)。

   完成后，单击“下一步”。

5. 在显示的 " **应用于** " 页上，确定该策略应用于的内部收件人。

   只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如， _\<recipient1\>_ 或 _\<recipient2\>_ ）。 不同的条件或例外使用“和”逻辑（例如， _\<recipient1\>_ 和 _\<member of group 1\>_ ）。

   单击 " **添加条件** "。 在出现的下拉列表中，选择 " **应用** 条件：

   - **收件人为** ：指定组织中的一个或多个邮箱、邮件用户或邮件联系人。
   - **收件人是的成员** ：指定组织中的一个或多个组。
   - **收件人域是** ：指定你的组织中配置的一个或多个接受的域中的收件人。

   选择条件后，将显示相应的下拉框，其中包含 **其中的任何** 框。

   - 在框中单击并滚动到要选择的值列表。
   - 在框中单击，然后开始键入以筛选列表并选择一个值。
   - 若要添加其他值，请单击框中的空白区域。
   - 若要删除单个条目， **Remove** 请单击 ![ ](../../media/scc-remove-icon.png) 值上的 "删除删除" 图标。
   - 若要删除整个条件，请 **Remove** 单击 ![ ](../../media/scc-remove-icon.png) 条件上的 "删除删除" 图标。

   若要添加其他条件，请单击 " **添加条件** "，然后选择 " **应用于** " 下的其他值。

   若要添加例外，请单击 " **添加条件** "，并在 " **除非** " 下选择例外。 设置和行为与条件完全相同。

   完成后，单击“下一步”。

6. 在显示的 " **查看您的设置** " 页上，查看您的设置。 您可以在每个设置上单击 " **编辑** " 以修改它。

   完成后，单击 " **完成** "。

## <a name="use-the-security--compliance-center-to-view-safe-links-policies"></a>使用安全 & 合规中心查看安全链接策略

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "。

2. 在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。

   弹出时显示策略详细信息

## <a name="use-the-security--compliance-center-to-modify-safe-links-policies"></a>使用安全 & 合规中心修改安全链接策略

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "。

2. 在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。

3. 在 "策略详细信息" 弹出显示，单击 " **编辑策略** "。

弹出的可用设置与 [使用 Security & 合规中心创建安全链接策略](#use-the-security--compliance-center-to-create-safe-links-policies) 一节中所述的相同。

若要启用或禁用策略或设置策略优先级顺序，请参阅以下各节。

### <a name="enable-or-disable-safe-links-policies"></a>启用或禁用安全链接策略

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "。

2. 请注意 " **状态** " 列中的值：

   - 将切换开关移动到左侧可禁用策略： ![关闭策略](../../media/scc-toggle-off.png).

   - 将切换开关移动到右侧可启用策略： ![启用策略](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png).

### <a name="set-the-priority-of-safe-links-policies"></a>设置安全链接策略的优先级

默认情况下，安全链接策略的优先级将根据其在 (较旧策略) 的创建顺序而得到的优先级。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

安全链接策略按其处理的顺序显示 (第一个策略的 **优先级** 值为 0) 。

**注意** ：在安全 & 合规性中心中，您只能在创建安全链接策略之后更改其优先级。 在 PowerShell 中，您可以在创建安全链接规则时替代默认优先级， (这会影响现有规则) 的优先级。

若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "。

2. 在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。

3. 在 "策略详细信息" 弹出显示时，单击 "可用优先级" 按钮：

   - **优先级** 值为 **0** 的安全链接策略仅有 " **降低优先级** " 按钮可用。

   - 具有最低 **优先级** 值的安全链接策略 (例如， **3** ) 仅有 " **提高优先级** " 按钮可用。

   - 如果您具有三个或更多安全链接策略，则在最高和最低优先级值之间的策略将具有 " **增加优先级** " 和 " **降低优先级** " 按钮可用。

4. 单击 " **提高优先级** " 或 " **降低优先级** " 以更改 **优先级** 值。

5. 完成后，单击“关闭”。

## <a name="use-the-security--compliance-center-to-remove-safe-links-policies"></a>使用安全 & 合规性中心删除安全链接策略

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "。

2. 在 " **安全链接** " 页上，从列表中选择一个策略，然后单击该策略 (不选中复选框) "。

3. 在 "策略详细信息" 弹出显示的内容中，单击 " **删除策略** "，然后在出现的警告对话框中单击 **"是"** 。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全链接策略

如前面所述，安全链接策略由安全链接策略和安全链接规则组成。

在 PowerShell 中，安全链接策略和安全链接规则的区别显而易见。 您可以使用 **\* -SafeLinksPolicy** cmdlet 管理安全链接策略，并使用 **\* -SafeLinksRule** cmdlet 管理安全链接规则。

- 在 PowerShell 中，首先创建安全链接策略，然后创建安全链接规则，以标识应用该规则的策略。
- 在 PowerShell 中，可以单独修改 "安全链接策略" 和 "安全链接" 规则中的设置。
- 从 PowerShell 中删除安全链接策略时，不会自动删除相应的安全链接规则，反之亦然。

### <a name="use-powershell-to-create-safe-links-policies"></a>使用 PowerShell 创建安全链接策略

在 PowerShell 中创建安全链接策略的过程分为两个步骤：

1. 创建安全链接策略。
2. 创建安全链接规则，该规则指定应用该规则的安全链接策略。

 **注意** ：

- 您可以创建新的安全链接规则，并向其分配现有的未关联的安全链接策略。 安全链接规则不能与多个安全链接策略相关联。

- 您可以在 PowerShell 中的新 "安全链接策略" 中配置以下设置，这些设置在 "安全 & 合规性中心" 中不可用，直到您创建了策略：

  - 将新策略创建为 _Enabled_ `$false` **SafeLinksRule** cmdlet) 上启用的禁用 (。
  - 在 _Priority_ _\<Number\>_ **SafeLinksRule** Cmdlet) 上创建 (优先级) 时设置策略的优先级。

- 在 PowerShell 中创建的新安全链接策略在安全 & 合规性中心中不可见，除非您将策略分配给安全链接规则。

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>步骤1：使用 PowerShell 创建安全链接策略

若要创建安全链接策略，请使用以下语法：

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

**注意** ：

- 有关用于 _DoNotRewriteUrls_ 参数的条目语法的详细信息，请参阅 ["不重写以下 url" 列表中的 "输入语法](atp-safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)"。

- 有关使用 **SafeLinksPolicy** cmdlet 修改现有安全链接策略时可用于 _DoNotRewriteUrls_ 参数的其他语法，请参阅本文后面的 [使用 PowerShell 修改安全链接策略](#use-powershell-to-modify-safe-links-policies)一节。

本示例创建一个名为 "Contoso All" 的安全链接策略，其中包含以下值：

- 启用电子邮件中的 URL 扫描和重写。
- 打开 "团队中的 URL 扫描" (点击 "仅预览") 。
- 启用单击的 Url 的实时扫描，包括指向文件的单击链接。
- 等待 URL 扫描完成后再传递邮件。
- 启用内部邮件的 URL 扫描和重写。
- 跟踪与安全链接保护相关的用户单击 (我们不使用 _DoNotTrackUserClicks_ 参数，默认值为 $false，这意味着将) 跟踪用户单击。
- 不允许用户单击到原始 URL。

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safelinkspolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>步骤2：使用 PowerShell 创建安全链接规则

若要创建安全链接规则，请使用以下语法：

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

本示例将创建一个名为 "Contoso All" 的安全链接规则，并满足以下条件：

- 规则与名为 "Contoso All" 的安全链接策略相关联。
- 该规则应用于 contoso.com 域中的所有收件人。
- 由于我们不使用 _Priority_ 参数，因此使用默认的优先级。
-  (我们不使用 _enabled_ 参数，并且默认值为) ，则启用该规则 `$true` 。

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/new-safelinksrule)。

### <a name="use-powershell-to-view-safe-links-policies"></a>使用 PowerShell 查看安全链接策略

若要查看现有的安全链接策略，请使用以下语法：

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本示例返回所有安全链接策略的摘要列表。

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

本示例返回名为 "Contoso 行政主管" 的安全链接策略的详细信息。

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safelinkspolicy)。

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

本示例返回名为 "Contoso 行政主管" 的安全链接规则的详细信息。

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/get-safelinksrule)。

### <a name="use-powershell-to-modify-safe-links-policies"></a>使用 PowerShell 修改安全链接策略

无法重命名 (PowerShell 中的安全链接策略 **SafeLinksPolicy** Cmdlet 没有 _名称_ 参数) 。 重命名安全 & 合规性中心中的 "安全链接" 策略时，只是重命名安全链接 _规则_ 。

修改 PowerShell 中的安全链接策略的唯一另一个注意事项是 _DoNotRewriteUrls_ 参数的可用语法， ( ["不重写以下 url" 列表](atp-safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies)) ：

- 若要添加将替换任何现有条目的值，请使用以下语法： `"Entry1","Entry2,..."EntryN"` 。
- 若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

否则，在创建安全链接策略时，可以使用相同的设置，如本文前面的 [步骤1：使用 PowerShell 创建安全链接策略](#step-1-use-powershell-to-create-a-safe-links-policy) 一节中所述。

若要修改安全链接策略，请使用以下语法：

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safelinkspolicy)。

### <a name="use-powershell-to-modify-safe-links-rules"></a>使用 PowerShell 修改安全链接规则

在 PowerShell 中修改安全链接规则时，唯一不可用的设置是允许您创建禁用规则的 _启用_ 参数。 若要启用或禁用现有安全链接规则，请参阅下一节。

否则，在创建规则时，可以使用相同的设置，如本文前面的 [步骤2：使用 PowerShell 创建安全链接规则](#step-2-use-powershell-to-create-a-safe-links-rule) 一节中所述。

若要修改安全链接规则，请使用以下语法：

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>使用 PowerShell 启用或禁用安全链接规则

启用或禁用 PowerShell 中的安全链接规则可启用或禁用 "安全链接" 规则和 "分配的安全链接" 策略) 的整个安全链接策略 (。

若要在 PowerShell 中启用或禁用安全链接规则，请使用以下语法：

```PowerShell
<Enable-SafeLinksRule | Disable-SafeLinksRule> -Identity "<RuleName>"
```

本示例禁用名为 "Marketing 部门" 的安全链接规则。

```PowerShell
Disable-SafeLinksRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-SafeLinksRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Enable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/enable-safelinksrule) 和 [Disable-SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/disable-safelinksrule)。

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

**注意** ：若要在创建新规则时设置其优先级，请改用 **SafeLinksRule** cmdlet 上的 _priority_ 参数。

有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-remove-safe-links-policies"></a>使用 PowerShell 删除安全链接策略

当您使用 PowerShell 删除安全链接策略时，不会删除相应的安全链接规则。

若要删除 PowerShell 中的安全链接策略，请使用以下语法：

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

本示例将删除名为 "Marketing 部门" 的安全链接策略。

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [SafeLinksPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safelinkspolicy)。

### <a name="use-powershell-to-remove-safe-links-rules"></a>使用 PowerShell 删除安全链接规则

当您使用 PowerShell 删除安全链接规则时，不会删除相应的安全链接策略。

若要删除 PowerShell 中的安全链接规则，请使用以下语法：

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

本示例将删除名为 "Marketing 部门" 的安全链接规则。

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [SafeLinksRule](https://docs.microsoft.com/powershell/module/exchange/remove-safelinksrule)。

若要验证安全链接是否正在扫描邮件，请查看可用的 Microsoft Defender for Office 365 报告。 有关详细信息，请参阅 [查看适用于 Office 365 的 Defender 报告](view-reports-for-atp.md) 和 [使用安全 & 合规性中心中的资源管理器](threat-explorer.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否已成功创建、修改或删除了安全链接策略，请执行以下任一步骤：

- 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全链接** "。 验证策略列表、策略的 **状态** 值及其 **优先级** 值。 若要查看更多详细信息，请从列表中选择策略，并在 "飞出" 中查看详细信息。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将替换 \<Name\> 为策略或规则的名称，运行以下命令，并验证设置：

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
