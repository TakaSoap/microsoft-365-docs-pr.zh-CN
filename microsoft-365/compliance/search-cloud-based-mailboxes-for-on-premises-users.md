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
description: 使用 Microsoft 365 中的电子数据展示工具在 Exchange 混合部署中搜索和导出本地用户的 Teams 聊天数据。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: ab59c179b62903dd5f1ddd9b718f81a1ac78923a
ms.sourcegitcommit: efb932db63ad3ab4af4b585428d567d069410e4e
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52311793"
---
# <a name="search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="df98c-103">搜索 Teams 中本地用户的聊天数据</span><span class="sxs-lookup"><span data-stu-id="df98c-103">Search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="df98c-104">如果你的组织具有 Exchange 混合部署（或者贵组织已将本地 Exchange 组织与 Office 365 同步），并且已启用 Microsoft Teams，则本地用户可以使用 Teams 聊天应用程序进行即时消息传递。</span><span class="sxs-lookup"><span data-stu-id="df98c-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, on-premises users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="df98c-105">对于基于云的用户，Teams 聊天数据（也称为 *1x1 或 1xN 聊天*）将保存到其基于云的主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="df98c-105">For a cloud-based user, Teams chat data (also called *1x1 or 1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="df98c-106">如果本地用户使用团队聊天应用程序，其聊天消息将无法存储在本地主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="df98c-106">When an on-premises user uses the Teams chat application, their chat messages can't be stored in their primary mailbox, which is located on-premises.</span></span> <span data-ttu-id="df98c-107">为了绕开此限制，Microsoft 发布了一项新功能，在其中创建了基于云的存储区域，以便使用电子数据展示工具搜索和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="df98c-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area is created so that you use eDiscovery tools to search for and export Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="df98c-108">以下是针对本地用户启用基于云的存储的要求和限制：</span><span class="sxs-lookup"><span data-stu-id="df98c-108">Here are the requirements and limitations for enabling cloud-based storage for on-premises users:</span></span>
  
- <span data-ttu-id="df98c-109">本地目录服务（如 Active Directory）中的用户帐户必须与 Azure Active Directory（Microsoft 365 中的目录服务）同步。</span><span class="sxs-lookup"><span data-stu-id="df98c-109">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="df98c-110">这意味着将在 Microsoft 365 中创建一个邮件用户帐户，并将该帐户与其主邮箱位于本地组织中的用户相关联。</span><span class="sxs-lookup"><span data-stu-id="df98c-110">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="df98c-111">必须为其主邮箱位于本地组织中的用户分配 Microsoft Teams 许可证和 Exchange Online 计划 1 许可证（最低要求）。</span><span class="sxs-lookup"><span data-stu-id="df98c-111">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="df98c-112">如果您的组织没有 Exchange 混合部署，则必须将本地 Exchange 架构同步到 Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="df98c-112">If your organization doesn't have an Exchange hybrid deployment, you must synchronize your on-premises Exchange schema to Azure Active Directory.</span></span> <span data-ttu-id="df98c-113">如果不这样做，虽然用户在本地 Exchange 组织中已有邮箱，你仍可能要冒险为其在 Exchange Online 中创建重复的基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="df98c-113">If you don't do this, you might risk creating duplicate cloud-based mailboxes in Exchange Online for users that have a mailbox in your on-premises Exchange organization.</span></span>

- <span data-ttu-id="df98c-114">只有与本地用户关联的 Teams 聊天数据存储在基于云的存储区域中。</span><span class="sxs-lookup"><span data-stu-id="df98c-114">Only the Teams chat data associated with an on-premises user is stored in the cloud-based storage area.</span></span> <span data-ttu-id="df98c-115">本地用户不能以任何方式访问此存储区域。</span><span class="sxs-lookup"><span data-stu-id="df98c-115">An on-premises user can't access this storage area in any way.</span></span>

