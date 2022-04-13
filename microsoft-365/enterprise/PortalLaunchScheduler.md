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
description: 本文介绍如何使用门户启动计划程序启动门户
ms.openlocfilehash: 74de87a41f0b8b29dd901e757e410ff57f8f1d39
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64824127"
---
# <a name="launch-your-portal-using-the-sharepoint-portal-launch-scheduler"></a>使用 SharePoint 门户启动计划程序启动门户

门户是 Intranet 上的一个SharePoint通信站点，流量很大，在数周内，该网站的查看人数从 10，000 到 100，000 人不等。 使用门户启动计划程序启动门户，以确保用户在访问新的SharePoint门户时具有流畅的查看体验。
<br>
<br>
门户启动计划程序旨在通过批处理波形查看器和管理新门户的 URL 重定向来帮助你遵循分阶段推出方法。 在启动每波期间，可以收集用户反馈、监视门户性能，并暂停启动以解决问题，然后再继续下一波。 详细了解如何[在 SharePoint 中规划门户启动](/microsoft-365/Enterprise/Planportallaunchroll-out)。

**重定向有两种类型：**

- **双向**：启动新的新式SharePoint门户，以替换现有的SharePoint经典或新式门户
- **重定向到临时页面**：在没有现有SharePoint门户时启动新的新式SharePoint门户

作为启动的一部分，站点权限必须与波形分开设置。 例如，如果要发布组织范围内的门户，则可以设置“除外部用户以外的所有人”的权限，然后使用安全组将用户分隔成波形。 将安全组添加到波形不会授予该安全组对站点的访问权限。

