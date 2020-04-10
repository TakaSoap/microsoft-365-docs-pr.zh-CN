---
title: 管理可创建 Office 365 组的人员
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
search.appverid:
- BCS160
- MSP160
- MST160
- MET150
- MOE150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: 了解如何控制哪些用户可以创建 Office 365 组。
ms.openlocfilehash: 9016b96821dd9d40a0fb65574ce96d7badd0c2bd
ms.sourcegitcommit: 4a34b48584071e0c43c920bb35025e34cb4f5d15
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2020
ms.locfileid: "43212077"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="32c75-103">管理可创建 Office 365 组的人员</span><span class="sxs-lookup"><span data-stu-id="32c75-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="32c75-104">由于用户可以很轻松地创建 Office 365 组，因此你不会收到代表其他人创建这些组的请求。</span><span class="sxs-lookup"><span data-stu-id="32c75-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="32c75-105">但是，根据您的业务，您可能希望控制谁能够创建组。</span><span class="sxs-lookup"><span data-stu-id="32c75-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="32c75-106">本文介绍如何禁用在所有使用组的 Office 365 服务中创建组的功能，其中包括：</span><span class="sxs-lookup"><span data-stu-id="32c75-106">This article explains how to disable the ability to create groups in all Office 365 services that use groups, including:</span></span>
  
- <span data-ttu-id="32c75-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="32c75-107">Outlook</span></span>
    
- <span data-ttu-id="32c75-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="32c75-108">SharePoint</span></span>
    
- <span data-ttu-id="32c75-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="32c75-109">Yammer</span></span>
    
- <span data-ttu-id="32c75-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="32c75-110">Microsoft Teams</span></span>

- <span data-ttu-id="32c75-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="32c75-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="32c75-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="32c75-112">StaffHub</span></span>
    
- <span data-ttu-id="32c75-113">Planner</span><span class="sxs-lookup"><span data-stu-id="32c75-113">Planner</span></span>
    
- <span data-ttu-id="32c75-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="32c75-114">PowerBI</span></span>

- <span data-ttu-id="32c75-115">路线图</span><span class="sxs-lookup"><span data-stu-id="32c75-115">Roadmap</span></span>
    
<span data-ttu-id="32c75-116">您可以将 Office 365 组创建限制为特定安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="32c75-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="32c75-117">若要配置此设置，请使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="32c75-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="32c75-118">本文将引导您完成所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="32c75-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="32c75-119">本文中的步骤不会阻止某些角色的成员创建组。</span><span class="sxs-lookup"><span data-stu-id="32c75-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="32c75-120">Office 365 全局管理员可以通过任何方式创建组，例如 Microsoft 365 管理中心、Planner、团队、Exchange 和 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="32c75-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="32c75-121">其他角色可以通过有限的方法创建组，如下所示。</span><span class="sxs-lookup"><span data-stu-id="32c75-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="32c75-122">Exchange 管理员： Exchange 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="32c75-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="32c75-123">合作伙伴第1层支持： Microsoft 365 管理中心、Exchange 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="32c75-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="32c75-124">合作伙伴第2层支持： Microsoft 365 管理中心、Exchange 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="32c75-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="32c75-125">目录写入程序： Azure AD</span><span class="sxs-lookup"><span data-stu-id="32c75-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="32c75-126">SharePoint 管理员： SharePoint 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="32c75-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="32c75-127">团队服务管理员：团队管理员中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="32c75-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="32c75-128">用户管理管理员： Microsoft 365 管理中心、Yammer、Azure AD</span><span class="sxs-lookup"><span data-stu-id="32c75-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="32c75-129">如果你属于以上其中一种角色的成员，则可以为受限用户创建 Office 365 组，然后将该用户分配为组所有者。</span><span class="sxs-lookup"><span data-stu-id="32c75-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="32c75-130">具有此角色的用户可以在 Yammer 中创建连接的组，而不考虑可能阻止创建的任何 PowerShell 设置。</span><span class="sxs-lookup"><span data-stu-id="32c75-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="32c75-131">许可要求</span><span class="sxs-lookup"><span data-stu-id="32c75-131">Licensing requirements</span></span>

