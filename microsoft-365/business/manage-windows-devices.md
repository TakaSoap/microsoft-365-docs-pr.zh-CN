---
title: 启用加入域的 Windows 10 设备，由 Microsoft 365 企业版
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
ms.audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 了解如何启用 Microsoft 365 来保护本地 AD 加入 Windows 10 设备。
ms.openlocfilehash: 6e66a2c5417c9037232c1ada654d4cac3c520607
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865548"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>启用加入域的 Windows 10 设备，由 Microsoft 365 企业版

如果您的组织使用 Windows Server Active Directory 部署，您可以设置 Microsoft 365 业务保护 Windows 10 设备，同时保持需要本地身份验证的本地资源的访问权限。您可以设置此第一个与 Azure Active Directory 后, 跟 Windows 10 设备注册 Azure AD 和注册这些移动设备管理由 Microsoft 365 业务同步您的 Active Directory。
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>设置由 Microsoft 365 业务的加入域的设备

若要设置组织的加入域的设备从内部部署 Active Directory 之外的 Azure Active Directory 所提供的功能受益，您可以实现**混合 Azure AD 加入设备**。它们同时连接到您的本地 Active Directory 和 Azure Active Directory 的设备。混合加入的 Azure AD 设备可以受保护，并由 Microsoft 365 业务正在 
  
完成以下步骤来使 Windows 10 设备混合 Azure AD 加入并由 Microsoft 365 企业版。
  
1. 若要将您的用户、 组和联系人从本地 Active Directory 同步到 Azure Active Directory 中，运行目录同步向导和 Azure Active Directory 连接[设置 Office 365 的目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)中所述。
    
    > [!NOTE]
    > 步骤是完全相同的 Microsoft 365 企业版。 
  
2. 完成步骤 3，允许在的混合 Azure AD 加入 Windows 10 设备之前，您需要确保您满足以下先决条件：
    
   - 您运行的最新版本的 Azure AD 连接。
    
   - Azure AD 连接已同步的要加入 Azure AD 的混合的设备的所有计算机对象。如果计算机对象属于特定组织单位 (OU)，则请确保这些 Ou 设置 Azure AD 中的同步连接以及。
    
3. 注册现有加入域的 Windows 10 混合 Azure AD 加入和设备注册这些 Intune （Microsoft 365 企业版） 通过移动设备管理：
    
4. 按照[How to 配置混合 Azure Active Directory 加入设备](https://go.microsoft.com/fwlink/p/?linkid=872870)中的循序渐进说明。这将使您的本地 Active directory 同步加入 Windows 10 计算机，并使其云就绪。
    
5. 若要注册移动设备管理 Windows 10 设备，说明，请参阅[注册使用组策略 Intune Windows 10 设备](https://go.microsoft.com/fwlink/p/?linkid=872871)。您可以设置的组策略在本地计算机上级别或对于批量操作，您可以在您的域控制器服务器上创建此组策略设置。 
    

