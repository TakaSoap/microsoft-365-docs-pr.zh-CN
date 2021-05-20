---
title: 数据丢失防护计划
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
description: 数据丢失防护的规划过程概述
ms.openlocfilehash: 84f1dc0426ba88f934c1d67d71f75364adeb4340
ms.sourcegitcommit: 9541d5e6720a06327dc785e3ad7e8fb11246fd72
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/20/2021
ms.locfileid: "52583348"
---
# <a name="plan-for-data-loss-prevention-dlp"></a><span data-ttu-id="2c81d-103">规划 DLP (数据丢失) </span><span class="sxs-lookup"><span data-stu-id="2c81d-103">Plan for data loss prevention (DLP)</span></span>

<span data-ttu-id="2c81d-104">每个组织都将以不同的方式 (DLP) 数据丢失防护，因为每个组织的业务需求、目标、资源和情况对于他们来说都是独一无二的。</span><span class="sxs-lookup"><span data-stu-id="2c81d-104">Every organization will plan for and implement data loss prevention (DLP) differently, because every organization's business needs, goals, resources, and situation are unique to them.</span></span> <span data-ttu-id="2c81d-105">但是，所有成功的 DLP 实现都有一些共同的元素。</span><span class="sxs-lookup"><span data-stu-id="2c81d-105">However, there are elements that are common to all successful DLP implementations.</span></span> <span data-ttu-id="2c81d-106">本文介绍组织在 DLP 规划中使用的最佳实践。</span><span class="sxs-lookup"><span data-stu-id="2c81d-106">This article presents the best practices that are used by organizations in their DLP planning.</span></span>

## <a name="multiple-starting-points"></a><span data-ttu-id="2c81d-107">多个起点</span><span class="sxs-lookup"><span data-stu-id="2c81d-107">Multiple starting points</span></span>

<span data-ttu-id="2c81d-108">许多组织选择实施 DLP 以遵守各种政府或行业法规。</span><span class="sxs-lookup"><span data-stu-id="2c81d-108">Many organizations choose to implement DLP to comply with various governmental or industry regulations.</span></span> <span data-ttu-id="2c81d-109">例如，欧盟的一般数据保护条例 (GDPR) 、《健康保险便利和责任法》 (HIPAA) 或加州消费者隐私法案 (CCPA) 。</span><span class="sxs-lookup"><span data-stu-id="2c81d-109">For example, the European Union's General Data Protection Regulation (GDPR), or the Health Insurance Portability and Accountability Act (HIPAA), or the California Consumer Privacy Act (CCPA).</span></span> <span data-ttu-id="2c81d-110">它们还实施数据丢失防护来保护其知识产权。</span><span class="sxs-lookup"><span data-stu-id="2c81d-110">They also implement data loss prevention to protect their intellectual property.</span></span> <span data-ttu-id="2c81d-111">但是 DLP 旅程中的起始位置和最终目的地有所不同。</span><span class="sxs-lookup"><span data-stu-id="2c81d-111">But the starting place and ultimate destination in the DLP journey vary.</span></span> 

<span data-ttu-id="2c81d-112">组织可以开始其 DLP 旅程：</span><span class="sxs-lookup"><span data-stu-id="2c81d-112">Organizations can start their DLP journey:</span></span>

- <span data-ttu-id="2c81d-113">来自平台焦点，例如想要保护聊天Teams频道消息或Windows 10信息</span><span class="sxs-lookup"><span data-stu-id="2c81d-113">from a platform focus, like wanting to protect information in Teams Chat and Channel messages or on Windows 10 devices</span></span>
- <span data-ttu-id="2c81d-114">了解他们希望优先保护哪些敏感信息（如医疗保健记录）并直接定义保护策略</span><span class="sxs-lookup"><span data-stu-id="2c81d-114">knowing what sensitive information they want to prioritize protecting, like health care records, and going straight to defining policies to protect it</span></span>
- <span data-ttu-id="2c81d-115">在不知道敏感信息是什么、敏感信息位于何处以及谁对敏感信息执行哪些操作的情况下，他们从发现和分类开始，采取更系统的方法</span><span class="sxs-lookup"><span data-stu-id="2c81d-115">without knowing what their sensitive information is, where it is, and who is doing what with it so they start with discovery and categorization and take a more methodical approach</span></span>
- <span data-ttu-id="2c81d-116">在不知道敏感信息是什么、敏感信息位于何处或谁正在对敏感信息执行哪些任务的情况下，他们直接进入定义策略，将那些结果用作起点，然后从该位置优化其策略</span><span class="sxs-lookup"><span data-stu-id="2c81d-116">without knowing what their sensitive information is, or where it is, or who is doing what with it, but they will move straight to defining policies and use those outcomes as a starting place and then refine their policies from there</span></span>
- <span data-ttu-id="2c81d-117">知道他们需要实现完整的信息保护Microsoft 365，因此打算采用更长期、有条理的方法</span><span class="sxs-lookup"><span data-stu-id="2c81d-117">knowing that they need to implement the full Microsoft 365 Information Protection stack and so intend to take a longer term, methodical approach</span></span>

<span data-ttu-id="2c81d-118">这些只是客户如何处理 DLP 的一些示例，从何处开始并不重要，Microsoft 365 DLP 足够灵活，可以适应从开始到完全实现的数据丢失防护策略的各种类型的信息保护之旅。</span><span class="sxs-lookup"><span data-stu-id="2c81d-118">These are just some examples of how customers can approach DLP and it doesn't matter where you start from, Microsoft 365 DLP is flexible enough to accommodate various types of information protection journeys from start to a fully realized data loss prevention strategy.</span></span> 

## <a name="overview-of-planning-process"></a><span data-ttu-id="2c81d-119">规划过程概述</span><span class="sxs-lookup"><span data-stu-id="2c81d-119">Overview of planning process</span></span>

