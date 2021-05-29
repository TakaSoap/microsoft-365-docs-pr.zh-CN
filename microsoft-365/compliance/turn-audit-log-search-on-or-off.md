---
title: 打开或关闭审核
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
description: 如何打开或关闭安全与合规中心Microsoft 365审核日志搜索功能，以启用或禁用管理员搜索审核日志。
ms.openlocfilehash: 457f453b001f71a095bc60932c8e0cebf46aa7b1
ms.sourcegitcommit: a05f61a291eb4595fa9313757a3815b7f217681d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/29/2021
ms.locfileid: "52706657"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="e2718-103">打开或关闭审核</span><span class="sxs-lookup"><span data-stu-id="e2718-103">Turn auditing on or off</span></span>

<span data-ttu-id="e2718-104">Microsoft 365 和 Office 365 企业版组织默认已打开审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="e2718-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="e2718-105">这包括具有 E3/G3 或 E5/G5 订阅的组织。</span><span class="sxs-lookup"><span data-stu-id="e2718-105">This includes organizations with E3/G3 or E5/G5 subscriptions.</span></span> <span data-ttu-id="e2718-106">在合规性中心内启用审核时，组织的用户和管理员活动将记录在 审核日志 中，并保留 90 天，最多保留一年，具体取决于分配给用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="e2718-106">When auditing in the compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="e2718-107">但是，您的组织可能出于不希望记录并保留数据审核日志的原因。</span><span class="sxs-lookup"><span data-stu-id="e2718-107">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="e2718-108">在这种情况下，全局管理员可能会决定在 Microsoft 365 中关闭审核。</span><span class="sxs-lookup"><span data-stu-id="e2718-108">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="e2718-109">如果关闭组织中Microsoft 365，则你无法通过 Office 365 管理活动 API 或 Azure Sentinel 访问组织的审核数据。</span><span class="sxs-lookup"><span data-stu-id="e2718-109">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="e2718-110">按照本文中的步骤关闭审核意味着在使用安全 & 合规中心搜索 审核日志 或在 Exchange Online PowerShell 中运行 **Search-UnifiedAuditLog** cmdlet 时不会返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="e2718-110">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Security & Compliance Center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="e2718-111">这也意味着审核日志无法通过 Office 365管理活动 API 或 Azure Sentinel 提供。</span><span class="sxs-lookup"><span data-stu-id="e2718-111">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="e2718-112">打开或关闭审核之前</span><span class="sxs-lookup"><span data-stu-id="e2718-112">Before you turn auditing on or off</span></span>

- <span data-ttu-id="e2718-113">必须分配有"审核日志"角色Exchange Online在组织中启用或Microsoft 365审核。</span><span class="sxs-lookup"><span data-stu-id="e2718-113">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="e2718-114">默认情况下，此角色分配给管理中心中"权限"页上的"合规性管理"和"组织Exchange组。</span><span class="sxs-lookup"><span data-stu-id="e2718-114">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="e2718-115">Microsoft 365中的全局管理员是组织中组织管理角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="e2718-115">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span> 

    > [!NOTE]
    > <span data-ttu-id="e2718-116">用户必须分配有权限Exchange Online才能启用或关闭审核。</span><span class="sxs-lookup"><span data-stu-id="e2718-116">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="e2718-117">如果在安全与合规中心的"权限"页上为用户分配"审核&"角色，他们将不能启用或关闭审核。</span><span class="sxs-lookup"><span data-stu-id="e2718-117">If you assign users the Audit Logs role on the **Permissions** page in the Security & Compliance Center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="e2718-118">这是因为基础 cmdlet 是一个Exchange Online PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="e2718-118">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span> 

