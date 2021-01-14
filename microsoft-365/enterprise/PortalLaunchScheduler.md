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
ms.openlocfilehash: 66912f5730c580bd75282a64124fefcdf262d738
ms.sourcegitcommit: cc354fd54400be0ff0401f60bbe68ed975b69cda
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "49864872"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>使用门户启动计划程序启动门户

门户是 Intranet 上的一个 SharePoint 网站，其中包含大量使用网站内容的网站查看者。 分波启动门户是确保用户在访问新 SharePoint Online 门户时获得流畅且性能丰富的体验的重要部分。 

分波启动是推出门户的关键方法，如在 SharePoint Online 中规划门户启动 [推出计划所详述](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out?view=o365-worldwide)。 门户启动计划程序旨在帮助你通过管理新门户的重定向遵循一波/分阶段推出方法。 在每个阶段中，你可以收集用户反馈并监视每一波部署期间的性能。 这有一个缓慢引入门户的优势，让你可以选择暂停并解决问题，然后再继续下一波，并最终确保为用户提供积极体验。 

有两种类型的重定向： 
- 双向：启动新的新式 SharePoint Online 门户以替换现有 SharePoint 经典或新式门户 
- 临时页面重定向：启动没有现有 SharePoint 门户的新新式 SharePoint Online 门户

门户启动计划程序仅可用于启动新式 SharePoint Online (例如通信网站) 。 启动必须至少提前 7 天进行计划。 所需的波形数由预期用户数决定。 在计划门户启动之前，必须运行 [SharePoint](https://aka.ms/perftool) 页面诊断工具，以验证门户上的主页是否正常运行。 在门户启动结束时，具有网站权限的所有用户都将能够访问新网站。 

有关启动成功门户的详细信息，请遵循在创建、启动和维护正常门户时详述的指导原则、实践 [和建议](https://docs.microsoft.com/sharepoint/portal-health)。 

> [!NOTE]
> 此功能不适用于 Office 365 Germany、由世纪 (中国) 或 Microsoft 365 美国政府版计划运营的 Office 365。

## <a name="app-setup-and-connecting-to-sharepoint-online"></a>应用程序安装和连接到 SharePoint Online
1. [下载最新的SharePoint在线管理壳](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

    > [!NOTE]
    > 如果你已安装早期版本的SharePoint Online Management Shell，请进入添加或删除程序并卸载 "SharePoint Online Management Shell"。<br>在 "下载中心" 页面上，选择你的语言，然后单击 "下载" 按钮。 系统会要求你下载 x64 和 x86 .msi 文件之间做出选择。 如果你运行的是64位版本的Windows，请下载x64文件，如果你运行的是32位版本，请下载x86文件。 如果你不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。 下载文件后，运行该文件并按照安装向导中的步骤进行操作。

2. 在Microsoft 365中，以[全局管理员或SharePoint管理员](/sharepoint/sharepoint-admin-role)连接到SharePoint。 若要了解具体操作步骤，请参阅 [SharePoint 在线管理壳入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。


## <a name="view-any-existing-portal-launch-setups"></a>查看任何现有的门户启动设置

查看是否有现有门户启动配置：

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

## <a name="schedule-a-portal-launch-on-the-site"></a>计划网站上门户的启动

所需的波形数取决于您预期的启动大小。 
- 少于 10，000 个用户：1 wave
- 10k 至 30k 用户：3 个波形 
- 30k+ 到 100，000 个用户：5 个波形
- 超过 100，000 个用户：5 次，并联系你的 Microsoft 帐户团队

### <a name="steps-for-bidirectional-redirection"></a>双向重定向的步骤

双向重定向涉及启动新的新式 SharePoint Online 门户以替换现有 SharePoint 经典或新式门户。 无论用户是导航到旧网站还是新网站，活动波中的用户都将重定向到新网站。 尝试访问新网站的未启动波中的用户将重定向回旧网站，直到启动其 Wave。 

我们仅支持在旧网站上的默认主页与新网站上的默认主页之间重定向。 如果管理员或所有者需要访问新旧网站，而无需重定向，请确保使用参数列出 `WaveOverrideUsers` 这些管理员或所有者。

以分步方式将用户从现有 SharePoint 网站迁移到新的 SharePoint 网站：

1. 运行以下命令以指定门户启动波。
   
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

2. 完成验证。 重定向可能需要 5-10 分钟才能完成整个服务的配置。 

### <a name="steps-for-redirection-to-temporary-page"></a>重定向到临时页面的步骤

当不存在现有 SharePoint 门户时，应该使用临时页面重定向。 用户以分步方式定向到新的新式 SharePoint Online 门户。 如果用户在尚未启动的波中，则他们将被重定向到包含任何 URL (临时) 。 

1. 运行以下命令以指定门户启动波。
   
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

2. 完成验证。 重定向可能需要 5-10 分钟才能完成整个服务的配置。 

## <a name="pause-or-restart-a-portal-launch-on-the-site"></a>暂停或重新启动网站上门户启动

1. 若要暂停正在启动的门户并暂时阻止即将发生的波级，请运行以下命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```
2. 验证所有用户是否被重定向到旧网站。 

3. 若要重新启动已暂停的门户启动，请运行以下命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```
   
4. 验证重定向现已还原。 

## <a name="delete-a-portal-launch-on-the-site"></a>删除网站上门户启动

1. 运行以下命令以删除已计划或正在进行某个网站的门户启动。

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. 验证所有用户是否未发生重定向。

## <a name="learn-more"></a>了解详细信息
[在 SharePoint Online 中规划门户启动推出计划](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)
