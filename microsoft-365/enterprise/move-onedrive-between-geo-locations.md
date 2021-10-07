---
title: 将 OneDrive 站点移动到其他地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: 查找有关将OneDrive网站移动到其他地理位置的信息，包括如何计划站点移动和向用户传达预期。
ms.openlocfilehash: 232654ac0cea95fee6dfef036ecb87768e5768d9
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60195349"
---
# <a name="move-a-onedrive-site-to-a-different-geo-location"></a>将 OneDrive 站点移动到其他地理位置 

通过OneDrive移动，你可以将用户OneDrive移动到其他地理位置。 OneDrive由 SharePoint Online 管理员或全局管理员Microsoft 365移动。 在开始异地OneDrive移动之前，请务必通知OneDrive移动的用户，并建议他们在移动期间关闭所有文件。  (如果用户在移动过程中使用 Office 客户端打开了一个文档，那么在移动完成时，文档将需要保存到新位置。) 如果需要，可以将移动安排在将来的时间。

该OneDrive服务使用 Azure Blob 存储存储内容。 存储与用户的 OneDrive 关联的 blob 将在目标地理位置可供用户使用的 40 天内OneDrive目标地理位置。 一旦目标 OneDrive可用，将恢复对OneDrive的访问权限。

在OneDrive移动窗口 (大约 2-6) 用户的移动OneDrive设置为只读。 用户仍可通过 OneDrive 同步 应用或 OneDrive Online SharePoint文件。 完成OneDrive OneDrive移动后，当用户导航到 OneDrive 应用启动器中的 OneDrive 时，该用户将自动连接到目标地理位置的 Microsoft 365。 同步应用将自动从新位置开始同步。

