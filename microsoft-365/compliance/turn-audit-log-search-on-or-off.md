---
title: 启用或禁用 Office 365 审核日志搜索
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MED150
- MET150
ms.assetid: e893b19a-660c-41f2-9074-d3631c95a014
description: 您可以在安全 & 合规性中心启用审核日志搜索功能。 如果你更改了想法，你可以随时关闭。 当 "审核日志搜索" 关闭时，管理员无法在组织中搜索用户和管理员活动的 Office 365 审核日志。
ms.openlocfilehash: 92a781ddb1fd4f5b41198f31ebff6bba9745d21d
ms.sourcegitcommit: 4ddbc1c3c29d79d3c4640b7b32f95576784efcca
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2020
ms.locfileid: "43240211"
---
# <a name="turn-office-365-audit-log-search-on-or-off"></a><span data-ttu-id="5ad49-105">启用或禁用 Office 365 审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="5ad49-105">Turn Office 365 audit log search on or off</span></span>

<span data-ttu-id="5ad49-106">您（或另一个管理员）必须先启用审核日志记录，然后才能开始搜索 Office 365 审核日志。</span><span class="sxs-lookup"><span data-stu-id="5ad49-106">You (or another admin) must turn on audit logging before you can start searching the Office 365 audit log.</span></span> <span data-ttu-id="5ad49-107">当安全 & 合规中心中的审核日志搜索打开时，组织中的用户和管理员活动将记录在审核日志中，并保留90天，且最多为一年，具体取决于分配给用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="5ad49-107">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="5ad49-108">但是，您的组织可能出于不需要记录和保留审核日志数据的原因。</span><span class="sxs-lookup"><span data-stu-id="5ad49-108">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="5ad49-109">在这些情况下，全局管理员可能会决定关闭 Office 365 中的审核。</span><span class="sxs-lookup"><span data-stu-id="5ad49-109">In those cases, a global admin may decide to turn off auditing in Office 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="5ad49-110">如果关闭了 Office 365 中的审核日志搜索，则不能使用 Office 365 管理活动 API 或 Azure Sentinel 来访问您的组织的审核数据。</span><span class="sxs-lookup"><span data-stu-id="5ad49-110">If you turn off audit log search in Office 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="5ad49-111">按照本文中的步骤关闭审核日志搜索意味着，在使用 Security & 合规中心或在 Exchange Online PowerShell 中运行**UnifiedAuditLog** cmdlet 时，搜索审核日志时不会返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="5ad49-111">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="5ad49-112">这也意味着不会通过 Office 365 管理活动 API 或 Azure Sentinel 提供审核日志。</span><span class="sxs-lookup"><span data-stu-id="5ad49-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="5ad49-113">准备工作</span><span class="sxs-lookup"><span data-stu-id="5ad49-113">Before you begin</span></span>

- <span data-ttu-id="5ad49-114">您必须在 Exchange Online 中向您分配 "审核日志" 角色，才能在 Office 365 组织中打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5ad49-114">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Office 365 organization.</span></span> <span data-ttu-id="5ad49-115">默认情况下，此角色在 Exchange 管理中心中的 "**权限**" 页上分配给合规性管理和组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="5ad49-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="5ad49-116">Office 365 中的全局管理员是 Exchange Online 中的 "组织管理" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="5ad49-116">Global admins in Office 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="5ad49-117">必须在 Exchange Online 中向用户分配权限，才能打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5ad49-117">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="5ad49-118">如果您在安全 & 合规中心中向用户分配 "**权限**" 页上的 "审核日志" 角色，则他们将无法打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5ad49-118">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="5ad49-119">这是因为基础 cmdlet 是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="5ad49-119">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="5ad49-120">有关搜索 Office 365 审核日志的分步说明，请参阅[在安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="5ad49-120">For step-by-step instructions on searching the Office 365 audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="5ad49-121">有关 Office 365 管理活动 API 的详细信息，请参阅[office 365 管理 api 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="5ad49-121">For more information about the Office 365 Management Activity API, see [Get started with Office 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="5ad49-122">启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="5ad49-122">Turn on audit log search</span></span>

<span data-ttu-id="5ad49-123">您可以使用安全 & 合规性中心或 PowerShell 在 Office 365 中启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5ad49-123">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Office 365.</span></span> <span data-ttu-id="5ad49-124">在您打开审核日志搜索后，可能需要几个小时才能在搜索审核日志时返回结果。</span><span class="sxs-lookup"><span data-stu-id="5ad49-124">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="5ad49-125">您必须在 Exchange Online 中向您分配 "审核日志" 角色，才能启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5ad49-125">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="5ad49-126">使用安全 & 合规性中心启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="5ad49-126">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="5ad49-127">在 "安全性 & 合规性中心中，转到"**搜索** \> **审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="5ad49-127">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
   <span data-ttu-id="5ad49-128">将显示一个横幅，指出审核必须打开以记录用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="5ad49-128">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

2. <span data-ttu-id="5ad49-129">单击 "**启用审核"**。</span><span class="sxs-lookup"><span data-stu-id="5ad49-129">Click **Turn on auditing**.</span></span>
    
    ![单击 "启用审核"](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="5ad49-131">标题已更新，指示审核日志正在准备，并且您可以在几个小时内搜索用户和管理活动。</span><span class="sxs-lookup"><span data-stu-id="5ad49-131">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>
    
### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="5ad49-132">使用 PowerShell 打开审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="5ad49-132">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="5ad49-133">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ad49-133">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="5ad49-134">运行以下 PowerShell 命令以在 Office 365 中启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5ad49-134">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="5ad49-135">将显示一条消息，指出可能需要长达60分钟的时间才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="5ad49-135">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="5ad49-136">关闭审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="5ad49-136">Turn off audit log search</span></span>

<span data-ttu-id="5ad49-137">您必须使用连接到 Exchange Online 组织的远程 PowerShell，才能关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5ad49-137">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="5ad49-138">与启用审核日志搜索类似，您必须在 Exchange Online 中将 "审核日志" 角色分配给 "关闭审核日志搜索"。</span><span class="sxs-lookup"><span data-stu-id="5ad49-138">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="5ad49-139">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="5ad49-139">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)
    
2. <span data-ttu-id="5ad49-140">运行以下 PowerShell 命令以关闭 Office 365 中的审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5ad49-140">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>
    
    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="5ad49-141">一段时间后，验证审核日志搜索是否已关闭（已禁用）。</span><span class="sxs-lookup"><span data-stu-id="5ad49-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="5ad49-142">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="5ad49-142">There are two ways to do this:</span></span>
    
    - <span data-ttu-id="5ad49-143">在 PowerShell 中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="5ad49-143">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="5ad49-144">UnifiedAuditLogIngestionEnabled 属性的`False`值指示_UnifiedAuditLogIngestionEnabled_已关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="5ad49-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 
    
    - <span data-ttu-id="5ad49-145">在 "安全性 & 合规性中心中，转到"**搜索** \> **审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="5ad49-145">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>
    
      <span data-ttu-id="5ad49-146">将显示一条横幅，指出必须打开审核才能记录用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="5ad49-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>
