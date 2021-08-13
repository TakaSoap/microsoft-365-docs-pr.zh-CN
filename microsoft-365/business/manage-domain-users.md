---
title: 将域用户同步到 Microsoft 365
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection: M365-subscription-management
ms.custom:
- Adm_O365
- Core_O365Admin_Migration
- MiniMaven
- MSB365
- OKR_SMB_M365
- seo-marvel-mar
- AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
description: 将域控制的用户与Microsoft 365同步。
ms.openlocfilehash: 468fa943df55b12573f0a4f595294e39a146b1850f3c430ac2088a30991c0e60
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53809304"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>将域用户同步到 Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. 准备目录同步 

在从本地 Active Directory 域同步用户和计算机之前，请查看准备进行目录[同步以Microsoft 365。](../enterprise/prepare-for-directory-synchronization.md) 特别是：

   - 请确保目录中不存在以下属性的重复项 **：mail、proxyAddresses** 和 **userPrincipalName**。 这些值必须是唯一的，并且必须删除任何重复项。
   
   - 建议您为每个本地用户帐户配置 **userPrincipalName** (UPN) 属性，以匹配与许可用户对应的主Microsoft 365地址。 例如 *：mary.shelley@contoso.com* 而不是 *mary@contoso.local*
   
   - 如果 Active Directory 域以不可路由的后缀（如 *.local* 或 *.lan）* 结束，而不是 Internet 可路由后缀（如 *.com* 或 *.org），* 请首先调整本地用户帐户的 UPN 后缀，如准备目录同步的不可路由域中所述。 [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md) 

下面的步骤 4 (4) 中运行 **IdFix** 还将确保本地 Active Directory 已做好目录同步准备。

## <a name="2-install-and-configure-azure-ad-connect"></a>2. 安装和配置 Azure AD 连接

若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory，Azure Active Directory 连接并设置目录同步。 

 1. 在管理 [中心中](https://go.microsoft.com/fwlink/p/?linkid=2024339)**，选择** 左侧导航中的"设置"。

 2. 在 **"登录和安全"下，** 选择 **"** 从组织目录同步用户 **"下的"查看"。**

 3. 在"**从组织目录同步** 用户"页上，选择"**开始使用"。**

 4. 在首次步骤中，运行 IdFix 工具以准备目录同步。

 5. 按照向导步骤下载 Azure AD 连接并使用它将域控制的用户同步到Microsoft 365。


有关详细信息[，请参阅为Microsoft 365](../enterprise/set-up-directory-synchronization.md)目录同步。

为 Azure AD 连接配置选项时，我们建议你启用密码同步、无缝单一登录和密码写回功能，该功能在 Microsoft 365 for business 中也受支持。 

> [!NOTE]
> 除了 Azure AD 连接 中的复选框之外，还有一些额外的密码写回连接。 有关详细信息，请参阅 [操作说明：配置密码写回](/azure/active-directory/authentication/howto-sspr-writeback)。 

如果你还想要管理已加入域Windows 10设备，请参阅启用已加入域的[Windows 10](manage-windows-devices.md)设备由 Microsoft 365 商业高级版 管理以设置混合 Azure AD 加入。