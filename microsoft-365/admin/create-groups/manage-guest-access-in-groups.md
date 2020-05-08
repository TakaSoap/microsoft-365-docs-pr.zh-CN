---
title: 在 Microsoft 365 组中管理来宾访问
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
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
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 了解如何将来宾添加到 Microsoft 365 组，查看来宾用户，以及如何使用 PowerShell 控制来宾访问。
ms.openlocfilehash: 48f3339968040eeb82a93d6540c70f0bbea0754a
ms.sourcegitcommit: 7ff75a0f45371b247d975fc61cfa286f5b6f42f6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2020
ms.locfileid: "44140539"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="3b937-103">在 Microsoft 365 组中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="3b937-103">Manage guest access in Microsoft 365 groups</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="3b937-104">管理员中心正在更改。</span><span class="sxs-lookup"><span data-stu-id="3b937-104">The admin center is changing.</span></span> <span data-ttu-id="3b937-105">如果你的体验与此处提供的详细信息不匹配，请参阅[关于新的 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="3b937-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="3b937-106">默认情况下，为您的组织启用对 Microsoft 365 组的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="3b937-106">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="3b937-107">管理员可以控制是否允许来宾访问整个组织或单个组的组。</span><span class="sxs-lookup"><span data-stu-id="3b937-107">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="3b937-108">当它打开时，组成员可以通过 Web 上的 Outlook 将来宾用户邀请到 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="3b937-108">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="3b937-109">邀请将发送给组所有者以供审批。</span><span class="sxs-lookup"><span data-stu-id="3b937-109">Invitations are sent to the group owner for approval.</span></span>

> [!Note]
> <span data-ttu-id="3b937-110">处于本机模式或[欧盟地区](https://go.microsoft.com/fwlink/?linkid=2107357)的 Yammer 企业网络不支持网络来宾。</span><span class="sxs-lookup"><span data-stu-id="3b937-110">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="3b937-111">Microsoft 365 连接的 Yammer 组目前不支持来宾访问，但你可以在 Yammer 网络中创建未连接的外部组。</span><span class="sxs-lookup"><span data-stu-id="3b937-111">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="3b937-112">有关说明，请参阅[在 Yammer 中创建和管理外部组](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups)。</span><span class="sxs-lookup"><span data-stu-id="3b937-112">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

### <a name="edit-guest-information"></a><span data-ttu-id="3b937-113">编辑来宾信息</span><span class="sxs-lookup"><span data-stu-id="3b937-113">Edit guest information</span></span>

<span data-ttu-id="3b937-114">批准后，会将来宾用户添加到目录和组中。</span><span class="sxs-lookup"><span data-stu-id="3b937-114">Once approved, the guest user is added to the directory and the group.</span></span>

<span data-ttu-id="3b937-115">组中的来宾访问通常用作包括 SharePoint 或团队的更广泛方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="3b937-115">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="3b937-116">这些服务具有自己的来宾共享设置。</span><span class="sxs-lookup"><span data-stu-id="3b937-116">These services have their own guest sharing settings.</span></span> <span data-ttu-id="3b937-117">有关在组、SharePoint 和团队中设置来宾共享的完整说明，请参阅：</span><span class="sxs-lookup"><span data-stu-id="3b937-117">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="3b937-118">在网站中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="3b937-118">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="3b937-119">在团队中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="3b937-119">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="3b937-120">管理组来宾访问</span><span class="sxs-lookup"><span data-stu-id="3b937-120">Manage groups guest access</span></span>

<span data-ttu-id="3b937-121">如果要启用或禁用组中的来宾访问，可以在 Microsoft 365 管理中心中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="3b937-121">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="3b937-122">在管理中心中，转到 "**设置** \> "**设置**并选择 " **Microsoft 365 组**"。</span><span class="sxs-lookup"><span data-stu-id="3b937-122">In the admin center, go to the **Settings** \> **Settings** and select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="3b937-123">在 " **Microsoft 365 组**" 页上，选择是否要让组织外部的用户访问组资源，或允许组所有者将组织外部的人员添加到组中。</span><span class="sxs-lookup"><span data-stu-id="3b937-123">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="3b937-124">从管理中心向 Microsoft 365 组添加来宾</span><span class="sxs-lookup"><span data-stu-id="3b937-124">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="3b937-125">如果来宾已经存在于目录中，则可以从 Microsoft 365 管理中心将其添加到你的组。</span><span class="sxs-lookup"><span data-stu-id="3b937-125">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="3b937-126">在 "管理中心" 中，转到 "**组** > **组**" 页面。</span><span class="sxs-lookup"><span data-stu-id="3b937-126">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="3b937-127">单击要向其添加来宾的组，然后选择 "**成员**" 选项卡上的 "**查看全部和管理成员**"。</span><span class="sxs-lookup"><span data-stu-id="3b937-127">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="3b937-128">选择 "**添加成员**"，然后选择要添加的来宾的名称。</span><span class="sxs-lookup"><span data-stu-id="3b937-128">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="3b937-129">选择“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="3b937-129">Select **Save**.</span></span>

<span data-ttu-id="3b937-130">如果要直接将来宾添加到目录中，可以[在 azure 门户中添加 Azure Active DIRECTORY B2B 协作用户](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)。</span><span class="sxs-lookup"><span data-stu-id="3b937-130">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="3b937-131">如果要编辑任何来宾的信息，可以[使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="3b937-131">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>
  
## <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="3b937-132">阻止特定组中的来宾用户</span><span class="sxs-lookup"><span data-stu-id="3b937-132">Block guest users from a specific group</span></span>

<span data-ttu-id="3b937-133">如果要允许来宾访问大多数组，但要阻止来宾访问，则可以使用 Microsoft PowerShell 阻止对各个组的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="3b937-133">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="3b937-134">您必须使用预览版本的[Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) （模块名称**AzureADPreview**）更改组级别的来宾访问设置：</span><span class="sxs-lookup"><span data-stu-id="3b937-134">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="3b937-135">如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)并按照说明安装公共预览版。</span><span class="sxs-lookup"><span data-stu-id="3b937-135">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="3b937-136">如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。</span><span class="sxs-lookup"><span data-stu-id="3b937-136">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="3b937-137">如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="3b937-137">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="3b937-138">您必须具有全局管理员权限才能运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="3b937-138">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="3b937-139">运行以下脚本，将其\* / \*更改为要阻止来宾访问的组的名称。</span><span class="sxs-lookup"><span data-stu-id="3b937-139">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="3b937-140">若要验证设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="3b937-140">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="3b937-141">验证如下所示：</span><span class="sxs-lookup"><span data-stu-id="3b937-141">The verification looks like this:</span></span>
    
![显示 "来宾组访问已设置为 false" 的 PowerShell 窗口的屏幕截图。](../../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="3b937-143">根据其域允许或阻止来宾访问</span><span class="sxs-lookup"><span data-stu-id="3b937-143">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="3b937-144">您可以允许或阻止使用特定域的来宾用户。</span><span class="sxs-lookup"><span data-stu-id="3b937-144">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="3b937-145">例如，如果您的企业（Contoso）与另一个业务（Fabrikam）有合作关系，则可以将 Fabrikam 添加到您的允许列表，以便您的用户可以将这些来宾添加到他们的组中。</span><span class="sxs-lookup"><span data-stu-id="3b937-145">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="3b937-146">有关详细信息，请参阅[允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="3b937-146">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="3b937-147">将来宾添加到全局地址列表</span><span class="sxs-lookup"><span data-stu-id="3b937-147">Add guests to the global address list</span></span>

<span data-ttu-id="3b937-148">默认情况下，来宾在 Exchange 全局地址列表中不可见。</span><span class="sxs-lookup"><span data-stu-id="3b937-148">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="3b937-149">使用下面列出的步骤使来宾在全局地址列表中可见。</span><span class="sxs-lookup"><span data-stu-id="3b937-149">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="3b937-150">通过运行以下命令查找来宾用户的 ObjectID：</span><span class="sxs-lookup"><span data-stu-id="3b937-150">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="3b937-151">然后，使用适用于 ObjectID、GivenName、姓、DisplayName 和 TelephoneNumber 的值运行以下各项。</span><span class="sxs-lookup"><span data-stu-id="3b937-151">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="3b937-152">相关文章</span><span class="sxs-lookup"><span data-stu-id="3b937-152">Related articles</span></span>

[<span data-ttu-id="3b937-153">在 Microsoft 365 管理中心中管理组成员身份</span><span class="sxs-lookup"><span data-stu-id="3b937-153">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="3b937-154">Azure Active Directory 访问审核</span><span class="sxs-lookup"><span data-stu-id="3b937-154">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="3b937-155">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="3b937-155">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
