---
title: 在组织中搜索并删除电子邮件
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- Strat_O365_IP
- M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: 3526fd06-b45f-445b-aed4-5ebd37b3762a
description: 使用安全与合规中心内的搜索和清除功能，在组织中的所有邮箱中搜索并删除电子邮件。
ms.openlocfilehash: 69df11f00680aec2380ed5663761a29bc1fcfebc
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626438"
---
# <a name="search-for-and-delete-email-messages"></a><span data-ttu-id="d54f5-103">搜索和删除电子邮件</span><span class="sxs-lookup"><span data-stu-id="d54f5-103">Search for and delete email messages</span></span>

<span data-ttu-id="d54f5-104">**本文适用于管理员。你是否尝试在邮箱中查找要删除的项目？请参阅[使用“即时搜索”查找邮件或项目](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**。</span><span class="sxs-lookup"><span data-stu-id="d54f5-104">**This article is for administrators. Are you trying to find items in your mailbox that you want to delete? See [Find a message or item with Instant Search](https://support.office.com/article/69748862-5976-47b9-98e8-ed179f1b9e4d)**.</span></span>
   
<span data-ttu-id="d54f5-105">你可以使用内容搜索功能，在组织中的所有邮箱中搜索并删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-105">You can use the Content Search feature to search for and delete an email message from all mailboxes in your organization.</span></span> <span data-ttu-id="d54f5-106">这可以帮助你查找并删除可能有害或高风险的电子邮件，例如：</span><span class="sxs-lookup"><span data-stu-id="d54f5-106">This can help you find and remove potentially harmful or high-risk email, such as:</span></span>
  
- <span data-ttu-id="d54f5-107">包含危险附件或病毒的邮件</span><span class="sxs-lookup"><span data-stu-id="d54f5-107">Messages that contain dangerous attachments or viruses</span></span>

- <span data-ttu-id="d54f5-108">网络仿冒邮件</span><span class="sxs-lookup"><span data-stu-id="d54f5-108">Phishing messages</span></span>

- <span data-ttu-id="d54f5-109">包含敏感数据的邮件</span><span class="sxs-lookup"><span data-stu-id="d54f5-109">Messages that contain sensitive data</span></span>

> [!CAUTION]
> <span data-ttu-id="d54f5-110">搜索和清除是一项强大的功能，允许分配有必要权限的任意用户从组织的邮箱中删除电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-110">Search and purge is a powerful feature that allows anyone that is assigned the necessary permissions to delete email messages from mailboxes in your organization.</span></span>
  
## <a name="before-you-begin"></a><span data-ttu-id="d54f5-111">准备工作</span><span class="sxs-lookup"><span data-stu-id="d54f5-111">Before you begin</span></span>

- <span data-ttu-id="d54f5-112">若要创建并运行内容搜索，你必须是**电子数据展示管理员**角色组的成员，或者分配有**合规性搜索**管理角色。</span><span class="sxs-lookup"><span data-stu-id="d54f5-112">To create and run a Content Search, you have to be a member of the **eDiscovery Manager** role group or be assigned the **Compliance Search** management role.</span></span> <span data-ttu-id="d54f5-113">若要删除邮件，你必须是**组织管理**角色组的成员或分配有**搜索并清除**管理角色。</span><span class="sxs-lookup"><span data-stu-id="d54f5-113">To delete messages, you have to be a member of the **Organization Management** role group or be assigned the **Search And Purge** management role.</span></span> <span data-ttu-id="d54f5-114">有关将用户添加到角色组的信息，请参阅[分配安全与合规中心中的电子数据展示权限](assign-ediscovery-permissions.md)。</span><span class="sxs-lookup"><span data-stu-id="d54f5-114">For information about adding users to a role group, see [Assign eDiscovery permissions in the Security & Compliance Center](assign-ediscovery-permissions.md).</span></span>
    
- <span data-ttu-id="d54f5-115">你必须使用安全与合规中心 PowerShell 删除邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-115">You have to use Security & Compliance Center PowerShell to delete messages.</span></span> <span data-ttu-id="d54f5-116">有关如何连接的说明，请参阅[步骤 2](#step-2-connect-to-security--compliance-center-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d54f5-116">See [Step 2](#step-2-connect-to-security--compliance-center-powershell) for instructions about how to connect.</span></span>
    
- <span data-ttu-id="d54f5-117">一次最多可以删除每个邮箱的 10 封邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-117">A maximum of 10 items per mailbox can be removed at one time.</span></span> <span data-ttu-id="d54f5-118">因为搜索和删除邮件的功能是用作事件响应工具，所以此限制可帮助确保从邮箱中快速删除邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-118">Because the capability to search for and remove messages is intended to be an incident-response tool, this limit helps ensure that messages are quickly removed from mailboxes.</span></span> <span data-ttu-id="d54f5-119">此功能并不用于清理用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="d54f5-119">This feature isn't intended to clean up user mailboxes.</span></span>
    
- <span data-ttu-id="d54f5-120">在内容搜索中，可通过搜索和清除操作删除其内项目的最大邮箱数为 50,000。</span><span class="sxs-lookup"><span data-stu-id="d54f5-120">The maximum number of mailboxes in a Content Search that you can delete items in by doing a search and purge action is 50,000.</span></span> <span data-ttu-id="d54f5-121">如果内容搜索（在[步骤 1](#step-1-create-a-content-search-to-find-the-message-to-delete) 中创建）具有超过 50,000 个源邮箱，则清除操作（在步骤 3 中创建）将失败。</span><span class="sxs-lookup"><span data-stu-id="d54f5-121">If the Content Search (that you create in [Step 1](#step-1-create-a-content-search-to-find-the-message-to-delete)) has more than 50,000 source mailboxes, the purge action (that you create in Step 3) will fail.</span></span> <span data-ttu-id="d54f5-122">请参阅[详细信息](#more-information)部分，以了解有关对超过 50,000 个邮箱执行搜索和清除操作的提示。</span><span class="sxs-lookup"><span data-stu-id="d54f5-122">See the [More information](#more-information) section for a tip on performing a search and purge operation on more than 50,000 mailboxes.</span></span> 
    
- <span data-ttu-id="d54f5-123">本文中所述的步骤只能用于删除 Exchange Online 邮箱和公用文件夹中的项目。</span><span class="sxs-lookup"><span data-stu-id="d54f5-123">The procedure in this article can only be used to delete items in Exchange Online mailboxes and public folders.</span></span> <span data-ttu-id="d54f5-124">无法将其用于删除 SharePoint 或 OneDrive for Business 网站中的内容。</span><span class="sxs-lookup"><span data-stu-id="d54f5-124">You can't use it to delete content from SharePoint or OneDrive for Business sites.</span></span>
    
## <a name="step-1-create-a-content-search-to-find-the-message-to-delete"></a><span data-ttu-id="d54f5-125">步骤 1：创建内容搜索来查找要删除的邮件</span><span class="sxs-lookup"><span data-stu-id="d54f5-125">Step 1: Create a Content Search to find the message to delete</span></span>

<span data-ttu-id="d54f5-126">第一步是创建并运行内容搜索以查找您想要从组织的邮箱中删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-126">The first step is to create and run a Content Search to find the message that you want to remove from mailboxes in your organization.</span></span> <span data-ttu-id="d54f5-127">你可以通过使用安全与合规中心或运行 **New-ComplianceSearch** 和 **Start-ComplianceSearch** cmdlet 来创建搜索。</span><span class="sxs-lookup"><span data-stu-id="d54f5-127">You can create the search by using the Security & Compliance Center or by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets.</span></span> <span data-ttu-id="d54f5-128">与此搜索的查询匹配的邮件将通过在[步骤 3](#step-3-delete-the-message) 中运行 **New-ComplianceSearchAction -Purge** 命令来删除。</span><span class="sxs-lookup"><span data-stu-id="d54f5-128">The messages that match the query for this search will be deleted by running the **New-ComplianceSearchAction -Purge** command in [Step 3](#step-3-delete-the-message).</span></span> <span data-ttu-id="d54f5-129">有关创建内容搜索和配置搜索查询的信息，请参阅下列主题：</span><span class="sxs-lookup"><span data-stu-id="d54f5-129">For information about creating a Content Search and configuring search queries, see the following topics:</span></span> 
  
- [<span data-ttu-id="d54f5-130">Office 365 中的内容搜索</span><span class="sxs-lookup"><span data-stu-id="d54f5-130">Content Search in Office 365</span></span>](content-search.md)
    
- [<span data-ttu-id="d54f5-131">内容搜索的关键字查询</span><span class="sxs-lookup"><span data-stu-id="d54f5-131">Keyword queries for Content Search</span></span>](keyword-queries-and-search-conditions.md)
    
- [<span data-ttu-id="d54f5-132">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="d54f5-132">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearch)
    
- [<span data-ttu-id="d54f5-133">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="d54f5-133">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/Start-ComplianceSearch)
    
> [!NOTE]
> <span data-ttu-id="d54f5-134">在此步骤中创建的内容搜索中搜索的内容位置不能包含 SharePoint 或 OneDrive for Business 网站。</span><span class="sxs-lookup"><span data-stu-id="d54f5-134">The content locations that are searched in the Content Search that you create in this step can't include SharePoint or OneDrive for Business sites.</span></span> <span data-ttu-id="d54f5-135">只能在内容搜索中包含将用于电子邮件的邮箱和公用文件夹。</span><span class="sxs-lookup"><span data-stu-id="d54f5-135">You can include only mailboxes and public folders in a Content Search that will be used to email messages.</span></span> <span data-ttu-id="d54f5-136">如果内容搜索包含网站，则在运行 **New-ComplianceSearchAction** cmdlet 时，你将在步骤 3 中收到错误消息。</span><span class="sxs-lookup"><span data-stu-id="d54f5-136">If the Content Search includes sites, you'll receive an error in Step 3 when you run the **New-ComplianceSearchAction** cmdlet.</span></span> 
  
### <a name="tips-for-finding-messages-to-remove"></a><span data-ttu-id="d54f5-137">查找要删除的邮件的提示</span><span class="sxs-lookup"><span data-stu-id="d54f5-137">Tips for finding messages to remove</span></span>

<span data-ttu-id="d54f5-p109">搜索查询的目标是将搜索结果的范围缩小到仅包含您想要删除的邮件。以下是一些提示：</span><span class="sxs-lookup"><span data-stu-id="d54f5-p109">The goal of the search query is to narrow the results of the search to only the message or messages that you want to remove. Here are some tips:</span></span>
  
- <span data-ttu-id="d54f5-140">如果你知道邮件的主题行中使用的确切文本或短语，请在搜索查询中使用**主题**属性。</span><span class="sxs-lookup"><span data-stu-id="d54f5-140">If you know the exact text or phrase used in the subject line of the message, use the **Subject** property in the search query.</span></span> 
    
- <span data-ttu-id="d54f5-141">如果你知道邮件的确切日期（或日期范围），请搜索查询中包括**接收日期**属性。</span><span class="sxs-lookup"><span data-stu-id="d54f5-141">If you know that exact date (or date range) of the message, include the **Received** property in the search query.</span></span> 
    
- <span data-ttu-id="d54f5-142">如果你知道邮件的发件人，请在搜索查询中包括**收件人**属性。</span><span class="sxs-lookup"><span data-stu-id="d54f5-142">If you know who sent the message, include the **From** property in the search query.</span></span> 
    
- <span data-ttu-id="d54f5-143">预览搜索结果以验证搜索是否仅返回你想要删除的邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-143">Preview the search results to verify that the search returned only the message (or messages) that you want to delete.</span></span>
    
- <span data-ttu-id="d54f5-144">使用搜索估计统计信息（在安全与合规中心内的搜索的详细信息窗格中显示，或使用 [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet）获取结果总数。</span><span class="sxs-lookup"><span data-stu-id="d54f5-144">Use the search estimate statistics (displayed in the details pane of the search in the Security & Compliance Center or by using the [Get-ComplianceSearch](https://go.microsoft.com/fwlink/p/?LinkId=517934) cmdlet) to get a count of the total number of results.</span></span> 
    
<span data-ttu-id="d54f5-145">以下是查找可疑电子邮件的两个查询示例。</span><span class="sxs-lookup"><span data-stu-id="d54f5-145">Here are two examples of queries to find suspicious email messages.</span></span>
  
- <span data-ttu-id="d54f5-146">此查询返回用户在 2016 年 4 月 13 日至 2016 年 4 月 14 日之间收到的邮件，而且包含主题行中的单词“操作”和“必需”。</span><span class="sxs-lookup"><span data-stu-id="d54f5-146">This query returns messages that were received by users between April 13, 2016 and April 14, 2016 and that contain the words "action" and "required" in the subject line.</span></span>
    
    ```powershell
    (Received:4/13/2016..4/14/2016) AND (Subject:'Action required')
    ```

- <span data-ttu-id="d54f5-147">此查询返回由 chatsuwloginsset12345@outlook.com 发送的邮件，而且包含主题行中的完全匹配的短语“更新您的帐户信息”。</span><span class="sxs-lookup"><span data-stu-id="d54f5-147">This query returns messages that were sent by chatsuwloginsset12345@outlook.com and that contain the exact phrase "Update your account information" in the subject line.</span></span>
    
    ```powershell
    (From:chatsuwloginsset12345@outlook.com) AND (Subject:"Update your account information")
    ```

<span data-ttu-id="d54f5-148">下面是使用查询创建和开始搜索的示例，方法是运行 **New-ComplianceSearch** 和 **Start-ComplianceSearch** cmdlet 来搜索组织中的所有邮箱：</span><span class="sxs-lookup"><span data-stu-id="d54f5-148">Here's an example of using a query to create and start a search by running the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets to search all mailboxes in the organization:</span></span>

```powershell
$Search=New-ComplianceSearch -Name "Remove Phishing Message" -ExchangeLocation All -ContentMatchQuery '(Received:4/13/2016..4/14/2016) AND (Subject:"Action required")'
Start-ComplianceSearch -Identity $Search.Identity
```

## <a name="step-2-connect-to-security--compliance-center-powershell"></a><span data-ttu-id="d54f5-149">步骤 2：连接到安全与合规中心 PowerShell</span><span class="sxs-lookup"><span data-stu-id="d54f5-149">Step 2: Connect to Security & Compliance Center PowerShell</span></span>

<span data-ttu-id="d54f5-150">下一步是连接到组织的安全与合规中心 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="d54f5-150">The next step is to connect to Security & Compliance Center PowerShell for your organization.</span></span> <span data-ttu-id="d54f5-151">有关分步说明，请参阅[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="d54f5-151">For step-by-step instructions, see [Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>
  
<span data-ttu-id="d54f5-152">如果你的 Microsoft 365 帐户使用多重身份验证 (MFA) 或联合身份验证，则无法使用上一主题中有关连接到安全与合规中心 PowerShell 的说明。</span><span class="sxs-lookup"><span data-stu-id="d54f5-152">If your Microsoft 365 account uses multi-factor authentication (MFA) or federated authentication, you can't use the instructions in the previous topic on connecting to Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="d54f5-153">请改为参阅主题[使用多重身份验证连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell) 中的说明。</span><span class="sxs-lookup"><span data-stu-id="d54f5-153">Instead, see the instructions in the topic [Connect to Security & Compliance Center PowerShell using multi-factor authentication](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/mfa-connect-to-scc-powershell).</span></span>

<span data-ttu-id="d54f5-154">连接到安全与合规中心 PowerShell 后，运行在上一步中准备的 **New-ComplianceSearch** 和 **Start-ComplianceSearch** cmdlet。</span><span class="sxs-lookup"><span data-stu-id="d54f5-154">After you've connected to Security & Compliance Center PowerShell, run the **New-ComplianceSearch** and **Start-ComplianceSearch** cmdlets that you prepared in the previous step.</span></span>
  
## <a name="step-3-delete-the-message"></a><span data-ttu-id="d54f5-155">步骤 3：删除邮件</span><span class="sxs-lookup"><span data-stu-id="d54f5-155">Step 3: Delete the message</span></span>

<span data-ttu-id="d54f5-156">创建并优化内容搜索以返回你想要删除的邮件并且连接到安全与合规中心 PowerShell 后，最后一步是运行 **New-ComplianceSearchAction** cmdlet 来删除邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-156">After you've created and refined a Content Search to return the message that you want to remove and are connected to Security & Compliance Center PowerShell, the final step is to run the **New-ComplianceSearchAction** cmdlet to delete the message.</span></span> <span data-ttu-id="d54f5-157">可对邮件进行软删除或硬删除。</span><span class="sxs-lookup"><span data-stu-id="d54f5-157">You can soft- or hard-delete the message.</span></span> <span data-ttu-id="d54f5-158">软删除的邮件将移至用户的“可恢复的项目”文件夹并保留，直到已删除项目的保留期到期。</span><span class="sxs-lookup"><span data-stu-id="d54f5-158">A soft-deleted message is moved to a user's Recoverable Items folder and retained until the deleted item retention period expires.</span></span> <span data-ttu-id="d54f5-159">硬删除的邮件被标记为从邮箱中永久删除，并在托管文件夹助理下次处理邮箱时永久删除。</span><span class="sxs-lookup"><span data-stu-id="d54f5-159">Hard-deleted messages are marked for permanent removal from the mailbox and will be permanently removed the next time the mailbox is processed by the Managed Folder Assistant.</span></span> <span data-ttu-id="d54f5-160">如果为邮箱启用了单个项目恢复，则在已删除项目的保留期到期后，将永久删除硬删除的项目。</span><span class="sxs-lookup"><span data-stu-id="d54f5-160">If single item recovery is enabled for the mailbox, hard-deleted items will be permanently removed after the deleted item retention period expires.</span></span> <span data-ttu-id="d54f5-161">如果邮箱处于保留状态，则会保留已删除的邮件，直到该项目的保留期到期或从邮箱中删除保留为止。</span><span class="sxs-lookup"><span data-stu-id="d54f5-161">If a mailbox is placed on hold, deleted messages are preserved until the hold duration for the item expires or until the hold is removed from the mailbox.</span></span>
  
<span data-ttu-id="d54f5-162">在以下示例中，该命令软删除名为“删除网络钓鱼邮件”的内容搜索返回的搜索结果。</span><span class="sxs-lookup"><span data-stu-id="d54f5-162">In the following example, the command soft-deletes the search results returned by a Content Search named "Remove Phishing Message".</span></span> 

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType SoftDelete
```

<span data-ttu-id="d54f5-163">要硬删除由“删除网络钓鱼邮件”内容搜索返回的项目，你需要运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="d54f5-163">To hard-delete the items returned by the "Remove Phishing Message" content search, you would run this command:</span></span>

```powershell
New-ComplianceSearchAction -SearchName "Remove Phishing Message" -Purge -PurgeType HardDelete
```

<span data-ttu-id="d54f5-164">当你运行上一个命令以软删除或硬删除邮件时，*SearchName* 参数是你在步骤 1 中创建的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="d54f5-164">When you run the previous command to soft- or hard-delete messages, the search specified by the  *SearchName*  parameter is the Content Search that you created in Step 1.</span></span> 
  
<span data-ttu-id="d54f5-165">有关详细信息，请参阅 [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction)。</span><span class="sxs-lookup"><span data-stu-id="d54f5-165">For more information, see [New-ComplianceSearchAction](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/New-ComplianceSearchAction).</span></span>

## <a name="more-information"></a><span data-ttu-id="d54f5-166">详细信息</span><span class="sxs-lookup"><span data-stu-id="d54f5-166">More information</span></span>

- <span data-ttu-id="d54f5-167">**如何获取有关搜索和删除操作的状态？**</span><span class="sxs-lookup"><span data-stu-id="d54f5-167">**How do you get status on the search and remove operation?**</span></span>

    <span data-ttu-id="d54f5-168">运行 **Get-ComplianceSearchAction** 以获取有关删除操作的状态。</span><span class="sxs-lookup"><span data-stu-id="d54f5-168">Run the **Get-ComplianceSearchAction** to get the status on the delete operation.</span></span> <span data-ttu-id="d54f5-169">运行 **New-ComplianceSearchAction** cmdlet 时创建的对象使用以下格式命名：`<name of Content Search>_Purge`。</span><span class="sxs-lookup"><span data-stu-id="d54f5-169">The object that is created when you run the **New-ComplianceSearchAction** cmdlet is named using this format:  `<name of Content Search>_Purge`.</span></span> 
    
- <span data-ttu-id="d54f5-170">**删除邮件后会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="d54f5-170">**What happens after you delete a message?**</span></span>

   <span data-ttu-id="d54f5-171">使用 `New-ComplianceSearchAction -Purge -PurgeType HardDelete` 命令删除的邮件将移至“清除”文件夹，用户无法访问这些邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-171">A message that's deleted with the  `New-ComplianceSearchAction -Purge -PurgeType HardDelete` command is moved to the Purges folder and can't be accessed by the user.</span></span> <span data-ttu-id="d54f5-172">将邮件移至“清除”文件夹后，如果为邮箱启用了单个项目恢复，则会在已删除的邮件保留期内保留邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-172">After the message is moved to the Purges folder, the message is retained for the duration of the deleted item retention period if single item recovery is enabled for the mailbox.</span></span> <span data-ttu-id="d54f5-173">（在 Microsoft 365 中，创建新邮箱时将默认启用单个项目恢复。）已删除项目的保留期到期后，邮件将标记为永久删除，并在托管文件夹助手下次处理邮箱时从 Microsoft 365 中清除。</span><span class="sxs-lookup"><span data-stu-id="d54f5-173">(In Microsoft 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Microsoft 365 the next time the mailbox is processed by the Managed Folder assistant.</span></span> 

   <span data-ttu-id="d54f5-174">如果使用 `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` 命令，邮件将移至用户的“可恢复的项目”文件夹内的“删除”文件夹中。</span><span class="sxs-lookup"><span data-stu-id="d54f5-174">If you use the `New-ComplianceSearchAction -Purge -PurgeType SoftDelete` command, messages are moved to the Deletions folder in the user's Recoverable Items folder.</span></span> <span data-ttu-id="d54f5-175">它不会立即从 Microsoft 365 中清除。</span><span class="sxs-lookup"><span data-stu-id="d54f5-175">It isn't immediately purged from Microsoft 365.</span></span> <span data-ttu-id="d54f5-176">在基于为邮箱配置的已删除邮件保留期的持续时间内，用户可以恢复“已删除邮件”文件夹中的邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-176">The user can recover messages in the Deleted Items folder for the duration based on the deleted item retention period configured for the mailbox.</span></span> <span data-ttu-id="d54f5-177">此保留期过期（或如果用户在过期之前清除邮件）后，邮件将移动到“清除”文件夹，用户将无法再访问。</span><span class="sxs-lookup"><span data-stu-id="d54f5-177">After this retention period expires (or if user purges the message before it expires), the message is moved to the Purges folder and can no longer be accessed by the user.</span></span> <span data-ttu-id="d54f5-178">进入“清除”文件夹后，如果启用了邮箱的单个邮件恢复，则邮件将保留一段时间，该时间取决于为邮箱配置的已删除邮件保留期。</span><span class="sxs-lookup"><span data-stu-id="d54f5-178">Once in the Purges folder, the message is retained for the duration based on the deleted item retention period configured for the mailbox if single items recovery is enabled for the mailbox.</span></span> <span data-ttu-id="d54f5-179">（在 Microsoft 365 中，创建新邮箱时将默认启用单个项目恢复。）已删除项目的保留期到期后，邮件将标记为永久删除，并在托管文件夹助手下次处理邮箱时从 Microsoft 365 中清除。</span><span class="sxs-lookup"><span data-stu-id="d54f5-179">(In Microsoft 365, single item recovery is enabled by default when a new mailbox is created.) After the deleted item retention period expires, the message is marked for permanent deletion and will be purged from Microsoft 365 the next time that the mailbox is processed by the Managed Folder assistant.</span></span> 
    
- <span data-ttu-id="d54f5-180">**如果必须删除超过 50,000 个邮箱中的邮件，该怎么办？**</span><span class="sxs-lookup"><span data-stu-id="d54f5-180">**What if you have to delete a message from more than 50,000 mailboxes?**</span></span>

    <span data-ttu-id="d54f5-181">如前文所述，你可以对最多 50,000 个邮箱执行搜索和清除操作。</span><span class="sxs-lookup"><span data-stu-id="d54f5-181">As previously stated, you can perform a search and purge operation on a maximum of 50,000 mailboxes.</span></span> <span data-ttu-id="d54f5-182">如果必须对超过 50,000 个邮箱执行搜索和清除操作，请考虑创建临时搜索权限筛选器，这会将要搜索的邮箱数减少到低于 50,000 个。</span><span class="sxs-lookup"><span data-stu-id="d54f5-182">If you have to do a search and purge operation on more than 50,000 mailboxes, consider creating temporary search permissions filters that would reduce the number of mailboxes that would be searched to less than 50,000 mailboxes.</span></span> <span data-ttu-id="d54f5-183">例如，如果你的组织包含不同部门、州或国家/地区的邮箱，则可以基于其中一个邮箱属性创建邮箱搜索权限筛选器，以搜索组织内的邮箱子集。</span><span class="sxs-lookup"><span data-stu-id="d54f5-183">For example, if your organization contains mailboxes in different departments, states, or countries, you can create a mailbox search permissions filter based on one of those mailbox properties to search a subset of mailboxes in your organization.</span></span> <span data-ttu-id="d54f5-184">创建搜索权限筛选器后，将创建搜索（如步骤 1 中所述），然后删除邮件（如步骤 3 中所述）。</span><span class="sxs-lookup"><span data-stu-id="d54f5-184">After you create the search permissions filter, you would create the search (described in Step 1) and then delete the message (described in Step 3).</span></span> <span data-ttu-id="d54f5-185">然后，你可以编辑筛选器以搜索和清除不同邮箱集中的邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-185">Then you can edit the filter to search for and purge messages in a different set of mailboxes.</span></span> <span data-ttu-id="d54f5-186">有关创建搜索权限筛选器的详细信息，请参阅[配置内容搜索的权限筛选](permissions-filtering-for-content-search.md)。</span><span class="sxs-lookup"><span data-stu-id="d54f5-186">For more information about creating search permissions filters, see [Configure permissions filtering for Content Search](permissions-filtering-for-content-search.md).</span></span>
    
- <span data-ttu-id="d54f5-187">**是否会删除搜索结果中包含的未编制索引的项目？**</span><span class="sxs-lookup"><span data-stu-id="d54f5-187">**Will unindexed items included in the search results be deleted?**</span></span>

    <span data-ttu-id="d54f5-188">不会，New-ComplianceSearchAction -Purge 命令不会删除未编制索引的项目。</span><span class="sxs-lookup"><span data-stu-id="d54f5-188">No, the  \`New-ComplianceSearchAction -Purge command doesn't delete unindexed items.</span></span> 
    
- <span data-ttu-id="d54f5-189">**如果从处于就地保留或诉讼保留状态的邮箱中删除邮件或为邮件分配 Microsoft 365 保留策略，会发生什么情况？**</span><span class="sxs-lookup"><span data-stu-id="d54f5-189">**What happens if a message is deleted from a mailbox that has been placed on In-Place Hold or Litigation Hold or is assigned to an Microsoft 365 retention policy?**</span></span>

    <span data-ttu-id="d54f5-190">清除邮件并将其移至“清除”文件夹后，将保留邮件，直到保留期到期为止。</span><span class="sxs-lookup"><span data-stu-id="d54f5-190">After the message is purged and moved to the Purges folder, the message is retained until the hold duration expires.</span></span> <span data-ttu-id="d54f5-191">如果为无限期的保留期，则这些项目会一直保留到你删除保留设置或更改保留期。</span><span class="sxs-lookup"><span data-stu-id="d54f5-191">If the hold duration is unlimited, then items are retained until the hold is removed or the hold duration is changed.</span></span>
    
- <span data-ttu-id="d54f5-192">**为什么在不同的安全与合规中心角色组之间划分搜索和删除工作流？**</span><span class="sxs-lookup"><span data-stu-id="d54f5-192">**Why is the search and remove workflow divided among different security and compliance center role groups?**</span></span>

    <span data-ttu-id="d54f5-193">如前所述，必须是电子数据展示管理员角色组的成员或者分配有合规性搜索管理角色的用户才能搜索邮箱。</span><span class="sxs-lookup"><span data-stu-id="d54f5-193">As previously explained, a person has to be a member of the eDiscovery Manager role group or be assigned the Compliance Search management role to search mailboxes.</span></span> <span data-ttu-id="d54f5-194">若要删除邮件，必须是组织管理角色组的成员，或分配有“搜索并清除”管理角色。</span><span class="sxs-lookup"><span data-stu-id="d54f5-194">To delete messages, a person has to be a member of the Organization Management role group or be assigned the Search And Purge management role.</span></span> <span data-ttu-id="d54f5-195">这就使得可以控制哪些人可以搜索组织中的邮箱以及哪些人可以删除邮件。</span><span class="sxs-lookup"><span data-stu-id="d54f5-195">This makes it possible to control who can search mailboxes in the organization and who can delete messages.</span></span> 
