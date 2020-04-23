---
title: 搜索本地用户基于云的邮箱
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
description: 在 Exchange 混合部署中，使用安全与合规中心中的内容搜索工具搜索并导出本地用户的 MicrosoftTeams 聊天数据（称为 1xN 聊天）。
ms.openlocfilehash: 9dc9219d6ef1a387e1514deb672386d7d3c18290
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43626448"
---
# <a name="searching-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="aad2b-103">搜索本地用户基于云的邮箱</span><span class="sxs-lookup"><span data-stu-id="aad2b-103">Searching cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="aad2b-104">如果你的组织具有 Exchange 混合部署（或者贵组织已将本地 Exchange 组织与 Office 365 同步），并且已启用 Microsoft Teams，则用户可以使用 Teams 聊天应用程序进行即时消息传递。</span><span class="sxs-lookup"><span data-stu-id="aad2b-104">If your organization has an Exchange hybrid deployment (or your organization synchronizes an on-premises Exchange organization with Office 365) and has enabled Microsoft Teams, users can use the Teams chat application for instant messaging.</span></span> <span data-ttu-id="aad2b-105">对于基于云的用户，Teams 聊天数据（也称为 *1xN 聊天*）将保存到其基于云的主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="aad2b-105">For a cloud-based user, the Teams chat data (also called *1xN chats*) is saved to their primary cloud-based mailbox.</span></span> <span data-ttu-id="aad2b-106">当本地用户使用 Teams 聊天应用程序时，其主邮箱位于本地。</span><span class="sxs-lookup"><span data-stu-id="aad2b-106">When an on-premises user uses the Team chat application, their primary mailbox is located on-premises.</span></span> <span data-ttu-id="aad2b-107">为了绕开此限制，Microsoft 发布了一项新功能，其中创建了基于云的存储区域（称为本地用户基于云的邮箱），用于存储本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-107">To get around this limitation, Microsoft has released a new feature where a cloud-based storage area (called a cloud-based mailbox for on-premises users) is created to store Teams chat data for on-premises users.</span></span> <span data-ttu-id="aad2b-108">这让你能够使用安全与合规中心中的内容搜索工具来搜索并导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-108">This lets you use the Content Search tool in the Security & Compliance Center to search and export Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="aad2b-109">以下是设置本地用户基于云的邮箱的要求和限制：</span><span class="sxs-lookup"><span data-stu-id="aad2b-109">Here are the requirements and limitations for setting up cloud-based mailboxes for on-premises users:</span></span>
  
- <span data-ttu-id="aad2b-110">本地目录服务（如 Active Directory）中的用户帐户必须与 Azure Active Directory（Microsoft 365 中的目录服务）同步。</span><span class="sxs-lookup"><span data-stu-id="aad2b-110">The user accounts in your on-premises directory service (such as Active Directory) must be synchronized with Azure Active Directory, the directory service in Microsoft 365.</span></span> <span data-ttu-id="aad2b-111">这意味着将在 Microsoft 365 中创建一个邮件用户帐户，并将该帐户与其主邮箱位于本地组织中的用户相关联。</span><span class="sxs-lookup"><span data-stu-id="aad2b-111">This means that a mail user account is created in Microsoft 365 and is associated with a user whose primary mailbox is located in the on-premises organization.</span></span>

- <span data-ttu-id="aad2b-112">必须为其主邮箱位于本地组织中的用户分配 Microsoft Teams 许可证和 Exchange Online 计划 1 许可证（最低要求）。</span><span class="sxs-lookup"><span data-stu-id="aad2b-112">The user whose primary mailbox is located in the on-premises organization must be assigned a Microsoft Teams license and a minimum of an Exchange Online Plan 1 license.</span></span>

- <span data-ttu-id="aad2b-113">本地用户基于云的邮箱仅用于存储 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-113">The cloud-based mailbox for on-premises users is used only store Teams chat data.</span></span> <span data-ttu-id="aad2b-114">本地用户不能以任何方式登录或访问基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-114">An on-premises user can't sign in to the cloud-based mailbox or access in any way.</span></span> <span data-ttu-id="aad2b-115">它不能用于发送或接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="aad2b-115">It can't be used to send or receive email messages.</span></span> 