<span data-ttu-id="2c81d-120">[了解数据丢失防护介绍了](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)DLP 规划过程的三[个不同方面](dlp-learn-about-dlp.md#plan-for-dlp)。</span><span class="sxs-lookup"><span data-stu-id="2c81d-120">The [Learn about data loss prevention](dlp-learn-about-dlp.md#learn-about-data-loss-prevention) introduces the three different aspects of the [DLP planning process](dlp-learn-about-dlp.md#plan-for-dlp).</span></span> <span data-ttu-id="2c81d-121">我们将在此处详细介绍所有 DLP 计划的常见元素。</span><span class="sxs-lookup"><span data-stu-id="2c81d-121">We'll go into more detail here on the elements that are common to all DLP plans.</span></span>

### <a name="identify-stakeholders"></a><span data-ttu-id="2c81d-122">确定利益干系人</span><span class="sxs-lookup"><span data-stu-id="2c81d-122">Identify stakeholders</span></span>

<span data-ttu-id="2c81d-123">实施后，DLP 策略可应用于组织的很大一部分。</span><span class="sxs-lookup"><span data-stu-id="2c81d-123">When implemented, DLP policies can be applied across large portions of your organization.</span></span> <span data-ttu-id="2c81d-124">IT 无法自行制定广泛的计划，且无负面影响。</span><span class="sxs-lookup"><span data-stu-id="2c81d-124">IT can't develop a broad ranging plan on their own without negative consequences.</span></span> <span data-ttu-id="2c81d-125">您需要确定能够：</span><span class="sxs-lookup"><span data-stu-id="2c81d-125">You need to identify the stakeholders who can:</span></span>

- <span data-ttu-id="2c81d-126">介绍组织要遵守的法规、法律和行业标准</span><span class="sxs-lookup"><span data-stu-id="2c81d-126">describe the regulations, laws, and industry standards your organization is subject to</span></span>
- <span data-ttu-id="2c81d-127">要保护的敏感项目类别</span><span class="sxs-lookup"><span data-stu-id="2c81d-127">the categories of sensitive items to be protected</span></span>
- <span data-ttu-id="2c81d-128">它们所使用的业务流程</span><span class="sxs-lookup"><span data-stu-id="2c81d-128">the business processes they are used in</span></span>
- <span data-ttu-id="2c81d-129">应受限的风险行为</span><span class="sxs-lookup"><span data-stu-id="2c81d-129">the risky behavior that should be limited</span></span>
- <span data-ttu-id="2c81d-130">根据所涉及项目的敏感度和风险确定应首先保护哪些数据的优先级</span><span class="sxs-lookup"><span data-stu-id="2c81d-130">prioritize which data should be protected first based on the sensitivity of the items and risk involved</span></span>
- <span data-ttu-id="2c81d-131">概述 DLP 策略匹配事件检查和修正过程</span><span class="sxs-lookup"><span data-stu-id="2c81d-131">outline the DLP policy match event review and remediation process</span></span> 
 
<span data-ttu-id="2c81d-132">一般情况下，这些需要具有 85% 的法规和合规性保护，以及 15% 的知识产权保护。</span><span class="sxs-lookup"><span data-stu-id="2c81d-132">In general these needs tend to be 85% regulatory and compliance protection, and 15% intellectual property protection.</span></span> <span data-ttu-id="2c81d-133">下面是有关要包括在规划过程中的角色的一些建议：</span><span class="sxs-lookup"><span data-stu-id="2c81d-133">Here are some suggestions on roles to include in your planning process:</span></span>

- <span data-ttu-id="2c81d-134">法规和合规部官员</span><span class="sxs-lookup"><span data-stu-id="2c81d-134">Regulatory and compliance officers</span></span>
- <span data-ttu-id="2c81d-135">首席风险官</span><span class="sxs-lookup"><span data-stu-id="2c81d-135">Chief risk officer</span></span>
- <span data-ttu-id="2c81d-136">法律官</span><span class="sxs-lookup"><span data-stu-id="2c81d-136">Legal officers</span></span>
- <span data-ttu-id="2c81d-137">安全与合规部官员</span><span class="sxs-lookup"><span data-stu-id="2c81d-137">Security and compliance officers</span></span>
- <span data-ttu-id="2c81d-138">数据项的业务所有者</span><span class="sxs-lookup"><span data-stu-id="2c81d-138">Business owners for the data items</span></span>
- <span data-ttu-id="2c81d-139">业务用户</span><span class="sxs-lookup"><span data-stu-id="2c81d-139">Business users</span></span>
- <span data-ttu-id="2c81d-140">IT</span><span class="sxs-lookup"><span data-stu-id="2c81d-140">IT</span></span>

### <a name="describe-the-categories-of-sensitive-information-to-protect"></a><span data-ttu-id="2c81d-141">描述要保护的敏感信息类别</span><span class="sxs-lookup"><span data-stu-id="2c81d-141">Describe the categories of sensitive information to protect</span></span>

<span data-ttu-id="2c81d-142">然后，利益干系人描述要保护的敏感信息的类别业务流程使用的敏感信息类别。</span><span class="sxs-lookup"><span data-stu-id="2c81d-142">The stakeholders then describe the categories of sensitive information to be protected and the business process that they're used in.</span></span> <span data-ttu-id="2c81d-143">例如，Microsoft 365 DLP 定义以下类别：</span><span class="sxs-lookup"><span data-stu-id="2c81d-143">For example, Microsoft 365 DLP defines these categories:</span></span>

- <span data-ttu-id="2c81d-144">金融</span><span class="sxs-lookup"><span data-stu-id="2c81d-144">Financial</span></span> 
- <span data-ttu-id="2c81d-145">医疗健康信息</span><span class="sxs-lookup"><span data-stu-id="2c81d-145">Medical and health information</span></span>
- <span data-ttu-id="2c81d-146">隐私</span><span class="sxs-lookup"><span data-stu-id="2c81d-146">Privacy</span></span>
- <span data-ttu-id="2c81d-147">自定义警报</span><span class="sxs-lookup"><span data-stu-id="2c81d-147">Custom</span></span>

<span data-ttu-id="2c81d-148">利益干系人可能会将敏感信息标识为"We are a data processor， so we have to implement privacy protections on data subject information and financial information"。</span><span class="sxs-lookup"><span data-stu-id="2c81d-148">The stakeholders might identify the sensitive information as "We are a data processor, so we have to implement privacy protections on data subject information and financial information".</span></span>

 
  <!-- The business process is important as it informs the ‘data at rest’, ‘data in transit’, ‘data in use’ aspect of DLP planning and who should be sharing the items and who should not.-->

### <a name="set-goals-and-strategy"></a><span data-ttu-id="2c81d-149">设置目标和策略</span><span class="sxs-lookup"><span data-stu-id="2c81d-149">Set goals and strategy</span></span>

<span data-ttu-id="2c81d-150">确定利益干系人并知道需要保护哪些敏感信息以及在何处使用敏感信息后，利益干系人可以设置其保护目标，IT 部门可以制定实施计划。</span><span class="sxs-lookup"><span data-stu-id="2c81d-150">Once you have identified your stakeholders and you know which sensitive information needs protection and where it's used, the stakeholders can set their protection goals and IT can develop an implementation plan.</span></span> 


 <!--
### Discovery
 for the locations (DLP workloads) of these types of items.  (mapping DLP locations and data at rest, data in transit, data in use)

### IT can start coding test policies
start small and always in test mode. Note that DLP policies can feed into insider risk.

### Business process owners help with tuning
 false positive/false negative results and fitting DLP into their business processes.

-->

### <a name="set-implementation-plan"></a><span data-ttu-id="2c81d-151">设置实施计划</span><span class="sxs-lookup"><span data-stu-id="2c81d-151">Set implementation plan</span></span>

<span data-ttu-id="2c81d-152">你的实施计划应包括：</span><span class="sxs-lookup"><span data-stu-id="2c81d-152">Your implementation plan should include:</span></span>

- <span data-ttu-id="2c81d-153">映射你的开始状态和所需的结束状态以及从一个开始状态到另一个状态的步骤</span><span class="sxs-lookup"><span data-stu-id="2c81d-153">Mapping out your starting state and desired end state and the steps to get from one to the other</span></span>
- <span data-ttu-id="2c81d-154">如何处理敏感项目的发现</span><span class="sxs-lookup"><span data-stu-id="2c81d-154">how you will address discovery of sensitive items</span></span>
- <span data-ttu-id="2c81d-155">策略规划及其实现顺序</span><span class="sxs-lookup"><span data-stu-id="2c81d-155">policy planning and the order that they will be implemented</span></span>
- <span data-ttu-id="2c81d-156">您将如何处理任何先决条件</span><span class="sxs-lookup"><span data-stu-id="2c81d-156">how you will address any prerequisites</span></span>
- <span data-ttu-id="2c81d-157">规划在移动到强制执行之前如何首先测试策略</span><span class="sxs-lookup"><span data-stu-id="2c81d-157">planning on how policies will first be tested before moving to enforcement</span></span>
- <span data-ttu-id="2c81d-158">如何培训最终用户</span><span class="sxs-lookup"><span data-stu-id="2c81d-158">how you will train your end users</span></span>
- <span data-ttu-id="2c81d-159">如何测试和调整策略</span><span class="sxs-lookup"><span data-stu-id="2c81d-159">how you will test and tune your policies</span></span>
- <span data-ttu-id="2c81d-160">如何根据不断变化的法规、法律、行业标准或知识产权和业务需求审阅和更新数据丢失防护策略</span><span class="sxs-lookup"><span data-stu-id="2c81d-160">how you will review and update your data loss prevention strategy based on changing regulatory, legal, industry standard or intellectual property protection and business needs</span></span>

#### <a name="map-out-path-from-start-to-desired-end-state"></a><span data-ttu-id="2c81d-161">从开始到所需结束状态映射路径</span><span class="sxs-lookup"><span data-stu-id="2c81d-161">Map out path from start to desired end state</span></span>

<span data-ttu-id="2c81d-162">记录组织从开始状态到所需结束状态的方式对于与利益干系人沟通和设置项目范围至关重要。</span><span class="sxs-lookup"><span data-stu-id="2c81d-162">Documenting how your organization is going to get from its starting state to the desired end state is essential to communicating with your stakeholders and setting the project scope.</span></span> <span data-ttu-id="2c81d-163">下面是一组通常用于部署 DLP 的步骤。</span><span class="sxs-lookup"><span data-stu-id="2c81d-163">Here is a set of steps that are commonly used to deploy DLP.</span></span> <span data-ttu-id="2c81d-164">你更需要此详细信息，但可以使用它来设置 DLP 采用路径。</span><span class="sxs-lookup"><span data-stu-id="2c81d-164">You'll want more detail than this, but you can use this to frame your DLP adoption path.</span></span>

![显示部署 DLP 的常见顺序的图形](../media/dlp-deployment-planning.png)

#### <a name="sensitive-item-discovery"></a><span data-ttu-id="2c81d-166">敏感项目发现</span><span class="sxs-lookup"><span data-stu-id="2c81d-166">Sensitive item discovery</span></span>

<span data-ttu-id="2c81d-167">有多种方法可发现各个敏感项及其所在的位置。</span><span class="sxs-lookup"><span data-stu-id="2c81d-167">There are multiple ways to discover what individual sensitive items are and where they are located.</span></span> <span data-ttu-id="2c81d-168">您可能已部署敏感度标签，或者您可能决定将广泛的 DLP 策略部署到仅发现和审核项目的所有位置。</span><span class="sxs-lookup"><span data-stu-id="2c81d-168">You may have sensitivity labels already deployed or you may have decided to deploy a broad DLP policy to all locations that only discovers and audits items.</span></span> <span data-ttu-id="2c81d-169">若要了解更多信息，请参阅 [了解数据](information-protection.md#know-your-data)。</span><span class="sxs-lookup"><span data-stu-id="2c81d-169">To learn more, see [Know your data](information-protection.md#know-your-data).</span></span>

#### <a name="policy-planning"></a><span data-ttu-id="2c81d-170">策略规划</span><span class="sxs-lookup"><span data-stu-id="2c81d-170">Policy planning</span></span>

<span data-ttu-id="2c81d-171">开始采用 DLP 时，可以使用这些问题重点关注策略设计和实施工作。</span><span class="sxs-lookup"><span data-stu-id="2c81d-171">As you begin your DLP adoption, you can use these questions to focus your policy design and implementation efforts.</span></span>

##### <a name="what-laws-regulations-and-industry-standards-must-your-organization-comply-with"></a><span data-ttu-id="2c81d-172">您的组织必须遵守哪些法律、法规和行业标准？</span><span class="sxs-lookup"><span data-stu-id="2c81d-172">What laws, regulations and industry standards must your organization comply with?</span></span>

<span data-ttu-id="2c81d-173">因为许多组织都以合规性为目标来使用 DLP，所以回答此问题是规划 DLP 实施的自然起点。</span><span class="sxs-lookup"><span data-stu-id="2c81d-173">Because many organizations come to DLP with the goal of regulatory compliance, answering this question is a natural starting place for planning your DLP implementation.</span></span> <span data-ttu-id="2c81d-174">但是，作为 IT 实施者，你可能没有找到答案。</span><span class="sxs-lookup"><span data-stu-id="2c81d-174">But, as the IT implementer, you're probably not positioned to answer it.</span></span> <span data-ttu-id="2c81d-175">它需由法律团队和业务主管回答。</span><span class="sxs-lookup"><span data-stu-id="2c81d-175">It needs to be answered by your legal team and business executives.</span></span> 
 
<span data-ttu-id="2c81d-176">**示例** 你的组织受英国</span><span class="sxs-lookup"><span data-stu-id="2c81d-176">**Example** Your organization is subject to U.K.</span></span> <span data-ttu-id="2c81d-177">财务法规。</span><span class="sxs-lookup"><span data-stu-id="2c81d-177">financial regulations.</span></span>


##### <a name="what-sensitive-items-does-your-organization-have-that-must-be-protected-from-leakage"></a><span data-ttu-id="2c81d-178">你的组织具有哪些必须防止泄露的敏感项目？</span><span class="sxs-lookup"><span data-stu-id="2c81d-178">What sensitive items does your organization have that must be protected from leakage?</span></span>

<span data-ttu-id="2c81d-179">在贵组织了解其就法规合规性需求而言的情况后，您将了解需要保护哪些敏感项目免受泄露，以及您希望如何确定策略实施优先级以保护它们。</span><span class="sxs-lookup"><span data-stu-id="2c81d-179">Once your organization knows where it stands in terms of regulatory compliance needs, you'll have some idea of what sensitive items need to be protected from leakage and how you want to prioritize policy implementation to protect them.</span></span> <span data-ttu-id="2c81d-180">这将帮助你选择最合适的 DLP 策略模板。</span><span class="sxs-lookup"><span data-stu-id="2c81d-180">This will help you choose the most appropriate DLP policy templates.</span></span> <span data-ttu-id="2c81d-181">Microsoft 365预配置的 DLP 模板用于财务、医疗与健康、隐私，并且您可以使用自定义模板构建您自己的模板。</span><span class="sxs-lookup"><span data-stu-id="2c81d-181">Microsoft 365 comes with pre-configured DLP templates for Financial, Medical and health, Privacy, and you can build your own using the Custom template.</span></span> <span data-ttu-id="2c81d-182">设计和创建实际 DLP 策略时，了解此问题的答案还将帮助你选择正确的 [敏感信息类型](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types)。</span><span class="sxs-lookup"><span data-stu-id="2c81d-182">As you design and create your actual DLP policies, knowing the answer to this question will also help you choose the right [sensitive information type](sensitive-information-type-learn-about.md#learn-about-sensitive-information-types).</span></span>

<span data-ttu-id="2c81d-183">**示例** 若要快速入门，请选取 `U.K. Financial Data` 策略模板，其中包括 、 和 `Credit Card Number` `EU Debit Card Number` `SWIFT Code` 敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="2c81d-183">**Example** To get started quickly, you pick the `U.K. Financial Data` policy template, which includes the `Credit Card Number`, `EU Debit Card Number`, and `SWIFT Code` sensitive information types.</span></span> 

##### <a name="where-are-the-sensitive-items-and-what-business-processes-are-they-involved-in"></a><span data-ttu-id="2c81d-184">敏感项目及其涉及的业务流程在哪里？</span><span class="sxs-lookup"><span data-stu-id="2c81d-184">Where are the sensitive items and what business processes are they involved in?</span></span>

<span data-ttu-id="2c81d-185">在业务过程中，每天都会使用包含组织敏感信息的项目。</span><span class="sxs-lookup"><span data-stu-id="2c81d-185">The items that contain your organizations sensitive information are used every day in the course of doing business.</span></span> <span data-ttu-id="2c81d-186">您需要了解该敏感信息的实例可能会发生在何处以及这些实例在哪些业务流程中使用。</span><span class="sxs-lookup"><span data-stu-id="2c81d-186">You need to know where instances of that sensitive information may occur and what business processes they are used in.</span></span> <span data-ttu-id="2c81d-187">这将帮助你选择要应用 DLP 策略的合适位置。</span><span class="sxs-lookup"><span data-stu-id="2c81d-187">This will help you choose the right locations to apply your DLP policies to.</span></span> <span data-ttu-id="2c81d-188">Microsoft 365DLP 策略适用于位置：</span><span class="sxs-lookup"><span data-stu-id="2c81d-188">Microsoft 365 DLP policies are applied to locations:</span></span>

- <span data-ttu-id="2c81d-189">Exchange 电子邮件</span><span class="sxs-lookup"><span data-stu-id="2c81d-189">Exchange email</span></span>
- <span data-ttu-id="2c81d-190">SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="2c81d-190">SharePoint sites</span></span>
- <span data-ttu-id="2c81d-191">OneDrive 账户</span><span class="sxs-lookup"><span data-stu-id="2c81d-191">OneDrive accounts</span></span>
- <span data-ttu-id="2c81d-192">Teams 聊天和通道消息</span><span class="sxs-lookup"><span data-stu-id="2c81d-192">Teams chat and channel messages</span></span>
- <span data-ttu-id="2c81d-193">Windows 10设备</span><span class="sxs-lookup"><span data-stu-id="2c81d-193">Windows 10 Devices</span></span>
- <span data-ttu-id="2c81d-194">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2c81d-194">Microsoft Cloud App Security</span></span>
- <span data-ttu-id="2c81d-195">本地存储库</span><span class="sxs-lookup"><span data-stu-id="2c81d-195">On-premises repositories</span></span>

<span data-ttu-id="2c81d-196">**示例** 组织的内部审核员正在跟踪一组信用卡号。</span><span class="sxs-lookup"><span data-stu-id="2c81d-196">**Example** Your organizations' internal auditors are tracking a set of credit card numbers.</span></span> <span data-ttu-id="2c81d-197">他们将其电子表格放在安全的安全SharePoint网站中。</span><span class="sxs-lookup"><span data-stu-id="2c81d-197">They keep a spreadsheet of them in a secure SharePoint site.</span></span> <span data-ttu-id="2c81d-198">一些员工在网站中复制并OneDrive for Business工作，该网站将同步到Windows 10设备。</span><span class="sxs-lookup"><span data-stu-id="2c81d-198">Several of the employees make copies and save them to their work OneDrive for Business site, which is synced to their Windows 10 device.</span></span> <span data-ttu-id="2c81d-199">其中一个将其中 14 个人的列表粘贴到电子邮件中，并尝试将其发送给外部审核员进行审阅。</span><span class="sxs-lookup"><span data-stu-id="2c81d-199">One of them pastes a list of 14 of them in an email and tries to send it to the outside auditors for review.</span></span> <span data-ttu-id="2c81d-200">您希望将策略应用于安全安全SharePoint、所有内部审核员OneDrive for Business帐户、Windows 10设备以及Exchange电子邮件。</span><span class="sxs-lookup"><span data-stu-id="2c81d-200">You'd want to apply the policy to the secure SharePoint site, all the internal auditors OneDrive for Business accounts, their Windows 10 devices, and Exchange email.</span></span>

##### <a name="what-is-your-organizations-tolerance-for-leakage"></a><span data-ttu-id="2c81d-201">组织对泄露的容忍度如何？</span><span class="sxs-lookup"><span data-stu-id="2c81d-201">What is your organizations tolerance for leakage?</span></span>

<span data-ttu-id="2c81d-202">贵组织中不同的组可能对敏感项目泄露的可接受级别和不可接受程度有不同的观点。</span><span class="sxs-lookup"><span data-stu-id="2c81d-202">Different groups in your organization may have different views on what's an acceptable level of sensitive item leakage and what's not.</span></span> <span data-ttu-id="2c81d-203">实现零泄露的实现可能会给业务造成太高的成本。</span><span class="sxs-lookup"><span data-stu-id="2c81d-203">Achieving the perfection of zero leakage may come at too high a cost to the business.</span></span>

<span data-ttu-id="2c81d-204">**示例** 组织的安全组以及法律团队都觉得不得与组织外部的任何人共享信用卡号，并坚持零泄露。</span><span class="sxs-lookup"><span data-stu-id="2c81d-204">**Example** Your organizations' security group, along with the legal team both feel that there should be no sharing of credit card numbers with anyone outside the org and insist on zero leakage.</span></span> <span data-ttu-id="2c81d-205">但是，作为定期审核信用卡号活动的一部分，内部审核员必须与第三方审核员共享一些信用卡号。</span><span class="sxs-lookup"><span data-stu-id="2c81d-205">But, as part of regular review of credit card number activity, the internal auditors must share some credit card numbers with third-party auditors.</span></span> <span data-ttu-id="2c81d-206">如果您的 DLP 策略禁止在组织外共享所有信用卡号，业务流程重大中断并增加了成本，以减少中断，以便内部审核员完成跟踪。</span><span class="sxs-lookup"><span data-stu-id="2c81d-206">If your DLP policy prohibits all sharing of credit card numbers outside the org, there will be a significant business process disruption and added cost to mitigate the disruption in order for the internal auditors to complete their tracking.</span></span> <span data-ttu-id="2c81d-207">管理层领导无法接受此额外成本。</span><span class="sxs-lookup"><span data-stu-id="2c81d-207">This extra cost is unacceptable to the executive leadership.</span></span> <span data-ttu-id="2c81d-208">若要解决此问题，需要进行内部对话，以决定可接受的泄露级别。</span><span class="sxs-lookup"><span data-stu-id="2c81d-208">To resolve this, there needs to be an internal conversation to decide an acceptable level of leakage.</span></span> <span data-ttu-id="2c81d-209">一旦决定，该策略可以为特定人员提供共享信息的例外，或者可在仅审核模式下应用它。</span><span class="sxs-lookup"><span data-stu-id="2c81d-209">Once that is decided the policy can provide exceptions for certain individuals to share the information or it can be applied in audit only mode.</span></span>

#### <a name="planning-for-prerequisites"></a><span data-ttu-id="2c81d-210">规划先决条件</span><span class="sxs-lookup"><span data-stu-id="2c81d-210">Planning for prerequisites</span></span>

<span data-ttu-id="2c81d-211">在监视某些 DLP 位置之前，必须先满足一些先决条件。</span><span class="sxs-lookup"><span data-stu-id="2c81d-211">Before you can monitor some DLP locations, there are prerequisites that must be met.</span></span> <span data-ttu-id="2c81d-212">请参阅 **开始之前部分** ：</span><span class="sxs-lookup"><span data-stu-id="2c81d-212">See the **Before you begin** sections of:</span></span>

- [<span data-ttu-id="2c81d-213">开始进行本地扫描仪的数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="2c81d-213">Get started with the data loss prevention on-premises scanner (preview)</span></span>](dlp-on-premises-scanner-get-started.md#before-you-begin)
- [<span data-ttu-id="2c81d-214">终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="2c81d-214">Get started with Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md#before-you-begin)
- [<span data-ttu-id="2c81d-215">Microsoft 合规性扩展和预览版 (入门) </span><span class="sxs-lookup"><span data-stu-id="2c81d-215">Get started with the Microsoft compliance extension (preview)</span></span>](dlp-chrome-get-started.md#before-you-begin)
- [<span data-ttu-id="2c81d-216">对非 Microsoft 云应用使用数据丢失防护策略 (预览) </span><span class="sxs-lookup"><span data-stu-id="2c81d-216">Use data loss prevention policies for non-Microsoft cloud apps (preview)</span></span>](dlp-use-policies-non-microsoft-cloud-apps.md#before-you-begin)

#### <a name="policy-deployment"></a><span data-ttu-id="2c81d-217">策略部署</span><span class="sxs-lookup"><span data-stu-id="2c81d-217">Policy deployment</span></span>

<span data-ttu-id="2c81d-218">创建 DLP 策略时，您应考虑逐步部署策略，在完全强制执行策略之前评估其影响，并测试其有效性。</span><span class="sxs-lookup"><span data-stu-id="2c81d-218">When you create your DLP policies, you should consider rolling them out gradually to assess their impact and test their effectiveness before fully enforcing them.</span></span> <span data-ttu-id="2c81d-219">例如，您不希望新的 DLP 策略无意中阻止对成千上万个文档的访问或破坏现有业务流程。</span><span class="sxs-lookup"><span data-stu-id="2c81d-219">For example, you don't want a new DLP policy to unintentionally block access to thousands of documents or to break an existing business process.</span></span>
  
<span data-ttu-id="2c81d-220">如果你创建的 DLP 策略具有较大的潜在影响，建议你按以下顺序执行操作：</span><span class="sxs-lookup"><span data-stu-id="2c81d-220">If you're creating DLP policies with a large potential impact, we recommend following this sequence:</span></span>
  
1. <span data-ttu-id="2c81d-221">**在不使用策略提示的情况下启动测试模式**，然后使用 DLP 报告和任何事件报告评估影响。</span><span class="sxs-lookup"><span data-stu-id="2c81d-221">**Start in test mode without Policy Tips** and then use the DLP reports and any incident reports to assess the impact.</span></span> <span data-ttu-id="2c81d-222">您可以使用 DLP 报告查看匹配策略的次数、位置、类型和严重性。</span><span class="sxs-lookup"><span data-stu-id="2c81d-222">You can use DLP reports to view the number, location, type, and severity of policy matches.</span></span> <span data-ttu-id="2c81d-223">根据结果，您可以根据需要微调策略。</span><span class="sxs-lookup"><span data-stu-id="2c81d-223">Based on the results, you can fine-tune the policies as needed.</span></span> <span data-ttu-id="2c81d-224">在测试模式下，DLP 策略不会影响您组织内的工作人员的工作效率。</span><span class="sxs-lookup"><span data-stu-id="2c81d-224">In test mode, DLP policies will not impact the productivity of people working in your organization.</span></span> <span data-ttu-id="2c81d-225">此外，使用此阶段测试您的工作流，进行 DLP 事件审阅并发出修正。</span><span class="sxs-lookup"><span data-stu-id="2c81d-225">Also, use this stage to test out your workflow for DLP event review and issue remediation.</span></span>
    
2. <span data-ttu-id="2c81d-226">**使用通知和** 策略策略使用技巧移动到测试模式，以便你可以开始向用户学习合规性策略，并为将要应用的策略做好准备。</span><span class="sxs-lookup"><span data-stu-id="2c81d-226">**Move to Test mode with notifications and Policy Tips** so that you can begin to teach users about your compliance policies and prepare them for the policies that are going to be applied.</span></span> <span data-ttu-id="2c81d-227">通过指向组织策略页的链接，该链接在策略提示中提供有关策略的更多详细信息，这非常有用。</span><span class="sxs-lookup"><span data-stu-id="2c81d-227">It's useful to have a link to an organization policy page that provides more details about the policy in the policy tip.</span></span> <span data-ttu-id="2c81d-228">在此阶段，您还可以要求用户报告误报，以便可以进一步优化策略。</span><span class="sxs-lookup"><span data-stu-id="2c81d-228">At this stage, you can also ask users to report false positives so that you can further refine the policies.</span></span> <span data-ttu-id="2c81d-229">当您确定策略应用程序的结果与利益干系人牢记的结果一致后，移动到此阶段。</span><span class="sxs-lookup"><span data-stu-id="2c81d-229">Move to this stage once you have confidence that the results of policy application match what they stakeholders had in mind.</span></span> 
    
3. <span data-ttu-id="2c81d-230">**开始完全强制执行策略**，以便应用规则中的操作，并保护内容。</span><span class="sxs-lookup"><span data-stu-id="2c81d-230">**Start full enforcement on the policies** so that the actions in the rules are applied and the content's protected.</span></span> <span data-ttu-id="2c81d-231">继续监视 DLP 报告及任何事件报告或通知，确保结果是你所期望的。</span><span class="sxs-lookup"><span data-stu-id="2c81d-231">Continue to monitor the DLP reports and any incident reports or notifications to make sure that the results are what you intend.</span></span> 

    ![使用测试模式和启用策略的选项](../media/49fafaac-c6cb-41de-99c4-c43c3e380c3a.png)

    <span data-ttu-id="2c81d-233">你可以随时关闭 DLP 策略，这将影响此策略中的所有规则。</span><span class="sxs-lookup"><span data-stu-id="2c81d-233">You can turn off a DLP policy at any time, which affects all rules in the policy.</span></span> <span data-ttu-id="2c81d-234">但是，也可以通过在规则编辑器中切换其状态来单独关闭每个规则。</span><span class="sxs-lookup"><span data-stu-id="2c81d-234">However, each rule can also be turned off individually by toggling its status in the rule editor.</span></span>

    ![关闭策略中的规则的选项](../media/f7b258ff-1b8b-4127-b580-83c6492f2bef.png)

    <span data-ttu-id="2c81d-236">你还可以更改策略中的多个规则的优先级。</span><span class="sxs-lookup"><span data-stu-id="2c81d-236">You can also change the priority of multiple rules in a policy.</span></span> <span data-ttu-id="2c81d-237">若要执行此操作，请打开要编辑的策略。</span><span class="sxs-lookup"><span data-stu-id="2c81d-237">To do that, open a policy for editing.</span></span> <span data-ttu-id="2c81d-238">在规则行中，选择省略号 (**...**)，然后选择一个选项，例如“**下移**”或“**移到最后**”。</span><span class="sxs-lookup"><span data-stu-id="2c81d-238">In a row for a rule, choose the ellipses (**...**), and then choose an option, such as **Move down** or **Bring to last**.</span></span>

    ![设置规则优先级](../media/dlp-set-rule-priority.png)

#### <a name="end-user-training"></a><span data-ttu-id="2c81d-240">最终用户培训</span><span class="sxs-lookup"><span data-stu-id="2c81d-240">End-user training</span></span>

<span data-ttu-id="2c81d-241">触发 DLP 策略后，可以将策略配置为发送电子邮件通知，并将 [DLP](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) 策略的策略提示显示给管理员和最终用户。</span><span class="sxs-lookup"><span data-stu-id="2c81d-241">When a DLP policy is triggered, you can configure your policies to [Send email notifications and show policy tips for DLP policies](use-notifications-and-policy-tips.md#send-email-notifications-and-show-policy-tips-for-dlp-policies) to admins and end users.</span></span> <span data-ttu-id="2c81d-242">虽然策略仍处于测试模式且未设置为强制执行阻止操作，但策略提示是一种有用的方法，用于提升对敏感项目风险行为的感知，并培训用户在将来避免这些行为。</span><span class="sxs-lookup"><span data-stu-id="2c81d-242">While your policies are still in test mode and before they are set to enforce a blocking action, policy tips are useful ways to raise awareness of risky behaviors on sensitive items and train users to avoid those behaviors in the future.</span></span>  

#### <a name="review-dlp-requirements-and-update-strategy"></a><span data-ttu-id="2c81d-243">查看 DLP 要求和更新策略</span><span class="sxs-lookup"><span data-stu-id="2c81d-243">Review DLP requirements and update strategy</span></span>

<span data-ttu-id="2c81d-244">组织所遵守的法规、法律和行业标准将随着时间的推移而改变，DLP 的业务目标也将发生变化。</span><span class="sxs-lookup"><span data-stu-id="2c81d-244">The regulations, laws, and industry standards that your organization is subject to will change over time and your business goals for DLP will too.</span></span> <span data-ttu-id="2c81d-245">请务必包括所有这些领域的定期评审，以便贵组织保持合规性，并且您的 DLP 实施继续满足您的业务需求。</span><span class="sxs-lookup"><span data-stu-id="2c81d-245">Be sure to include regular reviews of all these areas so that your organization stays in compliance and your DLP implementation continues to meet your business needs.</span></span>

## <a name="approaches-to-deployment"></a><span data-ttu-id="2c81d-246">部署方法</span><span class="sxs-lookup"><span data-stu-id="2c81d-246">Approaches to deployment</span></span>

|<span data-ttu-id="2c81d-247">客户业务需求说明</span><span class="sxs-lookup"><span data-stu-id="2c81d-247">Customer business needs description</span></span>  | <span data-ttu-id="2c81d-248">方法</span><span class="sxs-lookup"><span data-stu-id="2c81d-248">approach</span></span>  |
|---------|---------|
|<span data-ttu-id="2c81d-249">**Contoso Bank** 是一个高度管控的行业，在许多不同位置具有许多不同类型的敏感项目。</span><span class="sxs-lookup"><span data-stu-id="2c81d-249">**Contoso Bank** is in a highly regulated industry and has  many different types of sensitive items in many different locations.</span></span> </br> <span data-ttu-id="2c81d-250">- 了解敏感信息类型是最高优先级。</span><span class="sxs-lookup"><span data-stu-id="2c81d-250">- knows which types of sensitive information are top priority.</span></span> </br> <span data-ttu-id="2c81d-251">- 随着策略的推出，必须最大限度地减少业务中断。</span><span class="sxs-lookup"><span data-stu-id="2c81d-251">- must minimize business disruption as policies are rolled out.</span></span> </br> <span data-ttu-id="2c81d-252">- 具有 IT 资源，可以雇用专家来帮助规划、设计部署</span><span class="sxs-lookup"><span data-stu-id="2c81d-252">-  has IT resources and can hire experts to help plan, design deploy</span></span> </br> <span data-ttu-id="2c81d-253">- 与 Microsoft 签订顶级支持合同</span><span class="sxs-lookup"><span data-stu-id="2c81d-253">- has a premier support contract with Microsoft</span></span>| <span data-ttu-id="2c81d-254">- 花时间了解他们必须遵守哪些法规以及如何遵守。</span><span class="sxs-lookup"><span data-stu-id="2c81d-254">- Take the time to understand what regulations they must comply with and how they are going to comply.</span></span> </br> <span data-ttu-id="2c81d-255">-花时间了解信息保护堆栈的Microsoft 365价值</span><span class="sxs-lookup"><span data-stu-id="2c81d-255">-Take the time to understand the better together value of the Microsoft 365 Information Protection stack</span></span> </br> <span data-ttu-id="2c81d-256">- 为优先项目制定敏感度标签方案并应用</span><span class="sxs-lookup"><span data-stu-id="2c81d-256">- Develop sensitivity labeling scheme for prioritized items and apply</span></span> </br> <span data-ttu-id="2c81d-257">- 涉及业务流程所有者</span><span class="sxs-lookup"><span data-stu-id="2c81d-257">- Involve business process owners</span></span> </br><span data-ttu-id="2c81d-258">- 设计/代码策略，在测试模式下部署，培训用户</span><span class="sxs-lookup"><span data-stu-id="2c81d-258">- Design/code policies, deploy in test mode, train users</span></span> </br><span data-ttu-id="2c81d-259">- 重复</span><span class="sxs-lookup"><span data-stu-id="2c81d-259">- repeat</span></span>|
|<span data-ttu-id="2c81d-260">**TailSpin Toys** 不知道它们是什么或在哪里，并且很少甚至没有资源深度。</span><span class="sxs-lookup"><span data-stu-id="2c81d-260">**TailSpin Toys** doesn’t know what they have or where it is, and have little to no resource depth.</span></span> <span data-ttu-id="2c81d-261">它们广泛使用Teams、OneDrive for Business和Exchange应用。</span><span class="sxs-lookup"><span data-stu-id="2c81d-261">They use Teams, OneDrive for Business and Exchange extensively.</span></span>     |<span data-ttu-id="2c81d-262">- 从优先位置的简单策略开始。</span><span class="sxs-lookup"><span data-stu-id="2c81d-262">- Start with simple policies on the prioritized locations.</span></span> </br><span data-ttu-id="2c81d-263">- 监视识别哪些项</span><span class="sxs-lookup"><span data-stu-id="2c81d-263">- Monitor what gets identified</span></span> </br><span data-ttu-id="2c81d-264">- 相应地应用敏感度标签</span><span class="sxs-lookup"><span data-stu-id="2c81d-264">- Apply sensitivity labels accordingly</span></span> </br><span data-ttu-id="2c81d-265">- 优化策略，培训用户</span><span class="sxs-lookup"><span data-stu-id="2c81d-265">- Refine policies, train users</span></span>       |
|<span data-ttu-id="2c81d-266">**Fabrikam** 是一家小型初创公司，希望保护其知识产权，并且必须快速移动。</span><span class="sxs-lookup"><span data-stu-id="2c81d-266">**Fabrikam** is a small startup and wants to protect its intellectual property, and must move quickly.</span></span> <span data-ttu-id="2c81d-267">他们愿意投入一些资源，但无法承受聘用外部专家。</span><span class="sxs-lookup"><span data-stu-id="2c81d-267">They are willing to dedicate some resources, but can't afford to hire outside experts.</span></span> </br><span data-ttu-id="2c81d-268">- 敏感项目全部Microsoft 365 OneDrive for Business/SharePoint</span><span class="sxs-lookup"><span data-stu-id="2c81d-268">- Sensitive items are all in Microsoft 365 OneDrive for Business/SharePoint</span></span> </br><span data-ttu-id="2c81d-269">- 采用OneDrive for Business和SharePoint速度较慢，员工/影子 IT 使用 DropBox 和 Google 驱动器来共享/存储项目</span><span class="sxs-lookup"><span data-stu-id="2c81d-269">- Adoption of OneDrive for Business and SharePoint is slow, employees/shadow IT use DropBox and Google drive to share/store items</span></span> </br><span data-ttu-id="2c81d-270">- 员工在数据保护规范方面的价值工作速度</span><span class="sxs-lookup"><span data-stu-id="2c81d-270">- Employees value speed of work over data protection discipline</span></span> </br><span data-ttu-id="2c81d-271">- 客户清除并购买所有 18 名员工Windows 10设备</span><span class="sxs-lookup"><span data-stu-id="2c81d-271">- Customer splurged and bought all 18 employees new Windows 10 devices</span></span>     |<span data-ttu-id="2c81d-272">- 利用默认 DLP 策略Teams</span><span class="sxs-lookup"><span data-stu-id="2c81d-272">- Take advantage of the default DLP policy in Teams</span></span> </br><span data-ttu-id="2c81d-273">- 对项目使用默认设置SharePoint受限</span><span class="sxs-lookup"><span data-stu-id="2c81d-273">- Use restricted by default setting for SharePoint items</span></span> </br><span data-ttu-id="2c81d-274">- 部署阻止外部共享的策略</span><span class="sxs-lookup"><span data-stu-id="2c81d-274">- Deploy policies that prevent external sharing</span></span> </br><span data-ttu-id="2c81d-275">- 将策略部署到优先位置</span><span class="sxs-lookup"><span data-stu-id="2c81d-275">- Deploy policies to prioritized locations</span></span> </br><span data-ttu-id="2c81d-276">- 将策略部署到Windows 10设备</span><span class="sxs-lookup"><span data-stu-id="2c81d-276">- Deploy policies to Windows 10 devices</span></span> </br><span data-ttu-id="2c81d-277">- 阻止上载到非OneDrive for Business云存储</span><span class="sxs-lookup"><span data-stu-id="2c81d-277">- Block uploads to non-OneDrive for Business cloud storage</span></span>      |

<!--

## Planning for workloads

### Exchange

### SharePoint

### OneDrive for Business

### Teams

### Windows 10 Devices

### Microsoft Cloud App Security (MCAS)

### On-premises Scanner
-->

## <a name="see-also"></a><span data-ttu-id="2c81d-278">另请参阅</span><span class="sxs-lookup"><span data-stu-id="2c81d-278">See also</span></span>
- [<span data-ttu-id="2c81d-279">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="2c81d-279">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
