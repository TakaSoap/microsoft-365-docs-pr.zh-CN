---
title: 了解终结点数据丢失防护
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 了解如何使用数据丢失防护策略和工具Microsoft 365敏感信息，并浏览 DLP 生命周期。
ms.openlocfilehash: 88cf913f62d28c89bce7054473eb577217de9489
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52244608"
---
# <a name="learn-about-data-loss-prevention"></a><span data-ttu-id="784b4-103">了解终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="784b4-103">Learn about data loss prevention</span></span>

<span data-ttu-id="784b4-104">组织拥有其控制的敏感信息，例如财务数据、专有数据、信用卡号、健康记录或社会保险号。</span><span class="sxs-lookup"><span data-stu-id="784b4-104">Organizations have sensitive information under their control such as financial data, proprietary data, credit card numbers, health records, or social security numbers.</span></span> <span data-ttu-id="784b4-105">为了帮助保护此敏感数据并降低风险，他们需要一种方法来防止其用户与不应具有该数据的人不当共享它。</span><span class="sxs-lookup"><span data-stu-id="784b4-105">To help protect this sensitive data and reduce risk, they need a way to prevent their users from inappropriately sharing it with people who shouldn't have it.</span></span> <span data-ttu-id="784b4-106">此做法称为 DLP (数据丢失) 。</span><span class="sxs-lookup"><span data-stu-id="784b4-106">This practice is called data loss prevention (DLP).</span></span>

<span data-ttu-id="784b4-107">在Microsoft 365中，通过定义和应用 DLP 策略来实现数据丢失防护。</span><span class="sxs-lookup"><span data-stu-id="784b4-107">In Microsoft 365, you implement data loss prevention by defining and applying DLP policies.</span></span> <span data-ttu-id="784b4-108">使用 DLP 策略，可以标识、监视和自动保护以下各项中的敏感项目：</span><span class="sxs-lookup"><span data-stu-id="784b4-108">With a DLP policy, you can identify, monitor, and automatically protect sensitive items across:</span></span>

- <span data-ttu-id="784b4-109">Microsoft 365服务，如 Teams、Exchange、SharePoint 和 OneDrive</span><span class="sxs-lookup"><span data-stu-id="784b4-109">Microsoft 365 services such as Teams, Exchange, SharePoint, and OneDrive</span></span>
- <span data-ttu-id="784b4-110">Office Word、Excel 和 PowerPoint</span><span class="sxs-lookup"><span data-stu-id="784b4-110">Office applications such as Word, Excel, and PowerPoint</span></span>
- <span data-ttu-id="784b4-111">Windows 10终结点</span><span class="sxs-lookup"><span data-stu-id="784b4-111">Windows 10 endpoints</span></span>
- <span data-ttu-id="784b4-112">非 Microsoft 云应用</span><span class="sxs-lookup"><span data-stu-id="784b4-112">non-Microsoft cloud apps</span></span>
- <span data-ttu-id="784b4-113">本地文件共享和本地SharePoint。</span><span class="sxs-lookup"><span data-stu-id="784b4-113">on-premises file shares and on-premises SharePoint.</span></span>

<span data-ttu-id="784b4-114">Microsoft 365深入内容分析检测敏感项目，而不只是通过简单的文本扫描。</span><span class="sxs-lookup"><span data-stu-id="784b4-114">Microsoft 365 detects sensitive items by using deep content analysis, not by just a simple text scan.</span></span> <span data-ttu-id="784b4-115">内容按以下方法进行分析：关键字的主数据匹配、正则表达式评估、内部函数验证和与主要数据匹配接近的辅助数据匹配。</span><span class="sxs-lookup"><span data-stu-id="784b4-115">Content is analyzed for primary data matches to keywords, by the evaluation of regular expressions, by internal function validation, and by secondary data matches that are in proximity to the primary data match.</span></span> <span data-ttu-id="784b4-116">此外，DLP 还使用机器学习算法和其他方法来检测与 DLP 策略匹配的内容。</span><span class="sxs-lookup"><span data-stu-id="784b4-116">Beyond that DLP also uses machine learning algorithms and other methods to detect content that matches your DLP policies.</span></span>
  
## <a name="dlp-is-part-of-the-larger-microsoft-365-compliance-offering"></a><span data-ttu-id="784b4-117">DLP 是大型合规性Microsoft 365的一部分</span><span class="sxs-lookup"><span data-stu-id="784b4-117">DLP is part of the larger Microsoft 365 Compliance offering</span></span>

<span data-ttu-id="784b4-118">Microsoft 365DLP 只是一种Microsoft 365合规性工具，可用于帮助保护无论您的敏感项目位于何处或身在何处。</span><span class="sxs-lookup"><span data-stu-id="784b4-118">Microsoft 365 DLP is just one of the Microsoft 365 Compliance tools that you will use to help protect your sensitive items wherever they live or travel.</span></span> <span data-ttu-id="784b4-119">你应了解 Microsoft 365 合规性工具集内的其他工具、它们如何相互关联以及如何更好地协同工作。</span><span class="sxs-lookup"><span data-stu-id="784b4-119">You should understand the other tools in the Microsoft 365 Compliance tools set, how they interrelate, and work better together.</span></span>  <span data-ttu-id="784b4-120">请参阅[Microsoft 365合规性工具](protect-information.md)，详细了解信息保护过程。</span><span class="sxs-lookup"><span data-stu-id="784b4-120">See, [Microsoft 365 compliance tools](protect-information.md) to learn more about the information protection process.</span></span>

