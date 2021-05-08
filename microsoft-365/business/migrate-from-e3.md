---
title: 从 E3 Microsoft 365 商业版Office 365迁移
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
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
description: 了解如何将企业从 Microsoft 365 商业高级版 E3 Office 365迁移。
ms.openlocfilehash: f08b054473fdd63ec2372e81c776a1b64f89fe9d
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244828"
---
# <a name="migrating-from-office-365-e3-to-microsoft-365-business-premium"></a>从 Office 365 E3 迁移到 Microsoft 365 商业高级版

Microsoft 365 商业高级版你的小型企业所需的一切，将一流的基于云的生产力应用与简单的设备管理和安全性相结合。 如果你当前拥有 Office 365 E3 订阅，但员工不超过 300 人，请考虑切换到 Microsoft 365 商业高级版 添加的安全功能。

迁移非常简单：首先切换许可证，并保留当前订阅中所有数据和用户信息。 迁移后，你需要设置在迁移过程中添加Microsoft 365 商业高级版。

## <a name="differences-between-office-365-e3-and-microsoft-365-business-premium"></a>E3 Office 365 E3 和 Microsoft 365 商业高级版

此表显示了 Microsoft 365 商业高级版 和 Office 365 E3 之间的差异。

| 功能    | 支持Microsoft 365 商业高级版    | 在 E3 Office 365支持 | 
|:-------|:-----|:-----|
| **本地**        | | | 
| Office应用<sup>1</sup>    | Microsoft 365 商业应用版    | 适用于企业的 Microsoft 365 应用 | 
| **云生产力应用**        | | | 
| Exchange Online 和 Outlook    | 每个邮箱 50 GB 存储限制和无限Exchange Online Archiving    | 每个邮箱 100 GB 存储限制和无限制Exchange Online Archiving | 
| Teams    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| OneDrive for Business    | 每个用户 1 TB 存储限制    | 无限制 | 
| Yammer、SharePoint Online、Planner、Stream    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| StaffHub    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png) | 
| MileIQ    | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | | 
| **威胁防护**        | | | 
| Defender for Office 365 计划 1 | ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | 不包含，但可添加到 | 
| **身份管理**        | | | 
| Azure AD) 帐户的混合 Azure Active Directory (自助服务密码重置、Azure AD 多重身份验证 (MFA) 、条件访问、本地标识的密码写回|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    |  | 
| **设备和应用管理**        | | |
| Microsoft Intune、Windows AutoPilot|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    |  |
| 共享计算机激活|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    | ![包含在 Office 365 E3 中](../media/check-mark.png)| 
| 从 Win 7/8.1 Windows 10 专业版许可证升级Pro权限|     ![包含在Microsoft 365 商业高级版](../media/check-mark.png)    || 
| **信息保护**        | | |
|Office 365 数据丢失防护|    ![包含在Microsoft 365 商业高级版](../media/check-mark.png)|![包含在 Office 365 E3 中](../media/check-mark.png)|
|Azure 信息保护计划 1，BitLocker实施|![包含在Microsoft 365 商业高级版](../media/check-mark.png)||
|Azure 信息保护计划 1，敏感度标签|![包含在Microsoft 365 商业高级版](../media/check-mark.png)||
|**客户端访问许可证 (CAL 权限)**|||
|EnterpriseCAL Suite (Exchange、SharePoint、Skype) ||![包含在 Office 365 E3 中](../media/check-mark.png)|

<sup>1</sup> Microsoft 365 商业高级版应用的 Office 版本不包括通过组策略、应用遥测、更新控件、电子表格比较和查询或商业智能进行批量激活。

## <a name="migration"></a>迁移

若要迁移订阅[，请参阅手动](../commerce/subscriptions/change-plans-manually.md)更改计划，了解只需迁移几个人员以迁移Microsoft 365 商业高级版。 还可以自动[升级所有人](../commerce/subscriptions/upgrade-to-different-plan.md)，或与合作伙伴合作将 E3 订阅和许可证移动到 Microsoft 365 商业高级版 订阅。
以下各节介绍您需要所做的更改（如果有）以及您可以在迁移后执行哪些操作。

### <a name="office-365-e3-subscription-configuration-and-data"></a>Office 365E3 订阅配置和数据
在迁移之前，无需对当前订阅或数据执行任何更改，其中包括：

- 订阅配置，例如 DNS 记录和域名。
- 用户和组帐户以及身份验证设置，如多重身份验证或条件访问策略。
- 生产力服务配置及其数据，例如Teams、Exchange Online邮箱、SharePoint Online 网站、OneDrive for Business文件夹OneNote笔记本。
- Office应用程序将自动缩放。 Office 365新式许可将每 72 小时检查一次用户的许可证分配，并将Office应用程序转换为与用户订阅匹配的版本。

### <a name="windows-10"></a>Windows 10

如果你Windows创意者更新Windows Pro，请[将其升级到Windows Pro创意者更新。](upgrade-to-windows-pro-creators-update.md)

### <a name="set-up-policies-to-protect-user-devices-and-files"></a>设置策略以保护用户设备和文件

> [!NOTE]
> 如果你设置 mdm Office 365和设备，这些设备将列在管理中心的"设备"Microsoft 365页面上。  你设置的任何策略都将显示在 [Intune](https://portal.azure.com/#blade/Microsoft_Intune_DeviceSettings/ExtensionLandingBlade/overview)门户的经典策略列表中。

向用户分配许可证Microsoft 365 商业高级版，可以开始保护用户的设备和文件。

如果你将组织中所有人升级到 Microsoft 365 商业高级版，你将在主页上看到安装向导，并可以按照安装向导步骤中的设置[Microsoft 365 商业高级版](set-up.md)来保护文件和移动设备。

还可以在"设备"页上完成以下步骤：
  
1. 在管理中心的左侧导航中，转到 **"设备策略** \> **"。**
    
2. 在"**设备策略"页上**，选择"添加 **"。**
    
3. 在 **"添加策略** "窗格中，为策略命名，然后从下拉列表中选择 **策略类型** 。 
    
     你可以设置应用程序策略来保护 Android 和 iPhone 设备上的文件以及 Windows 10，还可以为公司拥有的 Windows 10 设备设置设备配置策略。 有关详细信息，请参阅以下链接：
    
  - [设置 Android 或 iOS 设备的应用保护设置](app-protection-settings-for-android-and-ios.md)
    
  - [设置 Windows 10 设备的应用程序保护设置](protection-settings-for-windows-10-devices.md)
    
  - [为电脑设置Windows 10保护设置](protection-settings-for-windows-10-pcs.md)
  
4. 设置策略后，你和员工可以设置设备：
    
  - 请参阅[为Windows用户设置Microsoft 365 商业高级版，](set-up-windows-devices.md)了解设备Windows步骤。 
    
  - 有关[Android 手机和](set-up-mobile-devices.md)iPhone Microsoft 365 商业高级版，请参阅为用户设置移动设备。 
  
### <a name="mailbox-size"></a>邮箱大小

Microsoft 365 商业高级版计划 1 使用的存储空间上限为 50 GB Exchange Online。 迁移到 Microsoft 365 商业高级版 时，如果任何用户超过 50 GB 的邮箱存储，建议您为此用户分配 Exchange Online 计划 2 并删除 Exchange Online 计划 1，因为分配这两者不可行。


### <a name="threat-protection"></a>威胁防护

迁移到 Microsoft 365 商业高级版 后，你拥有 Defender for Office 365。 有关[概述，Office 365](../security/office-365-security/defender-for-office-365.md) Microsoft Defender for Office 365。 若要设置，[请参阅设置保险箱](https://support.microsoft.com/office/61492713-53c2-47da-a6e7-fa97479e97fa)链接、设置保险箱附件和[](https://support.microsoft.com/office/e7e68934-23dc-4b9c-b714-e82e27a8f8a5)在 Defender 中设置防钓鱼[Office 365。](https://support.microsoft.com/office/86c425e1-1686-430a-9151-f7176cce4f2c)

### <a name="sensitivity-labels"></a>敏感度标签

若要开始使用敏感度标签，请参阅敏感度标签概述[以及](../compliance/sensitivity-labels.md)[创建和管理敏感度标签](../business-video/create-sensitivity-labels.md)视频。
