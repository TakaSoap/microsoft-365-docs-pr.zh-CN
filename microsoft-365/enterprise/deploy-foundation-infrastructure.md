---
title: Microsoft 365 企业版底层基础结构
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 08/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解组织中部署 Microsoft 365 企业版底层基础结构（也称为核心部署）的主要阶段。
ms.openlocfilehash: 0b54225d3ce9043564788e28ddd88426dae611e9
ms.sourcegitcommit: 86dba00cd786ac8ea761cdfcd85dfbd33e64d088
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/12/2019
ms.locfileid: "36297912"
---
# <a name="microsoft-365-enterprise-foundation-infrastructure"></a><span data-ttu-id="615f7-103">Microsoft 365 企业版底层基础结构</span><span class="sxs-lookup"><span data-stu-id="615f7-103">Microsoft 365 Enterprise foundation infrastructure</span></span>

<span data-ttu-id="615f7-104">如果你是自行端到端部署 Microsoft 365 企业版，则应首先奠定坚实的基础，在此基础上，应用程序和服务可以在安全的环境中激发创造力和提高团队协作。</span><span class="sxs-lookup"><span data-stu-id="615f7-104">If you're doing the end-to-end deployment of Microsoft 365 Enterprise yourself, you should first build a firm foundation upon which applications and services can unlock creativity and teamwork in a secure environment.</span></span> <span data-ttu-id="615f7-105">该底层有时称为*核心部署*。</span><span class="sxs-lookup"><span data-stu-id="615f7-105">This foundation is sometimes referred to as the core deployment.</span></span>

<span data-ttu-id="615f7-106">对于为部署定义的端到端路径，你可以使用这些阶段来规划和部署 Microsoft 365 企业版的底层基础结构：</span><span class="sxs-lookup"><span data-stu-id="615f7-106">For a defined end-to-end path for deployment, you can use these phases to plan for and deploy the foundation infrastructure of Microsoft 365 Enterprise:</span></span>

| | <span data-ttu-id="615f7-107">阶段</span><span class="sxs-lookup"><span data-stu-id="615f7-107">Phase</span></span> | <span data-ttu-id="615f7-108">结果</span><span class="sxs-lookup"><span data-stu-id="615f7-108">Results</span></span> |
|:-------|:-----|:-----|
|![](./media/deploy-foundation-infrastructure/networking_icon-small.png)|[<span data-ttu-id="615f7-109">阶段 1：网络</span><span class="sxs-lookup"><span data-stu-id="615f7-109">Phase 1: Networking</span></span>](networking-infrastructure.md)| <span data-ttu-id="615f7-110">网络已经过优化，以便访问 Microsoft 365 基于云的服务。</span><span class="sxs-lookup"><span data-stu-id="615f7-110">Your network is optimized for access to Microsoft 365's cloud-based services.</span></span> |
|![](./media/deploy-foundation-infrastructure/identity_icon-small.png)|[<span data-ttu-id="615f7-111">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="615f7-111">Phase 2: Identity</span></span>](identity-infrastructure.md)| <span data-ttu-id="615f7-112">管理员帐户受到保护，用户和组经过同步，并且采用强用户身份验证。</span><span class="sxs-lookup"><span data-stu-id="615f7-112">Your admin accounts are protected, your users and groups are synchronized, and your user authentication is strong.</span></span> |
|![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)|[<span data-ttu-id="615f7-113">阶段 3：Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="615f7-113">Phase 3: Windows 10 Enterprise</span></span>](windows10-infrastructure.md)| <span data-ttu-id="615f7-114">现有基于 Windows 的计算机可以升级至 Windows 10 企业版，并且新设备已安装了 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="615f7-114">Your existing Windows-based computers can upgrade to Windows 10 Enterprise and new devices are installed with Windows 10 Enterprise.</span></span> |
|![](./media/deploy-foundation-infrastructure/O365proplus_icon-small.png)|[<span data-ttu-id="615f7-115">阶段 4：Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="615f7-115">Phase 4: Office 365 ProPlus</span></span>](office365proplus-infrastructure.md)| <span data-ttu-id="615f7-116">现有 Microsoft Office 用户可以升级到 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="615f7-116">Your existing users of Microsoft Office can upgrade to Office 365 ProPlus.</span></span> |
|![](./media/deploy-foundation-infrastructure/mobiledevicemgmt_icon-small.png)|[<span data-ttu-id="615f7-117">阶段 5：移动设备管理</span><span class="sxs-lookup"><span data-stu-id="615f7-117">Phase 5: Mobile device management</span></span>](mobility-infrastructure.md)| <span data-ttu-id="615f7-118">可以注册和管理你的设备。</span><span class="sxs-lookup"><span data-stu-id="615f7-118">Your devices can be enrolled and managed.</span></span> |
|![](./media/deploy-foundation-infrastructure/infoprotection_icon-small.png)|[<span data-ttu-id="615f7-119">阶段 6：信息保护</span><span class="sxs-lookup"><span data-stu-id="615f7-119">Phase 6: Information protection</span></span>](infoprotect-infrastructure.md)| <span data-ttu-id="615f7-120">标签已准备好保护文档并且 Office 365 安全功能已启用。</span><span class="sxs-lookup"><span data-stu-id="615f7-120">Your labels are ready to protect documents and Office 365 security features are enabled.</span></span> |

