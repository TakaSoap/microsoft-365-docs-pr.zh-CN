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
ms.date: ''
search.appverid:
- MOE150
- MET150
ms.assetid: b10023f6-f30f-45d3-b3ad-b71aa4aa0d58
ms.collection:
- M365-security-compliance
description: 管理员可以了解 Microsoft 365 中的威胁防护，并配置如何将其用于组织。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8f1cecbb3141b4751778212025e5aad582707e12
ms.sourcegitcommit: e12fa502bc216f6083ef5666f693a04bb727d4df
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/20/2020
ms.locfileid: "46826821"
---
# <a name="protect-against-threats"></a>保护免遭威胁侵害

Microsoft 365 包括各种威胁防护功能。 下面是一个快速入门指南，你可以将其用作清单，以确保你的威胁防护功能已针对你的组织做了设置。 如果你不确定出 Office 365 中的威胁防护功能，或者不只是你不确定从哪里开始使用，请使用以下指南作为起点。

> [!IMPORTANT]
> **初始建议设置包括每种策略类型;但是，许多可用选项**，您可以根据特定组织的需求调整设置。 对于策略或更改大约 30 分钟，也可以使用更改来完成数据中心。

## <a name="requirements"></a>Requirements

### <a name="subscriptions"></a>订阅

所有 Microsoft 365 订阅中均包含威胁防护功能;但是，某些订阅包含更高级的功能。 下表列出了本文中包含的保护功能以及最低订阅要求。

****

