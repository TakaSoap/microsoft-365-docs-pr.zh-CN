---
title: 管理来宾组中来宾Microsoft 365访问
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
- admindeeplinkMAC
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 了解如何将来宾添加到 Microsoft 365 组、查看来宾用户和使用 PowerShell 控制来宾访问。
ms.openlocfilehash: 99c0a9f46abfffe56f8c751ca614287181f39a5d
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165744"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a>管理来宾组中来宾Microsoft 365访问

默认情况下，你的组织Microsoft 365组来宾访问。 管理员可以控制是允许来宾访问整个组织组还是允许单个组访问组。

启用后，组的成员可以通过 Web 上的Microsoft 365邀请来宾Outlook组。 邀请将发送给组所有者进行审批。

批准后，来宾用户将添加到目录和组中。

> [!Note]
> Yammer Enterprise模式或[欧盟地理位置](/yammer/manage-security-and-compliance/manage-data-compliance)的网络不支持网络来宾。
> Microsoft 365已Yammer组当前不支持来宾访问，但可以在非连接网络中创建Yammer组。 有关[说明，请参阅在](/yammer/work-with-external-users/create-and-manage-external-groups)Yammer 创建和管理外部组。

组中的来宾访问通常用作更广泛的方案的一部分，包括SharePoint或Teams。 这些服务具有其自己的来宾共享设置。 有关在组、用户和用户之间设置来宾共享SharePoint的完整Teams，请参阅：

- [在网站中与来宾协作](../../solutions/collaborate-in-site.md)
- [在团队中与来宾协作](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a>管理组来宾访问

如果要在组中启用或禁用来宾访问，可以在组 <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**中启用或禁用来宾访问**</a>。

1. In the admin center， go to **Show all** \> **设置** \> **Org settings** and on the **Services** tab， select <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**Microsoft 365 Groups**</a>.
  
2. 在 **"Microsoft 365** 组"页上，选择是允许组织外部人员访问组资源，还是允许组所有者将组织外部人员添加到组。

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a>从管理中心Microsoft 365来宾添加到组

如果目录中已存在来宾，你可以将它们添加到你的<a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Microsoft 365 管理中心。</a>  (动态成员身份的组必须在 .Azure Active Directory [.) ](/azure/active-directory/enterprise-users/groups-create-rule)
  
1. 在管理中心，转到组  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">**组**</a>。
  
2. 单击要添加来宾的组，然后选择"成员"选项卡上的"查看所有和管理 **成员**"。 
  
4. 选择 **"添加** 成员"，然后选择要添加的来宾的名称。
    
5. 选择“**保存**”。

如果你想要将来宾直接添加到目录，可以在[Azure 门户Azure Active Directory B2B 协作用户。](/azure/active-directory/b2b/add-users-administrator)

如果要编辑来宾的任何信息，可以使用 "添加或更新用户个人资料[Azure Active Directory"](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。

## <a name="related-content"></a>相关内容

[阻止特定组的来宾用户 (](../../solutions/per-group-guest-access.md) 文章) \
[管理组成员身份，Microsoft 365 管理中心 (](add-or-remove-members-from-groups.md)文章) \
[Azure Active Directory访问评审](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (文章) \
[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (文章) 