> [!NOTE]
> <span data-ttu-id="df98c-116">Teams 频道对话始终存储在与 Teams 关联的基于云的邮箱中，这意味着可以搜索频道对话。</span><span class="sxs-lookup"><span data-stu-id="df98c-116">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team, which means you can search for channel conversations.</span></span> <span data-ttu-id="df98c-117">有关搜索 Teams 频道对话的详细信息，请参阅[搜索 Microsoft Teams 和 Microsoft 365 组](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="df98c-117">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search-reference.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="df98c-118">运作方式</span><span class="sxs-lookup"><span data-stu-id="df98c-118">How it works</span></span>

<span data-ttu-id="df98c-119">如果启用 Microsoft Teams 的用户拥有本地邮箱，并且其用户帐户/标识已同步到云端，Microsoft 将创建基于云的存储，以便关联本地用户的1xN Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="df98c-119">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates cloud-based storage to associate the on-premises user's 1xN Teams chat data with.</span></span> <span data-ttu-id="df98c-120">本地用户的团队聊天数据已编入索引，可用于搜索。</span><span class="sxs-lookup"><span data-stu-id="df98c-120">Teams chat data for on-premises users is indexed for search.</span></span> <span data-ttu-id="df98c-121">这让你能够使用“内容搜索”（以及与核心电子数据展示和高级电子数据展示事例关联的搜索）来搜索、预览和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="df98c-121">This lets you Use Content search (and searches associated with Core eDiscovery and Advanced eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="df98c-122">你还可以使用安全与合规中心 PowerShell 中的 **\*ComplianceSearch** cmdlet 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="df98c-122">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="df98c-123">下图显示了搜索、预览和导出本地用户的 Teams 聊天数据的工作流。</span><span class="sxs-lookup"><span data-stu-id="df98c-123">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams 中的本地用户基于云的存储空间](../media/EHAMShard1.png)
  
<span data-ttu-id="df98c-125">除了此功能之外，你还可以使用电子数据展示工具在基于云的 SharePoint 网站和与每个 Microsoft Team 关联的 Exchange 邮箱中搜索、预览和导出 Teams 内容，以及在基于云的用户的 Exchange Online 邮箱中搜索、预览和导出 1xN Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="df98c-125">In addition to this capability, you can also use eDiscovery tools to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

### <a name="how-this-feature-is-supported-in-content-search-and-core-ediscovery-search-tools"></a><span data-ttu-id="df98c-126">“内容搜索”和核心电子数据展示搜索工具如何支持此功能</span><span class="sxs-lookup"><span data-stu-id="df98c-126">How this feature is supported in Content search and Core eDiscovery search tools</span></span>

<span data-ttu-id="df98c-127">Microsoft 365 合规中心中的“内容搜索”以及与核心电子数据展示事例关联的搜索工具中的以下 UI 元素：</span><span class="sxs-lookup"><span data-stu-id="df98c-127">The following UI elements in Content search and in the search tool associated with Core eDiscovery cases in the Microsoft 365 compliance center:</span></span>
  
- <span data-ttu-id="df98c-128">“**为本地用户添加应用内容**”复选框显示在内容搜索工具的“**位置**”向导页上，并默认选中。</span><span class="sxs-lookup"><span data-stu-id="df98c-128">The **Add app content for on-premises users** checkbox is displayed on the **Locations** wizard page in Content search tool and selected by default.</span></span> <span data-ttu-id="df98c-129">选中此复选框可在内容搜索中包括本地用户的基于云的存储。</span><span class="sxs-lookup"><span data-stu-id="df98c-129">Keep this checkbox selected to include the cloud-based storage for on-premises users in a content search.</span></span>

    ![向内容搜索 UI 添加“为本地用户添加 Office 应用内容”复选框](../media/EHAMShardCheckBox.png)
  
- <span data-ttu-id="df98c-131">当选择搜索特定用户时，可以搜索本地用户。</span><span class="sxs-lookup"><span data-stu-id="df98c-131">You can search for on-premises users when you choose specific users to search for.</span></span>

## <a name="searching-for-teams-chat-content-for-on-premises-users"></a><span data-ttu-id="df98c-132">搜索本地用户的 Teams 聊天内容</span><span class="sxs-lookup"><span data-stu-id="df98c-132">Searching for Teams chat content for on-premises users</span></span>

<span data-ttu-id="df98c-133">下面介绍了如何使用 Microsoft 365 合规中心中的“内容搜索”来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="df98c-133">Here's how to use Content search in the Microsoft 365 compliance center to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="df98c-134">在 Microsoft 365 合规中心中，转到“**内容搜索**”。</span><span class="sxs-lookup"><span data-stu-id="df98c-134">In the Microsoft 365 compliance center, go to **Content search**.</span></span>

2. <span data-ttu-id="df98c-135">在“**搜索**”选项卡上，单击“**新建搜索**”，然后命名新搜索。</span><span class="sxs-lookup"><span data-stu-id="df98c-135">On the **Searches** tab, click **New search**, and name the new search.</span></span>

3. <span data-ttu-id="df98c-136">在“**位置**”页面上，为 Exchange 邮箱将切换设置为“**打开**”。</span><span class="sxs-lookup"><span data-stu-id="df98c-136">On the **Locations** page, set the toggle to **On** for Exchange mailboxes.</span></span> <span data-ttu-id="df98c-137">请注意，“**为本地用户添加应用内容**”复选框已显示，并默认选中。</span><span class="sxs-lookup"><span data-stu-id="df98c-137">Notice that the **Add app content for on-premises users** checkbox is displayed and selected by default.</span></span>

4. <span data-ttu-id="df98c-138">若要搜索特定用户的 Teams 内容，请选择“**选择用户、组或团队**”，并选择特定用户包含在搜索中。</span><span class="sxs-lookup"><span data-stu-id="df98c-138">To search for Teams content for specific users, select **Choose user, groups, or teams** and choose specific users to include in the search.</span></span> <span data-ttu-id="df98c-139">否则，单击“**下一步**”搜索所有用户（包括本地用户）的 Teams 内容</span><span class="sxs-lookup"><span data-stu-id="df98c-139">Otherwise, click **Next** to search for Teams content for all users, including  on-premises users</span></span>

5. <span data-ttu-id="df98c-140">在“**定义搜索条件**”页面上，创建关键字查询，并在必要时将条件添加到搜索查询。</span><span class="sxs-lookup"><span data-stu-id="df98c-140">On the **Define your search conditions** page, create a keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="df98c-141">若要仅搜索 Teams 聊天数据，可在“**关键字**”框中添加以下查询：</span><span class="sxs-lookup"><span data-stu-id="df98c-141">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im AND kind:microsoftteams
    ```

6. <span data-ttu-id="df98c-142">提交并运行搜索。</span><span class="sxs-lookup"><span data-stu-id="df98c-142">Submit and run the search.</span></span> <span data-ttu-id="df98c-143">可像预览任何其他搜索结果一样预览本地用户的任何搜索结果。</span><span class="sxs-lookup"><span data-stu-id="df98c-143">Any search results for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="df98c-144">你还可以将搜索结果（包括任何 Teams 聊天数据）导出到 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="df98c-144">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="df98c-145">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="df98c-145">For more information, see:</span></span>

    - [<span data-ttu-id="df98c-146">创建搜索</span><span class="sxs-lookup"><span data-stu-id="df98c-146">Create a search</span></span>](content-search.md)

    - [<span data-ttu-id="df98c-147">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="df98c-147">Preview search results</span></span>](preview-ediscovery-search-results.md)

    - [<span data-ttu-id="df98c-148">导出搜索结果</span><span class="sxs-lookup"><span data-stu-id="df98c-148">Export search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-for-on-premises-users"></a><span data-ttu-id="df98c-149">使用 PowerShell 搜索本地用户的 Teams 聊天数据</span><span class="sxs-lookup"><span data-stu-id="df98c-149">Using PowerShell to search for Teams chat data for on-premises users</span></span>

<span data-ttu-id="df98c-150">你可以使用安全与合规中心 PowerShell 中的 **New-ComplianceSearch** 和 **Set-ComplianceSearch** cmdlet 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="df98c-150">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="df98c-151">如前文所述，无需提交支持请求即可使用 PowerShell 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="df98c-151">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
1. <span data-ttu-id="df98c-152">[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="df98c-152">[Connect to Security & Compliance Center PowerShell](/powershell/exchange/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="df98c-153">运行以下 PowerShell 命令以创建用于搜索本地用户 Teams 聊天数据的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="df98c-153">Run the following PowerShell command to create a content search that searches for Teams chat data for on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="df98c-154">*IncludeUserAppContent* 参数用于为由 *ExchangeLocation* 参数指定的一个或多个用户指定基于云的存储。</span><span class="sxs-lookup"><span data-stu-id="df98c-154">The *IncludeUserAppContent*  parameter is used to specify the cloud-based storage for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="df98c-155">*AllowNotFoundExchangeLocationsEnabled* 允许你搜索本地用户基于云的存储。</span><span class="sxs-lookup"><span data-stu-id="df98c-155">The *AllowNotFoundExchangeLocationsEnabled*  allows you to search the cloud-based storage for on-premises users.</span></span> <span data-ttu-id="df98c-156">使用此参数的 `$true` 值时，搜索不会在运行之前尝试验证邮箱是否存在。</span><span class="sxs-lookup"><span data-stu-id="df98c-156">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="df98c-157">这是搜索本地用户的基于云的存储所必需的，因为此基于云的存储未作为常规的基于云的邮箱进行解析。</span><span class="sxs-lookup"><span data-stu-id="df98c-157">This is required to search the cloud-based storage for on-premises users because this cloud-based storage doesn't resolve as a regular cloud-based mailbox.</span></span>

    <span data-ttu-id="df98c-158">以下示例在 Sara Davis 基于云的存储中搜索包含关键字“redstone”的 Teams 聊天，Sara Davis 是 Contoso 组织内的本地用户。</span><span class="sxs-lookup"><span data-stu-id="df98c-158">The following example searches for Teams chats that contain keyword "redstone" in the cloud-based storage for Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND (kind:im AND kind:microsoftteams)" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="df98c-159">创建搜索后，请务必使用 **Start-ComplianceSearch** cmdlet 运行搜索。</span><span class="sxs-lookup"><span data-stu-id="df98c-159">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span>
  
<span data-ttu-id="df98c-160">有关使用这些 cmdlet 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="df98c-160">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="df98c-161">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="df98c-161">New-ComplianceSearch</span></span>](/powershell/module/exchange/new-compliancesearch)

- [<span data-ttu-id="df98c-162">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="df98c-162">Set-ComplianceSearch</span></span>](/powershell/module/exchange/set-compliancesearch)

- [<span data-ttu-id="df98c-163">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="df98c-163">Start-ComplianceSearch</span></span>](/powershell/module/exchange/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="df98c-164">已知问题</span><span class="sxs-lookup"><span data-stu-id="df98c-164">Known issues</span></span>

- <span data-ttu-id="df98c-165">目前，你可以搜索、预览和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="df98c-165">Currently, you can search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="df98c-166">你还可以将本地用户的 Teams 聊天数据置于与核心和高级电子数据展示事例关联的保留中，并应用本地用户的 Teams 聊天或频道消息的保留策略。</span><span class="sxs-lookup"><span data-stu-id="df98c-166">You can also place the Teams chat data for an on-premises user on a hold associated with a Core or Advanced eDiscovery case, and apply a retention policy for Teams chats or channel messages for on-premises users.</span></span> <span data-ttu-id="df98c-167">但是，目前无法应用本地用户其他内容位置（如 Exchange 邮箱和 SharePoint 网站）的保留策略。</span><span class="sxs-lookup"><span data-stu-id="df98c-167">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="df98c-168">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="df98c-168">Frequently asked questions</span></span>

<span data-ttu-id="df98c-169">**是否必须提交支持请求才能搜索本地用户的聊天消息？**</span><span class="sxs-lookup"><span data-stu-id="df98c-169">**Do I have to submit a support request to search for chat messages for on-premises users?**</span></span>

<span data-ttu-id="df98c-170">否。</span><span class="sxs-lookup"><span data-stu-id="df98c-170">No.</span></span> <span data-ttu-id="df98c-171">将默认为所有组织启用此功能。</span><span class="sxs-lookup"><span data-stu-id="df98c-171">This feature is enabled by default for all organizations.</span></span> <span data-ttu-id="df98c-172">你曾经不得不联系 Microsoft 支持部门，但这种情况不再发生。</span><span class="sxs-lookup"><span data-stu-id="df98c-172">At one point, you did have to contact Microsoft Support but that is no longer the case.</span></span>
  
 <span data-ttu-id="df98c-173">**在为所有组织默认启用此功能之前，电子数据展示工具能否查找本地用户的较早 Teams 聊天数据？**</span><span class="sxs-lookup"><span data-stu-id="df98c-173">**Can eDiscovery tools find older Teams chat data for on-premises users before the time that this feature was enabled by default for all organizations?**</span></span>
  
<span data-ttu-id="df98c-p116">Microsoft 从 2018 年 1 月 31 日开始存储本地用户的 Teams 聊天数据。因此，如果自此日期以来在本地 Active Directory 和 Microsoft 365 中的 Azure Active Directory 之间同步了本地 Teams 用户的标识，则他们的 Teams 聊天数据存储在云中，并且可使用电子数据展示工具进行搜索。</span><span class="sxs-lookup"><span data-stu-id="df98c-p116">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018. So, if the identity of an on-premises Teams user has been synched between you on-premises Active Directory and Azure Active Directory in Microsoft 365 since this date, then their Teams chat data is stored in the cloud and is searchable using eDiscovery tools.</span></span>

 <span data-ttu-id="df98c-176">**本地用户是否需要许可证才能将他们的 Teams 聊天数据存储在云中？**</span><span class="sxs-lookup"><span data-stu-id="df98c-176">**Do on-premises users need a license to store their Teams chat data in the cloud?**</span></span>
  
<span data-ttu-id="df98c-p117">是的。若要将本地用户的 Teams 聊天数据存储在基于云的存储中，必须在 Office 365（或 Microsoft 365）中为该用户分配 Microsoft Teams 许可证和 Exchange Online 计划许可证。</span><span class="sxs-lookup"><span data-stu-id="df98c-p117">Yes. To store Teams chat data for an on-premises user in a cloud-based storage, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>

<span data-ttu-id="df98c-179">**本地用户基于云的邮箱位于何处？**</span><span class="sxs-lookup"><span data-stu-id="df98c-179">**Where is the cloud-based storage for on-premises users located?**</span></span>
  
<span data-ttu-id="df98c-180">Teams 聊天数据存储在本地用户的“首选数据位置”（PDL）中。</span><span class="sxs-lookup"><span data-stu-id="df98c-180">Teams chat data is stored in the Preferred Data Location (PDL) for an on-premises user.</span></span> <span data-ttu-id="df98c-181">PDL 同时在单一地理和多地理环境中都授予支持。</span><span class="sxs-lookup"><span data-stu-id="df98c-181">The PDL is honored in both Single-Geo and Multi-Geo environments.</span></span> <span data-ttu-id="df98c-182">有关详细信息，请参阅 [Microsoft 365 多地理位置](../enterprise/microsoft-365-multi-geo.md)。</span><span class="sxs-lookup"><span data-stu-id="df98c-182">For more information, see [Microsoft 365 Multi-Geo](../enterprise/microsoft-365-multi-geo.md).</span></span>

<span data-ttu-id="df98c-183">**如果将用户的本地邮箱迁移到云，是否有丢失 Teams 聊天数据的风险？**</span><span class="sxs-lookup"><span data-stu-id="df98c-183">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="df98c-p119">没有。将本地用户的主邮箱迁移到云后，该用户的 Teams 聊天数据将迁移到其基于云的新主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="df98c-p119">No. When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="df98c-186">**是否可以为本地用户应用电子数据展示保留或保留策略？**</span><span class="sxs-lookup"><span data-stu-id="df98c-186">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="df98c-187">是。</span><span class="sxs-lookup"><span data-stu-id="df98c-187">Yes.</span></span> <span data-ttu-id="df98c-188">你可以应用本地用户的 Team 聊天和频道消息的电子数据展示保留或保留策略。</span><span class="sxs-lookup"><span data-stu-id="df98c-188">You can apply eDiscovery holds or retention policies for Teams chats and channel messages of on-premises users.</span></span> <span data-ttu-id="df98c-189">但是，若要保留本地用户的 Teams 内容，必须为本地用户分配 Exchange Online 计划 2 许可证。</span><span class="sxs-lookup"><span data-stu-id="df98c-189">However, to preserve or retain Teams content for on-premises users, an on-premises user must be assigned an Exchange Online Plan 2 license.</span></span>