执行本文中的步骤需要安装 [Microsoft SharePoint Online PowerShell 模块](https://www.microsoft.com/download/details.aspx?id=35588)。

## <a name="communicating-to-your-users"></a>向用户传达

如果在地理位置之间移动 OneDrive 网站，请务必向用户传达预期内容。这有助于减少用户混淆并联系支持人员。移动前向用户发送电子邮件，让他们了解以下信息：

- 移动应该开始的时间和需要花费的时长
- 其 OneDrive 要移动到的地理位置和用于访问新位置的 URL
- 移动期间，他们应关闭文件，不进行任何编辑。
- 文件权限和共享不会因移动而更改。
- [多地理位置环境中的用户体验](multi-geo-user-experience.md)预期将呈现的内容

移动成功后，务必向用户发送电子邮件，告知他们可在 OneDrive 中恢复工作。

## <a name="scheduling-onedrive-site-moves"></a>安排 OneDrive 网站移动

可以提前安排 OneDrive 网站移动（在本文后面介绍）。建议先通过少数用户验证工作流和通信策略。如果你对该过程感到满意，可以按如下方式安排移动：

- 一次最多可以安排 4,000 次移动。
- 移动开始后，可以安排更多移动操作，在在队列及任何给定时间内最多有 4,000 个待处理移动。
- 可移动的最大 OneDrive 大小为 1 太字节 (1 TB)。

## <a name="moving-a-onedrive-site"></a>移动 OneDrive 网站

若要执行OneDrive移动，租户管理员必须先将用户的首选数据位置 (PDL) 设置为相应的地理位置。 设置 PDL 后，请等待至少 24 小时，让 PDL 更新跨地理位置同步，然后再开始OneDrive移动。

使用地理位置移动 cmdlet 时，使用以下语法连接到用户当前地理位置OneDrive SPO 服务：

`Connect-SPOService -url https://<tenantName>-admin.sharepoint.com`

例如：若要OneDrive用户"Matt@contosoenergy.onmicrosoft.com"，请连接到 EUR SharePoint 管理中心，因为OneDrive位于 EUR 地理位置：

`Connect-SPOSservice -url https://contosoenergyeur-admin.sharepoint.com`

![显示 connect-sposervice cmdlet 的 PowerShell 窗口屏幕截图。](../media/move-onedrive-between-geo-locations-image1.png)

## <a name="validating-the-environment"></a>验证环境

在启动 OneDrive 异地移动前，我们建议验证环境。

要确保所有地理位置都可兼容，请运行：

`Get-SPOGeoMoveCrossCompatibilityStatus`

你将会看到可以在其中移动的地理位置和天气内容列表将显示为“兼容”。 如果命令返回“不兼容”，请稍后重新验证状态。

举例来说，如果 OneDrive 包含子网站，则不能移动它。 你可以将 Start-SPOUserAndContentMove cmdlet 与 -ValidationOnly 参数结合使用，以验证 OneDrive 是否可以移动：

`Start-SPOUserAndContentMove -UserPrincipalName <UPN> -DestinationDataLocation <DestinationDataLocation> -ValidationOnly`

如果 OneDrive 可以移动，则返回“成功”，如果存在阻止 OneDrive 移动的法定保留或子网站，则返回“失败”。验证 OneDrive 可以移动后，即可开始移动。

## <a name="start-a-onedrive-geo-move"></a>启动 OneDrive 异地移动

若要开始移动，请运行：  

`Start-SPOUserAndContentMove -UserPrincipalName <UserPrincipalName> -DestinationDataLocation <DestinationDataLocation>`

使用以下参数：

-   _UserPrincipalName_ – 要移动其 OneDrive 的用户的 UPN。

-   _DestinationDataLocation_ – Geo-Location移动OneDrive位置。 这应该与用户的首选数据位置相同。

例如，若要将 matt@contosoenergy.onmicrosoft.com 的 OneDrive 从 EUR 移动到 AUS，请运行：

`Start-SPOUserAndContentMove -UserPrincipalName matt@contosoenergy.onmicrosoft.com -DestinationDataLocation AUS`

![显示 cmdlet 的 PowerShell Start-SPOUserAndContentMove屏幕截图。](../media/move-onedrive-between-geo-locations-image2.png)

若要设置在以后执行的异地移动，请使用以下参数之一：

-   _PreferredMoveBeginDate_ – 可能在此指定的时间内开始移动。必须使用协调世界时 (UTC) 指定时间。

-   _PreferredMoveEndDate_ – 可能在此指定的时间内完成移动。必须使用协调世界时 (UTC) 指定时间。 

## <a name="cancel-a-onedrive-geo-move"></a>取消 OneDrive 异地移动 

如果移动未进行或OneDrive cmdlet，可以停止用户移动的地理位置移动：

`Stop-SPOUserAndContentMove – UserPrincipalName <UserPrincipalName>`

其中 _UserPrincipalName_ 是你想要停止移动其 OneDrive 的用户的 UPN。

## <a name="determining-current-status"></a>确定当前状态

可以使用 OneDrive cmdlet 检查你连接到的地理位置Get-SPOUserAndContentMoveState状态。

下表描述了这些移动状态。

<table>
<thead>
<tr class="header">
<th align="left">状态</th>
<th align="left">说明</th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td align="left">NotStarted</td>
<td align="left">移动尚未开始。</td>
</tr>
<tr class="even">
<td align="left">InProgress (<em>n</em>/4)</td>
<td align="left">移动正在进行中，状态为以下之一：验证 (1/4)、备份 (2/4)、还原 (3/4)、清除 (4/4)。</td>
</tr>
<tr class="odd">
<td align="left">Success</td>
<td align="left">移动已成功完成。</td>
</tr>
<tr class="even">
<td align="left">Failed</td>
<td align="left">移动失败。</td>
</tr>
</tbody>
</table>

若要查找特定用户移动的状态，请使用 UserPrincipalName 参数：

`Get-SPOUserAndContentMoveState -UserPrincipalName <UPN>`

若要查找你连接到的地理位置中移移或移出的所有移动的状态，请使用 MoveState 参数和下列值之一：NotStarted、InProgress、Success、Failed、All。

`Get-SPOUserAndContentMoveState -MoveState <value>`

此外，还可以添加 `-Verbose` 参数，以获取移动状态更为详细的说明。

## <a name="user-experience"></a>用户体验

在用户的 OneDrive 被移动到其他地理位置时，OneDrive 用户应会注意到最小的中断。除了在移动期间的简要只读状态以外，一旦移动完成，现有链接和权限即可继续按预期运行。

### <a name="users-onedrive"></a>用户的 OneDrive

进行移动时，用户的OneDrive设置为只读。 移动完成后，当用户导航到 OneDrive 应用启动器或 Web 浏览器时，OneDrive定位到Microsoft 365位置中的用户。

### <a name="permissions-on-onedrive-content"></a>OneDrive 内容权限

在移动过程中OneDrive内容完成后，有权访问内容的用户将继续具有该内容的访问权限。

### <a name="onedrive-sync-app"></a>OneDrive 同步应用 

一OneDrive 同步异地移动完成后，OneDrive自动检测同步并无缝OneDrive转移到新位置。 用户无需再次登录或执行任何其他操作。   (需要同步应用的版本 17.3.6943.0625 或) 

如果用户在异地移动OneDrive更新文件，则同步应用将在移动进行时通知用户文件上传挂起。

### <a name="sharing-links"></a>共享链接 

OneDrive 异地移动完成后，被移动文件的现有共享链接将自动重定向到新地理位置。

### <a name="onenote-experience"></a>OneNote 体验 

OneDrive 异地移动完成后，OneNote win32 客户端和 UWP（通用）应用将自动检测笔记本并将其无缝同步到新的 OneDrive 位置。用户无需重新登录或执行任何其他操作。对用户唯一可见的指示符是，当 OneDrive 异地移动进行时，笔记本同步可能失败。以下 OneNote 客户端版本提供了此体验：

-   OneNote win32 – 版本 16.0.8326.2096（及更高版本）

-   OneNote UWP – 版本16.0.8431.1006（及更高版本）

-   OneNote 移动应用 – 版本 16.0.8431.1011（及更高版本）

### <a name="teams-app"></a>Teams 应用

在 OneDrive 异地移动完成后，用户将可以访问其在 Teams 应用上的 OneDrive 文件。此外，在异地移动前通过 Teams 聊天从其 OneDrive 中共享的文件将可在移动完成后继续使用。

### <a name="onedrive-mobile-app-ios"></a>OneDrive移动应用 (iOS)  

在 OneDrive 异地移动完成后，用户需要在 iOS 移动应用上注销并重新登录，以同步到新的 OneDrive 位置。

### <a name="existing-followed-groups-and-sites"></a>现有已关注组和网站

关注的网站和组将显示在用户的OneDrive，无论其地理位置如何。 在另一个地理位置托管的网站和组将在单独的选项卡中打开。

### <a name="delve-geo-url-updates"></a>Delve地理位置 URL 更新

只有在用户的 PDL Delve移动到新地理位置后，用户OneDrive地理位置。
