---
title: 搜索 Teams 中本地用户的聊天数据
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: M365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MST160
- MET150
ms.assetid: 3f7dde1a-a8ea-4366-86da-8ee6777f357c
description: 在 Exchange 混合部署中，使用安全与合规中心中的内容搜索工具搜索并导出本地用户的 Teams 聊天数据。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 9620c48056545e6d6cf053040849acfe0a1bc68e
ms.sourcegitcommit: c1f9a1b2a34146c51c9e33c4119a388b249ce7a9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/14/2021
ms.locfileid: "49868010"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="93267-103">搜索 Teams 中本地用户的聊天数据</span><span class="sxs-lookup"><span data-stu-id="93267-103">Search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="93267-104">如果你的组织具有 Exchange 混合部署（或者贵组织已将本地 Exchange 组织与 Office 365 同步），并且已启用 Microsoft Teams，则本地用户可以使用 Teams 聊天应用程序进行即时消息传递。</span><span class="sxs-lookup"><span data-stu-id="93267-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, on-premises users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="93267-105">对于基于云的用户，Teams 聊天数据（也称为 *1x1 或 1xN 聊天*）将保存到其基于云的主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="93267-105">For a cloud-based user, Teams chat data (also called *1x1 or 1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="93267-106">如果本地用户使用团队聊天应用程序，其聊天消息将无法存储在本地主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="93267-106">When an on-premises user uses the Teams chat application, their chat messages can't be stored in their primary mailbox, which is located on-premises.</span></span> <span data-ttu-id="93267-107">为了绕开此限制，Microsoft 发布了一项新功能，在其中创建了基于云的存储区域，以便使用电子数据展示工具搜索和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area is created so that you use eDiscovery tools to search for and export Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="93267-108">以下是针对本地用户启用基于云的存储的要求和限制：</span><span class="sxs-lookup"><span data-stu-id="93267-108">Here are the requirements and limitations for enabling cloud-based storage for on-premises users:</span></span>
  
- <span data-ttu-id="93267-109">本地目录服务（如 Active Directory）中的用户帐户必须与 Azure Active Directory（Microsoft 365 中的目录服务）同步。</span><span class="sxs-lookup"><span data-stu-id="93267-109">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="93267-110">这意味着将在 Microsoft 365 中创建一个邮件用户帐户，并将该帐户与其主邮箱位于本地组织中的用户相关联。</span><span class="sxs-lookup"><span data-stu-id="93267-110">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="93267-111">必须为其主邮箱位于本地组织中的用户分配 Microsoft Teams 许可证和 Exchange Online 计划 1 许可证（最低要求）。</span><span class="sxs-lookup"><span data-stu-id="93267-111">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="93267-112">只有与本地用户关联的 Teams 聊天数据存储在基于云的存储区域中。</span><span class="sxs-lookup"><span data-stu-id="93267-112">Only Teams chat data associated with an on-premises user is stored in the cloud-based storage area.</span></span> <span data-ttu-id="93267-113">本地用户不能以任何方式访问此存储区域。</span><span class="sxs-lookup"><span data-stu-id="93267-113">An on-premises user can't access this storage area in any way.</span></span>

- <span data-ttu-id="93267-114">你必须向 Microsoft 支持人员提交请求，以使贵组织能够搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-114">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="93267-115">请参阅本文中的[向 Microsoft 支持人员提交启用此功能的请求](#filing-a-request-with-microsoft-support-to-enable-this-feature)部分。</span><span class="sxs-lookup"><span data-stu-id="93267-115">See [Filing a request with Microsoft Support to enable this feature](#filing-a-request-with-microsoft-support-to-enable-this-feature) in this article.</span></span>

