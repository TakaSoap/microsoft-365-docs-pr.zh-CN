---
title: 设置概述
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
f1_keywords:
- O365E_M365SetupBanner
- BCS365_M365SetupBanner
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Adm_O365
- M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: 了解 Microsoft 365 商业高级版的安装步骤、订阅、添加域和用户、设置安全策略等。
ms.openlocfilehash: fa9c02fa9546437c83b9cc6c1f1e6e0d723ec868
ms.sourcegitcommit: 555d756c69ac9031d1fb928f2e1f9750beede066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/29/2020
ms.locfileid: "47306461"
---
# <a name="overview-of-setup"></a>设置概述

观看有关 Microsoft 365 商业高级版安装程序的简短视频。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

大部分安装步骤可以在安装向导中完成，但也会列出其他选项。

## <a name="step-1-add-your-domain-and-users"></a>步骤1：添加您的域和用户

   - **[添加你的域](set-up.md#add-your-domain-to-personalize-sign-in)** (如果你在 [注册](sign-up.md)过程中购买了你的域，则此步骤已完成。 ) 

   - **添加用户**。 可以通过以下三种方式之一添加用户：
        - 在 [向导](set-up.md#add-users-in-the-wizard)中。
        - 如果你有本地 Active directory，请使用目录同步来 [使用 AZURE AD Connect 添加用户](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) 。
        - 您还可以在随后的管理中心 [添加用户](add-users-m365b.md) 。
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>步骤2：设置安全策略和配置设备 

  - 使用 [安装向导](set-up.md#protect-your-organization) 配置设备策略。 
  - 您还可以在 [管理员中心](view-policies-and-devices.md) 和 [Intune 门户](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)中添加更多或编辑它们。
  - 安装向导还会设置基本威胁防护和数据丢失防护设置。
  
  除了安装向导中的安全设置之外，还可以通过添加以下设置来提高安全性：

- **电子邮件恶意软件保护**
- **ATP 反网络钓鱼**
- **Exchange Online Archiving**
- **Azure 信息保护 (Plan1**) 

若要开始，请参阅 [增加威胁防护](increase-threat-protection.md) 和 [设置合规性功能](set-up-compliance.md)。

请参阅 [保护 Microsoft 365 商业高级版](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data) 的十大方法，了解最佳安全实践的路线图。

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>步骤3：设置和管理 Windows 10 设备

运行设置向导后，您需要 proctect 组织中的所有 Windwos 10 台计算机。
  
- Windows 10 专业版是 Microsoft 365 商业高级版的 [先决条件](pre-requisites-for-data-protection.md) ，但如果你有 Windows 7 Pro、Windows 8 专业版或 Windows 8.1 pro，你的订阅让你能够 [升级到 Windows 10 专业](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)版。
- 按照 [安全 windows 10 电脑](secure-win-10-pcs.md) 中的步骤设置 windows 10 设备的策略。

将 Windows 10 设备加入 Azure AD 时，您为 Windows 10 计算机设置的策略将应用于。 有关详细信息，请参阅 [设置 Windows 设备 For Microsoft 365 users](set-up-windows-devices.md)。

## <a name="step-4-install-microsoft-365-apps-for-business"></a>步骤4：安装 Microsoft 365 的商业应用程序
- 您可以使用 [安装向导](set-up.md#deploy-office-365-client-apps)在 Windows 设备中自动安装 Office。
- 允许用户安装适用于 Windows 和设备的 [Office 应用程序](https://docs.microsoft.com/office365/admin/setup/install-applications) 。
     
## <a name="advanced"></a>高级
- **使用 Autopilot 设置新设备**
            
     可以使用 [Windows Autopilot](add-autopilot-devices-and-profile.md) 为用户自动预配置 **新** 的 Windows 10 设备，但更易于获取可为您执行此操作的 [合作伙伴](https://www.microsoft.com/solution-providers/search) 。 你也可以转到 [Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)，并请求云技术专家设置你购买的新设备。

- **访问本地资源**

     - 如果您的组织使用的是本地 Windows Server Active Directory，则可以将 Microsoft 365 商业高级版设置为保护您的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。 按照 [Microsoft 365 商业高级版中的 "启用加入域的 Windows 10 设备](manage-windows-devices.md) " 中的步骤进行操作，以设置此设置。 这是首选方法，而此状态的设备称为混合 Azure AD 加入的设备。

    - 如果你的企业有一个本地 Active Directory，其中包含一些本地资源 (如文件共享和打印机) ，则可以按照以下步骤为 Azure AD 联接的设备授予对这些资源的访问权限： [从 Microsoft 365 商业高级版中的 AZURE AD 加入设备访问本地资源](access-resources.md)。

## <a name="see-also"></a>另请参阅

[Microsoft 365 商业版培训视频](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
