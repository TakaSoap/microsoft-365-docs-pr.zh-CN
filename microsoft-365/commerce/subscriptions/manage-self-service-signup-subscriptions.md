---
title: 管理自助服务注册订阅
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: scotv
ms.reviewer: jkinma, jmueller
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- commerce_subscriptions
search.appverid: MET150
description: 了解如何管理组织的免费自助注册订阅。
ms.date: 03/17/2021
ms.openlocfilehash: b469515a649399c71ef64ba2567dfa376f21e9a7
ms.sourcegitcommit: 967f64dfa1a05f31179c8316b96bfb7758a5d990
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/12/2021
ms.locfileid: "52333214"
---
# <a name="manage-self-service-sign-up-subscriptions"></a><span data-ttu-id="047da-103">管理自助服务注册订阅</span><span class="sxs-lookup"><span data-stu-id="047da-103">Manage self-service sign-up subscriptions</span></span>

## <a name="what-are-self-service-sign-up-subscriptions"></a><span data-ttu-id="047da-104">什么是自助服务注册订阅？</span><span class="sxs-lookup"><span data-stu-id="047da-104">What are self-service sign-up subscriptions?</span></span>

<span data-ttu-id="047da-105">您的组织中的用户可以注册有限数量的免费自助注册订阅。</span><span class="sxs-lookup"><span data-stu-id="047da-105">There are a limited number of free self-service sign-up subscriptions available for users in your organization to sign up for.</span></span> <span data-ttu-id="047da-106">用户只能自行注册和使用自助注册订阅。</span><span class="sxs-lookup"><span data-stu-id="047da-106">A user can only sign up for and use a self-service sign-up subscription for themselves.</span></span> <span data-ttu-id="047da-107">通过阻止用户注册以及删除用户已注册的免费订阅，你可以管理自助服务注册订阅。</span><span class="sxs-lookup"><span data-stu-id="047da-107">You manage self-service sign-up subscriptions by blocking users from signing up, and by deleting free subscriptions that users have signed up for.</span></span> <span data-ttu-id="047da-108">有关自助注册和可用订阅的信息，请参阅在组织中使用自助服务 [注册](../../admin/misc/self-service-sign-up.md)。</span><span class="sxs-lookup"><span data-stu-id="047da-108">For more information about self-service sign up and the available subscriptions, see [Using self-service sign up in your organization](../../admin/misc/self-service-sign-up.md).</span></span>

## <a name="view-a-list-of-self-service-sign-up-subscriptions"></a><span data-ttu-id="047da-109">查看自助服务注册订阅列表</span><span class="sxs-lookup"><span data-stu-id="047da-109">View a list of self-service sign-up subscriptions</span></span>

1. <span data-ttu-id="047da-110">在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="047da-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="047da-111">在"**产品"** 选项卡上，选择筛选器图标，然后选择"免费 **"。**</span><span class="sxs-lookup"><span data-stu-id="047da-111">On the **Products** tab, select the filter icon, then select **Free**.</span></span> <span data-ttu-id="047da-112">将显示所有自助注册订阅的列表。</span><span class="sxs-lookup"><span data-stu-id="047da-112">A list of all self-service sign-up subscriptions is displayed.</span></span>

## <a name="how-are-these-subscriptions-different-from-self-service-purchase-subscriptions"></a><span data-ttu-id="047da-113">这些订阅与自助服务购买订阅如何不同？</span><span class="sxs-lookup"><span data-stu-id="047da-113">How are these subscriptions different from self-service purchase subscriptions?</span></span>

<span data-ttu-id="047da-114">自助服务注册订阅是免费的，可用于比自助服务购买订阅更大的产品列表。</span><span class="sxs-lookup"><span data-stu-id="047da-114">Self-service sign-up subscriptions are free and are available for a larger list of products than self-service purchase subscriptions.</span></span> <span data-ttu-id="047da-115">当用户注册自助服务购买订阅时，他们负责支付该订阅费用。</span><span class="sxs-lookup"><span data-stu-id="047da-115">When a user signs up for a self-service purchase subscription, they're responsible for paying for it.</span></span> <span data-ttu-id="047da-116">自助服务购买订阅仅适用于 Power BI、Power Apps 和 Power Automate (Power Automate) 、Project 和 Visio 等 Power Platform 产品。</span><span class="sxs-lookup"><span data-stu-id="047da-116">Self-service purchase subscriptions are only available for Power Platform products (Power BI, Power Apps, and Power Automate), Project, and Visio.</span></span> <span data-ttu-id="047da-117">有关详细信息，请参阅 [自助服务购买常见问题解答](self-service-purchase-faq.md)。</span><span class="sxs-lookup"><span data-stu-id="047da-117">For more information, see [Self-service purchase FAQ](self-service-purchase-faq.md).</span></span>

