---
title: 应用程序准备 Microsoft 托管桌面
description: ''
keywords: Microsoft 托管桌面，Microsoft 365 服务文档
ms.service: m365-md
author: jdeckerms
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.openlocfilehash: ebeb54bd5d1f50cbb6f78b1c8ad4a624c449b8c2
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865602"
---
# <a name="preparing-apps-for-microsoft-managed-desktop"></a><span data-ttu-id="98e19-103">应用程序准备 Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="98e19-103">Preparing apps for Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
<span data-ttu-id="98e19-104">Microsoft 和 Microsoft 托管桌面客户同样可以围绕用于 Microsoft 托管桌面应用程序的关键、 尚未不同责任。</span><span class="sxs-lookup"><span data-stu-id="98e19-104">Microsoft and Microsoft Managed Desktop customers have equally critical, yet different responsibilities around applications used with Microsoft Managed Desktop.</span></span>

## <a name="microsoft-responsibilites"></a><span data-ttu-id="98e19-105">Microsoft 职责</span><span class="sxs-lookup"><span data-stu-id="98e19-105">Microsoft responsibilites</span></span>
<span data-ttu-id="98e19-p101">**Office 365 应用程序**Microsoft 将提供完整的部署、 更新和支持的特定的 Office 365 应用程序服务。所有用户将都收到运行，以便用户可以迅速提高效率，包括在设备的图像的应用程序的 64 位版本的 Office 365 单击了基本集。项目和 Visio 中的应用程序的 Office 365 套件是单独授权。 Microsoft 托管桌面将提供部署组允许 IT 管理员管理许可证和部署这些适当地为其组织的应用程序。通过 Microsoft 托管桌面支持渠道这些应用程序的最终用户时，Microsoft 将提供支持。</span><span class="sxs-lookup"><span data-stu-id="98e19-p101">**Office 365 apps** Microsoft will provide full service for the deployment, update, and support of specific Office 365 apps. All users will receive the base set of Office 365 click to run, 64 bit version of applications included in the device’s image so that a user can quickly become productive. The Project and Visio applications in of the Office 365 suite are licensed separately.  Microsoft Managed Desktop will provide deployment groups allowing the IT Administrator to manage licenses and deploy these applications appropriately for their organization. Microsoft will support end users of these applications through the Microsoft Managed Desktop Support channels.</span></span>

