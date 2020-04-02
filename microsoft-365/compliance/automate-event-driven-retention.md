---
title: 自动执行事件驱动的保留
f1.keywords:
- NOCSH
ms.author: cabailey
author: cabailey
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 本主题介绍如何使用 Microsoft 365 REST API 设置业务流程以通过事件自动执行保留。
ms.openlocfilehash: 0b2507497bfd90b892e95934a03f795045c9bac2
ms.sourcegitcommit: e695bcfc69203da5d3d96f3d6a891664a0e27ae2
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2020
ms.locfileid: "43105649"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="14d12-103">自动执行基于事件的保留</span><span class="sxs-lookup"><span data-stu-id="14d12-103">Automate event-based retention</span></span>

><span data-ttu-id="14d12-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="14d12-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="14d12-p101">了解组织中呈爆炸式增长的内容以及它们如何变为 ROT（冗余、过时、无关紧要的）内容是一件头等大事。为了继续应对法律、业务和法规遵从性挑战，组织必须能够保留和保护重要信息，并快速找到相关信息。仅保留重要的相关信息是组织取得成功的关键。</span><span class="sxs-lookup"><span data-stu-id="14d12-p101">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business. To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant. Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="14d12-p102">为了帮助满足此需求，组织可以利用 Office 365 安全与合规中心中的保留解决方案。可以使用[保留标签](labels.md)触发保留。保留标签允许选择[基于特定事件的保留期](event-driven-retention.md)。通常，保留期基于已知日期，如内容的创建日期或上次修改日期。但是，组织还要求根据事件的发生处理内容，例如在员工离开组织 7 年后进行处理。</span><span class="sxs-lookup"><span data-stu-id="14d12-p102">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center. Retention can be triggered by using [retention labels](labels.md). A retention label has the option to [base the retention period on a specific event](event-driven-retention.md). Typically, the retention period is based on a known date, such as the creation date or last modified date for the content. However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="14d12-p103">为了确保内容的合规处理，必须知道事件何时发生。随着内容量的快速增长，以及时且合规的方式保留和处理内容变得更具挑战性。</span><span class="sxs-lookup"><span data-stu-id="14d12-p103">To ensure compliant disposal of content, it's imperative to know when an event takes place. With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="14d12-p104">基于事件的保留可解决这个问题。本主题介绍如何使用 Microsoft 365 REST API 设置业务流程以通过事件自动执行保留。</span><span class="sxs-lookup"><span data-stu-id="14d12-p104">Event-based retention solves this problem. This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="14d12-117">关于基于事件的保留</span><span class="sxs-lookup"><span data-stu-id="14d12-117">About event-based retention</span></span>

