---
title: 为 Microsoft 托管桌面准备应用程序
description: ''
keywords: microsoft 托管桌面, microsoft 365, 服务, 文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: be28760fc3facdb21643943ace11deda378d437c
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289059"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="5ef8c-103">为 Microsoft 托管桌面准备应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="5ef8c-104">microsoft 和 microsoft 托管桌面客户在 microsoft 托管桌面中使用的应用程序同等重要, 但也是不同的责任。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilities"></a><span data-ttu-id="5ef8c-105">Microsoft 职责</span><span class="sxs-lookup"><span data-stu-id="5ef8c-105">Microsoft responsibilities</span></span>
<span data-ttu-id="5ef8c-106">**Office 365 应用程序**Microsoft 将提供针对特定 Office 365 应用程序的部署、更新和支持的完整服务。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-106">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps.</span></span> <span data-ttu-id="5ef8c-107">所有用户都将收到 Office 365 的基本集。单击以运行, 64 位版本的应用程序包含在设备的图像中, 以便用户可以快速提高工作效率。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-107">All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive.</span></span> <span data-ttu-id="5ef8c-108">Office 365 套件中的项目和 Visio 应用程序是单独许可的。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-108">The Project and Visio applications in of the Office 365 suite are licensed separately.</span></span>  <span data-ttu-id="5ef8c-109">Microsoft 托管桌面将提供部署组, 让 IT 管理员能够管理许可证并为其组织适当地部署这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-109">Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization.</span></span> <span data-ttu-id="5ef8c-110">microsoft 将通过 microsoft 托管桌面支持频道支持这些应用程序的最终用户。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-110">Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="5ef8c-111">**业务线应用程序**Microsoft 为 IT 管理员提供了工具, 以便将业务线 (LOB) 应用程序作为 Intune 产品的一部分管理和部署到最终用户。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-111">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product.</span></span> <span data-ttu-id="5ef8c-112">Microsoft 将支持应用程序部署问题, 如[业务线应用程序](#line-of-business-applications)中所述</span><span class="sxs-lookup"><span data-stu-id="5ef8c-112">Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="5ef8c-113">**使用 Intune 部署**在 microsoft 托管桌面载入期间, Intune 将链接到**microsoft Store for Business** , 从而允许通过 Intune 部署已应用的应用。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-113">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune.</span></span> <span data-ttu-id="5ef8c-114">microsoft 还会将 microsoft Store 中的公司门户应用程序部署到最终用户, 以便 IT 管理员可以为他们的最终用户提供自助服务体验。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-114">Microsoft will also deploy the Company Portal application from the Microsoft Store to end users so that IT Administrators can provide a self-service experience for their end users.</span></span>

<span data-ttu-id="5ef8c-115">**应用程序管理**Microsoft 可能会发现由于其系统影响而不适合新式工作场所的受限制应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-115">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact.</span></span> <span data-ttu-id="5ef8c-116">如果标识了这样的应用程序, Microsoft 将会通知客户, 并且需要从租户中删除该应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-116">When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

<span data-ttu-id="5ef8c-117">有关受限制的应用程序行为和应用要求的详细信息, 请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5ef8c-117">For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="customer-responsibilities"></a><span data-ttu-id="5ef8c-118">客户责任</span><span class="sxs-lookup"><span data-stu-id="5ef8c-118">Customer responsibilities</span></span>
<span data-ttu-id="5ef8c-119">Office 365 套件是 microsoft 生产率产品的核心, 并包含在适用于所有 microsoft 托管桌面用户的 microsoft 365 许可证中。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-119">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users.</span></span> <span data-ttu-id="5ef8c-120">虽然 microsoft 将 Office 应用程序部署、更新并支持到 microsoft 托管桌面设备, 但仍有一些客户负责这些方面。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-120">While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="5ef8c-121">**分配许可证**-客户负责向最终用户分配适用于 Office 365 的许可证。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-121">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="5ef8c-122">**将用户添加到安全组**-对于具有需要 Project 或 Visio 的用户的客户, IT 管理员必须将这些用户添加到相应的部署组。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-122">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="5ef8c-123">IT 管理员还负责管理这些用户的生命周期的结束。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-123">IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="5ef8c-124">**部署 office 365 外接**程序-客户负责将任何插件部署到 Office 365 套件 (认为有必要)。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-124">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="5ef8c-125">由于业务线 (LOB) 应用程序对于每个客户都是唯一的, 因此客户负责管理其组织中的所有应用程序, 而不是由 Microsoft 部署的。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-125">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft.</span></span> <span data-ttu-id="5ef8c-126">具体包括：</span><span class="sxs-lookup"><span data-stu-id="5ef8c-126">This includes:</span></span>
- <span data-ttu-id="5ef8c-127">确定所需的应用程序以及需要它们的用户</span><span class="sxs-lookup"><span data-stu-id="5ef8c-127">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="5ef8c-128">将应用程序分配给这些用户</span><span class="sxs-lookup"><span data-stu-id="5ef8c-128">Assigning apps to those users</span></span>
- <span data-ttu-id="5ef8c-129">创建和维护用于管理应用程序分配的 Azure Active Directory (AD) 组</span><span class="sxs-lookup"><span data-stu-id="5ef8c-129">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="5ef8c-130">客户必须将 LOB 应用上传到 Intune。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-130">The customer must upload LOB apps to Intune.</span></span> <span data-ttu-id="5ef8c-131">然后, 他们负责在各自的生命周期中部署、更新和解除这些应用程序, 并为其用户管理这些应用程序的支持。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-131">They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.</span></span>

## <a name="office-applications"></a><span data-ttu-id="5ef8c-132">Office 应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-132">Office applications</span></span>
<span data-ttu-id="5ef8c-133">作为 microsoft 365 E5 许可证的一部分, Office 365 标准套件 (64 位) 由 microsoft 部署。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="5ef8c-134">有关详细信息, 请参阅[Microsoft 托管桌面技术](../intro/technologies.md)</span><span class="sxs-lookup"><span data-stu-id="5ef8c-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md)</span></span> <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.-->

## <a name="line-of-business-applications"></a><span data-ttu-id="5ef8c-135">业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-135">Line-of-business applications</span></span>
<span data-ttu-id="5ef8c-136">此表汇总了业务线 (LOB) 应用程序的各个阶段的责任。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="5ef8c-137">应用程序工作项</span><span class="sxs-lookup"><span data-stu-id="5ef8c-137">Application work items</span></span> |    <span data-ttu-id="5ef8c-138">客户</span><span class="sxs-lookup"><span data-stu-id="5ef8c-138">Customer</span></span>    | <span data-ttu-id="5ef8c-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="5ef8c-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="5ef8c-140">**载入应用**</span><span class="sxs-lookup"><span data-stu-id="5ef8c-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="5ef8c-141">确定目标用户组所需的应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-141">Identify applications needed for targeted user groups</span></span>   | ![是](images/checkmark.png)  |
<span data-ttu-id="5ef8c-143">创建和管理应用程序部署的 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="5ef8c-143">Create and manage Azure AD groups for app deployment</span></span> | ![是](images/checkmark.png) |   
<span data-ttu-id="5ef8c-145">**应用程序打包**</span><span class="sxs-lookup"><span data-stu-id="5ef8c-145">**App Packaging**</span></span> |  |
<span data-ttu-id="5ef8c-146">程序包应用程序以满足 Intune 部署标准</span><span class="sxs-lookup"><span data-stu-id="5ef8c-146">Package apps to meet Intune deployment standards</span></span> |  ![是](images/checkmark.png) |  
<span data-ttu-id="5ef8c-148">将应用程序上载到 Intune</span><span class="sxs-lookup"><span data-stu-id="5ef8c-148">Upload apps to Intune</span></span> | ![是](images/checkmark.png)     |
<span data-ttu-id="5ef8c-150">在 Microsoft 托管桌面环境中测试应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![是](images/checkmark.png) |  
<span data-ttu-id="5ef8c-152">使用最终用户测试应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-152">Test apps with end users</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="5ef8c-154">**部署**</span><span class="sxs-lookup"><span data-stu-id="5ef8c-154">**Deployment**</span></span> | |
<span data-ttu-id="5ef8c-155">管理用户并将其分配给应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-155">Manage and assign users to applications</span></span>  | ![是](images/checkmark.png)  |
<span data-ttu-id="5ef8c-157">Intune 部署工具将应用程序传递到远程客户端</span><span class="sxs-lookup"><span data-stu-id="5ef8c-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![是](images/checkmark.png)
<span data-ttu-id="5ef8c-159">通过 Intune 识别和部署应用程序更新</span><span class="sxs-lookup"><span data-stu-id="5ef8c-159">Identify and deploy application updates through Intune</span></span> | ![是](images/checkmark.png)    |
<span data-ttu-id="5ef8c-161">Unistall 和删除已停用的应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-161">Unistall and remove applications when they have been retired</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="5ef8c-163">**管理**</span><span class="sxs-lookup"><span data-stu-id="5ef8c-163">**Management**</span></span> | |
<span data-ttu-id="5ef8c-164">购买和分配许可证</span><span class="sxs-lookup"><span data-stu-id="5ef8c-164">Procure and assign licenses</span></span> |   ![是](images/checkmark.png)     |
<span data-ttu-id="5ef8c-166">为业务线应用程序提供最终用户支持</span><span class="sxs-lookup"><span data-stu-id="5ef8c-166">Provide end-user support for line-of-business apps</span></span>  | ![是](images/checkmark.png) |
<span data-ttu-id="5ef8c-168">远程管理应用程序设置</span><span class="sxs-lookup"><span data-stu-id="5ef8c-168">Manage app settings remotely</span></span>    | ![是](images/checkmark.png) |

<span data-ttu-id="5ef8c-170">有关 LOB 应用程序要求的信息, 请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="5ef8c-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>


## <a name="intune-application-deployment"></a><span data-ttu-id="5ef8c-171">Intune 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="5ef8c-171">Intune application deployment</span></span>
<span data-ttu-id="5ef8c-172">可以通过 Microsoft 托管桌面管理门户或 Intune 门户来处理应用程序管理。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-172">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal.</span></span> <span data-ttu-id="5ef8c-173">Intune 的应用程序管理门户显示为 Windows、Android 和 iOS 部署的应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-173">Intune’s app management portal shows applications deployed for Windows, Android, and iOS.</span></span> <span data-ttu-id="5ef8c-174">Microsoft 托管桌面管理门户将视图限制为 Windows 10 应用程序。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-174">Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications.</span></span> <span data-ttu-id="5ef8c-175">两者均可通过 Azure 门户获得。</span><span class="sxs-lookup"><span data-stu-id="5ef8c-175">Both are available through the Azure Portal.</span></span> 
* [<span data-ttu-id="5ef8c-176">Intune 应用管理基础</span><span class="sxs-lookup"><span data-stu-id="5ef8c-176">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
* [<span data-ttu-id="5ef8c-177">向 Intune 添加应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-177">Add apps to Intune</span></span>](https://docs.microsoft.com/intune/app-management)
   * [<span data-ttu-id="5ef8c-178">添加业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-178">Add a line-of-business App</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
   * [<span data-ttu-id="5ef8c-179">将 Win32 应用程序添加到 Intune</span><span class="sxs-lookup"><span data-stu-id="5ef8c-179">Add Win32 apps to Intune</span></span>](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [<span data-ttu-id="5ef8c-180">添加 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-180">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
* [<span data-ttu-id="5ef8c-181">部署应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-181">Deploy apps</span></span>](https://docs.microsoft.com/intune/apps-deploy)
   * [<span data-ttu-id="5ef8c-182">将应用程序部署到 Windows 10</span><span class="sxs-lookup"><span data-stu-id="5ef8c-182">Deploy apps to Windows 10</span></span>](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* <span data-ttu-id="5ef8c-183">公司门户</span><span class="sxs-lookup"><span data-stu-id="5ef8c-183">Company Portal</span></span>
   * [<span data-ttu-id="5ef8c-184">部署公司门户</span><span class="sxs-lookup"><span data-stu-id="5ef8c-184">Deploy the Company Portal</span></span>](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [<span data-ttu-id="5ef8c-185">配置公司门户应用程序</span><span class="sxs-lookup"><span data-stu-id="5ef8c-185">Configure the Company Portal app</span></span>](https://docs.microsoft.com/intune/company-portal-app)
