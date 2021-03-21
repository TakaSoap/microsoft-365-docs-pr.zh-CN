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
description: 如何打开或关闭安全与合规中心中的审核日志&启用或禁用管理员搜索审核日志。
ms.openlocfilehash: aecd1d47592b9a5e2f134b1d9db9ff203b815b18
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919278"
---
# <a name="turn-audit-log-search-on-or-off"></a><span data-ttu-id="96b6d-103">启用或禁用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="96b6d-103">Turn audit log search on or off</span></span>

<span data-ttu-id="96b6d-104">Microsoft 365 和 Office 365 企业版组织默认已打开审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="96b6d-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="96b6d-105">这包括具有 E3/G3 或 E5/G5 订阅的组织。</span><span class="sxs-lookup"><span data-stu-id="96b6d-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="96b6d-106">当审核日志中心中启用搜索时，组织的用户和管理员活动将记录在 审核日志 中，并保留 90 天，最多保留一年，具体取决于分配给用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="96b6d-106">When audit log search in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="96b6d-107">但是，您的组织可能出于不希望记录并保留数据审核日志的原因。</span><span class="sxs-lookup"><span data-stu-id="96b6d-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="96b6d-108">在这种情况下，全局管理员可能会决定在 Microsoft 365 中关闭审核。</span><span class="sxs-lookup"><span data-stu-id="96b6d-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="96b6d-109">如果关闭 Microsoft 365 审核日志搜索，则你无法使用 Office 365 管理活动 API 或 Azure Sentinel 访问组织的审核数据。</span><span class="sxs-lookup"><span data-stu-id="96b6d-109">If you turn off audit log search in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="96b6d-110">按照本文中的步骤关闭 审核日志 搜索意味着在使用安全 & 合规中心搜索 审核日志 或在 Exchange Online PowerShell 中运行 **Search-UnifiedAuditLog** cmdlet 时不会返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="96b6d-110">Turning off audit log search by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="96b6d-111">这也意味着审核日志无法通过 Office 365 管理活动 API 或 Azure Sentinel 提供。</span><span class="sxs-lookup"><span data-stu-id="96b6d-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-audit-log-search-on-or-off"></a><span data-ttu-id="96b6d-112">打开或审核日志搜索之前</span><span class="sxs-lookup"><span data-stu-id="96b6d-112">Before you turn audit log search on or off</span></span>

- <span data-ttu-id="96b6d-113">您必须在 Exchange Online 中分配审核日志角色，审核日志 Microsoft 365 组织中启用或关闭搜索功能。</span><span class="sxs-lookup"><span data-stu-id="96b6d-113">You have to be assigned the Audit Logs role in Exchange Online to turn audit log search on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="96b6d-114">默认情况下，此角色分配给 Exchange 管理中心中"权限"页上的"合规性管理"和"组织管理"角色组。</span><span class="sxs-lookup"><span data-stu-id="96b6d-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="96b6d-115">Microsoft 365 中的全局管理员是 Exchange Online 中组织管理角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="96b6d-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 
    
    > [!NOTE]
    > <span data-ttu-id="96b6d-116">用户必须分配有 Exchange Online 中的权限，才能审核日志或关闭搜索。</span><span class="sxs-lookup"><span data-stu-id="96b6d-116">Users have to be assigned permissions in Exchange Online to turn audit log search on or off.</span></span> <span data-ttu-id="96b6d-117">如果在安全与合规中心的"权限"页上为用户分配"审核日志"角色&，他们将无法打开或关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="96b6d-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn audit log search on or off.</span></span> <span data-ttu-id="96b6d-118">这是因为基础 cmdlet 是 Exchange Online PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="96b6d-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 
    
