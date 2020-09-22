---
title: 保护免遭威胁侵害
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
description: 管理员可以了解 Microsoft 365 中的威胁防护，并配置如何将其用于组织。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 1ad74e9bdcd7b937873108d2ba049c16db8c235b
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48202575"
---
# <a name="protect-against-threats"></a>保护免遭威胁侵害

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


下面是一个快速入门指南，用于将高级威胁防护的配置分解为多个块。 如果你刚开始使用 Office 365 中的威胁防护功能，则不确定从哪里开始，或者如果你了解 *最佳方法，* 请使用本指南作为检查表和起点。

> [!IMPORTANT]
> **为每种策略提供了初始推荐设置; 但是，有许多可用选项，您可以调整设置以满足特定组织的需求**。 为你的策略或更改允许大约30分钟，以在你的数据中心中工作。

## <a name="requirements"></a>Requirements

### <a name="subscriptions"></a>订阅

威胁防护功能包含在 *所有* Microsoft 或 Office 365 订阅中;但是，有些订阅具有高级功能。 下表列出了本文附带的保护功能以及最低订阅要求。

> [!TIP]
> 请注意，除了打开审核的说明之外， *步骤* 还启动反恶意软件、反网络钓鱼和反垃圾邮件，它们被标记为 Office 365 Exchange Online Protection (**EOP**) 的一部分。 这在高级威胁防护文章中似乎是不正常的，除非您记下高级威胁防护 (**ATP**) 包含，并在 EOP 中进行构建。

****

