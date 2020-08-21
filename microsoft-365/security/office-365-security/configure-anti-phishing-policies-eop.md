---
title: 在 EOP 中配置防钓鱼策略
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.date: ''
ms.service: O365-seccomp
localization_priority: Normal
ms.assetid: ''
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何创建、修改和删除在具有或不使用 Exchange Online 邮箱的情况下，在运行 EOP 和 () 组织的 Exchange Online Protection) 策略中使用的反网络钓鱼策略。
ms.openlocfilehash: af6577d32d43300867d29a365baaa4e1e7e1b5e3
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46825745"
---
# <a name="configure-anti-phishing-policies-in-eop"></a>在 EOP 中配置防钓鱼策略

在没有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，默认提供默认的反网络钓鱼策略包含默认情况下启用的有限数量的反欺骗功能。 有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

管理员可以查看、编辑和配置 (但不能) 删除默认的反网络钓鱼策略。 更精细地进行管理，还可以创建自定义防钓鱼策略，这些策略适用于组织中的特定用户、组或域。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

具有 Exchange Online 邮箱的组织可以在安全 & 合规中心或 Exchange Online PowerShell 中配置反网络钓鱼策略。 独立 EOP 组织只能使用安全与&合规中心。

有关创建和修改更高级的 ATP 反网络钓鱼策略在 Office 365 高级威胁防护 (Office 365 ATP) 中可用的信息，请参阅"[配置 ATP 防钓鱼策略"。](configure-atp-anti-phishing-policies.md)

防钓鱼策略的基本要点包括：

- **反钓鱼策略**：指定要启用或禁用的网络钓鱼防护以及应用选项的操作。
- **反网络钓鱼规则：** 指定 (策略应用于反钓鱼策略) 的优先级和收件人筛选器。

在安全与合规中心管理反网络钓鱼策略时，这两&意不显而是：

- 创建反网络钓鱼策略时，实际上是在同时创建反钓鱼规则和关联的反钓鱼策略：对这两者使用相同的名称。
- 修改反网络钓鱼策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置可以修改反网络钓鱼规则。 所有其他设置都将修改关联的反网络钓鱼策略。
- 删除反网络钓鱼策略时，将删除反网络钓鱼规则和关联的反网络钓鱼策略。

