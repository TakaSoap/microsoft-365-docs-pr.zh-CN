---
title: 从 Office 365 E3 迁移到 Microsoft 365 商业版
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
- Adm_O365
- M365-subscription-management
ms.custom:
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
description: 了解如何从 Office 365 E3 将业务移动到 Microsoft 365 商业高级版。
ms.openlocfilehash: f655037891bf8ec42e7b927256025c89c9354e98
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50912934"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>从 Office 365 E3 迁移到 Microsoft 365 商业高级版 

Microsoft 365 商业高级版具有小型企业所需的一切，将一流的基于云的生产力应用与简单的设备管理和安全性相结合。 如果当前拥有 Office 365 E3 订阅，但员工不超过 300 人，请考虑切换到 Microsoft 365 商业高级版，以添加安全功能。

迁移非常简单：首先切换许可证，并保留当前订阅中所有数据和用户信息。 迁移后，你需要设置在 Microsoft 365 商业高级版中添加的功能。

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>Office 365 E3 和 Microsoft 365 商业高级版之间的差异

此表显示了 Microsoft 365 商业高级版和 Office 365 E3 之间的差异。

| 功能    | Microsoft 365 商业高级版中的支持    | Office 365 E3 中的支持 | 
|:-------|:-----|:-----|
| **本地**        | | | 
| Office 应用<sup>1</sup>    | Microsoft 365 商业应用版    | 适用于企业的 Microsoft 365 应用 | 
| **云生产力应用**        | | | 
| Exchange Online 和 Outlook    | 每个邮箱 50 GB 存储限制和无限Exchange Online Archiving    | 每个邮箱 100 GB 存储限制和无限制Exchange Online Archiving | 
| Teams    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Office 365 E3 一起提供](../media/check-mark.png) | 
| OneDrive for Business    | 每个用户 1 TB 存储限制    | 无限制 | 
| Yammer、SharePoint Online、Planner、Stream    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Office 365 E3 一起提供](../media/check-mark.png) | 
| StaffHub    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Office 365 E3 一起提供](../media/check-mark.png) | 
| Outlook Customer Manager，MileIQ    | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | | 
| **威胁防护**        | | | 
| Defender for Office 365 计划 1 | ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | 不包含，但可添加到 | 
| **身份管理**        | | | 
| 混合 Azure Active Directory (Azure AD) 帐户、Azure AD 多重身份验证 (MFA) 、条件访问、本地标识的密码写回|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    |  | 
| **设备和应用管理**        | | |
| Microsoft Intune、Windows AutoPilot|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    |  |
| 共享计算机激活|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    | ![随 Office 365 E3 一起提供](../media/check-mark.png)| 
| 从 Win 7/8.1 专业版许可证升级到 Windows 10 专业版权限|     ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)    || 
| **信息保护**        | | |
|Office 365 数据丢失防护|    ![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)|![随 Office 365 E3 一起提供](../media/check-mark.png)|
|Azure 信息保护计划 1，Bitlocker 强制|![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)||
|Azure 信息保护计划 1，敏感度标签|![包含在 Microsoft 365 商业高级版中](../media/check-mark.png)||
|**客户端访问许可证 (CAL 权限)**|||
|Enterprise CAL Suite (Exchange、SharePoint、Skype) ||![随 Office 365 E3 一起提供](../media/check-mark.png)|

<sup>1</sup> Microsoft 365 商业高级版 Office 应用不包括通过组策略、应用遥测、更新控件、电子表格比较和查询或商业智能批量激活。

## <a name="migration"></a>迁移

若要迁移订阅，请参阅手动[](../commerce/subscriptions/change-plans-manually.md)更改计划，了解将几个用户迁移到 Microsoft 365 商业高级版的说明。 还可以自动 [升级每个人](../commerce/subscriptions/upgrade-to-different-plan.md)，或与合作伙伴合作将 E3 订阅和许可证移动到 Microsoft 365 商业高级版订阅。
以下各节介绍您需要所做的更改（如果有）以及您可以在迁移后执行哪些操作。

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 订阅配置和数据
在迁移之前，无需对当前订阅或数据执行任何更改，其中包括：

