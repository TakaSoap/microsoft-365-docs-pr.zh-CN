---
title: Microsoft Defender for Office 365
f1.keywords:
- CSH
ms.author: tracyp
author: msfttracyp
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Priority
search.appverid:
- MET150
- MOE150
ms.assetid: e100fe7c-f2a1-4b7d-9e08-622330b83653
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.custom:
- seo-marvel-apr2020
description: Microsoft Defender for Office 365 包括安全附件、安全链接、高级防钓鱼工具、报告工具和威胁智能功能。
ms.openlocfilehash: c102948ff66a6362a1adb60734629b79e7eb7ad5
ms.sourcegitcommit: 9546708a5506fdbadbfe2500cbf1bd1aeaec6fcb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/13/2020
ms.locfileid: "49021105"
---
# <a name="microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> 本文适用于拥有 [Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)的企业客户。 如果你使用的是 Outlook.com、Microsoft 365 家庭版或 Microsoft 365 个人版，并且正在查找有关 Outlook 中安全链接或安全附件的信息，请参阅[适用于 Microsoft 365 订阅者的高级 Outlook.com 安全机制](https://support.microsoft.com/office/882d2243-eab9-4545-a58a-b36fee4a46e2)。

Microsoft Defender for Office 365 可保护你的组织免受电子邮件、链接 (URL) 和协作工具带来的恶意威胁。 Defender for Office 365 包括：

