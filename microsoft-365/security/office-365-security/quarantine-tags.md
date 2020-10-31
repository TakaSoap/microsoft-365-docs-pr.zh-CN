---
title: 隔离标记
ms.author: chrisda
author: chrisda
manager: dansimp
ms.reviewer: ''
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: ''
ms.collection:
- M365-security-compliance
ROBOTS: NOINDEX
description: 管理员可以了解如何使用隔离标记来控制用户能够对其隔离邮件执行的操作。
ms.openlocfilehash: 89f03795d8f12b3df3e5090648c5a6c8b64c322a
ms.sourcegitcommit: 676479f1e65492b44c4d0316a765f55ae9fae374
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/31/2020
ms.locfileid: "48819736"
---
# <a name="quarantine-tags"></a>隔离标记

> [!NOTE]
> 本文中所述的功能目前处于预览阶段，不可用于所有人，并且可能会发生更改。

Exchange Online Protection (EOP 中的隔离标记) 允许管理员根据邮件到达隔离的方式来控制哪些用户能够对隔离邮件执行的操作。

EOP 传统上允许或阻止了 [隔离](find-and-release-quarantined-messages-as-a-user.md) 和 [最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)中的邮件的特定级别的交互。 例如，最终用户可以查看和释放反垃圾邮件筛选隔离为垃圾邮件或批量的邮件，但不能查看或释放被隔离为高可信度网络钓鱼的邮件。

对于 [受支持的保护功能](#step-2-assign-a-quarantine-tag-to-supported-features)，隔离标记指定了允许哪些用户在最终用户的垃圾邮件通知邮件以及隔离邮件的隔离邮件中执行的操作 (用户是其收件人) 的邮件。 将自动分配默认隔离标记，以针对隔离邮件强制实施最终用户的历史功能。 或者，您可以创建自定义隔离标记并将其分配给最终用户，以允许或阻止最终用户对隔离邮件执行特定操作。

各个权限组合到以下预设权限组中：

- 禁止访问
- 受限访问
- 完全访问

下表介绍了可用的个人权限以及预置权限组中包括或未包括的内容：

|权限|禁止访问|受限访问|完全访问|
|---|:---:|:---:|:---:|
|**允许发件人** ( _PermissionToAllowSender_ ) |||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**阻止发件人** ( _PermissionToBlockSender_ ) ||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**删除** ( _PermissionToDelete_ ) ||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
| ( _PermissionToPreview_ ) **预览**||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**允许收件人释放来自隔离** ( _PermissionToRelease_ 的邮件) |||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)|
|**允许收件人请求从隔离区发布邮件** ( _PermissionToRequestRelease_ ) ||![复选标记](../../media/f3b4c351-17d9-42d9-8540-e48e01779b31.png)||
|

如果您不喜欢预设权限组中的默认权限，则可以在创建或修改自定义隔离标记时使用自定义权限。 有关每个权限执行的操作的详细信息，请参阅本文后面的 [隔离标记权限详细信息](#quarantine-tag-permission-details) 部分。

在使用 Exchange Online 邮箱的 Microsoft 365 组织的 "安全 & 合规中心" 或 "PowerShell (Exchange Online PowerShell" 中创建和分配隔离标记;EOP 组织中的独立 EOP PowerShell，不) Exchange Online 邮箱。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 " **隔离标记** " 页，请打开 <https://protection.office.com/quarantineTags> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 若要查看、创建、修改或删除隔离标记，您必须是下列角色组之一的成员：
  - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“ **组织管理** ”或“ **安全管理员** ”。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“ **组织管理** ”或“ **清洁管理** ”。

## <a name="step-1-create-quarantine-tags-in-the-security--compliance-center"></a>步骤1：在安全 & 合规中心中创建隔离标记

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** "，然后选择 " **隔离标记** "。

2. 在 " **隔离标记** " 页上，选择 " **添加自定义标记** "。

3. 将打开 " **新建标记** " 向导。 在 " **标记名称** " 页上，在 " **标记名称** " 字段中输入一个简短但唯一的名称。 在后面的步骤中，您需要确定并按名称选择标记。 完成后，单击“下一步”  。

