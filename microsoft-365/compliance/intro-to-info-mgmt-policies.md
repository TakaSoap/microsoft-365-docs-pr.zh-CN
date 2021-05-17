---
title: 信息管理策略简介
f1.keywords:
- NOCSH
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
ms.date: 5/16/2014
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- WSU150
- SPO160
- OSU150
- MET150
ms.assetid: 63a0b501-ba59-44b7-a35c-999f3be057b2
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何使用信息管理策略控制和跟踪内容保留时间或用户可以对内容采取的操作等内容。
ms.openlocfilehash: dfb1aeb3dbd3a2b17f18bbd03d5f4d3e198e4c47
ms.sourcegitcommit: 973f5449784cb70ce5545bc3cf57bf1ce5209218
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2020
ms.locfileid: "44815509"
---
# <a name="introduction-to-information-management-policies"></a><span data-ttu-id="3c498-103">信息管理策略简介</span><span class="sxs-lookup"><span data-stu-id="3c498-103">Introduction to information management policies</span></span>

<span data-ttu-id="3c498-104">信息管理策略是适用于特定类型内容的一组规则。</span><span class="sxs-lookup"><span data-stu-id="3c498-104">An information management policy is a set of rules for a type of content.</span></span> <span data-ttu-id="3c498-105">信息管理策略使组织能够控制和跟踪多类信息，例如将内容保留多长时间，或者用户可以对该内容执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="3c498-105">Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content.</span></span> <span data-ttu-id="3c498-106">信息管理策略可帮助组织遵守法律或政府法规，或者可以仅强制执行内部业务流程。</span><span class="sxs-lookup"><span data-stu-id="3c498-106">Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes.</span></span> 
  
<span data-ttu-id="3c498-107">例如，必须遵守政府法规且要求其证明"充分控制"其财务报表的组织可以创建一个或多个信息管理策略，以审核与财务归档相关的所有文档的创作和审批过程中的特定操作。</span><span class="sxs-lookup"><span data-stu-id="3c498-107">For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.</span></span>
  
