---
title: 使用内容搜索搜索第三方导入的数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Normal
search.appverid:
- MOE150
- MET150
ms.assetid: ec2677ff-c4d7-4363-a9e7-22c80e015688
description: 使用内容搜索电子数据展示工具通过创建查询来搜索导入到第三Microsoft 365数据源中邮箱的项目。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 24ca63cf78b85f7b8b5181d5babd16058b641128
ms.sourcegitcommit: 25afc0c34edc7f8a5eb389d8c701175256c58ec8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/01/2020
ms.locfileid: "47324568"
---
# <a name="use-content-search-to-search-third-party-data-imported-by-a-custom-partner-connector"></a><span data-ttu-id="f4361-103">使用内容搜索搜索自定义合作伙伴连接器导入的第三方数据</span><span class="sxs-lookup"><span data-stu-id="f4361-103">Use Content Search to search third-party data imported by a custom partner connector</span></span>

<span data-ttu-id="f4361-104">您可以使用安全与合规中心的内容搜索[电子](content-search.md)数据展示工具&第三方数据源中导入 Microsoft 365 邮箱的项目。</span><span class="sxs-lookup"><span data-stu-id="f4361-104">You can use the [Content Search eDiscovery tool](content-search.md) in the Security & Compliance Center to search for items imported to mailboxes in Microsoft 365 from a third-party data source.</span></span> <span data-ttu-id="f4361-105">可以创建查询来搜索所有导入的第三方数据项，也可以创建查询来搜索特定的第三方数据项。</span><span class="sxs-lookup"><span data-stu-id="f4361-105">You can create a query to search all imported third-party data items or you can create a query to search specific third-party data items.</span></span> <span data-ttu-id="f4361-106">此外，还可以创建基于查询的保留策略或基于查询电子数据展示的保留，以保留第三方数据。</span><span class="sxs-lookup"><span data-stu-id="f4361-106">Also, you can also create a query-based retention policy or a query-based eDiscovery hold to preserve third-party data.</span></span>
  
<span data-ttu-id="f4361-107">有关与合作伙伴合作以导入第三方数据和可导入到 Microsoft 365 的第三方数据类型列表，请参阅与合作伙伴合作以在 Office 365 中存档第[三方数据](work-with-partner-to-archive-third-party-data.md)。</span><span class="sxs-lookup"><span data-stu-id="f4361-107">For more information about working with a partner to import third-party data and a list of the third-party data types that you can import to Microsoft 365, see [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md).</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f4361-108">本文中的指南仅适用于由自定义合作伙伴连接器导入的第三方数据。</span><span class="sxs-lookup"><span data-stu-id="f4361-108">The guidance in this article only applies to third-party data that was imported by a custom partner connector.</span></span> <span data-ttu-id="f4361-109">本文不适用于使用 Microsoft 合规中心中的第三方数据连接器导入的第三方[](archiving-third-party-data.md#third-party-data-connectors)数据。</span><span class="sxs-lookup"><span data-stu-id="f4361-109">This article doesn't apply to third-party data that is imported by using the [third-party data connectors](archiving-third-party-data.md#third-party-data-connectors) in the Microsoft compliance center.</span></span>
  
## <a name="creating-a-query-to-search-all-third-party-data"></a><span data-ttu-id="f4361-110">创建查询以搜索所有第三方数据</span><span class="sxs-lookup"><span data-stu-id="f4361-110">Creating a query to search all third-party data</span></span>

<span data-ttu-id="f4361-111">若要 (或将) 作为导入 Office 365 的任何类型的第三方数据进行搜索或保留，可以在内容搜索或创建基于查询的保留时，在关键字框中使用邮件属性值对。 `kind:externaldata`</span><span class="sxs-lookup"><span data-stu-id="f4361-111">To search (or place on hold) any type of third-party data that you've imported to Office 365, you can use the  `kind:externaldata` message property-value pair in the keyword box for a Content Search or when creating a query-based hold.</span></span> <span data-ttu-id="f4361-112">例如，若要搜索从任何第三方数据源导入的项目，并且导入项目的 Subject 属性中包含单词"contoso"，可以使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="f4361-112">For example, to search for items imported from any third-party data source and contain the word "contoso" in the Subject property of the imported item, you would use the following query:</span></span> 
  
```powershell
kind:externaldata AND subject:contoso
```

