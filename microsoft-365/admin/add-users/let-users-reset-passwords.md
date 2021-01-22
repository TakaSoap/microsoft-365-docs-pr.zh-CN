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
localization_priority: Normal
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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 了解如何使用自助服务密码重置工具重置密码。
ms.openlocfilehash: c777b9d840e0e9e467c1283fff94eca9a061ee73
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49925550"
---
# <a name="let-users-reset-their-own-passwords"></a>允许用户重置自己的密码

作为 Microsoft 365 管理员，你可以允许用户使用[](https://go.microsoft.com/fwlink/p/?LinkId=522677)自助服务密码重置工具，因此不必重置其密码。 减少工作量！
  
## <a name="before-you-begin"></a>准备工作
  
- 通过任何 Microsoft 365商业版、教育版或非盈利性付费计划，你可以免费为云用户重置自助服务密码。 它不能与 Microsoft 365 试用版一起使用。

- 该功能使用 Azure。将在执行下面的步骤时，自动在 Azure 中 **免费** 获得此功能。如果不使用其他 Azure 功能，则不需要支付任何费用即可启用自助密码重置功能。

- **如果使用的是本地 Active Directory，** 则上述两点不适用。 相反，你可以设置它， **但它需要 Azure AD Premium** 的付费订阅。

本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？](../admin-overview/admin-overview.md)

您必须是全局 [管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。

## <a name="watch-let-users-reset-their-own-passwords"></a>观看：让用户重置自己的密码

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

如果你发现此视频有帮助，请查看[适用于小型企业和 Microsoft 365 新用户的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="steps-let-people-reset-their-own-passwords"></a>步骤：让用户重置自己的密码

以下步骤将为企业中的所有人启用自助密码重置。
  
::: moniker range="o365-worldwide"

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>， **转到"设置** > **组织设置"** 页。

::: moniker-end

::: moniker range="o365-germany"

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>，转到"设置 \> **安全性 &amp; "隐私** 页面。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>，**转到"设置** \> **设置** \> **安全性 &amp; "隐私** 页面。

::: moniker-end

2. 在"组织设置" **页的顶部** ，选择"安全& **隐私"** 选项卡。
  
3. 选择 **"自助服务密码重置"。**

4. 在 **"自助服务密码重置"下**，选择"转到 Azure 门户"以 **启用自助服务密码重置**。

5. 在左侧导航窗格中，**选择"** 用户"，然后在"用户"| **所有用户页面**，选择 **"密码重置"。**
  
6. 在"**属性**"**页上，选择**"全部"为企业中的每个人启用它，然后选择"保存 **"。**
  
7. 当用户登录时，系统将提示他们输入其他联系人信息，以帮助他们在将来重置密码。

## <a name="related-content"></a>相关内容

[为组织设置密码过期策略](../manage/set-password-expiration-policy.md)

[将个人用户密码设置为永不过期](set-password-to-never-expire.md)

[Microsoft 365 商业版培训视频](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
