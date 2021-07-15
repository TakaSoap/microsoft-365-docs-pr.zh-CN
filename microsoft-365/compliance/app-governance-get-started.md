---
title: 开始使用应用治理
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: hub-page
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 开始使用应用治理功能来治理你的应用。
ms.openlocfilehash: 58f3bab9f8c5e28ce921ab244b23c49682394795
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430704"
---
# <a name="get-started-with-app-governance-in-preview"></a><span data-ttu-id="50939-103">开始使用应用治理（预览版）</span><span class="sxs-lookup"><span data-stu-id="50939-103">Get started with app governance (in preview)</span></span>

<span data-ttu-id="50939-104">开始使用 Microsoft Cloud App Security 的应用治理附加产品:</span><span class="sxs-lookup"><span data-stu-id="50939-104">To begin using the app governance add-on to Microsoft Cloud App Security:</span></span>

1. <span data-ttu-id="50939-p101">验证账户是否有适当的许可级别。应用治理是 Microsoft Cloud App Security (MCAS) 的附加功能，因此 MCAS 必须作为独立产品或作为下面列出的各种许可证包的一部分存在于帐户中。</span><span class="sxs-lookup"><span data-stu-id="50939-p101">Verify your account has the appropriate level of licensing. App governance is an add-on feature for Microsoft Cloud App Security (MCAS), and thus MCAS must be present in your account as either a standalone product or as part of the various license packages listed below.</span></span>
1. <span data-ttu-id="50939-107">你必须具有下面列出的管理员角色之一才能访问门户中的应用治理页面。</span><span class="sxs-lookup"><span data-stu-id="50939-107">You must have one of the administrator roles listed below to access the app governance pages in the portal.</span></span>

## <a name="licensing-for-app-governance"></a><span data-ttu-id="50939-108">应用治理许可</span><span class="sxs-lookup"><span data-stu-id="50939-108">Licensing for app governance</span></span>

<span data-ttu-id="50939-109">在开始使用应用治理之前，应该先确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans)和任何加载项。</span><span class="sxs-lookup"><span data-stu-id="50939-109">Before you get started with the app governance, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="50939-110">若要访问和使用应用治理，你的组织必须拥有以下订阅或加载项之一：</span><span class="sxs-lookup"><span data-stu-id="50939-110">To access and use app governance, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="50939-111">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="50939-111">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="50939-112">Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="50939-112">Microsoft 365 E5</span></span>
- <span data-ttu-id="50939-113">Microsoft 365 E5 合规</span><span class="sxs-lookup"><span data-stu-id="50939-113">Microsoft 365 E5 Compliance</span></span>
- <span data-ttu-id="50939-114">Microsoft 365 E5 开发者（不包括 Windows 和音频会议）</span><span class="sxs-lookup"><span data-stu-id="50939-114">Microsoft 365 E5 Developer (without Windows and Audio Conferencing)</span></span>
- <span data-ttu-id="50939-115">Microsoft 365 E5 信息保护和治理</span><span class="sxs-lookup"><span data-stu-id="50939-115">Microsoft 365 E5 Information Protection and Governance</span></span>
- <span data-ttu-id="50939-116">Microsoft 365 E5 安全性</span><span class="sxs-lookup"><span data-stu-id="50939-116">Microsoft 365 E5 Security</span></span>
- <span data-ttu-id="50939-117">Microsoft 365 E5（含呼叫分钟数）</span><span class="sxs-lookup"><span data-stu-id="50939-117">Microsoft 365 E5 with Calling Minutes</span></span>
- <span data-ttu-id="50939-118">不含音频会议的 Microsoft 365 E5</span><span class="sxs-lookup"><span data-stu-id="50939-118">Microsoft 365 E5 without Audio Conferencing</span></span>
- <span data-ttu-id="50939-119">Microsoft 365 A5 合规中心教职员工版</span><span class="sxs-lookup"><span data-stu-id="50939-119">Microsoft 365 A5 Compliance for faculty</span></span>
- <span data-ttu-id="50939-120">Microsoft 365 A5 合规中心学生版</span><span class="sxs-lookup"><span data-stu-id="50939-120">Microsoft 365 A5 Compliance for students</span></span>
- <span data-ttu-id="50939-121">Microsoft 365 A5 教职员工版</span><span class="sxs-lookup"><span data-stu-id="50939-121">Microsoft 365 A5 for faculty</span></span>
- <span data-ttu-id="50939-122">Microsoft 365 A5 学生版</span><span class="sxs-lookup"><span data-stu-id="50939-122">Microsoft 365 A5 for students</span></span>
- <span data-ttu-id="50939-123">Microsoft 365 A5 信息保护和治理教职员工版</span><span class="sxs-lookup"><span data-stu-id="50939-123">Microsoft 365 A5 Information Protection and Governance for faculty</span></span>
- <span data-ttu-id="50939-124">Microsoft 365 A5 信息保护和治理学生版</span><span class="sxs-lookup"><span data-stu-id="50939-124">Microsoft 365 A5 Information Protection and Governance for students</span></span>
- <span data-ttu-id="50939-125">Microsoft 365 A5 安全中心教职员工版</span><span class="sxs-lookup"><span data-stu-id="50939-125">Microsoft 365 A5 Security for faculty</span></span>
- <span data-ttu-id="50939-126">Microsoft 365 A5 安全中心学生版</span><span class="sxs-lookup"><span data-stu-id="50939-126">Microsoft 365 A5 Security for students</span></span>
- <span data-ttu-id="50939-127">Microsoft 365 A5 学生版使用权益</span><span class="sxs-lookup"><span data-stu-id="50939-127">Microsoft 365 A5 student use benefits</span></span>
- <span data-ttu-id="50939-128">Microsoft 365 A5（含呼叫分钟数）教职员工版</span><span class="sxs-lookup"><span data-stu-id="50939-128">Microsoft 365 A5 with Calling Minutes for Faculty</span></span>
- <span data-ttu-id="50939-129">Microsoft 365 A5（含呼叫分钟数）学生版</span><span class="sxs-lookup"><span data-stu-id="50939-129">Microsoft 365 A5 with Calling Minutes for Students</span></span>
- <span data-ttu-id="50939-130">Microsoft 365 A5（不包括音频会议）教职员工版</span><span class="sxs-lookup"><span data-stu-id="50939-130">Microsoft 365 A5 without Audio Conferencing for faculty</span></span>
- <span data-ttu-id="50939-131">Microsoft 365 A5（包括音频会议）学生版</span><span class="sxs-lookup"><span data-stu-id="50939-131">Microsoft 365 A5 without Audio Conferencing for students</span></span>
- <span data-ttu-id="50939-132">Microsoft 365 A5（不包括音频会议）学生版使用权益</span><span class="sxs-lookup"><span data-stu-id="50939-132">Microsoft 365 A5 without Audio Conferencing for students use benefit</span></span>

