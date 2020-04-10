---
title: Microsoft 365 使用情况分析疑难解答
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: a73632a1-62c8-4a13-8115-913773b30f93
description: 了解如何解决 Microsoft 365 使用情况分析模板应用程序中的问题。
ms.openlocfilehash: 7164aa246a79a8d8c5aa50d995b53b6221003c01
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212145"
---
# <a name="troubleshooting-microsoft-365-usage-analytics"></a><span data-ttu-id="94160-103">Microsoft 365 使用情况分析疑难解答</span><span class="sxs-lookup"><span data-stu-id="94160-103">Troubleshooting Microsoft 365 usage analytics</span></span>

<span data-ttu-id="94160-104">浏览以下错误消息列表，以获取有关 Microsoft 365 使用情况分析中最常见问题的帮助。</span><span class="sxs-lookup"><span data-stu-id="94160-104">Explore the following list of error messages to get help with the most common issues with Microsoft 365 usage analytics.</span></span>
  
    
## <a name="we-are-unable-to-process-your-request-you-have-to-first-subscribe-to-this-data-from-the-microsoft-365-admin-center"></a><span data-ttu-id="94160-105">无法处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="94160-105">We are unable to process your request.</span></span> <span data-ttu-id="94160-106">您必须先从 Microsoft 365 管理中心订阅此数据</span><span class="sxs-lookup"><span data-stu-id="94160-106">You have to first subscribe to this data from the Microsoft 365 admin center</span></span>

 <span data-ttu-id="94160-107">**错误代码：** 422</span><span class="sxs-lookup"><span data-stu-id="94160-107">**Error Code :** 422</span></span> 
  
 <span data-ttu-id="94160-108">**您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。</span><span class="sxs-lookup"><span data-stu-id="94160-108">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="94160-109">**原因：** 在连接到应用程序之前，您必须订阅来自 Microsoft 365 管理中心的数据。</span><span class="sxs-lookup"><span data-stu-id="94160-109">**Cause:** Before you can connect to the app you have to subscribe to the data from the Microsoft 365 admin center.</span></span> <span data-ttu-id="94160-110">如果不先执行此步骤，则不能连接到模板应用程序，即使你提供 Microsoft 365 租户 id 也是如此。</span><span class="sxs-lookup"><span data-stu-id="94160-110">If this step isn't done first, you won't be able to connect to the template app, even if you provide your Microsoft 365 tenant id.</span></span> 
  
 <span data-ttu-id="94160-111">**若要修复此错误：** 若要订阅数据，请转到管理中心\> **报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>，并在主仪表板页面上找到 Microsoft 365 使用情况分析磁贴。</span><span class="sxs-lookup"><span data-stu-id="94160-111">**To fix this error:** To subscribe to the data, go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="94160-112">选择 "**开始**使用" 按钮，然后在打开的 "**报告**" 窗格中，打开 "将**数据提供给 Power BI 的 Microsoft 365 使用情况分析**" 和 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="94160-112">Select the **Get started** button and then in the **Reports** pane that opens, turn the **Make data available to Microsoft 365 usage analytics for Power BI** setting on and **Save**.</span></span>
  