- <span data-ttu-id="96b6d-119">有关搜索安全与合规中心的分步审核日志，请参阅在安全审核日志[搜索&搜索。](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="96b6d-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="96b6d-120">有关 Microsoft 365 管理活动 API 详细信息，请参阅 [Microsoft 365 管理 API 入门](/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="96b6d-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="96b6d-121">若要验证审核日志搜索是否打开，可以在 Exchange Online PowerShell 中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="96b6d-121">To verify that audit log search is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="96b6d-122">`True` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核日志打开。</span><span class="sxs-lookup"><span data-stu-id="96b6d-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned on.</span></span> 
    
## <a name="turn-on-audit-log-search"></a><span data-ttu-id="96b6d-123">打开"审核日志搜索"</span><span class="sxs-lookup"><span data-stu-id="96b6d-123">Turn on audit log search</span></span>

<span data-ttu-id="96b6d-124">如果未审核日志启用搜索，可以在合规中心或通过使用 Exchange Online PowerShell 将其打开。</span><span class="sxs-lookup"><span data-stu-id="96b6d-124">If audit log search is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="96b6d-125">打开搜索后，可能需要几个小时审核日志才能在搜索搜索时返回审核日志。</span><span class="sxs-lookup"><span data-stu-id="96b6d-125">It may take several hours after you turn on audit log search before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-audit-log-search"></a><span data-ttu-id="96b6d-126">使用合规中心启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="96b6d-126">Use the compliance center to turn on audit log search</span></span>

1. <span data-ttu-id="96b6d-127">[转到合规中心并](https://protection.office.com) 登录。</span><span class="sxs-lookup"><span data-stu-id="96b6d-127">[Go to the compliance center](https://protection.office.com) and sign in.</span></span>

2. <span data-ttu-id="96b6d-128">在合规中心，转到"**搜索**  >  **审核日志搜索"。**</span><span class="sxs-lookup"><span data-stu-id="96b6d-128">In the compliance center, go to **Search** > **Audit log search**.</span></span>

   <span data-ttu-id="96b6d-129">如果未审核日志启用搜索，则会显示一个横幅，指出必须启用审核才能记录用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="96b6d-129">If audit log search is not turned on for your organization, a banner is displayed saying that auditing has to be turned on to record user and admin activity.</span></span>

3. <span data-ttu-id="96b6d-130">单击 **"启用审核"。**</span><span class="sxs-lookup"><span data-stu-id="96b6d-130">Click **Turn on auditing**.</span></span>

    ![单击"启用审核"](../media/39a9d35f-88d0-4bbe-a962-0be2f838e2bf.png)
  
    <span data-ttu-id="96b6d-132">横幅已更新，审核日志准备的时间，你可以搜索数小时内的用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="96b6d-132">The banner is updated to say the audit log is being prepared and that you can search for user and admin activity in a few hours.</span></span>

### <a name="use-powershell-to-turn-on-audit-log-search"></a><span data-ttu-id="96b6d-133">使用 PowerShell 启用审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="96b6d-133">Use PowerShell to turn on audit log search</span></span>

1. [<span data-ttu-id="96b6d-134">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="96b6d-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="96b6d-135">运行以下 PowerShell 命令以在 Office 365 中审核日志搜索功能。</span><span class="sxs-lookup"><span data-stu-id="96b6d-135">Run the following PowerShell command to turn on audit log search in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="96b6d-136">将显示一条消息，指出更改最多可能需要 60 分钟才能生效。</span><span class="sxs-lookup"><span data-stu-id="96b6d-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-audit-log-search"></a><span data-ttu-id="96b6d-137">关闭审核日志搜索</span><span class="sxs-lookup"><span data-stu-id="96b6d-137">Turn off audit log search</span></span>

<span data-ttu-id="96b6d-138">您必须使用 Exchange Online PowerShell 来关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="96b6d-138">You have to use Exchange Online PowerShell to turn off audit log search.</span></span>
  
1. [<span data-ttu-id="96b6d-139">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="96b6d-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="96b6d-140">运行以下 PowerShell 命令以关闭审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="96b6d-140">Run the following PowerShell command to turn off audit log search.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="96b6d-141">一段时间之后，确认审核日志搜索已关闭， (禁用) 。</span><span class="sxs-lookup"><span data-stu-id="96b6d-141">After a while, verify that audit log search is turned off (disabled).</span></span> <span data-ttu-id="96b6d-142">可通过 2 种方法执行此操作：</span><span class="sxs-lookup"><span data-stu-id="96b6d-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="96b6d-143">在 Exchange Online PowerShell 中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="96b6d-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="96b6d-144">`False` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核日志搜索已关闭。</span><span class="sxs-lookup"><span data-stu-id="96b6d-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that audit log search is turned off.</span></span> 

    - <span data-ttu-id="96b6d-145">在合规 [中心，](https://protection.office.com)转到"**搜索** \> **审核日志搜索"。**</span><span class="sxs-lookup"><span data-stu-id="96b6d-145">In the [compliance center](https://protection.office.com), go to **Search** \> **Audit log search**.</span></span>

      <span data-ttu-id="96b6d-146">将显示一个横幅，指出必须启用审核才能记录用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="96b6d-146">A banner is displayed saying that auditing has to be turned on in order to record user and admin activity.</span></span>