## <a name="administrator-roles"></a><span data-ttu-id="50939-133">管理员角色</span><span class="sxs-lookup"><span data-stu-id="50939-133">Administrator roles</span></span>

<span data-ttu-id="50939-134">若要查看应用治理页面或管理策略和设置，需要以下管理员角色之一：</span><span class="sxs-lookup"><span data-stu-id="50939-134">One of the following administrator roles are required to see app governance pages or manage policies and settings:</span></span>

- <span data-ttu-id="50939-135"> 应用程序管理员</span><span class="sxs-lookup"><span data-stu-id="50939-135">Application Administrator</span></span>
- <span data-ttu-id="50939-136">云 应用程序管理员</span><span class="sxs-lookup"><span data-stu-id="50939-136">Cloud Application Administrator</span></span>
- <span data-ttu-id="50939-137">公司管理员</span><span class="sxs-lookup"><span data-stu-id="50939-137">Company Administrator</span></span>
- <span data-ttu-id="50939-138">合规管理员</span><span class="sxs-lookup"><span data-stu-id="50939-138">Compliance Administrator</span></span>
- <span data-ttu-id="50939-139">合规数据管理员</span><span class="sxs-lookup"><span data-stu-id="50939-139">Compliance Data Administrator</span></span>
- <span data-ttu-id="50939-140">合规信息读取者（只读）</span><span class="sxs-lookup"><span data-stu-id="50939-140">Compliance Reader (read-only)</span></span>
- <span data-ttu-id="50939-141">全局读取者</span><span class="sxs-lookup"><span data-stu-id="50939-141">Global Reader</span></span>
- <span data-ttu-id="50939-142">安全管理员</span><span class="sxs-lookup"><span data-stu-id="50939-142">Security Administrator</span></span>
- <span data-ttu-id="50939-143">安全操作员</span><span class="sxs-lookup"><span data-stu-id="50939-143">Security Operator</span></span>
- <span data-ttu-id="50939-144">安全信息读取者（只读）</span><span class="sxs-lookup"><span data-stu-id="50939-144">Security Reader (read-only)</span></span>

<span data-ttu-id="50939-145">以下是每个角色的能力。</span><span class="sxs-lookup"><span data-stu-id="50939-145">Here are the capabilities for each role.</span></span>

