---
title: 在设备上安装 Intune 公司门户
description: 有关在 Microsoft 托管桌面设备上安装公司门户应用的信息
keywords: Microsoft 托管桌面，Microsoft 365，公司门户
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: f9f36d6ca14be610ce9374380349264439282a6a
ms.sourcegitcommit: 1206319a5d3fed8d52a2581b8beafc34ab064b1c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/29/2021
ms.locfileid: "52086681"
---
# <a name="install-intune-company-portal-on-devices"></a><span data-ttu-id="95920-104">在设备上安装 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="95920-104">Install Intune Company Portal on devices</span></span>

<span data-ttu-id="95920-105">Microsoft 托管桌面要求 IT 管理员使用 Microsoft 托管桌面设备为用户安装 Intune 公司门户。</span><span class="sxs-lookup"><span data-stu-id="95920-105">Microsoft Managed Desktop requires that IT administrators install Intune Company Portal for their users with Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="95920-106">以下是组织的一些好处：</span><span class="sxs-lookup"><span data-stu-id="95920-106">Here are some benefits for your organization:</span></span>
- <span data-ttu-id="95920-107">用户有一个浏览和安装可用应用程序的位置。</span><span class="sxs-lookup"><span data-stu-id="95920-107">Users have one place to browse and install available applications.</span></span> 
- <span data-ttu-id="95920-108">IT 管理员可以按用户类别组织应用程序。</span><span class="sxs-lookup"><span data-stu-id="95920-108">IT administrators can organize applications by categories for their users.</span></span>  
- <span data-ttu-id="95920-109">某些应用程序 (Microsoft Project 和 Microsoft Visio) 需要公司门户与 Microsoft 托管桌面一起部署。</span><span class="sxs-lookup"><span data-stu-id="95920-109">Some applications (like Microsoft Project and Microsoft Visio) require Company Portal to deploy with Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="95920-110">IT 管理员可以为组织自定义公司门户。</span><span class="sxs-lookup"><span data-stu-id="95920-110">IT administrators can customize Company Portal for their organization.</span></span> <span data-ttu-id="95920-111">这包括品牌映像、添加本地支持联系人等。</span><span class="sxs-lookup"><span data-stu-id="95920-111">This includes brand imaging, adding in local support contacts, and more.</span></span> <span data-ttu-id="95920-112">有关详细信息，请参阅 [如何配置 Microsoft Intune 公司门户应用](/intune/company-portal-app)。</span><span class="sxs-lookup"><span data-stu-id="95920-112">For more information, see [How to Configure the Microsoft Intune Company Portal app](/intune/company-portal-app).</span></span>   

<span data-ttu-id="95920-113">本主题介绍将 Intune 公司门户部署到 Microsoft 托管桌面用户的过程。</span><span class="sxs-lookup"><span data-stu-id="95920-113">This topic documents the process for deploying the Intune Company Portal to your Microsoft Managed Desktop users.</span></span> <span data-ttu-id="95920-114">整个过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="95920-114">The overall process looks like this:</span></span>
1. <span data-ttu-id="95920-115">从适用于企业 Microsoft Store 购买公司门户，并同步到 Intune</span><span class="sxs-lookup"><span data-stu-id="95920-115">Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
2. <span data-ttu-id="95920-116">将公司门户分配给用户</span><span class="sxs-lookup"><span data-stu-id="95920-116">Assign Company Portal to your users</span></span>
3. <span data-ttu-id="95920-117">向用户传达更改</span><span class="sxs-lookup"><span data-stu-id="95920-117">Communicate change to your users</span></span>

