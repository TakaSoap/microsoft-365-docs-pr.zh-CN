---
title: 管理可创建 Microsoft 365 组的人员
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
recommendations: false
description: 了解如何控制哪些用户可以创建Microsoft 365组。
ms.openlocfilehash: 19a106d255708f4b1df8f798219ea7ea778bbef3
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52539175"
---
# <a name="manage-who-can-create-microsoft-365-groups"></a><span data-ttu-id="f8f04-103">管理可创建 Microsoft 365 组的人员</span><span class="sxs-lookup"><span data-stu-id="f8f04-103">Manage who can create Microsoft 365 Groups</span></span>

<span data-ttu-id="f8f04-104">默认情况下，所有用户都可以创建Microsoft 365组。</span><span class="sxs-lookup"><span data-stu-id="f8f04-104">By default, all users can create Microsoft 365 groups.</span></span> <span data-ttu-id="f8f04-105">这是推荐的方法，因为它允许用户无需 IT 协助即可开始协作。</span><span class="sxs-lookup"><span data-stu-id="f8f04-105">This is the recommended approach because it allows users to start collaborating without requiring assistance from IT.</span></span>

<span data-ttu-id="f8f04-106">如果您的企业要求您限制可以创建组Microsoft 365，您可以将组创建限制为特定组Microsoft 365安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="f8f04-106">If your business requires that you restrict who can create groups, you can restrict Microsoft 365 Group creation to the members of a particular Microsoft 365 group or security group.</span></span>

<span data-ttu-id="f8f04-107">如果你担心用户创建不符合业务标准的团队或组，请考虑要求用户完成培训课程，然后将他们添加到允许的用户组。</span><span class="sxs-lookup"><span data-stu-id="f8f04-107">If you're concerned about users creating teams or groups that don't comply with your business standards, consider requiring users to complete a training course and then adding them to the group of allowed users.</span></span>

<span data-ttu-id="f8f04-108">限制可以创建组的人时，会影响依赖组访问的所有服务，包括：</span><span class="sxs-lookup"><span data-stu-id="f8f04-108">When you limit who can create a group, it affects all services that rely on groups for access, including:</span></span>

- <span data-ttu-id="f8f04-109">Outlook</span><span class="sxs-lookup"><span data-stu-id="f8f04-109">Outlook</span></span>
- <span data-ttu-id="f8f04-110">SharePoint</span><span class="sxs-lookup"><span data-stu-id="f8f04-110">SharePoint</span></span>
- <span data-ttu-id="f8f04-111">Yammer</span><span class="sxs-lookup"><span data-stu-id="f8f04-111">Yammer</span></span>
- <span data-ttu-id="f8f04-112">Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="f8f04-112">Microsoft Teams</span></span>
- <span data-ttu-id="f8f04-113">Microsoft Stream</span><span class="sxs-lookup"><span data-stu-id="f8f04-113">Microsoft Stream</span></span>
- <span data-ttu-id="f8f04-114">Planner</span><span class="sxs-lookup"><span data-stu-id="f8f04-114">Planner</span></span>
- <span data-ttu-id="f8f04-115">Power BI (经典) </span><span class="sxs-lookup"><span data-stu-id="f8f04-115">Power BI (classic)</span></span>
- <span data-ttu-id="f8f04-116">Project Web/路线图</span><span class="sxs-lookup"><span data-stu-id="f8f04-116">Project for the web / Roadmap</span></span>

<span data-ttu-id="f8f04-117">本文中的步骤不会阻止某些角色的成员创建组。</span><span class="sxs-lookup"><span data-stu-id="f8f04-117">The steps in this article won't prevent members of certain roles from creating Groups.</span></span> <span data-ttu-id="f8f04-118">Office 365全局管理员可以通过 Microsoft 365 管理中心、Planner、Exchange 和 SharePoint Online 创建组。</span><span class="sxs-lookup"><span data-stu-id="f8f04-118">Office 365 Global admins can create Groups via the Microsoft 365 admin center, Planner, Exchange, and SharePoint Online.</span></span> <span data-ttu-id="f8f04-119">其他角色可以通过有限的方式创建组，如下所示。</span><span class="sxs-lookup"><span data-stu-id="f8f04-119">Other roles can create Groups via limited means, listed below.</span></span>

