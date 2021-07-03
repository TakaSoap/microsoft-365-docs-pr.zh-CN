---
title: 使用 Microsoft 365 解决方案管理合同
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: ssquires
audience: admin
ms.topic: article
ms.date: ''
ms.prod: microsoft-365-enterprise
ms.collection: m365solution-managecontracts m365solution-overview
search.appverid: ''
localization_priority: None
ROBOTS: ''
description: 了解如何使用 Microsoft 365、SharePoint Syntex、SharePoint 列表、Microsoft Teams 和 Power Automate 解决方案管理Power Automate。
ms.openlocfilehash: bc2570b08add2fa93637b9f64931c5903795a079
ms.sourcegitcommit: 4886457c0d4248407bddec56425dba50bb60d9c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2021
ms.locfileid: "53287313"
---
# <a name="manage-contracts-using-a-microsoft-365-solution"></a><span data-ttu-id="f340c-103">使用 Microsoft 365 解决方案管理合同</span><span class="sxs-lookup"><span data-stu-id="f340c-103">Manage contracts using a Microsoft 365 solution</span></span>

<span data-ttu-id="f340c-104">本文介绍如何使用 SharePoint Syntex 和 Microsoft 365 的组件为组织创建合同Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f340c-104">This article describes how to create a contracts management solution for your organization by using SharePoint Syntex and components of Microsoft 365.</span></span> <span data-ttu-id="f340c-105">它提供了一个框架，可帮助你计划和创建满足你独特业务需求的解决方案。</span><span class="sxs-lookup"><span data-stu-id="f340c-105">It provides you with a framework to help you plan and create a solution that fits your unique business needs.</span></span> <span data-ttu-id="f340c-106">即使此解决方案讨论合同管理，也可以调整它以创建其他文档管理解决方案，如工作单或发票。</span><span class="sxs-lookup"><span data-stu-id="f340c-106">Even though this solution talks about contract management, you can adapt it to create other document management solutions, such as for statements of work or invoices.</span></span>

<span data-ttu-id="f340c-107">*此内容集记录由 Microsoft 365使用 Microsoft 新式工作解决方案策略团队开发的解决方案。*</span><span class="sxs-lookup"><span data-stu-id="f340c-107">*This content set documents a Microsoft 365 solution developed by Thomas Molbach with the Modern Work Solution Strategy Team at Microsoft.*</span></span>

## <a name="identify-the-business-problem"></a><span data-ttu-id="f340c-108">确定业务问题</span><span class="sxs-lookup"><span data-stu-id="f340c-108">Identify the business problem</span></span>

<span data-ttu-id="f340c-109">规划合同管理系统的第一步是了解您尝试解决的问题。</span><span class="sxs-lookup"><span data-stu-id="f340c-109">The first step in planning your contract management system is to understand the problem you're trying to solve.</span></span> <span data-ttu-id="f340c-110">对于此解决方案，需要解决四个关键问题：</span><span class="sxs-lookup"><span data-stu-id="f340c-110">For this solution, four key issues need to be addressed:</span></span>

- <span data-ttu-id="f340c-111">**确定合同**。</span><span class="sxs-lookup"><span data-stu-id="f340c-111">**Identify contracts**.</span></span> <span data-ttu-id="f340c-112">你的组织处理许多文档，如发票、合同、工作表等。</span><span class="sxs-lookup"><span data-stu-id="f340c-112">Your organization works with many documents, such as invoices, contracts, statements of work, and so on.</span></span>  <span data-ttu-id="f340c-113">一些是通过电子邮件发送的数字资产，一些是通过传统邮件发送的纸张资产。</span><span class="sxs-lookup"><span data-stu-id="f340c-113">Some are digital assets sent through email, and some are paper assets sent through traditional mail.</span></span> <span data-ttu-id="f340c-114">您需要一种方法来识别所有其他文档中的所有客户合同，然后对这些合同进行分类。</span><span class="sxs-lookup"><span data-stu-id="f340c-114">You need a way to identify all customer contracts from all other documents, and then classifying them as such.</span></span>

