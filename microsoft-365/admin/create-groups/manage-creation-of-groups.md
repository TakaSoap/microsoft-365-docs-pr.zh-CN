---
title: 管理可创建 Office 365 组的人员
f1.keywords:
- NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: pamgreen
audience: Admin
ms.topic: get-started-article
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
ms.openlocfilehash: 1f0d3109d1102c740a9be0b670e618eac982e6e2
ms.sourcegitcommit: ca2b58ef8f5be24f09e73620b74a1ffcf2d4c290
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/24/2020
ms.locfileid: "42238074"
---
# <a name="manage-who-can-create-office-365-groups"></a><span data-ttu-id="8e662-103">管理可创建 Office 365 组的人员</span><span class="sxs-lookup"><span data-stu-id="8e662-103">Manage who can create Office 365 Groups</span></span>

  
<span data-ttu-id="8e662-104">由于用户可以很轻松地创建 Office 365 组，因此你不会收到代表其他人创建这些组的请求。</span><span class="sxs-lookup"><span data-stu-id="8e662-104">Because it's so easy for users to create Office 365 Groups, you aren't inundated with requests to create them on behalf of other people.</span></span> <span data-ttu-id="8e662-105">但是，根据您的业务，您可能希望控制谁能够创建组。</span><span class="sxs-lookup"><span data-stu-id="8e662-105">Depending on your business, however, you might want to control who has the ability to create groups.</span></span>
  
<span data-ttu-id="8e662-106">本文介绍如何 **在所有使用组的 Office 365 服务中** 禁用组创建权限：</span><span class="sxs-lookup"><span data-stu-id="8e662-106">This article explains how to disable the ability to create groups **in all Office 365 services that use groups**:</span></span> 
  
- <span data-ttu-id="8e662-107">Outlook</span><span class="sxs-lookup"><span data-stu-id="8e662-107">Outlook</span></span>
    
- <span data-ttu-id="8e662-108">SharePoint</span><span class="sxs-lookup"><span data-stu-id="8e662-108">SharePoint</span></span>
    
- <span data-ttu-id="8e662-109">Yammer</span><span class="sxs-lookup"><span data-stu-id="8e662-109">Yammer</span></span>
    
- <span data-ttu-id="8e662-110">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="8e662-110">Microsoft Teams</span></span>

- <span data-ttu-id="8e662-111">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="8e662-111">Microsoft Stream</span></span>
    
- <span data-ttu-id="8e662-112">StaffHub</span><span class="sxs-lookup"><span data-stu-id="8e662-112">StaffHub</span></span>
    
- <span data-ttu-id="8e662-113">Planner</span><span class="sxs-lookup"><span data-stu-id="8e662-113">Planner</span></span>
    
- <span data-ttu-id="8e662-114">PowerBI</span><span class="sxs-lookup"><span data-stu-id="8e662-114">PowerBI</span></span>

- <span data-ttu-id="8e662-115">路线图</span><span class="sxs-lookup"><span data-stu-id="8e662-115">Roadmap</span></span>
    
<span data-ttu-id="8e662-116">您可以将 Office 365 组创建限制为特定安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="8e662-116">You can restrict Office 365 Group creation to the members of a particular security group.</span></span> <span data-ttu-id="8e662-117">若要配置此设置，请使用 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8e662-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="8e662-118">本文将引导您完成所需的步骤。</span><span class="sxs-lookup"><span data-stu-id="8e662-118">This article walks you through the needed steps.</span></span>
  
<span data-ttu-id="8e662-119">本文中的步骤不会阻止某些角色的成员创建组。</span><span class="sxs-lookup"><span data-stu-id="8e662-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="8e662-120">Office 365 全局管理员可以通过任何方式创建组，例如 Microsoft 365 管理中心、Planner、团队、Exchange 和 SharePoint Online。</span><span class="sxs-lookup"><span data-stu-id="8e662-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="8e662-121">其他角色可以通过有限的方法创建组，如下所示。</span><span class="sxs-lookup"><span data-stu-id="8e662-121">Other roles can create Groups via limited means, listed below.</span></span>
        
  - <span data-ttu-id="8e662-122">Exchange 管理员： Exchange 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8e662-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="8e662-123">合作伙伴第1层支持： Microsoft 365 管理中心、Exchange 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8e662-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="8e662-124">合作伙伴第2层支持： Microsoft 365 管理中心、Exchange 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8e662-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
    
  - <span data-ttu-id="8e662-125">目录写入程序： Azure AD</span><span class="sxs-lookup"><span data-stu-id="8e662-125">Directory Writers: Azure AD</span></span>

  - <span data-ttu-id="8e662-126">SharePoint 管理员： SharePoint 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8e662-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="8e662-127">团队服务管理员：团队管理员中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8e662-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
  
  - <span data-ttu-id="8e662-128">用户管理管理员： Microsoft 365 管理中心、Yammer、Azure AD</span><span class="sxs-lookup"><span data-stu-id="8e662-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>
     
