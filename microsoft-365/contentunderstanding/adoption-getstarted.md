---
title: Microsoft SharePoint Syntex采用：入门
description: 了解如何在组织中使用和实施SharePoint Syntex，以帮助你解决业务问题。
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 8a5442fcf8dd50cdee6be97ba7c9bbf5e21408a3
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53288151"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="19d60-103">Microsoft SharePoint Syntex采用：入门</span><span class="sxs-lookup"><span data-stu-id="19d60-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="19d60-104">将企业提供的智能内容服务SharePoint Syntex三个部分：</span><span class="sxs-lookup"><span data-stu-id="19d60-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="19d60-105">**内容了解：** 创建无代码 AI 模型以对内容进行分类和提取信息，以自动应用元数据进行知识发现和重用。</span><span class="sxs-lookup"><span data-stu-id="19d60-105">**Content understanding:** Create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="19d60-106">了解有关内容 [理解的更多信息](document-understanding-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="19d60-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="19d60-107">**内容处理：** 自动捕获、获取和分类内容，并简化使用 Power Automate 以内容为中心的Power Automate。</span><span class="sxs-lookup"><span data-stu-id="19d60-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="19d60-108">详细了解内容 [处理](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="19d60-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="19d60-109">**内容合规性：** 控制和管理内容，以改进安全性和管理，并集成Microsoft 信息保护。</span><span class="sxs-lookup"><span data-stu-id="19d60-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="19d60-110">借助新的 AI 服务和功能，你可以直接将内容理解和分类应用构建到内容管理流中，SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="19d60-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="19d60-111">有两种不同的内容理解方式。</span><span class="sxs-lookup"><span data-stu-id="19d60-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="19d60-112">使用的模型类型基于文件格式和用例：</span><span class="sxs-lookup"><span data-stu-id="19d60-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="19d60-113">表单处理</span><span class="sxs-lookup"><span data-stu-id="19d60-113">Form processing</span></span> | <span data-ttu-id="19d60-114">文档理解</span><span class="sxs-lookup"><span data-stu-id="19d60-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="19d60-115">从文档库创建。</span><span class="sxs-lookup"><span data-stu-id="19d60-115">Created from document library.</span></span> | <span data-ttu-id="19d60-116">在内容中心内创建，属于SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="19d60-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="19d60-117">在 AI 生成器中创建的模型。</span><span class="sxs-lookup"><span data-stu-id="19d60-117">Model created in AI builder.</span></span> | <span data-ttu-id="19d60-118">在本机接口中创建的模型。</span><span class="sxs-lookup"><span data-stu-id="19d60-118">Model created in native interface.</span></span> |
| <span data-ttu-id="19d60-119">用于半结构化文件格式。</span><span class="sxs-lookup"><span data-stu-id="19d60-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="19d60-120">用于非结构化文件格式。</span><span class="sxs-lookup"><span data-stu-id="19d60-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="19d60-121">可设置的分类器。</span><span class="sxs-lookup"><span data-stu-id="19d60-121">Settable classifier.</span></span> | <span data-ttu-id="19d60-122">带可选提取器、可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="19d60-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="19d60-123">仅限于单个库。</span><span class="sxs-lookup"><span data-stu-id="19d60-123">Restricted to a single library.</span></span> | <span data-ttu-id="19d60-124">可应用于多个库。</span><span class="sxs-lookup"><span data-stu-id="19d60-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="19d60-125">培训 PDF、JPG、PNG 格式，总计 50 MB/500 pp。</span><span class="sxs-lookup"><span data-stu-id="19d60-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="19d60-126">培训 5-10 个 PDF、Office 或电子邮件文件，包括反面例子。</span><span class="sxs-lookup"><span data-stu-id="19d60-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="19d60-127">有关功能的更完整比较，请参阅文档理解与 [表单处理模型的区别](difference-between-document-understanding-and-form-processing-model.md)。</span><span class="sxs-lookup"><span data-stu-id="19d60-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="19d60-128">确定要优化的试点业务方案</span><span class="sxs-lookup"><span data-stu-id="19d60-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="19d60-129">要准备在SharePoint Syntex中使用应用程序，首先需要了解它非常有用的方案。</span><span class="sxs-lookup"><span data-stu-id="19d60-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="19d60-130">"原因"可帮助确定需要哪种模型，以及如何根据将应用模型的地方构建组织。</span><span class="sxs-lookup"><span data-stu-id="19d60-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="19d60-131">下面是一些文档理解方案，可帮助您的组织：</span><span class="sxs-lookup"><span data-stu-id="19d60-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="19d60-132">**内容处理：** 处理合同、工作声明和其他类似表单的文档。</span><span class="sxs-lookup"><span data-stu-id="19d60-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="19d60-133">输入表单，训练模型以了解和映射字段，然后运行表单以自动收集数据。</span><span class="sxs-lookup"><span data-stu-id="19d60-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="19d60-134">有关详细信息，请参阅表单 [处理概述](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="19d60-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="19d60-135">**发票分析：** 从发票中拉出相关详细信息，并确保它们符合策略或正在适当处理。</span><span class="sxs-lookup"><span data-stu-id="19d60-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="19d60-136">考虑一下SharePoint Syntex组织的方式：</span><span class="sxs-lookup"><span data-stu-id="19d60-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="19d60-137">自动化业务流程</span><span class="sxs-lookup"><span data-stu-id="19d60-137">Automate business processes</span></span>
- <span data-ttu-id="19d60-138">提高搜索准确度</span><span class="sxs-lookup"><span data-stu-id="19d60-138">Improve search accuracy</span></span>
- <span data-ttu-id="19d60-139">管理合规性风险</span><span class="sxs-lookup"><span data-stu-id="19d60-139">Manage compliance risk</span></span>

