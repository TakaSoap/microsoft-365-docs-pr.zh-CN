---
title: 应用程序控制入门
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 12df7b074019ea47f2e293b71c6b0b25fe46f66f
ms.sourcegitcommit: 63887d742c59cc660fc85537b335e98a9dc66fbe
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/18/2020
ms.locfileid: "45170685"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="ed3f9-103">应用程序控制入门</span><span class="sxs-lookup"><span data-stu-id="ed3f9-103">Get started with app control</span></span>

<span data-ttu-id="ed3f9-104">在您的环境中启用应用程序控制之前，请务必查看并了解[Microsoft 托管桌面如何实现 it](../service-description/app-control.md)以及您的角色和职责。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="ed3f9-105">Microsoft 托管桌面通过解决获取安全基准策略的更具挑战性的方面，简化了应用程序控制。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="ed3f9-106">您的 IT 管理员仍必须在测试环中测试您的应用程序，并查看日志中的任何警告或错误。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="ed3f9-107">如果应用需要豁免，则可以对请求进行存档，也可以根据首先检测到的用户，Microsoft 托管桌面操作可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="ed3f9-108">应用程序的初始部署</span><span class="sxs-lookup"><span data-stu-id="ed3f9-108">Initial deployment of apps</span></span>

<span data-ttu-id="ed3f9-109">首次部署应用时，Microsoft 托管桌面需要评估其当前行为。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="ed3f9-110">启用应用程序控制的具体步骤取决于是否已在您的环境中部署设备。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="ed3f9-111">设备已在使用中</span><span class="sxs-lookup"><span data-stu-id="ed3f9-111">Devices already in use</span></span>

