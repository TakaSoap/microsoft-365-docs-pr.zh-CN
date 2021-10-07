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
ms.localizationpriority: medium
search.appverid:
- MET150
ms.assetid: a44764e9-a5d2-4c67-8888-e7fb871c17c7
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 管理员可以了解如何在 EOP 服务中查看、创建、修改和删除Exchange Online Protection (垃圾邮件) 。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 08621035f5bdd89b43cbe64e84802cdf0dfc5a79
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60196557"
---
# <a name="configure-outbound-spam-filtering-in-eop"></a>在 EOP 中配置出站垃圾邮件筛选

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

在 Microsoft 365 组织中，邮箱在 Exchange Online 或独立 Exchange Online Protection (EOP) 组织中没有 Exchange Online 邮箱，则自动检查通过 EOP 发送的出站电子邮件是否包含垃圾邮件和异常发送活动。

来自组织中用户的出站垃圾邮件通常指示帐户遭到入侵。 无论垃圾邮件可信度或 SCL) 是什么，可疑出站邮件都会标记为垃圾邮件 (并通过高风险传送池进行路由，以帮助[](high-risk-delivery-pool-for-outbound-messages.md)保护服务 (即使 Microsoft 365 源电子邮件服务器不受 IP 阻止列表) 限制。 管理员将自动收到可疑的出站电子邮件活动的通知，并且会通过警报策略阻止 [用户](../../compliance/alert-policies.md)。

EOP 使用出站垃圾邮件策略作为组织对垃圾邮件的整体防御的一部分。 有关详细信息，请参阅[反垃圾邮件保护](anti-spam-protection.md)。

管理员可以查看、编辑和配置 (，但不能) 默认出站垃圾邮件策略。 更精细地来说，您还可以创建适用于组织中特定用户、组或域的自定义出站垃圾邮件策略。 自定义策略始终优先于默认策略，但可以更改自定义策略的优先级（即运行顺序）。

您可以在邮件门户中或在 PowerShell Microsoft 365 Microsoft 365 Defender PowerShell 中为邮箱在 Microsoft 365 中的组织 (Exchange Online PowerShell 配置出站Exchange Online;适用于没有邮箱或邮箱Exchange Online的独立 EOP PowerShell) 。

EOP 中的出站垃圾邮件策略的基本元素包括：

- **出站垃圾邮件筛选策略**：指定出站垃圾邮件筛选裁定和通知选项的操作。
- **出站垃圾邮件筛选器** 规则：指定策略 (策略应用于出站垃圾邮件) 的优先级和收件人筛选器。

当您在邮件门户中管理出站垃圾邮件管理时，这两个元素Microsoft 365 Defender明显：

- 创建策略时，实际上是同时使用同一名称创建出站垃圾邮件筛选规则和相关出站垃圾邮件筛选策略。
- 修改策略时，与名称、优先级、启用或禁用以及收件人筛选器相关的设置将修改出站垃圾邮件筛选器规则。 所有其他设置修改关联的出站垃圾邮件筛选器策略。
- 删除策略时，将删除出站垃圾邮件筛选器规则和相关出站垃圾邮件筛选器策略。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，单独管理策略和规则。 有关详细信息，请参阅本文Exchange Online [PowerShell 或独立 EOP PowerShell](#use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies)配置出站垃圾邮件策略一节。

每个组织都有一个名为 Default 的内置出站垃圾邮件策略，该策略具有以下属性：

- 即使与策略关联的收件人筛选器没有出站垃圾邮件筛选规则， (应用于组织) 所有收件人。
- 该策略具有无法修改的自定义优先级值“**最低**”（表示此策略始终最后应用）。 你创建的任何自定义策略的优先级始终高于名为“默认”的策略。
- 该策略是默认策略（**IsDefault** 属性的值为 `True`），你无法删除默认策略。

若要提高出站垃圾邮件筛选的有效性，可以使用应用于特定用户或用户组的更严格的设置创建自定义出站垃圾邮件策略。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 访问 <https://security.microsoft.com> 打开 Microsoft 365 Defender 门户。 若要直接转到 **“反垃圾邮件设置”** 页，请访问 <https://security.microsoft.com/antispam>。

- 若要连接到 Exchange Online PowerShell，请参阅[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。 若要连接到独立 EOP PowerShell，请参阅[连接到 Exchange Online Protection PowerShell](/powershell/exchange/connect-to-exchange-online-protection-powershell)。

- 在 Exchange Online 网站中 **分配** 权限，才能执行本文中的步骤：
  - 若要添加、修改和删除出站垃圾邮件策略，您必须是组织管理或 **安全管理员角色组** 的成员。 
  - 若要对出站垃圾邮件策略进行只读访问，您需要是全局读者或安全 **读者角色组** 的成员。 

  有关详细信息，请参阅 [Exchange Online 中权限](/exchange/permissions-exo/permissions-exo)。

  **注意**：

  - 在 Microsoft 365 管理中心将用户添加到相应的 Azure Active Directory 角色后，将为用户提供所需的权限 _和_ Microsoft 365 中其他功能的所需权限。 有关详细信息，请参阅 [关于管理员角色](../../admin/add-users/about-admin-roles.md)。
  - [Exchange Online](/Exchange/permissions-exo/permissions-exo#role-groups) 中的 **仅查看组织管理人员** 角色组也提供到该功能的只读访问。

- 有关针对出站垃圾邮件策略的建议设置，请参阅 [EOP 出站垃圾邮件筛选器策略设置](recommended-settings-for-eop-and-office365.md#eop-outbound-spam-policy-settings)。

- 名为 [](../../compliance/alert-policies.md)Email **sending limit、Suspicious** **email sending patterns detected** 和 User restricted from sending **email** 的默认警报策略已向 **TenantAdmins** (**全局** 管理员) 组的成员发送有关异常出站电子邮件活动和因出站垃圾邮件被阻止的用户的电子邮件通知。 有关详细信息，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。 我们建议您使用这些警报策略，而不是出站垃圾邮件策略中的通知选项。

## <a name="use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies"></a>使用Microsoft 365 Defender门户创建出站垃圾邮件策略

在门户中创建自定义出站垃圾邮件Microsoft 365 Defender会同时使用同一名称创建垃圾邮件筛选规则和相关垃圾邮件筛选器策略。

1. 在 Microsoft 365 Defender 门户中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>的“**反垃圾邮件**”。

2. 在" **反垃圾邮件策略"页上** ，单击" ![ 创建图标"。](../../media/m365-cc-sc-create-icon.png) **创建策略** ，然后从 **下拉列表** 中选择"出站"。

3. 将打开策略向导。 在“**命名策略页面**”上，配置以下设置：
   - **名称**：输入策略的唯一描述性名称。
   - **说明**：输入策略的可选说明。

   完成后，单击“**下一步**”。

4. 在出现的“**用户、组和域**”页面上，标识策略应用于的内部收件人（收件人条件）：
   - **用户**：你的组织内指定的邮箱、邮件用户或邮件联系人。
   - **组**：你的组织内指定的通讯组、启用邮件的安全组或 Microsoft 365 组。
   - **域**：你的组织内指定的 [接受域](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)中的所有收件人。

   单击相应的框，开始键入值，然后从结果中选择所需的值。 根据需要多次重复此过程。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

   对于用户或组，可以使用大多数标识符（姓名、显示名称、别名、电子邮件地址、帐户名称等），但是相应的显示名称会显示在结果中。 对于用户，请自行输入星号 (\*) 以查看所有可用值。

   同一个条件的多个值使用 OR 逻辑（例如，_\<recipient1\>_ 或 _\<recipient2\>_）。 不同的条件使用 AND 逻辑（例如，_\<recipient1\>_ 和 _\<member of group 1\>_）。

   - **排除这些用户、组和域**：若要为策略应用于的内部收件人添加例外（收件人例外），请选择此选项并配置例外。 设置和行为与条件完全相同。

   完成后，单击“**下一步**”。

5. 在打开 **的** "保护设置"页上，配置以下设置：
   - **邮件** 限制：本节中的设置配置来自以下邮箱的出站 **Exchange Online** 限制：
     - **设置外部邮件限制**：每小时的最大外部收件人数。
     - **设置内部邮件限制**：每小时内部收件人的最大数量。
     - **设置每日邮件限制**：每天的最大收件人总数。

     有效值为 0 到 10000。 默认值为 0，表示使用服务默认值。 有关详细信息，请参阅发送 [限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-1)。

    在框中输入值，或使用框上的增加/减少箭头。

   - **对达到邮件限制的用户** 施加的限制：当超过"保护设置"部分的任何限制时，从下拉列表中选择一个操作。

     对于所有操作，在"用户限制发送电子邮件通知策略 ("中指定的收件人以及现在冗余的"如果发件人因发送出站垃圾邮件设置被阻止，则通知这些用户和组") 接收电子邮件通知。

     - **限制用户发送邮件，直到第二天**：此为默认值。 将发送电子邮件通知，用户将无法再发送任何邮件，直到第二天，基于 UTC 时间。 管理员无法覆盖此阻止。
       - 名为"用户 **被限制** 发送电子邮件"的警报策略 (通过电子邮件发送通知管理员，并通知管理员&警报查看警报 \> ") 。
       - 还会通知策略中"如果发件人因发送出站垃圾邮件而受阻，则通知特定人员"设置中指定的任何收件人。
       - 用户将无法发送其他任何邮件，直到第二天，基于 UTC 时间。 管理员无法覆盖此阻止。
     - 限制用户发送邮件：发送电子邮件通知、将用户添加到 Microsoft 365 Defender 门户中的受限用户，并且用户无法发送电子邮件，除非管理员将用户从受限用户中删除。 <https://security.microsoft.com/restrictedusers> 管理员从列表中删除用户后，该天不会再次限制该用户。 有关说明，请参阅 [在发送垃圾邮件后从受限用户门户删除用户](removing-user-from-restricted-users-portal-after-spam.md)。
     - **无操作，仅** 警报：发送电子邮件通知。

   - **转发规则**：使用本节中的设置控制自动电子邮件转发，Exchange Online **邮箱** 转发给外部发件人。 有关详细信息，请参阅在电子邮件中控制[自动外部](external-email-forwarding.md)Microsoft 365。

     > [!NOTE]
     > 禁用自动转发后，如果外部发件人向已就地转发的邮箱发送电子邮件 (收件人将收到未送达报告 (也称为 NDR 或退回邮件) 。 如果邮件由内部发件人发送，并且转发方法是邮箱转发 (也称为 [](/exchange/recipients-in-exchange-online/manage-user-mailboxes/configure-email-forwarding) _SMTP_) ，则内部发件人将获取 NDR。 如果转发由于收件箱规则而发生，则内部发件人不会获得 NDR。

     从"自动转发规则"下拉列表 **中选择下列** 操作之一：

     - **自动 - 系统控制**：允许出站垃圾邮件筛选控制自动外部电子邮件转发。 此为默认值。
     - **On**：策略不会禁用自动外部电子邮件转发。
     - **关闭**：策略禁用所有自动外部电子邮件转发。

   - **通知**：使用 部分中的设置配置其他收件人，这些收件人应接收可疑出站电子邮件的副本和通知：

     - **向这些用户** 和组发送超过这些限制的可疑出站副本：此设置将指定的收件人添加到可疑出站邮件的"Bcc"字段中。

       > [!NOTE]
       > 此设置仅适用于默认出站垃圾邮件策略。 它不能用于您创建的自定义出站垃圾邮件策略。

       若要启用此设置，请选中此复选框。 在出现的框中，单击该框，输入有效的电子邮件地址，然后按 Enter 或选择显示在框下方的完整值。

       根据需要重复执行此步骤（次数不限）。 若要删除现有值，请单击值旁边的 ![删除图标。](../../media/m365-cc-sc-remove-selection-icon.png) “删除”。

   - **如果发件人因发送出站垃圾邮件被阻止，则通知这些用户和组**

     > [!IMPORTANT]
     >
     > - 此设置正在被出站垃圾邮件策略弃用。
     >
     > - 名为"[](../../compliance/alert-policies.md)限制发送电子邮件的用户"的默认警报策略已在用户因超出"收件人限制"部分的限制而被阻止时，向 **TenantAdmins** (全局管理员 **)** 组的成员发送电子邮件通知。  **强烈建议使用警报** 策略，而不是出站垃圾邮件策略中的此设置来通知管理员和其他用户。 有关说明，请参阅 [验证受限用户的警报设置](removing-user-from-restricted-users-portal-after-spam.md#verify-the-alert-settings-for-restricted-users)。

   完成后，单击“**下一步**”。

6. 在出现的“**审阅**”页面上，查看你的设置。 可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

   完成后，单击“**创建**”。

7. 在出现的确认页面上，单击“**完成**”。

## <a name="use-the-microsoft-365-defender-portal-to-view-outbound-spam-policies"></a>使用Microsoft 365 Defender查看出站垃圾邮件策略

1. 在 Microsoft 365 Defender 门户中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>的“**反垃圾邮件**”。

2. 在 **“反垃圾邮件”策略** 页面上，查找以下值之一:
   - 类型 **值为** " **自定义出站垃圾邮件策略"**
   - Name 值为 **"反垃圾邮件出站策略" (默认)**

   反垃圾邮件策略列表中将显示以下属性：

   - **名称**
   - **状态**
   - **优先级**
   - **类型**

3. 当您通过单击该名称选择出站垃圾邮件策略时，策略设置将显示在一个飞出控件中。

## <a name="use-the-microsoft-365-defender-portal-to-modify-outbound-spam-policies"></a>使用Microsoft 365 Defender门户修改出站垃圾邮件策略

1. 在 Microsoft 365 Defender 门户中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>的“**反垃圾邮件**”。

2. 在 **"反垃圾邮件策略"** 页上，通过单击名称从列表中选择出站垃圾邮件策略：
   - 您创建的自定义策略，其中"类型"**列中的值为****"自定义出站垃圾邮件策略"。**
   - 名为"反垃圾邮件 **出站策略"的默认策略 (默认) 。**

3. 在出现的策略详细信息浮出控件中，选择每个部分中的“**编辑**”以修改该部分中的设置。 有关设置详细信息，请参阅本文中的上一Microsoft 365 Defender门户创建[出站](#use-the-microsoft-365-defender-portal-to-create-outbound-spam-policies)垃圾邮件策略部分。

   对于默认出站垃圾邮件策略，"应用于"部分 (该策略应用于所有) ，并且无法重命名该策略。

若要启用或禁用策略、设置策略优先级顺序或配置最终用户通知，请参阅以下部分。

### <a name="enable-or-disable-custom-outbound-spam-policies"></a>启用或禁用自定义出站垃圾邮件策略

不能禁用默认出站垃圾邮件策略。

1. 在 Microsoft 365 Defender 门户中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>的“**反垃圾邮件**”。

2. 在 **"反垃圾邮件策略"** 页上，单击名称，从列表中选择"类型"值为"自定义出站垃圾邮件策略"的策略。

3. 在出现的策略详细信息浮出控件顶部，你将看到以下值之一：
   - **策略关闭**：若要打开策略，请单击![“打开”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“打开”**。
   - **策略打开**：若要关闭策略，请单击![“关闭”图标。](../../media/m365-cc-sc-turn-on-off-icon.png)**“关闭”**。

4. 在出现的确认对话框中，单击“**打开**”或“**关闭**”。

5. 单击策略详细信息浮出控件中的“**关闭**”。

返回主策略页面，策略的“**状态**”值将为“**打开**”或“**关闭**”。

### <a name="set-the-priority-of-custom-outbound-spam-policies"></a>设置自定义出站垃圾邮件策略的优先级

默认情况下，根据出站垃圾邮件策略在 (中的创建顺序，出站垃圾邮件策略的优先级低于旧版策略) 。 低优先级数字表示高策略优先级（0 是最高优先级），且策略按照优先级顺序进行处理（高优先级策略先处理，低优先级策略后处理）。 没有两个策略可以具有相同的优先级，并且在应用第一个策略之后，策略处理将停止。

若要更改策略的优先级，请单击策略属性中的“**提高优先级**”或“**降低优先级**”（不能直接修改 Microsoft 365 Defender 门户中的“**优先级**”数字）。 只有当你有多个策略时，更改策略的优先级才有意义。

 **注意**：

- 在Microsoft 365 Defender门户中，只能在创建出站垃圾邮件策略后更改该策略的优先级。 在 PowerShell 中，可以在创建垃圾邮件筛选规则时替代默认优先级（这可能会影响现有规则的优先级）。
- 出站垃圾邮件策略按照其显示顺序进行处理 (第一个策略的优先级值为 0) 。  默认出站垃圾邮件策略的优先级值为 **"** 最低"，你无法更改它。

1. 在 Microsoft 365 Defender 门户中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>的“**反垃圾邮件**”。

2. 在 **"反垃圾邮件策略"** 页上，通过单击名称从列表中选择"类型"值为"自定义出站垃圾邮件策略"的策略。

3. 在出现的策略详细信息浮出控件顶部，你会看到“**提高优先级**”或“**降低优先级**”，具体取决于当前优先级值和自定义策略数量：
   - 优先级值为 **0** 的出站垃圾邮件策略仅提供 **"减少优先级"** 选项。
   - 优先级值最低的出站垃圾邮件策略 (例如 **，3**) 只有"增加 **优先级"** 选项可用。
   - 如果您有三个或多个出站垃圾邮件策略，则最高优先级和最低优先级值之间的策略同时具有"增加优先级"和"**减少优先级"** 选项。

   单击![“提高优先级”图标。](../../media/m365-cc-sc-increase-icon.png) **“提高优先级”** 或![“降低优先级”图标](../../media/m365-cc-sc-decrease-icon.png) **“降低优先级”** 以更改 **“优先级”** 值。

4. 完成后，单击策略详细信息浮出控件中的“**关闭**”。

## <a name="use-the-microsoft-365-defender-portal-to-remove-custom-outbound-spam-policies"></a>使用 Microsoft 365 Defender门户删除自定义出站垃圾邮件策略

使用自定义Microsoft 365 Defender删除自定义出站垃圾邮件策略时，垃圾邮件筛选器规则及相应的垃圾邮件筛选策略都将被删除。 不能删除默认出站垃圾邮件策略。

1. 在 Microsoft 365 Defender 门户中，转到“**策略**”部分中的“**电子邮件和协作**”\>“**策略和规则**”\>“**威胁策略**”\>的“**反垃圾邮件**”。

2. 在 **"反垃圾邮件策略"** 页上，单击名称，从列表中选择"类型"值为"自定义出站垃圾邮件策略"的策略。 在显示的策略详细信息浮出控件顶部，单击![更多操作图标。](../../media/m365-cc-sc-more-actions-icon.png) **更多操作** \> ![删除策略图标](../../media/m365-cc-sc-delete-icon.png) **删除策略**。

3. 在出现的确认对话框中，单击“**是**”。

## <a name="use-exchange-online-powershell-or-standalone-eop-powershell-to-configure-outbound-spam-policies"></a>使用 Exchange Online PowerShell 或独立 EOP PowerShell 配置出站垃圾邮件策略

如前所述，出站垃圾邮件策略由出站垃圾邮件筛选器策略和出站垃圾邮件筛选器规则组成。

在 Exchange Online PowerShell 或独立 EOP PowerShell 中，出站垃圾邮件筛选器策略和出站垃圾邮件筛选规则的区别显而易见。 您可以使用 **\* -HostedOutboundSpamFilterPolicy** cmdlet 管理出站垃圾邮件筛选器策略，使用 **\* -HostedOutboundSpamFilterRule** cmdlet 管理出站垃圾邮件筛选器规则。

- 在 PowerShell 中，首先创建出站垃圾邮件筛选策略，然后创建出站垃圾邮件筛选器规则，以标识该规则应用于的策略。
- 在 PowerShell 中，可以分别修改出站垃圾邮件筛选策略和出站垃圾邮件筛选规则中的设置。
- 从 PowerShell 中删除出站垃圾邮件筛选策略时，不会自动删除相应的出站垃圾邮件筛选规则，反之亦然。

### <a name="use-powershell-to-create-outbound-spam-policies"></a>使用 PowerShell 创建出站垃圾邮件策略

在 PowerShell 中创建出站垃圾邮件策略的过程包括两个步骤：

1. 创建出站垃圾邮件筛选器策略。
2. 创建出站垃圾邮件筛选器规则，该规则指定该规则适用的出站垃圾邮件筛选器策略。

   **注意**:

   - 您可以创建一个新的出站垃圾邮件筛选器规则，并为其分配现有的未关联的出站垃圾邮件筛选器策略。 出站垃圾邮件筛选器规则不能与多个出站垃圾邮件筛选器策略关联。
   - 可以在 PowerShell 中的新出站垃圾邮件筛选器策略上配置以下设置，这些设置在 Microsoft 365 Defender 门户中不可用，直到创建策略之后：
     - 在 `$false` **New-HostedOutboundSpamFilterRule** cmdlet (上创建禁用的新) 。
     - 在 _\<Number\>_ **New-HostedOutboundSpamFilterRule** cmdlet (中) 策略创建期间设置的优先级) 。
   - 在 PowerShell 中新建的出站垃圾邮件筛选器策略在 Microsoft 365 Defender门户中不可见，除非将策略分配给出站垃圾邮件筛选器规则。

#### <a name="step-1-use-powershell-to-create-an-outbound-spam-filter-policy"></a>步骤 1：使用 PowerShell 创建出站垃圾邮件筛选器策略

若要创建出站垃圾邮件筛选器策略，请使用以下语法：

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "<PolicyName>" [-AdminDisplayName "<Comments>"] <Additional Settings>
```

本示例将创建一个名为 Contoso Executives 的新出站垃圾邮件筛选器策略，该策略具有以下设置：

- 收件人速率限制仅限于默认值较小的值。 有关详细信息，请参阅跨选项[发送Microsoft 365限制](/office365/servicedescriptions/exchange-online-service-description/exchange-online-limits#sending-limits-across-office-365-options)。

- 达到其中一个限制后，将阻止用户发送邮件。

```PowerShell
New-HostedOutboundSpamFilterPolicy -Name "Contoso Executives" -RecipientLimitExternalPerHour 400 -RecipientLimitInternalPerHour 800 -RecipientLimitPerDay 800 -ActionWhenThresholdReached BlockUser
```

有关语法和参数的详细信息，请参阅 [New-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/new-hostedoutboundspamfilterpolicy)。

#### <a name="step-2-use-powershell-to-create-an-outbound-spam-filter-rule"></a>步骤 2：使用 PowerShell 创建出站垃圾邮件筛选器规则

若要创建出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
New-HostedOutboundSpamFilterRule -Name "<RuleName>" -HostedOutboundSpamFilterPolicy "<PolicyName>" <Recipient filters> [<Recipient filter exceptions>] [-Comments "<OptionalComments>"]
```

本示例创建一个名为 Contoso Executives 的新出站垃圾邮件筛选器规则，该规则具有以下设置：

- 名为 Contoso Executives 的出站垃圾邮件筛选器策略与该规则关联。
- 此规则应用于“Contoso Executives Group”组中的成员。

```PowerShell
New-HostedOutboundSpamFilterRule -Name "Contoso Executives" -HostedOutboundSpamFilterPolicy "Contoso Executives" -FromMemberOf "Contoso Executives Group"
```

有关语法和参数的详细信息，请参阅 [New-HostedOutboundSpamFilterRule](/powershell/module/exchange/new-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-view-outbound-spam-filter-policies"></a>使用 PowerShell 查看出站垃圾邮件筛选器策略

要返回所有出站垃圾邮件筛选器策略的摘要列表，请运行此命令：

```PowerShell
Get-HostedOutboundSpamFilterPolicy
```

要返回有关特定出站垃圾邮件筛选策略的详细信息，请使用以下语法：

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" | Format-List [<Specific properties to view>]
```

本示例返回名为 Executives 的出站垃圾邮件筛选策略的所有属性值。

```PowerShell
Get-HostedOutboundSpamFilterPolicy -Identity "Executives" | Format-List
```

有关语法和参数的详细信息，请参阅 [Get-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/get-hostedoutboundspamfilterpolicy)。

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

本示例返回名为 Contoso Executives 的出站垃圾邮件筛选规则的所有属性值。

```PowerShell
Get-HostedOutboundSpamFilterRule -Identity "Contoso Executives" | Format-List
```

有关语法和参数的详细信息，请参阅 [Get-HostedOutboundSpamFilterRule](/powershell/module/exchange/get-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-modify-outbound-spam-filter-policies"></a>使用 PowerShell 修改出站垃圾邮件筛选器策略

在 PowerShell 中修改恶意软件筛选器策略时可用的设置与创建策略时相同，如本文前面步骤 [1：使用 PowerShell](#step-1-use-powershell-to-create-an-outbound-spam-filter-policy) 创建出站垃圾邮件筛选器策略一节中所述。

> [!NOTE]
> 如果 **Set-HostedOutboundSpamFilterPolicy** cmdlet 没有 _Name_ (，则不能重命名出站垃圾邮件) 。 在邮件门户中重命名出站垃圾邮件Microsoft 365 Defender，只需重命名出站垃圾邮件筛选器 _规则_。

若要修改出站垃圾邮件筛选器策略，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/set-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-modify-outbound-spam-filter-rules"></a>使用 PowerShell 修改出站垃圾邮件筛选器规则

在 PowerShell 中修改出站垃圾邮件筛选规则时，唯一不可用的设置是允许您创建已禁用规则的 _Enabled_ 参数。 若要启用或禁用现有出站垃圾邮件筛选器规则，请参阅下一节。

否则，在 PowerShell 中修改出站垃圾邮件筛选规则时，其他设置将不可用。 创建规则时可用的设置与本文前面步骤 [2：使用 PowerShell](#step-2-use-powershell-to-create-an-outbound-spam-filter-rule) 创建出站垃圾邮件筛选规则一节中所述的设置相同。

要修改出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" <Settings>
```

有关语法和参数的详细信息，请参阅 [Set-HostedOutboundSpamFilterRule](/powershell/module/exchange/set-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-enable-or-disable-outbound-spam-filter-rules"></a>使用 PowerShell 启用或禁用出站垃圾邮件筛选规则

启用或禁用 PowerShell 中的出站垃圾邮件筛选规则启用或禁用整个出站垃圾邮件策略 (出站垃圾邮件筛选器规则，以及分配的出站垃圾邮件筛选器策略) 。 不能启用或禁用默认出站垃圾邮件策略 (它始终应用于所有收件人或) 。

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

有关语法和参数的详细信息，请参阅 [Enable-HostedOutboundSpamFilterRule](/powershell/module/exchange/enable-hostedoutboundspamfilterrule) 和 [Disable-HostedOutboundSpamFilterRule](/powershell/module/exchange/disable-hostedoutboundspamfilterrule)。

### <a name="use-powershell-to-set-the-priority-of-outbound-spam-filter-rules"></a>使用 PowerShell 设置出站垃圾邮件筛选规则的优先级

可以设置的规则最高优先级值是 0。可以设置的最小优先级值取决于规则的数量。例如，如果有五个规则，则可以使用的优先级值为 0 到 4。更改现有规则的优先级可对其他规则产生级联效应。例如，假设有五个自定义规则（优先级为 0 到 4），如果将某个规则的优先级更改为 2，则优先级为 2 的现有规则将更改为优先级 3，优先级为 3 的规则将更改为优先级 4。

若要在 PowerShell 中设置出站垃圾邮件筛选规则的优先级，请使用以下语法：

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "<RuleName>" -Priority <Number>
```

此示例将名为"Marketing Department"规则的优先级设置为 2：具有小于或等于 2 优先级的所有现有规则的编号将递减 1（它们的优先级编号均递增 1）。

```PowerShell
Set-HostedOutboundSpamFilterRule -Identity "Marketing Department" -Priority 2
```

**注意**：

- 若要在创建新规则的优先级时设置该规则的优先级，请改为使用 **New-HostedOutboundSpamFilterRule** cmdlet 上的 _Priority_ 参数。
- 出站默认垃圾邮件筛选策略没有对应的垃圾邮件筛选规则，并且始终具有不可修改的优先级值 **Lowest**。

### <a name="use-powershell-to-remove-outbound-spam-filter-policies"></a>使用 PowerShell 删除出站垃圾邮件筛选器策略

使用 PowerShell 删除出站垃圾邮件筛选策略时，不会删除相应的出站垃圾邮件筛选规则。

若要在 PowerShell 中删除出站垃圾邮件筛选器策略，请使用以下语法：

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "<PolicyName>"
```

本示例删除名为 Marketing Department 的出站垃圾邮件筛选器策略。

```PowerShell
Remove-HostedOutboundSpamFilterPolicy -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-HostedOutboundSpamFilterPolicy](/powershell/module/exchange/remove-hostedoutboundspamfilterpolicy)。

### <a name="use-powershell-to-remove-outbound-spam-filter-rules"></a>使用 PowerShell 删除出站垃圾邮件筛选器规则

使用 PowerShell 删除出站垃圾邮件筛选规则时，不会删除相应的出站垃圾邮件筛选策略。

若要在 PowerShell 中删除出站垃圾邮件筛选器规则，请使用以下语法：

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "<PolicyName>"
```

本示例删除名为"Marketing Department"的出站垃圾邮件筛选器规则。

```PowerShell
Remove-HostedOutboundSpamFilterRule -Identity "Marketing Department"
```

有关语法和参数的详细信息，请参阅 [Remove-HostedOutboundSpamFilterRule](/powershell/module/exchange/remove-hostedoutboundspamfilterrule)。

## <a name="for-more-information"></a>详细信息

[从“受限的用户”门户中删除被阻止的用户](removing-user-from-restricted-users-portal-after-spam.md)

[出站邮件的高风险传递池](high-risk-delivery-pool-for-outbound-messages.md)

[反垃圾邮件保护常见问题](anti-spam-protection-faq.yml)

[自动转发的消息报告](mfi-auto-forwarded-messages-report.md)
