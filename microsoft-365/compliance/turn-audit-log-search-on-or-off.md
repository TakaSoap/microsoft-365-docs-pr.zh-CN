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
description: 如何打开或关闭审核日志搜索功能Microsoft 365 合规中心启用或禁用管理员搜索审核日志。
ms.openlocfilehash: dd39b883036ce6060aef71c6a927c03f391d827f
ms.sourcegitcommit: 5db5047c24b56f3af90c2bc5c830a7a13eeeccad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/09/2021
ms.locfileid: "53341492"
---
# <a name="turn-auditing-on-or-off"></a><span data-ttu-id="26ac0-103">打开或关闭审核</span><span class="sxs-lookup"><span data-stu-id="26ac0-103">Turn auditing on or off</span></span>

<span data-ttu-id="26ac0-104">Microsoft 365 和 Office 365 企业版组织默认已打开审核日志搜索。</span><span class="sxs-lookup"><span data-stu-id="26ac0-104">Audit logging is turned on by default for Microsoft 365 and Office 365 enterprise organizations.</span></span> <span data-ttu-id="26ac0-105">启用 Microsoft 365 合规中心 中的审核时，组织的用户和管理员活动将记录在 审核日志 中，并保留 90 天，最多保留一年，具体取决于分配给用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="26ac0-105">When auditing in the Microsoft 365 compliance center is turned on, user and admin activity from your organization is recorded in the audit log and retained for 90 days, and up to one year depending on the license assigned to users.</span></span> <span data-ttu-id="26ac0-106">但是，您的组织可能出于不希望记录并保留数据审核日志的原因。</span><span class="sxs-lookup"><span data-stu-id="26ac0-106">However, your organization may have reasons for not wanting to record and retain audit log data.</span></span> <span data-ttu-id="26ac0-107">在这种情况下，全局管理员可能会决定在 Microsoft 365 中关闭审核。</span><span class="sxs-lookup"><span data-stu-id="26ac0-107">In those cases, a global admin may decide to turn off auditing in Microsoft 365.</span></span>

