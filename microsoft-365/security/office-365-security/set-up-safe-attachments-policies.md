---
title: 在 Microsoft Defender 保险箱中设置"附件"Office 365
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 了解如何定义附件保险箱保护组织免受电子邮件中恶意文件的攻击。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 3ae702417d34351c99ccbd8432c2fc29f11a433f
ms.sourcegitcommit: 7b83e2605895fee5c73cd1d01f4cd16e1457a69f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60907921"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender 保险箱中设置"附件"Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md)的企业客户。 如果你是一位家庭用户，正在查找有关电子邮件中的附件扫描Outlook，请参阅[Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

保险箱附件是 Microsoft [Defender for Office 365](whats-new-in-defender-for-office-365.md)中的一项功能，该功能使用虚拟环境在[Exchange Online Protection (EOP) ](anti-malware-protection.md)中经过反恶意软件保护扫描之后，在发送给收件人之前，使用虚拟环境检查入站电子邮件中的附件。 有关详细信息，请参阅 microsoft Defender 保险箱[中的附件Office 365。](safe-attachments.md)

尽管没有默认的"保险箱 附件"策略，但内置保护预设安全策略会为未在自定义 保险箱 附件策略) 中定义的所有 (收件人提供 保险箱 附件保护。 有关详细信息，请参阅[Preset security policies in EOP and Microsoft Defender for Office 365](preset-security-policies.md)。 您还可以使用本文中的过程创建适用于保险箱用户、组或域的附件策略。

可以在 保险箱 Microsoft 365 Defender 门户中或在 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的符合条件的 Microsoft 365 组织配置附件Exchange Online;独立 EOP PowerShell，适用于Exchange Online邮箱，但使用 Defender for Office 365 加载项订阅的组织) 。

"附件"策略保险箱元素包括：

- 安全附件策略：指定未知恶意软件检测的操作、是否将带恶意软件附件的邮件发送到指定的电子邮件地址，以及是否传递保险箱附件扫描无法完成时传递邮件。
- **安全附件规则**：指定策略应用于 (的优先级和收件人) 。

当您在邮件门户中管理"附件"保险箱，这两个元素Microsoft 365 Defender并不明显：

- 创建附件保险箱策略时，实际上是同时使用同一名称创建安全附件规则和相关的安全附件策略。
- 修改附件保险箱时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全附件规则。 所有其他设置修改关联的安全附件策略。
- 删除"附件保险箱时，安全附件规则和相关的安全附件策略将被删除。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文稍后的使用[Exchange Online PowerShell 或独立 EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies)配置 保险箱 附件策略一节。

> [!NOTE]
> 在"附件"设置的全局保险箱区域中，配置不依赖于"附件"保险箱的功能。 有关说明，[请参阅在](turn-on-mdo-for-spo-odb-and-teams.md)保险箱 中打开SharePoint、OneDrive 和 Microsoft Teams 保险箱[文档](safe-docs.md)Microsoft 365 E5。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到"附件 **保险箱，** 请使用 <https://security.microsoft.com/safeattachmentv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您需具有权限，然后才能执行本文中的过程：
  - 若要创建、修改和删除 保险箱 附件策略，您需要是 Microsoft 365 Defender 门户中组织管理或安全管理员角色组的成员以及 Exchange Online 中的组织管理角色组的成员。 
  - 若要对"附件"策略保险箱只读访问权限，您需要是"附件"门户中全局读取者或安全读者角色Microsoft 365 Defender的成员。

  有关详细信息，请参阅 Microsoft 365 Defender[门户中的权限](permissions-microsoft-365-security-center.md)Exchange Online。 [](/exchange/permissions-exo/permissions-exo)

  **注意**：

  - 将用户添加到 Azure Active Directory 中的相应 Microsoft 365 管理中心 可为用户提供 Microsoft 365 Defender 门户中所需的权限以及 Microsoft 365 中其他功能Microsoft 365。  有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关附件策略的建议保险箱，请参阅附件[保险箱设置](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)。

- 最多允许应用新策略或更新策略 30 分钟。

## <a name="use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies"></a>使用Microsoft 365 Defender门户创建保险箱附件策略

在 保险箱 门户中创建自定义附件Microsoft 365 Defender将同时创建安全附件规则和相关的安全附件策略，对二者使用相同的名称。

