---
title: 开始使用应用程序控制
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
ms.openlocfilehash: 431e6cb3b8d7ab7e1dd317918fab4821889c7d4e
ms.sourcegitcommit: 583fd1ac1f385c58b93bda648907a1bd8e0a1950
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "45430455"
---
# <a name="get-started-with-app-control"></a><span data-ttu-id="106e6-103">开始使用应用程序控制</span><span class="sxs-lookup"><span data-stu-id="106e6-103">Get started with app control</span></span>

<span data-ttu-id="106e6-104">在您的环境中启用应用程序控制之前，请务必查看并了解[Microsoft 托管桌面如何实现 it](../service-description/app-control.md)以及您的角色和职责。</span><span class="sxs-lookup"><span data-stu-id="106e6-104">Before you enable app control in your environment, be sure to review and understand [how Microsoft Managed Desktop implements it](../service-description/app-control.md) and your roles and responsibilities.</span></span>

<span data-ttu-id="106e6-105">Microsoft 托管桌面通过解决获取安全基准策略的更具挑战性的方面，简化了应用程序控制。</span><span class="sxs-lookup"><span data-stu-id="106e6-105">Microsoft Managed Desktop simplifies app control by taking care of the more challenging aspects of getting a secure base policy.</span></span> <span data-ttu-id="106e6-106">您的 IT 管理员仍必须在测试环中测试您的应用程序，并查看日志中的任何警告或错误。</span><span class="sxs-lookup"><span data-stu-id="106e6-106">Your IT Administrators must still test your apps in the Test ring and review the logs for any warnings or errors.</span></span> <span data-ttu-id="106e6-107">如果应用需要豁免，则可以对请求进行存档，也可以根据首先检测到的用户，Microsoft 托管桌面操作可能会发生此情况。</span><span class="sxs-lookup"><span data-stu-id="106e6-107">If an app needs an exemption, you can file a request, or Microsoft Managed Desktop Operation might, depending on who detects it first.</span></span>

## <a name="initial-deployment-of-apps"></a><span data-ttu-id="106e6-108">应用程序的初始部署</span><span class="sxs-lookup"><span data-stu-id="106e6-108">Initial deployment of apps</span></span>

<span data-ttu-id="106e6-109">首次部署应用时，Microsoft 托管桌面需要评估其当前行为。</span><span class="sxs-lookup"><span data-stu-id="106e6-109">When you first deploy apps, Microsoft Managed Desktop needs to assess their current behavior.</span></span> <span data-ttu-id="106e6-110">启用应用程序控制的具体步骤取决于是否已在您的环境中部署设备。</span><span class="sxs-lookup"><span data-stu-id="106e6-110">The exact steps for enabling app control depend on whether devices have already been deployed in your environment.</span></span>

### <a name="devices-not-yet-in-use"></a><span data-ttu-id="106e6-111">尚未使用的设备</span><span class="sxs-lookup"><span data-stu-id="106e6-111">Devices not yet in use</span></span>

<span data-ttu-id="106e6-112">如果你还没有使用任何设备，请使用 Microsoft 托管桌面操作打开一个服务票证，请求我们启用应用程序控制。</span><span class="sxs-lookup"><span data-stu-id="106e6-112">If you don't yet have any devices in use, open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="106e6-113">按照此计划，操作将逐步将策略部署到部署组：</span><span class="sxs-lookup"><span data-stu-id="106e6-113">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="106e6-114">部署组</span><span class="sxs-lookup"><span data-stu-id="106e6-114">Deployment group</span></span>  |<span data-ttu-id="106e6-115">策略类型</span><span class="sxs-lookup"><span data-stu-id="106e6-115">Policy type</span></span>  |<span data-ttu-id="106e6-116">Timing</span><span class="sxs-lookup"><span data-stu-id="106e6-116">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="106e6-117">测试</span><span class="sxs-lookup"><span data-stu-id="106e6-117">Test</span></span>     |  <span data-ttu-id="106e6-118">Audit</span><span class="sxs-lookup"><span data-stu-id="106e6-118">Audit</span></span>       |  <span data-ttu-id="106e6-119">第0天</span><span class="sxs-lookup"><span data-stu-id="106e6-119">Day 0</span></span>       |
|<span data-ttu-id="106e6-120">First</span><span class="sxs-lookup"><span data-stu-id="106e6-120">First</span></span>     | <span data-ttu-id="106e6-121">Enforced</span><span class="sxs-lookup"><span data-stu-id="106e6-121">Enforced</span></span>        | <span data-ttu-id="106e6-122">第 1 天</span><span class="sxs-lookup"><span data-stu-id="106e6-122">Day 1</span></span>        |
|<span data-ttu-id="106e6-123">快速</span><span class="sxs-lookup"><span data-stu-id="106e6-123">Fast</span></span>     | <span data-ttu-id="106e6-124">Enforced</span><span class="sxs-lookup"><span data-stu-id="106e6-124">Enforced</span></span>        |  <span data-ttu-id="106e6-125">第 2 天</span><span class="sxs-lookup"><span data-stu-id="106e6-125">Day 2</span></span>       |
|<span data-ttu-id="106e6-126">宽泛</span><span class="sxs-lookup"><span data-stu-id="106e6-126">Broad</span></span>     | <span data-ttu-id="106e6-127">Enforced</span><span class="sxs-lookup"><span data-stu-id="106e6-127">Enforced</span></span>        |  <span data-ttu-id="106e6-128">第 3 天</span><span class="sxs-lookup"><span data-stu-id="106e6-128">Day 3</span></span>       |