<span data-ttu-id="615f7-121">将从最基本的阶段（网络和标识）开始，然后创建基础结构设置和组层，以：</span><span class="sxs-lookup"><span data-stu-id="615f7-121">The phases start with the most foundational (networking and identity), and then create layers of infrastructure settings and groups to:</span></span>

- <span data-ttu-id="615f7-122">在设备上安装最新、最安全的 Windows 版本，并保证其处于最新状态。</span><span class="sxs-lookup"><span data-stu-id="615f7-122">Install the most current and secure version of Windows on your devices.</span></span>
- <span data-ttu-id="615f7-123">在设备上安装最新的 Microsoft Office 版本，并保证其处于最新状态。</span><span class="sxs-lookup"><span data-stu-id="615f7-123">Install the most current version of Microsoft Office on your devices and keep it current.</span></span>
- <span data-ttu-id="615f7-124">管理组织的设备及其对应用的访问。</span><span class="sxs-lookup"><span data-stu-id="615f7-124">Manage your organization's devices and their access to apps.</span></span>
- <span data-ttu-id="615f7-125">保护这些设备和云中的信息。</span><span class="sxs-lookup"><span data-stu-id="615f7-125">Protect the information on those devices and in the cloud.</span></span>

<span data-ttu-id="615f7-126">但是，你可以灵活地配置和部署阶段中的各个阶段和步骤，以满足你的 IT 资源和业务需求。</span><span class="sxs-lookup"><span data-stu-id="615f7-126">However, you have the flexibility of configuring and rolling out the phases or steps within phases to fit your IT resources and business needs.</span></span>

- <span data-ttu-id="615f7-127">**如果你是较小或较新的组织**，请根据需要按照各个阶段操作，以便有条不紊地构建基础结构。</span><span class="sxs-lookup"><span data-stu-id="615f7-127">**If you are a smaller or newer organization**, follow the phases as needed to methodically build out your infrastructure.</span></span> <span data-ttu-id="615f7-128">有关针对非企业的简化部署，请单击[此处](deploy-foundation-infrastructure-non-enterprises.md)。</span><span class="sxs-lookup"><span data-stu-id="615f7-128">For a simplified deployment for non-enterprises, click [here](deploy-foundation-infrastructure-non-enterprises.md).</span></span>

-  <span data-ttu-id="615f7-129">**如果你是企业组织**，请将阶段视作 IT 基础架构的层，而不是定义的路径，并确定如何更好地工作，以最终满足组织中每个层的要求。</span><span class="sxs-lookup"><span data-stu-id="615f7-129">**If you are an enterprise organization**, view the phases as layers of IT infrastructure, rather than a defined path, and determine how to best work toward eventual adherence to the requirements for each layer across your organization.</span></span>

<span data-ttu-id="615f7-130">在每个阶段结束时，你可以检查器退出条件，其中包括必须满足的必要条件以及可以考虑的可选条件。</span><span class="sxs-lookup"><span data-stu-id="615f7-130">At the end of each phase, you should examine its exit criteria, which include required conditions that you must meet and optional conditions to consider.</span></span> <span data-ttu-id="615f7-131">每个阶段的退出条件可确保本地和云基础结构以及相应的端到端配置满足 Microsoft 365 企业版部署的要求。</span><span class="sxs-lookup"><span data-stu-id="615f7-131">Exit criteria for each phase ensures that your on-premises and cloud infrastructure and resulting end-to-end configuration meet the requirements for a Microsoft 365 Enterprise deployment.</span></span>

<span data-ttu-id="615f7-132">如需查看内容的组织方式，请观看此短片。</span><span class="sxs-lookup"><span data-stu-id="615f7-132">To see how the content is structured, watch this short video.</span></span>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE23VRG]

