---
title: 将应用部署到设备
description: 有关向设备中添加和部署应用Microsoft 托管桌面的信息。
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、应用、业务线应用、LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 8bfc53d46bdcb91c16e9f4a1ddbc8ab3f6dfb47e
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922022"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="2b9b6-104">将应用部署到设备</span><span class="sxs-lookup"><span data-stu-id="2b9b6-104">Deploy apps to devices</span></span>
<span data-ttu-id="2b9b6-105">加入应用Microsoft 托管桌面包括向用户设备添加和部署应用。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="2b9b6-106">使用应用门户Microsoft 托管桌面，可以添加和部署应用。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="2b9b6-107">整个过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="2b9b6-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="2b9b6-108">向[Microsoft 托管桌面](#1)门户添加应用 - 这可以是现有业务线 (LOB) 应用或 适用于企业的 Microsoft Store 中已与 Intune 同步的应用。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="2b9b6-109">[为Azure Active Directory (创建) AD 组](#2)- 你将使用这些组管理应用分配。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="2b9b6-110">将应用分配给用户</span><span class="sxs-lookup"><span data-stu-id="2b9b6-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="2b9b6-111">步骤 1：将应用添加到Microsoft 托管桌面门户</span><span class="sxs-lookup"><span data-stu-id="2b9b6-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="2b9b6-112">你可以添加[Win32，Windows基于 MSI 的应用](#lob-apps)，或适用于企业的 Microsoft Store[应用Microsoft 托管桌面，](#msfb-apps)然后将它们部署到Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="2b9b6-113">将基于 win32 Windows基于 MSI 的应用Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="2b9b6-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="2b9b6-114">你可以向企业门户添加业务线 (LOB) 应用Microsoft 托管桌面应用。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="2b9b6-115">有关在设备上安装的应用Microsoft 托管桌面的信息，请参阅Microsoft 托管桌面[要求](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>

<span data-ttu-id="2b9b6-116">在此过程中，选择要添加的应用程序类型，然后配置和上载应用程序源。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="2b9b6-117">**将 LOB 应用或Windows添加到Microsoft 托管桌面门户**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="2b9b6-118">你可以登录到 Microsoft 托管桌面 门户，或登录到 Intune，然后搜索Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="2b9b6-119">我们将展示如何登录Microsoft 托管桌面门户。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="2b9b6-120">登录到管理[Microsoft 托管桌面 。](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="2b9b6-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="2b9b6-121">在 **"清单"** 下，选择 **"应用"。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-121">Under **Inventory**, select **Apps**.</span></span>
3.    <span data-ttu-id="2b9b6-122">在应用工作负载中 **，选择添加**。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-122">In the Apps workload, select **Add**.</span></span>
4.    <span data-ttu-id="2b9b6-123">在 **"添加应用**"**中，** 选择"业务线应用"**或Windows Win32 (应用) 。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32)**.</span></span>
    - <span data-ttu-id="2b9b6-124">如果 **选择了业务线** 应用，请参阅向 Windows [](/intune/lob-apps-windows)添加业务线应用Microsoft Intune，了解添加和配置业务线应用说明。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="2b9b6-125">如果你已选择 **Windows Win32** (应用) ，请参阅 [Win32](/intune/apps-win32-app-management)应用管理，了解有关添加和配置Windows说明。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-125">If you selected **Windows app (Win32)**, see [Win32 app management](/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="2b9b6-126">适用于企业的 Microsoft Store应用</span><span class="sxs-lookup"><span data-stu-id="2b9b6-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="2b9b6-127">如果你尚未注册应用适用于企业的 Microsoft Store，可以在购买应用时注册。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="2b9b6-128">拥有应用后，你可以将其与Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="2b9b6-129">**从应用商店购买适用于企业的 Microsoft Store**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="2b9b6-130">Sign in to[适用于企业的 Microsoft Store](https://businessstore.microsoft.com) with your 适用于企业的 Microsoft Store Admin account.</span><span class="sxs-lookup"><span data-stu-id="2b9b6-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="2b9b6-131">选择 **"购买我的组"。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="2b9b6-132">使用"搜索"查找你需要的应用，然后选择该应用。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="2b9b6-133">在产品详细信息上，选择"**获取应用"。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="2b9b6-134">Microsoft Store将应用添加到 **你的组织** 的产品。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="2b9b6-135">**强制在 Intune 和 适用于企业的 Microsoft Store**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="2b9b6-136">登录到管理[Microsoft Endpoint Manager中心](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="2b9b6-137">选择 **"**  >  **租户管理连接器和令牌**  >  适用于企业的 Microsoft Store"。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business**.</span></span>
3. <span data-ttu-id="2b9b6-138">选择 **"** 同步"，获取从 Intune Microsoft Store购买的应用。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="2b9b6-139">**验证 Intune 和 适用于企业的 Microsoft Store同步是否处于活动状态**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="2b9b6-140">Sign in to[适用于企业的 Microsoft Store](https://businessstore.microsoft.com) with your 适用于企业的 Microsoft Store Admin account.</span><span class="sxs-lookup"><span data-stu-id="2b9b6-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="2b9b6-141">选择"**管理"。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-141">Select **Manage**.</span></span>
3. <span data-ttu-id="2b9b6-142">选择 **设置"，** 然后选择"分发 **"。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-142">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="2b9b6-143">在 **"管理工具"** 下，验证 Intune 是否列出且状态为 **"活动"。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-143">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="2b9b6-144">步骤 2：创建 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="2b9b6-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="2b9b6-145">为每个应用创建三个 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="2b9b6-146">此表概述了你需要的组 (可用、必需和卸载) 。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="2b9b6-147">应用分配类型</span><span class="sxs-lookup"><span data-stu-id="2b9b6-147">App assignment type</span></span> |    <span data-ttu-id="2b9b6-148">组使用</span><span class="sxs-lookup"><span data-stu-id="2b9b6-148">Group use</span></span>    | <span data-ttu-id="2b9b6-149">示例 Azure AD 名称</span><span class="sxs-lookup"><span data-stu-id="2b9b6-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="2b9b6-150">可用</span><span class="sxs-lookup"><span data-stu-id="2b9b6-150">Available</span></span> |  <span data-ttu-id="2b9b6-151">该应用将在应用或公司门户提供。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="2b9b6-152">MMD – *应用名称* – 可用</span><span class="sxs-lookup"><span data-stu-id="2b9b6-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="2b9b6-153">必需</span><span class="sxs-lookup"><span data-stu-id="2b9b6-153">Required</span></span> |  <span data-ttu-id="2b9b6-154">应用安装在所选组的设备上。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="2b9b6-155">MMD – *应用名称* – 必需</span><span class="sxs-lookup"><span data-stu-id="2b9b6-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="2b9b6-156">卸载</span><span class="sxs-lookup"><span data-stu-id="2b9b6-156">Uninstall</span></span> |  <span data-ttu-id="2b9b6-157">从所选组的设备卸载应用。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="2b9b6-158">MMD – *应用名称* – 卸载</span><span class="sxs-lookup"><span data-stu-id="2b9b6-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="2b9b6-159">将用户添加到这些组，以便提供应用、安装应用，或者从他们的 Microsoft 托管桌面 设备中删除该应用。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="2b9b6-160">步骤 3：将应用分配给用户</span><span class="sxs-lookup"><span data-stu-id="2b9b6-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="2b9b6-161">**将应用分配给用户**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="2b9b6-162">登录到管理[Microsoft 托管桌面 。](https://aka.ms/mmdportal)</span><span class="sxs-lookup"><span data-stu-id="2b9b6-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="2b9b6-163">在"托管桌面"窗格中，选择"**应用"。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-163">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="2b9b6-164">在"应用工作负载"中，选择要为其分配用户的应用，然后选择"**分配用户组"。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="2b9b6-165">对于特定应用，选择分配类型 (可用、必需、卸载) 分配相应的组。</span><span class="sxs-lookup"><span data-stu-id="2b9b6-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="2b9b6-166">在"分配应用"窗格中，选择"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="2b9b6-166">In the Assign Apps pane, select **OK**.</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="2b9b6-167">开始使用 Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="2b9b6-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="2b9b6-168">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="2b9b6-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="2b9b6-169">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="2b9b6-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="2b9b6-170">分配许可证</span><span class="sxs-lookup"><span data-stu-id="2b9b6-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="2b9b6-171">部署 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="2b9b6-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="2b9b6-172">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="2b9b6-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="2b9b6-173">设置设备</span><span class="sxs-lookup"><span data-stu-id="2b9b6-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="2b9b6-174">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="2b9b6-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="2b9b6-175">在本主题 (部署) </span><span class="sxs-lookup"><span data-stu-id="2b9b6-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->