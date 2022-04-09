---
title: 设置和配置 Moodle 插件
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: 通过设置和配置 Moodle 插件，准备好集成 Moodle 和 Microsoft Teams。
ms.openlocfilehash: efe1ebdb92cbb3367e54e99df89b75c853c48357
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747382"
---
# <a name="set-up-and-configure-the-moodle-plugin"></a>设置和配置 Moodle 插件

本文介绍如何安装和配置 Moodle LMS 插件，以便将Microsoft Teams与 Moodle 体验结合在一起。

## <a name="prerequisites"></a>先决条件

下面是安装 Moodle 的先决条件：

* Moodle 管理员凭据。
* Azure AD管理员凭据。
* 可在其中创建新资源的 Azure 订阅。

## <a name="1-install-the-microsoft-365-moodle-plugins"></a>1. 安装Microsoft 365 Moodle 插件

Microsoft Teams中的 Moodle 集成由开放源代码[Microsoft 365 Moodle 插件集](https://github.com/Microsoft/o365-moodle)提供支持。

### <a name="requisite-applications-and-plugins"></a>必需的应用程序和插件

在继续安装Microsoft 365 Moodle 插件之前，请安装并下载以下项：

1. [当前稳定版本的 Moodle](https://download.moodle.org/releases/latest/)。
1. 将 Moodle [OpenID 连接](https://moodle.org/plugins/auth_oidc)和[Microsoft 365集成](https://moodle.org/plugins/local_o365)插件下载并保存到本地计算机。

    > [!NOTE]
    > 安装 OpenID 连接 和 Microsoft 365 集成插件是Teams集成所必需的。
    >
    > 建议[使用Microsoft 365 Teams主题](https://moodle.org/plugins/theme_boost_o365teams)插件。

### <a name="microsoft-365-moodle-plugins"></a>Microsoft 365 Moodle 插件

#### <a name="install-plugins"></a>安装插件

1. 登录到 Moodle 服务器并导航到 **站点管理**。
1. 选择 **“插件”** 选项卡，然后选择 **“安装插件**”。
1. 从 **ZIP 文件部分的“安装插件** ”部分中， **选择一个文件**。
1. 从左侧导航面板 **中选择Upload文件**，浏览下载的文件，然后选择 **此文件Upload**。
1. 从左侧导航面板中选择 **“站点管理** ”以返回到管理员仪表板。
1. 向下滚动到 **本地插件**，然后选择 **Microsoft 365集成** 链接。

    > [!IMPORTANT]
    >
    > * 将Microsoft 365 Moodle 插件配置页保留在单独的浏览器选项卡中打开，因为在整个过程中需要返回到这组页面。  
    >
    > * 如果没有现有的 Moodle 网站，请转到 [Azure 存储库上的 Moodle](https://github.com/azure/moodle) ，并快速部署 Moodle 实例并根据需要对其进行自定义。

#### <a name="enable-the-openid-connect-authentication-plugin"></a>启用 OpenID 连接身份验证插件

1. 导航到 **Site** **AdministrationPluginsAuthentication** >  > ，然后选择 **“管理身份验证**”。
1. 找到 **OpenID 连接** 身份验证插件，然后选择 *眼睛图标* 以启用它。
1. 为插件选择 **设置** 以验证 **授权** 和 **令牌** 终结点。
    1. 默认值应为：
        1. 授权终结点： ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. 令牌终结点： ``https://login.microsoftonline.com/common/oauth2/token``.
1. 记录 **重定向 URI** 供以后使用。

## <a name="2-configure-the-connection-between-the-microsoft-365-plugins-and-azure-ad"></a>2.配置Microsoft 365插件与Azure AD之间的连接

必须配置Microsoft 365插件与Azure AD之间的连接。

### <a name="requisites"></a>先决条件

使用 PowerShell 脚本将 Moodle 注册为Azure AD中的应用程序。 该脚本预配以下项：

* Microsoft 365租户的新Azure AD应用程序，由 Microsoft 365 Moodle 插件使用。
* Microsoft 365租户的应用为预配的应用设置所需的回复 URL 和权限，并返回`AppID``Key`和 。

使用生成`AppID``Key`的和在Microsoft 365 Moodle 插件设置页中使用Azure AD配置 Moodle 服务器站点。

> [!IMPORTANT]
>
> * PowerShell 脚本不会使用最新的配置项进行更新，因此，必须按照 Moodle [3.10.6 和 3.11.3](https://docs.moodle.org/311/en/Microsoft_365) 发行页上概述的步骤手动完成配置。
>
> * 有关手动注册 Moodle 实例的详细信息，请参阅 [将 Moodle 实例注册为应用程序](https://docs.moodle.org/311/en/Microsoft_365#Register_Application_in_Azure_manually)。

### <a name="the-teams-for-moodle-set-up-process"></a>Moodle Teams设置过程

1. 在“Microsoft 365集成插件”页中，选择 **“设置”** 选项卡。

1. 选择 **“下载 PowerShell 脚本”** 按钮，并将其作为 ZIP 文件夹保存到本地计算机。

1. 从 ZIP 文件准备 PowerShell 脚本，如下所示：

    1. 下载并提取 `Moodle-AzureAD-Powershell.zip` 文件。
    1. 打开提取的文件夹。
    1. 右键单击该 `Moodle-AzureAD-Script.ps1` 文件并选择 **“属性**”。
    1. 在属性窗口的“**常规**”选项卡下，选中`Unblock`位于窗口底部 **的安全** 属性旁边的复选框。
    1. 选择“确定”。
    1. 将目录路径复制到提取的文件夹。

1. 以管理员身份运行 PowerShell：

    1. 选择“开始”。
    1. 键入 PowerShell。
    1. 右键单击 **Windows PowerShell**。
    1. 选择 **“以管理员身份运行**”。

1. 通过键入 `cd .../.../Moodle-AzureAD-Powershell` 目录路径的位置 `.../...` ，导航到解压缩的目录。

1. 执行 PowerShell 脚本：

    1. 输入 `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser`。
    1. 输入 `./Moodle-AzureAD-Script.ps1`。
    1. 在弹出窗口中登录到Microsoft 365管理员帐户。
    1. 输入Azure AD应用程序的名称，例如 Moodle 或 Moodle 插件。
    1. 输入 Moodle 服务器的 URL。
    1. 复制脚本生成 **的应用程序 ID (`AppID`)** 和 **应用程序密钥 (`Key`)** 并保存它们。

1. 返回到插件管理页，**Site** administrationPluginsAuthenticationOpenID >  >  >  **连接**。

1. 将 `AppID` 值粘贴到“ **应用程序 ID** ”框中， `Key` 并将值粘贴到 **“密钥** ”框中，然后选择 **“保存更改**”。

1. 导航到 **Site** **administrationPluginsLocal** >  >  **插件**，然后选择 **Microsoft 365集成**。

1. 在 **“选择连接”方法** 中，选择“ **应用程序访问**”，然后再次选择 **“保存更改** ”。

1. 页面刷新后，可以看到另一个新分区 **管理员同意&其他信息**。
    1. 选择 **“提供管理员同意**”链接，输入Microsoft 365全局管理员凭据，然后 **接受** 以授予权限。
    1. 在 **“Azure AD租户**”字段旁边，选择“**检测”** 按钮。
    1. 在 **OneDrive for Business URL** 旁边，选择 **“检测”** 按钮。
    1. 填充字段后，再次选择 **“保存更改** ”按钮。

1. 选择 **“更新”** 按钮以验证安装，然后选择 **“保存更改**”。

1. 在 Moodle 服务器和Azure AD之间同步用户。 根据你的环境，你可以在此阶段选择不同的选项。 首先，请执行以下操作：
    1. 切换到 **“同步设置”选项卡**。

    1. 在“**使用Azure AD的同步用户**”部分中，选择适用于环境的复选框。 必须选择以下选项：  

        ✔ 在 Moodle 中为Azure AD中的用户创建帐户。
        
        ✔ 为Azure AD中的用户更新 Moodle 中的所有帐户。
        

    1. 在 **“用户创建限制**”部分中，可以设置筛选器以限制同步到 Moodle 的Azure AD用户。
    1. 在 **“课程同步**”部分中，可以选择 **“课程同步自定义”** 选项，以便自动创建某些或全部现有 Moodle 课程的组和Teams。

1. 若要验证 [cron](https://docs.moodle.org/310/en/Cron) 任务并首次手动运行它们，请导航到 **Site** administrationServerTasksScheduled >  >  >  **任务**。

    1. 向下滚动并找到 **具有Azure AD的任务同步用户**，然后选择 **“立即运行**”。
        1. 这会将AAD用户同步到 Moodle 网站。
    1. 接下来，找到 **同步 Moodle 课程以Microsoft Teams** 任务，然后选择 **“立即运行**”。
        1. 如果找到所有者，此任务将创建组并Teams。
        1. 如果用户在课程上下文中具有 `local/o365:teamowner` 功能，则用户是团队所有者。 如果用户在课程上下文中具有 `local/o365:teammember` 功能，则用户是团队成员。  
        1. 默认的 *教师* 角色具有 `local/o365:teamowner" capability`默认学生角色，并且默认 *学生* 角色具有该 `local/o365:teammember` 功能。

    > [!NOTE]
    >
    > Moodle [Cron](https://docs.moodle.org/311/en/Scheduled_tasks) 根据任务计划运行。 默认计划每天凌晨 1：00 在服务器的本地时区中一次。 但是，cron 应更频繁地运行以使所有内容保持同步。

1. 返回到网站管理页。

1. 配置所需的设置以启用Teams应用集成。

    1. 若要启用 **OpenID 连接**，请转到 **Site** **administrationPluginsManage** >  >  **身份验证**。
        1. 查找 **OpenID 连接**，并选择眼睛图标（如果已灰显）。保存更改。
    1. 若要启用帧嵌入，请转到 **站点管理** 并在 **“安全**”部分中选择 **“HTTP 安全** 性”。
        1. 选中 **“允许嵌入帧**”旁边的复选框。 保存更改。
    1. 若要启用启用 Moodle API 功能的 Web 服务，请转到 **Site** **administrationAdvanced** >  功能。
        1. 确保选中 **“启用 Web 服务”** 旁边的复选框。 保存更改。
    1. 若要为Microsoft 365启用外部服务，请转到 **Site** **administrationPlugins** > ，然后在 **Web 服务** 部分中选择 **外部服务**。

        ✔ 在 **“内置服务**”部分中，找到 **Moodle Microsoft 365 Web 服务**。
        
        ✔ 在 **Moodle Microsoft 365 Webservices 行上** 选择 **“编辑**”。
        
        ✔ 选择眼睛图标（如果其灰显）。保存更改。
        

    1. 编辑经过身份验证的用户权限，以允许他们创建 Web 服务令牌。

        ✔ 转到 **“网站管理**”、“**用户**”选项卡，并在“**权限**”部分中查找 **“定义角色**”。
        
        ✔ 在 **“管理用户** ”选项卡上，找到 **经过身份验证的用户** 角色，然后选择编辑图标。
        
        ✔ 向下滚动并找到 **“创建 Web 服务令牌** ”功能，然后选择“ **允许** ”复选框。 保存更改。
        

安装和配置插件后，可以：

* [将 Moodle 选项卡添加到Teams类](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app)。
* [将Teams类和会议添加到 Moodle LMS](teams-classes-meetings-with-moodle.md)。

## <a name="extra-moodle-plugin-documentation"></a>额外的 Moodle 插件文档

若要查看 Moodle Microsoft 365集成指南和发行说明，请参阅以下资源：

* [穆德尔和Microsoft 365 3.10.6](https://docs.moodle.org/310/en/Microsoft_365)。
* [穆德尔和Microsoft 365 3.11.3](https://docs.moodle.org/310/en/Microsoft_365)。