|保护类型|订阅要求|
|---|---|
|用于报告目的的审核日志记录 () |[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|反恶意软件保护|[Exchange Online Protection](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) (**EOP**) |
|防钓鱼保护|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|反垃圾邮件保护|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|电子邮件的零小时自动清除 () |[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|防止电子邮件和 Office 文档中的恶意 Url 和文件 (安全链接和安全附件) |[Office 365 高级威胁防护](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (**ATP**) |
|为 SharePoint、OneDrive 和 Microsoft 团队工作负荷启用 ATP| [ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide)|
|高级反网络钓鱼防护|[ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|

### <a name="roles-and-permissions"></a>角色和权限

若要配置 ATP 策略，必须在 [安全 & 合规性中心](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)中为您分配适当的角色。 有关可执行这些操作的角色，请查看下面的表格。

****

|角色或角色组|了解详细信息|
|---|---|
|全局管理员|[关于 Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|安全管理员|[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 组织管理|[Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>和<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

若要了解详细信息，请参阅 [安全 &amp; 合规性中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="before-you-begin-turn-on-audit-logging-for-reporting-and-investigation"></a>在开始之前，请启用报告和调查的审核日志记录

尽早启动审核日志记录。 您 **需要进行审核** ，以确保执行后续步骤。 审核日志记录在包括 [Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)的订阅中可用。 为了查看威胁防护报告中的数据（如 [安全仪表板](security-dashboard.md)、 [电子邮件安全报告](view-email-security-reports.md)和 [浏览器](threat-explorer.md)），审核日志记录必须 *打开*。 若要了解详细信息，请参阅 [打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)。

## <a name="part-1---anti-malware-protection"></a>第1部分-反恶意软件保护

[反恶意软件保护](anti-malware-protection.md) 在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的订阅中可用。

1. 在[安全 & 合规性中心](https://protection.office.com)中，选择 "**威胁管理**  >  **策略**  >  **反恶意软件**"。

2. 双击 **默认** 策略，然后选择 " **设置**"。

3. 指定以下设置：

    - 在 " **恶意软件检测响应** " 部分，保留默认设置 " **否**"。

    - 在 " **常见附件类型筛选器** " 部分，选择 **"启用"**。

4. 单击“**保存**”。

若要了解有关反恶意软件策略选项的详细信息，请参阅 [配置反恶意软件策略](configure-anti-malware-policies.md)。

## <a name="part-2---anti-phishing-protection"></a>第2部分-反网络钓鱼防护

[反钓鱼]

在包含[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的订阅中提供了[反网络钓鱼保护](anti-phishing-protection.md)。 在 [ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)中提供高级反钓鱼保护。

以下过程介绍如何配置 ATP 反网络钓鱼策略。 在不使用 ATP) 配置反网络钓鱼策略 (的步骤类似。

1. 在[安全 & 合规性中心](https://protection.office.com)中，选择**威胁管理**  >  **策略**  >  **ATP 反网络钓鱼**。

2. 单击 " **默认策略**"。

3. 在 " **模拟** " 部分，单击 " **编辑**"，然后指定以下设置：

   - 在 " **添加要保护的用户** " 选项 *卡上，打开保护* 。 然后添加用户，如贵组织的董事会成员、CEO、CFO 和其他高级领导者。  (您可以键入单个电子邮件地址，或单击以显示列表。 ) 

   - 在 " **要保护的添加域** " 选项卡上，打开 " **自动包括我拥有的域"**。 如果你有自定义域，请立即添加。

   - 在 "**操作**" 选项卡上，选择 "隔离**模拟用户**和**模拟域**的**邮件"** 选项。 此外，打开模拟安全提示。

   - 在 " **邮箱智能** " 选项卡上，确保已打开邮箱智能，并启用基于邮箱智能的模拟保护。 在 " **如果模拟用户发送电子邮件** " 列表中，选择 **"隔离邮件"**。

   - 在 " **添加受信任的发件人和域** " 选项卡上，指定要添加的任何受信任的发件人或域。

   - 查看设置后，**保存**在 "**查看您的设置**" 选项卡上。

4. 在 " **欺骗** " 部分，单击 " **编辑**"，然后指定以下设置：

   - 在 " **哄骗筛选器设置** " 选项卡上，确保已打开 "反欺骗保护"。

   - 在 " **操作** " 选项卡上，选择 " **隔离邮件"**。

   - 在审阅完更改后，**保存**在 "**查看您的设置**" 选项卡上。  (如果未进行任何更改，请 **取消**。 ) 

5. 关闭 "默认策略设置" 页。

若要了解有关反网络钓鱼策略选项的详细信息，请参阅 [配置 ATP 反网络钓鱼策略](configure-atp-anti-phishing-policies.md)。

## <a name="part-3---anti-spam-protection"></a>第3部分-反垃圾邮件保护

[反垃圾邮件保护](anti-spam-protection.md) 在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的订阅中可用。

1. 在[安全 & 合规性中心](https://protection.office.com)中，选择 "**威胁管理**  >  **策略**  >  **反垃圾邮件**"。

2. 在 " **自定义** " 选项卡上，打开 "自定义设置"。

3. 展开 " **默认垃圾邮件筛选器策略**"，单击 " **编辑策略**"，然后指定以下设置：

   - 在 " **垃圾邮件和批量操作** " 部分，将阈值设置为值5或6。

   - 在 " **允许列表** " 部分，查看 (和/或编辑) 您允许的发件人和域。

4. 单击“**保存**”。

若要了解有关您的反垃圾邮件策略选项的详细信息，请参阅 [在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="part-4---protection-from-malicious-urls-and-files-safe-links-and-safe-attachments"></a>第4部分-防止恶意 Url 和文件 (安全链接和安全附件) 

来自恶意 Url 和文件的点击时间保护在包含 [Office 365 atp](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (atp) 的订阅中可用。 它通过 [Atp 安全附件](atp-safe-attachments.md) 和 [atp 安全链接](atp-safe-links.md) 策略进行设置。

### <a name="atp-safe-attachments-policies"></a>ATP 安全附件策略

若要设置 [Atp 安全附件](atp-safe-attachments.md)，必须至少定义一个 ATP 安全附件策略。

1. 在 "[安全性 & 合规性中心](https://protection.office.com)中，选择"**威胁管理**  >  **策略**  >  **ATP 安全附件**"。

2. 选择 " **打开适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP**" 选项。

3. 在 " **保护电子邮件附件** " 部分，单击加号 (**+**) 。

4. 指定以下设置：

   - 在 " **名称** " 框中，键入 `Block malware` 。

   - 在 "响应" 部分，选择 " **阻止**"。

   - 在 " **重定向附件** " 部分，选择 " **启用重定向**" 选项。 指定组织的安全管理员或操作员的电子邮件地址，该地址将审阅检测到的文件。

   - 在 " **应用** 于" 部分中，选择 **"收件人域"**。 然后，选择您的域，选择 " **添加**"，然后选择 **"确定"**。

5. **保存**。

6.  (**建议的其他步骤**) 为全局管理员或 SharePoint Online 管理员，请运行 Microsoft 365 环境的**DisallowInfectedFileDownload**参数设置为*true*的**[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet。  (这将阻止用户打开、移动、复制或共享被检测为恶意的文件 ) 

若要了解详细信息，请参阅 [设置 office 365 Atp 安全附件策略](set-up-atp-safe-attachments-policies.md) 和 [打开 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 ATP](turn-on-atp-for-spo-odb-and-teams.md)。

### <a name="atp-safe-links-policies"></a>ATP 安全链接策略

若要设置 [ATP 安全链接](atp-safe-links.md)，请查看并编辑默认策略，并为特定用户添加策略。

1. 在 "[安全性 & 合规性中心](https://protection.office.com)中，选择"**威胁管理**  >  **策略**  >  **ATP 安全链接**"。

2. 双击 **默认** 策略。

3. 在 " **使用安全链接** " 部分，选择 " **Microsoft 365 Apps For enterprise，Office For iOS 和 Android**" 选项，然后单击 " **保存**"。

4. 在 " **适用于特定收件人的策略** " 部分，单击加号 (**+**) 。

5. 指定以下设置：

   - 在 " **名称** " 框中，键入一个名称，例如 `Safe Links` 。

   - 在 " **选择操作** " 部分，选择 **"启用"**。

   - 选择以下选项：

     - **使用安全附件扫描可下载的内容**

     - **将安全链接应用于在组织内发送的电子邮件**

     - **不要让用户通过指向原始 URL 的安全链接进行单击**

   - 在 " **应用** 于" 部分中，选择 **"收件人域"**。 然后，选择您的域，选择 " **添加**"，然后选择 **"确定"**。

6. **保存**。

若要了解详细信息，请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。

## <a name="part-5---turn-on-atp-for-sharepoint-onedrive-and-microsoft-teams-workloads"></a>第5部分-打开适用于 SharePoint、OneDrive 和 Microsoft 团队工作负荷的 ATP

SharePoint、OneDrive 和团队等工作负荷是为协作而构建的。 使用 ATP 有助于阻止和检测在工作组网站和文档库中被标识为恶意的文件。 您可以阅读有关 [此处](https://docs.microsoft.com/microsoft-365/security/office-365-security/atp-for-spo-odb-and-teams?view=o365-worldwide)的工作方式的详细信息。

> [!IMPORTANT]
> 在**开始此过程之前，请确保已为您的 Microsoft 365 环境启用审核日志记录**。 这通常由在 Exchange Online 中分配了审核日志角色的人完成。 有关详细信息，请参阅 [打开或关闭审核日志搜索](../../compliance/turn-audit-log-search-on-or-off.md)！

1. 转到 <https://protection.office.com> ，然后使用你的工作或学校帐户登录。

2. 在安全 & 合规性中心的左侧导航窗格中的 " **威胁管理**" 下，选择 " **策略** \> **安全附件**"。

   ![在安全 & 合规性中心中，选择威胁管理 \> 策略](../../media/08849c91-f043-4cd1-a55e-d440c86442f2.png)

3. 选择 " **为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP**"。

   ![为 SharePoint Online、OneDrive for Business 和 Microsoft 团队启用高级威胁防护](../../media/48cfaace-59cc-4e60-bf86-05ff6b99bdbf.png)

4. **保存**。

5. 查看 (，并根据需要编辑) 组织的 [安全附件策略](set-up-atp-safe-attachments-policies.md) 和 [安全链接策略](set-up-atp-safe-links-policies.md)。

6.  (推荐) 为全局管理员或 SharePoint Online 管理员，请运行 **[set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet，并将 _DisallowInfectedFileDownload_ 参数设置为 `$true` 。

   - `$true` 阻止除 Delete) 检测到的文件之外的所有操作 (。 用户无法打开、移动、复制或共享检测到的文件。
   - `$false` 阻止除 "删除" 和 "下载" 以外的所有操作。 用户可以选择接受风险并下载检测到的文件。

   > [!TIP]
   > 若要了解有关在 Microsoft 365 中使用 PowerShell 的详细信息，请参阅使用 [Powershell 管理 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/manage-microsoft-365-with-microsoft-365-powershell)。

7. 允许最长30分钟，你的更改将传播到所有 Microsoft 365 数据中心。

### <a name="now-set-up-alerts-for-detected-files"></a>现在为检测到的文件设置通知

若要在 SharePoint Online、OneDrive for Business 或 Microsoft 团队中的文件被标识为恶意文件时收到通知，可以设置警报。

1. 在 " [安全性 & 合规性中心](https://protection.office.com)中，选择" **通知**"" \> **管理通知**"。

2. 选择 " **新建警报策略**"。

3. 指定警报的名称。 例如，可以在库中键入恶意文件。

4. 键入警报的说明。 例如，可以键入在 SharePoint Online、OneDrive 或 Microsoft 团队中检测到恶意文件时通知管理员。

5. 在 "在 **以下时间发送此通知** " 部分中，设置：

   a. 在 " **活动** " 列表中，选择 " **文件中检测到的恶意软件**"。

   b. 将 " **用户** " 字段留空。

6. 在 " **将此通知发送给 ...** " 部分，选择一个或多个全局管理员、安全管理员或在检测到恶意文件时应收到通知的安全阅读者。

7. **保存**。

若要了解有关通知的详细信息，请参阅 [在安全 & 合规性中心中创建活动通知](../../compliance/create-activity-alerts.md)。

> [!NOTE]
> 完成配置后，请使用以下链接启动工作负荷调查：
>
> - [查看有关在 SharePoint、OneDrive 或 Microsoft 团队中检测到的恶意文件的信息](malicious-files-detected-in-spo-odb-or-teams.md)
> - [在 SharePoint Online、OneDrive 或 Microsoft 团队中找到恶意文件时要执行的操作](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)
> - [在 Microsoft 365 中以管理员身份管理隔离的邮件和文件](manage-quarantined-messages-and-files.md)

## <a name="part-6---additional-settings-to-configure"></a>第6部分-要配置的其他设置

通过对恶意软件、恶意 Url 和文件、网络钓鱼和垃圾邮件的保护进行配置，我们建议您配置零小时自动清除。

### <a name="zero-hour-auto-purge-for-email-in-eop"></a>EOP 中的电子邮件的零小时自动清除

[0 小时自动清除](zero-hour-auto-purge.md) (ZAP) 在包含 [EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)的订阅中可用。 此保护在默认情况下处于启用状态。但是，若要使保护生效，必须满足以下条件：

- 垃圾邮件操作设置为将**邮件移动到**[反垃圾邮件策略](anti-spam-protection.md)中的 "垃圾邮件" 文件夹。

- 用户保留其默认的 [垃圾邮件设置](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)，但尚未关闭垃圾邮件保护。

若要了解详细信息，请参阅 [针对垃圾邮件和恶意软件的零小时自动清除保护](zero-hour-auto-purge.md)。

## <a name="post-setup-tasks-and-next-steps"></a>安装后任务和后续步骤

在配置威胁防护功能之后，请务必监视这些功能的工作方式！ 查看和修订策略，以便他们可以执行所需的操作。 此外，还请注意可添加值的新功能和服务更新。

****

|需执行的操作|了解详细信息的资源|
|---|---|
|查看报告的威胁防护功能是如何为你的组织工作的|[安全仪表板](security-dashboard.md)<br/>[电子邮件安全报告](view-email-security-reports.md)<br/>[Office 365 ATP 报告](view-reports-for-atp.md)<br/>[威胁资源管理器](threat-explorer.md)|
|根据需要定期查看和修改威胁防护策略|[安全功能分数](../mtp/microsoft-secure-score.md)<br/>[智能报告和见解](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 威胁调查和响应功能](keep-users-safe-with-office-365-ti.md)|
|监视新功能和服务更新|[标准和目标发布选项](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[消息中心](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|了解有关 EOP 和 ATP 的推荐标准和严格安全配置的详细信息 | [EOP 和 Office 365 ATP 安全性的建议设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) |
