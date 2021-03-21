---
title: 数据移动常见问题解答
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
search.appverid:
- MET150
ms.assetid: 1f01bc6f-5d37-4d14-bdd3-9d94a1e23e14
f1.keywords:
- NOCSH
description: 查找常见问题解答 (常见问题解答) 核心数据移动到新的 Office 365 数据中心地理位置。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: e66c9f29b47c3f1bc8d6e89ebf2f077eee9f4adf
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50919124"
---
# <a name="data-move-general-faq"></a><span data-ttu-id="bd30e-103">数据移动常见问题解答</span><span class="sxs-lookup"><span data-stu-id="bd30e-103">Data move general FAQ</span></span>

<span data-ttu-id="bd30e-104">下面是有关将静止的核心客户数据移动到新数据中心地理位置的一般问题的答案。</span><span class="sxs-lookup"><span data-stu-id="bd30e-104">Here are answers to general questions about moving core customer data at rest to a new datacenter geo.</span></span>
  
## <a name="what-customers-are-eligible-to-request-a-move"></a><span data-ttu-id="bd30e-105">哪些客户有资格请求移动？</span><span class="sxs-lookup"><span data-stu-id="bd30e-105">What customers are eligible to request a move?</span></span>
  
<span data-ttu-id="bd30e-106">选择符合新数据中心地理位置条件的国家/地区的现有 Microsoft 365 商业客户将能够请求迁移。</span><span class="sxs-lookup"><span data-stu-id="bd30e-106">Existing Microsoft 365 commercial customers who selected a country eligible for the new datacenter geo will be able to request a move.</span></span> <span data-ttu-id="bd30e-107">该计划仅适用于具有分配给 Microsoft 365 租户的符合条件的国家/地区代码的租户，用于将符合条件的工作负载的其余核心客户数据迁移到相应的 Microsoft 365 数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="bd30e-107">The program exists only for tenants with an eligible country code assigned to the Microsoft 365 tenant to migrate core customer data at rest for eligible workloads to the corresponding Microsoft 365 datacenter geo.</span></span> <span data-ttu-id="bd30e-108">请参阅如何请求 [数据移动页面](request-your-data-move.md) 以确认国家/地区资格。</span><span class="sxs-lookup"><span data-stu-id="bd30e-108">Please refer to the [How to request your data move](request-your-data-move.md) page to confirm country eligibility.</span></span>   

## <a name="how-do-we-define-core-customer-data"></a><span data-ttu-id="bd30e-109">如何定义核心客户数据？</span><span class="sxs-lookup"><span data-stu-id="bd30e-109">How do we define Core Customer Data?</span></span>
 
