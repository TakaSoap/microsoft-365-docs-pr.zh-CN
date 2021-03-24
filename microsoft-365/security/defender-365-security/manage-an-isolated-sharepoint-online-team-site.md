---
title: 管理独立的 SharePoint Online 团队网站
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/15/2017
audience: ITPro
ms.topic: article
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- Ent_Solutions
- seo-marvel-apr2020
ms.assetid: 79a61003-4905-4ba8-9e8a-16def7add37c
description: 管理独立的 SharePoint Online 团队网站，添加新用户和组，删除用户和组，以及创建具有自定义权限的文档子文件夹。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 99b773547fa67068d75a79260af14010e456cb01
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51056195"
---
# <a name="manage-an-isolated-sharepoint-online-team-site"></a><span data-ttu-id="4ca4d-103">管理独立的 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="4ca4d-103">Manage an isolated SharePoint Online team site</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="4ca4d-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-104">**Applies to**</span></span>
- [<span data-ttu-id="4ca4d-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="4ca4d-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="4ca4d-106">适用于 Office 365 计划 1 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="4ca4d-106">Microsoft Defender for Office 365 plan 1</span></span>](defender-for-office-365.md)
- <span data-ttu-id="4ca4d-107">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4ca4d-107">SharePoint Online</span></span> 

 <span data-ttu-id="4ca4d-108">**摘要：** 通过这些过程管理独立的 SharePoint Online 团队网站。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-108">**Summary:** Manage your isolated SharePoint Online team site with these procedures.</span></span>

<span data-ttu-id="4ca4d-109">本文介绍了独立 SharePoint Online 团队网站的常见管理操作。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-109">This article describes common management operations for an isolated SharePoint Online team site.</span></span>

## <a name="add-a-new-user"></a><span data-ttu-id="4ca4d-110">添加新用户</span><span class="sxs-lookup"><span data-stu-id="4ca4d-110">Add a new user</span></span>

<span data-ttu-id="4ca4d-111">当有新用户加入网站时，您必须确定其参与网站的级别：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-111">When someone new joins the site, you must decide their level of participation in the site:</span></span>

- <span data-ttu-id="4ca4d-112">管理：将新用户帐户添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-112">Administration: Add the new user account to the site admins access group</span></span>

- <span data-ttu-id="4ca4d-113">活动协作：将用户帐户添加到网站成员访问组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-113">Active collaboration: Add the user account to the site members access group</span></span>

- <span data-ttu-id="4ca4d-114">查看：将用户帐户添加到网站查看者访问组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-114">Viewing: Add the user account to the site viewers access group</span></span>

<span data-ttu-id="4ca4d-115">如果要通过 Active Directory 域服务 (AD DS) 管理用户帐户和组，则使用常规 AD DS 用户和组管理过程将相应的用户添加到相应的访问组，并等待与订阅同步。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-115">If you are managing user accounts and groups through Active Directory Domain Services (AD DS), add the appropriate users to the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="4ca4d-116">如果通过 Microsoft 365 管理用户帐户和组，可以使用 Microsoft 365 管理中心或 Microsoft PowerShell：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-116">If you are managing user accounts and groups through Microsoft 365, you can use the Microsoft 365 admin center or Microsoft PowerShell:</span></span>

- <span data-ttu-id="4ca4d-117">对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的用户添加到相应的访问组。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-117">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate users to the appropriate access groups.</span></span>

