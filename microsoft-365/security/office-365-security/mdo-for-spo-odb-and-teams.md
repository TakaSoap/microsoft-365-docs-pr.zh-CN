---
title: 用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: conceptual
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
- m365initiative-defender-office365
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 了解适用于 SharePoint Online、OneDrive for Business 和 Microsoft Teams 中文件的 Microsoft Defender for Office 365。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 80e30a52ef77dad32450bdfecc5010752b199b37
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203277"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

[Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md)中的 SharePoint、OneDrive 和 Microsoft Teams 的安全附件为已在上传时由 Microsoft [365](virus-detection-in-spo.md)中的常见病毒检测引擎扫描的文件提供了一层额外的保护。 SharePoint、OneDrive 和 Microsoft Teams 的安全附件可帮助检测和阻止团队网站和文档库中标识为恶意的现有文件。

默认情况下，SharePoint、OneDrive 和 Microsoft Teams 的安全附件未启用。 若要启用它，请参阅启用 [SharePoint、OneDrive](turn-on-mdo-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件。

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint、OneDrive 和 Microsoft Teams 的安全附件的工作原理

如果启用 SharePoint、OneDrive 和 Microsoft Teams 的安全附件，并且将文件标识为恶意文件，则使用与文件存储的直接集成锁定该文件。 下图显示了在库中检测到的恶意文件的示例。

![OneDrive for Business 中的文件，其中一个文件被检测为恶意文件](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

尽管阻止的文件仍在文档库和 Web、移动或桌面应用程序中列出，但用户无法打开、复制、移动或共享该文件。 但他们可以删除阻止的文件。

下面是阻止的文件在移动设备上的外观示例：

![从 OneDrive 移动应用中删除 OneDrive for Business 中阻止的文件](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

默认情况下，用户可以下载阻止的文件。 下面是在移动设备上下载阻止的文件的外观：

![在 OneDrive for Business 中下载阻止的文件](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online 管理员可以阻止用户下载恶意文件。 有关说明，请参阅 [使用 SharePoint Online PowerShell 阻止用户下载恶意文件](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。

若要了解有关文件被检测为恶意文件时的用户体验，请参阅 [在 SharePoint Online、OneDrive](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)或 Microsoft Teams 中发现恶意文件时要执行哪些操作。

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>查看有关 SharePoint、OneDrive 和 Microsoft Teams 的安全附件检测到的恶意文件的信息

Microsoft Defender for Office 365 标识为恶意的文件将显示在 [Microsoft Defender for Office 365](view-reports-for-mdo.md) 的报告和资源管理器 [ (](threat-explorer.md)以及实时检测) 。

截至 2018 年 5 月，当 Microsoft Defender for Office 365 将文件标识为恶意文件时，该文件也可隔离。 有关详细信息，请参阅使用安全与& [中心管理隔离的文件](manage-quarantined-messages-and-files.md#microsoft-defender-for-office-365-only-use-the-security--compliance-center-to-manage-quarantined-files)。

## <a name="keep-these-points-in-mind"></a>请记住以下几点

- Defender for Office 365 不会扫描 SharePoint Online、OneDrive for Business 或 Microsoft Teams 中的每个文件。 这是设计使然的。 以异步方式扫描文件。 此过程使用共享和来宾活动事件以及智能启发和威胁信号来识别恶意文件。

- 确保 SharePoint 网站配置为使用新式 [体验](/sharepoint/guide-to-sharepoint-modern-experience)。 无论使用新式体验还是经典视图，Defender for Office 365 保护都适用;但是，文件被阻止的视觉指示器仅在新式体验中可用。

- SharePoint、OneDrive 和 Microsoft Teams 的安全附件是组织的整体威胁防护策略的一部分，其中包括 Exchange Online Protection (EOP) 中的反垃圾邮件和反恶意软件保护，以及 Microsoft Defender for Office 365 中的安全链接和安全附件。 若要了解更多信息，请参阅 Office [365 中的威胁防护](protect-against-threats.md)。