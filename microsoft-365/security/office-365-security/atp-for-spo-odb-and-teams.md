---
title: 适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
audience: Admin
ms.date: ''
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 26261670-db33-4c53-b125-af0662c34607
ms.collection:
- M365-security-compliance
- SPO_Content
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
description: 了解有关 SharePoint Online、OneDrive for Business 和 Microsoft 团队中的文件的 Office 365 高级威胁防护。
ms.openlocfilehash: 194b8e45e573ae4c4cd1f3428a1f80c48e1d80c8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326861"
---
# <a name="atp-for-sharepoint-onedrive-and-microsoft-teams"></a>适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

SharePoint、OneDrive 和 Microsoft team in [Office 365 高级威胁防护 (atp) ](office-365-atp.md) 为在 [Microsoft 365 中的常见病毒检测引擎](virus-detection-in-spo.md)在上载时已扫描的文件提供了额外的保护层。 SharePoint、OneDrive 和 Microsoft 团队的 ATP 可帮助检测和阻止在工作组网站和文档库中标识为恶意的现有文件。

默认情况下不启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP。 若要打开它，请参阅 [启用 SharePoint、OneDrive 和 Microsoft 团队的 ATP](turn-on-atp-for-spo-odb-and-teams.md)。

## <a name="how-atp-for-sharepoint-onedrive-and-microsoft-teams-works"></a>SharePoint、OneDrive 和 Microsoft 团队的 ATP 的工作原理

如果启用了 SharePoint、OneDrive 和 Microsoft 团队的 ATP，并将文件标识为恶意文件，则会使用与文件存储区的直接集成来锁定文件。 下图显示了在库中检测到的恶意文件的示例。

![OneDrive for business 中一个检测为恶意的文件](../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png)

尽管阻止的文件仍在文档库和 web、移动或桌面应用程序中列出，但用户无法打开、复制、移动或共享文件。 但它们可以删除被阻止的文件。

下面的示例展示了阻止的文件在移动设备上的显示效果：

![从 OneDrive 移动应用程序中删除 OneDrive for business 中的阻止文件](../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png)

默认情况下，用户可以下载被阻止的文件。 下面介绍了如何在移动设备上下载被阻止的文件：

![在 OneDrive for Business 中下载阻止的文件](../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png)

SharePoint Online 管理员可以阻止用户下载恶意文件。 有关说明，请参阅 [使用 SharePoint Online PowerShell 防止用户下载恶意文件](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。

若要详细了解在将文件检测为恶意时的用户体验，请参阅在 [SharePoint Online、OneDrive 或 Microsoft 团队中找到恶意文件时应执行的操作](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)。

## <a name="view-information-about-malicious-files-detected-by-atp-for-sharepoint-onedrive-and-microsoft-teams"></a>查看有关由 SharePoint、OneDrive 和 Microsoft 团队的 ATP 检测到的恶意文件的信息

由 ATP 标识为恶意的文件将显示在 [Office 365 高级威胁防护](view-reports-for-atp.md) 和资源管理器中的报告中， [ (和实时检测) ](threat-explorer.md)。

从5月2018，如果某个文件被 ATP 标识为恶意文件，则该文件也可在隔离区中使用。 有关详细信息，请参阅 [使用安全 & 合规性中心管理隔离的文件](manage-quarantined-messages-and-files.md#atp-only-use-the-security--compliance-center-to-manage-quarantined-files)。

## <a name="keep-these-points-in-mind"></a>记住这些要点

- ATP 将不会扫描 SharePoint Online、OneDrive for Business 或 Microsoft 团队中的每个单个文件。 这是设计使然的。 异步扫描文件。 此过程使用共享和来宾活动事件以及智能试探法和威胁信号来识别恶意文件。

- 确保您的 SharePoint 网站已配置为使用 [新式体验](https://docs.microsoft.com/sharepoint/guide-to-sharepoint-modern-experience)。 ATP protection 适用于是否使用新式体验或经典视图;但是，阻止文件被阻止的视觉指示器仅适用于新式体验。

- SharePoint、OneDrive 和 Microsoft 团队的 ATP 是组织的整体威胁防护策略的一部分，其中包括在 Exchange Online Protection 中的反垃圾邮件和反恶意软件保护 (EOP) ，以及 Office 365 ATP 中的安全链接和安全附件。 若要了解详细信息，请参阅 [在 Office 365 中防御威胁](protect-against-threats.md)。
