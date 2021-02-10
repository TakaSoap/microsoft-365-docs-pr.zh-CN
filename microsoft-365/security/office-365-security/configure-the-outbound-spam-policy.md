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
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何查看、创建、修改和删除 Exchange Online Protection (EOP) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 6b7ba1e398466c448de37060db340c1d20cb1504
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165759"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>在 EOP 中配置出站垃圾邮件筛选

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用于**
- [Exchange Online Protection](https://go.microsoft.com/fwlink/?linkid=2148611)
- [Microsoft Defender for Office 365 计划 1 和计划 2](https://go.microsoft.com/fwlink/?linkid=2148715)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

在具有 Exchange Online 邮箱或独立 Exchange Online Protection (EOP) 组织的 Microsoft 365 组织中，通过 EOP 发送的出站电子邮件将自动检查垃圾邮件和异常发送活动。

来自组织中用户的出站垃圾邮件通常指示帐户遭到入侵。 无论垃圾邮件可信度或 SCL) 如何，可疑出站邮件都会标记为垃圾邮件 (并通过高风险传递池进行路由，以帮助保护[](high-risk-delivery-pool-for-outbound-messages.md)服务 (的信誉，即使 Microsoft 365 源电子邮件服务器从 IP 阻止列表) 中排除。 管理员将自动收到可疑的出站电子邮件活动通知，并且通过警报策略 [阻止用户](../../compliance/alert-policies.md)。

EOP 使用出站垃圾邮件策略作为组织对垃圾邮件的整体防御的一部分。 有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。

管理员可以查看、编辑和配置 (，但不能删除) 出站垃圾邮件策略。 更具体一点，您还可以创建自定义出站垃圾邮件策略，这些策略适用于组织中特定用户、组或域。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

您可以在 &安全与合规中心或 PowerShell (Exchange Online PowerShell 中为在 Exchange Online 中拥有邮箱的 Microsoft 365 组织配置出站垃圾邮件策略;适用于没有 Exchange Online 邮箱的组织的独立 EOP PowerShell) 。

EOP 中出站垃圾邮件策略的基本元素包括：

- **出站垃圾邮件筛选策略**：指定出站垃圾邮件筛选裁定和通知选项的操作。
- **出站垃圾邮件筛选器** 规则：指定策略应用于 (发件人的优先级和收件人筛选器) 出站垃圾邮件筛选器策略的优先级和收件人筛选器。

在安全与合规中心内管理出站垃圾邮件策略时，这两个元素&不明显：

- 创建策略时，实际上是同时使用同一名称创建出站垃圾邮件筛选器规则和相关出站垃圾邮件筛选器策略。
- 修改策略时，与名称、优先级、已启用或禁用以及收件人筛选器相关的设置将修改出站垃圾邮件筛选器规则。 所有其他设置修改关联的出站垃圾邮件筛选器策略。
- 删除策略时，将删除出站垃圾邮件筛选器规则和相关出站垃圾邮件筛选器策略。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文稍后介绍的"使用 Exchange Online PowerShell 或独立 [EOP PowerShell 配置出站](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies) 垃圾邮件策略"部分。

每个组织都有一个名为 Default 的内置出站垃圾邮件策略，该策略具有以下属性：

- 即使与策略关联的收件人筛选器没有出站垃圾邮件筛选规则，该 (应用于组织) 所有收件人。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略的优先级始终高于名为“默认”的策略。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

若要提高出站垃圾邮件筛选的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义出站垃圾邮件策略。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 安全与合规中心的打开网址为 <https://protection.office.com/>。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://protection.office.com/antispam>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 必须分配有 Office 365 安全与合规中心内的权限，才能执行本文中的步骤：
  - 若要添加、修改和删除出站垃圾邮件策略，您必须是组织 **管理或****安全** 管理员角色组的成员。
  - 对于出站垃圾邮件策略的只读访问，你需要是全局读者或安全 **读者角色组** 的成员。 

  有关详细信息，请参阅 [安全与合规中心的权限](permissions-in-the-security-and-compliance-center.md)。

  **注意**：

  - 向 Microsoft 365 管理中心相应的 Azure 活动目录添加用户会向其提供安全与合规中心的必备权限 _以及_ Microsoft 365其它功能的权限。 有关详细信息，请参阅 [关于管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)。
  - [Exchange Online](https://docs.microsoft.com/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关针对出站垃圾邮件策略的建议设置，请参阅 [EOP 出站垃圾邮件筛选器策略设置](recommended-settings-for-eop-and-office365-atp.md#eop-outbound-spam-policy-settings)。

- 名为"电子邮件发送限制"的默认警报策略已超出"检测到可疑电子邮件发送模式"和"限制发送电子邮件的用户"已向 **TenantAdmins** (全局管理员 **)** 组的成员发送电子邮件通知，这些通知有关异常的出站电子邮件活动和因出站垃圾邮件而阻止的用户。 [](../../compliance/alert-policies.md) 有关详细信息，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 我们建议您使用这些警报策略，而不是出站垃圾邮件策略中的通知选项。

## <a name="use-the-security--compliance-center-to-create-outbound-spam-policies"></a>使用安全&合规中心创建出站垃圾邮件策略

在安全与合规中心内创建自定义出站垃圾邮件&将同时使用同一名称创建垃圾邮件筛选规则和相关垃圾邮件筛选器策略。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **"反垃圾邮件设置**"页上，单击 **"创建出站策略"。**

3. 在 **随即打开** 的出站垃圾邮件筛选器策略中，配置以下设置：

   - **名称**：输入策略的唯一描述性名称。

   - **说明**：输入策略的可选说明。

4.  (可选) 展开"通知"部分以配置应接收可疑出站电子邮件的副本和通知的其他用户：

   - **向特定人员发送** 可疑出站电子邮件的副本：此设置将指定用户添加为可疑出站邮件的"Bcc 收件人"。

     > [!NOTE]
     > 此设置仅适用于默认出站垃圾邮件策略。 它不在创建的自定义出站垃圾邮件策略中工作。

     若要启用此设置，

     1. 选中此复选框可启用该设置。

     1. 单击 **"添加人员"。** 在 **出现的"添加或删除收件人"** 飞出中：

     1. 输入发件人的电子邮件地址。 可以指定多个电子邮件地址，用分号分隔; () 一个收件人。

     1. 单击 ![添加图标](../../media/c2dd8b3a-5a22-412c-a7fa-143f5b2b5612.png) 添加收件人。

        根据需要重复执行这些步骤（次数不限）。

        您添加的收件人显示在飞出 **上的** "收件人列表"部分。 若要删除收件人，请单击" ![ 删除"按钮 ](../../media/scc-remove-icon.png) 。

     1. 完成后，单击“**保存**”。

        若要禁用此设置，请清除该复选框。

   - 如果发件人因发送出站垃圾邮件被阻止 **，请通知特定人员**：

     > [!IMPORTANT]
     >
     > - 此设置正在从出站垃圾邮件策略中弃用。
     >
     > - 当用户 [](../../compliance/alert-policies.md)因超出"收件人限制"部分的限制被阻止时，名为"限制发送电子邮件的用户"的默认警报策略已经向 **TenantAdmins** **(** 全局管理员) 组的成员发送电子邮件通知。  **我们强烈建议你** 使用警报策略，而不是出站垃圾邮件策略中的此设置来通知管理员和其他用户。 有关说明，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。

5.  (可选) 展开 **"收件人限制** "部分以配置可疑出站电子邮件的限制和操作：

   > [!NOTE]
   > 这些设置仅适用于基于云的邮箱。

   - **每个用户的最大收件人数**

     有效值为 0 到 10000。 默认值为 0，表示使用服务默认值。 有关详细信息，请参阅发送 [限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

     - **外部每小时限制**：每小时的最大外部收件人数。

     - **内部每小时限制**：每小时内部收件人的最大数量。

     - **每日限制**：每天的最大收件人总数。

   - **用户超过上述** 限制时的操作：配置当超过任何一个收件人 **限制时要** 执行的操作。 对于所有操作，如果用户由于发送出站垃圾邮件策略中的出站垃圾邮件设置而被阻止，则"用户"中指定的收件人将限制其发送电子邮件提醒策略 (以及现在冗余的"通知特定人员"，以接收电子邮件通知。

     - **限制用户发送邮件，直到第二天**：这是默认值。 将发送电子邮件通知，用户将无法发送任何其他邮件，直到第二天，基于 UTC 时间。 管理员无法覆盖此阻止。

       - 名为"用户 **被** 限制发送电子邮件"的活动警报会 (通知管理员，并通知管理员在"查看警报" **页上**) 。

       - 如果发件人因在策略中发送出站垃圾邮件设置而被阻止，则通知特定人员中指定的任何收件人也会收到通知。

       - 用户将无法发送任何其他消息，直到第二天，基于 UTC 时间。 管理员无法覆盖此阻止。

     - 限制用户发送邮件：发送电子邮件通知，将用户添加到安全 & 合规中心中的[受限用户 **] <https://sip.protection.office.com/restrictedusers>** 门户，并且用户无法发送电子邮件，直到管理员从受限用户门户中删除他们。 管理员从列表中删除用户后，该天不会再次限制该用户。 有关说明，请参阅发送垃圾邮件后从 [受限用户门户删除用户](removing-user-from-restricted-users-portal-after-spam.md)。

     - **无操作，仅警报**：发送电子邮件通知。

6.  (可选 **) 展开"** 自动转发"部分，以控制用户向外部发件人自动转发电子邮件。 有关详细信息，请参阅 [Microsoft 365 中的控制自动外部电子邮件转发](external-email-forwarding.md)。

   > [!NOTE]
   >
   > - 在 2020 年 9 月之前，这些设置可用，但不强制执行。
   >
   > - 这些设置仅适用于基于云的邮箱。
   >
   > - 禁用自动转发后，如果外部发件人将电子邮件发送到已就地转发的邮箱 (则收件人将收到未送达报告) 也称为 NDR 或退回邮件。 如果邮件由内部发件人发送，并且转发方法是邮箱转发 (也称为 [](https://docs.microsoft.com/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding)_SMTP_ 转发) ，则内部发件人将获取 NDR。 如果转发由于收件箱规则而发生，则内部发件人不会收到 NDR。

   可用值有：

   - **自动 - 系统控制**：允许出站垃圾邮件筛选控制自动外部电子邮件转发。 此值为默认值。
   - **On**： 策略不会禁用自动外部电子邮件转发。
   - **关闭**：策略禁用所有自动外部电子邮件转发。

7.  (必需) 展开"应用于"部分以标识策略所适用的内部发件人。

    只能使用一次条件或例外，但可以为条件或例外指定多个值。 同一个条件或例外的多个值使用“或”逻辑（例如，_\<sender1\>_ 或 _\<sender2\>_）。 不同的条件或例外使用“和”逻辑（例如，_\<sender1\>_ 和 _\<member of group 1\>_）。

    若要查看所有可配置的条件，最简单的方法是单击 **“添加条件”** 三次。 若要删除不需要配置的条件，可以单击 ![“删除”按钮](../../media/scc-remove-icon.png)。

    - **发件人域为**：指定组织中一个或多个已配置的接受域中的发件人。 单击 **“添加标记”** 框，以查看并选择域。 如果有多个域，请再次单击 **“添加标记”** 框来选择其他域。

    - **发件人为**：指定您的组织中的一个或多个用户。 单击 **“添加标记”**，然后开始键入内容来筛选列表。 再次单击 **"添加标记"** 框以选择其他发件人。

    - **发件人是：** 指定组织中一个或多个组的成员。 单击 **“添加标记”**，然后开始键入内容来筛选列表。 再次单击 **"添加标记"** 框以选择其他发件人。

    - **下列情况除外**：若要添加规则的例外情况，请单击 **“添加条件”** 三次，以查看所有可配置的例外。 设置和行为与条件完全相同。

8. 完成后，单击 **“保存”**。

## <a name="use-the-security--compliance-center-to-view-outbound-spam-policies"></a>使用安全&中心查看出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **"反垃圾邮件设置** "页上，单击 ![ "展开"图标 ](../../media/scc-expand-icon.png) 以展开出站垃圾邮件策略：

   - 名为"出站 **垃圾邮件筛选器策略"的默认策略**。

   - 您创建的自定义策略，其中 **"** 类型"列中的值为 **"自定义出站垃圾邮件策略"。**

3. 策略设置将显示在显示的扩展策略详细信息中，或者您可以单击"编辑 **策略"。**

## <a name="use-the-security--compliance-center-to-modify-outbound-spam-policies"></a>使用安全&合规中心修改出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **"反垃圾邮件设置** "页上，单击 ![ "展开"图标 ](../../media/scc-expand-icon.png) 以展开出站垃圾邮件策略：

   - 名为"出站 **垃圾邮件筛选器策略"的默认策略**。

   - 您创建的自定义策略，其中 **"** 类型"列中的值为 **"自定义出站垃圾邮件策略"。**

3. 单击 **“编辑策略”**。

对于自定义出站垃圾邮件策略，显示在出站中的可用设置与"使用安全与合规中心&创建 [出](#use-the-security--compliance-center-to-create-outbound-spam-policies) 站垃圾邮件策略部分中所述的设置相同。

对于名为"出站垃圾邮件筛选器策略"的默认出站垃圾邮件策略，"应用于"部分不可用 (该策略适用于所有) ，并且无法重命名该策略。 

若要启用或禁用策略、设置策略优先级顺序或配置最终用户隔离通知，请参阅以下各部分。

### <a name="enable-or-disable-outbound-spam-policies"></a>启用或禁用出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **"反垃圾邮件设置**"页上，单击"展开"图标以展开创建的自定义策略 ("类型"列中的值为"自定义出站垃圾邮件策略") 。 ![ ](../../media/scc-expand-icon.png)  

3. 在随即显示的展开策略详细信息中，注意 **“开”** 列中的值。

   将切换开关移动到左侧可禁用策略： ![切换开关关闭](../../media/scc-toggle-off.png)

   将切换开关移动到右侧可启用策略： ![切换开关打开](../../media/scc-toggle-on.png)

无法禁用默认出站垃圾邮件策略。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>设置自定义出站垃圾邮件策略的优先级

默认情况下，出站垃圾邮件策略的优先级基于它们在新策略中的创建顺序 (策略的优先级低于较旧策略) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

自定义出站垃圾邮件策略按处理顺序显示， (优先级值为 0) 。  名为"出站垃圾邮件筛选器策略 **"** 的默认出站垃圾邮件策略的优先级值为 **"** 最低"，你无法更改它。

若要更改策略优先级，请在列表中上移或下移策略（无法直接在安全与合规中心内修改 **“优先级”** 数字）。

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **"反垃圾邮件设置**"页上，查找"类型"列中的值为 **"自定义出站垃圾邮件策略"的策略**。  注意 **“优先级”** 列中的值：

   - 优先级最高的自定义出站垃圾邮件策略具有值 ![ 向下箭头图标 ](../../media/ITPro-EAC-DownArrowIcon.png) **0。**

   - 优先级最低的自定义出站垃圾邮件策略的值为"向上箭头"图标 n (![ ](../../media/ITPro-EAC-UpArrowIcon.png) 例如，向上箭头 ![ 图标 ](../../media/ITPro-EAC-UpArrowIcon.png) **3**) 。

   - 如果你有三个或多个自定义出站垃圾邮件策略，则最高优先级和最低优先级之间的策略具有值向上箭头图标向下箭头图标 n (例如，向上箭头图标向下箭头图标 ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png)  ![ ](../../media/ITPro-EAC-UpArrowIcon.png)![ ](../../media/ITPro-EAC-DownArrowIcon.png) **2**) 。

3. 单击 ![“向上箭头”图标](../../media/ITPro-EAC-UpArrowIcon.png) 或 ![“向下箭头”图标](../../media/ITPro-EAC-DownArrowIcon.png) 在优先级列表中上移或下移自定义出站垃圾邮件策略。

## <a name="use-the-security--compliance-center-to-remove-outbound-spam-policies"></a>使用安全&中心删除出站垃圾邮件策略

1. 在安全与合规中心内，依次转到 **“威胁管理”**\>**“策略”**\>**“反垃圾邮件”**。

2. 在 **"反垃圾邮件设置**"页上，单击"展开"图标以展开要删除的自定义策略 ("类型"列为"自定义出站垃圾邮件策略") 。 ![ ](../../media/scc-expand-icon.png)  

3. 在随即显示的展开策略详细信息中，单击 **“删除策略”**。

4. 在随即显示的警告对话框中，单击 **“是”**。

无法删除默认策略。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站垃圾邮件策略

如前所述，出站垃圾邮件策略由出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则组成。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，出站垃圾邮件筛选器策略和出站垃圾邮件筛选规则的区别显而易见。 您可以使用 **\* -HostedOutboundSpamFilterPolicy** cmdlet 管理出站垃圾邮件筛选器策略，使用 **\* -HostedOutboundSpamFilterRule** cmdlet 管理出站垃圾邮件筛选器规则。

- 在 PowerShell 中，首先创建出站垃圾邮件筛选策略，然后创建出站垃圾邮件筛选器规则，以标识该规则所适用的策略。
- 在 PowerShell 中，可以分别修改出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则中的设置。
- 从 PowerShell 删除出站垃圾邮件筛选器策略时，不会自动删除相应的出站垃圾邮件筛选规则，反之亦然。

### <a name="use-powershell-to-create-outbound-spam-policies"></a>使用 PowerShell 创建出站垃圾邮件策略

在 PowerShell 中创建出站垃圾邮件策略的过程分两步完成：

1. 创建出站垃圾邮件筛选器策略。
2. 创建出站垃圾邮件筛选器规则，该规则指定该规则适用的出站垃圾邮件筛选器策略。

 **注意**：

- 可以创建新的出站垃圾邮件筛选器规则，并为其分配现有的未关联的出站垃圾邮件筛选器策略。 出站垃圾邮件筛选器规则不能与多个出站垃圾邮件筛选器策略关联。

- 可以在 PowerShell 中的新出站垃圾邮件筛选器策略上配置以下设置，这些策略在创建策略之前&安全与合规中心内不可用：

  - 在 `$false` **New-HostedOutboundSpamFilterRule** cmdlet (上创建禁用的新策略) 。
  - 在 _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet (设置策略) 优先级) 。

- 在 PowerShell 中新建的出站垃圾邮件筛选器策略在安全与合规中心&，除非将策略分配给垃圾邮件筛选器规则。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>步骤 1：使用 PowerShell 创建出站垃圾邮件筛选器策略

若要创建出站垃圾邮件筛选器策略，请使用以下语法：

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

此示例创建一个名为 Contoso Executives 的新出站垃圾邮件筛选器策略，该策略具有以下设置：

- 收件人速率限制仅限于默认值较小的值。 有关详细信息，请参阅跨 [Microsoft 365 选项的发送限制](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。

- 达到其中一个限制后，将阻止用户发送邮件。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

有关语法和参数的详细信息，请参阅 [New-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>步骤 2：使用 PowerShell 创建出站垃圾邮件筛选器规则

若要创建出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

此示例使用这些设置创建一个名为 Contoso Executives 的新出站垃圾邮件筛选器规则：

- 名为 Contoso Executives 的出站垃圾邮件筛选器策略与该规则关联。

- 此规则应用于“Contoso Executives Group”组中的成员。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -SentToMemberOf "Contoso Executives Group"
```

有关语法和参数的详细信息，请参阅[New-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/new-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>使用 PowerShell 查看出站垃圾邮件筛选器策略

要返回所有出站垃圾邮件筛选器策略的摘要列表，请运行此命令：

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

要返回有关特定出站垃圾邮件筛选策略的详细信息，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

此示例返回名为 Executives 的出站垃圾邮件筛选器策略的所有属性值。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

有关语法和参数的详细信息，请参阅 [Get-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-view-outbound-spam-filter-rules"></a>使用 PowerShell 查看出站垃圾邮件筛选器规则

若要查看现有的出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterRule [-Identity "<RuleIdentity>"] [-State <Enabled | Disabled>]
```

要返回所有出站垃圾邮件筛选规则的摘要列表，请运行此命令：

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

要返回有关特定出站垃圾邮件筛选规则的详细信息，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "<RuleName>" | Format-List [<Specific properties to view>]
```

此示例返回名为 Contoso Executives 的出站垃圾邮件筛选规则的所有属性值。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

有关语法和参数的详细信息，请参阅[Get-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/get-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>使用 PowerShell 修改出站垃圾邮件筛选器策略

在 PowerShell 中修改恶意软件筛选器策略时，可以使用与在本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 创建出站垃圾邮件筛选器策略部分中所述的策略相同的设置。

> [!NOTE]
> 如果 **Set-HostedOutboundSpamFilterPolicy** cmdlet 没有 Name 参数 (，则不能重命名出站垃圾邮件筛选器) 。 在安全与合规中心重命名出站垃圾邮件&，只是重命名出站垃圾邮件筛选器 _规则_。

要修改出站垃圾邮件筛选器策略，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>使用 PowerShell 修改出站垃圾邮件筛选器规则

在 PowerShell 中修改出站垃圾邮件筛选规则时，唯一不可用的设置是允许创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有出站垃圾邮件筛选规则，请参阅下一节。

否则，在 PowerShell 中修改出站垃圾邮件筛选器规则时，将没有任何其他设置可用。 当您创建规则（如本文前面所述的步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 创建出站垃圾邮件筛选器规则部分中所述）时，可使用相同的设置。

要修改出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅[Set-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/set-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>使用 PowerShell 启用或禁用出站垃圾邮件筛选规则

在 PowerShell 中启用或禁用出站垃圾邮件筛选器规则可启用或禁用整个出站垃圾邮件策略 (出站垃圾邮件筛选器规则以及分配的出站垃圾邮件筛选器策略) 。 不能启用或禁用默认出站垃圾邮件策略 (该策略始终应用于所有) 。

若要在 PowerShell 中启用或禁用出站垃圾邮件筛选规则，请使用以下语法：

```PowerShell
<Enable-HostedOutboundSpamFilterRule | Disable-HostedOutboundSpamFilterRule> -Identity "<RuleName>"
```

本示例禁用名为 Marketing Department 的出站垃圾邮件筛选器规则。

```PowerShell
Disable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

下面的示例启用同一规则。

```PowerShell
Enable-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[Enable-HostedOutboundSpamFilterRule](https://docs.microsoft.com/powershell/module/exchange/enable-hostedoutboundspamfilterrule)和[Disable-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/disable-hostedoutboundspamfilterrule)

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>使用 PowerShell 设置出站垃圾邮件筛选规则的优先级

可以设置的规则最高优先级值是 0。 可以设置的最小优先级值取决于规则的数量。 例如，如果有五个规则，则可以使用的优先级值为 0 到 4。 更改现有规则的优先级可对其他规则产生级联效应。 例如，假设有五个自定义规则（优先级从 0 到 4）。如果你将某个规则的优先级更改为 2，那么优先级为 2 的现有规则会变成优先级 3，优先级为 3 的现有规则会变成优先级 4。

若要在 PowerShell 中设置出站垃圾邮件筛选器规则的优先级，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

下面的示例将名为“Marketing Department”的规则的优先级设置为 2。 优先级小于或等于 2 的所有现有规则的优先级都递减 1（即优先级数字都递增 1）。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

> [!NOTE]
>
> - 若要在创建新规则时设置规则的优先级，请改为使用 **New-HostedOutboundSpamFilterRule** cmdlet 的 _Priority_ 参数。
>
> - 出站默认垃圾邮件筛选器策略没有相应的垃圾邮件筛选规则，并且始终具有不可修改的优先级值 **最低**。

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>使用 PowerShell 删除出站垃圾邮件筛选器策略

使用 PowerShell 删除出站垃圾邮件筛选策略时，不会删除相应的出站垃圾邮件筛选器规则。

若要在 PowerShell 中删除出站垃圾邮件筛选器策略，请使用以下语法：

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

本示例删除名为"Marketing Department"的出站垃圾邮件筛选器策略。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-HostedOutboundSpamFilterPolicy](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>使用 PowerShell 删除出站垃圾邮件筛选器规则

使用 PowerShell 删除出站垃圾邮件筛选规则时，不会删除相应的出站垃圾邮件筛选策略。

若要在 PowerShell 中删除出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

本示例删除名为 Marketing Department 的出站垃圾邮件筛选器规则。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅[Remove-HostedOutboundSpamFilterRule。](https://docs.microsoft.com/powershell/module/exchange/remove-hostedoutboundspamfilterrule)

## <a name="for-more-information"></a>更多详细信息

[从“受限的用户”门户中删除被阻止的用户](removing-user-from-restricted-users-portal-after-spam.md)

[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[反垃圾邮件保护常见问题](anti-spam-protection-faq.md)

[自动转发的消息报告](mfi-auto-forwarded-messages-report.md)
