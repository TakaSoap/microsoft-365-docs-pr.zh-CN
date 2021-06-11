---
title: 抵御威胁
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
localization_priority: Normal
ms.date: 09/08/2020
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以在 Microsoft 365 中学习威胁防护并为组织配置使用方法。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 5d61b17fc4575249bb592fc4ca865c34a628361a
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878324"
---
# <a name="protect-against-threats"></a>抵御威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

这是一个快速的指南，它将 Defender for Office 365 的配置分成块。 如果你对 Microsoft Office 365 中的威胁防护功能不了解，不知道从哪里开始，或者你喜欢通过 *上手* 来学习，使用这个指南作为一个清单和开始。

> [!IMPORTANT]
> **包括了适合每种策略的初步推荐设置；然后，很多选项都可用，你可以调整设置以满足具体的组织需要**。 预留大概 30 分钟以让你的策略或更改在你的数据中心中正常工作。

## <a name="requirements"></a>要求

### <a name="subscriptions"></a>订阅

威胁防护功能含在 *所有* Microsoft 或 Office 365 订阅中；然而，一些订阅有高级功能。 下面的表格列出了包含在此文章中的防护功能，以及最低订阅要求。

> [!TIP]
> 注意，在打开审核之外，还包含开启反恶意软件、反钓鱼、反垃圾邮件的 *步骤*，这些是 Office 365 Exchange Online Protection (**EOP**) 的一部分。 在你记住 (**Defender for Office 365**) 包含内容、基础、EOP 之前，这可能在 Defender for Office 365 的文章里看起来很奇怪。

<br>

****

