---
title: 在 Microsoft Defender for Office 365
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
description: 管理员可以了解如何创建、修改和删除 Microsoft Defender for Office 365 组织提供的高级防钓鱼Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1c8d61aee9afb332a8426890560ad221a9c87c7d
ms.sourcegitcommit: 8685b0f7d53c99577fa65144ab60295dfa60f46f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51218779"
---
# <a name="configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

Microsoft Defender for [Office 365](defender-for-office-365.md)中的反网络钓鱼策略可帮助保护组织免受基于恶意模拟的网络钓鱼攻击和其他类型的网络钓鱼攻击。 有关 Exchange Online Protection (EOP) 中的反网络钓鱼策略与 Microsoft Defender for Office 365 中的防钓鱼策略之间的差异，请参阅反网络钓鱼[防护](anti-phishing-protection.md)。

管理员可以查看、编辑和配置 (，但不能) 默认的防钓鱼策略。 更精细地来说，您还可以创建适用于组织中特定用户、组或域的自定义防钓鱼策略。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

您可以在安全与合规中心或 PowerShell &反网络钓鱼Exchange Online策略。

有关在 Exchange Online Protection 组织 (（即没有 Microsoft Defender for Office 365) 的组织）中可用的反网络钓鱼策略配置更多限制的信息，请参阅在[EOP](configure-anti-phishing-policies-eop.md)中配置防钓鱼策略。

防钓鱼策略的基本元素包括：

- **防钓鱼策略**：指定要启用或禁用的网络钓鱼防护，以及应用选项的操作。
- **防钓鱼** 规则 ：指定策略应用于 (策略的收件人筛选器) 策略的优先级和收件人筛选器。

在安全与合规中心内管理防钓鱼策略时，这两个元素&不明显：

- 创建策略时，实际上是同时使用同一名称创建防钓鱼规则和相关防钓鱼策略。
- 修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改防钓鱼规则。 所有其他设置修改关联的防钓鱼策略。
- 删除策略时，将删除防钓鱼规则和相关反钓鱼策略。

