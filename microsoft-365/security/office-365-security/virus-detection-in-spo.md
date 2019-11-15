---
title: SharePoint Online 中的病毒检测
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 01/14/2019
audience: Admin
ms.topic: reference
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 通过检测用户上传到 SharePoint Online 的文件中的病毒，Office 365 可帮助保护您的环境免受恶意软件的攻击。 上载文件后，将对其进行病毒扫描。 如果发现文件感染了病毒，则会设置一个属性，以便用户无法下载或同步该文件。
ms.openlocfilehash: 9776dd7791d8543e0fd401a3c21c95d9fbf60f09
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639822"
---
# <a name="virus-detection-in-sharepoint-online"></a>SharePoint Online 中的病毒检测

> [!IMPORTANT]
> 若要使用此功能，需要 Office 365 高级威胁防护（ATP）。 有关详细信息，请参阅[开启适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/turn-on-atp-for-spo-odb-and-teams)。

通过检测用户上传到 SharePoint Online 的文件中的病毒，Office 365 可帮助保护您的环境免受恶意软件的攻击。 上载文件后，将对其进行病毒扫描。 如果发现文件感染了病毒，则会设置一个属性，以便用户无法下载或同步该文件。
  
> [!IMPORTANT]
> SharePoint Online 中的这些防病毒功能是包含病毒的一种方法。 它们不是为了抵御针对您的环境的恶意软件的单一防御点。 我们鼓励所有客户在各层评估和实施反恶意软件保护，并应用最佳做法来保护企业基础结构。 有关策略和最佳实践的详细信息，请参阅[安全路线图](security-roadmap.md)。 
  
## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>将受感染的文件上载到 SharePoint Online 时，会发生什么情况？

Office 365 使用通用的病毒检测引擎。 引擎在 SharePoint Online 中以异步方式运行，并在上载文件后对文件进行扫描。 当发现文件包含病毒时，会对其进行标记，以便无法再次下载。 在4月2018，我们删除了扫描文件的 25 MB 限制。
  
以下是所发生的情况：
  
1. 用户将文件上传到 SharePoint Online。
    
2. 病毒检测引擎将扫描文件。
    
3. 如果发现了病毒，病毒引擎将对文件设置一个属性，表明它已被感染。
    
## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>当用户尝试使用浏览器下载受感染的文件时，会发生什么情况？

如果文件感染了病毒，用户将无法使用浏览器从 SharePoint Online 下载该文件。
  
以下是所发生的情况：
  
1. 用户打开 web 浏览器并尝试从 SharePoint Online 下载感染病毒的文件。
    
2. 向用户提供一条警告，指示已检测到病毒。 向用户提供下载文件的选项，并尝试使用自己的病毒软件对其进行清理。

> [!NOTE]
> 您可以将 Set-spotenant cmdlet 与**DisallowInfectedFileDownload**参数一起使用，以禁止用户下载检测到的文件，即使在 "反病毒警告" 窗口中也是如此。 请参阅 [DisallowInfectedFileDownload]https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant)（。
    
## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>OneDrive 同步客户端尝试同步受感染的文件时，会发生什么情况？

无论用户是使用新 OneDrive 同步客户端（OneDrive .exe）还是以前的 OneDrive for Business 同步客户端（Groove）同步文件，同步客户端也不会下载该病毒。 同步客户端将显示一条通知，指出文件无法同步。
  