|防护类型|订阅要求|
|---|---|
|审核日志（出于报告的目的）|[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|反恶意软件保护|[Exchange Online Protection](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|防钓鱼保护|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|反垃圾邮件保护|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|零时差自动清除 (电子邮件)|[EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|保护电子邮件和附件文档中的恶意 URL 和Office (保险箱链接保险箱附件) |[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|打开保险箱、SharePoint OneDrive和Microsoft Teams附件|[Microsoft Defender for Office 365](turn-on-mdo-for-spo-odb-and-teams.md)|
|高级反钓鱼防护|[Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>角色和权限

若要配置 Defender for Office 365 策略，必须在[安全与合规中心](/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)分配给你一个适当的角色。 看看下面的表格，了解可以执行这些操作的角色。

<br>

****

|角色或角色组|在哪里了解更多信息|
|---|---|
|全局管理员|[关于 Microsoft 365 管理员角色](../../admin/add-users/about-admin-roles.md)|
|安全管理员|[Azure Active Directory 中的管理员角色权限](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 组织管理|[Exchange Online 中的权限](/exchange/permissions-exo/permissions-exo) <p> 和 <p> [Exchange Online PowerShell](/powershell/exchange/exchange-online-powershell)|
|

若要了解详细信息，请参阅 [安全与合规中心的访问权限](permissions-in-the-security-and-compliance-center.md)。

### <a name="turn-on-audit-logging-for-reporting-and-investigation"></a>打开用于报告和调查的审核日志记录

- 早点开始审核日志。 对于以下步骤中的 **一些步骤** ，你需要将审核功能启用。 审核日志在包括[Exchange Online](/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的订阅中可用。 为了查看威胁防护报告中的数据，比如 [安全性仪表板](security-dashboard.md)、[电子邮件安全报告](view-email-security-reports.md)、[Explorer](threat-explorer.md)，审核日志必须“*打开*”。 有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="part-1---anti-malware-protection-in-eop"></a>第 1 部分 - EOP 中的反恶意软件保护

有关反恶意软件的建议设置详细信息，请参阅 [EOP 反恶意软件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-malware-policy-settings)。

1. 打开 <https://security.microsoft.com/antimalwarev2> 。

2. 在 **"反恶意软件"** 页上，通过单击该名称选择名为 **"** 默认策略"的策略。

3. 在打开的策略详细信息飞出控件中，单击" **编辑保护设置"，** 然后配置以下设置：
   - 选择 **"启用常用附件筛选器** "以打开常用附件筛选器。 单击 **"自定义文件类型** "以添加更多文件类型。
   - 验证是否 **选中了"启用恶意软件的零时差自动清除** "。
   - 验证"通知"部分未 **选择** 任何设置。

   完成时，请单击“保存”。

4. 返回策略详细信息浮出控件，单击“**关闭**”。

有关配置反恶意软件策略的详细说明，请参阅在 EOP 中配置 [反恶意软件策略](configure-anti-malware-policies.md)。

## <a name="part-2---anti-phishing-protection-in-eop-and-defender-for-office-365"></a>第 2 部分 - EOP 和 Defender for Office 365

[反钓鱼软件防护](anti-phishing-protection.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。 高级反钓鱼保护在 [Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 中可用。

有关反网络钓鱼策略的建议设置详细信息，请参阅[EOP anti-phishing policy settings](recommended-settings-for-eop-and-office365.md#eop-anti-phishing-policy-settings)和 Microsoft Defender for Office 365 中的反网络钓鱼[策略设置](recommended-settings-for-eop-and-office365.md#anti-phishing-policy-settings-in-microsoft-defender-for-office-365)。

以下过程介绍如何配置默认的防钓鱼策略。 设置 Defender for Office 365中提供的信息会进行清晰标记。

1. 打开 <https://security.microsoft.com/antiphishing> 。

2. 在 **"防钓鱼"** 页面上，单击该名称，选择名为 **"Office365** 反钓鱼默认 (默认) "策略。

3. 在出现的策略详细信息飞出中，配置以下设置：

   - **网络钓鱼阈值&保护** 部分：单击"编辑保护设置"，然后配置打开的"编辑保护设置"飞出控件中的以下设置：
     - **网络钓鱼电子邮件阈值**：选择 <sup>\*</sup> **2 - (** 标准) 或 3 - 更主动 (严格 **) 。**
     - **模拟** 部分 <sup>\*</sup> ：配置以下值：
       - 选择"允许用户保护"，单击出现的"管理 **(nn)** 发件人 () "链接，然后添加内部和外部发件人，防止模拟，例如组织的会员、CEO、CFO 和其他高级领导。
       - 选择 **"启用域以保护"，** 然后配置出现的以下设置：
         - 选择 **"包括我拥有域**"以保护接受域中的内部发件人 (通过单击"查看我的域) 进行模拟"。
         - 若要保护其他域中的发件人，请选择"包括自定义域"，单击出现的"管理 (nn) 自定义域 **() "** 链接，然后添加其他域防止模拟。
     - 添加受信任的发件人和域部分：单击"管理 (nn) 受信任发件人 () 和域 <sup>\*</sup> (**) "** 以根据需要将发件人和发件人域例外配置为模拟保护。
     - 邮箱智能设置 <sup>\*</sup> ：验证是否 **选择了"启用邮箱智能****"和"启用模拟保护的** 智能"。
     - **欺骗** 部分：验证 **是否选择了"启用欺骗** 智能"。

     完成时，请单击“保存”。

   - **"** 操作"部分：单击 **"编辑操作** "，然后配置打开的"编辑 **操作** "飞出控件中的以下设置：
     - **"邮件** 操作"部分：配置以下设置：
       - **如果邮件被检测为模拟用户** <sup>\*</sup> ：请选择 **"隔离邮件"。**
       - **如果邮件被检测为模拟域** <sup>\*</sup> ：选择 **隔离邮件**。
       - **如果邮箱智能检测到模拟** 用户：选择"将邮件移动到收件人的垃圾邮件文件夹" ("标准) "或"隔离 (<sup>\*</sup> 严格) "。  
       - **如果邮件被检测** 为欺骗邮件：选择"将邮件移动到收件人的垃圾邮件文件夹" (标准) 或"隔离 (严格) "。 
     - **安全提示&** 指示器部分：配置以下设置：
       - **显示用户模拟安全提示：** <sup>\*</sup> 选择 (启用) 。
       - **显示域模拟安全提示：** <sup>\*</sup> 选择 (启用) 。
       - **显示用户模拟异常字符安全提示：** 选择 <sup>\*</sup> (打开) 。
       - **显示 (？)** 欺骗的未经身份验证的发件人：选择 (打开) 。
       - **显示"via"标记**：如果 (此设置) ，请选择"打开"。

     完成时，请单击“保存”。

   <sup>\*</sup>此设置仅在 Defender for Office 365。

4. 单击 **"保存"，** 然后单击" **关闭"**

有关配置防钓鱼策略的详细说明，请参阅在[EOP](configure-anti-phishing-policies-eop.md)中配置防钓鱼策略和在 Microsoft Defender 中配置防钓鱼策略[Office 365。](configure-atp-anti-phishing-policies.md)

## <a name="part-3---anti-spam-protection-in-eop"></a>第 3 部分 - EOP 中的反垃圾邮件保护

有关反垃圾邮件的建议设置详细信息，请参阅 [EOP 反垃圾邮件策略设置](recommended-settings-for-eop-and-office365.md#eop-anti-spam-policy-settings)。

1. 打开 <https://security.microsoft.com/antispam> 。

2. 在 **"反垃圾邮件策略**"页上，单击该名称，从 ("默认) "列表中选择名为"反垃圾邮件入站策略"的策略。

3. 在出现的策略详细信息飞出中，执行以下步骤：
   - **批量电子邮件阈值&"垃圾邮件属性"** 部分：单击"**编辑垃圾邮件阈值和属性"。** 在 **出现的垃圾邮件阈值和属性** 飞出控件中，将"批量电子邮件阈值"设置为 5 (Strict) 或 6 (Standard) 。 完成时，请单击“保存”。
   - **允许和阻止的发件人和域** 部分：查看或编辑允许的发件人和允许的域。

4. 完成后，单击“关闭”。

有关配置反垃圾邮件策略的详细说明，请参阅在 EOP 中配置 [反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>第四部分 - 防护恶意 URL 和文件带来的威胁（Defender for Office 365 中的安全链接和安全附件）

抵御恶意 URL 和文件的单击时防护在包含 [Microsoft Defender for Office 365](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 的订阅中可用。 通过 “[安全附件](safe-attachments.md)”和“[安全链接](safe-links.md)”策略设置。

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>在 Defender for Office 365 中的安全附件策略

要设置[安全附件](safe-attachments.md)，创建至少一个安全链接策略。

1. 在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**ATP 安全附件**”，然后单击“**创建**”。

2. 在出现的 **新安全附件策略** 向导中，配置下列设置：

   - 在“**名称**”框中，键入 `Block malware`，然后单击“**下一步**”。

   - 在“**设置**”页上，配置下列设置：
     - 在“**安全附件未知恶意软件响应**”中，选择“**阻止**”。
     - 在“**重定向附件**”中，选择“**启用重定向**”。 为组织中检查检测到的文件的安全管理员或操作员指定电子邮件地址。

     单击“**下一步**”。

3. 在“**应用到**”页面， 单击“**添加条件**”，选择“**应用条件：收件人域为**”， 单击“**添加**”，选择域，单击“**添加**”， 单击“**完成**”， 然后单击“**下一步**”。

4. 检查设置，然后单击“**完成**”。

### <a name="safe-links-policies-in-microsoft-defender-for-office-365"></a>在 Defender for Office 365 中设置安全链接策略

要设置“[安全链接](safe-links.md)”，检查并编辑你的安全链接全局设置，然后创建至少一个安全链接策略。

1. 在“[安全与合规中心](https://protection.office.com)“中，选择“**威胁管理**” \> “**策略**” \> **ATP 安全链接**，然后单击“**全局设置**”，然后配置下列设置：

   - 验证“**使用安全链接于：Office 365 应用**”已经“![打开](../../media/scc-toggle-on.png)”。
   - “**用户单击安全链接时不要跟踪**”：关闭来跟踪用户单击操作：“![关闭](../../media/scc-toggle-off.png)”。
   - “**不允许用户单击安全链接至初始 URL**“：验证此设置打开：”![打开](../../media/scc-toggle-on.png)“。

   完成后，单击“**保存**”。

2. 回到安全链接主界面，单击”**创建**“。

3. 在出现的 **创建安全链接策略** 向导中，配置下列设置：

   - 在“**名称**”框中，键入名称（如 `Safe Links`），然后单击”**下一步**“。

   - 在“**设置**”页上，配置下列设置：
     - 对于“**选择要对邮件中的未知潜在恶意 URL 执行的操作**”，选择“**打开**”。
     - 对于“**选择要对 Microsoft Teams 中的未知或潜在恶意 URL 执行的操作**”，选择“**打开**”。
     - **对组织内发送的电子邮件应用安全链接**
     - **等待 URL 扫描完成，然后再传递邮件**
     - **对组织内发送的电子邮件应用安全链接**
     - **不允许用户单击至初始 URL**

     单击“**下一步**”。

4. 在“**应用到**”页面， 单击“**添加条件**”，选择“**应用条件：收件人域为**”， 单击“**添加**”，选择域，单击“**添加**”， 单击“**完成**”， 然后单击“**下一步**”。

5. 检查设置，然后单击“**完成**”。

若要了解详细信息，请参阅“[设置安全链接策略](set-up-safe-links-policies.md)”。

## <a name="part-5---verify-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>第 5 部分 - 保险箱是否SharePoint、OneDrive和Microsoft Teams附件

SharePoint、OneDrive 和 Teams 这样的工作负载是为协作而构建的。 使用 Defender for Office 365 帮助组织和检测在团队站点和文件库中识别为恶意的文件。 你可以在[这里](mdo-for-spo-odb-and-teams.md)阅读有关详细信息。

> [!IMPORTANT]
> **开始此过程前，确保 Microsoft 365 环境的审核日志已打开**。 通常是由在 Exchange Online 中分配为审核日志的角色执行。 有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)！

1. 在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**ATP 安全附件**”，然后单击“**全局设置**”。

2. 验证打开 **Defender for Office 365 for SharePoint、OneDrive** 和 Microsoft Teams 开关是否位于右侧：打开切换，然后单击 ![ ](../../media/scc-toggle-on.png) 保存。 

3. 检查（并合适地编辑）组织的[安全附件策略](set-up-safe-attachments-policies.md)和[安全链接策略](set-up-safe-links-policies.md)。

4. （推荐）作为全局管理员或 SharePoint 在线管理员，在 _DisallowInfectedFileDownload_ 参数设置为 `$true` 时运行 **[Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet。

   - `$true`阻止所有检测到文件的操作（除了删除）。 人员不能打开、移动、复制或共享检测到的文件。
   - `$false`阻止所有除删除和下载的操作。 人员可以选择接受风险并下载检测到的文件。

   > [!TIP]
   > 了解更多用 Microsoft 365 使用 PowerShell 的信息，请参阅[使用 PowerShell 管理 Microsoft 365](../../enterprise/manage-microsoft-365-with-microsoft-365-powershell.md)。

5. 预留至多 30 分钟以让更改传播到所有 Microsoft 365 数据中心。

### <a name="now-set-up-alerts-for-detected-files"></a>现在为检测到的文件设置警报

若要当 SharePoint Oline、OneDrive for Business 或Microsoft Teams 中的文件识别为恶意文件时收到通知，你可以设置警报。

1. 在 [安全与合规中心](https://protection.office.com)内，依次转到“**警报**\>“**管理警报**”。

2. 选择“**新建警报策略**”。

3. 指定警报名称。 比如，你可以在库中键入恶意文件。

4. 键入警报说明。 比如，当恶意文件在 SharePoint Online、OneDrive 或 Microsoft Teams 中检测到时，你可以键入通知管理员。

5. 在“**当...时发送此警报**”中，设置：

   a. 在“**活动**”列表，选择“**文件中检测到的恶意软件**”。

   b. 留空 **用户** 字段。

6. 在 **将此警报发送至...** 中，选择一个或多个全局管理员，安全管理员，或安全读取者，他们会在监测到恶意软件时接收通知。

7. **保存**。

了解更多关于警报的信息，请参阅[在安全与合规中心中创建活动警报](../../compliance/create-activity-alerts.md)。

> [!NOTE]
> 当你完成配置时，使用这些链接开始工作负载调查：
>
>- [威胁防护状态报告](view-email-security-reports.md#threat-protection-status-report)
>- [使用 Microsoft 365 Defender 门户管理 Defender for Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)
>- [在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到恶意文件需采取的操作](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [在 Microsoft 365 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>第六部分 - 配置额外设置

除了配置恶意软件防护，恶意 URL 和文件、钓鱼软件和垃圾邮件之外，我们推荐你配置零时差自动清除。

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP 中电子邮件零时差自动清除

[零时差自动清除](zero-hour-auto-purge.md)在包含 [EOP](/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。 此防护默认开启；但是，防护有效的前提是下列情况满足：

- 在“[反垃圾邮件策略](anti-spam-protection.md)”中调整垃圾邮件设置为“**将消息移到垃圾邮件文件夹**”。

- 用户保持默认的[垃圾邮件设置](configure-junk-email-settings-on-exo-mailboxes.md)，且没有关闭垃圾邮件保护。

若要详细了解，请参阅[零时差自动清除 - 抵御垃圾邮件和恶意软件](zero-hour-auto-purge.md)。

## <a name="post-setup-tasks-and-next-steps"></a>安装后任务和接下来的步骤

配置威胁防护功能之后，确保监控这些功能的运行情况！ 检查并修改你的策略，让它们按你的需求运行。 同时，关注可以增加价值的新功能和服务。

****

|需执行的操作|了解详细信息的资源|
|---|---|
|通过查看报告了解威胁防护功能如何为你的阻止工作|[安全操作仪表板](security-dashboard.md) <p> [电子邮件安全报告](view-email-security-reports.md) <p> [Microsoft Defender for Office 365 报告](view-reports-for-mdo.md) <p> [威胁资源管理器](threat-explorer.md)|
|定期检查和修改你的威胁防护策略（如有需要）|[安全功能分数](../defender/microsoft-secure-score.md) <p> [智能报告和见解](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 威胁调查和响应功能](./office-365-ti.md)|
|关注新功能和服务更新|[标准和目标发布选项](../../admin/manage/release-options-in-office-365.md) <p> [消息中心](../../admin/manage/message-center.md) <p> [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [服务说明](/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|了解配置 EOP 和 Defender for Office 365 的标准和严格安全配置推荐的详细信息|[用于配置 EOP 和 Defender for Office 365 安全性的建议设置](recommended-settings-for-eop-and-office365.md)|