> [!NOTE]
> <span data-ttu-id="93267-116">Teams 频道对话始终存储在与 Teams 关联的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="93267-116">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team.</span></span> <span data-ttu-id="93267-117">这意味着您可以使用内容搜索来搜索频道对话，而无需提交支持请求。</span><span class="sxs-lookup"><span data-stu-id="93267-117">That means you can use Content Search to search channel conversations without have to file a support request.</span></span> <span data-ttu-id="93267-118">有关搜索 Teams 频道对话的详细信息，请参阅[搜索 Microsoft Teams 和 Microsoft 365 组](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="93267-118">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="93267-119">运作方式</span><span class="sxs-lookup"><span data-stu-id="93267-119">How it works</span></span>

<span data-ttu-id="93267-120">如果启用 Microsoft Teams 的用户拥有本地邮箱，并且其用户帐户/标识已同步到云端，Microsoft 将创建基于云的存储，以便关联本地用户的1xN Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-120">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates cloud-based storage to associate the on-premises user's 1xN Teams chat data with.</span></span> <span data-ttu-id="93267-121">本地用户的团队聊天数据已编入索引，可用于搜索。</span><span class="sxs-lookup"><span data-stu-id="93267-121">Teams chat data for on-premises users is indexed for search.</span></span> <span data-ttu-id="93267-122">这让你能够使用内容搜索（以及与核心和高级电子数据展示事例关联的搜索）来搜索、预览和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-122">This lets you Use Content Search (and searches associated with Core and Advanced eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="93267-123">你还可以使用安全与合规中心 PowerShell 中的 **\*ComplianceSearch** cmdlet 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-123">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="93267-124">下图显示了搜索、预览和导出本地用户的 Teams 聊天数据的工作流。</span><span class="sxs-lookup"><span data-stu-id="93267-124">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams 中的本地用户基于云的存储空间](../media/EHAMShard1.png)
  
<span data-ttu-id="93267-126">除了此新功能之外，你仍可以使用内容搜索在基于云的 SharePoint 网站和与每个 Microsoft Team 关联的 Exchange 邮箱中搜索、预览和导出 Teams 内容，以及在基于云的用户的 Exchange Online 邮箱中搜索、预览和导出 1xN Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-126">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a><span data-ttu-id="93267-127">向 Microsoft 支持人员提交启用此功能的请求</span><span class="sxs-lookup"><span data-stu-id="93267-127">Filing a request with Microsoft Support to enable this feature</span></span>

<span data-ttu-id="93267-128">你必须向 Microsoft 支持人员提交请求，以使贵组织能够使用安全与合规中心中的图形用户界面来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-128">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="93267-129">此功能在安全与合规中心 PowerShell 中提供。</span><span class="sxs-lookup"><span data-stu-id="93267-129">This feature is available in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="93267-130">无需提交支持请求即可使用 PowerShell 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-130">You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="93267-131">向 Microsoft 支持人员提交请求时，请包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="93267-131">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="93267-132">组织的默认域名。</span><span class="sxs-lookup"><span data-stu-id="93267-132">The default domain name of your organization.</span></span>

- <span data-ttu-id="93267-133">组织的租户名称和租户 ID。</span><span class="sxs-lookup"><span data-stu-id="93267-133">The tenant name and tenant ID of your organization.</span></span> <span data-ttu-id="93267-134">可在 Azure Active Directory 门户中找到这些信息（位于“**管理**”\>“**属性** 下）。</span><span class="sxs-lookup"><span data-stu-id="93267-134">You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**).</span></span> <span data-ttu-id="93267-135">请参阅[查找 Microsoft 365 租户 ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id)。</span><span class="sxs-lookup"><span data-stu-id="93267-135">See [Find your Microsoft 365 tenant ID](https://docs.microsoft.com/onedrive/find-your-office-365-tenant-id).</span></span>

- <span data-ttu-id="93267-136">可在支持请求中使用以下标题或说明：“为本地用户启用应用程序内容搜索”。</span><span class="sxs-lookup"><span data-stu-id="93267-136">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users".</span></span> <span data-ttu-id="93267-137">这有助于将请求传送到将实现请求的电子数据展示工程团队。</span><span class="sxs-lookup"><span data-stu-id="93267-137">This helps route the request to the eDiscovery engineering team who will implement the request.</span></span>

<span data-ttu-id="93267-138">执行工程更改后，Microsoft 支持人员将向你发送预计的部署日期。</span><span class="sxs-lookup"><span data-stu-id="93267-138">After the engineering change is made, Microsoft Support will send you an estimated deployment date.</span></span> <span data-ttu-id="93267-139">在提交支持请求后，部署过程通常需要 2 到 3 周的时间。</span><span class="sxs-lookup"><span data-stu-id="93267-139">The deployment process usually takes 2–3 weeks after you submit the support request.</span></span>
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="93267-140">启用此功能后会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="93267-140">What happens after this feature is enabled?</span></span>

<span data-ttu-id="93267-141">在组织中部署此功能后，将在安全与合规中心中的内容搜索以及与电子数据展示事例关联的搜索中进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="93267-141">After this feature is deployed in your organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="93267-142">在内容搜索的“**位置**”下方添加“**为本地用户添加 Office 应用内容**”复选框。</span><span class="sxs-lookup"><span data-stu-id="93267-142">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span>

    ![向内容搜索 UI 添加“为本地用户添加 Office 应用内容”复选框](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="93267-144">本地用户显示在内容位置选取器中，你可以使用它选择要搜索的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="93267-144">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span>

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a><span data-ttu-id="93267-145">搜索本地用户的 Teams 聊天内容</span><span class="sxs-lookup"><span data-stu-id="93267-145">Searching for Teams chat content for on-premises users</span></span>

<span data-ttu-id="93267-146">启用此功能后，可使用安全与合规中心中的内容搜索来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-146">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="93267-147">在安全与合规中心，转到“**搜索**”\>“**内容搜索**”</span><span class="sxs-lookup"><span data-stu-id="93267-147">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>

2. <span data-ttu-id="93267-148">在“**搜索**”页面上，单击“![添加”图标](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)“**新建搜索**”。</span><span class="sxs-lookup"><span data-stu-id="93267-148">On the **Search** page, click ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>

    <span data-ttu-id="93267-149">如前文所述，“**为本地用户添加 Office 应用内容**”复选框显示在“**位置**”下方。</span><span class="sxs-lookup"><span data-stu-id="93267-149">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="93267-150">它在默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="93267-150">It's selected by default.</span></span>

3. <span data-ttu-id="93267-151">创建关键字查询并为搜索查询添加条件（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="93267-151">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="93267-152">若要仅搜索 Teams 聊天数据，可在“**关键字**”框中添加以下查询：</span><span class="sxs-lookup"><span data-stu-id="93267-152">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im
    ```

4. <span data-ttu-id="93267-153">目前，可在“**位置**”下选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="93267-153">At this point, you can choose one of the following options under **Locations**:</span></span>

    - <span data-ttu-id="93267-154">**所有位置**：选择此选项可搜索组织中所有用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="93267-154">**All locations:** Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="93267-155">选中此复选框后，将搜索所有基于云的存储中本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-155">When the checkbox is selected, all cloud-based storage of Teams chat data for on-premises users will also be searched.</span></span>

    - <span data-ttu-id="93267-156">**特定位置**：选择此选项，然后单击“**修改**”\> 选择用户、组或团队以搜索特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="93267-156">**Specific locations:** Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="93267-157">如前文所述，位置选取器可用于搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-157">As previously explained, the locations picker lets you search for Teams chat data for on-premises users.</span></span>

5. <span data-ttu-id="93267-158">保存并运行搜索。</span><span class="sxs-lookup"><span data-stu-id="93267-158">Save and run the search.</span></span> <span data-ttu-id="93267-159">可像预览任何其他搜索结果一样预览本地用户的任何搜索结果。</span><span class="sxs-lookup"><span data-stu-id="93267-159">Any search results for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="93267-160">你还可以将搜索结果（包括任何 Teams 聊天数据）导出到 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="93267-160">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="93267-161">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="93267-161">For more information, see:</span></span>

    - [<span data-ttu-id="93267-162">创建搜索</span><span class="sxs-lookup"><span data-stu-id="93267-162">Create a search</span></span>](content-search.md#create-a-search)

    - [<span data-ttu-id="93267-163">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="93267-163">Preview search results</span></span>](content-search.md#preview-search-results)

    - [<span data-ttu-id="93267-164">导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="93267-164">Export Content Search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="93267-165">使用 PowerShell 搜索本地用户的 Teams 聊天数据</span><span class="sxs-lookup"><span data-stu-id="93267-165">Using PowerShell to search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="93267-166">你可以使用安全与合规中心 PowerShell 中的 **New-ComplianceSearch** 和 **Set-ComplianceSearch** cmdlet 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-166">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="93267-167">如前文所述，无需提交支持请求即可使用 PowerShell 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-167">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="93267-168">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="93267-168">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="93267-169">运行以下 PowerShell 命令以创建用于搜索本地用户 Teams 聊天数据的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="93267-169">Run the following PowerShell command to create a content search that searches for Teams chat data for on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="93267-170">*IncludeUserAppContent* 参数用于为由 *ExchangeLocation* 参数指定的一个或多个用户指定基于云的存储。</span><span class="sxs-lookup"><span data-stu-id="93267-170">The *IncludeUserAppContent*  parameter is used to specify the cloud-based storage for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="93267-171">*AllowNotFoundExchangeLocationsEnabled* 允许你搜索本地用户基于云的存储。</span><span class="sxs-lookup"><span data-stu-id="93267-171">The *AllowNotFoundExchangeLocationsEnabled*  allows you to search the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="93267-172">使用此参数的 `$true` 值时，搜索不会在运行之前尝试验证邮箱是否存在。</span><span class="sxs-lookup"><span data-stu-id="93267-172">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="93267-173">这是搜索本地用户的基于云的存储所必需的，因为此基于云的存储未作为常规的基于云的邮箱进行解析。</span><span class="sxs-lookup"><span data-stu-id="93267-173">This is required to search the cloud-based storage for on-premises users because this cloud-based storage doesn't resolve as a regular cloud-based mailbox.</span></span>

    <span data-ttu-id="93267-174">以下示例在 Sara Davis 基于云的存储中搜索包含关键字“redstone”的 Teams 聊天（它们是即时消息），Sara Davis 是 Contoso 组织内的本地用户。</span><span class="sxs-lookup"><span data-stu-id="93267-174">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based storage for Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="93267-175">创建搜索后，请务必使用 **Start-ComplianceSearch** cmdlet 运行搜索。</span><span class="sxs-lookup"><span data-stu-id="93267-175">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="93267-176">有关使用这些 cmdlet 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="93267-176">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="93267-177">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="93267-177">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/new-compliancesearch)

- [<span data-ttu-id="93267-178">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="93267-178">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/set-compliancesearch)

- [<span data-ttu-id="93267-179">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="93267-179">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="93267-180">已知问题</span><span class="sxs-lookup"><span data-stu-id="93267-180">Known issues</span></span>

- <span data-ttu-id="93267-181">目前，你可以搜索、预览和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-181">Currently, you can search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="93267-182">你还可以将本地用户的 Teams 聊天数据置于与核心和高级电子数据展示事例关联的保留中，并应用本地用户的 Teams 聊天或频道消息的保留策略。</span><span class="sxs-lookup"><span data-stu-id="93267-182">You can also place the Teams chat data for an on-premises user on a hold associated with a Core or Advanced eDiscovery case, and apply a retention policy for Teams chats or channel messages for on-premises users.</span></span> <span data-ttu-id="93267-183">但是，目前无法应用本地用户其他内容位置（如 Exchange 邮箱和 SharePoint 网站）的保留策略。</span><span class="sxs-lookup"><span data-stu-id="93267-183">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="93267-184">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="93267-184">Frequently asked questions</span></span>

<span data-ttu-id="93267-185">**本地用户基于云的邮箱位于何处？**</span><span class="sxs-lookup"><span data-stu-id="93267-185">**Where is the cloud-based storage for on-premises users located?**</span></span>
  
<span data-ttu-id="93267-186">Teams 聊天数据存储在本地用户的“首选数据位置”（PDL）中。</span><span class="sxs-lookup"><span data-stu-id="93267-186">Teams chat data is stored in the Preferred Data Location (PDL) for an on-premises user.</span></span> <span data-ttu-id="93267-187">PDL 同时在单一地理和多地理环境中都授予支持。</span><span class="sxs-lookup"><span data-stu-id="93267-187">The PDL is honored in both Single-Geo and Multi-Geo environments.</span></span> <span data-ttu-id="93267-188">有关详细信息，请参阅 [Microsoft 365 多地理位置](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo)。</span><span class="sxs-lookup"><span data-stu-id="93267-188">For more information, see [Microsoft 365 Multi-Geo](https://docs.microsoft.com/microsoft-365/enterprise/microsoft-365-multi-geo).</span></span>
  
 <span data-ttu-id="93267-189">**除了提交支持请求以外，还有其他要求吗？**</span><span class="sxs-lookup"><span data-stu-id="93267-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
<span data-ttu-id="93267-190">如前文所述，必须将具有本地邮箱的用户标识同步到基于云的组织，以便为 Office 365 中的每个本地用户帐户创建对应的邮件用户帐户。</span><span class="sxs-lookup"><span data-stu-id="93267-190">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="93267-191">你的组织还必须具有 Office 365 企业版订阅，例如 Office 365 企业版 E1、E3 或 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="93267-191">Your organization must also have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span>
  
 <span data-ttu-id="93267-192">**如果将用户的本地邮箱迁移到云，是否有丢失 Teams 聊天数据的风险？**</span><span class="sxs-lookup"><span data-stu-id="93267-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="93267-193">否。</span><span class="sxs-lookup"><span data-stu-id="93267-193">No.</span></span> <span data-ttu-id="93267-194">将本地用户的主邮箱迁移到云后，该用户的 Teams 聊天数据将迁移到其基于云的新主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="93267-194">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="93267-195">**是否可以为本地用户应用电子数据展示保留或保留策略？**</span><span class="sxs-lookup"><span data-stu-id="93267-195">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="93267-196">是。</span><span class="sxs-lookup"><span data-stu-id="93267-196">Yes.</span></span> <span data-ttu-id="93267-197">你可以应用本地用户的 Team 聊天和频道消息的电子数据展示保留或保留策略。</span><span class="sxs-lookup"><span data-stu-id="93267-197">You can apply eDiscovery holds or retention policies for Teams chats and channel messages of on-premises users.</span></span>
  
 <span data-ttu-id="93267-198">**在组织提交启用此功能的请求之前，内容搜索是否可以找到本地用户较早的 Teams 聊天数据？**</span><span class="sxs-lookup"><span data-stu-id="93267-198">**Can Content Search find older Teams chat data for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="93267-199">Microsoft 从 2018 年 1 月 31 日开始存储本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="93267-199">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="93267-200">因此，如果自此日期以来在 Active Directory 和 Azure Active Directory 之间同步了本地 Teams 用户的标识，则他们的 Teams 聊天数据存储在云中，并且可使用内容搜索进行搜索。</span><span class="sxs-lookup"><span data-stu-id="93267-200">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data is stored in the cloud and is searchable using Content Search.</span></span> <span data-ttu-id="93267-201">此外，Microsoft 正致力于将 2018 年 1 月 31 日之前的 Teams 聊天数据存储在本地用户基于云的存储中。</span><span class="sxs-lookup"><span data-stu-id="93267-201">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="93267-202">即将提供与此相关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="93267-202">More information about this will be available soon.</span></span>

 <span data-ttu-id="93267-203">**本地用户是否需要许可证才能将他们的 Teams 聊天数据存储在云中？**</span><span class="sxs-lookup"><span data-stu-id="93267-203">**Do on-premises users need a license to store their Teams chat data in the cloud?**</span></span>
  
<span data-ttu-id="93267-204">是。</span><span class="sxs-lookup"><span data-stu-id="93267-204">Yes.</span></span> <span data-ttu-id="93267-205">若要将本地用户的 Teams 聊天数据存储在基于云的存储中，必须在 Office 365（或 Microsoft 365）中为该用户分配 Microsoft Teams 许可证和 Exchange Online 计划许可证。</span><span class="sxs-lookup"><span data-stu-id="93267-205">To store Teams chat data for an on-premises user in a cloud-based storage, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>