<span data-ttu-id="98e19-p102">**业务线应用程序**Microsoft 提供的面向 IT 管理员管理和作为 Intune 产品的一部分部署到最终用户其业务线应用程序的工具。Microsoft 将支持[业务线应用程序](#line-of-business-applications)中所述的应用程序部署问题</span><span class="sxs-lookup"><span data-stu-id="98e19-p102">**Line-of-business apps** Microsoft provides tooling for IT Administrators to manage and deploy their Line of Business applications to end users as a part of the Intune product. Microsoft will support application deployment issues as detailed in [Line-of-business applications](#line-of-business-applications)</span></span> 

<span data-ttu-id="98e19-p103">**使用 Intune 部署**Intune 将链接到**Microsoft Store for Business**中，在 Microsoft 托管桌面入职培训允许已采购的应用程序通过 Intune 部署过程中。Microsoft 还会给最终用户部署的公司门户的基于 web 的版本，以便 IT 管理员可以为最终用户提供自助式体验。</span><span class="sxs-lookup"><span data-stu-id="98e19-p103">**Deploy with Intune** Intune will be linked to the **Microsoft Store for Business** during Microsoft Managed Desktop onboarding allowing procured apps to be deployed through Intune. Microsoft will also deploy the web-based version of the Company Portal to end users so that IT Administrators can provide a self-service experience for end users.</span></span>

<span data-ttu-id="98e19-p104">**应用程序管理**Microsoft 可能确定受限制的应用程序，由于其系统影响不适合现代工作区。标识此类应用程序时 Microsoft 将通知客户，该应用程序将需要从租户中删除。</span><span class="sxs-lookup"><span data-stu-id="98e19-p104">**App management** Microsoft may identify restricted applications which are not suitable for the modern workplace because of their system impact. When such an application is identified Microsoft will notify the customer and that application will need to be removed from the tenant.</span></span> 

## <a name="customer-responsibilities"></a><span data-ttu-id="98e19-117">客户责任</span><span class="sxs-lookup"><span data-stu-id="98e19-117">Customer responsibilities</span></span>
<span data-ttu-id="98e19-p105">Office 365 套件是 Microsoft 的工作效率产品的核心和包含的所有 Microsoft 托管桌面用户 Microsoft 365 许可证中。Microsoft 部署、 更新和支持 Microsoft 托管桌面设备的 Office 应用程序时仍有某些客户负责的区域。</span><span class="sxs-lookup"><span data-stu-id="98e19-p105">The Office 365 Suite is core to Microsoft’s productivity offerings and is included in the Microsoft 365 License for all Microsoft Managed Desktop users. While Microsoft deploys, updates, and supports Office Applications to Microsoft Managed Desktop Devices there are still some areas for which the customer is responsible.</span></span>
- <span data-ttu-id="98e19-120">**分配许可证**的客户负责将相应的许可证分配给 Office 365 的最终用户。</span><span class="sxs-lookup"><span data-stu-id="98e19-120">**Assign licenses** - Customers are responsible for assigning the appropriate licenses to end users for Office 365.</span></span> 
- <span data-ttu-id="98e19-p106">**向安全组添加用户**-与用户客户需要项目或 Visio 的 IT 管理员必须这些将用户添加到适当的部署组。IT 管理员也是负责管理这些用户的生命周期结束。</span><span class="sxs-lookup"><span data-stu-id="98e19-p106">**Add users to security groups** - For customers with users who need Project or Visio, the IT administrator must add those users to the appropriate deployment groups. IT administrators are also responsible for managing end of life for those users.</span></span> 
- <span data-ttu-id="98e19-123">**部署 Office 365 加载项**的客户负责部署到 Office 365 套件，这必要的任何插件。</span><span class="sxs-lookup"><span data-stu-id="98e19-123">**Deploy Office 365 Add Ons** - Customers are responsible for deploying any plugins to the Office 365 suite which are deemed necessary.</span></span> 

<span data-ttu-id="98e19-p107">由于是唯一的每个客户的业务线 (LOB) 应用程序，客户负责管理未部署由 Microsoft 其组织内的所有应用程序。这包括：</span><span class="sxs-lookup"><span data-stu-id="98e19-p107">Since line-of-business (LOB) apps are unique for each customer, customers are responsible for managing all applications within their organization not deployed by Microsoft. This includes:</span></span>
- <span data-ttu-id="98e19-126">确定所需的应用程序和用户需要它们</span><span class="sxs-lookup"><span data-stu-id="98e19-126">Deciding which apps are needed and who needs them</span></span>
- <span data-ttu-id="98e19-127">将应用程序分配给这些用户</span><span class="sxs-lookup"><span data-stu-id="98e19-127">Assigning apps to those users</span></span>
- <span data-ttu-id="98e19-128">创建和维护用于管理应用程序分配的 Azure Active Directory (AD) 组</span><span class="sxs-lookup"><span data-stu-id="98e19-128">Create and maintain Azure Active Directory (AD) groups for managing app assignments</span></span> 

<span data-ttu-id="98e19-p108">一旦被标识的 LOB 应用程序的核心集客户将采购、 许可、 打包、 和 Microsoft 托管桌面环境中测试这些应用程序。客户必须上载并部署到 Intune 以部署、 更新和停用其 LOB 应用程序的应用程序。客户负责管理 LOB 应用程序支持的用户。</span><span class="sxs-lookup"><span data-stu-id="98e19-p108">Once the core set of LOB apps has been identified the customer will procure, license, package, and test those applications in the Microsoft Managed Desktop environment. The customer must upload and deploy applications to Intune to deploy, update, and decommission their LOB applications. Customers are responsible for managing LOB apps support for their users.</span></span>
 

## <a name="office-applications"></a><span data-ttu-id="98e19-132">Office 应用程序</span><span class="sxs-lookup"><span data-stu-id="98e19-132">Office applications</span></span>
<span data-ttu-id="98e19-133">作为 Microsoft 365 E5 许可证的一部分，Microsoft 部署 Office 365 Standard Suite （64 位）。</span><span class="sxs-lookup"><span data-stu-id="98e19-133">As part of the Microsoft 365 E5 license, Office 365 Standard Suite (64 Bit) is deployed by Microsoft.</span></span> 

<span data-ttu-id="98e19-134">有关详细信息，请参阅[Microsoft 托管桌面技术](../intro/technologies.md)<!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span><span class="sxs-lookup"><span data-stu-id="98e19-134">For details, see [Microsoft Managed Desktop technologies](../intro/technologies.md) <!--- and the other applications licensed under Office 365 E5 may be deployed by the customer using Intune’s deployment tools.--></span></span>

## <a name="line-of-business-applications"></a><span data-ttu-id="98e19-135">业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="98e19-135">Line-of-business applications</span></span>
<span data-ttu-id="98e19-136">此表总结了跨-的业务线 (LOB) 应用程序的不同阶段的责任。</span><span class="sxs-lookup"><span data-stu-id="98e19-136">This table summarizes responsibilities across the different phases for line-of-business (LOB) applications.</span></span> 

<span data-ttu-id="98e19-137">应用程序工作项</span><span class="sxs-lookup"><span data-stu-id="98e19-137">Application work items</span></span> |    <span data-ttu-id="98e19-138">客户</span><span class="sxs-lookup"><span data-stu-id="98e19-138">Customer</span></span>    | <span data-ttu-id="98e19-139">Microsoft</span><span class="sxs-lookup"><span data-stu-id="98e19-139">Microsoft</span></span>
--- | --- | ---
<span data-ttu-id="98e19-140">**加入应用程序**</span><span class="sxs-lookup"><span data-stu-id="98e19-140">**Onboarding apps**</span></span> |  |
<span data-ttu-id="98e19-141">确定应用程序所需的目标的用户组</span><span class="sxs-lookup"><span data-stu-id="98e19-141">Identify applications needed for targeted user groups</span></span>   | ![是](images/checkmark.png)  |
<span data-ttu-id="98e19-143">创建和管理应用程序部署 Azure AD 组</span><span class="sxs-lookup"><span data-stu-id="98e19-143">Create and manage Azure AD groups for app deployment</span></span> | ![是](images/checkmark.png) |   
<span data-ttu-id="98e19-145">**应用程序打包**</span><span class="sxs-lookup"><span data-stu-id="98e19-145">**App Packaging**</span></span> |  |
<span data-ttu-id="98e19-146">包应用程序，以满足 Intune 部署标准</span><span class="sxs-lookup"><span data-stu-id="98e19-146">Package apps to meet Intune deployment standards</span></span> |  ![是](images/checkmark.png) |  
<span data-ttu-id="98e19-148">将应用程序上载到 Intune</span><span class="sxs-lookup"><span data-stu-id="98e19-148">Upload apps to Intune</span></span> | ![是](images/checkmark.png)     |
<span data-ttu-id="98e19-150">在 Microsoft 托管桌面环境中测试应用程序</span><span class="sxs-lookup"><span data-stu-id="98e19-150">Test apps in Microsoft Managed Desktop environment</span></span> |    ![是](images/checkmark.png) |  
<span data-ttu-id="98e19-152">与最终用户的测试应用程序</span><span class="sxs-lookup"><span data-stu-id="98e19-152">Test apps with end users</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="98e19-154">**Deployment**</span><span class="sxs-lookup"><span data-stu-id="98e19-154">**Deployment**</span></span> | |
<span data-ttu-id="98e19-155">管理，并将用户分配给应用程序</span><span class="sxs-lookup"><span data-stu-id="98e19-155">Manage and assign users to applications</span></span>  | ![是](images/checkmark.png)  |
<span data-ttu-id="98e19-157">Intune 部署工具提供向远程客户端应用程序</span><span class="sxs-lookup"><span data-stu-id="98e19-157">Intune deployment tools delivers application to remote clients</span></span>| |   ![是](images/checkmark.png)
<span data-ttu-id="98e19-159">确定并部署应用程序通过 Intune 的更新</span><span class="sxs-lookup"><span data-stu-id="98e19-159">Identify and deploy application updates through Intune</span></span> | ![是](images/checkmark.png)    |
<span data-ttu-id="98e19-161">卸载和删除应用程序，它们具有已停用时</span><span class="sxs-lookup"><span data-stu-id="98e19-161">Unistall and remove applications when they have been retired</span></span>    | ![是](images/checkmark.png) |    
<span data-ttu-id="98e19-163">**管理**</span><span class="sxs-lookup"><span data-stu-id="98e19-163">**Management**</span></span> | |
<span data-ttu-id="98e19-164">采购和分配许可证</span><span class="sxs-lookup"><span data-stu-id="98e19-164">Procure and assign licenses</span></span> |   ![是](images/checkmark.png)     |
<span data-ttu-id="98e19-166">提供对业务线应用程序的最终用户支持</span><span class="sxs-lookup"><span data-stu-id="98e19-166">Provide end-user support for line-of-business apps</span></span>  | ![是](images/checkmark.png) |
<span data-ttu-id="98e19-168">管理应用程序设置远程</span><span class="sxs-lookup"><span data-stu-id="98e19-168">Manage app settings remotely</span></span>    | ![是](images/checkmark.png) |

<span data-ttu-id="98e19-170">LOB 应用程序要求的信息，请参阅[Microsoft 托管桌面应用程序要求](../service-description/mmd-app-requirements.md)</span><span class="sxs-lookup"><span data-stu-id="98e19-170">For information on LOB application requirements, see [Microsoft Managed Desktop application requirements](../service-description/mmd-app-requirements.md)</span></span>

## <a name="resources"></a><span data-ttu-id="98e19-171">资源</span><span class="sxs-lookup"><span data-stu-id="98e19-171">Resources</span></span>
<span data-ttu-id="98e19-172">超出范围 Microsoft 托管桌面操作的许多服务时有哪些 Microsoft 提供的可帮助客户管理自己的应用程序的服务。</span><span class="sxs-lookup"><span data-stu-id="98e19-172">While many services are out of scope for Microsoft Managed Desktop operations there are services which Microsoft offers which may help the customer manage their applications.</span></span>

### <a name="windows-upgrade-readiness"></a><span data-ttu-id="98e19-173">Windows 升级准备</span><span class="sxs-lookup"><span data-stu-id="98e19-173">Windows Upgrade Readiness</span></span>
<span data-ttu-id="98e19-p109">设置新的 Microsoft 托管的设备的关键部分了解设备用户所需的应用程序。Windows 升级准备是一个有助于企业理解其公司，内部应用程序环境并帮助他们如查看有关这些应用程序的关键数据的 Microsoft 工具：</span><span class="sxs-lookup"><span data-stu-id="98e19-p109">A key part of setting up new Microsoft Managed Devices is understanding which apps are needed for device users. Windows Upgrade Readiness is a Microsoft tool which helps enterprises understand the application landscape inside their company, and helps them to review key data about those applications, such as:</span></span>

- <span data-ttu-id="98e19-176">**应用程序使用率**的遥测数据用于监视应用程序使用率。</span><span class="sxs-lookup"><span data-stu-id="98e19-176">**Application usage** - Telemetry data is used to monitor application usage.</span></span>
- <span data-ttu-id="98e19-p110">**应用程序兼容性**的升级准备查看每个应用程序和看到如何广泛已部署在最新版本的 Windows 10 并评估如何确定它是否"准备 Windows"。此数据可帮助焦点测试不已广泛所采用的应用程序上的工作。</span><span class="sxs-lookup"><span data-stu-id="98e19-p110">**Application compatibility** - Upgrade Readiness looks at each application and sees how broadly it has been deployed on the latest version of Windows 10 and assesses how to identify if it is “Ready for Windows”. This data helps focus testing efforts on applications which aren’t already broadly adopted.</span></span>

### <a name="intune-application-deployment"></a><span data-ttu-id="98e19-179">Intune 应用程序部署</span><span class="sxs-lookup"><span data-stu-id="98e19-179">Intune application deployment</span></span>
<span data-ttu-id="98e19-p111">通过 Microsoft 托管桌面管理门户，或通过 Intune 门户，可以处理应用程序管理。Intune 的应用程序管理门户显示为 Windows、 Android 和 iOS 部署的应用程序。Microsoft 托管桌面管理门户限制到 Windows 10 应用程序的视图。二者都有通过 Azure 门户。</span><span class="sxs-lookup"><span data-stu-id="98e19-p111">Application management can be handled through the Microsoft Managed Desktop Admin portal, or through the Intune portal. Intune’s app management portal shows applications deployed for Windows, Android, and iOS. Microsoft Managed Desktop Admin portal limits the view to Windows 10 applications. Both are available through the Azure Portal.</span></span> 
- [<span data-ttu-id="98e19-184">Intune 应用程序管理基础知识</span><span class="sxs-lookup"><span data-stu-id="98e19-184">Intune app management basics</span></span>](https://docs.microsoft.com/intune/app-management)
- [<span data-ttu-id="98e19-185">添加 Windows 32 应用程序</span><span class="sxs-lookup"><span data-stu-id="98e19-185">Add a Windows 32 application</span></span>](https://docs.microsoft.com/intune/lob-apps-windows)
- [<span data-ttu-id="98e19-186">添加 web 应用程序</span><span class="sxs-lookup"><span data-stu-id="98e19-186">Add web applications</span></span>](https://docs.microsoft.com/intune/web-app)
- [<span data-ttu-id="98e19-187">分配并将应用程序部署到组</span><span class="sxs-lookup"><span data-stu-id="98e19-187">Assign and deploy apps to groups</span></span>](https://docs.microsoft.com/intune/apps-deploy)

### <a name="application-packaging-standards"></a><span data-ttu-id="98e19-188">应用程序打包标准</span><span class="sxs-lookup"><span data-stu-id="98e19-188">Application packaging standards</span></span>
<span data-ttu-id="98e19-p112">部署 Windows 32 应用程序通过 Intune 它们必须打包为以下任意一个。MSI，.appx，或。MSIX。Intune 的最常见包类型是当前。MSI。</span><span class="sxs-lookup"><span data-stu-id="98e19-p112">To deploy Windows 32 applications through Intune they must be packaged as either a single .MSI, an .appx, or .MSIX. The most common package type for Intune is currently .MSI.</span></span>