| <span data-ttu-id="50939-146">角色</span><span class="sxs-lookup"><span data-stu-id="50939-146">Role</span></span> | <span data-ttu-id="50939-147">阅读仪表板</span><span class="sxs-lookup"><span data-stu-id="50939-147">Read the dashboard</span></span> | <span data-ttu-id="50939-148">读取所有应用</span><span class="sxs-lookup"><span data-stu-id="50939-148">Read all apps</span></span> |<span data-ttu-id="50939-149">读取策略</span><span class="sxs-lookup"><span data-stu-id="50939-149">Read policies</span></span> | <span data-ttu-id="50939-150">创建、更新或删除策略</span><span class="sxs-lookup"><span data-stu-id="50939-150">Create, update, or delete policies</span></span> | <span data-ttu-id="50939-151">读取警报</span><span class="sxs-lookup"><span data-stu-id="50939-151">Read alerts</span></span> | <span data-ttu-id="50939-152">更新警报</span><span class="sxs-lookup"><span data-stu-id="50939-152">Update alerts</span></span> | <span data-ttu-id="50939-153">读取设置</span><span class="sxs-lookup"><span data-stu-id="50939-153">Read settings</span></span> | <span data-ttu-id="50939-154">更新设置</span><span class="sxs-lookup"><span data-stu-id="50939-154">Update settings</span></span> | <span data-ttu-id="50939-155">读取修正</span><span class="sxs-lookup"><span data-stu-id="50939-155">Read Remediation</span></span> | <span data-ttu-id="50939-156">更新修正</span><span class="sxs-lookup"><span data-stu-id="50939-156">Update Remediation</span></span> |
|:-------|:-----|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|:-------|
| <span data-ttu-id="50939-157">应用程序管理员</span><span class="sxs-lookup"><span data-stu-id="50939-157">Application Administrator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| <span data-ttu-id="50939-168">云应用程序管理员</span><span class="sxs-lookup"><span data-stu-id="50939-168">Cloud Application Administrator</span></span> | ![复选标记](..\media\checkmark.png) | | | | | | | | | |
| <span data-ttu-id="50939-170">公司管理员</span><span class="sxs-lookup"><span data-stu-id="50939-170">Company Administrator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |
| <span data-ttu-id="50939-181">合规管理员</span><span class="sxs-lookup"><span data-stu-id="50939-181">Compliance Administrator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | |
| <span data-ttu-id="50939-190">合规数据管理员</span><span class="sxs-lookup"><span data-stu-id="50939-190">Compliance Data Administrator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | |
| <span data-ttu-id="50939-199">合规信息读取者</span><span class="sxs-lookup"><span data-stu-id="50939-199">Compliance Reader</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | | |
| <span data-ttu-id="50939-205">全局读取者</span><span class="sxs-lookup"><span data-stu-id="50939-205">Global Reader</span></span>  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | | |
| <span data-ttu-id="50939-211">安全管理员</span><span class="sxs-lookup"><span data-stu-id="50939-211">Security Administrator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | |
| <span data-ttu-id="50939-220">安全操作员</span><span class="sxs-lookup"><span data-stu-id="50939-220">Security Operator</span></span> | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | |
| <span data-ttu-id="50939-230">安全信息读取者</span><span class="sxs-lookup"><span data-stu-id="50939-230">Security Reader</span></span>  | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) |  | ![复选标记](..\media\checkmark.png) | |
|||||||||| | |

<span data-ttu-id="50939-237">有关每个角色的其他信息，请参阅[管理员角色权限](/azure/active-directory/roles/permissions-reference)。</span><span class="sxs-lookup"><span data-stu-id="50939-237">For additional information about each role, see [Administrator role permissions](/azure/active-directory/roles/permissions-reference).</span></span>

## <a name="add-app-governance-to-your-microsoft-365-account"></a><span data-ttu-id="50939-238">将应用治理添加到你的 Microsoft 365 帐户</span><span class="sxs-lookup"><span data-stu-id="50939-238">Add app governance to your Microsoft 365 account</span></span>

<span data-ttu-id="50939-239">对于现有的 Microsoft 365 客户：</span><span class="sxs-lookup"><span data-stu-id="50939-239">For existing Microsoft 365 customers:</span></span>

