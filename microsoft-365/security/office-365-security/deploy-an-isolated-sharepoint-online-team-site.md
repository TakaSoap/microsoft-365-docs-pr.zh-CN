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
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_Solutions
ms.assetid: 3033614b-e23b-4f68-9701-f62525eafaab
description: 摘要：使用这些分步说明部署一个新的独立 SharePoint Online 团队网站。
ms.openlocfilehash: e35e380b61a94e08ff25e2e4c4bdfa28a635449e
ms.sourcegitcommit: 2614f8b81b332f8dab461f4f64f3adaa6703e0d6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2020
ms.locfileid: "43637624"
---
# <a name="deploy-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="1729c-103">部署独立的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="1729c-103">Deploy an isolated SharePoint Online team site</span></span>

 <span data-ttu-id="1729c-104">**摘要：** 按照这些分步说明部署一个新的独立 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="1729c-104">**Summary:** Deploy a new isolated SharePoint Online team site with these step-by-step instructions.</span></span>
  
<span data-ttu-id="1729c-105">本文是在 Microsoft Office 365 中创建和配置独立的 SharePoint Online 团队网站的分步部署指南。</span><span class="sxs-lookup"><span data-stu-id="1729c-105">This article is a step-by-step deployment guide for creating and configuring an isolated SharePoint Online team site in Microsoft Office 365.</span></span> <span data-ttu-id="1729c-106">这些步骤假定使用三个默认 SharePoint 组和相应的权限级别，每个级别的访问权限都有一个基于 Azure Active Directory （AD）的访问组。</span><span class="sxs-lookup"><span data-stu-id="1729c-106">These steps assume the use of the three default SharePoint groups and corresponding permission levels, with a single Azure Active Directory (AD)-based access group for each level of access.</span></span>
  
## <a name="phase-1-create-and-populate-the-team-site-access-groups"></a><span data-ttu-id="1729c-107">第1阶段：创建和填充团队网站访问组</span><span class="sxs-lookup"><span data-stu-id="1729c-107">Phase 1: Create and populate the team site access groups</span></span>

<span data-ttu-id="1729c-108">在此阶段中，您将为三个默认 SharePoint 组创建三个基于 Azure AD 的访问组，并使用适当的用户帐户填充它们。</span><span class="sxs-lookup"><span data-stu-id="1729c-108">In this phase, you create the three Azure AD-based access groups for the three default SharePoint groups and populate them with the appropriate user accounts.</span></span>
  
> [!NOTE]
> <span data-ttu-id="1729c-109">以下步骤假定所有必需的用户帐户都已存在，并为其分配了适当的许可证。</span><span class="sxs-lookup"><span data-stu-id="1729c-109">The following steps assume that all necessary user accounts already exist and are assigned the appropriate licenses.</span></span> <span data-ttu-id="1729c-110">如果不是，请先添加它们并分配许可证，然后再继续执行步骤1。</span><span class="sxs-lookup"><span data-stu-id="1729c-110">If not, please add them and assign licenses before proceeding to step 1.</span></span> 
  
### <a name="step-1-list-the-sharepoint-online-admins-for-the-site"></a><span data-ttu-id="1729c-111">步骤1：列出网站的 SharePoint Online 管理员</span><span class="sxs-lookup"><span data-stu-id="1729c-111">Step 1: List the SharePoint Online admins for the site</span></span>

<span data-ttu-id="1729c-112">确定对应于独立团队网站的 SharePoint Online 管理员的用户帐户集。</span><span class="sxs-lookup"><span data-stu-id="1729c-112">Determine the set of user accounts corresponding to the SharePoint Online admins for the isolated team site.</span></span>
  
<span data-ttu-id="1729c-113">如果您通过 Microsoft 365 管理用户帐户和组，并且想要使用 Windows PowerShell，请列出其用户主体名称（upn）（示例 UPN： belindan@contoso.com）。</span><span class="sxs-lookup"><span data-stu-id="1729c-113">If you are managing user accounts and groups through Microsoft 365 and want to use Windows PowerShell, make a list of their user principal names (UPNs) (example UPN: belindan@contoso.com).</span></span>
  
