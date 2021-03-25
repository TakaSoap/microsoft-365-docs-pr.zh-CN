---
title: 与合作伙伴联系以存档第三方数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection: M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 了解如何设置自定义连接器以从数据源（如 Salesforce Chatter、Yahoo Messenger 或 Yammer）导入第三方数据。
ms.openlocfilehash: 6e93ff765129296f62b43c93937701169bbf4b03
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51164937"
---
# <a name="work-with-a-partner-to-archive-third-party-data"></a><span data-ttu-id="dcccb-103">与合作伙伴联系以存档第三方数据</span><span class="sxs-lookup"><span data-stu-id="dcccb-103">Work with a partner to archive third-party data</span></span>

<span data-ttu-id="dcccb-104">你可以与 Microsoft 合作伙伴合作，将第三方数据源的数据导入和存档到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dcccb-104">You can work with a Microsoft Partner to import and archive data from a third-party data source to Microsoft 365.</span></span> <span data-ttu-id="dcccb-105">合作伙伴可以为您提供一个自定义连接器，该连接器配置为定期从第三方数据源 (提取项目) 然后导入这些项目。</span><span class="sxs-lookup"><span data-stu-id="dcccb-105">A partner can provide you with a custom connector that is configured to extract items from the third-party data source (on a regular basis) and then import those items.</span></span> <span data-ttu-id="dcccb-106">合作伙伴连接器将项目的内容从数据源转换为电子邮件格式，然后将项目存储在邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dcccb-106">The partner connector converts the content of an item from the data source to an email message format and then stores the items in mailboxes.</span></span> <span data-ttu-id="dcccb-107">导入第三方数据后，可以将 Microsoft 365 合规性功能（如诉讼保留、电子数据展示、In-Place 存档、审核和 Microsoft 365 保留策略）应用于此数据。</span><span class="sxs-lookup"><span data-stu-id="dcccb-107">After third-party data is imported, you can apply Microsoft 365 compliance features such as Litigation Hold, eDiscovery, In-Place Archiving, Auditing, and Microsoft 365 retention policies to this data.</span></span>

>[!IMPORTANT]
><span data-ttu-id="dcccb-108">Microsoft [](communication-compliance.md) 365 中的通信合规性解决方案不能应用于本文中提到的合作伙伴连接器导入的第三方数据。</span><span class="sxs-lookup"><span data-stu-id="dcccb-108">The [Communication compliance](communication-compliance.md) solution in Microsoft 365 can't be applied to the third-party data imported by partner connectors mentioned in this article.</span></span> 

<span data-ttu-id="dcccb-109">下面概述了与 Microsoft 合作伙伴合作导入第三方数据所需的过程和步骤。</span><span class="sxs-lookup"><span data-stu-id="dcccb-109">Here's an overview of the process and the steps necessary to work with a Microsoft Partner to import third-party data.</span></span>