在 Exchange Online PowerShell 中，您可以单独管理策略和规则。 有关详细信息，请参阅本主题 [后面的"使用 Exchange Online PowerShell 配置反网络钓鱼](#use-exchange-online-powershell-to-configure-anti-phishing-policies) 策略"一节。

每个组织都有一个名为 Office365 AntiPhish Default 的内置反网络钓鱼策略，该策略具有以下属性：

- 策略会应用于组织中的所有收件人，即使没有任何反网络 (网络钓鱼规则) 自定义收件人筛选器。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略始终具有更高的优先级。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

若要提高防钓鱼防钓鱼保护的有效性，可以创建自定义反网络钓鱼策略，将这些设置应用于特定用户或用户组。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **"反网络钓鱼"页面，** 请使用 <https://protection.office.com/antiphishing> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。

  您不能在独立 EOP PowerShell 中管理反网络钓鱼策略。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 若要添加、修改和删除反网络钓鱼策略，你需要是以下角色组的成员之一：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 必须是以下角色组的成员之一，才能以只读方式访问反网络钓鱼策略：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

- 为了能够在独立 EOP 中创建和修改反垃圾邮件策略，您需要执行一些需要 _对租户执行_ 代理的操作。 例如，在 Exchange 管理中心 (EAC) 中，您可以转到" **权限"** 选项卡，选择现有角色组，单击" **编辑** ![ " ](../../media/ITPro-EAC-EditIcon.png) 图标，然后 (删除最终将添加回的) 。 如果租户从未延迟，则会出现一个名为" **更新组织设置"的** 对话框，并显示应成功完成的进度栏。 有关 hydration 的详细信息，请参阅独立 EOP PowerShell 或安全与合规中心仪表板 &中不可用的 [Enable-OrganizationCustomization](https://docs.microsoft.com/powershell/module/exchange/enable-organizationcustomization) cmdlet () 。

- 有关我们推荐的反网络钓鱼策略设置， [请参阅 EOP 默认防钓鱼策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-default-anti-phishing-policy-settings)。

- 最多允许应用更新的策略 30 分钟。

- 有关在筛选管道中应用防钓鱼策略的位置的信息，请参阅 [电子邮件保护的订单和优先级](how-policies-and-protections-are-combined.md)。

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies"></a>使用安全与&合规中心来创建反网络钓鱼策略

在安全 & 合规中心内创建自定义的反网络钓鱼策略将同时创建反钓鱼规则和关联的反钓鱼策略：将二者的同一名称用于两者。

在创建反网络钓鱼策略时，只能指定策略名称、描述和用于标识向其应用策略的收件人筛选器。 创建此策略后，可以修改该策略以更改或查看默认的防钓鱼设置。

1. 在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。

2. 在"**反网络钓鱼"页上，** 单击"创建 **"。**

3. 将 **打开"创建新的反网络钓鱼** 策略向导"。 在" **命名策略"** 页面上，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

   完成后，单击“下一步”****。

4. 在 **显示的"** 已应用到"页上，确定向其应用策略的内部收件人。

   只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   单击 **"添加条件"。** 在出现的下拉列表中，选择"已应用"下面的条件 **（如果出现该条件：）**

   - **收件人是**：指定您所在组织的一个或多个邮箱、邮件用户或邮件联系人。
   - **收件人为以下组的成员**：指定您所在组织的一个或多个组。
   - **收件人域是**：指定你的组织中配置的一个或多个接受的域中的收件人。

   选择条件后，将出现相应的下拉列表，其中有一个 **其中任何一个** 框。

   - 在框中单击，然后滚动要选择的值列表。
   - 单击此框，然后开始键入以筛选列表并选择一个值。
   - 若要添加其他值，请在框中的空白区域单击。
   - 若要删除各个条目，请单击该值 **上的** ![ " ](../../media/scc-remove-icon.png) 删除"图标。
   - 若要删除整个条件，请单击条件 **上的** ![ " ](../../media/scc-remove-icon.png) 删除"图标。

   要添加其他条件，请单击" **添加一个条件"，** 并在"应用时"下选择其 **余值**。

   要添加例外，请单击" **添加一个条件"，** 并在"除非"时 **选择例外情况**。 设置和行为与条件完全相同。

   完成后，单击“下一步”****。

5. 在" **查看显示的** 设置"页上，查看你的设置。 可以单击每个 **设置** 上的"编辑"以修改每个设置。

   完成后，请单击"创建**此策略"。**

6. 在 **出现** 的确认对话框中，单击"确定"。

在使用这些常规策略设置创建反网络钓鱼策略之后，请使用下一节中的说明来配置策略中的保护设置。

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies"></a>使用安全&与网络钓鱼策略

使用以下过程修改反网络钓鱼策略：已创建的新策略或已自定义的现有策略。

1. 如果你尚不在该位置，请打开安全与&合规中心，并转到 **威** \> **胁** \> **管理策略防钓鱼**。

2. 选择要修改的自定义反网络钓鱼策略。 如果已经选中，请取消选中它，然后重新选择它。

3. 此**时将显示" \<name\> **编辑策略"浮出控件。 单击任何 **部分** 中的"编辑"可访问该节中的设置。

   - 以下步骤按节显示的顺序显示，但它们不是一次性步骤 (您可以选择和修改这些部分，而无需按顺序) 。

   - 单击部分**中的"编辑**"后，可用设置将以向导格式显示，但可以按任意顺序跳转到页面内，并且你可以在任一页面上单击"**保存**"或" (取消"**或"** 关闭"图标**Close** ![ ](../../media/scc-remove-icon.png) ** \<name\> **以返回到"编辑策略"页面 (而无需访问向导的最后一页来保存或离开) 。

4. **策略设置**：单击 **"** 编辑"可修改与您在上一 [部分创建策略时](#use-the-security--compliance-center-to-create-anti-phishing-policies) 可用的设置相同的设置：

   - **名称**
   - **说明**
   - **应用于**
   - **查看你的设置**

   完成后，在任何页面上单击" **保存** "。

5. **欺骗**： **单击"编辑** "可打开或关闭欺骗智能，打开或关闭 Outlook 中的未经身份验证的发件人标识，以及将操作配置为应用于来自受阻止的欺骗性发件人的邮件。 有关详细信息，请参阅 [反网络钓鱼策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

   请注意，ATP 防钓鱼策略中也提供这些相同的设置。

   - **欺骗性筛选设置**：默认值是 **"打开"，** 建议将其保持为开。 若要将其关闭，请将切换开关滑动到 **"关闭"。** 有关详细信息，请参阅在 [EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > 如果你的 MX 记录不指向 Microsoft 365，则无需禁用反欺骗保护;改为启用连接器的增强筛选功能。 有关说明，请参阅["增强的 Exchange Online 中的连接器筛选"。](https://docs.microsoft.com/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **启用未经身份验证的**发件人功能：默认值是**On。** 若要将其关闭，请将切换开关滑动到 **"关闭"。**

   - **操作**： 指定要对未通过欺骗智能的邮件采取的操作：

     **如果电子邮件是由不允许欺骗你的域的人发送的**：

     - **将邮件移动到收件人的垃圾邮件文件夹**
     - **隔离邮件**

   - **查看你的设置**：设置显示在摘要中，而不是单击每个单独的步骤。

     - 您可以单击 **每个** 部分中的"编辑"以跳转到相关页面。
     - 可以直接在此页上**打开****或关闭**以下设置：

       - **启用防欺骗保护**
       - **启用未经身份验证的发件人功能**

   完成后，在任何页面上单击" **保存** "。

6. 返回到"编辑**策略" \<Name\> 页面**，查看设置，然后单击"关闭 **"。**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy"></a>使用安全与&网络中心修改默认防钓鱼策略

默认的反网络钓鱼策略名为"Office365 AntiPhish Default"，但不显示在策略列表中。 若要修改默认防钓鱼策略，请执行以下步骤：

1. 在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。

2. 在"**防网络钓鱼"页上，** 单击"默认**策略"。**

3. 此 **时将显示"编辑 Office365 防钓鱼 Default"** 页面。 以下部分均可用，它包含修改自定义策略时 [的相同设置](#use-the-security--compliance-center-to-modify-anti-phishing-policies)。

   - **模拟**
   - **Spoof**
   - **高级设置**

   修改默认策略时，以下设置不可用：

   - 您可以看到" **策略设置"** 部分和值，但是没有 **编辑链接** ，因此不能修改设置 (策略名称、描述以及该策略适用于 (的人员（) 例如) ）。
   - 不能删除默认策略。
   - 不能更改默认策略的优先级， (始终在上次应用的) 。

4. 在"**编辑策略 Office365 防钓鱼默认'** 页面上，查看你的设置，然后单击"关闭 **"。**

### <a name="enable-or-disable-custom-anti-phishing-policies"></a>启用或禁用自定义防钓鱼策略

1. 在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。

2. 请注意"状态" **列中的** 值：

   - 将切换开关滑 **动到** "关闭"可禁用此策略。

   - 将切换按钮滑 **动到"** 启用"以启用策略。

无法禁用默认防钓鱼策略。

### <a name="set-the-priority-of-custom-anti-phishing-policies"></a>设置自定义反网络钓鱼策略的优先级

默认情况下，反网络钓鱼策略根据在策略创建顺序来获得 (新策略的优先级低于旧策略创建) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

自定义的反网络钓鱼策略按处理它们时 (第一个策略的优先级值为 0 **) 。** 名为"Office365 AntiPhish Default"的默认反网络钓鱼策略的自定义优先级值 **"最低**"，你无法更改它。

 **注意**：在&合规性中心内，只能在创建后更改防钓鱼策略的优先级。 在 PowerShell 中，可在创建反网络钓鱼规则时 (它会影响现有规则的优先级) 。

要更改策略的优先级，请单击**策略**属性中的"提高优先级"或**Decrease priority**"减少优先级 (无法直接修改安全 & 合规中心) 中的优先级) 。 **Priority** 仅当你有多个策略时，更改策略的优先级也有任何作用。

1. 在安全与&中心内，转到 **威** \> **胁管理** \> **策略 ATP 防钓鱼**。

2. 选择要修改的策略。 如果已经选中，请取消选中它，然后重新选择它。

3. 此**时将显示" \<name\> **编辑策略"浮出控件。

   - 优先级值为 0 的自定义反网络**钓鱼****策略**只有 **"减少优先级"按钮**可用。

   - 优先级值较低的自定义反网络钓鱼 (例如 **，3** **Priority**) 保留策略只有"增加**优先级"** 按钮可用。

   - 如果你有三个或更多个自定义防钓鱼策略，则最高优先级和最低优先级值之间的策略会具有"增加优先级"**和****"减少优先级**"按钮。

4. 单击 **"提高优先级****"或"减少优先级"以**更改**优先级**值。

5. 完成后，单击“关闭”****。

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies"></a>使用安全与&策略查看反网络钓鱼策略

1. 在安全与&中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。

2. 采取以下步骤之一：

   - 选择要查看的自定义反网络钓鱼策略。 如果已经选中，请取消选中它，然后重新选择它。

   - 单击 **"** 默认策略"以查看默认的预钓鱼策略。

3. "**编辑策略 \<name\> **"浮出控件，可在其中查看设置和值。

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies"></a>使用安全与&中心可以删除防钓鱼策略

1. 在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。

2. 选择要删除的策略。 如果已经选中，请取消选中它，然后重新选择它。

3. 在随**即显示 \<name\> **的策略浮出控件中，单击 **"删除策略**"，然后在**出现**的警告对话框中单击"是"。

无法删除默认策略。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies"></a>使用 Exchange Online PowerShell 配置防钓鱼策略

如前所述，反垃圾邮件策略由一个反网络钓鱼策略和一个反网络钓鱼规则提供。

在 Exchange Online PowerShell 中，防钓鱼策略和反网络钓鱼规则之间的区别明显。 您可以使用** \* -AntiPhishPolicy** cmdlet 管理反钓鱼策略，并且可以通过** \* 使用 -AntiPhishRule** cmdlet 管理反钓鱼规则。

- 在 PowerShell 中，先创建反钓鱼策略，然后再创建反网络钓鱼规则，以标识将向其应用的策略。
- 在 PowerShell 中，分别修改防钓鱼策略和防钓鱼规则中的设置。
- 从 PowerShell 删除反网络钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦而是。

> [!NOTE]
> 使用 Exchange Online Protection PowerShell 无法在独立 EOP 组织中执行下列 PowerShell 过程。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>使用 PowerShell 创建反网络钓鱼策略

在 PowerShell 中创建防钓鱼策略的过程分为两步：

1. 创建反钓鱼策略。
2. 创建反网络钓鱼规则，以指定该规则将应用于的反网络钓鱼策略。

 **注意**：

- 可以创建新的反钓鱼规则并向它分配现有的未关联的反钓鱼策略。 一个反网络钓鱼规则不能与多个反网络钓鱼策略关联。

- 在创建策略之前，可以在 PowerShell 中配置新反钓鱼策略的以下设置，以防安全 & 合规中心内未提供：

  - 为禁用状态中心 (对_Enabled_ `$false` **New-AntiPhishRule cmdlet 策略列表启用) 。**
  - Set the priority of the policy during creation (_Priority_ _\<Number\>_) on the **New-AntiPhishRule** cmdlet) .

- 在 PowerShell 中创建的新反网络钓鱼策略在安全 & 合规中心内不可见，除非你将策略分配到反钓鱼规则。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>步骤 1：使用 PowerShell 创建反钓鱼策略

若要创建反网络钓鱼策略，请使用以下语法：

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] [-EnableAntiSpoofEnforcement <$true | $false>] [-AuthenticationFailAction <MoveToJmf | Quarantine>] [-EnableUnauthenticatedSender <$true | $false>]
```

本示例使用以下设置创建名为"研究隔离"的防钓鱼策略：

- 启用策略时 (没有使用 _Enabled 参数_ ，默认值为 `$true`) 。
- 该说明是：研究部门策略。
- 将欺骗的默认操作更改为隔离。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -AuthenticationFailAction Quarantine
```

有关语法和参数的详细信息，请参阅[New-AntiPhishPolicy。](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishPolicy)

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>步骤 2：使用 PowerShell 创建反网络钓鱼规则

若要创建反网络钓鱼规则，请使用以下语法：

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

本示例创建名为"研究部门"的反网络钓鱼规则，规则为以下条件：

- 此规则与名为"研究隔离"的反网络钓鱼策略相关联。
- 此规则应用于“研究部门”组中的成员。
- 因为我们没有使用 _Priority 参数_ ，因此使用默认优先级。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>使用 PowerShell 查看反网络钓鱼策略

若要查看现有的反网络钓鱼策略，请使用以下语法：

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

此示例返回所有反钓鱼策略的摘要列表以及指定的属性。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

此示例返回名为"Executives"的防钓鱼策略的所有属性值。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

有关语法和参数的详细信息，请参阅[Get-AntiPhishPolicy。](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishPolicy)

### <a name="use-powershell-to-view-anti-phish-rules"></a>使用 PowerShell 查看反网络钓鱼规则

若要查看现有的反网络钓鱼规则，请使用以下语法：

```PowerShell
Get-AntiPhishRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

本示例返回所有防钓鱼规则的摘要列表以及指定的属性。

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

本示例返回名为"Contoso Executives"的防钓鱼规则的所有属性值。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>使用 PowerShell 修改防钓鱼策略

除了以下项目之外，在 PowerShell 中修改反钓鱼策略时可用的设置，与在步骤 1 中创建策略时可用的设置相同，如本主题前面的步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建反网络钓鱼策略部分。

- The _MakeDefault_ switch that turns the specified policy into the default policy (applied to everyone， **alwaysest** priority， and you can't delete it) is only available when you modify an anti-phish policy in PowerShell.

- 无法在 **Set-AntiPhishPolicy** cmdlet 没有 _name_ 参数 (重命名反网络钓鱼策略) 。 在安全中心中重命名防钓 &鱼策略时，你仅将重命名反网络钓鱼 _规则_。

若要修改反网络钓鱼策略，请使用以下语法：

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅[Set-AntiPhishPolicy。](https://docs.microsoft.com/powershell/module/exchange/Set-AntiPhishPolicy)

### <a name="use-powershell-to-modify-anti-phish-rules"></a>使用 PowerShell 修改防钓鱼规则

在 PowerShell 中修改反钓鱼规则时，唯一不可用的设置 _是可以_ 创建已禁用规则的 Enabled 参数。 若要启用或禁用现有的反网络钓鱼规则，请参阅下一节。

否则，在 PowerShell 中修改反钓鱼规则时，将无法使用其他设置。 创建规则时可用的设置，与 [步骤 2：使用 PowerShell 创建本主题](#step-2-use-powershell-to-create-an-anti-phish-rule) 前面介绍的反网络钓鱼规则部分时可用的设置相同。

若要修改反网络钓鱼规则，请使用以下语法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>使用 PowerShell 启用或禁用防钓鱼规则

在 PowerShell 中启用或禁用防钓鱼规则会启用或禁用整个防钓鱼策略 (以及分配的反网络钓鱼策略) 。 您无法启用或禁用默认的反网络钓鱼策略 (所有收件人都将始终应用于所有) 。

若要在 PowerShell 中启用或禁用防钓鱼规则，请使用以下语法：

```PowerShell
<Enable-AntiPhishRule | Disable-AntiPhishRule> -Identity "<RuleName>"
```

本示例禁用名为"Marketing Department"的防钓鱼规则。

```PowerShell
Disable-AntiPhishRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-AntiPhishRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Enable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/enable-AntiPhishrule) 和 [Disable-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/disable-AntiPhishrule)。

### <a name="use-powershell-to-set-the-priority-of-anti-phish-rules"></a>使用 PowerShell 设置防钓鱼规则的优先级

可以设置的规则最高优先级值是 0。 可以设置的最小优先级值取决于规则的数量。 例如，如果有五个规则，则可以使用的优先级值为 0 到 4。 更改现有规则的优先级可对其他规则产生级联效应。 例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。

若要在 PowerShell 中设置反钓鱼规则的优先级，请使用以下语法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" -Priority <Number>
```

下面的示例将名为“Marketing Department”的规则的优先级设置为 2。 优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。

```PowerShell
Set-AntiPhishRule -Identity "Marketing Department" -Priority 2
```

**注意**：

- 若要在创建新规则时设置它的优先级，请对**New-AntiPhishRule** cmdlet 使用_Priority_参数。

- 默认的防钓鱼策略没有相应的防钓鱼规则，且始终具有不可修改的优先级值 **"最低"。**

### <a name="use-powershell-to-remove-anti-phish-policies"></a>使用 PowerShell 删除防钓鱼策略

使用 PowerShell 删除反网络钓鱼策略时，不会删除相应的反钓鱼规则。

若要在 PowerShell 中删除防钓鱼策略，请使用以下语法：

```PowerShell
Remove-AntiPhishPolicy -Identity "<PolicyName>"
```

本示例将删除名为 Marketing Department 的防钓鱼策略。

```PowerShell
Remove-AntiPhishPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[Remove-AntiPhishPolicy。](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishPolicy)

### <a name="use-powershell-to-remove-anti-phish-rules"></a>使用 PowerShell 删除防钓鱼规则

使用 PowerShell 删除防钓鱼规则时，不会删除相应的反钓鱼策略。

若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

本示例删除名为"Marketing Department"的防钓鱼规则。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](https://docs.microsoft.com/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证是否已成功配置 ATP 防钓鱼策略，请执行以下任意步骤：

- 在安全与 &合规中心内，转到 **威** \> **胁** \> **管理策略反网络钓鱼**。 验证策略列表、其 **状态** 值及其 **优先级** 值。 若要查看更多详细信息，请执行以下步骤之一：

  - 从列表中选择该策略，并在浮出控件中查看详细信息。
  - 单击 **"默认** 策略"并在浮出控件中查看详细信息。

- 在 Exchange Online PowerShell 中 \<Name\> ，将策略或规则的名称替换为策略或规则，并运行以下命令并验证设置：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```
