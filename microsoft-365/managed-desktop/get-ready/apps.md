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
ms.openlocfilehash: 37f533f34753d66d975cb557239b2b168ac78f8e
ms.sourcegitcommit: 997a21b83795789cda0a6b4a77f9985a3233d0c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53430764"
---
# <a name="apps-in-microsoft-managed-desktop"></a><span data-ttu-id="f6c06-104">Microsoft 托管桌面中的应用</span><span class="sxs-lookup"><span data-stu-id="f6c06-104">Apps in Microsoft Managed Desktop</span></span>

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a><span data-ttu-id="f6c06-105">应用一般</span><span class="sxs-lookup"><span data-stu-id="f6c06-105">Apps generally</span></span>

<span data-ttu-id="f6c06-106">Microsoft 包括某些关键应用以及Microsoft 365 E3参与此活动所需的 E5 或 Microsoft 托管桌面。</span><span class="sxs-lookup"><span data-stu-id="f6c06-106">Microsoft includes certain key apps along with the Microsoft 365 E3 or E5 license needed to participate in Microsoft Managed Desktop.</span></span> <span data-ttu-id="f6c06-107">但是，即使我们提供这些应用，你仍具有某些责任和操作需要完成。</span><span class="sxs-lookup"><span data-stu-id="f6c06-107">However, even though we provide these apps, you still have certain responsibilities and actions to complete.</span></span>

<span data-ttu-id="f6c06-108">此外，还可通过 公司门户 或所需的后台安装，向用户部署其他非 Microsoft 应用，Microsoft Intune部署管道。</span><span class="sxs-lookup"><span data-stu-id="f6c06-108">You can also deploy additional non-Microsoft apps to your users for self-service through the Company Portal or a required background installation, all using Microsoft Intune’s deployment pipeline.</span></span> 

## <a name="apps-provided-by-microsoft"></a><span data-ttu-id="f6c06-109">Microsoft 提供的应用</span><span class="sxs-lookup"><span data-stu-id="f6c06-109">Apps provided by Microsoft</span></span>

<span data-ttu-id="f6c06-110">Microsoft 托管桌面 许可证包含 Microsoft 365 企业应用版 Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Teams 和 OneNote.) 即点即用版本的 Microsoft Project 和 Visio 中应用的 64 位版本，但你可以请求添加它们。 </span><span class="sxs-lookup"><span data-stu-id="f6c06-110">Included with your Microsoft Managed Desktop license are 64-bit versions of the apps in the Microsoft 365 Apps for enterprise Standard Suite (Word, Excel, PowerPoint, Outlook, Publisher, Access, Teams, and OneNote.) Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but you can request them to be added.</span></span> <span data-ttu-id="f6c06-111">有关这些应用详细信息，请参阅在Microsoft Project[设备上Visio Microsoft Microsoft 托管桌面安装](../get-started/project-visio.md)。</span><span class="sxs-lookup"><span data-stu-id="f6c06-111">For more information about these apps, see [Install Microsoft Project or Microsoft Visio on Microsoft Managed Desktop devices](../get-started/project-visio.md).</span></span>

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a><span data-ttu-id="f6c06-112">Microsoft 为支持我们提供的应用而做哪些工作</span><span class="sxs-lookup"><span data-stu-id="f6c06-112">What Microsoft does to support the apps we provide</span></span>

