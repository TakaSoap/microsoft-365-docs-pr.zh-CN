---
title: 使用门户启动计划程序启动门户
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 本文介绍如何使用门户启动计划程序启动门户
ms.openlocfilehash: e5e5850fa7e74f3e3b342e9bb28d17f65b491664
ms.sourcegitcommit: 474bd6a86c3692d11fb2c454591c89029ac5bbd5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2020
ms.locfileid: "49356663"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>使用门户启动计划程序启动门户

门户是 Intranet 上的一个 SharePoint 网站，其中包含大量使用网站内容的网站查看者。 以波形的顺序启动门户是确保用户具有访问新 SharePoint Online 门户的流畅且能力丰富的体验的重要部分。 

以波形方式启动是一种用于滚动门户的关键方式，在 [SharePoint Online 中规划门户启动回滚计划中](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)有详细介绍。 门户启动计划程序旨在帮助您通过管理新门户的重定向来帮助您遵循波形/分阶段的滚动方法。 在每个波形过程中，可以在每次部署浪潮期间收集用户反馈并监视性能。 这样做的优势在于门户的速度缓慢，让您可以选择在继续下一次浪潮之前暂停和解决问题，并最终确保用户获得良好的体验。 

有两种类型的重定向： 
- 双向：启动新的新式 SharePoint Online 门户以替换现有 SharePoint 经典或新式门户 
- 临时页面重定向：启动新的新式 SharePoint Online 门户（没有现有 SharePoint 门户）

门户启动计划程序仅可用于启动新式 SharePoint Online 门户 (即通信网站) 。 必须提前安排启动时间至少7天。 所需的波浪数由预期的用户数决定。 在计划门户启动之前，必须运行 [SharePoint 工具的页面诊断程序](https://aka.ms/perftool) 以验证门户上的主页是否运行正常。 在门户启动结束时，具有网站权限的所有用户都将能够访问新网站。 

有关启动成功的门户的详细信息，请遵循 [创建、启动和维护正常门户](https://docs.microsoft.com/sharepoint/portal-health)中详细介绍的基本原则、实践和建议。 

> [!NOTE]
> 此功能不适用于 Office 365 德国、由世纪互联运营的 Office 365 (中国) 或 Microsoft 365 美国政府版计划。

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>应用程序设置和连接到 SharePoint Online
1. [下载最新的SharePoint在线管理壳](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

    > [!NOTE]
    > 如果你已安装早期版本的SharePoint Online Management Shell，请进入添加或删除程序并卸载 "SharePoint Online Management Shell"。<br>在 "下载中心" 页面上，选择你的语言，然后单击 "下载" 按钮。 系统会要求你下载 x64 和 x86 .msi 文件之间做出选择。 如果你运行的是64位版本的Windows，请下载x64文件，如果你运行的是32位版本，请下载x86文件。 如果你不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。 下载文件后，运行该文件并按照安装向导中的步骤进行操作。

2. 在Microsoft 365中，以[全局管理员或SharePoint管理员](/sharepoint/sharepoint-admin-role)连接到SharePoint。 若要了解具体操作步骤，请参阅 [SharePoint 在线管理壳入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。


## <a name="view-any-existing-portal-launch-setups"></a>查看任何现有的门户启动设置

若要查看是否存在现有门户启动配置，请执行以下操作：

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>在网站上安排门户启动

所需的波浪数取决于所需的启动大小。 
- 少于10k 用户：1波
- 10k 到30k 用户：3波 
- 30k + 到100k 用户：5波
- 超过100k 的用户：5个波，并联系你的 Microsoft 帐户团队

### <a name="steps-for-bidirectional-redirection"></a>双向重定向步骤

双向重定向包括启动新的新式 SharePoint Online 门户以替换现有的 SharePoint 经典或新式门户。 Active 无线电波中的用户将被重定向到新网站，无论它们是导航到旧网站还是新网站。 尝试访问新网站的非启动浪潮中的用户将被重定向回旧网站，直到其波形启动。 

如果您有需要访问旧网站和新网站的管理员或所有者而不进行重定向，请确保使用参数列出这些网站 `WaveOverrideUsers` 。 仅支持旧网站上的默认主页和新网站上的默认主页之间的重定向。

若要以暂存方式将用户从现有 SharePoint 网站迁移到新的 SharePoint 网站，请执行以下操作：

1. 运行以下命令以指定门户启动波形。
   
   ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType Bidirectional -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

示例：
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType Bidirectional -RedirectUrl "https://contoso.sharepoint.com/teams/oldsite" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 完整验证。 重定向可能需要5-10 分钟才能在服务中完成其配置。 

### <a name="steps-for-redirection-to-temporary-page"></a>重定向到临时页面的步骤

如果不存在任何现有 SharePoint 门户，则应使用临时页面重定向。 以暂存方式将用户定向到新新式 SharePoint Online 门户。 如果用户处于尚未启动的浪潮中，则会将它们重定向到 (任何 URL) 的临时页面。 

1. 运行以下命令以指定门户启动波形。
   
      ```PowerShell
    New-SPOPortalLaunchWaves -LaunchSiteUrl <object> -RedirectionType ToTemporaryPage -RedirectUrl <string> -ExpectedNumberOfUsers <object> -WaveOverrideUsers <object> -Waves <object>
    ```

示例：
   ```PowerShell
   New-SPOPortalLaunchWaves -LaunchSiteUrl "https://contoso.sharepoint.com/teams/newsite" -RedirectionType ToTemporaryPage -RedirectUrl "https://portal.contoso.com/UnderConstruction.aspx" -ExpectedNumberOfUsers 10kTo30kUsers -WaveOverrideUsers "admin@contoso.com" -Waves ' 
[{Name:"Wave 1", Groups:["Viewers 1"], LaunchDateUtc:"2020/10/14"}, 
{Name:"Wave 2", Groups:["Viewers 2"], LaunchDateUtc:"2020/10/15"}, 
{Name:"Wave 3", Groups:["Viewers 3"], LaunchDateUtc:"2020/10/16"}]'
   ```

2. 完整验证。 重定向可能需要5-10 分钟才能在服务中完成其配置。 
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>在网站上暂停或重新启动门户启动

1. 若要暂停正在进行的门户启动，并暂时阻止即将发生的声波 progressions，请运行以下命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. 验证是否已将所有用户重定向到旧网站。 

3. 若要重新启动已暂停的门户启动，请运行以下命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. 验证重定向现在是否已还原。 

## <a name="delete-a-portal-launch-on-the-site"></a>在网站上删除门户启动
1. 创建门户启动浪潮。
  - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 运行以下命令以删除已计划或正在进行的网站的门户启动。

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

3. 验证是否所有用户都不会进行重定向。

## <a name="learn-more"></a>了解详细信息
[在 SharePoint Online 中规划门户启动滚动计划](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