- <span data-ttu-id="aad2b-116">你必须向 Microsoft 支持人员提交请求，以使贵组织能够在本地用户基于云的邮箱中搜索 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-116">You have to submit a request to Microsoft Support to enable your organization to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="aad2b-117">请参阅本文中的[向 Microsoft 支持人员提交启用此功能的请求](#filing-a-request-with-microsoft-support-to-enable-this-feature)部分。</span><span class="sxs-lookup"><span data-stu-id="aad2b-117">See [Filing a request with Microsoft Support to enable this feature](#filing-a-request-with-microsoft-support-to-enable-this-feature) in this article.</span></span> 

> [!NOTE]
> <span data-ttu-id="aad2b-118">Teams 频道对话始终存储在与 Teams 关联的基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="aad2b-118">Teams channel conversations are always stored in the cloud-based mailbox that's associated with the Team.</span></span> <span data-ttu-id="aad2b-119">这意味着您可以使用内容搜索来搜索频道对话，而无需提交支持请求。</span><span class="sxs-lookup"><span data-stu-id="aad2b-119">That means you can use Content Search to search channel conversations without have to file a support request.</span></span> <span data-ttu-id="aad2b-120">有关搜索 Teams 频道对话的详细信息，请参阅[搜索 Microsoft Teams 和 Microsoft 365 组](content-search.md#searching-microsoft-teams-and-microsoft-365-groups)。</span><span class="sxs-lookup"><span data-stu-id="aad2b-120">For more information about searching Teams channel conversations, see [Searching Microsoft Teams and Microsoft 365 Groups](content-search.md#searching-microsoft-teams-and-microsoft-365-groups).</span></span>
  
## <a name="how-it-works"></a><span data-ttu-id="aad2b-121">工作原理</span><span class="sxs-lookup"><span data-stu-id="aad2b-121">How it works</span></span>

<span data-ttu-id="aad2b-122">如果已启用 Microsoft Teams 的用户拥有本地邮箱，并且其用户帐户/标识已同步到云端，则 Microsoft 将创建基于云的邮箱来存储 1xN Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-122">If a Microsoft Teams-enabled user has an on-premises mailbox and their user account/identity has been synched to the cloud, Microsoft creates a cloud-based mailbox to store 1xN Teams chat data.</span></span> <span data-ttu-id="aad2b-123">将 Teams 聊天数据存储在基于云的邮箱中后，系统会将其编入索引以供搜索。</span><span class="sxs-lookup"><span data-stu-id="aad2b-123">After the Teams chat data is stored in the cloud-based mailbox, it's indexed for search.</span></span> <span data-ttu-id="aad2b-124">这让你能够使用内容搜索（以及与电子数据展示事例关联的搜索）来搜索、预览和导出本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-124">This lets you Use Content Search (and searches associated with eDiscovery cases) to search, preview, and export Teams chat data for on-premises users.</span></span> <span data-ttu-id="aad2b-125">你还可以使用安全与合规中心 PowerShell 中的 **\*ComplianceSearch** cmdlet 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-125">You can also use **\*ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
<span data-ttu-id="aad2b-126">下图显示了搜索、预览和导出本地用户的 Teams 聊天数据的工作流。</span><span class="sxs-lookup"><span data-stu-id="aad2b-126">The following graphic shows the workflow of how Teams chat data for on-premises users is available to search, preview, and export.</span></span>
  
![Microsoft Teams 中的本地用户基于云的存储空间](../media/895845f8-2ceb-47ed-96c9-5ab7f1aea916.png)
  
<span data-ttu-id="aad2b-128">除了此新功能之外，你仍可以使用内容搜索在基于云的 SharePoint 网站和与每个 Microsoft Team 关联的 Exchange 邮箱中搜索、预览和导出 Teams 内容，以及在基于云的用户的 Exchange Online 邮箱中搜索、预览和导出 1xN Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-128">In addition to this new capability, you can still use Content Search to search, preview, and export Teams content in the cloud-based SharePoint site and Exchange mailbox associated with each Microsoft Team and 1xN Teams chat data in the Exchange Online mailbox for cloud-based users.</span></span>

## <a name="filing-a-request-with-microsoft-support-to-enable-this-feature"></a><span data-ttu-id="aad2b-129">向 Microsoft 支持人员提交启用此功能的请求</span><span class="sxs-lookup"><span data-stu-id="aad2b-129">Filing a request with Microsoft Support to enable this feature</span></span>

