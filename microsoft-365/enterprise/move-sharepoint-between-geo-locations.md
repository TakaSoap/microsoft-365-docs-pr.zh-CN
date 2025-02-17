---
title: 将 SharePoint 站点移到其他地理位置
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
f1.keywords:
- NOCSH
description: 了解如何将网站SharePoint多地理位置环境中的不同地理位置，并告知用户更改的预期。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9e4132b8399cc69067d24af6c3c9ec8e3baf52bd
ms.sourcegitcommit: 355ab75eb7b604c6afbe9a5a1b97ef16a1dec4fc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2022
ms.locfileid: "62806860"
---
# <a name="move-a-sharepoint-site-to-a-different-geo-location"></a>将 SharePoint 站点移到其他地理位置

利用 SharePoint 站点地理位置移动，你可以将 SharePoint 站点移到多地理位置环境内的其他地理位置。

可在地理位置之间移动以下类型的站点：

- Microsoft 365组连接的站点，包括与组关联的Microsoft Teams
- 没有组关联Microsoft 365新式网站
- 经典 SharePoint 站点
- 通信站点

你必须是全局管理员或 SharePoint 管理员才能在地理位置之间移动站点。

在移动站点地理位置期间，SharePoint一个只读窗口，时间约为 4-6 小时，具体取决于站点内容。

## <a name="best-practices"></a>最佳做法

- 尝试在测试站点上进行 SharePoint 站点移动，以熟悉程序。
- 在安排或执行移动之前，验证站点是否可移动。
- 尽可能将跨地理位置站点移动安排在非工作时间进行，以便减少用户影响。
- 在进行站点移动之前，与受影响的用户沟通。

## <a name="communicating-to-your-users"></a>向用户传达

在地理位置之间移动 SharePoint 站点时，请务必向站点的用户（通常是能够编辑站点的任何人）传达预期结果。 这可帮助减少用户困惑和致电技术支持的次数。 在移动之前向站点的用户发送电子邮件，告知他们以下信息：

- 移动应该开始的时间和需要花费的时长
- 其站点要移动到的地理位置和用于访问新位置的 URL
- 移动期间，他们应关闭文件，不进行任何编辑。
- 文件权限和共享不会因移动而更改。
- 多地理位置环境中的预期用户体验

移动成功完成后，务必向站点的用户发送电子邮件，告知他们可在站点上恢复工作。

## <a name="scheduling-sharepoint-site-moves"></a>安排 SharePoint 站点移动

你可以提前安排 SharePoint 站点移动 （在本文后面介绍）。 可以按如下方式安排移动：

- 一次最多可以安排 4,000 次移动。
- 移动开始后，可以安排更多移动操作，在在队列及任何给定时间内最多有 4,000 个待处理移动。
- 可移动的SharePoint最大大小为 1 TB (1 TB) 。

若要将 SharePoint 站点移动安排在稍后进行，请在开始移动时包括以下参数之一：

- `PreferredMoveBeginDate` -移动将可能在此指定时间开始。
- `PreferredMoveEndDate` -移动将尽可能在此指定时间之前完成。

对于这两个参数，均必须以协调世界时 (UTC) 指定时间。

## <a name="moving-the-site"></a>移动站点

SharePoint 站点地理位置移动要求你通过站点所在的地理位置中的 SharePoint 管理 URL 连接并执行移动。

例如，如果网站 URL 为 <https://contosohealthcare.sharepoint.com/sites/Turbines>，请连接到 SharePoint 管理员 URL，网址为 <https://contosohealthcare-admin.sharepoint.com>：

```powershell
Connect-SPOService -Url https://contosohealthcare-admin.sharepoint.com
```

![SharePoint联机命令行管理程序窗口，其中Connect-SPOService命令。](../media/move-onedrive-between-geo-locations-image1.png)

### <a name="validating-the-environment"></a>验证环境

在安排任何站点移动之前，我们建议你执行验证来确保站点可移动。

我们不支持移动包含以下各项的站点：

- Business Connectivity Services
- InfoPath 表单
- 已应用信息权限管理 (IRM) 模板

若要确保所有地理位置都兼容，请运行 `Get-SPOGeoMoveCrossCompatibilityStatus`： 这将显示所有地理位置，并显示环境是否与目标地理位置兼容。

若要在站点上执行仅验证检查，请将 `Start-SPOSiteContentMove`与 `-ValidationOnly` 参数结合使用，验证是否能够移动站点。 例如：

```PowerShell
Start-SPOSiteContentMove -SourceSiteUrl <SourceSiteUrl> -ValidationOnly -DestinationDataLocation <DestinationLocation>
```

如果站点可移动，这将返回 *Success*，如果存在任何造成阻碍的情况，则返回 *Fail*。

### <a name="start-a-sharepoint-site-geo-move-for-a-site-with-no-associated-microsoft-365-group"></a>为没有SharePoint组的网站开始站点地理位置Microsoft 365移动

默认情况下，站点的初始 URL 将更改为目标地理位置的 URL。 例如：

<https://Contoso.sharepoint.com/sites/projectx> 重命名为 <https://ContosoEUR.sharepoint.com/sites/projectx>

对于没有Microsoft 365组关联的网站，您还可以使用 参数重命名`-DestinationUrl`网站。 例如：

<https://Contoso.sharepoint.com/sites/projectx> 重命名为 <https://ContosoEUR.sharepoint.com/sites/projecty>

若要开始站点移动，请运行：

```powershell
Start-SPOSiteContentMove -SourceSiteUrl <siteURL> -DestinationDataLocation <DestinationDataLocation> -DestinationUrl <DestinationSiteURL>
```

![显示 cmdlet 的 PowerShell Start-SPOSiteContentMove屏幕截图。](../media/multi-geo-sharepoint-site-move-powershell.png)

