---
title: 部署 Microsoft 365 企业版
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 11/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解可用于在组织中部署 Microsoft 365 企业版的资源。
ms.openlocfilehash: ba0dd4d8af9f647b5368fdaa55837d3fe482fb55
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865937"
---
# <a name="deploy-microsoft-365-enterprise"></a><span data-ttu-id="b556d-103">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="b556d-103">Deploy Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b556d-104">Microsoft 365 企业版是 Office 365、企业移动性 + 安全性 (EMS) 和 Windows 10 企业版的组合：</span><span class="sxs-lookup"><span data-stu-id="b556d-104">Microsoft 365 Enterprise is a combination of Office 365, Enterprise Mobility + Security (EMS), and Windows 10 Enterprise that:</span></span> 

- <span data-ttu-id="b556d-105">具有智能安全性。</span><span class="sxs-lookup"><span data-stu-id="b556d-105">Has intelligent security.</span></span>
- <span data-ttu-id="b556d-106">集成式，更简单。</span><span class="sxs-lookup"><span data-stu-id="b556d-106">Is integrated for simplicity.</span></span>
- <span data-ttu-id="b556d-107">激发创造力。</span><span class="sxs-lookup"><span data-stu-id="b556d-107">Unlocks creativity.</span></span>
- <span data-ttu-id="b556d-108">专用于团队合作。</span><span class="sxs-lookup"><span data-stu-id="b556d-108">Is built for teamwork.</span></span>

<span data-ttu-id="b556d-p101">只获取这三个产品的许可证并不能实现这些优势，而要以特定方式部署产品及其功能。本组文档将引导你完成该部署以及这些产品及功能的正确且必需的配置。</span><span class="sxs-lookup"><span data-stu-id="b556d-p101">These benefits are not realized just by obtaining the licenses for these three products, but by deploying them and their features in a specific way. This documentation set guides you through that deployment and the correct and required configuration of these products and their features.</span></span>

<span data-ttu-id="b556d-111">部署 Microsoft 365 企业版的两个主要阶段：</span><span class="sxs-lookup"><span data-stu-id="b556d-111">There are two main phases to deploying Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="b556d-112">首先，为了简化管理，针对内置安全性和集成部署所需的[底层基础结构](deploy-foundation-infrastructure.md)，从而可更轻松地确保使用最新工作效率和安全增强功能更新客户端软件。</span><span class="sxs-lookup"><span data-stu-id="b556d-112">First, deploy the required [foundation infrastructure](deploy-foundation-infrastructure.md) for built-in security and integration for simplified management, which makes it easier to ensure your client software is updated with the latest productivity and security enhancements.</span></span>
2. <span data-ttu-id="b556d-113">接下来，在底层基础结构之上部署一组可选的[工作负载和方案](deploy-workloads.md)，以激发组织内的创造力和团队合作。</span><span class="sxs-lookup"><span data-stu-id="b556d-113">Next, deploy a set of optional [workloads and scenarios](deploy-workloads.md) on top of the foundation infrastructure, to unlock creativity and teamwork in your organization.</span></span>

<span data-ttu-id="b556d-114">下图展示了底层基础结构、工作负载和方案与整个部署内容路径之间的关系。</span><span class="sxs-lookup"><span data-stu-id="b556d-114">The following figure shows the relationship between the foundation infrastructure and the workloads and scenarios and your path through the content.</span></span>

![](./media/deploy-microsoft-365-enterprise/m365-deploy-content-arch.png)

<span data-ttu-id="b556d-115">为所有阶段的底层基础结构内置安全。</span><span class="sxs-lookup"><span data-stu-id="b556d-115">Security is built into all phases of the foundation infrastructure.</span></span>

## <a name="fasttrack"></a><span data-ttu-id="b556d-116">FastTrack</span><span class="sxs-lookup"><span data-stu-id="b556d-116">FastTrack</span></span>