### <a name="step-2-list-the-members-for-the-site"></a><span data-ttu-id="1729c-114">步骤2：列出网站的成员</span><span class="sxs-lookup"><span data-stu-id="1729c-114">Step 2: List the members for the site</span></span>

<span data-ttu-id="1729c-115">确定与独立团队网站的成员对应的用户帐户集，这些用户帐户将对存储在网站中的资源进行协作。</span><span class="sxs-lookup"><span data-stu-id="1729c-115">Determine the set of user accounts corresponding to the members for the isolated team site, those who will be collaborating on resources stored within the site.</span></span>
  
<span data-ttu-id="1729c-116">如果您通过 Microsoft 365 管理用户帐户和组，并且想要使用 PowerShell，请创建其 Upn 的列表。</span><span class="sxs-lookup"><span data-stu-id="1729c-116">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="1729c-117">如果有大量的网站成员，则可以将 Upn 列表存储在一个文本文件中，并将它们全部添加到一个 PowerShell 命令中。</span><span class="sxs-lookup"><span data-stu-id="1729c-117">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
### <a name="step-3-list-the-viewers-for-the-site"></a><span data-ttu-id="1729c-118">步骤3：列出网站的查看者</span><span class="sxs-lookup"><span data-stu-id="1729c-118">Step 3: List the viewers for the site</span></span>

<span data-ttu-id="1729c-119">确定与独立团队网站的查看者相对应的用户帐户集，这些用户可以查看存储在网站中的资源，但不能对其内容进行修改，也不能直接对其内容进行协作。</span><span class="sxs-lookup"><span data-stu-id="1729c-119">Determine the set of user accounts corresponding to the viewers of the isolated team site, those who can view the resources stored in the site but not modify them or directly collaborate on their contents.</span></span>
  
<span data-ttu-id="1729c-120">如果您通过 Microsoft 365 管理用户帐户和组，并且想要使用 PowerShell，请创建其 Upn 的列表。</span><span class="sxs-lookup"><span data-stu-id="1729c-120">If you are managing user accounts and groups through Microsoft 365 and want to use PowerShell, make a list of their UPNs.</span></span> <span data-ttu-id="1729c-121">如果有大量的网站成员，则可以将 Upn 列表存储在一个文本文件中，并将它们全部添加到一个 PowerShell 命令中。</span><span class="sxs-lookup"><span data-stu-id="1729c-121">If there are a lot of site members, you can store the list of UPNs in a text file and add them all with a single PowerShell command.</span></span>
  
<span data-ttu-id="1729c-122">网站的查看者可能包括行政管理、法律顾问或部门间利益干系人。</span><span class="sxs-lookup"><span data-stu-id="1729c-122">Viewers for the site might include executive management, legal counsel, or inter-departmental stakeholders.</span></span>
  
### <a name="step-4-create-the-three-access-groups-for-the-site-in-azure-ad"></a><span data-ttu-id="1729c-123">步骤4：在 Azure AD 中为网站创建三个访问组</span><span class="sxs-lookup"><span data-stu-id="1729c-123">Step 4: Create the three access groups for the site in Azure AD</span></span>

<span data-ttu-id="1729c-124">您需要在 Azure AD 中创建以下访问组：</span><span class="sxs-lookup"><span data-stu-id="1729c-124">You need to create the following access groups in Azure AD:</span></span>
  
- <span data-ttu-id="1729c-125">网站管理员（将包含步骤1中的列表）</span><span class="sxs-lookup"><span data-stu-id="1729c-125">Site admins (which will contain the list from step 1)</span></span>
    
- <span data-ttu-id="1729c-126">网站成员（将包含步骤2中的列表）</span><span class="sxs-lookup"><span data-stu-id="1729c-126">Site members (which will contain the list from step 2)</span></span>
    
- <span data-ttu-id="1729c-127">网站查看器（将包含步骤3中的列表）</span><span class="sxs-lookup"><span data-stu-id="1729c-127">Site viewers (which will contain the list from step 3)</span></span>
    
