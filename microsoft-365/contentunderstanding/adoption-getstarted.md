---
title: Microsoft SharePoint 合成器采用：入门
description: 了解如何在组织中使用和实施 SharePoint Syntex，以帮助你解决业务问题。
ms.author: samanro
author: samanro
manager: pamgreen
ms.date: 7/20/2020
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection: enabler-strategic
ms.custom: Adopt
search.appverid: ''
localization_priority: Normal
ms.openlocfilehash: 95e1ad15a62762c8b28203e178d4d4ae7906e38a
ms.sourcegitcommit: 222fb7fe2b26dde3d8591b61cc02113d6135012c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/06/2021
ms.locfileid: "49760238"
---
# <a name="microsoft-sharepoint-syntex-adoption-get-started"></a><span data-ttu-id="bed79-103">Microsoft SharePoint 合成器采用：入门</span><span class="sxs-lookup"><span data-stu-id="bed79-103">Microsoft SharePoint Syntex adoption: Get started</span></span>

<span data-ttu-id="bed79-104">将 SharePoint 合成中可用的智能内容服务视为具有三个部分：</span><span class="sxs-lookup"><span data-stu-id="bed79-104">Think of the intelligent content services available in SharePoint Syntex as having three parts:</span></span>

- <span data-ttu-id="bed79-105">**内容理解：** 创建无代码 AI 模型以对内容进行分类和提取信息，以自动应用元数据进行知识发现和重用。</span><span class="sxs-lookup"><span data-stu-id="bed79-105">**Content understanding:** create no-code AI models to classify and extract information from content to automatically apply metadata for knowledge discovery and reuse.</span></span> <span data-ttu-id="bed79-106">了解有关内容[了解的内容。](document-understanding-overview.md)</span><span class="sxs-lookup"><span data-stu-id="bed79-106">Learn more about [content understanding](document-understanding-overview.md).</span></span>
- <span data-ttu-id="bed79-107">**内容处理：** 使用 Power Automate 自动捕获、获取和分类内容并简化以内容为中心的流程。</span><span class="sxs-lookup"><span data-stu-id="bed79-107">**Content processing:** Automate capture, ingestion and categorization of content and streamline content-centric processes using Power Automate.</span></span> <span data-ttu-id="bed79-108">详细了解内容 [处理](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bed79-108">Learn more about [content processing](form-processing-overview.md).</span></span>
- <span data-ttu-id="bed79-109">**内容合规性：** 通过与 Microsoft 信息保护的集成来控制和管理内容以提高安全性和治理。</span><span class="sxs-lookup"><span data-stu-id="bed79-109">**Content compliance:** Control and manage content to improve security and governance with integration to Microsoft Information Protection.</span></span>

<span data-ttu-id="bed79-110">借助新的 AI 服务和功能，可以使用 SharePoint Syntex 将内容理解和分类应用程序直接构建到内容管理流中：</span><span class="sxs-lookup"><span data-stu-id="bed79-110">With new AI services and capabilities, you can build content understanding and classification apps directly into the content management flow using SharePoint Syntex:</span></span>

|<span data-ttu-id="bed79-111">手动输入</span><span class="sxs-lookup"><span data-stu-id="bed79-111">Manual entry</span></span>| <span data-ttu-id="bed79-112">表单处理</span><span class="sxs-lookup"><span data-stu-id="bed79-112">Form processing</span></span> | <span data-ttu-id="bed79-113">文档理解</span><span class="sxs-lookup"><span data-stu-id="bed79-113">Document understanding</span></span> |
|:-------|:--------|:--------|
| <span data-ttu-id="bed79-114">任何内容的数据输入和大量工作。</span><span class="sxs-lookup"><span data-stu-id="bed79-114">Data entry and labor-intensive on any content.</span></span> | <span data-ttu-id="bed79-115">标识文件或从结构化或半结构化文档（如表单或发票）中提取数据。</span><span class="sxs-lookup"><span data-stu-id="bed79-115">Identify files and extract data from structured or semi-structured documents, such as forms or invoices.</span></span> |  <span data-ttu-id="bed79-116">标识和提取非结构化文档（如信函或合同）的数据，其中要提取的文本实体位于文档的句子或特定区域。</span><span class="sxs-lookup"><span data-stu-id="bed79-116">Identify and extract data from unstructured documents, such as letters or contracts, where the text entities you want to extract reside in sentences or specific regions of the document.</span></span> |
| <span data-ttu-id="bed79-117">交互式。</span><span class="sxs-lookup"><span data-stu-id="bed79-117">Interactive.</span></span>   |  <span data-ttu-id="bed79-118">自定义，协助。</span><span class="sxs-lookup"><span data-stu-id="bed79-118">Custom, assisted.</span></span>  | <span data-ttu-id="bed79-119">预建、自动化。</span><span class="sxs-lookup"><span data-stu-id="bed79-119">Pre-built, automated.</span></span> |
| <span data-ttu-id="bed79-120">工作人员。</span><span class="sxs-lookup"><span data-stu-id="bed79-120">People doing the work.</span></span> | <span data-ttu-id="bed79-121">由行业专家与中小型企业 (专家) 。</span><span class="sxs-lookup"><span data-stu-id="bed79-121">Taught by your subject matter experts (SMEs).</span></span> | <span data-ttu-id="bed79-122">SMES 参与较少。</span><span class="sxs-lookup"><span data-stu-id="bed79-122">SMEs are less involved.</span></span> |

<span data-ttu-id="bed79-123">下表介绍了 SharePoint Syntex 的可用性和许可：</span><span class="sxs-lookup"><span data-stu-id="bed79-123">The following table explains availability and licensing for SharePoint Syntex:</span></span>

| <span data-ttu-id="bed79-124">表单处理</span><span class="sxs-lookup"><span data-stu-id="bed79-124">Form processing</span></span> | <span data-ttu-id="bed79-125">文档理解</span><span class="sxs-lookup"><span data-stu-id="bed79-125">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="bed79-126">表单处理依赖于 Power Platform。</span><span class="sxs-lookup"><span data-stu-id="bed79-126">Form processing relies on Power Platform.</span></span> <br><span data-ttu-id="bed79-127">有关 Power Platform 和 AI Builder 的全局可用性的信息，请参阅 [Power Platform 可用性](https://dynamics.microsoft.com/geographic-availability/)。</span><span class="sxs-lookup"><span data-stu-id="bed79-127">For information about global availability for Power Platform and AI Builder, see [Power Platform availability](https://dynamics.microsoft.com/geographic-availability/).</span></span> | <span data-ttu-id="bed79-128">可在所有区域使用。</span><span class="sxs-lookup"><span data-stu-id="bed79-128">Available in all regions.</span></span> |
| <span data-ttu-id="bed79-129">使用 AI Builder 信用额度。</span><span class="sxs-lookup"><span data-stu-id="bed79-129">Uses AI Builder credits.</span></span><br><span data-ttu-id="bed79-130">可以批量购买 1M 的信用额度。</span><span class="sxs-lookup"><span data-stu-id="bed79-130">Credits can be purchased in batches of 1M.</span></span><br><span data-ttu-id="bed79-131">购买 300 多个 SharePoint 合成器许可证时，将包含 100 万个信用额度。</span><span class="sxs-lookup"><span data-stu-id="bed79-131">1M credits are included when 300+ SharePoint Syntex licenses are purchased.</span></span><br><span data-ttu-id="bed79-132">1M 信用将允许处理 2000 个文件页。</span><span class="sxs-lookup"><span data-stu-id="bed79-132">1M credits will allow processing of 2000 file pages.</span></span> | <span data-ttu-id="bed79-133">模型在所有拉丁字母语言中均可用。</span><span class="sxs-lookup"><span data-stu-id="bed79-133">Models work on all latin alphabet languages.</span></span> <span data-ttu-id="bed79-134">除了英语之外，还有德语、瑞典语、法语、西班牙语、意大利语和葡萄牙语。</span><span class="sxs-lookup"><span data-stu-id="bed79-134">In addition to English: German, Swedish, French, Spanish, Italian, and Portuguese.</span></span> |
| <span data-ttu-id="bed79-135">针对默认公共数据服务环境进行设置。</span><span class="sxs-lookup"><span data-stu-id="bed79-135">Provisioned against the default common data service environment.</span></span> | <span data-ttu-id="bed79-136">没有容量限制。</span><span class="sxs-lookup"><span data-stu-id="bed79-136">Does not have capacity restrictions.</span></span> |

<span data-ttu-id="bed79-137">有关 AI Builder 信用和单位详细信息，请参阅 [AI Builder 许可](https://docs.microsoft.com/ai-builder/administer-licensing)。</span><span class="sxs-lookup"><span data-stu-id="bed79-137">For more information about AI Builder credits and units, see [AI Builder licensing](https://docs.microsoft.com/ai-builder/administer-licensing).</span></span>

<span data-ttu-id="bed79-138">有两种不同的内容理解方式。</span><span class="sxs-lookup"><span data-stu-id="bed79-138">There are two different ways of understanding your content.</span></span> <span data-ttu-id="bed79-139">使用的模型类型基于文件格式和用例：</span><span class="sxs-lookup"><span data-stu-id="bed79-139">The model type you use is based on file format and use case:</span></span>

| <span data-ttu-id="bed79-140">表单处理</span><span class="sxs-lookup"><span data-stu-id="bed79-140">Form processing</span></span> | <span data-ttu-id="bed79-141">文档理解</span><span class="sxs-lookup"><span data-stu-id="bed79-141">Document understanding</span></span> |
|:-------|:-------|
| <span data-ttu-id="bed79-142">从文档库创建。</span><span class="sxs-lookup"><span data-stu-id="bed79-142">Created from document library.</span></span> | <span data-ttu-id="bed79-143">在内容中心（SharePoint 合成的一部分）中创建。</span><span class="sxs-lookup"><span data-stu-id="bed79-143">Created in the content center, part of SharePoint Syntex.</span></span> |
| <span data-ttu-id="bed79-144">在 AI 生成器中创建的模型。</span><span class="sxs-lookup"><span data-stu-id="bed79-144">Model created in AI builder.</span></span> | <span data-ttu-id="bed79-145">在本机界面中创建的模型。</span><span class="sxs-lookup"><span data-stu-id="bed79-145">Model created in native interface.</span></span> |
| <span data-ttu-id="bed79-146">用于半结构化文件格式。</span><span class="sxs-lookup"><span data-stu-id="bed79-146">Used for semi-structured file formats.</span></span> | <span data-ttu-id="bed79-147">用于非结构化文件格式。</span><span class="sxs-lookup"><span data-stu-id="bed79-147">Used for unstructured file formats.</span></span> |
| <span data-ttu-id="bed79-148">可设置分类器。</span><span class="sxs-lookup"><span data-stu-id="bed79-148">Settable classifier.</span></span> | <span data-ttu-id="bed79-149">带可选提取器可训练的分类器。</span><span class="sxs-lookup"><span data-stu-id="bed79-149">Trainable classifier with optional extractors.</span></span> |
| <span data-ttu-id="bed79-150">仅限于单个库。</span><span class="sxs-lookup"><span data-stu-id="bed79-150">Restricted to a single library.</span></span> | <span data-ttu-id="bed79-151">可应用于多个库。</span><span class="sxs-lookup"><span data-stu-id="bed79-151">Can be applied to multiple libraries.</span></span> |
| <span data-ttu-id="bed79-152">培训 PDF、JPG、PNG 格式，总计 50 MB/500 pp。</span><span class="sxs-lookup"><span data-stu-id="bed79-152">Train on PDF, JPG, PNG format, total 50 MB/500 pp.</span></span> | <span data-ttu-id="bed79-153">培训 5-10 个 PDF、Office 或电子邮件文件，包括负数示例。</span><span class="sxs-lookup"><span data-stu-id="bed79-153">Train on 5-10 PDF, Office, or email files, including negative examples.</span></span> |

<span data-ttu-id="bed79-154">SharePoint Syntex 与 Microsoft 365 合规性功能集成，如：</span><span class="sxs-lookup"><span data-stu-id="bed79-154">SharePoint Syntex integrates with Microsoft 365 compliance features like:</span></span>

- <span data-ttu-id="bed79-155">根据文档期限或外部事件定义记录策略的保留标签。</span><span class="sxs-lookup"><span data-stu-id="bed79-155">Retention labels that define records policy based on document age or external events.</span></span>
- <span data-ttu-id="bed79-156">设置 DLP、加密、共享和条件访问策略的敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="bed79-156">Sensitivity labels that set DLP, encryption, sharing, and conditional access policies.</span></span>

<span data-ttu-id="bed79-157">用户可以应用标签，也可以由 SharePoint 合成 AI 模型自动应用标签。</span><span class="sxs-lookup"><span data-stu-id="bed79-157">Users can apply labels, or they can be applied automatically by SharePoint Syntex AI models.</span></span> <span data-ttu-id="bed79-158">分析和文件计划提供标签使用和策略的扩展管理。</span><span class="sxs-lookup"><span data-stu-id="bed79-158">Analytics and file plans provide scaled management of label usage and policies.</span></span>

## <a name="identify-pilot-business-scenarios-to-optimize"></a><span data-ttu-id="bed79-159">确定要优化的试点业务方案</span><span class="sxs-lookup"><span data-stu-id="bed79-159">Identify pilot business scenarios to optimize</span></span>

<span data-ttu-id="bed79-160">若要准备在组织中使用 SharePoint 合成，首先需要了解它很有用的方案。</span><span class="sxs-lookup"><span data-stu-id="bed79-160">To prepare for using SharePoint Syntex in your organization, you first need to understand the scenarios in which it will be useful.</span></span> <span data-ttu-id="bed79-161">原因有助于确定需要哪种模型，以及如何根据应用模型的地方构建组织。</span><span class="sxs-lookup"><span data-stu-id="bed79-161">The why helps determine what model will be needed, and how to structure your org based on where the model will be applied.</span></span> <span data-ttu-id="bed79-162">下面是一些文档理解方案，可帮助您的组织：</span><span class="sxs-lookup"><span data-stu-id="bed79-162">Here are a few scenarios where document understanding can help your organization:</span></span>

- <span data-ttu-id="bed79-163">内容处理：处理合同、工作说明和其他类似表单的文档。</span><span class="sxs-lookup"><span data-stu-id="bed79-163">Content processing: Process contracts, statements of work, and other form-like documents.</span></span> <span data-ttu-id="bed79-164">输入表单，训练模型以了解和映射字段，然后运行表单以自动收集数据。</span><span class="sxs-lookup"><span data-stu-id="bed79-164">Intake the forms, train the model to understand and map the fields, and then run your forms through to automatically collect the data.</span></span> <span data-ttu-id="bed79-165">有关详细信息，请参阅 [表单处理概述](form-processing-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="bed79-165">For more information, see [Form processing overview](form-processing-overview.md).</span></span>
- <span data-ttu-id="bed79-166">发票分析：从发票提取相关详细信息，并确保它们符合策略或正在适当处理。</span><span class="sxs-lookup"><span data-stu-id="bed79-166">Invoice analysis: Pull out the relevant details from your invoices and make sure they're complying with policy or are being processed appropriately.</span></span>

<span data-ttu-id="bed79-167">考虑 SharePoint Syntex 可帮助组织的方法：</span><span class="sxs-lookup"><span data-stu-id="bed79-167">Think about ways that SharePoint Syntex can help your organization:</span></span>

- <span data-ttu-id="bed79-168">自动化业务流程</span><span class="sxs-lookup"><span data-stu-id="bed79-168">Automate business processes</span></span>
- <span data-ttu-id="bed79-169">提高搜索准确度</span><span class="sxs-lookup"><span data-stu-id="bed79-169">Improve search accuracy</span></span>
- <span data-ttu-id="bed79-170">管理合规性风险</span><span class="sxs-lookup"><span data-stu-id="bed79-170">Manage compliance risk</span></span>

### <a name="form-processing-scenario-example"></a><span data-ttu-id="bed79-171">表单处理方案示例</span><span class="sxs-lookup"><span data-stu-id="bed79-171">Form processing scenario example</span></span>

<span data-ttu-id="bed79-172">例如，您可以使用 SharePoint Syntex 和 Power Automate 功能设置流程来跟踪和监视发票。</span><span class="sxs-lookup"><span data-stu-id="bed79-172">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="bed79-173">设置用于存储发票文档的库。</span><span class="sxs-lookup"><span data-stu-id="bed79-173">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="bed79-174">训练模型以识别文档中的字段。</span><span class="sxs-lookup"><span data-stu-id="bed79-174">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="bed79-175">将要跟踪的字段提取到列表中。</span><span class="sxs-lookup"><span data-stu-id="bed79-175">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="bed79-176">设置流以针对特定事件通知您，例如：</span><span class="sxs-lookup"><span data-stu-id="bed79-176">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="bed79-177">将添加一张新发票。</span><span class="sxs-lookup"><span data-stu-id="bed79-177">A new invoice is added.</span></span>
    - <span data-ttu-id="bed79-178">发票已过期。</span><span class="sxs-lookup"><span data-stu-id="bed79-178">An invoice is past its due date.</span></span>
    - <span data-ttu-id="bed79-179">发票用于大于自动审批金额的金额。</span><span class="sxs-lookup"><span data-stu-id="bed79-179">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![使用 SharePoint Syntex 和 Power Automate 跟踪和监视发票](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="bed79-181">当您自动执行此方案时，您可以：</span><span class="sxs-lookup"><span data-stu-id="bed79-181">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="bed79-182">通过自动从发票中提取数据而不是手动提取数据来节省时间和资金。</span><span class="sxs-lookup"><span data-stu-id="bed79-182">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="bed79-183">通过使用工作流对发票采取行动并通知您任何问题，减少潜在错误并确保更好的合规性。</span><span class="sxs-lookup"><span data-stu-id="bed79-183">Reduce potential errors and ensure better compliance by using workflows to act on the invoices and notify you of any issues.</span></span>

### <a name="document-understanding-scenario-example"></a><span data-ttu-id="bed79-184">文档了解方案示例</span><span class="sxs-lookup"><span data-stu-id="bed79-184">Document understanding scenario example</span></span>

<span data-ttu-id="bed79-185">另一个示例是，您可以设置一个流程来识别贵公司与其他公司或个人的合同。</span><span class="sxs-lookup"><span data-stu-id="bed79-185">As another example, you can set up a process to identify contracts that your company has with other companies or individuals.</span></span> <span data-ttu-id="bed79-186">您可以设置一个模型以从这些合同中提取关键信息，如客户端名称、费用、日期或其他重要信息，并将其添加到库中作为字段，以便您可以快速查看。</span><span class="sxs-lookup"><span data-stu-id="bed79-186">You can set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add that to the library as fields you can quickly view.</span></span> <span data-ttu-id="bed79-187">您可以对文档库应用保留标签，以确保在一段特定时间之前无法删除合同，以适当遵守业务法规。</span><span class="sxs-lookup"><span data-stu-id="bed79-187">And you can apply a retention label on the document library to ensure that contracts cannot be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="bed79-188">从内容中心开始，为合同创建新的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="bed79-188">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="bed79-189">上载示例文档，查看正面和负面示例，然后运行培训以确定合同文档并查看结果。</span><span class="sxs-lookup"><span data-stu-id="bed79-189">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="bed79-190">培训提取程序以识别合同中的字段，如客户端名称、费用、日期，然后测试提取程序。</span><span class="sxs-lookup"><span data-stu-id="bed79-190">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="bed79-191">模型完成后，将模型应用到可在其中上载合同库。</span><span class="sxs-lookup"><span data-stu-id="bed79-191">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="bed79-192">将保留标签应用于日期字段，以便合同在库中保留组织需要合同的时间长度。</span><span class="sxs-lookup"><span data-stu-id="bed79-192">Apply a retention label to the date field, so that contracts are retained in the library for the length of time your organization requires for contracts.</span></span>

![使用 SharePoint 合成和保留标签跟踪和监视合同](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="bed79-194">当您自动执行此方案时，您可以：</span><span class="sxs-lookup"><span data-stu-id="bed79-194">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="bed79-195">通过自动从合同中提取数据而不是手动提取数据来节省时间和资金。</span><span class="sxs-lookup"><span data-stu-id="bed79-195">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="bed79-196">通过使用保留标签来确保更好的合规性，以确保适当地保留合同。</span><span class="sxs-lookup"><span data-stu-id="bed79-196">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

### <a name="tips-for-identifying-scenarios"></a><span data-ttu-id="bed79-197">用于标识方案的提示</span><span class="sxs-lookup"><span data-stu-id="bed79-197">Tips for identifying scenarios</span></span>

<span data-ttu-id="bed79-198">在考虑要考虑哪些业务方案时，请询问自己以下问题：</span><span class="sxs-lookup"><span data-stu-id="bed79-198">When thinking about which business scenarios to consider, ask yourself the following questions:</span></span>

- <span data-ttu-id="bed79-199">它是否解决了一个实际问题？</span><span class="sxs-lookup"><span data-stu-id="bed79-199">Does it solve a real problem?</span></span>
- <span data-ttu-id="bed79-200">它将被广泛使用还是具有广泛的影响？</span><span class="sxs-lookup"><span data-stu-id="bed79-200">Will it be widely used or have broad impact?</span></span>
- <span data-ttu-id="bed79-201">是否可获取？</span><span class="sxs-lookup"><span data-stu-id="bed79-201">Is it obtainable?</span></span>
- <span data-ttu-id="bed79-202">能否衡量成功？</span><span class="sxs-lookup"><span data-stu-id="bed79-202">Can you measure success?</span></span>

<span data-ttu-id="bed79-203">根据影响和易于实现确定方案优先级。</span><span class="sxs-lookup"><span data-stu-id="bed79-203">Prioritize scenarios based on impact and ease of implementation.</span></span> <span data-ttu-id="bed79-204">使初始焦点区域具有更高的影响，这些应用场景也可以轻松实现。</span><span class="sxs-lookup"><span data-stu-id="bed79-204">Make your initial focus area higher impact scenarios that can also be easily implemented.</span></span> <span data-ttu-id="bed79-205">取消难以实现的影响较低的方案的优先级。</span><span class="sxs-lookup"><span data-stu-id="bed79-205">De-prioritize lower impact scenarios that are hard to implement.</span></span>

## <a name="identify-roles--responsibilities"></a><span data-ttu-id="bed79-206">确定角色&职责</span><span class="sxs-lookup"><span data-stu-id="bed79-206">Identify roles & responsibilities</span></span>

<span data-ttu-id="bed79-207">确定贵组织中谁将构建和管理模型？</span><span class="sxs-lookup"><span data-stu-id="bed79-207">Determine who in your organization will build and manage the models?</span></span> <span data-ttu-id="bed79-208">可能涉及以下角色：</span><span class="sxs-lookup"><span data-stu-id="bed79-208">The following roles might be involved:</span></span>

| <span data-ttu-id="bed79-209">SharePoint/知识管理员</span><span class="sxs-lookup"><span data-stu-id="bed79-209">SharePoint/Knowledge admin</span></span> | <span data-ttu-id="bed79-210">Power Platform 管理员</span><span class="sxs-lookup"><span data-stu-id="bed79-210">Power Platform admin</span></span> | <span data-ttu-id="bed79-211">知识管理器</span><span class="sxs-lookup"><span data-stu-id="bed79-211">Knowledge manager</span></span> | <span data-ttu-id="bed79-212">模型所有者</span><span class="sxs-lookup"><span data-stu-id="bed79-212">Model owner</span></span> |
|:-------|:-------|:-------|:-------|
| <span data-ttu-id="bed79-213">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="bed79-213">AAD role</span></span>| <span data-ttu-id="bed79-214">ADD 角色</span><span class="sxs-lookup"><span data-stu-id="bed79-214">ADD role</span></span> | <span data-ttu-id="bed79-215">AAD 角色</span><span class="sxs-lookup"><span data-stu-id="bed79-215">AAD role</span></span> | <span data-ttu-id="bed79-216">支持者</span><span class="sxs-lookup"><span data-stu-id="bed79-216">Champions</span></span> |
| <span data-ttu-id="bed79-217">配置表单处理</span><span class="sxs-lookup"><span data-stu-id="bed79-217">Configure form processing</span></span> | <span data-ttu-id="bed79-218">配置用于表单处理的常见数据服务环境</span><span class="sxs-lookup"><span data-stu-id="bed79-218">Configure Common data service environment for form processing</span></span> | <span data-ttu-id="bed79-219">收集用例</span><span class="sxs-lookup"><span data-stu-id="bed79-219">Gather use cases</span></span> | <span data-ttu-id="bed79-220">收集业务用例</span><span class="sxs-lookup"><span data-stu-id="bed79-220">Gather business use cases</span></span> |
| <span data-ttu-id="bed79-221">管理内容中心和权限</span><span class="sxs-lookup"><span data-stu-id="bed79-221">Manage content centers and permissions</span></span>| <span data-ttu-id="bed79-222">购买和分配 AIB 信用</span><span class="sxs-lookup"><span data-stu-id="bed79-222">Purchase and allocate AIB credits</span></span> | <span data-ttu-id="bed79-223">建立最佳做法并查看模型分析</span><span class="sxs-lookup"><span data-stu-id="bed79-223">Establish best practices and review model analytics</span></span> | <span data-ttu-id="bed79-224">创建和应用模型</span><span class="sxs-lookup"><span data-stu-id="bed79-224">Create and apply models</span></span> |

<span data-ttu-id="bed79-225">知识管理器、业务流程所有者和内容模型所有者在组织中创建示例模型和推广采用。</span><span class="sxs-lookup"><span data-stu-id="bed79-225">Knowledge manager, Business Process Owner and Content model owner create sample models and champion adoption in the organization.</span></span>
<span data-ttu-id="bed79-226">可能涉及的其他人：合规性管理员、分类管理员。</span><span class="sxs-lookup"><span data-stu-id="bed79-226">Others who may be involved: Compliance admin, Taxonomy managers.</span></span>

<span data-ttu-id="bed79-227">他们将在哪里生成和应用模型？</span><span class="sxs-lookup"><span data-stu-id="bed79-227">Where will they build and apply the models?</span></span> <span data-ttu-id="bed79-228">是否有可以增强的现有流程或存储库？</span><span class="sxs-lookup"><span data-stu-id="bed79-228">Are there existing processes or repositories that could be enhanced?</span></span>

- <span data-ttu-id="bed79-229">表单处理：确定哪些网站将获取表单处理操作。</span><span class="sxs-lookup"><span data-stu-id="bed79-229">Form processing: Decide which sites will get Form processing action.</span></span>
- <span data-ttu-id="bed79-230">文档了解：您可以为不同的业务区域创建多个内容中心。</span><span class="sxs-lookup"><span data-stu-id="bed79-230">Document understanding: You can create multiple content centers for different business areas.</span></span>

## <a name="strategic-positioning"></a><span data-ttu-id="bed79-231">战略定位</span><span class="sxs-lookup"><span data-stu-id="bed79-231">Strategic positioning</span></span>

<span data-ttu-id="bed79-232">与利益干系人合作，确保他们符合使用 SharePoint 合成器的策略。</span><span class="sxs-lookup"><span data-stu-id="bed79-232">Work with stakeholders to make sure they are aligned on the strategy for using SharePoint Syntex.</span></span> <span data-ttu-id="bed79-233">研究并提供以下资源来帮助进行此定位：</span><span class="sxs-lookup"><span data-stu-id="bed79-233">Research and provide the following resources to help with this positioning:</span></span>

- <span data-ttu-id="bed79-234">业务成果：</span><span class="sxs-lookup"><span data-stu-id="bed79-234">Business outcomes:</span></span>
  - <span data-ttu-id="bed79-235">潜在财务结果</span><span class="sxs-lookup"><span data-stu-id="bed79-235">Potential fiscal outcomes</span></span>
  - <span data-ttu-id="bed79-236">潜在的灵活性结果</span><span class="sxs-lookup"><span data-stu-id="bed79-236">Potential agility outcomes</span></span>
  - <span data-ttu-id="bed79-237">业务结果模板</span><span class="sxs-lookup"><span data-stu-id="bed79-237">Business outcome template</span></span>
- <span data-ttu-id="bed79-238">利益干系人/Exec 发起人购买/调整</span><span class="sxs-lookup"><span data-stu-id="bed79-238">Stakeholders/Exec sponsor buy-in/alignment</span></span>
  - <span data-ttu-id="bed79-239">业务案例平台</span><span class="sxs-lookup"><span data-stu-id="bed79-239">Business case decks</span></span>
  - <span data-ttu-id="bed79-240">财务模型</span><span class="sxs-lookup"><span data-stu-id="bed79-240">Financial models</span></span>
  - <span data-ttu-id="bed79-241">公司准备情况 - 文化</span><span class="sxs-lookup"><span data-stu-id="bed79-241">Company readiness - culture</span></span>

## <a name="identify-stakeholders"></a><span data-ttu-id="bed79-242">确定利益干系人</span><span class="sxs-lookup"><span data-stu-id="bed79-242">Identify stakeholders</span></span>

<span data-ttu-id="bed79-243">确定项目的利益干系人。</span><span class="sxs-lookup"><span data-stu-id="bed79-243">Identify the stakeholders for your project.</span></span>

|<span data-ttu-id="bed79-244">Role</span><span class="sxs-lookup"><span data-stu-id="bed79-244">Role</span></span> |<span data-ttu-id="bed79-245">Responsibilities</span><span class="sxs-lookup"><span data-stu-id="bed79-245">Responsibilities</span></span> |<span data-ttu-id="bed79-246">Department</span><span class="sxs-lookup"><span data-stu-id="bed79-246">Department</span></span> |
|:-------|:-------|:--------|
| <span data-ttu-id="bed79-247">执行发起 () </span><span class="sxs-lookup"><span data-stu-id="bed79-247">Executive sponsor(s)</span></span>   | <span data-ttu-id="bed79-248">向公司传达高级愿景和价值</span><span class="sxs-lookup"><span data-stu-id="bed79-248">Communicate high-level vision and values to the company</span></span>   |  <span data-ttu-id="bed79-249">管理层领导</span><span class="sxs-lookup"><span data-stu-id="bed79-249">Executive leadership</span></span>   |
| <span data-ttu-id="bed79-250">项目主管 () </span><span class="sxs-lookup"><span data-stu-id="bed79-250">Project lead(s)</span></span> | <span data-ttu-id="bed79-251">监督整个启动执行和推出过程</span><span class="sxs-lookup"><span data-stu-id="bed79-251">Oversee the entire launch execution and rollout process</span></span> | <span data-ttu-id="bed79-252">项目管理</span><span class="sxs-lookup"><span data-stu-id="bed79-252">Project management</span></span> |
| <span data-ttu-id="bed79-253">知识管理员</span><span class="sxs-lookup"><span data-stu-id="bed79-253">Knowledge administrators</span></span>| <span data-ttu-id="bed79-254">创建和管理内容中心</span><span class="sxs-lookup"><span data-stu-id="bed79-254">Create and manage the content centers</span></span> | <span data-ttu-id="bed79-255">IT 或其他部门</span><span class="sxs-lookup"><span data-stu-id="bed79-255">IT or other department</span></span>|
| <span data-ttu-id="bed79-256">内容管理员和模型所有者</span><span class="sxs-lookup"><span data-stu-id="bed79-256">Content managers and model owners</span></span>| <span data-ttu-id="bed79-257">收集用例并创建和应用模型</span><span class="sxs-lookup"><span data-stu-id="bed79-257">Gather use cases and create and apply models</span></span> | <span data-ttu-id="bed79-258">任何部门</span><span class="sxs-lookup"><span data-stu-id="bed79-258">Any department</span></span>|
| <span data-ttu-id="bed79-259">支持者</span><span class="sxs-lookup"><span data-stu-id="bed79-259">Champions</span></span> | <span data-ttu-id="bed79-260">帮助宣传和管理投诉处理</span><span class="sxs-lookup"><span data-stu-id="bed79-260">Help evangelize and manage objection handling</span></span> | <span data-ttu-id="bed79-261">任何部门 (员工) </span><span class="sxs-lookup"><span data-stu-id="bed79-261">Any department (staff)</span></span> |
| <span data-ttu-id="bed79-262">租户管理员</span><span class="sxs-lookup"><span data-stu-id="bed79-262">Tenant administrator</span></span> | <span data-ttu-id="bed79-263">配置租户级设置</span><span class="sxs-lookup"><span data-stu-id="bed79-263">Configure tenant-level settings</span></span> | <span data-ttu-id="bed79-264">IT 部门</span><span class="sxs-lookup"><span data-stu-id="bed79-264">IT department</span></span>|
| <span data-ttu-id="bed79-265">Power Platform 管理员</span><span class="sxs-lookup"><span data-stu-id="bed79-265">Power Platform administrator</span></span>| <span data-ttu-id="bed79-266">配置公共数据服务环境</span><span class="sxs-lookup"><span data-stu-id="bed79-266">Configure common data services environment</span></span> | <span data-ttu-id="bed79-267">IT 部门</span><span class="sxs-lookup"><span data-stu-id="bed79-267">IT department</span></span>|

> [!Note]
> <span data-ttu-id="bed79-268">尽管我们建议在整个推出过程中完成其中每个角色，但你可能会发现，你无需全部开始使用已确定的解决方案。</span><span class="sxs-lookup"><span data-stu-id="bed79-268">Though we recommend having each of these roles fulfilled throughout your rollout, you may find that you don't require them all to get started with your identified solution.</span></span>

## <a name="readiness-checklist"></a><span data-ttu-id="bed79-269">准备情况清单</span><span class="sxs-lookup"><span data-stu-id="bed79-269">Readiness checklist</span></span>

<span data-ttu-id="bed79-270">若要准备好实现 SharePoint 合成，需要：</span><span class="sxs-lookup"><span data-stu-id="bed79-270">To get ready for implementing SharePoint Syntex, you need to:</span></span>

![内容理解的准备情况](../media/content-understanding/cu-adoption-readinesschecklist.png)

1. <span data-ttu-id="bed79-272">规划结束状态</span><span class="sxs-lookup"><span data-stu-id="bed79-272">Plan the end state</span></span>
    - <span data-ttu-id="bed79-273">文档理解模型是方法，而不是结尾。</span><span class="sxs-lookup"><span data-stu-id="bed79-273">Document understanding models are the means, not the end.</span></span>
    - <span data-ttu-id="bed79-274">通过以下方式规划利用提取的元数据的价值：</span><span class="sxs-lookup"><span data-stu-id="bed79-274">Plan for harnessing the value of extracted metadata with:</span></span>
      - <span data-ttu-id="bed79-275">搜索</span><span class="sxs-lookup"><span data-stu-id="bed79-275">Search</span></span>
      - <span data-ttu-id="bed79-276">筛选和查看格式</span><span class="sxs-lookup"><span data-stu-id="bed79-276">Filtering and view formatting</span></span>
      - <span data-ttu-id="bed79-277">合规性</span><span class="sxs-lookup"><span data-stu-id="bed79-277">Compliance</span></span>
      - <span data-ttu-id="bed79-278">自动化</span><span class="sxs-lookup"><span data-stu-id="bed79-278">Automation</span></span>
2. <span data-ttu-id="bed79-279">标识</span><span class="sxs-lookup"><span data-stu-id="bed79-279">Identify</span></span>
    - <span data-ttu-id="bed79-280">了解现有信息体系结构和内容管理功能的使用。</span><span class="sxs-lookup"><span data-stu-id="bed79-280">Understand existing information architecture and content management feature use.</span></span>
    - <span data-ttu-id="bed79-281">任何现有内容类型是否适合模型？</span><span class="sxs-lookup"><span data-stu-id="bed79-281">Are any existing content types good candidates for models?</span></span>
    - <span data-ttu-id="bed79-282">元数据将改进哪些现有进程？</span><span class="sxs-lookup"><span data-stu-id="bed79-282">What existing processes would be improved by metadata?</span></span>
3. <span data-ttu-id="bed79-283">设计</span><span class="sxs-lookup"><span data-stu-id="bed79-283">Design</span></span>
    - <span data-ttu-id="bed79-284">设计信息体系结构、托管元数据和内容类型的方法</span><span class="sxs-lookup"><span data-stu-id="bed79-284">Design your approach to information architecture, managed metadata and content types</span></span>
    - <span data-ttu-id="bed79-285">设计定义、创建、管理过程。</span><span class="sxs-lookup"><span data-stu-id="bed79-285">Design the process for definition, creation, management.</span></span>

## <a name="engage-your-organization"></a><span data-ttu-id="bed79-286">参与你的组织</span><span class="sxs-lookup"><span data-stu-id="bed79-286">Engage your organization</span></span>

1. <span data-ttu-id="bed79-287">确定持有者、确认方案以及制定项目计划。</span><span class="sxs-lookup"><span data-stu-id="bed79-287">Identify stake holders, confirm scenarios, and develop project plan.</span></span>
1. <span data-ttu-id="bed79-288">配置设置并应用许可证。</span><span class="sxs-lookup"><span data-stu-id="bed79-288">Configure settings and apply licenses.</span></span>
1. <span data-ttu-id="bed79-289">开始认知和培训 – 招募冠军。</span><span class="sxs-lookup"><span data-stu-id="bed79-289">Begin awareness and training – Recruit Champions.</span></span>
1. <span data-ttu-id="bed79-290">分阶段推出。</span><span class="sxs-lookup"><span data-stu-id="bed79-290">Roll out in stages.</span></span>  
1. <span data-ttu-id="bed79-291">收集反馈并循环。</span><span class="sxs-lookup"><span data-stu-id="bed79-291">Gather feedback and iterate.</span></span>
1. <span data-ttu-id="bed79-292">随着使用情况增长，根据需要规划任何 AI Builder 信用。</span><span class="sxs-lookup"><span data-stu-id="bed79-292">As usage grows plan for any AI Builder credits as needed.</span></span>