<span data-ttu-id="19d60-140">在思考要考虑哪些业务方案时，请询问自己以下问题：</span><span class="sxs-lookup"><span data-stu-id="19d60-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="19d60-141">它是否解决了真正的问题？</span><span class="sxs-lookup"><span data-stu-id="19d60-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="19d60-142">它将被广泛使用还是具有广泛的影响？</span><span class="sxs-lookup"><span data-stu-id="19d60-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="19d60-143">它是否可获取？</span><span class="sxs-lookup"><span data-stu-id="19d60-143">Is it obtainable?</span></span>
- <span data-ttu-id="19d60-144">能否衡量成功？</span><span class="sxs-lookup"><span data-stu-id="19d60-144">Can you measure success?</span></span>

<span data-ttu-id="19d60-145">根据影响和实现方便性确定方案优先级。</span><span class="sxs-lookup"><span data-stu-id="19d60-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="19d60-146">使初始的重点关注区域具有更高的影响，这些应用场景也可以轻松实现。</span><span class="sxs-lookup"><span data-stu-id="19d60-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="19d60-147">取消难以实现的影响较低的方案的优先级。</span><span class="sxs-lookup"><span data-stu-id="19d60-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="19d60-148">使用[示例方案和用例来](adoption-scenarios.md)提示有关如何在组织中使用SharePoint Syntex的想法。</span><span class="sxs-lookup"><span data-stu-id="19d60-148">Use the [example scenarios and use cases](adoption-scenarios.md) to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="19d60-149">确定角色&职责</span><span class="sxs-lookup"><span data-stu-id="19d60-149">Identify roles & responsibilities</span></span>

<span data-ttu-id="19d60-150">确定贵组织中谁将构建和管理模型？</span><span class="sxs-lookup"><span data-stu-id="19d60-150">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="19d60-151">可能会涉及以下角色：</span><span class="sxs-lookup"><span data-stu-id="19d60-151">The following roles might be involved:</span></span>

