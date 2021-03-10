---
title: Microsoft SharePoint Syntex 采用：入门
description: 了解如何在组织中使用和实施 SharePoint Syntex，以帮助你解决业务问题。
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: e88a7de1c81995b878dbf8a9308fbc774583289e
ms.sourcegitcommit: 8950d3cb0f3087be7105e370ed02c7a575d00ec2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2021
ms.locfileid: "50597054"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="d8fda-103">Microsoft SharePoint Syntex 采用：入门</span><span class="sxs-lookup"><span data-stu-id="d8fda-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="d8fda-104">将 SharePoint Syntex 中可用的智能内容服务视为包含三个部分：</span><span class="sxs-lookup"><span data-stu-id="d8fda-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="d8fda-105">**内容了解：** 创建无代码 AI 模型以对内容进行分类和提取信息，以自动应用元数据以用于知识发现和重用。</span><span class="sxs-lookup"><span data-stu-id="d8fda-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="d8fda-106">了解有关内容[了解的内容。](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d8fda-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="d8fda-107">**内容处理：** 使用 Power Automate 自动化内容捕获、获取和分类，并简化以内容为中心的流程。</span><span class="sxs-lookup"><span data-stu-id="d8fda-107">**Content processing:** Automate capture, ingestion, and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="d8fda-108">详细了解内容 [处理](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d8fda-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="d8fda-109">**内容合规性：** 通过与 Microsoft 信息保护的集成来控制和管理内容以提高安全性和治理。</span><span class="sxs-lookup"><span data-stu-id="d8fda-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="d8fda-110">借助新的 AI 服务和功能，您可以使用 SharePoint Syntex 将内容理解和分类应用程序直接构建到内容管理流中。</span><span class="sxs-lookup"><span data-stu-id="d8fda-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex.</span></span> <span data-ttu-id="d8fda-111">有两种不同的内容理解方式。</span><span class="sxs-lookup"><span data-stu-id="d8fda-111">There are two different ways of understanding your content.</span></span> <span data-ttu-id="d8fda-112">使用的模型类型基于文件格式和用例：</span><span class="sxs-lookup"><span data-stu-id="d8fda-112">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="d8fda-113">表单处理</span><span class="sxs-lookup"><span data-stu-id="d8fda-113">Form processing</span></span> | <span data-ttu-id="d8fda-114">文档理解</span><span class="sxs-lookup"><span data-stu-id="d8fda-114">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="d8fda-115">从文档库创建。</span><span class="sxs-lookup"><span data-stu-id="d8fda-115">Created from document library.</span></span> | <span data-ttu-id="d8fda-116">在内容中心（SharePoint Syntex 的一部分）中创建。</span><span class="sxs-lookup"><span data-stu-id="d8fda-116">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="d8fda-117">在 AI 生成器中创建的模型。</span><span class="sxs-lookup"><span data-stu-id="d8fda-117">Model created in AI builder.</span></span> | <span data-ttu-id="d8fda-118">在本机界面中创建的模型。</span><span class="sxs-lookup"><span data-stu-id="d8fda-118">Model created in native interface.</span></span> |
| <span data-ttu-id="d8fda-119">用于半结构化文件格式。</span><span class="sxs-lookup"><span data-stu-id="d8fda-119">Used for semi-structured file formats.</span></span> | <span data-ttu-id="d8fda-120">用于非结构化文件格式。</span><span class="sxs-lookup"><span data-stu-id="d8fda-120">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="d8fda-121">可设置的分类器。</span><span class="sxs-lookup"><span data-stu-id="d8fda-121">Settable classifier.</span></span> | <span data-ttu-id="d8fda-122">带可选提取器的可训练分类器。</span><span class="sxs-lookup"><span data-stu-id="d8fda-122">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="d8fda-123">限制为单个库。</span><span class="sxs-lookup"><span data-stu-id="d8fda-123">Restricted to a single library.</span></span> | <span data-ttu-id="d8fda-124">可应用于多个库。</span><span class="sxs-lookup"><span data-stu-id="d8fda-124">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="d8fda-125">培训 PDF、JPG、PNG 格式，总大小为 50 MB/500 pp。</span><span class="sxs-lookup"><span data-stu-id="d8fda-125">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="d8fda-126">培训 5-10 个 PDF、Office 或电子邮件文件，包括负面示例。</span><span class="sxs-lookup"><span data-stu-id="d8fda-126">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="d8fda-127">有关功能的更完整比较，请参阅文档理解模型和表单 [处理模型的区别](difference-between-document-understanding-and-form-processing-model.md)。</span><span class="sxs-lookup"><span data-stu-id="d8fda-127">For a more complete comparison of the capabilities, see [Difference between document understanding and form processing models](difference-between-document-understanding-and-form-processing-model.md).</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="d8fda-128">确定要优化的试点业务方案</span><span class="sxs-lookup"><span data-stu-id="d8fda-128">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="d8fda-129">若要准备在组织中使用 SharePoint Syntex，您首先需要了解它非常有用的方案。</span><span class="sxs-lookup"><span data-stu-id="d8fda-129">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="d8fda-130">"原因"可帮助确定需要哪种模型，以及如何根据将应用模型的地方构建组织。</span><span class="sxs-lookup"><span data-stu-id="d8fda-130">The "why" helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="d8fda-131">以下是一些文档理解有助于组织的方案：</span><span class="sxs-lookup"><span data-stu-id="d8fda-131">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="d8fda-132">**内容处理：** 处理合同、工作说明和其他类似表单的文档。</span><span class="sxs-lookup"><span data-stu-id="d8fda-132">**Content processing:** Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="d8fda-133">输入表单，培训模型以了解和映射字段，然后运行表单以自动收集数据。</span><span class="sxs-lookup"><span data-stu-id="d8fda-133">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="d8fda-134">有关详细信息，请参阅 [窗体处理概述](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="d8fda-134">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="d8fda-135">**发票分析：** 从发票中拉出相关详细信息，并确保它们符合策略或正在适当处理。</span><span class="sxs-lookup"><span data-stu-id="d8fda-135">**Invoice analysis:** Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="d8fda-136">考虑 SharePoint Syntex 可帮助组织的方法：</span><span class="sxs-lookup"><span data-stu-id="d8fda-136">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="d8fda-137">自动化业务流程</span><span class="sxs-lookup"><span data-stu-id="d8fda-137">Automate business processes</span></span>
- <span data-ttu-id="d8fda-138">提高搜索准确度</span><span class="sxs-lookup"><span data-stu-id="d8fda-138">Improve search accuracy</span></span>
- <span data-ttu-id="d8fda-139">管理合规性风险</span><span class="sxs-lookup"><span data-stu-id="d8fda-139">Manage compliance risk</span></span>

<span data-ttu-id="d8fda-140">在考虑要考虑哪些业务方案时，请自问以下问题：</span><span class="sxs-lookup"><span data-stu-id="d8fda-140">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="d8fda-141">它是否解决了一个实际问题？</span><span class="sxs-lookup"><span data-stu-id="d8fda-141">Does it solve a real problem?</span></span>
- <span data-ttu-id="d8fda-142">它将被广泛使用还是具有广泛的影响？</span><span class="sxs-lookup"><span data-stu-id="d8fda-142">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="d8fda-143">是否可获取？</span><span class="sxs-lookup"><span data-stu-id="d8fda-143">Is it obtainable?</span></span>
- <span data-ttu-id="d8fda-144">能否衡量成功？</span><span class="sxs-lookup"><span data-stu-id="d8fda-144">Can you measure success?</span></span>

<span data-ttu-id="d8fda-145">根据影响和易于实现确定方案优先级。</span><span class="sxs-lookup"><span data-stu-id="d8fda-145">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="d8fda-146">使初始焦点区域具有更高的影响方案，这些应用场景也可轻松实现。</span><span class="sxs-lookup"><span data-stu-id="d8fda-146">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="d8fda-147">取消难以实现的影响较低的方案的优先级。</span><span class="sxs-lookup"><span data-stu-id="d8fda-147">De-prioritize lower impact scenarios that are hard to implement.</span></span>

<span data-ttu-id="d8fda-148">使用以下示例方案可提示有关如何在组织中使用 SharePoint Syntex 的想法。</span><span class="sxs-lookup"><span data-stu-id="d8fda-148">Use the following example scenarios to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

### <a name="scenario-track-data-from-invoices-with-form-processing"></a><span data-ttu-id="d8fda-149">方案：通过表单处理跟踪发票数据</span><span class="sxs-lookup"><span data-stu-id="d8fda-149">Scenario: Track data from invoices with form processing</span></span>

<span data-ttu-id="d8fda-150">例如，您可以使用 SharePoint Syntex 和 Power Automate 功能设置一个过程来跟踪和监视发票。</span><span class="sxs-lookup"><span data-stu-id="d8fda-150">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="d8fda-151">设置用于存储发票文档的库。</span><span class="sxs-lookup"><span data-stu-id="d8fda-151">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="d8fda-152">训练模型以识别文档中的字段。</span><span class="sxs-lookup"><span data-stu-id="d8fda-152">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="d8fda-153">将要跟踪的字段提取到列表中。</span><span class="sxs-lookup"><span data-stu-id="d8fda-153">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="d8fda-154">设置流以针对特定事件通知您，例如：</span><span class="sxs-lookup"><span data-stu-id="d8fda-154">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="d8fda-155">将添加一个新的发票。</span><span class="sxs-lookup"><span data-stu-id="d8fda-155">A new invoice is added.</span></span>
    - <span data-ttu-id="d8fda-156">发票已过期。</span><span class="sxs-lookup"><span data-stu-id="d8fda-156">An invoice is past its due date.</span></span>
    - <span data-ttu-id="d8fda-157">发票用于大于自动审批金额的金额。</span><span class="sxs-lookup"><span data-stu-id="d8fda-157">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![使用 SharePoint Syntex 和 Power Automate 跟踪和监视发票](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="d8fda-159">自动执行此方案时，可以：</span><span class="sxs-lookup"><span data-stu-id="d8fda-159">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="d8fda-160">通过自动从发票中提取数据而不是手动提取数据来节省时间和资金。</span><span class="sxs-lookup"><span data-stu-id="d8fda-160">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="d8fda-161">通过使用工作流检查发票并通知您任何问题，减少潜在错误并确保更好的合规性。</span><span class="sxs-lookup"><span data-stu-id="d8fda-161">Reduce potential errors and ensure better compliance by using workflows to check invoices and notify you of any issues.</span></span>

### <a name="scenario-track-information-from-contracts-with-document-understanding"></a><span data-ttu-id="d8fda-162">方案：跟踪合同信息，了解文档</span><span class="sxs-lookup"><span data-stu-id="d8fda-162">Scenario: Track information from contracts with document understanding</span></span>

<span data-ttu-id="d8fda-163">另一个示例是，您可以设置一个流程来标识贵公司与其他公司或个人的合同。</span><span class="sxs-lookup"><span data-stu-id="d8fda-163">As another example, you can set up a process to identify contracts your company has with other companies or individuals.</span></span> <span data-ttu-id="d8fda-164">设置一个模型以从这些合同中提取关键信息（如客户端名称、费用、日期或其他重要信息）并作为可快速查看的字段将信息添加到库中。</span><span class="sxs-lookup"><span data-stu-id="d8fda-164">Set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add the information to the library as fields you can quickly view.</span></span> <span data-ttu-id="d8fda-165">在文档库上应用保留标签，以确保在一段特定时间之前无法删除合同，以适当遵守业务法规。</span><span class="sxs-lookup"><span data-stu-id="d8fda-165">Apply a retention label on the document library to ensure that contracts can't be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="d8fda-166">从内容中心开始，为合同创建新的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="d8fda-166">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="d8fda-167">上载示例文档，查看正负示例，然后运行培训以确定合同文档并查看结果。</span><span class="sxs-lookup"><span data-stu-id="d8fda-167">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="d8fda-168">培训提取程序以识别合同中的字段，如客户端名称、费用、日期，然后测试提取程序。</span><span class="sxs-lookup"><span data-stu-id="d8fda-168">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="d8fda-169">模型完成后，将模型应用到可在其中上载合约的库。</span><span class="sxs-lookup"><span data-stu-id="d8fda-169">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="d8fda-170">将保留标签应用于日期字段，以便合同在库中保留所需时间长度。</span><span class="sxs-lookup"><span data-stu-id="d8fda-170">Apply a retention label to the date field, so that contracts are retained in the library for the required length of time.</span></span>

![使用 SharePoint 合成和保留标签跟踪和监视合同](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="d8fda-172">自动执行此方案时，可以：</span><span class="sxs-lookup"><span data-stu-id="d8fda-172">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="d8fda-173">通过自动从合同中提取数据而不是手动提取数据来节省时间和资金。</span><span class="sxs-lookup"><span data-stu-id="d8fda-173">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="d8fda-174">通过使用保留标签确保更好地合规，以确保适当地保留合同。</span><span class="sxs-lookup"><span data-stu-id="d8fda-174">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a><span data-ttu-id="d8fda-175">方案：根据 SharePoint Syntex 避免记录管理、文档管理和合规性流程的风险</span><span class="sxs-lookup"><span data-stu-id="d8fda-175">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>

<span data-ttu-id="d8fda-176">降低风险是大多数公司的一个共同目标。</span><span class="sxs-lookup"><span data-stu-id="d8fda-176">Reducing risks is a common goal for most companies.</span></span> <span data-ttu-id="d8fda-177">您可能需要：</span><span class="sxs-lookup"><span data-stu-id="d8fda-177">You might need:</span></span>

- <span data-ttu-id="d8fda-178">在整个租户中提供/强制执行信息治理的更好方法。</span><span class="sxs-lookup"><span data-stu-id="d8fda-178">A better way to provide/enforce information governance across your tenant.</span></span>
- <span data-ttu-id="d8fda-179">改进文档、电子邮件和视为项目的"记录"的其他形式的通信分类系统。</span><span class="sxs-lookup"><span data-stu-id="d8fda-179">To improve the system for classification of documents, emails and other forms of communication considered ‘records’ for projects.</span></span>
- <span data-ttu-id="d8fda-180">审核收据、合同等，以确保遵守公司策略。</span><span class="sxs-lookup"><span data-stu-id="d8fda-180">To audit receipts, contracts, and so on, to ensure compliance with company policies.</span></span>
- <span data-ttu-id="d8fda-181">确保项目具有合规性所需的所有文档。</span><span class="sxs-lookup"><span data-stu-id="d8fda-181">To ensure that projects have all the documentation required for compliance.</span></span>

<span data-ttu-id="d8fda-182">设置一些与 SharePoint Syntex 的合规性流程，以捕获和适当分类、审核和标记需要更好地管理的文档和表单。</span><span class="sxs-lookup"><span data-stu-id="d8fda-182">Set up some processes for compliance with SharePoint Syntex to capture and appropriately classify, audit, and flag documents and forms that need better governance.</span></span> <span data-ttu-id="d8fda-183">您可以依赖 SharePoint Syntex 对内容进行自动分类，而不是依赖最终用户手动标记，或者依赖合规性团队手动应用管理规则和存档。</span><span class="sxs-lookup"><span data-stu-id="d8fda-183">You can rely on SharePoint Syntex to auto classify content rather than relying on end users to manually tag, or the compliance team to manually apply governance rules and archiving.</span></span> <span data-ttu-id="d8fda-184">此外，还可以启用简化的搜索体验、管理数据卷、应用记录管理和保留策略、确保合规性以及最佳实践存档和清除实践。</span><span class="sxs-lookup"><span data-stu-id="d8fda-184">And you can enable a simplified search experience, manage data volumes, apply records management and retention policies, ensure compliance, and best practice archiving and purging practices.</span></span>

<span data-ttu-id="d8fda-185">当您自动执行此方案时，您感觉安全：</span><span class="sxs-lookup"><span data-stu-id="d8fda-185">When you automate this scenario, you can feel secure that:</span></span>

- <span data-ttu-id="d8fda-186">合规性得到维持，并且风险降低。</span><span class="sxs-lookup"><span data-stu-id="d8fda-186">Compliance is upheld and risk is reduced.</span></span>
- <span data-ttu-id="d8fda-187">分类和记录管理一致且准确应用。</span><span class="sxs-lookup"><span data-stu-id="d8fda-187">Taxonomy and records management is consistently and accurately applied.</span></span>
- <span data-ttu-id="d8fda-188">控制内容卷。</span><span class="sxs-lookup"><span data-stu-id="d8fda-188">Content volumes are controlled.</span></span>
- <span data-ttu-id="d8fda-189">员工可以轻松地在正确的上下文中发现正确的信息。</span><span class="sxs-lookup"><span data-stu-id="d8fda-189">Employees can easily discover the right information in the right context.</span></span>

### <a name="scenario-capture-information-from-previously-inaccessible-documents"></a><span data-ttu-id="d8fda-190">方案：捕获以前无法访问的文档的信息</span><span class="sxs-lookup"><span data-stu-id="d8fda-190">Scenario: Capture information from previously inaccessible documents</span></span>

<span data-ttu-id="d8fda-191">大多数组织都有法律文档、策略、合同、HR 文档和管理准则的大型存储库。</span><span class="sxs-lookup"><span data-stu-id="d8fda-191">Most organizations have large repositories of legal documents, policies, contracts, HR documents, and governance guidelines.</span></span> <span data-ttu-id="d8fda-192">挖掘这些数据存储以提取有价值的信息，例如：项目、部门、主题、人员、地理区域等。</span><span class="sxs-lookup"><span data-stu-id="d8fda-192">Mine these data stores to extract valuable information such as: projects, sectors, themes, people, geographical areas, and so on.</span></span>

<span data-ttu-id="d8fda-193">例如，HR 主管需要快速访问所有 HR 文档，包括简历、HR 策略和其他表单。</span><span class="sxs-lookup"><span data-stu-id="d8fda-193">For example, an HR director needs to quickly access all HR documents – including resumes, HR policies, and other forms.</span></span> <span data-ttu-id="d8fda-194">他们希望从简历和其他与 HR 相关的文档中快速识别必要信息，而无需手动筛选文档。</span><span class="sxs-lookup"><span data-stu-id="d8fda-194">And they want to quickly identify necessary information from resumes and other HR-related documents without manually sifting through the documents.</span></span> <span data-ttu-id="d8fda-195">他们正在寻找一个解决方案，让他们可以快速找到所需的信息，而无需手动查看数千份可能分布于多个网站的简历、HR 策略和其他文档。</span><span class="sxs-lookup"><span data-stu-id="d8fda-195">They’re looking for a solution that allows them to quickly find the information they need without having to manually look through thousands of resumes, HR policies, and other documentation that may be spread across several sites.</span></span>

<span data-ttu-id="d8fda-196">自动执行此方案时，可以：</span><span class="sxs-lookup"><span data-stu-id="d8fda-196">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="d8fda-197">从数字内容中解锁知识。</span><span class="sxs-lookup"><span data-stu-id="d8fda-197">Unlock knowledge from digital content.</span></span>
- <span data-ttu-id="d8fda-198">对 HR 策略、简历、销售文档、技术蓝图、帐户计划和提取信息进行分类。</span><span class="sxs-lookup"><span data-stu-id="d8fda-198">Classify HR policies, resumes, sales documents, technical blueprints, account plans and extract information.</span></span>
- <span data-ttu-id="d8fda-199">快速查找要查找的正确信息或文档。</span><span class="sxs-lookup"><span data-stu-id="d8fda-199">Quickly find the correct information or document that you’re looking for.</span></span>
- <span data-ttu-id="d8fda-200">获取对最新信息的即时访问。</span><span class="sxs-lookup"><span data-stu-id="d8fda-200">Get instant access to the latest information.</span></span>
- <span data-ttu-id="d8fda-201">缩短搜索时间。</span><span class="sxs-lookup"><span data-stu-id="d8fda-201">Reduce search times.</span></span>

### <a name="scenario-improve-data-processing-to-provide-insights--analytics"></a><span data-ttu-id="d8fda-202">方案：改进数据处理，以提供分析&见解</span><span class="sxs-lookup"><span data-stu-id="d8fda-202">Scenario: Improve data processing to provide insights & analytics</span></span>

<span data-ttu-id="d8fda-203">例如，一家保险公司可以使用 SharePoint Syntex 从 FDA 文档中提取信息，以回答其领导的问题。</span><span class="sxs-lookup"><span data-stu-id="d8fda-203">For example, a pharmaceutical company could use SharePoint Syntex to extract information from FDA documents to answer questions that their leaders have.</span></span> <span data-ttu-id="d8fda-204">让答案更易于访问可减少生成这些答案所需的时间，并增加数据的可用性，从而生成更准确的领导问题答案。</span><span class="sxs-lookup"><span data-stu-id="d8fda-204">Having the answers more easily accessible can reduce the time needed to produce these answers and increase the availability of data to generate more accurate answers to leadership questions.</span></span>

<span data-ttu-id="d8fda-205">例如，项目经理需要快速提供来自我的领导团队的产品相关问题的解答。</span><span class="sxs-lookup"><span data-stu-id="d8fda-205">For example, a project manager needs to quickly provide answers to product-related questions from my leadership team.</span></span> <span data-ttu-id="d8fda-206">他们需要在一个合并仪表板中查找与查询相关的信息和指标。</span><span class="sxs-lookup"><span data-stu-id="d8fda-206">They need to find information and metrics related to queries in one consolidated dashboard.</span></span> <span data-ttu-id="d8fda-207">他们正在寻找一种解决方案，从产品标签、产品标签和其他材料中提取他们需要的信息，并生成一份合并报告，在向领导团队报告时可以使用该报告。</span><span class="sxs-lookup"><span data-stu-id="d8fda-207">They’re looking for a solution that extracts the information they need from product labels, product pamphlets, and other materials and generates a consolidated report that they can use when reporting back to their leadership team.</span></span>

<span data-ttu-id="d8fda-208">自动执行此方案时，可以：</span><span class="sxs-lookup"><span data-stu-id="d8fda-208">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="d8fda-209">减少生成答案的时间。</span><span class="sxs-lookup"><span data-stu-id="d8fda-209">Reduce time to produce answers.</span></span>
- <span data-ttu-id="d8fda-210">提高数据的可用性。</span><span class="sxs-lookup"><span data-stu-id="d8fda-210">Increase availability of data.</span></span>
- <span data-ttu-id="d8fda-211">提供更准确的答案。</span><span class="sxs-lookup"><span data-stu-id="d8fda-211">Provide more accurate answers.</span></span>

### <a name="scenario-automate-order-processing"></a><span data-ttu-id="d8fda-212">方案：自动化订单处理</span><span class="sxs-lookup"><span data-stu-id="d8fda-212">Scenario: Automate order processing</span></span>

<span data-ttu-id="d8fda-213">使用 SharePoint Syntex，可以缩短手动处理客户订单的时间。</span><span class="sxs-lookup"><span data-stu-id="d8fda-213">With SharePoint Syntex, you can reduce the time of manual processing of customer orders.</span></span> <span data-ttu-id="d8fda-214">例如，您可以使用 OCR 处理将传真、电子邮件或纸张中的订单上载到 SharePoint，然后从这些订单中提取元数据，以便您可以使用自动化流程完成这些订单。</span><span class="sxs-lookup"><span data-stu-id="d8fda-214">For example, you can upload orders from fax, email, or paper into SharePoint by using OCR processing and then extract the metadata from those orders so you can fulfill them by using automated processes.</span></span>

<span data-ttu-id="d8fda-215">例如，供应链经理希望减少由手动数据输入导致的错误。</span><span class="sxs-lookup"><span data-stu-id="d8fda-215">For example, a supply chain manager wants to reduce errors caused by manual data entry.</span></span> <span data-ttu-id="d8fda-216">他们希望避免手动查看入站客户订单， (传真或电子邮件) 输入数据，以减少进入业务系统的错误。</span><span class="sxs-lookup"><span data-stu-id="d8fda-216">They want to avoid manual review and data entry of inbound customer orders (paper, fax, or e-mail) to reduce errors going into their business systems.</span></span> <span data-ttu-id="d8fda-217">他们希望一个应用 AI 和机器学习技术的解决方案来验证传入订单信息、提取核心数据并自动推送到 ERP 系统中，以便实现订单和进行对帐。</span><span class="sxs-lookup"><span data-stu-id="d8fda-217">They want a solution that applies AI and machine learning techniques to validate incoming order information, extract core data and automatically push it into their ERP system, for order fulfillment and reconciliation.</span></span>

<span data-ttu-id="d8fda-218">自动执行此方案时，可以确保：</span><span class="sxs-lookup"><span data-stu-id="d8fda-218">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="d8fda-219">订单和发货准确度提高。</span><span class="sxs-lookup"><span data-stu-id="d8fda-219">Order and shipment accuracy increases.</span></span>
- <span data-ttu-id="d8fda-220">减少与订单或发货错误相关的费用或处罚。</span><span class="sxs-lookup"><span data-stu-id="d8fda-220">Fees or penalties associated to order or shipment errors are reduced.</span></span>
- <span data-ttu-id="d8fda-221">发票或付款延迟减少。</span><span class="sxs-lookup"><span data-stu-id="d8fda-221">Delays in invoicing or payments decrease.</span></span>
- <span data-ttu-id="d8fda-222">人员成本降低。</span><span class="sxs-lookup"><span data-stu-id="d8fda-222">Personnel costs are reduced.</span></span>

### <a name="scenario-simplify-visa-renewal-process"></a><span data-ttu-id="d8fda-223">方案：简化续订过程</span><span class="sxs-lookup"><span data-stu-id="d8fda-223">Scenario: Simplify visa renewal process</span></span>

<span data-ttu-id="d8fda-224">SharePoint Syntex 可帮助您自动执行关键合同信息的提醒和续订。</span><span class="sxs-lookup"><span data-stu-id="d8fda-224">SharePoint Syntex can help you automate reminders and renewals for key contract information.</span></span> <span data-ttu-id="d8fda-225">例如，HR 主管需要确保员工的护照是最新的和/或及时续订的。</span><span class="sxs-lookup"><span data-stu-id="d8fda-225">For example, an HR director needs to ensure that employees’ visas are up to date and/or renewed on time.</span></span> <span data-ttu-id="d8fda-226">他们希望为用户提供一个简单直观的流程，用于更新其 Visa。</span><span class="sxs-lookup"><span data-stu-id="d8fda-226">They want to give people a simple and intuitive process for updating their Visas.</span></span> <span data-ttu-id="d8fda-227">他们需要一个从合同中提取续订日期的解决方案，并会在员工续订日期接近时自动发送提醒。</span><span class="sxs-lookup"><span data-stu-id="d8fda-227">They need a solution that extracts renewal dates from contracts and automatically sends employees reminders when their renewal dates are approaching.</span></span>

<span data-ttu-id="d8fda-228">自动执行此方案时，可以确保：</span><span class="sxs-lookup"><span data-stu-id="d8fda-228">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="d8fda-229">不合规级别降低。</span><span class="sxs-lookup"><span data-stu-id="d8fda-229">The levels of non-compliance are reduced.</span></span>
- <span data-ttu-id="d8fda-230">手动提醒的数量减少。</span><span class="sxs-lookup"><span data-stu-id="d8fda-230">The number of manual reminders is reduced.</span></span>
- <span data-ttu-id="d8fda-231">针对不合规的罚款数量减少。</span><span class="sxs-lookup"><span data-stu-id="d8fda-231">The number of fines for non-compliance is reduced.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="d8fda-232">确定&角色</span><span class="sxs-lookup"><span data-stu-id="d8fda-232">Identify roles & responsibilities</span></span>

<span data-ttu-id="d8fda-233">确定贵组织中谁将构建和管理模型？</span><span class="sxs-lookup"><span data-stu-id="d8fda-233">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="d8fda-234">可能涉及以下角色：</span><span class="sxs-lookup"><span data-stu-id="d8fda-234">The following roles might be involved:</span></span>

| <span data-ttu-id="d8fda-235">SharePoint/知识库管理员</span><span class="sxs-lookup"><span data-stu-id="d8fda-235">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="d8fda-236">Power Platform admin</span><span class="sxs-lookup"><span data-stu-id="d8fda-236">Power Platform admin</span></span> | <span data-ttu-id="d8fda-237">知识管理器</span><span class="sxs-lookup"><span data-stu-id="d8fda-237">Knowledge manager</span></span> | <span data-ttu-id="d8fda-238">模型所有者</span><span class="sxs-lookup"><span data-stu-id="d8fda-238">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="d8fda-239">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="d8fda-239">AAD role</span></span>| <span data-ttu-id="d8fda-240">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="d8fda-240">AAD role</span></span> | <span data-ttu-id="d8fda-241">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="d8fda-241">AAD role</span></span> | <span data-ttu-id="d8fda-242">支持者</span><span class="sxs-lookup"><span data-stu-id="d8fda-242">Champions</span></span> |
| <span data-ttu-id="d8fda-243">配置表单处理</span><span class="sxs-lookup"><span data-stu-id="d8fda-243">Configure form processing</span></span> | <span data-ttu-id="d8fda-244">配置用于表单处理的常见数据服务环境</span><span class="sxs-lookup"><span data-stu-id="d8fda-244">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="d8fda-245">收集用例</span><span class="sxs-lookup"><span data-stu-id="d8fda-245">Gather use cases</span></span> | <span data-ttu-id="d8fda-246">收集业务用例</span><span class="sxs-lookup"><span data-stu-id="d8fda-246">Gather business use cases</span></span> |
| <span data-ttu-id="d8fda-247">管理内容中心和权限</span><span class="sxs-lookup"><span data-stu-id="d8fda-247">Manage content centers and permissions</span></span>| <span data-ttu-id="d8fda-248">购买和分配 AIB 信用</span><span class="sxs-lookup"><span data-stu-id="d8fda-248">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="d8fda-249">建立最佳做法并查看模型分析</span><span class="sxs-lookup"><span data-stu-id="d8fda-249">Establish best practices and review model analytics</span></span> | <span data-ttu-id="d8fda-250">创建和应用模型</span><span class="sxs-lookup"><span data-stu-id="d8fda-250">Create and apply models</span></span> |

<span data-ttu-id="d8fda-251">知识经理、业务流程所有者和内容模型所有者创建示例模型，并支持在组织中采用。</span><span class="sxs-lookup"><span data-stu-id="d8fda-251">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="d8fda-252">可能涉及的其他人：合规性管理员、分类管理员。</span><span class="sxs-lookup"><span data-stu-id="d8fda-252">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="d8fda-253">他们将在哪里生成和应用模型？</span><span class="sxs-lookup"><span data-stu-id="d8fda-253">Where will they build and apply the models?</span></span> <span data-ttu-id="d8fda-254">是否有可以增强的现有流程或存储库？</span><span class="sxs-lookup"><span data-stu-id="d8fda-254">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="d8fda-255">表单处理：确定哪些网站将获取表单处理操作。</span><span class="sxs-lookup"><span data-stu-id="d8fda-255">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="d8fda-256">文档了解：您可以为不同的业务区域创建多个内容中心。</span><span class="sxs-lookup"><span data-stu-id="d8fda-256">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="d8fda-257">战略定位</span><span class="sxs-lookup"><span data-stu-id="d8fda-257">Strategic positioning</span></span>

<span data-ttu-id="d8fda-258">与利益干系人合作，确保他们在使用 SharePoint Syntex 的策略上保持一致。</span><span class="sxs-lookup"><span data-stu-id="d8fda-258">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="d8fda-259">研究并提供以下资源来帮助实现此定位：</span><span class="sxs-lookup"><span data-stu-id="d8fda-259">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="d8fda-260">业务成果：</span><span class="sxs-lookup"><span data-stu-id="d8fda-260">Business outcomes:</span></span>
  - <span data-ttu-id="d8fda-261">潜在的财政结果</span><span class="sxs-lookup"><span data-stu-id="d8fda-261">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="d8fda-262">潜在的灵活性结果</span><span class="sxs-lookup"><span data-stu-id="d8fda-262">Potential agility outcomes</span></span>
  - <span data-ttu-id="d8fda-263">业务结果模板</span><span class="sxs-lookup"><span data-stu-id="d8fda-263">Business outcome template</span></span>
- <span data-ttu-id="d8fda-264">利益干系人/Exec 发起人购买/调整</span><span class="sxs-lookup"><span data-stu-id="d8fda-264">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="d8fda-265">业务案例平台</span><span class="sxs-lookup"><span data-stu-id="d8fda-265">Business case decks</span></span>
  - <span data-ttu-id="d8fda-266">财务模型</span><span class="sxs-lookup"><span data-stu-id="d8fda-266">Financial models</span></span>
  - <span data-ttu-id="d8fda-267">公司准备情况 - 文化</span><span class="sxs-lookup"><span data-stu-id="d8fda-267">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="d8fda-268">确定利益干系人</span><span class="sxs-lookup"><span data-stu-id="d8fda-268">Identify stakeholders</span></span>

<span data-ttu-id="d8fda-269">确定项目的利益干系人。</span><span class="sxs-lookup"><span data-stu-id="d8fda-269">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="d8fda-270">角色</span><span class="sxs-lookup"><span data-stu-id="d8fda-270">Role</span></span> |<span data-ttu-id="d8fda-271">Responsibilities</span><span class="sxs-lookup"><span data-stu-id="d8fda-271">Responsibilities</span></span> |<span data-ttu-id="d8fda-272">Department</span><span class="sxs-lookup"><span data-stu-id="d8fda-272">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="d8fda-273">执行发起 () </span><span class="sxs-lookup"><span data-stu-id="d8fda-273">Executive sponsor(s)</span></span>   | <span data-ttu-id="d8fda-274">向公司传达高级愿景和价值</span><span class="sxs-lookup"><span data-stu-id="d8fda-274">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="d8fda-275">行政领导</span><span class="sxs-lookup"><span data-stu-id="d8fda-275">Executive leadership</span></span>   |
| <span data-ttu-id="d8fda-276">项目主管 () </span><span class="sxs-lookup"><span data-stu-id="d8fda-276">Project lead(s)</span></span> | <span data-ttu-id="d8fda-277">监督整个启动执行和推出过程</span><span class="sxs-lookup"><span data-stu-id="d8fda-277">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="d8fda-278">项目管理</span><span class="sxs-lookup"><span data-stu-id="d8fda-278">Project management</span></span> |
| <span data-ttu-id="d8fda-279">知识管理员</span><span class="sxs-lookup"><span data-stu-id="d8fda-279">Knowledge administrators</span></span>| <span data-ttu-id="d8fda-280">创建和管理内容中心</span><span class="sxs-lookup"><span data-stu-id="d8fda-280">Create and manage the content centers</span></span> | <span data-ttu-id="d8fda-281">IT 或其他部门</span><span class="sxs-lookup"><span data-stu-id="d8fda-281">IT or other department</span></span>|
| <span data-ttu-id="d8fda-282">内容管理员和模型所有者</span><span class="sxs-lookup"><span data-stu-id="d8fda-282">Content managers and model owners</span></span>| <span data-ttu-id="d8fda-283">收集用例并创建和应用模型</span><span class="sxs-lookup"><span data-stu-id="d8fda-283">Gather use cases and create and apply models</span></span> | <span data-ttu-id="d8fda-284">任何部门</span><span class="sxs-lookup"><span data-stu-id="d8fda-284">Any department</span></span>|
| <span data-ttu-id="d8fda-285">支持者</span><span class="sxs-lookup"><span data-stu-id="d8fda-285">Champions</span></span> | <span data-ttu-id="d8fda-286">帮助宣传和管理投诉处理</span><span class="sxs-lookup"><span data-stu-id="d8fda-286">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="d8fda-287">任何部门 (员工) </span><span class="sxs-lookup"><span data-stu-id="d8fda-287">Any department (staff)</span></span> |
| <span data-ttu-id="d8fda-288">租户管理员</span><span class="sxs-lookup"><span data-stu-id="d8fda-288">Tenant administrator</span></span> | <span data-ttu-id="d8fda-289">配置租户级别设置</span><span class="sxs-lookup"><span data-stu-id="d8fda-289">Configure tenant-level settings</span></span> | <span data-ttu-id="d8fda-290">IT 部门</span><span class="sxs-lookup"><span data-stu-id="d8fda-290">IT department</span></span>|
| <span data-ttu-id="d8fda-291">Power Platform 管理员</span><span class="sxs-lookup"><span data-stu-id="d8fda-291">Power Platform administrator</span></span>| <span data-ttu-id="d8fda-292">配置常见数据服务环境</span><span class="sxs-lookup"><span data-stu-id="d8fda-292">Configure common data services environment</span></span> | <span data-ttu-id="d8fda-293">IT 部门</span><span class="sxs-lookup"><span data-stu-id="d8fda-293">IT department</span></span>|

> [!Note]
> <span data-ttu-id="d8fda-294">尽管我们建议在整个推出过程中完成其中每个角色，但你可能会发现，你无需所有角色都开始使用已识别的解决方案。</span><span class="sxs-lookup"><span data-stu-id="d8fda-294">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="d8fda-295">准备情况清单</span><span class="sxs-lookup"><span data-stu-id="d8fda-295">Readiness checklist</span></span>

<span data-ttu-id="d8fda-296">若要准备好实现 SharePoint Syntex，您需要：</span><span class="sxs-lookup"><span data-stu-id="d8fda-296">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![内容理解准备情况](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="d8fda-298">规划结束状态</span><span class="sxs-lookup"><span data-stu-id="d8fda-298">Plan the end state</span></span>
    - <span data-ttu-id="d8fda-299">文档理解模型是方法，而不是结尾。</span><span class="sxs-lookup"><span data-stu-id="d8fda-299">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="d8fda-300">通过以下方式规划利用提取的元数据的价值：</span><span class="sxs-lookup"><span data-stu-id="d8fda-300">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="d8fda-301">搜索</span><span class="sxs-lookup"><span data-stu-id="d8fda-301">Search</span></span>
      - <span data-ttu-id="d8fda-302">筛选和查看格式</span><span class="sxs-lookup"><span data-stu-id="d8fda-302">Filtering and view formatting</span></span>
      - <span data-ttu-id="d8fda-303">合规性</span><span class="sxs-lookup"><span data-stu-id="d8fda-303">Compliance</span></span>
      - <span data-ttu-id="d8fda-304">自动化</span><span class="sxs-lookup"><span data-stu-id="d8fda-304">Automation</span></span>
2. <span data-ttu-id="d8fda-305">标识</span><span class="sxs-lookup"><span data-stu-id="d8fda-305">Identify</span></span>
    - <span data-ttu-id="d8fda-306">了解现有信息体系结构和内容管理功能的使用。</span><span class="sxs-lookup"><span data-stu-id="d8fda-306">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="d8fda-307">任何现有内容类型是否适合模型？</span><span class="sxs-lookup"><span data-stu-id="d8fda-307">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="d8fda-308">元数据将改进哪些现有进程？</span><span class="sxs-lookup"><span data-stu-id="d8fda-308">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="d8fda-309">设计</span><span class="sxs-lookup"><span data-stu-id="d8fda-309">Design</span></span>
    - <span data-ttu-id="d8fda-310">设计信息体系结构、托管元数据和内容类型的方法</span><span class="sxs-lookup"><span data-stu-id="d8fda-310">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="d8fda-311">设计定义、创建、管理过程。</span><span class="sxs-lookup"><span data-stu-id="d8fda-311">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="d8fda-312">让组织参与</span><span class="sxs-lookup"><span data-stu-id="d8fda-312">Engage your organization</span></span>

1. <span data-ttu-id="d8fda-313">确定持有者、确认方案并制定项目计划。</span><span class="sxs-lookup"><span data-stu-id="d8fda-313">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="d8fda-314">配置设置并应用许可证。</span><span class="sxs-lookup"><span data-stu-id="d8fda-314">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="d8fda-315">开始认知和培训 – 招募冠军。</span><span class="sxs-lookup"><span data-stu-id="d8fda-315">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="d8fda-316">分步推出。</span><span class="sxs-lookup"><span data-stu-id="d8fda-316">Roll out in stages.</span></span>  
1. <span data-ttu-id="d8fda-317">收集反馈并循环。</span><span class="sxs-lookup"><span data-stu-id="d8fda-317">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="d8fda-318">随着使用情况的扩大，可根据需要规划任何 AI Builder 信用额度。</span><span class="sxs-lookup"><span data-stu-id="d8fda-318">As usage grows plan for any AI Builder credits as needed.</span></span>