<span data-ttu-id="aad2b-130">你必须向 Microsoft 支持人员提交请求，以使贵组织能够使用安全与合规中心中的图形用户界面来搜索本地用户基于云的邮箱中的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-130">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="aad2b-131">此功能在安全与合规中心 PowerShell 中提供。</span><span class="sxs-lookup"><span data-stu-id="aad2b-131">This feature is available in Security & Compliance Center PowerShell.</span></span> <span data-ttu-id="aad2b-132">无需提交支持请求即可使用 PowerShell 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-132">You don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span>
  
<span data-ttu-id="aad2b-133">向 Microsoft 支持人员提交请求时，请包含以下信息：</span><span class="sxs-lookup"><span data-stu-id="aad2b-133">Include the following information when you submit the request to Microsoft Support:</span></span>
  
- <span data-ttu-id="aad2b-134">组织的默认域名。</span><span class="sxs-lookup"><span data-stu-id="aad2b-134">The default domain name of your organization.</span></span>

- <span data-ttu-id="aad2b-135">组织的租户名称和租户 ID。</span><span class="sxs-lookup"><span data-stu-id="aad2b-135">The tenant name and tenant ID of your organization.</span></span> <span data-ttu-id="aad2b-136">可在 Azure Active Directory 门户中找到这些信息（位于“**管理**”\>“**属性**下）。</span><span class="sxs-lookup"><span data-stu-id="aad2b-136">You can find these in the Azure Active Directory portal (under **Manage** \> **Properties**).</span></span> <span data-ttu-id="aad2b-137">请参阅[查找 Microsoft 365 租户 ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b)。</span><span class="sxs-lookup"><span data-stu-id="aad2b-137">See [Find your Microsoft 365 tenant ID](https://support.office.com/article/6891b561-a52d-4ade-9f39-b492285e2c9b).</span></span>

- <span data-ttu-id="aad2b-138">可在支持请求中使用以下标题或说明：“为本地用户启用应用程序内容搜索”。</span><span class="sxs-lookup"><span data-stu-id="aad2b-138">The following title or description of the purpose of the support request: "Enable Application Content Search for On-premises Users".</span></span> <span data-ttu-id="aad2b-139">这有助于将请求传送到将实现请求的电子数据展示工程团队。</span><span class="sxs-lookup"><span data-stu-id="aad2b-139">This helps route the request to the eDiscovery engineering team who will implement the request.</span></span>

<span data-ttu-id="aad2b-140">执行工程更改后，Microsoft 支持人员将向你发送预计的部署日期。</span><span class="sxs-lookup"><span data-stu-id="aad2b-140">After the engineering change is made, Microsoft Support will send you an estimated deployment date.</span></span> <span data-ttu-id="aad2b-141">在提交支持请求后，部署过程通常需要 2 到 3 周的时间。</span><span class="sxs-lookup"><span data-stu-id="aad2b-141">The deployment process usually takes 2–3 weeks after you submit the support request.</span></span>
  
### <a name="what-happens-after-this-feature-is-enabled"></a><span data-ttu-id="aad2b-142">启用此功能后会发生什么情况？</span><span class="sxs-lookup"><span data-stu-id="aad2b-142">What happens after this feature is enabled?</span></span>

<span data-ttu-id="aad2b-143">在组织中部署此功能后，将在安全与合规中心中的内容搜索以及与电子数据展示事例关联的搜索中进行以下更改：</span><span class="sxs-lookup"><span data-stu-id="aad2b-143">After this feature is deployed in your organization, the following changes are made in Content Search and in searches associated with an eDiscovery case in the Security & Compliance Center:</span></span>
  
- <span data-ttu-id="aad2b-144">在内容搜索的“**位置**”下方添加“**为本地用户添加 Office 应用内容**”复选框。</span><span class="sxs-lookup"><span data-stu-id="aad2b-144">The **Add Office app content for on-premises users** checkbox is added under the **Locations** in Content Search.</span></span>

    ![向内容搜索 UI 添加“为本地用户添加 Office 应用内容”复选框](../media/599e751e-17bd-408d-a18c-127538de6e85.png)
  
- <span data-ttu-id="aad2b-146">本地用户显示在内容位置选取器中，你可以使用它选择要搜索的用户邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-146">On-premises users are displayed in the content locations picker that you use to select user mailboxes to search.</span></span>

## <a name="searching-for-teams-chat-content-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="aad2b-147">搜索本地用户基于云的邮箱中的 Teams 聊天内容</span><span class="sxs-lookup"><span data-stu-id="aad2b-147">Searching for Teams chat content in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="aad2b-148">启用此功能后，可使用安全与合规中心中的内容搜索来搜索本地用户基于云的邮箱中的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-148">After the feature has been enabled, you can use Content Search in the Security & Compliance Center to search for Teams chat data in the cloud-based mailboxes for on-premises users.</span></span>
  
1. <span data-ttu-id="aad2b-149">在安全与合规中心，转到“**搜索**”\>“**内容搜索**”</span><span class="sxs-lookup"><span data-stu-id="aad2b-149">In the Security & Compliance Center, go to **Search** \> **Content search**</span></span>

2. <span data-ttu-id="aad2b-150">在“**搜索**”页面上，单击“![添加”图标](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif)“**新建搜索**”。</span><span class="sxs-lookup"><span data-stu-id="aad2b-150">On the **Search** page, click ![Add icon](../media/8ee52980-254b-440b-99a2-18d068de62d3.gif) **New search**.</span></span>

    <span data-ttu-id="aad2b-151">如前文所述，“**为本地用户添加 Office 应用内容**”复选框显示在“**位置**”下方。</span><span class="sxs-lookup"><span data-stu-id="aad2b-151">As previously explained, the **Add Office app content for on-premises users** checkbox is displayed under **Locations**.</span></span> <span data-ttu-id="aad2b-152">它在默认情况下处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="aad2b-152">It's selected by default.</span></span>

3. <span data-ttu-id="aad2b-153">创建关键字查询并为搜索查询添加条件（如有必要）。</span><span class="sxs-lookup"><span data-stu-id="aad2b-153">Create the keyword query and add conditions to the search query if necessary.</span></span> <span data-ttu-id="aad2b-154">若要仅搜索 Teams 聊天数据，可在“**关键字**”框中添加以下查询：</span><span class="sxs-lookup"><span data-stu-id="aad2b-154">To only search for Team chats data, you can add the following query in the **Keywords** box:</span></span>

    ```text
    kind:im
    ```

4. <span data-ttu-id="aad2b-155">目前，可在“**位置**”下选择以下选项之一：</span><span class="sxs-lookup"><span data-stu-id="aad2b-155">At this point, you can choose one of the following options under **Locations**:</span></span>

    - <span data-ttu-id="aad2b-156">**所有位置**：选择此选项可搜索组织中所有用户的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-156">**All locations:** Select this option to search the mailboxes of all users in your organization.</span></span> <span data-ttu-id="aad2b-157">选中该复选框时，还将搜索本地用户的所有基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-157">When the checkbox is selected, all cloud-based mailboxes for on-premises users will also be searched.</span></span>

    - <span data-ttu-id="aad2b-158">**特定位置**：选择此选项，然后单击“**修改**”\> 选择用户、组或团队以搜索特定邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-158">**Specific locations:** Select this option and then click **Modify** \> Choose user, groups, or teams to search specific mailboxes.</span></span> <span data-ttu-id="aad2b-159">如前文所述，位置选取器可用于搜索本地用户。</span><span class="sxs-lookup"><span data-stu-id="aad2b-159">As previously explained, the locations picker lets you search for on-premises users.</span></span>

5. <span data-ttu-id="aad2b-160">保存并运行搜索。</span><span class="sxs-lookup"><span data-stu-id="aad2b-160">Save and run the search.</span></span> <span data-ttu-id="aad2b-161">可像预览任何其他搜索结果一样预览本地用户基于云的邮箱中的任何搜索结果。</span><span class="sxs-lookup"><span data-stu-id="aad2b-161">Any search results from the cloud-based mailboxes for on-premises users can be previewed like any other search results.</span></span> <span data-ttu-id="aad2b-162">你还可以将搜索结果（包括任何 Teams 聊天数据）导出到 PST 文件。</span><span class="sxs-lookup"><span data-stu-id="aad2b-162">You can also export the search results (including any Teams chat data) to a PST file.</span></span> <span data-ttu-id="aad2b-163">有关详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="aad2b-163">For more information, see:</span></span> 

    - [<span data-ttu-id="aad2b-164">创建搜索</span><span class="sxs-lookup"><span data-stu-id="aad2b-164">Create a search</span></span>](content-search.md#create-a-search)

    - [<span data-ttu-id="aad2b-165">预览搜索结果</span><span class="sxs-lookup"><span data-stu-id="aad2b-165">Preview search results</span></span>](content-search.md#preview-search-results)

    - [<span data-ttu-id="aad2b-166">导出内容搜索结果</span><span class="sxs-lookup"><span data-stu-id="aad2b-166">Export Content Search results</span></span>](export-search-results.md)

## <a name="using-powershell-to-search-for-teams-chat-data-in-cloud-based-mailboxes-for-on-premises-users"></a><span data-ttu-id="aad2b-167">使用 PowerShell 搜索本地用户基于云的邮箱中的 Teams 聊天数据</span><span class="sxs-lookup"><span data-stu-id="aad2b-167">Using PowerShell to search for Teams chat data in cloud-based mailboxes for on-premises users</span></span>

<span data-ttu-id="aad2b-168">你可以使用安全与合规中心 PowerShell 中的 **New-ComplianceSearch** 和 **Set-ComplianceSearch** cmdlet 来搜索本地用户基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-168">You can use the **New-ComplianceSearch** and **Set-ComplianceSearch** cmdlets in the Security & Compliance Center PowerShell to search the cloud-based mailbox for on-premises users.</span></span> <span data-ttu-id="aad2b-169">如前文所述，无需提交支持请求即可使用 PowerShell 来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-169">As previously explained, you don't have to submit a support request to use PowerShell to search for Teams chat data for on-premises users.</span></span> 
  
1. <span data-ttu-id="aad2b-170">[连接到安全与合规中心 PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell)。</span><span class="sxs-lookup"><span data-stu-id="aad2b-170">[Connect to Security & Compliance Center PowerShell](https://docs.microsoft.com/powershell/exchange/office-365-scc/connect-to-scc-powershell/connect-to-scc-powershell).</span></span>

2. <span data-ttu-id="aad2b-171">运行以下 PowerShell 命令以创建用于搜索本地用户基于云的邮箱的内容搜索。</span><span class="sxs-lookup"><span data-stu-id="aad2b-171">Run the following PowerShell command to create a content search that searches the cloud-based mailboxes of on-premises users.</span></span>

    ```powershell
    New-ComplianceSearch <name of new search> -ContentMatchQuery <search query> -ExchangeLocation <on-premises user> -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

    <span data-ttu-id="aad2b-172">*IncludeUserAppContent* 参数用于为由 *ExchangeLocation* 参数指定的一个或多个用户指定基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-172">The *IncludeUserAppContent*  parameter is used to specify the cloud-based mailbox for the user or users who are specified by the  *ExchangeLocation*  parameter.</span></span> <span data-ttu-id="aad2b-173">*AllowNotFoundExchangeLocationsEnabled* 允许本地用户使用基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-173">The  *AllowNotFoundExchangeLocationsEnabled*  allows cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="aad2b-174">使用此参数的 `$true` 值时，搜索不会在运行之前尝试验证邮箱是否存在。</span><span class="sxs-lookup"><span data-stu-id="aad2b-174">When you use the `$true` value for this parameter, the search doesn't try to validate the existence of the mailbox before it runs.</span></span> <span data-ttu-id="aad2b-175">这是搜索本地用户基于云的邮箱所必需的，因为这些类型的邮箱无法解析为常规邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-175">This is required to search the cloud-based mailboxes for on-premises users because these types of mailboxes don't resolve as regular mailboxes.</span></span>

    <span data-ttu-id="aad2b-176">以下示例在 Sara Davis 基于云的邮箱中搜索包含关键字“redstone”的 Teams 聊天（它们是即时消息），Sara Davis 是 Contoso 组织内的本地用户。</span><span class="sxs-lookup"><span data-stu-id="aad2b-176">The following example searches for Teams chats (which are instant messages) that contain keyword "redstone" in the cloud-based mailbox of Sara Davis, who is an on-premises user in the Contoso organization.</span></span>
  
    ```powershell
    New-ComplianceSearch "Redstone_Search" -ContentMatchQuery "redstone AND kind:im" -ExchangeLocation sarad@contoso.com -IncludeUserAppContent $true -AllowNotFoundExchangeLocationsEnabled $true  
    ```

   <span data-ttu-id="aad2b-177">创建搜索后，请务必使用 **Start-ComplianceSearch** cmdlet 运行搜索。</span><span class="sxs-lookup"><span data-stu-id="aad2b-177">After you create a search, be sure to use the **Start-ComplianceSearch** cmdlet to run the search.</span></span> 
  
<span data-ttu-id="aad2b-178">有关使用这些 cmdlet 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="aad2b-178">For more information using these cmdlets, see:</span></span>
  
- [<span data-ttu-id="aad2b-179">New-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="aad2b-179">New-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/new-compliancesearch)

- [<span data-ttu-id="aad2b-180">Set-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="aad2b-180">Set-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/set-compliancesearch)

- [<span data-ttu-id="aad2b-181">Start-ComplianceSearch</span><span class="sxs-lookup"><span data-stu-id="aad2b-181">Start-ComplianceSearch</span></span>](https://docs.microsoft.com/powershell/module/exchange/policy-and-compliance-content-search/start-compliancesearch)

## <a name="known-issues"></a><span data-ttu-id="aad2b-182">已知问题</span><span class="sxs-lookup"><span data-stu-id="aad2b-182">Known issues</span></span>

- <span data-ttu-id="aad2b-183">目前，你可以在本地用户基于云的邮箱中搜索、预览和导出内容。</span><span class="sxs-lookup"><span data-stu-id="aad2b-183">Currently, you can search, preview, and export content in cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="aad2b-184">你还可以将本地用户基于云的邮箱置于与电子数据展示事例关联的保留中，并将 Teams 聊天或频道消息的保留策略应用于本地用户基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-184">You can also place a cloud-based mailbox for an on-premises user on a hold associated with an eDiscovery case, and apply a retention policy for Teams chats or channel messages to cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="aad2b-185">但是，目前无法将其他内容位置（如 Exchange 邮箱和 SharePoint 网站）的保留策略应用于本地用户基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-185">However at this time, you can't apply a retention policy for other content locations (such as Exchange mailboxes and SharePoint sites) to cloud-based mailboxes for on-premises users.</span></span>

## <a name="frequently-asked-questions"></a><span data-ttu-id="aad2b-186">常见问题</span><span class="sxs-lookup"><span data-stu-id="aad2b-186">Frequently asked questions</span></span>

 <span data-ttu-id="aad2b-187">**本地用户基于云的邮箱位于何处？**</span><span class="sxs-lookup"><span data-stu-id="aad2b-187">**Where are cloud-based mailboxes for on-premises users located?**</span></span>
  
<span data-ttu-id="aad2b-188">基于云的邮箱是在与组织相同的数据中心中创建并存储的。</span><span class="sxs-lookup"><span data-stu-id="aad2b-188">Cloud-based mailboxes are created and stored in the same datacenter as your organization.</span></span>
  
 <span data-ttu-id="aad2b-189">**除了提交支持请求以外，还有其他要求吗？**</span><span class="sxs-lookup"><span data-stu-id="aad2b-189">**Are there any other requirements other than submitting a support request?**</span></span>
  
 <span data-ttu-id="aad2b-190">如前文所述，必须将具有本地邮箱的用户标识同步到基于云的组织，以便为 Office 365 中的每个本地用户帐户创建对应的邮件用户帐户。</span><span class="sxs-lookup"><span data-stu-id="aad2b-190">As previously explained, the identities of users with on-prem mailboxes must be synchronized to your cloud-based organization so that a corresponding mail user account is created for each on-premises user account in Office 365.</span></span> <span data-ttu-id="aad2b-191">你的组织还必须具有 Office 365 企业版订阅，例如 Office 365 企业版 E1、E3 或 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="aad2b-191">Your organization must also have an Office 365 enterprise subscription, such as an Office 365 Enterprise E1, E3, or E5 subscription.</span></span>
  
 <span data-ttu-id="aad2b-192">**如果将用户的本地邮箱迁移到云，是否有丢失 Teams 聊天数据的风险？**</span><span class="sxs-lookup"><span data-stu-id="aad2b-192">**Is there a risk of losing the Teams chat data if the user's on-premises mailbox is migrated to the cloud?**</span></span>
  
<span data-ttu-id="aad2b-193">否。</span><span class="sxs-lookup"><span data-stu-id="aad2b-193">No.</span></span> <span data-ttu-id="aad2b-194">将本地用户的主邮箱迁移到云后，该用户的 Teams 聊天数据将迁移到其基于云的新主邮箱中。</span><span class="sxs-lookup"><span data-stu-id="aad2b-194">When you migrate the primary mailbox of an on-premises user to the cloud, the Teams chat data for that user will be migrated to their new cloud-based primary mailbox.</span></span>
  
 <span data-ttu-id="aad2b-195">**是否可以为本地用户应用电子数据展示保留或保留策略？**</span><span class="sxs-lookup"><span data-stu-id="aad2b-195">**Can I apply an eDiscovery hold or retention policies to on-premises users?**</span></span>
  
<span data-ttu-id="aad2b-196">可以。</span><span class="sxs-lookup"><span data-stu-id="aad2b-196">Yes.</span></span> <span data-ttu-id="aad2b-197">你可以将 Team 聊天和频道消息的电子数据展示保留或保留策略应用于本地用户基于云的邮箱。</span><span class="sxs-lookup"><span data-stu-id="aad2b-197">You can apply eDiscovery holds or retention policies for Teams chats and channel messages to cloud-based mailboxes for on-premises users.</span></span>
  
 <span data-ttu-id="aad2b-198">**在组织提交启用此功能的请求之前，内容搜索是否可以找到本地用户较早的 Teams 聊天？**</span><span class="sxs-lookup"><span data-stu-id="aad2b-198">**Can Content Search find older Teams chats for on-premises users before the time my organization submitted the request to enable this feature?**</span></span>
  
<span data-ttu-id="aad2b-199">Microsoft 从 2018 年 1 月 31 日开始存储本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="aad2b-199">Microsoft started storing the Teams chat data for on-premises users on January 31, 2018.</span></span> <span data-ttu-id="aad2b-200">因此，如果自此日期以来在 Active Directory 和 Azure Active Directory 之间同步了本地 Teams 用户的标识，则他们的 Teams 聊天数据存储在基于云的邮箱中，并且可使用内容搜索进行搜索。</span><span class="sxs-lookup"><span data-stu-id="aad2b-200">So, if the identity of an on-premises Teams user has been synched between Active Directory and Azure Active Directory since this date, then their Teams chat data is stored in a cloud-based mailbox and is searchable using Content Search.</span></span> <span data-ttu-id="aad2b-201">此外，Microsoft 正致力于将 2018 年 1 月 31 日之前的 Teams 聊天数据存储在本地用户基于云的邮箱中。</span><span class="sxs-lookup"><span data-stu-id="aad2b-201">Microsoft is also working on storing Teams chat data from prior to January 31, 2018 in the cloud-based mailboxes for on-premises users.</span></span> <span data-ttu-id="aad2b-202">即将提供与此相关的详细信息。</span><span class="sxs-lookup"><span data-stu-id="aad2b-202">More information about this will be available soon.</span></span>

 <span data-ttu-id="aad2b-203">**本地用户是否需要许可证才能将 Teams 聊天数据存储在基于云的邮箱中？**</span><span class="sxs-lookup"><span data-stu-id="aad2b-203">**Do on-premises users need a license to store Teams chat data in a cloud-based mailbox?**</span></span>
  
<span data-ttu-id="aad2b-204">是。</span><span class="sxs-lookup"><span data-stu-id="aad2b-204">Yes.</span></span> <span data-ttu-id="aad2b-205">若要将本地用户的 Teams 聊天数据存储在基于云的邮箱中，必须在 Office 365（或 Microsoft 365）中为该用户分配 Microsoft Teams 许可证和 Exchange Online 计划许可证。</span><span class="sxs-lookup"><span data-stu-id="aad2b-205">To store Teams chat data for an on-premises user in a cloud-based mailbox, the user must be assigned a Microsoft Teams license and an Exchange Online Plan license in Office 365 (or Microsoft 365).</span></span>
