---
title: 在 EOP 中配置反垃圾邮件策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何创建、修改和删除 Exchange Online Protection (EOP) 组织（具有或没有 Exchange Online 邮箱）中提供的防钓鱼策略。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5bab5e791cb58c4e681a802179583471bb6ab165
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287909"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>在 EOP 中配置反垃圾邮件策略

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)

在邮箱在 Exchange Online 中的 Microsoft 365 组织或没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，默认反网络钓鱼策略包含有限数量的默认情况下启用的反欺骗功能。 有关详细信息，请参阅反网络钓鱼策略 [中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

管理员可以查看、编辑和配置 (，但不能删除) 默认的防钓鱼策略。 更具体一些，您还可以创建自定义防钓鱼策略，这些策略适用于组织中特定的用户、组或域。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

具有 Exchange Online 邮箱的组织可以在安全与合规中心& Exchange Online PowerShell 中配置防钓鱼策略。 独立 EOP 组织只能使用安全&合规中心。

有关在适用于 Office 365 的 Defender 中可用的 Microsoft Defender for Office 365 中创建和修改更高级反网络钓鱼策略的信息，请参阅 [在 Microsoft Defender for Office 365](configure-atp-anti-phishing-policies.md)中配置反网络钓鱼策略。

反网络钓鱼策略的基本元素包括：

- **防钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及要应用选项的操作。
- **反网络钓鱼规则**：指定策略 (的优先级和收件人筛选器) 策略的收件人筛选器。

在安全与合规中心内管理防钓鱼策略时，这两个元素&并不明显：

- 创建防钓鱼策略时，实际上是同时使用同一名称创建反网络钓鱼规则和相关反网络钓鱼策略。
- 修改防钓鱼策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改反网络钓鱼规则。 所有其他设置修改关联的防钓鱼策略。
- 删除防钓鱼策略时，将删除防钓鱼规则和相关反网络钓鱼策略。

在 Exchange Online PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文稍后介绍的"使用 [Exchange Online PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 配置防钓鱼策略"部分。

每个组织都有一个名为 Office365 AntiPhish Default 的内置反网络钓鱼策略，该策略具有以下属性：

- 即使与策略关联的收件人筛选器没有反网络钓鱼规则， (策略) 应用于组织的所有收件人。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略始终具有更高的优先级。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

若要提高防钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义防钓鱼策略。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **"防钓鱼"页面，** 请使用 <https://protection.office.com/antiphishing> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

  无法管理独立 EOP PowerShell 中的防钓鱼策略。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要添加、修改和删除防钓鱼策略，您必须是组织 **管理或****安全管理员角色组** 的成员。
  - 若要对防钓鱼策略进行只读访问，你需要是全局读者或安全读者 **角色组的成员** <sup>\*</sup> 。

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - Exchange [Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) **中的"** 仅查看组织管理"角色组还授予对该功能的只读访问权限 <sup>\*</sup> 。
  - <sup>\*</sup> 在安全&合规中心，只读访问权限允许用户查看自定义防钓鱼策略的设置。 只读用户看不到默认防钓鱼策略中的设置。

- 若要在独立 EOP 中创建和修改防钓鱼策略，需要为租户执行需要冻结的一些操作。 例如，在 Exchange 管理中心 (EAC) 中，可以转到"权限"选项卡、选择现有角色组、单击"编辑编辑"图标并删除角色 (最终添加回 ![ ](../../media/ITPro-EAC-EditIcon.png)) 。 如果租户从未被冻结，则会出现一个名为"更新组织设置"的对话框，其进度栏应成功完成。 有关冻结详细信息，请参阅 [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet (该 cmdlet 在独立 EOP PowerShell 或安全与合规中心&中不可用) 。

- 有关我们推荐的反网络钓鱼策略设置，请参阅 [EOP 默认防钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

- 最多允许应用 30 分钟更新的策略。

- 有关反网络钓鱼策略在筛选管道中的应用位置的信息，请参阅电子邮件保护 [的顺序和优先级](how-policies-and-protections-are-combined.md)。

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>使用安全&合规中心创建防钓鱼策略

在安全与合规中心内创建自定义防钓鱼策略&同时使用同一名称创建反网络钓鱼规则和相关反钓鱼策略。

创建防钓鱼策略时，只能指定策略名称、说明和收件人筛选器，以标识策略适用的用户。 创建策略后，可以修改该策略以更改或查看默认的防钓鱼设置。

1. 在安全&合规中心，转到 **"威胁管理** \> **策略** \> **防钓鱼"。**

2. 在 **"防钓鱼"页上**，单击"**创建"。**

3. 将 **打开"新建防钓鱼策略"** 向导。 在 **"为策略命名"** 页上，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

   完成后，单击“下一步”。

4. 在 **出现的"应用于** "页上，标识策略应用于的内部收件人。

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

5. 在 **出现的"查看设置** "页上，查看设置。 可以单击 **每个设置** 上的"编辑"来修改它。

   完成后，单击"**创建此策略"。**

6. 在 **出现的** 确认对话框中单击"确定"。

使用这些常规策略设置创建防钓鱼策略后，请使用下一节中的说明在策略中配置保护设置。

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>使用安全&合规中心修改防钓鱼策略

使用以下过程可修改防钓鱼策略：您创建的新策略或已自定义的现有策略。

1. 如果还没有，请打开安全与合规&，然后转到 **"威胁管理** 策略 \>  \> **防钓鱼"。**

2. 选择要修改的自定义防钓鱼策略。 如果已选中，请取消选择它，然后再次选择它。

3. 将显示 **"编辑策略 \<name\>**"飞出控件。 单击 **任何** 部分中的"编辑"可让你访问该节中的设置。

   - 以下步骤按各节的显示顺序显示，但它们不是连续的 (您可以按任意顺序选择和修改节) 。

   - 单击分区中的"编辑"后，可用设置以向导格式显示，但您可以按任意顺序跳转到页面内，并可以单击任何页面上的"保存" (或 ![ ](../../media/scc-remove-icon.png) **\<name\>**"取消"或"关闭"图标返回到"编辑策略"页面 (无需访问向导的最后一页即可保存或离开) 。

4. **策略设置**：单击 **"** 编辑"可修改在上一部分中创建策略 [时可用的](#use-the-security--compliance-center-to-create-anti-phishing-policies) 相同设置：

   - **名称**
   - **说明**
   - **应用于**
   - **查看设置**

   完成后，单击"在任何 **页面上** 保存"。

5. **欺骗**：单击"编辑"打开或关闭欺骗智能，在 Outlook 中打开或关闭未经身份验证的发件人标识，并配置操作以应用于来自被阻止的欺骗发件人的邮件。 有关详细信息，请参阅反网络钓鱼策略 [中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

   请注意，这些相同的设置在 Defender for Office 365 中的防钓鱼策略中也可用。

   - **欺骗筛选器设置**：默认值为 **"打开**"，建议保留它。 若要将其关闭，请滑动切换至 **"关闭"。** 有关详细信息，请参阅在 [EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > 如果 MX 记录未指向 Microsoft 365，无需禁用反欺骗保护;改为启用连接器的增强筛选。 有关说明，请参阅 [Exchange Online 中连接器的增强筛选](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)。

   - **启用未经身份验证的发件人功能**：默认值为 **On。** 若要将其关闭，请滑动切换至 **"关闭"。**

   - **操作**：指定对欺骗智能失败的邮件要采取的操作：

     **如果电子邮件是由不允许欺骗你的域的人发送的**：

     - **将邮件移动到收件人的垃圾邮件文件夹**
     - **隔离邮件**

   - **查看设置**：设置显示在摘要中，而不是单击各个步骤。

     - 可以单击 **每个部分** 中的"编辑"跳转回相关页面。
     - 您可以直接在此页面上切换以下设置 **"开**"或"关"： 

       - **启用反反恶意软件保护**
       - **启用未经身份验证的发件人功能**

   完成后，单击"在任何 **页面上** 保存"。

6. 返回到"**编辑策略" \<Name\>** 页，查看设置，然后单击"**关闭"。**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>使用安全&合规中心修改默认的防钓鱼策略

默认的防钓鱼策略名为"Office365 反钓鱼默认策略"，它不会显示在策略列表中。 若要修改默认的防钓鱼策略，请执行以下步骤：

1. 在安全&合规中心，转到 **"威胁管理** \> **策略** \> **防钓鱼"。**

2. 在 **"防钓鱼"页上**，单击"**默认策略"。**

3. 将显示 **"编辑策略 Office365 反Phish 默认** "页。 以下各节可用，其中包含修改自定义策略 [时相同的设置](#use-the-security--compliance-center-to-modify-anti-phishing-policies)。

   - **模拟**
   - **欺骗**
   - **高级设置**

   修改默认策略时，以下设置不可用：

   - 可以看到"策略设置"部分和值，但没有"编辑"链接，因此不能修改设置 (策略名称、说明以及策略应用于其 (应用于所有收件人) ) 。
   - 不能删除默认策略。
   - 你无法更改默认策略的优先级 (它始终在上次应用) 。

4. 在"**编辑策略 Office365 反Phish 默认**"页上，查看设置，然后单击"**关闭"。**

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>启用或禁用自定义防钓鱼策略

1. 在安全&合规中心，转到 **"威胁管理** \> **策略** \> **防钓鱼"。**

2. 请注意" **状态"列中** 的值：

   - 将开关滑动到 **"关闭** "以禁用策略。

   - 将开关滑动到 **"打开** "以启用策略。

不能禁用默认的防钓鱼策略。

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>设置自定义防钓鱼策略的优先级

默认情况下，反网络钓鱼策略的优先级基于它们在新策略中创建的顺序 (较旧策略的优先级) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

自定义防钓鱼策略按处理策略的顺序显示 (优先级值为 0) 。  名为 Office365 AntiPhish Default 的默认防钓鱼策略具有自定义优先级值 **"** 最低"，你无法更改它。

 **注意**：在安全&合规中心，只能在创建后更改反网络钓鱼策略的优先级。 在 PowerShell 中，可以在创建反钓鱼规则时替代默认优先级 (这会影响现有规则优先级) 。

若要更改策略的优先级，请单击策略属性中的"增加优先级"或"降低优先级 (则不能直接修改安全与合规中心&优先级) 。  更改策略的优先级仅在有多个策略时有意义。

1. 在安全&合规中心，转到 **"威胁管理** \> **策略** \> **ATP 防钓鱼"。**

2. 选择要修改的策略。 如果已选中，请取消选择它，然后再次选择它。

3. 将显示 **"编辑策略 \<name\>**"飞出控件。

   - 优先级值为 **0** 的自定义防钓鱼策略只有"减少优先级 **"按钮** 可用。

   - 优先级值最低的自定义防钓鱼策略 (例如 **，3**) 只有"增加优先级 **"** 按钮可用。

   - 如果你有三个或多个自定义防钓鱼策略，则最高优先级值和最低优先级值之间的策略同时具有"增加优先级"和"减少优先级 **"** 按钮。

4. 单击 **"增加优先级** " **或"降低优先级** "可更改 **"优先级"** 值。

5. 完成后，单击“关闭”。

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>使用安全&合规中心查看防钓鱼策略

1. 在安全&合规中心，转到 **"威胁管理** \> **策略** \> **防钓鱼"。**

2. 采取以下步骤之一：

   - 选择要查看的自定义防钓鱼策略。 如果已选中，请取消选择它，然后再次选择它。

   - 单击 **"默认** 策略"可查看默认的防钓鱼策略。

3. 将显示 **"编辑策略 \<name\>**"飞出控件，可在其中查看设置和值。

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>使用安全&合规中心删除防钓鱼策略

1. 在安全&合规中心，转到 **"威胁管理** \> **策略** \> **防钓鱼"。**

2. 选择要删除的策略。 如果已选中，请取消选择它，然后再次选择它。

3. 在出现的 **"编辑策略 \<name\>**"弹出对话框中，单击"删除策略"，然后在出现的警告对话框中单击"是"。

无法删除默认策略。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>使用 Exchange Online PowerShell 配置防钓鱼策略

如前所述，防钓鱼策略由反网络钓鱼策略和防钓鱼规则组成。

在 Exchange Online PowerShell 中，防钓鱼策略和防钓鱼规则的区别显而易见。 您可以使用 **\* -AntiPhishPolicy** cmdlet 管理防钓鱼策略，使用 **\* -AntiPhishRule** cmdlet 管理防钓鱼规则。

- 在 PowerShell 中，首先创建防钓鱼策略，然后创建标识规则所适用的策略的防钓鱼规则。
- 在 PowerShell 中，分别修改反钓鱼策略和反钓鱼规则中的设置。
- 从 PowerShell 删除防钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。

> [!NOTE]
> 以下 PowerShell 过程不适用于使用 Exchange Online Protection PowerShell 的独立 EOP 组织。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>使用 PowerShell 创建防钓鱼策略

在 PowerShell 中创建防钓鱼策略的过程分两步完成：

1. 创建防钓鱼策略。
2. 创建指定规则所适用的防钓鱼策略的防钓鱼规则。

 **注意**：

- 您可以创建一个新的防钓鱼规则，并为其分配现有的未关联的反网络钓鱼策略。 反网络钓鱼规则不能与多个防钓鱼策略关联。

- 可以在 PowerShell 中对新的防钓鱼策略配置以下设置，这些策略在创建策略之前&安全与合规中心内不可用：

  - 在 `$false` **New-AntiPhishRule** cmdlet (上创建禁用的新) 。
  - 在 _\<Number\>_ **New-AntiPhishRule** cmdlet (设置策略) 优先级) 。

- 在 PowerShell 中创建的新防钓鱼策略在安全与合规&中不可见，除非将策略分配给防钓鱼规则。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>步骤 1：使用 PowerShell 创建防钓鱼策略

若要创建防钓鱼策略，请使用以下语法：

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableSpoofIntelligence <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

此示例创建一个名为"研究隔离"的反网络钓鱼策略，该策略具有以下设置：

- 描述为：研究部门策略。
- 将欺骗的默认操作更改为"隔离"。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

有关语法和参数的详细信息，请参阅 [New-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>步骤 2：使用 PowerShell 创建防钓鱼规则

若要创建防钓鱼规则，请使用以下语法：

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

此示例创建一个名为"研究部门"的反网络钓鱼规则，该规则具有以下条件：

- 该规则与名为"研究隔离"的防钓鱼策略相关联。
- 此规则应用于“研究部门”组中的成员。
- 因为我们没有使用 _Priority_ 参数，所以使用默认优先级。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>使用 PowerShell 查看防钓鱼策略

若要查看现有的防钓鱼策略，请使用以下语法：

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

此示例返回所有防钓鱼策略的摘要列表以及指定的属性。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

此示例返回名为 Executives 的反钓鱼策略的所有属性值。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

有关语法和参数的详细信息，请参阅 [Get-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)。

### <a name="use-powershell-to-view-anti-phish-rules"></a>使用 PowerShell 查看防钓鱼规则

若要查看现有的防钓鱼规则，请使用以下语法：

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

此示例返回所有防钓鱼规则的摘要列表以及指定的属性。

```PowerShell
Get-AntiPhishRule | Format-Table Name,Priority,State
```

若要按已启用或已禁用规则筛选列表，请运行以下命令：

```PowerShell
Get-AntiPhishRule -State Disabled | Format-Table Name,Priority
```

```PowerShell
Get-AntiPhishRule -State Enabled | Format-Table Name,Priority
```

此示例返回名为 Contoso Executives 的反钓鱼规则的所有属性值。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>使用 PowerShell 修改防钓鱼策略

除了以下项目外，在 PowerShell 中修改防钓鱼策略时可用的设置与步骤 1 中所述的创建策略时相同：使用 [PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建本文前面所述的防钓鱼策略。

- _MakeDefault_ 开关将指定策略转换为应用于所有人的默认策略 (，优先级始终最低，并且只有在修改 PowerShell 中的防钓鱼策略时) 才能将其删除。

- 如果 **Set-AntiPhishPolicy** cmdlet (Name 参数，则不能重命名防钓鱼) 。  在安全与合规中心内重命名防钓鱼&，只是重命名了防钓鱼 _规则_。

若要修改防钓鱼策略，请使用以下语法：

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>使用 PowerShell 修改防钓鱼规则

在 PowerShell 中修改防钓鱼规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有的防钓鱼规则，请参阅下一节。

否则，当您创建规则时，如本文前面所述的步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) 创建防钓鱼规则部分时，可使用相同的设置。

若要修改防钓鱼规则，请使用以下语法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>使用 PowerShell 启用或禁用防钓鱼规则

在 PowerShell 中启用或禁用反网络钓鱼规则可启用或禁用整个防钓鱼策略 (防钓鱼规则以及分配的反钓鱼策略) 。 无法启用或禁用默认防钓鱼策略 (该策略始终应用于所有收件人) 。

若要在 PowerShell 中启用或禁用反网络钓鱼规则，请使用以下语法：

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

本示例禁用名为 Marketing Department 的反网络钓鱼规则。

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-antiphishrule)和[Disable-AntiPhishRule。](https://docs.microsoft.com/powershell/module/exchange/disable-antiphishrule)

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>使用 PowerShell 设置防钓鱼规则的优先级

可以设置的规则最高优先级值是 0。 可以设置的最小优先级值取决于规则的数量。 例如，如果有五个规则，则可以使用的优先级值为 0 到 4。 更改现有规则的优先级可对其他规则产生级联效应。 例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。

若要在 PowerShell 中设置防钓鱼规则的优先级，请使用以下语法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

下面的示例将名为“Marketing Department”的规则的优先级设置为 2。 优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**注意**：

- 若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-AntiPhishRule** cmdlet 上的 _Priority_ 参数。

- 默认的防钓鱼策略没有对应的防钓鱼规则，并且始终具有不可修改的优先级值 **"最低"。**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>使用 PowerShell 删除防钓鱼策略

使用 PowerShell 删除防钓鱼策略时，不会删除相应的防钓鱼规则。

若要在 PowerShell 中删除防钓鱼策略，请使用以下语法：

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

此示例删除名为 Marketing Department 的防钓鱼策略。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-AntiPhishPolicy](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>使用 PowerShell 删除防钓鱼规则

使用 PowerShell 删除防钓鱼规则时，不会删除相应的防钓鱼策略。

若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

此示例删除名为"Marketing Department"的反网络钓鱼规则。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功在 Microsoft Defender for Office 365 中配置防钓鱼策略，请执行下列任一步骤：

- 在安全&合规中心，转到 **"威胁管理** \> **策略** \> **防钓鱼"。** 验证策略列表、其 **状态** 值及其 **优先级** 值。 若要查看更多详细信息，请执行下列任一步骤：

  - 从列表中选择策略，并查看该飞出项中的详细信息。
  - 单击 **"默认** 策略"，在飞出视图中查看详细信息。

- 在 Exchange Online PowerShell 中，替换为策略或规则的名称，运行 \<Name\> 以下命令并验证设置：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