- <span data-ttu-id="4ca4d-118">对于 PowerShell，首先 [使用 Azure Active Directory PowerShell graph 模块进行连接](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-118">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span> <span data-ttu-id="4ca4d-119">若要将用户帐户添加到其用户主体名称为 UPN (访问) ，请使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-119">To add a user account to an access group with its user principal name (UPN), use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="4ca4d-120">若要将用户帐户添加到访问组及其显示名称，请使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-120">To add a user account to an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="add-a-new-group"></a><span data-ttu-id="4ca4d-121">添加新组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-121">Add a new group</span></span>

<span data-ttu-id="4ca4d-122">若要向整个组添加访问权限，必须决定网站中组所有成员的参与级别：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-122">To add access to an entire group, you must decide the level of participation of all the members of the group in the site:</span></span>

- <span data-ttu-id="4ca4d-123">管理：将组添加到网站管理员访问组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-123">Administration: Add the group to the site admins access group</span></span>

- <span data-ttu-id="4ca4d-124">活动协作：将组添加到网站成员访问组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-124">Active collaboration: Add the group to the site members access group</span></span>

- <span data-ttu-id="4ca4d-125">查看：将组添加到网站查看者访问组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-125">Viewing: Add the group to the site viewers access group</span></span>

<span data-ttu-id="4ca4d-126">如果通过 AD DS 管理用户帐户和组，则使用常规 AD DS 用户和组管理过程将相应的组添加到相应的组，并等待与订阅同步。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-126">If you are managing user accounts and groups through AD DS, add the appropriate groups to the appropriate groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="4ca4d-127">如果通过 Office 365 管理用户帐户和组，可以使用 Microsoft 365 管理中心或 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-127">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="4ca4d-128">对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组将相应的组添加到相应的访问组。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-128">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to add the appropriate groups to the appropriate access groups.</span></span>

- <span data-ttu-id="4ca4d-129">对于 PowerShell，首先 [使用 Azure Active Directory PowerShell graph 模块进行连接](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-129">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
 <span data-ttu-id="4ca4d-130">然后，使用以下 PowerShell 命令：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-130">Then, use the following PowerShell commands:</span></span>

```powershell
$newGroupName="<display name of the new group to add>"
$siteGrpName="<display name of the access group>"
Add-AzureADGroupMember -RefObjectId (Get-AzureADGroup | Where { $_.DisplayName -eq $newGroupName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $siteGrpName }).ObjectID
```

## <a name="remove-a-user"></a><span data-ttu-id="4ca4d-131">删除用户</span><span class="sxs-lookup"><span data-stu-id="4ca4d-131">Remove a user</span></span>

<span data-ttu-id="4ca4d-132">当必须从网站中删除某人的访问权限时，根据用户对网站的参与情况，将其从当前是访问组的成员中删除：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-132">When someone's access must be removed from the site, you remove them from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="4ca4d-133">管理：从网站管理员访问组中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="4ca4d-133">Administration: Remove the user account from the site admins access group</span></span>

- <span data-ttu-id="4ca4d-134">活动协作：从网站成员访问组中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="4ca4d-134">Active collaboration: Remove the user account from the site members access group</span></span>

- <span data-ttu-id="4ca4d-135">查看：从网站查看者访问组中删除用户帐户</span><span class="sxs-lookup"><span data-stu-id="4ca4d-135">Viewing: Remove the user account from the site viewers access group</span></span>

<span data-ttu-id="4ca4d-136">如果通过 AD DS 管理用户帐户和组，则使用常规 AD DS 用户和组管理过程从相应的访问组中删除相应的用户，并等待与订阅同步。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-136">If you are managing user accounts and groups through AD DS, remove the appropriate users from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="4ca4d-137">如果通过 Office 365 管理用户帐户和组，可以使用 Microsoft 365 管理中心或 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-137">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="4ca4d-138">对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组从相应的访问组中删除相应的用户。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-138">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate users from the appropriate access groups.</span></span>

- <span data-ttu-id="4ca4d-139">对于 PowerShell，首先 [使用 Azure Active Directory PowerShell graph 模块进行连接](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-139">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="4ca4d-140">若要从具有 UPN 的访问组中删除用户帐户，请使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-140">To remove a user account from an access group with its UPN, use the following PowerShell command block:</span></span>

```powershell
$userUPN="<UPN of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.UserPrincipalName -eq $userUPN }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

<span data-ttu-id="4ca4d-141">若要从具有用户帐户访问权限的访问组中删除显示名称，请使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-141">To remove a user account from an access group with its display name, use the following PowerShell command block:</span></span>

```powershell
$userDisplayName="<display name of the user account>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADUser | Where { $_.DisplayName -eq $userDisplayName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="remove-a-group"></a><span data-ttu-id="4ca4d-142">删除组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-142">Remove a group</span></span>

<span data-ttu-id="4ca4d-143">若要删除整个组的访问权限，请根据组对网站的参与情况，从当前为访问组的成员中删除该组：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-143">To remove access for an entire group, you remove the group from the access group for which they are currently a member based on their participation in the site:</span></span>

- <span data-ttu-id="4ca4d-144">管理：从网站管理员访问组中删除组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-144">Administration: Remove the group from the site admins access group</span></span>

- <span data-ttu-id="4ca4d-145">活动协作：从网站成员访问组中删除组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-145">Active collaboration: Remove the group from the site members access group</span></span>

- <span data-ttu-id="4ca4d-146">查看：从网站查看器访问组中删除组</span><span class="sxs-lookup"><span data-stu-id="4ca4d-146">Viewing: Remove the group from the site viewers access group</span></span>

<span data-ttu-id="4ca4d-147">如果要通过 Windows Server Active Directory 管理用户帐户和组，则使用常规 AD DS 用户和组管理过程从相应的访问组中删除相应的组，并等待与订阅同步。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-147">If you are managing user accounts and groups through Windows Server Active Directory, remove the appropriate groups from the appropriate access groups using your normal AD DS user and group management procedures and wait for synchronization with your subscription.</span></span>

<span data-ttu-id="4ca4d-148">如果通过 Office 365 管理用户帐户和组，可以使用 Microsoft 365 管理中心或 PowerShell：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-148">If you are managing user accounts and groups through Office 365, you can use the Microsoft 365 admin center or PowerShell:</span></span>

- <span data-ttu-id="4ca4d-149">对于 Microsoft 365 管理中心，使用已分配有用户帐户管理员或公司管理员角色的用户帐户登录，并使用组从相应的访问组中删除相应的组。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-149">For the Microsoft 365 admin center, sign in with a user account that has been assigned the User Account Administrator or Company Administrator role and use Groups to remove the appropriate groups from the appropriate access groups.</span></span>

- <span data-ttu-id="4ca4d-150">对于 PowerShell，首先 [使用 Azure Active Directory PowerShell graph 模块进行连接](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-150">For PowerShell, first [Connect with the Azure Active Directory PowerShell for Graph module](../../enterprise/connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
<span data-ttu-id="4ca4d-151">若要使用组的显示名称从访问组中删除组，请使用以下 PowerShell 命令块：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-151">To remove a group from an access group using their display names, use the following PowerShell command block:</span></span>

```powershell
$groupMemberName="<display name of the group to remove>"
$grpName="<display name of the access group>"
Remove-AzureADGroupMember -MemberId (Get-AzureADGroup | Where { $_.DisplayName -eq $groupMemberName }).ObjectID -ObjectID (Get-AzureADGroup | Where { $_.DisplayName -eq $grpName }).ObjectID
```

## <a name="create-a-documents-subfolder-with-custom-permissions"></a><span data-ttu-id="4ca4d-152">使用自定义权限创建文档子文件夹</span><span class="sxs-lookup"><span data-stu-id="4ca4d-152">Create a documents subfolder with custom permissions</span></span>

<span data-ttu-id="4ca4d-153">在某些情况下，在独立网站中工作的一部分人员需要一个更为私人的协作位置。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-153">In some cases, a subset of the people working within the isolated site need a more private place to collaborate.</span></span> <span data-ttu-id="4ca4d-154">对于 SharePoint Online 网站，可以在网站的"文档"文件夹中创建子文件夹并分配自定义权限。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-154">For SharePoint Online sites, you can create a subfolder in the Documents folder of the site and assign custom permissions.</span></span> <span data-ttu-id="4ca4d-155">没有权限的用户将看不到子文件夹。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-155">Those without permissions will not see the subfolder.</span></span>

<span data-ttu-id="4ca4d-156">若要创建具有自定义权限的文档子文件夹，请执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="4ca4d-156">To create a documents subfolder with custom permissions, do the following:</span></span>

1. <span data-ttu-id="4ca4d-157">登录到作为网站的管理员访问组的成员的帐户。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-157">Sign in to an account that is a member of the admins access group for the site.</span></span> <span data-ttu-id="4ca4d-158">如需帮助，请参阅[在哪里登录 Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-158">For help, see [Where to sign in to Microsoft 365](https://support.microsoft.com/office/e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>

2. <span data-ttu-id="4ca4d-159">转到独立的团队网站，然后单击"文档 **"。**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-159">Go to the isolated team site and click **Documents**.</span></span>

3. <span data-ttu-id="4ca4d-160">浏览到将包含具有自定义权限的子文件夹的文档文件夹中的文件夹，创建该文件夹，然后打开它。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-160">Browse to the folder in the documents folder that will contain the subfolder with custom permissions, create the folder, and then open it.</span></span>

4. <span data-ttu-id="4ca4d-161">单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-161">Click **Share**.</span></span>

5. <span data-ttu-id="4ca4d-162">单击 **"与高级>共享"。**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-162">Click **Shared with > Advanced**.</span></span>

6. <span data-ttu-id="4ca4d-163">单击 **"停止继承权限"，** 然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-163">Click **Stop inheriting permissions**, and then click **OK**.</span></span>

7. <span data-ttu-id="4ca4d-164">单击“**共享**”。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-164">Click **Share**.</span></span>

8. <span data-ttu-id="4ca4d-165">单击 **"与高级>共享"。**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-165">Click **Shared with > Advanced**.</span></span>

9. <span data-ttu-id="4ca4d-166">单击 **"授予权限>共享>高级"。**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-166">Click **Grant Permissions > Shared with > Advanced**.</span></span>

10. <span data-ttu-id="4ca4d-167">在"权限"页上，单击 **\<site name> 列表中的"成员"。**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-167">On the permissions page, click **\<site name> Members in the list**.</span></span>

11. <span data-ttu-id="4ca4d-168">在"**\<site name> 成员"** 页上，选中网站成员访问组旁边的选中标记，单击"操作"，单击"**从** 组中删除用户"，然后单击"确定 **"。**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-168">On the **\<site name> Members** page, select the checkmark next to the site members access group, click **Actions**, click **Remove users from group**, and then click **OK**.</span></span>

12. <span data-ttu-id="4ca4d-169">若要向此子文件夹添加特定成员，请单击"新建>**添加用户"。**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-169">To add specific members to this subfolder, click **New > Add users**.</span></span>

13. <span data-ttu-id="4ca4d-170">在 **"共享**"对话框中，键入可以协作处理子文件夹文件的用户帐户的名称，然后单击"共享 **"。**</span><span class="sxs-lookup"><span data-stu-id="4ca4d-170">In the **Share** dialog box, type the names of the user accounts that can collaborate on files in the subfolder, and then click **Share**.</span></span>

14. <span data-ttu-id="4ca4d-171">刷新网页以查看新结果。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-171">Refresh the web page to see the new results.</span></span>

15. <span data-ttu-id="4ca4d-172">在 **左侧导航中的**"组"下，**\<site name>** 单击"访问者"组并使用步骤 11-14 指定一组用户帐户，这些用户帐户可根据需要 (子文件夹) 。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-172">Under **Groups** in the left navigation, click the **\<site name> Visitors** group and use steps 11-14 to specify the set of user accounts that can view the files in the subfolder (as needed).</span></span>

16. <span data-ttu-id="4ca4d-173">在 **左侧导航中的**"组"下，**\<site name>** 单击"所有者"组并使用步骤 11-14 指定一组用户帐户，这些用户帐户可根据需要管理子文件夹 (权限) 。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-173">Under **Groups** in the left navigation, click the **\<site name> Owners** group and use steps 11-14 to specify the set of user accounts that can administer the permissions in the subfolder (as needed).</span></span>

17. <span data-ttu-id="4ca4d-174">关闭 **浏览器中的"人员与组** "选项卡。</span><span class="sxs-lookup"><span data-stu-id="4ca4d-174">Close the **People and Groups** tab in your browser.</span></span>

## <a name="see-also"></a><span data-ttu-id="4ca4d-175">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4ca4d-175">See Also</span></span>

[<span data-ttu-id="4ca4d-176">独立 SharePoint Online 团队网站</span><span class="sxs-lookup"><span data-stu-id="4ca4d-176">Isolated SharePoint Online team sites</span></span>](isolated-sharepoint-online-team-sites.md)

[<span data-ttu-id="4ca4d-177">配置具有安全隔离的团队</span><span class="sxs-lookup"><span data-stu-id="4ca4d-177">Configure a team with security isolation</span></span>](/microsoft-365/solutions/secure-teams-security-isolation)