## <a name="step-1---purchase-company-portal-from-microsoft-store-for-business-and-sync-with-intune"></a><span data-ttu-id="95920-118">步骤 1 - 从适用于 Business 的 Microsoft Store 购买公司门户，并同步到 Intune</span><span class="sxs-lookup"><span data-stu-id="95920-118">Step 1 - Purchase Company Portal from Microsoft Store for Business and sync with Intune</span></span>
<span data-ttu-id="95920-119">若要了解如何购买应用和与 Intune 同步，请参阅将应用部署到 *Microsoft 托管* 桌面设备中的 [适用于企业](deploy-apps.md#msfb-apps)应用的 Microsoft Store 应用。</span><span class="sxs-lookup"><span data-stu-id="95920-119">For info on how to purchase the apps and sync with Intune, see [Microsoft Store for Business apps](deploy-apps.md#msfb-apps) in *Deploy apps to Microsoft Managed Desktop devices*.</span></span>

<span data-ttu-id="95920-120">本主题提供如何：</span><span class="sxs-lookup"><span data-stu-id="95920-120">This topic provides info on how to:</span></span> 
- <span data-ttu-id="95920-121">从适用于企业 Microsoft Store 购买公司门户</span><span class="sxs-lookup"><span data-stu-id="95920-121">Purchase Company Portal from Microsoft Store for Business</span></span> 
- <span data-ttu-id="95920-122">在 Intune 和适用于 Business 的 Microsoft Store 之间强制同步</span><span class="sxs-lookup"><span data-stu-id="95920-122">Force sync between Intune and Microsoft Store for Business</span></span>
- <span data-ttu-id="95920-123">验证 Intune 和适用于 Business 的 Microsoft Store 之间的活动同步</span><span class="sxs-lookup"><span data-stu-id="95920-123">Verify active sync between Intune and Microsoft Store for Business</span></span> 

## <a name="step-2---assign-company-portal-to-your-users"></a><span data-ttu-id="95920-124">步骤 2 - 将公司门户分配给用户</span><span class="sxs-lookup"><span data-stu-id="95920-124">Step 2 - Assign Company Portal to your users</span></span>
<span data-ttu-id="95920-125">注册 Microsoft 托管桌面后，我们将自动将公司门户部署到租户，并在你的组织的 Microsoft 托管桌面设备上安装该应用。</span><span class="sxs-lookup"><span data-stu-id="95920-125">Following your enrollment in Microsoft Managed Desktop, we will automatically deploy Company Portal to your tenant and install the app on Microsoft Managed Desktop devices in your organization.</span></span>

## <a name="step-3---communicate-change-to-your-users"></a><span data-ttu-id="95920-126">步骤 3 - 将更改传达给用户</span><span class="sxs-lookup"><span data-stu-id="95920-126">Step 3 - Communicate change to your users</span></span>
<span data-ttu-id="95920-127">作为组织的 IT 管理员，让用户了解如何在组织中使用公司门户非常重要。</span><span class="sxs-lookup"><span data-stu-id="95920-127">As the IT administrator for your organization, it’s important to let your users know how to use Company Portal in your organization.</span></span> <span data-ttu-id="95920-128">Microsoft 托管桌面建议：</span><span class="sxs-lookup"><span data-stu-id="95920-128">Microsoft Managed Desktop recommends:</span></span>
- <span data-ttu-id="95920-129">从公司门户安装应用程序的步骤。</span><span class="sxs-lookup"><span data-stu-id="95920-129">Steps on installing applications from the Company Portal.</span></span> <span data-ttu-id="95920-130">有关详细信息，请参阅在设备上 [安装和共享应用](/intune-user-help/install-apps-cpapp-windows)。</span><span class="sxs-lookup"><span data-stu-id="95920-130">For more information, see [Install and share apps on your device](/intune-user-help/install-apps-cpapp-windows).</span></span>
- <span data-ttu-id="95920-131">如何向 IT 管理员发送当前不可用的应用程序的请求。</span><span class="sxs-lookup"><span data-stu-id="95920-131">How to send requests to IT administrators for applications that are not currently available.</span></span> <span data-ttu-id="95920-132">有关详细信息，请参阅请求 [工作或学校应用](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school)。</span><span class="sxs-lookup"><span data-stu-id="95920-132">For more information, see [Request an app for work or school](/intune-user-help/install-apps-cpapp-windows#request-an-app-for-work-or-school).</span></span>  

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="95920-133">Microsoft 托管桌面入门步骤</span><span class="sxs-lookup"><span data-stu-id="95920-133">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="95920-134">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="95920-134">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="95920-135">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="95920-135">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="95920-136">分配许可证</span><span class="sxs-lookup"><span data-stu-id="95920-136">Assign licenses</span></span>](assign-licenses.md)
4. <span data-ttu-id="95920-137">部署 Intune 公司门户 (本主题) </span><span class="sxs-lookup"><span data-stu-id="95920-137">Deploy Intune Company Portal (this topic)</span></span>
5. [<span data-ttu-id="95920-138">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="95920-138">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="95920-139">设置设备</span><span class="sxs-lookup"><span data-stu-id="95920-139">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="95920-140">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="95920-140">Get your users ready to use devices</span></span>](get-started-devices.md)
8. [<span data-ttu-id="95920-141">部署应用</span><span class="sxs-lookup"><span data-stu-id="95920-141">Deploy apps</span></span>](deploy-apps.md)
