---
title: 在组中添加或删除Microsoft 365成员
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
search.appverid:
- MET150
ms.assetid: e186d224-a324-4afa-8300-0e4fc0c3000a
description: 了解如何向组添加成员、从组中删除成员以及管理组所有者Microsoft 365 管理中心。
ms.openlocfilehash: 610da28d6282cb45cb43e086fb3f80acaf18bb05
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60165816"
---
# <a name="add-or-remove-members-from-microsoft-365-groups-using-the-admin-center"></a>使用管理中心在Microsoft 365组中添加或删除成员

在Microsoft 365中，团队成员通常创建自己的组、将自己添加到要加入的组或受组所有者邀请的组。 如果组所有权发生更改，或者确定应添加或删除成员，作为管理员，还可以进行此更改。 只有全局管理员、Exchange管理员、组管理员或用户管理员才能进行这些更改。 [什么是Microsoft 365组？](https://support.microsoft.com/office/b565caa1-5c40-40ef-9915-60fdb2d97fa2)

> [!TIP]
> 如果你不是管理员，可以使用 "添加[或删除"Outlook。](https://support.microsoft.com/office/3b650f4a-5c9b-4f94-a1bb-0cca4b1091de)
  
## <a name="add-a-member-to-a-group-in-the-admin-center"></a>将成员添加到管理中心中的组

1. 在管理中心，转到" [**活动组"**](https://admin.microsoft.com/Adminportal/Home?#/groups) 页面。  

2. 单击组名称。

3. 在详细信息窗格中的"成员 **"** 选项卡上，选择"**查看所有和管理成员**"，然后选择"**添加成员"。**

4. 搜索或选择要添加的成员的名称。

5. 选择“**保存**”。

## <a name="add-a-group-to-a-member-in-the-admin-center"></a>将组添加到管理中心的成员

1. 在管理中心，转到" [**活动用户"**](https://admin.microsoft.com/Adminportal/Home?#/users) 页面。  

2. 单击用户。

3. 在详细信息窗格中的"帐户"**选项卡上**，选择"**管理组"。**

4. 搜索或选择要添加的组的名称。

5. 选择“**保存**”。

## <a name="remove-a-member-from-a-group-in-the-admin-center"></a>从管理中心中的组中删除成员

> [!NOTE]
> 从专用组中删除成员时，需要 5 分钟才能阻止该人员访问该组。

1. 在管理中心，转到" [**活动组"**](https://admin.microsoft.com/Adminportal/Home?#/groups) 页面。  

2. 单击组名称。

3. 在详细信息窗格中的"成员 **"选项卡上**，选择"**查看所有和管理成员"。**

4. 在要删除的成员旁边，选择"X"。

5. 选择 **"保存** "以删除成员。

## <a name="manage-group-owner-status"></a>管理组所有者状态

组的创建者默认为组所有者。通常，出于备份支持或其他原因，一个组将具有多个所有者。可将成员提升为所有者状态，并可将所有者降级为成员状态。
  
### <a name="promote-a-member-to-owner-status-in-the-admin-center"></a>在管理中心将成员提升为所有者状态

1. 在管理中心，转到" [**活动组"**](https://admin.microsoft.com/Adminportal/Home?#/groups) 页面。  

2. 单击组名称。

3. 在详细信息窗格中的"成员 **"选项卡上**，选择"**查看所有和管理所有者"。**

4. 选择 **"添加所有者"。**

5. 选中要添加的成员的名称旁边的复选框。

6. 选择 **"保存"，** 然后选择"**关闭"。**

### <a name="remove-owner-status-in-the-admin-center"></a>在管理中心删除所有者状态

1. 在管理中心，转到" [**活动组"**](https://admin.microsoft.com/Adminportal/Home?#/groups) 页面。  

2. 单击组名称。

3. 在详细信息窗格中的"成员 **"选项卡上**，选择"**查看所有和管理所有者"。**

4. 选择所有者姓名旁边的 X。

5. 选择“**保存**”。

## <a name="next-steps"></a>后续步骤

- [在 Azure Active Directory 中动态管理组](/azure/active-directory/fundamentals/active-directory-groups-create-azure-portal)：请参阅"如何动态管理组的成员？"部分

- 若要向组添加成百上千个用户，请使用 [Add-UnifiedGroupLinks](/powershell/module/exchange/add-unifiedgrouplinks)。

- [向孤立组分配新的所有者](https://support.microsoft.com/office/86bb3db6-8857-45d1-95c8-f6d540e45732)

## <a name="related-content"></a>相关内容

[将通讯组列表Microsoft 365本文Outlook (](../manage/upgrade-distribution-lists.md)组) \
[为什么应该将通讯组列表升级到](https://support.microsoft.com/office/7fb3d880-593b-4909-aafa-950dd50ce188)Outlook (中) \
[管理来宾组中来宾Microsoft 365 (](manage-guest-access-in-groups.md)文章) \
[使用 PowerShell Microsoft 365](../../enterprise/manage-microsoft-365-groups-with-powershell.md)组：本文介绍了关键 cmdlet，并提供了本文 (示例) \
[Microsoft 365文章 (组](../../solutions/groups-naming-policy.md)命名策略) 