<span data-ttu-id="bd30e-110">核心客户数据是一个术语，它引用在"客户术语"中定义的Microsoft Online Services [子集](https://aka.ms/ost)：</span><span class="sxs-lookup"><span data-stu-id="bd30e-110">Core customer data is a term that refers to a subset of customer data defined in the [Microsoft Online Services Terms](https://aka.ms/ost):</span></span> 
- <span data-ttu-id="bd30e-111">Exchange Online 邮箱 (电子邮件正文、日历条目以及电子邮件附件内容) </span><span class="sxs-lookup"><span data-stu-id="bd30e-111">Exchange Online mailbox content (email body, calendar entries, and the content of email attachments)</span></span>
- <span data-ttu-id="bd30e-112">SharePoint Online 网站内容和存储在该网站中的文件</span><span class="sxs-lookup"><span data-stu-id="bd30e-112">SharePoint Online site content and the files stored within that site</span></span>
- <span data-ttu-id="bd30e-113">上传到 OneDrive for Business 的文件</span><span class="sxs-lookup"><span data-stu-id="bd30e-113">Files uploaded to OneDrive for Business</span></span> 

## <a name="what-is-in-scope-for-teams-migration"></a><span data-ttu-id="bd30e-114">Teams 迁移的范围是什么？</span><span class="sxs-lookup"><span data-stu-id="bd30e-114">What is in scope for Teams migration?</span></span>

<span data-ttu-id="bd30e-115">除了 Exchange Online、SharePoint Online 和 OneDrive for Business;Microsoft 将 Teams 数据迁移到本地数据中心。</span><span class="sxs-lookup"><span data-stu-id="bd30e-115">In addition to Exchange Online, SharePoint Online, and OneDrive for Business; Microsoft will migrate Teams data to the local datacenter.</span></span> 
- <span data-ttu-id="bd30e-116">Teams 聊天消息，包括私人消息和频道消息。</span><span class="sxs-lookup"><span data-stu-id="bd30e-116">Teams chat messages, including private messages and channel messages.</span></span> 
- <span data-ttu-id="bd30e-117">聊天中使用的 Teams 图像。</span><span class="sxs-lookup"><span data-stu-id="bd30e-117">Teams images used in chats.</span></span> 

<span data-ttu-id="bd30e-118">Teams 文件存储在 SharePoint Online 中，Teams 聊天文件存储在 OneDrive for Business 中。</span><span class="sxs-lookup"><span data-stu-id="bd30e-118">Teams files are stored in SharePoint Online and Teams chat files are stored in OneDrive for Business.</span></span> <span data-ttu-id="bd30e-119">语音邮件、日历和联系人存储在 Exchange Online 中。</span><span class="sxs-lookup"><span data-stu-id="bd30e-119">Voicemail, calendar, and contacts are stored in Exchange Online.</span></span> <span data-ttu-id="bd30e-120">在许多情况下，Exchange Online、SharePoint Online 和 OneDrive for Business 已由本地数据中心地理位置的客户使用，也是符合条件的客户国家/地区 Microsoft 365 迁移计划的一部分。</span><span class="sxs-lookup"><span data-stu-id="bd30e-120">In many cases, Exchange Online, SharePoint Online, and OneDrive for Business are already used by the customer in the local datacenter geo and are also part of the Microsoft 365 migration program for eligible customer countries.</span></span>

## <a name="at-what-point-is-my-migration-complete-so-that-my-tenants-core-customer-data-is-being-stored-at-rest-in-my-new-geo"></a><span data-ttu-id="bd30e-121">我的迁移在什么时间点完成，以便我的租户的核心客户数据存储在我的新地理位置中？</span><span class="sxs-lookup"><span data-stu-id="bd30e-121">At what point is my migration complete so that my tenant's core customer data is being stored at rest in my new geo?</span></span>

<span data-ttu-id="bd30e-122">由于 Exchange Online 和 SharePoint Online/OneDrive for Business 之间的共享依赖关系，在迁移这两个服务之前，任何迁移都被视为已完成。</span><span class="sxs-lookup"><span data-stu-id="bd30e-122">Due to shared dependencies between Exchange Online and SharePoint Online/OneDrive for Business, any migration cannot be considered completed until both services are migrated.</span></span> <span data-ttu-id="bd30e-123">Exchange Online 和 SharePoint Online/OneDrive for Business 通常在单独的时间相互独立迁移。</span><span class="sxs-lookup"><span data-stu-id="bd30e-123">Exchange Online and SharePoint Online/OneDrive for Business often migrate at separate times and independently from one another.</span></span> <span data-ttu-id="bd30e-124">客户租户管理员在每个服务迁移完成时在消息中心收到确认，并且随时可以在管理中心查看数据位置卡，以确认每个服务的其余位置的核心客户数据。</span><span class="sxs-lookup"><span data-stu-id="bd30e-124">Customer tenant admins receive confirmation in Message Center when each service migration is completed and can view the data location card in the Admin Center at any time to confirm the core customer data at rest location for each service.</span></span>

## <a name="how-do-you-make-sure-my-customer-data-is-safe-during-the-move-and-that-i-wont-experience-downtime"></a><span data-ttu-id="bd30e-125">如何确保在移动期间我的客户数据是安全的，并且不会经历停机时间？</span><span class="sxs-lookup"><span data-stu-id="bd30e-125">How do you make sure my customer data is safe during the move and that I won't experience downtime?</span></span>
  
<span data-ttu-id="bd30e-126">数据移动是后端服务操作，对最终用户的影响最小。</span><span class="sxs-lookup"><span data-stu-id="bd30e-126">Data moves are a back-end service operation with minimal impact to end users.</span></span> <span data-ttu-id="bd30e-127">在数据移动期间和之后， [会列出可影响的功能](during-and-after-your-data-move.md)。</span><span class="sxs-lookup"><span data-stu-id="bd30e-127">Features that can be impacted are listed in [During and after your data move](during-and-after-your-data-move.md).</span></span> <span data-ttu-id="bd30e-128">我们遵守Microsoft Online Services [SLA ](https://go.microsoft.com/fwlink/p/?LinkId=523897) (SLA) ，因此在移动过程中客户无需准备或监视任何内容。</span><span class="sxs-lookup"><span data-stu-id="bd30e-128">We adhere to the [Microsoft Online Services Service Level Agreement (SLA)](https://go.microsoft.com/fwlink/p/?LinkId=523897) for availability so there is nothing that customers need to prepare for or to monitor during the move.</span></span> 
  
<span data-ttu-id="bd30e-129">所有 Microsoft 365 服务在数据中心中运行相同版本，因此可以保证功能一致。</span><span class="sxs-lookup"><span data-stu-id="bd30e-129">All Microsoft 365 services run the same versions in the datacenters, so you can be assured of consistent functionality.</span></span> <span data-ttu-id="bd30e-130">服务在整个过程中受到完全支持。</span><span class="sxs-lookup"><span data-stu-id="bd30e-130">Your service is fully supported throughout the process.</span></span>
  
## <a name="what-is-the-impact-of-having-different-services-located-in-different-geos"></a><span data-ttu-id="bd30e-131">将不同的服务位于不同的地理位置会有什么影响？</span><span class="sxs-lookup"><span data-stu-id="bd30e-131">What is the impact of having different services located in different geos?</span></span>

<span data-ttu-id="bd30e-132">某些 Microsoft 365 服务可能位于某些现有客户和进行移动过程中间的客户的不同地理位置。</span><span class="sxs-lookup"><span data-stu-id="bd30e-132">Some of the Microsoft 365 services may be located in different geos for some existing customers and for customers that are in the middle of the move process.</span></span> <span data-ttu-id="bd30e-133">我们的服务相互独立运行，如果是这样，则不会影响用户体验。</span><span class="sxs-lookup"><span data-stu-id="bd30e-133">Our services run independently of each other and there is no impact on the user experience if this is the case.</span></span> <span data-ttu-id="bd30e-134">但是，出于数据驻留目的，在将 Exchange Online 和 SharePoint Online/OneDrive for Business 迁移到同一数据中心地理位置之前，租户迁移不能被视为已完成。</span><span class="sxs-lookup"><span data-stu-id="bd30e-134">However, for data residency purposes, a tenant migration cannot be considered as complete until both Exchange Online and SharePoint Online/OneDrive for Business are migrated to the same datacenter geo.</span></span>

 ## <a name="where-is-my-core-customer-data-located"></a><span data-ttu-id="bd30e-135">我的核心客户数据位于何处？</span><span class="sxs-lookup"><span data-stu-id="bd30e-135">Where is my core customer data located?</span></span>

<span data-ttu-id="bd30e-136">客户租户管理员可以随时在管理中心内查看数据位置卡，以确认每个服务（特别是针对其租户）的其余位置的核心客户数据。</span><span class="sxs-lookup"><span data-stu-id="bd30e-136">Customer tenant admins can view the data location card in the Admin Center at any time to confirm the core customer data at rest location for each service, specifically for their tenant.</span></span>  <span data-ttu-id="bd30e-137">我们还在 Microsoft 365 交互式数据中心地图上发布了数据中心地理位置、数据中心和 Office [365 ](https://office.com/datamaps) 客户数据的位置，作为新租户的其余位置的当前默认核心客户数据的参考。</span><span class="sxs-lookup"><span data-stu-id="bd30e-137">We also publish the location of datacenter geos, datacenters, and location of Office 365 customer data on the [Microsoft 365 interactive datacenter maps ](https://office.com/datamaps) as a reference for the current default core customer data at rest locations for new tenants.</span></span> <span data-ttu-id="bd30e-138">可以通过 Microsoft 365 管理中心中"组织配置文件"下的"数据位置"部分验证客户数据处于其余位置。</span><span class="sxs-lookup"><span data-stu-id="bd30e-138">You can verify the location of your customer data at rest via the Data Location section under your Organization Profile in the Microsoft 365 admin center.</span></span>  
 
## <a name="when-will-i-be-able-to-request-a-move"></a><span data-ttu-id="bd30e-139">我何时可以请求移动？</span><span class="sxs-lookup"><span data-stu-id="bd30e-139">When will I be able to request a move?</span></span>
  
<span data-ttu-id="bd30e-140">请参阅如何请求 [数据](request-your-data-move.md) 移动页面，了解数据中心地理位置支持的时间范围。</span><span class="sxs-lookup"><span data-stu-id="bd30e-140">Please refer to the [How to request your data move](request-your-data-move.md) page for supported timeframes for your datacenter geo.</span></span>
  
## <a name="how-can-i-request-to-be-moved"></a><span data-ttu-id="bd30e-141">如何请求移动？</span><span class="sxs-lookup"><span data-stu-id="bd30e-141">How can I request to be moved?</span></span>
  
<span data-ttu-id="bd30e-142">符合条件的客户将看到 Microsoft [365 管理中心中的页面](https://admin.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="bd30e-142">Eligible customers will see a page in their [Microsoft 365 admin center](https://admin.microsoft.com/).</span></span> <span data-ttu-id="bd30e-143">有关如何 [请求移动的说明，](request-your-data-move.md) 请参阅如何请求数据移动。</span><span class="sxs-lookup"><span data-stu-id="bd30e-143">Please see [How to request your data move](request-your-data-move.md) for instructions on how to request a move.</span></span> 
  
## <a name="can-i-change-my-selection-after-requesting-a-move"></a><span data-ttu-id="bd30e-144">在请求移动后，我能否更改选择？</span><span class="sxs-lookup"><span data-stu-id="bd30e-144">Can I change my selection after requesting a move?</span></span>
  
<span data-ttu-id="bd30e-145">提交请求后，我们无法从流程中删除你。</span><span class="sxs-lookup"><span data-stu-id="bd30e-145">It is not possible for us to remove you from the process after you submit your request.</span></span>
  
## <a name="what-happens-if-i-do-not-request-a-move-before-the-deadline"></a><span data-ttu-id="bd30e-146">如果我在截止时间之前没有请求移动，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="bd30e-146">What happens if I do not request a move before the deadline?</span></span>
  
<span data-ttu-id="bd30e-147">在开放注册期后，我们不接受迁移请求。</span><span class="sxs-lookup"><span data-stu-id="bd30e-147">We cannot accept requests for migration after the open enrollment period.</span></span>

## <a name="what-if-i-want-to-move-my-data-in-order-to-get-better-network-performance"></a><span data-ttu-id="bd30e-148">如果我想移动数据以获得更好的网络性能，该做什么？</span><span class="sxs-lookup"><span data-stu-id="bd30e-148">What if I want to move my data in order to get better network performance?</span></span>
  
<span data-ttu-id="bd30e-149">与 Microsoft 365 数据中心的物理邻近度无法保证更好的网络性能。</span><span class="sxs-lookup"><span data-stu-id="bd30e-149">Physical proximity to a Microsoft 365 datacenter is not a guarantee for a better networking performance.</span></span> <span data-ttu-id="bd30e-150">影响最终用户和 Microsoft 365 服务之间的网络性能的因素和组件有很多。</span><span class="sxs-lookup"><span data-stu-id="bd30e-150">There are many factors and components that affect the network performance between the end user and the Microsoft 365 service.</span></span> <span data-ttu-id="bd30e-151">有关此优化和性能调整的信息，请参阅 [Microsoft 365 的网络规划和性能调整](network-planning-and-performance.md)。</span><span class="sxs-lookup"><span data-stu-id="bd30e-151">For more information about this and performance tuning, see [Network planning and performance tuning for Microsoft 365](network-planning-and-performance.md).</span></span>
  
 ## <a name="do-all-the-services-move-their-data-on-the-same-day"></a><span data-ttu-id="bd30e-152">所有服务是否在同一天移动数据？</span><span class="sxs-lookup"><span data-stu-id="bd30e-152">Do all the services move their data on the same day?</span></span>
 
<span data-ttu-id="bd30e-153">每个服务将独立移动，并且可能会在不同时间移动数据。</span><span class="sxs-lookup"><span data-stu-id="bd30e-153">Each service moves independently and will likely move their data at different times.</span></span>
  
 ## <a name="can-i-choose-when-i-want-my-data-to-be-moved"></a><span data-ttu-id="bd30e-154">我可以选择何时移动数据？</span><span class="sxs-lookup"><span data-stu-id="bd30e-154">Can I choose when I want my data to be moved?</span></span>
 
<span data-ttu-id="bd30e-155">客户无法选择特定日期，他们无法延迟移动，我们无法共享移动的特定日期或时间范围。</span><span class="sxs-lookup"><span data-stu-id="bd30e-155">Customers are not able to select a specific date, they cannot delay their move, and we cannot share a specific date or timeframe for the moves.</span></span>
  
 ## <a name="can-you-share-when-my-data-will-be-moved"></a><span data-ttu-id="bd30e-156">可以共享何时移动我的数据？</span><span class="sxs-lookup"><span data-stu-id="bd30e-156">Can you share when my data will be moved?</span></span>
  
<span data-ttu-id="bd30e-157">数据移动是后端操作，对最终用户的影响最小。</span><span class="sxs-lookup"><span data-stu-id="bd30e-157">Data moves are a back-end operation with minimal impact to end users.</span></span> <span data-ttu-id="bd30e-158">在全局运营和自动化环境中执行数据移动所需的复杂性、精度和规模会禁止我们在预计租户或其他任何单个租户完成数据移动时进行共享。</span><span class="sxs-lookup"><span data-stu-id="bd30e-158">The complexity, precision, and scale at which we need to perform data moves within a globally operated and automated environment prohibit us from sharing when a data move is expected to complete for your tenant or any other single tenant.</span></span> <span data-ttu-id="bd30e-159">完成数据移动后，客户将在每个参与服务的消息中心收到一个确认。</span><span class="sxs-lookup"><span data-stu-id="bd30e-159">Customers will receive one confirmation in Message Center per participating service when its data move has completed.</span></span> 
  
 ## <a name="what-happens-if-users-access-services-while-the-data-is-being-moved"></a><span data-ttu-id="bd30e-160">如果用户在数据移动时访问服务，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="bd30e-160">What happens if users access services while the data is being moved?</span></span>

<span data-ttu-id="bd30e-161">有关 [在每个服务](during-and-after-your-data-move.md) 的数据移动部分过程中可能受到限制的功能的完整列表，请参阅"数据移动期间"和"之后"。</span><span class="sxs-lookup"><span data-stu-id="bd30e-161">See [During and after your data move](during-and-after-your-data-move.md) for a complete list of features that may be limited during portions of the data move for each service.</span></span> 
  
 ## <a name="how-do-i-know-the-move-is-complete"></a><span data-ttu-id="bd30e-162">我如何知道移动已完成？</span><span class="sxs-lookup"><span data-stu-id="bd30e-162">How do I know the move is complete?</span></span>
  
<span data-ttu-id="bd30e-163">观看 Microsoft 365 消息中心，确认每项服务数据移动已完成。</span><span class="sxs-lookup"><span data-stu-id="bd30e-163">Watch the Microsoft 365 Message Center for confirmation that the move of each service's data is complete.</span></span> <span data-ttu-id="bd30e-164">当移动每个服务的数据时，我们将发布完成通知，以便你收到三个完成通知：分别针对 Exchange Online、SharePoint Online 和 Skype for Business Online。</span><span class="sxs-lookup"><span data-stu-id="bd30e-164">When each service's data is moved, we'll post a completion notice so you'll get three completion notices: one each for Exchange Online, SharePoint Online, and Skype for Business Online.</span></span> <span data-ttu-id="bd30e-165">您还可以通过 Microsoft 365 管理中心中"组织配置文件"下的"数据位置"部分验证客户数据处于其余位置。</span><span class="sxs-lookup"><span data-stu-id="bd30e-165">You can also verify the location of your customer data at rest via the Data Location section under your Organization Profile in the Microsoft 365 admin center.</span></span>  
  
## <a name="i-am-a-microsoft-365-customer-in-one-of-the-new-datacenter-geos-but-when-i-signed-up-i-selected-a-different-country-how-can-i-be-moved-to-the-new-datacenter-geo"></a><span data-ttu-id="bd30e-166">我是一个新的数据中心地理位置中的 Microsoft 365 客户，但在注册时，我选择了不同的国家/地区。</span><span class="sxs-lookup"><span data-stu-id="bd30e-166">I am a Microsoft 365 customer in one of the new datacenter geos, but when I signed up, I selected a different country.</span></span> <span data-ttu-id="bd30e-167">如何移动到新的数据中心地理位置？</span><span class="sxs-lookup"><span data-stu-id="bd30e-167">How can I be moved to the new datacenter geo?</span></span>

<span data-ttu-id="bd30e-168">无法更改与租户关联的注册国家/地区。</span><span class="sxs-lookup"><span data-stu-id="bd30e-168">It is not possible to change the signup country associated with your tenant.</span></span> <span data-ttu-id="bd30e-169">相反，你需要使用新订阅创建新的 Microsoft 365 租户，并手动将用户和数据移动到新租户。</span><span class="sxs-lookup"><span data-stu-id="bd30e-169">Instead, you need to create a new Microsoft 365 tenant with a new subscription and manually move your users and data to the new tenant.</span></span>
  
## <a name="what-happens-if-we-are-in-process-of-email-data-migration-to-microsoft-365-during-the-exchange-online-move"></a><span data-ttu-id="bd30e-170">如果在 Exchange Online 移动期间我们正将电子邮件数据迁移到 Microsoft 365，会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="bd30e-170">What happens if we are in process of email data migration to Microsoft 365 during the Exchange Online move?</span></span>

<span data-ttu-id="bd30e-171">这是一种非常常见的方案，完全受支持。</span><span class="sxs-lookup"><span data-stu-id="bd30e-171">This is a very common scenario and is fully supported.</span></span>  <span data-ttu-id="bd30e-172">数据中心地理位置之间的云迁移不会干扰任何本地到云邮箱的迁移。</span><span class="sxs-lookup"><span data-stu-id="bd30e-172">Cloud migration between datacenter geos does not interfere with any on-premises to cloud mailbox migrations.</span></span>
  
 ## <a name="can-i-pilot-some-users"></a><span data-ttu-id="bd30e-173">能否试用某些用户？</span><span class="sxs-lookup"><span data-stu-id="bd30e-173">Can I pilot some users?</span></span>
  
<span data-ttu-id="bd30e-174">你可以创建单独的试用租户来测试连接，但无法以任何方式将试用租户与现有租户结合使用。</span><span class="sxs-lookup"><span data-stu-id="bd30e-174">You can create a separate trial tenant to test connectivity, but the trial tenant can't be combined in any way with your existing tenant.</span></span>

## <a name="i-dont-want-to-wait-for-microsoft-to-move-my-data-can-i-just-create-a-new-tenant-and-move-myself"></a><span data-ttu-id="bd30e-175">我不想等待 Microsoft 移动我的数据。</span><span class="sxs-lookup"><span data-stu-id="bd30e-175">I don't want to wait for Microsoft to move my data.</span></span> <span data-ttu-id="bd30e-176">我可以创建新租户并移动自己吗？</span><span class="sxs-lookup"><span data-stu-id="bd30e-176">Can I just create a new tenant and move myself?</span></span>
  
<span data-ttu-id="bd30e-177">可以，但该过程不会像 Microsoft 执行数据移动一样无缝。</span><span class="sxs-lookup"><span data-stu-id="bd30e-177">Yes, however the process will not be as seamless as if Microsoft were to perform the data move.</span></span>
  
<span data-ttu-id="bd30e-178">如果在新的数据中心地理位置可用后创建新租户，则新租户将托管在新地理位置中。</span><span class="sxs-lookup"><span data-stu-id="bd30e-178">If you create a new tenant after the new datacenter geo is available, the new tenant will be hosted in the new geo.</span></span> <span data-ttu-id="bd30e-179">此新租户与以前的租户完全分开，你应负责移动所有的用户邮箱、网站内容、域名和任何其他数据。</span><span class="sxs-lookup"><span data-stu-id="bd30e-179">This new tenant is completely separate from your previous tenant and you would be responsible for moving all user mailboxes, site content, domain names, and any other data.</span></span> <span data-ttu-id="bd30e-180">请注意，你无法将租户名称从一个租户移动到另一个租户。</span><span class="sxs-lookup"><span data-stu-id="bd30e-180">Note that you can't move the tenant name from one tenant to another.</span></span> <span data-ttu-id="bd30e-181">我们建议你等待 Microsoft 提供的移动计划，因为我们将负责移动用户的所有设置、数据和订阅。</span><span class="sxs-lookup"><span data-stu-id="bd30e-181">We recommend that you wait for the move program provided by Microsoft as we'll take care of moving all settings, data, and subscriptions for your users.</span></span>
  
## <a name="my-customer-data-has-already-been-moved-to-a-new-datacenter-geo-can-i-move-back"></a><span data-ttu-id="bd30e-182">我的客户数据已移动到新的数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="bd30e-182">My customer data has already been moved to a new datacenter geo.</span></span> <span data-ttu-id="bd30e-183">我能否后退？</span><span class="sxs-lookup"><span data-stu-id="bd30e-183">Can I move back?</span></span>
 
<span data-ttu-id="bd30e-184">否，这是不可能的。</span><span class="sxs-lookup"><span data-stu-id="bd30e-184">No, this is not possible.</span></span> <span data-ttu-id="bd30e-185">已移动到新地理位置数据中心的客户无法移回。</span><span class="sxs-lookup"><span data-stu-id="bd30e-185">Customers who have been moved to new geo datacenters cannot be moved back.</span></span> <span data-ttu-id="bd30e-186">作为任何地理位置的客户，你将体验与之前相同的服务质量、性能和安全控制。</span><span class="sxs-lookup"><span data-stu-id="bd30e-186">As a customer in any geo, you will experience the same quality of service, performance, and security controls as you did before.</span></span> <span data-ttu-id="bd30e-187">[Microsoft 365](https://aka.ms/multi-geo) 多地理位置作为加载项提供给一些客户，允许单个租户创建多个附属地理位置，并借助数据驻留承诺将用户数据移动到这些地理位置。</span><span class="sxs-lookup"><span data-stu-id="bd30e-187">[Microsoft 365 Multi Geo](https://aka.ms/multi-geo) is available to some customers as an add-on and lets a single tenant create multiple satellite geos and move user data to those geos with data residency commitments.</span></span>
  
## <a name="will-microsoft-365-tenants-hosted-in-the-new-datacenters-be-available-to-users-outside-of-the-country"></a><span data-ttu-id="bd30e-188">托管于新数据中心的 Microsoft 365 租户将可供美国以外的用户使用吗？</span><span class="sxs-lookup"><span data-stu-id="bd30e-188">Will Microsoft 365 tenants hosted in the new datacenters be available to users outside of the country?</span></span>
  
<span data-ttu-id="bd30e-189">是。</span><span class="sxs-lookup"><span data-stu-id="bd30e-189">Yes.</span></span> <span data-ttu-id="bd30e-190">Microsoft 维护了一个大型全球网络，其公共 Internet 连接位于全球 35 个国家/地区中的 130 多个位置，与超过 2，700 个 Internet 服务提供商 (ISP) 。</span><span class="sxs-lookup"><span data-stu-id="bd30e-190">Microsoft maintains a large global network with public Internet connections in more than 130 locations in 35 countries around the world with peering agreements with more than 2,700 Internet Service Providers (ISPs).</span></span> <span data-ttu-id="bd30e-191">用户将能够从 Internet 上任何位置访问数据中心。</span><span class="sxs-lookup"><span data-stu-id="bd30e-191">Users will be able to access the datacenters from wherever they are on the Internet.</span></span>

## <a name="my-tenant-has-configured-the-multi-geo-add-on-can-i-still-enroll-in-my-tenant-in-the-microsoft-365-move-program-to-change-my-default-geo-and-move-any-user-not-in-a-satellite-region-to-the-new-default-geo"></a><span data-ttu-id="bd30e-192">我的租户已配置 [多地理位置加载项](https://aka.ms/multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="bd30e-192">My tenant has configured the [Multi Geo add-on](https://aka.ms/multi-geo).</span></span> <span data-ttu-id="bd30e-193">我是否仍可以在 Microsoft 365 移动计划租户中注册以更改默认地理位置，以及将附属区域外的任何用户移动到新的默认地理位置？</span><span class="sxs-lookup"><span data-stu-id="bd30e-193">Can I still enroll in my tenant in the Microsoft 365 Move Program to change my default geo and move any user not in a satellite region to the new default geo?</span></span>

<span data-ttu-id="bd30e-194">可以，租户符合注册条件，但存在重要注意事项，因为已配置多地理位置的客户未完全支持租户级移动。</span><span class="sxs-lookup"><span data-stu-id="bd30e-194">Yes, your tenant is eligible to enroll but there are significant considerations as tenant-level move is not fully supported for customers that have configured Multi-Geo.</span></span>

<span data-ttu-id="bd30e-195">SharePoint Online 和 OneDrive for Business 无法通过此计划迁移到租户级别的新数据中心地理位置。</span><span class="sxs-lookup"><span data-stu-id="bd30e-195">SharePoint Online and OneDrive for Business cannot migrate to the new datacenter geo at the tenant level through this program.</span></span> <span data-ttu-id="bd30e-196">客户管理员可以将 OneDrive for Business 共享配置为使用多地理位置移动到任何可用区域，但在为租户配置多地理位置后，无法更改租户的默认位置。</span><span class="sxs-lookup"><span data-stu-id="bd30e-196">The customer administrator can configure OneDrive for Business shares to move to any available region using Multi-Geo, but the default location for the tenant cannot be changed once Multi-Geo has been configured for a tenant.</span></span>

<span data-ttu-id="bd30e-197">对于选择迁移的客户 - 我们会将当前默认地理位置的所有 Exchange Online 邮箱移动到新的本地数据中心地理位置，并更新默认 Exchange Online 区域。</span><span class="sxs-lookup"><span data-stu-id="bd30e-197">For customers that opt-in for migration - we will move all Exchange Online mailboxes from your current default geo to your new local datacenter geo and update the default Exchange Online region.</span></span> <span data-ttu-id="bd30e-198">我们不会移动在多地理位置附属区域配置的任何 EXO 邮箱，以继续根据预期遵守附属区域数据驻留。</span><span class="sxs-lookup"><span data-stu-id="bd30e-198">We will not move any EXO mailboxes configured in Multi Geo satellite regions to continue to respect satellite region data residency as you’ve intended.</span></span> 

## <a name="related-topics"></a><span data-ttu-id="bd30e-199">相关主题</span><span class="sxs-lookup"><span data-stu-id="bd30e-199">Related topics</span></span>

[<span data-ttu-id="bd30e-200">将核心数据移动到新的 Microsoft 365 数据中心地理位置</span><span class="sxs-lookup"><span data-stu-id="bd30e-200">Moving core data to new Microsoft 365 datacenter geos</span></span>](moving-data-to-new-datacenter-geos.md)

[<span data-ttu-id="bd30e-201">如何请求数据移动</span><span class="sxs-lookup"><span data-stu-id="bd30e-201">How to request your data move</span></span>](request-your-data-move.md)

[<span data-ttu-id="bd30e-202">Microsoft 365 多地理位置</span><span class="sxs-lookup"><span data-stu-id="bd30e-202">Microsoft 365 Multi Geo</span></span>](https://aka.ms/multi-geo)

[<span data-ttu-id="bd30e-203">Microsoft 365 交互式数据中心地图</span><span class="sxs-lookup"><span data-stu-id="bd30e-203">Microsoft 365 interactive datacenter map</span></span>](https://office.com/datamaps)

[<span data-ttu-id="bd30e-204">Microsoft 365 支持</span><span class="sxs-lookup"><span data-stu-id="bd30e-204">Microsoft 365 Support</span></span>](../admin/contact-support-for-business-products.md)

[<span data-ttu-id="bd30e-205">新的数据中心地理位置Microsoft Dynamics CRM Online</span><span class="sxs-lookup"><span data-stu-id="bd30e-205">New datacenter geos for Microsoft Dynamics CRM Online</span></span>](/power-platform/admin/new-datacenter-regions)
  
[<span data-ttu-id="bd30e-206">按区域表示的 Azure 服务</span><span class="sxs-lookup"><span data-stu-id="bd30e-206">Azure services by region</span></span>](https://azure.microsoft.com/regions/)