|保护类型|订阅要求|
|---|---|
|反恶意软件保护|[使用](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description) EOP 管理 (Exchange Online) |
|防止电子邮件和 Office 文档中的恶意 URL 和文件|[Office 365 高级威胁防](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) 护 (ATP) |
|防钓鱼保护|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|高级防钓鱼保护|[Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)|
|反垃圾邮件保护|[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|电子邮件加密的零时 (自动清除) |[EOP](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)|
|审核 (用于报告目) |[Exchange Online](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)|
|

### <a name="roles-and-permissions"></a>角色和权限

您必须分配有适当的角色，才能在安全与 [合规&中配置策略](https://docs.microsoft.com/office365/servicedescriptions/office-365-platform-service-description/office-365-securitycompliance-center)。 下表提供一些示例：

****

|角色或角色组|了解详细信息在哪里|
|---|---|
|全局管理员|[关于 Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|安全管理员|[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)|
|Exchange Online 组织管理|[Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <br>和<br> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|

若要了解详细信息，请参阅 [安全合规中心 &amp; 中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="part-1---anti-malware-protection"></a>第 1 部分 - 反恶意软件保护

[反恶意软件保护](anti-malware-protection.md) 适用于包括 EOP 的 [订阅](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。

1. 在安全[与合规&，](https://protection.office.com)选择威**胁**  >  **管理**  >  **策略反恶意软件**。

2. 双击"默认 **"** 策略，**然后选择设置。**

3. 指定下列设置：

    - 在"**恶意软件检测响应"** 部分，保留默认设置"否 **"。**

    - 在"**常见附件类型筛选器"部分**中，选择"打开 **"。**

4. 单击“**保存**”。

有关反恶意软件策略选项的详细信息，请参阅配置 [反恶意软件策略](configure-anti-malware-policies.md)。

## <a name="part-2---protection-from-malicious-urls-and-files"></a>第 2 部分 - 防恶意 URL 和文件

来自恶意 URL 和文件的点击时保护适用于 [包括 Office 365 ATP](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description) (ATP) 的订阅，该订阅通过 ATP 安全附件和 [ATP](atp-safe-attachments.md) [安全链接](atp-safe-links.md) 策略进行设置。

### <a name="atp-safe-attachments-policies"></a>ATP 安全附件策略

若要设置 [ATP 安全附件，](atp-safe-attachments.md)必须至少定义一个 ATP 安全附件策略。

1. 在安全[与合规&中心](https://protection.office.com)内，选择**威**  >  **胁管理**  >  **策略 ATP 安全附件**。

2. 选择此选项 **"为 SharePoint、OneDrive 和 Microsoft Teams 打开 ATP"。**

3. 在" **保护电子邮件附件"** 部分中，单击加号 **+** () 。

4. 指定下列设置：

   - 在" **名称"** 框中，键入 `Block malware` .

   - 在响应部分，选择"**阻止"。**

   - 在" **重定向附件** "部分，选择 **"启用重定向"** 选项，然后为组织的安全管理员或话务员指定电子邮件地址，以查看检测到的文件。

   - 在"**适用于"部分**，选择"**收件人域为"。** 然后，选择您的域，选择"**添加"，** 然后单击"确定 **"。**

5. 单击“**保存**”。

6.  (**建议的额外**) 作为全局管理员或 SharePoint Online 管理员，为 Microsoft 365 环境运行**[Set-SPOTenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)** cmdlet，**将 DisallowInfectedFileDownload**参数设置为*true。*  (这会防止用户打开、移动、复制或共享检测为恶意文件) 

若要了解详细信息，请参阅["设置 Office 365 ATP 安全附件"策略，](set-up-atp-safe-attachments-policies.md)[并启用适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP。](turn-on-atp-for-spo-odb-and-teams.md)

### <a name="atp-safe-links-policies"></a>ATP 安全链接策略

若要设置 [ATP 安全链接，](atp-safe-links.md)请查看和编辑默认策略，并为特定用户添加策略。

1. 在安全[与合规&，](https://protection.office.com)选择 **"威**  >  **胁管理策略**  >  **ATP 安全链接"。**

2. 双击"默认 **"** 策略。

3. 在"**部分中使用安全链接"** 部分中，选择 **"Microsoft 365 企业应用版、Office for iOS"和"Outlook for Android"，** 然后单击"保存 **"。**

4. 在" **适用于特定收件人的策略"** 部分，单击加号 **+** () 。

5. 指定下列设置：

   - 在" **名称** "框中，键入名称，如 `Safe Links` 。

   - 在"**选择操作"部分中**，选择"打开 **"。**

   - 选择以下选项：

     - **使用安全附件扫描可下载的内容**

     - **向组织内发送的电子邮件应用安全链接**

     - **不允许用户单击至原始 URL 的安全链接**

   - 在"**适用于"部分**，选择"**收件人域为"。** 然后，选择您的域，选择"**添加"，** 然后单击"确定 **"。**

6. 单击“**保存**”。

若要了解详细信息，请参阅[设置 Office 365 ATP 安全链接策略](set-up-atp-safe-links-policies.md)。

## <a name="part-3---anti-phishing-protection"></a>第 3 部分 - 防钓鱼保护

[反网络钓鱼]

[在包括 EOP 的订阅中提供](anti-phishing-protection.md) 反网络钓鱼 [保护](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。 ATP 中提供高级反网络 [钓鱼保护](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)。

以下过程将介绍如何配置 ATP 防钓鱼策略。 这些步骤类似于在不包括 ATP 策略的情况下配置 (网络钓鱼) 。

1. 在安全[与&中心内，](https://protection.office.com)选择**威**  >  **胁**  >  **管理策略 ATP 防钓鱼**。

2. 单击 **"默认策略"。**

3. 在" **模拟"部分** ，单击" **编辑"，** 然后指定以下设置：

   - 在" **添加要保护的用户"** 选项卡上，打开保护。 然后添加用户，如组织的主层成员、CEO、CFO 和其他更高层领导。  (您可以键入单个电子邮件地址，或单击以显示 list.) 

   - 在"**添加域以保护"** 选项卡上，启用 **"自动包含我自己的域"。** 如果您有自定义域，则也请添加这些域。

   - 在 **"** 操作"选项卡上 **，选择模拟用户**和**模拟域**选项**的"隔离邮件"。** 此外，打开模拟安全提示。

   - 在 **"邮箱智能** "选项卡上，确保邮箱智能处于打开状态。 此外，启用基于邮箱智能的模拟保护。 在 **"如果电子邮件是由模拟用户列表发送**"中，请**选择"隔离邮件"。**

   - 在" **添加受信任的发件人和域** "选项卡上，指定要添加的任何受信任的发件人或域。

   - 在"**查看设置"** 选项卡上，查看设置后，单击"保存 **"。**

4. 在" **欺骗"** 部分， **单击"编辑**"，然后指定以下设置：

   - 在 **"欺骗检查** 设置"选项卡上，请确保启用反欺骗保护。

   - 在 **"操作**"**选项卡上，选择"隔离邮件"。**

   - 在"**查看设置"** 选项卡上，查看设置后，单击"保存 **"。**  (如果未进行任何更改，请单击 **"取消**.) 

5. 关闭默认的策略设置页。

若要了解有关反网络钓鱼策略选项的详细信息，请参阅配置 [ATP 防钓鱼策略](configure-atp-anti-phishing-policies.md)。

## <a name="part-4---anti-spam-protection"></a>第 4 部分 - 反垃圾邮件保护

[反垃圾邮件保护](anti-spam-protection.md) 适用于包括 EOP 在内的 [订阅](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)中。

1. 在安全[与合规&，](https://protection.office.com)选择威**胁**  >  **管理**  >  **策略反垃圾邮件**。

2. 在" **自定义"** 选项卡上，打开 **"自定义设置** "。

3. 展开 **"默认垃圾邮件筛选策略**"、单击 **"编辑策略**"，然后指定以下设置：

   - 在" **垃圾邮件和批量操作"** 部分，将阈值设为 5 或 6。

   - 在" **允许列表"** 部分， (根据需要编辑) 允许发件人和域。

4. 单击“**保存**”。

若要详细了解反垃圾邮件策略选项，请参阅在 [EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

## <a name="part-5---additional-settings-to-configure"></a>第 5 部分 - 要配置的其他设置

除了配置防止恶意软件、恶意 URL 和文件、网络钓鱼和垃圾邮件的保护，我们建议配置零时差自动清除和审核日志记录设置。

### <a name="zero-hour-auto-purge-for-email"></a>电子邮件的零时差自动清除

[零时差自动清除 (](zero-hour-auto-purge.md) ZAP) 包括 EOP 的订阅 [中可用](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-protection-service-description/exchange-online-protection-service-description)。 此保护默认处于打开状态;但是，保护必须满足以下条件才能生效：

- 在反垃圾邮件策略中 **，垃圾邮件操作被设置为"将邮件**[移动到"垃圾邮件"文件夹](anti-spam-protection.md)。

- 用户保留了他们的默认 [垃圾邮件设置，](ensure-that-spam-is-routed-to-each-user-s-junk-email-folder.md)但未关闭垃圾邮件保护。

若要了解详细信息， [请参阅零时差自动清除 - 防范垃圾邮件和恶意软件](zero-hour-auto-purge.md)。

### <a name="audit-logging-for-reporting-and-investigation"></a>报告和调查的审核日志记录

审核日志记录在包括 Exchange Online 的订阅 [中可用](https://docs.microsoft.com/office365/servicedescriptions/exchange-online-service-description/exchange-online-service-description)。 为了查看威胁防护报告中的数据（如 [安全仪表板](security-dashboard.md)、 [电子邮件安全报告](view-email-security-reports.md)和 [资源](threat-explorer.md)管理器），必须为组织启用审核日志记录。 若要了解详细信息，[请参阅审核日志打开或关闭搜索。](../../compliance/turn-audit-log-search-on-or-off.md)

## <a name="post-setup-tasks"></a>安装后任务

在配置威胁防护功能之后，请确保监视这些功能的运行方式、根据需要审核并修订策略，并观察新的功能和服务更新。

****

|需执行的操作|了解详细信息的资源|
|---|---|
|查看报告，了解威胁防护功能如何对组织工作|[安全仪表板](security-dashboard.md)<br/>[电子邮件安全报告](view-email-security-reports.md)<br/>[Office 365 ATP 报告](view-reports-for-atp.md)<br/>[威胁资源管理器](threat-explorer.md)|
|定期检查并修改威胁防护策略（如果需要）|[安全功能分数](../mtp/microsoft-secure-score.md)<br/>[智能报告和见解](reports-and-insights-in-security-and-compliance.md)<br/>[Microsoft 365 威胁调查和响应功能](keep-users-safe-with-office-365-ti.md)|
|观看新增功能和服务更新|[标准和定向发布选项](https://docs.microsoft.com/microsoft-365/admin/manage/release-options-in-office-365)<br/>[消息中心](https://docs.microsoft.com/microsoft-365/admin/manage/message-center)<br/>[Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)<br/>[服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-service-descriptions-technet-library)|
|