## <a name="block-users-from-signing-up"></a><span data-ttu-id="047da-118">阻止用户注册</span><span class="sxs-lookup"><span data-stu-id="047da-118">Block users from signing up</span></span>

<span data-ttu-id="047da-119">使用 [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet 和 **AllowAdHocSubscriptions** 参数控制用户是否可以注册自助注册订阅。</span><span class="sxs-lookup"><span data-stu-id="047da-119">You use the [**Set-MsolCompanySettings**](/powershell/module/msonline/set-msolcompanysettings?preserve-view=true&view=azureadps-1.0) cmdlet with the **AllowAdHocSubscriptions** parameter to control whether users can sign up for self-service sign-up subscriptions.</span></span> <span data-ttu-id="047da-120">有关详细信息，请参阅 [如何控制自助服务设置？](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span><span class="sxs-lookup"><span data-stu-id="047da-120">For more information, see [How do I control self-service settings?](/azure/active-directory/users-groups-roles/directory-self-service-signup#how-do-i-control-self-service-settings)</span></span>

## <a name="delete-a-self-service-sign-up-subscription"></a><span data-ttu-id="047da-121">删除自助服务注册订阅</span><span class="sxs-lookup"><span data-stu-id="047da-121">Delete a self-service sign-up subscription</span></span>

> [!IMPORTANT]
> <span data-ttu-id="047da-122">当您删除自助服务注册订阅时，将阻止所有用户访问其数据和电子邮件，并删除所有数据和电子邮件。</span><span class="sxs-lookup"><span data-stu-id="047da-122">When you delete a self-service sign-up subscription, you block all users from accessing their data and email and delete all data and email.</span></span>

1. <span data-ttu-id="047da-123">在管理中心中，转到“**账单**” > “<a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">你的产品</a>”页面。</span><span class="sxs-lookup"><span data-stu-id="047da-123">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842054" target="_blank">Your products</a> page.</span></span>
2. <span data-ttu-id="047da-124">在"**产品"** 选项卡上，选择筛选器图标，然后选择"免费 **"。**</span><span class="sxs-lookup"><span data-stu-id="047da-124">On the **Products** tab, select the filter icon, then select **Free**.</span></span>
3. <span data-ttu-id="047da-125">选择要删除的自助服务注册订阅。</span><span class="sxs-lookup"><span data-stu-id="047da-125">Select the self-service sign-up subscription that you want to delete.</span></span> 
4. <span data-ttu-id="047da-126">On the subscription details page， in the **Subscriptions and payment settings** section， select **Delete subscription**.</span><span class="sxs-lookup"><span data-stu-id="047da-126">On the subscription details page, in the **Subscriptions and payment settings** section, select **Delete subscription**.</span></span>
5. <span data-ttu-id="047da-127">在"**删除订阅"** 窗格中，选中复选框，然后选择"删除 **订阅"。**</span><span class="sxs-lookup"><span data-stu-id="047da-127">In the **Delete subscription** pane, select the check box, then select **Delete subscription**.</span></span>

## <a name="i-have-a-self-service-sign-up-subscription-that-blocks-directory-deletion"></a><span data-ttu-id="047da-128">我有一个自助式注册订阅，可阻止删除目录</span><span class="sxs-lookup"><span data-stu-id="047da-128">I have a self-service sign-up subscription that blocks directory deletion</span></span>

<span data-ttu-id="047da-129">单个用户可以注册的自助服务注册产品还可以在 Azure AD 目录中创建来宾用户进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="047da-129">The self-service sign-up products that individual users can sign up for also create a guest user for authentication in your Azure AD directory.</span></span> <span data-ttu-id="047da-130">为了避免数据丢失，这些自助式产品会阻止删除目录，直到从目录中完全删除。</span><span class="sxs-lookup"><span data-stu-id="047da-130">To avoid data loss, these self-service products block directory deletions until they're fully deleted from the directory.</span></span> <span data-ttu-id="047da-131">它们只能由 Azure AD 管理员删除。有关详细信息，请参阅删除 [Azure Active Directory 中的目录](/azure/active-directory/users-groups-roles/directory-delete-howto)。</span><span class="sxs-lookup"><span data-stu-id="047da-131">They can only be deleted by the Azure AD admin. For more information, see [Delete a directory in Azure Active Directory](/azure/active-directory/users-groups-roles/directory-delete-howto).</span></span>
