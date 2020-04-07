---
title: 从 Office 365 E3 迁移到 Microsoft 365 业务
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
search.appverid:
- BCS160
- MET150
description: 了解如何通过 Office 365 E3 将企业移动到 Microsoft 365 商业版。
ms.openlocfilehash: cff6166529df2e56ba948a9bd3ea4594fb295b08
ms.sourcegitcommit: e525bcf073a61e1350484719a0c3ceb6ff0d8db1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2020
ms.locfileid: "43153528"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business"></a>从 Office 365 E3 迁移到 Microsoft 365 业务 

Microsoft 365 业务具有你的小型企业所需的一切，从而将同类最佳的基于云的工作效率应用与简单的设备管理和安全性结合在一起。 如果你当前有一个 Office 365 E3 订阅，但没有超过300个员工，请考虑切换到 Microsoft 365 Business 以添加安全功能。

迁移非常简单：首先切换许可证，并保留当前订阅中的所有数据和用户信息。 迁移完成后，你将需要设置在 Microsoft 365 业务中添加的功能。

## <a name="differences-between-office-365-e3-and-microsoft-365-business"></a>Office 365 E3 与 Microsoft 365 商业版之间的区别

此表显示了 Microsoft 365 商业版和 Office 365 E3 之间的差异。

| 功能    | Microsoft 365 商业版中的支持    | Office 365 E3 中的支持 | 
|:-------|:-----|:-----|
| **本地**        | | | 
| Office 应用程序<sup>1</sup>    | Office 365 商业版    | Office 365 专业增强订阅版 | 
| **云生产力应用程序**        | | | 
| Exchange Online 和 Outlook    | 每个邮箱 50 GB 存储限制和不受限制的 Exchange Online 存档    | 每个邮箱 100 GB 存储限制和不受限制的 Exchange Online 存档 | 
| Teams    | ![包含在 Microsoft 365 商业版中](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| OneDrive for Business    | 每个用户 1 TB 存储限制    | 无限制 | 
| Yammer、SharePoint Online、Planner、Stream    | ![包含在 Microsoft 365 商业版中](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| StaffHub    | ![包含在 Microsoft 365 商业版中](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| Outlook 客户管理器，MileIQ    | ![包含在 Microsoft 365 商业版中](../media/check-mark.png)    | | 
| **威胁防护**        | | | 
| Office 365 高级威胁防护（ATP）计划1 | ![包含在 Microsoft 365 商业版中](../media/check-mark.png)    | 不包括在内，但可以添加到 | 
| **身份管理**        | | | 
| 混合 Azure Active Directory （Azure AD）帐户的自助密码重置、Azure 多重身份验证、条件访问、本地标识的密码写回|     ![包含在 Microsoft 365 商业版中](../media/check-mark.png)    |  | 
| **设备和应用程序管理**        | | |
| Microsoft Intune、Windows AutoPilot|     ![包含在 Microsoft 365 商业版中](../media/check-mark.png)    |  |
| 共享计算机激活|     ![包含在 Microsoft 365 商业版中](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png)| 
| 从 Win 7/8.1 Pro 许可证升级到 Windows 10 专业版的权限|     ![包含在 Microsoft 365 商业版中](../media/check-mark.png)    || 
| **信息保护**        | | |
|Office 365 数据丢失防护|    ![包含在 Microsoft 365 商业版中](../media/check-mark.png)|![包含在 Office 365 E3 中](../media/check-mark.png)|
|Azure 信息保护计划1，Bitlocker 强制|![包含在 Microsoft 365 商业版中](../media/check-mark.png)||
|Azure 信息保护计划1，敏感度标签|![包含在 Microsoft 365 商业版中](../media/check-mark.png)||
|**客户端访问许可证（CAL 权限）**|||
|企业 CAL 套件（Exchange、SharePoint、Skype）||![包含在 Office 365 E3 中](../media/check-mark.png)|

<sup>1</sup> Microsoft 365 商业版的 Office 应用程序不包括通过组策略、应用遥测、更新控件、电子表格比较和查询或商业智能等批量激活。

## <a name="migration"></a>迁移

若要迁移你的订阅，请参阅[手动更改计划](../commerce/subscriptions/change-plans-manually.md)以了解有关如何仅将少数用户移动到 Microsoft 365 业务的说明。 您还可以[自动升级每个人](../commerce/subscriptions/upgrade-to-different-plan.md)，或与合作伙伴合作，将您的 E3 订阅和许可证移到 Microsoft 365 业务订阅。
以下各节介绍了需要进行的更改（如果有），以及迁移后可以执行的操作。

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365 E3 订阅配置和数据
在迁移之前，无需对当前订阅或数据进行任何更改，其中包括：

- 订阅配置，如 DNS 记录和域名。
- 用户和组帐户以及身份验证设置，例如多重因素身份验证或条件访问策略。
- 生产率服务配置及其数据，如团队、Exchange Online 邮箱、SharePoint Online 网站、OneDrive for Business 文件夹和 OneNote 笔记本。

### <a name="windows-10"></a>Windows 10

如果 windows Pro Creator 更新中还没有你的 Windows，请[将其升级到 Windows Pro 创意者更新](upgrade-to-windows-pro-creators-update.md)。

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>设置策略以保护用户设备和文件

> [!NOTE]
> 如果设置了 Office 365 MDM 策略和设备，这些设备将在 Microsoft 365 管理中心的 "**设备**" 页上列出。 你设置的任何策略都将显示在[Intune 门户](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)中的经典策略列表中。

为 Microsoft 365 商业版分配许可证之后，可以开始保护用户的设备和文件。

如果将组织中的每个人升级到 Microsoft 365 企业版，您将在主页上看到 "安装向导"，并且可以按照[安装向导中设置的 Microsoft 365 业务中](set-up.md)的步骤操作，以保护文件和移动设备。

您还可以在 "设备" 页上完成以下步骤：
  
1. 在管理中心的左侧导航中，转到 "**设备** \> **策略**"。
    
2. 在 "**设备策略**" 页上，选择 "**添加**"。
    
3. 在 "**添加策略**" 窗格中，为策略指定一个名称，然后从下拉类型中选择一个**策略类型**。 
    
     您可以设置应用程序策略来保护 Android 和 iPhone 设备上的文件以及 Windows 10，还可以为公司拥有的 Windows 10 设备设置设备配置策略。 有关详细信息，请参阅以下链接：
    
  - [设置 Android 或 iOS 设备的应用保护设置](app-protection-settings-for-android-and-ios.md)
    
  - [设置 Windows 10 设备的应用程序保护设置](protection-settings-for-windows-10-devices.md)
    
  - [设置 Windows 10 电脑的设备保护设置](protection-settings-for-windows-10-pcs.md)
  
4. 设置策略后，你和你的员工可以设置设备：
    
  - 有关 Windows 设备的步骤，请参阅为[Microsoft 365 商业版用户设置 Windows 设备](set-up-windows-devices.md)。 
    
  - 有关 Android 手机和 Iphone 的步骤，请参阅为[Microsoft 365 商业版用户设置移动设备](set-up-mobile-devices.md)。 

### <a name="threat-protection"></a>威胁防护

迁移到 Microsoft 365 商业版后，你有 Office 365 ATP。 有关概述，请参阅[Office 365 ATP](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp) 。 若要设置，请参阅[设置 atp 安全链接](https://support.office.com/article/61492713-53c2-47da-a6e7-fa97479e97fa)、[设置 atp 安全附件](https://support.office.com/article/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)以及[设置 atp 反网络钓鱼](https://support.office.com/article/86c425e1-1686-430a-9151-f7176cce4f2c)。

### <a name="sensitivity-labels"></a>敏感度标签

若要开始使用敏感度标签，请参阅[敏感度标签概述](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels)和[创建和管理敏感度标签](https://support.office.com/article/2fb96b54-7dd2-4f0c-ac8d-170790d4b8b9)视频。