<span data-ttu-id="615f7-133">以下是 Microsoft 365 企业版整体部署指南中的底层基础结构：</span><span class="sxs-lookup"><span data-stu-id="615f7-133">Here's the foundation infrastructure in the overall Microsoft 365 Enterprise deployment guide:</span></span>

![](./media/deploy-foundation-infrastructure/m365-deploy-content-arch-foundation.png)

## <a name="at-a-glance"></a><span data-ttu-id="615f7-134">概览</span><span class="sxs-lookup"><span data-stu-id="615f7-134">At-a-glance</span></span>

<span data-ttu-id="615f7-135">[Microsoft 365 企业版底层基础结构海报](http://aka.ms/m365efoundinfraposter)是一个可查看各阶段相关情况的中心位置：</span><span class="sxs-lookup"><span data-stu-id="615f7-135">The [Microsoft 365 Enterprise foundation infrastructure poster](http://aka.ms/m365efoundinfraposter) is a central location for you to view, for each phase:</span></span>

- <span data-ttu-id="615f7-136">所处阶段对管理员和用户的整体目标</span><span class="sxs-lookup"><span data-stu-id="615f7-136">The overall goals of the phase for administrators and users</span></span>
- <span data-ttu-id="615f7-137">服务、功能和工具</span><span class="sxs-lookup"><span data-stu-id="615f7-137">The services, features, and tools</span></span>
- <span data-ttu-id="615f7-138">针对规划的关键设计决策</span><span class="sxs-lookup"><span data-stu-id="615f7-138">The key design decisions for planning</span></span>
- <span data-ttu-id="615f7-139">配置结果</span><span class="sxs-lookup"><span data-stu-id="615f7-139">The configuration results</span></span>
- <span data-ttu-id="615f7-140">新用户的载入进度</span><span class="sxs-lookup"><span data-stu-id="615f7-140">The process for onboarding a new user</span></span>
- <span data-ttu-id="615f7-141">监视和更新方式</span><span class="sxs-lookup"><span data-stu-id="615f7-141">How to monitor and update</span></span>

![](./media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.png)

<span data-ttu-id="615f7-142">要下载海报副本，请单击[此处](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf)。</span><span class="sxs-lookup"><span data-stu-id="615f7-142">To download a copy of the poster, click [here](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/deploy-foundation-infrastructure/Microsoft365EnterpriseFoundInfra.pdf).</span></span>


## <a name="infrastructure-configuration-vs-user-rollout"></a><span data-ttu-id="615f7-143">基础结构配置与用户部署</span><span class="sxs-lookup"><span data-stu-id="615f7-143">Infrastructure configuration vs. user rollout</span></span>

<span data-ttu-id="615f7-144">底层基础结构是一组经过配置的软件和服务，如果针对某一用户将它们组合到一起，可以充分利用 Microsoft 365 企业版具有的全部功能和保护。</span><span class="sxs-lookup"><span data-stu-id="615f7-144">The foundation infrastructure is a set of configured software and services that, when combined together for a user, allow them to take advantage of the entire spectrum of capabilities and protections that Microsoft 365 Enterprise offers.</span></span> <span data-ttu-id="615f7-145">端到端部署旅程的最终目标是将此基础结构应用于所有用户及其基于 Windows 的设备。</span><span class="sxs-lookup"><span data-stu-id="615f7-145">The ultimate destination of your end-to-end deployment journey is to have this infrastructure apply to all of your users and their Windows-based devices.</span></span> 

<span data-ttu-id="615f7-146">但是，必须注意的是，Microsoft 365 企业版底层基础结构与为用户部署软件和服务是不相关的。</span><span class="sxs-lookup"><span data-stu-id="615f7-146">However, it is important to note that the Microsoft 365 Enterprise foundation infrastructure is independent of the rollout of software and services to your users.</span></span> <span data-ttu-id="615f7-147">***你可以配置底层基础结构层，而无需将这些曾部署到所有用户中。***</span><span class="sxs-lookup"><span data-stu-id="615f7-147">***You can configure the layers of the foundation infrastructure without having to roll out those layers to all of your users.***</span></span>

<span data-ttu-id="615f7-148">可在将元素部署到组织办公室、区域或部门的众多用户之前配置、测试和试用底层基础结构的元素。</span><span class="sxs-lookup"><span data-stu-id="615f7-148">Therefore, it is possible to configure, test, and pilot elements of the foundation infrastructure well ahead of the rollout of those elements to the multitude of your users in the offices, regions, or divisions of your organization.</span></span>

<span data-ttu-id="615f7-149">例如，你可以为以下对象创建设置：</span><span class="sxs-lookup"><span data-stu-id="615f7-149">For example, you create the settings for:</span></span>

| <span data-ttu-id="615f7-150">阶段</span><span class="sxs-lookup"><span data-stu-id="615f7-150">Phase</span></span> | <span data-ttu-id="615f7-151">结果</span><span class="sxs-lookup"><span data-stu-id="615f7-151">Results</span></span> |
|:-------|:-----|
| <span data-ttu-id="615f7-152">标识</span><span class="sxs-lookup"><span data-stu-id="615f7-152">Identity</span></span> | <span data-ttu-id="615f7-153">帐户同步和适用于基于条件访问策略的组。</span><span class="sxs-lookup"><span data-stu-id="615f7-153">Account synchronization and groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="615f7-154">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="615f7-154">Windows 10 Enterprise</span></span> | <span data-ttu-id="615f7-155">将运行 Windows 7 或 Windows 8.1 的计算机自动升级到相应的 Windows 10 企业版的组。</span><span class="sxs-lookup"><span data-stu-id="615f7-155">Groups to automatically upgrade computers running Windows 7 or Windows 8.1 to Windows 10 Enterprise in place.</span></span> |
| <span data-ttu-id="615f7-156">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="615f7-156">Office 365 ProPlus</span></span> | <span data-ttu-id="615f7-157">为使用 Office 2010、Office 2013 或 Office 2016 的用户自动部署 Office 365 的组。</span><span class="sxs-lookup"><span data-stu-id="615f7-157">Groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="615f7-158">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="615f7-158">Mobile device management</span></span> | <span data-ttu-id="615f7-159">适合于设备注册和基于设备的条件访问策略的组。</span><span class="sxs-lookup"><span data-stu-id="615f7-159">Groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="615f7-160">信息保护</span><span class="sxs-lookup"><span data-stu-id="615f7-160">Information protection</span></span> | <span data-ttu-id="615f7-161">Office 365 敏感度和 Azure 信息保护标签和组。</span><span class="sxs-lookup"><span data-stu-id="615f7-161">Office 365 and Azure Information Protection labels and groups.</span></span> |

<span data-ttu-id="615f7-162">准备好为用户部署此基础结构的元素时，你可以：</span><span class="sxs-lookup"><span data-stu-id="615f7-162">When you are ready to rollout elements of this infrastructure to users, you:</span></span>

| <span data-ttu-id="615f7-163">阶段</span><span class="sxs-lookup"><span data-stu-id="615f7-163">Phase</span></span> | <span data-ttu-id="615f7-164">部署操作</span><span class="sxs-lookup"><span data-stu-id="615f7-164">Rollout action</span></span> |
|:-------|:-----|
| <span data-ttu-id="615f7-165">标识</span><span class="sxs-lookup"><span data-stu-id="615f7-165">Identity</span></span> | <span data-ttu-id="615f7-166">将用户帐户添加到基于标识的条件访问策略组。</span><span class="sxs-lookup"><span data-stu-id="615f7-166">Add user accounts to the groups for identity-based conditional access policies.</span></span> |
| <span data-ttu-id="615f7-167">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="615f7-167">Windows 10 Enterprise</span></span> | <span data-ttu-id="615f7-168">将帐户添加到组，以便为使用 Windows 7 或 Windows 8.1 的用户自动部署 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="615f7-168">Add accounts to the groups to automatically deploy Windows 10 Enterprise in place for users with Windows 7 or Windows 8.1.</span></span> |
| <span data-ttu-id="615f7-169">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="615f7-169">Office 365 ProPlus</span></span> | <span data-ttu-id="615f7-170">将用户帐户添加到组，以便为使用 Office 2010、Office 2013 或 Office 2016 的用户自动部署 Office 365 的组。</span><span class="sxs-lookup"><span data-stu-id="615f7-170">Add user accounts to the groups to automatically deploy Office 365 ProPlus for users with Office 2010, Office 2013, or Office 2016.</span></span> |
| <span data-ttu-id="615f7-171">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="615f7-171">Mobile device management</span></span> | <span data-ttu-id="615f7-172">将帐户添加到适合于设备注册和基于设备的条件访问策略的组。</span><span class="sxs-lookup"><span data-stu-id="615f7-172">Add accounts to the groups for device enrollment and device-based conditional access policies.</span></span> |
| <span data-ttu-id="615f7-173">信息保护</span><span class="sxs-lookup"><span data-stu-id="615f7-173">Information protection</span></span> | <span data-ttu-id="615f7-174">将用户帐户添加到信息保护标签组。</span><span class="sxs-lookup"><span data-stu-id="615f7-174">Add user accounts to the groups for Information Protection labels.</span></span> |

<span data-ttu-id="615f7-175">底层基础结构的阶段或元素完成、测试和试用之后，你可以为用户部署已安装的软件（例如 Windows 10 企业版和 Office 365 专业增强版）以及基于云的服务和保护（如设备注册和条件访问策略），以最适合你的业务目标和 IT 资源。</span><span class="sxs-lookup"><span data-stu-id="615f7-175">Once the foundation infrastructure is completed, tested, and piloted, you can roll out installed software, such as Windows 10 Enterprise and Office 365 ProPlus, and cloud-based services and protections, such as device enrollment and conditional access policies, to your users in the manner that best fits your business goals and IT resources.</span></span>

## <a name="deployment-and-project-management-strategies"></a><span data-ttu-id="615f7-176">部署和项目管理策略</span><span class="sxs-lookup"><span data-stu-id="615f7-176">Deployment and project management strategies</span></span>

<span data-ttu-id="615f7-177">若要就如何为组织的试点用户和其他用户进对底层基础结构的不同阶段进行项目管理给出一些看法，请参阅[部署战略](deployment-strategies-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="615f7-177">To give you some ideas on how to approach the project management of the different phases of the foundation infrastructure for pilot users and the rest of your organization, see [deployment strategies](deployment-strategies-microsoft-365-enterprise.md).</span></span>

## <a name="deployment-for-non-enterprises"></a><span data-ttu-id="615f7-178">针对非企业的部署</span><span class="sxs-lookup"><span data-stu-id="615f7-178">Deployment for non-enterprises</span></span>

<span data-ttu-id="615f7-179">如果你的组织规模较小，而 Microsoft 365 商业版不适合你，则请查看[针对非企业的部署](deploy-foundation-infrastructure-non-enterprises.md)。</span><span class="sxs-lookup"><span data-stu-id="615f7-179">If your organization is smaller and Microsoft 365 Business is not suitable for you, see [deployment for non-enterprises](deploy-foundation-infrastructure-non-enterprises.md).</span></span>


## <a name="next-step"></a><span data-ttu-id="615f7-180">后续步骤</span><span class="sxs-lookup"><span data-stu-id="615f7-180">Next step</span></span>

| <span data-ttu-id="615f7-181">我当前的境况</span><span class="sxs-lookup"><span data-stu-id="615f7-181">Where I am</span></span> | <span data-ttu-id="615f7-182">我需要达成的目标</span><span class="sxs-lookup"><span data-stu-id="615f7-182">Where I need to go</span></span> |
|:-------|:-----|
| <span data-ttu-id="615f7-183">我现在有针对 Office 365、企业移动性 + 安全性 (EMS) 或 Windows 10 企业版的基础结构。</span><span class="sxs-lookup"><span data-stu-id="615f7-183">I have existing infrastructure for Office 365, Enterprise Mobility + Security (EMS), or Windows 10 Enterprise:</span></span> | <span data-ttu-id="615f7-184">请首先[用基础结构进行部署](deploy-with-existing-infrastructure.md)按照步骤了解各阶段的退出条件。</span><span class="sxs-lookup"><span data-stu-id="615f7-184">Start with [Deploy with existing infrastructure](deploy-with-existing-infrastructure.md), which  steps you through the exit criteria for each phase.</span></span> |
| <span data-ttu-id="615f7-185">我要作为企业从头开始</span><span class="sxs-lookup"><span data-stu-id="615f7-185">I'm starting from scratch as an enterprise</span></span> | <span data-ttu-id="615f7-186">通过[阶段 1：网络](networking-infrastructure.md)开启你的端到端部署旅程。</span><span class="sxs-lookup"><span data-stu-id="615f7-186">Begin your end-to-end deployment journey with [Phase 1: Networking](networking-infrastructure.md).</span></span> |
| <span data-ttu-id="615f7-187">我要以非企业的身份从头开始</span><span class="sxs-lookup"><span data-stu-id="615f7-187">I'm starting from scratch as a non-enterprise</span></span> | <span data-ttu-id="615f7-188">通过[针对非企业的部署](deploy-foundation-infrastructure-non-enterprises.md)开启你的端到端部署旅程。</span><span class="sxs-lookup"><span data-stu-id="615f7-188">Begin your end-to-end deployment journey with [Deployment for non-enterprises](deploy-foundation-infrastructure-non-enterprises.md).</span></span> |
