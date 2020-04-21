---
title: 解决许可证冲突
f1.keywords:
- NOCSH
ms.author: cmcatee
author: cmcatee-MSFT
manager: mnirkhe
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
- BEA160
ms.assetid: 796f7eda-b1f8-479a-adee-bd9226ca47ec
description: 了解如何解决与 Microsoft 365 for business 订阅的许可证冲突。
ms.openlocfilehash: 51f87c055402d9e6e3bd732a99abf2c155887290
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43628084"
---
# <a name="resolve-license-conflicts"></a><span data-ttu-id="c9272-103">解决许可证冲突</span><span class="sxs-lookup"><span data-stu-id="c9272-103">Resolve license conflicts</span></span>

<span data-ttu-id="c9272-104">我们建议您在创建新用户之前购买订阅所需的许可证。</span><span class="sxs-lookup"><span data-stu-id="c9272-104">We recommend that you buy the licenses that you need for your subscription before you create new users.</span></span> <span data-ttu-id="c9272-105">通过这种方式，可在创建用户帐户时，将许可证分配给新用户。</span><span class="sxs-lookup"><span data-stu-id="c9272-105">That way, a license can be assigned to new users as user accounts are created.</span></span> <span data-ttu-id="c9272-106">如果你已将所有许可证分配给了用户，但一些许可证已经过期，或者你尝试删除已分配给某用户的许可证，将出现许可证冲突。</span><span class="sxs-lookup"><span data-stu-id="c9272-106">If you have already assigned all of your licenses to users, but some of the licenses have expired, or you try to remove a license that is already assigned to a user, you will have license conflicts.</span></span> <span data-ttu-id="c9272-107">有关详细信息，请参阅[从订阅中删除许可证](../../commerce/licenses/remove-licenses-from-subscription.md)。</span><span class="sxs-lookup"><span data-stu-id="c9272-107">For more information, see [Remove licenses from your subscription](../../commerce/licenses/remove-licenses-from-subscription.md).</span></span>
  
## <a name="how-do-i-view-license-conflicts"></a><span data-ttu-id="c9272-108">如何查看许可证冲突？</span><span class="sxs-lookup"><span data-stu-id="c9272-108">How do I view license conflicts?</span></span>

::: moniker range="o365-worldwide"

1. <span data-ttu-id="c9272-109">在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="c9272-109">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=842264" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-germany"

1. <span data-ttu-id="c9272-110">在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="c9272-110">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=848038" target="_blank">Licenses</a> page.</span></span>

::: moniker-end

::: moniker range="o365-21vianet"

1. <span data-ttu-id="c9272-111">在管理中心，转到 "**记帐** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">许可证</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="c9272-111">In the admin center, go to the **Billing** > <a href="https://go.microsoft.com/fwlink/p/?linkid=850625" target="_blank">Licenses</a> page.</span></span>

::: moniker-end


2. <span data-ttu-id="c9272-112">检查" **状态**"列以查看冲突信息。</span><span class="sxs-lookup"><span data-stu-id="c9272-112">Check the **Status** column for information about the conflict.</span></span> <span data-ttu-id="c9272-113">如果存在冲突，您将看到一条警告消息，指出一个或多个用户需要有效的许可证。</span><span class="sxs-lookup"><span data-stu-id="c9272-113">If there's a conflict, you'll see a warning message, that says one or more users need a valid license.</span></span>

    > [!NOTE]
    > <span data-ttu-id="c9272-114">如果没有冲突，则不会看到" **状态**"列。</span><span class="sxs-lookup"><span data-stu-id="c9272-114">You won't see the **Status** column if there are no conflicts.</span></span>

## <a name="how-do-i-resolve-license-conflicts"></a><span data-ttu-id="c9272-115">如何解决许可证冲突？</span><span class="sxs-lookup"><span data-stu-id="c9272-115">How do I resolve license conflicts?</span></span>

<span data-ttu-id="c9272-116">您可以通过[购买更多许可证](../../commerce/licenses/buy-licenses.md)或[从不再需要这些许可证的用户那里删除许可证](remove-licenses-from-users.md)来解决许可证冲突。</span><span class="sxs-lookup"><span data-stu-id="c9272-116">You can resolve license conflicts by either [buying more licenses](../../commerce/licenses/buy-licenses.md) or by [removing licenses from users who no longer need them](remove-licenses-from-users.md).</span></span> <span data-ttu-id="c9272-117">你可以根据需要[删除用户帐户以空出许可证](../add-users/delete-a-user.md)。</span><span class="sxs-lookup"><span data-stu-id="c9272-117">You can optionally [delete a user account to free a license](../add-users/delete-a-user.md).</span></span>
  
## <a name="related-articles"></a><span data-ttu-id="c9272-118">相关文章</span><span class="sxs-lookup"><span data-stu-id="c9272-118">Related articles</span></span> 

[<span data-ttu-id="c9272-119">向用户分配许可证</span><span class="sxs-lookup"><span data-stu-id="c9272-119">Assign licenses to users</span></span>](assign-licenses-to-users.md)
  
[<span data-ttu-id="c9272-120">删除用户许可证</span><span class="sxs-lookup"><span data-stu-id="c9272-120">Remove licenses from users</span></span>](remove-licenses-from-users.md)
