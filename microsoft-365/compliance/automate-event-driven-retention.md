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
ms.openlocfilehash: e3e58aab9bdcb5debcfe805b1ebdfd637c1d3851
ms.sourcegitcommit: 8595cb9ffe0ca5556080f24224182381e1d880de
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/03/2020
ms.locfileid: "45035647"
---
# <a name="automate-event-based-retention"></a><span data-ttu-id="3c233-103">自动执行基于事件的保留</span><span class="sxs-lookup"><span data-stu-id="3c233-103">Automate event-based retention</span></span>

><span data-ttu-id="3c233-104">*[Microsoft 365 安全性与合规性许可指南](https://aka.ms/ComplianceSD)。*</span><span class="sxs-lookup"><span data-stu-id="3c233-104">*[Microsoft 365 licensing guidance for security & compliance](https://aka.ms/ComplianceSD).*</span></span>

<span data-ttu-id="3c233-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span><span class="sxs-lookup"><span data-stu-id="3c233-105">The explosion of content in organizations and how it can become ROT (redundant, obsolete, trivial) is serious business.</span></span> <span data-ttu-id="3c233-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span><span class="sxs-lookup"><span data-stu-id="3c233-106">To continue to meet legal, business, and regulatory compliance challenges, organizations must be able to keep and protect important information and quickly find what’s relevant.</span></span> <span data-ttu-id="3c233-107">Retaining only important, pertinent information is key to an organization's success.</span><span class="sxs-lookup"><span data-stu-id="3c233-107">Retaining only important, pertinent information is key to an organization's success.</span></span>

<span data-ttu-id="3c233-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="3c233-108">To help meet this need, organizations can take advantage of retention solutions in the Office 365 Security & Compliance Center.</span></span> <span data-ttu-id="3c233-109">Retention can be triggered by using [retention labels](labels.md).</span><span class="sxs-lookup"><span data-stu-id="3c233-109">Retention can be triggered by using [retention labels](labels.md).</span></span> <span data-ttu-id="3c233-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="3c233-110">A retention label has the option to [base the retention period on a specific event](event-driven-retention.md).</span></span> <span data-ttu-id="3c233-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span><span class="sxs-lookup"><span data-stu-id="3c233-111">Typically, the retention period is based on a known date, such as the creation date or last modified date for the content.</span></span> <span data-ttu-id="3c233-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span><span class="sxs-lookup"><span data-stu-id="3c233-112">However, organizations also have requirements to dispose of content based on the occurrence of an event, such as seven years after an employee leaves an organization.</span></span>

<span data-ttu-id="3c233-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span><span class="sxs-lookup"><span data-stu-id="3c233-113">To ensure compliant disposal of content, it's imperative to know when an event takes place.</span></span> <span data-ttu-id="3c233-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span><span class="sxs-lookup"><span data-stu-id="3c233-114">With the volume of content increasing rapidly, it's becoming challenging to retain and dispose content in a timely and compliant manner.</span></span>

<span data-ttu-id="3c233-115">Event-based retention solves this problem.</span><span class="sxs-lookup"><span data-stu-id="3c233-115">Event-based retention solves this problem.</span></span> <span data-ttu-id="3c233-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span><span class="sxs-lookup"><span data-stu-id="3c233-116">This topic explains how to set up your business process flows to automate retention through events by using the Microsoft 365 REST API.</span></span>

## <a name="about-event-based-retention"></a><span data-ttu-id="3c233-117">关于基于事件的保留</span><span class="sxs-lookup"><span data-stu-id="3c233-117">About event-based retention</span></span>

<span data-ttu-id="3c233-118">An organization can be small, medium, or large.</span><span class="sxs-lookup"><span data-stu-id="3c233-118">An organization can be small, medium, or large.</span></span> <span data-ttu-id="3c233-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span><span class="sxs-lookup"><span data-stu-id="3c233-119">The number of business documents, legal documents, employee files, contracts, and product documents that get created and managed on a day-to-day basis is increasing dramatically.</span></span>

<span data-ttu-id="3c233-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span><span class="sxs-lookup"><span data-stu-id="3c233-120">For example, each day, tens and hundreds of employees are joining and leaving organizations.</span></span> <span data-ttu-id="3c233-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span><span class="sxs-lookup"><span data-stu-id="3c233-121">The HR department continues to create, update, or delete employee-related documents as per business requirements.</span></span> <span data-ttu-id="3c233-122">This process is subject to the different retention policies outlined for the business:</span><span class="sxs-lookup"><span data-stu-id="3c233-122">This process is subject to the different retention policies outlined for the business:</span></span>

- <span data-ttu-id="3c233-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span><span class="sxs-lookup"><span data-stu-id="3c233-123">**The period of retention for content can be a known date** such as the date the content was created, last modified, or labeled.</span></span> <span data-ttu-id="3c233-124">For example, you might retain documents for seven years after they're created and then delete them.</span><span class="sxs-lookup"><span data-stu-id="3c233-124">For example, you might retain documents for seven years after they're created and then delete them.</span></span>

- <span data-ttu-id="3c233-125">**The period of retention of content can also be an unknown date**.</span><span class="sxs-lookup"><span data-stu-id="3c233-125">**The period of retention of content can also be an unknown date**.</span></span> <span data-ttu-id="3c233-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span><span class="sxs-lookup"><span data-stu-id="3c233-126">For example, with retention labels, you can also base a retention period on when a specific type of event occurs, such as an employee leaving the organization.</span></span>

<span data-ttu-id="3c233-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span><span class="sxs-lookup"><span data-stu-id="3c233-127">The event triggers the start of the retention period, and all content with a label applied for that type of event get the label's retention actions enforced on them.</span></span> <span data-ttu-id="3c233-128">This is called event-based retention.</span><span class="sxs-lookup"><span data-stu-id="3c233-128">This is called event-based retention.</span></span> <span data-ttu-id="3c233-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span><span class="sxs-lookup"><span data-stu-id="3c233-129">To learn more, see [Overview of event-driven retention](event-driven-retention.md).</span></span>

## <a name="set-up-event-based-retention"></a><span data-ttu-id="3c233-130">设置基于事件的保留</span><span class="sxs-lookup"><span data-stu-id="3c233-130">Set up event-based retention</span></span>

<span data-ttu-id="3c233-131">本节介绍在保留内容之前需要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="3c233-131">This section describes what needs to be done before retaining content.</span></span>

### <a name="identify-roles"></a><span data-ttu-id="3c233-132">标识角色</span><span class="sxs-lookup"><span data-stu-id="3c233-132">Identify roles</span></span>

<span data-ttu-id="3c233-133">确定执行记录管理任务的组织中的不同角色，并且这些角色将负责有效且高效地保留业务文档。</span><span class="sxs-lookup"><span data-stu-id="3c233-133">Identify the different roles in an organization that perform Record Management tasks and would be responsible for effective and efficient retention of business documents.</span></span>

  | <span data-ttu-id="3c233-134">Persona</span><span class="sxs-lookup"><span data-stu-id="3c233-134">Persona</span></span> | <span data-ttu-id="3c233-135">角色</span><span class="sxs-lookup"><span data-stu-id="3c233-135">Role</span></span> |
  | - | - |
  | <span data-ttu-id="3c233-136">管理员</span><span class="sxs-lookup"><span data-stu-id="3c233-136">Admin</span></span> | <span data-ttu-id="3c233-137">在 SharePoint 中创建保留事件类型、保留标签和记录存储库</span><span class="sxs-lookup"><span data-stu-id="3c233-137">Creates Retention Event types, Retention labels and Record repositories in SharePoint</span></span> |
  | <span data-ttu-id="3c233-138">记录经理</span><span class="sxs-lookup"><span data-stu-id="3c233-138">Records Manager</span></span>                                  | <span data-ttu-id="3c233-139">提供保留策略和保留计划指南和合规性详细信息</span><span class="sxs-lookup"><span data-stu-id="3c233-139">Provides Retention Policies and Retention Schedules guidance and compliance details</span></span>   |
  | <span data-ttu-id="3c233-140">系统管理员（企业）</span><span class="sxs-lookup"><span data-stu-id="3c233-140">System Admin (business)</span></span>                          | <span data-ttu-id="3c233-141">设置和管理外部系统以使用 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="3c233-141">Sets up and manages external systems to work with Microsoft 365</span></span>                       |
  | <span data-ttu-id="3c233-142">信息工作者</span><span class="sxs-lookup"><span data-stu-id="3c233-142">Information Worker</span></span>                               | <span data-ttu-id="3c233-143">管理业务流程的生命周期（人力资源、财务、IT 等）</span><span class="sxs-lookup"><span data-stu-id="3c233-143">Manages the lifecycle of their business process (HR, Finance, IT, and so on)</span></span>                 |

### <a name="set-up-the-security--compliance-center"></a><span data-ttu-id="3c233-144">设置安全与合规中心</span><span class="sxs-lookup"><span data-stu-id="3c233-144">Set up the Security & Compliance Center</span></span>
  
1. <span data-ttu-id="3c233-145">合规性管理员可创建事件类型 &ndash; 例如“雇佣终止”、“合同到期”或“产品制造结束”。</span><span class="sxs-lookup"><span data-stu-id="3c233-145">Compliance admin creates an event type &ndash; for example, Employee Termination or Contract Expiration or End of Product Manufacturing.</span></span> <span data-ttu-id="3c233-146">（请在[事件驱动保留](event-driven-retention.md)中查看分步流程）。</span><span class="sxs-lookup"><span data-stu-id="3c233-146">(See the step-by-step process in [Event-driven retention](event-driven-retention.md).</span></span>
    
2. <span data-ttu-id="3c233-147">合规性管理员根据事件创建保留标签，并将标签与事件类型相关联。</span><span class="sxs-lookup"><span data-stu-id="3c233-147">Compliance admin creates a retention label based on an event and associates the label with an event type.</span></span>
    
    <span data-ttu-id="3c233-148">保留标签具有 4 种类型的触发器：</span><span class="sxs-lookup"><span data-stu-id="3c233-148">There are four types of triggers for retention labels:</span></span>
            
    1. <span data-ttu-id="3c233-149">创建日期</span><span class="sxs-lookup"><span data-stu-id="3c233-149">Create date</span></span>
                
    2. <span data-ttu-id="3c233-150">上次修改时间</span><span class="sxs-lookup"><span data-stu-id="3c233-150">Last modified</span></span>
                
    3. <span data-ttu-id="3c233-151">标签日期（标记内容的时间）</span><span class="sxs-lookup"><span data-stu-id="3c233-151">Label date (when the content was labeled)</span></span>
                
    4. <span data-ttu-id="3c233-152">基于事件</span><span class="sxs-lookup"><span data-stu-id="3c233-152">Event-based</span></span>
    
3. <span data-ttu-id="3c233-153">合规性管理员发布保留标签。</span><span class="sxs-lookup"><span data-stu-id="3c233-153">Compliance admin publishes the retention label.</span></span>

### <a name="set-up-sharepoint"></a><span data-ttu-id="3c233-154">设置 SharePoint</span><span class="sxs-lookup"><span data-stu-id="3c233-154">Set up SharePoint</span></span>
   
<span data-ttu-id="3c233-155">若要创建记录存储库，合规性管理员需要：</span><span class="sxs-lookup"><span data-stu-id="3c233-155">To create a records repository, the compliance admin:</span></span>

1. <span data-ttu-id="3c233-156">创建 SharePoint 网站。</span><span class="sxs-lookup"><span data-stu-id="3c233-156">Creates a SharePoint site.</span></span>

2. <span data-ttu-id="3c233-157">执行下列操作之一：</span><span class="sxs-lookup"><span data-stu-id="3c233-157">Does one of the following:</span></span>
        
   - <span data-ttu-id="3c233-158">Creates a SharePoint library: Set event-based label at the library level.</span><span class="sxs-lookup"><span data-stu-id="3c233-158">Creates a SharePoint library: Set event-based label at the library level.</span></span> <span data-ttu-id="3c233-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span><span class="sxs-lookup"><span data-stu-id="3c233-159">For more information, see [Applying a default retention label to all content in a SharePoint library, folder, or document set](labels.md#applying-a-default-retention-label-to-all-content-in-a-sharepoint-library-folder-or-document-set).</span></span>
          
   - <span data-ttu-id="3c233-160">在 SharePoint 中设置文档集。</span><span class="sxs-lookup"><span data-stu-id="3c233-160">Sets up a document set in SharePoint.</span></span> <span data-ttu-id="3c233-161">有关详细信息，请参阅[文档集简介](https://support.microsoft.com/zh-CN/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234)。</span><span class="sxs-lookup"><span data-stu-id="3c233-161">For more information, see [Introduction to document sets](https://support.microsoft.com/zh-CN/office/introduction-to-document-sets-3dbcd93e-0bed-46b7-b1ba-b31de2bcd234).</span></span>
      
3. <span data-ttu-id="3c233-162">为每个员工文档集分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="3c233-162">Assigns an asset ID to each employee document set.</span></span> <span data-ttu-id="3c233-163">资产 ID 是组织使用的产品名称或代码，例如员工编号可以是资产 ID。</span><span class="sxs-lookup"><span data-stu-id="3c233-163">An asset ID is a product name or code used by the organization, for example, Employee number can be an asset ID.</span></span> <span data-ttu-id="3c233-164">通过将资产 ID 分配给文件夹，该文件夹中的每个项目都会自动继承相同的资产 ID。</span><span class="sxs-lookup"><span data-stu-id="3c233-164">By assigning the asset ID to the folder, every item in that folder automatically inherits the same asset ID.</span></span> <span data-ttu-id="3c233-165">这意味着所有项目的保留期都可以由同一事件触发。</span><span class="sxs-lookup"><span data-stu-id="3c233-165">This means all the items can have their retention period triggered by the same event.</span></span>

## <a name="ways-to-trigger-event-based-retention"></a><span data-ttu-id="3c233-166">触发基于事件的保留的方法</span><span class="sxs-lookup"><span data-stu-id="3c233-166">Ways to trigger event-based retention</span></span>

<span data-ttu-id="3c233-167">可通过两种方法触发基于事件的保留：</span><span class="sxs-lookup"><span data-stu-id="3c233-167">There are two ways in which event-based retention can be triggered:</span></span>

- <span data-ttu-id="3c233-168">**使用管理中心 UI** 此流程适用于一次保留较少内容或者不经常触发保留的情形，例如每月或每年保留一次。</span><span class="sxs-lookup"><span data-stu-id="3c233-168">**Using the admin center UI** This is a process that can be used to retain less content at a time or the frequency to trigger retention isn't often, such as monthly or yearly.</span></span> <span data-ttu-id="3c233-169">有关此方法的详细信息，请参阅[事件驱动保留概述](event-driven-retention.md)。</span><span class="sxs-lookup"><span data-stu-id="3c233-169">For more information about this method, see [Overview of event-driven retention](event-driven-retention.md).</span></span> <span data-ttu-id="3c233-170">但是，这种触发保留的方法可能比较耗时且容易出错，这会影响可伸缩性。</span><span class="sxs-lookup"><span data-stu-id="3c233-170">However, this method of triggering retention can be time consuming and prone to error, thus stunting scalability.</span></span> <span data-ttu-id="3c233-171">用于触发保留的自动化无缝解决方案可以增强数据的安全性和合规性。</span><span class="sxs-lookup"><span data-stu-id="3c233-171">Therefore, an automated, seamless solution to trigger retention can enhance data security and compliance.</span></span>

- <span data-ttu-id="3c233-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span><span class="sxs-lookup"><span data-stu-id="3c233-172">**Using a M365 REST API** This process can be used when large amounts of content are to be retained at a time and/or the frequency to trigger retention is often such as daily or weekly.</span></span> <span data-ttu-id="3c233-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span><span class="sxs-lookup"><span data-stu-id="3c233-173">The flow detects when an event occurs in your line-of-business system, and then automatically creates a related event in the Security & Compliance Center.</span></span> <span data-ttu-id="3c233-174">You don't need to manually create an event in the UI each time one occurs.</span><span class="sxs-lookup"><span data-stu-id="3c233-174">You don't need to manually create an event in the UI each time one occurs.</span></span>

<span data-ttu-id="3c233-175">使用 REST API 有两种选择：</span><span class="sxs-lookup"><span data-stu-id="3c233-175">There are two options for using the REST API:</span></span>

- <span data-ttu-id="3c233-176">**Microsoft Flow 或类似的应用程序**可用于自动触发事件的发生。</span><span class="sxs-lookup"><span data-stu-id="3c233-176">**Microsoft Flow or a similar application** can be used to trigger the occurrence of an event automatically.</span></span> <span data-ttu-id="3c233-177">Microsoft Flow 是用于连接到其他系统的协调程序。</span><span class="sxs-lookup"><span data-stu-id="3c233-177">Microsoft Flow is an orchestrator for connecting to other systems.</span></span> <span data-ttu-id="3c233-178">使用 Microsoft Flow 不需要自定义解决方案。</span><span class="sxs-lookup"><span data-stu-id="3c233-178">Using Microsoft Flow doesn't require a custom solution.</span></span>

- <span data-ttu-id="3c233-179">\*\*使用 PowerShell 或 HTTP 客户端调用 REST API \*\*使用 PowerShell（版本 6 或更高版本）调用 Microsoft 365 REST API 以创建事件。</span><span class="sxs-lookup"><span data-stu-id="3c233-179">**PowerShell or an HTTP client to call REST API** Using PowerShell (version 6 or higher) to call Microsoft 365 REST API to create events.</span></span> 

<span data-ttu-id="3c233-180">Rest API 是一个支持多组 HTTP 操作（方法）的服务终结点，提供对服务资源的创建/检索/更新/删除操作权限。</span><span class="sxs-lookup"><span data-stu-id="3c233-180">A Rest API is a service endpoint that supports sets of HTTP operations (methods), which provide create/retrieve/update/delete access to the service's resources.</span></span> <span data-ttu-id="3c233-181">有关详细信息，请参阅 [REST API 请求/响应组件](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse)。</span><span class="sxs-lookup"><span data-stu-id="3c233-181">For more information, see [Components of a REST API request/response](https://docs.microsoft.com/rest/api/gettingstarted/#components-of-a-rest-api-requestresponse).</span></span> <span data-ttu-id="3c233-182">在这种情况下，通过使用 Microsoft 365 REST API，可以使用 POST 和 GET 操作（方法）来创建和检索事件。</span><span class="sxs-lookup"><span data-stu-id="3c233-182">In this case, by using the Microsoft 365 REST API, events can be created and retrieved using operations (methods) POST and GET.</span></span>

## <a name="example-scenarios"></a><span data-ttu-id="3c233-183">示例场景</span><span class="sxs-lookup"><span data-stu-id="3c233-183">Example scenarios</span></span>

<span data-ttu-id="3c233-184">让我们以如下场景为例。</span><span class="sxs-lookup"><span data-stu-id="3c233-184">Let’s consider the following scenarios.</span></span>

### <a name="scenario-1-employees-leaving-the-organization"></a><span data-ttu-id="3c233-185">场景 1：员工离开组织</span><span class="sxs-lookup"><span data-stu-id="3c233-185">Scenario 1: Employees leaving the organization</span></span> 

<span data-ttu-id="3c233-186">组织为每个员工创建和存储许多员工相关文档。</span><span class="sxs-lookup"><span data-stu-id="3c233-186">An organization creates and stores numerous employee-related documents per employee.</span></span> <span data-ttu-id="3c233-187">这些文档在每位员工的雇佣期内进行管理和保留。</span><span class="sxs-lookup"><span data-stu-id="3c233-187">These documents are managed and retained during the employment of each employee.</span></span> <span data-ttu-id="3c233-188">但是，当员工离开组织或终止雇佣关系时，组织有义务根据法律和业务要求在规定的时间内保留该员工的文档。</span><span class="sxs-lookup"><span data-stu-id="3c233-188">However, when the employee leaves the organization or the employment is terminated, the organization is obligated by legal and business requirements to retain the documents of that employee for a stipulated period.</span></span>

<span data-ttu-id="3c233-189">现在，如果每天有多名员工离开组织，组织必须在每天触发数百甚至数千个文档的保留期。</span><span class="sxs-lookup"><span data-stu-id="3c233-189">Now if multiple employees leave the organization every day, the organization must trigger the retention clock of hundreds if not thousands of documents each day.</span></span>

<span data-ttu-id="3c233-190">除此之外，还需要根据员工记录的类型计算每个员工的保留期，即雇佣终止日期 + 天数、月数或年数。</span><span class="sxs-lookup"><span data-stu-id="3c233-190">In addition to this, the retention period needs to be calculated for each of these employees as Employee termination date + number of days, months, or years based on the type of the employee record.</span></span> <span data-ttu-id="3c233-191">例如，同一员工的职工薪酬档案与福利档案可能需要不同的保留期。</span><span class="sxs-lookup"><span data-stu-id="3c233-191">For example, worker’s compensation of the employee vs. benefits filings of the same employee may need different retention.</span></span>

<span data-ttu-id="3c233-192">下图显示如何将多个标签与单个事件关联。</span><span class="sxs-lookup"><span data-stu-id="3c233-192">The diagram below shows how there can be multiple labels that are associated with a single event.</span></span> <span data-ttu-id="3c233-193">在此处，员工薪酬标签下的所有文件和员工福利标签下的所有文件都与单个事件相关联，即员工离开组织。</span><span class="sxs-lookup"><span data-stu-id="3c233-193">Here all the files under Worker’s compensation label and all the files under Employee benefits label are both associated with a single event, which is the employee leaving the organization.</span></span> <span data-ttu-id="3c233-194">每个不同的文件都有不同的保留期。</span><span class="sxs-lookup"><span data-stu-id="3c233-194">Each of these different files has different retention clocks.</span></span> <span data-ttu-id="3c233-195">因此，当员工离开组织时，每个标签中的这些文件都会经历不同的保留期。</span><span class="sxs-lookup"><span data-stu-id="3c233-195">So, when an employee leaves the organization, these files within each label experience a different retention period.</span></span> <span data-ttu-id="3c233-196">为每个员工的每种文件类型或标签触发所有这些不同的保留期是一项极具挑战的任务。</span><span class="sxs-lookup"><span data-stu-id="3c233-196">Triggering all these different retention clocks for each file type or label for each employee is a very challenging task.</span></span> <span data-ttu-id="3c233-197">想象一下，为多名员工做这件事将会如何。</span><span class="sxs-lookup"><span data-stu-id="3c233-197">Imagine doing this for multiple employees.</span></span>

![事件类型、事件和标签的关系图](../media/automate-event-driven-retention-event-diagram-employee-leaving.png)

<span data-ttu-id="3c233-199">为多个员工触发这些不同保留期的自动化流程将节省时间、无错误且极为高效。</span><span class="sxs-lookup"><span data-stu-id="3c233-199">Hence an automated process to trigger these different retention clocks for multiple employees will be time-saving, error-free, and extremely efficient.</span></span>

<span data-ttu-id="3c233-200">**为此场景配置基于事件的自动保留：**</span><span class="sxs-lookup"><span data-stu-id="3c233-200">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![针对员工离开组织的场景的角色和操作关系图](../media/automate-event-driven-retention-employee-termination-diagram.png)

  - <span data-ttu-id="3c233-202">管理员为文档集创建员工文件夹，如 Jane Doe、John Smith。</span><span class="sxs-lookup"><span data-stu-id="3c233-202">Admin creates employee folders to the Document set such as Jane Doe, John Smith.</span></span>

  - <span data-ttu-id="3c233-203">管理员将员工文件（如福利、工资单、员工薪酬）添加到每个员工文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3c233-203">Admin adds employee files such as Benefits, Payroll, Worker’s Compensation to each employee folder.</span></span>

  - <span data-ttu-id="3c233-204">管理员为每个员工文件夹分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="3c233-204">Admin assigns Asset ID to each employee folder.</span></span> 

  - <span data-ttu-id="3c233-205">SCC 管理员登录到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="3c233-205">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="3c233-206">SCC 管理员创建与员工相关的事件类型，例如“雇佣终止”和“员工雇用”事件。</span><span class="sxs-lookup"><span data-stu-id="3c233-206">SCC Admin creates employee-related events types such as “Employee Termination”, “Employee Hire” events.</span></span>

  - <span data-ttu-id="3c233-207">SCC 管理员创建“员工留任”标签。</span><span class="sxs-lookup"><span data-stu-id="3c233-207">SCC Admin creates “Employee Retention” label.</span></span>

  - <span data-ttu-id="3c233-208">此“员工保留”标签将手动或自动发布并应用于 SharePoint 中的员工文件。</span><span class="sxs-lookup"><span data-stu-id="3c233-208">This “Employee Retention” label is published and applied manually or automatically to the employee files in SharePoint.</span></span>

  - <span data-ttu-id="3c233-209">HR 管理系统（如 Workday）可以与 Microsoft Flow 一起定期运行以管理员工文件。</span><span class="sxs-lookup"><span data-stu-id="3c233-209">HR Management System like Workday can work with Microsoft Flow to run periodically to manage employee files.</span></span>

  - <span data-ttu-id="3c233-210">如果员工离开组织，Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定员工文件的保留期。</span><span class="sxs-lookup"><span data-stu-id="3c233-210">If an employee has left the organization, the Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific employee’s files.</span></span>

#### <a name="using-microsoft-flow"></a><span data-ttu-id="3c233-211">使用 Microsoft Flow</span><span class="sxs-lookup"><span data-stu-id="3c233-211">Using Microsoft Flow</span></span>

<span data-ttu-id="3c233-212">步骤 1 - 使用 Microsoft 365 REST API 创建用于创建事件的流</span><span class="sxs-lookup"><span data-stu-id="3c233-212">Step 1- Create a flow to create an event using the Microsoft 365 REST API</span></span>

![使用流创建事件](../media/automate-event-driven-retention-flow-1.png)

![使用流调用 REST API](../media/automate-event-driven-retention-flow-2.png)

##### <a name="create-an-event"></a><span data-ttu-id="3c233-215">创建事件</span><span class="sxs-lookup"><span data-stu-id="3c233-215">Create an event</span></span>

<span data-ttu-id="3c233-216">用于调用 REST API 的示例代码</span><span class="sxs-lookup"><span data-stu-id="3c233-216">Sample code to call the REST API</span></span>

- <span data-ttu-id="3c233-217">**方法**：POST</span><span class="sxs-lookup"><span data-stu-id="3c233-217">**Method**: POST</span></span>
- <span data-ttu-id="3c233-218">**URL**: https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</span><span class="sxs-lookup"><span data-stu-id="3c233-218">**URL**: https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent</span></span>
- <span data-ttu-id="3c233-219">**标头**：键 = Content-Type，值 = application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="3c233-219">**Headers**: Key = Content-Type, Value = application/atom+xml</span></span>
- <span data-ttu-id="3c233-220">**正文**：</span><span class="sxs-lookup"><span data-stu-id="3c233-220">**Body**:</span></span>
    
    ```xml
    <?xml version='1.0' encoding='utf-8' standalone='yes'?>
    
    <entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'
    
    xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'
    
    xmlns='http://www.w3.org/2005/Atom'>
    
    <category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />
    
    <updated>9/9/2017 10:50:00 PM</updated>
    
    <content type='application/xml'>
    
    <m:properties>
    
    <d:Name>Employee Termination </d:Name>
    
    <d:EventType>99e0ae64-a4b8-40bb-82ed-645895610f56</d:EventType>
    
    <d:SharePointAssetIdQuery>1234</d:SharePointAssetIdQuery>
    
    <d:EventDateTime>2018-12-01T00:00:00Z </d:EventDateTime>
    
    </m:properties>
    
    </content>
    
    </entry>
    ```
- <span data-ttu-id="3c233-221">**身份验证**: 基本</span><span class="sxs-lookup"><span data-stu-id="3c233-221">**Authentication**: Basic</span></span>
- <span data-ttu-id="3c233-222">**用户名**: "Complianceuser"</span><span class="sxs-lookup"><span data-stu-id="3c233-222">**Username**: "Complianceuser"</span></span>
- <span data-ttu-id="3c233-223">**密码**: "Compliancepassword"</span><span class="sxs-lookup"><span data-stu-id="3c233-223">**Password**: "Compliancepassword"</span></span>


##### <a name="available-parameters"></a><span data-ttu-id="3c233-224">可用参数</span><span class="sxs-lookup"><span data-stu-id="3c233-224">Available parameters</span></span>


|<span data-ttu-id="3c233-225">参数</span><span class="sxs-lookup"><span data-stu-id="3c233-225">Parameters</span></span>|<span data-ttu-id="3c233-226">说明</span><span class="sxs-lookup"><span data-stu-id="3c233-226">Description</span></span>|<span data-ttu-id="3c233-227">注释</span><span class="sxs-lookup"><span data-stu-id="3c233-227">Notes</span></span>|
|--- |--- |--- |
|<span data-ttu-id="3c233-228"><d:Name></d:Name></span><span class="sxs-lookup"><span data-stu-id="3c233-228"><d:Name></d:Name></span></span>|<span data-ttu-id="3c233-229">为事件提供唯一的名称，</span><span class="sxs-lookup"><span data-stu-id="3c233-229">Provide a unique name for the event,</span></span>|<span data-ttu-id="3c233-230">不能包含尾随空格和以下字符： % \* \ & < ></span><span class="sxs-lookup"><span data-stu-id="3c233-230">Cannot contain trailing spaces, and the following characters: % \* \ & < ></span></span> | <span data-ttu-id="3c233-231"># ?</span><span class="sxs-lookup"><span data-stu-id="3c233-231"># ?</span></span> <span data-ttu-id="3c233-232">, : ;</span><span class="sxs-lookup"><span data-stu-id="3c233-232">, : ;</span></span>|
|<span data-ttu-id="3c233-233"><d:EventType></d:EventType></span><span class="sxs-lookup"><span data-stu-id="3c233-233"><d:EventType></d:EventType></span></span>|<span data-ttu-id="3c233-234">输入事件类型名称（或 Guid），</span><span class="sxs-lookup"><span data-stu-id="3c233-234">Enter event type name (or Guid),</span></span>|<span data-ttu-id="3c233-235">Example: “Employee termination”.</span><span class="sxs-lookup"><span data-stu-id="3c233-235">Example: “Employee termination”.</span></span> <span data-ttu-id="3c233-236">Event type has to be associated with a retention label.</span><span class="sxs-lookup"><span data-stu-id="3c233-236">Event type has to be associated with a retention label.</span></span>|
|<span data-ttu-id="3c233-237"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span><span class="sxs-lookup"><span data-stu-id="3c233-237"><d:SharePointAssetIdQuery></d:SharePointAssetIdQuery></span></span>|<span data-ttu-id="3c233-238">输入“ComplianceAssetId:” + 员工 Id</span><span class="sxs-lookup"><span data-stu-id="3c233-238">Enter “ComplianceAssetId:” + employee Id</span></span>|<span data-ttu-id="3c233-239">示例："ComplianceAssetId:12345"</span><span class="sxs-lookup"><span data-stu-id="3c233-239">Example: "ComplianceAssetId:12345"</span></span>|
|<span data-ttu-id="3c233-240"><d:EventDateTime></d:EventDateTime></span><span class="sxs-lookup"><span data-stu-id="3c233-240"><d:EventDateTime></d:EventDateTime></span></span>|<span data-ttu-id="3c233-241">事件日期和时间</span><span class="sxs-lookup"><span data-stu-id="3c233-241">Event Date and Time</span></span>|<span data-ttu-id="3c233-242">格式：yyyy-MM-ddTHH:mm:ssZ，示例：2018-12-01T00:00:00Z</span><span class="sxs-lookup"><span data-stu-id="3c233-242">Format: yyyy-MM-ddTHH:mm:ssZ, Example: 2018-12-01T00:00:00Z</span></span>
|

##### <a name="response-codes"></a><span data-ttu-id="3c233-243">响应代码</span><span class="sxs-lookup"><span data-stu-id="3c233-243">Response codes</span></span>

| <span data-ttu-id="3c233-244">响应代码</span><span class="sxs-lookup"><span data-stu-id="3c233-244">Response Code</span></span> | <span data-ttu-id="3c233-245">说明</span><span class="sxs-lookup"><span data-stu-id="3c233-245">Description</span></span>       |
| ----------------- | --------------------- |
| <span data-ttu-id="3c233-246">302</span><span class="sxs-lookup"><span data-stu-id="3c233-246">302</span></span>               | <span data-ttu-id="3c233-247">重定向</span><span class="sxs-lookup"><span data-stu-id="3c233-247">Redirect</span></span>              |
| <span data-ttu-id="3c233-248">201</span><span class="sxs-lookup"><span data-stu-id="3c233-248">201</span></span>               | <span data-ttu-id="3c233-249">已创建</span><span class="sxs-lookup"><span data-stu-id="3c233-249">Created</span></span>               |
| <span data-ttu-id="3c233-250">403</span><span class="sxs-lookup"><span data-stu-id="3c233-250">403</span></span>               | <span data-ttu-id="3c233-251">授权失败</span><span class="sxs-lookup"><span data-stu-id="3c233-251">Authorization Failed</span></span>  |
| <span data-ttu-id="3c233-252">401</span><span class="sxs-lookup"><span data-stu-id="3c233-252">401</span></span>               | <span data-ttu-id="3c233-253">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="3c233-253">Authentication Failed</span></span> |

##### <a name="get-events-based-on-time-range"></a><span data-ttu-id="3c233-254">根据时间范围获取事件</span><span class="sxs-lookup"><span data-stu-id="3c233-254">Get Events based on time range</span></span>



|<span data-ttu-id="3c233-255">方法</span><span class="sxs-lookup"><span data-stu-id="3c233-255">Method</span></span>|<span data-ttu-id="3c233-256">GET</span><span class="sxs-lookup"><span data-stu-id="3c233-256">GET</span></span>||
|--- |--- |--- |
|<span data-ttu-id="3c233-257">URL</span><span class="sxs-lookup"><span data-stu-id="3c233-257">URL</span></span>|https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent?BeginDateTime=2019-01-11&EndDateTime=2019-01-16||
|<span data-ttu-id="3c233-258">标头</span><span class="sxs-lookup"><span data-stu-id="3c233-258">Headers</span></span>|<span data-ttu-id="3c233-259">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3c233-259">Content-Type</span></span>|<span data-ttu-id="3c233-260">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="3c233-260">application/atom+xml</span></span>|
||||
|<span data-ttu-id="3c233-261">身份验证</span><span class="sxs-lookup"><span data-stu-id="3c233-261">Authentication</span></span>|<span data-ttu-id="3c233-262">基本</span><span class="sxs-lookup"><span data-stu-id="3c233-262">Basic</span></span>||
|<span data-ttu-id="3c233-263">用户名</span><span class="sxs-lookup"><span data-stu-id="3c233-263">Username</span></span>|<span data-ttu-id="3c233-264">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="3c233-264">“Complianceuser”</span></span>||
|<span data-ttu-id="3c233-265">密码</span><span class="sxs-lookup"><span data-stu-id="3c233-265">Password</span></span>|<span data-ttu-id="3c233-266">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="3c233-266">“Compliancepassword”</span></span>||

##### <a name="response-codes"></a><span data-ttu-id="3c233-267">响应代码</span><span class="sxs-lookup"><span data-stu-id="3c233-267">Response codes</span></span>

| <span data-ttu-id="3c233-268">响应代码</span><span class="sxs-lookup"><span data-stu-id="3c233-268">Response Code</span></span> | <span data-ttu-id="3c233-269">说明</span><span class="sxs-lookup"><span data-stu-id="3c233-269">Description</span></span>                   |
| ----------------- | --------------------------------- |
| <span data-ttu-id="3c233-270">200</span><span class="sxs-lookup"><span data-stu-id="3c233-270">200</span></span>               | <span data-ttu-id="3c233-271">正常，atom+ xml 中的事件列表</span><span class="sxs-lookup"><span data-stu-id="3c233-271">OK, A list of events in atom+ xml</span></span> |
| <span data-ttu-id="3c233-272">404</span><span class="sxs-lookup"><span data-stu-id="3c233-272">404</span></span>               | <span data-ttu-id="3c233-273">未找到</span><span class="sxs-lookup"><span data-stu-id="3c233-273">Not found</span></span>                         |
| <span data-ttu-id="3c233-274">302</span><span class="sxs-lookup"><span data-stu-id="3c233-274">302</span></span>               | <span data-ttu-id="3c233-275">重定向</span><span class="sxs-lookup"><span data-stu-id="3c233-275">Redirect</span></span>                          |
| <span data-ttu-id="3c233-276">401</span><span class="sxs-lookup"><span data-stu-id="3c233-276">401</span></span>               | <span data-ttu-id="3c233-277">授权失败</span><span class="sxs-lookup"><span data-stu-id="3c233-277">Authorization Failed</span></span>              |
| <span data-ttu-id="3c233-278">403</span><span class="sxs-lookup"><span data-stu-id="3c233-278">403</span></span>               | <span data-ttu-id="3c233-279">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="3c233-279">Authentication Failed</span></span>             |

##### <a name="get-an-event-by-id"></a><span data-ttu-id="3c233-280">按 ID 获取事件。</span><span class="sxs-lookup"><span data-stu-id="3c233-280">Get an event by ID</span></span>

| <span data-ttu-id="3c233-281">方法</span><span class="sxs-lookup"><span data-stu-id="3c233-281">Method</span></span>         | <span data-ttu-id="3c233-282">GET</span><span class="sxs-lookup"><span data-stu-id="3c233-282">GET</span></span>   |                      |
| -------------- | ------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------ | -------------------- |
| <span data-ttu-id="3c233-283">URL</span><span class="sxs-lookup"><span data-stu-id="3c233-283">URL</span></span>            | <span data-ttu-id="3c233-284">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span><span class="sxs-lookup"><span data-stu-id="3c233-284">[https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent(‘174e9a86-74ff-4450-8666-7c11f7730f66’)](https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent\('174e9a86-74ff-4450-8666-7c11f7730f66'\))</span></span> |                      |
| <span data-ttu-id="3c233-285">标头</span><span class="sxs-lookup"><span data-stu-id="3c233-285">Header</span></span>         | <span data-ttu-id="3c233-286">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3c233-286">Content-Type</span></span>                                                                                                                                                                                                                                                       | <span data-ttu-id="3c233-287">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="3c233-287">application/atom+xml</span></span> |
| <span data-ttu-id="3c233-288">身份验证</span><span class="sxs-lookup"><span data-stu-id="3c233-288">Authentication</span></span> | <span data-ttu-id="3c233-289">基本</span><span class="sxs-lookup"><span data-stu-id="3c233-289">Basic</span></span>                                                                                                                                                                                                                                                              |                      |
| <span data-ttu-id="3c233-290">用户名</span><span class="sxs-lookup"><span data-stu-id="3c233-290">Username</span></span>       | <span data-ttu-id="3c233-291">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="3c233-291">“Complianceuser”</span></span>                                                                                                                                                                                                                                                   |                      |
| <span data-ttu-id="3c233-292">密码</span><span class="sxs-lookup"><span data-stu-id="3c233-292">Password</span></span>       | <span data-ttu-id="3c233-293">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="3c233-293">“Compliancepassword”</span></span>                                                                                                                                                                                                                                               |                      |

##### <a name="response-codes"></a><span data-ttu-id="3c233-294">响应代码</span><span class="sxs-lookup"><span data-stu-id="3c233-294">Response codes</span></span>

| <span data-ttu-id="3c233-295">响应代码</span><span class="sxs-lookup"><span data-stu-id="3c233-295">Response Code</span></span> | <span data-ttu-id="3c233-296">说明</span><span class="sxs-lookup"><span data-stu-id="3c233-296">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="3c233-297">200</span><span class="sxs-lookup"><span data-stu-id="3c233-297">200</span></span>               | <span data-ttu-id="3c233-298">正常，响应正文包含 atom+xml 中的事件</span><span class="sxs-lookup"><span data-stu-id="3c233-298">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="3c233-299">404</span><span class="sxs-lookup"><span data-stu-id="3c233-299">404</span></span>               | <span data-ttu-id="3c233-300">未找到</span><span class="sxs-lookup"><span data-stu-id="3c233-300">Not found</span></span>                                            |
| <span data-ttu-id="3c233-301">302</span><span class="sxs-lookup"><span data-stu-id="3c233-301">302</span></span>               | <span data-ttu-id="3c233-302">重定向</span><span class="sxs-lookup"><span data-stu-id="3c233-302">Redirect</span></span>                                             |
| <span data-ttu-id="3c233-303">401</span><span class="sxs-lookup"><span data-stu-id="3c233-303">401</span></span>               | <span data-ttu-id="3c233-304">授权失败</span><span class="sxs-lookup"><span data-stu-id="3c233-304">Authorization Failed</span></span>                                 |
| <span data-ttu-id="3c233-305">403</span><span class="sxs-lookup"><span data-stu-id="3c233-305">403</span></span>               | <span data-ttu-id="3c233-306">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="3c233-306">Authentication Failed</span></span>                                |

##### <a name="get-an-event-by-name"></a><span data-ttu-id="3c233-307">按名称获取事件</span><span class="sxs-lookup"><span data-stu-id="3c233-307">Get an event by name</span></span>

| <span data-ttu-id="3c233-308">方法</span><span class="sxs-lookup"><span data-stu-id="3c233-308">Method</span></span>         | <span data-ttu-id="3c233-309">GET</span><span class="sxs-lookup"><span data-stu-id="3c233-309">GET</span></span>       |                      |
| -------------- | -------------------------------------------------------------------------------------------------------------------------------------------- | -------------------- |
| <span data-ttu-id="3c233-310">URL</span><span class="sxs-lookup"><span data-stu-id="3c233-310">URL</span></span>            | <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent('EventByRESTPost-2226bfebcc2841a8968ba71f9516b763')> |                      |
| <span data-ttu-id="3c233-311">标头</span><span class="sxs-lookup"><span data-stu-id="3c233-311">Headers</span></span>        | <span data-ttu-id="3c233-312">Content-Type</span><span class="sxs-lookup"><span data-stu-id="3c233-312">Content-Type</span></span>                                                                                                                                 | <span data-ttu-id="3c233-313">application/atom+xml</span><span class="sxs-lookup"><span data-stu-id="3c233-313">application/atom+xml</span></span> |
| <span data-ttu-id="3c233-314">身份验证</span><span class="sxs-lookup"><span data-stu-id="3c233-314">Authentication</span></span> | <span data-ttu-id="3c233-315">基本</span><span class="sxs-lookup"><span data-stu-id="3c233-315">Basic</span></span>                                                                                                                                        |                      |
| <span data-ttu-id="3c233-316">用户名</span><span class="sxs-lookup"><span data-stu-id="3c233-316">Username</span></span>       | <span data-ttu-id="3c233-317">“Complianceuser”</span><span class="sxs-lookup"><span data-stu-id="3c233-317">“Complianceuser”</span></span>                                                                                                                             |                      |
| <span data-ttu-id="3c233-318">密码</span><span class="sxs-lookup"><span data-stu-id="3c233-318">Password</span></span>       | <span data-ttu-id="3c233-319">“Compliancepassword”</span><span class="sxs-lookup"><span data-stu-id="3c233-319">“Compliancepassword”</span></span>                                                                                                                         |                      |

##### <a name="response-codes"></a><span data-ttu-id="3c233-320">响应代码</span><span class="sxs-lookup"><span data-stu-id="3c233-320">Response codes</span></span>

| <span data-ttu-id="3c233-321">响应代码</span><span class="sxs-lookup"><span data-stu-id="3c233-321">Response Code</span></span> | <span data-ttu-id="3c233-322">说明</span><span class="sxs-lookup"><span data-stu-id="3c233-322">Description</span></span>                                      |
| ----------------- | ---------------------------------------------------- |
| <span data-ttu-id="3c233-323">200</span><span class="sxs-lookup"><span data-stu-id="3c233-323">200</span></span>               | <span data-ttu-id="3c233-324">正常，响应正文包含 atom+xml 中的事件</span><span class="sxs-lookup"><span data-stu-id="3c233-324">OK, The response body contains the event in atom+xml</span></span> |
| <span data-ttu-id="3c233-325">404</span><span class="sxs-lookup"><span data-stu-id="3c233-325">404</span></span>               | <span data-ttu-id="3c233-326">未找到</span><span class="sxs-lookup"><span data-stu-id="3c233-326">Not found</span></span>                                            |
| <span data-ttu-id="3c233-327">302</span><span class="sxs-lookup"><span data-stu-id="3c233-327">302</span></span>               | <span data-ttu-id="3c233-328">重定向</span><span class="sxs-lookup"><span data-stu-id="3c233-328">Redirect</span></span>                                             |
| <span data-ttu-id="3c233-329">401</span><span class="sxs-lookup"><span data-stu-id="3c233-329">401</span></span>               | <span data-ttu-id="3c233-330">授权失败</span><span class="sxs-lookup"><span data-stu-id="3c233-330">Authorization Failed</span></span>                                 |
| <span data-ttu-id="3c233-331">403</span><span class="sxs-lookup"><span data-stu-id="3c233-331">403</span></span>               | <span data-ttu-id="3c233-332">身份验证失败</span><span class="sxs-lookup"><span data-stu-id="3c233-332">Authentication Failed</span></span>                                |

#### <a name="using-powershell-ver6-or-higher-or-any-http-client"></a><span data-ttu-id="3c233-333">使用 PowerShell（版本 6 或更高版本）或任何 HTTP 客户端</span><span class="sxs-lookup"><span data-stu-id="3c233-333">Using PowerShell (ver.6 or higher) or any HTTP client</span></span>

<span data-ttu-id="3c233-334">步骤 1：连接到 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="3c233-334">Step 1: Connect to PowerShell.</span></span>

<span data-ttu-id="3c233-335">步骤 2：运行以下脚本。</span><span class="sxs-lookup"><span data-stu-id="3c233-335">Step 2: Run the following script.</span></span>

```powershell
param([string]$baseUri)

$userName = "UserName"

$password = "Password"

$securePassword = ConvertTo-SecureString $password -AsPlainText -Force

$credentials = New-Object System.Management.Automation.PSCredential($userName, $securePassword)

$EventName="EventByRESTPost-$(([Guid]::NewGuid()).ToString('N'))"

Write-Host "Start to create an event with name: $EventName"

$body = "<?xml version='1.0' encoding='utf-8' standalone='yes'?>

<entry xmlns:d='http://schemas.microsoft.com/ado/2007/08/dataservices'

xmlns:m='http://schemas.microsoft.com/ado/2007/08/dataservices/metadata'

xmlns='http://www.w3.org/2005/Atom'>

<category scheme='http://schemas.microsoft.com/ado/2007/08/dataservices/scheme' term='Exchange.ComplianceRetentionEvent' />

<updated>7/14/2017 2:03:36 PM</updated>

<content type='application/xml'>

<m:properties>

<d:Name>$EventName</d:Name>

<d:EventType>e823b782-9a07-4e30-8091-034fc01f9347</d:EventType>

<d:SharePointAssetIdQuery>'ComplianceAssetId:123'</d:SharePointAssetIdQuery>

</m:properties>

</content>

</entry>"

$event = $null

try

{

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri "$baseUri/ComplianceRetentionEvent" -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

catch

{

$response = $_.Exception.Response

if($response.StatusCode -eq "Redirect")

{

$url = $response.Headers.Location

Write-Host "redirected to $url"

$event = Invoke-RestMethod -Body $body -Method 'POST' -Uri $url -ContentType "application/atom+xml" -Authentication Basic -Credential $credentials -MaximumRedirection 0

}

}

$event | fl *

```


#### <a name="verify-the-outcome-in-both-options"></a><span data-ttu-id="3c233-336">验证两个选项的结果</span><span class="sxs-lookup"><span data-stu-id="3c233-336">Verify the outcome in both options</span></span>

<span data-ttu-id="3c233-337">步骤 1：转到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="3c233-337">Step 1: Go to the Security & Compliance Center.</span></span>

<span data-ttu-id="3c233-338">步骤 2：选择“**信息治理**”下的“**事件**”。</span><span class="sxs-lookup"><span data-stu-id="3c233-338">Step 2: Select **Events** under **Information governance**.</span></span>

<span data-ttu-id="3c233-339">步骤 3：验证已创建事件。</span><span class="sxs-lookup"><span data-stu-id="3c233-339">Step 3: Verify Event has been created.</span></span>

<span data-ttu-id="3c233-340">同样，上述用于自动执行基于事件的保留的选项也可用于以下场景。</span><span class="sxs-lookup"><span data-stu-id="3c233-340">Similarly, the above options to automate event-based retention can be used for the following scenarios as well.</span></span>

### <a name="scenario-2-contracts-expiring"></a><span data-ttu-id="3c233-341">场景 2：合同到期</span><span class="sxs-lookup"><span data-stu-id="3c233-341">Scenario 2: Contracts Expiring</span></span>

<span data-ttu-id="3c233-342">对于与客户、供应商和合作伙伴签订的单份合同，组织可能拥有多条记录。</span><span class="sxs-lookup"><span data-stu-id="3c233-342">An organization can have multiple records for a single contract with customers, vendors, and partners.</span></span> <span data-ttu-id="3c233-343">这些文档可以驻留在 SharePoint 等文档库中。</span><span class="sxs-lookup"><span data-stu-id="3c233-343">These documents can reside in a document library like SharePoint.</span></span> <span data-ttu-id="3c233-344">合同的终止决定了与合同关联的文档保留期的开始。</span><span class="sxs-lookup"><span data-stu-id="3c233-344">The end of a contract determines the start of the retention period of the documents associated with the contract.</span></span> <span data-ttu-id="3c233-345">例如：与合同相关的所有记录都需要在合同到期后保留 5 年。</span><span class="sxs-lookup"><span data-stu-id="3c233-345">For example, all records related to contracts need to be retained for five years from the time the contract expires.</span></span> <span data-ttu-id="3c233-346">触发 5 年保留期的事件是合同到期。</span><span class="sxs-lookup"><span data-stu-id="3c233-346">The event that triggers the five-year retention period is the expiration of the contract.</span></span>

<span data-ttu-id="3c233-347">客户关系管理 (CRM) 系统可以与 Microsoft 365 一起使用，用于触发合同文档的保留。</span><span class="sxs-lookup"><span data-stu-id="3c233-347">A Customer Relationship Management (CRM) system can work with Microsoft 365 and trigger retention of Contract documents.</span></span>

<span data-ttu-id="3c233-348">**为此场景配置基于事件的自动保留：**</span><span class="sxs-lookup"><span data-stu-id="3c233-348">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![针对合同到期场景的角色和任务关系图](../media/automate-event-driven-retention-contract-expiration.png)

  - <span data-ttu-id="3c233-350">管理员为每种合同类型创建一个包含各种文件夹的 SharePoint 库。</span><span class="sxs-lookup"><span data-stu-id="3c233-350">Admin creates a SharePoint library with various folders for each contract type.</span></span>

  - <span data-ttu-id="3c233-351">管理员将合同文件（如许可合同、开发合同）添加到每个合同文件夹。</span><span class="sxs-lookup"><span data-stu-id="3c233-351">Admin adds contract files such as License Contracts, Development Contracts to each contract folder.</span></span>

  - <span data-ttu-id="3c233-352">管理员为每个合同文件夹分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="3c233-352">Admin assigns Asset ID to each contract folder.</span></span>

  - <span data-ttu-id="3c233-353">SCC 管理员登录到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="3c233-353">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="3c233-354">SCC 管理员创建与合同相关的事件类型，例如“合同创建”和“合同到期”事件。</span><span class="sxs-lookup"><span data-stu-id="3c233-354">SCC Admin creates contract-related events types such as “Contract Creation”, “Contract Expiration” events.</span></span>

  - <span data-ttu-id="3c233-355">SCC 管理员创建“合同到期”标签。</span><span class="sxs-lookup"><span data-stu-id="3c233-355">SCC Admin creates “Contract Expiration” label.</span></span>

  - <span data-ttu-id="3c233-356">此“合同到期”标签将手动或自动发布并应用于 SharePoint 中的合同文件。</span><span class="sxs-lookup"><span data-stu-id="3c233-356">This “ Contract Expiration” label is published and applied manually or automatically to the contract files in SharePoint.</span></span>

  - <span data-ttu-id="3c233-357">合同管理系统可以与 Microsoft Flow 或类似的应用程序一起定期运行以管理合同文件。</span><span class="sxs-lookup"><span data-stu-id="3c233-357">Contract Management System can work with Microsoft Flow or a similar application to run periodically to manage contract files.</span></span>

  - <span data-ttu-id="3c233-358">如果合同到期，Microsoft Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定合同文件的保留期。</span><span class="sxs-lookup"><span data-stu-id="3c233-358">If a contract expires, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific contract’s files.</span></span>

### <a name="scenario-3-end-of-product-manufacturing"></a><span data-ttu-id="3c233-359">场景 3：产品制造终止</span><span class="sxs-lookup"><span data-stu-id="3c233-359">Scenario 3: End of Product Manufacturing</span></span>

<span data-ttu-id="3c233-360">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span><span class="sxs-lookup"><span data-stu-id="3c233-360">A manufacturing company that produces different lines of products creates many manufacturing specifications and pricing documents.</span></span> <span data-ttu-id="3c233-361">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span><span class="sxs-lookup"><span data-stu-id="3c233-361">When the product is no longer manufactured, all specifications and documents linked to this product need to be retained for a specific period after the end of the lifetime of the product.</span></span>

<span data-ttu-id="3c233-362">企业资源规划 (ERP) 系统可以与 Microsoft 365 和 Microsoft Flow 一起使用，用于触发保留。</span><span class="sxs-lookup"><span data-stu-id="3c233-362">An Enterprise Resource Planning (ERP) system can work with Microsoft 365 and Microsoft Flow to trigger retention.</span></span>

<span data-ttu-id="3c233-363">**为此场景配置基于事件的自动保留：**</span><span class="sxs-lookup"><span data-stu-id="3c233-363">**Configuring Automated Event Based Retention for this scenario:**</span></span>

![产品生命周期场景的角色和任务关系图](../media/automate-event-driven-retention-product-lifecycle-expiration.png)

  - <span data-ttu-id="3c233-365">管理员在文档集中创建产品文件夹，如产品 1、产品 2 等。</span><span class="sxs-lookup"><span data-stu-id="3c233-365">Admin creates product folders in the Document set such as Product 1, Product 2, and so on.</span></span>

  - <span data-ttu-id="3c233-366">管理员将产品文件（如制造规格、产品定价、产品许可）添加到每个产品文件夹中。</span><span class="sxs-lookup"><span data-stu-id="3c233-366">Admin adds product files such as Manufacturing Specifications, Product Pricing, Product licensing to each product folder.</span></span>

  - <span data-ttu-id="3c233-367">管理员为每个产品文件夹分配资产 ID。</span><span class="sxs-lookup"><span data-stu-id="3c233-367">Admin assigns Asset ID to each product folder.</span></span>

  - <span data-ttu-id="3c233-368">SCC 管理员登录到安全与合规中心。</span><span class="sxs-lookup"><span data-stu-id="3c233-368">SCC Admin logs into the Security & Compliance Center.</span></span>

  - <span data-ttu-id="3c233-369">SCC 管理员创建与员工相关的事件类型，例如“产品制造开始”和“产品制造结束”事件。</span><span class="sxs-lookup"><span data-stu-id="3c233-369">SCC Admin creates employee-related events types such as “Start of Product Manufacturing”, “End of Product Manufacturing” events.</span></span>

  - <span data-ttu-id="3c233-370">SCC 管理员创建“产品制造结束”标签。</span><span class="sxs-lookup"><span data-stu-id="3c233-370">SCC Admin creates “End of Product Manufacturing” label.</span></span>

  - <span data-ttu-id="3c233-371">此“产品制造终止”标签将手动或自动发布并应用于 SharePoint 中的产品文件。</span><span class="sxs-lookup"><span data-stu-id="3c233-371">This “ End of Product Manufacturing” label is published and applied manually or automatically to the product files in SharePoint.</span></span>

  - <span data-ttu-id="3c233-372">ERP 系统可以与 Microsoft Flow 或类似的应用程序一起定期运行以管理产品文件。</span><span class="sxs-lookup"><span data-stu-id="3c233-372">ERP Systems can work with Microsoft Flow or similar applications to run periodically to manage product files.</span></span>

  - <span data-ttu-id="3c233-373">如果产品制造终止，Microsoft Flow 将触发 M365 基于事件的保留 REST API，该 API 将开始特定产品文件的保留期。</span><span class="sxs-lookup"><span data-stu-id="3c233-373">If the manufacturing of a product ends, Microsoft Flow will trigger the M365 Event Based Retention REST API that will begin the retention clock on the specific product’s files.</span></span>

## <a name="appendix"></a><span data-ttu-id="3c233-374">附录</span><span class="sxs-lookup"><span data-stu-id="3c233-374">Appendix</span></span>

### <a name="using-redirect-302-response-results-to-call-the-rest-api"></a><span data-ttu-id="3c233-375">使用重定向 302 响应结果来调用 REST API</span><span class="sxs-lookup"><span data-stu-id="3c233-375">Using Redirect 302 response results to call the REST API</span></span>

1. <span data-ttu-id="3c233-376">通过使用 REST API URL <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> 调用 POST 保留事件调用（需要全局管理员权限）。</span><span class="sxs-lookup"><span data-stu-id="3c233-376">Invoke a POST retention event call by using the REST API URL, <https://ps.compliance.protection.outlook.com/psws/service.svc/ComplianceRetentionEvent> (Global Admin permissions are required).</span></span>

2. <span data-ttu-id="3c233-377">检查响应代码。</span><span class="sxs-lookup"><span data-stu-id="3c233-377">Check the response code.</span></span> <span data-ttu-id="3c233-378">如果是 302，则从响应标头的“位置”属性中获取重定向的 URL。</span><span class="sxs-lookup"><span data-stu-id="3c233-378">If it's 302, then get the redirected URL from Location property of the response header.</span></span>

3. <span data-ttu-id="3c233-379">使用重定向的 URL 再次调用 POST 保留事件调用。</span><span class="sxs-lookup"><span data-stu-id="3c233-379">Invoke the POST retention event call again using the redirected URL.</span></span>

## <a name="credits"></a><span data-ttu-id="3c233-380">制作人员</span><span class="sxs-lookup"><span data-stu-id="3c233-380">Credits</span></span>

<span data-ttu-id="3c233-381">本主题经过以下人员的审阅：</span><span class="sxs-lookup"><span data-stu-id="3c233-381">This topic was reviewed by:</span></span>

<span data-ttu-id="3c233-382">Antonio Maio</span><span class="sxs-lookup"><span data-stu-id="3c233-382">Antonio Maio</span></span><br/><span data-ttu-id="3c233-383">Microsoft Office 应用和服务 MVP</span><span class="sxs-lookup"><span data-stu-id="3c233-383">Microsoft Office Apps and Services MVP</span></span><br/> <span data-ttu-id="3c233-384">Antonio.Maio@Protiviti.com</span><span class="sxs-lookup"><span data-stu-id="3c233-384">Antonio.Maio@Protiviti.com</span></span>
