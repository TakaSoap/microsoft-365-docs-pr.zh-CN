---
title: Microsoft SharePoint Syntex 的方案和用例
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: laurieellis
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
description: 查找有关如何在组织中SharePoint Syntex 的方案。
ms.openlocfilehash: b28239a304c8fab209436c12e6cdbffe160b7981
ms.sourcegitcommit: a3359982fea01339c7377e3ee89f223788cee0bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/28/2021
ms.locfileid: "52697055"
---
# <a name="scenarios-and-use-cases-for-microsoft-sharepoint-syntex"></a><span data-ttu-id="88f2f-103">Microsoft SharePoint Syntex 的方案和用例</span><span class="sxs-lookup"><span data-stu-id="88f2f-103">Scenarios and use cases for Microsoft SharePoint Syntex</span></span>

<span data-ttu-id="88f2f-104">使用以下示例方案可提示你了解如何在组织中SharePoint Syntex。</span><span class="sxs-lookup"><span data-stu-id="88f2f-104">Use the following example scenarios to prompt ideas about how you can use SharePoint Syntex in your organization.</span></span>

- [<span data-ttu-id="88f2f-105">应用场景：通过表单处理跟踪发票数据</span><span class="sxs-lookup"><span data-stu-id="88f2f-105">Scenario: Track data from invoices with form processing</span></span>](adoption-scenarios.md#scenario-track-data-from-invoices-with-form-processing)
- [<span data-ttu-id="88f2f-106">方案：通过了解文档来跟踪合同信息</span><span class="sxs-lookup"><span data-stu-id="88f2f-106">Scenario: Track information from contracts with document understanding</span></span>](adoption-scenarios.md#scenario-track-information-from-contracts-with-document-understanding)
- [<span data-ttu-id="88f2f-107">应用场景：避免记录管理、文档管理和合规性流程的风险（SharePoint整合）</span><span class="sxs-lookup"><span data-stu-id="88f2f-107">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>](adoption-scenarios.md#scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex)
- [<span data-ttu-id="88f2f-108">方案：捕获以前无法访问的文档的信息</span><span class="sxs-lookup"><span data-stu-id="88f2f-108">Scenario: Capture information from previously inaccessible documents</span></span>](adoption-scenarios.md#scenario-capture-information-from-previously-inaccessible-documents)
- [<span data-ttu-id="88f2f-109">方案：改进数据处理以提供见解和分析</span><span class="sxs-lookup"><span data-stu-id="88f2f-109">Scenario: Improve data processing to provide insights and analytics</span></span>](adoption-scenarios.md#scenario-improve-data-processing-to-provide-insights-and-analytics)
- [<span data-ttu-id="88f2f-110">方案：自动执行订单处理</span><span class="sxs-lookup"><span data-stu-id="88f2f-110">Scenario: Automate order processing</span></span>](adoption-scenarios.md#scenario-automate-order-processing)
- [<span data-ttu-id="88f2f-111">应用场景：简化护照续订流程</span><span class="sxs-lookup"><span data-stu-id="88f2f-111">Scenario: Simplify visa renewal process</span></span>](adoption-scenarios.md#scenario-simplify-visa-renewal-process)

## <a name="scenario-track-data-from-invoices-with-form-processing"></a><span data-ttu-id="88f2f-112">应用场景：通过表单处理跟踪发票数据</span><span class="sxs-lookup"><span data-stu-id="88f2f-112">Scenario: Track data from invoices with form processing</span></span>

<span data-ttu-id="88f2f-113">例如，可以使用 Syntex 和 SharePoint 功能Power Automate和监视发票来设置流程。</span><span class="sxs-lookup"><span data-stu-id="88f2f-113">For example, you can set up a process using SharePoint Syntex and Power Automate features to track and monitor invoices.</span></span>

1. <span data-ttu-id="88f2f-114">设置用于存储发票文档的库。</span><span class="sxs-lookup"><span data-stu-id="88f2f-114">Set up a library to store the invoice documents.</span></span>
1. <span data-ttu-id="88f2f-115">训练模型以识别文档中的字段。</span><span class="sxs-lookup"><span data-stu-id="88f2f-115">Train the model to recognize fields in the documents.</span></span>
1. <span data-ttu-id="88f2f-116">将要跟踪的字段提取到列表中。</span><span class="sxs-lookup"><span data-stu-id="88f2f-116">Extract the fields you want to track into a list.</span></span>
1. <span data-ttu-id="88f2f-117">设置一个流，以针对特定事件通知您，例如：</span><span class="sxs-lookup"><span data-stu-id="88f2f-117">Set up a flow to notify you for specific events, such as:</span></span>
    - <span data-ttu-id="88f2f-118">将添加一个新的发票。</span><span class="sxs-lookup"><span data-stu-id="88f2f-118">A new invoice is added.</span></span>
    - <span data-ttu-id="88f2f-119">发票已过期。</span><span class="sxs-lookup"><span data-stu-id="88f2f-119">An invoice is past its due date.</span></span>
    - <span data-ttu-id="88f2f-120">发票的金额大于自动审批金额。</span><span class="sxs-lookup"><span data-stu-id="88f2f-120">An invoice is for an amount that's larger than your automatic approval amount.</span></span>

![使用 Syntex 和 SharePoint 跟踪和Power Automate](../media/content-understanding/process-invoices-flow.png)

<span data-ttu-id="88f2f-122">当您自动执行此方案时，您可以：</span><span class="sxs-lookup"><span data-stu-id="88f2f-122">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="88f2f-123">通过自动从发票中提取数据而不是手动提取数据来节省时间和资金。</span><span class="sxs-lookup"><span data-stu-id="88f2f-123">Save time and money by automatically extracting data from the invoices instead of doing it manually.</span></span>
- <span data-ttu-id="88f2f-124">通过使用工作流检查发票并通知您任何问题，减少潜在错误并确保更好的合规性。</span><span class="sxs-lookup"><span data-stu-id="88f2f-124">Reduce potential errors and ensure better compliance by using workflows to check invoices and notify you of any issues.</span></span>

## <a name="scenario-track-information-from-contracts-with-document-understanding"></a><span data-ttu-id="88f2f-125">方案：通过了解文档来跟踪合同信息</span><span class="sxs-lookup"><span data-stu-id="88f2f-125">Scenario: Track information from contracts with document understanding</span></span>

<span data-ttu-id="88f2f-126">另一个示例是，您可以设置一个流程来识别贵公司与其他公司或个人的合同。</span><span class="sxs-lookup"><span data-stu-id="88f2f-126">As another example, you can set up a process to identify contracts your company has with other companies or individuals.</span></span> <span data-ttu-id="88f2f-127">设置一个模型以从这些合同中提取关键信息（如客户端名称、费用、日期或其他重要信息）并作为可快速查看的字段将信息添加到库中。</span><span class="sxs-lookup"><span data-stu-id="88f2f-127">Set up a model to extract key information from those contracts, such as the client name, fees, dates, or other important information, and add the information to the library as fields you can quickly view.</span></span> <span data-ttu-id="88f2f-128">在文档库上应用保留标签，以确保在一段特定时间之前无法删除合同，以适当遵守业务法规。</span><span class="sxs-lookup"><span data-stu-id="88f2f-128">Apply a retention label on the document library to ensure that contracts can't be deleted before a specific length of time for appropriate compliance with your business regulations.</span></span>

1. <span data-ttu-id="88f2f-129">从内容中心开始，为合同创建新的文档理解模型。</span><span class="sxs-lookup"><span data-stu-id="88f2f-129">Start at the content center and create a new document understanding model for contracts.</span></span>
1. <span data-ttu-id="88f2f-130">Upload示例文档查看正面和负面的示例，然后运行培训以确定合同文档并查看结果。</span><span class="sxs-lookup"><span data-stu-id="88f2f-130">Upload sample documents for positive and negative examples, then run the training to identify contract documents and review the results.</span></span>
1. <span data-ttu-id="88f2f-131">培训提取程序以识别合约中的字段，如客户端名称、费用、日期，然后测试提取程序。</span><span class="sxs-lookup"><span data-stu-id="88f2f-131">Train the extractor to identify fields in the contracts, such as the client name, fee, and date, and then test the extractor.</span></span>
1. <span data-ttu-id="88f2f-132">模型完成后，将模型应用到可在其中上载合约的库。</span><span class="sxs-lookup"><span data-stu-id="88f2f-132">When the model is complete, apply the model to a library where you can upload contracts.</span></span>
1. <span data-ttu-id="88f2f-133">将保留标签应用于日期字段，以便合同在库中保留所需时间。</span><span class="sxs-lookup"><span data-stu-id="88f2f-133">Apply a retention label to the date field, so that contracts are retained in the library for the required length of time.</span></span>

![使用合成和保留SharePoint跟踪和监视合约](../media/content-understanding/process-contracts-flow.png)

<span data-ttu-id="88f2f-135">当您自动执行此方案时，您可以：</span><span class="sxs-lookup"><span data-stu-id="88f2f-135">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="88f2f-136">通过自动从合同中提取数据而不是手动提取数据来节省时间和资金。</span><span class="sxs-lookup"><span data-stu-id="88f2f-136">Save time and money by automatically extracting data from the contracts instead of doing it manually.</span></span>
- <span data-ttu-id="88f2f-137">通过使用保留标签来确保更好地合规性，以确保适当地保留合同。</span><span class="sxs-lookup"><span data-stu-id="88f2f-137">Ensure better compliance by using retention labels to ensure that the contracts are retained appropriately.</span></span>

## <a name="scenario-avoid-risk-with-records-management-document-governance-and-compliance-processes-based-on-sharepoint-syntex"></a><span data-ttu-id="88f2f-138">应用场景：避免记录管理、文档管理和合规性流程的风险（SharePoint整合）</span><span class="sxs-lookup"><span data-stu-id="88f2f-138">Scenario: Avoid risk with records management, document governance, and compliance processes based on SharePoint Syntex</span></span>

<span data-ttu-id="88f2f-139">降低风险是大多数公司的共同目标。</span><span class="sxs-lookup"><span data-stu-id="88f2f-139">Reducing risks is a common goal for most companies.</span></span> <span data-ttu-id="88f2f-140">您可能需要：</span><span class="sxs-lookup"><span data-stu-id="88f2f-140">You might need:</span></span>

- <span data-ttu-id="88f2f-141">在整个租户中提供/强制执行信息治理的更好方法。</span><span class="sxs-lookup"><span data-stu-id="88f2f-141">A better way to provide/enforce information governance across your tenant.</span></span>
- <span data-ttu-id="88f2f-142">改进文档、电子邮件和视为项目的"记录"的其他形式的通信的分类系统。</span><span class="sxs-lookup"><span data-stu-id="88f2f-142">To improve the system for classification of documents, emails and other forms of communication considered ‘records’ for projects.</span></span>
- <span data-ttu-id="88f2f-143">审核收据、合同等，以确保遵守公司策略。</span><span class="sxs-lookup"><span data-stu-id="88f2f-143">To audit receipts, contracts, and so on, to ensure compliance with company policies.</span></span>
- <span data-ttu-id="88f2f-144">确保项目具有合规性所需的全部文档。</span><span class="sxs-lookup"><span data-stu-id="88f2f-144">To ensure that projects have all the documentation required for compliance.</span></span>

<span data-ttu-id="88f2f-145">设置一些流程以遵守 SharePoint Syntex，以捕获和适当分类、审核和标记需要更好治理的文档和表单。</span><span class="sxs-lookup"><span data-stu-id="88f2f-145">Set up some processes for compliance with SharePoint Syntex to capture and appropriately classify, audit, and flag documents and forms that need better governance.</span></span> <span data-ttu-id="88f2f-146">您可以依赖SharePoint来自动对内容进行分类，而不是依赖最终用户手动标记，或者依赖合规性团队手动应用管理规则和存档。</span><span class="sxs-lookup"><span data-stu-id="88f2f-146">You can rely on SharePoint Syntex to auto classify content rather than relying on end users to manually tag, or the compliance team to manually apply governance rules and archiving.</span></span> <span data-ttu-id="88f2f-147">您可以启用简化的搜索体验、管理数据卷、应用记录管理和保留策略、确保合规性以及最佳实践存档和清除实践。</span><span class="sxs-lookup"><span data-stu-id="88f2f-147">And you can enable a simplified search experience, manage data volumes, apply records management and retention policies, ensure compliance, and best practice archiving and purging practices.</span></span>

<span data-ttu-id="88f2f-148">当您自动执行此方案时，您感觉安全：</span><span class="sxs-lookup"><span data-stu-id="88f2f-148">When you automate this scenario, you can feel secure that:</span></span>

- <span data-ttu-id="88f2f-149">合规性得到维持，并且风险已降低。</span><span class="sxs-lookup"><span data-stu-id="88f2f-149">Compliance is upheld and risk is reduced.</span></span>
- <span data-ttu-id="88f2f-150">分类和记录管理一致且准确应用。</span><span class="sxs-lookup"><span data-stu-id="88f2f-150">Taxonomy and records management is consistently and accurately applied.</span></span>
- <span data-ttu-id="88f2f-151">控制内容卷。</span><span class="sxs-lookup"><span data-stu-id="88f2f-151">Content volumes are controlled.</span></span>
- <span data-ttu-id="88f2f-152">员工可以轻松在正确的上下文中发现正确的信息。</span><span class="sxs-lookup"><span data-stu-id="88f2f-152">Employees can easily discover the right information in the right context.</span></span>

## <a name="scenario-capture-information-from-previously-inaccessible-documents"></a><span data-ttu-id="88f2f-153">方案：捕获以前无法访问的文档的信息</span><span class="sxs-lookup"><span data-stu-id="88f2f-153">Scenario: Capture information from previously inaccessible documents</span></span>

<span data-ttu-id="88f2f-154">大多数组织都有法律文档、策略、合同、HR 文档和管理准则的大型存储库。</span><span class="sxs-lookup"><span data-stu-id="88f2f-154">Most organizations have large repositories of legal documents, policies, contracts, HR documents, and governance guidelines.</span></span> <span data-ttu-id="88f2f-155">挖掘这些数据存储以提取有价值的信息，例如：项目、部门、主题、人员、地理区域等。</span><span class="sxs-lookup"><span data-stu-id="88f2f-155">Mine these data stores to extract valuable information such as: projects, sectors, themes, people, geographical areas, and so on.</span></span>

<span data-ttu-id="88f2f-156">例如，HR 主管需要快速访问所有 HR 文档，包括简历、HR 策略和其他表单。</span><span class="sxs-lookup"><span data-stu-id="88f2f-156">For example, an HR director needs to quickly access all HR documents – including resumes, HR policies, and other forms.</span></span> <span data-ttu-id="88f2f-157">他们希望从简历和其他与 HR 相关的文档中快速识别必要信息，而无需手动对文档进行筛选。</span><span class="sxs-lookup"><span data-stu-id="88f2f-157">And they want to quickly identify necessary information from resumes and other HR-related documents without manually sifting through the documents.</span></span> <span data-ttu-id="88f2f-158">他们正在寻找一个解决方案，通过该解决方案，他们可以快速找到所需的信息，而无需手动查看数千份简历、HR 策略和其他可能分布于多个网站的文档。</span><span class="sxs-lookup"><span data-stu-id="88f2f-158">They’re looking for a solution that allows them to quickly find the information they need without having to manually look through thousands of resumes, HR policies, and other documentation that may be spread across several sites.</span></span>

<span data-ttu-id="88f2f-159">当您自动执行此方案时，您可以：</span><span class="sxs-lookup"><span data-stu-id="88f2f-159">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="88f2f-160">从数字内容中解锁知识。</span><span class="sxs-lookup"><span data-stu-id="88f2f-160">Unlock knowledge from digital content.</span></span>
- <span data-ttu-id="88f2f-161">对 HR 策略、简历、销售文档、技术蓝图、帐户计划和提取信息进行分类。</span><span class="sxs-lookup"><span data-stu-id="88f2f-161">Classify HR policies, resumes, sales documents, technical blueprints, account plans and extract information.</span></span>
- <span data-ttu-id="88f2f-162">快速找到要查找的正确信息或文档。</span><span class="sxs-lookup"><span data-stu-id="88f2f-162">Quickly find the correct information or document that you’re looking for.</span></span>
- <span data-ttu-id="88f2f-163">即时访问最新信息。</span><span class="sxs-lookup"><span data-stu-id="88f2f-163">Get instant access to the latest information.</span></span>
- <span data-ttu-id="88f2f-164">缩短搜索时间。</span><span class="sxs-lookup"><span data-stu-id="88f2f-164">Reduce search times.</span></span>

## <a name="scenario-improve-data-processing-to-provide-insights-and-analytics"></a><span data-ttu-id="88f2f-165">方案：改进数据处理以提供见解和分析</span><span class="sxs-lookup"><span data-stu-id="88f2f-165">Scenario: Improve data processing to provide insights and analytics</span></span>

<span data-ttu-id="88f2f-166">例如，一家SharePoint公司可以使用 Syntex 从 FDA 文档中提取信息，以回答其领导的问题。</span><span class="sxs-lookup"><span data-stu-id="88f2f-166">For example, a pharmaceutical company could use SharePoint Syntex to extract information from FDA documents to answer questions that their leaders have.</span></span> <span data-ttu-id="88f2f-167">使答案更易于访问可以缩短生成这些答案的时间，并增加数据的可用性以生成更准确的领导问题的答案。</span><span class="sxs-lookup"><span data-stu-id="88f2f-167">Having the answers more easily accessible can reduce the time needed to produce these answers and increase the availability of data to generate more accurate answers to leadership questions.</span></span>

<span data-ttu-id="88f2f-168">例如，项目经理需要快速提供来自我领导团队的产品相关问题的解答。</span><span class="sxs-lookup"><span data-stu-id="88f2f-168">For example, a project manager needs to quickly provide answers to product-related questions from my leadership team.</span></span> <span data-ttu-id="88f2f-169">他们需要在一个合并仪表板中查找与查询相关的信息和指标。</span><span class="sxs-lookup"><span data-stu-id="88f2f-169">They need to find information and metrics related to queries in one consolidated dashboard.</span></span> <span data-ttu-id="88f2f-170">他们正在寻找一个解决方案，从产品标签、产品 pamphlet 和其他材料中提取他们需要的信息，并生成一份合并报告，在向领导团队报告时可以使用该报告。</span><span class="sxs-lookup"><span data-stu-id="88f2f-170">They’re looking for a solution that extracts the information they need from product labels, product pamphlets, and other materials and generates a consolidated report that they can use when reporting back to their leadership team.</span></span>

<span data-ttu-id="88f2f-171">当您自动执行此方案时，您可以：</span><span class="sxs-lookup"><span data-stu-id="88f2f-171">When you automate this scenario, you can:</span></span>

- <span data-ttu-id="88f2f-172">减少生成答案的时间。</span><span class="sxs-lookup"><span data-stu-id="88f2f-172">Reduce time to produce answers.</span></span>
- <span data-ttu-id="88f2f-173">提高数据的可用性。</span><span class="sxs-lookup"><span data-stu-id="88f2f-173">Increase availability of data.</span></span>
- <span data-ttu-id="88f2f-174">提供更准确的答案。</span><span class="sxs-lookup"><span data-stu-id="88f2f-174">Provide more accurate answers.</span></span>

## <a name="scenario-automate-order-processing"></a><span data-ttu-id="88f2f-175">方案：自动执行订单处理</span><span class="sxs-lookup"><span data-stu-id="88f2f-175">Scenario: Automate order processing</span></span>

<span data-ttu-id="88f2f-176">使用 SharePoint Syntex，可以缩短手动处理客户订单的时间。</span><span class="sxs-lookup"><span data-stu-id="88f2f-176">With SharePoint Syntex, you can reduce the time of manual processing of customer orders.</span></span> <span data-ttu-id="88f2f-177">例如，您可以使用 OCR 处理将传真、电子邮件或纸张中的订单上载到 SharePoint，然后从这些订单中提取元数据，以便您可以使用自动化流程完成这些订单。</span><span class="sxs-lookup"><span data-stu-id="88f2f-177">For example, you can upload orders from fax, email, or paper into SharePoint by using OCR processing and then extract the metadata from those orders so you can fulfill them by using automated processes.</span></span>

<span data-ttu-id="88f2f-178">例如，供应链经理希望减少由手动数据输入导致的错误。</span><span class="sxs-lookup"><span data-stu-id="88f2f-178">For example, a supply chain manager wants to reduce errors caused by manual data entry.</span></span> <span data-ttu-id="88f2f-179">他们希望避免手动查看入站客户订单和数据输入， (、传真或电子邮件) ，以减少进入业务系统的错误。</span><span class="sxs-lookup"><span data-stu-id="88f2f-179">They want to avoid manual review and data entry of inbound customer orders (paper, fax, or e-mail) to reduce errors going into their business systems.</span></span> <span data-ttu-id="88f2f-180">他们希望有一个应用 AI 和机器学习技术的解决方案，以验证传入订单信息、提取核心数据并自动将数据推送到其 ERP 系统中，以便订单履行与对帐。</span><span class="sxs-lookup"><span data-stu-id="88f2f-180">They want a solution that applies AI and machine learning techniques to validate incoming order information, extract core data and automatically push it into their ERP system, for order fulfillment and reconciliation.</span></span>

<span data-ttu-id="88f2f-181">自动执行此方案时，可以确保：</span><span class="sxs-lookup"><span data-stu-id="88f2f-181">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="88f2f-182">订单和装运准确度提高。</span><span class="sxs-lookup"><span data-stu-id="88f2f-182">Order and shipment accuracy increases.</span></span>
- <span data-ttu-id="88f2f-183">减少与订单或发货错误相关的费用或处罚。</span><span class="sxs-lookup"><span data-stu-id="88f2f-183">Fees or penalties associated to order or shipment errors are reduced.</span></span>
- <span data-ttu-id="88f2f-184">发票或付款延迟减少。</span><span class="sxs-lookup"><span data-stu-id="88f2f-184">Delays in invoicing or payments decrease.</span></span>
- <span data-ttu-id="88f2f-185">人员成本降低。</span><span class="sxs-lookup"><span data-stu-id="88f2f-185">Personnel costs are reduced.</span></span>

## <a name="scenario-simplify-visa-renewal-process"></a><span data-ttu-id="88f2f-186">应用场景：简化护照续订流程</span><span class="sxs-lookup"><span data-stu-id="88f2f-186">Scenario: Simplify visa renewal process</span></span>

<span data-ttu-id="88f2f-187">SharePointSyntex 可以帮助你自动执行关键合同信息的提醒和续订。</span><span class="sxs-lookup"><span data-stu-id="88f2f-187">SharePoint Syntex can help you automate reminders and renewals for key contract information.</span></span> <span data-ttu-id="88f2f-188">例如，HR 主管需要确保员工的护照是最新的和/或及时续订的。</span><span class="sxs-lookup"><span data-stu-id="88f2f-188">For example, an HR director needs to ensure that employees’ visas are up to date and/or renewed on time.</span></span> <span data-ttu-id="88f2f-189">他们希望为用户提供一个简单直观的更新其 Visa 的过程。</span><span class="sxs-lookup"><span data-stu-id="88f2f-189">They want to give people a simple and intuitive process for updating their Visas.</span></span> <span data-ttu-id="88f2f-190">他们需要一个解决方案，从合同中提取续订日期，并自动在员工续订日期接近时发送提醒。</span><span class="sxs-lookup"><span data-stu-id="88f2f-190">They need a solution that extracts renewal dates from contracts and automatically sends employees reminders when their renewal dates are approaching.</span></span>

<span data-ttu-id="88f2f-191">自动执行此方案时，可以确保：</span><span class="sxs-lookup"><span data-stu-id="88f2f-191">When you automate this scenario, you can ensure that:</span></span>

- <span data-ttu-id="88f2f-192">不合规级别已降低。</span><span class="sxs-lookup"><span data-stu-id="88f2f-192">The levels of non-compliance are reduced.</span></span>
- <span data-ttu-id="88f2f-193">减少了手动提醒的数量。</span><span class="sxs-lookup"><span data-stu-id="88f2f-193">The number of manual reminders is reduced.</span></span>
- <span data-ttu-id="88f2f-194">针对不合规的罚款数量减少。</span><span class="sxs-lookup"><span data-stu-id="88f2f-194">The number of fines for non-compliance is reduced.</span></span>

## <a name="see-also"></a><span data-ttu-id="88f2f-195">另请参阅</span><span class="sxs-lookup"><span data-stu-id="88f2f-195">See also</span></span>

[<span data-ttu-id="88f2f-196">Microsoft SharePoint整合采用：入门</span><span class="sxs-lookup"><span data-stu-id="88f2f-196">Microsoft SharePoint Syntex adoption: Get started</span></span>](adoption-getstarted.md)