## <a name="protective-actions-of-dlp-policies"></a><span data-ttu-id="784b4-121">DLP 策略的保护操作</span><span class="sxs-lookup"><span data-stu-id="784b4-121">Protective actions of DLP policies</span></span>

<span data-ttu-id="784b4-122">Microsoft 365DLP 策略是监视用户对其余敏感项目、传输中的敏感项或使用中的敏感项目执行的活动，并采取保护措施。</span><span class="sxs-lookup"><span data-stu-id="784b4-122">Microsoft 365 DLP policies are how you monitor the activities that users take on sensitive items at rest, sensitive items in transit, or sensitive items in use and take protective actions.</span></span> <span data-ttu-id="784b4-123">例如，当用户尝试采取禁止的操作（如将敏感项目复制到未批准的位置或在电子邮件中共享医疗信息或策略中规定的其他状况）时，DLP 可以：</span><span class="sxs-lookup"><span data-stu-id="784b4-123">For example, when a user attempts to take a prohibited action, like copying a sensitive item to an unapproved location or sharing medical information in an email or other conditions laid out in a policy, DLP can:</span></span>

- <span data-ttu-id="784b4-124">向用户显示一个弹出策略提示，警告他们可能会尝试以不当方式共享敏感项目</span><span class="sxs-lookup"><span data-stu-id="784b4-124">show a pop-up policy tip to the user that warns them that they may be trying to share a sensitive item inappropriately</span></span>
- <span data-ttu-id="784b4-125">阻止共享，并且通过策略提示允许用户替代阻止并捕获用户的理由</span><span class="sxs-lookup"><span data-stu-id="784b4-125">block the sharing and, via a policy tip, allow the user to override the block and capture the users' justification</span></span>
- <span data-ttu-id="784b4-126">在没有替代选项的情况下阻止共享</span><span class="sxs-lookup"><span data-stu-id="784b4-126">block the sharing without the override option</span></span>
- <span data-ttu-id="784b4-127">对于处于其余状态的数据，敏感项目可以锁定并移动到安全隔离位置</span><span class="sxs-lookup"><span data-stu-id="784b4-127">for data at rest, sensitive items can be locked and moved to a secure quarantine location</span></span>
- <span data-ttu-id="784b4-128">对于Teams聊天，将不会显示敏感信息</span><span class="sxs-lookup"><span data-stu-id="784b4-128">for Teams chat, the sensitive information will not be displayed</span></span>

