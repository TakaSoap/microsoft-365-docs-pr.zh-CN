---
title: 在管理中心管理加载项
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 了解如何使用集中式加载项将加载项部署到组织中用户和组。
ms.openlocfilehash: 5366bd5be80559f23490aeb54f9417a189169e12
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114197"
---
# <a name="manage-add-ins-in-the-admin-center"></a>在管理中心管理加载项

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。

::: moniker-end

Office 外接程序可帮助您个性化设置文档并简化访问 Web 上信息的方式 (请参阅"开始使用 [Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 外接程序) 。 

管理员为组织中用户部署外接程序后，管理员可以关闭或打开加载项，编辑、删除和管理对加载项的访问权限。

有关从管理中心安装加载项详细信息，请参阅在管理中心部署 [加载项](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)。
  
## <a name="add-in-states"></a>加载项状态

加载项可以位于"打开" **或** " **关闭"** 状态。
  
|**状态**|**状态出现的原因**|**影响**|
|:-----|:-----|:-----|
|**Active**  <br/> |管理员已上载外接程序并将其分配给用户或组。  <br/> |分配了加载项的用户和组可在相关客户端中看到它。  <br/> |
|**已禁用**  <br/> |管理员已禁用加载项。  <br/> |分配了外接程序的用户和组无法再访问它。  <br/> 如果外接程序的状态更改为"可用"，则用户和组将再次有权访问它。  <br/> |
|**已删除**  <br/> |管理员已删除加载项。  <br/> |分配了加载项的用户和组无法再访问它。  <br/> |
   
如果没有人再使用加载项，请考虑将其删除。 例如，如果加载项仅在一年的特定时间使用，则关闭外接程序可能有意义。

## <a name="delete-an-add-in"></a>删除加载项

还可以删除已部署的加载项。

1. 在管理中心，转到"设置  >  **服务&加载项页面**。

     > [!NOTE]
    > 管理中心将更新为集成应用的部署体验。 如果你看不到上述步骤，请转到"集中部署"部分，**具体方法为** 转到"设置集成  >  **应用"。** 在"集成应用 **"页面** 顶部，选择 **"加载项"。**

2. 选择已部署的外接程序。

3. 单击 **"删除加载项"。** 删除右下角的加载项按钮。

4. 验证你的选择，然后选择 **"删除外接程序"。**

## <a name="edit-add-in-access"></a>编辑加载项访问

部署后，管理员还可以管理用户对加载项的访问权限。

1. 在管理中心，转到"设置  >  **服务&加载项页面**。

     > [!NOTE]
    > 管理中心将更新为集成应用的部署体验。 如果你看不到上述步骤，请转到"集中部署"部分，**具体方法为** 转到"设置集成  >  **应用"。** 在"集成应用 **"页面** 顶部，选择 **"加载项"。**

2. 选择已部署的外接程序。

3. 单击"**谁****具有访问权限"下的"编辑"。**

4. 保存更改。

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>通过在所有客户端上关闭 Office 应用商店来阻止外接程序下载 (Outlook) 

> [!NOTE]
> Outlook 外接程序安装由另一个 [进程管理](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)。

作为组织，你可能希望阻止从 Office 应用商店下载新的 Office 外接程序。 这可与集中部署结合使用，以确保仅向组织内部的用户部署经组织核准的外接程序。
  
**关闭加载项获取**
  
1. 在管理中心，转到“**设置**”\> [服务和加载项](https://go.microsoft.com/fwlink/p/?linkid=2053743)页面。

     > [!NOTE]
    > 管理中心将更新为集成应用的部署体验。 如果你看不到上述步骤，请转到"集中部署"部分，**具体方法为** 转到"设置集成  >  **应用"。** 在"集成应用 **"页面** 顶部，选择 **"加载项"。**
    
3. 选择 **用户拥有的应用和服务**。
    
4. 清除允许用户访问 Office 应用商店的选项。

这将阻止所有用户从应用商店获取以下加载项。
  
- 适用于 Word、Excel 和 PowerPoint 2016 的外接程序来自：
    
  - Windows
    
  - Mac
    
  - Office
    
    
- 从 **AppSource 开始购置**
    
- Microsoft 365 中的加载项
    
尝试访问应用商店的用户将看到以下消息：抱歉 **，Microsoft 365** 已配置为阻止单独获取 Office 应用商店外接程序。
  
以下版本支持关闭 Office 应用商店：
  
- Windows：16.0.9001 - 当前可用。
    
- Mac：16.10.18011401 - 当前可用。
    
- iOS：2.9.18010804 - 当前可用。
    
- Web - 当前可用。
    
这不会阻止管理员使用集中部署从 Office 应用商店分配外接程序。
  
若要防止用户使用 Microsoft 帐户登录，可以将登录限制为仅使用组织帐户。 有关详细信息，请参阅 [Office 2016](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)中的标识、身份验证和授权。  

> [!NOTE]
> 阻止用户访问 Office 商店也会阻止他们旁 [加载 Office](https://docs.microsoft.com/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)外接程序进行测试。

## <a name="more-about-the-end-user-experience-with-add-ins"></a>有关外接程序的最终用户体验

部署外接程序后，最终用户可以开始在 Office 应用程序中使用它， ([Office](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862) 外接程序应用程序) 。 外接程序显示在外接程序支持的所有平台上。
  
如果加载项支持加载项命令，则 Office 功能区上会显示命令。在以下示例中，显示" **引文** "加载项的" **搜索引文** "命令。 

![具有搜索引文的 Office 功能区](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
如果部署的外接程序不支持外接程序命令，或者要查看所有部署的加载项，可以通过"我的外接程序 **"查看** 它们。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>在 Word 2016、Excel 2016 或 PowerPoint 2016 中

1. 选择 **" \> 插入我的外接程序"。** 
    
2. 选择 Office 加载项窗口中的" **由管理员管理** "选项卡。 
    
3. 双击先前部署的加载项（在本例中是" **引文** "）。 <br/>!["Office 加载项"页的"管理管理"选项卡](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>在 Outlook 中

1. 在"**主页"** 功能区上，选择"**获取加载项"。**<br/>![Outlook 中的'应用商店'按钮](../../media/getaddinsicon.png)
  
2. 选择 **左侧导航中的** "管理员管理"。 

## <a name="learn-more"></a>了解更多

[在管理中心部署加载项](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

深入了解如何创建和构建 [Office 加载项](https://docs.microsoft.com/office/dev/add-ins/overview/office-add-ins)。
  
[使用集中部署 PowerShell cmdlet 管理加载项](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)。
  
[疑难解答：用户看不到外接程序](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[次要加载项和从 Microsoft Store 获取加载项](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)
