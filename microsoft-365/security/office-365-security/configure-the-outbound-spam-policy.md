---
title: 配置出站垃圾邮件筛选
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在迁移 EOP 组织中的 Exchange Online Protection 中查看、创建、修改和删除 (垃圾邮件) 。
ms.openlocfilehash: 530c1af9b7802be6073f19331ce7f6a20bdb2668
ms.sourcegitcommit: 260bbb93bbda62db9e88c021ccccfa75ac39a32e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/21/2020
ms.locfileid: "46845974"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>在 EOP 中配置出站垃圾邮件筛选

在没有 Exchange Online 邮箱的 Microsoft 365 组织中，或在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，通过 EOP 发送的出站电子邮件将自动检查垃圾邮件和异常发送活动。

来自您组织中用户的出站垃圾邮件通常表示帐户被入入入。 无论垃圾邮件可信度或 SCL) ，可疑的出站邮件标记为垃圾邮件 (，并通过 [高风险](high-risk-delivery-pool-for-outbound-messages.md) 传送池进行路由，以帮助保护服务的信誉 (即使 Microsoft 365 源电子邮件服务器不使用 IP 阻止列表) 。 管理员自动通过警报策略通知可疑出站电子邮件活动和阻止 [的用户](../../compliance/alert-policies.md)。

EOP 使用出站垃圾邮件策略作为组织对垃圾邮件的整体防御的一部分。 有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。

管理员可以查看、编辑和配置默认 (出站垃圾邮件) 删除这些操作。 您也可以创建应用于组织中特定用户、组或域的自定义出站垃圾邮件策略，以进行更细分。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

可以在安全 & 合规中心或在具有 Exchange Online 邮箱的 Microsoft 365 (组织中使用 Exchange Online 的 PowerShell 配置出站垃圾邮件策略;没有 Exchange Online 邮箱策略的组织独立的 EOP) 。

EOP 中出站垃圾邮件策略的基本要部分是：

- **出站垃圾邮件筛选**策略：指定出站垃圾邮件筛选顶点和通知选项的操作。
- **出站垃圾邮件筛选规则**：指定向出站垃圾邮件筛选策略 (应用策略的) 筛选器。

在安全电子邮件合规性中心管理出站垃圾邮件策略时，这两个要点两&的区别&不可行：

- 创建策略时，实际上是对二者使用相同的名称同时创建出站垃圾邮件筛选规则和关联的出站垃圾邮件筛选策略。
- 修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置会修改出站垃圾邮件筛选规则。 其他所有设置会修改关联的出站垃圾邮件筛选策略。
- 当您删除策略时，出站垃圾邮件筛选规则及相关的出站垃圾邮件筛选策略都将删除。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本主题 [后面的"使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 垃圾邮件策略"部分。

每个组织都有名为"默认"的内置出站垃圾邮件策略，其属性为：

- 策略会应用于组织中的所有收件人，即使没有与此策略相关联的 (站垃圾邮件筛选器) 收件人筛选器。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略的优先级始终高于名为“默认”的策略。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

为了提高出站垃圾邮件筛选的有效性，您可以创建自定义出站垃圾邮件策略，它包含应用于特定用户或用户组的更严格设置。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 你必须首先分配有权限，然后才能执行本主题中的步骤：

  - 必须是下列角色之一的成员，才能添加、修改和删除出站垃圾邮件策略：

    - [安全和合规中心](permissions-in-the-security-and-compliance-center.md)中的“**组织管理**”或“**安全管理员**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**组织管理**”或“**清洁管理**”。

  - 对于出站垃圾邮件策略的只读访问权限，您需要是以下角色组之一的成员：

    - [安全与合规中心](permissions-in-the-security-and-compliance-center.md)内的“**安全读取者**”。
    - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的“**仅查看组织管理**”。

- 有关建议的出站垃圾邮件策略设置，请参阅 [EOP 出站垃圾邮件筛选器策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。

- 默认[警报策略](../../compliance/alert-policies.md)**"电子邮件发送限制已超出限制"、** 检测到的可疑**电子邮件**发送模式，**以及被限制**发送** (的**"**已存在对于出**站垃圾邮件"活动以及出站) 垃圾邮件而被阻止用户发送电子邮件的用户。 有关详细信息，请参阅" [验证受限的用户的警报"设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 建议在出站垃圾邮件策略中使用这些警报策略，而不要使用通知选项。

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>使用"安全性&中心"创建出站垃圾邮件策略

在安全 & 合规中心内创建自定义出站垃圾邮件策略会同时创建垃圾邮件筛选规则和关联的垃圾邮件筛选策略，并对二者使用相同的名称。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在"**反垃圾邮件设置"** 页面上，单击"**创建出站策略"。**

3. 在打开 **的出站垃圾邮件** 筛选策略浮出控件中，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

4.  (可选) **扩展"** 选项"部分配置应接收可疑出站电子邮件的副本和通知的其他用户：

   - **向特定人员发送可疑出站电子邮件**副本：此设置将指定用户作为"Bcc"收件人添加到可疑出站邮件。

     > [!NOTE]
     > 此设置仅适用于默认出站垃圾邮件策略。 它不能在您创建的自定义出站垃圾邮件策略中正常工作。

     若要启用此设置：

     1. 选中此复选框以启用该设置。

     1. 单击 **"添加人员"。** 在" **添加或删除出现** 下列内容的收件人"浮出控件中：

     1. 输入发件人的电子邮件地址。 可以指定多个电子邮件地址，中用分号分隔 (;) 换行一个收件人。

     1. 单击 ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 添加收件人。

        根据需要重复执行这些步骤（次数不限）。

        你添加的收件人显示在浮 **出控件上的** 收件人列表部分中。 若要删除收件人，请单击"删除 ![ "按钮 ](../../media/scc-remove-icon.png) 。

     1. 完成时，请单击“保存”****。

        若要禁用此设置，请清除此复选框。

   - **发件人由于发送出站垃圾邮件而被阻止时通知特定人员**：

     > [!IMPORTANT]
     >
     > - 此设置的过程中会弃用出站垃圾邮件策略。
     >
     > - 由于 [因"收件人](../../compliance/alert-policies.md) 限制 **"部分中的** 限制被阻止而被阻止时，"用户被限制发送至 TenantAdmins (全局管理员) "组成员，默认警报策略"用户"策略"受限制"向 **TenantAdmins** (**Global Admins**) **组成员发送电子邮件** 通知。 强烈建议您在出站垃圾邮件策略中使用该提醒策略而**非在出站垃圾邮件策略中进行此设置，以通知管理员和其他用户**。 有关说明，请参阅["验证受限的用户的警报设置"。](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)

5.  (可选) 展开 **"收件人** 限制"部分以配置可疑出站电子邮件的限制和操作：

   > [!NOTE]
   > 这些设置仅适用于基于云的邮箱。

   - **每个用户的最大收件人数**

     有效值为 0 至 10000。 默认值为 0，表示使用服务默认值。 有关详细信息，请参阅 [发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

     - **外部每小时限制**：每小时外部收件人的最大数量限制。

     - **内部每小时限制**：每小时的内部收件人的最大数量限制。

     - **每日限制：** 每天的最大收件人总数。

   - **当用户超过上述限制时执行下列操作**：配置超出任何一个收件人限制 **时要采取** 的操作。 对于所有操作，在"**被限制发送**电子邮件"提醒策略 (以及现在，如果出站垃圾邮件策略中发送出站**Notify specific people if a sender is blocked due to sending outbound spam**垃圾邮件设置而被阻止，则在冗余的冗余通知中指定的收件人发送电子邮件通知，

     - **限制用户向以下一天发送邮件**：这是默认值。 系统会发送电子邮件通知，用户将无法基于 UTC 时间在第二天内发送其他任何邮件。 管理员无法覆盖此阻止。

       - 名为" **用户"的活动提醒** ，已阻止通过电子邮件 (和"查看 **提醒"页面上** 收到) 。

       - 如果由于发送了策略 **中的出站垃圾邮件设置而** 阻止发件人，则在"通知特定人员"中指定的任何收件人也会收到通知。

       - 用户将无法根据 UTC 时间在第二天内发送其他任何信息。 管理员无法覆盖此阻止。

     - **限制用户发送邮件**：发送电子邮件通知，用户会被添加到安全 & 合规**中心的[受限 <https://sip.protection.office.com/restrictedusers> 用户]** 门户，并且用户无法发送电子邮件，直至管理员从"受限**的用户"** 门户将其删除为"管理员从列表中删除用户后，该用户在当天不会受到限制。 有关说明，请参阅 [发送垃圾邮件后从受限用户门户删除用户](removing-user-from-restricted-users-portal-after-spam.md)。

     - **无操作，仅提醒**：发送电子邮件通知。

6.  (可选) **展开自动转发** "部分来控制用户对外部发件人的自动电子邮件转发。 有关自动转发的详细信息，请参阅配置 [电子邮件转发](https://docs.microsoft.com/microsoft-365/admin/email/configure-email-forwarding)。

   > [!NOTE]
   >
   > - 2020 年 9 月之前，这些设置将提供，但不是强制实施。
   >
   > - 这些设置仅适用于基于云的邮箱。
   >
   > - 此设置不影响自动转发给内部收件人。

   可用值有：

   - **自动 - 系统控制：允许**出站垃圾邮件筛选控制自动外部电子邮件转发。 此值为默认值。

   - **启用**：策略不会禁用自动外部电子邮件转发。

   - **关闭**：策略禁用所有自动外部电子邮件转发。

7.  (") 展开" **应用到"** 部分，以确定向其应用策略的内部发件人。

    只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<sender1\>_ 或 _\<sender2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<sender1\>_ 和 _\<member of group 1\>_）。

    若要查看所有可配置的条件，最简单的方法是单击 **“添加条件”** 三次。 若要删除不需要配置的条件，可以单击 ![“删除”按钮](../../media/scc-remove-icon.png)。

    - **发件人域是**：指定组织中一个或多个配置的接受域中的发件人。 单击 **“添加标记”** 框，以查看并选择域。 如果有多个域，请再次单击 **“添加标记”** 框来选择其他域。

    - **发件人是**：指定您的组织中一个或多个用户。 单击 **“添加标记”**，然后开始键入内容来筛选列表。 请再次单击 **"添加标记** "框，选择其他发件人。

    - **发件人为以下组的成员**：指定您所在组织的一个或多个组。 单击 **“添加标记”**，然后开始键入内容来筛选列表。 请再次单击 **"添加标记** "框，选择其他发件人。

    - **下列情况除外**：若要添加规则的例外情况，请单击 **“添加条件”** 三次，以查看所有可配置的例外。 设置和行为与条件完全相同。

8. 完成后，单击 **“保存”**。

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>使用安全与&合规中心查看出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在" **反垃圾邮件设置"页面上** ，单击" ![ 展开" ](../../media/scc-expand-icon.png) 图标可展开出站垃圾邮件策略：

   - 名为"出站 **垃圾邮件筛选策略"的默认策略**。

   - 您创建的自定义策略，其中"类型"**列中的值为**"**自定义出站垃圾邮件策略"。**

3. 策略设置显示在出现的展开策略详细信息中，或者可以单击"编辑策略 **"。**

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>使用安全&合规中心修改出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在" **反垃圾邮件设置"页面上** ，单击" ![ 展开" ](../../media/scc-expand-icon.png) 图标可展开出站垃圾邮件策略：

   - 名为"出站 **垃圾邮件筛选策略"的默认策略**。

   - 您创建的自定义策略，其中"类型"**列中的值为**"**自定义出站垃圾邮件策略"。**

3. 单击 **“编辑策略”**。

对于自定义出站垃圾邮件策略，显示的浮出控件中的可用设置与使用安全 & 合规中心创建出站 [垃圾邮件策略部分中介绍的可用设置完全](#use-the-security--compliance-center-to-create-outbound-spam-policies) 相同。

对于默认的出站垃圾邮件策略 **（名为"出站垃圾邮件筛选**策略"）使用 **"** 应用到"部分 (无法选择该策略应用于每个用户) ，且无法重命名此策略。

若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。

### <a name="enable-or-disable-outbound-spam-policies"></a>启用或禁用出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在"**反垃圾邮件设置"页面上**，单击" ![ 展开" ](../../media/scc-expand-icon.png) 图标展开已创建的自定义策略 ("类型"**列中的**值为"**自定义出站垃圾邮件策略") 。**

3. 在随即显示的展开策略详细信息中，注意 **“开”** 列中的值。

   将切换开关移动到左侧可禁用策略： ![切换开关关闭](../../media/scc-toggle-off.png)

   将切换开关移动到右侧可启用策略： ![切换开关打开](../../media/963dfcd0-1765-4306-bcce-c3008c4406b9.png)

不能禁用默认出站垃圾邮件策略。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>设置自定义出站垃圾邮件策略的优先级

默认情况下，出站垃圾邮件策略根据在新策略中创建的顺序来获得优先级，而 (新策略的优先级低于早先策略的) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

自定义出站垃圾邮件策略按处理它们的顺序显示 (第一个策略的 **优先级值为** 0) 。 名为"出站垃圾邮件筛选 **策略"的默认出站垃圾邮件** 策略的优先级值为 **"最低**"，无法更改。

若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在"**反垃圾邮件设置"** 页面中，查找"类型"列中的值为"自定义**出站****垃圾邮件策略"的策略**。 注意 **“优先级”** 列中的值：

   - 优先级最高的自定义出站垃圾邮件策略的"向下箭 ![ 头"图标为 ](../../media/ITPro-EAC-DownArrowIcon.png) **0。**

   - 优先级最低的自定义出站垃圾邮件策略的"向上箭 ![ 头"图标 ](../../media/ITPro-EAC-UpArrowIcon.png) ** (** 例如，向上箭 ![ 头图标 ](../../media/ITPro-EAC-UpArrowIcon.png) **3**) 。

   - 如果您有三个或更多个自定义出站垃圾邮件策略，则最高优先级和最低优先级之间的策略的值为值"向上箭头"图标 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **n** (例如，"向下箭头"图标 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**) 。

3. 单击 ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) 或 ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) 在优先级列表中上移或下移自定义出站垃圾邮件策略。

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>使用安全与&中心删除出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在" **反垃圾邮件设置"页面上** ，单击 ![ "展开" ](../../media/scc-expand-icon.png) 图标展开要删除的自定义策略 ** ("类型"** 列是" **自定义出站垃圾邮件策略** ") 。

3. 在随即显示的展开策略详细信息中，单击 **“删除策略”**。

4. 在随即显示的警告对话框中，单击 **“是”**。

无法删除默认策略。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站垃圾邮件策略

如前所述，出站垃圾邮件策略由出站垃圾邮件筛选策略和出站垃圾邮件筛选规则提供。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，出站垃圾邮件筛选策略与出站垃圾邮件筛选规则之间的区别显而然。 您可以使用** \* -HostedOutboundSpamFilterPolicy cmdlet 管理出站垃圾邮件筛选器**策略，您可以使用** \* -HostedOutboundSpamFilterRule cmdlet 管理出站垃圾邮件**筛选器规则。

- 在 PowerShell 中，先创建出站垃圾邮件筛选策略，然后创建出站垃圾邮件筛选规则，以标识向应用此规则的策略。
- 在 PowerShell 中，分别修改出站垃圾邮件筛选策略和出站垃圾邮件筛选规则中的设置。
- 从 PowerShell 删除出站垃圾邮件筛选策略时，不会自动删除相应的出站垃圾邮件筛选规则，反之亦不行。

### <a name="use-powershell-to-create-outbound-spam-policies"></a>使用 PowerShell 创建出站垃圾邮件策略

在 PowerShell 中创建出站垃圾邮件策略的过程分为两步：

1. 创建出站垃圾邮件筛选策略。
2. 创建出站垃圾邮件筛选规则，它可指定该规则应用于的出站垃圾邮件筛选策略。

 **注意**：

- 您可以新建一个出站垃圾邮件筛选规则，并向其分配未关联的现有出站垃圾邮件筛选策略。 出站垃圾邮件筛选规则不能与多个出站垃圾邮件筛选策略相关联。

- 您可以在 PowerShell 中对新的出站垃圾邮件筛选策略配置以下设置（在安全 & 合规中心内，直至创建策略后，才能配置这些设置：）

  - 在_Enabled_ `$false` **New-HostedOutboundSpamFilterRule cmdlet 服务器上 (启用对已禁用的新**) 。
  - 在创建策略期间 _ (，_ 要) _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet) 邮箱设置优先级) 。