- <span data-ttu-id="f340c-115">**跟踪合同审批的历史记录**。</span><span class="sxs-lookup"><span data-stu-id="f340c-115">**Track the history of contract approvals**.</span></span> <span data-ttu-id="f340c-116">贵组织需要一种可靠的方法，以查找合同是否已获得批准或拒绝，以及是否已处理付款。</span><span class="sxs-lookup"><span data-stu-id="f340c-116">Your organization needs a reliable way to find whether contracts have been either approved or rejected, and whether payment has been processed.</span></span> 

- <span data-ttu-id="f340c-117">**用于管理合同审批的网站**。</span><span class="sxs-lookup"><span data-stu-id="f340c-117">**Site to manage contract approvals**.</span></span> <span data-ttu-id="f340c-118">组织需要建立一个协作网站，所有必需的利益干系人都可以在该网站中轻松审阅合同。</span><span class="sxs-lookup"><span data-stu-id="f340c-118">Your organization needs to set up a collaborative site in which all required stakeholders can easily review contracts.</span></span> <span data-ttu-id="f340c-119">利益干系人应能根据需要查看整个合同，但主要考虑查看每个合同 (例如客户名称、PO 编号和总成本) 。</span><span class="sxs-lookup"><span data-stu-id="f340c-119">Stakeholders should be able to review the whole contract if needed, but mostly care about seeing several key fields from each contract (for example, customer name, PO number, and total cost).</span></span> <span data-ttu-id="f340c-120">利益干系人应该能够轻松批准或拒绝传入合同。</span><span class="sxs-lookup"><span data-stu-id="f340c-120">Stakeholders should be able to easily approve or reject incoming contracts.</span></span>

- <span data-ttu-id="f340c-121">**路由已审阅合同**。</span><span class="sxs-lookup"><span data-stu-id="f340c-121">**Route reviewed contracts**.</span></span> <span data-ttu-id="f340c-122">需要通过特定工作流传送已批准和已拒绝合同。</span><span class="sxs-lookup"><span data-stu-id="f340c-122">Approved and rejected contracts need to be routed through a specific workflow.</span></span> <span data-ttu-id="f340c-123">批准的合同需要传送给第三方应用程序进行付款处理。</span><span class="sxs-lookup"><span data-stu-id="f340c-123">Approved contracts need to be routed to a third-party application for payment processing.</span></span> <span data-ttu-id="f340c-124">必须传送被拒绝的合同进行其他审阅。</span><span class="sxs-lookup"><span data-stu-id="f340c-124">Rejected contracts need to be routed for additional review.</span></span>

## <a name="overview-of-the-solution"></a><span data-ttu-id="f340c-125">解决方案概述</span><span class="sxs-lookup"><span data-stu-id="f340c-125">Overview of the solution</span></span>

  ![使用列表、列表SharePoint Syntex列表SharePoint列表Teams解决方案Power Automate。](../media/content-understanding/syntex-solution-manage-contracts-setup-steps.png)

<span data-ttu-id="f340c-127">此合同管理解决方案指南包括以下四个Microsoft 365：</span><span class="sxs-lookup"><span data-stu-id="f340c-127">This contract management solution guidance includes four components of Microsoft 365:</span></span>

- <span data-ttu-id="f340c-128">**Microsoft SharePoint Syntex：** 创建模型以标识和分类合同文件，然后从中提取适当的数据。</span><span class="sxs-lookup"><span data-stu-id="f340c-128">**Microsoft SharePoint Syntex**: Create models to identify and classify your contract files and then extract the appropriate data from them.</span></span>

- <span data-ttu-id="f340c-129">**Microsoft SharePoint列表**：使用新式列表SharePoint格式以业务友好格式显示合同。</span><span class="sxs-lookup"><span data-stu-id="f340c-129">**Microsoft SharePoint lists**: Use the formatting available in modern SharePoint lists to present contracts in a business-friendly format.</span></span>

