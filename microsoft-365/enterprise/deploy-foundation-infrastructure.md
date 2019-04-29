---
title: Microsoft 365 企业版底层基础结构
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 03/05/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解组织中部署 Microsoft 365 企业版底层基础结构（也称为核心部署）的主要阶段。
ms.openlocfilehash: e6b8a71f59f20633e323c71e931b930198bc4deb
ms.sourcegitcommit: 3b2d3e2b38c4860db977e73dda119a465c669fa4
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2019
ms.locfileid: "33400046"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="a3a3f-103">Microsoft 365 企业版底层基础结构</span><span class="sxs-lookup"><span data-stu-id="a3a3f-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="a3a3f-104">如果你是自行端到端部署 Microsoft 365 企业版，则应首先奠定坚实的基础，在此基础上，应用程序和服务可以在安全的环境中激发创造力和提高团队协作。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-104">If you're doing the end-to-end deployment of Microsoft 365 Enterprise yourself, you should first build a firm foundation upon which applications and services can unlock creativity and teamwork in a secure environment.</span></span> <span data-ttu-id="a3a3f-105">该底层有时称为核心部署。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-105">This foundation is sometimes referred to as the core deployment.</span></span>

<span data-ttu-id="a3a3f-106">对于为部署定义的端到端路径，你可以使用这些阶段来规划和部署 Microsoft 365 企业版的底层基础结构：</span><span class="sxs-lookup"><span data-stu-id="a3a3f-106">For a defined end-to-end path for deployment, you can use these phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise:</span></span>

| | <span data-ttu-id="a3a3f-107">阶段</span><span class="sxs-lookup"><span data-stu-id="a3a3f-107">Phase</span></span> | <span data-ttu-id="a3a3f-108">结果</span><span class="sxs-lookup"><span data-stu-id="a3a3f-108">Results</span></span> |
|:-------|:-----|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="a3a3f-109">阶段 1：网络</span><span class="sxs-lookup"><span data-stu-id="a3a3f-109">Phase 1: Networking</span></span>](networking-infrastructure.md)| <span data-ttu-id="a3a3f-110">网络已经过优化，以便访问 Microsoft 365 基于云的服务。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-110">Your network is optimized for access to Microsoft 365's cloud-based services.</span></span> |
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="a3a3f-111">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="a3a3f-111">Phase 2: Identity</span></span>](identity-infrastructure.md)| <span data-ttu-id="a3a3f-112">管理员帐户受到保护，用户和组经过同步，并且采用强用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-112">Your admin accounts are protected, your users and groups are synchronized, and your user authentication is strong.</span></span> |
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="a3a3f-113">阶段 3：Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="a3a3f-113">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)| <span data-ttu-id="a3a3f-114">现有基于 Windows 的计算机可以升级至 Windows 10 企业版，并且新设备已安装了 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-114">Your existing Windows-based computers can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="a3a3f-115">阶段 4：Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="a3a3f-115">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)| <span data-ttu-id="a3a3f-116">现有 Microsoft Office 用户可以升级到 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-116">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="a3a3f-117">阶段 5：移动设备管理</span><span class="sxs-lookup"><span data-stu-id="a3a3f-117">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)| <span data-ttu-id="a3a3f-118">可以注册和管理你的设备。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-118">Your devices can be enrolled and managed.</span></span> |
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="a3a3f-119">阶段 6：信息保护</span><span class="sxs-lookup"><span data-stu-id="a3a3f-119">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)| <span data-ttu-id="a3a3f-120">标签已准备好保护文档并且 Office 365 安全功能已启用。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-120">Your labels are ready to protect documents and Office 365 security features are enabled.</span></span> |

<span data-ttu-id="a3a3f-121">将从最基本的阶段（网络和标识）开始，然后创建基础结构设置和组层，以：</span><span class="sxs-lookup"><span data-stu-id="a3a3f-121">The phases start with the most foundational (networking and identity), and then create layers of infrastructure settings and groups to:</span></span>

- <span data-ttu-id="a3a3f-122">在设备上安装最新、最安全的 Windows 版本。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-122">Install the most current and secure version of Windows on your devices.</span></span>
- <span data-ttu-id="a3a3f-123">在设备上安装最新的 Office 版本。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-123">Install the most current version of Office on your devices.</span></span>
- <span data-ttu-id="a3a3f-124">管理组织的设备。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-124">Manage your organization's devices.</span></span>
- <span data-ttu-id="a3a3f-125">保护这些设备和云中的信息。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-125">Protect the information on those devices and in the cloud.</span></span>

<span data-ttu-id="a3a3f-126">但是，你可以灵活地配置和部署阶段中的各个阶段和步骤，以满足你的 IT 资源和业务需求。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-126">However, you have the flexibility of configuring and rolling out the phases or steps within phases to fit your IT resources and business needs.</span></span>

- <span data-ttu-id="a3a3f-127">**如果你是较小或较新的组织**，请根据需要按照各个阶段操作，以便有条不紊地构建基础结构。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-127">**If you are a smaller or newer organization**, follow the phases as needed to methodically build out your infrastructure.</span></span>