[<span data-ttu-id="dcccb-110">Step 1: Find a third-party data partner</span><span class="sxs-lookup"><span data-stu-id="dcccb-110">Step 1: Find a third-party data partner</span></span>](#step-1-find-a-third-party-data-partner)

[<span data-ttu-id="dcccb-111">步骤 2：创建和配置第三方数据邮箱</span><span class="sxs-lookup"><span data-stu-id="dcccb-111">Step 2: Create and configure a third-party data mailbox</span></span>](#step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365)

[<span data-ttu-id="dcccb-112">Step 3: Configure user mailboxes for third-party data</span><span class="sxs-lookup"><span data-stu-id="dcccb-112">Step 3: Configure user mailboxes for third-party data</span></span>](#step-3-configure-user-mailboxes-for-third-party-data)

[<span data-ttu-id="dcccb-113">步骤 4：为合作伙伴提供信息</span><span class="sxs-lookup"><span data-stu-id="dcccb-113">Step 4: Provide your partner with information</span></span>](#step-4-provide-your-partner-with-information)

[<span data-ttu-id="dcccb-114">步骤 5：在 Azure Active Directory 中注册第三方数据连接器</span><span class="sxs-lookup"><span data-stu-id="dcccb-114">Step 5: Register the third-party data connector in Azure Active Directory</span></span>](#step-5-register-the-third-party-data-connector-in-azure-active-directory)

## <a name="how-the-third-party-data-import-process-works"></a><span data-ttu-id="dcccb-115">第三方数据导入过程的工作原理</span><span class="sxs-lookup"><span data-stu-id="dcccb-115">How the third-party data import process works</span></span>

<span data-ttu-id="dcccb-116">下图和说明说明了与合作伙伴合作时第三方数据导入过程的工作方式。</span><span class="sxs-lookup"><span data-stu-id="dcccb-116">The following illustration and description explain how the third-party data import process works when working with a partner.</span></span>
  
![第三方数据导入过程的工作原理](../media/5d4cf8e9-b4cc-4547-90c8-d12d04a9f0e7.png)
  
1. <span data-ttu-id="dcccb-118">客户与所选择的合作伙伴合作，配置连接器，该连接器将提取第三方数据源中的项目，然后将这些项目导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dcccb-118">Customer works with their partner of choice to configure a connector that will extract items from the third-party data source and then import those items to Microsoft 365.</span></span>
    
2. <span data-ttu-id="dcccb-119">合作伙伴连接器通过计划或配置的第三方 API (连接到第三方数据源) 并从数据源中提取项目。</span><span class="sxs-lookup"><span data-stu-id="dcccb-119">The partner connector connects to third-party data sources via a third-party API (on a scheduled or as-configured basis) and extracts items from the data source.</span></span> <span data-ttu-id="dcccb-120">合作伙伴连接器将项目内容转换为电子邮件格式。</span><span class="sxs-lookup"><span data-stu-id="dcccb-120">The partner connector converts the content of an item to an email message format.</span></span> <span data-ttu-id="dcccb-121">有关 [邮件格式](#more-information) 架构的说明，请参阅详细信息部分。</span><span class="sxs-lookup"><span data-stu-id="dcccb-121">See the [More information](#more-information) section for a description of the message-format schema.</span></span> 
    
3. <span data-ttu-id="dcccb-122">合作伙伴连接器通过已知的终点使用 Exchange Web 服务 (EWS) 连接到 Microsoft 365 中的 Azure 服务。</span><span class="sxs-lookup"><span data-stu-id="dcccb-122">Partner connector connects to the Azure service in Microsoft 365 by using Exchange Web Service (EWS) via a well-known end point.</span></span>
    
4. <span data-ttu-id="dcccb-p103">项目便导入到特定用户的邮箱或“catch-all”第三方数据邮箱。无论项目是导入到特定用户邮箱还是第三方数据邮箱，都要基于以下条件：</span><span class="sxs-lookup"><span data-stu-id="dcccb-p103">Items are imported into the mailbox of a specific user or into a "catch-all" third-party data mailbox. Whether an item is imported into a specific user mailbox or to the third-party data mailbox is based on the following criteria:</span></span>
    
   1. <span data-ttu-id="dcccb-125">**具有与用户帐户对应的用户 ID 的项目：** 如果合作伙伴连接器可以将第三方数据源中项目的用户 ID 映射到 Microsoft 365 中的特定用户 ID，则该项目将复制到用户的"可恢复的项目"文件夹中的 **"** 清除"文件夹。</span><span class="sxs-lookup"><span data-stu-id="dcccb-125">**Items that have a user ID that corresponds to a user account:** If the partner connector can map the user ID of the item in the third-party data source to a specific user ID in Microsoft 365, the item is copied to the **Purges** folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="dcccb-126">用户无法访问“清除”文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="dcccb-126">Users can't access items in the Purges folder.</span></span> <span data-ttu-id="dcccb-127">但是，您可以使用电子数据展示工具搜索"清除"文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="dcccb-127">However, you can use eDiscovery tools to search for items in the Purges folder.</span></span>
    
   1. <span data-ttu-id="dcccb-128">**没有对应于用户帐户的用户 ID 的项目：** 如果合作伙伴连接器无法将项目的用户 ID 映射到特定用户 ID，该项目将复制到第三方数据邮箱的"收件箱"文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dcccb-128">**Items that don't have a user ID that corresponds to a user account:** If the partner connector can't map the user ID of an item to a specific user ID, the item is copied to the **Inbox** folder of the third-party data mailbox.</span></span> <span data-ttu-id="dcccb-129">将项目导入到收件箱允许您或组织中的其他人登录到第三方邮箱来查看和管理这些项目，并查看是否需要在合作伙伴连接器配置中进行任何调整。</span><span class="sxs-lookup"><span data-stu-id="dcccb-129">Importing items to the inbox allows you or someone in your organization to sign in to the third-party mailbox to view and manage these items, and see if any adjustments need to be made in the partner connector configuration.</span></span>
 
## <a name="step-1-find-a-third-party-data-partner"></a><span data-ttu-id="dcccb-130">步骤 1：寻找第三方数据合作伙伴</span><span class="sxs-lookup"><span data-stu-id="dcccb-130">Step 1: Find a third-party data partner</span></span>

<span data-ttu-id="dcccb-131">在 Microsoft 365 中存档第三方数据的关键组件是查找并与专门捕获来自第三方数据源的数据并导入到 Microsoft 365 的 Microsoft 合作伙伴合作。</span><span class="sxs-lookup"><span data-stu-id="dcccb-131">A key component for archiving third-party data in Microsoft 365 is finding and working with a Microsoft partner that specializes in capturing data from a third-party data source and importing it to Microsoft 365.</span></span> <span data-ttu-id="dcccb-132">导入数据后，可以将其与组织的其他 Microsoft 数据（如来自 Exchange 的电子邮件以及 SharePoint 和 OneDrive for Business 中的文档）一起存档和保留。</span><span class="sxs-lookup"><span data-stu-id="dcccb-132">After the data is imported, it can be archived and preserved along with your organization's other Microsoft data, such as email from Exchange and documents from SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="dcccb-133">合作伙伴创建一个连接器，从组织的第三方数据源 (如 BlackBerry、Facebook、Google+、Thomson Reuters、Twitter 和 YouTube) 中提取数据，并会将该数据传递给 Microsoft 365 API，以电子邮件方式将项目导入到 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="dcccb-133">A partner creates a connector that extracts data from your organization's third-party data sources (such as BlackBerry, Facebook, Google+, Thomson Reuters, Twitter, and YouTube) and passes that data to a Microsoft 365 API that imports items to Exchange mailboxes as email messages.</span></span>
  
<span data-ttu-id="dcccb-134">以下部分列出了 Microsoft 合作伙伴 (他们支持的第三方数据源) 参与 Microsoft 365 中存档第三方数据计划。</span><span class="sxs-lookup"><span data-stu-id="dcccb-134">The following sections list the Microsoft partners (and the third-party data sources they support) that are participating in the program for archiving third-party data in Microsoft 365.</span></span>

[<span data-ttu-id="dcccb-135">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="dcccb-135">17a-4 LLC</span></span>](#17a-4-llc)
  
[<span data-ttu-id="dcccb-136">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="dcccb-136">ArchiveSocial</span></span>](#archivesocial)
  
[<span data-ttu-id="dcccb-137">百里达</span><span class="sxs-lookup"><span data-stu-id="dcccb-137">Veritas</span></span>](#veritas)
  
[<span data-ttu-id="dcccb-138">OpenText</span><span class="sxs-lookup"><span data-stu-id="dcccb-138">OpenText</span></span>](#opentext)
  
[<span data-ttu-id="dcccb-139">Smarsh</span><span class="sxs-lookup"><span data-stu-id="dcccb-139">Smarsh</span></span>](#smarsh)

[<span data-ttu-id="dcccb-140">Verba</span><span class="sxs-lookup"><span data-stu-id="dcccb-140">Verba</span></span>](#verba)
  
### <a name="17a-4-llc"></a><span data-ttu-id="dcccb-141">17a-4 LLC</span><span class="sxs-lookup"><span data-stu-id="dcccb-141">17a-4 LLC</span></span>

<span data-ttu-id="dcccb-142">[17a-4 LLC](https://www.17a-4.com) 支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="dcccb-142">[17a-4 LLC](https://www.17a-4.com) supports the following third-party data sources:</span></span>
  
- <span data-ttu-id="dcccb-143">BlackBerry</span><span class="sxs-lookup"><span data-stu-id="dcccb-143">BlackBerry</span></span>
    
- <span data-ttu-id="dcccb-144">Bloomberg 数据流</span><span class="sxs-lookup"><span data-stu-id="dcccb-144">Bloomberg Data Streams</span></span>
    
- <span data-ttu-id="dcccb-145">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="dcccb-145">Cisco Jabber</span></span>
    
- <span data-ttu-id="dcccb-146">FactSet</span><span class="sxs-lookup"><span data-stu-id="dcccb-146">FactSet</span></span>
    
- <span data-ttu-id="dcccb-147">HipChat</span><span class="sxs-lookup"><span data-stu-id="dcccb-147">HipChat</span></span>
    
- <span data-ttu-id="dcccb-148">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="dcccb-148">InvestEdge</span></span>
    
- <span data-ttu-id="dcccb-149">LivePerson</span><span class="sxs-lookup"><span data-stu-id="dcccb-149">LivePerson</span></span>
    
- <span data-ttu-id="dcccb-150">MessageLabs 数据流</span><span class="sxs-lookup"><span data-stu-id="dcccb-150">MessageLabs Data Streams</span></span>
    
- <span data-ttu-id="dcccb-151">OpenText</span><span class="sxs-lookup"><span data-stu-id="dcccb-151">OpenText</span></span>
    
- <span data-ttu-id="dcccb-152">Oracle/ATG“单击以呼叫”Live 帮助</span><span class="sxs-lookup"><span data-stu-id="dcccb-152">Oracle/ATG 'click-to-call' Live Help</span></span>
    
- <span data-ttu-id="dcccb-153">Pivot IMTRADER</span><span class="sxs-lookup"><span data-stu-id="dcccb-153">Pivot IMTRADER</span></span>
    
- <span data-ttu-id="dcccb-154">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="dcccb-154">Microsoft SharePoint</span></span>
    
- <span data-ttu-id="dcccb-155">MindAlign</span><span class="sxs-lookup"><span data-stu-id="dcccb-155">MindAlign</span></span>
    
- <span data-ttu-id="dcccb-156">Sitrion One (Newsgator)</span><span class="sxs-lookup"><span data-stu-id="dcccb-156">Sitrion One (Newsgator)</span></span>
    
- <span data-ttu-id="dcccb-157">Skype for Business (Lync/OCS)</span><span class="sxs-lookup"><span data-stu-id="dcccb-157">Skype for Business (Lync/OCS)</span></span>
    
- <span data-ttu-id="dcccb-158">Skype for Business Online (Lync Online)</span><span class="sxs-lookup"><span data-stu-id="dcccb-158">Skype for Business Online (Lync Online)</span></span>
    
- <span data-ttu-id="dcccb-159">SQL 数据库</span><span class="sxs-lookup"><span data-stu-id="dcccb-159">SQL Databases</span></span>
    
- <span data-ttu-id="dcccb-160">Squawker</span><span class="sxs-lookup"><span data-stu-id="dcccb-160">Squawker</span></span>
    
- <span data-ttu-id="dcccb-161">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="dcccb-161">Thomson Reuters Eikon Messenger</span></span>
  

  
### <a name="archivesocial"></a><span data-ttu-id="dcccb-162">ArchiveSocial</span><span class="sxs-lookup"><span data-stu-id="dcccb-162">ArchiveSocial</span></span>

<span data-ttu-id="dcccb-163">[ArchiveSocial ](https://www.archivesocial.com) 支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="dcccb-163">[ArchiveSocial ](https://www.archivesocial.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="dcccb-164">Facebook</span><span class="sxs-lookup"><span data-stu-id="dcccb-164">Facebook</span></span>
    
- <span data-ttu-id="dcccb-165">Flickr</span><span class="sxs-lookup"><span data-stu-id="dcccb-165">Flickr</span></span>
    
- <span data-ttu-id="dcccb-166">Instagram</span><span class="sxs-lookup"><span data-stu-id="dcccb-166">Instagram</span></span>
    
- <span data-ttu-id="dcccb-167">领英</span><span class="sxs-lookup"><span data-stu-id="dcccb-167">LinkedIn</span></span>
    
- <span data-ttu-id="dcccb-168">Pinterest</span><span class="sxs-lookup"><span data-stu-id="dcccb-168">Pinterest</span></span>
    
- <span data-ttu-id="dcccb-169">Twitter</span><span class="sxs-lookup"><span data-stu-id="dcccb-169">Twitter</span></span>
    
- <span data-ttu-id="dcccb-170">YouTube</span><span class="sxs-lookup"><span data-stu-id="dcccb-170">YouTube</span></span>
    
- <span data-ttu-id="dcccb-171">Vimeo</span><span class="sxs-lookup"><span data-stu-id="dcccb-171">Vimeo</span></span>
  
### <a name="veritas"></a><span data-ttu-id="dcccb-172">百里达</span><span class="sxs-lookup"><span data-stu-id="dcccb-172">Veritas</span></span>

<span data-ttu-id="dcccb-173">[百](https://www.globanet.com) 年支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="dcccb-173">[Veritas](https://www.globanet.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="dcccb-174">使用 Pivot 客户端的 AOL</span><span class="sxs-lookup"><span data-stu-id="dcccb-174">AOL with Pivot Client</span></span> 
    
- <span data-ttu-id="dcccb-175">BlackBerry 呼叫日志（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="dcccb-175">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="dcccb-176">BlackBerry Messenger（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="dcccb-176">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="dcccb-177">BlackBerry PIN（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="dcccb-177">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="dcccb-178">BlackBerry 短信（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="dcccb-178">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="dcccb-179">Bloomberg 聊天</span><span class="sxs-lookup"><span data-stu-id="dcccb-179">Bloomberg Chat</span></span>
    
- <span data-ttu-id="dcccb-180">Bloomberg 邮件</span><span class="sxs-lookup"><span data-stu-id="dcccb-180">Bloomberg Mail</span></span>
    
- <span data-ttu-id="dcccb-181">Box</span><span class="sxs-lookup"><span data-stu-id="dcccb-181">Box</span></span>
    
- <span data-ttu-id="dcccb-182">适用于 Salesforce Chatter 的 CipherCloud</span><span class="sxs-lookup"><span data-stu-id="dcccb-182">CipherCloud for Salesforce Chatter</span></span>
    
- <span data-ttu-id="dcccb-183">Cisco IM &amp; Presence Server (v10、v10.5.1 SU1、v11.0、v11.5 SU2) </span><span class="sxs-lookup"><span data-stu-id="dcccb-183">Cisco IM &amp; Presence Server (v10, v10.5.1 SU1, v11.0, v11.5 SU2)</span></span>

- <span data-ttu-id="dcccb-184">Cisco Webex Teams</span><span class="sxs-lookup"><span data-stu-id="dcccb-184">Cisco Webex Teams</span></span>

- <span data-ttu-id="dcccb-185">Citrix Workspace &amp; ShareFile</span><span class="sxs-lookup"><span data-stu-id="dcccb-185">Citrix Workspace &amp; ShareFile</span></span>

- <span data-ttu-id="dcccb-186">CrowdCompass</span><span class="sxs-lookup"><span data-stu-id="dcccb-186">CrowdCompass</span></span>

- <span data-ttu-id="dcccb-187">自定义分隔的文本文件</span><span class="sxs-lookup"><span data-stu-id="dcccb-187">Custom-delimited text files</span></span>
    
- <span data-ttu-id="dcccb-188">自定义 XML 文件</span><span class="sxs-lookup"><span data-stu-id="dcccb-188">Custom XML files</span></span>
    
- <span data-ttu-id="dcccb-189">Facebook (页面) </span><span class="sxs-lookup"><span data-stu-id="dcccb-189">Facebook (Pages)</span></span>
    
- <span data-ttu-id="dcccb-190">Factset</span><span class="sxs-lookup"><span data-stu-id="dcccb-190">Factset</span></span>
    
- <span data-ttu-id="dcccb-191">FXConnect</span><span class="sxs-lookup"><span data-stu-id="dcccb-191">FXConnect</span></span>
    
- <span data-ttu-id="dcccb-192">ICE Chat/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="dcccb-192">ICE Chat/YellowJacket</span></span>
    
- <span data-ttu-id="dcccb-193">Jive</span><span class="sxs-lookup"><span data-stu-id="dcccb-193">Jive</span></span>
    
- <span data-ttu-id="dcccb-194">Macgregor XIP</span><span class="sxs-lookup"><span data-stu-id="dcccb-194">Macgregor XIP</span></span>

- <span data-ttu-id="dcccb-195">Microsoft Exchange Server</span><span class="sxs-lookup"><span data-stu-id="dcccb-195">Microsoft Exchange Server</span></span>
    
- <span data-ttu-id="dcccb-196">Microsoft OneDrive for Business</span><span class="sxs-lookup"><span data-stu-id="dcccb-196">Microsoft OneDrive for Business</span></span>

- <span data-ttu-id="dcccb-197">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="dcccb-197">Microsoft Teams</span></span>
       
- <span data-ttu-id="dcccb-198">Microsoft Yammer</span><span class="sxs-lookup"><span data-stu-id="dcccb-198">Microsoft Yammer</span></span>
    
- <span data-ttu-id="dcccb-199">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="dcccb-199">Mobile Guard</span></span>
    
- <span data-ttu-id="dcccb-200">透视</span><span class="sxs-lookup"><span data-stu-id="dcccb-200">Pivot</span></span>
    
- <span data-ttu-id="dcccb-201">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="dcccb-201">Salesforce Chatter</span></span>

- <span data-ttu-id="dcccb-202">Skype for Business Online</span><span class="sxs-lookup"><span data-stu-id="dcccb-202">Skype for Business Online</span></span>
    
- <span data-ttu-id="dcccb-203">Skype for Business，版本 2007 R2 - 2016（本地）</span><span class="sxs-lookup"><span data-stu-id="dcccb-203">Skype for Business, versions 2007 R2 - 2016 (on-premises)</span></span>
    
- <span data-ttu-id="dcccb-204">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="dcccb-204">Slack Enterprise Grid</span></span>
    
- <span data-ttu-id="dcccb-205">Symphony</span><span class="sxs-lookup"><span data-stu-id="dcccb-205">Symphony</span></span>
    
- <span data-ttu-id="dcccb-206">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="dcccb-206">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="dcccb-207">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="dcccb-207">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="dcccb-208">Thomson Reuters Dealings 3000 / FX Trading</span><span class="sxs-lookup"><span data-stu-id="dcccb-208">Thomson Reuters Dealings 3000 / FX Trading</span></span>
    
- <span data-ttu-id="dcccb-209">Twitter</span><span class="sxs-lookup"><span data-stu-id="dcccb-209">Twitter</span></span>
    
- <span data-ttu-id="dcccb-210">UBS 聊天</span><span class="sxs-lookup"><span data-stu-id="dcccb-210">UBS Chat</span></span>
    
- <span data-ttu-id="dcccb-211">YouTube</span><span class="sxs-lookup"><span data-stu-id="dcccb-211">YouTube</span></span>
  
### <a name="opentext"></a><span data-ttu-id="dcccb-212">OpenText</span><span class="sxs-lookup"><span data-stu-id="dcccb-212">OpenText</span></span>

<span data-ttu-id="dcccb-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) 支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="dcccb-213">[OpenText](https://www.opentext.com/what-we-do/products/opentext-product-offerings-catalog/rebranded-products/daegis) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="dcccb-214">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="dcccb-214">Axs Encrypted</span></span>
    
- <span data-ttu-id="dcccb-215">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="dcccb-215">Axs Exchange</span></span>
    
- <span data-ttu-id="dcccb-216">Axs 本地存档</span><span class="sxs-lookup"><span data-stu-id="dcccb-216">Axs Local Archive</span></span>
    
- <span data-ttu-id="dcccb-217">Axs PlaceHolder</span><span class="sxs-lookup"><span data-stu-id="dcccb-217">Axs PlaceHolder</span></span>
    
- <span data-ttu-id="dcccb-218">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="dcccb-218">Axs Signed</span></span>
    
- <span data-ttu-id="dcccb-219">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="dcccb-219">Bloomberg</span></span>
    
- <span data-ttu-id="dcccb-220">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="dcccb-220">Thomson Reuters</span></span>
  
### <a name="smarsh"></a><span data-ttu-id="dcccb-221">Smarsh</span><span class="sxs-lookup"><span data-stu-id="dcccb-221">Smarsh</span></span>

<span data-ttu-id="dcccb-222">[Smarsh](https://www.smarsh.com) 支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="dcccb-222">[Smarsh](https://www.smarsh.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="dcccb-223">AIM</span><span class="sxs-lookup"><span data-stu-id="dcccb-223">AIM</span></span>
    
- <span data-ttu-id="dcccb-224">American Idol</span><span class="sxs-lookup"><span data-stu-id="dcccb-224">American Idol</span></span>
    
- <span data-ttu-id="dcccb-225">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="dcccb-225">Apple Juice</span></span>
    
- <span data-ttu-id="dcccb-226">使用 Pivot 客户端的 AOL</span><span class="sxs-lookup"><span data-stu-id="dcccb-226">AOL with Pivot client</span></span>
    
- <span data-ttu-id="dcccb-227">Ares</span><span class="sxs-lookup"><span data-stu-id="dcccb-227">Ares</span></span>
    
- <span data-ttu-id="dcccb-228">Bazaar Voice</span><span class="sxs-lookup"><span data-stu-id="dcccb-228">Bazaar Voice</span></span>
    
- <span data-ttu-id="dcccb-229">Bear Share</span><span class="sxs-lookup"><span data-stu-id="dcccb-229">Bear Share</span></span>
    
- <span data-ttu-id="dcccb-230">Bit Torrent</span><span class="sxs-lookup"><span data-stu-id="dcccb-230">Bit Torrent</span></span>
    
- <span data-ttu-id="dcccb-231">BlackBerry 呼叫日志（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="dcccb-231">BlackBerry Call Logs (v5, v10, v12)</span></span>
    
- <span data-ttu-id="dcccb-232">BlackBerry Messenger（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="dcccb-232">BlackBerry Messenger (v5, v10, v12)</span></span>
    
- <span data-ttu-id="dcccb-233">BlackBerry PIN（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="dcccb-233">BlackBerry PIN (v5, v10, v12)</span></span>
    
- <span data-ttu-id="dcccb-234">BlackBerry 短信（v5、v10、v12）</span><span class="sxs-lookup"><span data-stu-id="dcccb-234">BlackBerry SMS (v5, v10, v12)</span></span>
    
- <span data-ttu-id="dcccb-235">Bloomberg 邮件</span><span class="sxs-lookup"><span data-stu-id="dcccb-235">Bloomberg Mail</span></span>
    
- <span data-ttu-id="dcccb-236">CellTrust</span><span class="sxs-lookup"><span data-stu-id="dcccb-236">CellTrust</span></span>
    
- <span data-ttu-id="dcccb-237">Chat Import</span><span class="sxs-lookup"><span data-stu-id="dcccb-237">Chat Import</span></span>
    
- <span data-ttu-id="dcccb-238">聊天实时日志记录和策略</span><span class="sxs-lookup"><span data-stu-id="dcccb-238">Chat Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="dcccb-239">Chatter</span><span class="sxs-lookup"><span data-stu-id="dcccb-239">Chatter</span></span>
    
- <span data-ttu-id="dcccb-240">Cisco IM &amp; Presence Server (v9.0.1、v9.1、v9.1.1 SU1、v10、v10.5.1 SU1) </span><span class="sxs-lookup"><span data-stu-id="dcccb-240">Cisco IM &amp; Presence Server (v9.0.1, v9.1, v9.1.1 SU1, v10, v10.5.1 SU1)</span></span>
    
- <span data-ttu-id="dcccb-241">Cisco Unified Presence 服务器（v8.6.3、v8.6.4、v8.6.5）</span><span class="sxs-lookup"><span data-stu-id="dcccb-241">Cisco Unified Presence Server (v8.6.3, v8.6.4, v8.6.5)</span></span>
    
- <span data-ttu-id="dcccb-242">协作导入</span><span class="sxs-lookup"><span data-stu-id="dcccb-242">Collaboration Import</span></span>
    
- <span data-ttu-id="dcccb-243">协作实时日志记录</span><span class="sxs-lookup"><span data-stu-id="dcccb-243">Collaboration Real Time Logging</span></span>
    
- <span data-ttu-id="dcccb-244">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="dcccb-244">Direct Connect</span></span>
    
- <span data-ttu-id="dcccb-245">Facebook</span><span class="sxs-lookup"><span data-stu-id="dcccb-245">Facebook</span></span>
    
- <span data-ttu-id="dcccb-246">FactSet</span><span class="sxs-lookup"><span data-stu-id="dcccb-246">FactSet</span></span>
    
- <span data-ttu-id="dcccb-247">FastTrack</span><span class="sxs-lookup"><span data-stu-id="dcccb-247">FastTrack</span></span>
    
- <span data-ttu-id="dcccb-248">符合该规范的</span><span class="sxs-lookup"><span data-stu-id="dcccb-248">Gnutella</span></span>
    
- <span data-ttu-id="dcccb-249">Google+</span><span class="sxs-lookup"><span data-stu-id="dcccb-249">Google+</span></span>
    
- <span data-ttu-id="dcccb-250">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="dcccb-250">GoToMyPC</span></span>
    
- <span data-ttu-id="dcccb-251">Hopster</span><span class="sxs-lookup"><span data-stu-id="dcccb-251">Hopster</span></span>
    
- <span data-ttu-id="dcccb-252">HubConnex</span><span class="sxs-lookup"><span data-stu-id="dcccb-252">HubConnex</span></span>
    
- <span data-ttu-id="dcccb-253">IBM Connections（v3.0.1、v4.0、v4.5、v4.5 CR3、v5）</span><span class="sxs-lookup"><span data-stu-id="dcccb-253">IBM Connections (v3.0.1, v4.0, v4.5, v4.5 CR3, v5)</span></span>
    
- <span data-ttu-id="dcccb-254">IBM Connections Chat Cloud</span><span class="sxs-lookup"><span data-stu-id="dcccb-254">IBM Connections Chat Cloud</span></span>
    
- <span data-ttu-id="dcccb-255">IBM Connections Social Cloud</span><span class="sxs-lookup"><span data-stu-id="dcccb-255">IBM Connections Social Cloud</span></span>
    
- <span data-ttu-id="dcccb-256">IBM SameTime Advanced 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="dcccb-256">IBM SameTime Advanced 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="dcccb-257">IBM SameTime Communicate 9.0</span><span class="sxs-lookup"><span data-stu-id="dcccb-257">IBM SameTime Communicate 9.0</span></span>
    
- <span data-ttu-id="dcccb-258">IBM SameTime Community (v8.0.2、v8.5.1 IFR2、v8.5.2 IFR1、v9.1)</span><span class="sxs-lookup"><span data-stu-id="dcccb-258">IBM SameTime Community (v8.0.2, v8.5.1 IFR2, v8.5.2 IFR1, v9.1)</span></span>
    
- <span data-ttu-id="dcccb-259">IBM SameTime Complete 9.0</span><span class="sxs-lookup"><span data-stu-id="dcccb-259">IBM SameTime Complete 9.0</span></span>
    
- <span data-ttu-id="dcccb-260">IBM SameTime Conference 9.0</span><span class="sxs-lookup"><span data-stu-id="dcccb-260">IBM SameTime Conference 9.0</span></span>
    
- <span data-ttu-id="dcccb-261">IBM SameTime Meeting 8.5.2 IFR1</span><span class="sxs-lookup"><span data-stu-id="dcccb-261">IBM SameTime Meeting 8.5.2 IFR1</span></span>
    
- <span data-ttu-id="dcccb-262">ICE/YellowJacket</span><span class="sxs-lookup"><span data-stu-id="dcccb-262">ICE/YellowJacket</span></span>
    
- <span data-ttu-id="dcccb-263">即时消息导入</span><span class="sxs-lookup"><span data-stu-id="dcccb-263">IM Import</span></span>
    
- <span data-ttu-id="dcccb-264">即时消息实时日志记录和策略</span><span class="sxs-lookup"><span data-stu-id="dcccb-264">IM Real Time Logging and Policy</span></span>
    
- <span data-ttu-id="dcccb-265">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="dcccb-265">Indii Messenger</span></span>
    
- <span data-ttu-id="dcccb-266">即时 Bloomberg</span><span class="sxs-lookup"><span data-stu-id="dcccb-266">Instant Bloomberg</span></span>
    
- <span data-ttu-id="dcccb-267">IRC</span><span class="sxs-lookup"><span data-stu-id="dcccb-267">IRC</span></span>
    
- <span data-ttu-id="dcccb-268">Jive</span><span class="sxs-lookup"><span data-stu-id="dcccb-268">Jive</span></span>
    
- <span data-ttu-id="dcccb-269">Jive 6 实时日志记录（v6、v7）</span><span class="sxs-lookup"><span data-stu-id="dcccb-269">Jive 6 Real Time Logging (v6, v7)</span></span>
    
- <span data-ttu-id="dcccb-270">Jive 导入</span><span class="sxs-lookup"><span data-stu-id="dcccb-270">Jive Import</span></span>
    
- <span data-ttu-id="dcccb-271">JXTA</span><span class="sxs-lookup"><span data-stu-id="dcccb-271">JXTA</span></span>
    
- <span data-ttu-id="dcccb-272">领英</span><span class="sxs-lookup"><span data-stu-id="dcccb-272">LinkedIn</span></span>
    
- <span data-ttu-id="dcccb-273">Microsoft Lync（2010、2013）</span><span class="sxs-lookup"><span data-stu-id="dcccb-273">Microsoft Lync (2010, 2013)</span></span>
    
- <span data-ttu-id="dcccb-274">MFTP</span><span class="sxs-lookup"><span data-stu-id="dcccb-274">MFTP</span></span>
    
- <span data-ttu-id="dcccb-275">Microsoft Lync 2013 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-275">Microsoft Lync 2013 Voice</span></span>
    
- <span data-ttu-id="dcccb-276">Microsoft SharePoint（2010、2013）</span><span class="sxs-lookup"><span data-stu-id="dcccb-276">Microsoft SharePoint (2010, 2013)</span></span>
    
- <span data-ttu-id="dcccb-277">Microsoft SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="dcccb-277">Microsoft SharePoint Online</span></span>
    
- <span data-ttu-id="dcccb-278">Microsoft UC（统一通信）</span><span class="sxs-lookup"><span data-stu-id="dcccb-278">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="dcccb-279">MindAlign</span><span class="sxs-lookup"><span data-stu-id="dcccb-279">MindAlign</span></span>
    
- <span data-ttu-id="dcccb-280">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="dcccb-280">Mobile Guard</span></span>
    
- <span data-ttu-id="dcccb-281">MSN</span><span class="sxs-lookup"><span data-stu-id="dcccb-281">MSN</span></span>
    
- <span data-ttu-id="dcccb-282">My Space</span><span class="sxs-lookup"><span data-stu-id="dcccb-282">My Space</span></span>
    
- <span data-ttu-id="dcccb-283">完成</span><span class="sxs-lookup"><span data-stu-id="dcccb-283">NEONetwork</span></span>
    
- <span data-ttu-id="dcccb-284">Microsoft 365 Lync Dedicated</span><span class="sxs-lookup"><span data-stu-id="dcccb-284">Microsoft 365 Lync Dedicated</span></span>
    
- <span data-ttu-id="dcccb-285">Microsoft 365 共享 IM</span><span class="sxs-lookup"><span data-stu-id="dcccb-285">Microsoft 365 Shared IM</span></span>
    
- <span data-ttu-id="dcccb-286">Pinterest</span><span class="sxs-lookup"><span data-stu-id="dcccb-286">Pinterest</span></span>
    
- <span data-ttu-id="dcccb-287">透视</span><span class="sxs-lookup"><span data-stu-id="dcccb-287">Pivot</span></span>
    
- <span data-ttu-id="dcccb-288">QQ</span><span class="sxs-lookup"><span data-stu-id="dcccb-288">QQ</span></span>
    
- <span data-ttu-id="dcccb-289">Skype for Business 2015</span><span class="sxs-lookup"><span data-stu-id="dcccb-289">Skype for Business 2015</span></span>
    
- <span data-ttu-id="dcccb-290">SoftEther</span><span class="sxs-lookup"><span data-stu-id="dcccb-290">SoftEther</span></span>
    
- <span data-ttu-id="dcccb-291">Symphony</span><span class="sxs-lookup"><span data-stu-id="dcccb-291">Symphony</span></span>
    
- <span data-ttu-id="dcccb-292">Thomson Reuters Eikon</span><span class="sxs-lookup"><span data-stu-id="dcccb-292">Thomson Reuters Eikon</span></span>
    
- <span data-ttu-id="dcccb-293">Thomson Reuters Messenger</span><span class="sxs-lookup"><span data-stu-id="dcccb-293">Thomson Reuters Messenger</span></span>
    
- <span data-ttu-id="dcccb-294">Tor</span><span class="sxs-lookup"><span data-stu-id="dcccb-294">Tor</span></span>
    
- <span data-ttu-id="dcccb-295">TTT</span><span class="sxs-lookup"><span data-stu-id="dcccb-295">TTT</span></span>
    
- <span data-ttu-id="dcccb-296">Twitter</span><span class="sxs-lookup"><span data-stu-id="dcccb-296">Twitter</span></span>
    
- <span data-ttu-id="dcccb-297">WinMX</span><span class="sxs-lookup"><span data-stu-id="dcccb-297">WinMX</span></span>
    
- <span data-ttu-id="dcccb-298">Winny</span><span class="sxs-lookup"><span data-stu-id="dcccb-298">Winny</span></span>
    
- <span data-ttu-id="dcccb-299">Yahoo</span><span class="sxs-lookup"><span data-stu-id="dcccb-299">Yahoo</span></span>
    
- <span data-ttu-id="dcccb-300">Yammer</span><span class="sxs-lookup"><span data-stu-id="dcccb-300">Yammer</span></span>
    
- <span data-ttu-id="dcccb-301">YouTube</span><span class="sxs-lookup"><span data-stu-id="dcccb-301">YouTube</span></span>
    

### <a name="verba"></a><span data-ttu-id="dcccb-302">Verba</span><span class="sxs-lookup"><span data-stu-id="dcccb-302">Verba</span></span>

<span data-ttu-id="dcccb-303">[Verba](https://www.verba.com) 支持以下第三方数据源：</span><span class="sxs-lookup"><span data-stu-id="dcccb-303">[Verba](https://www.verba.com) supports the following third-party data sources:</span></span> 
  
- <span data-ttu-id="dcccb-304">Avaya Aura 视频</span><span class="sxs-lookup"><span data-stu-id="dcccb-304">Avaya Aura Video</span></span>
    
- <span data-ttu-id="dcccb-305">Avaya Aura 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-305">Avaya Aura Voice</span></span>
    
- <span data-ttu-id="dcccb-306">Avtec 调频广播</span><span class="sxs-lookup"><span data-stu-id="dcccb-306">Avtec Radio</span></span>
    
- <span data-ttu-id="dcccb-307">Bosch/Telex 调频广播</span><span class="sxs-lookup"><span data-stu-id="dcccb-307">Bosch/Telex Radio</span></span>
    
- <span data-ttu-id="dcccb-308">BroadSoft 视频</span><span class="sxs-lookup"><span data-stu-id="dcccb-308">BroadSoft Video</span></span>
    
- <span data-ttu-id="dcccb-309">BroadSoft 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-309">BroadSoft Voice</span></span>
    
- <span data-ttu-id="dcccb-310">Centile 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-310">Centile Voice</span></span>
    
- <span data-ttu-id="dcccb-311">Cisco Jabber 即时消息</span><span class="sxs-lookup"><span data-stu-id="dcccb-311">Cisco Jabber IM</span></span>
    
- <span data-ttu-id="dcccb-312">Cisco UC 视频</span><span class="sxs-lookup"><span data-stu-id="dcccb-312">Cisco UC Video</span></span>
    
- <span data-ttu-id="dcccb-313">Cisco UC 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-313">Cisco UC Voice</span></span>
    
- <span data-ttu-id="dcccb-314">Cisco UCCX/UCCE 视频</span><span class="sxs-lookup"><span data-stu-id="dcccb-314">Cisco UCCX/UCCE Video</span></span>
    
- <span data-ttu-id="dcccb-315">Cisco UCCX/UCCE 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-315">Cisco UCCX/UCCE Voice</span></span>
    
- <span data-ttu-id="dcccb-316">ESChat 调频广播</span><span class="sxs-lookup"><span data-stu-id="dcccb-316">ESChat Radio</span></span>
    
- <span data-ttu-id="dcccb-317">Geoman 联络专家</span><span class="sxs-lookup"><span data-stu-id="dcccb-317">Geoman Contact Expert</span></span>
    
- <span data-ttu-id="dcccb-318">IP Trade 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-318">IP Trade Voice</span></span>
    
- <span data-ttu-id="dcccb-319">Luware LUCS 联络中心</span><span class="sxs-lookup"><span data-stu-id="dcccb-319">Luware LUCS Contact Center</span></span>
    
- <span data-ttu-id="dcccb-320">Microsoft UC（统一通信）</span><span class="sxs-lookup"><span data-stu-id="dcccb-320">Microsoft UC (Unified Communications)</span></span>
    
- <span data-ttu-id="dcccb-321">适用于 Lync 的 Mitel MiContact 中心 (prairieFyre)</span><span class="sxs-lookup"><span data-stu-id="dcccb-321">Mitel MiContact Center for Lync (prairieFyre)</span></span>
    
- <span data-ttu-id="dcccb-322">Oracle / Acme 数据包会话边界控制器视频</span><span class="sxs-lookup"><span data-stu-id="dcccb-322">Oracle / Acme Packet Session Border Controller Video</span></span>
    
- <span data-ttu-id="dcccb-323">Oracle / Acme 数据包会话边界控制器语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-323">Oracle / Acme Packet Session Border Controller Voice</span></span>
    
- <span data-ttu-id="dcccb-324">Singtel Mobile 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-324">Singtel Mobile Voice</span></span>
    
- <span data-ttu-id="dcccb-325">SIPREC 视频</span><span class="sxs-lookup"><span data-stu-id="dcccb-325">SIPREC Video</span></span>
    
-  <span data-ttu-id="dcccb-326">SIPREC 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-326">SIPREC Voice</span></span> 
    
- <span data-ttu-id="dcccb-327">Skype for Business/Lync 即时消息</span><span class="sxs-lookup"><span data-stu-id="dcccb-327">Skype for Business / Lync IM</span></span>
    
- <span data-ttu-id="dcccb-328">Skype for Business/Lync 视频</span><span class="sxs-lookup"><span data-stu-id="dcccb-328">Skype for Business / Lync Video</span></span>
    
- <span data-ttu-id="dcccb-329">Skype for Business/Lync 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-329">Skype for Business / Lync Voice</span></span>
    
- <span data-ttu-id="dcccb-330">Speakerbus 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-330">Speakerbus Voice</span></span>
    
- <span data-ttu-id="dcccb-331">标准 SIP/H.323 视频</span><span class="sxs-lookup"><span data-stu-id="dcccb-331">Standard SIP/H.323 Video</span></span>
    
- <span data-ttu-id="dcccb-332">标准 SIP/H.323 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-332">Standard SIP/H.323 Voice</span></span>
    
- <span data-ttu-id="dcccb-333">Truphone 语音</span><span class="sxs-lookup"><span data-stu-id="dcccb-333">Truphone Voice</span></span>
    
- <span data-ttu-id="dcccb-334">TwistedPair 调频广播</span><span class="sxs-lookup"><span data-stu-id="dcccb-334">TwistedPair Radio</span></span>
    
- <span data-ttu-id="dcccb-335">Windows 桌面计算机屏幕</span><span class="sxs-lookup"><span data-stu-id="dcccb-335">Windows Desktop Computer Screen</span></span>
  
## <a name="step-2-create-and-configure-a-third-party-data-mailbox-in-microsoft-365"></a><span data-ttu-id="dcccb-336">步骤 2：在 Microsoft 365 中创建和配置第三方数据邮箱</span><span class="sxs-lookup"><span data-stu-id="dcccb-336">Step 2: Create and configure a third-party data mailbox in Microsoft 365</span></span>

<span data-ttu-id="dcccb-337">以下是创建和配置第三方数据邮箱以将数据导入到 Microsoft 365 的步骤。</span><span class="sxs-lookup"><span data-stu-id="dcccb-337">Here are the steps for creating and configuring a third-party data mailbox for importing data to Microsoft 365.</span></span> <span data-ttu-id="dcccb-338">如上所述，如果合作伙伴连接器无法将项目的用户 ID 映射到用户帐户，则项目将导入到此邮箱。</span><span class="sxs-lookup"><span data-stu-id="dcccb-338">As previous explained, items are imported to this mailbox if the partner connector can't map the user ID of the item to a user account.</span></span>
  
 <span data-ttu-id="dcccb-339">**在 Microsoft 365 管理中心完成这些任务**</span><span class="sxs-lookup"><span data-stu-id="dcccb-339">**Complete these tasks in the Microsoft 365 admin center**</span></span>
  
1. <span data-ttu-id="dcccb-340">创建用户帐户并为其分配 Exchange Online 计划 2 许可证;请参阅[将用户添加到 Microsoft 365。](../admin/add-users/add-users.md)</span><span class="sxs-lookup"><span data-stu-id="dcccb-340">Create a user account and assign it an Exchange Online Plan 2 license; see [Add users to Microsoft 365](../admin/add-users/add-users.md).</span></span> <span data-ttu-id="dcccb-341">若要将邮箱置于诉讼保留状态或启用具有无限存储配额的存档邮箱，需要计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="dcccb-341">A Plan 2 license is required to place the mailbox on Litigation Hold or enable an archive mailbox that has an unlimited storage quota.</span></span>
    
2. <span data-ttu-id="dcccb-342">将第三方数据邮箱的用户帐户添加到 Microsoft 365 中的 **Exchange** 管理员管理员角色;请参阅 [在 Microsoft 365 中分配管理员角色](../admin/add-users/assign-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="dcccb-342">Add the user account for the third-party data mailbox to the **Exchange administrator** admin role in Microsoft 365; see [Assign admin roles in Microsoft 365](../admin/add-users/assign-admin-roles.md).</span></span>
    
    > [!TIP]
    > <span data-ttu-id="dcccb-343">写下此用户帐户的凭据。</span><span class="sxs-lookup"><span data-stu-id="dcccb-343">Write down the credentials for this user account.</span></span> <span data-ttu-id="dcccb-344">您需要将它们提供给您的合作伙伴，如步骤 4 中所述。</span><span class="sxs-lookup"><span data-stu-id="dcccb-344">You need to provide them to your partner, as described in Step 4.</span></span> 
  
 <span data-ttu-id="dcccb-345">**在 Exchange 管理中心完成这些任务**</span><span class="sxs-lookup"><span data-stu-id="dcccb-345">**Complete these tasks in the Exchange admin center**</span></span>
  
1. <span data-ttu-id="dcccb-346">在组织的通讯簿和其他地址列表中隐藏第三方数据邮箱;请参阅 [管理用户邮箱](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes)。</span><span class="sxs-lookup"><span data-stu-id="dcccb-346">Hide the third-party data mailbox from the address book and other address lists in your organization; see [Manage user mailboxes](/exchange/recipients-in-exchange-online/manage-user-mailboxes/manage-user-mailboxes).</span></span> <span data-ttu-id="dcccb-347">或者，可以运行以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="dcccb-347">Alternatively, you can run the following PowerShell command:</span></span>
    
    ```powershell
    Set-Mailbox -Identity <identity of third-party data mailbox> -HiddenFromAddressListsEnabled $true
    ```

2. <span data-ttu-id="dcccb-348">为第三方数据邮箱分配 **FullAccess** 权限，以便管理员或合规部官员可以在 Outlook 桌面客户端中打开第三方数据邮箱;请参阅 [管理收件人的权限](https://go.microsoft.com/fwlink/p/?LinkId=692104)。</span><span class="sxs-lookup"><span data-stu-id="dcccb-348">Assign the **FullAccess** permission to the third-party data mailbox so that administrators or compliance officers can open the third-party data mailbox in the Outlook desktop client; see [Manage permissions for recipients](https://go.microsoft.com/fwlink/p/?LinkId=692104).</span></span>
    
3. <span data-ttu-id="dcccb-349">为第三方数据邮箱启用以下合规性相关功能：</span><span class="sxs-lookup"><span data-stu-id="dcccb-349">Enable the following compliance-related features for the third-party data mailbox:</span></span>
    
    - <span data-ttu-id="dcccb-350">启用存档邮箱;请参阅[启用存档邮箱和](enable-archive-mailboxes.md)[启用无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="dcccb-350">Enable the archive mailbox; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span> <span data-ttu-id="dcccb-351">这样，您通过设置存档策略（将第三方数据项目移动到存档邮箱）释放主邮箱中的存储空间。</span><span class="sxs-lookup"><span data-stu-id="dcccb-351">This lets you free-up storage space in the primary mailbox by setting up an archive policy that moves third-party data items to the archive mailbox.</span></span> <span data-ttu-id="dcccb-352">这将为第三方数据提供无限制的存储。</span><span class="sxs-lookup"><span data-stu-id="dcccb-352">This provides you with unlimited storage for third-party data.</span></span>
    
    - <span data-ttu-id="dcccb-353">将第三方数据邮箱置于诉讼保留的位置。</span><span class="sxs-lookup"><span data-stu-id="dcccb-353">Place the third-party data mailbox on Litigation Hold.</span></span> <span data-ttu-id="dcccb-354">还可以在安全与合规中心应用 Microsoft 365 保留策略。</span><span class="sxs-lookup"><span data-stu-id="dcccb-354">You can also apply a Microsoft 365 retention policy in the security and compliance center.</span></span> <span data-ttu-id="dcccb-355">保留此邮箱会无限期保留第三 (或保留指定的持续时间) 并阻止从邮箱中清除它们。</span><span class="sxs-lookup"><span data-stu-id="dcccb-355">Placing this mailbox on hold retains third-party data items (indefinitely or for a specified duration) and prevent them from being purged from the mailbox.</span></span> <span data-ttu-id="dcccb-356">请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="dcccb-356">See one of the following topics:</span></span>
    
      - [<span data-ttu-id="dcccb-357">将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="dcccb-357">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)
    
      - [<span data-ttu-id="dcccb-358">了解保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="dcccb-358">Learn about retention policies and retention labels</span></span>](retention.md)
    
    - <span data-ttu-id="dcccb-359">为所有者、代理人和第三方数据邮箱的管理员访问权限启用邮箱审核日志记录;请参阅 [启用邮箱审核](enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="dcccb-359">Enable mailbox audit logging for owner, delegate, and admin access to the third-party data mailbox; see [Enable mailbox auditing](enable-mailbox-auditing.md).</span></span> <span data-ttu-id="dcccb-360">这允许您审核有权访问第三方数据邮箱的任何用户执行的所有活动。</span><span class="sxs-lookup"><span data-stu-id="dcccb-360">This allows you to audit all activity performed by any user who has access to the third-party data mailbox.</span></span>

## <a name="step-3-configure-user-mailboxes-for-third-party-data"></a><span data-ttu-id="dcccb-361">步骤 3：为第三方数据配置用户邮箱</span><span class="sxs-lookup"><span data-stu-id="dcccb-361">Step 3: Configure user mailboxes for third-party data</span></span>

<span data-ttu-id="dcccb-362">下一步是配置用户邮箱以支持第三方数据。</span><span class="sxs-lookup"><span data-stu-id="dcccb-362">The next step is to configure user mailboxes to support third-party data.</span></span> <span data-ttu-id="dcccb-363">使用 Exchange 管理中心或相应的 cmdlet 完成这些任务Windows PowerShell cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dcccb-363">Complete these tasks by using the Exchange admin center or by using the corresponding Windows PowerShell cmdlets.</span></span>
  
1. <span data-ttu-id="dcccb-364">为每个用户启用存档邮箱;请参阅[启用存档邮箱和](enable-archive-mailboxes.md)[启用无限制存档](enable-unlimited-archiving.md)。</span><span class="sxs-lookup"><span data-stu-id="dcccb-364">Enable the archive mailbox for each user; see [Enable archive mailboxes](enable-archive-mailboxes.md) and [Enable unlimited archiving](enable-unlimited-archiving.md).</span></span>
    
2. <span data-ttu-id="dcccb-365">将用户邮箱置于诉讼保留或应用 Microsoft 365 保留策略;请参阅下列主题之一：</span><span class="sxs-lookup"><span data-stu-id="dcccb-365">Place user mailboxes on Litigation Hold or apply a Microsoft 365 retention policy; see one of the following topics:</span></span> 
    
    - [<span data-ttu-id="dcccb-366">将邮箱置于诉讼保留状态</span><span class="sxs-lookup"><span data-stu-id="dcccb-366">Place a mailbox on Litigation Hold</span></span>](./create-a-litigation-hold.md)
    
    - [<span data-ttu-id="dcccb-367">了解保留策略和保留标签</span><span class="sxs-lookup"><span data-stu-id="dcccb-367">Learn about retention policies and retention labels</span></span>](retention.md)
    
    <span data-ttu-id="dcccb-368">如前所述，在将邮箱置于保留时，您可以设置保留第三方数据源中项目的时长，或者也可以选择无限期保留这些项目。</span><span class="sxs-lookup"><span data-stu-id="dcccb-368">As previously stated, when you place mailboxes on hold, you can set a duration for how long to hold items from the third-party data source or you can choose to hold items indefinitely.</span></span>

## <a name="step-4-provide-your-partner-with-information"></a><span data-ttu-id="dcccb-369">步骤 4：为合作伙伴提供信息</span><span class="sxs-lookup"><span data-stu-id="dcccb-369">Step 4: Provide your partner with information</span></span>

<span data-ttu-id="dcccb-370">最后一步是向合作伙伴提供以下信息，以便他们可以配置连接器以连接到您的组织以将数据导入到用户邮箱和第三方数据邮箱。</span><span class="sxs-lookup"><span data-stu-id="dcccb-370">The final step is to provide your partner with the following information so they can configure the connector to connect to your organization to import data to user mailboxes and to the third-party data mailbox.</span></span> 
  
- <span data-ttu-id="dcccb-371">用于连接到 Microsoft 365 中的 Azure 服务的终结点：</span><span class="sxs-lookup"><span data-stu-id="dcccb-371">The endpoint used to connect to the Azure service in Microsoft 365:</span></span>

    ```http
    https://office365ingestionsvc.gble1.protection.outlook.com/service/ThirdPartyIngestionService.svc
    ```

- <span data-ttu-id="dcccb-372">Microsoft 365 (365 用户 ID 和密码) 步骤 2 中创建的第三方数据邮箱的登录凭据。</span><span class="sxs-lookup"><span data-stu-id="dcccb-372">The sign-in credentials (Microsoft 365 user ID and password) of the third-party data mailbox that you created in Step 2.</span></span> <span data-ttu-id="dcccb-373">这些凭据是必需的，以便合作伙伴连接器可以访问并将项目导入用户邮箱和第三方数据邮箱。</span><span class="sxs-lookup"><span data-stu-id="dcccb-373">These credentials are required so that the partner connector can access and import items to user mailboxes and to the third-party data mailbox.</span></span>
 
## <a name="step-5-register-the-third-party-data-connector-in-azure-active-directory"></a><span data-ttu-id="dcccb-374">步骤 5：在 Azure Active Directory 中注册第三方数据连接器</span><span class="sxs-lookup"><span data-stu-id="dcccb-374">Step 5: Register the third-party data connector in Azure Active Directory</span></span>

<span data-ttu-id="dcccb-375">从 2018 年 9 月 30 开始，Microsoft 365 中的 Azure 服务将开始使用 Exchange Online 中的新式验证来验证尝试连接到组织以导入数据的第三方数据连接器。</span><span class="sxs-lookup"><span data-stu-id="dcccb-375">Starting September 30, 2018, the Azure service in Microsoft 365 will begin using modern authentication in Exchange Online to authenticate third-party data connectors that attempt to connect to your organization to import data.</span></span> <span data-ttu-id="dcccb-376">进行此更改的原因是，新式身份验证提供比当前方法更多的安全性，当前方法基于使用前面所述的终结点连接到 Azure 服务的第三方连接器的允许列表。</span><span class="sxs-lookup"><span data-stu-id="dcccb-376">The reason for this change is that modern authentication provides more security than the current method, which was based on an allow list for third-party connectors that use the previously described endpoint to connect to the Azure service.</span></span>

<span data-ttu-id="dcccb-377">若要使第三方数据连接器能够使用新的新式身份验证方法连接到 Microsoft 365，组织的管理员必须同意在 Azure Active Directory 中将连接器注册为受信任的服务应用程序。</span><span class="sxs-lookup"><span data-stu-id="dcccb-377">To enable a third-party data connector to connect to Microsoft 365 using the new modern authentication method, an administrator in your organization must consent to register the connector as a trusted service application in Azure Active Directory.</span></span> <span data-ttu-id="dcccb-378">这是通过接受允许连接器在 Azure Active Directory 中访问组织数据的权限请求完成。</span><span class="sxs-lookup"><span data-stu-id="dcccb-378">This is done by accepting a permission request to allow the connector to access your organization's data in Azure Active Directory.</span></span> <span data-ttu-id="dcccb-379">接受此请求后，第三方数据连接器会作为企业应用程序添加到 Azure Active Directory，并表示为服务主体。</span><span class="sxs-lookup"><span data-stu-id="dcccb-379">After you accept this request, the third-party data connector is added as an enterprise application to Azure Active Directory and represented as a service principal.</span></span> <span data-ttu-id="dcccb-380">有关同意过程详细信息，请参阅租户  [管理员同意](/skype-sdk/trusted-application-api/docs/tenantadminconsent)。</span><span class="sxs-lookup"><span data-stu-id="dcccb-380">For more information the consent process, see  [Tenant Admin Consent](/skype-sdk/trusted-application-api/docs/tenantadminconsent).</span></span>

<span data-ttu-id="dcccb-381">以下是访问和接受连接器注册请求的步骤：</span><span class="sxs-lookup"><span data-stu-id="dcccb-381">Here are the steps to access and accept the request to register the connector:</span></span>

1. <span data-ttu-id="dcccb-382">转到 [此页面，](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) 然后使用全局管理员的凭据登录。</span><span class="sxs-lookup"><span data-stu-id="dcccb-382">Go to [this page](https://login.microsoftonline.com/common/oauth2/authorize?client_id=8dfbc50b-2111-4d03-9b4d-dd0d00aae7a2&response_type=code&redirect_uri=https://portal.azure.com/&nonce=1234&prompt=admin_consent) and sign in using the credentials of a global administrator.</span></span>

   <span data-ttu-id="dcccb-383">将显示以下对话框。</span><span class="sxs-lookup"><span data-stu-id="dcccb-383">The following dialog box is displayed.</span></span> <span data-ttu-id="dcccb-384">可以展开插入文件，查看将分配给连接器的权限。</span><span class="sxs-lookup"><span data-stu-id="dcccb-384">You can expand the carets to review the permissions that will be assigned to the connector.</span></span>

   ![将显示权限请求对话框](../media/O365-ThirdPartyDataConnector-OptIn1.png)

2. <span data-ttu-id="dcccb-386">单击“Accept”。</span><span class="sxs-lookup"><span data-stu-id="dcccb-386">Click **Accept**.</span></span>

<span data-ttu-id="dcccb-387">接受请求后， [将显示 Azure](https://portal.azure.com) 门户。</span><span class="sxs-lookup"><span data-stu-id="dcccb-387">After you accept the request, the [Azure portal](https://portal.azure.com) is displayed.</span></span> <span data-ttu-id="dcccb-388">若要查看组织的应用程序列表，请单击 **"Azure Active Directory**  >  **企业应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="dcccb-388">To view the list of applications for your organization, click **Azure Active Directory** > **Enterprise applications**.</span></span> <span data-ttu-id="dcccb-389">"企业应用程序"边栏选项卡上列出了 Microsoft 365 第三方 **数据** 连接器。</span><span class="sxs-lookup"><span data-stu-id="dcccb-389">The Microsoft 365 third-party data connector is listed on the **Enterprise applications** blade.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dcccb-390">2018 年 9 月 30 日之后，如果未在 Azure Active Directory 中注册第三方数据连接器，则第三方数据将不再导入到您组织的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dcccb-390">After September 30, 2018, third-party data will no longer be imported into mailboxes in your organization if you don't register a third-party data connector in Azure Active Directory.</span></span> <span data-ttu-id="dcccb-391">请注意，在 2018 (2018 年 9 月 30 日之前创建的现有第三方数据连接器) 也必须按照步骤 5 中的过程在 Azure Active Directory 中注册。</span><span class="sxs-lookup"><span data-stu-id="dcccb-391">Note existing third-party data connectors (those created before September 30, 2018) must also be registered in Azure Active Directory by following the procedure in Step 5.</span></span>

### <a name="revoking-consent-for-a-third-party-data-connector"></a><span data-ttu-id="dcccb-392">撤销第三方数据连接器的同意</span><span class="sxs-lookup"><span data-stu-id="dcccb-392">Revoking consent for a third-party data connector</span></span>

<span data-ttu-id="dcccb-393">在组织同意在 Azure Active Directory 中注册第三方数据连接器的权限请求后，你的组织可以随时撤销该同意。</span><span class="sxs-lookup"><span data-stu-id="dcccb-393">After your organization consents to the permissions request to register a third-party data connector in Azure Active Directory, your organization can revoke that consent at any time.</span></span> <span data-ttu-id="dcccb-394">但是，撤销对连接器的同意意味着来自第三方数据源的数据将不再导入到 Microsoft 365 中。</span><span class="sxs-lookup"><span data-stu-id="dcccb-394">However, revoking the consent for a connector means that data from the third-party data source will no longer be imported into Microsoft 365.</span></span>

<span data-ttu-id="dcccb-395">若要撤销第三方数据连接器的同意，可以通过使用 Azure 门户中的"企业应用程序"边栏选项卡从 Azure Active Directory 中删除相应的服务主体) ，或者使用 Microsoft 365 PowerShell 中的[Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal)删除应用程序 (。 </span><span class="sxs-lookup"><span data-stu-id="dcccb-395">To revoke consent for a third-party data connector, you can delete the application (by deleting the corresponding service principal) from Azure Active Directory using the **Enterprise applications** blade in the Azure portal, or by using the [Remove-MsolServicePrincipal](/powershell/module/msonline/remove-msolserviceprincipal) in Microsoft 365 PowerShell.</span></span> <span data-ttu-id="dcccb-396">您还可以使用 Azure Active Directory PowerShell 中的 [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet。</span><span class="sxs-lookup"><span data-stu-id="dcccb-396">You can also use the [Remove-AzureADServicePrincipal](/powershell/module/azuread/remove-azureadserviceprincipal) cmdlet in Azure Active Directory PowerShell.</span></span>
  
## <a name="more-information"></a><span data-ttu-id="dcccb-397">更多信息</span><span class="sxs-lookup"><span data-stu-id="dcccb-397">More information</span></span>

- <span data-ttu-id="dcccb-398">如前所述，第三方数据源中的项目将作为电子邮件导入到 Exchange 邮箱。</span><span class="sxs-lookup"><span data-stu-id="dcccb-398">As previous explained, items from third-party data sources are imported to Exchange mailboxes as email messages.</span></span> <span data-ttu-id="dcccb-399">合作伙伴连接器使用 Microsoft 365 API 所需的架构导入项目。</span><span class="sxs-lookup"><span data-stu-id="dcccb-399">The partner connector imports the item using a schema required by the Microsoft 365 API.</span></span> <span data-ttu-id="dcccb-400">下表介绍了第三方数据源中的项目作为电子邮件导入到 Exchange 邮箱之后的邮件属性。</span><span class="sxs-lookup"><span data-stu-id="dcccb-400">The following table describes the message properties of an item from a third-party data source after it's imported to an Exchange mailbox as an email message.</span></span> <span data-ttu-id="dcccb-401">该表还指出该邮件属性是否是强制属性。</span><span class="sxs-lookup"><span data-stu-id="dcccb-401">The table also indicates if the message property is mandatory.</span></span> <span data-ttu-id="dcccb-402">必须填充强制属性。</span><span class="sxs-lookup"><span data-stu-id="dcccb-402">Mandatory properties must be populated.</span></span> <span data-ttu-id="dcccb-403">如果某个项目缺少强制属性，它不会导入到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="dcccb-403">If an item is missing a mandatory property, it won't be imported to Microsoft 365.</span></span> <span data-ttu-id="dcccb-404">导入过程返回一条错误消息，说明未导入项目的原因以及缺少的属性。</span><span class="sxs-lookup"><span data-stu-id="dcccb-404">The import process returns an error message explaining why an item wasn't imported and which property is missing.</span></span><br/><br/>
    
    |<span data-ttu-id="dcccb-405">**邮件属性**</span><span class="sxs-lookup"><span data-stu-id="dcccb-405">**Message property**</span></span>|<span data-ttu-id="dcccb-406">**强制？**</span><span class="sxs-lookup"><span data-stu-id="dcccb-406">**Mandatory?**</span></span>|<span data-ttu-id="dcccb-407">**说明**</span><span class="sxs-lookup"><span data-stu-id="dcccb-407">**Description**</span></span>|<span data-ttu-id="dcccb-408">**示例值**</span><span class="sxs-lookup"><span data-stu-id="dcccb-408">**Example value**</span></span>|
    |:-----|:-----|:-----|:-----|
    |<span data-ttu-id="dcccb-409">**FROM**</span><span class="sxs-lookup"><span data-stu-id="dcccb-409">**FROM**</span></span> <br/> |<span data-ttu-id="dcccb-410">是</span><span class="sxs-lookup"><span data-stu-id="dcccb-410">Yes</span></span>  <br/> |<span data-ttu-id="dcccb-411">最初创建或发送第三方数据源中的项目的用户。</span><span class="sxs-lookup"><span data-stu-id="dcccb-411">The user who originally created or sent the item in the third-party data source.</span></span> <span data-ttu-id="dcccb-412">合作伙伴连接器尝试将源项目 (例如 Twitter 句柄) 映射到所有参与者（FROM 和 TO 字段中 (用户）的用户帐户) 。</span><span class="sxs-lookup"><span data-stu-id="dcccb-412">The partner connector attempts to map the user ID from the source item (for example a Twitter handle) to a user account for all participants (users in the FROM and TO fields).</span></span> <span data-ttu-id="dcccb-413">邮件的副本将导入到每个参与者的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="dcccb-413">A copy of the message will be imported to the mailbox of every participant.</span></span> <span data-ttu-id="dcccb-414">如果项目参与者均无法映射到用户帐户，该项目将导入到 Microsoft 365 中的第三方存档邮箱。</span><span class="sxs-lookup"><span data-stu-id="dcccb-414">If none of the participants from the item can be mapped to a user account, the item will be imported to the third-party archiving mailbox in Microsoft 365.</span></span>  <br/> <br/> <span data-ttu-id="dcccb-415">被标识为项目发件人的参与者在将项目导入到的组织中必须具有活动邮箱。</span><span class="sxs-lookup"><span data-stu-id="dcccb-415">The participant who's identified as the sender of the item must have an active mailbox in the organization that the item is being imported to.</span></span> <span data-ttu-id="dcccb-416">如果发件人没有活动邮箱，则会返回以下错误：</span><span class="sxs-lookup"><span data-stu-id="dcccb-416">If the sender doesn't have an active mailbox, the following error is returned:</span></span><br/><br/>  `One or more messages in the Request failed to be delivered to either From or Sender email address. You will need to resend your entire Request. Error: The request failed. The remote server returned an error: (401) Unauthorized.`  | `bob@contoso.com` <br/> |
    |<span data-ttu-id="dcccb-417">**TO**</span><span class="sxs-lookup"><span data-stu-id="dcccb-417">**TO**</span></span> <br/> |<span data-ttu-id="dcccb-418">是</span><span class="sxs-lookup"><span data-stu-id="dcccb-418">Yes</span></span>  <br/> |<span data-ttu-id="dcccb-419">接收项目的用户（如果适用于数据源中的项目）。</span><span class="sxs-lookup"><span data-stu-id="dcccb-419">The user who received an item, if applicable for an item in the data source.</span></span>  <br/> | `bob@contoso.com` <br/> |
    |<span data-ttu-id="dcccb-420">**主题**</span><span class="sxs-lookup"><span data-stu-id="dcccb-420">**SUBJECT**</span></span> <br/> |<span data-ttu-id="dcccb-421">否</span><span class="sxs-lookup"><span data-stu-id="dcccb-421">No</span></span>  <br/> |<span data-ttu-id="dcccb-422">源项目中的主题。</span><span class="sxs-lookup"><span data-stu-id="dcccb-422">The subject from the source item.</span></span>  <br/> | `"Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/> |
    |<span data-ttu-id="dcccb-423">**DATE**</span><span class="sxs-lookup"><span data-stu-id="dcccb-423">**DATE**</span></span> <br/> |<span data-ttu-id="dcccb-424">是</span><span class="sxs-lookup"><span data-stu-id="dcccb-424">Yes</span></span>  <br/> |<span data-ttu-id="dcccb-425">最初在客户数据源中创建或发布项目的日期。</span><span class="sxs-lookup"><span data-stu-id="dcccb-425">The date the item was originally created or posted in the customer data source.</span></span> <span data-ttu-id="dcccb-426">例如，Twitter 消息推文的日期。</span><span class="sxs-lookup"><span data-stu-id="dcccb-426">For example, that date when a Twitter message was tweeted.</span></span>  <br/> | `01 NOV 2015` <br/> |
    |<span data-ttu-id="dcccb-427">**BODY**</span><span class="sxs-lookup"><span data-stu-id="dcccb-427">**BODY**</span></span> <br/> |<span data-ttu-id="dcccb-428">否</span><span class="sxs-lookup"><span data-stu-id="dcccb-428">No</span></span>  <br/> |<span data-ttu-id="dcccb-429">消息或帖子的内容。</span><span class="sxs-lookup"><span data-stu-id="dcccb-429">The contents of the message or post.</span></span> <span data-ttu-id="dcccb-430">对于某些数据源，此属性的内容可能与“主题”属性的内容相同。</span><span class="sxs-lookup"><span data-stu-id="dcccb-430">For some data sources, the contents of this property could be the same as the content for the **SUBJECT** property.</span></span> <span data-ttu-id="dcccb-431">在导入过程中，合作伙伴连接器会尝试尽可能保持内容源的完全保真度。</span><span class="sxs-lookup"><span data-stu-id="dcccb-431">During the import process, the partner connector attempts to maintain full fidelity from the content source as possible.</span></span> <span data-ttu-id="dcccb-432">如果可能，源项目正文中的文件、图形或其他内容会包含在此属性中。</span><span class="sxs-lookup"><span data-stu-id="dcccb-432">If possible files, graphics, or other content from the body of the source item is included in this property.</span></span> <span data-ttu-id="dcccb-433">否则，源项目中的内容会包含在“附件”属性中。</span><span class="sxs-lookup"><span data-stu-id="dcccb-433">Otherwise, content from the source item is included in the **ATTACHMENT** property.</span></span> <span data-ttu-id="dcccb-434">此属性的内容取决于合作伙伴连接器和源平台的功能。</span><span class="sxs-lookup"><span data-stu-id="dcccb-434">The contents of this property depends on the partner connector and on the capability of the source platform.</span></span>  <br/> | `Author: bob@contoso.com` <br/>  `Date: 10 DEC 2014` <br/>  `Tweet: "Mega deals with Contoso coming your way! #ContosoHolidayDeals"` <br/>  `Date: 01 NOV 2015` <br/> |
    |<span data-ttu-id="dcccb-435">**ATTACHMENT**</span><span class="sxs-lookup"><span data-stu-id="dcccb-435">**ATTACHMENT**</span></span> <br/> |<span data-ttu-id="dcccb-436">否</span><span class="sxs-lookup"><span data-stu-id="dcccb-436">No</span></span>  <br/> |<span data-ttu-id="dcccb-437">如果数据源中的项目 (Twitter 中的推文或即时消息对话) 具有附加文件或包含图像，合作伙伴连接将首先尝试在 **BODY** 属性中包括附件。</span><span class="sxs-lookup"><span data-stu-id="dcccb-437">If an item in the data source (such as a tweet in Twitter or an instant messaging conversation) has an attached file or include images, the partner connect will first attempt to include attachments in the **BODY** property.</span></span> <span data-ttu-id="dcccb-438">如果不可能，则它将被添加到 \*\* ATTACHMENT \*\* 属性。</span><span class="sxs-lookup"><span data-stu-id="dcccb-438">If that isn't possible, then it's added to the \*\* ATTACHMENT \*\* property.</span></span> <span data-ttu-id="dcccb-439">其他附件示例包括 Facebook 中的点赞，内容源中的元数据，以及对消息或帖子的回复。</span><span class="sxs-lookup"><span data-stu-id="dcccb-439">Other examples of attachments include Likes in Facebook, metadata from the content source, and responses to a message or post.</span></span>  <br/> | `image.gif` <br/> |
    |<span data-ttu-id="dcccb-440">**MESSAGECLASS**</span><span class="sxs-lookup"><span data-stu-id="dcccb-440">**MESSAGECLASS**</span></span> <br/> |<span data-ttu-id="dcccb-441">是</span><span class="sxs-lookup"><span data-stu-id="dcccb-441">Yes</span></span>  <br/> | <span data-ttu-id="dcccb-442">这是一个多值属性，由合作伙伴连接器创建和填充。</span><span class="sxs-lookup"><span data-stu-id="dcccb-442">This is a multi-value property, which is created and populated by partner connector.</span></span> <span data-ttu-id="dcccb-443">此属性的格式为  `IPM.NOTE.Source.Event` 。</span><span class="sxs-lookup"><span data-stu-id="dcccb-443">The format of this property is  `IPM.NOTE.Source.Event`.</span></span> <span data-ttu-id="dcccb-444"> (此属性必须以 开头  `IPM.NOTE` 。</span><span class="sxs-lookup"><span data-stu-id="dcccb-444">(This property must begin with  `IPM.NOTE`.</span></span> <span data-ttu-id="dcccb-445">此格式类似于邮件类的格式  `IPM.NOTE.X` 。) 此属性包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="dcccb-445">This format is similar to the one for the  `IPM.NOTE.X` message class.) This property includes the following information:</span></span>  <br/><br/><span data-ttu-id="dcccb-446">`Source`：指示第三方数据源;例如，Twitter、Facebook 或 BlackBerry。</span><span class="sxs-lookup"><span data-stu-id="dcccb-446">`Source`: Indicates the third-party data source; for example, Twitter, Facebook, or BlackBerry.</span></span>  <br/> <br/>  <span data-ttu-id="dcccb-447">`Event`：指示在生成项目的第三方数据源中执行的活动类型;例如，Twitter 中的推文或 Facebook 中的帖子。</span><span class="sxs-lookup"><span data-stu-id="dcccb-447">`Event`: Indicates the type of activity that was performed in the third-party data source that produced the items; for example, a tweet in Twitter or a post in Facebook.</span></span> <span data-ttu-id="dcccb-448">事件特定于数据源。</span><span class="sxs-lookup"><span data-stu-id="dcccb-448">Events are specific to the data source.</span></span>  <br/> <br/>  <span data-ttu-id="dcccb-449">此属性的一个目的是基于项目源自的数据源或基于事件类型筛选特定项目。</span><span class="sxs-lookup"><span data-stu-id="dcccb-449">One purpose of this property is to filter specific items based on the data source where an item originated or based on the type of event.</span></span> <span data-ttu-id="dcccb-450">例如，在电子数据展示搜索中，您可以创建一个搜索查询来查找特定用户发布的所有微博。</span><span class="sxs-lookup"><span data-stu-id="dcccb-450">For example, in an eDiscovery search you could create a search query to find all the tweets that were posted by a specific user.</span></span>  <br/> | `IPM.NOTE.Twitter.Tweet` <br/> |
   
- <span data-ttu-id="dcccb-451">当项目成功导入到 Microsoft 365 中的邮箱时，唯一标识符作为 HTTP 响应的一部分返回给调用方。</span><span class="sxs-lookup"><span data-stu-id="dcccb-451">When items are successfully imported to mailboxes in Microsoft 365, a unique identifier is returned back to the caller as part of the HTTP response.</span></span> <span data-ttu-id="dcccb-452">合作伙伴可以将此标识符（称为 ）用于后续疑难解答目的，以便  `x-IngestionCorrelationID` 对项目进行端到端跟踪。</span><span class="sxs-lookup"><span data-stu-id="dcccb-452">This identifier, called  `x-IngestionCorrelationID`, can be used for subsequent troubleshooting purposes by partners for end-to-end tracking of items.</span></span> <span data-ttu-id="dcccb-453">建议合作伙伴捕获此信息，并在他们的所在端相应地记录此信息。</span><span class="sxs-lookup"><span data-stu-id="dcccb-453">It's recommended that partners capture this information and log it accordingly at their end.</span></span> <span data-ttu-id="dcccb-454">下面是显示此标识符的 HTTP 响应的示例：</span><span class="sxs-lookup"><span data-stu-id="dcccb-454">Here's an example of an HTTP response showing this identifier:</span></span>

    ```http
    HTTP/1.1 200 OK
    Content-Type: text/xml; charset=utf-8
    Server: Microsoft-IIS/8.5
    x-IngestionCorrelationID: 1ec7667d-f097-47fe-a9a2-bc7ab0a7552b
    X-AspNet-Version: 4.0.30319
    X-Powered-By: ASP.NET
    Date: Tue, 02 Feb 2016 22:55:33 GMT 
    ```

- <span data-ttu-id="dcccb-455">可以使用安全与合规中心的内容搜索工具搜索已导入第三方数据源中的邮箱的项目。</span><span class="sxs-lookup"><span data-stu-id="dcccb-455">You can use the Content Search tool in the security and compliance center to search for items that were imported to mailboxes from a third-party data source.</span></span> <span data-ttu-id="dcccb-456">若要专门搜索这些导入的项目，可以在内容搜索的关键字框中使用以下邮件属性值对。</span><span class="sxs-lookup"><span data-stu-id="dcccb-456">To search specifically for these imported items, you can use the following message property-value pairs in the keyword box for a Content Search.</span></span>
    
  - <span data-ttu-id="dcccb-457">**`kind:externaldata`**：使用此属性值对搜索所有第三方数据类型。</span><span class="sxs-lookup"><span data-stu-id="dcccb-457">**`kind:externaldata`**: Use this property-value pair to search all third-party data types.</span></span> <span data-ttu-id="dcccb-458">例如，若要搜索从第三方数据源导入并包含在导入项目的 Subject 属性中的单词"contoso"的项目，您可以使用关键字查询  `kind:externaldata AND subject:contoso` 。</span><span class="sxs-lookup"><span data-stu-id="dcccb-458">For example, to search for items that were imported from a third-party data source and contained the word "contoso" in the Subject property of the imported item, you would use the keyword query  `kind:externaldata AND subject:contoso`.</span></span>
    
  - <span data-ttu-id="dcccb-459">**`itemclass:ipm.externaldata.<third-party data type>`**：使用此属性值对仅搜索第三方数据的指定类型。</span><span class="sxs-lookup"><span data-stu-id="dcccb-459">**`itemclass:ipm.externaldata.<third-party data type>`**: Use this property-value pair to only search a specify type of third-party data.</span></span> <span data-ttu-id="dcccb-460">例如，若要仅搜索 Subject 属性中包含单词"contoso"的 Facebook 数据，您可以使用关键字查询  `itemclass:ipm.externaldata.Facebook* AND subject:contoso` 。</span><span class="sxs-lookup"><span data-stu-id="dcccb-460">For example, to only search Facebook data that contains the word "contoso" in the Subject property, you would use the keyword query  `itemclass:ipm.externaldata.Facebook* AND subject:contoso`.</span></span> 

  <span data-ttu-id="dcccb-461">有关用于属性的第三方数据类型的值的完整列表，请参阅使用内容搜索搜索已导入  `itemclass` [到 Microsoft 365 的第三方数据](use-content-search-to-search-third-party-data-that-was-imported.md)。</span><span class="sxs-lookup"><span data-stu-id="dcccb-461">For a complete list of values to use for third-party data types for the  `itemclass` property, see [Use Content Search to search third-party data that was imported to Microsoft 365](use-content-search-to-search-third-party-data-that-was-imported.md).</span></span>
    
   <span data-ttu-id="dcccb-462">有关如何使用内容搜索以及创建关键字搜索查询的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="dcccb-462">For more information about using Content Search and creating keyword search queries, see:</span></span>
    
  - [<span data-ttu-id="dcccb-463">内容搜索</span><span class="sxs-lookup"><span data-stu-id="dcccb-463">Content Search</span></span>](content-search.md)
    
  - [<span data-ttu-id="dcccb-464">内容搜索的关键字查询和搜索条件</span><span class="sxs-lookup"><span data-stu-id="dcccb-464">Keyword queries and search conditions for Content Search</span></span>](keyword-queries-and-search-conditions.md)