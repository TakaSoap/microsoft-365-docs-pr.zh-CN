---
title: 设置 Windows 10 设备的应用程序保护设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 02e74022-44af-414b-9d74-0ebf5c2197f0
description: 了解如何在 Windows 10 设备上创建应用管理策略并保护工作文件。
ms.openlocfilehash: 289c6a74f6ccb53f6a833612a7b4a5bcddd3ea56
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32278152"
---
# <a name="set-application-protection-settings-for-windows-10-devices"></a>设置 Windows 10 设备的应用程序保护设置

## <a name="create-an-app-management-policy-for-windows-10"></a>创建适用于 Windows 10 的应用管理

如果用户在个人 Windows 10 设备上执行工作任务，也可以在该类设备上保护你的数据。
  
1. 使用全局管理员凭据登录到[admin center](https://go.microsoft.com/fwlink/p/?linkid=837890) 。 选择" **管理**"图块，进入管理中心。 
    
2. 在左侧导航中, 选择 "**设备** \> **策略** \> " "**添加**"。

3. 在" **添加策略**"窗格中，输入此策略的唯一名称。 
    
4. 在" **策略类型**"下，选择" **适用于 Windows 10 的应用程序管理**"。
    
5. Under ** Device type **, choose either **Personal** or **Company Owned**.
    
6. 将自动打开" **加密工作文件**"。 
    
7. 如果不希望用户在其电脑上保存工作文件，请将" **阻止用户将公司数据复制到个人文件，并强制其将工作文件保存到 OneDrive for Business**"设置为" **开**"。 
    
8. Expand **Manage how users access Office files on devices** \> configure the settings how you would like. The **Manage how users access Office devices on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. 有关详细信息, 请参阅[可用设置](#available-settings)。 
    
    始终可使用" **重置默认设置**"链接返回到默认设置。 
    
9. 展开" **恢复 Windows 设备上的数据**"，建议将其设置为" **开**"。
    
    必须先创建一个数据恢复代理证书，才能浏览到该证书的位置。有关说明，请参阅[创建并验证加密文件系统 (EFS) 数据恢复代理 (DRA) 证书](https://go.microsoft.com/fwlink/p/?linkid=853700)。
    
    默认情况下，使用存储在设备上并与用户配置文件相关联的密钥对工作文件进行加密。只有该用户可以打开和解密文件。但是，如果设备丢失或用户被删除，文件可能停滞在加密状态。管理员可以使用数据恢复代理 (DRA) 证书对文件解密。
    
    ![Browse to Data Recovery Agent certificate.](media/7d7d664f-b72f-4293-a3e7-d0fa7371366c.png)
  
10. 若要添加其他域或 SharePoint Online 位置，确保所有列出应用中的文件均受到保护，请展开" **保护其他网络和云位置**"。如需为某字段输入多个项，请使用分号 (;) 进行分隔。 
    
    ![Expand Protect additional network and cloud locations, and enter domains or SharePoint Online sites you own.](media/7afaa0c7-ba53-456d-8c61-312c45e09625.png)
  
11. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
    
12. 最后，选择" **添加**"以保存该策略，并将其分配到设备。 
    
## <a name="available-settings"></a>可用设置

以下设置可用于管理用户访问 Office 工作文件的方式：
  
有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。
  
|**设置**|**说明**|
|:-----|:-----|
|需要 PIN 或指纹才能访问 Office 应用  <br/> |如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。  <br/> |
|登录失败以下次数后重置 PIN  <br/> |若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。  <br/> |
|要求用户在 Office 应用空闲以下时间后重新登录  <br/> |此设置确定用户保持空闲状态多久后系统会提示再次登录。  <br/> |
   

