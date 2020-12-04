---
title: 在 Microsoft Defender for Office 365 中设置安全附件策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 078eb946-819a-4e13-8673-fe0c0ad3a775
ms.collection:
- M365-security-compliance
description: 了解如何定义安全附件策略以保护组织免受电子邮件中的恶意文件的攻击。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: a14f5a22795fc08b76165466d8e44ee38d8a2d81
ms.sourcegitcommit: d81c7cea85af6ad5fef81d3c930514a51464368c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/04/2020
ms.locfileid: "49572630"
---
# <a name="set-up-safe-attachments-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for Office 365 中设置安全附件策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender For Office 365](office-365-atp.md)的商业客户。 如果你是在 Outlook 中查找有关附件扫描的信息的家庭用户，请参阅 [Advanced Outlook.com security](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

安全附件是 [Microsoft Defender For Office 365](office-365-atp.md) 中的一项功能，在 [Exchange ONLINE protection (EOP) ](anti-malware-protection.md)中，但在传递给收件人之前，它使用虚拟环境检查入站电子邮件中的附件是否已被反恶意软件保护扫描。 有关详细信息，请参阅 [Microsoft Defender For Office 365 中的安全附件](atp-safe-attachments.md)。

没有内置或默认的安全附件策略。 若要获取安全附件扫描电子邮件附件，您需要创建一个或多个安全附件策略，如本文中所述。

您可以使用 Exchange Online 中的邮箱在安全 & 合规性中心或 PowerShell (Exchange Online PowerShell 中配置安全附件策略，以获取符合 Exchange Online 中邮箱的符合条件的 Microsoft 365 组织;独立 EOP PowerShell for 不含 Exchange Online 邮箱的组织，但使用适用于 Office 365 附加订阅的订阅) 。

安全附件策略的基本元素为：

