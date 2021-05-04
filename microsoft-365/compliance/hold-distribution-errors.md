---
title: 解决电子数据展示保留错误
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
description: 解决与核心电子数据展示中应用于保管人和非监管数据源的法律保留相关的错误。
ms.openlocfilehash: 3bd417f2eb6bfb8de8d4b5ccaeb48e6ae1c888eb
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860383"
---
# <a name="troubleshoot-ediscovery-hold-errors"></a><span data-ttu-id="83a35-103">解决电子数据展示保留错误</span><span class="sxs-lookup"><span data-stu-id="83a35-103">Troubleshoot eDiscovery hold errors</span></span>

<span data-ttu-id="83a35-104">本文讨论电子数据展示保留中可能会出现的常见问题以及如何解决这些问题。</span><span class="sxs-lookup"><span data-stu-id="83a35-104">This article discusses common issues that may occur with eDiscovery holds and how to resolve them.</span></span> <span data-ttu-id="83a35-105">本文还包括帮助您缓解或避免这些问题的建议做法。</span><span class="sxs-lookup"><span data-stu-id="83a35-105">The article also includes recommended practices to help you mitigate or avoid these issues.</span></span>

## <a name="recommended-practices"></a><span data-ttu-id="83a35-106">建议的做法</span><span class="sxs-lookup"><span data-stu-id="83a35-106">Recommended practices</span></span>

<span data-ttu-id="83a35-107">若要减少与电子数据展示保留相关的错误数，建议采用以下做法：</span><span class="sxs-lookup"><span data-stu-id="83a35-107">To reduce the number of errors related to eDiscovery holds, we recommend the following practices:</span></span>

- <span data-ttu-id="83a35-108">如果保留分发仍处于待定状态，状态为 或 ，请等到保留分发完成，然后再 `On (Pending)` `Off (Pending)` 进行进一步更新。</span><span class="sxs-lookup"><span data-stu-id="83a35-108">If a hold distribution is still pending, with a status of either `On (Pending)` or `Off (Pending)`, wait until the hold distribution is complete before you make any further updates.</span></span>

