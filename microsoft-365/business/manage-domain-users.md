---
title: 将域用户同步到 Microsoft 365
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: sirkkuw
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
description: 将受域控制的用户与 Microsoft 365 for business 同步。
ms.openlocfilehash: b40a995a1723808d2fd171c534e9131a891840ba
ms.sourcegitcommit: e56894917d2aae05705c3b9447388d10e2156183
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48841351"
---
# <a name="synchronize-domain-users-to-microsoft-365"></a>将域用户同步到 Microsoft 365

## <a name="1-prepare-for-directory-synchronization"></a>1. 准备目录同步 

在将用户和计算机从本地 Active Directory 域同步之前，请查看 " [准备将目录同步到 Microsoft 365](https://docs.microsoft.com/microsoft-365/enterprise/prepare-for-directory-synchronization)"。 具体而言：

   - 请确保目录中不存在以下属性的重复项： **mail** 、 **proxyAddresses** 和 **userPrincipalName** 。 这些值必须是唯一的，并且必须删除任何重复的值。
   
   - 建议您为每个本地用户帐户配置 **userPrincipalName** (UPN) 属性，以匹配与已授权的 Microsoft 365 用户相对应的主电子邮件地址。 例如： *mary.shelley@contoso.com* 而不是 *mary@contoso。本地*
   
   - 如果 Active Directory 域以不可路由的后缀（如 *local* 或 *lan* ）结尾，而不是 internet 路由后缀（如 *.com* 或 *. org* ），请先按照为 [目录同步准备不可路由的域](https://docs.microsoft.com/microsoft-365/enterprise/prepare-a-non-routable-domain-for-directory-synchronization)中所述的步骤调整本地用户帐户的 UPN 后缀。 

下面的步骤 4 (4) 中的 **Run IdFix** 还将确保您的内部部署 Active Directory 已准备好进行目录同步。

## <a name="2-install-and-configure-azure-ad-connect"></a>2. 安装和配置 Azure AD Connect

若要将本地 Active Directory 中的用户、组和联系人同步到 Azure Active Directory 中，请安装 Azure Active Directory Connect 并设置目录同步。 

 1. 在 [管理中心](https://go.microsoft.com/fwlink/p/?linkid=2024339)内，选择左侧导航中的 " **设置** "。

 2. 在 " **登录和安全** " 下，选择 "在 **组织的目录中同步用户** " 下的 " **查看** "。

 3. 在 " **从您的组织的目录中同步用户** " 页上，选择 " **开始** "。

 4. 在第一步中运行 IdFix 工具以准备目录同步。

 5. 按照向导步骤下载 Azure AD Connect，并使用它将域控制的用户同步到 Microsoft 365。


若要了解详细信息，请参阅 [设置 Microsoft 365 的目录同步](https://docs.microsoft.com/microsoft-365/enterprise/set-up-directory-synchronization) 。

在为 Azure AD Connect 配置选项时，我们建议您启用 **密码同步** 、 **无缝单一登录** 和 **密码写回** 功能，这在 Microsoft 365 for business 中也受支持。

> [!NOTE]
> 除了 Azure AD Connect 中的复选框之外，还需要执行一些额外的密码写回步骤。 有关详细信息，请参阅 [操作方法：配置密码写回](https://docs.microsoft.com/azure/active-directory/authentication/howto-sspr-writeback)。 

如果你还想要管理加入域的 Windows 10 设备，请参阅 [Enable 由 Microsoft 365 商业高级版管理的加入域的 windows 10 设备](manage-windows-devices.md) ，以设置混合 Azure AD 加入。 