---
title: 管理可以创建 Microsoft 365 组的人
f1.keywords: NOCSH
ms.author: mikeplum
ms.reviewer: arvaradh
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- m365solution-collabgovernance
search.appverid:
- MET150
ms.assetid: 4c46c8cb-17d0-44b5-9776-005fced8e618
description: 了解如何控制哪些用户可以创建 Microsoft 365 组。
ms.openlocfilehash: 3fa430e44c272e5ababbfb0e4befba707c72c1ba
ms.sourcegitcommit: 719b89baca1bae14455acf2e517ec18fc473636c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50122380"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="7c50b-103">管理可以创建 Microsoft 365 组的人</span><span class="sxs-lookup"><span data-stu-id="7c50b-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="7c50b-104">默认情况下，所有用户都可以创建 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="7c50b-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="7c50b-105">这是推荐的方法，因为它允许用户开始协作，而无需 IT 人员协助。</span><span class="sxs-lookup"><span data-stu-id="7c50b-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="7c50b-106">如果您的企业要求您限制可以创建组的人，您可以按照本文中的过程操作。</span><span class="sxs-lookup"><span data-stu-id="7c50b-106">If your business requires that you restrict who can create groups, you can do so by following the procedures in this article.</span></span> <span data-ttu-id="7c50b-107">当您限制可以创建组的人时，它将影响依赖组访问的所有服务，包括：</span><span class="sxs-lookup"><span data-stu-id="7c50b-107">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="7c50b-108">Outlook</span><span class="sxs-lookup"><span data-stu-id="7c50b-108">Outlook</span></span>
- <span data-ttu-id="7c50b-109">SharePoint</span><span class="sxs-lookup"><span data-stu-id="7c50b-109">SharePoint</span></span>
- <span data-ttu-id="7c50b-110">Yammer</span><span class="sxs-lookup"><span data-stu-id="7c50b-110">Yammer</span></span>
- <span data-ttu-id="7c50b-111">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="7c50b-111">Microsoft Teams</span></span>
- <span data-ttu-id="7c50b-112">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="7c50b-112">Microsoft Stream</span></span>
- <span data-ttu-id="7c50b-113">Planner</span><span class="sxs-lookup"><span data-stu-id="7c50b-113">Planner</span></span>
- <span data-ttu-id="7c50b-114">Power BI (经典) </span><span class="sxs-lookup"><span data-stu-id="7c50b-114">Power BI (classic)</span></span>
- <span data-ttu-id="7c50b-115">Project 网页/路线图</span><span class="sxs-lookup"><span data-stu-id="7c50b-115">Project for the web / Roadmap</span></span>

<span data-ttu-id="7c50b-116">可以将 Microsoft 365 组创建限制为特定 Microsoft 365 组或安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="7c50b-116">You can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span> <span data-ttu-id="7c50b-117">若要配置此配置，请使用Windows PowerShell。</span><span class="sxs-lookup"><span data-stu-id="7c50b-117">To configure this, you use Windows PowerShell.</span></span> <span data-ttu-id="7c50b-118">本文将指导你完成所需步骤。</span><span class="sxs-lookup"><span data-stu-id="7c50b-118">This article walks you through the needed steps.</span></span>

<span data-ttu-id="7c50b-119">本文中的步骤不会阻止某些角色的成员创建组。</span><span class="sxs-lookup"><span data-stu-id="7c50b-119">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="7c50b-120">Office 365 全局管理员可以通过任何方式（如 Microsoft 365 管理中心、Planner、Teams、Exchange 和 SharePoint Online）创建组。</span><span class="sxs-lookup"><span data-stu-id="7c50b-120">Office 365 Global admins can create Groups via any means, such as the Microsoft 365 admin center, Planner, Teams, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="7c50b-121">其他角色可以通过有限的方式创建组，如下所示。</span><span class="sxs-lookup"><span data-stu-id="7c50b-121">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="7c50b-122">Exchange 管理员：Exchange 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c50b-122">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="7c50b-123">合作伙伴层 1 支持：Microsoft 365 管理中心、Exchange 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c50b-123">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="7c50b-124">合作伙伴层 2 支持：Microsoft 365 管理中心、Exchange 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c50b-124">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="7c50b-125">目录编写器：Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c50b-125">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="7c50b-126">SharePoint 管理员：SharePoint 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c50b-126">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="7c50b-127">Teams 服务管理员：Teams 管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c50b-127">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="7c50b-128">用户管理管理员：Microsoft 365 管理中心、Yammer、Azure AD</span><span class="sxs-lookup"><span data-stu-id="7c50b-128">User Management Administrator: Microsoft 365 Admin center, Yammer, Azure AD</span></span>