- **[威胁防护策略](#configure-microsoft-defender-for-office-365-policies)** ：定义威胁防护策略，为组织设置适当级别的保护。

- **[报告](#view-microsoft-defender-for-office-365-reports)** ：查看实时报告，监视组织中的 Defender for Office 365 性能。

- **[威胁调查和响应功能](#use-threat-investigation-and-response-capabilities)** ：使用前沿工具调查、理解、模拟和阻止威胁。

- **[自动调查和响应功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)** ：节省时间和精力来调查和缓解威胁。

## <a name="getting-started"></a>入门

如果你没有使用过 Microsoft Defender for Office 365 或者“ *做* 中学”，则可将初始 Defender for Office 365 配置分解为区块、调查以及使用此文章作为参考查看报告，从而获得最佳益处。 下面是逻辑早期配置块：

- 为所有内容的名称配置“ *anti* ”。
    - 反恶意软件
    - 防网络钓鱼
    - 反垃圾邮件
- 为所有内容的名称设置“ *safe* ”。
    - 安全链接
    - 安全附件
- 保护工作负载（例如 SharePoint Online、OneDrive 和 Teams） 
- 通过零时差自动清除进行保护

若要做中学，请[单击此链接](https://docs.microsoft.com/microsoft-365/security/office-365-security/protect-against-threats?view=o365-worldwide&preserve-view=true)。 

> [!NOTE]
> Microsoft Defender for Office 365 有两种不同计划类型。 如果你具有“实时检测”功能，则可以判断你是否拥有 **计划 1** ；如果具有威胁资源管理器，则可以判断是否拥有 **计划 2** 。 你拥有的计划会影响你将看到的工具，因此请确保在学习过程中了解自己的计划。

## <a name="microsoft-defender-for-office-365-plan-1-and-plan-2"></a>Microsoft Defender for Office 365 计划 1 和计划 2

下表概括了每个计划中包含的内容。

****

|Microsoft Defender for Office 365 计划 1|Microsoft Defender for Office 365 计划 2|
|---|---|
|<br/>配置、保护和检测功能： <ul><li>[安全附件](atp-safe-attachments.md)</li><li>[安全链接](atp-safe-links.md)</li><li>[适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)</li><li>[Defender for Office 365 保护中的防钓鱼](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)</li><li>[实时检测](threat-explorer.md)</li></ul>|Microsoft Defender for Office 365 计划 1 功能<br/>--- + ---<br/>自动化、调查、补救措施和教育功能：</li><li>[威胁跟踪器](threat-trackers.md)</li><li>[威胁资源管理器](threat-explorer.md)</li><li>[自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)</li><li>[攻击模拟器](attack-simulator.md)</li></ul>|
|

- Office 365 E5、Office 365 A5、Microsoft 365 E5 安全性和 Microsoft 365 E5 中包含 Microsoft Defender for Office 365 计划 2。

- Microsoft Defender for Office 365 计划 1 包含在 Microsoft 365 商业高级版中。

- Microsoft Defender for Office 365 计划 1 和 Microsoft Defender for Office 365 计划 2 均可用作特定订阅的加载项。 若要了解详细信息，请参阅[Microsoft Defender for Office 365 计划的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- 只有拥有 Microsoft 365 E5 或 Microsoft 365 E5 安全性许可证（未包括在 Microsoft Defender for Office 365 计划内）的用户才能使用[安全文档](safe-docs.md)功能。

- 如果你当前的订阅不包括 Microsoft Defender for Office 365，请[与销售人员联系以开始试用](https://go.microsoft.com/fwlink/p/?LinkId=518644)，并查看 Defender for Office 365 如何为你的组织所用。

## <a name="configure-microsoft-defender-for-office-365-policies"></a>配置 Microsoft Defender for Office 365 策略

借助 Microsoft Defender for Office 365，你组织的安全团队可以在安全与合规中心内定义策略（依次转到 [https://protection.office.com](https://protection.office.com) > **“威胁管理”** > **“策略”** ），从而配置保护。

> [!TIP]
> 有关可定义的策略的快速列表，请参阅[威胁防护](protect-against-threats.md)。

## <a name="defender-for-office-365-policies"></a>Defender for Office 365 策略

为组织定义的策略将确定预定义威胁的行为和保护级别。 策略选项非常灵活。 例如，组织的安全团队可以在用户、组织、收件人和域级别设置细化的威胁防护。 定期查看策略非常重要，因为每天都会出现新的威胁和挑战。

- **[安全附件](atp-safe-attachments.md)** ：提供可通过检查电子邮件附件查找恶意内容来保护邮件系统的零日防护。 它会将无病毒/恶意软件签名的所有邮件和附件路由到特殊环境，然后使用机器学习和分析技术检测恶意意向。 如果未找到可疑活动，邮件将转发到邮箱。 若要了解详细信息，请参阅[设置“安全附件”策略](set-up-atp-safe-attachments-policies.md)。

- **[安全链接](atp-safe-links.md)** ：在诸如电子邮件和 Office 文件中提供 URL 的单击时验证。 正在进行保护并适用于邮件和 Office 环境。 每次单击时都扫描链接：安全链接仍然可访问，恶意链接被动态阻止。 若要了解详细信息，请参阅[设置“安全链接”策略](set-up-atp-safe-links-policies.md)。

- **[用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](atp-for-spo-odb-and-teams.md)** ：当用户协作和共享文件时，可通过识别和阻止工作组网站和文档库中的恶意文件来保护你的组织。 若要了解详细信息，请参阅[开启适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Defender for Office 365](turn-on-atp-for-spo-odb-and-teams.md)。

- **[Defender for Office 365 中的防钓鱼保护](set-up-anti-phishing-policies.md#exclusive-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)** ：检测模拟用户和内部或自定义域的尝试。 它应用机器学习模型和高级模仿检测算法，防止钓鱼攻击。 若要了解详细信息，请参阅[在 Microsoft Defender for Office 365 中配置防钓鱼策略](configure-atp-anti-phishing-policies.md)。

## <a name="view-microsoft-defender-for-office-365-reports"></a>查看 Microsoft Defender for Office 365 报告

Microsoft Defender for Office 365 包括高级 [报告仪表板](view-reports-for-atp.md) 以监视你的 Defender for Office 365 性能。 可在安全与合规中心的“ **报告** ” > “ **仪表板** ”处访问该内容。

实时更新报告，为你提供最新见解。 这些报告还提供建议并向你提醒即将面临的威胁。 预定义的报告包括以下内容：

- [威胁资源管理器（或实时检测）](threat-explorer.md)

- [威胁防护状态报告](view-reports-for-atp.md#threat-protection-status-report)

- [Defender for Office 365 文件类型报告](view-reports-for-atp.md#defender-for-office-365-file-types-report)

- [Defender for Office 365 邮件处置报告](view-reports-for-atp.md#defender-for-office-365-message-disposition-report)

- …及更多精彩内容。

## <a name="use-threat-investigation-and-response-capabilities"></a>使用威胁调查和响应功能

Microsoft Defender for Office 365 计划 2 包括同类最佳的[威胁调查和响应工具](office-365-ti.md)，可让组织的安全团队预测、理解和防范恶意攻击。

- **[威胁跟踪器](threat-trackers.md)** 提供有关主流网络安全问题的最新智能。 例如，你可以查看有关最新恶意软件的信息，并采取措施，然后将其作为组织的实际威胁。 可用的跟踪器包括[值得注意的跟踪器](threat-trackers.md#noteworthy-trackers)、[趋势跟踪器](threat-trackers.md#trending-trackers)、[跟踪的查询](threat-trackers.md#tracked-queries)和[已保存的查询](threat-trackers.md#saved-queries)。

- **[威胁资源管理器（或实时检测）](threat-explorer.md)** 也称为“资源管理器”，它是一种实时报表，可用于识别和分析最近的威胁。 可配置资源管理器显示自定义期间的数据。

- **[攻击仿真程序](attack-simulator.md)** 使你能够在组织中运行现实的攻击方案以确定漏洞。 可仿真当前类型的攻击，包括鱼叉式网络钓鱼凭据收集和附件攻击、密码喷射攻击和暴力密码攻击。

## <a name="save-time-with-automated-investigation-and-response"></a>节省自动调查和响应的时间

（ **新增！** ）调查可能的网络攻击时，时间至关重要。 越快地识别和缓解威胁，贵公司的状况就越好。 [自动调查和响应](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air) (AIR) 功能包括一套可自动启动（例如触发预警时）或手动启动（例如从资源管理器中的视图启动）的安全手册。 AIR 可以有效且高效地节省安全操作团队缓解威胁的时间和精力。 要了解详细信息，请参阅 [Office 365 中的 AIR](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-air)。

## <a name="permissions-required-to-use-microsoft-defender-for-office-365-features"></a>使用 Microsoft Defender for Office 365 功能所需权限

若要访问安全与合规中心中的 Microsoft Defender for Office 365 功能，你必须分配有相应的角色。 下表提供一些示例：

|角色或角色组|了解详细信息的资源|
|---|---|
|全局管理员（可以在 Azure Active Directory 或安全与合规中心内分配此权限）|[关于 Microsoft 365 管理员角色](https://docs.microsoft.com/microsoft-365/admin/add-users/about-admin-roles)|
|安全管理员（可以在 Azure Active Directory 或安全与合规中心内分配此权限）|[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles) <p> [安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)|
|Exchange Online 组织管理（在 Exchange Online 中分配此权限）|[Exchange Online 中的权限](https://docs.microsoft.com/exchange/permissions-exo/permissions-exo) <p> [Exchange Online PowerShell](https://docs.microsoft.com/powershell/exchange/exchange-online-powershell)|
|搜索和清除（仅在安全与合规中心内分配此权限）|[安全与合规中心内的权限](permissions-in-the-security-and-compliance-center.md)|

有关详细信息，请参阅[安全与合规中心中的权限](permissions-in-the-security-and-compliance-center.md)。

## <a name="get-microsoft-defender-for-office-365"></a>获取 Microsoft Defender for Office 365

Microsoft Defender for Office 365 包含在特定订阅中，如 Microsoft 365 E5、Office 365 E5、Office 365 A5 和 Microsoft 365 商业高级版。 如果你的订阅不包含 Defender for Office 365，可以购买 Defender for Office 365 计划 1 或 Defender for Office 365 计划 2 作为特定订阅的加载项。 若要了解详细信息，请参阅以下资源：

- [Microsoft Defender for Office 365 可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#office-365-advanced-threat-protection-atp-availability)获取包括 Defender for Office 365 计划的订阅列表。

- 有关计划 1 和 2 中所含功能的列表，请参阅[Microsoft Defender for Office 365 计划的功能可用性](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。

- [获取合适的 Microsoft Defender for Office 365](https://products.office.com/exchange/advance-threat-protection#pmg-allup-content) 以便比较计划并购买 Defender for Office 365。

- [启动免费试用版](https://go.microsoft.com/fwlink/p/?LinkID=698279)

## <a name="new-features-in-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的新增功能

新功能持续添加到 Microsoft Defender for Office 365 中。 若要了解详细信息，请参阅以下资源：

- [Microsoft 365 路线图](https://www.microsoft.com/microsoft-365/roadmap?filters=&searchterms=advanced%2Cthreat%2Cprotection)提供了正在开发和即将推出的新功能列表。

- [Microsoft Defender for Office 365 服务说明](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#whats-new-in-office-365-advanced-threat-protection-atp)介绍了 Defender for Office 365 计划的功能和可用性。

## <a name="see-also"></a>另请参阅

- [Microsoft 365 Defender](../mtp/microsoft-threat-protection.md)

- [Microsoft 365 Defender 中的自动调查和响应 (AIR)](../mtp/mtp-autoir.md)
