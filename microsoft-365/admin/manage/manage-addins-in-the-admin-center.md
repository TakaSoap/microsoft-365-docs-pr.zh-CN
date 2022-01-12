---
title: 在管理中心管理加载项
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_NonTOC
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 737e8c86-be63-44d7-bf02-492fa7cd9c3f
description: 了解如何使用集中式加载项将加载项部署到组织中用户和组。
ms.openlocfilehash: d2d1c4d36bf37ad82ac5c720931146c0dfb2220d
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61935833"
---
# <a name="manage-add-ins-in-the-admin-center"></a>在管理中心管理加载项

Office外接程序可帮助您个性化设置文档并简化访问 Web 上信息的方式。 请参阅[开始使用Office外接程序](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)。 

管理员为组织中用户部署外接程序后，管理员可以关闭或打开外接程序、编辑、删除和管理对外接程序的访问权限。

有关从管理中心安装加载项的信息，请参阅在管理中心部署 [加载项](./manage-deployment-of-add-ins.md)。
  
## <a name="add-in-states"></a>加载项状态

加载项可以"开"或"**关"** 状态。 
  
| 状态 | 此状态如何出现 | 影响 |
|:-----|:-----|:-----|
|**活动**  <br/> |管理员已上载外接程序并将其分配给用户或组。  <br/> |分配了加载项的用户和组可在相关客户端中看到它。  <br/> |
|**已禁用**  <br/> |管理员已禁用加载项。  <br/> |分配了外接程序的用户和组无法再访问它。  <br/> 如果外接程序的状态更改为"可用"，则用户和组将再次有权访问它。  <br/> |
|**已删除**  <br/> |管理员已删除加载项。  <br/> |分配了加载项的用户和组无法再访问它。  <br/> |
   
如果没有人再使用加载项，请考虑将其删除。 例如，如果外接程序仅在一年的特定时间使用，则关闭外接程序可能有意义。

## <a name="delete-an-add-in"></a>删除加载项

还可以删除已部署的加载项。

1. In the admin center， go to the **设置**  >  **Integrated apps** page.

2. 选择已部署的加载项，然后选择“**配置**”选项卡。

3. 在"**配置"** 窗格中，转到"**高级设置**  >  **加载项"。**

4. 再次从列表中选择该加载项。

5. 选择“**删除加载项**”。 删除右下角的“加载项”按钮。

6. 验证你的选择，然后选择“**删除**”。

## <a name="edit-add-in-access"></a>编辑加载项访问

完成部署后，管理员还可以管理用户对加载项的访问权限。

1. In the admin center， go to the **设置**  >  **Integrated apps** page.

2. 选择已部署的加载项。

3. 单击“**谁可以访问**”下的“**编辑**”。

4. 保存更改。

## <a name="prevent-add-in-downloads-by-turning-off-the-office-store-across-all-clients-except-outlook"></a>通过在所有客户端上关闭 Office Store 来阻止外接程序下载 (除Outlook) 

> [!NOTE]
> Outlook加载项安装由不同的进程[管理](/exchange/clients-and-mobile-in-exchange-online/add-ins-for-outlook/specify-who-can-install-and-manage-add-ins)。

作为组织，你可能希望阻止从 Office 应用商店下载新的 Office 外接程序。 这可与集中部署结合使用，以确保仅向组织内部的用户部署经组织核准的外接程序。
  
**关闭加载项购置**
  
1. In the admin center， go to the **设置** \> [Org settings](https://go.microsoft.com/fwlink/p/?linkid=2053743) page.

2. 选择“**用户自有应用和服务**”。
    
3. 清除允许用户访问 Office 应用商店的选项。

    这将阻止所有用户从应用商店获取以下加载项。
      
    - 适用于以下版本的 Word、Excel 和 PowerPoint 2016 的加载项：
        
      - Windows
      - Mac
      - 办公室
        
        
    - 从 **AppSource 内开始购置**
        
    - Microsoft 365 中的加载项
        
    尝试访问应用商店的用户将看到以下消息："抱歉，Microsoft 365已配置为阻止单独获取 Office **Store 外接程序。**
  
以下版本Office支持关闭应用商店：
  
- Windows：16.0.9001 - 当前可用。
    
- Mac：16.10.18011401 - 当前可用。
    
- iOS：2.9.18010804 - 当前可用。
    
- Web - 当前可用。
    
这不会阻止管理员使用集中部署从应用商店分配Office加载项。

> [!NOTE] 
> 外接程序（如 Visio 数据可视化工具、必应地图 和 People Graph）仍将显示在功能区中，即使管理员已禁用应用商店。 若要删除这些链接，管理员必须通过组策略对象或 GPO (Store) 。
  
若要防止用户使用 Microsoft 帐户登录，可以将登录限制为仅使用组织帐户。 有关详细信息，请参阅[Identity， authentication， and authorization in Office 2016](/DeployOffice/security/identity-authentication-and-authorization-in-office)。  

> [!NOTE] 
> 阻止用户访问 Office 商店还会阻止他们从Office外接程序旁[加载以进行测试](/office/dev/add-ins/testing/create-a-network-shared-folder-catalog-for-task-pane-and-content-add-ins)。

## <a name="more-about-the-end-user-experience-with-add-ins"></a>有关外接程序的最终用户体验的更多内容

部署外接程序后，最终用户可以开始在 Office 应用程序中使用它。 外接程序将显示在外接程序支持的所有平台上。 请参阅[开始使用Office外接程序](https://support.microsoft.com/office/82e665c4-6700-4b56-a3f3-ef5441996862)。 
  
如果加载项支持加载项命令，则 Office 功能区上会显示命令。在以下示例中，显示" **引文** "加载项的" **搜索引文** "命令。 

![Office搜索引文功能区。](../../media/553b0c0a-65e9-4746-b3b0-8c1b81715a86.png)
  
如果部署的加载项不支持加载项命令，或者要查看所有部署的加载项，可以通过我的加载项 **查看**。 
  
### <a name="in-word-2016-excel-2016-or-powerpoint-2016"></a>在 Word 2016、Excel 2016 或 PowerPoint 2016 中

1. 选择 **" \> 插入我的外接程序"。** 
    
2. 选择 Office 加载项窗口中的" **由管理员管理** "选项卡。 
    
3. 双击您之前部署的外接程序， (" **引文**) 。

    !["加载项"Office"管理"选项卡。](../../media/fd36ba81-9882-40f0-9fce-74f991aa97d5.png)
  
### <a name="in-outlook"></a>在 Outlook 中

1. 在"**主页"** 功能区上，**选择"获取外接程序"。**

    !["应用商店"按钮Outlook。](../../media/getaddinsicon.png)
  
2. 在左侧导航中选择“**管理员托管**”。 

## <a name="related-content"></a>相关内容

[次要加载项和从加载项Microsoft Store](./minors-and-acquiring-addins-from-the-store.md)

