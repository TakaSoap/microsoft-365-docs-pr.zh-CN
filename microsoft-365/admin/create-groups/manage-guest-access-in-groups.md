---
title: 在 Microsoft 365 组中管理来宾访问
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
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
description: 了解如何将来宾添加到 Microsoft 365 组，查看来宾用户，以及如何使用 PowerShell 控制来宾访问。
ms.openlocfilehash: 640a35cbb1a3eb395453b224cadcf0d0db82fab8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326515"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>在 Microsoft 365 组中管理来宾访问

默认情况下，为您的组织启用对 Microsoft 365 组的来宾访问。 管理员可以控制是否允许来宾访问整个组织或单个组的组。

当它打开时，组成员可以通过 Web 上的 Outlook 将来宾用户邀请到 Microsoft 365 组。 邀请将发送给组所有者以供审批。

批准后，会将来宾用户添加到目录和组中。

> [!Note]
> 处于本机模式或 [欧盟地区](https://go.microsoft.com/fwlink/?linkid=2107357) 的 Yammer 企业网络不支持网络来宾。
> Microsoft 365 连接的 Yammer 组目前不支持来宾访问，但你可以在 Yammer 网络中创建未连接的外部组。 有关说明，请参阅 [在 Yammer 中创建和管理外部组](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) 。

组中的来宾访问通常用作包括 SharePoint 或团队的更广泛方案的一部分。 这些服务具有自己的来宾共享设置。 有关在组、SharePoint 和团队中设置来宾共享的完整说明，请参阅：

- [在网站中与来宾协作](../../solutions/collaborate-in-site.md)
- [在团队中与来宾协作](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>管理组来宾访问

如果要启用或禁用组中的来宾访问，可以在 Microsoft 365 管理中心中执行此操作。

1. 在管理中心中，转到 " **显示所有** \> **设置**" " \> **组织设置** "，并在 " **服务** " 选项卡上选择 " **Microsoft 365 组**"。
  
2. 在 " **Microsoft 365 组** " 页上，选择是否要让组织外部的用户访问组资源，或允许组所有者将组织外部的人员添加到组中。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>从管理中心向 Microsoft 365 组添加来宾

如果来宾已经存在于目录中，则可以从 Microsoft 365 管理中心将其添加到你的组。
  
1. 在 "管理中心" 中，转到 "**组**  >  **组**" 页面。
  
2. 单击要向其添加来宾的组，然后选择 "**成员**" 选项卡上的 "**查看全部和管理成员**"。 
  
4. 选择 " **添加成员**"，然后选择要添加的来宾的名称。
    
5. 选择“**保存**”。

如果要直接将来宾添加到目录中，可以 [在 azure 门户中添加 Azure Active DIRECTORY B2B 协作用户](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)。

如果要编辑任何来宾的信息，可以 [使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

## <a name="see-also"></a>另请参阅

[阻止特定组中的来宾用户](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[在 Microsoft 365 管理中心中管理组成员身份](add-or-remove-members-from-groups.md)
  
[Azure Active Directory 访问审核](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[AzureADUser](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
