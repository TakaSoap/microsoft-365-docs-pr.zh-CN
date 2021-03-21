---
title: Microsoft 托管桌面中的应用
description: 介绍如何处理应用，包括如何打包、部署和支持它们。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: ea0990e5f30aa45ec48bb2e6a7c957c187c74ebb
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922940"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="97d53-104">Microsoft 托管桌面中的应用</span><span class="sxs-lookup"><span data-stu-id="97d53-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="97d53-105">应用一般</span><span class="sxs-lookup"><span data-stu-id="97d53-105">Apps generally</span></span>

<span data-ttu-id="97d53-106">Microsoft 包括某些关键应用以及参与 Microsoft 托管桌面所需的 Microsoft 365 E3 或 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="97d53-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="97d53-107">但是，即使我们提供这些应用，你仍具有某些责任和操作需要完成。</span><span class="sxs-lookup"><span data-stu-id="97d53-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="97d53-108">还可通过公司门户或所需的后台安装（全部使用 Microsoft Intune 的部署管道）向用户部署其他非 Microsoft 应用进行自助服务。</span><span class="sxs-lookup"><span data-stu-id="97d53-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="97d53-109">如果你拥有专业知识，你可以迁移自己所需的应用;或者，Microsoft 咨询服务 (MCS) 或非 Microsoft 供应商将乐于帮助你完成打包和迁移项目。</span><span class="sxs-lookup"><span data-stu-id="97d53-109">If you have the expertise, you can migrate those apps you need yourself; alternatively, Microsoft Consulting Services (MCS) or non-Microsoft vendors will be happy to help you with a packaging and migration project.</span></span> <span data-ttu-id="97d53-110">有关使用 MCS 的信息，请参阅使用 [Microsoft 咨询服务](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="97d53-110">For more information about working with MCS, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>


## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="97d53-111">Microsoft 提供的应用</span><span class="sxs-lookup"><span data-stu-id="97d53-111">Apps provided by Microsoft</span></span>