<span data-ttu-id="f6c06-113">Microsoft 将为包含的应用的部署、更新和支持提供Microsoft 365 企业应用版服务。</span><span class="sxs-lookup"><span data-stu-id="f6c06-113">Microsoft will provide full service for the deployment, update, and support for the included Microsoft 365 Apps for enterprise apps.</span></span> <span data-ttu-id="f6c06-114">默认情况下不包含 Microsoft Project 和 Visio 即点即用版本，但Microsoft 托管桌面 将提供部署组，让 IT 管理员能够管理许可证并为组织适当地部署这些应用程序。</span><span class="sxs-lookup"><span data-stu-id="f6c06-114">Click-to-Run versions of Microsoft Project and Visio are *not* included by default, but Microsoft Managed Desktop will provide deployment groups allowing your IT administrator to manage licenses and deploy these applications appropriately for your organization.</span></span> <span data-ttu-id="f6c06-115">Microsoft 将支持这些应用程序的用户通过Microsoft 托管桌面支持渠道。</span><span class="sxs-lookup"><span data-stu-id="f6c06-115">Microsoft will support users of these applications through the Microsoft Managed Desktop support channels.</span></span>

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a><span data-ttu-id="f6c06-116">需要执行哪些工作来支持我们提供的应用</span><span class="sxs-lookup"><span data-stu-id="f6c06-116">What you need to do to support the apps we provide</span></span>

<span data-ttu-id="f6c06-117">对于这些应用，仍需要执行某些操作：</span><span class="sxs-lookup"><span data-stu-id="f6c06-117">There are still certain things you need to do with these apps:</span></span>

- <span data-ttu-id="f6c06-118">**分配** 许可证 - 你负责获取适当的许可证并将其分配给用户进行Microsoft 365 企业应用版。</span><span class="sxs-lookup"><span data-stu-id="f6c06-118">**Assign licenses** - You are responsible for obtaining and assigning the appropriate licenses to users for Microsoft 365 Apps for enterprise.</span></span>
- <span data-ttu-id="f6c06-119">**将用户添加到安全组**- 如果使用 Microsoft Project 或 Visio，则 IT 管理员必须将这些用户添加到相应的部署组。</span><span class="sxs-lookup"><span data-stu-id="f6c06-119">**Add users to security groups** - If you're using Microsoft Project or Visio, your IT administrator must add those users to the appropriate deployment groups.</span></span> <span data-ttu-id="f6c06-120">IT 管理员还负责在用户离开公司时回收这些用户的许可证。</span><span class="sxs-lookup"><span data-stu-id="f6c06-120">IT administrators are also responsible for reclaiming licenses from those users if they leave the company.</span></span>
- <span data-ttu-id="f6c06-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 企业应用版 apps， deploy them centrally like any other Windows 32 app.</span><span class="sxs-lookup"><span data-stu-id="f6c06-121">**Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 Apps for enterprise apps, deploy them centrally like any other Windows 32 app.</span></span> 

## <a name="apps-you-provide"></a><span data-ttu-id="f6c06-122">你提供的应用</span><span class="sxs-lookup"><span data-stu-id="f6c06-122">Apps you provide</span></span>

<span data-ttu-id="f6c06-123">你可能拥有业务操作所需的其他应用。</span><span class="sxs-lookup"><span data-stu-id="f6c06-123">You probably have other apps you need for your business operations.</span></span> <span data-ttu-id="f6c06-124">这些应用只能Microsoft 托管桌面部署管道部署到Microsoft Intune设备。</span><span class="sxs-lookup"><span data-stu-id="f6c06-124">These apps can only be deployed to Microsoft Managed Desktop devices by using Microsoft Intune’s deployment pipeline.</span></span> <span data-ttu-id="f6c06-125">有关应用程序部署详细信息，请按照将应用部署到Microsoft 托管桌面[中的步骤操作](../get-started/deploy-apps.md)。</span><span class="sxs-lookup"><span data-stu-id="f6c06-125">For more information about application deployment follow the steps in [Deploy apps to Microsoft Managed Desktop devices](../get-started/deploy-apps.md).</span></span>

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a><span data-ttu-id="f6c06-126">准备自己的应用以包含在Microsoft 托管桌面</span><span class="sxs-lookup"><span data-stu-id="f6c06-126">Preparing your own apps for inclusion in Microsoft Managed Desktop</span></span>
<span data-ttu-id="f6c06-127">查看应用，检查：</span><span class="sxs-lookup"><span data-stu-id="f6c06-127">Review your apps, checking:</span></span>