<span data-ttu-id="26ac0-108">在组织中设置Microsoft 365 Office 365时，可以验证组织的审核状态。</span><span class="sxs-lookup"><span data-stu-id="26ac0-108">When setting up a new Microsoft 365 or Office 365 organization, you can verify the auditing status for your organization.</span></span> <span data-ttu-id="26ac0-109">有关说明，请参阅本文 [中的验证组织的](#verify-the-auditing-status-for-your-organization) 审核状态部分。</span><span class="sxs-lookup"><span data-stu-id="26ac0-109">For instructions, see the [Verify the auditing status for your organization](#verify-the-auditing-status-for-your-organization) section in this article.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="26ac0-110">如果关闭组织中Microsoft 365，则你无法通过 Office 365 管理活动 API 或 Azure Sentinel 访问组织的审核数据。</span><span class="sxs-lookup"><span data-stu-id="26ac0-110">If you turn off auditing in Microsoft 365, you can't use the Office 365 Management Activity API or Azure Sentinel to access auditing data for your organization.</span></span> <span data-ttu-id="26ac0-111">按照本文中的步骤关闭审核意味着在使用 Microsoft 365 合规中心 搜索 审核日志 或在 Exchange Online PowerShell 中运行 **Search-UnifiedAuditLog** cmdlet 时不会返回任何结果。</span><span class="sxs-lookup"><span data-stu-id="26ac0-111">Turning off auditing by following the steps in this article means that no results will be returned when you search the audit log using the Microsoft 365 compliance center or when you run the **Search-UnifiedAuditLog** cmdlet in Exchange Online PowerShell.</span></span> <span data-ttu-id="26ac0-112">这也意味着审核日志无法通过 Office 365管理活动 API 或 Azure Sentinel 提供。</span><span class="sxs-lookup"><span data-stu-id="26ac0-112">This also means that audit logs won't be available through the Office 365 Management Activity API or Azure Sentinel.</span></span>
  
## <a name="before-you-turn-auditing-on-or-off"></a><span data-ttu-id="26ac0-113">打开或关闭审核之前</span><span class="sxs-lookup"><span data-stu-id="26ac0-113">Before you turn auditing on or off</span></span>

- <span data-ttu-id="26ac0-114">必须分配有"审核日志"角色Exchange Online在组织中启用或Microsoft 365审核。</span><span class="sxs-lookup"><span data-stu-id="26ac0-114">You have to be assigned the Audit Logs role in Exchange Online to turn auditing on or off in your Microsoft 365 organization.</span></span> <span data-ttu-id="26ac0-115">默认情况下，此角色分配给管理中心中"权限"页上的"合规性管理"和"组织Exchange组。</span><span class="sxs-lookup"><span data-stu-id="26ac0-115">By default, this role is assigned to the Compliance Management and Organization Management role groups on the **Permissions** page in the Exchange admin center.</span></span> <span data-ttu-id="26ac0-116">Microsoft 365中的全局管理员是组织中组织管理角色Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="26ac0-116">Global admins in Microsoft 365 are members of the Organization Management role group in Exchange Online.</span></span>

    > [!NOTE]
    > <span data-ttu-id="26ac0-117">用户必须分配有权限Exchange Online才能启用或关闭审核。</span><span class="sxs-lookup"><span data-stu-id="26ac0-117">Users have to be assigned permissions in Exchange Online to turn auditing on or off.</span></span> <span data-ttu-id="26ac0-118">如果为用户分配"权限"页上的"审核日志"角色Microsoft 365 合规中心，他们将无法启用或关闭审核。</span><span class="sxs-lookup"><span data-stu-id="26ac0-118">If you assign users the Audit Logs role on the **Permissions** page in the Microsoft 365 compliance center, they won't be able to turn auditing on or off.</span></span> <span data-ttu-id="26ac0-119">这是因为基础 cmdlet 是一个Exchange Online PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="26ac0-119">This is because the underlying cmdlet is an Exchange Online PowerShell cmdlet.</span></span>

- <span data-ttu-id="26ac0-120">有关搜索搜索列表的审核日志， [请参阅搜索](search-the-audit-log-in-security-and-compliance.md)审核日志。</span><span class="sxs-lookup"><span data-stu-id="26ac0-120">For step-by-step instructions on searching the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span> <span data-ttu-id="26ac0-121">有关管理活动 API Microsoft 365，请参阅 Microsoft 365 管理[API 入门](/office/office-365-management-api/get-started-with-office-365-management-apis)。</span><span class="sxs-lookup"><span data-stu-id="26ac0-121">For more information about the Microsoft 365 Management Activity API, see [Get started with Microsoft 365 Management APIs](/office/office-365-management-api/get-started-with-office-365-management-apis).</span></span>

## <a name="verify-the-auditing-status-for-your-organization"></a><span data-ttu-id="26ac0-122">验证组织的审核状态</span><span class="sxs-lookup"><span data-stu-id="26ac0-122">Verify the auditing status for your organization</span></span>

<span data-ttu-id="26ac0-123">若要验证你的组织是否启用审核，可以在[PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)中运行Exchange Online命令：</span><span class="sxs-lookup"><span data-stu-id="26ac0-123">To verify that auditing is turned on for your organization, you can run the following command in [Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell):</span></span>

```powershell
Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
```

<span data-ttu-id="26ac0-124">`True` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核已打开。</span><span class="sxs-lookup"><span data-stu-id="26ac0-124">A value of `True` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned on.</span></span> <span data-ttu-id="26ac0-125">值 `False` 表示未启用审核。</span><span class="sxs-lookup"><span data-stu-id="26ac0-125">A value of `False` indicates that auditing is not turned on.</span></span>

## <a name="turn-on-auditing"></a><span data-ttu-id="26ac0-126">启用审核</span><span class="sxs-lookup"><span data-stu-id="26ac0-126">Turn on auditing</span></span>

<span data-ttu-id="26ac0-127">如果未为组织启用审核，可以在 Microsoft 365 合规中心或通过使用 PowerShell Exchange Online审核。</span><span class="sxs-lookup"><span data-stu-id="26ac0-127">If auditing is not turned on for your organization, you can turn it on in the Microsoft 365 compliance center or by using Exchange Online PowerShell.</span></span> <span data-ttu-id="26ac0-128">在打开审核后，可能需要几个小时才能在搜索查询时返回审核日志。</span><span class="sxs-lookup"><span data-stu-id="26ac0-128">It may take several hours after you turn on auditing before you can return results when you search the audit log.</span></span>
  
### <a name="use-the-compliance-center-to-turn-on-auditing"></a><span data-ttu-id="26ac0-129">使用合规中心启用审核</span><span class="sxs-lookup"><span data-stu-id="26ac0-129">Use the compliance center to turn on auditing</span></span>

1. <span data-ttu-id="26ac0-130">转到 <https://compliance.microsoft.com> 并登录。</span><span class="sxs-lookup"><span data-stu-id="26ac0-130">Go to <https://compliance.microsoft.com> and sign in.</span></span>

2. <span data-ttu-id="26ac0-131">在页面的左侧导航窗格中，Microsoft 365 合规中心审核 **"。**</span><span class="sxs-lookup"><span data-stu-id="26ac0-131">In the left navigation pane of the Microsoft 365 compliance center, click **Audit**.</span></span>

   <span data-ttu-id="26ac0-132">如果未为组织启用审核，则会显示横幅，提示你开始录制用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="26ac0-132">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>

   ![审核页上的横幅](../media/AuditingBanner.png)

3. <span data-ttu-id="26ac0-134">单击" **开始录制用户和管理员活动"** 横幅。</span><span class="sxs-lookup"><span data-stu-id="26ac0-134">Click the **Start recording user and admin activity** banner.</span></span>

   <span data-ttu-id="26ac0-135">更改最多可能需要 60 分钟才能生效。</span><span class="sxs-lookup"><span data-stu-id="26ac0-135">It may take up to 60 minutes for the change to take effect.</span></span>

### <a name="use-powershell-to-turn-on-auditing"></a><span data-ttu-id="26ac0-136">使用 PowerShell 启用审核</span><span class="sxs-lookup"><span data-stu-id="26ac0-136">Use PowerShell to turn on auditing</span></span>

1. <span data-ttu-id="26ac0-137">[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="26ac0-137">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="26ac0-138">运行以下 PowerShell 命令以启用审核。</span><span class="sxs-lookup"><span data-stu-id="26ac0-138">Run the following PowerShell command to turn on auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $true
    ```

    <span data-ttu-id="26ac0-139">将显示一条消息，指出更改最多可能需要 60 分钟才能生效。</span><span class="sxs-lookup"><span data-stu-id="26ac0-139">A message is displayed saying that it may take up to 60 minutes for the change to take effect.</span></span>
  
## <a name="turn-off-auditing"></a><span data-ttu-id="26ac0-140">关闭审核</span><span class="sxs-lookup"><span data-stu-id="26ac0-140">Turn off auditing</span></span>

<span data-ttu-id="26ac0-141">您必须使用 Exchange Online PowerShell 来关闭审核。</span><span class="sxs-lookup"><span data-stu-id="26ac0-141">You have to use Exchange Online PowerShell to turn off auditing.</span></span>
  
1. <span data-ttu-id="26ac0-142">[连接到 Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell)。</span><span class="sxs-lookup"><span data-stu-id="26ac0-142">[Connect to Exchange Online PowerShell](/powershell/exchange/connect-to-exchange-online-powershell).</span></span>

2. <span data-ttu-id="26ac0-143">运行以下 PowerShell 命令以关闭审核。</span><span class="sxs-lookup"><span data-stu-id="26ac0-143">Run the following PowerShell command to turn off auditing.</span></span>

    ```powershell
    Set-AdminAuditLogConfig -UnifiedAuditLogIngestionEnabled $false
    ```

3. <span data-ttu-id="26ac0-144">一段时间之后，验证审核是否处于关闭状态 (禁用) 。</span><span class="sxs-lookup"><span data-stu-id="26ac0-144">After a while, verify that auditing is turned off (disabled).</span></span> <span data-ttu-id="26ac0-145">可以通过两种方式来执行此操作：</span><span class="sxs-lookup"><span data-stu-id="26ac0-145">There are two ways to do this:</span></span>

    - <span data-ttu-id="26ac0-146">在 Exchange Online PowerShell 中，运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="26ac0-146">In Exchange Online PowerShell, run the following command:</span></span>

      ```powershell
      Get-AdminAuditLogConfig | FL UnifiedAuditLogIngestionEnabled
      ```

      <span data-ttu-id="26ac0-147">`False` _UnifiedAuditLogIngestionEnabled_ 属性的值指示审核已关闭。</span><span class="sxs-lookup"><span data-stu-id="26ac0-147">The value of  `False` for the  _UnifiedAuditLogIngestionEnabled_ property indicates that auditing is turned off.</span></span>

    - <span data-ttu-id="26ac0-148">转到 **"审核**"页Microsoft 365 合规中心。</span><span class="sxs-lookup"><span data-stu-id="26ac0-148">Go to the **Audit** page in the Microsoft 365 compliance center.</span></span>

      <span data-ttu-id="26ac0-149">如果未为组织启用审核，则会显示横幅，提示你开始录制用户和管理员活动。</span><span class="sxs-lookup"><span data-stu-id="26ac0-149">If auditing is not turned on for your organization, a banner is displayed prompting you start recording user and admin activity.</span></span>