- **安全附件策略**：指定用于未知恶意软件检测的操作、是否向指定的电子邮件地址发送包含恶意软件附件的邮件，以及是否在无法完成安全附件扫描时传递邮件。
- **安全附件规则**：指定策略应用于) 的优先级和收件人筛选器 (。

当您在安全 & 合规中心中管理安全附件策略时，这两个元素之间的差异并不明显：

- 创建安全附件策略时，实际上是同时创建安全附件规则和关联的安全附件策略，同时为两者使用相同的名称。
- 修改安全附件策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改安全附件规则。 所有其他设置修改关联的安全附件策略。
- 删除安全附件策略时，将删除安全附件规则和关联的安全附件策略。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文后面的 [使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全附件策略](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies) 一节。

> [!NOTE]
> 在 "安全附件设置" 的 "全局设置" 区域中，配置不依赖于安全附件策略的功能。 有关说明，请参阅打开[microsoft 365 E5 中](safe-docs.md)[的 SharePoint、OneDrive 和 Microsoft 团队](turn-on-atp-for-spo-odb-and-teams.md)和安全文档的 ATP。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 " **安全附件** " 页面，请使用 <https://protection.office.com/safeattachmentv2> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 您需要在安全 & 合规性中心中分配权限，然后才能执行本文中的过程：
  - 若要创建、修改和删除安全附件策略，您必须是 " **组织管理** " 或 " **安全管理员** " 角色组的成员。
  - 若要对安全附件策略进行只读访问，您需要是 **全局读取器** 或 **安全读者** 角色组的成员。

  有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 将用户添加到 Microsoft 365 管理中心中对应的 Azure Active Directory 角色，用户可为用户提供安全 & 合规性中心的必需权限 _以及_ Microsoft 365 中其他功能的权限。 有关详细信息，请参阅[关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups)中的 "**仅查看组织管理**" 角色组也提供了对功能的只读访问权限。

- 有关安全附件策略的推荐设置，请参阅 [安全附件设置](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。

- 允许使用最长30分钟的时间来应用新的或更新的策略。

## <a name="use-the-security--compliance-center-to-create-safe-attachments-policies"></a>使用安全 & 合规中心创建安全附件策略

在安全 & 合规中心中创建自定义安全附件策略，将同时为两者创建安全附件规则和关联的安全附件策略，同时使用相同的名称。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"。

2. 在 " **安全附件** " 页上，单击 " **创建**"。

3. 将打开 " **新建安全附件策略** " 向导。 在 " **命名策略** " 页上，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

   完成后，单击“下一步”。

4. 在出现的 " **设置** " 页上，配置以下设置：

   - **安全附件未知的恶意软件响应**：选择下列值之一：

     - **Off**：通常情况下，我们不建议采用此值。
     - **监视器**
     - **Block**：这是默认值，以及标准和严格的 [预设安全策略](preset-security-policies.md)中建议的值。
     - **Replace**
     - **动态传递 (预览功能)**

     这些值在 [安全附件策略设置](atp-safe-attachments.md#safe-attachments-policy-settings)中进行了说明。

   - **将附件发送到以下电子邮件地址**：对于操作值 " **阻止**、 **监视** 或 **替换**"，您可以选择 " **启用重定向** "，以便将包含恶意软件附件的邮件发送到指定的内部或外部电子邮件地址进行分析和调查。

     标准策略设置和严格策略设置的建议是启用重定向。 有关详细信息，请参阅 [安全附件设置](recommended-settings-for-eop-and-office365-atp.md#safe-attachments-settings)。

   - **如果恶意软件扫描附件超时或发生错误，则应用上述选择**：安全附件指定的操作对邮件执行 **未知恶意软件响应** ，即使安全附件扫描无法完成也是如此。 如果选择 " **启用重定向**"，请始终选择此选项。 否则，邮件可能会丢失。

   完成后，单击“下一步”。

5. 在显示的 " **应用于** " 页上，确定该策略应用于的内部收件人。

   只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   单击 " **添加条件**"。 在出现的下拉列表中，选择 " **应用** 条件：

   - **收件人为**：指定组织中的一个或多个邮箱、邮件用户或邮件联系人。
   - **收件人是的成员**：指定组织中的一个或多个组。
   - **收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。

   选择条件后，将显示相应的下拉框，其中包含 **其中的任何** 框。

   - 在框中单击并滚动到要选择的值列表。
   - 在框中单击，然后开始键入以筛选列表并选择一个值。
   - 若要添加其他值，请单击框中的空白区域。
   - 若要删除单个条目， **Remove** 请单击 ![ ](../../media/scc-remove-icon.png) 值上的 "删除删除" 图标。
   - 若要删除整个条件，请 **Remove** 单击 ![ ](../../media/scc-remove-icon.png) 条件上的 "删除删除" 图标。

   若要添加其他条件，请单击 " **添加条件** "，然后选择 " **应用于**" 下的其他值。

   若要添加例外，请单击 " **添加条件** "，并在 " **除非**" 下选择例外。 设置和行为与条件完全相同。

   完成后，单击“下一步”。

6. 在显示的 " **查看您的设置** " 页上，查看您的设置。 您可以在每个设置上单击 " **编辑** " 以修改它。

   完成后，单击 " **完成**"。

## <a name="use-the-security--compliance-center-to-view-safe-attachments-policies"></a>使用安全 & 合规性中心查看安全附件策略

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"。

2. 在 " **安全附件** " 页面上，从列表中选择一个策略并单击该策略 (未选中复选框) 。

   弹出时显示策略详细信息

## <a name="use-the-security--compliance-center-to-modify-safe-attachments-policies"></a>使用安全 & 合规性中心修改安全附件策略

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"。

2. 在 " **安全附件** " 页面上，从列表中选择一个策略并单击该策略 (未选中复选框) 。

3. 在 "策略详细信息" 弹出显示，单击 " **编辑策略**"。

弹出的可用设置与 " [使用安全 & 合规中心创建安全附件策略](#use-the-security--compliance-center-to-create-safe-attachments-policies) " 一节中所述的相同。

若要启用或禁用策略或设置策略优先级顺序，请参阅以下各节。

### <a name="enable-or-disable-safe-attachments-policies"></a>启用或禁用安全附件策略

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"。

2. 请注意 " **状态** " 列中的值：

   - 将切换向左移动 ![关闭策略](../../media/scc-toggle-off.png) 禁用该策略。

   - 将切换向右移动 ![启用策略](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png) 启用该策略。

### <a name="set-the-priority-of-safe-attachments-policies"></a>设置安全附件策略的优先级

默认情况下，安全附件策略的优先级将根据其在 (较旧策略) 中创建的顺序的优先级降低。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

安全附件策略按其处理顺序显示 (第一个策略的 **优先级** 值为 0) 。

**注意**：在安全 & 合规性中心中，您只能在创建安全附件策略后更改其优先级。 在 PowerShell 中，您可以在创建安全附件规则时覆盖默认优先级， (这可能会影响现有规则) 的优先级。

若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"。

2. 在 " **安全附件** " 页面上，从列表中选择一个策略并单击该策略 (未选中复选框) 。

3. 在 "策略详细信息" 飞出时，单击出现的 "可用优先级" 按钮。

   - **优先级** 值为 **0** 的安全附件策略仅有 "**降低优先级**" 按钮可用。

   - **优先级** 值最低的安全附件策略 (例如， **3**) 仅有 "**提高优先级**" 按钮可用。

   - 如果您具有三个或更多安全附件策略，则在最高和最低优先级值之间的策略将具有 " **增加优先级** " 和 " **降低优先级** " 按钮可用。

4. 单击 " **提高优先级** " 或 " **降低优先级** " 以更改 **优先级** 值。

5. 完成后，单击“关闭”。

## <a name="use-the-security--compliance-center-to-remove-safe-attachments-policies"></a>使用安全 & 合规性中心删除安全附件策略

1. 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"。

2. 在 " **安全附件** " 页面上，从列表中选择一个策略并单击该策略 (未选中复选框) 。

3. 在 "策略详细信息" 弹出显示的内容中，单击 " **删除策略**"，然后在出现的警告对话框中单击 **"是"** 。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-safe-attachments-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置安全附件策略

如前面所述，安全附件策略由安全附件策略和安全附件规则组成。

在 PowerShell 中，安全附件策略和安全附件规则之间的区别很明显。 您可以使用 **\* -SafeAttachmentPolicy** cmdlet 管理安全附件策略，还可以使用 **\* -SafeAttachmentRule** cmdlet 管理安全附件规则。

- 在 PowerShell 中，首先创建安全附件策略，然后创建标识应用规则的策略的安全附件规则。
- 在 PowerShell 中，可以单独修改安全附件策略和安全附件规则中的设置。
- 从 PowerShell 中删除安全附件策略时，不会自动删除相应的安全附件规则，反之亦然。

### <a name="use-powershell-to-create-safe-attachments-policies"></a>使用 PowerShell 创建安全附件策略

在 PowerShell 中创建安全附件策略的过程分为两个步骤：

1. 创建安全附件策略。
2. 创建安全附件规则，该规则指定应用该规则的安全附件策略。

 **注意**：

- 您可以创建新的安全附件规则，并向其分配现有的未关联的安全附件策略。 一个安全附件规则不能与多个安全附件策略相关联。

- 您可以在 PowerShell 的新安全附件策略中配置以下设置，这些设置在安全 & 合规性中心中不可用，直到您创建了策略：
  - 将新策略创建为 _Enabled_ `$false` **SafeAttachmentRule** cmdlet) 上启用的禁用 (。
  - 在 _Priority_ _\<Number\>_ **SafeAttachmentRule** Cmdlet) 上创建 (优先级) 时设置策略的优先级。

- 在 PowerShell 中创建的新安全附件策略在安全 & 合规性中心中不可见，除非您将策略分配给安全附件规则。

#### <a name="step-1-use-powershell-to-create-a-safe-attachment-policy"></a>步骤1：使用 PowerShell 创建安全附件策略

若要创建安全附件策略，请使用以下语法：

```PowerShell
New-SafeAttachmentPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-Action <Allow | Block | Replace | DynamicDelivery>] [-Redirect <$true | $false>] [-RedirectAddress <SMTPEmailAddress>] [-ActionOnError <$true | $false>]
```

本示例创建一个名为 "Contoso All" 的安全附件策略，其中包含以下值：

- 阻止找到的包含恶意文档的恶意软件的邮件扫描 (我们不使用 _Action_ 参数，并且默认值为 `Block`) 。
- 启用了重定向，并将找到的包含恶意软件的邮件发送到 sec-ops@contoso.com 以进行分析和调查。
- 如果安全附件扫描不可用或遇到错误，则不要传递邮件 (我们不使用 _ActionOnError_ 参数，默认值为 `$true`) 。

```PowerShell
New-SafeAttachmentPolicy -Name "Contoso All" -Redirect $true -RedirectAddress sec-ops@contoso.com
```

有关语法和参数的详细信息，请参阅 [SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentpolicy)。

#### <a name="step-2-use-powershell-to-create-a-safe-attachment-rule"></a>步骤2：使用 PowerShell 创建安全附件规则

若要创建安全附件规则，请使用以下语法：

```PowerShell
New-SafeAttachmentRule -Name "<RuleName>" -SafeAttachmentPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"] [-Enabled <$true | $false>]
```

本示例将创建一个名为 "Contoso All" 的安全附件规则和以下条件：

- 规则与名为 "Contoso All" 的安全附件策略相关联。
- 该规则应用于 contoso.com 域中的所有收件人。
- 由于我们不使用 _Priority_ 参数，因此使用默认的优先级。
-  (我们不使用 _enabled_ 参数，并且默认值为) ，则启用该规则 `$true` 。

```powershell
New-SafeAttachmentRule -Name "Contoso All" -SafeAttachmentPolicy "Contoso All" -RecipientDomainIs contoso.com
```

有关语法和参数的详细信息，请参阅 [SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/new-safeattachmentrule)。

### <a name="use-powershell-to-view-safe-attachment-policies"></a>使用 PowerShell 查看安全附件策略

若要查看现有的安全附件策略，请使用以下语法：

```PowerShell
Get-SafeAttachmentPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本示例返回所有安全附件策略的摘要列表。

```PowerShell
Get-SafeAttachmentPolicy
```

本示例返回名为 "Contoso 行政主管" 的安全附件策略的详细信息。

```PowerShell
Get-SafeAttachmentPolicy -Identity "Contoso Executives" | Format-List
```

有关语法和参数的详细信息，请参阅 [SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentpolicy)。

### <a name="use-powershell-to-view-safe-attachment-rules"></a>使用 PowerShell 查看安全附件规则

若要查看现有的安全附件规则，请使用以下语法：

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

本示例返回名为 "Contoso 行政主管" 的安全附件规则的详细信息。

```PowerShell
Get-SafeAttachmentRule -Identity "Contoso Executives" | Format-List
```

有关语法和参数的详细信息，请参阅 [SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/get-safeattachmentrule)。

### <a name="use-powershell-to-modify-safe-attachment-policies"></a>使用 PowerShell 修改安全附件策略

无法重命名 PowerShell (**SafeAttachmentPolicy** Cmdlet 没有 _名称_ 参数) 的安全附件策略。 重命名安全 & 合规性中心中的安全附件策略时，只是重命名安全附件 _规则_。

否则，在创建安全附件策略时，可以使用相同的设置，如上文中的 " [步骤1：使用 PowerShell 创建安全附件策略](#step-1-use-powershell-to-create-a-safe-attachment-policy) " 一节中所述。

若要修改安全附件策略，请使用以下语法：

```PowerShell
Set-SafeAttachmentPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentpolicy)。

### <a name="use-powershell-to-modify-safe-attachment-rules"></a>使用 PowerShell 修改安全附件规则

在 PowerShell 中修改安全附件规则时，唯一的设置是 _已启用_ 的参数，允许您创建禁用的规则。 若要启用或禁用现有安全附件规则，请参阅下一节。

否则，在创建规则时，将在本文前面的 " [步骤2：使用 PowerShell 创建安全附件规则](#step-2-use-powershell-to-create-a-safe-attachment-rule) " 一节中所述的那样使用相同的设置。

若要修改安全附件规则，请使用以下语法：

```PowerShell
Set-SafeAttachmentRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-enable-or-disable-safe-attachment-rules"></a>使用 PowerShell 启用或禁用安全附件规则

启用或禁用 "PowerShell 中的安全附件规则" 可启用或禁用 "安全附件" 规则和 "分配的安全附件" 策略) 的整个安全附件策略 (。

若要在 PowerShell 中启用或禁用安全附件规则，请使用以下语法：

```PowerShell
<Enable-SafeAttachmentRule | Disable-SafeAttachmentRule> -Identity "<RuleName>"
```

本示例禁用名为 "Marketing 部门" 的安全附件规则。

```PowerShell
Disable-SafeAttachmentRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-SafeAttachmentRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Enable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/enable-safeattachmentrule) 和 [Disable-SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/disable-safeattachmentrule)。

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

**注意**：若要在创建新规则时设置其优先级，请改用 **SafeAttachmentRule** cmdlet 上的 _priority_ 参数。

有关语法和参数的详细信息，请参阅 [SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/set-safeattachmentrule)。

### <a name="use-powershell-to-remove-safe-attachment-policies"></a>使用 PowerShell 删除安全附件策略

当您使用 PowerShell 删除安全附件策略时，不会删除相应的安全附件规则。

若要在 PowerShell 中删除安全附件策略，请使用以下语法：

```PowerShell
Remove-SafeAttachmentPolicy -Identity "<PolicyName>"
```

本示例将删除名为 "Marketing 部门" 的安全附件策略。

```PowerShell
Remove-SafeAttachmentPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [SafeAttachmentPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentpolicy)。

### <a name="use-powershell-to-remove-safe-attachment-rules"></a>使用 PowerShell 删除安全附件规则

当您使用 PowerShell 删除安全附件规则时，不会删除相应的安全附件策略。

若要删除 PowerShell 中的安全附件规则，请使用以下语法：

```PowerShell
Remove-SafeAttachmentRule -Identity "<PolicyName>"
```

本示例删除名为 "Marketing 部门" 的安全附件规则。

```PowerShell
Remove-SafeAttachmentRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [SafeAttachmentRule](https://docs.microsoft.com/powershell/module/exchange/remove-safeattachmentrule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否已成功创建、修改或删除了安全附件策略，请执行以下任一步骤：

- 在安全 & 合规性中心中，转到 " **威胁管理** \> **策略** \> **ATP 安全附件**"。 验证策略列表、策略的 **状态** 值及其 **优先级** 值。 若要查看更多详细信息，请从列表中选择策略，并在 "飞出" 中查看详细信息。

- 在 Exchange Online PowerShell 或 Exchange Online Protection PowerShell 中，将替换 \<Name\> 为策略或规则的名称，运行以下命令，并验证设置：

  ```PowerShell
  Get-SafeAttachmentPolicy -Identity "<Name>" | Format-List
  ```

  ```PowerShell
  Get-SafeAttachmentRule -Identity "<Name>" | Format-List
  ```

若要验证安全附件是否正在扫描邮件，请检查可用的 Office 365 的 Defender for Office 报告。 有关详细信息，请参阅 [查看适用于 Office 365 的 Defender 报告](view-reports-for-atp.md) 和 [使用安全 & 合规性中心中的资源管理器](threat-explorer.md)。
