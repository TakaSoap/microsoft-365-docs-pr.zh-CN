---
title: 在设备上安装 Intune 公司门户
description: 有关在 Microsoft 托管桌面设备上安装公司门户应用程序的信息
keywords: Microsoft 托管桌面，Microsoft 365，公司门户
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 371656168f32db86ff32f187736d59dbd5dbe749
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46529691"
---
# <a name="install-intune-company-portal-on-on-devices"></a><span data-ttu-id="131a8-104">在设备上安装 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="131a8-104">Install Intune Company Portal on on devices</span></span>

<span data-ttu-id="131a8-105">Microsoft 托管桌面要求 IT 管理员使用 Microsoft 托管桌面设备为其用户安装 Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="131a8-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="131a8-106">以下是贵组织的一些好处：</span><span class="sxs-lookup"><span data-stu-id="131a8-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="131a8-107">用户有一个位置来浏览和安装可用的应用程序。</span><span class="sxs-lookup"><span data-stu-id="131a8-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="131a8-108">IT 管理员可以按类别组织其用户的应用程序。</span><span class="sxs-lookup"><span data-stu-id="131a8-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="131a8-109">有些应用程序（如 Microsoft Project 和 Microsoft Visio）要求公司门户部署 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="131a8-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="131a8-110">IT 管理员可以为其组织自定义公司门户。</span><span class="sxs-lookup"><span data-stu-id="131a8-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="131a8-111">这包括品牌图像、在本地支持联系人中添加等。</span><span class="sxs-lookup"><span data-stu-id="131a8-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="131a8-112">有关详细信息，请参阅 how [To Configure The Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app)。</span><span class="sxs-lookup"><span data-stu-id="131a8-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](https://docs.microsoft.com/intune/company-portal-app).</span></span>   

<span data-ttu-id="131a8-113">本主题介绍了将 Intune 公司门户部署到 Microsoft 托管桌面用户的过程。</span><span class="sxs-lookup"><span data-stu-id="131a8-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="131a8-114">整个过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="131a8-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="131a8-115">从 Microsoft Store for Business 购买公司门户并与 Intune 同步</span><span class="sxs-lookup"><span data-stu-id="131a8-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="131a8-116">为您的用户分配公司门户</span><span class="sxs-lookup"><span data-stu-id="131a8-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="131a8-117">向用户传达更改</span><span class="sxs-lookup"><span data-stu-id="131a8-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="131a8-118">第1步-从 Microsoft Store for Business 购买公司门户并与 Intune 同步</span><span class="sxs-lookup"><span data-stu-id="131a8-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="131a8-119">有关如何购买应用并与 Intune 同步的信息，请参阅将*应用程序部署到 Microsoft 托管桌面设备*中的[Microsoft Store for Business 应用](deploy-apps.md#msfb-apps)。</span><span class="sxs-lookup"><span data-stu-id="131a8-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="131a8-120">本主题提供了有关如何执行以下操作的信息：</span><span class="sxs-lookup"><span data-stu-id="131a8-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="131a8-121">购买 Microsoft Store for Business 中的公司门户</span><span class="sxs-lookup"><span data-stu-id="131a8-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="131a8-122">在 Intune 与 Microsoft Store for Business 之间强制同步</span><span class="sxs-lookup"><span data-stu-id="131a8-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="131a8-123">验证 Intune 与 Microsoft Store for Business 之间的主动同步</span><span class="sxs-lookup"><span data-stu-id="131a8-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="131a8-124">步骤 2-将公司门户分配给用户</span><span class="sxs-lookup"><span data-stu-id="131a8-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="131a8-125">通过 Microsoft 托管桌面管理门户将支持请求提交到 Microsoft 托管桌面操作。</span><span class="sxs-lookup"><span data-stu-id="131a8-125">Submit a support request to Microsoft Managed Desktop Operations through the Microsoft Managed Desktop Admin portal.</span></span> <span data-ttu-id="131a8-126">在支持请求中，请求将公司门户分配给您的用户。</span><span class="sxs-lookup"><span data-stu-id="131a8-126">In the support request, request that Company Portal be assigned to your users.</span></span> <span data-ttu-id="131a8-127">Microsoft 托管桌面会将公司门户部署到你的租户，并将应用安装在组织中的 Microsoft 托管桌面设备上。</span><span class="sxs-lookup"><span data-stu-id="131a8-127">Microsoft Managed Desktop will deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

<span data-ttu-id="131a8-128">有关使用 Microsoft 托管桌面提交支持请求的详细信息，请参阅[Microsoft 托管桌面的管理员支持](../working-with-managed-desktop/admin-support.md)。</span><span class="sxs-lookup"><span data-stu-id="131a8-128">For more information on submitting support requests with Microsoft Managed Desktop, see [Admin support for Microsoft Managed Desktop](../working-with-managed-desktop/admin-support.md).</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="131a8-129">第3步-将更改传达给用户</span><span class="sxs-lookup"><span data-stu-id="131a8-129">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="131a8-130">作为组织的 IT 管理员，让你的用户知道如何在你的组织中使用公司门户，这一点非常重要。</span><span class="sxs-lookup"><span data-stu-id="131a8-130">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="131a8-131">Microsoft 托管桌面建议：</span><span class="sxs-lookup"><span data-stu-id="131a8-131">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="131a8-132">从公司门户安装应用程序的步骤。</span><span class="sxs-lookup"><span data-stu-id="131a8-132">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="131a8-133">有关详细信息，请参阅在[设备上安装和共享应用](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows)。</span><span class="sxs-lookup"><span data-stu-id="131a8-133">For more information, see [Install and share apps on your device](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="131a8-134">如何向 IT 管理员发送对当前不可用的应用程序的请求。</span><span class="sxs-lookup"><span data-stu-id="131a8-134">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="131a8-135">有关详细信息，请参阅[请求适用于工作或学校的应用程序](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。</span><span class="sxs-lookup"><span data-stu-id="131a8-135">For more information, see [Request an app for work or school](https://docs.microsoft.com/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="131a8-136">Microsoft 托管桌面入门步骤</span><span class="sxs-lookup"><span data-stu-id="131a8-136">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="131a8-137">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="131a8-137">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="131a8-138">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="131a8-138">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="131a8-139">分配许可证</span><span class="sxs-lookup"><span data-stu-id="131a8-139">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="131a8-140">部署 Intune 公司门户（本主题）</span><span class="sxs-lookup"><span data-stu-id="131a8-140">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="131a8-141">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="131a8-141">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="131a8-142">设置设备</span><span class="sxs-lookup"><span data-stu-id="131a8-142">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="131a8-143">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="131a8-143">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="131a8-144">部署应用</span><span class="sxs-lookup"><span data-stu-id="131a8-144">Deploy apps</span></span>](deploy-apps.md)