<span data-ttu-id="b556d-p102">FastTrack 的优势在于持续且可重复（可用作订阅的一部分），由 Microsoft 工程师提供以帮助你按自己的节奏移动到云。此外，FastTrack 还可使你根据需要访问合格的合作伙伴以获取其他服务。目前为止，40,000 多个客户已启用此功能，FastTrack 可帮助最大化 ROI、加快部署，提高整个组织的采用率。请参阅[适用于 Microsoft 365 的 FastTrack](https://fasttrack.microsoft.com/microsoft365)。</span><span class="sxs-lookup"><span data-stu-id="b556d-p102">FastTrack is an ongoing and repeatable benefit—available as part of your subscription—that is delivered by Microsoft engineers to help you move to the cloud at your own pace. FastTrack also gives you access to qualified partners for additional services, as needed. With over 40,000 customers enabled to date, FastTrack helps maximize ROI, accelerate deployment, and increase adoption across your organization. See [FastTrack for Microsoft 365](https://fasttrack.microsoft.com/microsoft365).</span></span>

<span data-ttu-id="b556d-p103">如果想要充分利用 FastTrack 来部署 Microsoft 365 企业版，可以使用 FastTrack [Microsoft 365 部署顾问](https://aka.ms/microsoft365setupguide)了解如何部署和设置底层基础结构。必须以全局管理员的身份在 Office 365 或 Microsoft 365 租户中登录，才能访问此页面。</span><span class="sxs-lookup"><span data-stu-id="b556d-p103">If you want to take advantage of FastTrack to deploy Microsoft 365 Enterprise, you can use the FastTrack [Microsoft 365 deployment advisor](https://aka.ms/microsoft365setupguide) for guidance on how to deploy and set up your foundation infrastructure. You must be signed on as a global administrator in an Office 365 or Microsoft 365 tenant in order to access this page.</span></span>

## <a name="take-a-test-drive"></a><span data-ttu-id="b556d-123">试用体验版</span><span class="sxs-lookup"><span data-stu-id="b556d-123">Take a test drive</span></span>

<span data-ttu-id="b556d-p104">在生产部署或特定选项部署前，使用测试实验室指南 (TLG) 对 Microsoft 365 企业版进行测试。TLG 是模块化的规范性文章，指导你在已简化但具有代表性的环境中使用试用版或付费订阅分步完成对基础结构或功能的配置。</span><span class="sxs-lookup"><span data-stu-id="b556d-p104">Play with Microsoft 365 Enterprise prior to production deployment or the deployment of specific options with Test Lab Guides (TLGs). TLGs are modular, prescriptive articles that step you through the configuration of infrastructure or a feature in a simplified but representative environment using trial or paid subscriptions.</span></span> 

<span data-ttu-id="b556d-126">使用 TLG，可以演示、自定义或论证复杂配置、工作负载或端到端方案的概念。</span><span class="sxs-lookup"><span data-stu-id="b556d-126">With TLGs, you can demonstrate, customize, or build a proof of concept of a complex configuration, workload, or end-to-end scenario.</span></span>

<span data-ttu-id="b556d-127">有关详细信息，请参阅 [Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="b556d-127">For more information, see [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>

![适用于 Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

## <a name="how-customers-use-microsoft-365-enterprise"></a><span data-ttu-id="b556d-129">客户如何使用 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="b556d-129">How customers use Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b556d-130">请参阅以下资源，了解客户如何使用 Microsoft 365 企业版作为完整、智能的解决方案，使每个人都能够发挥创造力并安全地协同工作：</span><span class="sxs-lookup"><span data-stu-id="b556d-130">See these resources to learn how customers are using Microsoft 365 Enterprise as their complete, intelligent solution that empowers everyone to be creative and work together securely:</span></span>

- <span data-ttu-id="b556d-131">健康服务</span><span class="sxs-lookup"><span data-stu-id="b556d-131">Health services</span></span>
  - [<span data-ttu-id="b556d-132">Lilly 设想了下面这样的工作场所：内部和外部协作共同推动创新，并缩短新药物的上市时间</span><span class="sxs-lookup"><span data-stu-id="b556d-132">Lilly envisions a workplace where internal and external collaboration help enable innovation and accelerate time-to-market for new medicines</span></span>](https://aka.ms/Eli_CLS)
  - [<span data-ttu-id="b556d-133">医疗保健技术创新者在云中加速推进糖尿病预防</span><span class="sxs-lookup"><span data-stu-id="b556d-133">Healthcare technology innovator accelerates diabetes prevention in the cloud </span></span>](https://aka.ms/Soleracasestudy)
  - [<span data-ttu-id="b556d-134">美国基督复临安息日会健康照护系统正在使用 Microsoft 365 增强医疗保健服务水平</span><span class="sxs-lookup"><span data-stu-id="b556d-134">Adventist Health System is enhancing healthcare delivery using Microsoft 365</span></span>](https://aka.ms/adventisthealth)
  - [<span data-ttu-id="b556d-135">Abrona 通过 Microsoft 365 促进 GDPR 合规性并提高生产力</span><span class="sxs-lookup"><span data-stu-id="b556d-135">Abrona accelerates GDPR compliance and increases productivity with Microsoft 365</span></span>](https://aka.ms/Abrona)
  - [<span data-ttu-id="b556d-136">Centra 采用 Microsoft 365 智能业务工具实现转型并提升患者护理水平</span><span class="sxs-lookup"><span data-stu-id="b556d-136">Centra embraces transformation, improves patient care with Microsoft 365 intelligent business tools</span></span>](https://aka.ms/Centra_Health)
  - [<span data-ttu-id="b556d-137">Advocate Aurora Health 使用 Microsoft 护理协作解决方案增强协作，帮助患者变得身强体健</span><span class="sxs-lookup"><span data-stu-id="b556d-137">Advocate Aurora Health helps patients live well using Microsoft care coordination solution to enhance collaboration</span></span>](https://aka.ms/Advocate_)
- <span data-ttu-id="b556d-138">金融服务</span><span class="sxs-lookup"><span data-stu-id="b556d-138">Financial services</span></span>
  - [<span data-ttu-id="b556d-139">多伦多道明银行在 Office 365 和 Windows 10 中为员工提供辅助技术</span><span class="sxs-lookup"><span data-stu-id="b556d-139">TD Bank empowers employees with assistive technology in Office 365 and Windows 10</span></span>](https://aka.ms/tdbankgroup)
  - [<span data-ttu-id="b556d-140">提供家庭纳税筹划服务的初创企业选择一体化解决方案来帮助发展业务</span><span class="sxs-lookup"><span data-stu-id="b556d-140">Family tax preparation startup chooses all-in-one solution to help grow business</span></span>](https://aka.ms/SOSCaseStudy)
- <span data-ttu-id="b556d-141">交通</span><span class="sxs-lookup"><span data-stu-id="b556d-141">Transportation</span></span>
  - [<span data-ttu-id="b556d-142">Qantas 为员工提供 Microsoft 365，让员工能够取得最佳业绩，同时增强客户体验</span><span class="sxs-lookup"><span data-stu-id="b556d-142">Qantas empowers employees to do their best work with Microsoft 365, enhancing customer experience</span></span>](https://aka.ms/Qantas_CS)
  - [<span data-ttu-id="b556d-143">Amtrak 通过 Microsoft 365 让其移动企业能够提前完成工作</span><span class="sxs-lookup"><span data-stu-id="b556d-143">Amtrak keeps its mobile enterprise running ahead of schedule with Microsoft 365</span></span>](https://aka.ms/Amtrak_)
- <span data-ttu-id="b556d-144">制造</span><span class="sxs-lookup"><span data-stu-id="b556d-144">Manufacturing</span></span>
  - [<span data-ttu-id="b556d-145">钢铁公司消除了硬件成本、简化了 IT，并提高了云中的移动生产力</span><span class="sxs-lookup"><span data-stu-id="b556d-145">Steel company eliminates hardware costs, streamlines IT, and gains mobile productivity in the cloud</span></span>](https://aka.ms/Steeledalecasestudy)
  - [<span data-ttu-id="b556d-146">刺绣设备供应商通过基于云的服务为其业务提供技术支持，并向其他小型企业传递信息</span><span class="sxs-lookup"><span data-stu-id="b556d-146">Embroidery equipment supplier empowers its business with cloud-based services, spreads word to other small businesses</span></span>](https://aka.ms/PriorityLLCCaseStudy)
  - [<span data-ttu-id="b556d-147">父子经营的业务向世界证明了残障员工可以取得的成就</span><span class="sxs-lookup"><span data-stu-id="b556d-147">Father and son business shows the world what employees with disabilities can achieve</span></span>](https://aka.ms/JCSCaseStudy)
  - [<span data-ttu-id="b556d-148">Coconut 公司通过新式协作工具提升了移动性、指标和效率</span><span class="sxs-lookup"><span data-stu-id="b556d-148">Coconut company gains improved mobility, better metrics, and increased productivity by modernizing collaboration tools</span></span>](https://aka.ms/SilvermillCS)
  - [<span data-ttu-id="b556d-149">新兴日本创新者通过 Microsoft 365 商业版发现不会过时的灵活性和安全性增强解决方案</span><span class="sxs-lookup"><span data-stu-id="b556d-149">Thriving Japanese innovator finds future-proof flexibility and enhanced security with Microsoft 365 Business</span></span>](https://aka.ms/DreamFactoryCaseStudy)
- <span data-ttu-id="b556d-150">工程</span><span class="sxs-lookup"><span data-stu-id="b556d-150">Engineering</span></span>
   - [<span data-ttu-id="b556d-151">Cadence 使用移动协作工具加快业务节奏</span><span class="sxs-lookup"><span data-stu-id="b556d-151">Cadence increases the pace of business with mobile collaboration tools</span></span>](https://customers.microsoft.com/story/cadence-partner-professional-services-microsoft-365)
- <span data-ttu-id="b556d-152">专业服务</span><span class="sxs-lookup"><span data-stu-id="b556d-152">Professional services</span></span>
  - [<span data-ttu-id="b556d-153">精品商务和房地产律师事务所通过全面的基于云的平台支持业务扩展</span><span class="sxs-lookup"><span data-stu-id="b556d-153">Boutique business and real estate law firm supports expansion with comprehensive cloud-based platform </span></span>](https://aka.ms/Lieserskaffcasestudy)
  - [<span data-ttu-id="b556d-154">体育科技公司通过生物反馈法和分析帮助运动员达到顶峰状态</span><span class="sxs-lookup"><span data-stu-id="b556d-154">Sports technology company helps athletes reach their peak through biofeedback and analytics </span></span>](https://aka.ms/KMOTIONCasestudy)
  - [<span data-ttu-id="b556d-155">数字化转型和云使商业协会能够更好地为其成员服务</span><span class="sxs-lookup"><span data-stu-id="b556d-155">Digital transformation and the cloud empower business association to serve its members better </span></span>](https://aka.ms/AIMCS)
- <span data-ttu-id="b556d-156">能源服务</span><span class="sxs-lookup"><span data-stu-id="b556d-156">Energy services</span></span>
  - [<span data-ttu-id="b556d-157">斯伦贝谢有限公司通过 Microsoft 365 改进了全球团队合作</span><span class="sxs-lookup"><span data-stu-id="b556d-157">Schlumberger refines global teamwork with Microsoft 365</span></span>](https://aka.ms/Schlumberger_)
- <span data-ttu-id="b556d-158">建筑</span><span class="sxs-lookup"><span data-stu-id="b556d-158">Construction</span></span>
  - [<span data-ttu-id="b556d-159">常规工程承包公司在搜索数据安全性解决方案时发现 Microsoft 365 的协作功能十分实用</span><span class="sxs-lookup"><span data-stu-id="b556d-159">Search for data security solution unearths collaborative capabilities of Microsoft 365 at general contracting company</span></span>](https://aka.ms/Transbluecasestudy)
- <span data-ttu-id="b556d-160">咨询</span><span class="sxs-lookup"><span data-stu-id="b556d-160">Consulting</span></span>
  - [<span data-ttu-id="b556d-161">ERM 通过 Microsoft 365 参与构建更具可持续性的未来</span><span class="sxs-lookup"><span data-stu-id="b556d-161">ERM contributes to a more sustainable future with Microsoft 365</span></span>](https://aka.ms/ERM_CS)
- <span data-ttu-id="b556d-162">公益</span><span class="sxs-lookup"><span data-stu-id="b556d-162">Non-profit</span></span>
  - [<span data-ttu-id="b556d-163">迁移到云中可节省 $500,000 公益资金，同时提升安全性、移动性和协作</span><span class="sxs-lookup"><span data-stu-id="b556d-163">Move to the cloud saves nonprofit $500,000 while improving security, mobility, and collaboration </span></span>](https://aka.ms/MOWCaseStudy)
  
## <a name="how-microsoft-uses-microsoft-365-enterprise"></a><span data-ttu-id="b556d-164">Microsoft 如何使用 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="b556d-164">How Microsoft uses Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b556d-165">一窥 Microsoft IT 内部的情况并了解他们如何部署 Microsoft 365 企业版以及 Microsoft 员工每天如何使用该产品。</span><span class="sxs-lookup"><span data-stu-id="b556d-165">Take a peek inside Microsoft IT and learn how they deployed Microsoft 365 Enterprise and how Microsoft employees use it every day.</span></span>

### <a name="networking"></a><span data-ttu-id="b556d-166">网络</span><span class="sxs-lookup"><span data-stu-id="b556d-166">Networking</span></span>

- [<span data-ttu-id="b556d-167">优化 Microsoft Office 365 的网络性能</span><span class="sxs-lookup"><span data-stu-id="b556d-167">Optimizing network performance for Microsoft Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/631/Optimizing-network-performance-for-Microsoft-Office-365)

### <a name="identity"></a><span data-ttu-id="b556d-168">标识</span><span class="sxs-lookup"><span data-stu-id="b556d-168">Identity</span></span>

- [<span data-ttu-id="b556d-169">管理 Microsoft 用户标识和安全访问</span><span class="sxs-lookup"><span data-stu-id="b556d-169">Managing user identities and secure access at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [<span data-ttu-id="b556d-170">使用 Azure AD Privileged Identity Management 进行提升的访问</span><span class="sxs-lookup"><span data-stu-id="b556d-170">Using Azure AD Privileged Identity Management for elevated access</span></span>](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

### <a name="windows-10-enterprise"></a><span data-ttu-id="b556d-171">Windows 10 企业版</span><span class="sxs-lookup"><span data-stu-id="b556d-171">Windows 10 Enterprise</span></span>

- [<span data-ttu-id="b556d-172">为组织准备 Windows 10 无缝部署</span><span class="sxs-lookup"><span data-stu-id="b556d-172">Preparing your organization for a seamless Windows 10 deployment</span></span>](https://www.microsoft.com/itshowcase/windows10deployment?wt.mc_id=bmkg_itsc)
- [<span data-ttu-id="b556d-173">在 Microsoft 中采用 Windows 作为服务</span><span class="sxs-lookup"><span data-stu-id="b556d-173">Adopting Windows as a service at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/851/Adopting-Windows-as-a-service-at-Microsoft)
- [<span data-ttu-id="b556d-174">在 Microsoft 中将 Windows 10 部署为就地升级</span><span class="sxs-lookup"><span data-stu-id="b556d-174">Deploying Windows 10 at Microsoft as an in-place upgrade</span></span>](https://www.microsoft.com/itshowcase/Article/Content/668/Deploying-Windows-10-at-Microsoft-as-an-inplace-upgrade)
- [<span data-ttu-id="b556d-175">使用 Windows Hello 企业版实现功能强大的用户身份验证</span><span class="sxs-lookup"><span data-stu-id="b556d-175">Implementing strong user authentication with Windows Hello for Business</span></span>](https://www.microsoft.com/itshowcase/Article/Content/756/Implementing-strong-user-authentication-with-Windows-Hello-for-Business)
- <span data-ttu-id="b556d-176">[Windows 10 部署：来自 Microsoft IT 部门的提示和技巧](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT)（视频）</span><span class="sxs-lookup"><span data-stu-id="b556d-176">[Windows 10 deployment: tips and tricks from Microsoft IT](https://www.microsoft.com/itshowcase/Article/Content/951/Windows-10-deployment-tips-and-tricks-from-Microsoft-IT) (video)</span></span>
- [<span data-ttu-id="b556d-177">Windows Defender ATP 有助于检测到复杂的威胁</span><span class="sxs-lookup"><span data-stu-id="b556d-177">Windows Defender ATP helps detect sophisticated threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/854/Windows-Defender-ATP-helps-detect-sophisticated-threats)
- <span data-ttu-id="b556d-178">[使用 Windows Defender 和 Windows Defender ATP 保护现代企业的安全](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP)（视频）</span><span class="sxs-lookup"><span data-stu-id="b556d-178">[Securing the modern enterprise with Windows Defender and Windows Defender ATP](https://www.microsoft.com/itshowcase/Article/Content/903/Securing-the-modern-enterprise-with-Windows-Defender-and-Windows-Defender-ATP) (video)</span></span>

### <a name="office-365-proplus"></a><span data-ttu-id="b556d-179">Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="b556d-179">Office 365 ProPlus</span></span>

- [<span data-ttu-id="b556d-180">为组织准备 Office 365 专业增强版 2016 无缝部署</span><span class="sxs-lookup"><span data-stu-id="b556d-180">Preparing your organization for a seamless Office 365 ProPlus 2016 deployment</span></span>](https://www.microsoft.com/itshowcase/Office365adoption)
- [<span data-ttu-id="b556d-181">部署和更新 Microsoft Office 365 专业增强版</span><span class="sxs-lookup"><span data-stu-id="b556d-181">Deploying and updating Microsoft Office 365 ProPlus</span></span>](https://www.microsoft.com/itshowcase/Article/Content/757/Deploying-and-updating-Microsoft-Office-365-ProPlus)
- <span data-ttu-id="b556d-182">[自动化和更新通道有助于部署 Microsoft Office 365 专业增强版](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus)（视频）</span><span class="sxs-lookup"><span data-stu-id="b556d-182">[Automation and update channels help deploy Microsoft Office 365 ProPlus](https://www.microsoft.com/itshowcase/Article/Content/794/Automation-and-update-channels-help-deploy-Microsoft-Office-365-ProPlus) (video)</span></span>

### <a name="mobility-and-device-management"></a><span data-ttu-id="b556d-183">移动性和设备管理</span><span class="sxs-lookup"><span data-stu-id="b556d-183">Mobility and device management</span></span>

- [<span data-ttu-id="b556d-184">通过企业移动性 + 安全性管理新式移动效率</span><span class="sxs-lookup"><span data-stu-id="b556d-184">Managing modern mobile productivity with Enterprise Mobility + Security</span></span>](https://www.microsoft.com/itshowcase/Article/Content/972/Managing-modern-mobile-productivity-with-Enterprise-Mobility--Security)
- [<span data-ttu-id="b556d-185">通过 Microsoft Intune 在 Windows 10 设备上连接到工作内容</span><span class="sxs-lookup"><span data-stu-id="b556d-185">Connecting to work on your Windows 10 device with Microsoft Intune</span></span>](https://www.microsoft.com/itshowcase/Article/Content/783/Connecting-to-work-on-your-Windows-10-device-with-Microsoft-Intune)
- [<span data-ttu-id="b556d-186">在 Microsoft 推动 iOS、OS X 和 Android 设备的移动效率</span><span class="sxs-lookup"><span data-stu-id="b556d-186">Enabling mobile productivity for iOS, OS X, and Android devices at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/773/Enabling-mobile-productivity-for-iOS-OS-X-and-Android-devices-at-Microsoft)

### <a name="security-and-information-protection"></a><span data-ttu-id="b556d-187">安全和信息保护</span><span class="sxs-lookup"><span data-stu-id="b556d-187">Security and information protection</span></span>

- [<span data-ttu-id="b556d-188">使用 Azure 信息保护来保护云中的文件</span><span class="sxs-lookup"><span data-stu-id="b556d-188">Protecting files in the cloud with Azure Information Protection</span></span>](https://www.microsoft.com/itshowcase/Article/Content/924/Protecting-files-in-the-cloud-with-Azure-Information-Protection)
- [<span data-ttu-id="b556d-189">Microsoft 使用威胁智能来保护、检测和响应威胁</span><span class="sxs-lookup"><span data-stu-id="b556d-189">Microsoft uses threat intelligence to protect, detect, and respond to threats</span></span>](https://www.microsoft.com/itshowcase/Article/Content/934/Microsoft-uses-threat-intelligence-to-protect-detect-and-respond-to-threats)
- [<span data-ttu-id="b556d-190">Microsoft 使用 Office 365 阻止网络钓鱼的尝试</span><span class="sxs-lookup"><span data-stu-id="b556d-190">Microsoft thwarts phishing attempts with Office 365</span></span>](https://www.microsoft.com/itshowcase/Article/Content/956/Microsoft-thwarts-phishing-attempts-with-Office-365)

### <a name="microsoft-teams"></a><span data-ttu-id="b556d-191">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="b556d-191">Microsoft Teams</span></span>

- [<span data-ttu-id="b556d-192">部署 Microsoft Teams 可简化协作流程并增强团队合作</span><span class="sxs-lookup"><span data-stu-id="b556d-192">Deploying Microsoft Teams streamlines collaboration and improves teamwork</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1013/Deploying-Microsoft-Teams-streamlines-collaboration-and-improves-teamwork)
- [<span data-ttu-id="b556d-193">Microsoft Teams 可增强 Microsoft 现代工作场所中的协作</span><span class="sxs-lookup"><span data-stu-id="b556d-193">Microsoft Teams increases collaboration in the modern workplace at Microsoft</span></span>](https://www.microsoft.com/itshowcase/Article/Content/1012/Microsoft-Teams-increases-collaboration-in-the-modern-workplace-at-Microsoft)

### <a name="data-migration"></a><span data-ttu-id="b556d-194">数据迁移</span><span class="sxs-lookup"><span data-stu-id="b556d-194">Data migration</span></span>

- [<span data-ttu-id="b556d-195">Microsoft 将 150,000 个邮箱迁移到 Exchange Online</span><span class="sxs-lookup"><span data-stu-id="b556d-195">Microsoft migrates 150,000 mailboxes to Exchange Online</span></span>](https://www.microsoft.com/itshowcase/Article/Content/577/Microsoft-migrates-150000-mailboxes-to-Exchange-Online)
- [<span data-ttu-id="b556d-196">SharePoint 到云：了解 Microsoft 如何运行自己的迁移</span><span class="sxs-lookup"><span data-stu-id="b556d-196">SharePoint to the cloud: Learn how Microsoft ran its own migration</span></span>](https://www.microsoft.com/itshowcase/Article/Content/691/SharePoint-to-the-cloud-Learn-how-Microsoft-ran-its-own-migration)

## <a name="how-the-contoso-corporation-deployed-microsoft-365-enterprise"></a><span data-ttu-id="b556d-197">Contoso Corporation 如何部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="b556d-197">How the Contoso Corporation deployed Microsoft 365 Enterprise</span></span>

<span data-ttu-id="b556d-p105">Contoso Corporation 是一个虚构但具有代表性的全球大型制造企业，总部设在巴黎。请了解 [Contoso 如何部署 Microsoft 365 企业版](contoso-case-study.md)并且完成了主要设计决策和针对以下方面的实施细节：网络、标识、Windows 10 企业版、Office 365 专业增强版、移动设备管理、信息保护和安全性。</span><span class="sxs-lookup"><span data-stu-id="b556d-p105">The Contoso Corporation is a fictional but representative global manufacturing conglomerate with its headquarters in Paris. See how [Contoso deployed Microsoft 365 Enterprise](contoso-case-study.md) and addressed major design decisions and implementation details for networking, identity, Windows 10 Enterprise, Office 365 ProPlus, mobile device management, information protection, and security.</span></span> 

![](./media/contoso-overview/contoso-icon.png)

## <a name="additional-microsoft-365-solutions"></a><span data-ttu-id="b556d-200">其他 Microsoft 365 解决方案</span><span class="sxs-lookup"><span data-stu-id="b556d-200">Additional Microsoft 365 solutions</span></span>

- [<span data-ttu-id="b556d-201">Microsoft 365 商业版</span><span class="sxs-lookup"><span data-stu-id="b556d-201">Microsoft 365 Business</span></span>](https://docs.microsoft.com/microsoft-365/business/)
 
  <span data-ttu-id="b556d-202">将 Office 365 一流的工作效率和协作功能与设备管理和安全解决方案汇集在了一起，可保护中小型企业 (SMB) 业务数据的安全。</span><span class="sxs-lookup"><span data-stu-id="b556d-202">Bring together the best-in-class productivity and collaboration capabilities of Office 365 with device management and security solutions to safeguard business data for small and midsize businesses (SMB).</span></span>

- [<span data-ttu-id="b556d-203">Microsoft 365 教育版</span><span class="sxs-lookup"><span data-stu-id="b556d-203">Microsoft 365 Education</span></span>](https://docs.microsoft.com/education)
 
  <span data-ttu-id="b556d-204">通过为教育版构建单一、价格合理的解决方案，使教育工作者可以充分发挥创造力、提升团队合作，并提供安全易用的用户体验。</span><span class="sxs-lookup"><span data-stu-id="b556d-204">Empower educators to unlock creativity, promote teamwork, and provide a simple and safe experience in a single, affordable solution built for education.</span></span>

## <a name="next-step"></a><span data-ttu-id="b556d-205">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b556d-205">Next step</span></span>

<span data-ttu-id="b556d-206">使用 [FastTrack](https://fasttrack.microsoft.com/microsoft365) 或开始设置[底层基础结构](deploy-foundation-infrastructure.md)。</span><span class="sxs-lookup"><span data-stu-id="b556d-206">Use [FastTrack](https://fasttrack.microsoft.com/microsoft365) or get started with the [foundation infrastructure](deploy-foundation-infrastructure.md).</span></span>