- <span data-ttu-id="f8f04-120">Exchange管理员：Exchange管理中心，Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8f04-120">Exchange Administrator: Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="f8f04-121">合作伙伴第 1 层支持：Microsoft 365管理中心、Exchange管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8f04-121">Partner Tier 1 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="f8f04-122">合作伙伴第 2 层支持：Microsoft 365管理中心、Exchange管理中心、Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8f04-122">Partner Tier 2 Support: Microsoft 365 Admin center, Exchange Admin center, Azure AD</span></span>
- <span data-ttu-id="f8f04-123">目录编写器：Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8f04-123">Directory Writers: Azure AD</span></span>
- <span data-ttu-id="f8f04-124">SharePoint管理员：SharePoint管理中心，Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8f04-124">SharePoint Administrator: SharePoint Admin center, Azure AD</span></span>
- <span data-ttu-id="f8f04-125">Teams服务管理员：Teams管理中心，Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8f04-125">Teams Service Administrator: Teams Admin center, Azure AD</span></span>
- <span data-ttu-id="f8f04-126">用户管理员：Microsoft 365管理中心，Azure AD</span><span class="sxs-lookup"><span data-stu-id="f8f04-126">User Administrator: Microsoft 365 Admin center, Azure AD</span></span>

<span data-ttu-id="f8f04-127">如果你是其中一个角色的成员，你可以为受限用户Microsoft 365组"，然后将该用户分配为组的所有者。</span><span class="sxs-lookup"><span data-stu-id="f8f04-127">If you're a member of one of these roles, you can create Microsoft 365 Groups for restricted users, and then assign the user as the owner of the group.</span></span>

## <a name="licensing-requirements"></a><span data-ttu-id="f8f04-128">许可要求</span><span class="sxs-lookup"><span data-stu-id="f8f04-128">Licensing requirements</span></span>

<span data-ttu-id="f8f04-129">若要管理创建组的用户，以下人员需要 Azure AD 高级版或分配给他们的 Azure AD 基本 EDU 许可证：</span><span class="sxs-lookup"><span data-stu-id="f8f04-129">To manage who creates groups, the following people need Azure AD Premium licenses or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="f8f04-130">配置这些组创建设置的管理员</span><span class="sxs-lookup"><span data-stu-id="f8f04-130">The admin who configures these group creation settings</span></span>
- <span data-ttu-id="f8f04-131">允许创建组的组的成员</span><span class="sxs-lookup"><span data-stu-id="f8f04-131">The members of the group who are allowed to create groups</span></span>

> [!NOTE]
> <span data-ttu-id="f8f04-132">请参阅[在 Azure Active Directory 门户](/azure/active-directory/fundamentals/license-users-groups)中分配或删除许可证，了解有关如何分配 Azure 许可证的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="f8f04-132">See [Assign or remove licenses in the Azure Active Directory portal](/azure/active-directory/fundamentals/license-users-groups) for more details about how to assign Azure licenses.</span></span>

<span data-ttu-id="f8f04-133">以下人员不需要 Azure AD 高级版或分配给他们的 Azure AD 基本 EDU 许可证：</span><span class="sxs-lookup"><span data-stu-id="f8f04-133">The following people don't need Azure AD Premium or Azure AD Basic EDU licenses assigned to them:</span></span>

- <span data-ttu-id="f8f04-134">作为组Microsoft 365且无法创建其他组的人。</span><span class="sxs-lookup"><span data-stu-id="f8f04-134">People who are members of Microsoft 365 groups and who don't have the ability to create other groups.</span></span>

## <a name="step-1-create-a-group-for-users-who-need-to-create-microsoft-365-groups"></a><span data-ttu-id="f8f04-135">步骤 1：为需要创建组的用户Microsoft 365组</span><span class="sxs-lookup"><span data-stu-id="f8f04-135">Step 1: Create a group for users who need to create Microsoft 365 groups</span></span>

<span data-ttu-id="f8f04-136">组织中只能有一个组可用于控制能够创建组的人。</span><span class="sxs-lookup"><span data-stu-id="f8f04-136">Only one group in your organization can be used to control who is able to create Groups.</span></span> <span data-ttu-id="f8f04-137">但是，可以将其他组嵌套为此组的成员。</span><span class="sxs-lookup"><span data-stu-id="f8f04-137">But, you can nest other groups as members of this group.</span></span>

<span data-ttu-id="f8f04-138">上述角色中的管理员无需是此组的成员：他们保留创建组的能力。</span><span class="sxs-lookup"><span data-stu-id="f8f04-138">Admins in the roles listed above do not need to be members of this group: they retain their ability to create groups.</span></span>

