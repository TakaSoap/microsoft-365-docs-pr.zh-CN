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
# <a name="troubleshoot-ediscovery-hold-errors"></a>解决电子数据展示保留错误

本文讨论电子数据展示保留中可能会出现的常见问题以及如何解决这些问题。 本文还包括帮助您缓解或避免这些问题的建议做法。

## <a name="recommended-practices"></a>建议的做法

若要减少与电子数据展示保留相关的错误数，建议采用以下做法：

- 如果保留分发仍处于待定状态，状态为 或 ，请等到保留分发完成，然后再 `On (Pending)` `Off (Pending)` 进行进一步更新。

- 将更新合并到单个批量请求中的电子数据展示保留，而不是针对每个事务重复更新保留策略。 例如，若要使用 [Set-CaseHoldPolicy](/powershell/module/exchange/set-caseholdpolicy) cmdlet 将多个用户邮箱添加到现有保留策略，请运行命令 (或将 作为代码块添加到脚本) 以便它只运行一次以添加多个用户。

  **正确**

    ```powershell
    Set-CaseHoldPolicy -AddExchangeLocation {$user1, $user2, $user3, $user4, $user5}
    ```

   **错误**

    ```powershell
    $users = {$user1, $user2, $user3, $user4, $user5}
    ForEach($user in $users)
    {
        Set-CaseHoldPolicy -AddExchangeLocation $user
    }
    ```

   在上一错误示例中，cmdlet 将单独运行五次以完成任务。 有关将用户添加到保留策略的建议做法详细信息，请参阅 [详细信息](#more-information) 部分。

- 在就电子数据展示保留问题与 Microsoft 支持部门联系之前，请按照错误 [/问题：保留不同步](#errorissue-holds-dont-sync) 部分中的步骤重试保留分配。 此过程通常会解决临时问题，包括内部服务器错误。

## <a name="errorissue-holds-dont-sync"></a>错误/问题：保留未同步

如果将保管人和数据源置于保留状态时看到以下错误消息之一，请使用解决方案步骤解决问题。

> 资源：部署策略所花时间超过预期。 更新最终部署状态可能需要 2 小时，因此请在几小时后重新检查。

> 由于临时部署数据中心问题，无法将策略Office 365内容源。 当前策略不会应用于源中任何内容，因此阻止的部署没有影响。 若要解决此问题，请尝试重新部署策略。

> 很抱歉，由于暂时性内部服务器错误，我们无法执行请求的策略更改。 请在 30 分钟后重试。

### <a name="resolution"></a>解决方案

1. 连接安全&合规中心[PowerShell，](/powershell/exchange/connect-to-scc-powershell)然后针对电子数据展示保留运行以下命令：

   ```powershell
   Get-CaseHoldPolicy <policyname> -DistributionDetail | FL
   ```

2. 检查 *DistributionDetail 参数中的* 值。 查找如下所示的错误：

   > 错误：资源：部署策略所花时间超过预期。 更新最终部署状态可能需要 2 小时，因此请在几小时后重新检查。

3. 尝试对问题的保留策略运行 **Set-CaseHoldPolicy -RetryDistribution** 命令;例如：

   ```powershell
   Set-CaseHoldPolicy <policyname> -RetryDistribution
   ```

## <a name="more-information"></a>详细信息

- "建议的做法"部分中有关为多个用户更新保留策略的指南是系统阻止同时更新保留策略的结果。 这意味着，当更新的保留策略应用于新内容位置且保留策略为挂起状态时，其他内容位置无法添加到保留策略。 以下是一些需要记住的以帮助你缓解此问题的一些内容：
  
  - 每次更新保留时，它会立即进入挂起状态。 挂起状态状态表示保留正在应用于内容位置。
  
  - 如果您有一个脚本，该脚本运行循环并将位置按一个 (添加到策略中 (类似于) 的"推荐做法"部分中显示的错误示例，则第一个内容位置 (例如，用户邮箱) 将启动触发挂起状态的同步过程。 这意味着在后续循环中添加到策略的其他用户将导致错误。
  
  - 如果您的组织使用运行循环来更新保留策略的内容位置的脚本，则必须更新该脚本，以便它在单个批量操作中更新位置 (如) 的"建议做法"部分的正确示例所示。
