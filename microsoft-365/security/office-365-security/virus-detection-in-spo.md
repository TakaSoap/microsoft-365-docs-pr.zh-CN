---
title: SharePoint Online、OneDrive 和 Microsoft Teams 中的内置病毒防护
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: ''
audience: Admin
ms.topic: reference
localization_priority: Normal
search.appverid:
- SPO160
- MOE150
- MET150
ms.assetid: e3c6df61-8513-499d-ad8e-8a91770bff63
ms.collection:
- M365-security-compliance
description: 了解 SharePoint Online 如何在用户上载的文件中检测到病毒，以及如何阻止用户下载或同步文件。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: a651d198f441c26525cbfb5d7406ae350db8b79e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908078"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive 和 Microsoft Teams 中的内置病毒防护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](office-365-atp.md)

Microsoft 365 使用常见的病毒检测引擎扫描用户上传到 SharePoint Online、OneDrive 和 Microsoft Teams 的文件。 此保护包含在包括 SharePoint Online、OneDrive 和 Microsoft Teams 的所有订阅中。

> [!IMPORTANT]
> 内置防病毒功能是一种帮助包含病毒的方法。 它们不能作为针对你的环境抵御恶意软件的单一防御点。 我们鼓励所有客户在各种层调查和实施反恶意软件保护，并应用最佳实践来保护其企业基础结构。 有关策略和最佳做法详细信息，请参阅安全 [路线图](security-roadmap.md)。

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>如果将受感染的文件上传到 SharePoint Online 会发生什么情况？

Microsoft 365 病毒检测引擎以异步方式运行， (与 SharePoint Online 中的文件) 无关。 **不会自动扫描所有文件**。 启发式方法确定要扫描的文件。 当发现文件包含病毒时，将标记该文件。 2018 年 4 月，我们删除了扫描文件 25 MB 的限制。

下面是发生的情况：

1. 用户将文件上载到 SharePoint Online。
2. SharePoint Online 是病毒扫描过程的一部分，稍后将确定文件是否满足扫描条件。
3. 如果文件满足扫描条件，病毒检测引擎将扫描该文件。
4. 如果在扫描的文件中发现了病毒，则病毒引擎在文件上设置一个属性，指示它受到感染。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>当用户尝试使用浏览器下载受感染的文件时，会发生什么情况？

如果文件受到感染，则用户无法通过使用浏览器从 SharePoint Online 下载文件。

下面是发生的情况：

1. 用户打开 Web 浏览器并尝试从 SharePoint Online 下载受感染的文件。
2. 用户得到一条警告，指出已检测到病毒。 默认情况下，用户可以选择下载文件，并尝试在其自己的设备上使用防病毒软件进行清理。

> [!NOTE]
>
> 管理员可以在 SharePoint Online PowerShell 中 [对 Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet 使用 *DisallowInfectedFileDownload* 参数，以防止用户下载受感染的文件，即使在防病毒警告窗口中也可以。 有关说明，请参阅 [使用 SharePoint Online PowerShell 阻止用户下载恶意文件](turn-on-atp-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。
>
> 一旦启用 *DisallowInfectedFileDownload* 参数，用户和管理员将完全阻止访问检测到/阻止的文件。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>OneDrive 同步客户端尝试同步受感染的文件时会发生什么情况？

OneDrive 同步客户端不会下载包含病毒的文件。 同步客户端将显示文件无法同步的通知。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365 的扩展功能

订阅中包含 Microsoft Defender for Office 365 或作为加载项购买 Microsoft [365 的 Microsoft 365](office-365-atp.md) 组织可以启用 SharePoint、OneDrive 和 Microsoft Teams 的安全附件，以增强报告和保护。 有关详细信息，请参阅 [SharePoint、OneDrive](atp-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件。

## <a name="related-articles"></a>相关文章

[Microsoft 365 中的恶意软件和勒索软件保护](/compliance/assurance/assurance-malware-and-ransomware-protection)

有关 SharePoint Online、OneDrive 和 Microsoft Teams 中的防病毒功能详细信息[](protect-against-threats.md)，请参阅防止威胁和启用[SharePoint、OneDrive](turn-on-atp-for-spo-odb-and-teams.md)和 Microsoft Teams 的安全附件。