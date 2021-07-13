---
title: Microsoft 365 Lighthouse用户页面概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，请了解"用户"页面。
ms.openlocfilehash: 795e387850bd2945c4019cbb467de87fecc15f86
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53395019"
---
# <a name="microsoft-365-lighthouse-users-page-overview"></a><span data-ttu-id="45096-103">Microsoft 365 Lighthouse用户页面概述</span><span class="sxs-lookup"><span data-stu-id="45096-103">Microsoft 365 Lighthouse Users page overview</span></span> 

> [!NOTE]
> <span data-ttu-id="45096-104">本文中所述的功能在预览版中，可能会更改，并且仅对满足要求 [的合作伙伴可用](m365-lighthouse-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="45096-104">The features described in this article are in Preview, are subject to change, and are only available to partners who meet the [requirements](m365-lighthouse-requirements.md).</span></span> <span data-ttu-id="45096-105">如果你的组织没有此Microsoft 365 Lighthouse，请参阅[注册Microsoft 365 Lighthouse。](m365-lighthouse-sign-up.md)</span><span class="sxs-lookup"><span data-stu-id="45096-105">If your organization does not have Microsoft 365 Lighthouse, see [Sign up for Microsoft 365 Lighthouse](m365-lighthouse-sign-up.md).</span></span>

<span data-ttu-id="45096-106">Microsoft 365 Lighthouse通过选择左侧导航窗格中的"用户"打开"用户"页面，跨租户帐户管理用户。</span><span class="sxs-lookup"><span data-stu-id="45096-106">Microsoft 365 Lighthouse lets you manage users across tenant accounts by selecting **Users** in the left navigation pane to open the Users page.</span></span> <span data-ttu-id="45096-107">在此页中，可以搜索用户，并评估用户帐户的安全状态并采取行动。</span><span class="sxs-lookup"><span data-stu-id="45096-107">From this page, you can search for users and assess and act on the security state of your user accounts.</span></span> <span data-ttu-id="45096-108">您还可以查看风险用户的见解，以及多重身份验证和自助服务密码重置的状态。</span><span class="sxs-lookup"><span data-stu-id="45096-108">You can also view insights into risky users and the status of multifactor authentication and self-service password reset.</span></span>  
  
## <a name="search-users-tab"></a><span data-ttu-id="45096-109">"搜索用户"选项卡</span><span class="sxs-lookup"><span data-stu-id="45096-109">Search users tab</span></span>  
  
<span data-ttu-id="45096-110">从"搜索用户"选项卡中，可以跨租户快速搜索特定用户并执行基本用户管理操作，如重置帐户密码。</span><span class="sxs-lookup"><span data-stu-id="45096-110">From the Search users tab, you can quickly search across tenants for specific users and perform basic user management actions such as resetting an account password.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-search-users-tab.png" alt-text="&quot;搜索用户&quot;选项卡的屏幕截图。":::

## <a name="risky-users-tab"></a><span data-ttu-id="45096-112">"有风险的用户"选项卡</span><span class="sxs-lookup"><span data-stu-id="45096-112">Risky users tab</span></span>

<span data-ttu-id="45096-113">"风险用户"选项卡显示租户中已标记为存在风险行为的用户帐户。</span><span class="sxs-lookup"><span data-stu-id="45096-113">The Risky Users tab shows user accounts across your tenants that have been flagged for risky behavior.</span></span> <span data-ttu-id="45096-114">选择任意用户以查看检测到的风险详细信息，或者通过重置用户密码或阻止登录来缓解风险。</span><span class="sxs-lookup"><span data-stu-id="45096-114">Select any of the users to view more information on a detected risk or to mitigate a risk by resetting a user's password or blocking sign-in.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-risky-users-tab.png" alt-text="&quot;有风险的用户&quot;选项卡的屏幕截图。":::

## <a name="multifactor-authentication-tab"></a><span data-ttu-id="45096-116">"多重身份验证"选项卡</span><span class="sxs-lookup"><span data-stu-id="45096-116">Multifactor Authentication tab</span></span>

<span data-ttu-id="45096-117">The Multifactor Authentication tab provides detailed information on the status of multifactor authentication (MFA) enablement across your tenants.</span><span class="sxs-lookup"><span data-stu-id="45096-117">The Multifactor Authentication tab provides detailed information on the status of multifactor authentication (MFA) enablement across your tenants.</span></span> <span data-ttu-id="45096-118">选择列表中的任意租户以查看该租户的更多详细信息，包括已配置哪些需要 MFA 的条件访问策略，以及哪些用户尚未注册 MFA。</span><span class="sxs-lookup"><span data-stu-id="45096-118">Select any tenant in the list to see more details for that tenant, including which Conditional Access policies requiring MFA are already configured and which users have not yet registered for MFA.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-mfa-tab.png" alt-text="&quot;多重身份验证&quot;选项卡的屏幕截图。":::

## <a name="password-reset-tab"></a><span data-ttu-id="45096-120">密码重置选项卡</span><span class="sxs-lookup"><span data-stu-id="45096-120">Password reset tab</span></span>

<span data-ttu-id="45096-121">"密码重置"选项卡显示有关租户中自助服务密码重置启用状态的详细信息。</span><span class="sxs-lookup"><span data-stu-id="45096-121">The Password reset tab shows detailed information on the status of self-service password reset enablement across your tenants.</span></span>

:::image type="content" source="../media/m365-lighthouse-users-page-overview/users-password-reset-tab.png" alt-text="&quot;密码重置&quot;选项卡的屏幕截图。":::

## <a name="related-content"></a><span data-ttu-id="45096-123">相关内容</span><span class="sxs-lookup"><span data-stu-id="45096-123">Related content</span></span>

<span data-ttu-id="45096-124">[Microsoft 365 Lighthouse设备合规性页面概述 (](m365-lighthouse-device-compliance-page-overview.md)文章) </span><span class="sxs-lookup"><span data-stu-id="45096-124">[Microsoft 365 Lighthouse device compliance page overview](m365-lighthouse-device-compliance-page-overview.md) (article)</span></span>\
<span data-ttu-id="45096-125">[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) </span><span class="sxs-lookup"><span data-stu-id="45096-125">[Microsoft 365 Lighthouse FAQ](m365-lighthouse-faq.yml) (article)</span></span>