<span data-ttu-id="f4361-113">前面的关键字查询示例包括 subject 属性。</span><span class="sxs-lookup"><span data-stu-id="f4361-113">The previous keyword query example includes the subject property.</span></span> <span data-ttu-id="f4361-114">有关可以在关键字查询中包括的第三方数据项的其他属性的列表，请参阅与合作伙伴合作以在关键字查询中存档第三方数据中的"[详细信息"Office 365。](work-with-partner-to-archive-third-party-data.md#more-information)</span><span class="sxs-lookup"><span data-stu-id="f4361-114">For a list of other properties for third-party data items that can include in a keyword query, see the "More information" section in [Work with a partner to archive third-party data in Office 365](work-with-partner-to-archive-third-party-data.md#more-information).</span></span>
  
<span data-ttu-id="f4361-115">创建查询以搜索和保留第三方数据时，您还可以使用条件来缩小搜索结果范围。</span><span class="sxs-lookup"><span data-stu-id="f4361-115">When creating queries to search and hold third-party data, you can also use conditions to narrow the search results.</span></span> <span data-ttu-id="f4361-116">有关创建内容搜索查询的信息，请参阅内容搜索的关键字查询 [和搜索条件](keyword-queries-and-search-conditions.md)。</span><span class="sxs-lookup"><span data-stu-id="f4361-116">For more information about creating Content Search queries, see [Keyword queries and search conditions for Content Search](keyword-queries-and-search-conditions.md).</span></span>
  
## <a name="creating-a-query-to-search-specific-types-of-third-party-data"></a><span data-ttu-id="f4361-117">创建查询以搜索特定类型的第三方数据</span><span class="sxs-lookup"><span data-stu-id="f4361-117">Creating a query to search specific types of third-party data</span></span>

<span data-ttu-id="f4361-118">您可以创建仅搜索指定类型第三方数据的查询，而不是搜索所有类型的第三方数据，具体方法为使用下列邮件属性：内容搜索的关键字框中的值对：</span><span class="sxs-lookup"><span data-stu-id="f4361-118">Instead of searching all types of third-party data, you can create queries that only search for a specify type of third-party data by using the following message *property: value* pair in the keyword box for a Content Search:</span></span>
  
```powershell
itemclass:ipm.externaldata.<third-party data type>* 
```

<span data-ttu-id="f4361-119">例如，若要搜索 Subject 属性中包含单词"contoso"的 Facebook 数据，可使用以下查询：</span><span class="sxs-lookup"><span data-stu-id="f4361-119">For example, to search Facebook data that contains the word "contoso" in the Subject property, you would use the following query:</span></span>
  
```powershell
itemclass:ipm.externaldata.Facebook* AND subject:contoso
```

<span data-ttu-id="f4361-120">下表列出了可以搜索的第三方数据类型，以及用于邮件属性以专门搜索该类型第  `itemclass:` 三方数据的值。</span><span class="sxs-lookup"><span data-stu-id="f4361-120">The following table lists the third-party data types that you can search, and the value to use for the  `itemclass:` message property to specifically search for that type of third-party data.</span></span> <span data-ttu-id="f4361-121">查询语法不区分大小写。</span><span class="sxs-lookup"><span data-stu-id="f4361-121">The query syntax isn't case-sensitive.</span></span> 
  
|<span data-ttu-id="f4361-122">**第三方数据类型**</span><span class="sxs-lookup"><span data-stu-id="f4361-122">**Third-party data type**</span></span>|<span data-ttu-id="f4361-123">**属性值 `itemclass:`**</span><span class="sxs-lookup"><span data-stu-id="f4361-123">**Value for  `itemclass:` property**</span></span>|
|:-----|:-----|
|<span data-ttu-id="f4361-124">AIM</span><span class="sxs-lookup"><span data-stu-id="f4361-124">AIM</span></span>  <br/> | `ipm.externaldata.AIM*` <br/> |
|<span data-ttu-id="f4361-125">American Idol</span><span class="sxs-lookup"><span data-stu-id="f4361-125">American Idol</span></span>  <br/> | `ipm.externaldata.AmericanIdol*` <br/> |
|<span data-ttu-id="f4361-126">使用 Pivot 客户端的 AOL</span><span class="sxs-lookup"><span data-stu-id="f4361-126">AOL with Pivot Client</span></span>  <br/> | `ipm.externaldata.Pivot.IM` <br/> |
|<span data-ttu-id="f4361-127">Apple Juice</span><span class="sxs-lookup"><span data-stu-id="f4361-127">Apple Juice</span></span>  <br/> | `ipm.externaldata.AppleJuice*` <br/> |
|<span data-ttu-id="f4361-128">Ares</span><span class="sxs-lookup"><span data-stu-id="f4361-128">Ares</span></span>  <br/> | `ipm.externaldata.Ares*` <br/> |
|<span data-ttu-id="f4361-129">Axs Encrypted</span><span class="sxs-lookup"><span data-stu-id="f4361-129">Axs Encrypted</span></span>  <br/> | `ipm.externaldata.AxsEncrypted*` <br/> |
|<span data-ttu-id="f4361-130">Axs Exchange</span><span class="sxs-lookup"><span data-stu-id="f4361-130">Axs Exchange</span></span>  <br/> | `ipm.externaldata.AxsExchange*` <br/> |
|<span data-ttu-id="f4361-131">Axs 本地存档</span><span class="sxs-lookup"><span data-stu-id="f4361-131">Axs Local Archive</span></span>  <br/> | `ipm.externaldata.AxsLocalArchive*` <br/> |
|<span data-ttu-id="f4361-132">Axs 占位符</span><span class="sxs-lookup"><span data-stu-id="f4361-132">Axs Placeholder</span></span>  <br/> | `ipm.externaldata.AxsPlaceHolder*` <br/> |
|<span data-ttu-id="f4361-133">Axs Signed</span><span class="sxs-lookup"><span data-stu-id="f4361-133">Axs Signed</span></span>  <br/> | `ipm.externaldata.AxsSigned*` <br/> |
|<span data-ttu-id="f4361-134">Bazaarvoice</span><span class="sxs-lookup"><span data-stu-id="f4361-134">Bazaarvoice</span></span>  <br/> | `ipm.externaldata.Bazaarvoice*` <br/> |
|<span data-ttu-id="f4361-135">Bearshare</span><span class="sxs-lookup"><span data-stu-id="f4361-135">Bearshare</span></span>  <br/> | `ipm.externaldata.Bearshare*` <br/> |
|<span data-ttu-id="f4361-136">BitTorrent</span><span class="sxs-lookup"><span data-stu-id="f4361-136">BitTorrent</span></span>  <br/> | `ipm.externaldata.BitTorrent*` <br/> |
|<span data-ttu-id="f4361-137">Blackberry</span><span class="sxs-lookup"><span data-stu-id="f4361-137">Blackberry</span></span>  <br/> | `ipm.externaldata.Blackberry*` <br/> |
|<span data-ttu-id="f4361-138">BlackBerry 呼叫日志</span><span class="sxs-lookup"><span data-stu-id="f4361-138">BlackBerry Call Logs</span></span>  <br/> | `ipm.externaldata.BlackBerryCall*` <br/> |
|<span data-ttu-id="f4361-139">BlackBerry Messenger</span><span class="sxs-lookup"><span data-stu-id="f4361-139">BlackBerry Messenger</span></span>  <br/> | `ipm.externaldata.BlackBerryMessenger*` <br/> |
|<span data-ttu-id="f4361-140">BlackBerry PIN</span><span class="sxs-lookup"><span data-stu-id="f4361-140">BlackBerry PIN</span></span>  <br/> | `ipm.externaldata.BlackBerryPIN*` <br/> |
|<span data-ttu-id="f4361-141">BlackBerry 短信</span><span class="sxs-lookup"><span data-stu-id="f4361-141">BlackBerry SMS</span></span>  <br/> | `ipm.externaldata.BlackBerrySMS*` <br/> |
|<span data-ttu-id="f4361-142">Bloomberg</span><span class="sxs-lookup"><span data-stu-id="f4361-142">Bloomberg</span></span>  <br/> | `ipm.externaldata.Bloomberg*` <br/> |
|<span data-ttu-id="f4361-143">Bloomberg 消息</span><span class="sxs-lookup"><span data-stu-id="f4361-143">Bloomberg Message</span></span>  <br/> | `ipm.externaldata.conversation.Bloomberg Message*` <br/> |
|<span data-ttu-id="f4361-144">Bloomberg 消息</span><span class="sxs-lookup"><span data-stu-id="f4361-144">Bloomberg Messaging</span></span>  <br/> | `ipm.externaldata.BloombergMessaging*` <br/> |
|<span data-ttu-id="f4361-145">Box</span><span class="sxs-lookup"><span data-stu-id="f4361-145">Box</span></span>  <br/> | `ipm.externaldata.Box*` <br/> |
|<span data-ttu-id="f4361-146">Cisco IM &amp; Presence Server</span><span class="sxs-lookup"><span data-stu-id="f4361-146">Cisco IM &amp; Presence Server</span></span>  <br/> | `ipm.externaldata.Jabber.IM` <br/> |
|<span data-ttu-id="f4361-147">Cisco Jabber</span><span class="sxs-lookup"><span data-stu-id="f4361-147">Cisco Jabber</span></span>  <br/> | `ipm.externaldata.Jabber*` <br/> |
|<span data-ttu-id="f4361-148">适用于 Salesforce Chatter 的 CipherCloud</span><span class="sxs-lookup"><span data-stu-id="f4361-148">CipherCloud for Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter.Post` <br/>  `ipm.externaldata.Chatter.Comment` <br/> |
|<span data-ttu-id="f4361-149">Direct Connect</span><span class="sxs-lookup"><span data-stu-id="f4361-149">Direct Connect</span></span>  <br/> | `ipm.externaldata.DirectConnect*` <br/> |
|<span data-ttu-id="f4361-150">Facebook</span><span class="sxs-lookup"><span data-stu-id="f4361-150">Facebook</span></span>  <br/> | `ipm.externaldata.Facebook*` <br/> |
|<span data-ttu-id="f4361-151">FastTrack</span><span class="sxs-lookup"><span data-stu-id="f4361-151">FastTrack</span></span>  <br/> | `ipm.externaldata.FastTrack*` <br/> |
|<span data-ttu-id="f4361-152">FXConnect</span><span class="sxs-lookup"><span data-stu-id="f4361-152">FXConnect</span></span>  <br/> | `ipm.externaldata.FXConnect.chat` <br/> |
|<span data-ttu-id="f4361-153">Flickr</span><span class="sxs-lookup"><span data-stu-id="f4361-153">Flickr</span></span>  <br/> | `ipm.externaldata.Flickr*` <br/> |
|<span data-ttu-id="f4361-154">符合该规范的</span><span class="sxs-lookup"><span data-stu-id="f4361-154">Gnutella</span></span>  <br/> | `ipm.externaldata.Gnutella*` <br/> |
|<span data-ttu-id="f4361-155">Google+</span><span class="sxs-lookup"><span data-stu-id="f4361-155">Google+</span></span>  <br/> | `ipm.externaldata.GooglePlus*` <br/> |
|<span data-ttu-id="f4361-156">Google Talk</span><span class="sxs-lookup"><span data-stu-id="f4361-156">Google Talk</span></span>  <br/> | `ipm.externaldata.GoogleTalk*` <br/> |
|<span data-ttu-id="f4361-157">GoToMyPC</span><span class="sxs-lookup"><span data-stu-id="f4361-157">GoToMyPC</span></span>  <br/> | `ipm.externaldata.GoToMyPC*` <br/> |
|<span data-ttu-id="f4361-158">HipChat</span><span class="sxs-lookup"><span data-stu-id="f4361-158">HipChat</span></span>  <br/> | `ipm.externaldata.HipChat*` <br/> |
|<span data-ttu-id="f4361-159">Hopster</span><span class="sxs-lookup"><span data-stu-id="f4361-159">Hopster</span></span>  <br/> | `ipm.externaldata.Hopster*` <br/> |
|<span data-ttu-id="f4361-160">HubConnex</span><span class="sxs-lookup"><span data-stu-id="f4361-160">HubConnex</span></span>  <br/> | `ipm.externaldata.HubConnex*` <br/> |
|<span data-ttu-id="f4361-161">IBM Connections</span><span class="sxs-lookup"><span data-stu-id="f4361-161">IBM Connections</span></span>  <br/> | `ipm.externaldata.Connections*` <br/> |
|<span data-ttu-id="f4361-162">IBM SameTime</span><span class="sxs-lookup"><span data-stu-id="f4361-162">IBM SameTime</span></span>  <br/> | `ipm.externaldata.Sametime*` <br/> |
|<span data-ttu-id="f4361-163">ICE 聊天</span><span class="sxs-lookup"><span data-stu-id="f4361-163">ICE Chat</span></span>  <br/> | `ipm.externaldata.conversation.Ice Chat*` <br/> |
|<span data-ttu-id="f4361-164">Indii Messenger</span><span class="sxs-lookup"><span data-stu-id="f4361-164">Indii Messenger</span></span>  <br/> | `ipm.externaldata.Indii*` <br/> |
|<span data-ttu-id="f4361-165">Instagram</span><span class="sxs-lookup"><span data-stu-id="f4361-165">Instagram</span></span>  <br/> | `ipm.externaldata.Instagram*` <br/> |
|<span data-ttu-id="f4361-166">即时 Bloomberg</span><span class="sxs-lookup"><span data-stu-id="f4361-166">Instant Bloomberg</span></span>  <br/> | `ipm.externaldata.InstantBloomberg*` <br/> |
|<span data-ttu-id="f4361-167">InvestEdge</span><span class="sxs-lookup"><span data-stu-id="f4361-167">InvestEdge</span></span>  <br/> | `ipm.externaldata.InvestEdge*` <br/> |
|<span data-ttu-id="f4361-168">IRC</span><span class="sxs-lookup"><span data-stu-id="f4361-168">IRC</span></span>  <br/> | `ipm.externaldata.IRC*` <br/> |
|<span data-ttu-id="f4361-169">Jive</span><span class="sxs-lookup"><span data-stu-id="f4361-169">Jive</span></span>  <br/> | `ipm.externaldata.Jive*` <br/> |
|<span data-ttu-id="f4361-170">JiveApiRetention</span><span class="sxs-lookup"><span data-stu-id="f4361-170">JiveApiRetention</span></span>  <br/> | `ipm.externaldata.JiveApiRetention*` <br/> |
|<span data-ttu-id="f4361-171">JXTA</span><span class="sxs-lookup"><span data-stu-id="f4361-171">JXTA</span></span>  <br/> | `ipm.externaldata.JXTA*` <br/> |
|<span data-ttu-id="f4361-172">领英</span><span class="sxs-lookup"><span data-stu-id="f4361-172">LinkedIn</span></span>  <br/> | `ipm.externaldata.LinkedIn*` <br/> |
|<span data-ttu-id="f4361-173">MFTP</span><span class="sxs-lookup"><span data-stu-id="f4361-173">MFTP</span></span>  <br/> | `ipm.externaldata.MFTP*` <br/> |
|<span data-ttu-id="f4361-174">Microsoft UC</span><span class="sxs-lookup"><span data-stu-id="f4361-174">Microsoft UC</span></span>  <br/> | `ipm.externaldata.MicrosoftUC*` <br/> |
|<span data-ttu-id="f4361-175">居中对齐</span><span class="sxs-lookup"><span data-stu-id="f4361-175">Mind Align</span></span>  <br/> | `ipm.externaldata.MindAlign*` <br/> |
|<span data-ttu-id="f4361-176">Mobile Guard</span><span class="sxs-lookup"><span data-stu-id="f4361-176">Mobile Guard</span></span>  <br/> | `ipm.externaldata.MobileGuard*` <br/> |
|<span data-ttu-id="f4361-177">MSN</span><span class="sxs-lookup"><span data-stu-id="f4361-177">MSN</span></span>  <br/> | `ipm.externaldata.MSN*` <br/> |
|<span data-ttu-id="f4361-178">MySpace</span><span class="sxs-lookup"><span data-stu-id="f4361-178">MySpace</span></span>  <br/> | `ipm.externaldata.MySpace*` <br/> |
|<span data-ttu-id="f4361-179">完成</span><span class="sxs-lookup"><span data-stu-id="f4361-179">NEONetwork</span></span>  <br/> | `ipm.externaldata.NEONetwork*` <br/> |
|<span data-ttu-id="f4361-180">OpenNap</span><span class="sxs-lookup"><span data-stu-id="f4361-180">OpenNap</span></span>  <br/> | `ipm.externaldata.OpenNap*` <br/> |
|<span data-ttu-id="f4361-181">Pinterest</span><span class="sxs-lookup"><span data-stu-id="f4361-181">Pinterest</span></span>  <br/> | `ipm.externaldata.Pinterest*` <br/> |
|<span data-ttu-id="f4361-182">Pivot</span><span class="sxs-lookup"><span data-stu-id="f4361-182">Pivot</span></span>  <br/> | `ipm.externaldata.Pivot*` <br/> |
|<span data-ttu-id="f4361-183">QQ</span><span class="sxs-lookup"><span data-stu-id="f4361-183">QQ</span></span>  <br/> | `ipm.externaldata.QQ*` <br/> |
|<span data-ttu-id="f4361-184">Microsoft SharePoint</span><span class="sxs-lookup"><span data-stu-id="f4361-184">Microsoft SharePoint</span></span>  <br/> | `ipm.externaldata.SharePoint*` <br/> |
|<span data-ttu-id="f4361-185">Salesforce Chatter</span><span class="sxs-lookup"><span data-stu-id="f4361-185">Salesforce Chatter</span></span>  <br/> | `ipm.externaldata.Chatter*` <br/> |
|<span data-ttu-id="f4361-186">Skype for Business</span><span class="sxs-lookup"><span data-stu-id="f4361-186">Skype for Business</span></span>  <br/> | `ipm.externaldata.Skype*` <br/> |
|<span data-ttu-id="f4361-187">Slack Enterprise Grid</span><span class="sxs-lookup"><span data-stu-id="f4361-187">Slack Enterprise Grid</span></span>  <br/> | `ipm.externaldata.Slack.IM` <br/> |
|<span data-ttu-id="f4361-188">SoftEther</span><span class="sxs-lookup"><span data-stu-id="f4361-188">SoftEther</span></span>  <br/> | `ipm.externaldata.SoftEther*` <br/> |
|<span data-ttu-id="f4361-189">Squawker</span><span class="sxs-lookup"><span data-stu-id="f4361-189">Squawker</span></span>  <br/> | `ipm.externaldata.Squawker*` <br/> |
|<span data-ttu-id="f4361-190">Symphony</span><span class="sxs-lookup"><span data-stu-id="f4361-190">Symphony</span></span>  <br/> | `ipm.externaldata.Symphony*` <br/> |
|<span data-ttu-id="f4361-191">Thomson Reuters</span><span class="sxs-lookup"><span data-stu-id="f4361-191">Thomson Reuters</span></span>  <br/> | `ipm.externaldata.Reuters*` <br/> |
| <span data-ttu-id="f4361-192">Thomson Reuters Eikon Messenger</span><span class="sxs-lookup"><span data-stu-id="f4361-192">Thomson Reuters Eikon Messenger</span></span>  <br/> | `ipm.externaldata.ReutersEikon*` <br/> |
|<span data-ttu-id="f4361-193">Tor</span><span class="sxs-lookup"><span data-stu-id="f4361-193">Tor</span></span>  <br/> | `ipm.externaldata.Tor*` <br/> |
|<span data-ttu-id="f4361-194">TTT</span><span class="sxs-lookup"><span data-stu-id="f4361-194">TTT</span></span>  <br/> | `ipm.externaldata.TTT*` <br/> |
|<span data-ttu-id="f4361-195">Twitter</span><span class="sxs-lookup"><span data-stu-id="f4361-195">Twitter</span></span>  <br/> | `ipm.externaldata.Twitter*` <br/> |
|<span data-ttu-id="f4361-196">UBS 聊天</span><span class="sxs-lookup"><span data-stu-id="f4361-196">UBS Chat</span></span>  <br/> | `ipm.externaldata.UBS*` <br/> |
|<span data-ttu-id="f4361-197">Vimeo</span><span class="sxs-lookup"><span data-stu-id="f4361-197">Vimeo</span></span>  <br/> | `ipm.externaldata.Vimeo*` <br/> |
|<span data-ttu-id="f4361-198">WinMX</span><span class="sxs-lookup"><span data-stu-id="f4361-198">WinMX</span></span>  <br/> | `ipm.externaldata.WinMX*` <br/> |
|<span data-ttu-id="f4361-199">Winny</span><span class="sxs-lookup"><span data-stu-id="f4361-199">Winny</span></span>  <br/> | `ipm.externaldata.Winny*` <br/> |
|<span data-ttu-id="f4361-200">Yahoo！</span><span class="sxs-lookup"><span data-stu-id="f4361-200">Yahoo!</span></span>  <br/> | `ipm.externaldata.Yahoo!*` <br/> |
|<span data-ttu-id="f4361-201">Yammer</span><span class="sxs-lookup"><span data-stu-id="f4361-201">Yammer</span></span>  <br/> | `ipm.externaldata.Yammer*` <br/> |
|<span data-ttu-id="f4361-202">YellowJacket</span><span class="sxs-lookup"><span data-stu-id="f4361-202">YellowJacket</span></span>  <br/> | `ipm.externaldata.YellowJacket*` <br/> |
|<span data-ttu-id="f4361-203">YouTube</span><span class="sxs-lookup"><span data-stu-id="f4361-203">YouTube</span></span>  <br/> | `ipm.externaldata.YouTube*` <br/> |