<span data-ttu-id="97d53-112">Microsoft 托管桌面许可证包含 Microsoft 365 企业应用标准套件 (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business 和 One ) Note 中的 64 位版本的应用程序。默认情况下，Microsoft Project 和 Visio 的即点即用版本不包含在内。但你可以请求添加它们。</span><span class="sxs-lookup"><span data-stu-id="97d53-112">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="97d53-113">有关这些应用的信息，请参阅在 Microsoft 托管桌面设备上安装 Microsoft Project 或[Microsoft Visio。](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="97d53-113">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="97d53-114">Microsoft 为支持我们提供的应用而做哪些工作</span><span class="sxs-lookup"><span data-stu-id="97d53-114">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="97d53-115">Microsoft 将为包含的 Microsoft 365 企业应用版应用提供部署、更新和支持的完整服务。</span><span class="sxs-lookup"><span data-stu-id="97d53-115">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="97d53-116">默认情况下不包括 Microsoft Project 和 Visio 的即点即用版本，但 Microsoft 托管桌面将提供部署组，允许 IT 管理员管理许可证并为组织适当地部署这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="97d53-116">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="97d53-117">Microsoft 将通过 Microsoft 托管桌面支持渠道支持这些应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="97d53-117">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="97d53-118">需要执行哪些工作来支持我们提供的应用</span><span class="sxs-lookup"><span data-stu-id="97d53-118">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="97d53-119">对于这些应用，仍需要执行某些操作：</span><span class="sxs-lookup"><span data-stu-id="97d53-119">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="97d53-120">**分配许可证** - 你负责为 Microsoft 365 企业应用版的用户获取和分配相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="97d53-120">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="97d53-121">**将用户添加到安全组** - 如果使用的是 Microsoft Project 或 Visio，则 IT 管理员必须将这些用户添加到相应的部署组。</span><span class="sxs-lookup"><span data-stu-id="97d53-121">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="97d53-122">IT 管理员还负责在用户离开公司时回收这些用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="97d53-122">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="97d53-123">**部署 Microsoft 365** 加载项 - 如果你需要任何 Microsoft 365 企业应用版应用的任何加载项，请像任何其他 Windows 32 应用一样集中部署它们。</span><span class="sxs-lookup"><span data-stu-id="97d53-123">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="97d53-124">你提供的应用</span><span class="sxs-lookup"><span data-stu-id="97d53-124">Apps you provide</span></span>

<span data-ttu-id="97d53-125">你可能拥有业务操作所需的其他应用。</span><span class="sxs-lookup"><span data-stu-id="97d53-125">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="97d53-126">这些应用只能使用 Microsoft Intune 的部署管道部署到 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="97d53-126">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="97d53-127">如果应用需要它，你可以将其打包为供应商 (该供应商可能是非 Microsoft 供应商或 Microsoft 咨询服务 (MCS) ) 或者如果您具有方法，您可以自己打包它们。</span><span class="sxs-lookup"><span data-stu-id="97d53-127">If the app needs it you can have them packaged by a vendor (which could be a non-Microsoft vendor or Microsoft Consulting Services (MCS)) or if you have the means, you can package them yourself.</span></span> <span data-ttu-id="97d53-128">然后，将这些程序包添加到 Microsoft 托管桌面门户，并将其分配给 Azure Active Directory 组以触发部署。</span><span class="sxs-lookup"><span data-stu-id="97d53-128">You then add these packages to the Microsoft Managed Desktop portal and assign them to Azure Active Directory groups to trigger the deployment.</span></span> 

<span data-ttu-id="97d53-129">如果你当前使用 Microsoft Endpoint Configuration Manager 部署应用，Microsoft 托管桌面可以向您提供一个查询来评估你的应用，并发现哪些应用已准备好迁移到 Microsoft Intune 以及哪些可能需要一些调整。</span><span class="sxs-lookup"><span data-stu-id="97d53-129">If you currently deploy your apps by using Microsoft Endpoint Configuration Manager, Microsoft Managed Desktop can provide you with a query to assess your apps and discover which ones are ready for to migrate to Microsoft Intune and which ones might require some adjustment.</span></span>


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="97d53-130">准备你自己的应用以包含在 Microsoft 托管桌面中</span><span class="sxs-lookup"><span data-stu-id="97d53-130">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="97d53-131">查看应用，检查：</span><span class="sxs-lookup"><span data-stu-id="97d53-131">Review your apps, checking:</span></span>

- <span data-ttu-id="97d53-132">如 Microsoft 托管桌面应用要求中所述，任何应用均不受禁止或 [具有受限行为](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="97d53-132">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="97d53-133">应用必须已准备好由 Microsoft Intune 管理。</span><span class="sxs-lookup"><span data-stu-id="97d53-133">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="97d53-134">有关本主题的详细信息，请参阅使用[Microsoft Intune 的 Windows 10](/intune/apps-windows-10-app-deploy)应用部署和[将应用添加到 Microsoft Intune。](/intune/apps-add)</span><span class="sxs-lookup"><span data-stu-id="97d53-134">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="97d53-135">其他预打包要求，如提供许可证密钥、与许可条款的协议以及预先设置服务器连接。</span><span class="sxs-lookup"><span data-stu-id="97d53-135">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

### <a name="decide-how-to-package-apps"></a><span data-ttu-id="97d53-136">确定如何打包应用</span><span class="sxs-lookup"><span data-stu-id="97d53-136">Decide how to package apps</span></span>

<span data-ttu-id="97d53-137">一些独立的软件发布者可能要求在集中部署应用之前将其打包。</span><span class="sxs-lookup"><span data-stu-id="97d53-137">Some independent software publishers might require that your apps are packaged before they are centrally deployed.</span></span> <span data-ttu-id="97d53-138">"打包"意味着应用的安装程序使用许可证密钥、远程服务器位置或桌面快捷方式等设置进行配置，以便可以在后台安装应用。</span><span class="sxs-lookup"><span data-stu-id="97d53-138">“Packaging” means that the app’s installer is configured with settings like license keys, remote server locations, or desktop shortcuts so that the app can be installed in the background.</span></span>

<span data-ttu-id="97d53-139">有三个选项可以打包应用：</span><span class="sxs-lookup"><span data-stu-id="97d53-139">There are three options to get your apps packaged:</span></span> 


- <span data-ttu-id="97d53-140">你可以自己打包应用</span><span class="sxs-lookup"><span data-stu-id="97d53-140">You can package apps yourself</span></span>
- <span data-ttu-id="97d53-141">你可以与非 Microsoft 供应商合作</span><span class="sxs-lookup"><span data-stu-id="97d53-141">You can work with a non-Microsoft vendor</span></span>
- <span data-ttu-id="97d53-142">你可以与 MCS 合作打包应用。</span><span class="sxs-lookup"><span data-stu-id="97d53-142">You can engage with MCS to package your apps.</span></span> <span data-ttu-id="97d53-143">与 Microsoft 客户代表合作。</span><span class="sxs-lookup"><span data-stu-id="97d53-143">Work with your Microsoft account representative.</span></span> <span data-ttu-id="97d53-144">有关详细信息，请参阅使用 [Microsoft 咨询服务](apps-MCS.md)。</span><span class="sxs-lookup"><span data-stu-id="97d53-144">For more information, see [Working with Microsoft Consulting Services](apps-MCS.md).</span></span>



## <a name="deploying-apps"></a><span data-ttu-id="97d53-145">部署应用</span><span class="sxs-lookup"><span data-stu-id="97d53-145">Deploying apps</span></span>

<span data-ttu-id="97d53-146">无论使用哪种方法打包应用，完成后，你都已准备好按照将应用部署到 [Microsoft 托管桌面设备中的步骤操作](../get-started/deploy-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="97d53-146">Whatever method you use to get apps packaged, once that is complete, you're ready to follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>