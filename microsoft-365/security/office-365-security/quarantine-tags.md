---
title: 隔离策略
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 管理员可以了解如何使用隔离策略来控制用户可以对隔离邮件执行哪些操作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 96dc1e2158787457884ca6a3c6f27bf76e83a369
ms.sourcegitcommit: b3c4816b55657b87ed4a5f6a4abe3d505392218e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/04/2021
ms.locfileid: "53757218"
---
# <a name="quarantine-policies"></a>隔离策略

> [!NOTE]
> 本文中介绍的功能目前处于预览阶段，不可供所有人使用，并且可能会更改。

 (EOP) 中以前称为隔离标记 Exchange Online Protection () 的隔离策略允许管理员根据邮件如何到达隔离区来控制用户能够对隔离邮件执行哪些操作。

EOP 在传统上允许或阻止隔离和最终用户垃圾邮件通知中的邮件的某些[交互级别](use-spam-notifications-to-release-and-report-quarantined-messages.md)。 [](find-and-release-quarantined-messages-as-a-user.md) 例如，用户可以查看并释放被反垃圾邮件筛选隔离为垃圾邮件或批量邮件的邮件，但他们无法查看或释放被隔离为高可信度网络钓鱼的邮件 (只有管理员才能执行) 。

对于 [受支持的保护](#step-2-assign-a-quarantine-policy-to-supported-features)功能，隔离策略指定允许用户在最终用户垃圾邮件通知邮件中和隔离邮件中执行哪些操作 (用户是收件人收件人的邮件) 。 自动分配默认隔离策略，以对隔离邮件的用户强制实施历史功能。 或者，可以创建和分配自定义隔离策略，以允许或阻止最终用户对隔离邮件执行特定操作。

各个权限组合到以下预设权限组中：

- 无访问权限
- 受限访问
- 完全访问权限

下表介绍了可用的单个权限以及预设权限组中包含或不包含哪些权限：

<br>

****

|权限|无访问权限|受限访问|完全访问权限|
|---|:---:|:---:|:---:|
|**允许发件人 (** _PermissionToAllowSender)_|||![复选标记](../../media/checkmark.png)|
|**阻止发件人 (** _PermissionToBlockSender_) ||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|**删除** (_PermissionToDelete_) ||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|**预览** (_PermissionToPreview_) ||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|**允许收件人通过** _PermissionToRelease (隔离邮件)_|||![复选标记](../../media/checkmark.png)|
|**允许收件人请求从隔离邮箱** 中释放 (_PermissionToRequestRelease_) ||![复选标记](../../media/checkmark.png)||
|

如果您不喜欢预设权限组中的默认权限，可以在创建或修改自定义隔离策略时使用自定义权限。 有关每个权限执行哪些操作的详细信息，请参阅本文稍后[](#quarantine-policy-permission-details)介绍的隔离策略权限详细信息部分。

在邮箱门户或 PowerShell Microsoft 365 Defender PowerShell (Exchange Online邮箱Microsoft 365分配隔离Exchange Online策略;EOP 组织中独立的 EOP PowerShell，Exchange Online邮箱) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 或者，若要直接转到隔离 **策略页面** ，请打开 <https://security.microsoft.com/quarantineTags> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 若要查看、创建、修改或删除隔离策略，您需要是组织管理或安全管理员角色在 Microsoft 365 Defender的成员。  有关详细信息，请参阅 [Microsoft 365 Defender 门户中的权限](permissions-microsoft-365-security-center.md)。

## <a name="step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal"></a>步骤 1：在管理门户Microsoft 365 Defender隔离策略

1. 在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**

2. 在"**隔离策略"页上**，单击" ![ 添加自定义策略"图标 ](../../media/m365-cc-sc-create-icon.png) **"添加自定义策略"。**

3. 将 **打开"新建策略** "向导。 在" **策略名称"** 页上，在"策略名称"框中输入简短但 **唯一** 的名称。 你需要在即将推出的步骤中按名称标识并选择隔离策略。 完成后，单击“**下一步**”。

4. 在" **收件人邮件访问"** 页上，选择下列值之一：
   - **禁止访问**
   - **受限访问**
   - **完全访问权限**

   本文前面介绍了这些权限组中包含的单个权限。

   若要指定自定义权限，请选择"使用高级 (设置) 并配置以下显示设置：

     - **选择发布操作首选项**：选择下列值之一：
       - **无发布操作**：这是默认值。
       - **允许收件人从隔离中释放邮件**
       - **允许收件人请求从隔离区中释放邮件**
     - **选择收件人对隔离邮件** 可以执行的其他操作：选择以下部分值、全部值或下列值之一：
       - **删除**
       - **预览**
       - **阻止发件人**

   本文稍后的隔离策略权限详细信息部分介绍了这些权限及其对隔离邮件和最终用户垃圾邮件通知的影响。 [](#quarantine-policy-permission-details)

   完成后，单击“**下一步**”。

5. 在出现的 **"查看** 策略"页上，查看设置。 可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   完成后，请单击“**提交**”。

6. 在出现的确认页面上，单击“**完成**”。

现在，你已准备好将隔离策略分配给隔离功能，如步骤 [2](#step-2-assign-a-quarantine-policy-to-supported-features) 部分中所述。

### <a name="create-quarantine-policies-in-powershell"></a>在 PowerShell 中创建隔离策略

如果你希望使用 PowerShell 创建隔离策略，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 并使用 **New-QuarantineTag** cmdlet。 有两种不同的方法可供选择：

- 使用 _EndUserQuarantinePermissionsValue_ 参数。
- 使用 _EndUserQuarantinePermissions_ 参数。

以下各节介绍了这些方法。

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>使用 EndUserQuarantinePermissionsValue 参数

若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离策略，请使用以下语法：

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

_EndUserQuarantinePermissionsValue_ 参数使用从二进制值转换的十进制值。 二进制值对应于按特定顺序可用的最终用户隔离权限。 对于每个权限，值 1 等于 True，值 0 等于 False。

下表介绍了预设权限组中各个权限的必需顺序和值：

<br>

****

|权限|无访问权限|受限访问|完全访问权限|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|0|0|1|
|PermissionToBlockSender|0|1|1|
|PermissionToDelete|0|1|1|
|PermissionToDownload<sup>\*</sup>|0|0|0|
|PermissionToPreview|0|1|1|
|PermissionToRelease<sup>\*\*</sup>|0|0|1|
|PermissionToRequestRelease<sup>\*\*</sup>|0|1|0|
|PermissionToViewHeader<sup>\*</sup>|0|0|0|
|二进制值|00000000|01101010|11101100|
|使用的小数值|0|106|236|
|

<sup>\*</sup> 目前，此值始终为 0。 对于 PermissionToViewHeader，值 0 不会在隔离邮件的详细信息中隐藏"查看邮件头"按钮 (该按钮始终) 。

<sup>\*\*</sup> 不要将两个值都设置为 1。 将一个设置为 1，另一个设置为 0，或同时设置为 0。

此示例创建一个新的隔离策略名称 NoAccess，该名称分配"无访问权限"权限，如上表所述。

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

对于"受限访问权限"，请使用值 106。 对于"完全访问权限"，请使用值 236。

对于自定义权限，请使用上表获取与所需的权限对应的二进制值。 将二进制值转换为十进制值，并将小数值用于 _EndUserQuarantinePermissionsValue_ 参数。

有关语法和参数的详细信息，请参阅 [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)。

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>使用 EndUserQuarantinePermissions 参数

若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离策略，请执行以下步骤：

答： 使用 **New-QuarantinePermissions** cmdlet 将隔离权限对象存储在变量中。

<p>

B. 在 **New-QuarantineTag** 命令中将变量用作 _EndUserQuarantinePermissions_ 值。

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>步骤 A：将隔离权限对象存储在变量中

使用以下语法:

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

任何未使用的参数的默认值都是 ，因此只需使用要将值 `$false` 设置为 的参数 `$true` 。

以下示例显示如何创建与预设权限组对应的权限对象：

- **无法访问**：

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **受限访问**：

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **完全访问权限**：

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

To see the values that you've set， run the variable name as a command (for example， run the command `$NoAccess`) .

对于自定义权限，不要同时将 _PermissionToRelease_ 和 _PermissionToRequestRelease_ 参数设置为 `$true` 。 将一个 `$true` 设置为 ，将另一个设置为 `$false` ，或者将两者都保留为 `$false` 。

您还可以在创建之后、使用 **Set-QuarantinePermissions** cmdlet 使用之前修改现有 permissions 对象变量。

有关语法和参数的详细信息，请参阅[New-QuarantinePermissions](/powershell/module/exchange/new-quarantinepermissions)和[Set-QuarantinePermissions。](/powershell/module/exchange/set-quarantinepermissions)

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>步骤 B：在命令中New-QuarantineTag变量

创建权限对象并存储到变量中后，请使用以下 **New-QuarantineTag** 命令中的 _EndUserQuarantinePermission_ 参数值变量：

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

此示例使用上一步中介绍和创建的权限对象创建名为 LimitedAccess 的新 `$LimitedAccess` 隔离策略。

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

有关语法和参数的详细信息，请参阅 [New-QuarantineTag](/powershell/module/exchange/new-quarantinetag)。

## <a name="step-2-assign-a-quarantine-policy-to-supported-features"></a>步骤 2：将隔离策略分配给支持的功能

在 _可_ 自动隔离邮件或文件的 (或作为可配置操作) ，您可以将隔离策略分配给可用的隔离操作。 下表介绍了隔离邮件的功能和隔离策略的可用性：

<br>

****

|功能|支持隔离策略？|使用的默认隔离策略|
|---|:---:|---|
|[反垃圾邮件策略](configure-your-spam-filter-policies.md)： <ul><li>**Spam** (_SpamAction_) </li><li>**高可信度垃圾邮件** (_HighConfidenceSpamAction_) </li><li>**Phishing** (_PhishSpamAction_) </li><li>**高可信度网络钓鱼** (_HighConfidencePhishAction_) </li><li>**批量** (_BulkSpamAction_) </li></ul>|是|<ul><li>DefaultSpamTag (完全访问权限) </li><li>DefaultHighConfSpamTag (完全访问权限) </li><li>DefaultPhishTag (完全访问权限) </li><li>DefaultHighConfPhishTag (无法访问) </li><li>DefaultBulkTag (完全访问权限) </li></ul>
|防钓鱼策略： <ul><li>[](set-up-anti-phishing-policies.md#spoof-settings) _AuthenticationFailAction (反欺骗智能_) </li><li>[模拟保护](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)：<sup>\*</sup> <ul><li>**如果邮件被检测为** _TargetedUserProtectionAction_ (模拟) </li><li>**如果邮件被检测为** _TargetedDomainProtectionAction_ (模拟) </li><li>**如果邮箱智能检测到并模拟** _MailboxIntelligenceProtectionAction (MailboxIntelligenceProtectionAction_) </li></ul></li></ul></ul>|否|不适用|
|[反恶意软件策略](configure-anti-malware-policies.md)：始终隔离所有检测到的邮件。|否|不适用|
|[用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](mdo-for-spo-odb-and-teams.md)|否|不适用|
|[邮件流规则](/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (操作) 传输规则： **将** 邮件发送到托管隔离邮箱 (_隔离_) 。|否|不适用|
|

<sup>\*</sup>模拟保护设置仅在 Microsoft Defender for Office 365 中的反网络钓鱼策略中Office 365。

如果您对默认隔离策略提供的最终用户权限满意，则无需执行任何操作。 如果要自定义最终用户功能 (最终用户垃圾邮件) 或隔离邮件详细信息中的可用按钮，您可以分配自定义隔离策略。

### <a name="assign-quarantine-policies-in-anti-spam-policies-in-the-microsoft-365-defender-portal"></a>在门户中的反垃圾邮件策略中分配Microsoft 365 Defender策略

有关创建和修改反垃圾邮件策略的完整说明，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

1. In the Microsoft 365 Defender portal， go to **Email & collaboration** Policies & \> **rules** \> **Policies** section \> **Anti-spam**. 或者，打开 <https://security.microsoft.com/antispam> 。

2. 在 **"反垃圾邮件策略"** 页上，执行下列步骤之一：
   - 查找并选择现有的 **入站** 反垃圾邮件策略。
   - 创建新的 **入站** 反垃圾邮件策略。

3. 采取以下步骤之一：
   - **编辑现有的反垃圾邮件策略**：在策略详细信息飞出控件中，转到"**操作**"部分，然后单击"编辑 **操作"。**
   - **创建新的反垃圾邮件策略**：在新建策略向导中，转到" **操作"** 页面。

4. 在" **操作"** 页上。 每个具有"隔离邮件 **"操作** 裁定还将具有" **选择** 隔离策略"框，供你选择相应的隔离策略。

   **注意**：创建新策略时，空白选择隔离策略值表示已使用该裁定的默认隔离策略。 以后编辑策略时，空白值将替换为实际的默认隔离策略名称，如上表所述。

   ![反垃圾邮件策略中的隔离策略选择](../../media/quarantine-tags-in-anti-spam-policies.png)

5. 完成后，单击“**保存**”。

#### <a name="assign-quarantine-policies-in-anti-spam-policies-in-powershell"></a>在 PowerShell 中的反垃圾邮件策略中分配隔离策略

如果您更希望使用 PowerShell 在反垃圾邮件策略中分配隔离策略，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 并使用以下语法：

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**注意**:

- _HighConfidencePhishAction_ 参数的默认值为 Quarantine，因此无需设置新反垃圾邮件策略中的高可信度网络钓鱼检测的隔离操作。 对于新的或现有的反垃圾邮件策略中的所有其他垃圾邮件筛选裁定，隔离策略仅在操作值为 Quarantine 时有效。 若要查看现有反垃圾邮件策略中的操作值，请运行以下命令：

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  有关默认操作值以及 Standard 和 Strict 的建议操作值的信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。

- 没有相应的隔离策略参数的垃圾邮件筛选裁定意味着使用该 [裁定的默认](#step-2-assign-a-quarantine-policy-to-supported-features) 隔离策略。

  如果希望更改隔离邮件的默认最终用户功能，只需将默认隔离策略替换为自定义隔离策略。

- PowerShell 中的新反垃圾邮件策略需要使用 **New-HostedContentFilterPolicy** cmdlet 和新的垃圾邮件筛选器规则 (收件人筛选器) cmdlet 创建垃圾邮件筛选策略 (设置) 。  有关说明，请参阅 [使用 PowerShell 创建反垃圾邮件策略](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。

本示例将创建一个名为"Research Department"的新垃圾邮件筛选策略，并具有以下设置：

- 所有垃圾邮件筛选裁定的操作均设置为"隔离"。
- 分配"无访问权限"的名为 NoAccess的自定义隔离策略将替换默认情况下尚未分配"无访问权限"的任何默认隔离策略。

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](/powershell/module/exchange/new-hostedcontentfilterpolicy)。

此示例修改名为 Human Resources 的现有垃圾邮件筛选器策略。 垃圾邮件隔离裁定的操作设置为"隔离"，并分配名为 NoAccess 的自定义隔离策略。

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](/powershell/module/exchange/set-hostedcontentfilterpolicy)。

## <a name="configure-global-quarantine-notification-settings-in-the-microsoft-365-defender-portal"></a>在门户中配置全局隔离Microsoft 365 Defender设置

隔离策略的全局设置允许您自定义发送到已隔离邮件收件人的最终用户垃圾邮件通知。 有关这些通知详细信息，请参阅 [最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。

1. 在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**

2. 在"**隔离策略"页上**，选择"**全局设置"。**

3. 在打开 **的"隔离** 通知设置"飞出中，配置以下部分或所有设置：

   - **显示名称**：自定义显示名称垃圾邮件通知中使用的发件人地址。

     对于已添加的每种语言，选择第二种语言框中的语言 (不要单击 X) 请在"显示名称"框中输入您需要 **的文本值。**

     以下屏幕截图显示了最终用户显示名称中的自定义邮件：

     ![自定义发件人显示名称最终用户垃圾邮件通知中](../../media/quarantine-tags-esn-customization-display-name.png)

   - **免责声明**：将自定义免责声明添加到最终用户垃圾邮件通知的底部。 您组织的本地化文本 **（免责声明：）** 始终先包含，后跟您指定的文本。

     对于已添加的每种语言，选择第二种语言框中 (不要单击"X) "，在"免责声明"框中输入 **您需要的文本值** 。

     以下屏幕截图显示了最终用户垃圾邮件通知中的自定义免责声明：

     ![最终用户垃圾邮件通知底部的自定义免责声明](../../media/quarantine-tags-esn-customization-disclaimer.png)

   - **选择语言**：最终用户垃圾邮件通知已根据收件人的语言设置进行本地化。 您可以为"显示名称"和"免责声明"值指定不同语言的 **自定义** 文本。

     至少从第一种语言框中选择一种语言， **然后单击添加**。 可以通过单击每种语言后的" **添加** "来选择多种语言。 部分语言框显示你选择的所有语言：

     ![隔离策略的全局隔离通知设置中第二种语言框中选定的语言](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **使用我的公司徽标**：选择此选项可替换最终用户垃圾邮件通知顶部使用的默认 Microsoft 徽标。 在这样做之前，你需要按照自定义组织的自定义Microsoft 365[主题](../../admin/setup/customize-your-organization-theme.md)中的说明上载自定义徽标。

     以下屏幕截图显示了最终用户垃圾邮件通知中的自定义徽标：

     ![最终用户垃圾邮件通知中的自定义徽标](../../media/quarantine-tags-esn-customization-logo.png)

## <a name="view-quarantine-policies-in-the-microsoft-365-defender-portal"></a>在门户中查看隔离Microsoft 365 Defender策略

1. 在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**

2. "**隔离策略**"页按名称和上次更新日期 **显示策略** 列表。

3. 若要查看内置或自定义隔离策略的设置，请通过单击名称从列表中选择隔离策略。

4. 若要查看全局设置，请单击" **全局设置"**

### <a name="view-quarantine-policies-in-powershell"></a>在 PowerShell 中查看隔离策略

如果更希望使用 PowerShell 查看隔离策略，请执行以下步骤之一：

- 若要查看所有内置或自定义策略的摘要列表，请运行以下命令：

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- 若要查看内置或自定义隔离策略的设置，请将 替换为隔离策略的名称，然后 \<QuarantinePolicyName\> 运行以下命令：

  ```powershell
  Get-QuarantineTag -Identity "<QuarantinePolicyName>"
  ```

- 若要查看全局设置，请运行以下命令：

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](/powershell/module/exchange/get-hostedcontentfilterpolicy)。

## <a name="modify-quarantine-policies-in-the-microsoft-365-defender-portal"></a>修改 Microsoft 365 Defender 门户中的隔离策略

1. 在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**

2. 在" **隔离策略"** 页上，通过单击名称选择策略。

3. 选择该策略后，单击出现的"编辑 ![ 策略"图标 ](../../media/m365-cc-sc-edit-icon.png) "编辑策略图标"。

4. 打开 **的编辑** 策略向导几乎与"新建策略"向导相同，如本文前面在 Microsoft 365 Defender [门户](#step-1-create-quarantine-policies-in-the-microsoft-365-defender-portal)创建隔离策略部分所述。

   主要区别在于：无法重命名现有策略。

5. 完成策略修改后，转到摘要页，**然后单击提交**。 

### <a name="modify-quarantine-policies-in-powershell"></a>在 PowerShell 中修改隔离策略

如果您更希望使用 PowerShell 修改自定义隔离策略，请将 替换为隔离策略 \<QuarantinePolicyName\> 的名称，并使用以下语法：

```powershell
Set-QuarantineTag -Identity "<QuarantinePolicyName>" [Settings]
```

可用的设置与本文前面介绍的创建隔离策略的设置相同。

有关语法和参数的详细信息，请参阅 [Set-QuarantineTag](/powershell/module/exchange/set-quarantinetag)。

## <a name="remove-quarantine-policies-in-the-microsoft-365-defender-portal"></a>删除 Microsoft 365 Defender 门户中的隔离策略

**注意**:

- 无法删除内置隔离策略。
- 在删除自定义隔离策略之前，请验证该策略是否未使用。 例如，在 PowerShell 中运行以下命令：

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  如果使用隔离策略， [请替换已分配的隔离策略](#step-2-assign-a-quarantine-policy-to-supported-features) ，然后再删除它。

1. 在 Microsoft 365 Defender 门户中，转到"电子邮件&协作威胁策略"部分"**隔离** 策略"， \>  \>  \> 然后选择"隔离 **策略"。**

2. 在" **隔离策略** "页上，单击名称，选择要删除的自定义隔离策略。

3. 选择该策略后，单击出现的"删除策略 ![ "图标 ](../../media/m365-cc-sc-delete-icon.png) **"** 删除策略图标"。

4. 单击 **出现的** 确认对话框中的"删除策略"。

### <a name="remove-quarantine-policies-in-powershell"></a>在 PowerShell 中删除隔离策略

如果你希望使用 PowerShell 删除自定义隔离策略，请将 替换为隔离策略的名称，然后 \<QuarantinePolicyName\> 运行以下命令：

```powershell
Remove-QuarantineTag -Identity "<QuarantinePolicyName>"
```

有关语法和参数的详细信息，请参阅 [Remove-QuarantineTag](/powershell/module/exchange/remove-quarantinetag)。

## <a name="quarantine-policy-permission-details"></a>隔离策略权限详细信息

以下各节介绍预设权限组和个人权限在隔离邮件的详细信息和最终用户垃圾邮件通知中的影响。

### <a name="preset-permissions-groups"></a>预设权限组

本文开头的表中列出了预设权限组中包含的单个权限。

#### <a name="no-access"></a>无访问权限

如果隔离策略将"无访问权限" (没有权限) ，则用户仍获得一些基线功能：

- **隔离邮件详细信息****："查看邮件头**"按钮始终可用。

  ![隔离策略授予用户无访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **最终用户垃圾邮件通知**： **将用户** 发送到隔离邮件的"审阅"按钮始终可用。

  ![如果隔离策略授予用户无访问权限，最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>受限访问

如果隔离策略分配 **"受限"** 访问权限，则用户会获得以下功能：

- **隔离邮件详细信息**：以下按钮可用：
  - **请求释放**
  - **查看邮件头**
  - **预览邮件**
  - **阻止发件人**
  - **从隔离区中删除**

  ![隔离策略授予用户受限访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **最终用户垃圾邮件通知**：以下按钮可用：
  - **阻止发件人**
  - **审阅**

  ![如果隔离策略授予用户受限访问权限，最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>完全访问权限

如果隔离策略 **将"完全** 访问权限" (所有可用) ，则用户会获得以下功能：

- **隔离邮件详细信息**：以下按钮可用：
  - **释放邮件**
  - **查看邮件头**
  - **预览邮件**
  - **阻止发件人**
  - **允许发件人**
  - **从隔离区中删除**

  ![隔离策略授予用户完全访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **最终用户垃圾邮件通知**：以下按钮可用：
  - **阻止发件人**
  - **发布**
  - **审阅**

  ![如果隔离策略授予用户完全访问权限，最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>个人权限

> [!NOTE]
> 请记住，用户始终获取"无法访问"部分 [中描述的](#no-access) 按钮。 这些按钮不包含在单个权限说明中。

#### <a name="allow-sender-permission"></a>允许发件人权限

_PermissionToAllowSender_ ("允许发件人"权限) 控制对按钮的访问，该按钮允许用户方便地将隔离的邮件发件人添加到其"保险箱发件人"列表中。 

- **隔离邮件详细信息**：
  - **启用发件人** 权限：" **允许发件人"** 按钮可用。
  - **禁用发件人** 权限：" **允许发件人"** 按钮不可用。

- **最终用户垃圾邮件通知：** 不起作用。

有关发件人列表保险箱，请参阅防止阻止受信任发件人和使用 Exchange Online [](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) PowerShell 配置邮箱[的安全列表集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。

#### <a name="block-sender-permission"></a>阻止发件人权限

_PermissionToBlockSender_ (阻止发件人) 控制对按钮的访问权限，该按钮允许用户便捷地将隔离的邮件发件人添加到其阻止的发件人列表。 

- **隔离邮件详细信息**：
  - **阻止发件人** 权限已启用 **："阻止发件人"** 按钮可用。
  - **阻止发件人** 权限已禁用：阻止 **发件人** 按钮不可用。

- **最终用户垃圾邮件通知**：
  - **阻止发件人** 权限已禁用：阻止 **发件人** 按钮不可用。
  - **阻止发件人** 权限已启用 **："阻止发件人"** 按钮可用。

有关阻止的发件人列表的信息，请参阅阻止来自某人的邮件[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)和使用 Exchange Online PowerShell 配置邮箱[的安全列表集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。

#### <a name="delete-permission"></a>删除权限

_PermissionToDelete (PermissionToDelete_) 控制用户能否删除其邮件 (用户是收件人的邮件，) 隔离。 

- **隔离邮件详细信息**：
  - **启用** 删除权限：" **从隔离区删除"** 按钮可用。
  - **删除** 权限已禁用：" **从隔离区删除"** 按钮不可用。

- **最终用户垃圾邮件通知：** 不起作用。

#### <a name="preview-permission"></a>预览权限

_PermissionToPreview_ (预览) 控制用户在隔离中预览邮件的能力。 

- **隔离邮件详细信息**：
  - **预览** 权限已启用： **预览邮件** 按钮可用。
  - **预览** 权限已禁用： **预览邮件** 按钮不可用。

- **最终用户垃圾邮件通知：** 不起作用。

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>允许收件人解除邮件隔离权限

_PermissionToRelease_) 中的"允许收件人从隔离中释放邮件"权限 (控制用户直接释放隔离邮件的能力，而无需经过管理员批准。 

- **隔离邮件详细信息**：
  - 已启用权限 **："释放邮件"** 按钮可用。
  - 权限已禁用 **："释放邮件** "按钮不可用。

- **最终用户垃圾邮件通知**：
  - 已启用权限 **："释放** "按钮可用。
  - 权限已禁用 **："释放** "按钮不可用。

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>允许收件人请求从隔离权限中释放邮件

允许 **收件人** 请求从隔离中释放的邮件权限 (_PermissionToRequestRelease_) 控制用户请求释放其隔离邮件的能力。  邮件仅在管理员批准请求后释放。

- **隔离邮件详细信息**：
  - 已启用权限 **："请求释放** "按钮可用。
  - 权限已禁用 **："请求释放** "按钮不可用。

- **最终用户垃圾邮件通知**：" **释放** "按钮不可用。