1. 在Microsoft 365 Defender门户中，转到"策略"部分中的"电子邮件&协作策略 \> **"&"** 规则保险箱 \>  \> **附件****"。**

2. 在 **"保险箱"页上**，单击" ![ 创建图标"。](../../media/m365-cc-sc-create-icon.png) **Create**。

3. 将打开策略向导。 在" **命名策略"** 页上，配置以下设置：
   - **名称**：输入策略的唯一描述性名称。
   - **说明**：输入策略的可选说明。

   完成后，单击“**下一步**”。

4. 在 **出现的"用户** 和域"页上，标识策略应用于以下收件人 (内部) ：
   - **用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。
   - **组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。
   - **域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。

   单击相应的框，开始键入值，然后从结果中选择所需的值。 根据需要多次重复此过程。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

   对于用户或组，可以使用大多数标识符（名称、显示名称、别名、电子邮件地址、帐户名称等），但相应的显示名称则显示在结果中。对于用户，请自行输入星号（\*），以查看所有可用值。

   同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   - **排除这些用户、组和域**：若要为策略应用于的内部收件人添加例外（收件人例外），请选择此选项并配置例外。 设置和行为与条件完全相同。

   完成后，单击“**下一步**”。

5. 在“**设置**”页上，配置下列设置：

   - **保险箱附件未知恶意软件响应**：选择下列值之一：
     - **关闭**：通常，不建议使用此值。
     - **监视器**
     - **Block**：这是默认值，也是"标准"和"严格"预设 [安全策略中的建议值](preset-security-policies.md)。
     - **Replace**
     - **动态传递 (预览功能)**

     这些值在附件策略[保险箱中进行了说明](safe-attachments.md#safe-attachments-policy-settings)。

   - **隔离策略**：选择适用于由"附件"保险箱隔离的邮件的隔离策略 (阻止、替换或动态传递) 。    隔离策略定义用户可以对隔离邮件执行哪些操作，以及用户是否收到隔离通知。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

     空值表示默认隔离策略 (AdminOnlyAccessPolicy，用于通过"附件"保险箱检测) 。 稍后编辑"附件保险箱或查看设置时，将显示默认隔离策略名称。

   - 重定向带检测到的附件的邮件：如果选择"启用重定向"，可以在"将包含阻止、监视或替换附件的邮件发送到指定电子邮件地址"框中指定电子邮件地址，以发送包含恶意软件附件的邮件进行分析和调查。 

     对于"标准"和"严格"策略设置，建议启用重定向。 有关详细信息，请参阅附件[保险箱附件设置。](recommended-settings-for-eop-and-office365.md#safe-attachments-settings)

   - 如果扫描无法完成 (超时或错误 **) ，** 则应用 保险箱 附件检测响应：即使 **保险箱** 附件扫描无法完成，保险箱 附件未知恶意软件响应也针对邮件执行指定的操作。 如果选择此选项，请始终选择" **启用重定向** "，并指定电子邮件地址以发送包含恶意软件附件的邮件。 否则，邮件可能会丢失。

   完成后，单击“**下一步**”。

6. 在出现的“**审阅**”页面上，查看你的设置。 可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   完成后，请单击“**提交**”。

7. 在出现的确认页面上，单击“**完成**”。

## <a name="use-the-microsoft-365-defender-portal-to-view-safe-attachments-policies"></a>使用 Microsoft 365 Defender 门户查看保险箱附件策略

1. 在Microsoft 365 Defender门户中，转到"策略"部分中的"电子邮件&协作策略 \> **"&"** 规则保险箱 \>  \> **附件****"。**

2. 在 **保险箱附件**"页上，策略列表中将显示以下属性：
   - **名称**
   - **状态**
   - **优先级**

3. 当您通过单击该名称选择策略时，策略设置将显示在一个飞出内容中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-safe-attachments-policies"></a>使用Microsoft 365 Defender门户修改保险箱附件策略

1. 在Microsoft 365 Defender门户中，转到"策略"部分中的"电子邮件&协作策略 \> **"&"** 规则保险箱 \>  \> **附件****"。**

2. On the **保险箱 Attachments** page， select a policy from the list by clicking on the name.

3. 在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。 有关设置详细信息，请参阅本文前面使用Microsoft 365 Defender门户创建保险箱[附件](#use-the-microsoft-365-defender-portal-to-create-safe-attachments-policies)策略"部分。

若要启用或禁用策略或设置策略优先级顺序，请参阅以下几节。

### <a name="enable-or-disable-safe-attachments-policies"></a>启用或禁用保险箱附件策略

1. 在Microsoft 365 Defender门户中，转到"策略"部分中的"电子邮件&协作策略 \> **"&"** 规则保险箱 \>  \> **附件****"。**

2. On the **保险箱 Attachments** page， select a policy from the list by clicking on the name.

3. 在出现的策略详细信息浮出控件顶部，你将看到以下值之一：
   - **策略关闭**：若要打开策略，请单击![“打开”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“打开”**。
   - **策略打开**：若要关闭策略，请单击![“关闭”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“关闭”**。

4. 在出现的确认对话框中，单击“**打开**”或“**关闭**”。

5. 单击策略详细信息浮出控件中的“**关闭**”。

返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。

### <a name="set-the-priority-of-safe-attachments-policies"></a>设置"附件保险箱的优先级

默认情况下，保险箱附件策略的优先级取决于它们在 (中的创建顺序) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

保险箱附件策略按其处理顺序显示 (策略的优先级值为 0) 。 

**注意**：在Microsoft 365 Defender门户中，只能更改"附件保险箱策略的优先级。 在 PowerShell 中，您可以在创建安全附件规则策略时替代默认优先级 (这可能会影响现有规则) 。

要更改策略的优先级，请在策略属性中单击“**提高优先级**”或“**降低优先级**”（不能在 Microsoft 365 Defender 门户中直接修改 **优先级** 编号）。仅当具有多个策略时，更改策略的优先级才有意义。

1. 在Microsoft 365 Defender门户中，转到"策略"部分中的"电子邮件&协作策略 \> **"&"** 规则保险箱 \>  \> **附件****"。**

2. On the **保险箱 Attachments** page， select a policy from the list by clicking on the name.

3. 在出现的策略详细信息飞出的顶部，你将看到"根据当前优先级值和策略数增加优先级"或"减少优先级"：
   - 优先级值为 **0** **的策略** 只有"**减少优先级"** 选项可用。
   - 优先级 **值最低的策略** (例如 **，3**) 只有"增加优先级 **"** 选项可用。
   - 如果你有三个或多个策略，则最高优先级值和最低优先级值之间的策略同时具有"增加 **优先级** "和" **减少优先级"** 选项。

   单击![“提高优先级”图标。](../../media/m365-cc-sc-increase-icon.png) **“提高优先级”** 或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png) **“降低优先级”** 以更改 **“优先级”** 值。

4. 完成后，单击策略详细信息浮出控件中的“**关闭**”。

## <a name="use-the-microsoft-365-defender-portal-to-remove-safe-attachments-policies"></a>使用 Microsoft 365 Defender 门户删除保险箱附件策略

1. 在Microsoft 365 Defender门户中，转到"策略"部分中的"电子邮件&协作策略 \> **"&"** 规则保险箱 \>  \> **附件****"。**

2. On the **保险箱 Attachments** page， select a custom policy from the list by clicking on the name of the policy.

3. 在显示的策略详细信息浮出控件顶部，单击![更多操作图标。](../../media/m365-cc-sc-more-actions-icon.png) **更多操作** \> ![删除策略图标](../../media/m365-cc-sc-delete-icon.png) **删除策略**。

4. 在出现的确认对话框中，单击“**是**”。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置保险箱附件策略

如前面所述，保险箱附件策略由安全附件策略和安全附件规则组成。

在 PowerShell 中，安全附件策略和安全附件规则的区别显而易见。 您可以使用 **\* -SafeAttachmentPolicy** cmdlet 管理安全附件策略，然后使用 **\* -SafeAttachmentRule** cmdlet 管理安全附件规则。

- 在 PowerShell 中，首先创建安全附件策略，然后创建用于标识该规则所适用的策略的安全附件规则。
- 在 PowerShell 中，分别修改安全附件策略和安全附件规则中的设置。
- 从 PowerShell 中删除安全附件策略时，不会自动删除相应的安全附件规则，反之亦然。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>使用 PowerShell 创建保险箱附件策略

在 PowerShell 保险箱附件策略的过程包含两个步骤：

1. 创建安全附件策略。
2. 创建安全附件规则，该规则指定应用该规则的安全附件策略。

 **注意**：

- 可以创建新的安全附件规则，并为其分配现有的未关联的安全附件策略。 安全附件规则不能与多个安全附件策略关联。

- 可以在 PowerShell 中的新安全附件策略上配置以下设置，这些设置在 Microsoft 365 Defender 门户中不可用，直到创建策略之后：
  - 在 `$false` **New-SafeAttachmentRule** cmdlet cmdlet 上 (策略为"已禁用") 。
  - 在 _\<Number\>_ **New-SafeAttachmentRule** cmdlet (中) 策略的优先级) 。

- 在 PowerShell 中新建的安全附件策略在 Microsoft 365 Defender门户中不可见，除非将策略分配给安全附件规则。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>步骤 1：使用 PowerShell 创建安全附件策略

若要创建安全附件策略，请使用以下语法：

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" -Enable $true [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>] [-QuarantineTag <QuarantinePolicyName>]
```

此示例创建一个名为 Contoso All 的安全附件策略，并具有以下值：

- 在未使用 _Action_ 参数保险箱扫描 (发现包含恶意软件的邮件，默认值为 `Block`) 。
- 默认 [隔离策略](quarantine-policies.md) (AdminOnlyAccessPolicy) ，因为我们没有使用 _QuarantineTag_ 参数。
- 启用重定向，发现包含恶意软件的邮件将发送到 sec-ops@contoso.com 进行分析和调查。
- 保险箱附件扫描不可用或遇到错误，请不要传递邮件 (我们未使用 _ActionOnError_ 参数，默认值为 `$true`) 。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Enable $true -Redirect $true -RedirectAddress sec-ops@contoso.com
```

有关语法和参数的详细信息，请参阅 [New-SafeAttachmentPolicy](/powershell/module/exchange/new-safeattachmentpolicy)。

> [!NOTE]
> 有关指定在安全附件[策略](quarantine-policies.md)中使用的隔离策略的详细说明，请参阅使用 PowerShell 在"附件策略"保险箱[隔离策略。](quarantine-policies.md#safe-attachments-policies-in-powershell)

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>步骤 2：使用 PowerShell 创建安全附件规则

若要创建安全附件规则，请使用以下语法：

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

本示例创建名为 Contoso All 的安全附件规则，并满足以下条件：

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

如果 **Set-SafeAttachmentPolicy** cmdlet 没有 Name 参数，则 (PowerShell 中的安全附件策略) 。 当你在 保险箱 门户中重命名Microsoft 365 Defender附件策略时，你仅重命名安全附件 _规则_。

否则，创建安全附件策略时可用的设置相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-a-safe-attachment-policy) 创建安全附件策略部分所述。

若要修改安全附件策略，请使用以下语法：

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-SafeAttachmentPolicy](/powershell/module/exchange/set-safeattachmentpolicy)。

> [!NOTE]
> 有关指定在安全附件[策略](quarantine-policies.md)中使用的隔离策略的详细说明，请参阅使用 PowerShell 在"附件策略"保险箱[隔离策略。](quarantine-policies.md#safe-attachments-policies-in-powershell)

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>使用 PowerShell 修改安全附件规则

在 PowerShell 中修改安全附件规则时不可用的唯一设置是允许创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有安全附件规则，请参阅下一节。

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

可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。

若要在 PowerShell 中设置安全附件规则的优先级，请使用以下语法：

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" -Priority <Number>
```

此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。

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

本示例删除名为"Marketing Department"的安全附件规则。

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-SafeAttachmentRule](/powershell/module/exchange/remove-safeattachmentrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功创建、修改或删除附件保险箱，请执行下列任一步骤：

- 在 Microsoft 365 Defender 门户中，转到"策略"&中的"电子邮件&"&规则威胁策略保险箱 \>  \>  \> **附件**"。  验证策略列表、 **策略的 Status** 值及其 **Priority** 值。 若要查看更多详细信息，请通过单击名称从列表中选择策略，并查看飞出中的详细信息。

- 在Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将 替换为策略或规则的名称，运行以下命令并 \<Name\> 验证设置：

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

若要验证保险箱附件是否正在扫描邮件，请检查可用的 Defender Office 365报告。 有关详细信息，请参阅查看 Defender [for Office 365](view-reports-for-mdo.md)报告和使用浏览器在 Microsoft 365 Defender[门户](threat-explorer.md)。
