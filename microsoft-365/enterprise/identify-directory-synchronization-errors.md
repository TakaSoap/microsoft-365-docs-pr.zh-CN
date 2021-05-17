---
title: 查看目录中的目录同步Microsoft 365
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOE150
- MED150
- MBS150
- GPA150
ms.assetid: b4fc07a5-97ea-4ca6-9692-108acab74067
description: 了解如何在管理中心中查看目录同步错误Microsoft 365修复。
ms.openlocfilehash: 76717fc158aa0cee47f784919f19a295378bbd5b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50907500"
---
# <a name="view-directory-synchronization-errors-in-microsoft-365"></a>查看目录中的目录同步Microsoft 365

可以在管理中心内查看Microsoft 365同步错误。 只显示 User 对象错误。 若要查看 PowerShell 错误，请参阅 [使用 DirSyncProvisioningErrors](/azure/active-directory/hybrid/how-to-connect-syncservice-duplicate-attribute-resiliency)标识对象。

## <a name="view-directory-synchronization-errors-in-the-microsoft-365-admin-center"></a>在管理中心内查看Microsoft 365同步错误

若要查看管理中心内Microsoft 365错误：
  
1. 使用全局管理员[Microsoft 365](https://admin.microsoft.com)登录管理中心。 
    
2. 在 **主页** 上，你将看到用户 **管理** 卡。 
    
    ![管理中心的用户Microsoft 365卡片](../media/060006e9-de61-49d5-8979-e77cda198e71.png)
  
3. On the card， choose **Sync errors** under **Azure AD 连接** to see the errors on the **Directory sync errors** page.   
    
    ![目录同步错误页面的示例](../media/882094a3-80d3-4aae-b90b-78b27047974c.png)

4. 选择任何错误以显示详细信息窗格，其中包含有关错误的信息以及如何修复错误的提示。

   ![目录同步错误的详细信息示例](../media/a6e302d4-6be7-4e3a-b4b5-81c5a2c02952.png)
  
查看后，请参阅[修复目录同步Microsoft 365](fix-problems-with-directory-synchronization.md)修复任何已识别的问题。