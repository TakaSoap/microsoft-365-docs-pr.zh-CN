---
title: 阻止将来宾添加到特定组
ms.reviewer: arvaradh
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 了解如何阻止将来宾添加到特定组
ms.openlocfilehash: 8bee26bf5ec323536ca1ac6f25ce96927634cee7
ms.sourcegitcommit: 0a8b0186cc041db7341e57f375d0d010b7682b7d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/11/2020
ms.locfileid: "49660044"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="a16c4-103">阻止将来宾添加到特定的 Microsoft 365 组或 Microsoft Teams 团队</span><span class="sxs-lookup"><span data-stu-id="a16c4-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="a16c4-104">如果要允许对大多数组和团队进行来宾访问，但希望阻止某些组和团队访问来宾，可以阻止各个组和团队的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="a16c4-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="a16c4-105"> (通过阻止来宾访问关联组来阻止来宾访问团队。) 这将阻止添加新来宾，但不删除已加入组或团队的来宾。</span><span class="sxs-lookup"><span data-stu-id="a16c4-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="a16c4-106">如果在组织中使用敏感度标签，我们建议使用敏感度标签按组控制来宾访问。</span><span class="sxs-lookup"><span data-stu-id="a16c4-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="a16c4-107">若要了解如何进行此操作，请使用敏感度标签来保护 [Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="a16c4-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="a16c4-108">这是建议的方法。</span><span class="sxs-lookup"><span data-stu-id="a16c4-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="a16c4-109">使用 Microsoft PowerShell 更改组设置</span><span class="sxs-lookup"><span data-stu-id="a16c4-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="a16c4-110">您还可以使用 PowerShell 阻止向各个组添加新来宾。</span><span class="sxs-lookup"><span data-stu-id="a16c4-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="a16c4-111"> (请记住，团队的关联 SharePoint 网站具有 [单独的来宾共享控件](https://docs.microsoft.com/sharepoint/change-external-sharing-site).) </span><span class="sxs-lookup"><span data-stu-id="a16c4-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](https://docs.microsoft.com/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="a16c4-112">必须使用 Azure [Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (模块名称 **AzureADPreview**) 预览版更改组级来宾访问设置：</span><span class="sxs-lookup"><span data-stu-id="a16c4-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="a16c4-113">如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true)并按照说明安装公共预览版。</span><span class="sxs-lookup"><span data-stu-id="a16c4-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview&preserve-view=true) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="a16c4-114">如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。</span><span class="sxs-lookup"><span data-stu-id="a16c4-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="a16c4-115">如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="a16c4-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="a16c4-116">您必须具有全局管理员权限才能运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="a16c4-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="a16c4-117">运行以下脚本，更改到要阻止来宾访问 */<GroupName/>* 的组的名称。</span><span class="sxs-lookup"><span data-stu-id="a16c4-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="a16c4-118">若要验证设置，请运行此命令：</span><span class="sxs-lookup"><span data-stu-id="a16c4-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="a16c4-119">验证如下所示：</span><span class="sxs-lookup"><span data-stu-id="a16c4-119">The verification looks like this:</span></span>
    
![显示来宾组访问权限已设置为 false 的 PowerShell 窗口屏幕截图。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="a16c4-121">允许或阻止基于其域的来宾访问</span><span class="sxs-lookup"><span data-stu-id="a16c4-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="a16c4-122">你可以允许或阻止使用特定域的来宾。</span><span class="sxs-lookup"><span data-stu-id="a16c4-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="a16c4-123">例如，如果您的企业 (Contoso) 与另一个业务 (Fabrikam) 建立了合作关系，您可以将 Fabrikam 添加到允许列表中，以便您的用户可以将这些来宾添加到其组。</span><span class="sxs-lookup"><span data-stu-id="a16c4-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="a16c4-124">有关详细信息，请参阅"允许[或阻止来自特定组织的 B2B 用户的邀请"。](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)</span><span class="sxs-lookup"><span data-stu-id="a16c4-124">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="a16c4-125">将来宾添加到全局地址列表</span><span class="sxs-lookup"><span data-stu-id="a16c4-125">Add guests to the global address list</span></span>

<span data-ttu-id="a16c4-126">默认情况下，来宾在 Exchange 全局地址列表中不可见。</span><span class="sxs-lookup"><span data-stu-id="a16c4-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="a16c4-127">使用下面列出的步骤使来宾在全局地址列表中可见。</span><span class="sxs-lookup"><span data-stu-id="a16c4-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="a16c4-128">通过运行以下方法查找来宾的 ObjectID：</span><span class="sxs-lookup"><span data-stu-id="a16c4-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="a16c4-129">然后，使用 ObjectID、GivenName、Surname、DisplayName 和 TelephoneNumber 的适当值运行以下代码。</span><span class="sxs-lookup"><span data-stu-id="a16c4-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="a16c4-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="a16c4-130">Related topics</span></span>

[<span data-ttu-id="a16c4-131">协作治理规划分步规划</span><span class="sxs-lookup"><span data-stu-id="a16c4-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="a16c4-132">创建协作治理计划</span><span class="sxs-lookup"><span data-stu-id="a16c4-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="a16c4-133">在 Microsoft 365 管理中心管理组成员身份</span><span class="sxs-lookup"><span data-stu-id="a16c4-133">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="a16c4-134">Azure Active Directory 访问评审</span><span class="sxs-lookup"><span data-stu-id="a16c4-134">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="a16c4-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="a16c4-135">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