<span data-ttu-id="32c75-132">若要管理创建组的人员，以下人员需要分配给它们的 Azure AD Premium 许可证或 Azure AD 基本 EDU 许可证：</span><span class="sxs-lookup"><span data-stu-id="32c75-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="32c75-133">配置这些组创建设置的管理员</span><span class="sxs-lookup"><span data-stu-id="32c75-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="32c75-134">允许创建组的安全组的成员</span><span class="sxs-lookup"><span data-stu-id="32c75-134">The members of the security group who are allowed to create groups</span></span>

<span data-ttu-id="32c75-135">以下人员不需要为其分配 Azure AD Premium 或 Azure AD 基本 EDU 许可证：</span><span class="sxs-lookup"><span data-stu-id="32c75-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="32c75-136">属于 Office 365 组成员并不能创建其他组的人员。</span><span class="sxs-lookup"><span data-stu-id="32c75-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="32c75-137">步骤 1：为需要创建 Office 365 组 的用户创建一个安全组</span><span class="sxs-lookup"><span data-stu-id="32c75-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="32c75-138">您的组织中仅有一个安全组可用于控制能够创建组的用户。</span><span class="sxs-lookup"><span data-stu-id="32c75-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="32c75-139">但是，你可以将其他安全组包含在内作为该组的成员。</span><span class="sxs-lookup"><span data-stu-id="32c75-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="32c75-140">例如，名为"允许创建组"的组作为指定的安全组，名为"Microsoft Planner 用户"和"Exchange Online 用户"的组作为该安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="32c75-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="32c75-141">上面列出的角色中的管理员不需要是该组的成员：它们保留了其创建组的能力。</span><span class="sxs-lookup"><span data-stu-id="32c75-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="32c75-142">请务必使用**安全组**来限制可以创建组的用户。</span><span class="sxs-lookup"><span data-stu-id="32c75-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="32c75-143">如果您尝试使用 Office 365 组，则成员将无法从 SharePoint 创建组，因为它会检查安全组。</span><span class="sxs-lookup"><span data-stu-id="32c75-143">If you try to use an Office 365 group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="32c75-144">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="32c75-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="32c75-145">单击 "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="32c75-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="32c75-146">选择 "**安全**" 作为组类型。</span><span class="sxs-lookup"><span data-stu-id="32c75-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="32c75-147">请记住该组的名称！</span><span class="sxs-lookup"><span data-stu-id="32c75-147">Remember the name of the group!</span></span> <span data-ttu-id="32c75-148">稍后需要用到该名称。</span><span class="sxs-lookup"><span data-stu-id="32c75-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="32c75-149">完成设置安全组，添加你希望能够在你的组织中创建组的人员或其他安全组。</span><span class="sxs-lookup"><span data-stu-id="32c75-149">Finish setting up the security group, adding people or other security groups who you want to be able to create groups in your org.</span></span>
    
<span data-ttu-id="32c75-150">有关详细说明，请参阅[在 Microsoft 365 管理中心中创建、编辑或删除安全组](../email/create-edit-or-delete-a-security-group.md)。</span><span class="sxs-lookup"><span data-stu-id="32c75-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
 
## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="32c75-151">步骤 2：运行 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="32c75-151">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="32c75-152">您必须使用预览版本的[Azure Active Directory PowerShell For Graph （AzureAD）](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （模块名称**AzureADPreview**）更改组级别的来宾访问设置：</span><span class="sxs-lookup"><span data-stu-id="32c75-152">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="32c75-153">如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)并按照说明安装公共预览版。</span><span class="sxs-lookup"><span data-stu-id="32c75-153">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="32c75-154">如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。</span><span class="sxs-lookup"><span data-stu-id="32c75-154">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="32c75-155">如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="32c75-155">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>