<span data-ttu-id="784b4-129">默认情况下，所有 DLP 监视的活动都记录到Microsoft 365[审核日志](search-the-audit-log-in-security-and-compliance.md)，并路由到活动[资源管理器](data-classification-activity-explorer.md)。</span><span class="sxs-lookup"><span data-stu-id="784b4-129">All DLP monitored activities are recorded to the [Microsoft 365 Audit log](search-the-audit-log-in-security-and-compliance.md) by default and routed to [Activity explorer](data-classification-activity-explorer.md).</span></span> <span data-ttu-id="784b4-130">当用户执行符合 DLP 策略条件的操作并且配置了警报时，DLP 将在 DLP 警报管理仪表板 [中发出警报](dlp-configure-view-alerts-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="784b4-130">When a user performs an action that meets the criteria of a DLP policy, and you have alerts configured, DLP provides alerts in the [DLP alert management dashboard](dlp-configure-view-alerts-policies.md).</span></span>

## <a name="dlp-lifecycle"></a><span data-ttu-id="784b4-131">DLP 生命周期</span><span class="sxs-lookup"><span data-stu-id="784b4-131">DLP lifecycle</span></span>

<span data-ttu-id="784b4-132">DLP 实现通常遵循以下主要阶段。</span><span class="sxs-lookup"><span data-stu-id="784b4-132">A DLP implementation typically follows these major phases.</span></span>

- [<span data-ttu-id="784b4-133">规划 DLP</span><span class="sxs-lookup"><span data-stu-id="784b4-133">Plan for DLP</span></span>](#plan-for-dlp)
- [<span data-ttu-id="784b4-134">准备 DLP</span><span class="sxs-lookup"><span data-stu-id="784b4-134">Prepare for DLP</span></span>](#prepare-for-dlp)
- [<span data-ttu-id="784b4-135">在生产中部署策略</span><span class="sxs-lookup"><span data-stu-id="784b4-135">Deploy your policies in production</span></span>](#deploy-your-policies-in-production)


<!--ADD DIAGRAM OF THE DLP LIFECYCLE WORK ON WITH MAS-->

### <a name="plan-for-dlp"></a><span data-ttu-id="784b4-136">规划 DLP</span><span class="sxs-lookup"><span data-stu-id="784b4-136">Plan for DLP</span></span>

<span data-ttu-id="784b4-137">Microsoft 365DLP 监视和保护对于用户每天使用的应用程序是本机的。</span><span class="sxs-lookup"><span data-stu-id="784b4-137">Microsoft 365 DLP monitoring and protection are native to the applications that users use every day.</span></span> <span data-ttu-id="784b4-138">这有助于保护组织的敏感项目免受风险活动的影响，即使用户未习惯数据丢失防护的思路和做法。</span><span class="sxs-lookup"><span data-stu-id="784b4-138">This helps to protect your organizations' sensitive items from risky activities even if your users are unaccustomed to data loss prevention thinking and practices.</span></span> <span data-ttu-id="784b4-139">如果您的组织和用户对数据丢失防护做法没有了解，则采用 DLP 可能需要更改业务流程，并且您的用户会进行文化转变。</span><span class="sxs-lookup"><span data-stu-id="784b4-139">If your organization and your users are new to data loss prevention practices, the adoption of DLP may require a change to your business processes and there will be a culture shift for your users.</span></span> <span data-ttu-id="784b4-140">但是，通过适当的规划、测试和调整，DLP 策略将保护敏感项目，同时最大限度地减少任何潜在的业务流程中断。</span><span class="sxs-lookup"><span data-stu-id="784b4-140">But, with proper planning, testing and tuning, your DLP policies will protect your sensitive items while minimizing any potential business process disruptions.</span></span>

<span data-ttu-id="784b4-141">**DLP 技术规划**</span><span class="sxs-lookup"><span data-stu-id="784b4-141">**Technology planning for DLP**</span></span>

<span data-ttu-id="784b4-142">请记住，作为一种技术，DLP 可以监视和保护处于非活动状态的数据、使用中的数据和跨 Microsoft 365 服务、Windows 10 设备、本地文件共享和本地 SharePoint 运行的数据。</span><span class="sxs-lookup"><span data-stu-id="784b4-142">Keep in mind that DLP as a technology can monitor and protect your data at rest, data in use and data in motion across Microsoft 365 services, Windows 10 devices, on-premises file shares, and on-premises SharePoint.</span></span> <span data-ttu-id="784b4-143">对不同位置、要监视和保护的数据类型以及发生策略匹配时要采取的操作有规划影响。</span><span class="sxs-lookup"><span data-stu-id="784b4-143">There are planning implications for the different locations, the type of data you want to monitor and protect, and the actions to be taken when a policy match occurs.</span></span>  

<span data-ttu-id="784b4-144">**规划 DLP 的业务流程**</span><span class="sxs-lookup"><span data-stu-id="784b4-144">**Business processes planning for DLP**</span></span>

<span data-ttu-id="784b4-145">DLP 策略可以阻止禁止的活动，例如通过电子邮件不当共享敏感信息。</span><span class="sxs-lookup"><span data-stu-id="784b4-145">DLP policies can block prohibited activities, like inappropriate sharing of sensitive information via email.</span></span> <span data-ttu-id="784b4-146">在规划 DLP 策略时，必须确定涉及敏感项目的业务流程。</span><span class="sxs-lookup"><span data-stu-id="784b4-146">As you plan your DLP policies, you must identify the business processes that touch your sensitive items.</span></span> <span data-ttu-id="784b4-147">用户业务流程有助于确定应允许的适当用户行为以及应防止的不当用户行为。</span><span class="sxs-lookup"><span data-stu-id="784b4-147">The business process owners can help you identify appropriate user behaviors that should be allowed and inappropriate user behaviors that should be protected against.</span></span> <span data-ttu-id="784b4-148">应先规划策略，在测试模式下部署策略，并首先通过活动资源管理器评估[](data-classification-activity-explorer.md)其影响，然后再在更严格的模式下应用策略。</span><span class="sxs-lookup"><span data-stu-id="784b4-148">You should plan your policies and deploy them in test mode, and evaluate their impact via [activity explorer](data-classification-activity-explorer.md) first, before applying them in more restrictive modes.</span></span>

<span data-ttu-id="784b4-149">**DLP 的组织文化规划**</span><span class="sxs-lookup"><span data-stu-id="784b4-149">**Organizational culture planning for DLP**</span></span>

<span data-ttu-id="784b4-150">成功的 DLP 实现与让用户接受数据丢失防护实践的训练和适应，就像在精心规划并调整策略上一样。</span><span class="sxs-lookup"><span data-stu-id="784b4-150">A successful DLP implementation is as much dependent on getting your users trained and acclimated to data loss prevention practices as it is on well planned and tuned policies.</span></span> <span data-ttu-id="784b4-151">由于用户涉及大量内容，因此请务必为用户规划培训。</span><span class="sxs-lookup"><span data-stu-id="784b4-151">Since your users are heavily involved, be sure to plan for training for them too.</span></span> <span data-ttu-id="784b4-152">在将策略强制执行从测试模式更改为更严格的模式之前，你可以从战略上使用策略提示提高用户意识。</span><span class="sxs-lookup"><span data-stu-id="784b4-152">You can strategically use policy tips to raise awareness with your users before changing the policy enforcement from test mode to more restrictive modes.</span></span>

<!--For more information on planning for DLP, including suggestions for deployment based on your needs and resources, see [Planning for Microsoft 365 data loss prevention](dlp-plan-for-dlp.md).-->

### <a name="prepare-for-dlp"></a><span data-ttu-id="784b4-153">准备 DLP</span><span class="sxs-lookup"><span data-stu-id="784b4-153">Prepare for DLP</span></span>

<span data-ttu-id="784b4-154">您可以将 DLP 策略应用于处于其余状态的数据、使用中的数据和位置中运动的数据，例如：</span><span class="sxs-lookup"><span data-stu-id="784b4-154">You can apply DLP policies to data at rest, data in use, and data in motion in locations, such as:</span></span>

- <span data-ttu-id="784b4-155">Exchange Online电子邮件</span><span class="sxs-lookup"><span data-stu-id="784b4-155">Exchange Online email</span></span>
- <span data-ttu-id="784b4-156">SharePoint Online 站点</span><span class="sxs-lookup"><span data-stu-id="784b4-156">SharePoint Online sites</span></span>
- <span data-ttu-id="784b4-157">OneDrive 帐户</span><span class="sxs-lookup"><span data-stu-id="784b4-157">OneDrive accounts</span></span>
- <span data-ttu-id="784b4-158">Teams 聊天和通道消息</span><span class="sxs-lookup"><span data-stu-id="784b4-158">Teams chat and channel messages</span></span>
- <span data-ttu-id="784b4-159">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="784b4-159">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="784b4-160">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="784b4-160">Windows 10 devices</span></span>
- <span data-ttu-id="784b4-161">本地存储库</span><span class="sxs-lookup"><span data-stu-id="784b4-161">On-premises repositories</span></span>

<span data-ttu-id="784b4-162">每个先决条件各不相同。</span><span class="sxs-lookup"><span data-stu-id="784b4-162">Each one has different pre-requisites.</span></span> <span data-ttu-id="784b4-163">某些位置（如 Exchange）中的敏感项目只需配置适用于它们的策略，就可以将其放在 DLP 保护之下。</span><span class="sxs-lookup"><span data-stu-id="784b4-163">Sensitive items in some locations, like Exchange online, can be brought under the DLP umbrella by just configuring a policy that applies to them.</span></span> <span data-ttu-id="784b4-164">其他项目（如本地文件存储库）需要部署 Azure 信息保护 (AIP) 扫描程序。</span><span class="sxs-lookup"><span data-stu-id="784b4-164">Others, such as on-premises file repositories require a deployment of Azure Information Protection (AIP) scanner.</span></span> <span data-ttu-id="784b4-165">在激活任何阻止操作之前，你需要准备环境、代码草稿策略并全面测试它们。</span><span class="sxs-lookup"><span data-stu-id="784b4-165">You'll need to prepare your environment, code draft policies, and test them thoroughly before activating any blocking actions.</span></span>

### <a name="deploy-your-policies-in-production"></a><span data-ttu-id="784b4-166">在生产中部署策略</span><span class="sxs-lookup"><span data-stu-id="784b4-166">Deploy your policies in production</span></span>

#### <a name="design-your-policies"></a><span data-ttu-id="784b4-167">设计策略</span><span class="sxs-lookup"><span data-stu-id="784b4-167">Design your policies</span></span>

<span data-ttu-id="784b4-168">首先定义你的控制目标，以及如何在各自的工作负载中应用这些目标。</span><span class="sxs-lookup"><span data-stu-id="784b4-168">Start by defining your control objectives, and how they apply across each respective workload.</span></span> <span data-ttu-id="784b4-169">制定实现目标的策略。</span><span class="sxs-lookup"><span data-stu-id="784b4-169">Draft a policy that embodies your objectives.</span></span> <span data-ttu-id="784b4-170">可随意从一次一个工作负荷开始，也可以跨所有工作负载开始 ，这还没有任何影响。</span><span class="sxs-lookup"><span data-stu-id="784b4-170">Feel free to start with one workload at a time, or across all workloads - there's no impact yet.</span></span>

#### <a name="implement-policy-in-test-mode"></a><span data-ttu-id="784b4-171">在测试模式下实现策略</span><span class="sxs-lookup"><span data-stu-id="784b4-171">Implement policy in test mode</span></span>

<span data-ttu-id="784b4-172">在测试模式下使用 DLP 策略实现控件，评估这些控件的影响。</span><span class="sxs-lookup"><span data-stu-id="784b4-172">Evaluate the impact of the controls by implementing them with a DLP policy in test mode.</span></span> <span data-ttu-id="784b4-173">可以在测试模式下将策略应用于所有工作负荷，以便你可以获得完整的结果，但如果需要，你可以从一个工作负荷开始。</span><span class="sxs-lookup"><span data-stu-id="784b4-173">It's ok to apply the policy to all workloads in test mode, so that you can get the full breadth of results, but you can start with one workload if you need to.</span></span>

#### <a name="monitor-outcomes-and-fine-tune-the-policy"></a><span data-ttu-id="784b4-174">监视结果并微调策略</span><span class="sxs-lookup"><span data-stu-id="784b4-174">Monitor outcomes and fine-tune the policy</span></span>

<span data-ttu-id="784b4-175">在测试模式下，监视策略结果并微调策略，以便它满足控制目标，同时确保不会对有效用户工作流和工作效率造成负面影响或无意影响。</span><span class="sxs-lookup"><span data-stu-id="784b4-175">While in test mode, monitor the outcomes of the policy and fine-tune it so that it meets your control objectives while ensuring you aren't adversely or inadvertently impacting valid user workflows and productivity.</span></span> <span data-ttu-id="784b4-176">下面是要微调的一些内容示例：</span><span class="sxs-lookup"><span data-stu-id="784b4-176">Here are some examples of things to fine-tune:</span></span>

- <span data-ttu-id="784b4-177">调整范围内或超出范围的位置和人员/位置</span><span class="sxs-lookup"><span data-stu-id="784b4-177">adjusting the locations and people/places that are in or out of scope</span></span>
- <span data-ttu-id="784b4-178">调整用于确定项目及其所执行操作是否与策略匹配的条件和例外</span><span class="sxs-lookup"><span data-stu-id="784b4-178">tune the conditions and exceptions that are used to determine if an item and what is being done with it matches the policy</span></span>
- <span data-ttu-id="784b4-179">敏感信息定义</span><span class="sxs-lookup"><span data-stu-id="784b4-179">the sensitive information definition/s</span></span>
- <span data-ttu-id="784b4-180">操作</span><span class="sxs-lookup"><span data-stu-id="784b4-180">the actions</span></span>
- <span data-ttu-id="784b4-181">限制级别</span><span class="sxs-lookup"><span data-stu-id="784b4-181">the level of restrictions</span></span>
- <span data-ttu-id="784b4-182">添加新控件</span><span class="sxs-lookup"><span data-stu-id="784b4-182">add new controls</span></span>
- <span data-ttu-id="784b4-183">添加新人员</span><span class="sxs-lookup"><span data-stu-id="784b4-183">add new people</span></span>
- <span data-ttu-id="784b4-184">添加新的受限应用</span><span class="sxs-lookup"><span data-stu-id="784b4-184">add new restricted apps</span></span>
- <span data-ttu-id="784b4-185">添加新的受限网站</span><span class="sxs-lookup"><span data-stu-id="784b4-185">add new restricted sites</span></span>

#### <a name="enable-the-control-and-tune-your-policies"></a><span data-ttu-id="784b4-186">启用控制并调整策略</span><span class="sxs-lookup"><span data-stu-id="784b4-186">Enable the control and tune your policies</span></span>

<span data-ttu-id="784b4-187">策略满足所有目标后，将其打开。</span><span class="sxs-lookup"><span data-stu-id="784b4-187">Once the policy meets all your objectives, turn it on.</span></span> <span data-ttu-id="784b4-188">继续监视策略应用程序的结果并根据需要进行调整。</span><span class="sxs-lookup"><span data-stu-id="784b4-188">Continue to monitor the outcomes of the policy application and tune as needed.</span></span> <span data-ttu-id="784b4-189">一般情况下，策略在打开后大约一小时生效。</span><span class="sxs-lookup"><span data-stu-id="784b4-189">In general, policies take effect about an hour after being turned on.</span></span> <span data-ttu-id="784b4-190"><!--查看位置特定详细信息 SLA 的 LINK TO 主题-- ></span><span class="sxs-lookup"><span data-stu-id="784b4-190"><!--See, LINK TO topic for SLAs for location specific  details-- ></span></span>

## <a name="dlp-policy-configuration-overview"></a><span data-ttu-id="784b4-191">DLP 策略配置概述</span><span class="sxs-lookup"><span data-stu-id="784b4-191">DLP policy configuration overview</span></span>

<span data-ttu-id="784b4-192">您可以灵活地创建和配置 DLP 策略。</span><span class="sxs-lookup"><span data-stu-id="784b4-192">You have flexibility in how you create and configure your DLP policies.</span></span> <span data-ttu-id="784b4-193">你可以从预定义模板开始，只需单击几下即可创建策略，也可以从头开始设计自己的策略。</span><span class="sxs-lookup"><span data-stu-id="784b4-193">You can start from a predefined template and create a policy in just a few clicks or you can design your own from the ground up.</span></span> <span data-ttu-id="784b4-194">无论你选择哪一个，所有 DLP 策略都需要您提供相同的信息。</span><span class="sxs-lookup"><span data-stu-id="784b4-194">No matter which you choose, all DLP policies require the same information from you.</span></span>

1. <span data-ttu-id="784b4-195">**选择要监视的内容**- Microsoft 365许多预定义的策略模板，可帮助你入门或创建自定义策略。</span><span class="sxs-lookup"><span data-stu-id="784b4-195">**Choose what you want to monitor** - Microsoft 365 comes with many predefined policy templates to help you get started or you can create a custom policy.</span></span>
    - <span data-ttu-id="784b4-196">预定义的策略模板：财务数据、医疗健康数据、隐私数据，所有国家和地区的隐私数据。</span><span class="sxs-lookup"><span data-stu-id="784b4-196">A predefined policy template: Financial data, Medical and health data, Privacy data all for various countries and regions.</span></span>
    - <span data-ttu-id="784b4-197">使用可用敏感信息类型、保留标签和敏感度标签的自定义策略。</span><span class="sxs-lookup"><span data-stu-id="784b4-197">A custom policy that uses the available sensitive information types, retention labels, and sensitivity labels.</span></span>
2. <span data-ttu-id="784b4-198">**Choose where you want to monitor** - You pick one or more locations that you want DLP to monitor for sensitive information.</span><span class="sxs-lookup"><span data-stu-id="784b4-198">**Choose where you want to monitor** - You pick one or more locations that you want DLP to monitor for sensitive information.</span></span> <span data-ttu-id="784b4-199">你可以监视：</span><span class="sxs-lookup"><span data-stu-id="784b4-199">You can monitor:</span></span>
    
<span data-ttu-id="784b4-200">位置</span><span class="sxs-lookup"><span data-stu-id="784b4-200">location</span></span> | <span data-ttu-id="784b4-201">包含/排除方式</span><span class="sxs-lookup"><span data-stu-id="784b4-201">include/exclude by</span></span>|
|---------|---------|
|<span data-ttu-id="784b4-202">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="784b4-202">Exchange email</span></span>| <span data-ttu-id="784b4-203">通讯组</span><span class="sxs-lookup"><span data-stu-id="784b4-203">distribution groups</span></span>|
|<span data-ttu-id="784b4-204">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="784b4-204">SharePoint sites</span></span> |<span data-ttu-id="784b4-205">网站</span><span class="sxs-lookup"><span data-stu-id="784b4-205">sites</span></span> |
|<span data-ttu-id="784b4-206">OneDrive 账户</span><span class="sxs-lookup"><span data-stu-id="784b4-206">OneDrive accounts</span></span> |<span data-ttu-id="784b4-207">帐户或通讯组</span><span class="sxs-lookup"><span data-stu-id="784b4-207">accounts or distribution groups</span></span> |
|<span data-ttu-id="784b4-208">Teams 聊天和通道消息</span><span class="sxs-lookup"><span data-stu-id="784b4-208">Teams chat and channel messages</span></span> |<span data-ttu-id="784b4-209">账户</span><span class="sxs-lookup"><span data-stu-id="784b4-209">accounts</span></span> |
|<span data-ttu-id="784b4-210">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="784b4-210">Windows 10 devices</span></span> |<span data-ttu-id="784b4-211">用户或组</span><span class="sxs-lookup"><span data-stu-id="784b4-211">user or group</span></span> |
|<span data-ttu-id="784b4-212">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="784b4-212">Microsoft Cloud App Security</span></span> |<span data-ttu-id="784b4-213">实例</span><span class="sxs-lookup"><span data-stu-id="784b4-213">instance</span></span> |
|<span data-ttu-id="784b4-214">本地存储库</span><span class="sxs-lookup"><span data-stu-id="784b4-214">On-premises repositories</span></span>| <span data-ttu-id="784b4-215">存储库文件路径</span><span class="sxs-lookup"><span data-stu-id="784b4-215">repository file path</span></span>|

3. <span data-ttu-id="784b4-216">**选择要应用于项目** 的策略必须匹配的条件 - 可以接受预配置的条件或定义自定义条件。</span><span class="sxs-lookup"><span data-stu-id="784b4-216">**Choose the conditions that must be matched for a policy to be applied to an item** - you can accept pre-configured conditions or define custom conditions.</span></span> <span data-ttu-id="784b4-217">示例如下：</span><span class="sxs-lookup"><span data-stu-id="784b4-217">Some examples are:</span></span>

- <span data-ttu-id="784b4-218">项包含特定上下文中使用的指定类型的敏感信息。</span><span class="sxs-lookup"><span data-stu-id="784b4-218">item contains a specified kind of sensitive information that is being used in a certain context.</span></span> <span data-ttu-id="784b4-219">例如，向组织外部的收件人发送电子邮件的 95 个社会保险号码。</span><span class="sxs-lookup"><span data-stu-id="784b4-219">For example, 95 social security numbers being emailed to recipient outside your org.</span></span>
- <span data-ttu-id="784b4-220">项具有指定的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="784b4-220">item has a specified sensitivity label</span></span>
- <span data-ttu-id="784b4-221">包含敏感信息的项目在内部或外部共享</span><span class="sxs-lookup"><span data-stu-id="784b4-221">item with sensitive information is shared either internally or externally</span></span>

4. <span data-ttu-id="784b4-222">**选择在满足策略** 条件时要采取的操作 - 操作取决于活动发生的位置。</span><span class="sxs-lookup"><span data-stu-id="784b4-222">**Choose the action to take when the policy conditions are met** - The actions depend on the location where the activity is happening.</span></span>  <span data-ttu-id="784b4-223">示例如下：</span><span class="sxs-lookup"><span data-stu-id="784b4-223">Some examples are:</span></span>

- <span data-ttu-id="784b4-224">SharePoint/Exchange/OneDrive：阻止组织外部人员表单访问内容。</span><span class="sxs-lookup"><span data-stu-id="784b4-224">SharePoint/Exchange/OneDrive: Block people who are outside your organization form accessing the content.</span></span> <span data-ttu-id="784b4-225">向用户显示提示，并发送电子邮件通知，告知他们正在采取 DLP 策略禁止的操作。</span><span class="sxs-lookup"><span data-stu-id="784b4-225">Show the user a tip and send them an email notification that they are taking an action that is prohibited by the DLP policy.</span></span>
- <span data-ttu-id="784b4-226">Teams聊天和频道：阻止在聊天或频道中共享敏感信息</span><span class="sxs-lookup"><span data-stu-id="784b4-226">Teams Chat and Channel: Block sensitive information from being shared in the chat or channel</span></span>
- <span data-ttu-id="784b4-227">Windows 10设备：审核或限制将敏感项复制到可删除的 USB 设备</span><span class="sxs-lookup"><span data-stu-id="784b4-227">Windows 10 Devices: Audit or restrict copying a sensitive item to a removeable USB device</span></span> 
- <span data-ttu-id="784b4-228">Office应用：显示弹出窗口，通知用户他们正在参与有风险的行为，并阻止或阻止但允许替代。</span><span class="sxs-lookup"><span data-stu-id="784b4-228">Office Apps: Show a popup notifying the user that they are engaging in a risky behavior and block or block but allow override.</span></span>
- <span data-ttu-id="784b4-229">本地文件共享：将文件从存储位置移动到隔离文件夹</span><span class="sxs-lookup"><span data-stu-id="784b4-229">On-premises file shares: move the file from where it is stored to a quarantine folder</span></span>

> [!NOTE]
> <span data-ttu-id="784b4-230">条件和要采取的操作在名为 Rule 的对象中定义。</span><span class="sxs-lookup"><span data-stu-id="784b4-230">The conditions and the actions to take are defined in an object called a Rule.</span></span>

<!--## Create a DLP policy

All DLP policies are created and maintained in the Microsoft 365 Compliance center. See, INSERT LINK TO ARTICLE THAT WILL START WALKING THEM THROUGH THE POLICY CREATION PROCEDURES for more information.-->

<span data-ttu-id="784b4-231">在合规性中心创建 DLP 策略后，该策略将存储在中央策略存储中，然后同步到各种内容源，包括：</span><span class="sxs-lookup"><span data-stu-id="784b4-231">After you create a DLP policy in the Compliance Center, it's stored in a central policy store, and then synced to the various content sources, including:</span></span>
  
- <span data-ttu-id="784b4-232">Exchange Online，并从它同步到 Outlook 网页版和 Outlook。</span><span class="sxs-lookup"><span data-stu-id="784b4-232">Exchange Online, and from there to Outlook on the web and Outlook.</span></span>
- <span data-ttu-id="784b4-233">OneDrive for Business 网站。</span><span class="sxs-lookup"><span data-stu-id="784b4-233">OneDrive for Business sites.</span></span>
- <span data-ttu-id="784b4-234">SharePoint Online 网站。</span><span class="sxs-lookup"><span data-stu-id="784b4-234">SharePoint Online sites.</span></span>
- <span data-ttu-id="784b4-235">Office 桌面程序（Excel、PowerPoint 和 Word）。</span><span class="sxs-lookup"><span data-stu-id="784b4-235">Office desktop programs (Excel, PowerPoint, and Word).</span></span>
- <span data-ttu-id="784b4-236">Microsoft Teams 频道和聊天消息。</span><span class="sxs-lookup"><span data-stu-id="784b4-236">Microsoft Teams channels and chat messages.</span></span>
    
<span data-ttu-id="784b4-237">该策略同步到正确的位置后，它将开始评估内容并强制执行操作。</span><span class="sxs-lookup"><span data-stu-id="784b4-237">After the policy's synced to the right locations, it starts to evaluate content and enforce actions.</span></span>

## <a name="viewing-policy-application-results"></a><span data-ttu-id="784b4-238">查看策略应用程序结果</span><span class="sxs-lookup"><span data-stu-id="784b4-238">Viewing policy application results</span></span>

<span data-ttu-id="784b4-239">DLP 报告大量信息，Microsoft 365监视、策略匹配和操作以及用户活动。</span><span class="sxs-lookup"><span data-stu-id="784b4-239">DLP reports a vast amount of information into Microsoft 365 from monitoring, policy matches and actions, and user activities.</span></span> <span data-ttu-id="784b4-240">你将需要使用和操作该信息，以调整策略和对敏感项目采取的会审操作。</span><span class="sxs-lookup"><span data-stu-id="784b4-240">You'll need to consume and act on that information to tune your policies and triage actions taken on sensitive items.</span></span> <span data-ttu-id="784b4-241">该遥测首先会进入Microsoft 365[](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center)中心审核日志，然后进行处理，然后转到不同的报告工具。</span><span class="sxs-lookup"><span data-stu-id="784b4-241">The telemetry goes into the [Microsoft 365 Compliance center Audit Logs](search-the-audit-log-in-security-and-compliance.md#search-the-audit-log-in-the-compliance-center) first, is processed, and makes its way to different reporting tools.</span></span> <span data-ttu-id="784b4-242">每个报告工具都有不同的用途。</span><span class="sxs-lookup"><span data-stu-id="784b4-242">Each reporting tool has a different purpose.</span></span>  

### <a name="dlp-alerts-dashboard"></a><span data-ttu-id="784b4-243">DLP 警报仪表板</span><span class="sxs-lookup"><span data-stu-id="784b4-243">DLP Alerts Dashboard</span></span>

<span data-ttu-id="784b4-244">当 DLP 对敏感项目采取操作时，可以通过可配置的警报通知您该操作。</span><span class="sxs-lookup"><span data-stu-id="784b4-244">When DLP takes an action on a sensitive item, you can be notified of that action via a configurable alert.</span></span> <span data-ttu-id="784b4-245">合规性中心在 DLP 警报管理仪表板 中提供它们，而不是让这些警报在邮箱中可供你 [浏览](dlp-configure-view-alerts-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="784b4-245">Rather than having these alerts pile up in a mailbox for you to sift through, the Compliance center makes them available in the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span> <span data-ttu-id="784b4-246">使用 DLP 警报仪表板配置警报、查看警报、对警报分类并跟踪 DLP 警报的解析。</span><span class="sxs-lookup"><span data-stu-id="784b4-246">Use the DLP Alerts dashboard to configure alerts, review them, triage them and track resolution of DLP Alerts.</span></span> <span data-ttu-id="784b4-247">下面是策略匹配和来自设备的活动生成的警报Windows 10示例。</span><span class="sxs-lookup"><span data-stu-id="784b4-247">Here's an example of alerts generated by policy matches and activities from Windows 10 devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="784b4-248">![警报信息](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="784b4-248">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="784b4-249">你还可以在同一仪表板中查看关联事件的详细信息以及丰富元数据</span><span class="sxs-lookup"><span data-stu-id="784b4-249">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="784b4-250">![事件信息](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="784b4-250">![event info](../media/Event-info-1.png)</span></span>

### <a name="reports"></a><span data-ttu-id="784b4-251">报表</span><span class="sxs-lookup"><span data-stu-id="784b4-251">Reports</span></span>

<span data-ttu-id="784b4-252">[DLP 报告](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention)显示了一段时间的广泛趋势，并提供了以下具体见解：</span><span class="sxs-lookup"><span data-stu-id="784b4-252">The [DLP reports](view-the-dlp-reports.md#view-the-reports-for-data-loss-prevention) show broad trends over time and give specific insights into:</span></span>

- <span data-ttu-id="784b4-253">**DLP 策略随着时间的推移匹配** ，并按日期范围、位置、策略或操作进行筛选</span><span class="sxs-lookup"><span data-stu-id="784b4-253">**DLP Policy Matches** over time and filter by date range, location, policy, or action</span></span>
- <span data-ttu-id="784b4-254">**DLP 事件匹配** 还会显示一段时间的匹配项，但会透视项目而不是策略规则。</span><span class="sxs-lookup"><span data-stu-id="784b4-254">**DLP incident matches** also shows matches over time, but pivots on the items rather than the policy rules.</span></span>
- <span data-ttu-id="784b4-255">**DLP 误报和重写** 显示误报计数，如果配置，则显示用户替代以及用户理由。</span><span class="sxs-lookup"><span data-stu-id="784b4-255">**DLP false positives and overrides** shows the count of false positives and, if configured, user-overrides along with the user justification.</span></span>

### <a name="dlp-activity-explorer"></a><span data-ttu-id="784b4-256">DLP 活动资源管理器</span><span class="sxs-lookup"><span data-stu-id="784b4-256">DLP Activity Explorer</span></span>

<span data-ttu-id="784b4-257">DLP 页面上的"活动资源管理器"选项卡将" *活动* "筛选器预设为 *DLPRuleMatch*。</span><span class="sxs-lookup"><span data-stu-id="784b4-257">The Activity explorer tab on the DLP page has the *Activity* filter preset to *DLPRuleMatch*.</span></span> <span data-ttu-id="784b4-258">使用此工具查看与包含敏感信息或应用了标签的内容相关的活动，例如更改了哪些标签、修改了哪些文件以及匹配了规则。</span><span class="sxs-lookup"><span data-stu-id="784b4-258">Use this tool to review activity related to content that contains sensitive info or has labels applied, such as what labels were changed, files were modified, and matched a rule.</span></span>

![<span data-ttu-id="784b4-259">DLPRuleMatch 范围活动资源管理器的屏幕截图</span><span class="sxs-lookup"><span data-stu-id="784b4-259">screenshot of the DLPRuleMatch scoped activity explorer</span></span> ](../media/dlp-activity-explorer.png)

<span data-ttu-id="784b4-260">有关详细信息，请参阅活动 [资源管理器入门](data-classification-activity-explorer.md)</span><span class="sxs-lookup"><span data-stu-id="784b4-260">For more information, see [Get started with activity explorer](data-classification-activity-explorer.md)</span></span>

<span data-ttu-id="784b4-261">若要了解有关 DLP Microsoft 365，请参阅：</span><span class="sxs-lookup"><span data-stu-id="784b4-261">To learn more about Microsoft 365 DLP, see:</span></span>

- [<span data-ttu-id="784b4-262">了解 Microsoft 365 终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="784b4-262">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="784b4-263">了解 Microsoft Teams（预览版）中的默认数据丢失防护策略</span><span class="sxs-lookup"><span data-stu-id="784b4-263">Learn about the default data loss prevention policy in Microsoft Teams (preview)</span></span>](dlp-teams-default-policy.md)
- [<span data-ttu-id="784b4-264">了解 Microsoft 365 本地扫描仪数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="784b4-264">Learn about the Microsoft 365 data loss prevention on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-learn.md)
- [<span data-ttu-id="784b4-265">了解 Microsoft 合规性扩展（预览版）</span><span class="sxs-lookup"><span data-stu-id="784b4-265">Learn about the Microsoft Compliance Extension (preview)</span></span>](dlp-chrome-learn-about.md)
- [<span data-ttu-id="784b4-266">了解数据丢失防护警报仪表板</span><span class="sxs-lookup"><span data-stu-id="784b4-266">Learn about the data loss prevention Alerts dashboard</span></span>](dlp-alerts-dashboard-learn.md)

<span data-ttu-id="784b4-267">若要了解如何使用数据丢失防护来遵守数据隐私法规，请参阅使用 Microsoft 365 (aka.ms/m365dataprivacy) 部署数据[隐私法规](../solutions/information-protection-deploy.md)的信息保护。</span><span class="sxs-lookup"><span data-stu-id="784b4-267">To learn how to use data loss prevention to comply with data privacy regulations, see [Deploy information protection for data privacy regulations with Microsoft 365](../solutions/information-protection-deploy.md)  (aka.ms/m365dataprivacy).</span></span>