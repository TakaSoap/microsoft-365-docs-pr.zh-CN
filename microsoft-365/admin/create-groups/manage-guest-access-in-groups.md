---
title: 在 Microsoft 365 组中管理来宾访问
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 了解如何将来宾添加到 Microsoft 365 组、查看来宾用户和使用 PowerShell 控制来宾访问。
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453653"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>在 Microsoft 365 组中管理来宾访问

默认情况下，为组织启用 Microsoft 365 组的来宾访问。 管理员可以控制是允许来宾访问整个组织组还是允许单个组访问组。

启用后，组成员可以通过 Outlook 网页版邀请来宾用户加入 Microsoft 365 组。 邀请将发送给组所有者进行审批。

批准后，来宾用户将添加到目录和组。

> [!Note]
> 本机模式或欧盟地理位置中的 Yammer Enterprise [网络不支持](https://go.microsoft.com/fwlink/?linkid=2107357) 网络来宾。
> Microsoft 365 连接的 Yammer 组当前不支持来宾访问，但您可以在 Yammer 网络中创建未连接的外部组。 有关 [说明，请参阅在 Yammer 中](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) 创建和管理外部组。

组中的来宾访问通常用作包括 SharePoint 或 Teams 的更广泛的方案的一部分。 这些服务有其自己的来宾共享设置。 有关跨组、SharePoint 和 Teams 设置来宾共享的完整说明，请参阅：

- [在网站中与来宾协作](../../solutions/collaborate-in-site.md)
- [在团队中与来宾协作](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>管理组来宾访问

如果要在组中启用或禁用来宾访问，可以在 Microsoft 365 管理中心中启用或禁用来宾访问。

1. 在管理中心中，转到"显示 **所有** 设置组织设置"，在"服务"选项卡上，选择 \>  \> **Microsoft 365 组**。 
  
2. 在 **"Microsoft 365** 组"页上，选择是允许组织外部人员访问组资源，还是允许组所有者将组织外部人员添加到组。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>从管理中心向 Microsoft 365 组添加来宾

如果目录中已存在来宾，可以从 Microsoft 365 管理中心将其添加到组。  (动态成员身份的组必须在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).) 
  
1. 在管理中心，转到"组  >  **组"** 页。
  
2. 单击要添加来宾的组，然后选择"成员"选项卡上的"查看所有和管理 **成员**"。 
  
4. 选择 **"** 添加成员"，然后选择要添加的来宾的名称。
    
5. 选择“**保存**”。

如果要直接向目录添加来宾，可以在 Azure 门户中添加 Azure [Active Directory B2B 协作用户](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)。

如果要编辑任何来宾信息，可以使用 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)添加或更新用户配置文件信息。

## <a name="see-also"></a>另请参阅

[阻止特定组的来宾用户](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[在 Microsoft 365 管理中心管理组成员身份](add-or-remove-members-from-groups.md)
  
[Azure Active Directory 访问评审](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[Set-AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