| <span data-ttu-id="19d60-152">SharePoint/知识管理员</span><span class="sxs-lookup"><span data-stu-id="19d60-152">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="19d60-153">Power 平台管理员</span><span class="sxs-lookup"><span data-stu-id="19d60-153">Power Platform admin</span></span> | <span data-ttu-id="19d60-154">知识经理</span><span class="sxs-lookup"><span data-stu-id="19d60-154">Knowledge manager</span></span> | <span data-ttu-id="19d60-155">模型所有者</span><span class="sxs-lookup"><span data-stu-id="19d60-155">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="19d60-156">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="19d60-156">AAD role</span></span>| <span data-ttu-id="19d60-157">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="19d60-157">AAD role</span></span> | <span data-ttu-id="19d60-158">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="19d60-158">AAD role</span></span> | <span data-ttu-id="19d60-159">支持者</span><span class="sxs-lookup"><span data-stu-id="19d60-159">Champions</span></span> |
| <span data-ttu-id="19d60-160">配置表单处理</span><span class="sxs-lookup"><span data-stu-id="19d60-160">Configure form processing</span></span> | <span data-ttu-id="19d60-161">配置用于表单处理的常见数据服务环境</span><span class="sxs-lookup"><span data-stu-id="19d60-161">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="19d60-162">收集用例</span><span class="sxs-lookup"><span data-stu-id="19d60-162">Gather use cases</span></span> | <span data-ttu-id="19d60-163">收集业务用例</span><span class="sxs-lookup"><span data-stu-id="19d60-163">Gather business use cases</span></span> |
| <span data-ttu-id="19d60-164">管理内容中心和权限</span><span class="sxs-lookup"><span data-stu-id="19d60-164">Manage content centers and permissions</span></span>| <span data-ttu-id="19d60-165">购买和分配 AIB 信用额度</span><span class="sxs-lookup"><span data-stu-id="19d60-165">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="19d60-166">建立最佳做法并查看模型分析</span><span class="sxs-lookup"><span data-stu-id="19d60-166">Establish best practices and review model analytics</span></span> | <span data-ttu-id="19d60-167">创建和应用模型</span><span class="sxs-lookup"><span data-stu-id="19d60-167">Create and apply models</span></span> |

<span data-ttu-id="19d60-168">知识管理器、业务流程所有者和内容模型所有者在组织中创建示例模型和采用者。</span><span class="sxs-lookup"><span data-stu-id="19d60-168">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="19d60-169">可能涉及的其他人：合规性管理员、分类管理员。</span><span class="sxs-lookup"><span data-stu-id="19d60-169">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="19d60-170">他们将在哪里生成和应用模型？</span><span class="sxs-lookup"><span data-stu-id="19d60-170">Where will they build and apply the models?</span></span> <span data-ttu-id="19d60-171">是否有可以增强的现有流程或存储库？</span><span class="sxs-lookup"><span data-stu-id="19d60-171">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="19d60-172">表单处理：确定哪些网站将获取表单处理操作。</span><span class="sxs-lookup"><span data-stu-id="19d60-172">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="19d60-173">文档了解：您可以为不同的业务区域创建多个内容中心。</span><span class="sxs-lookup"><span data-stu-id="19d60-173">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="19d60-174">战略定位</span><span class="sxs-lookup"><span data-stu-id="19d60-174">Strategic positioning</span></span>

<span data-ttu-id="19d60-175">与利益干系人合作，确保他们符合使用 SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="19d60-175">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="19d60-176">研究和提供以下资源来帮助实现此定位：</span><span class="sxs-lookup"><span data-stu-id="19d60-176">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="19d60-177">业务成果：</span><span class="sxs-lookup"><span data-stu-id="19d60-177">Business outcomes:</span></span>
  - <span data-ttu-id="19d60-178">潜在的财务结果</span><span class="sxs-lookup"><span data-stu-id="19d60-178">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="19d60-179">潜在的灵活性结果</span><span class="sxs-lookup"><span data-stu-id="19d60-179">Potential agility outcomes</span></span>
  - <span data-ttu-id="19d60-180">业务结果模板</span><span class="sxs-lookup"><span data-stu-id="19d60-180">Business outcome template</span></span>
- <span data-ttu-id="19d60-181">利益干系人/Exec 发起人购买/调整</span><span class="sxs-lookup"><span data-stu-id="19d60-181">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="19d60-182">业务案例平台</span><span class="sxs-lookup"><span data-stu-id="19d60-182">Business case decks</span></span>
  - <span data-ttu-id="19d60-183">财务模型</span><span class="sxs-lookup"><span data-stu-id="19d60-183">Financial models</span></span>
  - <span data-ttu-id="19d60-184">公司准备情况 - 文化</span><span class="sxs-lookup"><span data-stu-id="19d60-184">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="19d60-185">确定利益干系人</span><span class="sxs-lookup"><span data-stu-id="19d60-185">Identify stakeholders</span></span>

