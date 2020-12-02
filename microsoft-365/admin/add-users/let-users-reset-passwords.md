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
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 5bc3f460-13cc-48c0-abd6-b80bae72d04a
description: 了解如何使用自助密码重置工具来重置密码。
ms.openlocfilehash: bbde517858186d844412aca21f231620ed76496a
ms.sourcegitcommit: 38d828ae8d4350ae774a939c8decf30cb36c3bea
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49551916"
---
# <a name="let-users-reset-their-own-passwords"></a>允许用户重置自己的密码

作为 Microsoft 365 管理员，你可以让用户使用 [自助密码重置工具](https://go.microsoft.com/fwlink/p/?LinkId=522677) ，这样你就不必重置它们的密码。 减少工作量！
  
## <a name="before-you-begin"></a>准备工作
  
- 通过任何 Microsoft 365 商业版、教育版或非盈利的计划 **免费** 为云用户获取自助服务密码重置。 它不适用于 Microsoft 365 试用版。

- 该功能使用 Azure。将在执行下面的步骤时，自动在 Azure 中 **免费** 获得此功能。如果不使用其他 Azure 功能，则不需要支付任何费用即可启用自助密码重置功能。

- **如果使用的是本地 Active Directory**，则不适用以上两个点。 相反，您可以对此进行设置，但 **需要付费的 AZURE AD Premium 订阅**。

本文面向的是为企业、学校或非营利组织设置密码过期策略的人员。 若要完成这些步骤，你需要使用 Microsoft 365 管理员帐户登录。 [什么是管理员帐户？](../admin-overview/admin-overview.md)

您必须是 [全局管理员或密码管理员](about-admin-roles.md) 才能执行这些步骤。

## <a name="watch-let-users-reset-their-own-passwords"></a>手表：让用户重置自己的密码

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3AY8S]

如果你觉得这段视频有用，请查看[适用于小型企业和 Microsoft 365 新手的完整培训系列](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)。

## <a name="steps-let-people-reset-their-own-passwords"></a>步骤：让用户重置自己的密码

以下步骤将为企业中的所有人启用自助密码重置。
  
::: moniker range="o365-worldwide"

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2024339" target="_blank">管理中心</a>中，转到 " **设置** > **组织设置** " 页。

::: moniker-end

::: moniker range="o365-germany"

1. 在 " <a href="https://go.microsoft.com/fwlink/p/?linkid=848041" target="_blank">管理中心</a>" 中，转到 " **设置** \> **安全 &amp; 隐私** " 页。

::: moniker-end

::: moniker range="o365-21vianet"

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=850627" target="_blank">管理中心</a>中，转到 "**设置** \> **设置** \> **安全 &amp; 隐私**" 页。

::: moniker-end

2. 在 " **组织设置** " 页的顶部，选择 " **安全性" & "隐私** " 选项卡。
  
3. 选择 " **自助密码重置**"。

4. 在 " **自助密码重置**" 下，选择 **"转到 Azure 门户" 以启用自助密码重置**。

5. 在左侧导航窗格中，选择 " **用户**"，然后在 " **用户" | ""所有用户** " 页上，选择 " **密码重置**"。
  
6. 在 " **属性** " 页上，选择 " **全部** " 以为企业中的所有人启用它，然后选择 " **保存**"。
  
7. 当用户登录时，系统会提示他们输入其他联系人信息，这将帮助他们将来重置其密码。

## <a name="related-content"></a>相关内容

[为组织设置密码过期策略](../manage/set-password-expiration-policy.md)

[将个人用户密码设置为永不过期](set-password-to-never-expire.md)

[Microsoft 365 商业版培训视频](https://support.microsoft.com/office/6ab4bbcd-79cf-4000-a0bd-d42ce4d12816)
