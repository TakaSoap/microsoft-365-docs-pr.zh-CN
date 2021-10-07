---
title: 允许用户重置自己的密码
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- MSStore_Link
- TRN_M365B
- OKR_SMB_Videos
- AdminSurgePortfolio
- okr_smb
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 了解如何设置策略以允许用户使用自助服务密码重置工具重置自己的密码。
ms.openlocfilehash: a30c32239cb1c995beaaf725aaf5dc3821beec8e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60161770"
---
# <a name="let-users-reset-their-own-passwords"></a>允许用户重置自己的密码

作为Microsoft 365管理员，你可以让用户使用自助服务密码重置工具，这样[](https://go.microsoft.com/fwlink/p/?LinkId=522677)你就不必重置其密码。 减少工作量！
  
## <a name="before-you-begin"></a>准备工作
  
- 你可以免费为云用户重置自助服务密码 **，Microsoft 365商业**、教育或非营利组织付费计划。 它不能与试用版Microsoft 365一。

- 该功能使用 Azure。将在执行下面的步骤时，自动在 Azure 中 **免费** 获得此功能。如果不使用其他 Azure 功能，则不需要支付任何费用即可启用自助密码重置功能。

- **如果你使用的是本地 Active Directory，** 则上述两点不适用。 相反，你可以进行设置，**但需要付费订阅** 才能Azure AD Premium。

本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？](../../business-video/admin-center-overview.md)

您必须是全局 [管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。

## <a name="watch-let-users-reset-their-own-passwords"></a>观看：让用户重置自己的密码

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](../../business-video/index.yml)。

## <a name="steps-let-people-reset-their-own-passwords"></a>步骤：让用户重置自己的密码

以下步骤将为企业中的所有人启用自助密码重置。

1. 在管理 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">中心</a>中，转到  >  **"设置"组织设置"** 页面。

2. 在"组织设置"页 **的顶部** ，选择"安全& **隐私"** 选项卡。
  
3. 选择 **"自助密码重置"。**

4. 在 **"自助服务密码重置"下**，选择"转到 Azure 门户"以打开 **自助服务密码重置**。

5. 在"**属性"****页上，选择**"全部"为企业中的每个人启用它，然后选择"保存 **"。**
  
6. 当用户登录时，系统将提示用户输入其他联系人信息，以帮助他们在将来重置密码。

## <a name="related-content"></a>相关内容

[设置组织的密码过期策略 (](../manage/set-password-expiration-policy.md) 文章) \
[将个人用户密码设置为永不过期](set-password-to-never-expire.md)（文章）\
[Microsoft 365业务培训视频 (](../../business-video/index.yml)链接页) 