- 订阅配置，例如 DNS 记录和域名。
- 用户和组帐户以及身份验证设置，如多重身份验证或条件访问策略。
- 生产力服务配置及其数据，例如 Teams、Exchange Online 邮箱、SharePoint Online 网站、OneDrive for Business 文件夹和 OneNote 笔记本。
- Office 应用程序将自动缩放。 Office 365 新式许可将每 72 小时检查一次用户的许可证分配，并将 Office 应用程序转换为与用户订阅匹配的版本。

### <a name="windows-10"></a>Windows 10

如果你的 Windows 还没有使用 Windows 专业版创意者更新， [请将其升级到 Windows 专业版创意者更新](upgrade-to-windows-pro-creators-update.md)。

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>设置策略以保护用户设备和文件

> [!NOTE]
> 如果设置 Office 365 MDM 策略和设备，这些设备将列在 Microsoft 365 管理中心的"设备"页面上。  你设置的任何策略都将显示在 [Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)门户的经典策略列表中。

向 Microsoft 365 商业高级版分配许可证后，可以开始保护用户的设备和文件。

如果你将组织中的每个人升级到 Microsoft 365 商业高级版，你将在主页上看到安装向导，并且可以按照设置向导步骤中的设置 [Microsoft 365 商业](set-up.md) 高级版来保护文件和移动设备。

还可以在"设备"页上完成以下步骤：
  
1. 在管理中心的左侧导航中，转到 **"设备策略** \> **"。**
    
2. 在"**设备策略"页上**，选择"添加 **"。**
    
3. 在 **"添加策略** "窗格中，为策略命名，然后从下拉列表中选择 **策略类型** 。 
    
     你可以设置用于保护 Android 和 iPhone 设备以及 Windows 10 上的文件的应用程序策略，还可以为公司拥有的 Windows 10 设备设置设备配置策略。 有关详细信息，请参阅以下链接：
    
  - [设置 Android 或 iOS 设备的应用保护设置](app-protection-settings-for-android-and-ios.md)
    
  - [设置 Windows 10 设备的应用程序保护设置](protection-settings-for-windows-10-devices.md)
    
  - [设置 Windows 10 电脑的设备保护设置](protection-settings-for-windows-10-pcs.md)
  
4. 设置策略后，你和员工可以设置设备：
    
  - 有关 Windows 设备的步骤，请参阅为 [Microsoft 365 商业高级版](set-up-windows-devices.md) 用户设置 Windows 设备。 
    
  - 有关 Android 手机和 iPhone 的步骤，请参阅为 [Microsoft 365 商业](set-up-mobile-devices.md) 高级版用户设置移动设备。 
  
### <a name="mailbox-size"></a>邮箱大小

Microsoft 365 商业高级版具有 50 GB 存储空间限制，因为它使用 Exchange Online 计划 1。 迁移到 Microsoft 365 商业高级版时，如果任何用户超过 50 GB 的邮箱存储空间，建议为该用户分配 Exchange Online 计划 2 并删除 Exchange Online 计划 1，因为分配这两者不可行。


### <a name="threat-protection"></a>威胁防护

迁移到 Microsoft 365 商业高级版后，你拥有适用于 Office 365 的 Defender。 有关[概述，请参阅 Microsoft Defender for Office 365。](../security/office-365-security/office-365-atp.md) 若要设置[，请参阅在](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)Defender for [](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5) [Office 365](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)中设置安全链接、设置安全附件和设置防钓鱼。

### <a name="sensitivity-labels"></a>敏感度标签

若要开始使用敏感度标签，请参阅敏感度标签概述[以及](../compliance/sensitivity-labels.md)[创建和管理敏感度标签](https://support.microsoft.com/office/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)视频。