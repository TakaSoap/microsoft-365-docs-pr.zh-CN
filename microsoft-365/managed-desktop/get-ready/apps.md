---
title: Microsoft 托管桌面中的应用程序
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: db89e3b1f8b5b8073eab62e4b4d38087e1e73fa4
ms.sourcegitcommit: 498340389e1c34f49f0b2da382c23c8d5334ae47
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2019
ms.locfileid: "34913043"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="095ee-103">Microsoft 托管桌面中的应用程序</span><span class="sxs-lookup"><span data-stu-id="095ee-103">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="095ee-104">应用程序通常</span><span class="sxs-lookup"><span data-stu-id="095ee-104">Apps generally</span></span>

<span data-ttu-id="095ee-105">Microsoft 包括一些关键应用, 以及 Microsoft 365 E3 或 E5 许可证需要参与 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="095ee-105">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="095ee-106">但是, 即使我们提供这些应用, 仍需要完成一些责任和操作。</span><span class="sxs-lookup"><span data-stu-id="095ee-106">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="095ee-107">您还可以通过公司门户或所需的后台安装将其他非 Microsoft 应用程序部署到最终用户, 以使用 Microsoft Intune 的部署管道进行自助服务。</span><span class="sxs-lookup"><span data-stu-id="095ee-107">You can also deploy additional non-Microsoft apps to your end users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="095ee-108">如果你有专业技能, 你可以自己迁移你需要的应用程序;如果不是 Microsoft 咨询服务 (MCS) 或非 Microsoft 供应商将很乐意帮助你进行打包和迁移项目。</span><span class="sxs-lookup"><span data-stu-id="095ee-108">If you have the expertise you can migrate those apps you need yourself; if not either Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="095ee-109">有关使用 MCS 的详细信息, 请参阅使用[Microsoft 咨询服务](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="095ee-109">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="095ee-110">Microsoft 提供的应用程序</span><span class="sxs-lookup"><span data-stu-id="095ee-110">Apps provided by Microsoft</span></span>

<span data-ttu-id="095ee-111">包含在 Microsoft 托管桌面许可证中, 是 Office 365 专业增强版 Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business 和 OneNote) 中的应用程序的64位版本。默认情况下,*不*包含即点即用版本的 Microsoft Project 和 Visio, 但您可以请求添加它们。</span><span class="sxs-lookup"><span data-stu-id="095ee-111">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Office 365 ProPlus Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="095ee-112">有关这些应用程序的详细信息, 请参阅[在 Microsoft 托管桌面设备上安装 Microsoft Project 或 Microsoft Visio](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="095ee-112">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="095ee-113">Microsoft 为支持我们提供的应用程序所做的操作</span><span class="sxs-lookup"><span data-stu-id="095ee-113">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="095ee-114">Microsoft 将为包含的 Office 365 专业增强版应用程序提供完整的服务, 以实现部署、更新和支持。</span><span class="sxs-lookup"><span data-stu-id="095ee-114">Microsoft will provide full service for the deployment, update, and support for the included Office 365 ProPlus apps.</span></span> <span data-ttu-id="095ee-115">即点即用版本的 Microsoft Project 和 Visio 在默认情况下*不*包括在内, 但 Microsoft 托管桌面将提供部署组, 使 IT 管理员能够管理许可证并适当地部署这些应用程序以适合您的组织.</span><span class="sxs-lookup"><span data-stu-id="095ee-115">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="095ee-116">Microsoft 将通过 Microsoft 托管桌面支持频道支持这些应用程序的最终用户。</span><span class="sxs-lookup"><span data-stu-id="095ee-116">Microsoft will support end users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="095ee-117">为支持我们提供的应用程序所需的操作</span><span class="sxs-lookup"><span data-stu-id="095ee-117">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="095ee-118">对于这些应用程序, 仍需要执行某些操作:</span><span class="sxs-lookup"><span data-stu-id="095ee-118">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="095ee-119">**分配许可证**-您负责为最终用户获取和分配适用于 Office 365 专业增强版的许可证。</span><span class="sxs-lookup"><span data-stu-id="095ee-119">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to end users for Office 365 ProPlus.</span></span>
- <span data-ttu-id="095ee-120">**将用户添加到安全组**-如果你使用的是 Microsoft Project 或 VISIO, IT 管理员必须将这些用户添加到相应的部署组。</span><span class="sxs-lookup"><span data-stu-id="095ee-120">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="095ee-121">IT 管理员还负责从这些用户那里回收许可证 (如果他们离开公司)。</span><span class="sxs-lookup"><span data-stu-id="095ee-121">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="095ee-122">**部署 office 365 Addons** -如果您需要任何 Office 365 专业增强版应用程序的 Addons, 请将其集中部署, 如任何其他 Windows 32 应用。</span><span class="sxs-lookup"><span data-stu-id="095ee-122">**Deploy Office 365 Addons** - If you need any Addons for any of the Office 365 ProPlus apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="095ee-123">你提供的应用</span><span class="sxs-lookup"><span data-stu-id="095ee-123">Apps you provide</span></span>

<span data-ttu-id="095ee-124">当然, 您可能需要许多其他应用程序来实现业务运营。</span><span class="sxs-lookup"><span data-stu-id="095ee-124">Of course, you probably have a number of other apps you need for your business operations.</span></span> <span data-ttu-id="095ee-125">只能使用 Microsoft Intune 的部署管道将这些可部署到 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="095ee-125">These can can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="095ee-126">如果应用程序需要, 可以让供应商打包它们 (可能是非 Microsoft 供应商或 Microsoft 咨询服务 (MCS)), 或者如果你有这种方法, 则可以自行打包。</span><span class="sxs-lookup"><span data-stu-id="095ee-126">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="095ee-127">然后, 将这些程序包添加到 Microsoft 托管桌面门户, 并将其分配给 Azure Active Directory 组以触发部署。</span><span class="sxs-lookup"><span data-stu-id="095ee-127">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="095ee-128">如果你当前使用 System Center Configuration Manager 部署应用, Microsoft 托管桌面可以为你提供评估应用程序的查询, 并发现哪些应用程序可以迁移到 Microsoft Intune, 以及哪些可能需要进行一些调整.</span><span class="sxs-lookup"><span data-stu-id="095ee-128">If you currently deploy your apps by using System Center Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="095ee-129">准备您自己的应用程序以包含在 Microsoft 托管桌面中</span><span class="sxs-lookup"><span data-stu-id="095ee-129">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="095ee-130">查看您的应用程序, 检查:</span><span class="sxs-lookup"><span data-stu-id="095ee-130">Review your apps, checking:</span></span>

- <span data-ttu-id="095ee-131">不允许任何应用程序, 也不具有限制的行为, 如[Microsoft 托管桌面应用程序要求](https://aka.ms/app-req)中所述。</span><span class="sxs-lookup"><span data-stu-id="095ee-131">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](https://aka.ms/app-req).</span></span>
- <span data-ttu-id="095ee-132">应用必须准备好由 Microsoft Intune 进行管理。</span><span class="sxs-lookup"><span data-stu-id="095ee-132">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="095ee-133">有关此信息的详细信息, 请参阅[使用 Microsoft intune 的 Windows 10 应用程序部署](https://docs.microsoft.com/intune/apps-windows-10-app-deploy)和[向 Microsoft intune 添加应用程序](https://docs.microsoft.com/intune/apps-add)。</span><span class="sxs-lookup"><span data-stu-id="095ee-133">For more about this, see [Windows 10 app deployment using Microsoft Intune](https://docs.microsoft.com/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](https://docs.microsoft.com/intune/apps-add).</span></span>
- <span data-ttu-id="095ee-134">其他预打包要求, 例如提供许可证密钥、许可条款协议和预设置服务器连接。</span><span class="sxs-lookup"><span data-stu-id="095ee-134">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="095ee-135">决定如何打包应用程序</span><span class="sxs-lookup"><span data-stu-id="095ee-135">Decide how to package apps</span></span>

<span data-ttu-id="095ee-136">某些独立软件供应商可能需要先打包应用程序, 然后再进行集中部署。</span><span class="sxs-lookup"><span data-stu-id="095ee-136">Some independent software vendors might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="095ee-137">"打包" 意味着应用程序的安装程序配置了诸如许可证密钥、远程服务器位置或桌面快捷方式之类的设置, 以便可以在后台安装应用程序。</span><span class="sxs-lookup"><span data-stu-id="095ee-137">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="095ee-138">有三个选项可用于获取打包的应用程序:</span><span class="sxs-lookup"><span data-stu-id="095ee-138">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="095ee-139">您可以自己打包应用程序</span><span class="sxs-lookup"><span data-stu-id="095ee-139">You can package apps yourself</span></span>
- <span data-ttu-id="095ee-140">您可以使用非 Microsoft 供应商</span><span class="sxs-lookup"><span data-stu-id="095ee-140">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="095ee-141">你可以与 MCS 接洽以打包你的应用。</span><span class="sxs-lookup"><span data-stu-id="095ee-141">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="095ee-142">与你的 Microsoft 帐户代表合作。</span><span class="sxs-lookup"><span data-stu-id="095ee-142">Work with your Microsoft account representative.</span></span> <span data-ttu-id="095ee-143">有关更多详细信息, 请参阅使用[Microsoft 咨询服务](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="095ee-143">For more details, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>







## <a name="deploying-apps"></a><span data-ttu-id="095ee-144">部署应用程序</span><span class="sxs-lookup"><span data-stu-id="095ee-144">Deploying apps</span></span>

<span data-ttu-id="095ee-145">无论使用哪种方法来获取打包的应用程序, 完成后, 都可以按照 "[将应用程序部署到 Microsoft 托管桌面设备](../get-started/deploy-apps.md)" 中的步骤进行操作。</span><span class="sxs-lookup"><span data-stu-id="095ee-145">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>