- <span data-ttu-id="f6c06-128">任何应用均不受禁止或具有受限行为，如Microsoft 托管桌面[要求中所述](../service-description/mmd-app-requirements.md)。</span><span class="sxs-lookup"><span data-stu-id="f6c06-128">None of the apps are prohibited or have restricted behavior, as described in [Microsoft Managed Desktop app requirements](../service-description/mmd-app-requirements.md).</span></span>
- <span data-ttu-id="f6c06-129">应用必须已准备好通过管理Microsoft Intune。</span><span class="sxs-lookup"><span data-stu-id="f6c06-129">Apps must be ready for management by Microsoft Intune.</span></span> <span data-ttu-id="f6c06-130">有关本主题的详细信息，请参阅使用[Windows 10 部署应用](/intune/apps-windows-10-app-deploy)和Microsoft Intune[应用Microsoft Intune。](/intune/apps-add)</span><span class="sxs-lookup"><span data-stu-id="f6c06-130">For more about this topic, see [Windows 10 app deployment using Microsoft Intune](/intune/apps-windows-10-app-deploy) and [Add apps to Microsoft Intune](/intune/apps-add).</span></span>
- <span data-ttu-id="f6c06-131">其他预打包要求，如提供许可证密钥、与许可条款的协议以及预先设置服务器连接。</span><span class="sxs-lookup"><span data-stu-id="f6c06-131">Other pre-packaging requirements such as providing license keys, agreement with license terms, and pre-setting server connections.</span></span>

## <a name="steps-to-get-ready"></a><span data-ttu-id="f6c06-132">准备步骤</span><span class="sxs-lookup"><span data-stu-id="f6c06-132">Steps to get ready</span></span>

1. <span data-ttu-id="f6c06-133">Review [Prerequisites for Microsoft 托管桌面](prerequisites.md).</span><span class="sxs-lookup"><span data-stu-id="f6c06-133">Review [Prerequisites for Microsoft Managed Desktop](prerequisites.md).</span></span>
2. <span data-ttu-id="f6c06-134">使用 [准备情况评估工具](readiness-assessment-tool.md)。</span><span class="sxs-lookup"><span data-stu-id="f6c06-134">Use [Readiness assessment tools](readiness-assessment-tool.md).</span></span>
3. [<span data-ttu-id="f6c06-135">来宾帐户的先决条件</span><span class="sxs-lookup"><span data-stu-id="f6c06-135">Prerequisites for guest accounts</span></span>](guest-accounts.md)
4. [<span data-ttu-id="f6c06-136">Microsoft 托管桌面的网络配置</span><span class="sxs-lookup"><span data-stu-id="f6c06-136">Network configuration for Microsoft Managed Desktop</span></span>](network.md)
5. [<span data-ttu-id="f6c06-137">为 Microsoft 托管桌面准备证书和网络配置文件</span><span class="sxs-lookup"><span data-stu-id="f6c06-137">Prepare certificates and network profiles for Microsoft Managed Desktop</span></span>](certs-wifi-lan.md)
6. [<span data-ttu-id="f6c06-138">为 Microsoft 托管桌面准备本地资源访问权限</span><span class="sxs-lookup"><span data-stu-id="f6c06-138">Prepare on-premises resources access for Microsoft Managed Desktop</span></span>](authentication.md)
7. <span data-ttu-id="f6c06-139">[Microsoft 托管桌面 (](apps.md)本文) </span><span class="sxs-lookup"><span data-stu-id="f6c06-139">[Apps in Microsoft Managed Desktop](apps.md) (This article)</span></span>
8. [<span data-ttu-id="f6c06-140">为 Microsoft 托管桌面准备映射的驱动器</span><span class="sxs-lookup"><span data-stu-id="f6c06-140">Prepare mapped drives for Microsoft Managed Desktop</span></span>](mapped-drives.md)
9. [<span data-ttu-id="f6c06-141">为 Microsoft 托管桌面准备打印资源</span><span class="sxs-lookup"><span data-stu-id="f6c06-141">Prepare printing resources for Microsoft Managed Desktop</span></span>](printing.md)
