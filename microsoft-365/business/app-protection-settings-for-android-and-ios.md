---
title: 设置 Android 或 iOS 设备的应用保护设置
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: Adm_O365
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何创建、 编辑或删除应用程序管理策略，和保护 Android 或 iOS 设备上的工作文件。
ms.openlocfilehash: ed03227496120369b94bf2396974eebfd7798678
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865969"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>设置 Android 或 iOS 设备的应用保护设置

## <a name="create-an-app-management-policy"></a>创建应用管理策略

1. 使用全局管理员凭据登录 [Microsoft 365 商业版](https://portal.office.com)。 
    
2. 在管理中心内的" **设备策略**"卡上，选择" **添加策略**"。
    
    ![Device policies card in the admin center.](media/27c12b61-d112-4348-b557-4f3e46204797.png)
  
3. 在" **添加策略**"窗格中，输入此策略的唯一名称。 
    
4. 在" **策略类型**"下，根据要创建的策略集，选择" **适用于 Android 的应用程序管理**"或" **适用于 iOS 的应用程序管理**"。 
    
5. 展开**保护工作文件时丢失或被盗设备**和**管理用户如何访问移动设备上的 Office 文件**\>配置方式的设置。默认情况下**管理用户如何访问移动设备上的 Office 文件**处于**关闭状态**，但建议您**将其打开**，并接受默认值。有关详细信息，请参阅[可用的设置](app-protection-settings-for-android-and-ios.md#bkmk_availablesettings)。 
    
    始终可使用" **重置默认设置**"链接返回到默认设置。 
    
    ![Screenshot of Create a policy with Application management for Android selected](media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. 接下来决定**用户会收到这些设置？** 如果您不希望使用默认的**所有用户**安全组，选择**更改**、 选择用户会收到这些设置的安全组\>**选择**。
    
7. 最后，选择" **完成**"以保存该策略，并将其分配到设备。 
    
## <a name="edit-an-app-management-policy"></a>编辑应用管理策略

1. 在**策略**卡片中，选择**编辑策略**。
    
2. 在" **编辑策略**"窗格中，选择要更改的策略 
    
3. 选择每个设置旁边的" **编辑**"来更改策略中的值。更改值后，它将自动保存到该策略 
    
4. 完成操作后，关闭" **编辑策略**"窗格。 
    
## <a name="delete-an-app-management-policy"></a>删除应用管理策略

1. 在" **策略**"卡中，选择" **删除策略**"。
    
2. 在**删除策略**窗格中，选择您要删除的策略\>**选择**，然后**确认**删除的策略或您选择的策略。 
    
## <a name="available-settings"></a>可用设置

以下表格提供了有关用于保护设备上工作文件的可用设置以及控制用户如何从其移动设备访问 Office 文件的设置的详细信息。
  
 有关详细信息，请参阅 [Microsoft 365 商业版中的保护功能如何映射到 Intune 设置](map-protection-features-to-intune-settings.md)。 
  
### <a name="settings-that-protect-work-files"></a>用于保护工作文件的设置

如果用户的设备丢失或被盗，以下设置可用于保护工作文件：
  
|||
|:-----|:-----|
|设置  <br/> |说明  <br/> |
|在以下天数后，从非活动的设备删除工作文件  <br/> |如果设备的未使用天数达到指定天数，则自动删除该设备上存储的任何工作文件。  <br/> |
|强制要求用户将所有的工作文件保存到 OneDrive for Business  <br/> |如果此设置为" **开**"，则工作文件的唯一可用保存位置是 OneDrive for Business。  <br/> |
|对工作文件进行加密  <br/> |将此设置保持为" **开**"，可通过加密保护工作文件。即使设备丢失或被盗，也没有人能够读取公司的数据。  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>用于控制用户如何在移动设备上访问 Office 文件的设置

以下设置可用于管理用户访问 Office 工作文件的方式：
  
|||
|:-----|:-----|
|设置  <br/> |说明  <br/> |
|需要 PIN 或指纹才能访问 Office 应用  <br/> |如果此设置在" **开**"位置，则用户必须在提供用户名和密码后再提供一种形式的身份验证，才能在其移动设备上使用 Office 应用。  <br/> |
|登录失败以下次数后重置 PIN  <br/> |若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。  <br/> |
|要求用户在 Office 应用空闲以下时间后重新登录  <br/> |此设置确定用户保持空闲状态多久后系统会提示再次登录。  <br/> |
|在已越狱或取得 root 权限的设备上拒绝对工作文件的访问  <br/> |一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **开** "，会阻止这些设备。  <br/> |
|允许用户从 Office 应用将内容复制到个人应用  <br/> |我们执行允许此默认情况下，但如果设置为**上**，用户无法复制信息中工作文件到个人文件。如果设置为**关闭**，用户将无法从工作帐户的信息复制到的个人的应用程序或个人帐户。<br/> |
   

  

