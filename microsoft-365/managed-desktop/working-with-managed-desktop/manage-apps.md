---
title: 在 Microsoft 托管桌面中管理应用
description: 有关如何更新部署到 Microsoft 托管桌面设备的业务线应用程序的信息
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.date: 01/18/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a6b91ab5b4523f4b980dab0c25af41a9d614189
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41600679"
---
# <a name="manage-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="415b3-104">在 Microsoft 托管桌面中管理业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="415b3-104">Manage line-of-business apps in Microsoft Managed Desktop</span></span>

<!--Application management -->

<span data-ttu-id="415b3-105">有几种方法可以管理已载入到 Microsoft 托管桌面的应用程序的应用程序更新，并将其部署到 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="415b3-105">There are a couple of ways to manage app updates for apps that you've onboarded to Microsoft Managed Desktop and deployed to your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="415b3-106">你可以在 Microsoft 托管桌面门户或 Intune 中进行应用更新。</span><span class="sxs-lookup"><span data-stu-id="415b3-106">You can make app updates in Microsoft Managed Desktop portal, or Intune.</span></span> 

<span id="update-app-mmd" />

## <a name="update-line-of-business-apps-in-microsoft-managed-desktop"></a><span data-ttu-id="415b3-107">在 Microsoft 托管桌面中更新业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="415b3-107">Update line-of-business apps in Microsoft Managed Desktop</span></span>

