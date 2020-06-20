---
title: 启用或禁用审核日志搜索
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
ms.custom: seo-marvel-apr2020
description: 如何在安全 & 合规中心中打开或关闭审核日志搜索功能，以启用或禁用管理员在审核日志中搜索的功能。
ms.openlocfilehash: 4571c90c4fa680acd8925e83e32ffcf07de7d626
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44819132"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="2a575-103">启用或禁用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="2a575-103">Turn audit log search on or off</span></span>

<span data-ttu-id="2a575-104">您（或另一个管理员）必须先启用审核日志记录，然后才能开始搜索审核日志。</span><span class="sxs-lookup"><span data-stu-id="2a575-104">You (or another admin) must turn on audit logging before you can start searching the audit log.</span></span> <span data-ttu-id="2a575-105">当安全 & 合规中心中的审核日志搜索打开时，组织中的用户和管理员活动将记录在审核日志中，并保留90天，且最多为一年，具体取决于分配给用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="2a575-105">When audit log search in the Security & Compliance Center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="2a575-106">但是，您的组织可能出于不需要记录和保留审核日志数据的原因。</span><span class="sxs-lookup"><span data-stu-id="2a575-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="2a575-107">在这些情况下，全局管理员可能会决定关闭 Microsoft 365 中的审核。</span><span class="sxs-lookup"><span data-stu-id="2a575-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2a575-108">如果您在 Microsoft 365 中关闭审核日志搜索，则不能使用 Office 365 管理活动 API 或 Azure Sentinel 来访问您的组织的审核数据。</span><span class="sxs-lookup"><span data-stu-id="2a575-108">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="2a575-109">按照本文中的步骤关闭审核日志搜索意味着，在使用 Security & 合规中心或在 Exchange Online PowerShell 中运行**UnifiedAuditLog** cmdlet 时，搜索审核日志时不会返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="2a575-109">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="2a575-110">这也意味着不会通过 Office 365 管理活动 API 或 Azure Sentinel 提供审核日志。</span><span class="sxs-lookup"><span data-stu-id="2a575-110">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="2a575-111">在打开或关闭审核日志搜索之前</span><span class="sxs-lookup"><span data-stu-id="2a575-111">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="2a575-112">您必须在 Exchange Online 中向您分配 "审核日志" 角色，才能在 Microsoft 365 组织中打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="2a575-112">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="2a575-113">默认情况下，此角色在 Exchange 管理中心中的 "**权限**" 页上分配给合规性管理和组织管理角色组。</span><span class="sxs-lookup"><span data-stu-id="2a575-113">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="2a575-114">Microsoft 365 中的全局管理员是 Exchange Online 中的 "组织管理" 角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="2a575-114">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="2a575-115">必须在 Exchange Online 中向用户分配权限，才能打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="2a575-115">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="2a575-116">如果您在安全 & 合规中心中向用户分配 "**权限**" 页上的 "审核日志" 角色，则他们将无法打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="2a575-116">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="2a575-117">这是因为基础 cmdlet 是 Exchange Online cmdlet。</span><span class="sxs-lookup"><span data-stu-id="2a575-117">This is because the underlying cmdlet is an Exchange Online cmdlet.</span></span> 
    
- <span data-ttu-id="2a575-118">有关搜索审核日志的分步说明，请参阅[在安全 & 合规性中心中搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="2a575-118">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="2a575-119">有关 Microsoft 365 管理活动 API 的详细信息，请参阅[microsoft 365 管理 api 入门](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="2a575-119">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](https://docs.microsoft.com/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="2a575-120">启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="2a575-120">Turn on audit log search</span></span>

<span data-ttu-id="2a575-121">您可以使用安全 & 合规性中心或 PowerShell 在 Microsoft 365 中启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="2a575-121">You can use the Security & Compliance Center or PowerShell to turn on audit log search in Microsoft 365.</span></span> <span data-ttu-id="2a575-122">在您打开审核日志搜索后，可能需要几个小时才能在搜索审核日志时返回结果。</span><span class="sxs-lookup"><span data-stu-id="2a575-122">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span> <span data-ttu-id="2a575-123">您必须在 Exchange Online 中向您分配 "审核日志" 角色，才能启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="2a575-123">You have to be assigned the Audit Logs role in Exchange Online to turn on audit log search.</span></span>
  
### <a name="use-the-security--compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="2a575-124">使用安全 & 合规性中心启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="2a575-124">Use the Security & Compliance Center to turn on audit log search</span></span>

1. <span data-ttu-id="2a575-125">[转到安全 & 合规性中心](https://protection.office.com)并登录。</span><span class="sxs-lookup"><span data-stu-id="2a575-125">[Go to the Security & Compliance Center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="2a575-126">在 "安全性 & 合规性中心中，转到"**搜索** \> **审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="2a575-126">In the Security & Compliance Center, go to **Search** \> **Audit log search**.</span></span>

   <span data-ttu-id="2a575-127">将显示一个横幅，指出审核必须打开以记录用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="2a575-127">A banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="2a575-128">单击 "**启用审核"**。</span><span class="sxs-lookup"><span data-stu-id="2a575-128">Click **Turn on auditing**.</span></span>

    ![单击 "启用审核"](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="2a575-130">标题已更新，指示审核日志正在准备，并且您可以在几个小时内搜索用户和管理活动。</span><span class="sxs-lookup"><span data-stu-id="2a575-130">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="2a575-131">使用 PowerShell 打开审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="2a575-131">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="2a575-132">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a575-132">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="2a575-133">运行以下 PowerShell 命令以在 Office 365 中启用审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="2a575-133">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="2a575-134">将显示一条消息，指出可能需要长达60分钟的时间才能使更改生效。</span><span class="sxs-lookup"><span data-stu-id="2a575-134">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="2a575-135">关闭审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="2a575-135">Turn off audit log search</span></span>

<span data-ttu-id="2a575-136">您必须使用连接到 Exchange Online 组织的远程 PowerShell，才能关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="2a575-136">You have to use remote PowerShell connected to your Exchange Online organization to turn off audit log search.</span></span> <span data-ttu-id="2a575-137">与启用审核日志搜索类似，您必须在 Exchange Online 中将 "审核日志" 角色分配给 "关闭审核日志搜索"。</span><span class="sxs-lookup"><span data-stu-id="2a575-137">Similar to turning on audit log search, you have to be assigned the Audit Logs role in Exchange Online to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="2a575-138">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="2a575-138">Connect to Exchange Online PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkID=396554)

2. <span data-ttu-id="2a575-139">运行以下 PowerShell 命令以关闭 Office 365 中的审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="2a575-139">Run the following PowerShell command to turn off audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="2a575-140">一段时间后，验证审核日志搜索是否已关闭（已禁用）。</span><span class="sxs-lookup"><span data-stu-id="2a575-140">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="2a575-141">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="2a575-141">There are two ways to do this:</span></span>

    - <span data-ttu-id="2a575-142">在 PowerShell 中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="2a575-142">In PowerShell, run the following command:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

      <span data-ttu-id="2a575-143">`False` _UnifiedAuditLogIngestionEnabled_属性的值指示已关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="2a575-143">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="2a575-144">在 "[安全性 & 合规性中心](https://protection.office.com)中，转到"**搜索** \> **审核日志搜索**"。</span><span class="sxs-lookup"><span data-stu-id="2a575-144">In the [Security & Compliance Center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="2a575-145">将显示一条横幅，指出必须打开审核才能记录用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="2a575-145">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>