<span data-ttu-id="19d60-186">确定你的项目的利益干系人。</span><span class="sxs-lookup"><span data-stu-id="19d60-186">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="19d60-187">角色</span><span class="sxs-lookup"><span data-stu-id="19d60-187">Role</span></span> |<span data-ttu-id="19d60-188">责任</span><span class="sxs-lookup"><span data-stu-id="19d60-188">Responsibilities</span></span> |<span data-ttu-id="19d60-189">部门</span><span class="sxs-lookup"><span data-stu-id="19d60-189">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="19d60-190">执行发起 (计划) </span><span class="sxs-lookup"><span data-stu-id="19d60-190">Executive sponsor(s)</span></span>   | <span data-ttu-id="19d60-191">向公司传达高级别愿景和价值</span><span class="sxs-lookup"><span data-stu-id="19d60-191">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="19d60-192">行政领导</span><span class="sxs-lookup"><span data-stu-id="19d60-192">Executive leadership</span></span>   |
| <span data-ttu-id="19d60-193">Project潜在客户 () </span><span class="sxs-lookup"><span data-stu-id="19d60-193">Project lead(s)</span></span> | <span data-ttu-id="19d60-194">监督整个启动执行和推广流程</span><span class="sxs-lookup"><span data-stu-id="19d60-194">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="19d60-195">项目管理</span><span class="sxs-lookup"><span data-stu-id="19d60-195">Project management</span></span> |
| <span data-ttu-id="19d60-196">知识管理员</span><span class="sxs-lookup"><span data-stu-id="19d60-196">Knowledge administrators</span></span>| <span data-ttu-id="19d60-197">创建和管理内容中心</span><span class="sxs-lookup"><span data-stu-id="19d60-197">Create and manage the content centers</span></span> | <span data-ttu-id="19d60-198">IT 或其他部门</span><span class="sxs-lookup"><span data-stu-id="19d60-198">IT or other department</span></span>|
| <span data-ttu-id="19d60-199">内容管理者和模型所有者</span><span class="sxs-lookup"><span data-stu-id="19d60-199">Content managers and model owners</span></span>| <span data-ttu-id="19d60-200">收集用例并创建和应用模型</span><span class="sxs-lookup"><span data-stu-id="19d60-200">Gather use cases and create and apply models</span></span> | <span data-ttu-id="19d60-201">任何部门</span><span class="sxs-lookup"><span data-stu-id="19d60-201">Any department</span></span>|
| <span data-ttu-id="19d60-202">支持者</span><span class="sxs-lookup"><span data-stu-id="19d60-202">Champions</span></span> | <span data-ttu-id="19d60-203">帮助宣传和管理异议处理</span><span class="sxs-lookup"><span data-stu-id="19d60-203">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="19d60-204">任何部门（员工）</span><span class="sxs-lookup"><span data-stu-id="19d60-204">Any department (staff)</span></span> |
| <span data-ttu-id="19d60-205">租户管理员</span><span class="sxs-lookup"><span data-stu-id="19d60-205">Tenant administrator</span></span> | <span data-ttu-id="19d60-206">配置租户级别设置</span><span class="sxs-lookup"><span data-stu-id="19d60-206">Configure tenant-level settings</span></span> | <span data-ttu-id="19d60-207">IT 部门</span><span class="sxs-lookup"><span data-stu-id="19d60-207">IT department</span></span>|
| <span data-ttu-id="19d60-208">Power 平台管理员</span><span class="sxs-lookup"><span data-stu-id="19d60-208">Power Platform administrator</span></span>| <span data-ttu-id="19d60-209">配置通用数据服务环境</span><span class="sxs-lookup"><span data-stu-id="19d60-209">Configure common data services environment</span></span> | <span data-ttu-id="19d60-210">IT 部门</span><span class="sxs-lookup"><span data-stu-id="19d60-210">IT department</span></span>|