1. <span data-ttu-id="50939-240">在你的“[Microsoft 365 管理中心](https://admin.microsoft.com)”，导航到 **“计费”-“购买服务”**，然后单击“**加载项**”。</span><span class="sxs-lookup"><span data-stu-id="50939-240">In your [Microsoft 365 admin center](https://admin.microsoft.com), navigate to **Billing - Purchase services** and click **Add-ons**.</span></span>
1. <span data-ttu-id="50939-241">在应用治理卡片中，单击“**详细信息**”。</span><span class="sxs-lookup"><span data-stu-id="50939-241">In the app governance card, click **Details**.</span></span>
1. <span data-ttu-id="50939-242">单击“**开始免费试用**”。</span><span class="sxs-lookup"><span data-stu-id="50939-242">Click **Start free trial**.</span></span>
1. <span data-ttu-id="50939-243">填写请求的信息，以将应用治理添加到所选租户。</span><span class="sxs-lookup"><span data-stu-id="50939-243">Complete the requested information to add app governance to your selected tenant.</span></span> <span data-ttu-id="50939-244">如果你是新客户，必须先提供信息来建立帐户并创建针对你的试用期的租户。</span><span class="sxs-lookup"><span data-stu-id="50939-244">I you are a new customer, you must first provide information to establish an account and create a tenant for your trial period.</span></span> <span data-ttu-id="50939-245">完成此操作后，即可将应用治理添加到试用版。</span><span class="sxs-lookup"><span data-stu-id="50939-245">Once this is done you can add app governance to the trial.</span></span>

<span data-ttu-id="50939-246">对于新的 Microsoft 365 客户：</span><span class="sxs-lookup"><span data-stu-id="50939-246">For new Microsoft 365 customers:</span></span>

1. <span data-ttu-id="50939-247">在此页面顶部，单击“**免费帐户**”按钮。</span><span class="sxs-lookup"><span data-stu-id="50939-247">At the top of this page, click the **Free Account** button.</span></span>
1. <span data-ttu-id="50939-248">在“**试用 Microsoft 365 商业版**”下，单击“**免费试用 1 个月**”。</span><span class="sxs-lookup"><span data-stu-id="50939-248">Under **Try Microsoft 365 for business** click **Try 1 month free**.</span></span>

<span data-ttu-id="50939-249">对于新客户和现有客户：</span><span class="sxs-lookup"><span data-stu-id="50939-249">For both:</span></span>

1. <span data-ttu-id="50939-250">在注册门户中，提供用于试用的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="50939-250">In the sign-up portal, provide your email address to use for the trial.</span></span> <span data-ttu-id="50939-251">如果你是现有客户，请使用与你的帐户关联的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="50939-251">If you are an existing customer, use the email associated with your account.</span></span> <span data-ttu-id="50939-252">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="50939-252">Click **Next**</span></span>
1. <span data-ttu-id="50939-253">登录后，单击“**立即试用**”以获取免费试用版。</span><span class="sxs-lookup"><span data-stu-id="50939-253">Once you have signed in, click **Try now** to get the free trial.</span></span>
1. <span data-ttu-id="50939-254">单击“**继续**”关闭页面并开始设置试用版。</span><span class="sxs-lookup"><span data-stu-id="50939-254">Click **Continue** to close page and begin trial setup.</span></span> <span data-ttu-id="50939-255">对于应用治理的新客户，应用治理实例最多需要两个小时才可用。</span><span class="sxs-lookup"><span data-stu-id="50939-255">For new app governance customers, it will take up to two hours for your app governance instance to become available.</span></span> <span data-ttu-id="50939-256">对于现有客户，现有服务不会中断。</span><span class="sxs-lookup"><span data-stu-id="50939-256">For existing customers, there will be no interruption of existing services.</span></span>
  > [!NOTE]
<span data-ttu-id="50939-257">如果你还没有帐户，系统会提示你先设置一个新帐户，然后才能继续试用。</span><span class="sxs-lookup"><span data-stu-id="50939-257">If you do not already have an account you will be prompted to set up a new account before you can proceed with the trial.</span></span>

1. <span data-ttu-id="50939-258">为你的 AAD 租户输入一个可用的域名，然后单击“**检查可用性**”。</span><span class="sxs-lookup"><span data-stu-id="50939-258">Enter in an available domain name for your AAD tenant and click **Check availability**.</span></span> <span data-ttu-id="50939-259">系统会自动为你分配一个管理员角色（如果你没有用于应用治理的现有角色），并且可以随时更改域名和/或稍后通过 Microsoft 365 管理中心购买更多租户。</span><span class="sxs-lookup"><span data-stu-id="50939-259">You will automatically be assigned an Admin role (if you don’t have an existing role for app governance) and can always change the domain name and/or purchase more tenants later through the Microsoft 365 admin center.</span></span>
1. <span data-ttu-id="50939-260">输入要用于登录帐户的用户名和密码。</span><span class="sxs-lookup"><span data-stu-id="50939-260">Enter the username and password you would like to use to login to your account.</span></span> <span data-ttu-id="50939-261">单击“**注册**”。</span><span class="sxs-lookup"><span data-stu-id="50939-261">Click **Sign up**.</span></span>
1. <span data-ttu-id="50939-262">单击“**开始使用**”转至应用治理门户，或者单击“**管理订阅**”转至 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="50939-262">Click **Get started** to go to the app governance portal or **Manage your subscription** to go to the Microsoft 365 admin center.</span></span>
