---
title: 将应用部署到设备
description: 将应用添加到 Microsoft 托管桌面设备并将其部署到的信息。
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、应用程序、业务线应用程序、LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 2eb8b984550f301af9d99e738f6db4623aa2cc86
ms.sourcegitcommit: 6647055154002c7d3b8f7ce25ad53c9636bc8066
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769102"
---
# <a name="deploy-apps-to-devices"></a><span data-ttu-id="722d9-104">将应用部署到设备</span><span class="sxs-lookup"><span data-stu-id="722d9-104">Deploy apps to devices</span></span>
<span data-ttu-id="722d9-105">Microsoft 托管桌面的加入部分包括向用户设备添加应用程序并将其部署到用户设备。</span><span class="sxs-lookup"><span data-stu-id="722d9-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user's devices.</span></span> <span data-ttu-id="722d9-106">在使用 Microsoft 托管桌面门户后，可以添加和部署应用。</span><span class="sxs-lookup"><span data-stu-id="722d9-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="722d9-107">整个过程如下所示：</span><span class="sxs-lookup"><span data-stu-id="722d9-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="722d9-108">[向 Microsoft 托管桌面门户添加应用](#1) 程序-它可以是现有业务线 (LOB) 应用程序或 Microsoft Store for business 中已与 Intune 同步的应用程序。</span><span class="sxs-lookup"><span data-stu-id="722d9-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="722d9-109">[为应用分配创建 Azure Active Directory (AD) 组](#2) -你将使用这些组管理应用分配。</span><span class="sxs-lookup"><span data-stu-id="722d9-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="722d9-110">将应用程序分配给用户</span><span class="sxs-lookup"><span data-stu-id="722d9-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="722d9-111">步骤1：向 Microsoft 托管桌面门户添加应用程序</span><span class="sxs-lookup"><span data-stu-id="722d9-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="722d9-112">你可以将 [Win32 （或基于 WINDOWS MSI 的应用](#lob-apps)）或 [Microsoft Store for Business 应用](#msfb-apps) 添加到 microsoft 托管桌面，然后将其部署到 microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="722d9-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="722d9-113">Microsoft 托管桌面的基于 Win32 或 Windows MSI 的应用程序</span><span class="sxs-lookup"><span data-stu-id="722d9-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="722d9-114">你可以将业务线 (LOB) 应用添加到 Microsoft 托管桌面门户。</span><span class="sxs-lookup"><span data-stu-id="722d9-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="722d9-115">有关安装在 Microsoft 托管桌面设备上的应用程序的要求的信息，请参阅 [Microsoft 托管桌面应用程序要求](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)。</span><span class="sxs-lookup"><span data-stu-id="722d9-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="722d9-116">在此过程中，您将选择要添加的应用程序类型，然后配置和上载应用程序源。</span><span class="sxs-lookup"><span data-stu-id="722d9-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="722d9-117">**将 LOB 应用程序或 Windows 应用添加到 Microsoft 托管桌面门户**</span><span class="sxs-lookup"><span data-stu-id="722d9-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="722d9-118">你可以登录到 Microsoft 托管桌面门户，或登录到 Intune，然后搜索 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="722d9-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="722d9-119">我们将显示登录到 Microsoft 托管桌面门户。</span><span class="sxs-lookup"><span data-stu-id="722d9-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.    <span data-ttu-id="722d9-120">登录到 [Microsoft 托管桌面管理门户](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="722d9-120">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span> 
2.    <span data-ttu-id="722d9-121">在 " **清单** " 下，选择 " **应用** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-121">Under **Inventory** , select **Apps** .</span></span>
3.    <span data-ttu-id="722d9-122">在 "应用工作负荷" 中，选择 " **添加** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-122">In the Apps workload, select **Add** .</span></span>
4.    <span data-ttu-id="722d9-123">在 " **添加应用程序** " 中，选择 " **业务线应用程序** " 或 " **Windows 应用程序 (Win32)** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-123">In **Add app** , select **Line-of-business app** or **Windows app (Win32)** .</span></span>
    - <span data-ttu-id="722d9-124">如果选择了 " **业务线应用程序** "，请参阅 [向 Microsoft Intune 添加 Windows 业务线应用程序](https://docs.microsoft.com/intune/lob-apps-windows) ，以了解有关添加和配置业务线应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="722d9-124">If you selected **Line-of-business app** , see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="722d9-125">如果您选择了 " **windows 应用 (Win32)** "，请参阅 [Win32 应用程序管理](https://docs.microsoft.com/intune/apps-win32-app-management) ，以获取有关添加和配置 Windows 应用的说明。</span><span class="sxs-lookup"><span data-stu-id="722d9-125">If you selected **Windows app (Win32)** , see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="722d9-126">Microsoft Store for Business 应用</span><span class="sxs-lookup"><span data-stu-id="722d9-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="722d9-127">如果你尚未注册 Microsoft Store for Business，你可以在购买应用时进行注册。</span><span class="sxs-lookup"><span data-stu-id="722d9-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="722d9-128">拥有你的应用程序后，可以使用 Microsoft 托管桌面同步这些应用。</span><span class="sxs-lookup"><span data-stu-id="722d9-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="722d9-129">**从适用于企业的 Microsoft Store 购买应用程序**</span><span class="sxs-lookup"><span data-stu-id="722d9-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="722d9-130">使用 Microsoft Store for Business Administration account 登录 [Microsoft store For business](https://businessstore.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="722d9-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="722d9-131">选择 **"为我的组购买"** 。</span><span class="sxs-lookup"><span data-stu-id="722d9-131">Select **Shop for my group** .</span></span>
3. <span data-ttu-id="722d9-132">使用 "搜索" 查找所需的应用程序，并选择该应用程序。</span><span class="sxs-lookup"><span data-stu-id="722d9-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="722d9-133">在 "产品详细信息" 中，选择 **"获取应用程序** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-133">On the product details, select **Get the App** .</span></span> <span data-ttu-id="722d9-134">Microsoft Store 将应用添加到 **你** 的组织中的产品。</span><span class="sxs-lookup"><span data-stu-id="722d9-134">Microsoft Store adds the app to **Your products** for your organization.</span></span>

<span data-ttu-id="722d9-135">**在 Intune 和 Microsoft Store for Business 之间强制进行同步**</span><span class="sxs-lookup"><span data-stu-id="722d9-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="722d9-136">登录到 [Microsoft 终结点管理器管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)。</span><span class="sxs-lookup"><span data-stu-id="722d9-136">Sign in to the [Microsoft Endpoint Manager admin center](https://go.microsoft.com/fwlink/?linkid=2109431).</span></span>
2. <span data-ttu-id="722d9-137">选择 " **租户管理**  >  **连接器" 和 "标记**  >  **Microsoft Store for Business** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-137">Select **Tenant administration** > **Connectors and tokens** > **Microsoft Store for Business** .</span></span>
3. <span data-ttu-id="722d9-138">选择 " **同步** " 以获取从 Microsoft Store 购买的应用程序到 Intune。</span><span class="sxs-lookup"><span data-stu-id="722d9-138">Select **Sync** to get the apps you've purchased from the Microsoft Store into Intune.</span></span>

<span data-ttu-id="722d9-139">**验证 Intune 与 Microsoft Store for Business 之间的同步是否处于活动状态**</span><span class="sxs-lookup"><span data-stu-id="722d9-139">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="722d9-140">使用 Microsoft Store for Business Administration account 登录 [Microsoft store For business](https://businessstore.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="722d9-140">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="722d9-141">选择 " **管理** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-141">Select **Manage** .</span></span>
3. <span data-ttu-id="722d9-142">选择 " **设置** "，然后选择 " **分发** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-142">Select **Settings** and then select **Distribute** .</span></span>
4. <span data-ttu-id="722d9-143">在 " **管理工具** " 下，验证是否列出了 Intune 以及状态是否为 " **活动** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-143">Under **Management tools** , verify that Intune is listed and that the status is **Active** .</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="722d9-144">步骤2：创建 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="722d9-144">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="722d9-145">为每个应用程序创建三个 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="722d9-145">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="722d9-146">下表概述了 (可用、必需和卸载) 需要的组。</span><span class="sxs-lookup"><span data-stu-id="722d9-146">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="722d9-147">应用程序分配类型</span><span class="sxs-lookup"><span data-stu-id="722d9-147">App assignment type</span></span> |    <span data-ttu-id="722d9-148">组使用</span><span class="sxs-lookup"><span data-stu-id="722d9-148">Group use</span></span>    | <span data-ttu-id="722d9-149">示例 Azure AD 名称</span><span class="sxs-lookup"><span data-stu-id="722d9-149">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="722d9-150">可用</span><span class="sxs-lookup"><span data-stu-id="722d9-150">Available</span></span> |  <span data-ttu-id="722d9-151">该应用程序将从公司门户应用程序或网站提供。</span><span class="sxs-lookup"><span data-stu-id="722d9-151">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="722d9-152">MMD – *应用程序名称* –可用</span><span class="sxs-lookup"><span data-stu-id="722d9-152">MMD – *app name* – Available</span></span>
<span data-ttu-id="722d9-153">必需</span><span class="sxs-lookup"><span data-stu-id="722d9-153">Required</span></span> |  <span data-ttu-id="722d9-154">应用程序安装在所选组中的设备上。</span><span class="sxs-lookup"><span data-stu-id="722d9-154">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="722d9-155">MMD – *应用程序名称* –必需</span><span class="sxs-lookup"><span data-stu-id="722d9-155">MMD – *app name* – Required</span></span>
<span data-ttu-id="722d9-156">Uninstall</span><span class="sxs-lookup"><span data-stu-id="722d9-156">Uninstall</span></span> |  <span data-ttu-id="722d9-157">将从所选组中的设备中卸载应用程序。</span><span class="sxs-lookup"><span data-stu-id="722d9-157">The app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="722d9-158">MMD – *应用程序名称* –卸载</span><span class="sxs-lookup"><span data-stu-id="722d9-158">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="722d9-159">将您的用户添加到这些组，以使应用程序可用，安装应用程序，或从 Microsoft 托管桌面设备中删除该应用。</span><span class="sxs-lookup"><span data-stu-id="722d9-159">Add your users to these groups to either make the app available, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="722d9-160">步骤3：将应用程序分配给用户</span><span class="sxs-lookup"><span data-stu-id="722d9-160">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="722d9-161">**将应用程序分配给用户**</span><span class="sxs-lookup"><span data-stu-id="722d9-161">**To assign the app to your users**</span></span>

1. <span data-ttu-id="722d9-162">登录到 [Microsoft 托管桌面管理门户](https://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="722d9-162">Sign in to [Microsoft Managed Desktop Admin portal](https://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="722d9-163">在 "托管桌面" 窗格中，选择 " **应用程序** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-163">In Managed Desktop pane, select **Apps** .</span></span>
3. <span data-ttu-id="722d9-164">在 "应用程序工作负荷" 中，选择要向其分配用户的应用，然后选择 " **分配用户组** "。</span><span class="sxs-lookup"><span data-stu-id="722d9-164">In the Apps workload, select the app you want to assign users to and select **Assign users groups** .</span></span>
4. <span data-ttu-id="722d9-165">对于特定应用程序，选择 "可用"、"必需"、"卸载) " 和 "分配相应的组" 中的 "分配 (类型"。</span><span class="sxs-lookup"><span data-stu-id="722d9-165">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="722d9-166">在 "分配应用程序" 窗格中，选择 **"确定"** 。</span><span class="sxs-lookup"><span data-stu-id="722d9-166">In the Assign Apps pane, select **OK** .</span></span>


## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a><span data-ttu-id="722d9-167">Microsoft 托管桌面入门步骤</span><span class="sxs-lookup"><span data-stu-id="722d9-167">Steps to get started with Microsoft Managed Desktop</span></span>

1. [<span data-ttu-id="722d9-168">在管理门户中添加和验证管理员联系人</span><span class="sxs-lookup"><span data-stu-id="722d9-168">Add and verify admin contacts in the Admin portal</span></span>](add-admin-contacts.md)
2. [<span data-ttu-id="722d9-169">调整条件访问</span><span class="sxs-lookup"><span data-stu-id="722d9-169">Adjust conditional access</span></span>](conditional-access.md)
3. [<span data-ttu-id="722d9-170">分配许可证</span><span class="sxs-lookup"><span data-stu-id="722d9-170">Assign licenses</span></span>](assign-licenses.md)
4. [<span data-ttu-id="722d9-171">部署 Intune 公司门户</span><span class="sxs-lookup"><span data-stu-id="722d9-171">Deploy Intune Company Portal</span></span>](company-portal.md)
5. [<span data-ttu-id="722d9-172">启用企业状态漫游</span><span class="sxs-lookup"><span data-stu-id="722d9-172">Enable Enterprise State Roaming</span></span>](enterprise-state-roaming.md)
6. [<span data-ttu-id="722d9-173">设置设备</span><span class="sxs-lookup"><span data-stu-id="722d9-173">Set up devices</span></span>](set-up-devices.md)
7. [<span data-ttu-id="722d9-174">让用户做好使用设备的准备</span><span class="sxs-lookup"><span data-stu-id="722d9-174">Get your users ready to use devices</span></span>](get-started-devices.md)
8. <span data-ttu-id="722d9-175">部署本主题 (的应用程序) </span><span class="sxs-lookup"><span data-stu-id="722d9-175">Deploy apps (this topic)</span></span>


<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

-->