1. <span data-ttu-id="1729c-128">在浏览器中，转到 Azure 门户， [https://portal.azure.com](https://portal.azure.com)并使用已分配给用户管理管理员或公司管理员角色的帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="1729c-128">In your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com) and sign in with the credentials of an account that has been assigned with User Management Admin or Company Administrator role.</span></span>
    
2. <span data-ttu-id="1729c-129">在 Azure 门户中，单击“**Azure Active Directory”>“组**”。</span><span class="sxs-lookup"><span data-stu-id="1729c-129">In the Azure portal, click **Azure Active Directory > Groups**.</span></span>
    
3. <span data-ttu-id="1729c-130">在“**组 - 所有组**”边栏选项卡上，单击“**+ 新建组**”。</span><span class="sxs-lookup"><span data-stu-id="1729c-130">On the **Groups - All groups** blade, click **+ New group**.</span></span>
    
4. <span data-ttu-id="1729c-131">在**新组**边栏上：</span><span class="sxs-lookup"><span data-stu-id="1729c-131">On the **New Group** blade:</span></span>
    
    - <span data-ttu-id="1729c-132">在“组类型”中选择“安全性”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1729c-132">Select **Security** in **Group type**.</span></span>

    - <span data-ttu-id="1729c-133">在 "**名称**" 中键入组名称。</span><span class="sxs-lookup"><span data-stu-id="1729c-133">Type the group name in **Name**.</span></span>

    - <span data-ttu-id="1729c-134">在 "**组说明**" 中键入组的说明。</span><span class="sxs-lookup"><span data-stu-id="1729c-134">Type a description of the group in **Group description**.</span></span>

    - <span data-ttu-id="1729c-135">在“**成员身份**”类型中，选择“**已分配**”。</span><span class="sxs-lookup"><span data-stu-id="1729c-135">Select **Assigned** in **Membership type**.</span></span>
    
5. <span data-ttu-id="1729c-136">单击“**创建**”，然后关闭“**组**”边栏选项卡。</span><span class="sxs-lookup"><span data-stu-id="1729c-136">Click **Create**, and then close the **Group** blade.</span></span>
    
6. <span data-ttu-id="1729c-137">对其他组重复步骤3-5。</span><span class="sxs-lookup"><span data-stu-id="1729c-137">Repeat steps 3-5 for your additional groups.</span></span>
    
> [!NOTE]
> <span data-ttu-id="1729c-138">您需要使用 Azure 门户来创建组，以便他们启用 Office 功能。</span><span class="sxs-lookup"><span data-stu-id="1729c-138">You need to use the Azure portal to create the groups so that they have Office features enabled.</span></span> <span data-ttu-id="1729c-139">如果后来将 SharePoint Online 独立网站配置为具有 Azure 信息保护标签的高度机密网站来加密文件，并为特定组分配权限，则必须已在启用 Office 功能的情况下创建允许的组。</span><span class="sxs-lookup"><span data-stu-id="1729c-139">If a SharePoint Online isolated site is later configured as a Highly Confidential site with an Azure Information Protection label to encrypt files and assign permission to specific groups, the permitted groups must have been created with Office features enabled.</span></span> <span data-ttu-id="1729c-140">Azure AD 组创建后，无法更改其 Office 功能设置。</span><span class="sxs-lookup"><span data-stu-id="1729c-140">You cannot change the Office features setting of an Azure AD group after it has been created.</span></span> 
  
<span data-ttu-id="1729c-141">下面是具有三个网站访问组的结果配置。</span><span class="sxs-lookup"><span data-stu-id="1729c-141">Here is your resulting configuration with the three site access groups.</span></span>
  
![用于部署独立 SharePoint Online 网站的三个访问组。](../../media/c2557f61-478b-4494-95e9-d79fe5909e8b.png)
  
### <a name="step-5-add-the-user-accounts-to-the-access-groups"></a><span data-ttu-id="1729c-143">第 5 步：</span><span class="sxs-lookup"><span data-stu-id="1729c-143">Step 5.</span></span> <span data-ttu-id="1729c-144">将用户帐户添加到访问组</span><span class="sxs-lookup"><span data-stu-id="1729c-144">Add the user accounts to the access groups</span></span>

<span data-ttu-id="1729c-145">在此步骤中，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1729c-145">In this step, do the following:</span></span>
  
1. <span data-ttu-id="1729c-146">将步骤1中的用户列表添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="1729c-146">Add the list of users from step 1 to the site admins access group</span></span>
    
2. <span data-ttu-id="1729c-147">将步骤2中的用户列表添加到网站成员访问组</span><span class="sxs-lookup"><span data-stu-id="1729c-147">Add the list of users from step 2 to the site members access group</span></span>
    
3. <span data-ttu-id="1729c-148">将步骤3中的用户列表添加到 "网站查看者访问" 组</span><span class="sxs-lookup"><span data-stu-id="1729c-148">Add the list of users from step 3 to the site viewers access group</span></span>
    
<span data-ttu-id="1729c-149">如果通过 Active Directory 域服务（AD DS）管理用户帐户和组，请使用常规 AD DS 用户和组管理程序将用户添加到相应的访问组，并等待与 Microsoft 365 订阅同步。</span><span class="sxs-lookup"><span data-stu-id="1729c-149">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your Microsoft 365 subscription.</span></span>
  
<span data-ttu-id="1729c-150">如果通过 Office 365 管理用户帐户和组，则可以使用 Microsoft 365 管理中心或 PowerShell。</span><span class="sxs-lookup"><span data-stu-id="1729c-150">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell.</span></span> <span data-ttu-id="1729c-151">如果有任何访问组的组名称重复，则应使用 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="1729c-151">If you have duplicate group names for any of the access groups, you should use the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="1729c-152">对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的用户帐户和组添加到相应的访问组。</span><span class="sxs-lookup"><span data-stu-id="1729c-152">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate user accounts and groups to the appropriate access groups.</span></span>
  
<span data-ttu-id="1729c-153">对于 PowerShell，首先[与 Azure Active Directory PowerShell For Graph 模块进行连接](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="1729c-153">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
  
<span data-ttu-id="1729c-154">接下来，使用以下命令块将单个用户帐户添加到访问组中：</span><span class="sxs-lookup"><span data-stu-id="1729c-154">Next, use the following command block to add an individual user account to an access group:</span></span>
  
```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```
<span data-ttu-id="1729c-155">如果您为文本文件中的任何访问组存储了用户帐户的 Upn，则可以使用下面的 PowerShell 命令块一次添加所有这些组：</span><span class="sxs-lookup"><span data-stu-id="1729c-155">If you stored the UPNs of user accounts for any of the access groups in a text file, you can use the following PowerShell command block to add them all at one time:</span></span>
  
```powershell
$grpName="<display name of the access group>"
$fileName="<path and name of the file containing the list of account UPNs>"
$grpID=(Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
Get-Content $fileName | ForEach { $userUPN=$_; Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID $grpID }
```

<span data-ttu-id="1729c-156">对于 PowerShell，使用以下命令块将单个组添加到访问组中：</span><span class="sxs-lookup"><span data-stu-id="1729c-156">For PowerShell, use the following command block to add an individual group to an access group:</span></span>
  
```powershell
$nestedGrpName="<display name of the group to add to the access group>"
$grpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $nestedGrpName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID

```

<span data-ttu-id="1729c-157">结果应如下所示：</span><span class="sxs-lookup"><span data-stu-id="1729c-157">The results should be the following:</span></span>
  
- <span data-ttu-id="1729c-158">网站管理员 Azure AD 组包含网站管理员用户帐户或组</span><span class="sxs-lookup"><span data-stu-id="1729c-158">The site admins Azure AD group contains the site admin user accounts or groups</span></span>
    
- <span data-ttu-id="1729c-159">网站成员 Azure AD 组包含网站成员用户帐户或组</span><span class="sxs-lookup"><span data-stu-id="1729c-159">The site members Azure AD group contains the site member user accounts or groups</span></span>
    
- <span data-ttu-id="1729c-160">网站查看器 Azure AD 组包含仅可查看网站内容的用户帐户或组</span><span class="sxs-lookup"><span data-stu-id="1729c-160">The site viewers Azure AD group contains the user accounts or groups that can only view the site contents</span></span>
    
<span data-ttu-id="1729c-161">使用 Microsoft 365 管理中心或以下 PowerShell 命令块验证每个访问组的组成员列表：</span><span class="sxs-lookup"><span data-stu-id="1729c-161">Validate the list of group members for each access group with the Microsoft 365 admin center or with the following PowerShell command block:</span></span>
  
```powershell
$grpName="<display name of the access group>"
Get-AzureADGroupMember -ObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID | Sort UserPrincipalName | Select UserPrincipalName,DisplayName,UserType
```

<span data-ttu-id="1729c-162">下面是通过使用用户帐户或组填充的三个网站访问组生成的配置。</span><span class="sxs-lookup"><span data-stu-id="1729c-162">Here is your resulting configuration with the three site access groups populated with user accounts or groups.</span></span>
  
![三个使用用户帐户填充的访问组。](../../media/2320107c-dad6-4c8f-94e5-f6427c125e71.png)
  
## <a name="phase-2-create-and-configure-the-isolated-team-site"></a><span data-ttu-id="1729c-164">阶段2：创建和配置独立的团队网站</span><span class="sxs-lookup"><span data-stu-id="1729c-164">Phase 2: Create and configure the isolated team site</span></span>

<span data-ttu-id="1729c-165">在此阶段中，您将创建独立的 SharePoint Online 网站，并将默认 SharePoint Online 权限级别的权限配置为使用新的基于 Azure AD 的访问组。</span><span class="sxs-lookup"><span data-stu-id="1729c-165">In this phase, you create the isolated SharePoint Online site and configure the permissions for the default SharePoint Online permission levels to use your new Azure AD-based access groups.</span></span> <span data-ttu-id="1729c-166">默认情况下，新的工作组网站包含 Microsoft 365 组和其他相关资源，但在这种情况下，我们将在没有 Microsoft 365 组的情况下创建团队网站。</span><span class="sxs-lookup"><span data-stu-id="1729c-166">By default, new team sites include a Microsoft 365 group and other related resources, but in this case, we'll create a team site without a Microsoft 365 group.</span></span> <span data-ttu-id="1729c-167">这样可以完全通过 SharePoint 维护权限。</span><span class="sxs-lookup"><span data-stu-id="1729c-167">This allows maintaining permissions entirely through SharePoint.</span></span>
  
<span data-ttu-id="1729c-168">首先，使用这些步骤创建 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="1729c-168">First, create the SharePoint Online team site with these steps.</span></span>
  
1. <span data-ttu-id="1729c-169">使用将用于管理 SharePoint Online 团队网站（SharePoint Online 管理员）的帐户登录到 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="1729c-169">Sign in to the Microsoft 365 admin center with an account that will also be used to administer the SharePoint Online team site (a SharePoint Online administrator).</span></span> <span data-ttu-id="1729c-170">如需帮助，请参阅[如何登录到 Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="1729c-170">For help, see [Where to sign in to Office 365](https://support.office.com/article/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="1729c-171">在 Microsoft 365 管理中心的 "**管理中心**" 下，单击 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-171">In the Microsoft 365 admin center, under **Admin centers**, click **SharePoint**.</span></span>

3. <span data-ttu-id="1729c-172">在 SharePoint 管理中心中，展开 "**网站**"，然后单击 "**活动网站**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-172">In the SharePoint admin center, expand **Sites** and click **Active sites**.</span></span>

4. <span data-ttu-id="1729c-173">单击 "**创建**"，然后选择 "**其他选项**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-173">Click **Create**, and then choose **Other options**.</span></span>

5. <span data-ttu-id="1729c-174">在 "**选择模板**" 列表中，选择 "**团队网站**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-174">In the **Choose a template** list, choose **Team site**.</span></span>
   
6. <span data-ttu-id="1729c-175">在 "**网站名称**" 中，键入团队网站的名称。</span><span class="sxs-lookup"><span data-stu-id="1729c-175">In **Site name**, type a name for the team site.</span></span> 
    
7. <span data-ttu-id="1729c-176">在**主管理员**中，键入您登录时使用的帐户。</span><span class="sxs-lookup"><span data-stu-id="1729c-176">In **Primary administrator**, type the account that you are logged in with.</span></span>
 
8. <span data-ttu-id="1729c-177">单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1729c-177">Click **Finish**.</span></span>
    
<span data-ttu-id="1729c-178">接下来，从新的 SharePoint Online 团队网站配置权限。</span><span class="sxs-lookup"><span data-stu-id="1729c-178">Next, from the new SharePoint Online team site, configure permissions.</span></span>
  
1. <span data-ttu-id="1729c-179">在工具栏中，依次单击设置图标和“**网站权限**”。</span><span class="sxs-lookup"><span data-stu-id="1729c-179">In the tool bar, click the settings icon, and then click **Site permissions**.</span></span>

2. <span data-ttu-id="1729c-180">在 "**网站共享**" 下，单击 "**更改成员可以共享的方式**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-180">Under **Site sharing**, click **Change how members can share**.</span></span>

3. <span data-ttu-id="1729c-181">选择 "**仅网站所有者" 可以共享文件、文件夹和网站**。</span><span class="sxs-lookup"><span data-stu-id="1729c-181">Choose the **Only site owners can share files, folders, and the site**.</span></span>

4. <span data-ttu-id="1729c-182">将 "**允许访问请求**" 设置为 "**关闭**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-182">Set **Allow access requests** to **Off**.</span></span>

5. <span data-ttu-id="1729c-183">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="1729c-183">Click **Save**.</span></span>
    
6. <span data-ttu-id="1729c-184">在 "**权限**" 窗格中，单击 "**高级权限设置**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-184">In the **Permissions** pane, click **Advanced permissions settings**.</span></span>
    
7. <span data-ttu-id="1729c-185">在浏览器的 "**权限**" 选项卡上，单击\*\* \<\*\* 列表中的 "网站名称"> 成员。</span><span class="sxs-lookup"><span data-stu-id="1729c-185">On the **Permissions** tab of your browser, click **\<site name> Members** in the list.</span></span>
    
8. <span data-ttu-id="1729c-186">在“人员和组”中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1729c-186">In **People and Groups**, click **New**.</span></span>
    
9. <span data-ttu-id="1729c-187">在 "**共享**" 对话框中，键入网站成员访问组的名称，选择它，然后单击 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-187">In the **Share** dialog box, type the name of the site members access group, select it, and then click **Share**.</span></span>
    
10. <span data-ttu-id="1729c-188">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="1729c-188">Click the back button on your browser.</span></span>
    
11. <span data-ttu-id="1729c-189">单击列表中的 " \*\* \<网站名称"> 所有者\*\*"。</span><span class="sxs-lookup"><span data-stu-id="1729c-189">Click **\<site name> Owners** in the list.</span></span>
    
12. <span data-ttu-id="1729c-190">在“人员和组”中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1729c-190">In **People and Groups**, click **New**.</span></span>
    
13. <span data-ttu-id="1729c-191">在 "**共享**" 对话框中，键入 "网站管理员" 访问组的名称，选择它，然后单击 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-191">In the **Share** dialog box, type the name of the site admins access group, select it, and then click **Share**.</span></span>
    
14. <span data-ttu-id="1729c-192">单击浏览器上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="1729c-192">Click the back button on your browser.</span></span>
    
15. <span data-ttu-id="1729c-193">在列表中单击 " \*\* \<网站名称"> 访问者\*\*。</span><span class="sxs-lookup"><span data-stu-id="1729c-193">Click **\<site name> Visitors** in the list.</span></span>
    
16. <span data-ttu-id="1729c-194">在“人员和组”中，单击“新建”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1729c-194">In **People and Groups**, click **New**.</span></span>
    
17. <span data-ttu-id="1729c-195">在 "**共享**" 对话框中，键入 "网站查看者访问" 组的名称，选择它，然后单击 "**共享**"。</span><span class="sxs-lookup"><span data-stu-id="1729c-195">In the **Share** dialog box, type the name of the site viewers access group, select it, and then click **Share**.</span></span>
    
18. <span data-ttu-id="1729c-196">关闭浏览器的“权限”标签页\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1729c-196">Close the **Permissions** tab of your browser.</span></span>
    
<span data-ttu-id="1729c-197">以下是这些权限设置的结果：</span><span class="sxs-lookup"><span data-stu-id="1729c-197">The results of these permission settings are:</span></span>
  
- <span data-ttu-id="1729c-198">" \*\* \<网站名称> 所有者**" SharePoint 组包含 "网站管理员" 访问组，其中所有成员都具有 "**完全控制\*\*" 权限级别。</span><span class="sxs-lookup"><span data-stu-id="1729c-198">The **\<site name> Owners** SharePoint group contains the site admins access group, in which all the members have the **Full control** permission level.</span></span>
    
- <span data-ttu-id="1729c-199">" \*\* \<网站名称> 成员**" SharePoint 组包含 "网站成员" 访问组，其中所有成员都具有 "**编辑\*\*" 权限级别。</span><span class="sxs-lookup"><span data-stu-id="1729c-199">The **\<site name> Members** SharePoint group contains the site members access group, in which all the members have the **Edit** permission level.</span></span>
    
- <span data-ttu-id="1729c-200">" \*\* \<网站名称> 访问者**" SharePoint 组包含 "网站查看者" 访问组，其中所有成员都具有 "**读取\*\*" 权限级别。</span><span class="sxs-lookup"><span data-stu-id="1729c-200">The **\<site name> Visitors** SharePoint group contains the site viewers access group, in which all the members have the **Read** permission level.</span></span>
    
- <span data-ttu-id="1729c-201">禁用成员邀请其他成员或非成员请求访问的功能已被禁用。</span><span class="sxs-lookup"><span data-stu-id="1729c-201">The ability for members to invite other members or for non-members to request access is disabled.</span></span>
    
<span data-ttu-id="1729c-202">下面是配置了三个 SharePoint 组的网站的结果配置，该网站配置为使用三个访问组，其中填充了用户帐户或 Azure AD 组。</span><span class="sxs-lookup"><span data-stu-id="1729c-202">Here is your resulting configuration with the three SharePoint groups for the site configured to use the three access groups, which are populated with user accounts or Azure AD groups.</span></span>
  
![使用访问组和用户帐户的独立 SharePoint Online 网站的最终配置。](../../media/e7618971-06ab-447b-90ff-d8be3790fe63.png)
  
<span data-ttu-id="1729c-204">您和网站成员（通过其中一个访问组中的组成员身份）现在可以使用网站的资源进行协作。</span><span class="sxs-lookup"><span data-stu-id="1729c-204">You and the members of the site, through group membership in one of the access groups, can now collaborate using the resources of the site.</span></span>
  
## <a name="next-step"></a><span data-ttu-id="1729c-205">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1729c-205">Next step</span></span>

<span data-ttu-id="1729c-206">如果需要更改网站访问组成员身份或创建具有自定义权限的文档文件夹，请参阅[管理独立的 SharePoint Online 团队网站](manage-an-isolated-sharepoint-online-team-site.md)。</span><span class="sxs-lookup"><span data-stu-id="1729c-206">When you need to change site access group membership or create a document folder with custom permissions, see [Manage an isolated SharePoint Online team site](manage-an-isolated-sharepoint-online-team-site.md).</span></span>
  
## <a name="see-also"></a><span data-ttu-id="1729c-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1729c-207">See Also</span></span>

[<span data-ttu-id="1729c-208">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="1729c-208">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)
  
[<span data-ttu-id="1729c-209">设计单独的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="1729c-209">Design an isolated SharePoint Online team site</span></span>](design-an-isolated-sharepoint-online-team-site.md)
  
[<span data-ttu-id="1729c-210">管理独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="1729c-210">Manage an isolated SharePoint Online team site</span></span>](manage-an-isolated-sharepoint-online-team-site.md)
  



