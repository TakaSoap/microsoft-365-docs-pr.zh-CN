---
title: 启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- M365-identity-device-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
search.appverid:
- BCS160
- MET150
ms.assetid: 9b4de218-f1ad-41fa-a61b-e9e8ac0cf993
description: 了解如何启用 Microsoft 365 以保护本地 AD 加入 Windows 10 设备。
ms.openlocfilehash: af0e78ef6e79bfd612b11a16538e7afcd377ffb0
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34071542"
---
# <a name="enable-domain-joined-windows-10-devices-to-be-managed-by-microsoft-365-business"></a>启用要由 Microsoft 365 商业版管理的加入域的 Windows 10 设备

如果您的组织使用的是本地 Windows Server Active Directory, 则可以将 Microsoft 365 商业版设置为保护 Windows 10 设备, 同时仍保持对需要本地身份验证的本地资源的访问权限。 你可以先将 Active Directory 与 Azure Active Directory 同步, 然后使用 Azure AD 注册 Windows 10 设备, 并注册 Microsoft 365 商业版的移动设备管理, 从而对此进行设置。
  
## <a name="set-up-domain-joined-devices-to-be-managed-by-microsoft-365-business"></a>设置由 Microsoft 365 商业版管理的加入域的设备

若要将组织的加入域的设备设置为从 Azure Active Directory 提供的功能中受益, 除了本地 Active Directory 之外, 还可以实现混合的**AZURE AD 加入设备**。 这些是同时连接到本地 Active Directory 和 Azure Active Directory 的设备。 混合 Azure AD 加入的设备可受到 Microsoft 365 商业版的保护和管理。 
  
完成以下步骤, 使 Microsoft 365 商业版加入和管理 Windows 10 设备混合的 Azure AD。
  
1. 若要将您的用户、组和联系人从本地 Active Directory 同步到 Azure Active Directory, 请运行目录同步向导和 Azure Active Directory Connect, 如[设置 Office 365 的 "设置目录同步](https://support.office.com/article/1b3b5318-6977-42ed-b5c7-96fa74b08846)" 中所述。
    
    > [!NOTE]
    > 对于 Microsoft 365 商业版的步骤完全相同。 
  
2. 在完成第3步以使 Windows 10 设备成为合并的 Azure AD 之前, 您需要确保满足以下先决条件:

   - 您运行的是最新版本的 Azure AD connect。

   - Azure AD connect 已同步要连接混合 Azure AD 的设备的所有计算机对象。 如果计算机对象属于特定的组织单位 (OU), 请确保将这些 Ou 设置为在 Azure AD connect 中进行同步。
    
3. 将现有的加入域的 Windows 10 设备注册为混合 Azure AD 加入并注册为 Intune (Microsoft 365 Business) 进行移动设备管理:
    
4. 按照[如何配置混合 Azure Active Directory 已加入设备](https://go.microsoft.com/fwlink/p/?linkid=872870)的分步说明操作。 这将启用已加入 Windows 10 计算机的本地 Active Directory 的同步, 并使其成为云就绪状态。
    
5. 若要为移动设备管理注册 Windows 10 设备, 请参阅[使用组策略向 Intune 注册 windows 10 设备](https://go.microsoft.com/fwlink/p/?linkid=872871), 以获取说明。 您可以在本地计算机级别或批量操作中设置组策略, 您可以在域控制器服务器上创建此组策略设置。