-  <span data-ttu-id="a3a3f-128">**如果你是企业组织**，请将阶段视作 IT 基础架构的层，而不是定义的路径，并确定如何更好地工作，以最终满足组织中每个层的要求。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-128">**If you are an enterprise organization**, view the phases as layers of IT infrastructure, rather than a defined path, and determine how to best work toward eventual adherence to the requirements for each layer across your organization.</span></span>

<span data-ttu-id="a3a3f-129">在每个阶段结束时，你可以检查器退出条件，其中包括必须满足的必要条件以及可以考虑的可选条件。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-129">At the end of each phase, you should examine its exit criteria, which include required conditions that you must meet and optional conditions to consider.</span></span> <span data-ttu-id="a3a3f-130">每个阶段的退出条件可确保本地和云基础结构以及相应的端到端配置满足 Microsoft 365 企业版部署的要求。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-130">Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="a3a3f-131">如需查看内容的组织方式，请观看此短片。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-131">To see how the content is structured, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="a3a3f-132">以下是 Microsoft 365 企业版整体部署指南中的底层基础结构：</span><span class="sxs-lookup"><span data-stu-id="a3a3f-132">Here's the foundation infrastructure in the overall Microsoft 365 Enterprise deployment guide:</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="infrastructure-configuration-vs-user-rollout"></a><span data-ttu-id="a3a3f-133">基础结构配置与用户部署</span><span class="sxs-lookup"><span data-stu-id="a3a3f-133">Infrastructure configuration vs. user rollout</span></span>

<span data-ttu-id="a3a3f-134">底层基础结构是一组经过配置的软件和服务，如果针对某一用户将它们组合到一起，可以充分利用 Microsoft 365 企业版具有的全部功能和保护。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-134">The foundation infrastructure is a set of configured software and services that, when combined together for a user, allow them to take advantage of the entire spectrum of capabilities and protections that Microsoft 365 Enterprise offers.</span></span> <span data-ttu-id="a3a3f-135">端到端部署旅程的最终目标是将此基础结构应用于所有用户及其基于 Windows 的设备。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-135">The ultimate destination of your end-to-end deployment journey is to have this infrastructure apply to all of your users and their Windows-based devices.</span></span> 

<span data-ttu-id="a3a3f-136">但是，必须注意的是，Microsoft 365 企业版底层基础结构与为用户部署软件和服务是不相关的。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-136">However, it is important to note that the Microsoft 365 Enterprise foundation infrastructure is independent of the rollout of software and services to your users.</span></span> <span data-ttu-id="a3a3f-137">***你可以配置底层基础结构层，而无需将这些曾部署到所有用户中。***</span><span class="sxs-lookup"><span data-stu-id="a3a3f-137">***You can configure the layers of the foundation infrastructure without having to roll out those layers to all of your users.***</span></span>

<span data-ttu-id="a3a3f-138">因此，可以在将元素部署到组织办公室、区域或部门的众多用户之前配置、测试和试用底层基础结构的元素。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-138">Therefore, it is possible to configure, test, and pilot elements of the foundation infrastructure well ahead of the rollout of those elements to the multitude of your users in the offices, regions, or divisions of your organization.</span></span>

<span data-ttu-id="a3a3f-139">例如，你可以为以下对象创建设置：</span><span class="sxs-lookup"><span data-stu-id="a3a3f-139">For example, you create the settings for:</span></span>

| <span data-ttu-id="a3a3f-140">阶段</span><span class="sxs-lookup"><span data-stu-id="a3a3f-140">Phase</span></span> | <span data-ttu-id="a3a3f-141">结果</span><span class="sxs-lookup"><span data-stu-id="a3a3f-141">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="a3a3f-142">标识</span><span class="sxs-lookup"><span data-stu-id="a3a3f-142">Identity</span></span> | <span data-ttu-id="a3a3f-143">帐户同步和适用于基于条件访问策略的组。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-143">Account synchronization and groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="a3a3f-144">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="a3a3f-144">Windows 10 Enterprise</span></span> | <span data-ttu-id="a3a3f-145">将运行 Windows 7 或 Windows 8.1 的计算机自动升级到相应的 Windows 10 企业版的组。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-145">Groups to automatically upgrade computers running Windows 7 or Windows 8.1 to Windows 10 Enterprise in place.</span></span> |
| <span data-ttu-id="a3a3f-146">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="a3a3f-146">Office 365 ProPlus</span></span> | <span data-ttu-id="a3a3f-147">为使用 Office 2010、Office 2013 或 Office 2016 的用户自动部署 Office 365 的组。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-147">Groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="a3a3f-148">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="a3a3f-148">Mobile device management</span></span> | <span data-ttu-id="a3a3f-149">适合于设备注册和基于设备的条件访问策略的组。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-149">Groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="a3a3f-150">信息保护</span><span class="sxs-lookup"><span data-stu-id="a3a3f-150">Information protection</span></span> | <span data-ttu-id="a3a3f-151">Office 365 和 Azure 信息保护标签和组。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-151">Office 365 and Azure Information Protection labels and groups.</span></span> |

