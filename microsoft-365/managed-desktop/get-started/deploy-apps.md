---
title: 部署 Microsoft 托管桌面设备的应用程序
description: 将应用添加到 Microsoft 托管桌面设备并将其部署到的信息。
keywords: microsoft 托管桌面、microsoft 365、服务、文档、应用程序、业务线应用程序、LOB 应用
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 01/17/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: febb3198c434e638f83c412a3f8a3b688d9f5bd1
ms.sourcegitcommit: 8d2e6bcc257a665f53ee914c7f0e1dfb9d31a9e0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/06/2019
ms.locfileid: "30414161"
---
# <a name="deploy-apps-to-microsoft-managed-desktop-devices"></a><span data-ttu-id="e7c89-104">将应用程序部署到 Microsoft 托管桌面设备</span><span class="sxs-lookup"><span data-stu-id="e7c89-104">Deploy apps to Microsoft Managed Desktop devices</span></span>
<span data-ttu-id="e7c89-105">Microsoft 托管桌面的加入部分包括向用户设备添加应用程序并将其部署到用户设备。</span><span class="sxs-lookup"><span data-stu-id="e7c89-105">Part of onboarding to Microsoft Managed Desktop includes adding and deploying apps to your user’s devices.</span></span> <span data-ttu-id="e7c89-106">在使用 Microsoft 托管桌面门户后, 可以添加和部署应用。</span><span class="sxs-lookup"><span data-stu-id="e7c89-106">Once you're using the Microsoft Managed Desktop portal, you can add and deploy your apps.</span></span> 

