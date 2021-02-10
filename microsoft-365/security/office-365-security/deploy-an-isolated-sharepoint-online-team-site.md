---
title: 部署独立的 SharePoint Online 团队网站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 07/30/2019
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 使用此分步部署指南在 Microsoft Office 365 中创建和配置独立的 SharePoint Online 团队网站。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 1b1f0342afc92b4540330417ad0fc9cabe1dc8a8
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50165495"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="b1f10-103">部署独立的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="b1f10-103">Deploy an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="b1f10-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="b1f10-104">**Applies to**</span></span>
- [<span data-ttu-id="b1f10-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="b1f10-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="b1f10-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b1f10-106">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="b1f10-107">**摘要：** 使用这些分步说明部署新的独立 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="b1f10-107">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>

<span data-ttu-id="b1f10-108">本文是一个分步部署指南，用于创建和配置 Microsoft Office 365 中的独立 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="b1f10-108">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="b1f10-109">这些步骤假定使用三个默认的 SharePoint 组和相应的权限级别，每个访问级别具有一个 Azure Active Directory (AD) 基于 AD 的访问组。</span><span class="sxs-lookup"><span data-stu-id="b1f10-109">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>

## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="b1f10-110">阶段 1：创建和填充团队网站访问组</span><span class="sxs-lookup"><span data-stu-id="b1f10-110">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="b1f10-111">在此阶段，为三个默认 SharePoint 组创建三个基于 Azure AD 的访问组，并使用相应的用户帐户填充它们。</span><span class="sxs-lookup"><span data-stu-id="b1f10-111">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>

> [!NOTE]
> <span data-ttu-id="b1f10-112">以下步骤假定所有必需的用户帐户已经存在，并分配有相应的许可证。</span><span class="sxs-lookup"><span data-stu-id="b1f10-112">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="b1f10-113">如果没有，请在继续步骤 1 之前添加它们并分配许可证。</span><span class="sxs-lookup"><span data-stu-id="b1f10-113">If not, please add them and assign licenses before proceeding to step 1.</span></span>

### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="b1f10-114">步骤 1：列出网站的 SharePoint Online 管理员</span><span class="sxs-lookup"><span data-stu-id="b1f10-114">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="b1f10-115">确定对应于独立团队网站的 SharePoint Online 管理员的用户帐户集。</span><span class="sxs-lookup"><span data-stu-id="b1f10-115">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>

<span data-ttu-id="b1f10-116">如果通过 Microsoft 365 管理用户帐户和组，并且希望使用 Windows PowerShell，请列出其用户主体名称 (UPN)  (UPN：belindan@contoso.com) 。</span><span class="sxs-lookup"><span data-stu-id="b1f10-116">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>

### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="b1f10-117">步骤 2：列出网站的成员</span><span class="sxs-lookup"><span data-stu-id="b1f10-117">Step 2: List the members for the site</span></span>

<span data-ttu-id="b1f10-118">确定对应于独立团队网站的成员（将协作处理网站中存储的资源的成员）的用户帐户集。</span><span class="sxs-lookup"><span data-stu-id="b1f10-118">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>

<span data-ttu-id="b1f10-119">如果通过 Microsoft 365 管理用户帐户和组，并且想要使用 PowerShell，请列出其 UPN。</span><span class="sxs-lookup"><span data-stu-id="b1f10-119">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="b1f10-120">如果有很多网站成员，可以将 UPN 列表存储在文本文件中，然后使用单个 PowerShell 命令添加所有 UPN。</span><span class="sxs-lookup"><span data-stu-id="b1f10-120">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="b1f10-121">步骤 3：列出网站的查看者</span><span class="sxs-lookup"><span data-stu-id="b1f10-121">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="b1f10-122">确定对应于独立团队网站的查看者（可以查看网站中存储的资源但不修改它们或直接协作处理其内容）的用户帐户集。</span><span class="sxs-lookup"><span data-stu-id="b1f10-122">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>

<span data-ttu-id="b1f10-123">如果通过 Microsoft 365 管理用户帐户和组，并且想要使用 PowerShell，请列出其 UPN。</span><span class="sxs-lookup"><span data-stu-id="b1f10-123">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="b1f10-124">如果有很多网站成员，可以将 UPN 列表存储在文本文件中，然后使用单个 PowerShell 命令添加所有 UPN。</span><span class="sxs-lookup"><span data-stu-id="b1f10-124">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>

<span data-ttu-id="b1f10-125">网站的查看者可能包括管理层、法律顾问或部门间利益干系人。</span><span class="sxs-lookup"><span data-stu-id="b1f10-125">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>

### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="b1f10-126">步骤 4：在 Azure AD 中为网站创建三个访问组</span><span class="sxs-lookup"><span data-stu-id="b1f10-126">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="b1f10-127">你需要在 Azure AD 中创建以下访问组：</span><span class="sxs-lookup"><span data-stu-id="b1f10-127">You need to create the following access groups in Azure AD:</span></span>

- <span data-ttu-id="b1f10-128">网站管理员 (将包含步骤 1 中的列表) </span><span class="sxs-lookup"><span data-stu-id="b1f10-128">Site admins (which will contain the list from step 1)</span></span>
- <span data-ttu-id="b1f10-129">网站 (将包含步骤 2 中的列表) </span><span class="sxs-lookup"><span data-stu-id="b1f10-129">Site members (which will contain the list from step 2)</span></span>
- <span data-ttu-id="b1f10-130">网站查看 (，其中包含步骤 3 中的) </span><span class="sxs-lookup"><span data-stu-id="b1f10-130">Site viewers (which will contain the list from step 3)</span></span>

1. <span data-ttu-id="b1f10-131">在浏览器中，转到 Azure 门户，然后使用已分配有用户管理管理员或公司管理员角色的帐户凭据 <https://portal.azure.com> 登录。</span><span class="sxs-lookup"><span data-stu-id="b1f10-131">In your browser, go to the Azure portal at <https://portal.azure.com> and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>

2. <span data-ttu-id="b1f10-132">在 Azure 门户中，单击“**Azure Active Directory”>“组**”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-132">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>

3. <span data-ttu-id="b1f10-133">在“**组 - 所有组**”边栏选项卡上，单击“**+ 新建组**”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-133">On the **Groups - All groups** blade, click **+ New group**.</span></span>

4. <span data-ttu-id="b1f10-134">在" **新建组"** 边栏选项卡上：</span><span class="sxs-lookup"><span data-stu-id="b1f10-134">On the **New Group** blade:</span></span>

   - <span data-ttu-id="b1f10-135">在“组类型”中选择“安全性”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-135">Select **Security** in **Group type**.</span></span>

   - <span data-ttu-id="b1f10-136">在名称中键入组 **名称**。</span><span class="sxs-lookup"><span data-stu-id="b1f10-136">Type the group name in **Name**.</span></span>

   - <span data-ttu-id="b1f10-137">在组说明中键入组 **的说明**。</span><span class="sxs-lookup"><span data-stu-id="b1f10-137">Type a description of the group in **Group description**.</span></span>

   - <span data-ttu-id="b1f10-138">在“**成员身份**”类型中，选择“**已分配**”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-138">Select **Assigned** in **Membership type**.</span></span>

5. <span data-ttu-id="b1f10-139">单击“**创建**”，然后关闭“**组**”边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="b1f10-139">Click **Create**, and then close the **Group** blade.</span></span>

6. <span data-ttu-id="b1f10-140">对其他组重复步骤 3-5。</span><span class="sxs-lookup"><span data-stu-id="b1f10-140">Repeat steps 3-5 for your additional groups.</span></span>

> [!NOTE]
> <span data-ttu-id="b1f10-141">你需要使用 Azure 门户创建组，以便启用 Office 功能。</span><span class="sxs-lookup"><span data-stu-id="b1f10-141">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="b1f10-142">如果 SharePoint Online 独立网站稍后被配置为具有 Azure 信息保护标签的高度机密网站，以加密文件并将权限分配给特定组，则必须在启用 Office 功能的情况下创建允许的组。</span><span class="sxs-lookup"><span data-stu-id="b1f10-142">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="b1f10-143">创建 Azure AD 组的 Office 功能设置后，无法更改。</span><span class="sxs-lookup"><span data-stu-id="b1f10-143">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span>

<span data-ttu-id="b1f10-144">下面是使用三个网站访问组生成的配置。</span><span class="sxs-lookup"><span data-stu-id="b1f10-144">Here is your resulting configuration with the three site access groups.</span></span>

![用于部署独立 SharePoint Online 网站的三个访问组。](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)

### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="b1f10-146">步骤 5.</span><span class="sxs-lookup"><span data-stu-id="b1f10-146">Step 5.</span></span> <span data-ttu-id="b1f10-147">将用户帐户添加到访问组</span><span class="sxs-lookup"><span data-stu-id="b1f10-147">Add the user accounts to the access groups</span></span>

<span data-ttu-id="b1f10-148">在此步骤中，执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="b1f10-148">In this step, do the following:</span></span>

1. <span data-ttu-id="b1f10-149">将步骤 1 中的用户列表添加到网站管理员访问组。</span><span class="sxs-lookup"><span data-stu-id="b1f10-149">Add the list of users from step 1 to the site admins access group.</span></span>
2. <span data-ttu-id="b1f10-150">将步骤 2 中的用户列表添加到网站成员访问组。</span><span class="sxs-lookup"><span data-stu-id="b1f10-150">Add the list of users from step 2 to the site members access group.</span></span>
3. <span data-ttu-id="b1f10-151">将步骤 3 中的用户列表添加到网站查看者访问组。</span><span class="sxs-lookup"><span data-stu-id="b1f10-151">Add the list of users from step 3 to the site viewers access group.</span></span>

<span data-ttu-id="b1f10-152">如果通过 Active Directory 域服务 (AD DS) 管理用户帐户和组，则使用正常的 AD DS 用户和组管理过程将用户添加到相应的访问组，并等待与 Microsoft 365 订阅同步。</span><span class="sxs-lookup"><span data-stu-id="b1f10-152">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>

<span data-ttu-id="b1f10-153">如果通过 Office 365 管理用户帐户和组，可以使用 Microsoft 365 管理中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="b1f10-153">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="b1f10-154">如果任何访问组具有重复的组名称，则应该使用 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="b1f10-154">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>

<span data-ttu-id="b1f10-155">对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的用户帐户和组添加到相应的访问组。</span><span class="sxs-lookup"><span data-stu-id="b1f10-155">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>

<span data-ttu-id="b1f10-156">对于 PowerShell，首先 [使用适用于 Graph 模块的 Azure Active Directory PowerShell 进行连接](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="b1f10-156">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>

<span data-ttu-id="b1f10-157">接下来，使用以下命令块将单个用户帐户添加到访问组：</span><span class="sxs-lookup"><span data-stu-id="b1f10-157">Next, use the following command block to add an individual user account to an access group:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="b1f10-158">如果将任何访问组的用户帐户 UPN 存储在文本文件中，可以使用以下 PowerShell 命令块一次添加所有 UPN：</span><span class="sxs-lookup"><span data-stu-id="b1f10-158">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>

```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="b1f10-159">对于 PowerShell，使用以下命令块将单个组添加到访问组：</span><span class="sxs-lookup"><span data-stu-id="b1f10-159">For PowerShell, use the following command block to add an individual group to an access group:</span></span>

```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="b1f10-160">结果应为：</span><span class="sxs-lookup"><span data-stu-id="b1f10-160">The results should be the following:</span></span>

- <span data-ttu-id="b1f10-161">网站管理员 Azure AD 组包含网站管理员用户帐户或组</span><span class="sxs-lookup"><span data-stu-id="b1f10-161">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
- <span data-ttu-id="b1f10-162">网站成员 Azure AD 组包含站点成员用户帐户或组</span><span class="sxs-lookup"><span data-stu-id="b1f10-162">The site members Azure AD group contains the site member user accounts or groups</span></span>
- <span data-ttu-id="b1f10-163">网站查看者 Azure AD 组包含只能查看网站内容的用户帐户或组</span><span class="sxs-lookup"><span data-stu-id="b1f10-163">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>

<span data-ttu-id="b1f10-164">使用 Microsoft 365 管理中心或以下 PowerShell 命令块验证每个访问组的组成员列表：</span><span class="sxs-lookup"><span data-stu-id="b1f10-164">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>

```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="b1f10-165">下面是使用用户帐户或组填充的三个网站访问组生成的配置。</span><span class="sxs-lookup"><span data-stu-id="b1f10-165">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>

![使用用户帐户填充的三个访问组。](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)

## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="b1f10-167">第 2 阶段：创建和配置独立的团队网站</span><span class="sxs-lookup"><span data-stu-id="b1f10-167">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="b1f10-168">在此阶段，创建独立的 SharePoint Online 网站，并配置默认 SharePoint Online 权限级别的权限，以使用新的基于 Azure AD 的访问组。</span><span class="sxs-lookup"><span data-stu-id="b1f10-168">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="b1f10-169">默认情况下，新的团队网站包括 Microsoft 365 组和其他相关资源，但在这种情况下，我们将创建没有 Microsoft 365 组的团队网站。</span><span class="sxs-lookup"><span data-stu-id="b1f10-169">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="b1f10-170">这允许完全通过 SharePoint 维护权限。</span><span class="sxs-lookup"><span data-stu-id="b1f10-170">This allows maintaining permissions entirely through SharePoint.</span></span>

<span data-ttu-id="b1f10-171">首先，使用以下步骤创建 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="b1f10-171">First, create the SharePoint Online team site with these steps.</span></span>

1. <span data-ttu-id="b1f10-172">使用还将用于管理 SharePoint Online (SharePoint Online 团队网站的帐户登录到 Microsoft 365 管理) 。</span><span class="sxs-lookup"><span data-stu-id="b1f10-172">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="b1f10-173">如需帮助，请参阅[如何登录到 Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="b1f10-173">For help, see [Where to sign in to Office 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="b1f10-174">在 Microsoft 365 管理中心的"管理 **中心**"下，单击 **"SharePoint"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-174">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="b1f10-175">在 SharePoint 管理中心中，展开 **"网站**"，然后单击 **"活动网站"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-175">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="b1f10-176">单击 **"** 创建"，然后选择 **"其他选项"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-176">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="b1f10-177">在"**选择模板"列表中**，选择 **"团队网站"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-177">In the **Choose a template** list, choose **Team site**.</span></span>

6. <span data-ttu-id="b1f10-178">在 **"网站** 名称"中，键入团队网站的名称。</span><span class="sxs-lookup"><span data-stu-id="b1f10-178">In **Site name**, type a name for the team site.</span></span>

7. <span data-ttu-id="b1f10-179">在 **主管理员** 中，键入您登录时使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="b1f10-179">In **Primary administrator**, type the account that you are logged in with.</span></span>

8. <span data-ttu-id="b1f10-180">单击“完成”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-180">Click **Finish**.</span></span>

<span data-ttu-id="b1f10-181">接下来，从新的 SharePoint Online 团队网站配置权限。</span><span class="sxs-lookup"><span data-stu-id="b1f10-181">Next, from the new SharePoint Online team site, configure permissions.</span></span>

1. <span data-ttu-id="b1f10-182">在工具栏中，依次单击设置图标和“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-182">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="b1f10-183">在 **"网站共享**"下，**单击"更改成员共享"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-183">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="b1f10-184">选择" **仅网站所有者"可以共享文件、文件夹和网站**。</span><span class="sxs-lookup"><span data-stu-id="b1f10-184">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="b1f10-185">将 **"允许访问请求"设置为\*\*\*\*"关闭"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-185">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="b1f10-186">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-186">Click **Save**.</span></span>

6. <span data-ttu-id="b1f10-187">在 **"权限"** 窗格中，单击 **"高级权限设置"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-187">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>

7. <span data-ttu-id="b1f10-188">在 **浏览器的**"权限"选项卡上，单击 **\<site name> 列表中的**"成员"。</span><span class="sxs-lookup"><span data-stu-id="b1f10-188">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>

8. <span data-ttu-id="b1f10-189">在“人员和组”中，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-189">In **People and Groups**, click **New**.</span></span>

9. <span data-ttu-id="b1f10-190">在 **"共享**"对话框中，键入网站成员访问组的名称，选择它，然后单击"**共享"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-190">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>

10. <span data-ttu-id="b1f10-191">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="b1f10-191">Click the back button on your browser.</span></span>

11. <span data-ttu-id="b1f10-192">单击 **\<site name> 列表中的**"所有者"。</span><span class="sxs-lookup"><span data-stu-id="b1f10-192">Click **\<site name> Owners** in the list.</span></span>

12. <span data-ttu-id="b1f10-193">在“人员和组”中，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-193">In **People and Groups**, click **New**.</span></span>

13. <span data-ttu-id="b1f10-194">在 **"共享**"对话框中，键入网站管理员访问组的名称，选择它，然后单击"**共享"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-194">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>

14. <span data-ttu-id="b1f10-195">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="b1f10-195">Click the back button on your browser.</span></span>

15. <span data-ttu-id="b1f10-196">单击 **\<site name> 列表中的**"访问者"。</span><span class="sxs-lookup"><span data-stu-id="b1f10-196">Click **\<site name> Visitors** in the list.</span></span>

16. <span data-ttu-id="b1f10-197">在“人员和组”中，单击“新建”。</span><span class="sxs-lookup"><span data-stu-id="b1f10-197">In **People and Groups**, click **New**.</span></span>

17. <span data-ttu-id="b1f10-198">在 **"共享**"对话框中，键入网站查看器访问组的名称，选择它，然后单击"**共享"。**</span><span class="sxs-lookup"><span data-stu-id="b1f10-198">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>

18. <span data-ttu-id="b1f10-199">关闭浏览器的“权限”标签页。</span><span class="sxs-lookup"><span data-stu-id="b1f10-199">Close the **Permissions** tab of your browser.</span></span>

<span data-ttu-id="b1f10-200">以下是这些权限设置的结果：</span><span class="sxs-lookup"><span data-stu-id="b1f10-200">The results of these permission settings are:</span></span>

- <span data-ttu-id="b1f10-201">Owners **\<site name>** SharePoint 组包含网站管理员访问组，其中所有成员均具有完全 **控制** 权限级别。</span><span class="sxs-lookup"><span data-stu-id="b1f10-201">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
- <span data-ttu-id="b1f10-202">成员 **\<site name>** SharePoint 组包含网站成员访问组，其中所有成员都有"编辑 **"** 权限级别。</span><span class="sxs-lookup"><span data-stu-id="b1f10-202">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
- <span data-ttu-id="b1f10-203">Visitors **\<site name>** SharePoint 组包含网站查看者访问组，其中所有成员都有 **读取** 权限级别。</span><span class="sxs-lookup"><span data-stu-id="b1f10-203">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
- <span data-ttu-id="b1f10-204">禁用成员邀请其他成员或非成员请求访问的能力。</span><span class="sxs-lookup"><span data-stu-id="b1f10-204">The ability for members to invite other members or for non-members to request access is disabled.</span></span>

<span data-ttu-id="b1f10-205">下面是生成的配置，其中为网站配置了三个 SharePoint 组，以使用三个访问组，这些访问组填充了用户帐户或 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="b1f10-205">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>

![具有访问组和用户帐户的隔离 SharePoint Online 网站的最终配置。](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)

<span data-ttu-id="b1f10-207">通过其中一个访问组的组成员身份，您和网站的成员现在可以使用网站资源进行协作。</span><span class="sxs-lookup"><span data-stu-id="b1f10-207">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>

## <a name="next-step"></a><span data-ttu-id="b1f10-208">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b1f10-208">Next step</span></span>

<span data-ttu-id="b1f10-209">当需要更改网站访问组成员身份或创建具有自定义权限的文档文件夹时，请参阅["管理独立的 SharePoint Online 团队网站"。](manage-an-isolated-sharepoint-online-team-site.md)</span><span class="sxs-lookup"><span data-stu-id="b1f10-209">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>

## <a name="see-also"></a><span data-ttu-id="b1f10-210">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b1f10-210">See Also</span></span>

[<span data-ttu-id="b1f10-211">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="b1f10-211">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="b1f10-212">设计单独的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="b1f10-212">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)

[<span data-ttu-id="b1f10-213">管理独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="b1f10-213">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