在 Exchange Online PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文稍后介绍Exchange Online [PowerShell](#use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365)在 Microsoft Defender for Office 365中配置防钓鱼策略一节。

每个 Microsoft Defender for Office 365 组织都有一个名为 Office365 AntiPhish Default 的内置防钓鱼策略，该策略具有以下属性：

- 即使与策略关联的收件人筛选器没有反网络钓鱼规则， (应用于组织) 所有收件人。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略始终具有更高的优先级。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

若要提高 Microsoft Defender for Office 365 中的防钓鱼保护的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义防钓鱼策略。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **ATP 防钓鱼页面** ，请使用 <https://protection.office.com/antiphishing> 。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要添加、修改和删除防钓鱼策略，你需要是组织管理或安全 **管理员角色****组** 的成员。
  - 若要对防钓鱼策略进行只读访问，你需要是全局读者或 **安全读者角色****组的成员** <sup>\*</sup> 。

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：

  - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - 此 **策略中的**"仅查看组织管理"角色 [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups)还授予对该功能的只读访问权限 <sup>\*</sup> 。
  - <sup>\*</sup> 在安全&合规中心，只读访问允许用户查看自定义防钓鱼策略的设置。 只读用户看不到默认防钓鱼策略中的设置。

- 有关 Microsoft Defender for Office 365 中的反网络钓鱼策略建议设置，请参阅 Defender 中的反网络钓鱼策略，了解Office 365[设置](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。

- 最多允许应用新策略或更新策略 30 分钟。

- 有关反网络钓鱼策略在筛选管道中的应用位置的信息，请参阅电子邮件保护的顺序 [和优先级](how-policies-and-protections-are-combined.md)。

## <a name="use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>使用安全&合规中心在 Microsoft Defender for Office 365

在安全与合规中心内创建自定义防钓鱼策略&使用相同的名称同时创建防钓鱼规则和相关防钓鱼策略。

创建防钓鱼策略时，只能指定策略名称、说明和收件人筛选器，以标识策略的适用者。 创建策略后，可以修改该策略以更改或查看默认的防钓鱼设置。

1. 在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。

2. 在"**防钓鱼"页上，** 单击"创建 **"。**

3. 将 **打开"创建新的防钓鱼策略"** 向导。 在" **命名策略"** 页上，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

   完成后，单击“下一步”。

4. 在 **出现的"应用于** "页上，标识策略应用于的内部收件人。

   只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   单击 **"添加条件"。** In the dropdown that appears， select a condition under **Applied if**：

   - **收件人为**：指定您的组织中的一个或多个邮箱、邮件用户或邮件联系人。
   - **收件人是 ：指定** 组织中一个或多个组的成员。
   - **收件人域为**：指定组织中一个或多个已配置的接受域中的收件人。

   选择条件后，将显示相应的下拉列表，其中显示其中 **任何** 一个框。

   - 在框中单击并滚动要选择的值列表。
   - 在框中单击并开始键入以筛选列表并选择一个值。
   - 若要添加其他值，请单击框中的空白区域。
   - 若要删除单个条目，请单击值 **上的"** ![ 删除 ](../../media/scc-remove-icon.png) ""删除"图标。
   - 若要删除整个条件，请单击条件 ![ 上的"删除 ](../../media/scc-remove-icon.png) ""删除"图标。

   若要添加其他条件，请单击" **添加条件** "，然后选择"应用的条件 **"下的其余值**。

   若要添加例外，请单击" **添加条件"，** 然后选择"例外条件 **"下的例外**。 设置和行为与条件完全相同。

   完成后，单击“下一步”。

5. 在出现的 **"查看设置** "页上，查看设置。 可以单击每个 **设置** 上的"编辑"来修改它。

   完成后，单击"创建 **此策略"。**

6. 在 **出现的** 确认对话框中单击"确定"。

使用这些常规设置创建防钓鱼策略后，请使用下一节中的说明配置策略中的保护设置。

## <a name="use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>使用安全&合规中心修改 Microsoft Defender for Office 365

使用以下过程可修改防钓鱼策略：您创建的新策略或已自定义的现有策略。

1. 如果尚未开始，请打开安全与合规&， **然后转到威胁** 管理 \> **策略** \> **ATP 防钓鱼**。

2. 选择要修改的自定义防钓鱼策略。 如果已选择，请取消选择它，然后再次选择它。

3. 将显示 **"编辑策略 \<name\>**"飞出控件。 单击 **任何** 部分中的"编辑"，即可访问该部分中的设置。

   - 以下步骤按各节的显示顺序显示，但它们不是按顺序 (您可以按任意顺序选择和修改) 。

   - 在部分中单击"编辑"后，可用设置以向导格式显示，但您可以按任意顺序跳转到页面内，并且您可以单击任何页面的"保存" (或 ![ ](../../media/scc-remove-icon.png) **\<name\>**"取消"或"关闭"图标返回到"编辑策略"页面 (无需访问向导的最后一页即可保存或离开) 。

4. **策略设置****：单击**"编辑"修改在上一部分中创建 [策略时可用的](#use-the-security--compliance-center-to-create-anti-phishing-policies-in-microsoft-defender-for-office-365)相同设置：

   - **名称**
   - **说明**
   - **应用于**
   - **查看设置**

   完成后，单击任意 **页面上** 的"保存"。

5. **模拟**：单击 **"** 编辑"修改策略中的受保护的发件人和受保护的域。 这些设置是策略的一个条件，用于标识欺骗性发件人，以单独 (或按域) 入站邮件的发件人地址查找邮件。 有关详细信息，请参阅 Microsoft Defender for Office 365 中的防钓鱼[策略中的模拟Office 365。](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **添加要保护的用户**：默认值为 **Off**。 若要将其打开，将切换开关滑动到 **"开**"，然后单击出现的 **"添加用户** "按钮。

     在出现的 **"添加** 用户"飞出中，配置以下值：

     - **电子邮件地址**：

       - 在框中单击并滚动浏览要选择的用户列表。
       - 在框中单击并开始键入以筛选列表并选择用户。
       - 若要删除条目，请单击 **用户上的"** ![ ](../../media/scc-remove-icon.png) 删除"图标。

     - **名称**：此值将基于你选择的电子邮件地址进行填充，但你可以更改它。

     完成后，单击任意 **页面上** 的"保存"。

     若要编辑现有条目，请在列表中选择受保护的用户。

     > [!NOTE]
     >
     > - 在每个防钓鱼策略中，最多可指定 60 个受保护 (发件人电子邮件地址) 。 不能在多个策略中指定同一受保护的用户。
     >
     > - 如果发件人和收件人之前通过电子邮件进行通信，则用户模拟保护不起作用。 如果发件人和收件人从未通过电子邮件进行通信，则邮件将被标识为模拟尝试。

   - **添加要保护的域**：配置以下一个或两个设置：

     - **自动包含我拥有的域**：默认值为 **Off**。 若要将其打开，将切换开关滑动到 **开**。
     - **包含自定义域**：默认值为 **Off**。 若要将其打开，将开关滑动到 **"** 开"，在"添加域"框中，输入域名 (例如 contoso.com) ，按 Enter，然后根据需要重复。

     > [!NOTE]
     > 在所有防钓鱼策略中最多可以有 50 个域。

   - **操作**：单击 **"编辑"**

     - **如果电子邮件由** 模拟用户发送：为欺骗性发件人是添加要保护的用户中指定的受保护用户之一的邮件配置以下操作 **之一**：

       - **不应用任何操作**
       - **将邮件重定向到其他电子邮件地址**
       - **将邮件移动到"垃圾邮件"文件夹**
       - **隔离邮件**
       - **传递邮件，将其他地址添加到"Bcc"行**
       - **在邮件传递之前删除邮件**

     - **如果电子邮件是由** 模拟域发送的：为欺骗性发件人位于你在添加要保护的域中指定的其中一个受保护的域的邮件配置以下操作 **之一**：

       - **不应用任何操作**
       - **将邮件重定向到其他电子邮件地址**
       - **将邮件移动到"垃圾邮件"文件夹**
       - **隔离邮件**
       - **传递邮件，将其他地址添加到"Bcc"行**
       - **在邮件传递之前删除邮件**

   - 单击 **"打开模拟安全提示"** 并配置以下任一设置：

     - **显示模拟用户的提示**：默认值为 **Off**。 若要将其打开，将切换开关滑动到 **开**。
     - **显示模拟域的提示**：默认值为 **Off**。 若要将其打开，将切换开关滑动到 **开**。
     - **显示异常字符的提示**：默认值为 **Off**。 若要将其打开，将切换开关滑动到 **开**。

     完成后，单击“**保存**”。

   - **邮箱智能**：

     - **启用邮箱智能？：** 默认值为 **On。** 若要关闭它，将切换开关滑动到 **关闭**。

     - **启用基于邮箱智能的模拟保护？：** 此设置仅在启用 **邮箱智能时可用？** 为 **On**。 打开此设置可指定对邮件执行的操作，以从邮箱智能结果进行模拟检测。

       在 **"** 如果电子邮件由模拟用户发送"中，可以指定以下操作之一 (保护用户和受保护的域可执行) ：

       - **不要应用任何操作**：请注意，此值与启用邮箱智能具有相同的结果 **？但关闭** 启用基于邮箱 **智能的模拟保护？。**
       - **将邮件重定向到其他电子邮件地址**
       - **将邮件移动到"垃圾邮件"文件夹**
       - **隔离邮件**
       - **传递邮件，将其他地址添加到"Bcc"行**
       - **在邮件传递之前删除邮件**

   - **添加受信任的发件人和域**：指定策略的例外：

     - **受信任的发件人**：

       - 在框中单击并滚动浏览要选择的用户列表。
       - 在框中单击并开始键入以筛选列表并选择用户。
       - 若要删除条目，请单击 **用户上的"** ![ ](../../media/scc-remove-icon.png) 删除"图标。

     - **受信任的域**：输入域名 (例如，contoso.com) 按 Enter，然后根据需要重复。

   - **查看设置**：设置会显示在摘要中，而不是单击每个单独的步骤。

     - 可以单击每个 **部分** 中的"编辑"跳转回相关页面。
     - 您可以直接在此页面上切换以下设置 **：打开****或关闭**：

       - **受保护的用户**
       - **受保护的域** \>**包含我拥有域**
       - **受保护的域** \>**受保护的域 (** 自定义域) 
       - **邮箱智能**

   完成后，单击任意 **页面上** 的"保存"。

6. **欺骗**：单击"编辑"打开或关闭欺骗智能，在 Outlook 中打开或关闭未经身份验证的发件人标识，并配置操作以应用于来自被阻止的欺骗发件人的邮件。 有关详细信息，请参阅反网络钓鱼 [策略中的欺骗设置](set-up-anti-phishing-policies.md#spoof-settings)。

   请注意，EOP 中的防钓鱼策略中也提供了这些相同的设置。

   - **欺骗筛选器设置**：默认值为 **"开**"，建议保持打开状态。 若要关闭它，将切换开关滑动到 **关闭**。 有关详细信息，请参阅在 [EOP 中配置欺骗智能](learn-about-spoof-intelligence.md)。

     > [!NOTE]
     > 如果你的 MX 记录没有指向任何位置，你无需禁用反欺骗Microsoft 365;改为启用连接器的增强筛选。 有关说明，请参阅[增强的连接器筛选Exchange Online。](/Exchange/mail-flow-best-practices/use-connectors-to-configure-mail-flow/enhanced-filtering-for-connectors)

   - **启用未经身份验证的发件人功能**：默认值为 **On**。 若要关闭它，将切换开关滑动到 **关闭**。

   - **操作**：指定对未通过欺骗智能的邮件采取的操作：

     **如果电子邮件是由不允许欺骗你的域的人发送的**：

     - **将邮件移动到收件人的"垃圾邮件"文件夹**
     - **隔离邮件**

   - **查看设置**：设置会显示在摘要中，而不是单击每个单独的步骤。

     - 可以单击每个 **部分** 中的"编辑"跳转回相关页面。
     - 您可以直接在此页面上切换以下设置 **：打开****或关闭**：
       - **启用反应答保护**
       - **启用未经身份验证的发件人功能**

   完成后，单击任意 **页面上** 的"保存"。

7. **高级设置**：单击 **"** 编辑"以配置高级网络钓鱼阈值。 有关详细信息，请参阅 Microsoft Defender for Office 365 中的反网络钓鱼策略[中的高级网络钓鱼Office 365。](set-up-anti-phishing-policies.md#advanced-phishing-thresholds-in-anti-phishing-policies-in-microsoft-defender-for-office-365)

   - **高级网络钓鱼阈值**：选择下列值之一：

   - **1 - 标准** (此值为默认值。) 
   - **2 - 主动**
   - **3 - 更主动**
   - **4 - 最积极**

   - **查看设置：** 单击 **"编辑** "跳转回 **"高级网络钓鱼阈值"** 页面。

   完成后，单击任一 **页面上的"** 保存"。

8. 返回到"**编辑策略"页面 \<Name\>**，查看设置，然后单击"关闭 **"。**

### <a name="use-the-security--compliance-center-to-modify-the-default-anti-phishing-policy-in-microsoft-defender-for-office-365"></a>使用安全&合规中心修改 Microsoft Defender for Office 365

Microsoft Defender for Office 365 中的默认防钓鱼策略名为"Office365 反钓鱼默认策略"，它不会显示在策略列表中。 若要修改默认的防钓鱼策略，请执行以下步骤：

1. 在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。

2. 在"**反网络钓鱼"页上**，单击"**默认策略"。**

3. 将显示 **"编辑你的策略 Office365 反语言默认"** 页。 以下部分可用，其中包含修改自定义策略 [时相同的设置](#use-the-security--compliance-center-to-modify-anti-phishing-policies-in-microsoft-defender-for-office-365)：

   - **模拟**
   - **欺骗**
   - **高级设置**

   修改默认策略时，以下设置不可用：

   - You can see the **Policy setting section** and values， but there's no **Edit** link， so you can't modify the settings (policy name， description， and who the policy applies to (it applies to all recipients) ) .
   - 不能删除默认策略。
   - 你无法更改默认策略的优先级 (它始终在上次应用) 。

4. 在"**编辑策略 Office365 反默认** 策略"页上，查看设置，然后单击"关闭 **"。**

### <a name="enable-or-disable-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender 中为用户启用或禁用自定义防钓鱼Office 365

1. 在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。

2. 请注意"状态" **列中** 的值：

   - 将开关滑动到 **"关闭"** 以禁用该策略。

   - 将切换开关滑动 **到"打开** "以启用策略。

无法禁用默认的防钓鱼策略。

### <a name="set-the-priority-of-custom-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>在 Microsoft Defender for Office 365 中设置自定义防钓鱼策略Office 365

默认情况下，基于反网络钓鱼策略在 (较旧策略中创建的顺序，反网络钓鱼策略的优先级低于较旧策略) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

有关优先级顺序以及如何评估和应用多个策略的详细信息，请参阅[电子邮件保护的顺序和优先级](how-policies-and-protections-are-combined.md)。

自定义防钓鱼策略按照其处理顺序显示， (策略的优先级值为 0) 。  名为"Office365 反钓鱼默认"的默认防钓鱼策略具有自定义优先级值 **"** 最低"，你无法更改它。

 **注意**：在安全&合规中心，只能在创建后更改反网络钓鱼策略的优先级。 在 PowerShell 中，您可以在创建反网络钓鱼规则策略时替代默认优先级 (这可能会影响现有规则集的) 。

若要更改策略的优先级，请单击策略属性中的"增加优先级"或"减少优先级 (你无法直接修改安全与合规中心&优先级) 。  更改策略的优先级仅在有多个策略时有意义。

1. 在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。

2. 选择要修改的策略。 如果已选择，请取消选择它，然后再次选择它。

3. 将显示 **"编辑策略 \<name\>**"飞出控件。

   - 优先级值为 **0** 的自定义防钓鱼策略仅具有"**减少优先级"** 按钮。

   - 优先级值最低的自定义防钓鱼策略 (例如 **，3**) 只有"增加优先级 **"** 按钮可用。

   - 如果你有三个或多个自定义防钓鱼策略，则优先级最高的值和最低优先级值之间的策略同时具有"增加优先级"和"**减少优先级"** 按钮。

4. 单击 **"增加优先级** " **或"减少优先级** "可更改 **"优先级"** 值。

5. 完成后，单击“关闭”。

## <a name="use-the-security--compliance-center-to-view-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>使用安全&中心查看 Microsoft Defender for Office 365

1. 在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。

2. 采取以下步骤之一：

   - 选择要查看的自定义防钓鱼策略。 如果已选择，请取消选择它，然后再次选择它。

   - 单击 **"默认** 策略"以查看默认的防钓鱼策略。

3. 将出现 **"编辑策略 \<name\>**"飞出控件，可在其中查看设置和值。

## <a name="use-the-security--compliance-center-to-remove-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>使用安全&合规中心删除 Microsoft Defender for Office 365

1. 在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。

2. 选择要删除的策略。 如果已选择，请取消选择它，然后再次选择它。

3. 在出现的 **"编辑策略 \<name\>**"飞出控件中，单击"删除策略"，然后在出现的警告对话框中单击"是"。

无法删除默认策略。

## <a name="use-exchange-online-powershell-to-configure-anti-phishing-policies-in-microsoft-defender-for-office-365"></a>使用 Exchange Online PowerShell 在 Microsoft Defender for Office 365

如前所述，反垃圾邮件策略由反网络钓鱼策略和反网络钓鱼规则组成。

在 Exchange Online PowerShell 中，防钓鱼策略和防钓鱼规则的区别显而易见。 您可以使用 **\* -AntiPhishPolicy** cmdlet 管理防钓鱼策略，使用 **\* -AntiPhishRule** cmdlet 管理反钓鱼规则。

- 在 PowerShell 中，首先创建防钓鱼策略，然后创建标识该规则所适用的策略的防钓鱼规则。
- 在 PowerShell 中，分别修改反钓鱼策略和反钓鱼规则中的设置。
- 从 PowerShell 删除防钓鱼策略时，不会自动删除相应的反网络钓鱼规则，反之亦然。

### <a name="use-powershell-to-create-anti-phishing-policies"></a>使用 PowerShell 创建防钓鱼策略

在 PowerShell 中创建防钓鱼策略的过程包括两个步骤：

1. 创建防钓鱼策略。
2. 创建指定该规则所适用的防钓鱼策略的防钓鱼规则。

 **注意**：

- 你可以创建新的防钓鱼规则，并为其分配现有的未关联的反网络钓鱼策略。 反网络钓鱼规则不能与多个防钓鱼策略关联。

- 可以在 PowerShell 中的新防钓鱼策略上配置以下设置，这些设置在创建策略之前&安全与合规中心内不可用：

  - 在 `$false` **New-AntiPhishRule** cmdlet (上创建禁用的新策略) 。
  - 在 _\<Number\>_ **New-AntiPhishRule** cmdlet cmdlet (中) 策略的优先级) 。

- 在安全与合规中心内看不到在 PowerShell 中创建的新防钓鱼策略&策略分配给防钓鱼规则。

#### <a name="step-1-use-powershell-to-create-an-anti-phish-policy"></a>步骤 1：使用 PowerShell 创建防钓鱼策略

若要创建防钓鱼策略，请使用以下语法：

```PowerShell
New-AntiPhishPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

本示例将创建名为"Research Quarantine"的防钓鱼策略，并具有以下设置：

- 如果策略 (_Enabled_ 参数，则启用该策略，默认值为 `$true`) 。
- 描述为：研究部门策略。
- 针对所有接受的域启用组织域保护，为组织域启用目标域 fabrikam.com。
- 指定一 (mfujito@fabrikam.com) 用户的身份进行保护，防止模拟。
- 启用邮箱智能。
- 启用邮箱智能保护，并指定隔离操作。
- 启用安全提示。

```powershell
New-AntiPhishPolicy -Name "Monitor Policy" -AdminDisplayName "Research department policy" -EnableOrganizationDomainsProtection $true -EnableTargetedDomainsProtection $true -TargetedDomainsToProtect fabrikam.com -TargetedDomainProtectionAction Quarantine -EnableTargetedUserProtection $true -TargetedUsersToProtect "Mai Fujito;mfujito@fabrikam.com" -TargetedUserProtectionAction Quarantine -EnableMailboxIntelligence $true -EnableMailboxIntelligenceProtection $true -MailboxIntelligenceProtectionAction Quarantine -EnableSimilarUsersSafetyTips $true -EnableSimilarDomainsSafetyTips $true -EnableUnusualCharactersSafetyTips $true
```

有关语法和参数的详细信息，请参阅 [New-AntiPhishPolicy](/powershell/module/exchange/New-AntiPhishPolicy)。

#### <a name="step-2-use-powershell-to-create-an-anti-phish-rule"></a>步骤 2：使用 PowerShell 创建防钓鱼规则

若要创建防钓鱼规则，请使用以下语法：

```PowerShell
New-AntiPhishRule -Name "<RuleName>" -AntiPhishPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

本示例创建一个名为"Research Department"的防钓鱼规则，并满足以下条件：

- 该规则与名为"研究隔离"的防钓鱼策略相关联。
- 此规则应用于“研究部门”组中的成员。
- 因为我们没有使用 _Priority_ 参数，所以使用默认优先级。

```powershell
New-AntiPhishRule -Name "Research Department" -AntiPhishPolicy "Research Quarantine" -SentToMemberOf "Research Department"
```

有关语法和参数的详细信息，请参阅 [New-AntiPhishRule](/powershell/module/exchange/New-AntiPhishRule)。

### <a name="use-powershell-to-view-anti-phish-policies"></a>使用 PowerShell 查看防钓鱼策略

若要查看现有的防钓鱼策略，请使用以下语法：

```PowerShell
Get-AntiPhishPolicy [-Identity "<PolicyIdentity>"] [| <Format-Table | Format-List> <Property1,Property2,...>]
```

此示例返回所有防钓鱼策略的摘要列表以及指定的属性。

```PowerShell
Get-AntiPhishPolicy | Format-Table Name,IsDefault
```

此示例返回名为 Executives 的反网络钓鱼策略的所有属性值。

```PowerShell
Get-AntiPhishPolicy -Identity "Executives"
```

有关语法和参数的详细信息，请参阅 [Get-AntiPhishPolicy](/powershell/module/exchange/Get-AntiPhishPolicy)。

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

此示例返回名为 Contoso Executives 的防钓鱼规则的所有属性值。

```PowerShell
Get-AntiPhishRule -Identity "Contoso Executives"
```

有关语法和参数的详细信息，请参阅 [Get-AntiPhishRule](/powershell/module/exchange/Get-AntiPhishrule)。

### <a name="use-powershell-to-modify-anti-phish-policies"></a>使用 PowerShell 修改防钓鱼策略

除了以下项目外，在 PowerShell 中修改防钓鱼策略时可用的设置与创建策略时相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-anti-phish-policy) 创建防钓鱼策略一节中所述。

- _MakeDefault_ 开关将指定策略转换为应用于所有人的默认策略 (，优先级始终最低，并且只有修改 PowerShell 中的防钓鱼策略时) 才能将其删除。

- 如果 **Set-AntiPhishPolicy** cmdlet 没有 Name 参数 (，则不能重命名反网络钓鱼) 。  在安全与合规中心内重命名防钓鱼&，只需重命名防钓鱼 _规则_。

要修改防钓鱼策略，请使用以下语法：

```PowerShell
Set-AntiPhishPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-AntiPhishPolicy](/powershell/module/exchange/Set-AntiPhishPolicy)。

### <a name="use-powershell-to-modify-anti-phish-rules"></a>使用 PowerShell 修改防钓鱼规则

在 PowerShell 中修改反网络钓鱼规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有防钓鱼规则，请参阅下一节。

否则，在 PowerShell 中修改防钓鱼规则时，其他设置将不可用。 创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-anti-phish-rule) 创建防钓鱼规则一节中所述的设置相同。

要修改防钓鱼规则，请使用以下语法：

```PowerShell
Set-AntiPhishRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-AntiPhishRule](/powershell/module/exchange/set-antiphishrule)。

### <a name="use-powershell-to-enable-or-disable-anti-phish-rules"></a>使用 PowerShell 启用或禁用防钓鱼规则

在 PowerShell 中启用或禁用反网络钓鱼规则可启用或禁用整个防钓鱼策略 (以及分配的防钓鱼策略策略) 。 无法启用或禁用默认反网络钓鱼策略 (该策略始终应用于所有) 。

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

有关语法和参数的详细信息，请参阅[Enable-AntiPhishRule](/powershell/module/exchange/enable-antiphishrule)和[Disable-AntiPhishRule。](/powershell/module/exchange/disable-antiphishrule)

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

- 默认防钓鱼策略没有对应的防钓鱼规则，并且始终具有不可修改的优先级值 **Lowest**。

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

有关语法和参数的详细信息，请参阅 [Remove-AntiPhishPolicy](/powershell/module/exchange/Remove-AntiPhishPolicy)。

### <a name="use-powershell-to-remove-anti-phish-rules"></a>使用 PowerShell 删除防钓鱼规则

使用 PowerShell 删除防钓鱼规则时，不会删除相应的防钓鱼策略。

若要在 PowerShell 中删除防钓鱼规则，请使用以下语法：

```PowerShell
Remove-AntiPhishRule -Identity "<PolicyName>"
```

此示例删除名为 Marketing Department 的防钓鱼规则。

```PowerShell
Remove-AntiPhishRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-AntiPhishRule](/powershell/module/exchange/Remove-AntiPhishRule)。

## <a name="how-do-you-know-these-procedures-worked"></a>如何判断这些过程生效了？

若要验证您是否已成功在 Microsoft Defender for Office 365配置防钓鱼策略，请执行以下步骤之一：

- 在安全&中心，转到威胁 **管理** \> **策略** \> **ATP 防钓鱼**。 验证策略列表、 **策略的 Status** 值及其 **Priority** 值。 若要查看更多详细信息，请执行下列任一步骤：

  - 从列表中选择策略，并查看该飞出内容中的详细信息。
  - 单击 **"默认** 策略"，在飞出视图中查看详细信息。

- 在 Exchange Online PowerShell 中，将 替换为策略或规则的名称，然后运行 \<Name\> 以下命令并验证设置：

  ```PowerShell
  Get-AntiPhishPolicy -Identity "<Name>"
  ```

  ```PowerShell
  Get-AntiPhishRule -Identity "<Name>"
  ```