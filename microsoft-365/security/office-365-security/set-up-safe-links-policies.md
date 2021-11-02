---
title: 在 Microsoft Defender 保险箱设置链接策略Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: ''
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: bdd5372d-775e-4442-9c1b-609627b94b5d
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在 Microsoft Defender for 保险箱 中查看、创建、修改和删除保险箱链接策略和全局Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 878f29e07c99892fddf322c2435c6eeebc694f07
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/02/2021
ms.locfileid: "60646359"
---
# <a name="set-up-safe-links-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender 保险箱设置链接策略Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender for Office 365](defender-for-office-365.md)的企业客户。 如果你是一位家庭用户，正在查找有关 Outlook 中的安全链接的信息，请参阅 Advanced [Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

保险箱Microsoft [Defender for Office 365](defender-for-office-365.md)中的链接提供对邮件流中入站电子邮件的 URL 扫描，以及电子邮件和其他位置中 URL 和链接的单击验证时间。 有关详细信息，请参阅 microsoft [Defender for 保险箱 中的链接Office 365。](safe-links.md)

尽管没有默认的 保险箱 链接策略，但内置保护预设安全策略为未在自定义 保险箱 链接策略) 中定义的所有收件人 (提供 保险箱 链接保护。 有关详细信息，请参阅[Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md)。

您还可以使用本文中的过程创建适用于保险箱用户、组或域的链接策略。

> [!NOTE]
>
> 在链接策略之外配置保险箱 **链接保护保险箱** 全局设置。 有关说明，请参阅[在 Microsoft Defender 中配置保险箱链接的全局Office 365。](configure-global-settings-for-safe-links.md)
>
> 管理员应考虑链接的不同配置保险箱设置。 可用选项之一是在"链接"中包括保险箱信息。 此功能使 *安全运营团队* 能够调查潜在用户泄露、采取纠正措施并限制代价高昂的泄露。

您可以在 保险箱 门户中或在 PowerShell (Exchange Online Microsoft 365 Defender PowerShell 中为具有 Exchange Online 邮箱的符合条件的 Microsoft 365 组织配置链接Exchange Online;适用于没有邮箱且Exchange Online Microsoft Defender for Office 365加载项订阅的组织的独立 EOP PowerShell) 。

链接策略的基本保险箱包括：

- 安全链接策略：打开 保险箱 链接保护，启用实时 URL 扫描，指定是否在传递邮件之前等待实时扫描完成，启用内部邮件扫描，指定是否跟踪用户单击 URL，并指定是否允许用户单击原始 URL。
- **安全链接规则**：指定策略应用于 (的优先级和收件人) 。

当你在门户中管理"链接"保险箱，这两个元素Microsoft 365 Defender并不明显：

- 创建链接保险箱，实际上是同时使用同一名称创建安全链接规则和相关安全链接策略。
- 修改邮件保险箱策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全链接规则。 所有其他设置修改关联的安全链接策略。
- 删除链接保险箱，安全链接规则和相关的安全链接策略将被删除。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文稍后的使用[Exchange Online PowerShell 或独立 EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies)配置 保险箱 链接策略一节。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com/> 打开 Microsoft 365 Defender 门户。 若要直接转到"链接 **保险箱，** 请使用 <https://security.microsoft.com/safelinksv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您需获得权限，然后才能执行本文中的过程：
  - 若要创建、修改和删除 保险箱 链接策略，您需要是 Microsoft 365 Defender 门户中组织管理或安全管理员角色组的成员以及 Exchange Online 中的组织管理角色组的成员。 
  - 若要对链接策略保险箱只读访问权限，你需要是全局读者或安全读者 **角色组的成员**。 

  有关详细信息，请参阅 Microsoft 365 Defender[门户中的权限](permissions-microsoft-365-security-center.md)和 Exchange Online 中[的权限](/exchange/permissions-exo/permissions-exo)。

  > [!NOTE]
  >
  > - 将用户添加到 Azure Active Directory Microsoft 365 管理中心 中的相应 Azure Active Directory 角色会为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。 有关详细信息，请参阅[关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  . - **Exchange Online** 中的"仅查看组织管理"[](/Exchange/permissions-exo/permissions-exo#role-groups)角色组还授予对该功能的只读访问权限。

- 有关推荐的链接策略保险箱，请参阅保险箱[链接策略设置。](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)

- 最多允许应用新策略或更新策略 30 分钟。

- [新功能不断添加到 Microsoft Defender for Office 365。](defender-for-office-365.md#new-features-in-microsoft-defender-for-office-365) 添加新功能时，可能需要对现有"链接"策略保险箱调整。

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-links-policies"></a>使用 Microsoft 365 Defender 门户创建保险箱链接策略

在 保险箱 门户中创建自定义链接Microsoft 365 Defender将同时创建安全链接规则和相关的安全链接策略，对二者使用相同的名称。

1. 在 Microsoft 365 Defender 门户中，转到"策略&**规则** \> **""** 威胁策略策略" \> 部分保险箱 \> **链接"。**

2. 在 **"保险箱"** 页上，单击" ![ 创建图标"。](../../media/m365-cc-sc-create-icon.png) **Create**。

3. "**新建保险箱链接"策略** 向导将打开。 在" **命名策略"** 页上，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。
   - **说明**：输入策略的可选说明。

   完成后，单击“**下一步**”。

4. 在 **出现的"用户和** 域"页上，标识策略应用于以下收件人 (内部) ：
   - **用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。
   - **组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。
   - **域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。

   单击相应的框，开始键入值，然后从结果中选择所需的值。 根据需要多次重复此过程。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

   对于用户或组，可以使用大多数标识符（名称、显示名称、别名、电子邮件地址、帐户名称等），但相应的显示名称则显示在结果中。对于用户，请自行输入星号（\*），以查看所有可用值。

   同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   - **排除这些用户、组和域**：要为策略所应用的内部收件人添加例外（收件人例外），请选择此选项并配置例外。设置和行为与条件完全相同。

   完成后，单击“**下一步**”。

5. 在出现的 **"** 保护设置"页上，配置以下设置：
   - **选择邮件中未知潜在** 恶意 URL 的操作：选择"打开"以保险箱电子邮件中的链接的链接保护。 如果启用此设置，则以下设置可用：
     - **对指向文件的可疑链接应用实时 URL** 扫描：选择此选项可启用电子邮件中链接实时扫描。 如果打开此设置，则以下设置可用：
       - **等待 URL 扫描完成，然后再传递邮件**：选择此选项以等待实时 URL 扫描完成，然后再传递邮件。
     - **Apply 保险箱 Links to email messages sent within the organization**： Select this option to apply the 保险箱 Links policy to messages between internal senders and internal recipients.
   - **Select the action for unknown or potentially malicious URLS within Microsoft Teams：** Select **On** to enable 保险箱 Links protection for links in Teams. 请注意，此设置最多可能需要 24 小时才能生效。
   - **Do not track user clicks**： Leave this setting unselected to enable the tracking user clicks on URLs in email messages.
   - **不允许用户单击到原始 URL：** 选择此选项可阻止用户单击到警告页面中 [的原始](safe-links.md#warning-pages-from-safe-links)URL。
   - **不要重写以下 URL：** 允许访问指定 URL，否则，链接保险箱阻止。

     在框中，键入您需要的 URL 或值，然后单击"添加 **"。** 根据需要重复执行此步骤（次数不限）。

     若要删除现有条目，请单击 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) 项旁边。

     有关条目语法，请参阅 ["不重写以下 URL"列表的条目语法](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)。

   有关这些设置的详细信息，请参阅保险箱[电子邮件](safe-links.md#safe-links-settings-for-email-messages)的链接设置和保险箱[的链接Microsoft Teams。](safe-links.md#safe-links-settings-for-microsoft-teams)

   有关"标准"和"严格"策略[设置保险箱建议的值](recommended-settings-for-eop-and-office365.md#safe-links-policy-settings)，请参阅链接策略设置。

   完成后，单击“**下一步**”。

6. 在 **出现的"** 通知"页上，为"如何通知用户？"选择下列值 **之一**：
   - **使用默认通知文本**
   - **使用自定义通知文本**：如果选择此值 (长度不能超过 200 个字符) ，将显示以下设置：
     - **使用Microsoft 翻译工具进行自动本地化**
     - **自定义通知文本**：在此框中输入自定义通知文本。

   完成后，单击“**下一步**”。

7. 在出现的“**审阅**”页面上，查看你的设置。 可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   完成后，请单击“**提交**”。

8. 在出现的确认页面上，单击“**完成**”。

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-links-policies"></a>使用 Microsoft 365 Defender 门户查看保险箱链接策略

1. In the Microsoft 365 Defender portal， go to **Policies & rules** Threat \> **Policies** \> **Policies** section \> **保险箱 Links**.

2. 在 **"保险箱链接**"页上，以下属性显示在"链接保险箱列表中：
   - **名称**
   - **状态**
   - **优先级**

3. 当您通过单击该名称选择策略时，策略设置将显示在一个飞出内容中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-links-policies"></a>使用 Microsoft 365 Defender门户修改保险箱链接策略

1. In the Microsoft 365 Defender portal， go to **Policies & rules** Threat \> **Policies** \> **Policies** section \> **保险箱 Links**.

2. 在 **"保险箱链接**"页上，通过单击名称从列表中选择策略。

3. 在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。 有关设置详细信息，请参阅本文前面的使用 Microsoft 365 Defender[门户创建保险箱链接](#use-the-microsoft-365-defender-portal-to-create-safe-links-policies)策略部分。

若要启用或禁用策略或设置策略优先级顺序，请参阅以下部分。

### <a name="enable-or-disable-safe-links-policies"></a>启用或禁用保险箱链接策略

1. 在 Microsoft 365 Defender 门户中，转到"策略"部分中的"电子邮件&协作策略&规则威胁保险箱链接 \>  \>  \> " 。 

2. 在 **"保险箱链接**"页上，通过单击名称从列表中选择策略。

3. 在出现的策略详细信息浮出控件顶部，你将看到以下值之一：
   - **策略关闭**：若要打开策略，请单击![“打开”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“打开”**。
   - **策略打开**：若要关闭策略，请单击![“关闭”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“关闭”**。

4. 在出现的确认对话框中，单击“**打开**”或“**关闭**”。

5. 单击策略详细信息浮出控件中的“**关闭**”。

返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。

### <a name="set-the-priority-of-safe-links-policies"></a>设置链接保险箱优先级

默认情况下，保险箱链接的优先级基于它们在 (中的创建顺序，因此其优先级低于较旧策略) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

要更改策略的优先级，请在策略属性中单击“**提高优先级**”或“**降低优先级**”（不能在 Microsoft 365 Defender 门户中直接修改 **优先级** 编号）。仅当具有多个策略时，更改策略的优先级才有意义。

**注意**：

- 在Microsoft 365 Defender门户中，创建链接策略保险箱更改策略的优先级。 在 PowerShell 中，您可以在创建安全链接规则集时替代默认优先级 (这可能会影响现有规则集) 。
- 保险箱按照链接策略的显示顺序处理 (优先级值为 0 时) 。  有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

1. 在 Microsoft 365 Defender 门户中，转到"策略"部分中的"电子邮件&协作策略&规则威胁保险箱链接 \>  \>  \> " 。 

2. 在 **"保险箱链接**"页上，通过单击名称从列表中选择策略。

3. 在出现的策略详细信息浮出控件顶部，你会看到“**提高优先级**”或“**降低优先级**”，具体取决于当前优先级值和自定义策略数量：
   - 优先级值为 **0** **的策略** 只有"**减少优先级"** 选项可用。
   - 优先级 **值最低的策略** (例如 **，3**) 只有"增加优先级 **"** 选项可用。
   - 如果你有三个或多个策略，则最高优先级值和最低优先级值之间的策略同时具有"增加 **优先级** "和" **减少优先级"** 选项。

   单击![“提高优先级”图标。](../../media/m365-cc-sc-increase-icon.png) **“提高优先级”** 或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png) **“降低优先级”** 以更改 **“优先级”** 值。

4. 完成后，单击策略详细信息浮出控件中的“**关闭**”。

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-links-policies"></a>使用 Microsoft 365 Defender 门户删除保险箱链接策略

1. 在 Microsoft 365 Defender 门户中，转到"策略"部分中的"电子邮件&协作策略&规则威胁保险箱链接 \>  \>  \> " 。 

2. 在 **"保险箱链接**"页上，通过单击名称从列表中选择策略。 在显示的策略详细信息浮出控件顶部，单击![更多操作图标。](../../media/m365-cc-sc-more-actions-icon.png) **更多操作** \> ![删除策略图标](../../media/m365-cc-sc-delete-icon.png) **删除策略**。

3. 在出现的确认对话框中，单击“**是**”。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-links-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置保险箱链接策略

如前面所述，保险箱链接策略由安全链接策略和安全链接规则组成。

在 PowerShell 中，安全链接策略和安全链接规则的区别显而易见。 您可以使用 **\* -SafeLinksPolicy** cmdlet 管理安全链接策略，使用 **\* -SafeLinksRule** cmdlet 管理安全链接规则。

- 在 PowerShell 中，首先创建安全链接策略，然后创建安全链接规则，以标识该规则应用于的策略。
- 在 PowerShell 中，分别修改安全链接策略和安全链接规则中的设置。
- 从 PowerShell 中删除安全链接策略时，不会自动删除相应的安全链接规则，反之亦然。

### <a name="use-powershell-to-create-safe-links-policies"></a>使用 PowerShell 创建链接保险箱链接策略

在 PowerShell 保险箱链接策略的过程包含两个步骤：

1. 创建安全链接策略。
2. 创建安全链接规则，该规则指定应用该规则的安全链接策略。

> [!NOTE]
>
> - 你可以创建新的安全链接规则，并为其分配现有的未关联安全链接策略。 安全链接规则不能与多个安全链接策略关联。
>
> - 可以在 PowerShell 中的新安全链接策略上配置以下设置，这些设置在 Microsoft 365 Defender创建策略之前在 Microsoft 365 Defender 门户中不可用：
>   - 在 `$false` **New-SafeLinksRule** cmdlet (上创建禁用的新策略) 。
>   - 在 _\<Number\>_ **New-SafeLinksRule** cmdlet cmdlet (中) 策略的优先级) 。
>
> - 在 PowerShell 中创建的新安全链接策略在 Microsoft 365 Defender门户中不可见，除非将策略分配给安全链接规则。

#### <a name="step-1-use-powershell-to-create-a-safe-links-policy"></a>步骤 1：使用 PowerShell 创建安全链接策略

若要创建安全链接策略，请使用以下语法：

```PowerShell
New-SafeLinksPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-IsEnabled <$true | $false>] [-EnableSafeLinksForTeams <$true | $false>] [-ScanUrls <$true | $false>] [-DeliverMessageAfterScan <$true | $false>] [-EnableForInternalSenders <$true | $false>] [-DoNotAllowClickThrough <$true | $false>] [-DoNotTrackUserClicks <$true | $false>] [-DoNotRewriteUrls "Entry1","Entry2",..."EntryN"]
```

> [!NOTE]
>
> - 有关要用于 _DoNotRewriteUrls_ 参数的条目语法的详细信息，请参阅"不要重写以下 [URL"](safe-links.md#entry-syntax-for-the-do-not-rewrite-the-following-urls-list)列表的条目语法。
>
> - 有关在使用 **Set-SafeLinksPolicy** cmdlet 修改现有安全链接策略时可用于 _DoNotRewriteUrls_ 参数的其他语法，请参阅本文稍后的使用 [PowerShell](#use-powershell-to-modify-safe-links-policies)修改安全链接策略一节。

此示例创建一个名为 Contoso All 的安全链接策略，并具有以下值：

- 在电子邮件中打开 URL 扫描和重写。
- 在"URL 扫描"中Teams。
- 打开单击的 URL（包括指向文件的单击链接）实时扫描。
- 等待 URL 扫描完成，然后再传递邮件。
- 打开内部邮件的 URL 扫描和重写。
- 跟踪与 保险箱 链接保护相关的用户单击 (我们并不使用 _DoNotTrackUserClicks_ 参数，默认值为 $false，这意味着用户单击会) 。
- 不允许用户单击访问原始 URL。

```PowerShell
New-SafeLinksPolicy -Name "Contoso All" -IsEnabled $true -EnableSafeLinksForTeams $true -ScanUrls $true -DeliverMessageAfterScan $true -EnableForInternalSenders $true -DoNotAllowClickThrough $true
```

有关语法和参数的详细信息，请参阅[New-SafeLinksPolicy。](/powershell/module/exchange/new-safelinkspolicy)

#### <a name="step-2-use-powershell-to-create-a-safe-links-rule"></a>步骤 2：使用 PowerShell 创建安全链接规则

若要创建安全链接规则，请使用以下语法：

```PowerShell
New-SafeLinksRule -Name "<RuleName>" -SafeLinksPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

本示例创建一个名为"Contoso All"的安全链接规则，并满足以下条件：

- 该规则与名为 Contoso All 的安全链接策略相关联。
- 该规则适用于域中的所有 contoso.com。
- 因为我们没有使用 _Priority_ 参数，所以使用默认优先级。
- 如果规则 (_Enabled_ 参数，则启用该规则，默认值为 `$true`) 。

```powershell
New-SafeLinksRule -Name "Contoso All" -SafeLinksPolicy "Contoso All" -RecipientDomainIs contoso.com
```

有关语法和参数的详细信息，请参阅[New-SafeLinksRule。](/powershell/module/exchange/new-safelinksrule)

### <a name="use-powershell-to-view-safe-links-policies"></a>使用 PowerShell 查看安全链接策略

若要查看现有安全链接策略，请使用以下语法：

```PowerShell
Get-SafeLinksPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本示例返回所有安全链接策略的摘要列表。

```PowerShell
Get-SafeLinksPolicy | Format-Table Name
```

此示例返回名为 Contoso Executives 的安全链接策略的详细信息。

```PowerShell
Get-SafeLinksPolicy -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅 [Get-SafeLinksPolicy](/powershell/module/exchange/get-safelinkspolicy)。

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

本示例返回名为 Contoso Executives 的安全链接规则的详细信息。

```PowerShell
Get-SafeLinksRule -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅 [Get-SafeLinksRule](/powershell/module/exchange/get-safelinksrule)。

### <a name="use-powershell-to-modify-safe-links-policies"></a>使用 PowerShell 修改安全链接策略

You can't rename a safe links policy in PowerShell (**the Set-SafeLinksPolicy** cmdlet has no _Name_ parameter) . 当你在 保险箱 门户中重命名Microsoft 365 Defender链接策略时，你仅重命名安全链接 _规则_。

在 PowerShell 中修改安全链接策略的唯一额外注意事项是 _DoNotRewriteUrls_ 参数的可用语法 ("不重写以下 [URL"](safe-links.md#do-not-rewrite-the-following-urls-lists-in-safe-links-policies) 列表) ：

- 若要添加将替换任何现有条目的值，请使用以下语法： `"Entry1","Entry2,..."EntryN"` 。
- 若要在不影响其他现有条目的情况下添加或删除值，请使用以下语法： `@{Add="Entry1","Entry2"...; Remove="Entry3","Entry4"...}`

否则，创建安全链接策略时，会提供相同的设置，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-a-safe-links-policy) 创建安全链接策略一节中所述。

若要修改安全链接策略，请使用以下语法：

```PowerShell
Set-SafeLinksPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-SafeLinksPolicy](/powershell/module/exchange/set-safelinkspolicy)。

### <a name="use-powershell-to-modify-safe-links-rules"></a>使用 PowerShell 修改安全链接规则

在 PowerShell 中修改安全链接规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有安全链接规则，请参阅下一节。

否则，创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-a-safe-links-rule) 创建安全链接规则一节中所述的设置相同。

若要修改安全链接规则，请使用以下语法：

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-enable-or-disable-safe-links-rules"></a>使用 PowerShell 启用或禁用安全链接规则

在 PowerShell 中启用或禁用安全链接规则可启用或禁用整个 保险箱 链接策略 (安全链接规则以及分配的安全链接策略) 。

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

有关语法和参数的详细信息，请参阅[Enable-SafeLinksRule](/powershell/module/exchange/enable-safelinksrule)和[Disable-SafeLinksRule。](/powershell/module/exchange/disable-safelinksrule)

### <a name="use-powershell-to-set-the-priority-of-safe-links-rules"></a>使用 PowerShell 设置安全链接规则的优先级

可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。

若要在 PowerShell 中设置安全链接规则的优先级，请使用以下语法：

```PowerShell
Set-SafeLinksRule -Identity "<RuleName>" -Priority <Number>
```

此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。

```PowerShell
Set-SafeLinksRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
> 若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-SafeLinksRule** cmdlet 上的 _Priority_ 参数。

有关语法和参数的详细信息，请参阅 [Set-SafeLinksRule](/powershell/module/exchange/set-safelinksrule)。

### <a name="use-powershell-to-remove-safe-links-policies"></a>使用 PowerShell 删除安全链接策略

使用 PowerShell 删除安全链接策略时，不会删除相应的安全链接规则。

若要在 PowerShell 中删除安全链接策略，请使用以下语法：

```PowerShell
Remove-SafeLinksPolicy -Identity "<PolicyName>"
```

此示例删除名为 Marketing Department 的安全链接策略。

```PowerShell
Remove-SafeLinksPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[Remove-SafeLinksPolicy。](/powershell/module/exchange/remove-safelinkspolicy)

### <a name="use-powershell-to-remove-safe-links-rules"></a>使用 PowerShell 删除安全链接规则

使用 PowerShell 删除安全链接规则时，不会删除相应的安全链接策略。

若要在 PowerShell 中删除安全链接规则，请使用以下语法：

```PowerShell
Remove-SafeLinksRule -Identity "<PolicyName>"
```

本示例删除名为"Marketing Department"的安全链接规则。

```PowerShell
Remove-SafeLinksRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-SafeLinksRule](/powershell/module/exchange/remove-safelinksrule)。

若要验证保险箱是否正在扫描邮件，请检查可用的 Microsoft Defender Office 365报告。 有关详细信息，请参阅查看 Defender [for Office 365](view-reports-for-mdo.md)报告和使用浏览器在 Microsoft 365 Defender[门户](threat-explorer.md)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否成功创建、修改或删除了链接保险箱，请执行下列任一步骤：

- In the Microsoft 365 Defender portal， go to **Policies & rules** Threat policies \> **保险箱** \> **Links**. 验证策略列表、 **策略的 Status** 值及其 **Priority** 值。 若要查看更多详细信息，请从列表中选择策略，然后查看飞出中的详细信息。

- 在Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将 替换为策略或规则的名称，运行以下命令并 \<Name\> 验证设置：

  ```PowerShell
  Get-SafeLinksPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-SafeLinksRule -Identity "<Name>"
  ```