<span data-ttu-id="a3a3f-152">准备好为用户部署此基础结构的元素时，你可以：</span><span class="sxs-lookup"><span data-stu-id="a3a3f-152">When you are ready to rollout elements of this infrastructure to users, you:</span></span>

| <span data-ttu-id="a3a3f-153">阶段</span><span class="sxs-lookup"><span data-stu-id="a3a3f-153">Phase</span></span> | <span data-ttu-id="a3a3f-154">部署操作</span><span class="sxs-lookup"><span data-stu-id="a3a3f-154">Rollout action</span></span> |
|:-------|:-----|
| <span data-ttu-id="a3a3f-155">标识</span><span class="sxs-lookup"><span data-stu-id="a3a3f-155">Identity</span></span> | <span data-ttu-id="a3a3f-156">将用户帐户添加到基于标识的条件访问策略组。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-156">Add user accounts to the groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="a3a3f-157">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="a3a3f-157">Windows 10 Enterprise</span></span> | <span data-ttu-id="a3a3f-158">将帐户添加到组，以便为使用 Windows 7 或 Windows 8.1 的用户自动部署 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-158">Add accounts to the groups to automatically deploy Windows 10 Enterprise in place for users with Windows 7 or Windows 8.1.</span></span> |
| <span data-ttu-id="a3a3f-159">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="a3a3f-159">Office 365 ProPlus</span></span> | <span data-ttu-id="a3a3f-160">将用户帐户添加到组，以便为使用 Office 2010、Office 2013 或 Office 2016 的用户自动部署 Office 365 的组。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-160">Add user accounts to the groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="a3a3f-161">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="a3a3f-161">Mobile device management</span></span> | <span data-ttu-id="a3a3f-162">将帐户添加到适合于设备注册和基于设备的条件访问策略的组。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-162">Add accounts to the groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="a3a3f-163">信息保护</span><span class="sxs-lookup"><span data-stu-id="a3a3f-163">Information protection</span></span> | <span data-ttu-id="a3a3f-164">将用户帐户添加到信息保护标签组。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-164">Add user accounts to the groups for Information Protection labels.</span></span> |

<span data-ttu-id="a3a3f-165">底层基础结构完成、测试和试用之后，你可以为用户部署已安装的软件（例如 Windows 10 企业版和 Office 365 专业增强版）以及基于云的服务和保护（如设备注册和条件访问策略），以最适合你的业务目标和 IT 资源。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-165">Once the foundation infrastructure is completed, tested, and piloted, you can roll out installed software, such as Windows 10 Enterprise and Office 365 ProPlus, and cloud-based services and protections, such as device enrollment and conditional access policies, to your users in the manner that best fits your business goals and IT resources.</span></span>

## <a name="deployment-and-project-management-strategies"></a><span data-ttu-id="a3a3f-166">部署和项目管理策略</span><span class="sxs-lookup"><span data-stu-id="a3a3f-166">Deployment and project management strategies</span></span>

<span data-ttu-id="a3a3f-167">若要就如何为组织的试点用户和其他用户进对底层基础结构的不同阶段进行项目管理给出一些看法，请参阅[部署战略](deployment-strategies-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-167">To give you some ideas on how to approach the project management of the different phases of the foundation infrastructure for pilot users and the rest of your organization, see [deployment strategies](deployment-strategies-microsoft-365-enterprise.md).</span></span>


## <a name="next-step"></a><span data-ttu-id="a3a3f-168">下一步骤</span><span class="sxs-lookup"><span data-stu-id="a3a3f-168">Next step</span></span>

- <span data-ttu-id="a3a3f-169">我已经有适用于 Office 365、企业移动性 + 安全性 (EMS) 或 Windows 10 企业版的基础结构：</span><span class="sxs-lookup"><span data-stu-id="a3a3f-169">I have existing infrastructure for Office 365, Enterprise Mobility + Security (EMS), or Windows 10 Enterprise:</span></span>
  - <span data-ttu-id="a3a3f-170">请参阅[利用现有基础结构部署](deploy-with-existing-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-170">See [Deploy with existing infrastructure](deploy-with-existing-infrastructure.md).</span></span> <span data-ttu-id="a3a3f-171">本文将指导你了解每个阶段的退出条件。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-171">This article steps you through the exit criteria for each phase.</span></span>
- <span data-ttu-id="a3a3f-172">我将从头开始：</span><span class="sxs-lookup"><span data-stu-id="a3a3f-172">I'm starting from scratch:</span></span> 
   - <span data-ttu-id="a3a3f-173">从[阶段 1：网络](networking-infrastructure.md)开始你的端到端部署旅程。</span><span class="sxs-lookup"><span data-stu-id="a3a3f-173">Begin your end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span>