<span data-ttu-id="e7c89-107">整个过程如下所示:</span><span class="sxs-lookup"><span data-stu-id="e7c89-107">The overall process looks like this:</span></span>
1. <span data-ttu-id="e7c89-108">[向 microsoft 托管桌面门户添加应用](#1)程序-它可以是现有业务线 (LOB) 应用程序, 也可以是 microsoft Store for business 中已与 Intune 同步的应用。</span><span class="sxs-lookup"><span data-stu-id="e7c89-108">[Add apps to Microsoft Managed Desktop portal](#1) - This can be existing line-of-business (LOB) apps, or apps from Microsoft Store for Business that you've synced with Intune.</span></span> 
2. <span data-ttu-id="e7c89-109">[为应用分配创建 Azure Active Directory (AD) 组](#2)-你将使用这些组来管理应用分配。</span><span class="sxs-lookup"><span data-stu-id="e7c89-109">[Create Azure Active Directory (AD) groups for app assignment](#2) - You'll use these groups to manage app assignment.</span></span>
3. [<span data-ttu-id="e7c89-110">将应用程序分配给用户</span><span class="sxs-lookup"><span data-stu-id="e7c89-110">Assign apps to your users</span></span>](#3)

<span id="1" />

## <a name="step-1-add-apps-to-microsoft-managed-desktop-portal"></a><span data-ttu-id="e7c89-111">步骤 1: 向 Microsoft 托管桌面门户添加应用程序</span><span class="sxs-lookup"><span data-stu-id="e7c89-111">Step 1: Add apps to Microsoft Managed Desktop portal</span></span>
<span data-ttu-id="e7c89-112">你可以将[Win32 (或基于 Windows MSI 的应用](#lob-apps)) 或[microsoft Store for Business 应用](#msfb-apps)添加到 microsoft 托管桌面, 然后将其部署到 microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="e7c89-112">You can add [Win32, or Windows MSI-based apps](#lob-apps), or [Microsoft Store for Business apps](#msfb-apps) to Microsoft Managed Desktop, and then deploy them to Microsoft Managed Desktop devices.</span></span>

<span id="lob-apps">

###  <a name="win32-or-windows-msi-based-apps-to-microsoft-managed-desktop"></a><span data-ttu-id="e7c89-113">Microsoft 托管桌面的基于 Win32 或 Windows MSI 的应用程序</span><span class="sxs-lookup"><span data-stu-id="e7c89-113">Win32 or Windows MSI-based apps to Microsoft Managed Desktop</span></span>

<span data-ttu-id="e7c89-114">你可以将业务线 (LOB) 应用添加到 Microsoft 托管桌面门户。</span><span class="sxs-lookup"><span data-stu-id="e7c89-114">You can add your line-of-business (LOB) apps to Microsoft Managed Desktop portal.</span></span> <span data-ttu-id="e7c89-115">有关安装在 Microsoft 托管桌面设备上的应用程序的要求的信息, 请参阅[microsoft 托管桌面应用程序要求](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements)。</span><span class="sxs-lookup"><span data-stu-id="e7c89-115">For information on requirements for apps installed on Microsoft Managed Desktop devices, see [Microsoft Managed Desktop app requirements](https://docs.microsoft.com/microsoft-365/managed-desktop/service-description/mmd-app-requirements).</span></span>

<span data-ttu-id="e7c89-116">在此过程中, 您将选择要添加的应用程序类型, 然后配置和上载应用程序源。</span><span class="sxs-lookup"><span data-stu-id="e7c89-116">In this procedure, you'll select which kind of app you want to add, and then configure and upload the app source.</span></span> 

<span data-ttu-id="e7c89-117">**将 LOB 应用程序或 Windows 应用添加到 Microsoft 托管桌面门户**</span><span class="sxs-lookup"><span data-stu-id="e7c89-117">**To add your LOB app or Windows app to Microsoft Managed Desktop portal**</span></span>

<span data-ttu-id="e7c89-118">你可以登录到 microsoft 托管桌面门户, 或登录到 Intune, 然后搜索 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="e7c89-118">You can sign in to Microsoft Managed Desktop portal, or sign in to Intune and then search for Microsoft Managed Desktop.</span></span> <span data-ttu-id="e7c89-119">我们将显示登录到 Microsoft 托管桌面门户。</span><span class="sxs-lookup"><span data-stu-id="e7c89-119">We'll show signing in to Microsoft Managed Desktop portal.</span></span> 

1.  <span data-ttu-id="e7c89-120">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="e7c89-120">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span> 
2.  <span data-ttu-id="e7c89-121">在 "**清单**" 下, 选择 "**应用**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-121">Under **Inventory**, select **Apps**.</span></span>
3.  <span data-ttu-id="e7c89-122">在 "应用工作负荷" 中, 选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-122">In the Apps workload, select **Add**.</span></span>
4.  <span data-ttu-id="e7c89-123">在 "**添加应用程序**" 中, 选择 "**业务线应用程序**" 或 " **Windows 应用程序 (Win32) 预览**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-123">In **Add app**, select **Line-of-business app** or **Windows app (Win32) - preview**.</span></span>
    - <span data-ttu-id="e7c89-124">如果选择了 "**业务线应用程序**", 请参阅[向 Microsoft Intune 添加 Windows 业务线应用程序](https://docs.microsoft.com/intune/lob-apps-windows), 以了解有关添加和配置业务线应用程序的说明。</span><span class="sxs-lookup"><span data-stu-id="e7c89-124">If you selected **Line-of-business app**, see [Add a Windows line-of-business app to Microsoft Intune](https://docs.microsoft.com/intune/lob-apps-windows) for instruction on adding and configuring line-of-business apps.</span></span>
    - <span data-ttu-id="e7c89-125">如果选择了 " **windows 应用 (Win32) 预览**", 请参阅[Win32 应用管理](https://docs.microsoft.com/intune/apps-win32-app-management)以了解有关添加和配置 Windows 应用的说明。</span><span class="sxs-lookup"><span data-stu-id="e7c89-125">If you selected **Windows app (Win32) - preview**, see [Win32 app management](https://docs.microsoft.com/intune/apps-win32-app-management) for instruction on adding and configuring Windows apps.</span></span>

<span id="msfb-apps">

### <a name="microsoft-store-for-business-apps"></a><span data-ttu-id="e7c89-126">Microsoft Store for Business 应用</span><span class="sxs-lookup"><span data-stu-id="e7c89-126">Microsoft Store for Business apps</span></span>
<span data-ttu-id="e7c89-127">如果你尚未注册 Microsoft Store for Business, 你可以在购买应用时进行注册。</span><span class="sxs-lookup"><span data-stu-id="e7c89-127">If you haven't signed up with Microsoft Store for Business, you can sign up when you shop for apps.</span></span> <span data-ttu-id="e7c89-128">拥有你的应用程序后, 可以使用 Microsoft 托管桌面同步这些应用。</span><span class="sxs-lookup"><span data-stu-id="e7c89-128">After you have your apps, you can sync them with Microsoft Managed Desktop.</span></span> 

<span data-ttu-id="e7c89-129">**从适用于企业的 Microsoft Store 购买应用程序**</span><span class="sxs-lookup"><span data-stu-id="e7c89-129">**To buy apps from the Microsoft Store for Business**</span></span>

1. <span data-ttu-id="e7c89-130">使用 microsoft store for business administration account 登录[microsoft store for business](https://businessstore.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="e7c89-130">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="e7c89-131">选择 **"为我的组购买"**。</span><span class="sxs-lookup"><span data-stu-id="e7c89-131">Select **Shop for my group**.</span></span>
3. <span data-ttu-id="e7c89-132">使用 "搜索" 查找所需的应用程序, 并选择该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7c89-132">Use Search to find that the app that you want, and select the app.</span></span>
4. <span data-ttu-id="e7c89-133">在 "产品详细信息" 中, 选择 **"获取应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-133">On the product details, select **Get the App**.</span></span> <span data-ttu-id="e7c89-134">Microsoft Store 将应用程序添加到组织的**产品 & 服务**。</span><span class="sxs-lookup"><span data-stu-id="e7c89-134">Microsoft Store adds the app to **Products & services** for your organization.</span></span>

<span data-ttu-id="e7c89-135">**在 Intune 和 Microsoft Store for Business 之间强制进行同步**</span><span class="sxs-lookup"><span data-stu-id="e7c89-135">**To force a sync between Intune and Microsoft Store for Business**</span></span>
1. <span data-ttu-id="e7c89-136">以 Intune 管理员身份登录到[Azure 门户](https://portal.azure.com/)或为你的租户登录全局管理员</span><span class="sxs-lookup"><span data-stu-id="e7c89-136">Sign in to [Azure Portal](https://portal.azure.com/) as Intune Admin or Global Admin for your tenant</span></span>
2. <span data-ttu-id="e7c89-137">选择 "**所有服务" > Intune**。</span><span class="sxs-lookup"><span data-stu-id="e7c89-137">Select **All services > Intune**.</span></span> <span data-ttu-id="e7c89-138">Intune 位于 "监控 + 管理" 部分。</span><span class="sxs-lookup"><span data-stu-id="e7c89-138">Intune is in the Monitoring + Management section.</span></span>
3. <span data-ttu-id="e7c89-139">在 Intune 窗格中, 选择 "**客户端应用程序**", 然后选择 " **Microsoft Store for Business**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-139">In the Intune pane, select **Client Apps**, and then select **Microsoft Store for Business**.</span></span>
4. <span data-ttu-id="e7c89-140">选择 "**启用**" 以使用 Intune 同步 Microsoft Store for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e7c89-140">Select **Enable** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="e7c89-141">如果尚未安装, 请使用 Intune 注册并关联 Microsoft Store for Business 帐户</span><span class="sxs-lookup"><span data-stu-id="e7c89-141">If you haven't already, sign up and associate your Microsoft Store for Business account with Intune</span></span>
    - <span data-ttu-id="e7c89-142">选择在 Intune 控制台中显示 Microsoft Store for Business 中的应用程序将在其中显示的语言</span><span class="sxs-lookup"><span data-stu-id="e7c89-142">Select the language in which apps from the Microsoft Store for Business will be displayed in your Intune console</span></span>
    - <span data-ttu-id="e7c89-143">选择 "**同步**" 以使用 Intune 同步 Microsoft Store for Business 应用。</span><span class="sxs-lookup"><span data-stu-id="e7c89-143">Select **Sync** to sync your Microsoft Store for Business apps with Intune.</span></span>
    - <span data-ttu-id="e7c89-144">验证 Microsoft Store for Business 和 Intune 之间的同步是否处于活动状态 (下一步)。</span><span class="sxs-lookup"><span data-stu-id="e7c89-144">Verify that the sync between Microsoft Store for Business and Intune is active (next step).</span></span> 

<span data-ttu-id="e7c89-145">**验证 Intune 与 Microsoft Store for Business 之间的同步是否处于活动状态**</span><span class="sxs-lookup"><span data-stu-id="e7c89-145">**To verify that a sync between Intune and Microsoft Store for Business is active**</span></span>
1. <span data-ttu-id="e7c89-146">使用 microsoft store for business administration account 登录[microsoft store for business](https://businessstore.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="e7c89-146">Sign in to [Microsoft Store for Business](https://businessstore.microsoft.com) with your Microsoft Store for Business Admin account.</span></span>
2. <span data-ttu-id="e7c89-147">选择 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-147">Select **Manage**.</span></span>
3. <span data-ttu-id="e7c89-148">选择 "**设置**", 然后选择 "**分发**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-148">Select **Settings** and then select **Distribute**.</span></span>
4. <span data-ttu-id="e7c89-149">在 "**管理工具**" 下, 验证是否列出了 Intune 以及状态是否为 "**活动**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-149">Under **Management tools**, verify that Intune is listed and that the status is **Active**.</span></span>  

<span id="2" />

## <a name="step-2-create-azure-ad-groups"></a><span data-ttu-id="e7c89-150">步骤 2: 创建 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="e7c89-150">Step 2: Create Azure AD groups</span></span>

<span data-ttu-id="e7c89-151">为每个应用程序创建三个 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="e7c89-151">Create three Azure AD groups for each app.</span></span> <span data-ttu-id="e7c89-152">此表概述了您需要的组 (可用、必需和卸载)。</span><span class="sxs-lookup"><span data-stu-id="e7c89-152">This table outlines the groups you'll need (Available, Required, and Uninstall).</span></span> 

<span data-ttu-id="e7c89-153">应用程序分配类型</span><span class="sxs-lookup"><span data-stu-id="e7c89-153">App assignment type</span></span> |   <span data-ttu-id="e7c89-154">组使用</span><span class="sxs-lookup"><span data-stu-id="e7c89-154">Group use</span></span>   | <span data-ttu-id="e7c89-155">示例 Azure AD 名称</span><span class="sxs-lookup"><span data-stu-id="e7c89-155">Example Azure AD name</span></span>
--- | --- | ---
<span data-ttu-id="e7c89-156">可用</span><span class="sxs-lookup"><span data-stu-id="e7c89-156">Available</span></span> |  <span data-ttu-id="e7c89-157">该应用程序将从公司门户应用程序或网站提供。</span><span class="sxs-lookup"><span data-stu-id="e7c89-157">The app will be available from Company Portal app or website.</span></span> | <span data-ttu-id="e7c89-158">MMD –*应用程序名称*–可用</span><span class="sxs-lookup"><span data-stu-id="e7c89-158">MMD – *app name* – Available</span></span>
<span data-ttu-id="e7c89-159">必需</span><span class="sxs-lookup"><span data-stu-id="e7c89-159">Required</span></span> |  <span data-ttu-id="e7c89-160">应用程序安装在所选组中的设备上。</span><span class="sxs-lookup"><span data-stu-id="e7c89-160">The app is installed on devices in the selected groups.</span></span> | <span data-ttu-id="e7c89-161">MMD –*应用程序名称*–必需</span><span class="sxs-lookup"><span data-stu-id="e7c89-161">MMD – *app name* – Required</span></span>
<span data-ttu-id="e7c89-162">Uninstall</span><span class="sxs-lookup"><span data-stu-id="e7c89-162">Uninstall</span></span> |  <span data-ttu-id="e7c89-163">将从所选组中的设备中卸载应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7c89-163">TThe app is uninstalled from devices in the selected groups.</span></span> | <span data-ttu-id="e7c89-164">MMD –*应用程序名称*–卸载</span><span class="sxs-lookup"><span data-stu-id="e7c89-164">MMD – *app name* – Uninstall</span></span>

<span data-ttu-id="e7c89-165">将您的用户添加到这些组, 以使应用程序 availabe、安装应用程序或从其 Microsoft 托管桌面设备中删除该应用程序。</span><span class="sxs-lookup"><span data-stu-id="e7c89-165">Add your users to these groups to either make the app availabe, install the app, or remove the app from their Microsoft Managed Desktop device.</span></span> 

<span id="3" />

## <a name="step-3-assign-apps-to-your-users"></a><span data-ttu-id="e7c89-166">步骤 3: 将应用程序分配给用户</span><span class="sxs-lookup"><span data-stu-id="e7c89-166">Step 3: Assign apps to your users</span></span>

<span data-ttu-id="e7c89-167">**将应用程序分配给用户**</span><span class="sxs-lookup"><span data-stu-id="e7c89-167">**To assign the app to your users**</span></span>

1. <span data-ttu-id="e7c89-168">登录到[Microsoft 托管桌面管理门户](http://aka.ms/mmdportal)。</span><span class="sxs-lookup"><span data-stu-id="e7c89-168">Sign in to [Microsoft Managed Desktop Admin portal](http://aka.ms/mmdportal).</span></span>
2. <span data-ttu-id="e7c89-169">在 "托管桌面" 窗格中, 选择 "**应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-169">In Managed Desktop pane, select **Apps**.</span></span>
3. <span data-ttu-id="e7c89-170">在 "应用程序工作负荷" 中, 选择要向其分配用户的应用, 然后选择 "**分配用户组**"。</span><span class="sxs-lookup"><span data-stu-id="e7c89-170">In the Apps workload, select the app you want to assign users to and select **Assign users groups**.</span></span>
4. <span data-ttu-id="e7c89-171">对于特定应用程序, 选择 "分配类型" (可用、必需、卸载) 并分配适当的组。</span><span class="sxs-lookup"><span data-stu-id="e7c89-171">For the specific app, select an assignment type (Available, Required, Uninstall) and assign the appropriate group.</span></span>
5. <span data-ttu-id="e7c89-172">在 "分配应用程序" 窗格中, 选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e7c89-172">In the Assign Apps pane, select **OK**.</span></span>

<!--# Preparing apps for Microsoft Managed Desktop

This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.

Applications: supported/onboard/deployment
 
Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.

## Microsoft responsibilities
**Office 365 apps**
Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.

**Line-of-business apps**
Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications) 

**Deploy with Intune**
Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.

**App management**
Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant. 

For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)

## Customer responsibilities
The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.
- **Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365. 
- **Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users. 
- **Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary. 

Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:
- Deciding which apps are needed and who needs them
- Assigning apps to those users
- Create and maintain Azure Active Directory (AD) groups for managing app assignments 

The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.

## Office applications
As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft. 

For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.

## Line-of-business applications
This table summarizes responsibilities across the different phases for line-of-business (LOB) applications. 

Application work items |    Customer    | Microsoft
--- | --- | ---
**Onboarding apps** |  |
Identify applications needed for targeted user groups   | ![yes](images/checkmark.png)  |
Create and manage Azure AD groups for app deployment | ![yes](images/checkmark.png) |   
**App Packaging** |  |
Package apps to meet Intune deployment standards |  ![yes](images/checkmark.png) |  
Upload apps to Intune | ![yes](images/checkmark.png)     |
Test apps in Microsoft Managed Desktop environment |    ![yes](images/checkmark.png) |  
Test apps with end users    | ![yes](images/checkmark.png) |    
**Deployment** | |
Manage and assign users to applications  | ![yes](images/checkmark.png)  |
Intune deployment tools delivers application to remote clients| |   ![yes](images/checkmark.png)
Identify and deploy application updates through Intune | ![yes](images/checkmark.png)    |
Unistall and remove applications when they have been retired    | ![yes](images/checkmark.png) |    
**Management** | |
Procure and assign licenses |   ![yes](images/checkmark.png)     |
Provide end-user support for line-of-business apps  | ![yes](images/checkmark.png) |
Manage app settings remotely    | ![yes](images/checkmark.png) |

For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)


## Intune application deployment
Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal. 
* [Intune app management basics](https://docs.microsoft.com/intune/app-management)
* [Add apps to Intune](https://docs.microsoft.com/intune/app-management)
   * [Add a line-of-business App](https://docs.microsoft.com/intune/lob-apps-windows)
   * [Add Win32 apps to Intune](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [Add web applications](https://docs.microsoft.com/intune/web-app)
* [Deploy apps](https://docs.microsoft.com/intune/apps-deploy)
   * [Deploy apps to Windows 10](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* Company Portal
   * [Deploy the Company Portal](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [Configure the Company Portal app](https://docs.microsoft.com/intune/company-portal-app)-->