---
title: 应用程序准备 Microsoft 托管桌面
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: b46e3de4a4cfe2140574ab9fc589e3a738bd2e17
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865602"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="ac590-103">应用程序准备 Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="ac590-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="ac590-104">Microsoft 和 Microsoft 托管桌面客户同样可以围绕用于 Microsoft 托管桌面应用程序的关键、 尚未不同责任。</span><span class="sxs-lookup"><span data-stu-id="ac590-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilities"></a><span data-ttu-id="ac590-105">Microsoft 职责</span><span class="sxs-lookup"><span data-stu-id="ac590-105">Microsoft responsibilities</span></span>
<span data-ttu-id="ac590-p101">**Office 365 应用程序**Microsoft 将提供完整的部署、 更新和支持的特定的 Office 365 应用程序服务。所有用户将都收到运行，以便用户可以迅速提高效率，包括在设备的图像的应用程序的 64 位版本的 Office 365 单击了基本集。项目和 Visio 中的应用程序的 Office 365 套件是单独授权。 Microsoft 托管桌面将提供部署组允许 IT 管理员管理许可证和部署这些适当地为其组织的应用程序。通过 Microsoft 托管桌面支持渠道这些应用程序的最终用户时，Microsoft 将提供支持。</span><span class="sxs-lookup"><span data-stu-id="ac590-p101">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="ac590-p102">**业务线应用程序**Microsoft 提供的面向 IT 管理员管理和作为 Intune 产品的一部分部署到最终用户其业务线 (LOB) 应用程序的工具。Microsoft 将支持[业务线应用程序](#line-of-business-applications)中所述的应用程序部署问题</span><span class="sxs-lookup"><span data-stu-id="ac590-p102">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their line-of-business (LOB) applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="ac590-p103">**使用 Intune 部署**Intune 将链接到**Microsoft Store for Business**中，在 Microsoft 托管桌面入职培训允许已采购的应用程序通过 Intune 部署过程中。Microsoft 还会给最终用户部署的公司门户的基于 web 的版本，以便 IT 管理员可以为最终用户提供自助式体验。</span><span class="sxs-lookup"><span data-stu-id="ac590-p103">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.</span></span>

<span data-ttu-id="ac590-p104">**应用程序管理**Microsoft 可能确定受限制的应用程序，由于其系统影响不适合现代工作区。标识此类应用程序时 Microsoft 将通知客户，该应用程序将需要从租户中删除。</span><span class="sxs-lookup"><span data-stu-id="ac590-p104">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

<span data-ttu-id="ac590-117">有关受限制的应用程序行为和应用程序要求的详细信息，请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="ac590-117">For more information on restricted app behaviors and app requirements, see [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="customer-responsibilities"></a><span data-ttu-id="ac590-118">客户责任</span><span class="sxs-lookup"><span data-stu-id="ac590-118">Customer responsibilities</span></span>
<span data-ttu-id="ac590-p105">Office 365 套件是 Microsoft 的工作效率产品的核心和包含的所有 Microsoft 托管桌面用户 Microsoft 365 许可证中。Microsoft 部署、 更新和支持 Microsoft 托管桌面设备的 Office 应用程序时仍有某些客户负责的区域。</span><span class="sxs-lookup"><span data-stu-id="ac590-p105">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="ac590-121">**分配许可证**的客户负责将相应的许可证分配给 Office 365 的最终用户。</span><span class="sxs-lookup"><span data-stu-id="ac590-121">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="ac590-p106">**向安全组添加用户**-与用户客户需要项目或 Visio 的 IT 管理员必须这些将用户添加到适当的部署组。IT 管理员也是负责管理这些用户的生命周期结束。</span><span class="sxs-lookup"><span data-stu-id="ac590-p106">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="ac590-124">**部署 Office 365 加载项**的客户负责部署到 Office 365 套件，这必要的任何插件。</span><span class="sxs-lookup"><span data-stu-id="ac590-124">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="ac590-p107">由于是唯一的每个客户的业务线 (LOB) 应用程序，客户负责管理未部署由 Microsoft 其组织内的所有应用程序。这包括：</span><span class="sxs-lookup"><span data-stu-id="ac590-p107">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:</span></span>
- <span data-ttu-id="ac590-127">确定所需的应用程序和用户需要它们</span><span class="sxs-lookup"><span data-stu-id="ac590-127">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="ac590-128">将应用程序分配给这些用户</span><span class="sxs-lookup"><span data-stu-id="ac590-128">Assigning apps to those users</span></span>
- <span data-ttu-id="ac590-129">创建和维护用于管理应用程序分配的 Azure Active Directory (AD) 组</span><span class="sxs-lookup"><span data-stu-id="ac590-129">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="ac590-p108">客户必须将 LOB 应用程序上载到 Intune。这样，负责部署、 更新和通过其各自的生命周期、 停用这些应用程序以及管理这些应用程序的用户的支持。</span><span class="sxs-lookup"><span data-stu-id="ac590-p108">The customer must upload LOB apps to Intune. They are then responsible for deploying, updating, and decommissioning those applications over their respective lifecycles, as well as managing support for these apps for their users.</span></span>

## <a name="office-applications"></a><span data-ttu-id="ac590-132">Office 应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-132">Office applications</span></span>
<span data-ttu-id="ac590-133">作为 Microsoft 365 E5 许可证的一部分，Microsoft 部署 Office 365 Standard Suite （64 位）。</span><span class="sxs-lookup"><span data-stu-id="ac590-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="ac590-134">有关详细信息，请参阅[Microsoft 托管桌面技术](../intro/technologies.md)<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span><span class="sxs-lookup"><span data-stu-id="ac590-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span></span>

## <a name="line-of-business-applications"></a><span data-ttu-id="ac590-135">业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-135">Line-of-business applications</span></span>
<span data-ttu-id="ac590-136">此表总结了跨-的业务线 (LOB) 应用程序的不同阶段的责任。</span><span class="sxs-lookup"><span data-stu-id="ac590-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="ac590-137">应用程序工作项</span><span class="sxs-lookup"><span data-stu-id="ac590-137">Application work items</span></span> |    <span data-ttu-id="ac590-138">客户</span><span class="sxs-lookup"><span data-stu-id="ac590-138">Customer</span></span>    | <span data-ttu-id="ac590-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="ac590-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="ac590-140">**加入应用程序**</span><span class="sxs-lookup"><span data-stu-id="ac590-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="ac590-141">确定应用程序所需的目标的用户组</span><span class="sxs-lookup"><span data-stu-id="ac590-141">Identify applications needed for targeted user groups</span></span>   | ![是](images/checkmark.png)  |
<span data-ttu-id="ac590-143">创建和管理应用程序部署 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="ac590-143">Create and manage Azure AD groups for app deployment</span></span> | ![是](images/checkmark.png) |   
<span data-ttu-id="ac590-145">**应用程序打包**</span><span class="sxs-lookup"><span data-stu-id="ac590-145">**App Packaging**</span></span> |  |
<span data-ttu-id="ac590-146">包应用程序，以满足 Intune 部署标准</span><span class="sxs-lookup"><span data-stu-id="ac590-146">Package apps to meet Intune deployment standards</span></span> |  ![是](images/checkmark.png) |  
<span data-ttu-id="ac590-148">将应用程序上载到 Intune</span><span class="sxs-lookup"><span data-stu-id="ac590-148">Upload apps to Intune</span></span> | ![是](images/checkmark.png)     |
<span data-ttu-id="ac590-150">在 Microsoft 托管桌面环境中测试应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![是](images/checkmark.png) |  
<span data-ttu-id="ac590-152">与最终用户的测试应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-152">Test apps with end users</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="ac590-154">**部署**</span><span class="sxs-lookup"><span data-stu-id="ac590-154">**Deployment**</span></span> | |
<span data-ttu-id="ac590-155">管理，并将用户分配给应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-155">Manage and assign users to applications</span></span>  | ![是](images/checkmark.png)  |
<span data-ttu-id="ac590-157">Intune 部署工具提供向远程客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![是](images/checkmark.png)
<span data-ttu-id="ac590-159">确定并部署应用程序通过 Intune 的更新</span><span class="sxs-lookup"><span data-stu-id="ac590-159">Identify and deploy application updates through Intune</span></span> | ![是](images/checkmark.png)    |
<span data-ttu-id="ac590-161">卸载和删除应用程序，它们具有已停用时</span><span class="sxs-lookup"><span data-stu-id="ac590-161">Unistall and remove applications when they have been retired</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="ac590-163">**管理**</span><span class="sxs-lookup"><span data-stu-id="ac590-163">**Management**</span></span> | |
<span data-ttu-id="ac590-164">采购和分配许可证</span><span class="sxs-lookup"><span data-stu-id="ac590-164">Procure and assign licenses</span></span> |   ![是](images/checkmark.png)     |
<span data-ttu-id="ac590-166">提供对业务线应用程序的最终用户支持</span><span class="sxs-lookup"><span data-stu-id="ac590-166">Provide end-user support for line-of-business apps</span></span>  | ![是](images/checkmark.png) |
<span data-ttu-id="ac590-168">管理应用程序设置远程</span><span class="sxs-lookup"><span data-stu-id="ac590-168">Manage app settings remotely</span></span>    | ![是](images/checkmark.png) |

<span data-ttu-id="ac590-170">LOB 应用程序要求的信息，请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="ac590-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>


## <a name="intune-application-deployment"></a><span data-ttu-id="ac590-171">Intune 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="ac590-171">Intune application deployment</span></span>
<span data-ttu-id="ac590-p109">通过 Microsoft 托管桌面管理门户，或通过 Intune 门户，可以处理应用程序管理。Intune 的应用程序管理门户显示为 Windows、 Android 和 iOS 部署的应用程序。Microsoft 托管桌面管理门户限制到 Windows 10 应用程序的视图。二者都有通过 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="ac590-p109">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal.</span></span> 
* [<span data-ttu-id="ac590-176">Intune 应用程序管理基础知识</span><span class="sxs-lookup"><span data-stu-id="ac590-176">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
* [<span data-ttu-id="ac590-177">向 Intune 添加应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-177">Add apps to Intune</span></span>](https://docs.microsoft.com/intune/app-management)
   * [<span data-ttu-id="ac590-178">添加业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-178">Add a line-of-business App</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
   * [<span data-ttu-id="ac590-179">向 Intune 添加 Win32 应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-179">Add Win32 apps to Intune</span></span>](https://docs.microsoft.com/intune/apps-win32-app-management)
   * [<span data-ttu-id="ac590-180">添加 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-180">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
* [<span data-ttu-id="ac590-181">部署应用程序</span><span class="sxs-lookup"><span data-stu-id="ac590-181">Deploy apps</span></span>](https://docs.microsoft.com/intune/apps-deploy)
   * [<span data-ttu-id="ac590-182">将应用程序部署到 Windows 10</span><span class="sxs-lookup"><span data-stu-id="ac590-182">Deploy apps to Windows 10</span></span>](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)
* <span data-ttu-id="ac590-183">公司门户</span><span class="sxs-lookup"><span data-stu-id="ac590-183">Company Portal</span></span>
   * [<span data-ttu-id="ac590-184">部署的公司门户</span><span class="sxs-lookup"><span data-stu-id="ac590-184">Deploy the Company Portal</span></span>](https://docs.microsoft.com/intune/store-apps-company-portal-app)
   * [<span data-ttu-id="ac590-185">公司门户应用程序配置</span><span class="sxs-lookup"><span data-stu-id="ac590-185">Configure the Company Portal app</span></span>](https://docs.microsoft.com/intune/company-portal-app)