1. <span data-ttu-id="f8f04-139">在管理中心中，转到"组 ["页面](https://admin.microsoft.com/adminportal/home#/groups)。</span><span class="sxs-lookup"><span data-stu-id="f8f04-139">In the admin center, go to the [Groups page](https://admin.microsoft.com/adminportal/home#/groups).</span></span>

2. <span data-ttu-id="f8f04-140">单击"**添加组"。**</span><span class="sxs-lookup"><span data-stu-id="f8f04-140">Click on **Add a Group**.</span></span>

3. <span data-ttu-id="f8f04-141">选择您想要的组类型。</span><span class="sxs-lookup"><span data-stu-id="f8f04-141">Choose the group type you want.</span></span> <span data-ttu-id="f8f04-142">请记住该组的名称！</span><span class="sxs-lookup"><span data-stu-id="f8f04-142">Remember the name of the group!</span></span> <span data-ttu-id="f8f04-143">稍后需要用到该名称。</span><span class="sxs-lookup"><span data-stu-id="f8f04-143">You'll need it later.</span></span>

4. <span data-ttu-id="f8f04-144">完成组设置，添加要能够在组织内创建组的人或其他组。</span><span class="sxs-lookup"><span data-stu-id="f8f04-144">Finish setting up the group, adding people or other groups who you want to be able to create groups in your org.</span></span>

<span data-ttu-id="f8f04-145">有关详细说明，请参阅在管理中心创建、编辑或删除Microsoft 365[组](../admin/email/create-edit-or-delete-a-security-group.md)。</span><span class="sxs-lookup"><span data-stu-id="f8f04-145">For detailed instructions, see [Create, edit, or delete a security group in the Microsoft 365 admin center](../admin/email/create-edit-or-delete-a-security-group.md).</span></span>

## <a name="step-2-run-powershell-commands"></a><span data-ttu-id="f8f04-146">步骤 2：运行 PowerShell 命令</span><span class="sxs-lookup"><span data-stu-id="f8f04-146">Step 2: Run PowerShell commands</span></span>

<span data-ttu-id="f8f04-147">你必须使用 [Azure Active Directory PowerShell for Graph (AzureAD](/powershell/azure/active-directory/install-adv2))  (模块名称 **AzureADPreview**) 的预览版本来更改组级别的来宾访问设置：</span><span class="sxs-lookup"><span data-stu-id="f8f04-147">You must use the preview version of [Azure Active Directory PowerShell for Graph (AzureAD)](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="f8f04-148">如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)并按照说明安装公共预览版。</span><span class="sxs-lookup"><span data-stu-id="f8f04-148">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="f8f04-149">如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。</span><span class="sxs-lookup"><span data-stu-id="f8f04-149">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="f8f04-150">如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="f8f04-150">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

<span data-ttu-id="f8f04-151">将下面的脚本复制到文本编辑器（如 记事本 或[Windows PowerShell ISE 中](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise)）。</span><span class="sxs-lookup"><span data-stu-id="f8f04-151">Copy the script below into a text editor, such as Notepad, or the [Windows PowerShell ISE](/powershell/scripting/components/ise/introducing-the-windows-powershell-ise).</span></span>

<span data-ttu-id="f8f04-152">将 *\<GroupName\>* 替换为您创建的组的名称。</span><span class="sxs-lookup"><span data-stu-id="f8f04-152">Replace *\<GroupName\>* with the name of the group that you created.</span></span> <span data-ttu-id="f8f04-153">例如：</span><span class="sxs-lookup"><span data-stu-id="f8f04-153">For example:</span></span>

`$GroupName = "Group Creators"`

<span data-ttu-id="f8f04-154">将文件另存为GroupCreators.ps1。</span><span class="sxs-lookup"><span data-stu-id="f8f04-154">Save the file as GroupCreators.ps1.</span></span>

<span data-ttu-id="f8f04-155">在 PowerShell 窗口中，导航到保存文件的位置， ("CD <FileLocation> ") 。</span><span class="sxs-lookup"><span data-stu-id="f8f04-155">In the PowerShell window, navigate to the location where you saved the file (type "CD <FileLocation>").</span></span>

<span data-ttu-id="f8f04-156">通过键入以下命令运行脚本：</span><span class="sxs-lookup"><span data-stu-id="f8f04-156">Run the script by typing:</span></span>

`.\GroupCreators.ps1`

<span data-ttu-id="f8f04-157">[，当系统提示时，使用](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription)管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f8f04-157">and [sign in with your administrator account](../enterprise/connect-to-microsoft-365-powershell.md#step-2-connect-to-azure-ad-for-your-microsoft-365-subscription) when prompted.</span></span>

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

<span data-ttu-id="f8f04-158">脚本的最后一行将显示更新的设置：</span><span class="sxs-lookup"><span data-stu-id="f8f04-158">The last line of the script will display the updated settings:</span></span>

![PowerShell 脚本输出的屏幕截图。](../media/952cd982-5139-4080-9add-24bafca0830c.png)

<span data-ttu-id="f8f04-160">如果将来要更改使用哪个组，可以使用新组的名称重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="f8f04-160">If in the future you want to change which group is used, you can rerun the script with the name of the new group.</span></span>

<span data-ttu-id="f8f04-161">如果要关闭组创建限制，并再次允许所有用户创建组，$GroupName设置为""，$AllowGroupCreation设置为"True"，然后重新运行脚本。</span><span class="sxs-lookup"><span data-stu-id="f8f04-161">If you want to turn off the group creation restriction and again allow all users to create groups, set $GroupName to "" and $AllowGroupCreation to "True" and rerun the script.</span></span>

## <a name="step-3-verify-that-it-works"></a><span data-ttu-id="f8f04-162">步骤 3：验证有效性</span><span class="sxs-lookup"><span data-stu-id="f8f04-162">Step 3: Verify that it works</span></span>

<span data-ttu-id="f8f04-163">更改可能需要 30 分钟或更多时间才能生效。</span><span class="sxs-lookup"><span data-stu-id="f8f04-163">Changes can take thirty minutes or more to take effect.</span></span> <span data-ttu-id="f8f04-164">可以通过执行以下操作来验证新设置：</span><span class="sxs-lookup"><span data-stu-id="f8f04-164">You can verify the new settings by doing the following:</span></span>

1. <span data-ttu-id="f8f04-165">使用Microsoft 365无法创建组的用户的用户帐户登录。</span><span class="sxs-lookup"><span data-stu-id="f8f04-165">Sign in to Microsoft 365 with a user account of someone who should NOT have the ability to create groups.</span></span> <span data-ttu-id="f8f04-166">即，他们不是你创建的组的成员或管理员。</span><span class="sxs-lookup"><span data-stu-id="f8f04-166">That is, they are not a member of the group you created or an administrator.</span></span>

2. <span data-ttu-id="f8f04-167">选择 **Planner** 磁贴。</span><span class="sxs-lookup"><span data-stu-id="f8f04-167">Select the **Planner** tile.</span></span>

3. <span data-ttu-id="f8f04-168">在 Planner 中， **选择** 左侧导航栏中的"新建计划"以创建计划。</span><span class="sxs-lookup"><span data-stu-id="f8f04-168">In Planner, select **New Plan** in the left navigation to create a plan.</span></span>

4. <span data-ttu-id="f8f04-169">应收到一条消息，指出已禁用计划和组创建。</span><span class="sxs-lookup"><span data-stu-id="f8f04-169">You should get a message that plan and group creation is disabled.</span></span>

<span data-ttu-id="f8f04-170">请再次与组的成员尝试相同的过程。</span><span class="sxs-lookup"><span data-stu-id="f8f04-170">Try the same procedure again with a member of the group.</span></span>

> [!NOTE]
> <span data-ttu-id="f8f04-171">如果组的成员无法创建组，请检查他们是否未通过 OWA 邮箱策略 [被阻止](/powershell/module/exchange/set-owamailboxpolicy)。</span><span class="sxs-lookup"><span data-stu-id="f8f04-171">If members of the group aren't able to create groups, check that they aren't being blocked through their [OWA mailbox policy](/powershell/module/exchange/set-owamailboxpolicy).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f8f04-172">相关主题</span><span class="sxs-lookup"><span data-stu-id="f8f04-172">Related topics</span></span>

[<span data-ttu-id="f8f04-173">协作治理规划分步规划</span><span class="sxs-lookup"><span data-stu-id="f8f04-173">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="f8f04-174">创建协作管理计划</span><span class="sxs-lookup"><span data-stu-id="f8f04-174">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="f8f04-175">Office 365 PowerShell 入门</span><span class="sxs-lookup"><span data-stu-id="f8f04-175">Getting started with Office 365 PowerShell</span></span>](../enterprise/getting-started-with-microsoft-365-powershell.md)

[<span data-ttu-id="f8f04-176">在"管理中心"中设置自助服务Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="f8f04-176">Set up self-service group management in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-self-service-management)

[<span data-ttu-id="f8f04-177">Set-ExecutionPolicy</span><span class="sxs-lookup"><span data-stu-id="f8f04-177">Set-ExecutionPolicy</span></span>](/powershell/module/microsoft.powershell.security/set-executionpolicy)

[<span data-ttu-id="f8f04-178">用于配置组设置的 Azure Active Directory cmdlet</span><span class="sxs-lookup"><span data-stu-id="f8f04-178">Azure Active Directory cmdlets for configuring group settings</span></span>](/azure/active-directory/users-groups-roles/groups-settings-cmdlets)
