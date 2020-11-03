---
title: SharePoint Online、OneDrive 和 Microsoft 团队中的内置病毒防护
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
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
description: 了解 SharePoint Online 如何检测用户上载的文件中的病毒并阻止用户下载或同步文件。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f774c9afd0988c504d6207b0e71ee9561312e6b4
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844232"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive 和 Microsoft 团队中的内置病毒防护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

Microsoft 365 使用通用的病毒检测引擎来扫描用户上载到 SharePoint Online、OneDrive 和 Microsoft 团队的文件。 此保护包括在所有订阅中，包括 SharePoint Online、OneDrive 和 Microsoft 团队。

> [!IMPORTANT]
> 内置防病毒功能是一种帮助包含病毒的方法。 它们不是为了抵御针对您的环境的恶意软件的单一防御点。 我们鼓励所有客户在不同的层调查和实施反恶意软件保护，并应用最佳做法来保护其企业基础结构。 有关策略和最佳实践的详细信息，请参阅 [安全路线图](security-roadmap.md)。

## <a name="what-happens-when-an-infected-file-is-uploaded-to-sharepoint-online"></a>将受感染的文件上载到 SharePoint Online 时，会发生什么情况？

Microsoft 365 病毒检测引擎在 SharePoint Online 中异步运行。 **上载时不会自动扫描所有文件** 。 启发式确定要扫描的文件。 找到文件以包含病毒时，文件会被标记为无法再次下载。 在4月2018，我们删除了扫描文件的 25 MB 限制。

以下是所发生的情况：

1. 用户将文件上传到 SharePoint Online。
2. SharePoint Online 决定文件是否符合扫描的条件。
3. 病毒检测引擎将扫描文件。
4. 如果发现了病毒，病毒引擎将对文件设置一个属性，表明它已被感染。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>当用户尝试使用浏览器下载受感染的文件时，会发生什么情况？

如果文件受到感染，用户不能使用浏览器从 SharePoint Online 下载文件。

以下是所发生的情况：

1. 用户打开 web 浏览器并尝试从 SharePoint Online 下载感染病毒的文件。
2. 向用户提供一条警告，指示已检测到病毒。 默认情况下，会向用户提供下载文件的选项，并尝试使用防病毒软件在自己的设备上进行清理。

> [!NOTE]
>
> 管理员可以在 SharePoint Online PowerShell 中使用 [set-spotenant](https://docs.microsoft.com/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet 上的 *DisallowInfectedFileDownload* 参数，以防止用户下载感染病毒的文件，即使在 "反病毒警告" 窗口中也是如此。 有关说明，请参阅 [使用 SharePoint Online PowerShell 防止用户下载恶意文件](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。
>
> 一旦启用 *DisallowInfectedFileDownload* 参数，就会为用户和管理员完全阻止对已检测/被阻止文件的访问。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>OneDrive 同步客户端尝试同步受感染的文件时，会发生什么情况？

OneDrive 同步客户端不会下载包含病毒的文件。 同步客户端将显示一条通知，指出文件无法同步。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 中的扩展功能

订阅中包含 [Microsoft Defender For Office 365](office-365-atp.md) 的 microsoft 365 组织，或作为加载项购买的 microsoft 组织可以为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP，以增强报告和保护功能。 有关详细信息，请参阅 [适用于 SharePoint、OneDrive 和 Microsoft 团队的 ATP](atp-for-spo-odb-and-teams.md)。

## <a name="more-information"></a>更多信息

有关 SharePoint Online、OneDrive 和 Microsoft 团队中的防病毒的详细信息，请参阅 [防止威胁](protect-against-threats.md) 并 [打开 SharePoint、OneDrive 和 MICROSOFT 团队的 ATP](turn-on-atp-for-spo-odb-and-teams.md)。