<span data-ttu-id="3c498-108">有关使用方法的信息，请参阅创建 [和应用信息管理策略](create-info-mgmt-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="3c498-108">For how-to information, see [Create and apply information management policies](create-info-mgmt-policies.md).</span></span>
  
## <a name="features-of-information-management-policies"></a><span data-ttu-id="3c498-109">信息管理策略的功能</span><span class="sxs-lookup"><span data-stu-id="3c498-109">Features of information management policies</span></span>
<span data-ttu-id="3c498-110"><a name="__top"> </a></span><span class="sxs-lookup"><span data-stu-id="3c498-110"><a name="__top"> </a></span></span>

<span data-ttu-id="3c498-111">有四种预定义策略功能的基本类别，组织可以单独或组合使用这些功能来管理内容和流程。</span><span class="sxs-lookup"><span data-stu-id="3c498-111">There are four basic categories of predefined policy features that organizations can use individually or in combination to manage content and processes.</span></span> 
  
![内容策略的类型](../media/19fcb8a3-974b-40d3-a13f-b76088d122f8.png)
  
<span data-ttu-id="3c498-113">审核策略功能可帮助组织分析如何通过记录对文档和列表项执行的事件和操作来使用其内容管理系统。</span><span class="sxs-lookup"><span data-stu-id="3c498-113">The Auditing policy feature helps organizations analyze how their content management systems are used by logging events and operations that are performed on documents and list items.</span></span> <span data-ttu-id="3c498-114">可以将审核策略功能配置为记录事件，例如编辑、查看、签入、签出、删除文档或项目或更改其权限时。</span><span class="sxs-lookup"><span data-stu-id="3c498-114">You can configure the Auditing policy feature to log events such as when a document or item is edited, viewed, checked in, checked out, deleted, or has its permissions changed.</span></span> <span data-ttu-id="3c498-115">所有审核信息都存储在服务器的单个审核日志中，网站管理员可以对它运行报告。</span><span class="sxs-lookup"><span data-stu-id="3c498-115">All of the audit information is stored in a single audit log on the server, and site administrators can run reports on it.</span></span> 
  
<span data-ttu-id="3c498-116">过期策略功能可帮助组织以一致且可跟踪的方式从网站中删除过期内容。</span><span class="sxs-lookup"><span data-stu-id="3c498-116">The Expiration policy feature helps organizations delete or remove out-of-date content from their sites in a consistent, trackable way.</span></span> <span data-ttu-id="3c498-117">这可以帮助您管理与保留过期内容相关的成本和风险。</span><span class="sxs-lookup"><span data-stu-id="3c498-117">This helps you manage both the cost and risk associated with retaining out-of-date content.</span></span> <span data-ttu-id="3c498-118">您可以配置过期策略，以指定特定类型的内容在特定日期或文档创建或上次修改后的一段时间过期。</span><span class="sxs-lookup"><span data-stu-id="3c498-118">You can configure an Expiration policy to specify that certain types of content expire on a particular date or within a period of time after the document was created or last modified.</span></span>
  
<span data-ttu-id="3c498-119">组织还可以创建和部署自定义策略功能，以满足特定需求。</span><span class="sxs-lookup"><span data-stu-id="3c498-119">Organizations can also create and deploy custom policy features to meet specific needs.</span></span> <span data-ttu-id="3c498-120">例如，制造组织可能需要为禁止用户在不安全的打印机上打印这些文档副本的所有产品开发规范草稿文档定义信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-120">For example, a manufacturing organization might want to define an information management policy for all draft product-design specification documents that prohibits users from printing copies of these documents on nonsecure printers.</span></span> <span data-ttu-id="3c498-121">若要定义此类信息管理策略，可以创建和部署可添加到产品开发规范内容类型相关信息管理策略中的打印限制策略功能。</span><span class="sxs-lookup"><span data-stu-id="3c498-121">To define this kind of information management policy, you can create and deploy a Printing Restriction policy feature that can be added to the relevant information management policy for the product design specification content type.</span></span>
  
## <a name="locations-to-use-an-information-management-policy"></a><span data-ttu-id="3c498-122">使用信息管理策略的位置</span><span class="sxs-lookup"><span data-stu-id="3c498-122">Locations to use an information management policy</span></span>
<span data-ttu-id="3c498-123"><a name="__toc340213528"> </a></span><span class="sxs-lookup"><span data-stu-id="3c498-123"><a name="__toc340213528"> </a></span></span>

<span data-ttu-id="3c498-124">若要实现信息管理策略，您必须将其添加到网站中的列表、库或内容类型。</span><span class="sxs-lookup"><span data-stu-id="3c498-124">To implement an information management policy, you must add it to a list, library, or content type in a site.</span></span> <span data-ttu-id="3c498-125">创建或添加信息管理策略的位置会影响策略的适用范围或策略的适用范围。</span><span class="sxs-lookup"><span data-stu-id="3c498-125">The location where you create or add an information management policy affects how broadly the policy applies or how broadly it can be used.</span></span> <span data-ttu-id="3c498-126">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="3c498-126">You can:</span></span>
  
 <span data-ttu-id="3c498-127">**创建网站集策略，然后将此策略添加到内容类型、列表或库** 可以在网站集首要网站的"策略"列表中创建网站集策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-127">**Create a site collection policy and then add this policy to a content type, list, or library** You can create a site collection policy in the Policies list in the top-level site of a site collection.</span></span> <span data-ttu-id="3c498-128">创建网站集策略后，可以导出它，以便其他网站集的管理员可以将其导入到其策略列表中。</span><span class="sxs-lookup"><span data-stu-id="3c498-128">After you create a site collection policy, you can export it so that administrators of other site collections can import it into their Policies list.</span></span> <span data-ttu-id="3c498-129">通过创建可导出的网站集策略，您可以标准化组织中各个网站的信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-129">Creating an exportable site collection policy enables you to standardize the information management policies across the sites in your organization.</span></span> 
  
<span data-ttu-id="3c498-130">当您将网站集策略添加到网站内容类型，并且该网站内容类型的实例添加到列表或库中时，该列表或库的所有者无法修改列表或库的网站集策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-130">When you add a site collection policy to a site content type, and an instance of that site content type is added to a list or library, the owner of that list or library cannot modify the site collection policy for the list or library.</span></span> <span data-ttu-id="3c498-131">将网站集策略添加到网站内容类型是确保网站集策略在网站层次结构的每个级别强制实施的一个好方法。</span><span class="sxs-lookup"><span data-stu-id="3c498-131">Adding a site collection policy to a site content type is a good way to ensure that site collection policies are enforced at each level of your site hierarchy.</span></span>
  
!["网站集"页上的"内容类型策略设置链接](../media/26d3466a-23ec-443f-88f0-2aaff38e992b.png)
  
 <span data-ttu-id="3c498-133">在首要网站的"网站内容类型库"中为网站内容类型创建信息管理策略，然后将该内容类型添加到一 **个或多个列表或库中** 您还可以直接为网站内容类型创建信息管理策略，然后将该网站内容类型的实例与多个列表或库关联。</span><span class="sxs-lookup"><span data-stu-id="3c498-133">**Create an information management policy for a site content type in the top-level site's Site Content Type Gallery, and then add that content type to one or more lists or libraries** You can also create an information management policy directly for a site content type and then associate an instance of that site content type with multiple lists or libraries.</span></span> <span data-ttu-id="3c498-134">如果这样创建信息管理策略，则此内容类型的网站集或从该内容类型继承的内容类型中的每个项目都有该策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-134">If you create an information management policy this way, every item in the site collection of that content type or a content type that inherits from that content type has the policy.</span></span> <span data-ttu-id="3c498-135">但是，如果直接为网站内容类型创建信息管理策略，则更难在其他网站集中重复使用此信息管理策略，因为无法导出通过此方式创建的策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-135">However, if you create an information management policy directly for a site content type, it is more difficult to reuse this information management policy in other site collections, because policies that are created this way cannot be exported.</span></span> 
  
!["网站类型"页上的"网站设置链接](../media/6f6fa51f-15d7-4782-b06f-a7b36e874cd3.png)
  
![网站内容类型的设置页上的信息管理策略链接](../media/15d83a34-6c8f-4b6e-b6ee-e9b0a70cbb4b.png)
  
<span data-ttu-id="3c498-138">注释 若要控制网站集中使用哪些策略，网站集管理员可以禁用直接在内容类型上设置策略功能的功能。</span><span class="sxs-lookup"><span data-stu-id="3c498-138">Note To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a content type.</span></span> <span data-ttu-id="3c498-139">当此限制生效时，创建内容类型的用户只能从网站集策略列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-139">When this restriction is in effect, users who create content types are limited to selecting policies from the site collection Policies list.</span></span>
  
 <span data-ttu-id="3c498-140">**为列表或库创建信息管理策略** 如果您的组织需要将特定的信息管理策略应用于一组非常有限的内容，您可以创建仅适用于单个列表或库的信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-140">**Create an information management policy for a list or library** If your organization needs to apply a specific information management policy to a very limited set of content, you can create an information management policy that applies only to an individual list or library.</span></span> <span data-ttu-id="3c498-141">这种创建信息管理策略的方法最不灵活，因为该策略仅适用于一个位置，并且不能导出或重新用于其他位置。</span><span class="sxs-lookup"><span data-stu-id="3c498-141">This method of creating an information management policy is the least flexible, because the policy applies only to one location, and it cannot be exported or reused for other locations.</span></span> <span data-ttu-id="3c498-142">但是，有时可能需要创建具有有限适用性的唯一信息管理策略来解决特定情况。</span><span class="sxs-lookup"><span data-stu-id="3c498-142">However, sometimes you may need to create unique information management policies with limited applicability to address specific situations.</span></span> 
  
![文档库的设置页上的信息管理策略链接](../media/9fa6d366-6aab-49e1-a05c-898ac6f536e6.png)
  
<span data-ttu-id="3c498-144">备注</span><span class="sxs-lookup"><span data-stu-id="3c498-144">Notes</span></span> 
  
<span data-ttu-id="3c498-145">只有当列表或库不支持多种内容类型时，才能为该列表或库创建信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-145">You can create an information management policy for a list or library only if that list or library does not support multiple content types.</span></span> <span data-ttu-id="3c498-146">如果列表或库支持多种内容类型，则需要为与该列表或库关联的每个列表内容类型定义信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-146">If a list or library supports multiple content types, you need to define an information management policy for each individual list content type that is associated with that list or library.</span></span> <span data-ttu-id="3c498-147"> (与特定列表或库关联的网站内容类型的实例称为列表内容类型。) </span><span class="sxs-lookup"><span data-stu-id="3c498-147">(Instances of a site content type that are associated with a specific list or library are known as list content types.)</span></span>
  
<span data-ttu-id="3c498-148">若要控制网站集中使用哪些策略，网站集管理员可以禁用直接在列表或库上设置策略功能的功能。</span><span class="sxs-lookup"><span data-stu-id="3c498-148">To control which policies are used in a site collection, site collection administrators can disable the ability to set policy features directly on a list or library.</span></span> <span data-ttu-id="3c498-149">当此限制生效时，管理列表或库的用户只能从网站集策略列表中选择策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-149">When this restriction is in effect, users who manage lists or libraries are limited to selecting policies from the site collection Policies list.</span></span>
  
[<span data-ttu-id="3c498-150">信息管理策略是一组适用于一类内容的规则。信息管理策略使组织能够控制和跟踪内容保留时间或用户可以对内容采取的操作等内容。信息管理策略可帮助组织遵守法律或政府法规，也可以只强制执行内部业务流程。例如，必须遵守政府法规且要求其证明"充分控制"其财务报表的组织可以创建一个或多个信息管理策略，以审核与财务归档相关的所有文档的创作和审批过程中的特定操作。有关使用方法的信息，请参阅创建和应用信息管理策略。</span><span class="sxs-lookup"><span data-stu-id="3c498-150">An information management policy is a set of rules for a type of content. Information management policies enable organizations to control and track things like how long content is retained or what actions users can take with that content. Information management policies can help organizations comply with legal or governmental regulations, or they can simply enforce internal business processes. For example, an organization that must follow government regulations requiring that they demonstrate "adequate controls" of their financial statements might create one or more information management policies that audit specific actions in the authoring and approval process for all documents related to financial filings.For how-to information, see Create and apply information management policies.</span></span>](intro-to-info-mgmt-policies.md#__top)
  