<span data-ttu-id="ed3f9-112">如果已有至少一个 Microsoft 托管桌面设备在使用中，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ed3f9-112">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="ed3f9-113">打开包含 Microsoft 托管桌面操作的服务票证，请求我们启用应用程序控制。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-113">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="ed3f9-114">操作将向所有设备部署[审核策略](../service-description/app-control.md#audit-policy)。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-114">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="ed3f9-115">[测试应用程序](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app)以查看是否有任何将被阻止。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-115">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="ed3f9-116">如果某个应用程序将被阻止，请打开一个[签署人请求](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-116">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="ed3f9-117">完成测试后（无论结果如何），通知操作，记下任何待处理的签名者请求。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-117">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="ed3f9-118">按照此计划，操作将逐步将策略部署到部署组：</span><span class="sxs-lookup"><span data-stu-id="ed3f9-118">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="ed3f9-119">部署组</span><span class="sxs-lookup"><span data-stu-id="ed3f9-119">Deployment group</span></span>  |<span data-ttu-id="ed3f9-120">策略类型</span><span class="sxs-lookup"><span data-stu-id="ed3f9-120">Policy type</span></span>  |<span data-ttu-id="ed3f9-121">Timing</span><span class="sxs-lookup"><span data-stu-id="ed3f9-121">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ed3f9-122">测试</span><span class="sxs-lookup"><span data-stu-id="ed3f9-122">Test</span></span>     |  <span data-ttu-id="ed3f9-123">Audit</span><span class="sxs-lookup"><span data-stu-id="ed3f9-123">Audit</span></span>       |  <span data-ttu-id="ed3f9-124">第0天</span><span class="sxs-lookup"><span data-stu-id="ed3f9-124">Day 0</span></span>       |
|<span data-ttu-id="ed3f9-125">First</span><span class="sxs-lookup"><span data-stu-id="ed3f9-125">First</span></span>     | <span data-ttu-id="ed3f9-126">Enforced</span><span class="sxs-lookup"><span data-stu-id="ed3f9-126">Enforced</span></span>        | <span data-ttu-id="ed3f9-127">第 1 天</span><span class="sxs-lookup"><span data-stu-id="ed3f9-127">Day 1</span></span>        |
|<span data-ttu-id="ed3f9-128">快速</span><span class="sxs-lookup"><span data-stu-id="ed3f9-128">Fast</span></span>     | <span data-ttu-id="ed3f9-129">Enforced</span><span class="sxs-lookup"><span data-stu-id="ed3f9-129">Enforced</span></span>        |  <span data-ttu-id="ed3f9-130">第 3 天</span><span class="sxs-lookup"><span data-stu-id="ed3f9-130">Day 3</span></span>       |
|<span data-ttu-id="ed3f9-131">宽泛</span><span class="sxs-lookup"><span data-stu-id="ed3f9-131">Broad</span></span>     | <span data-ttu-id="ed3f9-132">Enforced</span><span class="sxs-lookup"><span data-stu-id="ed3f9-132">Enforced</span></span>        |  <span data-ttu-id="ed3f9-133">第 7 天</span><span class="sxs-lookup"><span data-stu-id="ed3f9-133">Day 7</span></span>       |

<span data-ttu-id="ed3f9-134">在首次部署期间，您始终可以打开另一个服务请求以暂停或回滚此部署的部分。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-134">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="ed3f9-135">尚未使用的设备</span><span class="sxs-lookup"><span data-stu-id="ed3f9-135">Devices not yet in use</span></span>

<span data-ttu-id="ed3f9-136">如果你还没有使用任何设备，请使用 Microsoft 托管桌面操作打开一个服务票证，请求我们启用应用程序控制。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-136">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="ed3f9-137">按照此计划，操作将逐步将策略部署到部署组：</span><span class="sxs-lookup"><span data-stu-id="ed3f9-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="ed3f9-138">部署组</span><span class="sxs-lookup"><span data-stu-id="ed3f9-138">Deployment group</span></span>  |<span data-ttu-id="ed3f9-139">策略类型</span><span class="sxs-lookup"><span data-stu-id="ed3f9-139">Policy type</span></span>  |<span data-ttu-id="ed3f9-140">Timing</span><span class="sxs-lookup"><span data-stu-id="ed3f9-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="ed3f9-141">测试</span><span class="sxs-lookup"><span data-stu-id="ed3f9-141">Test</span></span>     |  <span data-ttu-id="ed3f9-142">Audit</span><span class="sxs-lookup"><span data-stu-id="ed3f9-142">Audit</span></span>       |  <span data-ttu-id="ed3f9-143">第0天</span><span class="sxs-lookup"><span data-stu-id="ed3f9-143">Day 0</span></span>       |
|<span data-ttu-id="ed3f9-144">First</span><span class="sxs-lookup"><span data-stu-id="ed3f9-144">First</span></span>     | <span data-ttu-id="ed3f9-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="ed3f9-145">Enforced</span></span>        | <span data-ttu-id="ed3f9-146">第 1 天</span><span class="sxs-lookup"><span data-stu-id="ed3f9-146">Day 1</span></span>        |
|<span data-ttu-id="ed3f9-147">快速</span><span class="sxs-lookup"><span data-stu-id="ed3f9-147">Fast</span></span>     | <span data-ttu-id="ed3f9-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="ed3f9-148">Enforced</span></span>        |  <span data-ttu-id="ed3f9-149">第 3 天</span><span class="sxs-lookup"><span data-stu-id="ed3f9-149">Day 3</span></span>       |
|<span data-ttu-id="ed3f9-150">宽泛</span><span class="sxs-lookup"><span data-stu-id="ed3f9-150">Broad</span></span>     | <span data-ttu-id="ed3f9-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="ed3f9-151">Enforced</span></span>        |  <span data-ttu-id="ed3f9-152">第 7 天</span><span class="sxs-lookup"><span data-stu-id="ed3f9-152">Day 7</span></span>       |

<span data-ttu-id="ed3f9-153">在首次部署期间，您始终可以打开另一个服务请求以暂停或回滚此部署的部分。</span><span class="sxs-lookup"><span data-stu-id="ed3f9-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

