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
description: 将域控制的用户与 Microsoft 365 商业版同步。
ms.openlocfilehash: b477b8a1f35a790d6c49937c973c141ad9f90ad4
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51578399"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>将域用户同步到 Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. 准备目录同步 

在从本地 Active Directory 域同步用户和计算机之前，请查看准备与 [Microsoft 365](../enterprise/prepare-for-directory-synchronization.md)的目录同步。 特别是：

   - 请确保目录中不存在以下属性的重复项 **：mail、proxyAddresses** 和 **userPrincipalName**。 这些值必须是唯一的，并且必须删除任何重复项。
   
   - 我们建议您为每个本地用户帐户配置 **userPrincipalName** (UPN) 属性，以匹配与许可的 Microsoft 365 用户对应的主电子邮件地址。 例如 *：mary.shelley@contoso.com* 而不是 *mary@contoso.local*
   
   - 如果 Active Directory 域以不可路由的后缀（如 *.local* 或 *.lan）* 结束，而不是 Internet 可路由后缀（如 *.com* 或 *.org），* 请首先调整本地用户帐户的 UPN 后缀，如准备目录同步的不可路由域中所述。 [](../enterprise/prepare-a-non-routable-domain-for-directory-synchronization.md) 

下面的步骤 4 (4) 中运行 **IdFix** 还将确保本地 Active Directory 已做好目录同步准备。

## <a name="2-install-and-configure-azure-ad-connect"></a>2. 安装和配置 Azure AD Connect

若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory，请安装 Azure Active Directory Connect 并设置目录同步。 

 1. 在管理 [中心中](https://go.microsoft.com/fwlink/p/?linkid=2024339)**，选择** 左侧导航中的"设置"。

 2. 在 **"登录和安全"下，** 选择 **"** 从组织目录同步用户 **"下的"查看"。**

 3. 在"**从组织目录同步** 用户"页上，选择"**开始使用"。**

 4. 在首次步骤中，运行 IdFix 工具以准备目录同步。

 5. 按照向导步骤下载 Azure AD Connect，并使用它将域控制的用户同步到 Microsoft 365。


有关详细信息 [，请参阅设置 Microsoft 365](../enterprise/set-up-directory-synchronization.md) 的目录同步。

配置 Azure AD Connect 选项时，我们建议你启用密码同步、无缝单一登录和密码写 **回** 功能，Microsoft 365 商业版也支持此功能。

> [!NOTE]
> 除了 Azure AD Connect 中的复选框之外，还有一些额外的密码写回步骤。 有关详细信息，请参阅 [操作说明：配置密码写回](/azure/active-directory/authentication/howto-sspr-writeback)。 

如果你还想要管理加入域的 Windows 10 设备，请参阅启用加入域的 Windows 10 设备以由 [Microsoft 365](manage-windows-devices.md) 商业高级版管理以设置混合 Azure AD 加入。