- 在 PowerShell 中创建的新出站垃圾邮件筛选策略在安全 & 合规中心内不可见，除非您将策略分配到垃圾邮件筛选规则。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>第 1 步：使用 PowerShell 创建出站垃圾邮件筛选器策略

若要创建出站垃圾邮件筛选策略，请使用以下语法：

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

本示例将使用以下设置创建名为"Contoso Executives"的新出站垃圾邮件筛选策略：

- 收件人速率限制限于小于默认值。 有关详细信息，请参阅 Microsoft [365 中的发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。

- 达到其中一个限制后，将阻止用户发送邮件。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

若要详细了解语法和参数，请参阅[New-HostedOutboundSpamFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>第 2 步：使用 PowerShell 创建出站垃圾邮件筛选规则

若要创建出站垃圾邮件筛选规则，请使用以下语法：

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

下面的示例使用以下设置新建名为"Contoso Executives"的出站垃圾邮件筛选规则：

- 名为"Contoso Executives"的出站垃圾邮件筛选策略与此规则关联。

- 此规则应用于“Contoso Executives Group”组中的成员。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

若要详细了解语法和参数，请参阅[New-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>使用 PowerShell 查看出站垃圾邮件筛选策略

若要返回所有出站垃圾邮件筛选策略的摘要列表，请运行以下命令：

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

若要返回有关特定出站垃圾邮件筛选策略的详细信息，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

本示例返回名为"Executives"的出站垃圾邮件筛选策略的所有属性值。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

若要详细了解语法和参数，请参阅[Get-HostedOutboundSpamFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>使用 PowerShell 查看出站垃圾邮件筛选规则

若要查看现有出站垃圾邮件筛选规则，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>] [-State <Enabled | Disabled]
```

若要返回所有出站垃圾邮件筛选规则的摘要列表，请运行以下命令：

```PowerShell
Get-HostedOutboundSpamFilterRule
```

若要按已启用或已禁用规则筛选列表，请运行以下命令：

```PowerShell
Get-HostedOutboundSpamFilterRule -State Disabled
```

```PowerShell
Get-HostedOutboundSpamFilterRule -State Enabled
```

若要返回特定出站垃圾邮件筛选规则的详细信息，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

本示例返回名为"Contoso Executives"的出站垃圾邮件筛选规则的所有属性值。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

有关语法和参数的详细信息，请参阅[Get-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>使用 PowerShell 修改出站垃圾邮件筛选器策略

在 PowerShell 中修改恶意软件筛选策略时可用的设置与您创建策略时可用的设置相同，如本主题前面部分所述 [：使用 PowerShell 创建本主题前面部分](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 的出站垃圾邮件筛选策略部分。

> [!NOTE]
> 无法在 **Set-HostedOutboundSpamFilterPolicy** cmdlet 没有 _Name_ 参数 (重命名出站垃圾邮件筛选器) 。 在安全中心中重命名出站 &垃圾邮件策略时，只是重命名出站垃圾邮件筛选 _规则_。

若要修改出站垃圾邮件筛选策略，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

若要详细了解语法和参数，请参阅["Set-HostedOutboundSpamFilterPolicy"。](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>使用 PowerShell 修改出站垃圾邮件筛选规则

在 PowerShell 中修改出站垃圾邮件筛选规则时，唯一不可用的设置 _是可以_ 创建已禁用规则的 Enabled 参数。 若要启用或禁用现有出站垃圾邮件筛选规则，请参阅下一部分。

否则，在 PowerShell 中修改出站垃圾邮件筛选规则时，将无法使用其他任何设置。 创建规则时可用的设置，与步骤 [2：使用 PowerShell 创建本主题前面部分中](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 介绍的出站垃圾邮件筛选规则部分相同。

若要修改出站垃圾邮件筛选规则，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

若要详细了解语法和参数，请参阅 [Set-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>使用 PowerShell 启用或禁用出站垃圾邮件筛选规则

在 PowerShell 中启用或禁用出站垃圾邮件筛选规则会启用或禁用整个出站垃圾邮件策略 (出站垃圾邮件筛选规则和分配的出站垃圾邮件筛选策略) 。 您无法启用或禁用默认出站垃圾邮件策略， (它始终应用于包含该邮件的) 。

若要在 PowerShell 中启用或禁用出站垃圾邮件筛选规则，请使用以下语法：

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

本示例禁用名为"Marketing Department"的出站垃圾邮件筛选规则。

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

若要详细了解语法和参数，请参阅 [Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 和 [Disable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>使用 PowerShell 设置出站垃圾邮件筛选规则的优先级

可以设置的规则最高优先级值是 0。 可以设置的最小优先级值取决于规则的数量。 例如，如果有五个规则，则可以使用的优先级值为 0 到 4。 更改现有规则的优先级可对其他规则产生级联效应。 例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。

若要在 PowerShell 中设置出站垃圾邮件筛选规则的优先级，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

下面的示例将名为“Marketing Department”的规则的优先级设置为 2。 优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - 若要在创建新规则时设置它的优先级，请改为对**New-HostedOutboundSpamFilterRule** cmdlet 使用_Priority_参数。
>
> - 出站默认垃圾邮件筛选策略没有相应的垃圾邮件筛选规则，且始终有不可修改的优先级值 **"最低"。**

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>使用 PowerShell 删除出站垃圾邮件筛选器策略

当您使用 PowerShell 删除出站垃圾邮件筛选策略时，不会删除相应的出站垃圾邮件筛选规则。

若要在 PowerShell 中删除出站垃圾邮件筛选策略，请使用以下语法：

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

本示例删除名为"Marketing Department"的出站垃圾邮件筛选策略。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

若要详细了解语法和参数，请参阅[Remove-HostedOutboundSpamFilterPolicy。](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>使用 PowerShell 删除出站垃圾邮件筛选规则

使用 PowerShell 删除出站垃圾邮件筛选规则时，不会删除相应的出站垃圾邮件筛选策略。

若要在 PowerShell 中删除出站垃圾邮件筛选规则，请使用以下语法：

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

本示例删除名为"Marketing Department"的出站垃圾邮件筛选规则。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

若要详细了解语法和参数，请参阅[Remove-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)

## <a name="for-more-information"></a>详细信息

[从“受限的用户”门户中删除被阻止的用户](removing-user-from-restricted-users-portal-after-spam.md)

[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[反垃圾邮件保护常见问题](anti-spam-protection-faq.md)

[自动转发的消息报告](mfi-auto-forwarded-messages-report.md)