<span data-ttu-id="8e662-129">如果你属于以上其中一种角色的成员，则可以为受限用户创建 Office 365 组，然后将该用户分配为组所有者。</span><span class="sxs-lookup"><span data-stu-id="8e662-129">If you're a member of one of these roles, you can create Office 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span> <span data-ttu-id="8e662-130">具有此角色的用户可以在 Yammer 中创建连接的组，而不考虑可能阻止创建的任何 PowerShell 设置。</span><span class="sxs-lookup"><span data-stu-id="8e662-130">Users that have this role are able to create connected groups in Yammer, regardless of any PowerShell settings that might prevent creation.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="8e662-131">许可要求</span><span class="sxs-lookup"><span data-stu-id="8e662-131">Licensing requirements</span></span>

<span data-ttu-id="8e662-132">若要管理创建组的人员，以下人员需要分配给它们的 Azure AD Premium 许可证或 Azure AD 基本 EDU 许可证：</span><span class="sxs-lookup"><span data-stu-id="8e662-132">To manage who creates Groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="8e662-133">配置这些组创建设置的管理员</span><span class="sxs-lookup"><span data-stu-id="8e662-133">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="8e662-134">允许创建组的安全组的成员</span><span class="sxs-lookup"><span data-stu-id="8e662-134">The members of the security group who are allowed to create Groups</span></span>

<span data-ttu-id="8e662-135">以下人员不需要为其分配 Azure AD Premium 或 Azure AD 基本 EDU 许可证：</span><span class="sxs-lookup"><span data-stu-id="8e662-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="8e662-136">属于 Office 365 组成员并不能创建其他组的人员。</span><span class="sxs-lookup"><span data-stu-id="8e662-136">People who are members of Office 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-security-group-for-users-who-need-to-create-office-365-groups"></a><span data-ttu-id="8e662-137">步骤 1：为需要创建 Office 365 组 的用户创建一个安全组</span><span class="sxs-lookup"><span data-stu-id="8e662-137">Step 1: Create a security group for users who need to create Office 365 Groups</span></span>

<span data-ttu-id="8e662-138">您的组织中仅有一个安全组可用于控制能够创建组的用户。</span><span class="sxs-lookup"><span data-stu-id="8e662-138">Only one security group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="8e662-139">但是，你可以将其他安全组包含在内作为该组的成员。</span><span class="sxs-lookup"><span data-stu-id="8e662-139">But, you can nest other security groups as members of this group.</span></span> <span data-ttu-id="8e662-140">例如，名为"允许创建组"的组作为指定的安全组，名为"Microsoft Planner 用户"和"Exchange Online 用户"的组作为该安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="8e662-140">For example, the group named Allow Group Creation is the designated security group, and the groups named Microsoft Planner Users and Exchange Online Users are members of that group.</span></span>

<span data-ttu-id="8e662-141">上面列出的角色中的管理员不需要是该组的成员：它们保留了其创建组的能力。</span><span class="sxs-lookup"><span data-stu-id="8e662-141">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="8e662-142">请务必使用**安全组**来限制可以创建组的用户。</span><span class="sxs-lookup"><span data-stu-id="8e662-142">Be sure to use a **security group** to restrict who can create groups.</span></span> <span data-ttu-id="8e662-143">如果尝试使用 Office 365 组，则成员无法通过 SharePoint 创建组，因为它会检查是否存在安全组。</span><span class="sxs-lookup"><span data-stu-id="8e662-143">If you try to use an Office 365 Group, members won't be able to create a group from SharePoint because it checks for a security group.</span></span> 
    
1. <span data-ttu-id="8e662-144">在 "管理中心" 中，转到 "**组** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">组</a>" 页面。</span><span class="sxs-lookup"><span data-stu-id="8e662-144">In the admin center, go to the **Groups** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2052855" target="_blank">Groups</a> page.</span></span>

2. <span data-ttu-id="8e662-145">单击 "**添加组**"。</span><span class="sxs-lookup"><span data-stu-id="8e662-145">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="8e662-146">选择 "**安全**" 作为组类型。</span><span class="sxs-lookup"><span data-stu-id="8e662-146">Choose **Security** as the group type.</span></span> <span data-ttu-id="8e662-147">请记住该组的名称！</span><span class="sxs-lookup"><span data-stu-id="8e662-147">Remember the name of the group!</span></span> <span data-ttu-id="8e662-148">稍后需要用到该名称。</span><span class="sxs-lookup"><span data-stu-id="8e662-148">You'll need it later.</span></span>
  
