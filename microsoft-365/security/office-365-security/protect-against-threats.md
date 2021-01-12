---
title: 抵御威胁
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
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
ms.openlocfilehash: 2951d5725237d572d357ac3fc6cff0ac4df7e8f0
ms.sourcegitcommit: 9833f95ab6ab95aea20d68a277246dca2223f93d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/11/2021
ms.locfileid: "49794432"
---
# <a name="protect-against-threats"></a>抵御威胁

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


这是一个快速的指南，它将 Defender for Office 365 的配置分成块。 如果你对 Microsoft Office 365 中的威胁防护功能不了解，不知道从哪里开始，或者你喜欢通过 *上手* 来学习，使用这个指南作为一个清单和开始。

> [!IMPORTANT]
> **包括了适合每种策略的初步推荐设置；然后，很多选项都可用，你可以调整设置以满足具体的组织需要**。 预留大概 30 分钟以让你的策略或更改在你的数据中心中正常工作。

## <a name="requirements"></a>要求

### <a name="subscriptions"></a>订阅

威胁防护功能含在 *所有* Microsoft 或 Office 365 订阅中；然而，一些订阅有高级功能。 下面的表格列出了包含在此文章中的防护功能，以及最低订阅要求。

> [!TIP]
> 注意，在打开审核之外，还包含开启反恶意软件、反钓鱼、反垃圾邮件的 *步骤*，这些是 Office 365 Exchange Online Protection (**EOP**) 的一部分。 在你记住 (**Defender for Office 365**) 包含内容、基础、EOP 之前，这可能在 Defender for Office 365 的文章里看起来很奇怪。

****