- <span data-ttu-id="83a35-109">将更新合并到单个批量请求中的电子数据展示保留，而不是针对每个事务重复更新保留策略。</span><span class="sxs-lookup"><span data-stu-id="83a35-109">Merge your updates to an eDiscovery hold in a single bulk request rather than updating the hold policy repeatedly for each transaction.</span></span> <span data-ttu-id="83a35-110">例如，若要使用 [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet 将多个用户邮箱添加到现有保留策略，请运行命令 (或将 作为代码块添加到脚本) 以便它只运行一次以添加多个用户。</span><span class="sxs-lookup"><span data-stu-id="83a35-110">For example, to add multiple user mailboxes to an existing hold policy using the [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet, run the command (or add as a code block to a script) so that it runs only once to add multiple users.</span></span>

  <span data-ttu-id="83a35-111">**正确**</span><span class="sxs-lookup"><span data-stu-id="83a35-111">**Correct**</span></span>

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   <span data-ttu-id="83a35-112">**错误**</span><span class="sxs-lookup"><span data-stu-id="83a35-112">**Incorrect**</span></span>

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   <span data-ttu-id="83a35-113">在上一错误示例中，cmdlet 将单独运行五次以完成任务。</span><span class="sxs-lookup"><span data-stu-id="83a35-113">In the previous incorrect example, the cmdlet is run five separate times to complete the task.</span></span> <span data-ttu-id="83a35-114">有关将用户添加到保留策略的建议做法详细信息，请参阅 [详细信息](#more-information) 部分。</span><span class="sxs-lookup"><span data-stu-id="83a35-114">For more information about the recommended practices for adding users to a hold policy, see the [More information](#more-information) section.</span></span>

- <span data-ttu-id="83a35-115">在就电子数据展示保留问题与 Microsoft 支持部门联系之前，请按照错误 [/问题：保留不同步](#errorissue-holds-dont-sync) 部分中的步骤重试保留分配。</span><span class="sxs-lookup"><span data-stu-id="83a35-115">Before contacting Microsoft Support about eDiscovery hold issues, follow the steps in the [Error/issue: Holds don't sync](#errorissue-holds-dont-sync) section to retry the hold distribution.</span></span> <span data-ttu-id="83a35-116">此过程通常会解决临时问题，包括内部服务器错误。</span><span class="sxs-lookup"><span data-stu-id="83a35-116">This process often resolves temporary issues including, internal server errors.</span></span>

## <a name="errorissue-holds-dont-sync"></a><span data-ttu-id="83a35-117">错误/问题：保留未同步</span><span class="sxs-lookup"><span data-stu-id="83a35-117">Error/issue: Holds don't sync</span></span>

<span data-ttu-id="83a35-118">如果将保管人和数据源置于保留状态时看到以下错误消息之一，请使用解决方案步骤解决问题。</span><span class="sxs-lookup"><span data-stu-id="83a35-118">If you see one the following error messages when putting custodians and data sources on hold, use the resolution steps to troubleshoot the issue.</span></span>

> <span data-ttu-id="83a35-119">资源：部署策略所花时间超过预期。</span><span class="sxs-lookup"><span data-stu-id="83a35-119">Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="83a35-120">更新最终部署状态可能需要 2 小时，因此请在几小时后重新检查。</span><span class="sxs-lookup"><span data-stu-id="83a35-120">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

> <span data-ttu-id="83a35-121">由于临时部署数据中心问题，无法将策略Office 365内容源。</span><span class="sxs-lookup"><span data-stu-id="83a35-121">Policy cannot be deployed to the content source due to a temporary Office 365 datacenter issue.</span></span> <span data-ttu-id="83a35-122">当前策略不会应用于源中任何内容，因此阻止的部署没有影响。</span><span class="sxs-lookup"><span data-stu-id="83a35-122">The current policy is not applied to any content in the source, so there's no impact from the blocked deployment.</span></span> <span data-ttu-id="83a35-123">若要解决此问题，请尝试重新部署策略。</span><span class="sxs-lookup"><span data-stu-id="83a35-123">To fix this issue, please try redeploying the policy.</span></span>

> <span data-ttu-id="83a35-124">很抱歉，由于暂时性内部服务器错误，我们无法执行请求的策略更改。</span><span class="sxs-lookup"><span data-stu-id="83a35-124">Sorry, we could not perform the requested changes to policy due to a transient internal server error.</span></span> <span data-ttu-id="83a35-125">请在 30 分钟后重试。</span><span class="sxs-lookup"><span data-stu-id="83a35-125">Please try again in 30 minutes.</span></span>

### <a name="resolution"></a><span data-ttu-id="83a35-126">解决方案</span><span class="sxs-lookup"><span data-stu-id="83a35-126">Resolution</span></span>

1. <span data-ttu-id="83a35-127">连接安全&合规中心[PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后针对电子数据展示保留运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="83a35-127">Connect to [Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell) and run the following command for an eDiscovery hold:</span></span>

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. <span data-ttu-id="83a35-128">检查 *DistributionDetail 参数中的* 值。</span><span class="sxs-lookup"><span data-stu-id="83a35-128">Examine the value in the *DistributionDetail* parameter.</span></span> <span data-ttu-id="83a35-129">查找如下所示的错误：</span><span class="sxs-lookup"><span data-stu-id="83a35-129">Look for errors like the following:</span></span>

   > <span data-ttu-id="83a35-130">错误：资源：部署策略所花时间超过预期。</span><span class="sxs-lookup"><span data-stu-id="83a35-130">Error: Resources: It's taking longer than expected to deploy the policy.</span></span> <span data-ttu-id="83a35-131">更新最终部署状态可能需要 2 小时，因此请在几小时后重新检查。</span><span class="sxs-lookup"><span data-stu-id="83a35-131">It might take an additional 2 hours to update the final deployment status, so check back in a couple hours.</span></span>

3. <span data-ttu-id="83a35-132">尝试对问题的保留策略运行 **Set-CaseHoldPolicy -RetryDistribution** 命令;例如：</span><span class="sxs-lookup"><span data-stu-id="83a35-132">Try running the **Set-CaseHoldPolicy -RetryDistribution** command on the hold policy in question; for example:</span></span>

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a><span data-ttu-id="83a35-133">更多信息</span><span class="sxs-lookup"><span data-stu-id="83a35-133">More information</span></span>

- <span data-ttu-id="83a35-134">"建议的做法"部分中有关为多个用户更新保留策略的指南是系统阻止同时更新保留策略的结果。</span><span class="sxs-lookup"><span data-stu-id="83a35-134">The guidance about updating hold policies for multiple users in the "Recommended practices" section results from the fact that the system blocks simultaneous updates to a hold policy.</span></span> <span data-ttu-id="83a35-135">这意味着，当更新的保留策略应用于新内容位置且保留策略为挂起状态时，其他内容位置无法添加到保留策略。</span><span class="sxs-lookup"><span data-stu-id="83a35-135">That means when an updated hold policy is applied to new content locations and the hold policy is in a pending state, additional content locations can't be added to the hold policy.</span></span> <span data-ttu-id="83a35-136">以下是一些需要记住的以帮助你缓解此问题的一些内容：</span><span class="sxs-lookup"><span data-stu-id="83a35-136">Here are some things to keep in mind to help you mitigate this issue:</span></span>
  
  - <span data-ttu-id="83a35-137">每次更新保留时，它会立即进入挂起状态。</span><span class="sxs-lookup"><span data-stu-id="83a35-137">Every time a hold updated is updated, it immediately goes into a pending state.</span></span> <span data-ttu-id="83a35-138">挂起状态状态表示保留正在应用于内容位置。</span><span class="sxs-lookup"><span data-stu-id="83a35-138">The pending state status means the hold is being applied to content locations.</span></span>
  
  - <span data-ttu-id="83a35-139">如果您有一个脚本，该脚本运行循环并将位置按一个 (添加到策略中 (类似于) 的"推荐做法"部分中显示的错误示例，则第一个内容位置 (例如，用户邮箱) 将启动触发挂起状态的同步过程。</span><span class="sxs-lookup"><span data-stu-id="83a35-139">If you have a script that runs a loop and adds locations to policy one by one (similar to the incorrect example shown in the "Recommended practices" section), the first content location (for example, a user mailbox) initiates the sync process that triggers the pending state.</span></span> <span data-ttu-id="83a35-140">这意味着在后续循环中添加到策略的其他用户将导致错误。</span><span class="sxs-lookup"><span data-stu-id="83a35-140">That means the other users that are added to the policy in subsequent loops result in an error.</span></span>
  
  - <span data-ttu-id="83a35-141">如果您的组织使用运行循环来更新保留策略的内容位置的脚本，则必须更新该脚本，以便它在单个批量操作中更新位置 (如) 的"建议做法"部分的正确示例所示。</span><span class="sxs-lookup"><span data-stu-id="83a35-141">If your organization is using a script that runs a loop to update the content locations for a hold policy, you must update the script so that it updates locations in a single bulk operation (as shown in the correct example in the "Recommended practices" section).</span></span>
