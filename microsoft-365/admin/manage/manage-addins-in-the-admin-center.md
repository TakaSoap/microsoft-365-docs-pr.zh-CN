---
title: 在管理中心中管理外接程序
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
description: 了解如何通过在管理中心中使用集中部署将外接程序部署到组织中的用户和组。
ms.openlocfilehash: caaea8404c099f56704d21684323a4b20e61f52d
ms.sourcegitcommit: 222fc3f8841de82b1b558f47db8a79aa5054d0ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/11/2020
ms.locfileid: "45103086"
---
# <a name="manage-add-ins-in-the-admin-center"></a>在管理中心中管理外接程序

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

Office 加载项可帮助您对文档进行个性化设置，并简化访问 web 上的信息的方式 (请参阅[开始使用 Office 加载项](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。 

在管理员为组织中的用户部署外接程序后，管理员可以关闭或打开、编辑、删除和管理对外接程序的访问的外接程序。

有关从管理中心安装外接程序的详细信息，请参阅[在管理中心部署外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)。
  
## <a name="add-in-states"></a>加载项状态

外接程序可以处于 "**打开**" 或 "**关闭**" 状态。
  
|**状态**|**状态出现的原因**|**影响**|
|:-----|:-----|:-----|
|**Active**  <br/> |管理员上载了加载项，并将其分配给用户或组。  <br/> |分配了加载项的用户和组可在相关客户端中看到它。  <br/> |
|**已禁用**  <br/> |管理员已禁用加载项。  <br/> |分配了外接程序的用户和组无法再访问它。  <br/> 如果外接程序的状态更改为"可用"，则用户和组将再次有权访问它。  <br/> |
|**已删除**  <br/> |管理员已删除加载项。  <br/> |分配了加载项的用户和组无法再访问它。  <br/> |
   
如果没有人再使用加载项，请考虑删除外接程序。 例如，如果外接程序仅在一年的特定时间内使用，则关闭外接程序可能会有意义。

## <a name="delete-an-add-in"></a>删除外接程序

您还可以删除已部署的外接程序。

1. 在 "管理中心" 中，转到 "**设置**  >  **服务" & "加载项**" 页面。

2. 选择部署的加载项。

3. 单击 "**删除加载项**"。 移除右下角的外接端按钮。

4. 验证您的选择，然后选择 "**删除外接程序**"。

## <a name="edit-add-in-access"></a>编辑外接访问

部署后，管理员还可以管理用户对外接程序的访问。

1. 在 "管理中心" 中，转到 "**设置**  >  **服务" & "加载项**" 页面。

2. 选择部署的加载项。

3. 单击 "**有权访问**" 下的 "**编辑**"。

4. 保存所做的更改。

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>通过在除 Outlook) 之外的所有客户端中关闭 Office 应用商店来阻止加载项下载 (

> [!NOTE]
> Outlook 外接程序安装由[不同的进程](https://technet.microsoft.com/library/jj943754%28v=exchg.150%29.aspx)进行管理。

作为组织，您可能希望阻止从 Office 应用商店下载新的 Office 加载项。 这可与集中部署结合使用，以确保仅向组织中的用户部署组织批准的外接程序。
  
**关闭外接的获取**
  
1. 在管理中心，转到“**设置**”\> [服务和加载项](https://go.microsoft.com/fwlink/p/?linkid=2053743)页面。
    
3. 选择 "**用户拥有的应用和服务**"。
    
4. 清除 "允许用户访问 Office 应用商店" 选项。

这将阻止所有用户从存储中获取以下外接程序。
  
- Word、Excel 和 PowerPoint 2016 的外接程序来自：
    
  - Windows
    
  - Mac
    
  - Office
    
    
- 从**AppSource**中开始的收购
    
- Microsoft 365 中的外接程序
    
尝试访问应用商店的用户将看到以下消息：**抱歉，Microsoft 365 已配置为阻止单独获取 Office 应用商店外接程序。**
  
以下版本提供了对 Office 应用商店关闭的支持：
  
- Windows： 16.0.9001-当前可用。
    
- Mac： 16.10.18011401-当前可用。
    
- iOS： 2.9.18010804-当前可用。
    
- Web 当前可用。
    
这不会阻止管理员使用集中部署从 Office 应用商店分配外接程序。
  
若要阻止用户使用 Microsoft 帐户登录，可以将登录限制为仅使用组织帐户。 有关详细信息，请参阅[Office 2016 中的标识、身份验证和授权](https://technet.microsoft.com/library/jj683102%28v=office.16%29.aspx)。  

## <a name="more-about-the-end-user-experience-with-add-ins"></a>有关外接程序的最终用户体验的详细信息

部署加载项后，最终用户可以开始在 Office 应用程序中使用它 (请参阅[开始使用 Office 加载项](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)) 。 外接程序将显示在外接程序支持的所有平台上。
  
如果加载项支持加载项命令，则 Office 功能区上会显示命令。在以下示例中，显示" **引文** "加载项的" **搜索引文** "命令。 

![带有搜索引文的 Office 功能区](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
如果部署的外接程序不支持外接程序命令，或者如果您想要查看所有部署的加载项，可以通过**我的外接**程序查看它们。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>在 Word 2016、Excel 2016 或 PowerPoint 2016 中

1. 选择** \> "插入我的外接程序"**。 
    
2. 选择 Office 加载项窗口中的" **由管理员管理** "选项卡。 
    
3. 双击先前部署的加载项（在本例中是" **引文** "）。 <br/>!["Office 外接程序" 页的 "管理托管" 选项卡](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>在 Outlook 中

1. 在 "**主页**" 功能区上，选择 "**获取外接程序**"。<br/>![Outlook 中的'应用商店'按钮](../../media/getaddinsicon.png)
  
2. 在左侧导航中选择 "**管理员管理**"。 

## <a name="learn-more"></a>了解详细信息

[在管理中心部署外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/manage-deployment-of-add-ins)

深入了解如何创建和构建 [Office 加载项](https://go.microsoft.com/fwlink/p/?linkid=846362)。
  
[使用集中部署 PowerShell cmdlet 管理外接程序](https://docs.microsoft.com/office365/enterprise/use-the-centralized-deployment-powershell-cmdlets-to-manage-add-ins)。
  
[疑难解答：用户看不到外接程序](https://docs.microsoft.com/office365/troubleshoot/access-management/user-not-seeing-add-ins)

[来自 Microsoft Store 的未成年人和收购外接程序](https://docs.microsoft.com/microsoft-365/admin/manage/minors-and-acquiring-addins-from-the-store)