<span data-ttu-id="415b3-108">**在 Microsoft 托管桌面门户中更新业务线应用程序**</span><span class="sxs-lookup"><span data-stu-id="415b3-108">**To update your line-of-business apps in Microsoft Managed Desktop portal**</span></span>
1. <span data-ttu-id="415b3-109">登录到[Microsoft 托管桌面管理门户](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="415b3-109">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="415b3-110">在 "**清单**" 下，选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-110">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="415b3-111">选择要更新的应用程序，然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-111">Select the app you want to updates, and then select **Edit**.</span></span>
4. <span data-ttu-id="415b3-112">在 "**管理**" 下，选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-112">Under **Manage**, select **Properties**.</span></span> 
5. <span data-ttu-id="415b3-113">单击 "**应用程序包文件**"，然后浏览以上载新的应用程序包文件。</span><span class="sxs-lookup"><span data-stu-id="415b3-113">Click **App package file**, and then browse to upload a new app package file.</span></span>
6. <span data-ttu-id="415b3-114">选择 "**应用程序包文件**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-114">Select **App package file**.</span></span>
7. <span data-ttu-id="415b3-115">选择文件夹图标并浏览到更新后的应用程序文件所在的位置。</span><span class="sxs-lookup"><span data-stu-id="415b3-115">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="415b3-116">选择“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="415b3-116">Select **Open**.</span></span> <span data-ttu-id="415b3-117">应用程序信息使用包信息进行更新。</span><span class="sxs-lookup"><span data-stu-id="415b3-117">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="415b3-118">验证**应用程序版本**是否反映了更新后的应用程序包。</span><span class="sxs-lookup"><span data-stu-id="415b3-118">Verify that **App version** reflects the updated app package.</span></span> 

<span data-ttu-id="415b3-119">更新后的应用程序将部署到您的用户的设备上。</span><span class="sxs-lookup"><span data-stu-id="415b3-119">The updated app will be deployed to your user's devices.</span></span>

<span id="update-app-intune" />

## <a name="update-line-of-business-apps-in-intune"></a><span data-ttu-id="415b3-120">更新 Intune 中的业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="415b3-120">Update line-of-business apps in Intune</span></span>

<span data-ttu-id="415b3-121">**在 Intune 中更新业务线应用程序**</span><span class="sxs-lookup"><span data-stu-id="415b3-121">**To update your line-of-business apps in Intune**</span></span>
1. <span data-ttu-id="415b3-122">登录到[Azure 门户](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="415b3-122">Sign in to [Azure portal](https://portal.azure.com).</span></span>
2. <span data-ttu-id="415b3-123">选择 "**所有服务** > "**Intune**。</span><span class="sxs-lookup"><span data-stu-id="415b3-123">Select **All Services** > **Intune**.</span></span> <span data-ttu-id="415b3-124">Intune 位于 "**监控 + 管理**" 部分。</span><span class="sxs-lookup"><span data-stu-id="415b3-124">Intune is in the **Monitoring + Management** section.</span></span>
3. <span data-ttu-id="415b3-125">选择 "**客户端应用 > 应用**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-125">Select **Client Apps > Apps**.</span></span>
4. <span data-ttu-id="415b3-126">在应用列表中查找并选择您的应用程序。</span><span class="sxs-lookup"><span data-stu-id="415b3-126">Find and select your app in the list of apps.</span></span>
5. <span data-ttu-id="415b3-127">在**概述**边栏中，选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-127">In the **Overview** blade, select **Properties**.</span></span>
6. <span data-ttu-id="415b3-128">选择 "**应用程序包文件**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-128">Select **App package file**.</span></span>
7. <span data-ttu-id="415b3-129">选择文件夹图标并浏览到更新后的应用程序文件所在的位置。</span><span class="sxs-lookup"><span data-stu-id="415b3-129">Select the folder icon and browse to the location of your updated app file.</span></span> <span data-ttu-id="415b3-130">选择“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="415b3-130">Select **Open**.</span></span> <span data-ttu-id="415b3-131">应用程序信息使用包信息进行更新。</span><span class="sxs-lookup"><span data-stu-id="415b3-131">The app information is updated with the package information.</span></span>
8. <span data-ttu-id="415b3-132">验证**应用程序版本**是否反映了更新后的应用程序包。</span><span class="sxs-lookup"><span data-stu-id="415b3-132">Verify that **App version** reflects the updated app package.</span></span>

<span id="roll-back-app-mmd" />

## <a name="roll-back-an-app-to-a-previous-version"></a><span data-ttu-id="415b3-133">将应用程序回退到以前的版本</span><span class="sxs-lookup"><span data-stu-id="415b3-133">Roll back an app to a previous version</span></span>

<span data-ttu-id="415b3-134">如果在部署新版本的应用程序时发现错误，则可以回滚到以前的版本。</span><span class="sxs-lookup"><span data-stu-id="415b3-134">If there's an error found when a new version of an app is deployed, you can roll back to a previous version.</span></span> <span data-ttu-id="415b3-135">此处所述的过程适用于类型列为**WINDOWS MSI 应用程序**或 windows 应用程序的应用程序 **（Win 32）-preview**</span><span class="sxs-lookup"><span data-stu-id="415b3-135">The process outlined here is for apps where type is listed as **Windows MSI line-of-business app** or **Windows app (Win 32) - preview**</span></span>

<span data-ttu-id="415b3-136">**将业务线应用程序回滚到以前的版本**</span><span class="sxs-lookup"><span data-stu-id="415b3-136">**To roll back a line-of-business app to a previous version**</span></span>

1. <span data-ttu-id="415b3-137">登录到[Microsoft 托管桌面管理门户](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="415b3-137">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="415b3-138">在 "**清单**" 下，选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-138">Under **Inventory**, select **Apps**.</span></span>  
3. <span data-ttu-id="415b3-139">选择需要回滚的应用程序，然后选择 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-139">Select the app you need to roll back, and then select **Edit**.</span></span>
4. <span data-ttu-id="415b3-140">在 "**管理**" 下，选择 "**属性**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-140">Under **Manage**, select **Properties**.</span></span> 
    - <span data-ttu-id="415b3-141">对于**WINDOWS MSI 应用**程序应用程序，请选择 "**应用程序信息**"，然后在 "**忽略应用程序版本**" 下，选择 **"是"**。</span><span class="sxs-lookup"><span data-stu-id="415b3-141">For **Windows MSI line-of-business app** apps, select **App information**, and then under **Ignore app version**, select **Yes**.</span></span>
    - <span data-ttu-id="415b3-142">对于**Windows 应用（Win 32）-预览**应用程序，选择 "**应用程序信息**"，选择 "**检测规则**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-142">For **Windows app (Win 32) - preview** apps, select **App information**, select **Detection rules**, and then select **Add**.</span></span> 
    <span data-ttu-id="415b3-143">如果存在 MSI 规则，请验证**msi 产品版本检查**是否设置为 "**否**"。</span><span class="sxs-lookup"><span data-stu-id="415b3-143">If there is an MSI rule, verify that **MSI product version check** is set to **No**.</span></span>
5. <span data-ttu-id="415b3-144">将[以前版本的应用程序源文件上传](../get-started/deploy-apps.md)到 Microsoft 托管桌面管理门户。</span><span class="sxs-lookup"><span data-stu-id="415b3-144">[Upload a previous version of the app source file](../get-started/deploy-apps.md) to Microsoft Managed Desktop Admin portal.</span></span>  

