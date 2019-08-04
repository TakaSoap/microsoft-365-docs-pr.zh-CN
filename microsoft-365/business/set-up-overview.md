---
title: 设置概述
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
search.appverid:
- BCS160
- MET150
ms.assetid: 6e7a2dfd-8ec4-4eb7-8390-3ee103e5fece
description: Microsoft 365 商业版的设置步骤概述。
ms.openlocfilehash: ae7ed0aab36a6e759e0f0c1fbc3d3183273a284e
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34074402"
---
# <a name="overview-of-setup"></a>安装程序概述

大部分设置步骤可以在安装向导中完成, 但也会列出其他选项。


## <a name="step-1-add-your-domain-and-users"></a>步骤 1: 添加您的域和用户

   - **[添加你的域](set-up.md#add-your-domain-to-personalize-sign-in)**(如果你在[注册](sign-up.md)期间购买了你的域, 则此步骤已完成。)

    - **添加用户**。 可以通过以下三种方式之一执行此操作:
        - 在[向导](set-up.md#add-users-in-the-wizard)中。
        - 如果你有本地 Active directory, 请使用目录同步来[使用 AZURE AD Connect 添加用户](https://docs.microsoft.com/office365/enterprise/set-up-directory-synchronization)。
        - 您还可以在随后的管理中心[添加用户](add-users-m365b.md)。
## <a name="step-2-set-up-security-policies-and-configure-devices"></a>步骤 2: 设置安全策略和配置设备 

  - 使用[安装向导](set-up.md#set-up-security-policies-and-device-configurations)配置设备和安全策略。 
  - 您还可以在[管理员中心](view-policies-and-devices.md)和[Intune 门户](https://docs.microsoft.com/intune/tutorial-walkthrough-intune-portal)中添加更多或编辑它们。
  - 除了安装向导中的安全设置之外, 还可以通过添加以下设置来提高安全性:

      - **电子邮件恶意软件保护**
      - **高级威胁防护 (ATP) 安全链接**
      - **ATP 安全附件**
      - **ATP 反网络钓鱼**
      - **Exchange Online Archiving**
      - **Data Loss Prevention (DLP)**
      - **Azure 信息保护 (Plan1**)

          若要开始, 请[设置高级安全策略](set-up-advanced-security.md)。

        请参阅[保护 Microsoft 365 业务的十大方法](https://docs.microsoft.com/office365/admin/security-and-compliance/secure-your-business-data), 以获得最佳安全实践的路线图。

## <a name="step-3-set-up-and-manage-windows-10-devices"></a>步骤 3: 设置和管理 Windows 10 设备

   将 Windows 10 设备加入 Azure AD 时, 将在[步骤 2](#step-2-set-up-security-policies-and-configure-devices)中设置的策略应用于该 AD。

   - Windows 10 专业版是 Microsoft 365 商业版的[先决条件](pre-requisites-for-data-protection.md), 但如果你有 Windows 7 Pro、Windows 8 专业版或 Windows 8.1 专业版, 你的订阅使你能够[升级到 Windows 10 专业](https://docs.microsoft.com/microsoft-365/business/upgrade-to-windows-pro-creators-update)版。
    - 使用[安装向导](set-up.md#set-up-security-policies-and-device-configurations)为 Windows 10 设备配置策略。

## <a name="stes-4-install-office-365-business"></a>Stes 4: 安装 Office 365 商业版
- 您可以使用[安装向导](set-up.md#deploy-office-365-client-apps)在 Windows 设备中自动安装 Office。
- 从管理中心自动[安装 Office](auto-install-or-uninstall-office.md) 。
- 允许用户安装适用于 Windows 和设备的[Office 应用程序](https://docs.microsoft.com/office365/admin/setup/install-applications)。
     
## <a name="advanced"></a>高级
- **使用 Autopilot 设置新设备**
            
     可以使用[Windows Autopilot](add-autopilot-devices-and-profile.md)为用户自动预配置**新**的 Windows 10 设备, 但更易于获取可为您执行此操作的[合作伙伴](https://www.microsoft.com/solution-providers/search)。 你也可以转到[Microsoft Store](https://go.microsoft.com/fwlink/?linkid=874598)并咨询云技术专家, 以设置你购买的新设备。

- **访问本地资源**

     - 如果您的组织使用的是本地 Windows Server Active Directory, 则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备, 同时仍保持对需要本地身份验证的本地资源的访问权限。 按照 Microsoft 365 商业版中的 "[启用加入域的 Windows 10 设备](manage-windows-devices.md)" 中的步骤进行操作, 以便对此进行设置。 这是此状态的首选方法, 称为混合 Azure AD 加入的设备。

    - 如果你的企业有包含某些本地资源 (如文件共享和打印机) 的本地 Active Directory, 则可以执行以下步骤, 为 Azure AD 联接的设备提供对这些资源的访问权限:[从访问本地资源Microsoft 365 商业版中的 Azure AD 加入设备](access-resources.md)。

  