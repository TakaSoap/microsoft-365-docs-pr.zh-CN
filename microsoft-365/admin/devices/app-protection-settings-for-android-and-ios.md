---
title: 设置 Android 或 iOS 设备的应用保护设置
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Adm_O365
- M365-subscription-management
- M365-identity-device-management
- Adm_TOC
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6f2b80b4-81c3-4714-a7bc-ae69313e8a33
description: 了解如何创建、编辑或删除应用管理策略，并保护 Android 或 iOS 设备上的工作文件。
ms.openlocfilehash: 6849b24f691f7b567cc55dce2dda21f2a7e93f22
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63313981"
---
# <a name="set-app-protection-settings-for-android-or-ios-devices"></a>设置 Android 或 iOS 设备的应用保护设置

本文适用于Microsoft 365 商业高级版。

> [!NOTE]
> 从 2022 年 3 月 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 此产品/服务为设备提供其他安全功能。 [详细了解 Defender for Business](../../security/defender-business/mdb-overview.md)。

## <a name="watch-secure-office-apps-on-ios"></a>观看：Office iOS 上的应用安全

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE1FLvZ?autoplay=false]

可以设置要求移动用户输入 PIN 或指纹才能登录的用户访问策略，并加密存储在其设备上的工作文件。

1. 登录到 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">Microsoft 365 管理中心</a>。
1. 在 **"策略"** 下， **选择"添加策略"**。
1. 在"**添加策略"** 窗格中，在"策略名称"下输入名称，然后选择"策略类型"下想要 **的策略类型**。
1. 打开 **"管理用户如何在Office** 访问文件"，然后确保以下三个设置已打开：
    - **需要 PIN 或指纹才能访问 Office 应用**
    - **在设备丢失或被盗时保护工作文件**
    - **加密工作文件**

1. 在 **"这些应用中的文件将受到保护"下**，Office你想要在移动设备上保护的应用。
1. 在“**谁将收到这些设置?**”下方，将默认选中所有用户，但可以选择“**更改**”以选择所创建的任何安全组。
1. 选择“**添加**”，策略即创建完毕。
1. 在“**添加策略**”页面上，选择“**关闭**”。
1. 在管理中心主页上，选择“**策略**”并在“**策略**”页面上查看策略，确认已添加新策略。

## <a name="create-an-app-management-policy"></a>创建应用管理策略

1. 转到位于 <a href="https://go.microsoft.com/fwlink/p/?linkid=837890" target="_blank">https://admin.microsoft.com</a> 的管理中心。 
    
2. 在左侧导航中，选择 **"设备策略"** \> **"添加** \> **"**。
  
3. 在" **添加策略**"窗格中，输入此策略的唯一名称。 
    
4. 在 **"策略类型**"下，选择" **Android** 应用程序管理"或" **适用于 iOS** 的应用程序管理"，具体取决于要创建的策略集。 
    
5. Expand **Protect work files when devices are lost or stolen** and **Manage how users access Office files on mobile devices**. 配置您喜欢的设置。 **管理用户在移动设备上Office** 文件方式默认为"关闭"，但我们建议你将其打开并接受默认值。 有关详细信息，请参阅可用 [设置](#available-settings)。 
    
    始终可使用" **重置默认设置**"链接返回到默认设置。 
    
    ![Screenshot of Create a policy with Application management for Android selected.](../../media/eabbe06d-ac0a-4f3a-8630-68c808b1e662.png)
  
6. Next decide **Who will get these settings?** 如果您不想使用默认的"所有用户"安全组，请选择"更改"，选择获取这些设置的安全组"选择 **"**。\>
    
7. 最后，选择" **完成**"以保存该策略，并将其分配到设备。 
    
## <a name="edit-an-app-management-policy"></a>编辑应用管理策略

1. 在" **策略"** 卡上，选择 **"编辑策略"**。
    
2. 在" **编辑策略**"窗格中，选择要更改的策略 
    
3. 选择每个设置旁边的" **编辑**"来更改策略中的值。 更改值时，它会自动保存在策略中。
    
4. 完成后，关闭"编辑 **策略"** 窗格。 
    
## <a name="delete-an-app-management-policy"></a>删除应用管理策略

1. 在" **策略"** 页上，选择一个策略，然后选择" **删除"**。
    
2. 在" **删除策略"** 窗格中，选择" **确认** "以删除你选择的策略。 
    
## <a name="available-settings"></a>可用设置

下表详细介绍了可用于保护设备上工作文件的设置，以及控制用户如何从Office访问工作文件的设置。
  
 有关详细信息，请参阅如何将保护[功能Microsoft 365 商业高级版映射到 Intune 设置](map-protection-features-to-intune-settings.md)。 
  
### <a name="settings-that-protect-work-files"></a>用户保护工作文件的设置

如果用户的设备丢失或被盗，以下设置可用于保护工作文件：


|Setting  <br/> |说明  <br/> |
|:-----|:-----|
|在以下天数后，从非活动的设备删除工作文件  <br/> |如果设备不用于你在此处指定的天数，则将自动删除设备上存储的任何工作文件。  <br/> |
|强制要求用户将所有的工作文件保存到 OneDrive for Business  <br/> |如果此设置为 **"打开"**，则工作文件的唯一可用保存位置OneDrive for Business。  <br/> |
|对工作文件进行加密  <br/> |将此设置保持为" **打开**"，可通过加密保护工作文件。 即使设备丢失或被盗，也没有人可以读取你的公司数据。  <br/> |
   
### <a name="settings-that-control-how-users-access-office-files-on-mobile-devices"></a>用于控制用户如何在移动设备上访问 Office 文件的设置

以下设置可用于管理用户访问 Office 工作文件的方式：


|Setting  <br/> |说明  <br/> |
|:-----|:-----|
|需要 PIN 或指纹才能访问 Office 应用  <br/> |如果此设置为 **"打开**"，则除了用户名和密码之外，用户还必须提供另一种形式的身份验证，然后才能在移动设备上Office应用。<br/> |
|登录失败以下次数后重置 PIN  <br/> |若要防止未经授权的用户随机猜测 PIN，PIN 将在达到指定的错误输入次数后重置。  <br/> |
|要求用户在 Office 应用空闲以下时间后重新登录  <br/> |此设置确定用户在系统提示重新登录之前可以处于空闲状态的时间。  <br/> |
|在已越狱或取得 root 权限的设备上拒绝对工作文件的访问  <br/> |一些聪明的用户的设备可能已越狱或取得 root 权限。这意味着用户可以修改操作系统，从而导致设备更易受到恶意软件的攻击。如果此设置为" **打开**"，会阻止这些设备。  <br/> |
|不允许用户将内容从应用Office个人应用中  <br/> |默认允许此设置，但如果设置为" **开**"，用户可将工作文件中的信息复制到个人文件。 如果设置为" **关** "，用户无法将工作帐户中的信息复制到个人应用或个人帐户。  <br/> |

## <a name="see-also"></a>另请参阅

[保护业务Microsoft 365的十大方法](../security-and-compliance/secure-your-business-data.md)