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
ms.localizationpriority: medium
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
description: 了解 Microsoft Defender for Office 365 Online、SharePoint 和 Microsoft Teams 中的OneDrive for Business。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 220bb976ebe701e5db5f03370a1a7c188f197cb1
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64475754"
---
# <a name="safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>用于 SharePoint、OneDrive 和 Microsoft Teams 的安全附件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

保险箱 [Microsoft Defender for Office 365](whats-new-in-defender-for-office-365.md) 中的 SharePoint、OneDrive 和 Microsoft Teams 附件为已由[Microsoft 365](virus-detection-in-spo.md)。 保险箱附件SharePoint、OneDrive 和 Microsoft Teams 有助于检测并阻止在团队网站和文档库中标识为恶意的现有文件。

默认情况下，不启用 SharePoint、OneDrive 和 Microsoft Teams 的安全附件。 若要打开它，请参阅打开保险箱[附件SharePoint、OneDrive和Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)。

## <a name="how-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams-works"></a>保险箱、SharePoint、OneDrive和Microsoft Teams附件的工作原理

保险箱启用SharePoint、OneDrive 和 Microsoft Teams 附件，并且将文件标识为恶意文件时，会使用与文件存储的直接集成锁定该文件。 以下图像显示了库中检测到的恶意文件示例。

:::image type="content" source="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png" alt-text="其中的文件OneDrive for Business一个被检测为恶意文件" lightbox="../../media/2bba71cc-7ad1-4799-8b9d-d56f923db3a7.png":::

尽管阻止的文件仍列在文档库以及 Web、移动或桌面应用程序中，但用户无法打开、复制、移动或共享该文件。 但他们可以删除阻止的文件。

下面是阻止的文件在移动设备上的外观示例：

:::image type="content" source="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png" alt-text="从应用移动应用中删除OneDrive for Business阻止OneDrive的选项" lightbox="../../media/cb1c1705-fd0a-45b8-9a26-c22503011d54.png":::

默认情况下，用户可以下载阻止的文件。 下面是在移动设备上下载阻止的文件的外观：

:::image type="content" source="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png" alt-text="用于下载阻止的文件的选项OneDrive for Business" lightbox="../../media/be288a82-bdd8-4371-93d8-1783db3b61bc.png":::

SharePoint Online 管理员可以阻止用户下载恶意文件。 有关说明，请参阅[使用 SharePoint Online PowerShell 阻止用户下载恶意文件](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。

若要了解有关文件被检测为恶意文件时的用户体验，请参阅在 [SharePoint Online](https://support.microsoft.com/office/01e902ad-a903-4e0f-b093-1e1ac0c37ad2)、OneDrive 或 Microsoft Teams 中发现恶意文件时Microsoft Teams。

## <a name="view-information-about-malicious-files-detected-by-safe-attachments-for-sharepoint-onedrive-and-microsoft-teams"></a>查看有关附件中检测到的恶意保险箱文件SharePoint、OneDrive和Microsoft Teams

SharePoint、OneDrive 和 Microsoft Teams 的 保险箱 附件标识为恶意的文件将显示在 [Microsoft Defender for Office 365](view-reports-for-mdo.md) 的报告以及资源管理器 (和实时检测 [) 中](threat-explorer.md)。

当文件被 保险箱 Attachments for SharePoint、OneDrive 和 Microsoft Teams 标识为恶意文件时，该文件也可隔离，但仅对管理员可用。 有关详细信息，请参阅在 [Defender for Office 365 中管理隔离Office 365](manage-quarantined-messages-and-files.md#use-the-microsoft-365-defender-portal-to-manage-quarantined-files-in-defender-for-office-365)。

## <a name="keep-these-points-in-mind"></a>请记住以下几点

- Defender for Office 365不会扫描 SharePoint Online、OneDrive for Business 或 Microsoft Teams。 这是设计使然的。 以异步方式扫描文件。 此过程使用共享和来宾活动事件以及智能启发和威胁信号来识别恶意文件。

- 确保你的SharePoint网站配置为使用新式[体验](/sharepoint/guide-to-sharepoint-modern-experience)。 Defender for Office 365保护适用于是否使用新式体验或经典视图;但是，文件被阻止的视觉指示器仅在新式体验中可用。

- 保险箱 SharePoint、OneDrive 和 Microsoft Teams 的附件是组织的整体威胁防护策略的一部分，其中包括 Exchange Online Protection (EOP) 中的反垃圾邮件和反恶意软件保护以及 保险箱 链接和 保险箱 Microsoft Defender for Office 365 中的附件。 若要了解更多信息，请参阅防止[威胁Office 365](protect-against-threats.md)。