- <span data-ttu-id="e2718-119">有关搜索安全与合规中心的分步审核日志，请参阅在安全审核日志[搜索&搜索。](search-the-audit-log-in-security-and-compliance.md)</span><span class="sxs-lookup"><span data-stu-id="e2718-119">For step-by-step instructions on searching the audit log, see [Search the audit log in the Security & Compliance Center](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="e2718-120">有关管理活动 API Microsoft 365，请参阅 Microsoft 365 管理[API 入门](/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="e2718-120">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

- <span data-ttu-id="e2718-121">若要验证审核是否打开，可以在 PowerShell 中运行Exchange Online命令：</span><span class="sxs-lookup"><span data-stu-id="e2718-121">To verify that auditing is turned on, you can run the following command in Exchange Online PowerShell:</span></span>

    ```powershell
    Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
    ```

    <span data-ttu-id="e2718-122">`True` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核已打开。</span><span class="sxs-lookup"><span data-stu-id="e2718-122">The value of  `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> 

## <a name="turn-on-auditing"></a><span data-ttu-id="e2718-123">启用审核</span><span class="sxs-lookup"><span data-stu-id="e2718-123">Turn on auditing</span></span>

<span data-ttu-id="e2718-124">如果未为组织启用审核，可以在合规中心内或通过使用 PowerShell Exchange Online审核。</span><span class="sxs-lookup"><span data-stu-id="e2718-124">If auditing is not turned on for your organization, you can turn it on in the compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="e2718-125">在打开审核后，可能需要几个小时才能在搜索查询时返回审核日志。</span><span class="sxs-lookup"><span data-stu-id="e2718-125">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="e2718-126">使用合规中心启用审核</span><span class="sxs-lookup"><span data-stu-id="e2718-126">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="e2718-127">转到 <https://compliance.microsoft.com> 并登录。</span><span class="sxs-lookup"><span data-stu-id="e2718-127">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="e2718-128">在合规性中心的左侧导航Microsoft 365，单击"全部 **显示**"，然后单击"审核 **"。**</span><span class="sxs-lookup"><span data-stu-id="e2718-128">In the left navigation pane of the Microsoft 365 compliance center, click **Show all**, and then click **Audit**.</span></span>

   <span data-ttu-id="e2718-129">如果未为组织启用审核，则会显示横幅，提示你开始录制用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="e2718-129">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![审核页上的横幅](../media/AuditingBanner.png)

3. <span data-ttu-id="e2718-131">单击" **开始录制用户和管理员活动"** 横幅。</span><span class="sxs-lookup"><span data-stu-id="e2718-131">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="e2718-132">更改最多可能需要 60 分钟才能生效。</span><span class="sxs-lookup"><span data-stu-id="e2718-132">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="e2718-133">使用 PowerShell 启用审核</span><span class="sxs-lookup"><span data-stu-id="e2718-133">Use PowerShell to turn on auditing</span></span>

1. [<span data-ttu-id="e2718-134">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2718-134">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="e2718-135">运行以下 PowerShell 命令以在 Office 365 中启用审核。</span><span class="sxs-lookup"><span data-stu-id="e2718-135">Run the following PowerShell command to turn on auditing in Office 365.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="e2718-136">将显示一条消息，指出更改最多可能需要 60 分钟才能生效。</span><span class="sxs-lookup"><span data-stu-id="e2718-136">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="e2718-137">关闭审核</span><span class="sxs-lookup"><span data-stu-id="e2718-137">Turn off auditing</span></span>

<span data-ttu-id="e2718-138">您必须使用 Exchange Online PowerShell 来关闭审核。</span><span class="sxs-lookup"><span data-stu-id="e2718-138">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. [<span data-ttu-id="e2718-139">连接到 Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="e2718-139">Connect to Exchange Online PowerShell</span></span>](/powershell/exchange/connect-to-exchange-online-powershell)

2. <span data-ttu-id="e2718-140">运行以下 PowerShell 命令以关闭审核。</span><span class="sxs-lookup"><span data-stu-id="e2718-140">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="e2718-141">一段时间之后，验证审核是否处于关闭状态 (禁用) 。</span><span class="sxs-lookup"><span data-stu-id="e2718-141">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="e2718-142">可以通过两种方式来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="e2718-142">There are two ways to do this:</span></span>

    - <span data-ttu-id="e2718-143">在 Exchange Online PowerShell 中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e2718-143">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="e2718-144">`False` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核已关闭。</span><span class="sxs-lookup"><span data-stu-id="e2718-144">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="e2718-145">转到合规性 **中心** 中的Microsoft 365页面。</span><span class="sxs-lookup"><span data-stu-id="e2718-145">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="e2718-146">如果未为组织启用审核，则会显示横幅，提示你开始录制用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="e2718-146">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