4. <span data-ttu-id="8e662-149">完成设置安全组，添加你希望能够在你的组织中创建组的人员或其他安全组。</span><span class="sxs-lookup"><span data-stu-id="8e662-149">Finish setting up the security group, adding people or other security groups who you want to be able to create Groups in your org.</span></span>
    
<span data-ttu-id="8e662-150">有关详细说明，请参阅[在 Microsoft 365 管理中心中创建、编辑或删除安全组](../email/create-edit-or-delete-a-security-group.md)。</span><span class="sxs-lookup"><span data-stu-id="8e662-150">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../email/create-edit-or-delete-a-security-group.md).</span></span>
  
## <a name="step-2-install-the-preview-version-of-the-azure-active-directory-powershell-for-graph"></a><span data-ttu-id="8e662-151">步骤2：为 Graph 安装 Azure Active Directory PowerShell 的预览版本</span><span class="sxs-lookup"><span data-stu-id="8e662-151">Step 2: Install the preview version of the Azure Active Directory PowerShell for Graph</span></span>

<span data-ttu-id="8e662-152">这些过程需要 Azure Active Directory PowerShell 的预览版本的图形。</span><span class="sxs-lookup"><span data-stu-id="8e662-152">These procedures require the preview version of the Azure Active Directory PowerShell for Graph.</span></span> <span data-ttu-id="8e662-153">GA 版本将不起作用。</span><span class="sxs-lookup"><span data-stu-id="8e662-153">The GA version will not work.</span></span>


> [!IMPORTANT]
> <span data-ttu-id="8e662-154">无法同时在同一台计算机上安装预览版本和 GA 版本。</span><span class="sxs-lookup"><span data-stu-id="8e662-154">You cannot install both the preview and GA versions on the same computer at the same time.</span></span> <span data-ttu-id="8e662-155">你可以在 windows 10 Windows Server 2016 上安装该模块。</span><span class="sxs-lookup"><span data-stu-id="8e662-155">You can install the module on Windows 10, Windows Server 2016.</span></span>

  
<span data-ttu-id="8e662-156">建议的最佳做法是 *始终*  保持最新：先卸载旧的 AzureADPreview 或 AzureAD 版本，然后再获取最新版本。</span><span class="sxs-lookup"><span data-stu-id="8e662-156">As a best practice, we recommend  *always*  staying current: uninstall the old AzureADPreview or old AzureAD version and get the latest one.</span></span> 
  
1. <span data-ttu-id="8e662-157">在搜索栏中，键入 Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="8e662-157">In your search bar, type Windows PowerShell.</span></span>
    
2. <span data-ttu-id="8e662-158">右键单击 **Windows PowerShell**，然后选择" **以管理员身份运行**"。</span><span class="sxs-lookup"><span data-stu-id="8e662-158">Right-click on **Windows PowerShell** and select **Run as Administrator**.</span></span>
    
    ![通过'以管理员身份运行'打开 PowerShell。](../media/52517af8-c7b0-4c8f-b2f3-0f82f9d5ace1.png)
  
2. <span data-ttu-id="8e662-160">检查已安装的模块：</span><span class="sxs-lookup"><span data-stu-id="8e662-160">Check installed module:</span></span>
    
    ```
    Get-InstalledModule -Name "AzureAD*"
    ```

3. <span data-ttu-id="8e662-161">3.要卸载早期版本的 AzureADPreview 或 AzureAD，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="8e662-161">To uninstall a previous version of AzureADPreview or AzureAD, run this command:</span></span>
  
    ```
    Uninstall-Module AzureADPreview
    ```

    <span data-ttu-id="8e662-162">或者</span><span class="sxs-lookup"><span data-stu-id="8e662-162">or</span></span>
  
    ```
    Uninstall-Module AzureAD
    ```

4. <span data-ttu-id="8e662-163">To install the latest version of AzureADPreview, run this command:</span><span class="sxs-lookup"><span data-stu-id="8e662-163">To install the latest version of AzureADPreview, run this command:</span></span>
  
    ```
    Install-Module AzureADPreview
    ```

    <span data-ttu-id="8e662-164">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install. </span><span class="sxs-lookup"><span data-stu-id="8e662-164">At the message about an untrusted repository, type **Y**. It will take a minute or so for the new module to install.</span></span>

<span data-ttu-id="8e662-165">在下面的步骤3中，让 PowerShell 窗口保持打开状态。</span><span class="sxs-lookup"><span data-stu-id="8e662-165">Leave the PowerShell window open for Step 3, below.</span></span>
  
