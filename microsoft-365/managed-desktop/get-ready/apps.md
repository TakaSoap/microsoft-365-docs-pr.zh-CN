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
audience: Admin
ms.openlocfilehash: 571acc9c240fc0243998050ac3013258a2f85a3e
ms.sourcegitcommit: e02cf5702af178ddd2968877a808874ecb49ed2c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/26/2021
ms.locfileid: "52028940"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="04ad1-104">Microsoft 托管桌面中的应用</span><span class="sxs-lookup"><span data-stu-id="04ad1-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="04ad1-105">应用一般</span><span class="sxs-lookup"><span data-stu-id="04ad1-105">Apps generally</span></span>

<span data-ttu-id="04ad1-106">Microsoft 包括某些关键应用以及参与 Microsoft 托管桌面所需的 Microsoft 365 E3 或 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="04ad1-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="04ad1-107">但是，即使我们提供这些应用，你仍具有某些责任和操作需要完成。</span><span class="sxs-lookup"><span data-stu-id="04ad1-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="04ad1-108">还可通过公司门户或所需的后台安装（全部使用 Microsoft Intune 的部署管道）向用户部署其他非 Microsoft 应用进行自助服务。</span><span class="sxs-lookup"><span data-stu-id="04ad1-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="04ad1-109">Microsoft 提供的应用</span><span class="sxs-lookup"><span data-stu-id="04ad1-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="04ad1-110">Microsoft 托管桌面许可证包含 Microsoft 365 企业应用标准套件 (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business 和 One ) Note 中的 64 位版本的应用程序。默认情况下，Microsoft Project 和 Visio 的即点即用版本不包含在内。但你可以请求添加它们。</span><span class="sxs-lookup"><span data-stu-id="04ad1-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Skype for Business, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="04ad1-111">有关这些应用的信息，请参阅在 Microsoft 托管桌面设备上安装 Microsoft Project 或[Microsoft Visio。](../get-started/project-visio.md)</span><span class="sxs-lookup"><span data-stu-id="04ad1-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="04ad1-112">Microsoft 为支持我们提供的应用而做哪些工作</span><span class="sxs-lookup"><span data-stu-id="04ad1-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="04ad1-113">Microsoft 将为包含的 Microsoft 365 企业应用版应用提供部署、更新和支持的完整服务。</span><span class="sxs-lookup"><span data-stu-id="04ad1-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="04ad1-114">默认情况下不包括 Microsoft Project 和 Visio 的即点即用版本，但 Microsoft 托管桌面将提供部署组，允许 IT 管理员管理许可证并为组织适当地部署这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="04ad1-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="04ad1-115">Microsoft 将通过 Microsoft 托管桌面支持渠道支持这些应用程序的用户。</span><span class="sxs-lookup"><span data-stu-id="04ad1-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="04ad1-116">需要执行哪些工作来支持我们提供的应用</span><span class="sxs-lookup"><span data-stu-id="04ad1-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="04ad1-117">对于这些应用，仍需要执行某些操作：</span><span class="sxs-lookup"><span data-stu-id="04ad1-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="04ad1-118">**分配许可证** - 你负责为 Microsoft 365 企业应用版的用户获取和分配相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="04ad1-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="04ad1-119">**将用户添加到安全组** - 如果使用的是 Microsoft Project 或 Visio，则 IT 管理员必须将这些用户添加到相应的部署组。</span><span class="sxs-lookup"><span data-stu-id="04ad1-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="04ad1-120">IT 管理员还负责在用户离开公司时回收这些用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="04ad1-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="04ad1-121">**部署 Microsoft 365** 加载项 - 如果你需要任何 Microsoft 365 企业应用版应用的任何加载项，请像任何其他 Windows 32 应用一样集中部署它们。</span><span class="sxs-lookup"><span data-stu-id="04ad1-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="04ad1-122">你提供的应用</span><span class="sxs-lookup"><span data-stu-id="04ad1-122">Apps you provide</span></span>

<span data-ttu-id="04ad1-123">你可能拥有业务操作所需的其他应用。</span><span class="sxs-lookup"><span data-stu-id="04ad1-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="04ad1-124">这些应用只能使用 Microsoft Intune 的部署管道部署到 Microsoft 托管桌面设备。</span><span class="sxs-lookup"><span data-stu-id="04ad1-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="04ad1-125">有关应用程序部署详细信息，请按照将应用部署到 [Microsoft 托管桌面设备中的步骤操作](../get-started/deploy-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="04ad1-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="04ad1-126">准备你自己的应用以包含在 Microsoft 托管桌面中</span><span class="sxs-lookup"><span data-stu-id="04ad1-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="04ad1-127">查看应用，检查：</span><span class="sxs-lookup"><span data-stu-id="04ad1-127">Review your apps, checking:</span></span>

- <span data-ttu-id="04ad1-128">如 Microsoft 托管桌面应用要求中所述，任何应用均不受禁止或 [具有受限行为](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="04ad1-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="04ad1-129">应用必须已准备好由 Microsoft Intune 管理。</span><span class="sxs-lookup"><span data-stu-id="04ad1-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="04ad1-130">有关本主题的详细信息，请参阅使用[Microsoft Intune 的 Windows 10](/intune/apps-windows-10-app-deploy)应用部署和[将应用添加到 Microsoft Intune。](/intune/apps-add)</span><span class="sxs-lookup"><span data-stu-id="04ad1-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="04ad1-131">其他预打包要求，如提供许可证密钥、与许可条款的协议以及预先设置服务器连接。</span><span class="sxs-lookup"><span data-stu-id="04ad1-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="04ad1-132">准备步骤</span><span class="sxs-lookup"><span data-stu-id="04ad1-132">Steps to get ready</span></span>

1. <span data-ttu-id="04ad1-133">查看 [Microsoft 托管桌面的先决条件](prerequisites.md)。</span><span class="sxs-lookup"><span data-stu-id="04ad1-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="04ad1-134">使用 [准备情况评估工具](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="04ad1-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="04ad1-135">来宾帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="04ad1-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="04ad1-136">Microsoft 托管桌面的网络配置</span><span class="sxs-lookup"><span data-stu-id="04ad1-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="04ad1-137">为 Microsoft 托管桌面准备证书和网络配置文件</span><span class="sxs-lookup"><span data-stu-id="04ad1-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="04ad1-138">为 Microsoft 托管桌面准备本地资源访问权限</span><span class="sxs-lookup"><span data-stu-id="04ad1-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="04ad1-139">[Microsoft 托管桌面](apps.md) 应用程序中 (本文) </span><span class="sxs-lookup"><span data-stu-id="04ad1-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="04ad1-140">为 Microsoft 托管桌面准备映射的驱动器</span><span class="sxs-lookup"><span data-stu-id="04ad1-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="04ad1-141">为 Microsoft 托管桌面准备打印资源</span><span class="sxs-lookup"><span data-stu-id="04ad1-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
