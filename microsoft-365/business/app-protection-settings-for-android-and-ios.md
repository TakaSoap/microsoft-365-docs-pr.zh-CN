---
title: 设置 Android 或 iOS 设备的应用保护设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何创建、编辑或删除应用管理策略，以及如何保护 Android 或 iOS 设备上的工作文件。
ms.openlocfilehash: a829cfbcb3209313a53e0a1406f5252d3d5580d8
ms.sourcegitcommit: bd52f7b662887f552f90c46f69d6a2a42fb66914
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/17/2019
ms.locfileid: "37574730"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>设置 Android 或 iOS 设备的应用保护设置

![指向的标题https://aka.ms/aboutM365preview。](media/m365admincenterchanging.png)

## <a name="create-an-app-management-policy"></a>创建应用管理策略

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。 
    
2. 在左侧导航中，选择 "**设备** \> **策略** \> " "**添加**"。
  
3. 在" **添加策略**"窗格中，输入此策略的唯一名称。 
    
4. 在" **策略类型**"下，根据要创建的策略集，选择" **适用于 Android 的应用程序管理**"或" **适用于 iOS 的应用程序管理**"。 
    
5. Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices** \> configure the settings how you would like. The **Manage how users access Office files on mobile devices** is **Off** by default, but it is recommended that you turn it **On** and accept the default values. 有关详细信息，请参阅[可用设置](#available-settings)。 
    
    始终可使用" **重置默认设置**"链接返回到默认设置。 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Next decide **Who will get these settings?** If you don't want to use the default **All Users** security group, choose **Change**, choose the security groups who will get these settings \> **Select**.
    
7. 最后，选择" **完成**"以保存该策略，并将其分配到设备。 
    
## <a name="edit-an-app-management-policy"></a>编辑应用管理策略

1. 在**策略**卡上，选择 "**编辑策略**"。
    
2. 在" **编辑策略**"窗格中，选择要更改的策略 
    
3. 选择每个设置旁边的" **编辑**"来更改策略中的值。更改值后，它将自动保存到该策略 
    
4. 完成操作后，关闭" **编辑策略**"窗格。 
    
## <a name="delete-an-app-management-policy"></a>删除应用管理策略

1. 在 "**策略**" 页上，选择策略，然后单击 "**删除**"。
    
2. 在 "**删除策略**" 窗格中，选择 "**确认**" 以删除所选的策略或策略。 
    
## <a name="available-settings"></a>可用设置

以下表格提供了有关用于保护设备上工作文件的可用设置以及控制用户如何从其移动设备访问 Office 文件的设置的详细信息。
  
 有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。 
  
### <a name="settings-that-protect-work-files"></a>用于保护工作文件的设置

如果用户的设备丢失或被盗，以下设置可用于保护工作文件：
  
|||
|:-----|:-----|
|Setting  <br/> |说明  <br/> |
|在以下天数后，从非活动的设备删除工作文件  <br/> |如果设备的未使用天数达到指定天数，则自动删除该设备上存储的任何工作文件。  <br/> |
|强制要求用户将所有的工作文件保存到 OneDrive for Business  <br/> |如果此设置为" **打开**"，则工作文件的唯一可用保存位置是 OneDrive for Business。  <br/> |
|对工作文件进行加密  <br/> |将此设置保持为" **打开**"，可通过加密保护工作文件。即使设备丢失或被盗，也没有人能够读取公司的数据。  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>用于控制用户如何在移动设备上访问 Office 文件的设置

以下设置可用于管理用户访问 Office 工作文件的方式：
  
|||
|:-----|:-----|
|Setting  <br/> |说明  <br/> |
|需要 PIN 或指纹才能访问 Office 应用  <br/> |如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。  <br/> |
|登录失败以下次数后重置 PIN  <br/> |若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。  <br/> |
|要求用户在 Office 应用空闲以下时间后重新登录  <br/> |此设置确定用户保持空闲状态多久后系统会提示再次登录。  <br/> |
|在已越狱或取得 root 权限的设备上拒绝对工作文件的访问  <br/> |一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **打开**"，会阻止这些设备。  <br/> |
|允许用户从 Office 应用将内容复制到个人应用  <br/> |默认允许此设置，但如果设置为" **开**"，用户可将工作文件中的信息复制到个人文件。 如果设置为" **关** "，用户无法将工作帐户中的信息复制到个人应用或个人帐户。  <br/> |
   

  

