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
ms.localizationpriority: medium
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
ms.openlocfilehash: ddb424458e991becefb98efbad5b2a86c5f9441c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60208897"
---
# <a name="built-in-virus-protection-in-sharepoint-online-onedrive-and-microsoft-teams"></a>SharePoint Online、OneDrive 和 Microsoft Teams 中的内置病毒防护

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)

Microsoft 365使用常见的病毒检测引擎扫描用户上传到 SharePoint Online、OneDrive 和 Microsoft Teams 的文件。 此保护包含在包括 SharePoint Online、OneDrive 和 Microsoft Teams 的所有订阅中。

> [!IMPORTANT]
> 内置防病毒功能是一种帮助包含病毒的方法。 它们不是针对你的环境抵御恶意软件的单一防御点。 我们鼓励所有客户在各种层调查和实施反恶意软件保护，并应用最佳实践来保护其企业基础结构。 有关策略和最佳做法详细信息，请参阅安全 [路线图](security-roadmap.md)。

## <a name="what-happens-if-an-infected-file-is-uploaded-to-sharepoint-online"></a>如果将受感染的文件上传到联机版，会发生什么SharePoint？

病毒Microsoft 365引擎在独立于 (Online 中的文件上载) 异步SharePoint运行。 **不会自动扫描所有文件**。 启发式方法确定要扫描的文件。 当发现文件包含病毒时，将标记该文件。 2018 年 4 月，我们删除了扫描文件 25 MB 的限制。

下面是发生的情况：

1. 用户将文件上传到 SharePoint Online。
2. SharePoint作为病毒扫描过程的一部分，联机稍后将确定文件是否满足扫描条件。
3. 如果文件满足扫描条件，病毒检测引擎将扫描该文件。
4. 如果在扫描的文件中发现了病毒，则病毒引擎在文件上设置一个属性，指示它受到感染。

## <a name="what-happens-when-a-user-tries-to-download-an-infected-file-by-using-the-browser"></a>当用户尝试使用浏览器下载受感染的文件时，会发生什么情况？

如果文件受到感染，则用户无法通过使用浏览器从 SharePoint Online 下载该文件。

下面是发生的情况：

1. 用户打开 Web 浏览器并尝试从 SharePoint Online 下载受感染的文件。
2. 用户得到一条警告，指出已检测到病毒。 默认情况下，用户可以选择下载文件，并尝试使用自己的设备上防病毒软件进行清理。

> [!NOTE]
>
> 管理员可以在 SharePoint Online PowerShell 中 [对 Set-SPOTenant](/powershell/module/sharepoint-online/Set-SPOTenant) cmdlet 使用 *DisallowInfectedFileDownload* 参数，以防止用户下载受感染的文件，即使在防病毒警告窗口中也可以。 有关说明，请参阅[使用 SharePoint Online PowerShell 阻止用户下载恶意文件](turn-on-mdo-for-spo-odb-and-teams.md#step-2-recommended-use-sharepoint-online-powershell-to-prevent-users-from-downloading-malicious-files)。
>
> 一旦启用 *DisallowInfectedFileDownload* 参数，用户和管理员将完全阻止访问检测到/阻止的文件。

## <a name="what-happens-when-the-onedrive-sync-client-tries-to-sync-an-infected-file"></a>当客户端尝试OneDrive 同步感染的文件时，会发生什么情况？

将恶意文件上传到OneDrive，它将先同步到本地计算机，然后再被标记为恶意软件。 在将同步文件标记为恶意软件后，用户无法再从本地计算机打开同步文件。

## <a name="extended-capabilities-with-microsoft-defender-for-office-365"></a>Microsoft Defender for Office 365

Microsoft 365 Microsoft [Defender for Office 365](defender-for-office-365.md)或作为加载项购买的组织可以启用 保险箱 Attachments for SharePoint、OneDrive 和 Microsoft Teams 增强的报告和保护。 有关详细信息，请参阅 保险箱[Attachments for SharePoint， OneDrive， and Microsoft Teams](mdo-for-spo-odb-and-teams.md)。

## <a name="related-articles"></a>相关文章

[恶意软件和勒索软件保护Microsoft 365](/compliance/assurance/assurance-malware-and-ransomware-protection)

有关 SharePoint Online、OneDrive 和 Microsoft Teams 中的防病毒功能详细信息，请参阅抵御威胁和启用 保险箱[](protect-against-threats.md)Attachments for [SharePoint， OneDrive， and Microsoft Teams](turn-on-mdo-for-spo-odb-and-teams.md)。