<span data-ttu-id="7c50b-129">如果你是其中一个角色的成员，你可以为受限用户创建 Microsoft 365 组，然后将该用户分配为组的所有者。</span><span class="sxs-lookup"><span data-stu-id="7c50b-129">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="7c50b-130">许可要求</span><span class="sxs-lookup"><span data-stu-id="7c50b-130">Licensing requirements</span></span>

<span data-ttu-id="7c50b-131">若要管理创建组的用户，以下人员需要分配给他们的 Azure AD Premium 许可证或 Azure AD Basic EDU 许可证：</span><span class="sxs-lookup"><span data-stu-id="7c50b-131">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7c50b-132">配置这些组创建设置的管理员</span><span class="sxs-lookup"><span data-stu-id="7c50b-132">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="7c50b-133">允许创建组的组的成员</span><span class="sxs-lookup"><span data-stu-id="7c50b-133">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="7c50b-134">请参阅 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) 门户中的分配或删除许可证，了解有关如何分配 Azure 许可证的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="7c50b-134">See [Assign or remove licenses in the Azure Active Directory portal](https://docs.microsoft.com/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="7c50b-135">以下人员不需要为其分配 Azure AD Premium 或 Azure AD Basic EDU 许可证：</span><span class="sxs-lookup"><span data-stu-id="7c50b-135">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="7c50b-136">作为 Microsoft 365 组的成员且无法创建其他组的人。</span><span class="sxs-lookup"><span data-stu-id="7c50b-136">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="7c50b-137">步骤 1：为需要创建 Microsoft 365 组的用户创建组</span><span class="sxs-lookup"><span data-stu-id="7c50b-137">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="7c50b-138">组织中只能使用一个组来控制能够创建组的人。</span><span class="sxs-lookup"><span data-stu-id="7c50b-138">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="7c50b-139">但是，可以将其他组嵌套为此组的成员。</span><span class="sxs-lookup"><span data-stu-id="7c50b-139">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="7c50b-140">上述角色中的管理员无需是此组的成员：他们保留创建组的能力。</span><span class="sxs-lookup"><span data-stu-id="7c50b-140">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="7c50b-141">在管理中心，转到"组 ["页](https://admin.microsoft.com/adminportal/home#/groups)。</span><span class="sxs-lookup"><span data-stu-id="7c50b-141">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="7c50b-142">单击 **"添加组"。**</span><span class="sxs-lookup"><span data-stu-id="7c50b-142">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="7c50b-143">选择您想要的组类型。</span><span class="sxs-lookup"><span data-stu-id="7c50b-143">Choose the group type you want.</span></span> <span data-ttu-id="7c50b-144">请记住该组的名称！</span><span class="sxs-lookup"><span data-stu-id="7c50b-144">Remember the name of the group!</span></span> <span data-ttu-id="7c50b-145">稍后需要用到该名称。</span><span class="sxs-lookup"><span data-stu-id="7c50b-145">You'll need it later.</span></span>

4. <span data-ttu-id="7c50b-146">完成组设置，添加您希望能够在您的组织中创建组的人或其他组。</span><span class="sxs-lookup"><span data-stu-id="7c50b-146">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="7c50b-147">有关详细说明，请参阅 [在 Microsoft 365](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group)管理中心创建、编辑或删除安全组。</span><span class="sxs-lookup"><span data-stu-id="7c50b-147">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/email/create-edit-or-delete-a-security-group).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="7c50b-148">步骤 2：运行 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="7c50b-148">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="7c50b-149">必须使用适用于 Graph (AzureAD)  (模块名称 **AzureADPreview**) 的 [Azure Active Directory PowerShell](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2)预览版更改组级来宾访问设置：</span><span class="sxs-lookup"><span data-stu-id="7c50b-149">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="7c50b-150">如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)并按照说明安装公共预览版。</span><span class="sxs-lookup"><span data-stu-id="7c50b-150">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="7c50b-151">如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。</span><span class="sxs-lookup"><span data-stu-id="7c50b-151">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="7c50b-152">如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="7c50b-152">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="7c50b-153">将下面的脚本复制到文本编辑器（如记事本）或 Windows PowerShell [ISE。](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)</span><span class="sxs-lookup"><span data-stu-id="7c50b-153">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](https://docs.microsoft.com/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="7c50b-154">*\<GroupName\>* 替换为您创建的组的名称。</span><span class="sxs-lookup"><span data-stu-id="7c50b-154">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="7c50b-155">例如：</span><span class="sxs-lookup"><span data-stu-id="7c50b-155">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="7c50b-156">将文件另存为GroupCreators.ps1。</span><span class="sxs-lookup"><span data-stu-id="7c50b-156">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="7c50b-157">在 PowerShell 窗口中，导航到保存文件的位置 <FileLocation> ， ("CD") 。</span><span class="sxs-lookup"><span data-stu-id="7c50b-157">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="7c50b-158">通过键入以下命令运行脚本：</span><span class="sxs-lookup"><span data-stu-id="7c50b-158">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="7c50b-159">[在系统提示时使用管理员帐户](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)登录。</span><span class="sxs-lookup"><span data-stu-id="7c50b-159">and [sign in with your administrator account](https://docs.microsoft.com/microsoft-365/enterprise/connect-to-microsoft-365-powershell#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

```PowerShell
$GroupName = "<GroupName>"
$AllowGroupCreation = $False

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

<span data-ttu-id="7c50b-160">脚本的最后一行将显示更新的设置：</span><span class="sxs-lookup"><span data-stu-id="7c50b-160">The last line of the script will display the updated settings:</span></span>

![This is what your settings will look like when you're done.](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="7c50b-162">如果将来要更改使用哪个组，可以使用新组的名称重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="7c50b-162">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="7c50b-163">如果要关闭组创建限制，并再次允许所有用户创建组，$GroupName设置为""，$AllowGroupCreation设置为"True"，然后重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="7c50b-163">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="7c50b-164">步骤 3：验证有效性</span><span class="sxs-lookup"><span data-stu-id="7c50b-164">Step 3: Verify that it works</span></span>

<span data-ttu-id="7c50b-165">更改可能需要 30 分钟或更多时间才能生效。</span><span class="sxs-lookup"><span data-stu-id="7c50b-165">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="7c50b-166">可以通过执行以下操作来验证新设置：</span><span class="sxs-lookup"><span data-stu-id="7c50b-166">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="7c50b-167">使用不应能够创建组的用户的用户帐户登录 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="7c50b-167">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="7c50b-168">也就是说，他们不是您创建的组的成员或管理员。</span><span class="sxs-lookup"><span data-stu-id="7c50b-168">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="7c50b-169">选择 **Planner** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="7c50b-169">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="7c50b-170">在 Planner 中 **，选择** 左侧导航栏中的"新建计划"以创建计划。</span><span class="sxs-lookup"><span data-stu-id="7c50b-170">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="7c50b-171">应收到一条消息，指出已禁用计划和组创建。</span><span class="sxs-lookup"><span data-stu-id="7c50b-171">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="7c50b-172">请再次与组的成员尝试相同的过程。</span><span class="sxs-lookup"><span data-stu-id="7c50b-172">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="7c50b-173">如果组的成员无法创建组，请检查他们是否未通过 OWA 邮箱策略 [被阻止](https://go.microsoft.com/fwlink/?linkid=852135)。</span><span class="sxs-lookup"><span data-stu-id="7c50b-173">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](https://go.microsoft.com/fwlink/?linkid=852135).</span></span>

## <a name="related-topics"></a><span data-ttu-id="7c50b-174">相关主题</span><span class="sxs-lookup"><span data-stu-id="7c50b-174">Related topics</span></span>

[<span data-ttu-id="7c50b-175">协作治理规划分步规划</span><span class="sxs-lookup"><span data-stu-id="7c50b-175">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="7c50b-176">创建协作治理计划</span><span class="sxs-lookup"><span data-stu-id="7c50b-176">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="7c50b-177">Office 365 PowerShell 入门</span><span class="sxs-lookup"><span data-stu-id="7c50b-177">Getting started with Office 365 PowerShell</span></span>](https://go.microsoft.com/fwlink/p/?LinkId=808033)

[<span data-ttu-id="7c50b-178">在 Azure Active Directory 中设置自助服务组管理</span><span class="sxs-lookup"><span data-stu-id="7c50b-178">Set up self-service group management in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="7c50b-179">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="7c50b-179">Set-ExecutionPolicy</span></span>](https://docs.microsoft.com/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="7c50b-180">用于配置组设置的 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="7c50b-180">Azure Active Directory cmdlets for configuring group settings</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
