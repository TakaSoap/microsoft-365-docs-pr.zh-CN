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
ms.openlocfilehash: 929492742fd140654bd13be8165093ee10647c6d
ms.sourcegitcommit: da34ac08c7d029c2c42d4428d0bb03fd57c448be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2020
ms.locfileid: "48999567"
---
# <a name="launch-your-portal-using-the-portal-launch-scheduler"></a>使用门户启动计划程序启动门户

您可以使用门户启动计划程序启动门户，方法是首先验证租户管理员为新门户设置波形的能力。 然后，管理员可以根据主动波中的用户是否存在来验证请求的重定向。

有关启动成功的门户的详细信息，请遵循 [创建、启动和维护正常门户](https://go.microsoft.com/fwlink/?linkid=2105838)中详细介绍的基本原则、实践和建议。 

## <a name="app-setup"></a>应用程序设置
1. 如果已 `Microsoft.Online.SharePoint.PowerShell` 通过控制面板从计算机中删除现有的，请卸载。
2. 在 PowerShell pass 上 `Install-Module -Name Microsoft.Online.SharePoint.PowerShell` 。

## <a name="connect-to-sharepoint-online"></a>连接到 SharePoint Online
1. 在 Windows 中打开 [SharePoint Online 命令行管理](https://docs.microsoft.com/powershell/sharepoint/sharepoint-online/connect-sharepoint-online) 程序。
2. 以管理员身份连接到你的租户。
   - `Connect-SPOService -Url "https://*-admin.sharepoint.com" -Credential "username”`
3.  在收到提示时提供你的密码。

## <a name="command-to-get-an-existing-setup"></a>用于获取现有安装程序的命令

要查看现有的门户启动配置，请执行以下操作：

1. Pass `Get-SPOPortalLaunchWaves  -LaunchSiteUrl  https://*.sharepoint.com/sites/newsite` 。
2. `-DisplayFormat Raw`如果想要查看格式化为原始输入格式的波形集合，请传递其他参数。

## <a name="commands-for-bi-directional-redirection"></a>双向重定向命令

若要以暂存方式将旧网站用户迁移到新网站，请执行以下操作：

1. 创建门户启动波形。
   - 这仅适用于早期版本的测试阶段。
   - 若要立即测试更改的影响，请确保第一个波形 `LaunchDateUtc` 设置为当前日期。 如果不提供此标志，则会收到一条错误消息。 发生此错误的原因是，在生产中启动的时间必须至少提前7天。

  `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/newsite" -RedirectionType Bidirectional -RedirectUrl "https://*.sharepoint.com/sites/oldsite" -ExpectedNumberOfUsers LessThan10kUsers -WaveOverrideUsers "*@microsoft.com" -Waves ' [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 完整验证。
  - 重定向在整个服务中完成其配置最长可能需要5分钟，因此请等待，然后继续。
  - 如果使用指定的用户登录 `WaveOverrideUsers` ，则不会发生任何更改。 您应始终在导航到的网站上进行。
  - 使用作为 *查看者 SG1* 一部分的用户登录。
    - 导航到旧网站，您应重定向到新网站。
    - 导航到新网站，您应停留在新网站上。
    - 在 *查看者 SG2* 中使用用户登录并导航到旧网站并停留在旧网站上。
    - 导航到新网站，并将重定向到旧网站。

3. 暂停门户启动。
  - 如果需要暂停启动波形，可以将其暂停为 "x" 天。 将此 `Status` 标志设置为 pause 可阻止所有即将到来的浪潮 progressions。 
  - `Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - 这将验证是否已将所有用户重定向到旧网站。

4. 重新启动门户启动进展。 
  - `Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - 验证重定向现在是否已还原。

5. 删除门户启动安装程序。
  - `Remove-SPOPortalLaunchWaves -LaunchSiteUrl https://*.sharepoint.com/sites/NewSite`.
  - 验证是否所有用户都不会进行重定向。

## <a name="commands-for-redirection-to-temporary-page"></a>用于重定向到临时页的命令

如果你没有以前的网站，并且要在新门户页上省略不在 wave 中的用户，请按照以下步骤操作。

若要在任何网站中创建临时页面，请执行以下操作：

1. 创建门户启动浪潮。
   - `New-SPOPortalLaunchWaves  -LaunchSiteUrl "https://*.sharepoint.com/sites/NewSite" -RedirectionType ToTemporaryPage -RedirectUrl "https://*.sharepoint.com/sites/OldSite" -ExpectedNumberOfUsers From10kTo30kUsers -WaveOverrideUsers *@microsoft.com -Waves [{Name:"Wave 1", Groups:["Viewers SG1"], LaunchDateUtc:"2020/10/14"}, {Name:"Wave 2", Groups:["Viewers SG2"], LaunchDateUtc:"2020/10/15"}]' -IsTesting $true`

2. 完整验证。

  - 在继续之前，请等待5分钟，因为该操作最长可能需要五分钟才能完成。
  - 使用作为 *查看者 SG1* 的一部分的用户记录日志，并：
     - 导航到新网站，您应停留在新网站上。
     - 导航到 "temp" 页面，您应停留在 "temp" 页面上。
  - 使用作为 *查看者 SG2* 的一部分的用户记录日志，并：
     - 导航到新网站，您应重定向到 "temp" 页面。
     - 导航到 "temp" 页面，您应停留在 "temp" 页面上。

3. 删除门户启动安装程序。
  - `Remove-SPOPortalLaunchWaves - LaunchSiteUrl  https://*.sharepoint.com/sites/NewSite`.
  - 验证是否所有用户都不会进行重定向。

## <a name="learn-more"></a>了解详细信息
[在 SharePoint Online 中规划门户启动滚动计划](https://docs.microsoft.com/microsoft-365/Enterprise/Planportallaunchroll-out)