|防护类型|订阅要求|
|---|---|
|审核日志（出于报告的目的）|[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|反恶意软件保护|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**)|
|防钓鱼保护|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|反垃圾邮件保护|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|零时差自动清除 (电子邮件)|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|防护 Office 文件和电子邮件中的恶意 URL 和文件带来的威胁（安全链接和安全附件）|[Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|启用适用于 SharePoint、OneDrive 和 Microsoft Teams 工作负载的 ATP|[Defender for Office 365](atp-for-spo-odb-and-teams.md)|
|高级反钓鱼保护|[Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>角色和权限

若要配置 Defender for Office 365 策略，必须在[安全与合规中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)分配给你一个适当的角色。 看看下面的表格，了解可以执行这些操作的角色。

****

|角色或角色组|在哪里了解更多信息|
|---|---|
|全局管理员|[关于 Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|安全管理员|[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 组织管理|[Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> 和 <p> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

若要了解详细信息，请参阅 [安全与合规中心的访问权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>开始前，打开报告和调查的审核日志

早点开始审核日志。 你将需要“**打开**”审核，以执行下面的一些步骤。 审核日志在包括[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的订阅中可用。 为了查看威胁防护报告中的数据，比如 [安全性仪表板](security-dashboard.md)、[电子邮件安全报告](view-email-security-reports.md)、[Explorer](threat-explorer.md)，审核日志必须“*打开*”。 有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="part-1---anti-malware-protection"></a>第一部分 - 反恶意软件保护

[反恶意软件防护](anti-malware-protection.md)在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。

1. 在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**反恶意软件**”。

2. 双击“**默认**”策略，然后选择“**设置**”。

3. 指定以下设置：

    - 在“**反恶意软件检测响应**”中，保持默认设置“**不**”。

    - 在“**常见附件类型筛选器**”中，选择“**打开**”。

4. 单击“**保存**”。

了解更多关于反恶意软件策略选项的信息，请参阅[配置反恶意软件策略](configure-anti-malware-policies.md)。

## <a name="part-2---anti-phishing-protection"></a>第二部分 - 防钓鱼保护

[反钓鱼软件防护](anti-phishing-protection.md)在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。 高级反钓鱼保护在 [Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 中可用。

下列过程介绍了如何在 Microsoft Defender for Office 365 中配置反钓鱼策略。 这些步骤与在 EOP 中配置反钓鱼策略相似。

1. 在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**ATP 反钓鱼**”。

2. 单机“**默认策略**”。

3. 在“**模拟**”中，单击“**编辑**”，然后指定下列设置：

   - 在“**添加保护用户**”选项卡中，“*打开*”防护。 然后添加用户，比如组织的董事会成员、CEO、CFO 和其他高级官员。 （你可以键入个人的电子邮件账号，或单击显示一个列表。）

   - 在“**添加保护域**”选项卡中，开大“**自动包含我拥有的域**”。 如果你有自定义的域，添加它们。

   - 在“**操作**”选项卡中，选择“**隔离消息**”，对“**模拟用户**”和“**模拟域**”选项适用。 同时，打开模拟安全提示。

   - 在“**邮箱智能**”选项卡中，确保邮箱智能打开，且打开邮箱基于智能的模拟防护。 在“**如果模拟用户发送电子邮件**” 列表中，选择“**隔离此消息**”。

   - 在“**添加信任的发送者和域**”选项卡中，指定任何你想添加的信任的发送者和域。

   - 检查设置后，在“**检查你的设置**”选项卡中，“**保存**”。

4. 在“**欺骗**”中，单击“**编辑**”，然后指定下列设置：

   - 在“**欺骗筛选器设置**”选项卡中，确保反欺骗保护已开启。

   - 在“**操作**”选项卡中，选择“**隔离此消息**”。

   - 检查更改后，在“**检查你的设置**”选项卡中，“**保存**”。 （如果你没有做出任何更改，“**取消**。”）

5. 关闭默认策略设置页面。

若要了解关于反钓鱼策略选项详细信息，请参阅[在 Microsoft Defender for Office 365 中配置防钓鱼策略](configure-atp-anti-phishing-policies.md)。

## <a name="part-3---anti-spam-protection"></a>第三部分 - 电子邮件反垃圾邮件保护

[反垃圾邮件软件防护](anti-spam-protection.md)在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。

1. 在 [安全与合规中心](https://protection.office.com)内，依次转到“**威胁管理**”\>“**策略**”\>“**反垃圾邮件**”。

2. 在“**自定义**”选项卡中，打开自定义设置。

3. 展开“**默认垃圾邮件筛选器策略**”，单击“**编辑策略**”，然后指定下列设置：

   - 在“**垃圾邮件和批量操作**”中，设置值的阈值为 5 或 6。

   - 在“**允许列表**”中，检查（和/或编辑）你的受信任发送者和域。

4. 单击“**保存**”。

了解更多关于反垃圾邮件策略选项的信息，请参阅[配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments-in-defender-for-office-365"></a>第四部分 - 防护恶意 URL 和文件带来的威胁（Defender for Office 365 中的安全链接和安全附件）

抵御恶意 URL 和文件的单击时防护在包含 [Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 的订阅中可用。 通过 “[安全附件](atp-safe-attachments.md)”和“[安全链接](atp-safe-links.md)”策略设置。

### <a name="safe-attachments-policies-in-microsoft-defender-for-office-365"></a>在 Defender for Office 365 中的安全附件策略

要设置[安全附件](atp-safe-attachments.md)，创建至少一个安全链接策略。

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

要设置“[安全链接](atp-safe-links.md)”，检查并编辑你的安全链接全局设置，然后创建至少一个安全链接策略。

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

若要了解详细信息，请参阅“[设置安全链接策略](set-up-atp-safe-links-policies.md)”。

## <a name="part-5---verify-atp-for-sharepoint-onedrive-and-microsoft-teams-is-turned-on"></a>第五部分 - 验证适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP

SharePoint、OneDrive 和 Teams 这样的工作负载是为协作而构建的。 使用 Defender for Office 365 帮助组织和检测在团队站点和文件库中识别为恶意的文件。 你可以在[这里](atp-for-spo-odb-and-teams.md)阅读有关详细信息。

> [!IMPORTANT]
> **开始此过程前，确保 Microsoft 365 环境的审核日志已打开**。 通常是由在 Exchange Online 中分配为审核日志的角色执行。 有关详细信息，请参阅[打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)！

1. 在 [安全与合规中心](https://protection.office.com)中， 选择“**威胁管理**” \> “**策略**” \> “**ATP 安全附件**”，然后单击“**全局设置**”。

2. 验证“**为 SharePoint、OneDrive 和 Microsoft Teams 启用 ATP**”切换键在右边：“![打开](../../media/scc-toggle-on.png)”，然后单击“**保存**”。

3. 检查（并合适地编辑）组织的[安全附件策略](set-up-atp-safe-attachments-policies.md)和[安全链接策略](set-up-atp-safe-links-policies.md)。

4. （推荐）作为全局管理员或 SharePoint 在线管理员，在 _DisallowInfectedFileDownload_ 参数设置为 `$true` 时运行 **[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet。

   - `$true`阻止所有检测到文件的操作（除了删除）。 人员不能打开、移动、复制或共享检测到的文件。
   - `$false`阻止所有除删除和下载的操作。 人员可以选择接受风险并下载检测到的文件。

   > [!TIP]
   > 了解更多用 Microsoft 365 使用 PowerShell 的信息，请参阅[使用 PowerShell 管理 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)。

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
>- [使用安全与合规中心管理隔离文件](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)
>- [在 SharePoint Online、OneDrive 或 Microsoft Teams 中找到恶意文件需采取的操作](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
>- [在 Microsoft 365 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>第六部分 - 配置额外设置

除了配置恶意软件防护，恶意 URL 和文件、钓鱼软件和垃圾邮件之外，我们推荐你配置零时差自动清除。

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP 中电子邮件零时差自动清除

[零时差自动清除](zero-hour-auto-purge.md)在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) 的订阅中可用。 此防护默认开启；但是，防护有效的前提是下列情况满足：

- 在“[反垃圾邮件策略](anti-spam-protection.md)”中调整垃圾邮件设置为“**将消息移到垃圾邮件文件夹**”。

- 用户保持默认的[垃圾邮件设置](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，且没有关闭垃圾邮件保护。

若要详细了解，请参阅[零时差自动清除 - 抵御垃圾邮件和恶意软件](zero-hour-auto-purge.md)。

## <a name="post-setup-tasks-and-next-steps"></a>安装后任务和接下来的步骤

配置威胁防护功能之后，确保监控这些功能的运行情况！ 检查并修改你的策略，让它们按你的需求运行。 同时，关注可以增加价值的新功能和服务。

****

|需执行的操作|了解详细信息的资源|
|---|---|
|通过查看报告了解威胁防护功能如何为你的阻止工作|[安全操作仪表板](security-dashboard.md) <p> [电子邮件安全报告](view-email-security-reports.md) <p> [Microsoft Defender for Office 365 报告](view-reports-for-atp.md) <p> [威胁资源管理器](threat-explorer.md)|
|定期检查和修改你的威胁防护策略（如有需要）|[安全功能分数](../mtp/microsoft-secure-score.md) <p> [智能报告和见解](reports-and-insights-in-security-and-compliance.md) <p> [Microsoft 365 威胁调查和响应功能](keep-users-safe-with-office-365-ti.md)|
|关注新功能和服务更新|[标准和目标发布选项](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365) <p> [消息中心](https://docs.microsoft.com/microsoft-365/admin/manage/message-center) <p> [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection) <p> [服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|了解配置 EOP 和 Defender for Office 365 的标准和严格安全配置推荐的详细信息|[用于配置 EOP 和 Defender for Office 365 安全性的建议设置](recommended-settings-for-eop-and-office365-atp.md)|