<span data-ttu-id="14d12-p105">组织可以分为小型、中型或大型组织。每天创建和管理的业务文档、法律文档、员工文件，合同和产品文档的数量正在急剧增加。</span><span class="sxs-lookup"><span data-stu-id="14d12-p105">An organization can be small, medium, or large. The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="14d12-p106">例如，每天都有数十和数百名员工加入和离开组织。人力资源部门需要根据业务需求继续创建、更新或删除与员工相关的文档。此流程受为企业制定的不同保留策略的约束：</span><span class="sxs-lookup"><span data-stu-id="14d12-p106">For example, each day, tens and hundreds of employees are joining and leaving organizations. The HR department continues to create, update, or delete employee-related documents as per business requirements. This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="14d12-p107">**内容的保留期可以是已知日期**，如内容创建、上次修改或标记的日期。例如，你可以在创建文档后将其保留 7 年，然后将其删除。</span><span class="sxs-lookup"><span data-stu-id="14d12-p107">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled. For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="14d12-p108">**内容保留期也可以是未知日期**。例如，对于保留标签，你还可以根据特定类型事件的发生时间（如员工离开组织）来确定保留期。</span><span class="sxs-lookup"><span data-stu-id="14d12-p108">**The period of retention of content can also be an unknown date**. For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="14d12-p109">该事件会触发保留期的开始，并且会对已为该事件类型应用标签的所有内容强制执行标签的保留操作。这称为基于事件的保留。有关详细信息，请参阅[事件驱动保留概述](event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="14d12-p109">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them. This is called event-based retention. To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="14d12-130">设置基于事件的保留</span><span class="sxs-lookup"><span data-stu-id="14d12-130">Set up event-based retention</span></span>

<span data-ttu-id="14d12-131">本节介绍在保留内容之前需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="14d12-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="14d12-132">标识角色</span><span class="sxs-lookup"><span data-stu-id="14d12-132">Identify roles</span></span>

<span data-ttu-id="14d12-133">确定执行记录管理任务的组织中的不同角色，并且这些角色将负责有效且高效地保留业务文档。</span><span class="sxs-lookup"><span data-stu-id="14d12-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="14d12-134">**角色**</span><span class="sxs-lookup"><span data-stu-id="14d12-134">**Persona**</span></span>| <span data-ttu-id="14d12-135">**角色**</span><span class="sxs-lookup"><span data-stu-id="14d12-135">**Role**</span></span>|
  | - | - |
  | <span data-ttu-id="14d12-136">管理员</span><span class="sxs-lookup"><span data-stu-id="14d12-136">Admin</span></span> | <span data-ttu-id="14d12-137">在 SharePoint 中创建保留事件类型、保留标签和记录存储库</span><span class="sxs-lookup"><span data-stu-id="14d12-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="14d12-138">记录经理</span><span class="sxs-lookup"><span data-stu-id="14d12-138">Records Manager</span></span>                                  | <span data-ttu-id="14d12-139">提供保留策略和保留计划指南和合规性详细信息</span><span class="sxs-lookup"><span data-stu-id="14d12-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="14d12-140">系统管理员（企业）</span><span class="sxs-lookup"><span data-stu-id="14d12-140">System Admin (business)</span></span>                          | <span data-ttu-id="14d12-141">设置和管理外部系统以使用 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="14d12-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="14d12-142">信息工作者</span><span class="sxs-lookup"><span data-stu-id="14d12-142">Information Worker</span></span>                               | <span data-ttu-id="14d12-143">管理业务流程的生命周期（人力资源、财务、IT 等）</span><span class="sxs-lookup"><span data-stu-id="14d12-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="14d12-144">设置安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="14d12-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="14d12-145">合规性管理员可创建事件类型 &ndash; 例如“雇佣终止”、“合同到期”或“产品制造结束”。</span><span class="sxs-lookup"><span data-stu-id="14d12-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="14d12-146">（请在[事件驱动保留](event-driven-retention.md)中查看分步流程）。</span><span class="sxs-lookup"><span data-stu-id="14d12-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="14d12-147">合规性管理员根据事件创建保留标签，并将标签与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="14d12-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="14d12-148">保留标签具有 4 种类型的触发器：</span><span class="sxs-lookup"><span data-stu-id="14d12-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="14d12-149">创建日期</span><span class="sxs-lookup"><span data-stu-id="14d12-149">Create date</span></span>
                
    2. <span data-ttu-id="14d12-150">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="14d12-150">Last modified</span></span>
                
    3. <span data-ttu-id="14d12-151">标签日期（标记内容的时间）</span><span class="sxs-lookup"><span data-stu-id="14d12-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="14d12-152">基于事件</span><span class="sxs-lookup"><span data-stu-id="14d12-152">Event-based</span></span>
    
3. <span data-ttu-id="14d12-153">合规性管理员发布保留标签。</span><span class="sxs-lookup"><span data-stu-id="14d12-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="14d12-154">设置 SharePoint</span><span class="sxs-lookup"><span data-stu-id="14d12-154">Set up SharePoint</span></span>
   
<span data-ttu-id="14d12-155">若要创建记录存储库，合规性管理员需要：</span><span class="sxs-lookup"><span data-stu-id="14d12-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="14d12-156">创建 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="14d12-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="14d12-157">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="14d12-157">Does one of the following:</span></span>
        
    - <span data-ttu-id="14d12-p111">创建 SharePoint 库：在库级别设置基于事件的标签。有关详细信息，请参阅[将默认保留标签应用于 SharePoint 库、文件夹或文档集中的所有内容](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set)。</span><span class="sxs-lookup"><span data-stu-id="14d12-p111">Creates a SharePoint library: Set event-based label at the library level. For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
    - <span data-ttu-id="14d12-160">在 SharePoint 中设置文档集。</span><span class="sxs-lookup"><span data-stu-id="14d12-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="14d12-161">有关详细信息，请参阅[文档集简介](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234)。</span><span class="sxs-lookup"><span data-stu-id="14d12-161">For more information, see [Introduction to document sets](https://support.office.com/article/3DBCD93E-0BED-46B7-B1BA-B31DE2BCD234).</span></span>
      
3. <span data-ttu-id="14d12-162">为每个员工文档集分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="14d12-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="14d12-163">资产 ID 是组织使用的产品名称或代码，例如员工编号可以是资产 ID。</span><span class="sxs-lookup"><span data-stu-id="14d12-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="14d12-164">通过将资产 ID 分配给文件夹，该文件夹中的每个项目都会自动继承相同的资产 ID。</span><span class="sxs-lookup"><span data-stu-id="14d12-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="14d12-165">这意味着所有项目的保留期都可以由同一事件触发。</span><span class="sxs-lookup"><span data-stu-id="14d12-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="14d12-166">触发基于事件的保留的方法</span><span class="sxs-lookup"><span data-stu-id="14d12-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="14d12-167">可通过两种方法触发基于事件的保留：</span><span class="sxs-lookup"><span data-stu-id="14d12-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="14d12-168">**使用管理中心 UI** 此流程适用于一次保留较少内容或者不经常触发保留的情形，例如每月或每年保留一次。</span><span class="sxs-lookup"><span data-stu-id="14d12-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="14d12-169">有关此方法的详细信息，请参阅[事件驱动保留概述](event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="14d12-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="14d12-170">但是，这种触发保留的方法可能比较耗时且容易出错，这会影响可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="14d12-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="14d12-171">用于触发保留的自动化无缝解决方案可以增强数据的安全性和合规性。</span><span class="sxs-lookup"><span data-stu-id="14d12-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="14d12-p115">**使用 M365 REST API** 当一次保留大量内容和/或触发保留的频率通常是每天或每周时，可以使用此流程。该流程会检测你的业务线系统中何时发生事件，然后在安全与合规中心自动创建相关事件。每次发生事件时，你无需在 UI 中手动创建事件。</span><span class="sxs-lookup"><span data-stu-id="14d12-p115">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly. The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center. You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="14d12-175">使用 REST API 有两种选择：</span><span class="sxs-lookup"><span data-stu-id="14d12-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="14d12-176">**Microsoft Flow 或类似的应用程序**可用于自动触发事件的发生。</span><span class="sxs-lookup"><span data-stu-id="14d12-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="14d12-177">Microsoft Flow 是用于连接到其他系统的协调程序。</span><span class="sxs-lookup"><span data-stu-id="14d12-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="14d12-178">使用 Microsoft Flow 不需要自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="14d12-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="14d12-179">\*\*使用 PowerShell 或 HTTP 客户端调用 REST API \*\*使用 PowerShell（版本 6 或更高版本）调用 Microsoft 365 REST API 以创建事件。</span><span class="sxs-lookup"><span data-stu-id="14d12-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="14d12-180">Rest API 是一个支持多组 HTTP 操作（方法）的服务终结点，提供对服务资源的创建/检索/更新/删除操作权限。</span><span class="sxs-lookup"><span data-stu-id="14d12-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="14d12-181">有关详细信息，请参阅 [REST API 请求/响应组件](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)。</span><span class="sxs-lookup"><span data-stu-id="14d12-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="14d12-182">在这种情况下，通过使用 Microsoft 365 REST API，可以使用 POST 和 GET 操作（方法）来创建和检索事件。</span><span class="sxs-lookup"><span data-stu-id="14d12-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="14d12-183">示例场景</span><span class="sxs-lookup"><span data-stu-id="14d12-183">Example scenarios</span></span>

<span data-ttu-id="14d12-184">让我们以如下场景为例。</span><span class="sxs-lookup"><span data-stu-id="14d12-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="14d12-185">场景 1：员工离开组织</span><span class="sxs-lookup"><span data-stu-id="14d12-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="14d12-186">组织为每个员工创建和存储许多员工相关文档。</span><span class="sxs-lookup"><span data-stu-id="14d12-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="14d12-187">这些文档在每位员工的雇佣期内进行管理和保留。</span><span class="sxs-lookup"><span data-stu-id="14d12-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="14d12-188">但是，当员工离开组织或终止雇佣关系时，组织有义务根据法律和业务要求在规定的时间内保留该员工的文档。</span><span class="sxs-lookup"><span data-stu-id="14d12-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="14d12-189">现在，如果每天有多名员工离开组织，组织必须在每天触发数百甚至数千个文档的保留期。</span><span class="sxs-lookup"><span data-stu-id="14d12-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="14d12-190">除此之外，还需要根据员工记录的类型计算每个员工的保留期，即雇佣终止日期 + 天数、月数或年数。</span><span class="sxs-lookup"><span data-stu-id="14d12-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="14d12-191">例如，同一员工的职工薪酬档案与福利档案可能需要不同的保留期。</span><span class="sxs-lookup"><span data-stu-id="14d12-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="14d12-192">下图显示如何将多个标签与单个事件关联。</span><span class="sxs-lookup"><span data-stu-id="14d12-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="14d12-193">在此处，员工薪酬标签下的所有文件和员工福利标签下的所有文件都与单个事件相关联，即员工离开组织。</span><span class="sxs-lookup"><span data-stu-id="14d12-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="14d12-194">每个不同的文件都有不同的保留期。</span><span class="sxs-lookup"><span data-stu-id="14d12-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="14d12-195">因此，当员工离开组织时，每个标签中的这些文件都会经历不同的保留期。</span><span class="sxs-lookup"><span data-stu-id="14d12-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="14d12-196">为每个员工的每种文件类型或标签触发所有这些不同的保留期是一项极具挑战的任务。</span><span class="sxs-lookup"><span data-stu-id="14d12-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="14d12-197">想象一下，为多名员工做这件事将会如何。</span><span class="sxs-lookup"><span data-stu-id="14d12-197">Imagine doing this for multiple employees.</span></span>

![事件类型、事件和标签的关系图](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="14d12-199">为多个员工触发这些不同保留期的自动化流程将节省时间、无错误且极为高效。</span><span class="sxs-lookup"><span data-stu-id="14d12-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="14d12-200">**为此场景配置基于事件的自动保留：**</span><span class="sxs-lookup"><span data-stu-id="14d12-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![针对员工离开组织的场景的角色和操作关系图](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="14d12-202">管理员为文档集创建员工文件夹，如 Jane Doe、John Smith。</span><span class="sxs-lookup"><span data-stu-id="14d12-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="14d12-203">管理员将员工文件（如福利、工资单、员工薪酬）添加到每个员工文件夹中。</span><span class="sxs-lookup"><span data-stu-id="14d12-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="14d12-204">管理员为每个员工文件夹分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="14d12-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="14d12-205">SCC 管理员登录到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="14d12-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="14d12-206">SCC 管理员创建与员工相关的事件类型，例如“雇佣终止”和“员工雇用”事件。</span><span class="sxs-lookup"><span data-stu-id="14d12-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="14d12-207">SCC 管理员创建“员工留任”标签。</span><span class="sxs-lookup"><span data-stu-id="14d12-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="14d12-208">此“员工保留”标签将手动或自动发布并应用于 SharePoint 中的员工文件。</span><span class="sxs-lookup"><span data-stu-id="14d12-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="14d12-209">HR 管理系统（如 Workday）可以与 Microsoft Flow 一起定期运行以管理员工文件。</span><span class="sxs-lookup"><span data-stu-id="14d12-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="14d12-210">如果员工离开组织，Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定员工文件的保留期。</span><span class="sxs-lookup"><span data-stu-id="14d12-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="14d12-211">使用 Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="14d12-211">Using Microsoft Flow</span></span>

<span data-ttu-id="14d12-212">步骤 1 - 使用 Microsoft 365 REST API 创建用于创建事件的流</span><span class="sxs-lookup"><span data-stu-id="14d12-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![使用流创建事件](../media/automate-event-driven-retention-flow-1.png)

![使用流调用 REST API](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="14d12-215">创建事件</span><span class="sxs-lookup"><span data-stu-id="14d12-215">Create an event</span></span>

<span data-ttu-id="14d12-216">用于调用 REST API 的示例代码</span><span class="sxs-lookup"><span data-stu-id="14d12-216">Sample code to call the REST API</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="14d12-217">方法</span><span class="sxs-lookup"><span data-stu-id="14d12-217">Method</span></span></th>
<th><span data-ttu-id="14d12-218">POST</span><span class="sxs-lookup"><span data-stu-id="14d12-218">POST</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="14d12-219">URL</span><span class="sxs-lookup"><span data-stu-id="14d12-219">URL</span></span></td>
<td>https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="14d12-220">标头</span><span class="sxs-lookup"><span data-stu-id="14d12-220">Headers</span></span></td>
<td><span data-ttu-id="14d12-221">Content-Type</span><span class="sxs-lookup"><span data-stu-id="14d12-221">Content-Type</span></span></td>
<td><span data-ttu-id="14d12-222">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="14d12-222">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="14d12-223">正文</span><span class="sxs-lookup"><span data-stu-id="14d12-223">Body</span></span></td>
<td><p><span data-ttu-id="14d12-224">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-224">&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="14d12-225">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="14d12-225">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="14d12-226">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="14d12-226">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="14d12-227">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-227">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="14d12-228">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-228">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="14d12-229">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-229">&lt;updated&gt;9/9/2017 10:50:00 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="14d12-230">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-230">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="14d12-231">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-231">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="14d12-232">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-232">&lt;d:Name&gt;Employee Termination &lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="14d12-233">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-233">&lt;d:EventType&gt;99e0ae64-a4b8-40bb-82ed-645895610f56&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="14d12-234">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-234">&lt;d:SharePointAssetIdQuery&gt;1234&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="14d12-235">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-235">&lt;d:EventDateTime&gt;2018-12-01T00:00:00Z &lt;/d:EventDateTime&gt;</span></span></p>
<p><span data-ttu-id="14d12-236">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-236">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="14d12-237">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-237">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="14d12-238">&lt;/entry&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-238">&lt;/entry&gt;</span></span></p></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="14d12-239">身份验证</span><span class="sxs-lookup"><span data-stu-id="14d12-239">Authentication</span></span></td>
<td><span data-ttu-id="14d12-240">基本</span><span class="sxs-lookup"><span data-stu-id="14d12-240">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="14d12-241">用户名</span><span class="sxs-lookup"><span data-stu-id="14d12-241">Username</span></span></td>
<td><span data-ttu-id="14d12-242">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="14d12-242">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="14d12-243">密码</span><span class="sxs-lookup"><span data-stu-id="14d12-243">Password</span></span></td>
<td><span data-ttu-id="14d12-244">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="14d12-244">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="available-parameters"></a><span data-ttu-id="14d12-245">可用参数</span><span class="sxs-lookup"><span data-stu-id="14d12-245">Available parameters</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="14d12-246"><strong>参数</strong></span><span class="sxs-lookup"><span data-stu-id="14d12-246"><strong>Parameters</strong></span></span></th>
<th><span data-ttu-id="14d12-247"><strong>说明</strong></span><span class="sxs-lookup"><span data-stu-id="14d12-247"><strong>Description</strong></span></span></th>
<th><span data-ttu-id="14d12-248"><strong>注释</strong></span><span class="sxs-lookup"><span data-stu-id="14d12-248"><strong>Notes</strong></span></span></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="14d12-249">&lt;d:Name&gt;&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-249">&lt;d:Name&gt;&lt;/d:Name&gt;</span></span></td>
<td><span data-ttu-id="14d12-250">为事件提供唯一的名称，</span><span class="sxs-lookup"><span data-stu-id="14d12-250">Provide a unique name for the event,</span></span></td>
<td><span data-ttu-id="14d12-p121">不能包含尾随空格和以下字符：% \* \ &amp; &lt; &gt; | # ? , : ;</span><span class="sxs-lookup"><span data-stu-id="14d12-p121">Cannot contain trailing spaces, and the following characters: % \* \ &amp; &lt; &gt; | # ? , : ;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="14d12-253">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-253">&lt;d:EventType&gt;&lt;/d:EventType&gt;</span></span></td>
<td><span data-ttu-id="14d12-254">输入事件类型名称（或 Guid），</span><span class="sxs-lookup"><span data-stu-id="14d12-254">Enter event type name (or Guid),</span></span></td>
<td><span data-ttu-id="14d12-p122">示例：“雇佣终止”。事件类型必须与保留标签相关联。</span><span class="sxs-lookup"><span data-stu-id="14d12-p122">Example: “Employee termination”. Event type has to be associated with a retention label.</span></span></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="14d12-257">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-257">&lt;d:SharePointAssetIdQuery&gt;&lt;/d:SharePointAssetIdQuery&gt;</span></span></td>
<td><span data-ttu-id="14d12-258">输入“ComplianceAssetId:” + 员工 Id</span><span class="sxs-lookup"><span data-stu-id="14d12-258">Enter “ComplianceAssetId:” + employee Id</span></span></td>
<td><span data-ttu-id="14d12-259">示例：&quot;ComplianceAssetId:12345&quot;</span><span class="sxs-lookup"><span data-stu-id="14d12-259">Example:&quot;ComplianceAssetId:12345&quot;</span></span></td>
</tr>
<tr class="even">
<td><span data-ttu-id="14d12-260">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-260">&lt;d:EventDateTime&gt;&lt;/d:EventDateTime&gt;</span></span></td>
<td><span data-ttu-id="14d12-261">事件日期和时间</span><span class="sxs-lookup"><span data-stu-id="14d12-261">Event Date and Time</span></span></td>
<td><p><span data-ttu-id="14d12-262">格式：yyyy-MM-ddTHH:mm:ssZ，示例：</span><span class="sxs-lookup"><span data-stu-id="14d12-262">Format: yyyy-MM-ddTHH:mm:ssZ, Example:</span></span></p>
<p><span data-ttu-id="14d12-263">2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="14d12-263">2018-12-01T00:00:00Z</span></span></p></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="14d12-264">响应代码</span><span class="sxs-lookup"><span data-stu-id="14d12-264">Response codes</span></span>

| <span data-ttu-id="14d12-265">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="14d12-265">**Response Code**</span></span> | <span data-ttu-id="14d12-266">**说明**</span><span class="sxs-lookup"><span data-stu-id="14d12-266">**Description**</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="14d12-267">302</span><span class="sxs-lookup"><span data-stu-id="14d12-267">302</span></span>               | <span data-ttu-id="14d12-268">重定向</span><span class="sxs-lookup"><span data-stu-id="14d12-268">Redirect</span></span>              |
| <span data-ttu-id="14d12-269">201</span><span class="sxs-lookup"><span data-stu-id="14d12-269">201</span></span>               | <span data-ttu-id="14d12-270">已创建</span><span class="sxs-lookup"><span data-stu-id="14d12-270">Created</span></span>               |
| <span data-ttu-id="14d12-271">403</span><span class="sxs-lookup"><span data-stu-id="14d12-271">403</span></span>               | <span data-ttu-id="14d12-272">授权失败</span><span class="sxs-lookup"><span data-stu-id="14d12-272">Authorization Failed</span></span>  |
| <span data-ttu-id="14d12-273">401</span><span class="sxs-lookup"><span data-stu-id="14d12-273">401</span></span>               | <span data-ttu-id="14d12-274">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="14d12-274">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="14d12-275">根据时间范围获取事件</span><span class="sxs-lookup"><span data-stu-id="14d12-275">Get Events based on time range</span></span>

<table>
<thead>
<tr class="header">
<th><span data-ttu-id="14d12-276">方法</span><span class="sxs-lookup"><span data-stu-id="14d12-276">Method</span></span></th>
<th><span data-ttu-id="14d12-277">GET</span><span class="sxs-lookup"><span data-stu-id="14d12-277">GET</span></span></th>
<th></th>
</tr>
</thead>
<tbody>
<tr class="odd">
<td><span data-ttu-id="14d12-278">URL</span><span class="sxs-lookup"><span data-stu-id="14d12-278">URL</span></span></td>
<td><ol start="4" type="1">
<li><p><span data-ttu-id="14d12-279">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span><span class="sxs-lookup"><span data-stu-id="14d12-279">https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&amp;EndDateTime=2019-01-16</span></span></p></li>
</ol></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="14d12-280">标头</span><span class="sxs-lookup"><span data-stu-id="14d12-280">Headers</span></span></td>
<td><span data-ttu-id="14d12-281">Content-Type</span><span class="sxs-lookup"><span data-stu-id="14d12-281">Content-Type</span></span></td>
<td><span data-ttu-id="14d12-282">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="14d12-282">application/atom+xml</span></span></td>
</tr>
<tr class="odd">
<td></td>
<td></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="14d12-283">身份验证</span><span class="sxs-lookup"><span data-stu-id="14d12-283">Authentication</span></span></td>
<td><span data-ttu-id="14d12-284">基本</span><span class="sxs-lookup"><span data-stu-id="14d12-284">Basic</span></span></td>
<td></td>
</tr>
<tr class="odd">
<td><span data-ttu-id="14d12-285">用户名</span><span class="sxs-lookup"><span data-stu-id="14d12-285">Username</span></span></td>
<td><span data-ttu-id="14d12-286">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="14d12-286">“Complianceuser”</span></span></td>
<td></td>
</tr>
<tr class="even">
<td><span data-ttu-id="14d12-287">密码</span><span class="sxs-lookup"><span data-stu-id="14d12-287">Password</span></span></td>
<td><span data-ttu-id="14d12-288">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="14d12-288">“Compliancepassword”</span></span></td>
<td></td>
</tr>
</tbody>
</table>

##### <a name="response-codes"></a><span data-ttu-id="14d12-289">响应代码</span><span class="sxs-lookup"><span data-stu-id="14d12-289">Response codes</span></span>

| <span data-ttu-id="14d12-290">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="14d12-290">**Response Code**</span></span> | <span data-ttu-id="14d12-291">**说明**</span><span class="sxs-lookup"><span data-stu-id="14d12-291">**Description**</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="14d12-292">200</span><span class="sxs-lookup"><span data-stu-id="14d12-292">200</span></span>               | <span data-ttu-id="14d12-293">正常，atom+ xml 中的事件列表</span><span class="sxs-lookup"><span data-stu-id="14d12-293">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="14d12-294">404</span><span class="sxs-lookup"><span data-stu-id="14d12-294">404</span></span>               | <span data-ttu-id="14d12-295">未找到</span><span class="sxs-lookup"><span data-stu-id="14d12-295">Not found</span></span>                         |
| <span data-ttu-id="14d12-296">302</span><span class="sxs-lookup"><span data-stu-id="14d12-296">302</span></span>               | <span data-ttu-id="14d12-297">重定向</span><span class="sxs-lookup"><span data-stu-id="14d12-297">Redirect</span></span>                          |
| <span data-ttu-id="14d12-298">401</span><span class="sxs-lookup"><span data-stu-id="14d12-298">401</span></span>               | <span data-ttu-id="14d12-299">授权失败</span><span class="sxs-lookup"><span data-stu-id="14d12-299">Authorization Failed</span></span>              |
| <span data-ttu-id="14d12-300">403</span><span class="sxs-lookup"><span data-stu-id="14d12-300">403</span></span>               | <span data-ttu-id="14d12-301">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="14d12-301">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="14d12-302">按 ID 获取事件。</span><span class="sxs-lookup"><span data-stu-id="14d12-302">Get an event by ID</span></span>

| <span data-ttu-id="14d12-303">方法</span><span class="sxs-lookup"><span data-stu-id="14d12-303">Method</span></span>         | <span data-ttu-id="14d12-304">GET</span><span class="sxs-lookup"><span data-stu-id="14d12-304">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="14d12-305">URL</span><span class="sxs-lookup"><span data-stu-id="14d12-305">URL</span></span>            | <span data-ttu-id="14d12-306">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="14d12-306">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="14d12-307">标头</span><span class="sxs-lookup"><span data-stu-id="14d12-307">Header</span></span>         | <span data-ttu-id="14d12-308">Content-Type</span><span class="sxs-lookup"><span data-stu-id="14d12-308">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="14d12-309">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="14d12-309">application/atom+xml</span></span> |
| <span data-ttu-id="14d12-310">身份验证</span><span class="sxs-lookup"><span data-stu-id="14d12-310">Authentication</span></span> | <span data-ttu-id="14d12-311">基本</span><span class="sxs-lookup"><span data-stu-id="14d12-311">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="14d12-312">用户名</span><span class="sxs-lookup"><span data-stu-id="14d12-312">Username</span></span>       | <span data-ttu-id="14d12-313">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="14d12-313">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="14d12-314">密码</span><span class="sxs-lookup"><span data-stu-id="14d12-314">Password</span></span>       | <span data-ttu-id="14d12-315">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="14d12-315">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="14d12-316">响应代码</span><span class="sxs-lookup"><span data-stu-id="14d12-316">Response codes</span></span>

| <span data-ttu-id="14d12-317">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="14d12-317">**Response Code**</span></span> | <span data-ttu-id="14d12-318">**说明**</span><span class="sxs-lookup"><span data-stu-id="14d12-318">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="14d12-319">200</span><span class="sxs-lookup"><span data-stu-id="14d12-319">200</span></span>               | <span data-ttu-id="14d12-320">正常，响应正文包含 atom+xml 中的事件</span><span class="sxs-lookup"><span data-stu-id="14d12-320">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="14d12-321">404</span><span class="sxs-lookup"><span data-stu-id="14d12-321">404</span></span>               | <span data-ttu-id="14d12-322">未找到</span><span class="sxs-lookup"><span data-stu-id="14d12-322">Not found</span></span>                                            |
| <span data-ttu-id="14d12-323">302</span><span class="sxs-lookup"><span data-stu-id="14d12-323">302</span></span>               | <span data-ttu-id="14d12-324">重定向</span><span class="sxs-lookup"><span data-stu-id="14d12-324">Redirect</span></span>                                             |
| <span data-ttu-id="14d12-325">401</span><span class="sxs-lookup"><span data-stu-id="14d12-325">401</span></span>               | <span data-ttu-id="14d12-326">授权失败</span><span class="sxs-lookup"><span data-stu-id="14d12-326">Authorization Failed</span></span>                                 |
| <span data-ttu-id="14d12-327">403</span><span class="sxs-lookup"><span data-stu-id="14d12-327">403</span></span>               | <span data-ttu-id="14d12-328">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="14d12-328">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="14d12-329">按名称获取事件</span><span class="sxs-lookup"><span data-stu-id="14d12-329">Get an event by name</span></span>

| <span data-ttu-id="14d12-330">方法</span><span class="sxs-lookup"><span data-stu-id="14d12-330">Method</span></span>         | <span data-ttu-id="14d12-331">GET</span><span class="sxs-lookup"><span data-stu-id="14d12-331">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="14d12-332">URL</span><span class="sxs-lookup"><span data-stu-id="14d12-332">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="14d12-333">标头</span><span class="sxs-lookup"><span data-stu-id="14d12-333">Headers</span></span>        | <span data-ttu-id="14d12-334">Content-Type</span><span class="sxs-lookup"><span data-stu-id="14d12-334">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="14d12-335">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="14d12-335">application/atom+xml</span></span> |
| <span data-ttu-id="14d12-336">身份验证</span><span class="sxs-lookup"><span data-stu-id="14d12-336">Authentication</span></span> | <span data-ttu-id="14d12-337">基本</span><span class="sxs-lookup"><span data-stu-id="14d12-337">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="14d12-338">用户名</span><span class="sxs-lookup"><span data-stu-id="14d12-338">Username</span></span>       | <span data-ttu-id="14d12-339">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="14d12-339">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="14d12-340">密码</span><span class="sxs-lookup"><span data-stu-id="14d12-340">Password</span></span>       | <span data-ttu-id="14d12-341">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="14d12-341">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="14d12-342">响应代码</span><span class="sxs-lookup"><span data-stu-id="14d12-342">Response codes</span></span>

| <span data-ttu-id="14d12-343">**响应代码**</span><span class="sxs-lookup"><span data-stu-id="14d12-343">**Response Code**</span></span> | <span data-ttu-id="14d12-344">**说明**</span><span class="sxs-lookup"><span data-stu-id="14d12-344">**Description**</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="14d12-345">200</span><span class="sxs-lookup"><span data-stu-id="14d12-345">200</span></span>               | <span data-ttu-id="14d12-346">正常，响应正文包含 atom+xml 中的事件</span><span class="sxs-lookup"><span data-stu-id="14d12-346">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="14d12-347">404</span><span class="sxs-lookup"><span data-stu-id="14d12-347">404</span></span>               | <span data-ttu-id="14d12-348">未找到</span><span class="sxs-lookup"><span data-stu-id="14d12-348">Not found</span></span>                                            |
| <span data-ttu-id="14d12-349">302</span><span class="sxs-lookup"><span data-stu-id="14d12-349">302</span></span>               | <span data-ttu-id="14d12-350">重定向</span><span class="sxs-lookup"><span data-stu-id="14d12-350">Redirect</span></span>                                             |
| <span data-ttu-id="14d12-351">401</span><span class="sxs-lookup"><span data-stu-id="14d12-351">401</span></span>               | <span data-ttu-id="14d12-352">授权失败</span><span class="sxs-lookup"><span data-stu-id="14d12-352">Authorization Failed</span></span>                                 |
| <span data-ttu-id="14d12-353">403</span><span class="sxs-lookup"><span data-stu-id="14d12-353">403</span></span>               | <span data-ttu-id="14d12-354">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="14d12-354">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="14d12-355">使用 PowerShell（版本 6 或更高版本）或任何 HTTP 客户端</span><span class="sxs-lookup"><span data-stu-id="14d12-355">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="14d12-356">步骤 1：连接到 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="14d12-356">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="14d12-357">步骤 2：运行以下脚本。</span><span class="sxs-lookup"><span data-stu-id="14d12-357">Step 2: Run the following script.</span></span>

<table>
<tbody>
<tr class="odd">
<td><p><span data-ttu-id="14d12-358">param([string]$baseUri)</span><span class="sxs-lookup"><span data-stu-id="14d12-358">param([string]$baseUri)</span></span></p>
<p><span data-ttu-id="14d12-359">$userName = &quot;UserName&quot;</span><span class="sxs-lookup"><span data-stu-id="14d12-359">$userName = &quot;UserName&quot;</span></span></p>
<p><span data-ttu-id="14d12-360">$password = &quot;Password&quot;</span><span class="sxs-lookup"><span data-stu-id="14d12-360">$password = &quot;Password&quot;</span></span></p>
<p><span data-ttu-id="14d12-361">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span><span class="sxs-lookup"><span data-stu-id="14d12-361">$securePassword = ConvertTo-SecureString $password -AsPlainText -Force</span></span></p>
<p><span data-ttu-id="14d12-362">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span><span class="sxs-lookup"><span data-stu-id="14d12-362">$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)</span></span></p>
<p><span data-ttu-id="14d12-363">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span><span class="sxs-lookup"><span data-stu-id="14d12-363">$EventName=&quot;EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))&quot;</span></span></p>
<p><span data-ttu-id="14d12-364">Write-Host &quot;Start to create an event with name: $EventName&quot;</span><span class="sxs-lookup"><span data-stu-id="14d12-364">Write-Host &quot;Start to create an event with name: $EventName&quot;</span></span></p>
<p><span data-ttu-id="14d12-365">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-365">$body = &quot;&lt;?xml version='1.0' encoding='utf-8' standalone='yes'?&gt;</span></span></p>
<p><span data-ttu-id="14d12-366">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span><span class="sxs-lookup"><span data-stu-id="14d12-366">&lt;entry xmlns:d='https://schemas.microsoft.com/ado/2007/08/dataservices'</span></span></p>
<p><span data-ttu-id="14d12-367">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span><span class="sxs-lookup"><span data-stu-id="14d12-367">xmlns:m='https://schemas.microsoft.com/ado/2007/08/dataservices/metadata'</span></span></p>
<p><span data-ttu-id="14d12-368">xmlns='https://www.w3.org/2005/Atom'&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-368">xmlns='https://www.w3.org/2005/Atom'&gt;</span></span></p>
<p><span data-ttu-id="14d12-369">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-369">&lt;category scheme='https://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' /&gt;</span></span></p>
<p><span data-ttu-id="14d12-370">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-370">&lt;updated&gt;7/14/2017 2:03:36 PM&lt;/updated&gt;</span></span></p>
<p><span data-ttu-id="14d12-371">&lt;content type='application/xml'&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-371">&lt;content type='application/xml'&gt;</span></span></p>
<p><span data-ttu-id="14d12-372">&lt;m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-372">&lt;m:properties&gt;</span></span></p>
<p><span data-ttu-id="14d12-373">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-373">&lt;d:Name&gt;$EventName&lt;/d:Name&gt;</span></span></p>
<p><span data-ttu-id="14d12-374">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-374">&lt;d:EventType&gt;e823b782-9a07-4e30-8091-034fc01f9347&lt;/d:EventType&gt;</span></span></p>
<p><span data-ttu-id="14d12-375">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-375">&lt;d:SharePointAssetIdQuery&gt;'ComplianceAssetId:123'&lt;/d:SharePointAssetIdQuery&gt;</span></span></p>
<p><span data-ttu-id="14d12-376">&lt;/m:properties&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-376">&lt;/m:properties&gt;</span></span></p>
<p><span data-ttu-id="14d12-377">&lt;/content&gt;</span><span class="sxs-lookup"><span data-stu-id="14d12-377">&lt;/content&gt;</span></span></p>
<p><span data-ttu-id="14d12-378">&lt;/entry&gt;&quot;</span><span class="sxs-lookup"><span data-stu-id="14d12-378">&lt;/entry&gt;&quot;</span></span></p>
<p><span data-ttu-id="14d12-379">$event = $null</span><span class="sxs-lookup"><span data-stu-id="14d12-379">$event = $null</span></span></p>
<p><span data-ttu-id="14d12-380">try</span><span class="sxs-lookup"><span data-stu-id="14d12-380">try</span></span></p>
<p><span data-ttu-id="14d12-381">{</span><span class="sxs-lookup"><span data-stu-id="14d12-381">{</span></span></p>
<p><span data-ttu-id="14d12-382">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="14d12-382">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri &quot;$baseUri/ComplianceRetentionEvent&quot; -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="14d12-383">}</span><span class="sxs-lookup"><span data-stu-id="14d12-383">}</span></span></p>
<p><span data-ttu-id="14d12-384">catch</span><span class="sxs-lookup"><span data-stu-id="14d12-384">catch</span></span></p>
<p><span data-ttu-id="14d12-385">{</span><span class="sxs-lookup"><span data-stu-id="14d12-385">{</span></span></p>
<p><span data-ttu-id="14d12-386">$response = $_.Exception.Response</span><span class="sxs-lookup"><span data-stu-id="14d12-386">$response = $_.Exception.Response</span></span></p>
<p><span data-ttu-id="14d12-387">if($response.StatusCode -eq &quot;Redirect&quot;)</span><span class="sxs-lookup"><span data-stu-id="14d12-387">if($response.StatusCode -eq &quot;Redirect&quot;)</span></span></p>
<p><span data-ttu-id="14d12-388">{</span><span class="sxs-lookup"><span data-stu-id="14d12-388">{</span></span></p>
<p><span data-ttu-id="14d12-389">$url = $response.Headers.Location</span><span class="sxs-lookup"><span data-stu-id="14d12-389">$url = $response.Headers.Location</span></span></p>
<p><span data-ttu-id="14d12-390">Write-Host &quot;redirected to $url&quot;</span><span class="sxs-lookup"><span data-stu-id="14d12-390">Write-Host &quot;redirected to $url&quot;</span></span></p>
<p><span data-ttu-id="14d12-391">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span><span class="sxs-lookup"><span data-stu-id="14d12-391">$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType &quot;application/atom+xml&quot; -Authentication Basic -Credential $credentials -MaximumRedirection 0</span></span></p>
<p><span data-ttu-id="14d12-392">}</span><span class="sxs-lookup"><span data-stu-id="14d12-392">}</span></span></p>
<p><span data-ttu-id="14d12-393">}</span><span class="sxs-lookup"><span data-stu-id="14d12-393">}</span></span></p>
<p><span data-ttu-id="14d12-394">$event | fl \*</span><span class="sxs-lookup"><span data-stu-id="14d12-394">$event | fl \*</span></span></p></td>
</tr>
</tbody>
</table>

#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="14d12-395">验证两个选项的结果</span><span class="sxs-lookup"><span data-stu-id="14d12-395">Verify the outcome in both options</span></span>

<span data-ttu-id="14d12-396">步骤 1：转到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="14d12-396">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="14d12-397">步骤 2：选择“**信息治理**”下的“**事件**”。</span><span class="sxs-lookup"><span data-stu-id="14d12-397">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="14d12-398">步骤 3：验证已创建事件。</span><span class="sxs-lookup"><span data-stu-id="14d12-398">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="14d12-399">同样，上述用于自动执行基于事件的保留的选项也可用于以下场景。</span><span class="sxs-lookup"><span data-stu-id="14d12-399">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="14d12-400">场景 2：合同到期</span><span class="sxs-lookup"><span data-stu-id="14d12-400">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="14d12-401">对于与客户、供应商和合作伙伴签订的单份合同，组织可能拥有多条记录。</span><span class="sxs-lookup"><span data-stu-id="14d12-401">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="14d12-402">这些文档可以驻留在 SharePoint 等文档库中。</span><span class="sxs-lookup"><span data-stu-id="14d12-402">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="14d12-403">合同的终止决定了与合同关联的文档保留期的开始。</span><span class="sxs-lookup"><span data-stu-id="14d12-403">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="14d12-404">例如：与合同相关的所有记录都需要在合同到期后保留 5 年。</span><span class="sxs-lookup"><span data-stu-id="14d12-404">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="14d12-405">触发 5 年保留期的事件是合同到期。</span><span class="sxs-lookup"><span data-stu-id="14d12-405">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="14d12-406">客户关系管理 (CRM) 系统可以与 Microsoft 365 一起使用，用于触发合同文档的保留。</span><span class="sxs-lookup"><span data-stu-id="14d12-406">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents</span></span>

<span data-ttu-id="14d12-407">**为此场景配置基于事件的自动保留：**</span><span class="sxs-lookup"><span data-stu-id="14d12-407">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![针对合同到期场景的角色和任务关系图](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="14d12-409">管理员为每种合同类型创建一个包含各种文件夹的 SharePoint 库。</span><span class="sxs-lookup"><span data-stu-id="14d12-409">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="14d12-410">管理员将合同文件（如许可合同、开发合同）添加到每个合同文件夹。</span><span class="sxs-lookup"><span data-stu-id="14d12-410">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="14d12-411">管理员为每个合同文件夹分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="14d12-411">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="14d12-412">SCC 管理员登录到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="14d12-412">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="14d12-413">SCC 管理员创建与合同相关的事件类型，例如“合同创建”和“合同到期”事件。</span><span class="sxs-lookup"><span data-stu-id="14d12-413">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="14d12-414">SCC 管理员创建“合同到期”标签。</span><span class="sxs-lookup"><span data-stu-id="14d12-414">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="14d12-415">此“合同到期”标签将手动或自动发布并应用于 SharePoint 中的合同文件。</span><span class="sxs-lookup"><span data-stu-id="14d12-415">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="14d12-416">合同管理系统可以与 Microsoft Flow 或类似的应用程序一起定期运行以管理合同文件。</span><span class="sxs-lookup"><span data-stu-id="14d12-416">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="14d12-417">如果合同到期，Microsoft Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定合同文件的保留期。</span><span class="sxs-lookup"><span data-stu-id="14d12-417">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="14d12-418">场景 3：产品制造终止</span><span class="sxs-lookup"><span data-stu-id="14d12-418">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="14d12-p124">一家生产不同产品系列的制造公司创建了许多制造规格和定价文件。当不再生产某款产品时，与该产品相关的所有规格和文件都需要在产品生存期结束后的特定时间内保留。</span><span class="sxs-lookup"><span data-stu-id="14d12-p124">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents. When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="14d12-421">企业资源规划 (ERP) 系统可以与 Microsoft 365 和 Microsoft Flow 一起使用，用于触发保留。</span><span class="sxs-lookup"><span data-stu-id="14d12-421">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="14d12-422">**为此场景配置基于事件的自动保留：**</span><span class="sxs-lookup"><span data-stu-id="14d12-422">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![产品生命周期场景的角色和任务关系图](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="14d12-424">管理员在文档集中创建产品文件夹，如产品 1、产品 2 等。</span><span class="sxs-lookup"><span data-stu-id="14d12-424">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="14d12-425">管理员将产品文件（如制造规格、产品定价、产品许可）添加到每个产品文件夹中。</span><span class="sxs-lookup"><span data-stu-id="14d12-425">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="14d12-426">管理员为每个产品文件夹分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="14d12-426">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="14d12-427">SCC 管理员登录到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="14d12-427">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="14d12-428">SCC 管理员创建与员工相关的事件类型，例如“产品制造开始”和“产品制造结束”事件。</span><span class="sxs-lookup"><span data-stu-id="14d12-428">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="14d12-429">SCC 管理员创建“产品制造结束”标签。</span><span class="sxs-lookup"><span data-stu-id="14d12-429">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="14d12-430">此“产品制造终止”标签将手动或自动发布并应用于 SharePoint 中的产品文件。</span><span class="sxs-lookup"><span data-stu-id="14d12-430">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="14d12-431">ERP 系统可以与 Microsoft Flow 或类似的应用程序一起定期运行以管理产品文件。</span><span class="sxs-lookup"><span data-stu-id="14d12-431">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="14d12-432">如果产品制造终止，Microsoft Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定产品文件的保留期。</span><span class="sxs-lookup"><span data-stu-id="14d12-432">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="14d12-433">附录</span><span class="sxs-lookup"><span data-stu-id="14d12-433">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="14d12-434">使用重定向 302 响应结果来调用 REST API</span><span class="sxs-lookup"><span data-stu-id="14d12-434">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="14d12-435">使用 REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> 调用 POST 保留事件调用（需要全局管理员权限）</span><span class="sxs-lookup"><span data-stu-id="14d12-435">Invoke a POST retention event call using the REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required)</span></span>

2. <span data-ttu-id="14d12-p125">检查响应代码。如果是 302，则从响应标头的“位置”属性中获取重定向的 URL</span><span class="sxs-lookup"><span data-stu-id="14d12-p125">Check the response code. If it’s 302, then get the redirected URL from Location property of the response header</span></span>

3. <span data-ttu-id="14d12-438">使用重定向的 URL 再次调用 POST 保留事件调用。</span><span class="sxs-lookup"><span data-stu-id="14d12-438">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="14d12-439">制作人员</span><span class="sxs-lookup"><span data-stu-id="14d12-439">Credits</span></span>

<span data-ttu-id="14d12-440">本主题经过以下人员的审阅：</span><span class="sxs-lookup"><span data-stu-id="14d12-440">This topic was reviewed by:</span></span>

<span data-ttu-id="14d12-441">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="14d12-441">Antonio Maio</span></span><br/><span data-ttu-id="14d12-442">Microsoft Office 应用和服务 MVP</span><span class="sxs-lookup"><span data-stu-id="14d12-442">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="14d12-443">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="14d12-443">Antonio.Maio@Protiviti.com</span></span>