- <span data-ttu-id="f340c-130">**Microsoft Teams：** 使用 Teams 渠道和关联选项卡的功能，让利益干系人能够审阅和管理合同。</span><span class="sxs-lookup"><span data-stu-id="f340c-130">**Microsoft Teams**: Use the functionality of a Teams channel and associated tabs to allow your stakeholders to review and manage contracts.</span></span>

- <span data-ttu-id="f340c-131">**Power Automate：** 使用流来指导合同完成审批过程，然后引导到第三方应用程序进行付款。</span><span class="sxs-lookup"><span data-stu-id="f340c-131">**Power Automate**: Use flows to guide contracts through the approval process, and then to a third-party application for payment.</span></span>

### <a name="how-it-all-works"></a><span data-ttu-id="f340c-132">一切如何工作</span><span class="sxs-lookup"><span data-stu-id="f340c-132">How it all works</span></span>

  ![显示工作流的解决方案图表，该工作流用于上载文档、提取数据、通知利益干系人以及批准或拒绝合同。](../media/content-understanding/syntex-solution-manage-contracts-overview.png)

1. <span data-ttu-id="f340c-134">将文档上载到SharePoint库中。</span><span class="sxs-lookup"><span data-stu-id="f340c-134">Documents are uploaded to a SharePoint document library.</span></span> <span data-ttu-id="f340c-135">一SharePoint Syntex文档理解模型已应用于文档库。</span><span class="sxs-lookup"><span data-stu-id="f340c-135">A SharePoint Syntex document understanding model has been applied to the document library.</span></span> <span data-ttu-id="f340c-136">它检查每个文件，以查看是否与经过训练要查找的"合同"内容类型匹配。</span><span class="sxs-lookup"><span data-stu-id="f340c-136">It checks each file to see if any match a "contract" content type it's trained to look for.</span></span> <span data-ttu-id="f340c-137">如果找到匹配项，它会将文件分类为"协定"，并更新文档的内容类型。</span><span class="sxs-lookup"><span data-stu-id="f340c-137">If it finds a match, it classifies the file as a "contract" and updates the content type for the document.</span></span>

2. <span data-ttu-id="f340c-138">模型还会从利益干系人感兴趣的每个合同文件中提取特定数据，如客户、承包商 *和费用金额*。  </span><span class="sxs-lookup"><span data-stu-id="f340c-138">The model also pulls out specific data from each contract file that stakeholders are interested in seeing, such as the *Client*, *Contractor*, and *Fee amount*.</span></span>

    <span data-ttu-id="f340c-139">以下页面是模型经过训练可识别的合约示例。</span><span class="sxs-lookup"><span data-stu-id="f340c-139">The following page is an example of a contract that the model is trained to identify.</span></span>

      ![合同示例。](../media/content-understanding/contract.png)

3. <span data-ttu-id="f340c-141">在Microsoft Teams中，所有利益干系人都是安全Teams通道的成员，其中文档库中的所有合同都可以看到批准或拒绝。</span><span class="sxs-lookup"><span data-stu-id="f340c-141">In Microsoft Teams, all stakeholders are members of a secure Teams channel in which all contracts in the document library are visible for approval or rejection.</span></span> <span data-ttu-id="f340c-142">通过使用Teams功能，当需要审阅新合同时，将通知所有利益干系人。</span><span class="sxs-lookup"><span data-stu-id="f340c-142">By using Teams functionality, all stakeholders are notified when new contracts need to be reviewed.</span></span>

4. <span data-ttu-id="f340c-143">通过使用Power Automate，合同将经过审批流程在 Teams 通道中移动。</span><span class="sxs-lookup"><span data-stu-id="f340c-143">By using Power Automate, contracts are moved through the approval process in the Teams channel.</span></span> <span data-ttu-id="f340c-144">当成员批准合同时，合同状态更改为已批准，通过 Teams 帖子通知所有成员，并创建一个行项目以显示合同已准备好付款。</span><span class="sxs-lookup"><span data-stu-id="f340c-144">When a member approves a contract, the contract status is changed to approved, all members are notified through a Teams post, and a line item is created to show that the contract is ready for payout.</span></span> <span data-ttu-id="f340c-145">此过程可以扩展为直接写入第三方财务应用程序进行支付。</span><span class="sxs-lookup"><span data-stu-id="f340c-145">This process can be extended to write directly to a third-party financial application for payment.</span></span>