<span data-ttu-id="32c75-156">将下面的脚本复制到文本编辑器（如记事本）或[Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)中。</span><span class="sxs-lookup"><span data-stu-id="32c75-156">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="32c75-157">将\* \<SecurityGroupName\> \*替换为您创建的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="32c75-157">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="32c75-158">例如：</span><span class="sxs-lookup"><span data-stu-id="32c75-158">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="32c75-159">将文件另存为 GroupCreators。</span><span class="sxs-lookup"><span data-stu-id="32c75-159">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="32c75-160">在 PowerShell 窗口中，导航到保存文件的位置（键入 "CD <FileLocation>"）。</span><span class="sxs-lookup"><span data-stu-id="32c75-160">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="32c75-161">通过键入以下命令运行脚本：</span><span class="sxs-lookup"><span data-stu-id="32c75-161">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="32c75-162">出现提示时，[使用管理员帐户登录](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription)。</span><span class="sxs-lookup"><span data-stu-id="32c75-162">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<SecurityGroupName>"
$AllowGroupCreation = "False"

Connect-AzureAD

$settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
if(!$settingsObjectID)
{
      $template = Get-AzureADDirectorySettingTemplate | Where-object {$_.displayname -eq "group.unified"}
    $settingsCopy = $template.CreateDirectorySetting()
    New-AzureADDirectorySetting -DirectorySetting $settingsCopy
    $settingsObjectID = (Get-AzureADDirectorySetting | Where-object -Property Displayname -Value "Group.Unified" -EQ).id
}

$settingsCopy = Get-AzureADDirectorySetting -Id $settingsObjectID
$settingsCopy["EnableGroupCreation"] = $AllowGroupCreation

if($GroupName)
{
    $settingsCopy["GroupCreationAllowedGroupId"] = (Get-AzureADGroup -SearchString $GroupName).objectid
}
 else {
$settingsCopy["GroupCreationAllowedGroupId"] = $GroupName
}
Set-AzureADDirectorySetting -Id $settingsObjectID -DirectorySetting $settingsCopy

(Get-AzureADDirectorySetting -Id $settingsObjectID).Values
```

<span data-ttu-id="32c75-163">脚本的最后一行将显示更新的设置：</span><span class="sxs-lookup"><span data-stu-id="32c75-163">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="32c75-165">如果将来您想要更改所使用的安全组，则可以使用新安全组的名称重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="32c75-165">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="32c75-166">如果要关闭组创建限制，并再次允许所有用户创建组，请将 $GroupName 设置为 "" 并 $AllowGroupCreation 为 "True"，然后重新运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="32c75-166">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="32c75-167">步骤4：验证它是否正常运行</span><span class="sxs-lookup"><span data-stu-id="32c75-167">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="32c75-168">使用不应具备组创建权限的人员的用户帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="32c75-168">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="32c75-169">也就是说，它们不是您创建的安全组的成员，也不是管理员的成员。</span><span class="sxs-lookup"><span data-stu-id="32c75-169">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="32c75-170">选择 " **Planner** " 磁贴。</span><span class="sxs-lookup"><span data-stu-id="32c75-170">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="32c75-171">在 Planner 中，选择左侧导航中的 "**新建计划**" 以创建一个计划。</span><span class="sxs-lookup"><span data-stu-id="32c75-171">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="32c75-172">您应该会收到一条消息，指出计划和组创建已禁用。</span><span class="sxs-lookup"><span data-stu-id="32c75-172">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="32c75-173">请使用安全组的成员再次尝试相同的过程。</span><span class="sxs-lookup"><span data-stu-id="32c75-173">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="32c75-174">如果安全组的成员无法创建组，请检查它们是否通过[OWA 邮箱策略](https://go.microsoft.com/fwlink/?linkid=852135)被阻止。</span><span class="sxs-lookup"><span data-stu-id="32c75-174">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="32c75-175">相关文章</span><span class="sxs-lookup"><span data-stu-id="32c75-175">Related articles</span></span>

[<span data-ttu-id="32c75-176">Office 365 PowerShell 入门</span><span class="sxs-lookup"><span data-stu-id="32c75-176">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="32c75-177">在 Azure Active Directory 中设置自助服务组管理</span><span class="sxs-lookup"><span data-stu-id="32c75-177">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="32c75-178">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="32c75-178">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="32c75-179">用于配置组设置的 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="32c75-179">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
