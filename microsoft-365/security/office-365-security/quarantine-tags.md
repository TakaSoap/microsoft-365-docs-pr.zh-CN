---
title: 隔离标记
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
description: 管理员可以了解如何使用隔离标记来控制用户可以对隔离邮件执行哪些操作。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 207f22c9acaa183e195f5a2ee33be65cdf4991dd
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50289409"
---
# <a name="quarantine-tags"></a>隔离标记

> [!NOTE]
> 本文中介绍的功能目前处于预览阶段，不向所有人提供，并且可能会更改。

Exchange Online Protection (EOP) 中的隔离标记允许管理员根据邮件如何到达隔离区来控制用户能够对隔离邮件执行哪些操作。

EOP 在传统上允许或阻止隔离邮件和最终用户垃圾邮件通知中的某些[级别的交互](use-spam-notifications-to-release-and-report-quarantined-messages.md)。 [](find-and-release-quarantined-messages-as-a-user.md) 例如，最终用户可以查看并释放被反垃圾邮件筛选隔离为垃圾邮件或批量邮件的邮件，但他们无法查看或释放被隔离为高可信度网络钓鱼的邮件。

对于 [受支持的保护](#step-2-assign-a-quarantine-tag-to-supported-features)功能，隔离标记指定允许用户在最终用户垃圾邮件通知邮件和隔离邮件中执行哪些操作 (用户是收件人收件人的邮件中) 。 自动分配默认隔离标记，以对隔离邮件的最终用户强制实施历史功能。 或者，您可以创建和分配自定义隔离标记，以允许或阻止最终用户对隔离邮件执行特定操作。

各个权限组合到以下预设权限组中：

- 禁止访问
- 受限访问
- 完全访问权限

下表介绍了可用的单个权限以及预设权限组中包含或不包含哪些权限：

|权限|禁止访问|受限访问|完全访问权限|
|---|:---:|:---:|:---:|
|**允许发件人 (** _PermissionToAllowSender)_|||![复选标记](../../media/checkmark.png)|
|**阻止发件人 (** _PermissionToBlockSender)_||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|**删除** (_PermissionToDelete_) ||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|**预览** (_PermissionToPreview)_||![复选标记](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|
|**允许收件人从隔离邮箱中释放** (_PermissionToRelease_) |||![复选标记](../../media/checkmark.png)|
|**允许收件人请求从隔离邮箱** 释放 (_PermissionToRequestRelease_) ||![复选标记](../../media/checkmark.png)||
|

如果不喜欢预设权限组中的默认权限，可以在创建自定义隔离标记或修改自定义隔离标记时使用自定义权限。 有关每个权限执行哪些操作的详细信息，请参阅本文稍后介绍的 ["隔离标记](#quarantine-tag-permission-details) 权限详细信息"部分。

在安全与合规中心或 PowerShell &为具有 Exchange Online 邮箱的 Microsoft 365 (Exchange Online PowerShell 创建和分配隔离标记;EOP 组织中没有 Exchange Online 邮箱的独立 EOP PowerShell) 。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到" **隔离标记"** 页，请打开 <https://protection.office.com/quarantineTags> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 若要查看、创建、修改或删除隔离标记，你需要是安全与合规中心内组织管理或安全管理员&[的成员](permissions-in-the-security-and-compliance-center.md)。 

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>步骤 1：在安全与合规中心&隔离标记

1. 在安全&，转到 **"威胁管理** 策略 \> "，然后选择"**隔离标记"。**

2. 在"**隔离标记"** 页上，选择 **"添加自定义标记"。**

3. 将 **打开"新建标记** "向导。 在 **"标记名称** "页上，在"标记名称"字段中输入简短但 **唯一** 的名称。 你需要在即将推出的步骤中按名称标识和选择标记。 完成后，单击“下一步”。

4. 在 **"收件人邮件访问"** 页上，选择下列值之一：
   - **禁止访问**
   - **受限访问**
   - **完全访问权限**

   本文前面介绍了这些权限组中包含的单个权限。

   若要指定自定义权限，请选择"在高级 (**设置**) 并配置以下设置：

     - **选择释放操作首选项**：选择下列值之一：
       - **无释放操作**：这是默认值。
       - **允许收件人从隔离区释放邮件**
       - **允许收件人请求从隔离区释放邮件**

     - **选择收件人对** 隔离邮件可以执行的其他操作：选择下列一些、全部或无一个值：
       - **删除**
       - **预览**
       - **允许发件人**
       - **阻止发件人**

   本文稍后的"隔离标记权限详细信息"部分介绍了这些权限及其对隔离邮件和最终用户垃圾邮件通知[](#quarantine-tag-permission-details)的影响。

   完成后，单击“下一步”。

5. 在 **出现的"摘要"** 页上，查看设置。 可以单击 **每个设置** 上的"编辑"来修改它。

   完成后，单击"提交 **"。**

6. 在 **出现的** 确认页面上单击"完成"。

现在，您已准备好将隔离标记分配给隔离功能，如步骤 [2 部分](#step-2-assign-a-quarantine-tag-to-supported-features) 中所述。

### <a name="create-quarantine-tags-in-powershell"></a>在 PowerShell 中创建隔离标记

如果你希望使用 PowerShell 创建隔离标记，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 并使用 **New-QuarantineTag** cmdlet。 有两种不同的方法可供选择：

- 使用 _EndUserQuarantinePermissionsValue_ 参数。
- 使用 _EndUserQuarantinePermissions_ 参数。

以下各节介绍了这些方法。

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>使用 EndUserQuarantinePermissionsValue 参数

若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离标记，请使用以下语法：

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

_EndUserQuarantinePermissionsValue_ 参数使用从二进制值转换的十进制值。 二进制值以特定顺序对应于可用的最终用户隔离权限。 对于每个权限，值 1 等于 True，值 0 等于 False。

下表介绍了预设权限组中每个权限的必需顺序和值：

****

|权限|禁止访问|受限访问|完全访问权限|
|---|:---:|:---:|:---:|
|PermissionToAllowSender|0|0|1 |
|PermissionToBlockSender|0|1 |1 |
|PermissionToDelete|0|1 |1 |
|PermissionToDownload<sup>\*</sup>|0|0|0|
|PermissionToPreview|0|1 |1 |
|PermissionToRelease<sup>\*\*</sup>|0|0|1 |
|PermissionToRequestRelease<sup>\*\*</sup>|0|1 |0|
|PermissionToViewHeader<sup>\*</sup>|0|0|0|
|二进制值|00000000|01101010|11101100|
|要使用的十进制值|0|106|236|

<sup>\*</sup> 目前，此值始终为 0。 对于 PermissionToViewHeader，值 0 不会隐藏隔离邮件的详细信息中的"查看邮件头"按钮 (该按钮始终可用) 。

<sup>\*\*</sup> 不要同时将这两个值都设置为 1。 将一个设置为 1，将另一个设置为 0，或同时设置为 0。

本示例创建一个新的隔离标记名称 NoAccess，以分配上表中所述的"无访问权限"权限。

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

对于受限访问权限，请使用值 106。 对于完全访问权限，请使用值 236。

对于自定义权限，请使用上表获取与所需的权限对应的二进制值。 将二进制值转换为十进制值，并使用 _EndUserQuarantinePermissionsValue_ 参数的十进制值。

有关语法和参数的详细信息，请参阅 [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>使用 EndUserQuarantinePermissions 参数

若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离标记，请执行以下步骤：

A. 使用 **New-QuarantinePermissions** cmdlet 将隔离权限对象存储在变量中。

<p>

B. 在 **New-QuarantineTag** 命令中将变量用作 _EndUserQuarantinePermissions_ 值。

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>步骤 A：在变量中存储隔离权限对象

使用以下语法：

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

任何未使用的参数的默认值都是，因此只需使用要设置值 `$false` 的参数 `$true` 。

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

对于自定义权限，不要同时将 _PermissionToRelease_ 和 _PermissionToRequestRelease_ 参数设置为 `$true` 。 将一个 `$true` 设置为另一个，将另一个保留 `$false` 为 ，或同时保留为 `$false` 。

您还可以在创建后、使用 **Set-QuarantinePermissions** cmdlet 使用之前修改现有权限对象变量。

有关语法和参数的详细信息，请参阅[New-QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions)和[Set-QuarantinePermissions。](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>步骤 B：在命令中New-QuarantineTag变量

在变量中创建和存储权限对象后，请使用以下 **New-QuarantineTag** 命令 _中的 EndUserQuarantinePermission_ 参数值的变量：

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

此示例使用上一步中介绍和创建的权限对象创建名为 LimitedAccess 的新 `$LimitedAccess` 隔离标记。

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

有关语法和参数的详细信息，请参阅 [New-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>步骤 2：向支持的功能分配隔离标记

在 _可自动_ 隔离邮件或文件的受支持保护 (或作为可配置操作) ，您可以为可用的隔离操作分配隔离标记。 下表介绍了隔离邮件的功能和隔离标记的可用性：

****

|功能|支持隔离标记？|使用的默认隔离标记|
|---|:---:|---|
|[反垃圾邮件策略](configure-your-spam-filter-policies.md)： <ul><li>**Spam** (_SpamAction_) </li><li>**高可信度垃圾邮件 (** _HighConfidenceSpamAction_) </li><li>**网络钓鱼电子邮件 (** _PhishSpamAction_) </li><li>**高可信度网络钓鱼电子邮件 (** _HighConfidencePhishAction_) </li><li>**BulkSpamAction** (_BulkSpamAction_) </li></ul>|是|<ul><li>DefaultSpamTag (完全访问权限) </li><li>DefaultHighConfSpamTag (完全) </li><li>DefaultPhishTag (完全访问权限) </li><li>DefaultHighConfPhishTag (无法访问) </li><li>DefaultBulkTag (完全访问权限) </li></ul>
|防钓鱼策略： <ul><li>[](set-up-anti-phishing-policies.md#spoof-settings) _AuthenticationFailAction (欺骗智能_) </li><li>[模拟保护](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)：<sup>\*</sup> <ul><li>**如果电子邮件是由模拟用户 (** _TargetedUserProtectionAction_) </li><li>**如果电子邮件是由模拟** 域发送 (_TargetedDomainProtectionAction_) </li><li>**邮箱智能** \>**如果电子邮件是由模拟用户 (** _MailboxIntelligenceProtectionAction_) </li></ul></li></ul></ul>|否|不适用|
|[反恶意软件策略](configure-anti-malware-policies.md)：始终隔离所有检测到的邮件。|否|不适用|
|[用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件](atp-for-spo-odb-and-teams.md)|否|不适用|
|[邮件流规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (操作) 传输规则：将邮件发送到托管隔离邮箱 (_隔离_) 。 |否|不适用|
|

<sup>\*</sup> 模拟保护设置仅在 Microsoft Defender for Office 365 中的防钓鱼策略中可用。

如果您对默认隔离标记提供的最终用户权限满意，则无需执行任何操作。 如果要自定义最终用户功能 (最终用户垃圾邮件) 或隔离邮件详细信息中的可用按钮，您可以分配自定义隔离标记。

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>在安全与合规中心中的反垃圾邮件策略中&标记

有关创建和修改反垃圾邮件策略的完整说明，请参阅[EOP 中的"配置反垃圾邮件策略"。](configure-your-spam-filter-policies.md)

1. 在安全&合规中心，转到 **"威胁管理** 策略 \>  \> "，然后选择 **"反垃圾邮件"。** 或者，打开 <https://protection.office.com/antispam> 。

2. 查找并选择要编辑的现有反垃圾邮件策略，或创建新的反垃圾邮件策略。

3. 在策略详细信息飞出中，展开" **垃圾邮件和批量操作"** 部分。

4. 如果选择了"隔离邮件 **"作为可用** 垃圾邮件筛选裁定的操作，则"应用隔离策略标记"框可供你选择该裁定的隔离标记。

   **注意**：创建新策略时，垃圾邮件筛选裁定的空白隔离标记值指示该裁定的默认隔离标记已使用。 稍后编辑策略时，空白值将替换为上表中所述的实际默认隔离标记名称。

   ![反垃圾邮件策略中的隔离标记选择](../../media/quarantine-tags-in-anti-spam-policies.png)

5. 完成时，请单击“保存”。

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>在 PowerShell 中的反垃圾邮件策略中分配隔离标记

如果你希望使用 PowerShell 在反垃圾邮件策略中分配隔离标记，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell，并使用以下语法：

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**注意**：

- _HighConfidencePhishAction_ 参数的默认值为"隔离"，因此无需设置新反垃圾邮件策略中高可信度网络钓鱼检测的隔离操作。 对于新的或现有的反垃圾邮件策略中的所有其他垃圾邮件筛选裁定，隔离标记仅在操作值为"隔离"时有效。 若要查看现有反垃圾邮件策略中的操作值，请运行以下命令：

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  有关默认操作值以及 Standard 和 Strict 的建议操作值的信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

- 没有相应隔离标记参数的垃圾邮件筛选裁定意味着该裁定[](#step-2-assign-a-quarantine-tag-to-supported-features)的默认隔离标记已使用。

  如果要更改隔离邮件的默认最终用户功能，只需将默认隔离标记替换为自定义隔离标记。

- PowerShell 中的新反垃圾邮件策略需要使用 **New-HostedContentFilterPolicy** cmdlet 和新的垃圾邮件筛选器规则 (收件人筛选器) 使用 **New-HostedContentFilterRule** cmdlet 使用垃圾邮件筛选器策略 (设置) 。 有关说明，请参阅 [使用 PowerShell 创建反垃圾邮件策略](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。

此示例创建一个名为 Research Department 的新垃圾邮件筛选器策略，该策略具有以下设置：

- 所有垃圾邮件筛选裁定的操作都设置为"隔离"。
- 分配"无访问权限"的名为 NoAccess的自定义隔离标记将替换默认情况下尚未分配 **"** 无访问权限"的任何默认隔离标记。

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)。

此示例修改名为 Human Resources 的现有垃圾邮件筛选器策略。 垃圾邮件隔离裁定的操作设置为"隔离"，并分配名为 NoAccess 的自定义隔离标记。

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)。

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>在安全与合规中心&全局隔离通知设置

隔离标记的全局设置允许您自定义发送给已隔离邮件收件人的最终用户垃圾邮件通知。 有关这些通知详细信息，请参阅 [最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。

1. 在安全&，转到 **"威胁管理** 策略 \> "，然后选择"**隔离标记"。**

2. 在"**隔离标记"** 页上，选择 **"全局设置"。**

3. 在打开 **的** "隔离通知设置"飞出中，配置以下部分或所有设置：

   - **使用我的公司徽标**：选择此选项可替换最终用户垃圾邮件通知顶部使用的默认 Microsoft 徽标。 在这样做之前，你需要按照 [自定义组织的 Microsoft 365](../../admin/setup/customize-your-organization-theme.md) 主题中的说明上载自定义徽标。

     以下屏幕截图显示了最终用户垃圾邮件通知中的自定义徽标：

     ![最终用户垃圾邮件通知中的自定义徽标](../../media/quarantine-tags-esn-customization-logo.png)

   - **选择语言**：最终用户垃圾邮件通知已基于收件人的语言设置进行本地化。 您可以为显示名称和免责声明值指定不同语言的 **自定义** 文本。

     从第一个语言框中至少选择一种语言，然后单击"**添加"。** 可以通过单击每种语言后的"添加 **"来选择** 多种语言。 节语言框显示已选择的所有语言：

     ![隔离标记的全局隔离通知设置中第二种语言框中选定的语言](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **显示名称**：自定义显示名称垃圾邮件通知中使用的发件人地址。

     对于已添加的每种语言，请选择第二种语言框中的语言 (不要单击 X) 请在"显示名称"框中输入您想要 **的文本值。**

     以下屏幕截图显示了最终用户显示名称中的自定义邮件：

     ![自定义发件人显示名称最终用户垃圾邮件通知中](../../media/quarantine-tags-esn-customization-display-name.png)

   - **免责声明**：将自定义免责声明添加到最终用户垃圾邮件通知的底部。 本地化文本（ **来自组织的免责声明）：** 始终先包含，后跟指定文本。

     对于已添加的每种语言，请选择第二种语言框中的语言 (不要单击 X) 请在"免责声明"框中输入 **您想要的文本值** 。

     以下屏幕截图显示了最终用户垃圾邮件通知中的自定义免责声明：

     ![最终用户垃圾邮件通知底部的自定义免责声明](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>在安全与合规中心&隔离标记

1. 在安全&，转到 **"威胁管理** 策略 \> "，然后选择"**隔离标记"。**

- 若要查看内置或自定义隔离标记的设置，请从列表中选择隔离标记 (不要选中复选框) 。

- 若要查看全局设置，请选择 **"全局设置"**

### <a name="view-quarantine-tags-in-powershell"></a>在 PowerShell 中查看隔离标记

如果你希望使用 PowerShell 查看隔离标记，请执行下列任一步骤：

- 若要查看所有内置或自定义标记的摘要列表，请运行以下命令：

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- 若要查看内置或自定义隔离标记的设置，请替换为隔离标记的名称， \<TagName\> 然后运行以下命令：

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- 若要查看全局设置，请运行以下命令：

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)。

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>在安全与合规中心&隔离标记

**注意**：

- 无法删除内置隔离标记。

- 在删除自定义隔离标记之前，请验证该标记是否未使用。 例如，在 PowerShell 中运行以下命令：

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  如果使用隔离标记， [请替换分配的隔离](#step-2-assign-a-quarantine-tag-to-supported-features) 标记，然后再将其删除。

1. 在安全&，转到 **"威胁管理** 策略 \> "，然后选择"**隔离标记"。**

2. 在 **"隔离标记"** 页上，选择要删除的自定义隔离标记，然后单击"删除 **"标记**。

3. 单击 **出现的** 确认对话框中的"删除标记"。

### <a name="remove-quarantine-tags-in-powershell"></a>在 PowerShell 中删除隔离标记

如果希望使用 PowerShell 删除自定义隔离标记，请替换为隔离标记的名称， \<TagName\> 然后运行以下命令：

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

有关语法和参数的详细信息，请参阅 [Remove-QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)。

## <a name="quarantine-tag-permission-details"></a>隔离标记权限详细信息

以下各节介绍预设权限组和单个权限在隔离邮件的详细信息和最终用户垃圾邮件通知中的影响。

### <a name="preset-permissions-groups"></a>预设权限组

本文开头的表中列出了预设权限组中包含的单个权限。

#### <a name="no-access"></a>禁止访问

如果隔离标记将"无访问权限" (没有权限) ，则用户仍获得一些基线功能：

- **隔离邮件详细信息****："查看邮件头**"按钮始终可用。

  ![隔离标记向用户授予"无访问权限"时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **最终用户垃圾邮件通知**：将用户发送到隔离邮件的"审阅"按钮始终可用。

  ![如果隔离标记授予用户无访问权限，则最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>受限访问

如果隔离标记分配 **受限** 访问权限，则用户获得以下功能：

- **隔离邮件详细信息**：以下按钮可用：
  - **请求释放**
  - **查看邮件头**
  - **预览邮件**
  - **阻止发件人**
  - **从隔离区删除**

  ![隔离标记授予用户受限访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **最终用户垃圾邮件通知**：以下按钮可用：
  - **阻止发件人**
  - 审阅

  ![如果隔离标记授予用户受限访问权限，则最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>完全访问权限

如果隔离标记分配了所有可用 (的完全访问权限) ，则用户获得以下功能：

- **隔离邮件详细信息**：以下按钮可用：
  - **释放邮件**
  - **查看邮件头**
  - **预览邮件**
  - **阻止发件人**
  - **允许发件人**
  - **从隔离区删除**

  ![隔离标记授予用户完全访问权限时隔离邮件详细信息中的可用按钮](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **最终用户垃圾邮件通知**：以下按钮可用：
  - **阻止发件人**
  - **发布**
  - 审阅

  ![如果隔离标记授予用户完全访问权限，则最终用户垃圾邮件通知中的可用按钮](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>个人权限

> [!NOTE]
> 请记住，用户始终获取"无访问"部分 [中描述的](#no-access) 按钮。 这些按钮不包含在单个权限说明中。

#### <a name="allow-sender-permission"></a>允许发件人权限

_PermissionToAllowSender_ ("允许发件人"权限) 控制对按钮的访问权限，该按钮允许用户方便地将隔离的邮件发件人添加到其安全发件人列表。 

- **隔离邮件详细信息**：
  - **启用发件人** 权限：" **允许发件人"** 按钮可用。
  - **禁用发件人** 权限：" **允许发件人"** 按钮不可用。

- **最终用户垃圾邮件通知**：不起作用。

有关安全发件人列表详细信息，请参阅"阻止受信任[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666)发件人"，并使用[Exchange Online PowerShell](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)在邮箱上配置安全列表集合。

#### <a name="block-sender-permission"></a>阻止发件人权限

_PermissionToBlockSender_ (阻止发件人权限) 控制对按钮的访问权限，该按钮允许用户方便地将隔离的邮件发件人添加到其阻止的发件人列表。 

- **隔离邮件详细信息**：
  - **启用阻止发件人** 权限 **："阻止发件人"** 按钮可用。
  - **阻止发件人** 权限已禁用：" **阻止发件人"** 按钮不可用。

- **最终用户垃圾邮件通知**：
  - **阻止发件人** 权限已禁用：" **阻止发件人"** 按钮不可用。
  - **启用阻止发件人** 权限 **："阻止发件人"** 按钮可用。

有关阻止发件人列表的信息，请参阅"阻止来自某人的邮件[](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667)"，并使用 Exchange Online PowerShell 在邮箱上配置[安全列表集合](configure-junk-email-settings-on-exo-mailboxes.md#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。

#### <a name="delete-permission"></a>删除权限

_PermissionToDelete_ (权限) 控制用户删除其邮件 (用户是隔离收件人的邮件) 邮件。 

- **隔离邮件详细信息**：
  - **启用** 删除权限：" **从隔离区删除"** 按钮可用。
  - **禁用** 删除权限：" **从隔离中删除"** 按钮不可用。

- **最终用户垃圾邮件通知**：不起作用。

#### <a name="preview-permission"></a>预览权限

_PermissionToPreview_ (预览权限) 控制用户在隔离中预览邮件的能力。 

- **隔离邮件详细信息**：
  - **启用** 预览权限： **预览邮件** 按钮可用。
  - **预览** 权限已禁用： **预览邮件** 按钮不可用。

- **最终用户垃圾邮件通知**：不起作用。

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>允许收件人从隔离权限中释放邮件

允许 **收件人** 从隔离权限 (_PermissionToRelease_) 中释放邮件控制用户直接释放其隔离邮件的能力，而无需经过管理员批准。

- **隔离邮件详细信息**：
  - 已启用权限 **："释放邮件"** 按钮可用。
  - 权限已禁用 **："释放邮件** "按钮不可用。

- **最终用户垃圾邮件通知**：
  - 已启用权限 **："释放"** 按钮可用。
  - 权限已禁用：" **释放** "按钮不可用。

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>允许收件人请求从隔离权限中释放邮件

允许 **收件人** 请求从隔离权限 (_PermissionToRequestRelease_) 释放邮件控制用户请求释放其隔离邮件的能力。  邮件仅在管理员批准请求后释放。

- **隔离邮件详细信息**：
  - 已启用权限 **："请求释放** "按钮可用。
  - 权限已禁用 **："请求释放** "按钮不可用。

- **最终用户垃圾邮件通知**：" **释放** "按钮不可用。