5. <span data-ttu-id="f340c-146">当成员拒绝合同时，状态将更改为"已拒绝"，并且将通过一条帖子通知所有成员Teams通知。</span><span class="sxs-lookup"><span data-stu-id="f340c-146">When a member rejects a contract, the status is changed to rejected, and all members are notified through a Teams post.</span></span>

6. <span data-ttu-id="f340c-147">此解决方案的最终结果是业务流程自动部署。</span><span class="sxs-lookup"><span data-stu-id="f340c-147">The end result of this solution is an automated business process for your organization.</span></span> <span data-ttu-id="f340c-148">员工可以轻松使用自定义磁贴视图Teams启动和监视文档的审批工作流。</span><span class="sxs-lookup"><span data-stu-id="f340c-148">Employees can easily use the custom tile view in Teams to initiate and monitor the approval workflow of your documents.</span></span> 

     !["合同"选项卡。](../media/content-understanding/tile-view.png)

### <a name="licensing-requirements"></a><span data-ttu-id="f340c-150">许可要求</span><span class="sxs-lookup"><span data-stu-id="f340c-150">Licensing requirements</span></span>

<span data-ttu-id="f340c-151">此解决方案依赖于以下功能，这些功能均作为 Microsoft 365 企业版 (E1、E3、E5、F3) 或 Business (Basic、Standard 或 高级版) 许可证的一部分提供：</span><span class="sxs-lookup"><span data-stu-id="f340c-151">This solution relies on the following functionality, all available as part of a Microsoft 365 Enterprise (E1, E3, E5, F3) or Business (Basic, Standard, or Premium) license:</span></span>

- <span data-ttu-id="f340c-152">Microsoft SharePoint Syntex</span><span class="sxs-lookup"><span data-stu-id="f340c-152">Microsoft SharePoint Syntex</span></span>
- <span data-ttu-id="f340c-153">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f340c-153">Microsoft Teams</span></span>
- <span data-ttu-id="f340c-154">Power Automate</span><span class="sxs-lookup"><span data-stu-id="f340c-154">Power Automate</span></span>

## <a name="create-the-solution"></a><span data-ttu-id="f340c-155">创建解决方案</span><span class="sxs-lookup"><span data-stu-id="f340c-155">Create the solution</span></span>

<span data-ttu-id="f340c-156">以下各节将详细介绍如何配置合同管理解决方案。</span><span class="sxs-lookup"><span data-stu-id="f340c-156">The next sections will go into detail about how to configure your contracts management solution.</span></span> <span data-ttu-id="f340c-157">它分为三个步骤：</span><span class="sxs-lookup"><span data-stu-id="f340c-157">It's divided into three steps:</span></span>

- [<span data-ttu-id="f340c-158">步骤 1.使用SharePoint Syntex标识合同文件并提取数据</span><span class="sxs-lookup"><span data-stu-id="f340c-158">Step 1. Use SharePoint Syntex to identify contract files and extract data</span></span>](solution-manage-contracts-step1.md)
- [<span data-ttu-id="f340c-159">步骤 2.使用Microsoft Teams创建合同管理通道</span><span class="sxs-lookup"><span data-stu-id="f340c-159">Step 2. Use Microsoft Teams to create your contract management channel</span></span>](solution-manage-contracts-step2.md)
- [<span data-ttu-id="f340c-160">步骤 3.使用 Power Automate 创建处理合同的流程</span><span class="sxs-lookup"><span data-stu-id="f340c-160">Step 3. Use Power Automate to create your flow to process your contracts</span></span>](solution-manage-contracts-step3.md)