### <a name="start-a-sharepoint-site-geo-move-for-a-microsoft-365-group-connected-site"></a>开始SharePoint组连接的站点进行Microsoft 365移动

若要移动Microsoft 365连接的站点，全局管理员或 SharePoint 管理员必须先更改组的首选数据位置 (PDL) 属性Microsoft 365属性。

若要为组设置 PDL Microsoft 365：

```PowerShell
Set-SPOUnifiedGroup -PreferredDataLocation <PDL> -GroupAlias <GroupAlias>
Get-SPOUnifiedGroup -GroupAlias <GroupAlias>
```

更新 PDL 之后，你就可以开始站点移动：

```PowerShell
Start-SPOUnifiedGroupMove -GroupAlias <GroupAlias> -DestinationDataLocation <DestinationDataLocation>
```

## <a name="cancel-a-sharepoint-site-geo-move"></a>取消 SharePoint 站点地理位置移动

如果移动尚未进行或尚未完成，则可以使用 `Stop-SPOSiteContentMove` cmdlet 来停止 SharePoint 站点地理位置移动。

## <a name="determining-the-status-of-a-sharepoint-site-geo-move"></a>确定 SharePoint 站点地理位置移动的状态

通过使用以下 cmdlet，你可以确定站点移入或移出所连接到的地理位置的状态：

- [Get-SPOSiteContentMoveState](/powershell/module/sharepoint-online/get-spositecontentmovestate)（非组连接的站点）
- [Get-SPOUnifiedGroupMoveState (](/powershell/module/sharepoint-online/get-spounifiedgroupmovestate) 组连接的站点) 

使用 `-SourceSiteUrl` 参数来指定要查看其移动状态的站点。

下表描述了这些移动状态。

****

|状态|说明|
|---|---|
|Ready to Trigger|移动尚未开始。|
|Scheduled|移动在队列中，但尚未开始。|
|InProgress (n/4)|移动正在进行，状态为以下之一：Validation (1/4) 、Back up (2/4) 、Restore (3/4) 、Cleanup (4/4) 。|
|Success|移动已成功完成。|
|Failed|移动失败。|
|

你也可以应用 `-Verbose` 选项来查看有关移动的其他信息。

## <a name="user-experience"></a>用户体验

将站点用户的站点移动到其他地理位置时，应最大限度地减少用户会注意到的中断情况。 除了在移动过程中会有很短的一段时间处于只读状态外，现有链接和权限在移动完成后将继续按预期方式工作。

### <a name="site"></a>站点

在移动进行时，网站设置为只读。 移动完成后，当用户单击书签或其他站点链接时，系统会将用户定向到新地理位置中的新站点。

### <a name="permissions"></a>权限

在移动进行时和完成后，有权访问站点的用户将仍然能够继续访问站点。

### <a name="sync-app"></a>同步应用

站点移动完成后，同步应用将自动检测同步并无缝转移到新站点位置。 用户无需再次登录或进行其他操作。  (需要同步应用的版本 17.3.6943.0625 或) 

如果用户在移动进行时更新文件，同步应用将通知他们在移动进行时文件上载挂起。

### <a name="sharing-links"></a>共享链接

SharePoint 站点地理位置移动完成后，被移动文件的现有共享链接将自动重定向到新地理位置。

### <a name="most-recently-used-files-in-office-mru"></a>Office 中最近使用的文件 (MRU)

移动完成后，MRU 服务将随站点 URL 及其内容 URL 一起更新。 这适用于 Word、Excel 和 PowerPoint。

### <a name="onenote-experience"></a>OneNote 体验

站点移动完成后，OneNote win32 客户端和 UWP （通用）应用会自动检测并将笔记本无缝同步到新站点位置。 用户无需再次登录或进行其他操作。 站点移动正在进行时，用户只会看到笔记本同步将失败的指示符。 以下 OneNote 客户端版本上提供了此体验：

- OneNote win32 – 版本 16.0.8326.2096（及更高版本）
- OneNote UWP – 版本16.0.8431.1006（及更高版本）
- OneNote 移动应用 – 版本 16.0.8431.1011（及更高版本）

### <a name="teams-applicable-to-microsoft-365-group-connected-sites"></a>Teams (组Microsoft 365连接的网站) 

当SharePoint地理位置移动完成后，用户将有权访问Microsoft 365应用上的组Teams文件。 此外，在地理位置移动之前通过 Teams 聊天从其站点中共享的文件在移动完成后将继续工作。

SharePoint地理位置移动不支持将专用通道从一个地理位置移动到另一个地理位置。 私人频道保留在原始地理位置。
  

### <a name="sharepoint-mobile-app-iosandroid"></a>SharePoint 移动应用 (iOS/Android)

SharePoint 移动应用跨地理位置兼容，并能够检测站点的新地理位置。

### <a name="sharepoint-workflows"></a>SharePoint 工作流

SharePoint移动后，必须重新发布 2013 工作流。 SharePoint 2010 工作流应会继续正常工作。

### <a name="apps"></a>应用

如果要使用应用移动站点，则必须在站点的新地理位置中重新建立应用，因为应用及其连接在目标地理位置中可能不可用。

### <a name="flow"></a>Flow

在大多数情况下，流在站点地理位置移动SharePoint继续工作。 我们建议你在移动完成后测试流程。

### <a name="power-apps"></a>Power Apps

Power Apps需要在目标位置重新创建。

### <a name="data-movement-between-geo-locations"></a>地理位置之间的数据移动

SharePoint 为其内容使用 Azure Blob 存储，而与站点关联的元数据及其文件存储在 SharePoint 内。 将站点从其源地理位置移到目标位置后，服务也会移动其关联的 Blob 存储。 Blob 存储移动将在大约 40 天内完成。
