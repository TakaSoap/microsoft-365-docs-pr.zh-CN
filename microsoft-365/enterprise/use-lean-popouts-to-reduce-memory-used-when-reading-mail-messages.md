---
title: 使用斜弹出式弹出窗口减少阅读邮件时所使用的内存
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 12/3/2019
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: a6d6ba01-2562-4c3d-a8f1-78748dd506cf
f1.keywords:
- NOCSH
description: 本文包含有关在 Outlook 网页中使用精简弹出窗口提高邮件下载性能的信息。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0fec3e0267b7299e34de541a184cf92e99e260f1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925252"
---
# <a name="use-lean-popouts-to-reduce-memory-used-when-reading-mail-messages"></a><span data-ttu-id="6e15d-103">使用斜弹出式弹出窗口减少阅读邮件时所使用的内存</span><span class="sxs-lookup"><span data-stu-id="6e15d-103">Use lean popouts to reduce memory used when reading mail messages</span></span>

<span data-ttu-id="6e15d-104">本文包含用于提高 Outlook 网页邮件下载性能的信息。</span><span class="sxs-lookup"><span data-stu-id="6e15d-104">This article contains information for improving message download performance in Outlook on the web.</span></span> <span data-ttu-id="6e15d-105">本文是 Office [365 项目的网络规划和性能调整的一](./network-planning-and-performance.md) 部分。</span><span class="sxs-lookup"><span data-stu-id="6e15d-105">This article is part of the [Network planning and performance tuning for Office 365](./network-planning-and-performance.md) project.</span></span>
  
<span data-ttu-id="6e15d-106">作为 Office 365 全局管理员，可以将 Outlook 网页版配置为提供精简弹出窗口，即 Microsoft Edge 或 Internet Explorer 中某些电子邮件的较小、内存占用较少的版本。</span><span class="sxs-lookup"><span data-stu-id="6e15d-106">As an Office 365 global administrator, you can configure Outlook on the web to deliver _lean popouts_, a smaller, less memory-intensive version of certain email messages in Microsoft Edge or Internet Explorer.</span></span> <span data-ttu-id="6e15d-107">当为 Web 上的 Outlook 配置精简弹出窗口时，将加载服务器端呈现的组件以优化性能。</span><span class="sxs-lookup"><span data-stu-id="6e15d-107">When lean popouts are configured for Outlook on the web, server-side rendered components are loaded that optimize performance.</span></span>
  
> [!NOTE]
> <span data-ttu-id="6e15d-108">截至 2018 年 3 月，精简弹出窗口不适用于指定使用权限限制的邮件，例如信息权限管理 (IRM) 。</span><span class="sxs-lookup"><span data-stu-id="6e15d-108">As of March 2018, lean popouts are not available for messages that specify usage rights restrictions, such as Information Rights Management (IRM).</span></span>
  
<span data-ttu-id="6e15d-109">这些功能将继续在主窗口中工作，但在精简弹出窗口中不可用：</span><span class="sxs-lookup"><span data-stu-id="6e15d-109">These features will continue to work in the main window but are not available in lean popouts:</span></span>
  
- <span data-ttu-id="6e15d-110">Outlook 外接程序</span><span class="sxs-lookup"><span data-stu-id="6e15d-110">Outlook add-ins</span></span>
  
- <span data-ttu-id="6e15d-111">Skype for Business 状态</span><span class="sxs-lookup"><span data-stu-id="6e15d-111">Skype for Business presence</span></span>
  
## <a name="to-configure-lean-popouts-for-all-users-within-your-office-365-organization"></a><span data-ttu-id="6e15d-112">为 Office 365 组织中所有用户配置精简弹出窗口</span><span class="sxs-lookup"><span data-stu-id="6e15d-112">To configure lean popouts for all users within your Office 365 organization</span></span>
  
1. <span data-ttu-id="6e15d-113">[使用远程 PowerShell 连接到 Exchange Online。](/powershell/exchange/connect-to-exchange-online-powershell)</span><span class="sxs-lookup"><span data-stu-id="6e15d-113">[Connect to Exchange Online Using Remote PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>
  
2. <span data-ttu-id="6e15d-114">运行带 LeanPopoutEnabled 参数的 [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet，如下所示：</span><span class="sxs-lookup"><span data-stu-id="6e15d-114">Run the [Set-OrganizationConfig](/powershell/module/exchange/set-organizationconfig) cmdlet with the LeanPopoutEnabled parameter as follows:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled <$true |$false >
  ```

  <span data-ttu-id="6e15d-115">例如，若要为组织中所有用户启用精简弹出窗口：</span><span class="sxs-lookup"><span data-stu-id="6e15d-115">For example, to enable lean popouts for all users in your organization:</span></span>
  
  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $true
  ```

  <span data-ttu-id="6e15d-116">若要禁用组织中所有用户的精简弹出窗口：：</span><span class="sxs-lookup"><span data-stu-id="6e15d-116">To disable lean popouts for all users in your organization:</span></span>

  ```powershell
  Set-OrganizationConfig -LeanPopoutEnabled $false
  ```