---
title: 设置概述
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
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
description: 了解 Microsoft 365 商业高级版（从订阅到添加域和用户、设置安全策略等）的设置步骤。
ms.openlocfilehash: 749acbfdbde92ad97b09dc720c85dd850b76c9cf
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51579926"
---
# <a name="overview-of-setup"></a>设置概述

观看有关 Microsoft 365 商业高级版设置的简短视频。<br><br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4jZwg] 

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

大多数设置步骤都可以在引导式设置中完成，但还会列出其他选项。

## <a name="step-1-add-your-domain-and-users"></a>步骤 1：添加域和用户

   - **[如果在注册](set-up.md#add-your-domain-to-personalize-sign-in)** (购买了域，请添加域策略，此步骤 [](sign-up.md)已完成。) 

   - **添加用户**。 您可以通过以下三种方法之一添加用户：
        - 在引导 [式设置中](set-up.md#add-users-in-the-wizard)。
        - 如果你有本地 Active Directory，请使用目录同步通过 [Azure AD Connect](../enterprise/set-up-directory-synchronization.md) 添加用户。
        - 还可以稍后 [在管理中心](../admin/add-users/add-users.md) 中添加用户。
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>步骤 2：设置安全策略和配置设备 

  - 使用 [引导式设置](set-up.md#protect-your-organization) 配置设备策略。 
  - 还可以在管理中心和 Intune 门户中稍后[](view-policies-and-devices.md)添加更多或[编辑它们](/intune/tutorial-walkthrough-intune-portal)。
  - 安装向导还将设置基本威胁防护和数据丢失防护设置。
  
  除了安装向导中的安全设置之外，您还可以通过添加以下设置来增强安全性：

- **电子邮件恶意软件保护**
- **Office 365 Defender 中的防钓鱼**
- **Exchange Online Archiving**
- **Azure 信息保护 (计划 1**) 

若要开始，请参阅[增加威胁防护](increase-threat-protection.md)[和设置合规性功能](set-up-compliance.md)。

另请参阅 [保护 Microsoft 365](/office365/admin/security-and-compliance/secure-your-business-data) 商业高级版前 10 种方法，了解最佳安全做法路线图。

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>步骤 3：设置和管理 Windows 10 设备

完成引导式设置后，你将希望保护组织的所有 Windows 10 计算机。
  
- Windows 10 专业[](pre-requisites-for-data-protection.md)版是 Microsoft 365 商业高级版的先决条件，但如果你拥有 Windows 7 专业版、Windows 8 专业版 或 Windows 8.1 专业版，你的订阅将授权你升级到[Windows 10 专业版](./upgrade-to-windows-pro-creators-update.md)。
- 按照安全 [Windows 10 电脑](secure-win-10-pcs.md) 中的步骤为 Windows 10 设备设置策略。

将 Windows 10 设备加入 Azure AD 时，你为 Windows 10 计算机设置的策略将应用于该设备。 有关详细信息，请参阅为 [Microsoft 365 用户设置 Windows 设备](set-up-windows-devices.md)。

## <a name="step-4-install-microsoft-365-apps-for-business"></a>步骤 4：安装 Microsoft 365 商业应用版
- 可以使用安装向导在 Windows 设备中自动[安装 Office。](set-up.md#deploy-office-365-client-apps)
- 让用户 [安装适用于](/office365/admin/setup/install-applications) Windows 和设备的 Office 应用。
     
## <a name="advanced"></a>高级
- **使用 Autopilot 设置新设备**
            
     可以使用 [Windows Autopilot](add-autopilot-devices-and-profile.md)为用户自动预配置新的 **Windows** 10 设备，但可能更易于获取可为此操作的合作伙伴 [](https://www.microsoft.com/solution-providers/search)。 还可以转到 Microsoft [Store，](https://go.microsoft.com/fwlink/?linkid=874598)让云技术专家设置你购买的新设备。

- **访问本地资源**

     - 如果你的组织使用本地 Windows Server Active Directory，你可以设置 Microsoft 365 商业高级版来保护你的 Windows 10 设备，同时仍保持对需要本地身份验证的本地资源的访问权限。 请按照允许 [Microsoft 365](manage-windows-devices.md) 商业高级版管理已加入域的 Windows 10 设备中的步骤进行设置。 这是首选方法，并且此状态中的设备称为加入混合 Azure AD 的设备。

    - 如果你的企业有一个本地 Active Directory，其中包含一些本地资源 (例如文件共享和打印机) ，你可以按照以下步骤为加入 Azure AD 的设备提供对这些资源的访问权限：在 [Microsoft 365](access-resources.md)商业高级版 中从加入 Azure AD 的设备访问本地资源。

## <a name="see-also"></a>另请参阅

[Microsoft 365 商业版培训视频](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)