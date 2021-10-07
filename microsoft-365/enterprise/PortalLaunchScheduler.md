---
title: 使用门户启动计划程序启动门户
ms.author: jhendr
author: jhendr
manager: pamgreen
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- SPO160
- MET150
description: 本文介绍了如何使用门户启动计划程序启动门户
ms.openlocfilehash: 035ed3401323ae1221c7e7afd6f6c7d34b78aea4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60172091"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a>使用门户启动SharePoint启动计划程序启动门户

门户是 Intranet 上高流量的 SharePoint 通信网站，在几周内拥有 10，000 到 100，000 多个查看者的网站。 使用门户启动计划程序启动门户，以确保用户在访问新的门户时具有流畅的SharePoint体验。
<br>
<br>
门户启动计划程序旨在帮助你遵循分阶段推出方法，方法是分批对查看者进行批处理，并管理新门户的 URL 重定向。 在每个波的启动过程中，你可以收集用户反馈、监视门户性能，并暂停启动以解决问题，然后再继续下一波。 详细了解如何在 SharePoint 中[规划门户SharePoint。](/microsoft-365/Enterprise/Planportallaunchroll-out)

**有两种类型的重定向：**

- **双向：启动** 新的新式SharePoint门户以替换现有SharePoint或新式门户
- **重定向到临时页面**：启动新的新式SharePoint门户，无现有SharePoint门户

在启动时，必须独立于波形设置网站权限。 例如，如果要发布组织范围的门户，可以将权限设置为"除外部用户以外的所有人"，然后使用安全组将用户分为多个组。 向 Wave 添加安全组不会授予该安全组对网站的访问权限。