## <a name="step-3-run-powershell-commands"></a><span data-ttu-id="8e662-166">步骤3：运行 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="8e662-166">Step 3: Run PowerShell commands</span></span>

<span data-ttu-id="8e662-167">将下面的脚本复制到文本编辑器（如记事本）或[Windows POWERSHELL ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)中。</span><span class="sxs-lookup"><span data-stu-id="8e662-167">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="8e662-168">将\* \<SecurityGroupName\> \*替换为您创建的安全组的名称。</span><span class="sxs-lookup"><span data-stu-id="8e662-168">Replace *\<SecurityGroupName\>* with the name of the security group that you created.</span></span> <span data-ttu-id="8e662-169">例如：</span><span class="sxs-lookup"><span data-stu-id="8e662-169">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="8e662-170">将文件另存为 GroupCreators。</span><span class="sxs-lookup"><span data-stu-id="8e662-170">Save the file as GroupCreators.ps1.</span></span> 

<span data-ttu-id="8e662-171">在 PowerShell 窗口中，导航到保存文件的位置（键入 "CD <FileLocation>"）。</span><span class="sxs-lookup"><span data-stu-id="8e662-171">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="8e662-172">通过键入以下命令运行脚本：</span><span class="sxs-lookup"><span data-stu-id="8e662-172">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="8e662-173">出现提示时，[使用管理员帐户登录](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription)。</span><span class="sxs-lookup"><span data-stu-id="8e662-173">and [sign in with your administrator account](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#step-2-connect-to-azure-ad-for-your-office-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="8e662-174">脚本的最后一行将显示更新的设置：</span><span class="sxs-lookup"><span data-stu-id="8e662-174">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="8e662-176">如果将来您想要更改所使用的安全组，则可以使用新安全组的名称重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="8e662-176">If in the future you want to change which security group is used, you can rerun the script with the name of the new security group.</span></span>

<span data-ttu-id="8e662-177">如果要关闭组创建限制，并再次允许所有用户创建组，请将 $GroupName 设置为 "" 并 $AllowGroupCreation 为 "True"，然后重新运行该脚本。</span><span class="sxs-lookup"><span data-stu-id="8e662-177">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>
    
## <a name="step-4-verify-that-it-works"></a><span data-ttu-id="8e662-178">步骤4：验证它是否正常运行</span><span class="sxs-lookup"><span data-stu-id="8e662-178">Step 4: Verify that it works</span></span>

1. <span data-ttu-id="8e662-179">使用不应具备组创建权限的人员的用户帐户登录 Office 365。</span><span class="sxs-lookup"><span data-stu-id="8e662-179">Sign in to Office 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="8e662-180">也就是说，它们不是您创建的安全组的成员，也不是管理员的成员。</span><span class="sxs-lookup"><span data-stu-id="8e662-180">That is, they are not a member of the security group you created or an administrator.</span></span>
    
2. <span data-ttu-id="8e662-181">选择 " **Planner** " 磁贴。</span><span class="sxs-lookup"><span data-stu-id="8e662-181">Select the **Planner** tile.</span></span> 
    
3. <span data-ttu-id="8e662-182">在 Planner 中，选择左侧导航中的 "**新建计划**" 以创建一个计划。</span><span class="sxs-lookup"><span data-stu-id="8e662-182">In Planner, select **New Plan** in the left navigation to create a plan.</span></span> 
  
4. <span data-ttu-id="8e662-183">您应该会收到一条消息，指出计划和组创建已禁用。</span><span class="sxs-lookup"><span data-stu-id="8e662-183">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="8e662-184">请使用安全组的成员再次尝试相同的过程。</span><span class="sxs-lookup"><span data-stu-id="8e662-184">Try the same procedure again with a member of the security group.</span></span>

> [!NOTE]
> <span data-ttu-id="8e662-185">如果安全组的成员无法创建组，请检查它们是否通过[OWA 邮箱策略](https://go.microsoft.com/fwlink/?linkid=852135)被阻止。</span><span class="sxs-lookup"><span data-stu-id="8e662-185">If members of the security group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>
    
## <a name="related-articles"></a><span data-ttu-id="8e662-186">相关文章</span><span class="sxs-lookup"><span data-stu-id="8e662-186">Related articles</span></span>

[<span data-ttu-id="8e662-187">Office 365 PowerShell 入门</span><span class="sxs-lookup"><span data-stu-id="8e662-187">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="8e662-188">在 Azure Active Directory 中设置自助服务组管理</span><span class="sxs-lookup"><span data-stu-id="8e662-188">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="8e662-189">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="8e662-189">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="8e662-190">用于配置组设置的 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="8e662-190">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