> [!NOTE]
>
> - 可从SharePoint通信网站主页上的 **设置** 面板访问此功能。
> - 此功能只能在使用网站页面的新式SharePoint通信网站上使用，因为它们是用于门户的默认和建议类型。
> - 必须具有网站所有者权限，网站才能自定义和计划门户的启动。
> - 至少必须提前七天计划发射，每波发射可以持续一到七天。
> - 所需的波数由预期的用户数自动确定。
> - 在计划门户启动之前，必须运行[页面诊断SharePoint工具](https://aka.ms/perftool)来验证网站的主页是否正常。
> - 启动结束时，拥有网站权限的所有用户都可以访问新网站。
> - 如果你的组织正在使用[Viva Connections](/SharePoint/viva-connections)，用户可能会在Microsoft Teams应用栏中看到组织的图标，但是当图标被选中时，用户将无法访问门户，直到其波浪启动。
> - 此功能不适用于Office 365德国、Office 365由世纪互联 (中国) 运营，或Microsoft 365美国政府计划。

## <a name="understand-the-differences-between-portal-launch-scheduler-options"></a>了解门户启动计划程序选项之间的差异：

以前，门户启动只能通过 SharePoint PowerShell 进行计划。 现在，你有两个选项来帮助计划和管理门户的启动。 了解这两种工具之间的主要区别：

**SharePoint PowerShell 版本：**

- 使用 [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) 需要管理员凭据
- 一波的最小要求
- 根据协调世界时 (UTC) 时区计划启动

**产品内版本：**

- 需要站点所有者凭据
- 两个波的最低要求
- 根据门户的本地时区计划启动，如区域设置中所示

## <a name="get-started-using-the-portal-launch-scheduler"></a>使用门户启动计划程序开始

1. 在使用门户启动计划程序工具之前，添加 [所有需要通过网站权限访问此网站](https://support.microsoft.com/office/share-a-site-958771a8-d041-4eb8-b51c-afea2eae3658)**的** 用户，作为网站所有者、网站成员或访问者。

2. 然后，通过以下两种方式之一访问门户启动计划程序，开始计划门户的启动：

   **选项 1**：在您编辑和重新发布主页更改的前几次（或直到主页版本 3.0）之前，系统会提示你使用门户启动计划程序工具。 选择 **“计划启动** ”以继续计划。 或者选择 **“重新发布** ”以重新发布页面编辑，而无需安排启动。

   ![重新发布主页时提示使用门户启动计划程序的图像。](../media/portal-launch-republish-2.png)

   **选项 2**：随时可以导航到SharePoint通信网站主页，选择 **设置**，然后 **计划网站启动** 以计划门户的启动。

   ![“设置”窗格的图像，其中突出显示了“计划网站启动”。](../media/portal-launch-settings-2.png)

3. 接下来，确认门户的运行状况分数，并根据需要使用 [页面诊断SharePoint](https://aka.ms/perftool)工具对门户进行改进，直到门户收到 **“正常**”分数。 然后，选择“下一步”。

   ![门户启动计划程序工具的图像。](../media/portal-launch-panel-2.png)

   > [!NOTE]
   > 无法从门户启动计划程序编辑网站名称和说明，而是可以通过从主页中选择 **设置** 和 **网站信息** 来更改。

4. 从下拉列表中选择 **预期用户数** 。 此数字表示最有可能需要访问该网站的用户数。 门户启动计划程序将自动确定理想的波数，具体取决于预期用户，如下所示：

   - 不到 1 万用户：两波
   - 1 万到 3 万用户：三波
   - 3 万至 10 万用户：五波
   - 超过 10 万用户：通过启动门户中列出的包含超过 10 万用户部分的步骤，五波并联系 Microsoft 支持人员。

5. 然后，确定所需的 **重定向类型** ：

   **选项 1：将用户发送到现有的SharePoint页面 (双向)** – 在启动新的新式SharePoint门户以替换现有SharePoint门户时使用此选项。 活动波形中的用户将被重定向到新网站，无论他们是导航到旧站点还是新网站。 尝试访问新网站的非启动波中的用户将被重定向回旧网站，直到其波浪启动。

   > [!NOTE]
   > 使用双向选项时，计划启动的人员还必须具有对其他SharePoint门户的站点所有者权限。

   **选项 2：将用户发送到自动生成的临时页面 (临时页面重定向)** – 如果不存在现有的SharePoint门户，则应使用临时页面重定向。 用户被定向到新的新式SharePoint门户，如果用户处于尚未启动的波浪中，他们将被重定向到临时页面。

   **选项 3：将用户发送到外部页面** – 向临时登陆页面体验提供外部 URL，直到用户的波浪启动。

6. 将观众分成波浪。 每波最多添加 20 个安全组。 可以编辑波形详细信息，直至每波启动为止。 每波至少可以持续一天 (24小时) ，最多7天。 这使SharePoint和技术环境有机会适应和缩放到大量网站用户。 通过 UI 计划启动时，时区基于站点的区域设置。

   > [!NOTE]
   >
   > - 门户启动计划程序将自动默认为至少 2 波。 但是，此工具的 PowerShell 版本将允许 1 波。
   > - 此版本的门户启动计划程序不支持Microsoft 365组。

7. 确定谁需要立即查看站点，并将其信息输入到 **“从波浪中免除的用户** ”字段中。 这些用户从波形中排除，不会在启动之前、期间或之后重定向。

    >[!NOTE]
    > 最多可以添加 50 个不同的用户或安全组。 当需要超过 50 个人才能在波浪启动之前访问门户时，请使用安全组。

8. 确认门户启动详细信息并选择 **“计划**”。 计划启动后，对SharePoint门户主页所做的任何更改都需要在门户启动恢复之前收到正常的诊断结果。

### <a name="launch-a-portal-with-over-100k-users"></a>启动用户超过 10 万的门户

如果计划启动包含超过 100，000 个用户的门户，请按照下面列出的步骤提交支持请求。 请确保包含所有请求的信息。

> [!NOTE]
>
> - 只有在满足以下要求时，才应执行此过程：
> - 启动页已完成。
> - 已遵循[门户运行状况指南](https://aka.ms/portalhealth)。
> - 启动日期在 14 天内。

**请按以下步骤操作：**

1. 作为管理员，单击以下链接，该链接将在管理中心填充帮助查询。

[使用 10 万用户启动 SharePoint 门户](https://admin.microsoft.com/AdminPortal/?searchSolutions=Launch%20SharePoint%20Portal%20with%20100k%20users)

2. 在窗格底部，选择“**联系客户支持**”，然后选择“**新建服务请求**”。

3. 在 **“说明**”下，输入“使用 10 万用户启动SharePoint门户”。

4. 填写其余信息，然后选择“与我联系”。

5. 创建票证后，请确保向支持专员提供以下信息：
   - 门户 URL
   - 预期用户数
   - 估计的启动计划 (详细介绍波形大小) 
   - 使用页面诊断工具“导出启动页的 HAR 文件”，并在支持下共享文件

## <a name="make-changes-to-a-scheduled-portal-launch"></a>对计划的门户启动进行更改

可以针对每波进行启动详细信息编辑，直至波的启动日期。

1. 若要编辑门户启动详细信息，请导航到 **设置** 并选择 **“计划”网站启动**。
2. 然后，选择 **“编辑**”。
3. 完成编辑后，选择 **“更新**”。

## <a name="delete-a-scheduled-portal-launch"></a>删除计划的门户启动

可以随时取消或删除使用门户启动计划程序工具计划启动的启动，即使某些波形已启动。

1. 若要取消门户的启动，请导航到 **设置** 并 **计划网站启动**。

2. 然后，选择 **“删除** ”，然后在看到以下消息时再次选择 **“删除** ”。

   ![提示的图像，该提示询问是要删除还是保留计划的启动。](../media/portal-launch-delete-2.png)

## <a name="use-the-powershell-portal-launch-scheduler"></a>使用 PowerShell 门户启动计划程序

SharePoint门户启动计划程序工具最初仅通过 [SharePoint PowerShell](/powershell/sharepoint/sharepoint-online/introduction-sharepoint-online-management-shell) 提供，并且将继续通过 PowerShell 为喜欢此方法的客户提供支持。 本文开头的相同说明适用于门户启动计划程序的两个版本。

> [!NOTE]
> 需要管理员权限才能使用 SharePoint PowerShell。
> PowerShell 中创建的启动的门户启动详细信息将显示，可在 SharePoint 的新门户启动计划程序工具中进行管理。

### <a name="app-setup-and-connecting-to-sharepoint-online"></a>应用设置和连接到 SharePoint Online

1. [下载最新的SharePoint在线管理壳](https://go.microsoft.com/fwlink/p/?LinkId=255251)。

    > [!NOTE]
    > 如果你已安装早期版本的SharePoint Online Management Shell，请进入添加或删除程序并卸载 "SharePoint Online Management Shell"。
    >
    > 在 "下载中心" 页面上，选择你的语言，然后单击 "下载" 按钮。 系统会要求你下载 x64 和 x86 .msi 文件之间做出选择。 如果你运行的是64位版本的Windows，请下载x64文件，如果你运行的是32位版本，请下载x86文件。 如果你不知道，请参阅[我运行的是哪个版本的 Windows 操作系统？](https://support.microsoft.com/help/13443/windows-which-operating-system)。 下载文件后，运行该文件并按照安装向导中的步骤进行操作。

2. 在 Microsoft 365 中以[全局管理员或 SharePoint 管理员](/sharepoint/sharepoint-admin-role)身份连接到 SharePoint Online。要了解具体操作步骤，请参阅 [SharePoint Online 命令行管理程序入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

### <a name="view-any-existing-portal-launch-setups"></a>查看任何现有门户启动设置

若要查看是否存在现有的门户启动配置，

   ```PowerShell
   Get-SPOPortalLaunchWaves -LaunchSiteUrl <object> -DisplayFormat <object>
   ```

### <a name="schedule-a-portal-launch-on-the-site"></a>在网站上计划门户启动

所需的波数取决于预期的启动大小。

- 不到 1 万用户：一波
- 1 万到 3 万用户：三波
- 3 万至 10 万用户：五波
- 超过 10 万用户：五波并联系你的 Microsoft 帐户团队

#### <a name="steps-for-bidirectional-redirection"></a>双向重定向的步骤

双向重定向涉及启动新的新式 SharePoint Online 门户，以替换现有的SharePoint经典或新式门户。 活动波形中的用户将被重定向到新网站，无论他们是导航到旧站点还是新网站。 尝试访问新网站的非启动波中的用户将被重定向回旧网站，直到其波浪启动。

我们仅支持在旧网站上的默认主页与新网站上的默认主页之间重定向。 如果管理员或所有者需要访问旧站点和新网站而不被重定向，请确保使用 `WaveOverrideUsers` 该参数列出这些站点。

以暂存方式将用户从现有SharePoint站点迁移到新的SharePoint站点：

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

不存在现有SharePoint门户时，应使用临时页面重定向。 用户将以暂存方式定向到新的新式 SharePoint Online 门户。 如果用户处于尚未启动的波形中，它们将被重定向到任何 URL)  (临时页面。

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

### <a name="pause-or-restart-a-portal-launch-on-the-site"></a>暂停或重启网站上的门户启动

1. 若要暂停正在进行的门户启动并暂时防止即将发生的波形进度，请运行以下命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Pause - LaunchSiteUrl <object>
   ```

2. 验证是否将所有用户重定向到旧网站。

3. 若要重启已暂停的门户启动，请运行以下命令：

   ```PowerShell
   Set-SPOPortalLaunchWaves -Status Restart - LaunchSiteUrl <object>
   ```

4. 验证重定向现在是否已还原。

### <a name="delete-a-portal-launch-on-the-site"></a>删除网站上的门户启动

1. 运行以下命令以删除网站的计划或正在进行的门户启动。

   ```PowerShell
   Remove-SPOPortalLaunchWaves -LaunchSiteUrl <object>
   ```

2. 验证是否没有针对所有用户进行重定向。

## <a name="learn-more"></a>了解详细信息

[在 SharePoint Online 中规划门户启动推出计划](./planportallaunchroll-out.md)

[规划通信站点](https://support.microsoft.com/office/plan-your-sharepoint-communication-site-35d9adfe-d5cc-462f-a63a-bae7f2529182)