4. 在 " **收件人邮件访问** " 页上，选择下列值之一：
   - **禁止访问**
   - **受限访问**
   - **完全访问**

   本文前面将介绍这些权限组中包含的各个权限。

   若要指定自定义权限，请选择 " **设置特定访问权限 (高级)** "，并配置以下设置：

     - **选择 "释放操作" 首选项** ：选择下列值之一：
       - **无发布操作** ：这是默认值。
       - **允许收件人从隔离区中释放邮件**
       - **允许收件人请求从隔离区中释放邮件**

     - **选择 "其他操作收件人可对隔离邮件执行操作** "：选择以下任何值：
       - **删除**
       - **预览**
       - **允许发件人**
       - **阻止发件人**

   这些权限以及它们对隔离邮件和最终用户垃圾邮件通知中的影响将在本文后面的 [隔离标记权限详细信息](#quarantine-tag-permission-details) 部分中进行介绍。

   完成后，单击“下一步”  。

5. 在出现的 **摘要** 页上，查看您的设置。 您可以在每个设置上单击 " **编辑** " 以修改它。

   完成后，请单击 " **提交** "。

6. 在出现的确认页上单击 " **完成** "。

现在您已准备好将隔离标记分配给隔离功能，如 " [步骤 2](#step-2-assign-a-quarantine-tag-to-supported-features) " 一节中所述。

### <a name="create-quarantine-tags-in-powershell"></a>在 PowerShell 中创建隔离标记

如果您更愿意使用 PowerShell 创建隔离标记，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell，并使用 **QuarantineTag** cmdlet。 有两种不同的方法可供选择：

- 使用 _EndUserQuarantinePermissionsValue_ 参数。
- 使用 _EndUserQuarantinePermissions_ 参数。

以下各节介绍了这些方法。

#### <a name="use-the-enduserquarantinepermissionsvalue-parameter"></a>使用 EndUserQuarantinePermissionsValue 参数

若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离标记，请使用以下语法：

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissionsValue <0 to 236>
```

_EndUserQuarantinePermissionsValue_ 参数使用从二进制值转换而来的十进制值。 二进制值对应于可用的最终用户隔离权限，以特定顺序排列。 对于每个权限，值1等于 True，值0等于 False。

下表介绍了预置权限组中每个单独权限的必需顺序和值：

****

|权限|禁止访问|受限访问|完全访问|
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
|要使用的十进制值|0|106|236|

<sup>\*</sup> 目前，此值始终为0。 对于 PermissionToViewHeader，值0不会在隔离邮件的详细信息中隐藏 " **查看邮件标题** " 按钮 (该按钮始终) 可用。

<sup>\*\*</sup> 请勿将这两个值都设置为1。 将1设置为1，将另一个设置为0，或将两者都设置为0。

本示例创建一个新的隔离标记名称 NoAccess，该名称分配了上表中描述的 "无访问权限"。

```powershell
New-QuarantineTag -Name NoAccess -EndUserQuarantinePermissionsValue 0
```

对于受限制的访问权限，请使用值106。 若要获取完全访问权限，请使用值236。

对于自定义权限，请使用上表获取与所需权限对应的二进制值。 将二进制值转换为十进制值，并使用 _EndUserQuarantinePermissionsValue_ 参数的十进制值。

有关语法和参数的详细信息，请参阅 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。

#### <a name="use-the-enduserquarantinepermissions-parameter"></a>使用 EndUserQuarantinePermissions 参数

若要使用 _EndUserQuarantinePermissionsValue_ 参数创建隔离标记，请执行以下步骤：

A. 使用 **QuarantinePermissions** cmdlet 将隔离权限对象存储在变量中。
<br/>
B. 将变量用作 **QuarantineTag** 命令中的 _EndUserQuarantinePermissions_ 值。

##### <a name="step-a-store-a-quarantine-permissions-object-in-a-variable"></a>步骤 A：将隔离权限对象存储在变量中

使用以下语法：

```powershell
$<VariableName> = New-QuarantinePermissions [-PermissionToAllowSender <$true | $False>] [-PermissionToBlockSender <$true | $False>] [-PermissionToDelete <$true | $False>] [-PermissionToPreview <$true | $False>] [-PermissionToRelease <$true | $False>] [-PermissionToRequestRelease <$true | $False>]
```

任何未使用的参数的默认值为 `$false` ，因此您只需要使用要将值设置为的参数 `$true` 。

下面的示例展示了如何创建与预置权限组对应的权限对象：

- **无访问权限** ：

  ```powershell
  $NoAccess = New-QuarantinePermissions
  ```

- **受限访问** ：

  ```powershell
  $LimitedAccess = New-QuarantinePermissions -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRequestRelease $true
  ```

- **完全访问** ：

  ```powershell
  $FullAccess = New-QuarantinePermissions -PermissionToAllowSender $true -PermissionToBlockSender $true -PermissionToDelete $true -PermissionToPreview $true -PermissionToRelease $true
  ```

若要查看已设置的值，请将变量名称作为命令运行 (例如，运行命令 `$NoAccess`) 。

对于自定义权限，请勿将 _PermissionToRelease_ 和 _PermissionToRequestRelease_ 参数都设置为 `$true` 。 将一个设置为，将另一个设置为 `$true` `$false` ，或将两者都保留 `$false` 。

您还可以在创建现有的权限对象变量之后，在使用 **QuarantinePermissions** cmdlet 之前对其进行修改。

有关语法和参数的详细信息，请参阅 [QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/new-quarantinepermissions) 和 [QuarantinePermissions](https://docs.microsoft.com/powershell/module/exchange/set-quarantinepermissions)。

##### <a name="step-b-use-the-variable-in-the-new-quarantinetag-command"></a>步骤 B：在 New-QuarantineTag 命令中使用变量

在变量中创建并存储了权限对象后，在下面的 **QuarantineTag** 命令中使用 _EndUserQuarantinePermission_ 参数值的变量：

```powershell
New-QuarantineTag -Name "<UniqueName>" -EndUserQuarantinePermissions $<VariableName>
```

本示例使用 `$LimitedAccess` 在上一步中描述和创建的权限对象创建一个名为 LimitedAccess 的新的隔离标记。

```powershell
New-QuarantineTag -Name LimitedAccess -EndUserQuarantinePermissions $LimitedAccess
```

有关语法和参数的详细信息，请参阅 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/new-quarantinetag)。

## <a name="step-2-assign-a-quarantine-tag-to-supported-features"></a>步骤2：将隔离标记分配给支持的功能

在 (自动或作为可配置动作) 隔离邮件或文件的 _受支持_ 的保护功能中，可以为可用的隔离操作分配隔离标记。 下表介绍了隔离邮件的功能和隔离标记的可用性：

****

|功能|是否支持隔离标记？|使用的默认隔离标记|
|---|:---:|---|
|[反垃圾邮件策略](configure-your-spam-filter-policies.md)： <ul><li>**垃圾邮件** ( _SpamAction_ ) </li><li>**高可信度垃圾邮件** ( _HighConfidenceSpamAction_ ) </li><li>**网络钓鱼电子邮件** ( _PhishSpamAction_ ) </li><li>**高可信度网络钓鱼电子邮件** ( _HighConfidencePhishAction_ ) </li><li>**批量电子邮件** ( _BulkSpamAction_ ) </li></ul>|是|<ul><li>DefaultSpamTag (完全访问) </li><li>DefaultHighConfSpamTag (完全访问) </li><li>DefaultPhishTag (完全访问) </li><li>DefaultHighConfPhishTag (无访问权限) </li><li>DefaultBulkTag (完全访问) </li></ul>
|反网络钓鱼策略： <ul><li> ( _AuthenticationFailAction_ ) 的 [欺骗性智能保护](set-up-anti-phishing-policies.md#spoof-settings)</li><li>[模拟保护](set-up-anti-phishing-policies.md#impersonation-settings-in-atp-anti-phishing-policies)：<sup>\*</sup> <ul><li>**如果模拟用户发送电子邮件** ( _TargetedUserProtectionAction_ ) </li><li>**如果由模拟域发送的电子邮件** ( _TargetedDomainProtectionAction_ ) </li><li>**邮箱智能** \>**如果模拟用户发送电子邮件** ( _MailboxIntelligenceProtectionAction_ ) </li></ul></li></ul></ul>|否|不适用|
|[反恶意软件策略](configure-anti-malware-policies.md)：始终隔离所有检测到的邮件。|否|不适用|
|[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)|否|不适用|
|[邮件流规则](https://docs.microsoft.com/exchange/security-and-compliance/mail-flow-rules/mail-flow-rules) (也称为传输规则) 与操作：将 **邮件传递到托管隔离** ( _隔离_ ) 。|否|不适用|
|

<sup>\*</sup> 模拟保护设置仅适用于 Microsoft Defender for Office 365 中的反网络钓鱼策略。

如果你对由默认隔离标记提供的最终用户权限感到满意，则无需执行任何操作。 如果要自定义最终用户功能 (可用按钮) 在最终用户垃圾邮件通知或隔离邮件的详细信息中，则可以分配自定义隔离标记。

### <a name="assign-quarantine-tags-in-anti-spam-policies-in-the-security--compliance-center"></a>在安全 & 合规性中心中的反垃圾邮件策略中分配隔离标记

有关创建和修改反垃圾邮件策略的完整说明，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** "， \> 然后选择 " **反垃圾邮件** "。 或者，打开 <https://protection.office.com/antispam> 。

2. 查找并选择要编辑的现有反垃圾邮件策略，或创建新的反垃圾邮件策略。

3. 在 "策略详细信息" 浮出控件中，展开 " **垃圾邮件和批量操作** " 部分。
  
4. 如果已为可用垃圾邮件筛选判定的操作选择了 " **隔离邮件** "，则可以使用 " **应用隔离策略标记** " 框来选择该判定的隔离标记。

   **注意** ：创建新策略时，垃圾邮件筛选判定的空隔离标记值表示使用该判定的默认隔离标记。 当您随后编辑策略时，空值将被实际的默认隔离标记名称替换，如上表中所述。
  
   ![反垃圾邮件策略中的隔离标记选择](../../media/quarantine-tags-in-anti-spam-policies.png)

5. 完成时，请单击“保存”  。

#### <a name="assign-quarantine-tags-in-anti-spam-policies-in-powershell"></a>在 PowerShell 中的反垃圾邮件策略中分配隔离标记

如果您希望使用 PowerShell 在反垃圾邮件策略中分配隔离标记，请连接到 Exchange Online PowerShell 或 Exchange Online Protection PowerShell，并使用以下语法：

```powershell
<New-HostedContentFilterPolicy -Name "<Unique name>" | Set-HostedContentFilterPolicy -Identity "<Policy name>">  [-SpamAction Quarantine] [-SpamQuarantineTag <QuarantineTagName>] [-HighConfidenceSpamAction Quarantine] [-HighConfidenceSpamQuarantineTag <QuarantineTagName>] [-PhishSpamAction Quarantine] [-PhishQuarantineTag <QuarantineTagName>] [-HighConfidencePhishQuarantineTag <QuarantineTagName>] [-BulkSpamAction Quarantine] [-BulkQuarantineTag <QuarantineTagName>] ...
```

**注意** ：

- _HighConfidencePhishAction_ 参数的默认值为 "隔离"，因此您无需为新的反垃圾邮件策略中的高可信度网络钓鱼检测设置隔离操作。 对于新的或现有的反垃圾邮件策略中的所有其他垃圾邮件筛选 verdicts，只有在 action 值为 "隔离" 的情况下，隔离标记才有效。 若要查看现有反垃圾邮件策略中的操作值，请运行以下命令：

  ```powershell
  Get-HostedContentFilterPolicy | Format-Table Name,*SpamAction,HighConfidencePhishAction
  ```

  有关默认操作值以及标准和严格的建议操作值的信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-anti-spam-policy-settings)。

- 垃圾邮件筛选判定如果没有对应的隔离标记参数，则表示已使用该结论的 [默认隔离标记](#step-2-assign-a-quarantine-tag-to-supported-features) 。

  如果要更改隔离邮件的默认最终用户功能，则只需将默认的隔离标记替换为自定义隔离标记。

- PowerShell 中的新反垃圾邮件策略要求使用 **set-hostedcontentfilterpolicy** cmdlet 的垃圾邮件筛选器策略 (设置) 使用 **disable-hostedcontentfilterrule** cmdlet) 收件人筛选器使用新的垃圾邮件筛选规则 (收件人筛选器。 有关说明，请参阅 [使用 PowerShell 创建反垃圾邮件策略](configure-your-spam-filter-policies.md#use-powershell-to-create-anti-spam-policies)。

本示例使用以下设置创建名为 "研究部门" 的新垃圾邮件筛选器策略：

- 所有垃圾邮件筛选 verdicts 的操作都设置为 "隔离"。
- 名为 NoAccess 的自定义隔离标记（分配 **无访问** 权限）将替换默认情况下尚未分配 " **无访问** 权限" 的任何默认隔离标记。

```powershell
New-HostedContentFilterPolicy -Name Research Department -SpamAction Quarantine -SpamQuarantineTag NoAccess -HighConfidenceSpamAction Quarantine -HighConfidenceSpamQuarantineTag NoAction -PhishSpamAction Quarantine -PhishQuarantineTag NoAction -BulkSpamAction Quarantine -BulkQuarantineTag NoAccess
```

若要详细了解语法和参数，请参阅 [New-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedcontentfilterpolicy)。

本示例修改名为 "人力资源" 的现有垃圾邮件筛选器策略。 垃圾邮件隔离判定的操作将设置为 "隔离"，并分配名为 "NoAccess" 的自定义隔离标记。

```powershell
Set-HostedContentFilterPolicy -Identity "Human Resources" -SpamAction Quarantine -SpamQuarantineTag NoAccess
```

若要详细了解语法和参数，请参阅 [Set-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedcontentfilterpolicy)。

## <a name="configure-global-quarantine-notification-settings-in-the-security--compliance-center"></a>在安全 & 合规中心中配置全局隔离通知设置

通过 "隔离标记的全局设置"，可以自定义向已隔离邮件的收件人发送的最终用户垃圾邮件通知。 有关这些通知的详细信息，请参阅 [最终用户垃圾邮件通知](use-spam-notifications-to-release-and-report-quarantined-messages.md)。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** "，然后选择 " **隔离标记** "。

2. 在 " **隔离标记** " 页上，选择 " **全局设置** "。

3. 在打开的 " **隔离通知设置** " 浮出控件中，配置以下部分或所有设置：

   - **使用 "我的公司徽标** "：选择此选项可替换最终用户垃圾邮件通知顶部使用的默认 Microsoft 徽标。 在执行此操作之前，您需要按照 [自定义您的组织的 Microsoft 365 主题](https://docs.microsoft.com/microsoft-365/admin/setup/customize-your-organization-theme) 中的说明上传您的自定义徽标。

     下面的屏幕截图显示最终用户垃圾邮件通知中的自定义徽标：

     ![最终用户垃圾邮件通知中的自定义徽标](../../media/quarantine-tags-esn-customization-logo.png)

   - **选择语言** ：最终用户垃圾邮件通知已根据收件人的语言设置进行本地化。 您可以为 **显示名称** 和 **免责声明** 值指定不同语言的自定义文本。

     从 "第一种语言" 框中选择至少一种语言，然后单击 " **添加** "。 您可以通过在每个语言后面单击 " **添加** " 来选择多种语言。 "部分语言" 框显示已选择的所有语言：

     ![隔离标记全局隔离通知设置中的第二个语言框中的选定语言](../../media/quarantine-tags-esn-customization-selected-languages.png)

   - **显示名称** ：自定义在最终用户垃圾邮件通知中使用的发件人的显示名称。

     对于已添加的每种语言，在 "第二语言" 框中选择语言 (不单击 X) 并在 " **显示名称** " 框中输入所需的文本值。

     下面的屏幕截图显示最终用户垃圾邮件通知中自定义的显示名称：

     ![最终用户垃圾邮件通知中的自定义发件人显示名称](../../media/quarantine-tags-esn-customization-display-name.png)

   - **免责声明** ：将自定义免责声明添加到最终用户垃圾邮件通知的底部。 本地化后的文本、 **组织中的免责声明：** 总是首先包括您指定的文本。

     对于已添加的每种语言，在 "第二语言" 框中选择语言 (不单击 X) 并在 " **免责声明** " 框中输入所需的文本值。

     下面的屏幕截图显示最终用户垃圾邮件通知中的自定义免责声明：

     ![最终用户垃圾邮件通知底部的自定义免责声明](../../media/quarantine-tags-esn-customization-disclaimer.png)

## <a name="view-quarantine-tags-in-the-security--compliance-center"></a>查看安全 & 合规中心内的隔离标记

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** "，然后选择 " **隔离标记** "。

- 若要查看内置或自定义隔离标记的设置，请从列表中选择隔离标记 (不要选中该复选框) 。

- 若要查看全局设置，请选择 " **全局设置** "

### <a name="view-quarantine-tags-in-powershell"></a>查看 PowerShell 中的隔离标记

如果您希望使用 PowerShell 查看隔离标记，请执行以下任一步骤：

- 若要查看所有内置或自定义标记的摘要列表，请运行以下命令：

  ```powershell
  Get-QuarantineTag | Format-Table Name
  ```

- 若要查看内置或自定义隔离标记的设置，请将替换 \<TagName\> 为隔离标记的名称，然后运行以下命令：

  ```powershell
  Get-QuarantineTag -Identity "<TagName>"
  ```

- 若要查看全局设置，请运行以下命令：

  ```powershell
  Get-QuarantineTag -QuarantineTagType GlobalQuarantineTag
  ```

若要详细了解语法和参数，请参阅 [Get-HostedContentFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedcontentfilterpolicy)。

## <a name="remove-quarantine-tags-in-the-security--compliance-center"></a>在安全 & 合规中心中删除隔离标记

**注意** ：

- 无法删除内置隔离标记。

- 在删除自定义隔离标记之前，请确认未使用该标记。 例如，在 PowerShell 中运行以下命令：

  ```powershell
  Get-HostedContentFilterPolicy | Format-List Name,*QuarantineTag
  ```

  如果正在使用隔离标记，则在删除之前 [将其替换为已分配的隔离标记](#step-2-assign-a-quarantine-tag-to-supported-features) 。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** "，然后选择 " **隔离标记** "。

2. 在 " **隔离标记** " 页上，选择要删除的自定义隔离标记，然后单击 " **删除标记** "。

3. 在出现的确认对话框中，单击 " **删除标记** "。

### <a name="remove-quarantine-tags-in-powershell"></a>删除 PowerShell 中的隔离标记

如果您希望使用 PowerShell 删除自定义隔离标记，请将 \<TagName\> 其替换为隔离标记的名称，然后运行以下命令：

```powershell
Remove-QuarantineTag -Identity "<TagName>"
```

有关语法和参数的详细信息，请参阅 [QuarantineTag](https://docs.microsoft.com/powershell/module/exchange/remove-quarantinetag)。

## <a name="quarantine-tag-permission-details"></a>隔离标记权限详细信息

以下各节介绍了在隔离邮件的详细信息和最终用户垃圾邮件通知中，预置权限组和各个权限的影响。

### <a name="preset-permissions-groups"></a>预设权限组

[！注意] 本文开头的表中列出了 "预置权限" 组中包含的各个权限。

#### <a name="no-access"></a>禁止访问

如果隔离标记分配了 " **无访问** 权限" (不) 任何权限，则用户仍会获得一些基准功能：

- **隔离的邮件详细信息** ： " **查看邮件头** " 按钮始终可用。

  ![隔离邮件详细信息中的可用按钮（如果隔离标记向用户授予无访问权限）](../../media/quarantine-tags-quarantined-message-details-no-access.png)

- **最终用户垃圾邮件通知** ：将用户带到隔离区中的邮件的 " **审阅** " 按钮始终可用。

  ![最终用户垃圾邮件通知中的可用按钮（如果隔离标记向用户授予无访问权限）](../../media/quarantine-tags-esn-no-access.png)

#### <a name="limited-access"></a>受限访问

如果隔离标记分配了 **有限的访问** 权限，则用户将获得以下功能：

- **隔离的邮件详细信息** ：以下按钮可用：
  - **请求释放**
  - **查看邮件头**
  - **预览邮件**
  - **阻止发件人**
  - **从隔离区中删除**

  ![隔离邮件详细信息中的可用按钮（如果隔离标记向用户授予限制访问权限）](../../media/quarantine-tags-quarantined-message-details-limited-access.png)

- **最终用户垃圾邮件通知** ：可使用以下按钮：
  - **阻止发件人**
  - 审阅

  ![最终用户垃圾邮件通知中的可用按钮（如果隔离标记向用户授予限制访问权限）](../../media/quarantine-tags-esn-limited-access.png)

#### <a name="full-access"></a>完全访问

如果隔离标记分配了所有可用权限) 的 **完全访问** 权限 (，则用户将获得以下功能：

- **隔离的邮件详细信息** ：以下按钮可用：
  - **释放邮件**
  - **查看邮件头**
  - **预览邮件**
  - **阻止发件人**
  - **允许发件人**
  - **从隔离区中删除**

  ![隔离邮件详细信息中的可用按钮（如果隔离标记向用户授予 "完全访问" 权限）](../../media/quarantine-tags-quarantined-message-details-full-access.png)

- **最终用户垃圾邮件通知** ：可使用以下按钮：
  - **阻止发件人**
  - **发布**
  - 审阅

  ![如果隔离标记向用户授予 "完全访问" 权限，则为最终用户垃圾邮件通知中的可用按钮。](../../media/quarantine-tags-esn-full-access.png)

### <a name="individual-permissions"></a>单个权限

> [!NOTE]
> 请记住，用户始终会收到 " [无访问](#no-access) " 部分中所述的按钮。 这些按钮不包含在各个权限说明中。

#### <a name="allow-sender-permission"></a>允许发件人权限

" **允许发件人** " 权限 ( _PermissionToAllowSender_ ") 控制对按钮的访问，使用户可以方便地将隔离邮件发件人添加到其安全发件人列表。

- **隔离的邮件详细信息** ：
  - 启用 " **允许发件人** " 权限： " **允许发件人** " 按钮可用。
  - 禁用 " **允许发件人** " 权限： " **允许发件人** " 按钮不可用。

- **最终用户垃圾邮件通知** ：不起作用。

有关安全发件人列表的详细信息，请参阅 [阻止受信任发件人被阻止](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379666) 并 [使用 Exchange Online PowerShell 在邮箱上配置安全列表集合](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。

#### <a name="block-sender-permission"></a>阻止发件人权限

 ( _PermissionToBlockSender_ ) 的 **阻止发件人** 权限控制对按钮的访问，从而使用户可以方便地将隔离邮件发件人添加到其阻止的发件人列表。

- **隔离的邮件详细信息** ：
  - **阻止发件人** 权限已启用： " **阻止发件人** " 按钮可用。
  - **阻止发件人** 权限已禁用： " **阻止发件人** " 按钮不可用。

- **最终用户垃圾邮件通知** ：
  - **阻止发件人** 权限已禁用： " **阻止发件人** " 按钮不可用。
  - **阻止发件人** 权限已启用： " **阻止发件人** " 按钮可用。

有关阻止发件人列表的详细信息，请参阅 [阻止来自某人的邮件](https://support.microsoft.com/office/274ae301-5db2-4aad-be21-25413cede077#__toc304379667) ，并 [使用 Exchange Online PowerShell 在邮箱上配置安全列表集合](https://docs.microsoft.com/microsoft-365/security/office-365-security/configure-junk-email-settings-on-exo-mailboxes#use-exchange-online-powershell-to-configure-the-safelist-collection-on-a-mailbox)。

#### <a name="delete-permission"></a>删除权限

**Delete** 权限 ( _PermissionToDelete_ ) 控制用户能否删除其邮件 (邮件，而用户是从隔离) 的收件人。

- **隔离的邮件详细信息** ：
  - 已启用 **删除** 权限：可以使用 " **从隔离中删除** " 按钮。
  - 禁用 **删除** 权限： " **从隔离中删除** " 按钮不可用。

- **最终用户垃圾邮件通知** ：不起作用。

#### <a name="preview-permission"></a>预览权限

 ( _PermissionToPreview_ ) 的 **预览** 权限控制用户在隔离中预览其邮件的能力。

- **隔离的邮件详细信息** ：
  - 已启用 **预览** 权限： " **预览邮件** " 按钮可用。
  - 已禁用 **预览** 权限： " **预览邮件** " 按钮不可用。

- **最终用户垃圾邮件通知** ：不起作用。

#### <a name="allow-recipients-to-release-a-message-from-quarantine-permission"></a>允许收件人释放隔离权限中的邮件

" **允许收件人从隔离权限发布邮件** " ( _PermissionToRelease_ ") 控制用户在不审批管理员的情况下直接释放隔离邮件的能力。

- **隔离的邮件详细信息** ：
  - 已启用权限： " **释放邮件** " 按钮可用。
  - 禁用了权限： " **释放邮件** " 按钮不可用。
  
- **最终用户垃圾邮件通知** ：
  - 已启用权限： **释放** 按钮可用。
  - 已禁用权限： **释放** 按钮不可用。

#### <a name="allow-recipients-to-request-a-message-to-be-released-from-quarantine-permission"></a>允许收件人请求从隔离权限中释放邮件

" **允许收件人请求从隔离权限发布邮件** " ( _PermissionToRequestRelease_ ) 控制用户 _请求_ 释放隔离邮件的能力。 仅在管理员批准请求后才发布邮件。

- **隔离的邮件详细信息** ：
  - 已启用权限： " **请求释放** " 按钮可用。
  - 已禁用权限： " **请求释放** " 按钮不可用。

- **最终用户垃圾邮件通知** ： " **释放** " 按钮不可用。
