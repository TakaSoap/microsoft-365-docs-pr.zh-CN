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
ms.openlocfilehash: 39951ce125f86748beab12cf1998075e26ad734b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50917184"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="a96d3-103">搜索 Teams 中本地用户的聊天数据</span><span class="sxs-lookup"><span data-stu-id="a96d3-103">Search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="a96d3-104">如果你的组织具有 Exchange 混合部署（或者贵组织已将本地 Exchange 组织与 Office 365 同步），并且已启用 Microsoft Teams，则本地用户可以使用 Teams 聊天应用程序进行即时消息传递。</span><span class="sxs-lookup"><span data-stu-id="a96d3-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, on-premises users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="a96d3-105">对于基于云的用户，Teams 聊天数据（也称为 *1x1 或 1xN 聊天*）将保存到其基于云的主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="a96d3-105">For a cloud-based user, Teams chat data (also called *1x1 or 1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="a96d3-106">如果本地用户使用团队聊天应用程序，其聊天消息将无法存储在本地主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="a96d3-106">When an on-premises user uses the Teams chat application, their chat messages can't be stored in their primary mailbox, which is located on-premises.</span></span> <span data-ttu-id="a96d3-107">为了绕开此限制，Microsoft 发布了一项新功能，在其中创建了基于云的存储区域，以便使用电子数据展示工具搜索和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area is created so that you use eDiscovery tools to search for and export Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="a96d3-108">以下是针对本地用户启用基于云的存储的要求和限制：</span><span class="sxs-lookup"><span data-stu-id="a96d3-108">Here are the requirements and limitations for enabling cloud-based storage for on-premises users:</span></span>
  
- <span data-ttu-id="a96d3-109">本地目录服务（如 Active Directory）中的用户帐户必须与 Azure Active Directory（Microsoft 365 中的目录服务）同步。</span><span class="sxs-lookup"><span data-stu-id="a96d3-109">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="a96d3-110">这意味着将在 Microsoft 365 中创建一个邮件用户帐户，并将该帐户与其主邮箱位于本地组织中的用户相关联。</span><span class="sxs-lookup"><span data-stu-id="a96d3-110">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="a96d3-111">必须为其主邮箱位于本地组织中的用户分配 Microsoft Teams 许可证和 Exchange Online 计划 1 许可证（最低要求）。</span><span class="sxs-lookup"><span data-stu-id="a96d3-111">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="a96d3-112">如果您的组织没有 Exchange 混合部署，则必须将本地 Exchange 架构同步到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="a96d3-112">If your organization doesn't have an Exchange hybrid deployment, you must synchronize your on-premises Exchange schema to Azure Active Directory.</span></span> <span data-ttu-id="a96d3-113">如果不这样做，虽然用户在本地 Exchange 组织中已有邮箱，你仍可能要冒险为其在 Exchange Online 中创建重复的基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a96d3-113">If you don't do this, you might risk creating duplicate cloud-based mailboxes in Exchange Online for users that have a mailbox in your on-premises Exchange organization.</span></span>

- <span data-ttu-id="a96d3-114">只有与本地用户关联的 Teams 聊天数据存储在基于云的存储区域中。</span><span class="sxs-lookup"><span data-stu-id="a96d3-114">Only Teams chat data associated with an on-premises user is stored in the cloud-based storage area.</span></span> <span data-ttu-id="a96d3-115">本地用户不能以任何方式访问此存储区域。</span><span class="sxs-lookup"><span data-stu-id="a96d3-115">An on-premises user can't access this storage area in any way.</span></span>

> [!NOTE]
> <span data-ttu-id="a96d3-116">Teams 频道对话始终存储在与 Teams 关联的基于云的邮箱中，这意味着可以搜索频道对话。</span><span class="sxs-lookup"><span data-stu-id="a96d3-116">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team, which means you can search for channel conversations.</span></span> <span data-ttu-id="a96d3-117">有关搜索 Teams 频道对话的详细信息，请参阅[搜索 Microsoft Teams 和 Microsoft 365 组](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="a96d3-117">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="a96d3-118">运作方式</span><span class="sxs-lookup"><span data-stu-id="a96d3-118">How it works</span></span>

<span data-ttu-id="a96d3-119">如果启用 Microsoft Teams 的用户拥有本地邮箱，并且其用户帐户/标识已同步到云端，Microsoft 将创建基于云的存储，以便关联本地用户的1xN Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-119">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates cloud-based storage to associate the on-premises user's 1xN Teams chat data with.</span></span> <span data-ttu-id="a96d3-120">本地用户的团队聊天数据已编入索引，可用于搜索。</span><span class="sxs-lookup"><span data-stu-id="a96d3-120">Teams chat data for on-premises users is indexed for search.</span></span> <span data-ttu-id="a96d3-121">这让你能够使用内容搜索（以及与核心和高级电子数据展示事例关联的搜索）来搜索、预览和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-121">This lets you Use Content Search (and searches associated with Core and Advanced eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="a96d3-122">你还可以使用安全与合规中心 PowerShell 中的 **\*ComplianceSearch** cmdlet 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-122">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="a96d3-123">下图显示了搜索、预览和导出本地用户的 Teams 聊天数据的工作流。</span><span class="sxs-lookup"><span data-stu-id="a96d3-123">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams 中的本地用户基于云的存储空间](../media/EHAMShard1.png)
  
<span data-ttu-id="a96d3-125">除了此新功能之外，你仍可以使用内容搜索在基于云的 SharePoint 网站和与每个 Microsoft Team 关联的 Exchange 邮箱中搜索、预览和导出 Teams 内容，以及在基于云的用户的 Exchange Online 邮箱中搜索、预览和导出 1xN Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-125">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>


### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="a96d3-126">启用此功能后会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="a96d3-126">What happens after this feature is enabled?</span></span>

<span data-ttu-id="a96d3-127">在组织中部署此功能后，将在安全与合规中心中的内容搜索以及与电子数据展示事例关联的搜索中进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="a96d3-127">After this feature is deployed in your organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="a96d3-128">在内容搜索的“**位置**”下方添加“**为本地用户添加 Office 应用内容**”复选框。</span><span class="sxs-lookup"><span data-stu-id="a96d3-128">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span>

    ![向内容搜索 UI 添加“为本地用户添加 Office 应用内容”复选框](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="a96d3-130">本地用户显示在内容位置选取器中，你可以使用它选择要搜索的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="a96d3-130">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span>

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a><span data-ttu-id="a96d3-131">搜索本地用户的 Teams 聊天内容</span><span class="sxs-lookup"><span data-stu-id="a96d3-131">Searching for Teams chat content for on-premises users</span></span>

<span data-ttu-id="a96d3-132">启用此功能后，可使用安全与合规中心中的内容搜索来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-132">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="a96d3-133">在安全与合规中心，转到“**搜索**”\>“**内容搜索**”</span><span class="sxs-lookup"><span data-stu-id="a96d3-133">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>

2. <span data-ttu-id="a96d3-134">在“**搜索**”页面上，单击“![添加”图标](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)“**新建搜索**”。</span><span class="sxs-lookup"><span data-stu-id="a96d3-134">On the **Search** page, click ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>

    <span data-ttu-id="a96d3-135">如前文所述，“**为本地用户添加 Office 应用内容**”复选框显示在“**位置**”下方。</span><span class="sxs-lookup"><span data-stu-id="a96d3-135">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="a96d3-136">它在默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="a96d3-136">It's selected by default.</span></span>

3. <span data-ttu-id="a96d3-137">创建关键字查询并为搜索查询添加条件（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="a96d3-137">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="a96d3-138">若要仅搜索 Teams 聊天数据，可在“**关键字**”框中添加以下查询：</span><span class="sxs-lookup"><span data-stu-id="a96d3-138">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im
    ```

4. <span data-ttu-id="a96d3-139">目前，可在“**位置**”下选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="a96d3-139">At this point, you can choose one of the following options under **Locations**:</span></span>

    - <span data-ttu-id="a96d3-140">**所有位置**：选择此选项可搜索组织中所有用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="a96d3-140">**All locations:** Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="a96d3-141">选中此复选框后，将搜索所有基于云的存储中本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-141">When the checkbox is selected, all cloud-based storage of Teams chat data for on-premises users will also be searched.</span></span>

    - <span data-ttu-id="a96d3-142">**特定位置**：选择此选项，然后单击“**修改**”\> 选择用户、组或团队以搜索特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="a96d3-142">**Specific locations:** Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="a96d3-143">如前文所述，位置选取器可用于搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-143">As previously explained, the locations picker lets you search for Teams chat data for on-premises users.</span></span>

5. <span data-ttu-id="a96d3-144">保存并运行搜索。</span><span class="sxs-lookup"><span data-stu-id="a96d3-144">Save and run the search.</span></span> <span data-ttu-id="a96d3-145">可像预览任何其他搜索结果一样预览本地用户的任何搜索结果。</span><span class="sxs-lookup"><span data-stu-id="a96d3-145">Any search results for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="a96d3-146">你还可以将搜索结果（包括任何 Teams 聊天数据）导出到 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="a96d3-146">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="a96d3-147">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a96d3-147">For more information, see:</span></span>

    - [<span data-ttu-id="a96d3-148">创建搜索</span><span class="sxs-lookup"><span data-stu-id="a96d3-148">Create a search</span></span>](content-search.md#create-a-search)

    - [<span data-ttu-id="a96d3-149">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="a96d3-149">Preview search results</span></span>](content-search.md#preview-search-results)

    - [<span data-ttu-id="a96d3-150">导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="a96d3-150">Export Content Search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="a96d3-151">使用 PowerShell 搜索本地用户的 Teams 聊天数据</span><span class="sxs-lookup"><span data-stu-id="a96d3-151">Using PowerShell to search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="a96d3-152">你可以使用安全与合规中心 PowerShell 中的 **New-ComplianceSearch** 和 **Set-ComplianceSearch** cmdlet 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-152">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="a96d3-153">如前文所述，无需提交支持请求即可使用 PowerShell 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-153">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="a96d3-154">[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="a96d3-154">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="a96d3-155">运行以下 PowerShell 命令以创建用于搜索本地用户 Teams 聊天数据的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="a96d3-155">Run the following PowerShell command to create a content search that searches for Teams chat data for on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="a96d3-156">*IncludeUserAppContent* 参数用于为由 *ExchangeLocation* 参数指定的一个或多个用户指定基于云的存储。</span><span class="sxs-lookup"><span data-stu-id="a96d3-156">The *IncludeUserAppContent*  parameter is used to specify the cloud-based storage for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="a96d3-157">*AllowNotFoundExchangeLocationsEnabled* 允许你搜索本地用户基于云的存储。</span><span class="sxs-lookup"><span data-stu-id="a96d3-157">The *AllowNotFoundExchangeLocationsEnabled*  allows you to search the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="a96d3-158">使用此参数的 `$true` 值时，搜索不会在运行之前尝试验证邮箱是否存在。</span><span class="sxs-lookup"><span data-stu-id="a96d3-158">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="a96d3-159">这是搜索本地用户的基于云的存储所必需的，因为此基于云的存储未作为常规的基于云的邮箱进行解析。</span><span class="sxs-lookup"><span data-stu-id="a96d3-159">This is required to search the cloud-based storage for on-premises users because this cloud-based storage doesn't resolve as a regular cloud-based mailbox.</span></span>

    <span data-ttu-id="a96d3-160">以下示例在 Sara Davis 基于云的存储中搜索包含关键字“redstone”的 Teams 聊天（它们是即时消息），Sara Davis 是 Contoso 组织内的本地用户。</span><span class="sxs-lookup"><span data-stu-id="a96d3-160">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based storage for Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="a96d3-161">创建搜索后，请务必使用 **Start-ComplianceSearch** cmdlet 运行搜索。</span><span class="sxs-lookup"><span data-stu-id="a96d3-161">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="a96d3-162">有关使用这些 cmdlet 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="a96d3-162">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="a96d3-163">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="a96d3-163">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

- [<span data-ttu-id="a96d3-164">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="a96d3-164">Set-ComplianceSearch</span></span>](/powershell/module/exchange/set-compliancesearch)

- [<span data-ttu-id="a96d3-165">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="a96d3-165">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="a96d3-166">已知问题</span><span class="sxs-lookup"><span data-stu-id="a96d3-166">Known issues</span></span>

- <span data-ttu-id="a96d3-167">目前，你可以搜索、预览和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-167">Currently, you can search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="a96d3-168">你还可以将本地用户的 Teams 聊天数据置于与核心和高级电子数据展示事例关联的保留中，并应用本地用户的 Teams 聊天或频道消息的保留策略。</span><span class="sxs-lookup"><span data-stu-id="a96d3-168">You can also place the Teams chat data for an on-premises user on a hold associated with a Core or Advanced eDiscovery case, and apply a retention policy for Teams chats or channel messages for on-premises users.</span></span> <span data-ttu-id="a96d3-169">但是，目前无法应用本地用户其他内容位置（如 Exchange 邮箱和 SharePoint 网站）的保留策略。</span><span class="sxs-lookup"><span data-stu-id="a96d3-169">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="a96d3-170">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="a96d3-170">Frequently asked questions</span></span>

<span data-ttu-id="a96d3-171">**本地用户基于云的邮箱位于何处？**</span><span class="sxs-lookup"><span data-stu-id="a96d3-171">**Where is the cloud-based storage for on-premises users located?**</span></span>
  
<span data-ttu-id="a96d3-172">Teams 聊天数据存储在本地用户的“首选数据位置”（PDL）中。</span><span class="sxs-lookup"><span data-stu-id="a96d3-172">Teams chat data is stored in the Preferred Data Location (PDL) for an on-premises user.</span></span> <span data-ttu-id="a96d3-173">PDL 同时在单一地理和多地理环境中都授予支持。</span><span class="sxs-lookup"><span data-stu-id="a96d3-173">The PDL is honored in both Single-Geo and Multi-Geo environments.</span></span> <span data-ttu-id="a96d3-174">有关详细信息，请参阅 [Microsoft 365 多地理位置](../enterprise/microsoft-365-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="a96d3-174">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>
  
 <span data-ttu-id="a96d3-175">**除了提交支持请求以外，还有其他要求吗？**</span><span class="sxs-lookup"><span data-stu-id="a96d3-175">**Are there any other requirements other than submitting a support request?**</span></span>
  
<span data-ttu-id="a96d3-176">如前文所述，必须将具有本地邮箱的用户标识同步到基于云的组织，以便为 Office 365 中的每个本地用户帐户创建对应的邮件用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a96d3-176">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="a96d3-177">你的组织还必须具有 Office 365 企业版订阅，例如 Office 365 企业版 E1、E3 或 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="a96d3-177">Your organization must also have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span>
  
 <span data-ttu-id="a96d3-178">**如果将用户的本地邮箱迁移到云，是否有丢失 Teams 聊天数据的风险？**</span><span class="sxs-lookup"><span data-stu-id="a96d3-178">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="a96d3-179">否。</span><span class="sxs-lookup"><span data-stu-id="a96d3-179">No.</span></span> <span data-ttu-id="a96d3-180">将本地用户的主邮箱迁移到云后，该用户的 Teams 聊天数据将迁移到其基于云的新主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="a96d3-180">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="a96d3-181">**是否可以为本地用户应用电子数据展示保留或保留策略？**</span><span class="sxs-lookup"><span data-stu-id="a96d3-181">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="a96d3-182">是。</span><span class="sxs-lookup"><span data-stu-id="a96d3-182">Yes.</span></span> <span data-ttu-id="a96d3-183">你可以应用本地用户的 Team 聊天和频道消息的电子数据展示保留或保留策略。</span><span class="sxs-lookup"><span data-stu-id="a96d3-183">You can apply eDiscovery holds or retention policies for Teams chats and channel messages of on-premises users.</span></span>
  
 <span data-ttu-id="a96d3-184">**在组织提交启用此功能的请求之前，内容搜索是否可以找到本地用户较早的 Teams 聊天数据？**</span><span class="sxs-lookup"><span data-stu-id="a96d3-184">**Can Content Search find older Teams chat data for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="a96d3-185">Microsoft 从 2018 年 1 月 31 日开始存储本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="a96d3-185">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="a96d3-186">因此，如果自此日期以来在 Active Directory 和 Azure Active Directory 之间同步了本地 Teams 用户的标识，则他们的 Teams 聊天数据存储在云中，并且可使用内容搜索进行搜索。</span><span class="sxs-lookup"><span data-stu-id="a96d3-186">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data is stored in the cloud and is searchable using Content Search.</span></span> <span data-ttu-id="a96d3-187">此外，Microsoft 正致力于将 2018 年 1 月 31 日之前的 Teams 聊天数据存储在本地用户基于云的存储中。</span><span class="sxs-lookup"><span data-stu-id="a96d3-187">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="a96d3-188">即将提供与此相关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="a96d3-188">More information about this will be available soon.</span></span>

 <span data-ttu-id="a96d3-189">**本地用户是否需要许可证才能将他们的 Teams 聊天数据存储在云中？**</span><span class="sxs-lookup"><span data-stu-id="a96d3-189">**Do on-premises users need a license to store their Teams chat data in the cloud?**</span></span>
  
<span data-ttu-id="a96d3-190">是。</span><span class="sxs-lookup"><span data-stu-id="a96d3-190">Yes.</span></span> <span data-ttu-id="a96d3-191">若要将本地用户的 Teams 聊天数据存储在基于云的存储中，必须在 Office 365（或 Microsoft 365）中为该用户分配 Microsoft Teams 许可证和 Exchange Online 计划许可证。</span><span class="sxs-lookup"><span data-stu-id="a96d3-191">To store Teams chat data for an on-premises user in a cloud-based storage, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>