---
title: 在管理中心部署加载项
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom:
- AdminSurgePortfolio
- okr_smb
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 了解如何使用管理中心中的集中部署将加载项部署到组织的用户和组。
ms.openlocfilehash: 9ded0294912a3c3c99e62913bcdc349de7bae1b5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50915382"
---
# <a name="deploy-add-ins-in-the-admin-center"></a>在管理中心部署加载项

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](../microsoft-365-admin-center-preview.md?preserve-view=true&view=o365-21vianet)。

::: moniker-end

Office 加载项可帮助用户个性化设置文档并加速访问 Web 上的信息（请参阅[开始使用 Office 加载项](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)）。 作为管理员，可以使用 Microsoft 365 管理中心中的集中部署功能为贵组织的用户部署 Office 外接程序。 对于大多数管理员来说，集中部署是推荐且功能最丰富的方法，用于将外接程序部署到组织内的用户和组。

若要详细了解如何确定组织能否支持集中部署，请参阅确定加载项集中部署是否 [适用于组织](centralized-deployment-of-add-ins.md)。

若要了解有关在部署后管理加载项的更多信息，请参阅在[管理](manage-addins-in-the-admin-center.md)中心管理加载项
  
> [!NOTE]
>  对于 Word，Excel 和 PowerPoint 使用 [SharePoint](https://dev.office.com/docs/add-ins/publish/publish-task-pane-and-content-add-ins-to-an-add-in-catalog) 应用程序目录向本地环境中的用户部署外接程序，无需连接到 Microsoft 365 和/或需要支持 SharePoint 外接程序。 For Outlook use Exchange control panel to deploy in an on-premises environment without a connection to Microsoft 365.
  
## <a name="recommended-approach-for-deploying-office-add-ins"></a>部署 Office 加载项的推荐方法

若要使用分阶段方法推出加载项，建议采用以下方法：
  
1. 将外接程序推出给一小组业务利益干系人以及 IT 部门的成员。 如果部署成功，请移至步骤 2。
    
2. 向更多企业内部人员推出外接程序。 同样，评估结果，如果成功，则继续完整部署。
    
3. 向所有用户执行全面推出。
    
根据目标访问群体的规模，可以添加或删除推出步骤。
  
## <a name="deploy-an-office-add-in-using-the-admin-center"></a>使用管理中心部署 Office 加载项

在开始之前，请参阅确定外接程序的集中部署 [是否适用于你的组织](centralized-deployment-of-add-ins.md)。
  
1. 在管理中心， **转到"设置** \> **""加载项"** 页面。 如果看不到"加载项"页面 **，** 请转到"设置"" \> **集成** \> **应用""加载项"** 页面。

2. 选择 **页面顶部的"** 部署外接程序"，然后选择"下一步 **"。**

    > [!NOTE]
    > 管理中心将更新为集成应用的部署体验。 集成应用仅对全局管理员可见，而对于其他人，旧体验仍然存在。 如果看不到上述步骤，请转到"集中部署"部分，**具体方法为** 转到"设置""集成  >  **应用"。** 在"集成应用"**页面顶部**，选择"**加载项"。**

3. 选择一个选项并按照说明进行操作。
  
4. 如果选择了从 Office 应用商店添加外接程序的选项，则选择外接程序。 </br>

    可以按类别查看可用加载项：**建议**、评级或 **名称**。  Office 应用商店中仅提供免费加载项。 目前尚不支持付费加载项。 选择外接程序后，接受条款和条件以继续。 <br/> 

    > [!NOTE]
    > 使用 Office 应用商店选项，更新和增强功能会自动部署到用户。

5. On the next page， select **Everyone**， **Specific users/groups**， or **Just me** to specify who the add-in is deployed to. 使用"搜索"框查找特定用户或组。 <br/>

    > [!NOTE]
    > 若要了解适用于加载项的其他状态，请参阅 [加载项状态](./manage-addins-in-the-admin-center.md)。
  
6. 选择“部署”。
  
7. 部署加载项时，会出现绿色刻度线。 按照页面上的说明测试外接程序。

    > [!NOTE]
    > 用户可能需要重新启动 Office，以查看应用程序功能区上的外接程序图标。 Outlook 外接程序最多可能需要 24 小时才能显示在应用程序功能区上。

8. 完成后，选择下一 **步**。 如果只向自己部署，可以选择"更改有权访问加载项的用户 **"，** 以部署到更多用户。

    如果已经将加载项部署到组织的其他成员，请按照说明宣布部署加载项。 <br/>
  
    最佳做法是通知用户和组已部署的外接程序可用。 请考虑发送描述何时以及如何使用外接程序的电子邮件。 包含或链接到帮助内容或常见问题解答，如果用户遇到加载项问题，这些内容或常见问题解答可能会帮助用户。
  
### <a name="considerations-when-assigning-an-add-in-to-users-and-groups"></a>为用户和组分配加载项时的注意事项

全局管理员和 Exchange 管理员可以将外接程序分配给每个人或特定用户和组。 每个选项都有含义：
  
- **所有人** 此选项将外接程序分配给组织的每个用户。 请谨慎使用此选项，且仅应用于真正在组织中通用的加载项。

- **用户** 如果将加载项分配给单个用户，然后将加载项部署到新用户，则必须先添加新用户。

- **组** 如果将外接程序分配给组，则会自动为添加到该组的用户分配外接程序。 从组中删除用户时，用户将失去对外接程序的访问权限。 在任一情况下，管理员无需执行任何其他操作。

- **只有我** 如果您仅将外接程序分配给自己，则仅将外接程序分配给您的帐户，这是测试外接程序的理想帐户。

适合贵组织的选项取决于您的配置。 但是，我们建议使用组进行分配。 作为管理员，您可能会发现使用组并控制这些组的成员身份（而不是每次分配单个用户）可以更轻松地管理外接程序。 在某些情况下，您可能希望通过手动分配用户来向特定用户分配分配，从而限制对一小组用户的访问权限。
  
## <a name="more-about-office-add-ins-security"></a>有关 Office 加载项安全性的更多内容

Office 加载项结合了一个包含加载项相关元数据的 XML 清单文件，但最重要的是它指向包含所有代码和逻辑的 Web 应用程序。加载项的功能范围很广。例如，加载项可以：
  
- 显示数据。

- 读取用户文档以提供上下文服务。

- 从用户文档读取数据并向用户文档写入数据，以便向该用户提供价值。

若要详细了解 Office 加载项的类型和功能，请参阅 [Office Add-ins platform overview](/office/dev/add-ins/overview/office-add-ins)（Office 加载项平台概述），尤其是"Anatomy of an Office Add-in"（Office 加载项分析）一节。
  
若要与用户文档进行交互，加载项需要在清单中声明需要哪些权限。五级 JavaScript API 访问权限模型为任务窗格加载项的用户提供隐私和安全性的基础。Office 应用商店 中的大多数加载项是 ReadWriteDocument 级别，几乎所有加载项均至少支持 ReadDocument 级别。有关权限级别的详细信息，请参阅 [Requesting permissions for API use in content and task pane add-ins](/office/dev/add-ins/develop/requesting-permissions-for-api-use-in-content-and-task-pane-add-ins)（请求在内容和任务窗格加载项中使用 API 的权限）。
  
更新清单时，通常更改加载项的图标和文本。有时会更改加载项命令。但是，不会更改加载项的权限。Web 应用程序（加载项的所有代码和逻辑在其中运行）可以随时更改，这是 Web 应用程序的特性。
  
加载项更新的情况如下：
  
- **业务线加载项：** 在这种情况下，管理员显式上传清单，加载项需要管理员上传新的清单文件以支持元数据的更改。相关 Office 应用程序下次启动时，该加载项会更新。Web 应用程序可以随时更改。

    > [!NOTE]
    > 管理员无需删除 LOB 加载项以执行更新。   在"外接程序"部分，管理员只需单击 LOB 外接程序并选择右下角的"更新按钮"。 只有在新加载项的版本大于现有加载项版本时，更新才能运行。

- **Office 应用商店加载项：** 管理员从 Office 应用商店 中选择加载项后，如果 Office 应用商店 中更新了加载项，则该加载项会稍后以集中式部署方式更新。相关 Office 应用程序下次启动时，该加载项会更新。Web 应用程序可以随时更改。
  
## <a name="learn-more"></a>了解更多

[在管理中心管理加载项](manage-addins-in-the-admin-center.md)

[生成首个 Word 任务窗格加载项](/office/dev/add-ins/quickstarts/word-quickstart?tabs=yeomangenerator)。

[次要加载项和从应用商店获取加载项](minors-and-acquiring-addins-from-the-store.md)
  
[使用集中部署 PowerShell cmdlet 管理外接程序](../../enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins.md)
  
[疑难解答：用户看不到外接程序](/office365/troubleshoot/access-management/user-not-seeing-add-ins)