## <a name="we-are-processing-your-data"></a><span data-ttu-id="94160-113">正在处理你的数据</span><span class="sxs-lookup"><span data-stu-id="94160-113">We are processing your data</span></span>

 <span data-ttu-id="94160-114">**您将在其中看到以下消息：** 在 microsoft 365 管理中心的**使用**仪表板上的**microsoft 365 使用情况分析**磁贴中。</span><span class="sxs-lookup"><span data-stu-id="94160-114">**Where you will see this message:** In the **Microsoft 365 usage analytics** tile on the **Usage** dashboard in the Microsoft 365 admin center.</span></span> 
  
 <span data-ttu-id="94160-115">**原因：** 当您在 Microsoft 365 管理中心中[选择查看模板应用程序](enable-usage-analytics.md)中的数据时，Microsoft 365 系统会开始为您的组织生成历史使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="94160-115">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the Microsoft 365 admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="94160-116">此步骤可能需要 2 至 48 小时的时间，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="94160-116">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="94160-117">**若要修复此问题：** 只需耐心等待，但如果在3天后消息未更改为 "**数据已就绪**"，请[联系 Microsoft 365 以获取商业支持](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="94160-117">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** after 3 days, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="we-are-unable-to-process-your-request-at-this-time-we-are-still-preparing-the-data-for-your-organization"></a><span data-ttu-id="94160-118">我们现在无法处理你的请求。</span><span class="sxs-lookup"><span data-stu-id="94160-118">We are unable to process your request at this time.</span></span> <span data-ttu-id="94160-119">仍在准备组织数据</span><span class="sxs-lookup"><span data-stu-id="94160-119">We are still preparing the data for your organization</span></span>

 <span data-ttu-id="94160-120">**错误代码：** 423</span><span class="sxs-lookup"><span data-stu-id="94160-120">**Error Code:** 423</span></span> 
  
 <span data-ttu-id="94160-121">**您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。</span><span class="sxs-lookup"><span data-stu-id="94160-121">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="94160-122">**原因：** 当您[选择从管理中心查看模板应用程序](enable-usage-analytics.md)中的数据时，Microsoft 365 系统会开始为您的组织生成历史使用情况数据。</span><span class="sxs-lookup"><span data-stu-id="94160-122">**Cause:** When you [opt in to seeing data in the template app](enable-usage-analytics.md) from the admin center, the Microsoft 365 system starts generating historical usage data for your organization.</span></span> <span data-ttu-id="94160-123">此步骤可能需要 2 至 48 小时的时间，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="94160-123">Depending on the size of your tenant, this step could take anywhere between 2 hours to 48 hours.</span></span> 
  
 <span data-ttu-id="94160-124">**若要修复此问题：** 只需耐心等待，但是如果自启动以来，如果消息未更改为 "**数据已就绪**"，则[请联系 Microsoft 365 以获取商业支持](../contact-support-for-business-products.md)。</span><span class="sxs-lookup"><span data-stu-id="94160-124">**To fix this:** Just be patient, but if the message does not change to **Your data is ready** even 3 days since initiation, [contact Microsoft 365 for business support](../contact-support-for-business-products.md).</span></span>
  
## <a name="the-tenant-id-you-provided-is-not-in-the-correct-format"></a><span data-ttu-id="94160-125">提供的租户 ID 格式不正确</span><span class="sxs-lookup"><span data-stu-id="94160-125">The tenant ID you provided is not in the correct format</span></span>

 <span data-ttu-id="94160-126">**错误代码：** 400</span><span class="sxs-lookup"><span data-stu-id="94160-126">**Error Code:** 400</span></span> 
  
 <span data-ttu-id="94160-127">**您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。</span><span class="sxs-lookup"><span data-stu-id="94160-127">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="94160-p107">**原因：** 租户 ID 为 GUID，且必须为 xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx 格式。如果在租户输入框中输入任何其他字符串，将收到此错误。</span><span class="sxs-lookup"><span data-stu-id="94160-p107">**Cause:** The tenant id is a guid and has to be in the format of xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx. If you enter any other string in the tenant input box you will get this error.</span></span> 
  
 <span data-ttu-id="94160-130">**若要修复此错误：** 转\>到 "管理中心"**报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>，并在主仪表板页面上找到 "Microsoft 365 使用情况分析" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="94160-130">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="94160-131">该磁贴上列出了租户 ID。</span><span class="sxs-lookup"><span data-stu-id="94160-131">The tenant id is listed on the tile.</span></span> <span data-ttu-id="94160-132">您可以从此处复制它，并将其粘贴到对话框中，以连接到模板应用程序。</span><span class="sxs-lookup"><span data-stu-id="94160-132">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="the-tenant-id-you-provided-is-not-recognized-by-our-system"></a><span data-ttu-id="94160-133">系统无法识别你提供的租户 ID</span><span class="sxs-lookup"><span data-stu-id="94160-133">The tenant ID you provided is not recognized by our system</span></span>

 <span data-ttu-id="94160-134">**错误代码：** 404</span><span class="sxs-lookup"><span data-stu-id="94160-134">**Error Code:** 404</span></span> 
  
 <span data-ttu-id="94160-135">**您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。</span><span class="sxs-lookup"><span data-stu-id="94160-135">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="94160-136">**原因：** 提供的租户 ID 无效或不存在。</span><span class="sxs-lookup"><span data-stu-id="94160-136">**Cause:** The tenant id you provided is not valid or does not exist.</span></span> 
  
 <span data-ttu-id="94160-137">**若要修复此错误：** 转\>到 "管理中心"**报告** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>，并在主仪表板页面上找到 "Microsoft 365 使用情况分析" 磁贴。</span><span class="sxs-lookup"><span data-stu-id="94160-137">**To fix this error:** Go to the admin center \> **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> and locate the Microsoft 365 usage analytics tile on the main dashboard page.</span></span> <span data-ttu-id="94160-138">该磁贴上列出了租户 ID。</span><span class="sxs-lookup"><span data-stu-id="94160-138">The tenant id is listed on the tile.</span></span> <span data-ttu-id="94160-139">您可以从此处复制它，并将其粘贴到对话框中，以连接到模板应用程序。</span><span class="sxs-lookup"><span data-stu-id="94160-139">You can copy it from here and paste it in the dialog box for connecting to the template app.</span></span> 
  
## <a name="please-re-enter-your-credentials-to-sign-in-to-power-bi-again"></a><span data-ttu-id="94160-140">请重新输入凭据以再次登录到 Power BI</span><span class="sxs-lookup"><span data-stu-id="94160-140">Please re-enter your credentials to sign in to Power BI again</span></span>

<span data-ttu-id="94160-141">错误代码:302</span><span class="sxs-lookup"><span data-stu-id="94160-141">Error Code: 302</span></span>
  
 <span data-ttu-id="94160-142">**您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。</span><span class="sxs-lookup"><span data-stu-id="94160-142">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="94160-143">**原因：** 授权代码失败，可能需要再次输入凭据。</span><span class="sxs-lookup"><span data-stu-id="94160-143">**Cause:** The authorization code failed and may require you to enter your credentials again.</span></span> 
  
 <span data-ttu-id="94160-144">**若要修复此错误：** 注销 Power BI，然后再次登录。</span><span class="sxs-lookup"><span data-stu-id="94160-144">**To fix this error:** Sign out of Power BI, and then sign in again.</span></span> 
  
## <a name="you-do-not-have-the-right-authorization-to-access-to-this-data-to-be-able-to-gain-access-to-the-data-from-this-service-you-need-to-be-either-a-global-admin-or-any-one-of-the-product-admins"></a><span data-ttu-id="94160-145">你不具有访问此数据的正确授权。</span><span class="sxs-lookup"><span data-stu-id="94160-145">You do not have the right authorization to access to this data.</span></span> <span data-ttu-id="94160-146">需要是全局管理员或任一产品管理员才能获取从该服务访问数据的权限</span><span class="sxs-lookup"><span data-stu-id="94160-146">To be able to gain access to the data from this service you need to be either a global admin or any one of the product admins</span></span>

 <span data-ttu-id="94160-147">**错误代码：** 403</span><span class="sxs-lookup"><span data-stu-id="94160-147">**Error Code:** 403</span></span> 
  
 <span data-ttu-id="94160-148">**您将在其中看到以下消息：** 在 Power BI 中，当您连接到 Microsoft 365 使用情况分析模板应用或直接调用 Microsoft 365 报告 Api 时。</span><span class="sxs-lookup"><span data-stu-id="94160-148">**Where you will see this message:** In Power BI when you are connecting to the Microsoft 365 Usage Analytics template app or when directly calling the Microsoft 365 Reporting APIs.</span></span> 
  
 <span data-ttu-id="94160-149">**原因：** 授权代码失败，因为尝试连接到模板应用程序的用户不具有访问此数据的适当级别的授权。</span><span class="sxs-lookup"><span data-stu-id="94160-149">**Cause:** The authorization code failed because the user who tried connecting to the template app does not have the right level of authorization to access this data.</span></span> 
  
 <span data-ttu-id="94160-150">**若要修复此错误：** 提供用户的凭据，该用户是**全局管理员**、 **Exchange 管理员**、 **Skype for business 管理员**、 **SharePoint 管理员**、**全局读者**或**报告阅读器**以连接到模板应用。</span><span class="sxs-lookup"><span data-stu-id="94160-150">**To fix this error:** Provide the credentials of a user who is either a **Global admin**, **Exchange admin**, **Skype for Business admin**, **SharePoint admin**, **Global reader** or **Report reader** to connect to the template app.</span></span> <span data-ttu-id="94160-151">有关详细信息，请参阅[关于管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="94160-151">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
## <a name="refresh-failed"></a><span data-ttu-id="94160-152">刷新失败</span><span class="sxs-lookup"><span data-stu-id="94160-152">Refresh failed</span></span>

 <span data-ttu-id="94160-153">**将出现此消息的情况：** Power BI 中的电子邮件或刷新历史记录中的失败状态。</span><span class="sxs-lookup"><span data-stu-id="94160-153">**Where you will see this message:** Email from Power BI or failed status in the refresh history.</span></span> 
  
 <span data-ttu-id="94160-154">**原因：** 有时，连接到模板应用程序的用户的凭据会重置，并且未在模板应用程序的连接设置中进行更新，从而导致用户看到刷新失败错误。</span><span class="sxs-lookup"><span data-stu-id="94160-154">**Cause:** Sometimes the credentials of the user who connected to the template app are reset, and not updated in the connection settings of the template app causing the user to see refresh failure errors.</span></span> 
  
 <span data-ttu-id="94160-155">**若要修复此错误：** 在 Power BI 中，查找与 Microsoft 365 使用情况分析模板应用程序对应的数据集，选择 "**计划刷新**并提供管理员凭据"。</span><span class="sxs-lookup"><span data-stu-id="94160-155">**To fix this error:** In Power BI, find the dataset corresponding to the Microsoft 365 Usage Analytics template app, select **schedule refresh** and provide your admin credentials.</span></span> 
  
<span data-ttu-id="94160-156">如果不起作用，请清除缓存，然后重新创建模板应用。</span><span class="sxs-lookup"><span data-stu-id="94160-156">If that doesn't work, clear the cache, and re-create the template app.</span></span>
  
  