> [!Note]
> <span data-ttu-id="19d60-211">尽管我们建议在部署过程中完成其中每个角色，但你可能会发现，你无需所有角色都开始使用你确定的解决方案。</span><span class="sxs-lookup"><span data-stu-id="19d60-211">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="19d60-212">准备情况清单</span><span class="sxs-lookup"><span data-stu-id="19d60-212">Readiness checklist</span></span>

<span data-ttu-id="19d60-213">若要准备好实现SharePoint Syntex，您需要：</span><span class="sxs-lookup"><span data-stu-id="19d60-213">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![内容理解的准备情况](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="19d60-215">规划结束状态</span><span class="sxs-lookup"><span data-stu-id="19d60-215">Plan the end state</span></span>
    - <span data-ttu-id="19d60-216">文档理解模型是方法，而不是结尾。</span><span class="sxs-lookup"><span data-stu-id="19d60-216">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="19d60-217">规划利用提取的元数据的价值，包括：</span><span class="sxs-lookup"><span data-stu-id="19d60-217">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="19d60-218">搜索</span><span class="sxs-lookup"><span data-stu-id="19d60-218">Search</span></span>
      - <span data-ttu-id="19d60-219">筛选和查看格式</span><span class="sxs-lookup"><span data-stu-id="19d60-219">Filtering and view formatting</span></span>
      - <span data-ttu-id="19d60-220">合规性</span><span class="sxs-lookup"><span data-stu-id="19d60-220">Compliance</span></span>
      - <span data-ttu-id="19d60-221">自动化</span><span class="sxs-lookup"><span data-stu-id="19d60-221">Automation</span></span>
2. <span data-ttu-id="19d60-222">标识</span><span class="sxs-lookup"><span data-stu-id="19d60-222">Identify</span></span>
    - <span data-ttu-id="19d60-223">了解现有信息体系结构和内容管理功能的使用。</span><span class="sxs-lookup"><span data-stu-id="19d60-223">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="19d60-224">任何现有内容类型是否适合模型？</span><span class="sxs-lookup"><span data-stu-id="19d60-224">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="19d60-225">元数据将改进哪些现有进程？</span><span class="sxs-lookup"><span data-stu-id="19d60-225">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="19d60-226">设计</span><span class="sxs-lookup"><span data-stu-id="19d60-226">Design</span></span>
    - <span data-ttu-id="19d60-227">设计信息体系结构、托管元数据和内容类型的方法。</span><span class="sxs-lookup"><span data-stu-id="19d60-227">Design your approach to information architecture, managed metadata and content types.</span></span>
    - <span data-ttu-id="19d60-228">设计定义、创建、管理过程。</span><span class="sxs-lookup"><span data-stu-id="19d60-228">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="19d60-229">参与你的组织</span><span class="sxs-lookup"><span data-stu-id="19d60-229">Engage your organization</span></span>

1. <span data-ttu-id="19d60-230">确定持有者、确认方案以及制定项目计划。</span><span class="sxs-lookup"><span data-stu-id="19d60-230">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="19d60-231">配置设置并应用许可证。</span><span class="sxs-lookup"><span data-stu-id="19d60-231">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="19d60-232">开始认知和培训 – 招募冠军。</span><span class="sxs-lookup"><span data-stu-id="19d60-232">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="19d60-233">分步推出。</span><span class="sxs-lookup"><span data-stu-id="19d60-233">Roll out in stages.</span></span>  
1. <span data-ttu-id="19d60-234">收集反馈并循环。</span><span class="sxs-lookup"><span data-stu-id="19d60-234">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="19d60-235">随着使用情况的扩大，可根据需要规划任何 AI Builder 信用额度。</span><span class="sxs-lookup"><span data-stu-id="19d60-235">As usage grows plan for any AI Builder credits as needed.</span></span>

## <a name="see-also"></a><span data-ttu-id="19d60-236">另请参阅</span><span class="sxs-lookup"><span data-stu-id="19d60-236">See also</span></span>

[<span data-ttu-id="19d60-237">应用场景和SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="19d60-237">Scenarios and use cases for SharePoint Syntex</span></span>](adoption-scenarios.md)