<span data-ttu-id="106e6-129">在首次部署期间，您始终可以打开另一个服务请求以暂停或回滚此部署的部分。</span><span class="sxs-lookup"><span data-stu-id="106e6-129">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>

### <a name="devices-already-in-use"></a><span data-ttu-id="106e6-130">设备已在使用中</span><span class="sxs-lookup"><span data-stu-id="106e6-130">Devices already in use</span></span>

<span data-ttu-id="106e6-131">如果已有至少一个 Microsoft 托管桌面设备在使用中，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="106e6-131">If already have at least one Microsoft Managed Desktop device in use, follow these steps:</span></span>

1. <span data-ttu-id="106e6-132">打开包含 Microsoft 托管桌面操作的服务票证，请求我们启用应用程序控制。</span><span class="sxs-lookup"><span data-stu-id="106e6-132">Open a service ticket with Microsoft Managed Desktop Operations requesting that we turn on app control.</span></span> <span data-ttu-id="106e6-133">操作将向所有设备部署[审核策略](../service-description/app-control.md#audit-policy)。</span><span class="sxs-lookup"><span data-stu-id="106e6-133">Operations will deploy an [Audit policy](../service-description/app-control.md#audit-policy) to all devices.</span></span>
2. <span data-ttu-id="106e6-134">[测试应用程序](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app)以查看是否有任何将被阻止。</span><span class="sxs-lookup"><span data-stu-id="106e6-134">[Test your applications](../working-with-managed-desktop/work-with-app-control.md#add-a-new-app) to see if any would be blocked.</span></span> <span data-ttu-id="106e6-135">如果某个应用程序将被阻止，请打开一个[签署人请求](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer)。</span><span class="sxs-lookup"><span data-stu-id="106e6-135">If an application would be blocked, open a [signer request](../working-with-managed-desktop/work-with-app-control.md#add-or-remove-a-trusted-signer).</span></span> 
3. <span data-ttu-id="106e6-136">完成测试后（无论结果如何），通知操作，记下任何待处理的签名者请求。</span><span class="sxs-lookup"><span data-stu-id="106e6-136">Once you have completed your testing (whatever the results), notify Operations, noting any pending signer requests.</span></span> <span data-ttu-id="106e6-137">按照此计划，操作将逐步将策略部署到部署组：</span><span class="sxs-lookup"><span data-stu-id="106e6-137">Operations will progressively deploy policies to deployment groups following this schedule:</span></span>

|<span data-ttu-id="106e6-138">部署组</span><span class="sxs-lookup"><span data-stu-id="106e6-138">Deployment group</span></span>  |<span data-ttu-id="106e6-139">策略类型</span><span class="sxs-lookup"><span data-stu-id="106e6-139">Policy type</span></span>  |<span data-ttu-id="106e6-140">Timing</span><span class="sxs-lookup"><span data-stu-id="106e6-140">Timing</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="106e6-141">测试</span><span class="sxs-lookup"><span data-stu-id="106e6-141">Test</span></span>     |  <span data-ttu-id="106e6-142">Audit</span><span class="sxs-lookup"><span data-stu-id="106e6-142">Audit</span></span>       |  <span data-ttu-id="106e6-143">第0天</span><span class="sxs-lookup"><span data-stu-id="106e6-143">Day 0</span></span>       |
|<span data-ttu-id="106e6-144">First</span><span class="sxs-lookup"><span data-stu-id="106e6-144">First</span></span>     | <span data-ttu-id="106e6-145">Enforced</span><span class="sxs-lookup"><span data-stu-id="106e6-145">Enforced</span></span>        | <span data-ttu-id="106e6-146">第 1 天</span><span class="sxs-lookup"><span data-stu-id="106e6-146">Day 1</span></span>        |
|<span data-ttu-id="106e6-147">快速</span><span class="sxs-lookup"><span data-stu-id="106e6-147">Fast</span></span>     | <span data-ttu-id="106e6-148">Enforced</span><span class="sxs-lookup"><span data-stu-id="106e6-148">Enforced</span></span>        |  <span data-ttu-id="106e6-149">已暂停，在请求时进行部署</span><span class="sxs-lookup"><span data-stu-id="106e6-149">Paused, rollout on request</span></span>       |
|<span data-ttu-id="106e6-150">宽泛</span><span class="sxs-lookup"><span data-stu-id="106e6-150">Broad</span></span>     | <span data-ttu-id="106e6-151">Enforced</span><span class="sxs-lookup"><span data-stu-id="106e6-151">Enforced</span></span>        |  <span data-ttu-id="106e6-152">已暂停，在请求时进行部署</span><span class="sxs-lookup"><span data-stu-id="106e6-152">Paused, rollout on request</span></span>       |

<span data-ttu-id="106e6-153">在首次部署期间，您始终可以打开另一个服务请求以暂停或回滚此部署的部分。</span><span class="sxs-lookup"><span data-stu-id="106e6-153">You can always open another service request to pause or roll back part of this deployment at any time during the rollout.</span></span>



