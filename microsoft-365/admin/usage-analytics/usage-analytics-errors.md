---
title: Microsoft 365 使用情况分析疑难解答
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: 了解如何解决 Microsoft 365 使用情况分析模板应用的问题。
ms.openlocfilehash: bc7f1f7188a209188f1a67a20bf79477c6e1d4a0
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580734"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="46e40-103">Microsoft 365 使用情况分析疑难解答</span><span class="sxs-lookup"><span data-stu-id="46e40-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="46e40-104">浏览以下错误消息列表，获取有关 Microsoft 365 使用情况分析的最常见问题的帮助。</span><span class="sxs-lookup"><span data-stu-id="46e40-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="46e40-105">无法处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="46e40-105">We are unable to process your request.</span></span> <span data-ttu-id="46e40-106">你首先需要从 Microsoft 365 管理中心订阅此数据</span><span class="sxs-lookup"><span data-stu-id="46e40-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="46e40-107">**错误代码** ：422</span><span class="sxs-lookup"><span data-stu-id="46e40-107">**Error Code:** 422</span></span> 
  
 <span data-ttu-id="46e40-108">**将在什么位置看到此消息：** 在 Power BI 中，当连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。</span><span class="sxs-lookup"><span data-stu-id="46e40-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="46e40-109">**原因：** 在连接到应用之前，你必须从 Microsoft 365 管理中心订阅数据。</span><span class="sxs-lookup"><span data-stu-id="46e40-109">**Cause:** Before you can connect to the app, you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="46e40-110">如果未首先完成此步骤，则即使提供 Microsoft 365 租户 ID，也将无法连接到模板应用。</span><span class="sxs-lookup"><span data-stu-id="46e40-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant ID.</span></span> 
  
 <span data-ttu-id="46e40-111">**若要修复此错误：** 若要订阅数据，请转到管理中心"报告使用情况"，并找到主仪表板页面上的 \>  \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank"></a>"Microsoft 365 使用情况分析"磁贴。</span><span class="sxs-lookup"><span data-stu-id="46e40-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="46e40-112">选择 **"开始"** 按钮，然后在打开的"报告"窗格中，打开"向 **Microsoft 365 使用情况分析提供 Power BI** 数据"设置并 **"保存"。**</span><span class="sxs-lookup"><span data-stu-id="46e40-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="46e40-113">正在处理你的数据</span><span class="sxs-lookup"><span data-stu-id="46e40-113">We are processing your data</span></span>

 <span data-ttu-id="46e40-114">**将在什么位置看到此消息：** 在 **Microsoft 365** 管理中心使用情况仪表板上的 Microsoft 365 使用情况分析磁贴中。</span><span class="sxs-lookup"><span data-stu-id="46e40-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="46e40-115">**原因：** 当你 [选择从](enable-usage-analytics.md) Microsoft 365 管理中心查看模板应用中的数据时，Microsoft 365 系统开始为组织生成历史使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="46e40-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="46e40-116">此步骤可能需要 2 至 48 小时的时间，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="46e40-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="46e40-117">**若要修复此问题，请进行修复：** 请耐心等待，但如果邮件未在 3天后更改为你的数据已准备就绪，请联系 [Microsoft 365 商业版支持](../contact-support-for-business-products.md)人员。</span><span class="sxs-lookup"><span data-stu-id="46e40-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="46e40-118">我们现在无法处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="46e40-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="46e40-119">仍在准备组织数据</span><span class="sxs-lookup"><span data-stu-id="46e40-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="46e40-120">**错误代码：** 423</span><span class="sxs-lookup"><span data-stu-id="46e40-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="46e40-121">**将在什么位置看到此消息：** 在 Power BI 中，当你连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。</span><span class="sxs-lookup"><span data-stu-id="46e40-121">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="46e40-122">**原因：** 当你 [选择从管理中心查看](enable-usage-analytics.md) 模板应用中的数据时，Microsoft 365 系统开始为组织生成历史使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="46e40-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="46e40-123">根据租户大小，此步骤可能需要 2 小时到 48 小时之间的任意时间。</span><span class="sxs-lookup"><span data-stu-id="46e40-123">Depending on the size of your tenant, this step could take anywhere between two hours to 48 hours.</span></span> 
  
 <span data-ttu-id="46e40-124">**若要修复此问题，请进行修复：** 请耐心等待，但如果消息在启动 3天后未更改为你的数据已准备就绪，请联系 [Microsoft 365 商业版支持](../contact-support-for-business-products.md)人员。</span><span class="sxs-lookup"><span data-stu-id="46e40-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="46e40-125">提供的租户 ID 格式不正确</span><span class="sxs-lookup"><span data-stu-id="46e40-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="46e40-126">**错误代码：** 400</span><span class="sxs-lookup"><span data-stu-id="46e40-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="46e40-127">**将在什么位置看到此消息：** 在 Power BI 中，当你连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。</span><span class="sxs-lookup"><span data-stu-id="46e40-127">**Where you will see this message:** In Power BI, when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="46e40-128">**原因：** 租户 ID 是 guid，必须采用 xxxxxxxx-xxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx 格式。</span><span class="sxs-lookup"><span data-stu-id="46e40-128">**Cause:** The tenant ID is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx.</span></span> <span data-ttu-id="46e40-129">如果在租户输入框中输入任何其他字符串，将收到此错误。</span><span class="sxs-lookup"><span data-stu-id="46e40-129">If you enter any other string in the tenant input box, you will get this error.</span></span> 
  
 <span data-ttu-id="46e40-130">**若要修复此错误：** 转到管理中心 \> **"报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况"，</a> 在主仪表板页面上找到"Microsoft 365 使用情况分析"磁贴。</span><span class="sxs-lookup"><span data-stu-id="46e40-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="46e40-131">租户 ID 在磁贴上列出。</span><span class="sxs-lookup"><span data-stu-id="46e40-131">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="46e40-132">你可以从此处复制它，并将其粘贴到对话框中以连接到模板应用。</span><span class="sxs-lookup"><span data-stu-id="46e40-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="46e40-133">系统无法识别你提供的租户 ID</span><span class="sxs-lookup"><span data-stu-id="46e40-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="46e40-134">**错误代码：** 404</span><span class="sxs-lookup"><span data-stu-id="46e40-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="46e40-135">**将在什么位置看到此消息：** 在 Power BI 中，当连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。</span><span class="sxs-lookup"><span data-stu-id="46e40-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="46e40-136">**原因：** 你提供的租户 ID 无效或不存在。</span><span class="sxs-lookup"><span data-stu-id="46e40-136">**Cause:** The tenant ID you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="46e40-137">**若要修复此错误：** 转到管理中心 \> **"报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况"，</a> 在主仪表板页面上找到"Microsoft 365 使用情况分析"磁贴。</span><span class="sxs-lookup"><span data-stu-id="46e40-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="46e40-138">租户 ID 在磁贴上列出。</span><span class="sxs-lookup"><span data-stu-id="46e40-138">The tenant ID is listed on the tile.</span></span> <span data-ttu-id="46e40-139">你可以从此处复制它，并将其粘贴到对话框中以连接到模板应用。</span><span class="sxs-lookup"><span data-stu-id="46e40-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="46e40-140">请重新输入凭据以再次登录到 Power BI</span><span class="sxs-lookup"><span data-stu-id="46e40-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="46e40-141">错误代码:302</span><span class="sxs-lookup"><span data-stu-id="46e40-141">Error Code: 302</span></span>
  
 <span data-ttu-id="46e40-142">**将在什么位置看到此消息：** 在 Power BI 中，当连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。</span><span class="sxs-lookup"><span data-stu-id="46e40-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="46e40-143">**原因：** 授权代码失败，可能需要再次输入凭据。</span><span class="sxs-lookup"><span data-stu-id="46e40-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="46e40-144">**若要修复此错误：** 注销 Power BI，然后再次登录。</span><span class="sxs-lookup"><span data-stu-id="46e40-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="46e40-145">你不具有访问此数据的正确授权。</span><span class="sxs-lookup"><span data-stu-id="46e40-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="46e40-146">需要是全局管理员或任一产品管理员才能获取从该服务访问数据的权限</span><span class="sxs-lookup"><span data-stu-id="46e40-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="46e40-147">**错误代码：** 403</span><span class="sxs-lookup"><span data-stu-id="46e40-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="46e40-148">**将在什么位置看到此消息：** 在 Power BI 中，当连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 API 时。</span><span class="sxs-lookup"><span data-stu-id="46e40-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="46e40-149">**原因：** 授权代码失败，因为尝试连接到模板应用的用户没有访问此数据的授权级别。</span><span class="sxs-lookup"><span data-stu-id="46e40-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="46e40-150">**若要修复此错误：** 提供全局管理员 **、Exchange** 管理员 **、Skype for Business** 管理员 **、SharePoint** 管理员、全局读取者或报表阅读者的用户凭据，以连接到模板应用。 </span><span class="sxs-lookup"><span data-stu-id="46e40-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="46e40-151">有关详细信息 [，请参阅](../add-users/about-admin-roles.md) 关于管理员角色。</span><span class="sxs-lookup"><span data-stu-id="46e40-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="46e40-152">刷新失败</span><span class="sxs-lookup"><span data-stu-id="46e40-152">Refresh failed</span></span>

 <span data-ttu-id="46e40-153">**将出现此消息的情况：** Power BI 中的电子邮件或刷新历史记录中的失败状态。</span><span class="sxs-lookup"><span data-stu-id="46e40-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="46e40-154">**原因：** 有时，连接到模板应用的用户的凭据会重置，并且不会在模板应用的连接设置中更新，从而导致用户看到刷新失败错误。</span><span class="sxs-lookup"><span data-stu-id="46e40-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="46e40-155">**若要修复此错误：** 在 Power BI 中，查找与 Microsoft 365 使用情况分析模板应用对应的数据集，选择计划刷新并提供管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="46e40-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="46e40-156">如果不起作用，请清除缓存，然后重新创建模板应用。</span><span class="sxs-lookup"><span data-stu-id="46e40-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
