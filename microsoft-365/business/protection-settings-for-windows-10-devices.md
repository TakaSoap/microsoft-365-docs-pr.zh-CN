---
title: 编辑或设置 Windows 10 设备的应用程序保护设置
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- Win10AppPolicy
- O365E_Win10AppPolicy
- BCS365_Win10AppPolicy
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何在用户的个人 Windows 10 设备上创建或编辑应用管理策略和保护工作文件。
ms.openlocfilehash: 64c6aa620171a373cd7564c7de3abbf4a4546c4e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912814"
---
# <a name="set-or-edit-application-protection-settings-for-windows-10-devices"></a>设置或编辑 Windows 10 设备的应用程序保护设置

本文适用于 Microsoft 365 商业高级版。

## <a name="edit-an-app-management-policy-for-windows-10"></a>编辑 Windows 10 的应用管理策略

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。     
2. 在左侧导航中，选择 **"设备策略** \> **"。**
1. 选择现有的 Windows 应用策略，然后选择"编辑 **"。**
1. 选择 **要** 更改的设置旁边的"编辑"，然后选择"保存 **"。**

## <a name="create-an-app-management-policy-for-windows-10"></a>创建适用于 Windows 10 的应用管理

如果用户在个人 Windows 10 设备上执行工作任务，也可以在该类设备上保护你的数据。
  
1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。 
2. 在左侧导航上，选择 **"设备策略** \>  \> **""添加"。**
3. 在" **添加策略**"窗格中，输入此策略的唯一名称。 
4. 在" **策略类型**"下，选择" **适用于 Windows 10 的应用程序管理**"。
5. 在 **"设备类型**"下，选择"**个人"** 或 **"公司拥有"。**
6. 将自动打开" **加密工作文件**"。 
7. 如果不希望用户在其电脑上保存工作文件，请将" **阻止用户将公司数据复制到个人文件，并强制其将工作文件保存到 OneDrive for Business**"设置为" **开**"。 
9. 展开 **"恢复 Windows 设备上的数据"。** 建议将其 **打开。**
    必须先创建一个数据恢复代理证书，才能浏览到该证书的位置。 有关说明，请参阅 [Create and verify an Encrypting File System (EFS) Data Recovery Agent (DRA) certificate](/windows/security/information-protection/windows-information-protection/create-and-verify-an-efs-dra-certificate)。
    
    默认情况下，使用存储在设备上并与用户配置文件相关联的密钥对工作文件进行加密。 只有该用户可以打开和解密文件。 但是，如果设备丢失或用户被删除，文件可能停滞在加密状态。 管理员可以使用数据恢复代理 (DRA) 解密文件。
    
    ![Browse to Data Recovery Agent certificate.](../media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. 如果要 **添加其他域** 或 SharePoint Online 位置，请展开"保护其他网络和云位置"，以确保所有列出的应用中的文件都受到保护。 如需为某字段输入多个项，请使用分号 (;) 进行分隔。
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](../media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
12. 最后，选择" **添加**"以保存该策略，并将其分配到设备。