> [!NOTE]
>
> - 从 2021年 5 月开始，可从面向目标发布客户的 SharePoint 通信网站的主页上的 设置 面板访问此功能，并将于 2021 年 7 月提供给所有客户。
> - 此工具的 PowerShell 版本现在可用。
> - 此功能只能在新式通信SharePoint使用。
> - 您必须具有网站的网站所有者权限才能自定义和计划门户的启动。
> - 启动必须至少提前 7 天进行，并且每一波可以持续 1 到 7 天。
> - 所需的波形数由预期用户数自动确定。
> - 在计划门户启动之前，必须运行[](https://aka.ms/perftool)SharePoint 诊断工具，以验证网站的主页是否正常运行。
> - 在启动结束时，具有网站权限的所有用户都将能够访问新网站。
> - 如果组织使用的是[Viva 连接](/SharePoint/viva-connections)，则用户可能会看到 Microsoft Teams 应用栏中的组织图标，但是当选择该图标时，用户将无法访问门户，直到其 Wave 启动。
> - 此功能不适用于德国Office 365、由世纪Office 365中国 (运营) 或美国政府Microsoft 365计划。

## <a name="understand-the-differences-between-portal-launch-scheduler-options"></a>了解门户启动计划程序选项之间的差异：

以前，门户启动只能通过 PowerShell SharePoint计划。 现在，有两个选项可帮助你计划和管理门户的启动。 了解这两种工具之间的主要差异：

**SharePointPowerShell 版本：**

- 使用 PowerShell 时需要[管理员SharePoint凭据](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell)
- 第一波的最低要求
- 根据协调世界时与 UTC 时区 () 启动

**产品内版本：**

- 需要网站所有者凭据
- 两个波形的最低要求
- 根据门户的本地时区（如区域设置中指示）计划启动

## <a name="get-started-using-the-portal-launch-scheduler"></a>开始使用门户启动计划程序

1. 使用门户启动计划程序工具之前，将[](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658)需要通过网站权限访问此网站的所有用户添加为网站所有者、网站成员或访问者。

2. 然后，通过以下两种方式之一访问门户启动计划程序，开始计划门户的启动：

   **选项 1：** 编辑和重新发布对主页所做的更改（或直到主页版本 3.0 之前）的首次操作，系统将提示你使用门户启动计划程序工具。 选择 **计划启动** 以使用计划前进。 或者， **选择"重新发布** "以重新发布页面编辑，而不计划启动。

   ![重新发布主页时使用门户启动计划程序提示的图像。](../media/portal-launch-republish-2.png)

   **选项 2：** 你随时都可以导航到 SharePoint 通信网站主页，选择 **"设置"，然后** 计划网站启动以计划门户的启动。

   ![突出显示"设置启动计划"窗格的图像。](../media/portal-launch-settings-2.png)

3. 接下来，使用适用于 SharePoint 的页面诊断工具确认门户的运行状况分数 [，](https://aka.ms/perftool)并根据需要对门户 **进行改进，** 直到门户获得正常分数。 然后，选择“下一步”。

   ![门户启动计划程序工具的图像。](../media/portal-launch-panel-2.png)

   > [!NOTE]
   > 无法从门户启动计划程序编辑网站名称和说明，而是可以通过从主页选择"网站 **设置"网站** 信息"进行更改。 

4. 从 **下拉列表中选择** "预期用户数"。 此图表示最有可能需要访问网站的用户数。 门户启动计划程序将根据预期用户自动确定理想的波形数，如下所示：

   - 少于 10，000 个用户：两个波形
   - 10k 至 30k 用户：三个波形
   - 30k+ 到 100，000 个用户：五个波形
   - 超过 100，000 个用户：五个波形，通过启动门户（用户超过 10 万）部分中列出的步骤联系 Microsoft。

5. 然后，确定 **所需的重定向** 类型：

   **选项 1：** 将用户发送到现有 SharePoint 页面 (双向) – 在启动新的新式 SharePoint 门户以替换现有 SharePoint 门户时，请使用此选项。 无论用户导航到旧站点还是新站点，活动波中的用户都将重定向到新站点。 尝试访问新网站的非启动波中的用户将被重定向回旧网站，直到启动其 Wave。

   > [!NOTE]
   > 使用双向选项时，计划启动的用户还必须具有对另一个网站门户SharePoint权限。

   **选项 2：** 将用户发送到自动生成的临时 (页面重定向) – 当不存在现有页面重定向门户SharePoint使用临时页面重定向。 用户将被定向到新的新式SharePoint门户，如果用户在尚未启动的波波中，他们将被重定向到临时页面。

   **选项 3：将用户** 发送到外部页面 – 提供外部 URL 以用于临时登陆页面体验，直到启动用户的 Wave。

6. 将受众分成一个波波。 每波最多添加 20 个安全组。 可以一直编辑 Wave 详细信息，直到启动每一波。 每一波可以持续至少一天 (24 小时) 最多七天。 这使SharePoint和技术环境有机会适应和扩展大量网站用户。 通过 UI 计划启动时，时区基于网站的区域设置。

   > [!NOTE]
   >
   > - 门户启动计划程序将自动默认为至少 2 个波形。 但是，此工具的 PowerShell 版本将允许使用 1 波。
   > - Microsoft 365版本的门户启动计划程序不支持这些组。

7. 确定需要马上查看网站的用户，并输入其信息到"免受波形影响的用户 **"** 字段中。 这些用户被从波形中排除，并且不会在启动之前、期间或之后重定向。


    >[!NOTE]
    > 最多可以添加 50 个不同的用户或安全组。 当需要超过 50 个人才能在波形开始启动之前访问门户时，请使用安全组。 

8.  确认门户启动详细信息，然后选择 **计划**。 计划启动后，对 SharePoint 门户主页的任何更改都需要在门户启动恢复之前收到正常的诊断结果。


### <a name="launch-a-portal-with-over-100k-users"></a>启动具有超过 10 万个用户的门户

如果计划启动的用户数超过 100，000 的门户，请按照下面列出的步骤提交支持请求。 确保包含所有请求的信息。

> [!NOTE]
>
> - 只有在满足以下要求时，才应执行此过程：
> - "启动页"已完成。
> - [已遵循门户](https://aka.ms/portalhealth) 运行状况指南。
> - 启动日期在 14 天内。

**请按以下步骤操作：**

1. 作为管理员，单击以下链接以填充管理中心中的帮助查询。 

[启动SharePoint 10 万个用户的用户的门户](https://admin.microsoft.com/AdminPortal/?searchSolutions=Launch%20SharePoint%20Portal%20with%20100k%20users)

2. 在窗格底部，选择“**联系客户支持**”，然后选择“**新建服务请求**”。 

3. 在 **"说明**"下，输入"SharePoint 10 万个用户启动门户"。 

4. 填写其余信息，然后选择“与我联系”。

5. 创建票证后，请确保向支持专员提供以下信息：
   - 门户 URL 的
   - 预期用户数
   - 估计的启动计划

## <a name="make-changes-to-a-scheduled-portal-launch"></a>对计划的门户启动进行更改

可以编辑每一波的启动详细信息，直到 Wave 启动日期为止。

1. 若要编辑门户启动详细信息，**请导航到**"设置，然后选择"**计划网站启动"。**
2. 然后，选择"**编辑"。**
3. 完成编辑后，选择"更新 **"。**

## <a name="delete-a-scheduled-portal-launch"></a>删除计划的门户启动

使用门户启动计划程序工具安排的启动可以随时取消或删除，即使已启动某些波形。

1. 若要取消门户的启动，请导航到"设置 **计划****网站启动"。**

2. 然后，选择 **"删除** "，然后在看到下面的邮件时，选择"再次 **删除** "。

   ![询问是否要删除或保留计划启动的提示的图像。](../media/portal-launch-delete-2.png)

## <a name="use-the-powershell-portal-launch-scheduler"></a>使用 PowerShell 门户启动计划程序

the SharePoint Portal launch scheduler tool was originally only available via [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) and will continue to be supported through PowerShell for customers who prefer this method. 本文开头的相同说明适用于门户启动计划程序这两个版本。

> [!NOTE]
> 您需要管理员权限才能使用 SharePoint PowerShell。
> 将在 PowerShell 中创建的启动的门户启动详细信息显示，并且可在 SharePoint 中新的门户启动计划程序工具中进行管理。

### <a name="app-setup-and-connecting-to-sharepoint-online"></a>应用设置和连接到 SharePoint Online

1. [下载最新的SharePoint在线管理壳](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

    > [!NOTE]
    > 如果你已安装早期版本的SharePoint Online Management Shell，请进入添加或删除程序并卸载 "SharePoint Online Management Shell"。
    > 
    > 在 "下载中心" 页面上，选择你的语言，然后单击 "下载" 按钮。 系统会要求你下载 x64 和 x86 .msi 文件之间做出选择。 如果你运行的是64位版本的Windows，请下载x64文件，如果你运行的是32位版本，请下载x86文件。 如果你不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。 下载文件后，运行该文件并按照安装向导中的步骤进行操作。

2. 在Microsoft 365中，以[全局管理员或SharePoint管理员](/sharepoint/sharepoint-admin-role)连接到SharePoint。 若要了解具体操作步骤，请参阅 [SharePoint 在线管理壳入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

### <a name="view-any-existing-portal-launch-setups"></a>查看任何现有的门户启动设置

查看是否有现有的门户启动配置：

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a>计划站点上的门户启动

所需的波形数取决于您预期的启动大小。

- 少于 10，000 个用户：一波
- 10k 至 30k 用户：三个波形 
- 30k+ 到 100，000 个用户：五个波形
- 超过 100，000 个用户：五个波形并联系你的 Microsoft 帐户团队

#### <a name="steps-for-bidirectional-redirection"></a>双向重定向的步骤

双向重定向涉及启动新的新式 SharePoint Online 门户，以替换现有SharePoint或新式门户。 无论用户导航到旧站点还是新站点，活动波中的用户都将重定向到新站点。 尝试访问新网站的非启动波中的用户将被重定向回旧网站，直到启动其 Wave。

我们仅支持在旧网站上的默认主页和新网站上的默认主页之间进行重定向。 如果管理员或所有者需要访问新旧网站而无需重定向，请确保使用 参数列出 `WaveOverrideUsers` 这些管理员或所有者。

以分步方式SharePoint用户从现有SharePoint网站迁移到新网站：

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

#### <a name="steps-for-redirection-to-temporary-page"></a>重定向到临时页面的步骤

当不存在现有门户时，应该使用SharePoint重定向。 用户以一种分步SharePoint定向到新的新式联机门户。 如果用户在尚未启动的波形中，他们将被重定向到包含任何 URL (临时) 。

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

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a>暂停或重新启动站点上的门户启动

1. 若要暂停正在启动的门户并暂时阻止即将发生的波形进度，请运行以下命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. 验证所有用户是否都重定向到旧网站。

3. 若要重新启动已暂停的门户启动，请运行以下命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```

4. 验证重定向现已还原。

### <a name="delete-a-portal-launch-on-the-site"></a>删除站点上的门户启动

1. 运行以下命令以删除已计划或正在进行某个网站的门户启动。

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. 验证所有用户是否未发生重定向。

## <a name="learn-more"></a>了解详细信息

[在 SharePoint Online 中规划门户启动推出计划](./planportallaunchroll-out.md)

[规划通信网站](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
