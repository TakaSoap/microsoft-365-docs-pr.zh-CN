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
recommendations: false
description: 了解如何阻止将来宾添加到特定组
ms.openlocfilehash: 1db2055f3e546c05905dbf4c854333387112f06e
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52538923"
---
# <a name="prevent-guests-from-being-added-to-a-specific-microsoft-365-group-or-microsoft-teams-team"></a><span data-ttu-id="bcff9-103">阻止来宾添加到特定组或Microsoft 365组Microsoft Teams组</span><span class="sxs-lookup"><span data-stu-id="bcff9-103">Prevent guests from being added to a specific Microsoft 365 group or Microsoft Teams team</span></span>

<span data-ttu-id="bcff9-104">如果要允许对大多数组和团队进行来宾访问，但希望阻止某些组和团队访问来宾，可以阻止单个组和团队的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="bcff9-104">If you want to allow guest access to most groups and teams, but have some where you want to prevent guest access, you can block guest access for individual groups and teams.</span></span> <span data-ttu-id="bcff9-105"> (通过阻止来宾访问关联组来阻止来宾访问团队。) 这将阻止添加新来宾，但不删除已加入组或团队的来宾。</span><span class="sxs-lookup"><span data-stu-id="bcff9-105">(Blocking guest access to a team is done by blocking guest access to the associated group.) This prevents new guests from being added but does not remove guests that are already in the group or team.</span></span>

<span data-ttu-id="bcff9-106">如果你在你的组织中使用敏感度标签，我们建议使用它们以按组控制来宾访问。</span><span class="sxs-lookup"><span data-stu-id="bcff9-106">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="bcff9-107">若要了解如何进行此操作，请使用敏感度标签来保护网站Microsoft Teams、Microsoft 365[组SharePoint内容](../compliance/sensitivity-labels-teams-groups-sites.md)。</span><span class="sxs-lookup"><span data-stu-id="bcff9-107">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](../compliance/sensitivity-labels-teams-groups-sites.md).</span></span> <span data-ttu-id="bcff9-108">这是建议的方法。</span><span class="sxs-lookup"><span data-stu-id="bcff9-108">This is the recommended approach.</span></span>

## <a name="change-group-settings-using-microsoft-powershell"></a><span data-ttu-id="bcff9-109">使用 Microsoft PowerShell 更改组设置</span><span class="sxs-lookup"><span data-stu-id="bcff9-109">Change group settings using Microsoft PowerShell</span></span>

<span data-ttu-id="bcff9-110">您还可以使用 PowerShell 阻止向各个组添加新来宾。</span><span class="sxs-lookup"><span data-stu-id="bcff9-110">You can also prevent the addition of new guests to individual groups by using PowerShell.</span></span> <span data-ttu-id="bcff9-111"> (请记住，团队的关联网站SharePoint单独的[来宾](/sharepoint/change-external-sharing-site)共享控件 。) </span><span class="sxs-lookup"><span data-stu-id="bcff9-111">(Remember that the team's associated SharePoint site has [separate guest sharing controls](/sharepoint/change-external-sharing-site).)</span></span>

<span data-ttu-id="bcff9-112">你必须使用 Azure Active Directory [PowerShell](/powershell/azure/active-directory/install-adv2)的预览版Graph (**AzureADPreview**) 更改组级别的来宾访问设置：</span><span class="sxs-lookup"><span data-stu-id="bcff9-112">You must use the preview version of [Azure Active Directory PowerShell for Graph](/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="bcff9-113">如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview)并按照说明安装公共预览版。</span><span class="sxs-lookup"><span data-stu-id="bcff9-113">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](/powershell/azure/active-directory/install-adv2?preserve-view=true&view=azureadps-2.0-preview) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="bcff9-114">如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。</span><span class="sxs-lookup"><span data-stu-id="bcff9-114">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="bcff9-115">如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="bcff9-115">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="bcff9-116">您必须具有全局管理员权限才能运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="bcff9-116">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="bcff9-117">运行以下脚本，更改为要阻止来宾访问 */<GroupName/>* 的组的名称。</span><span class="sxs-lookup"><span data-stu-id="bcff9-117">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="bcff9-118">若要验证设置，请运行此命令：</span><span class="sxs-lookup"><span data-stu-id="bcff9-118">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="bcff9-119">验证如下所示：</span><span class="sxs-lookup"><span data-stu-id="bcff9-119">The verification looks like this:</span></span>
    
![显示来宾组访问已设置为 false 的 PowerShell 窗口屏幕截图。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="bcff9-121">基于其域允许或阻止来宾访问</span><span class="sxs-lookup"><span data-stu-id="bcff9-121">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="bcff9-122">你可以允许或阻止使用特定域的来宾。</span><span class="sxs-lookup"><span data-stu-id="bcff9-122">You can allow or block guests who are using a specific domain.</span></span> <span data-ttu-id="bcff9-123">例如，如果您的企业 (Contoso) 与另一个业务 (Fabrikam) 有合作关系，您可以将 Fabrikam 添加到允许列表，以便您的用户可以将那些来宾添加到其组。</span><span class="sxs-lookup"><span data-stu-id="bcff9-123">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="bcff9-124">有关详细信息，请参阅允许或阻止来自特定组织的 [B2B 用户的邀请](/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="bcff9-124">For more information, see [Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="bcff9-125">将来宾添加到全局地址列表</span><span class="sxs-lookup"><span data-stu-id="bcff9-125">Add guests to the global address list</span></span>

<span data-ttu-id="bcff9-126">默认情况下，来宾在全局地址列表中Exchange可见。</span><span class="sxs-lookup"><span data-stu-id="bcff9-126">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="bcff9-127">使用下面列出的步骤使来宾在全局地址列表中可见。</span><span class="sxs-lookup"><span data-stu-id="bcff9-127">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="bcff9-128">通过运行以下方法查找来宾的 ObjectID：</span><span class="sxs-lookup"><span data-stu-id="bcff9-128">Find the guest's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="bcff9-129">然后，使用 ObjectID、GivenName、Surname、DisplayName 和 TelephoneNumber 的适当值运行以下代码。</span><span class="sxs-lookup"><span data-stu-id="bcff9-129">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-topics"></a><span data-ttu-id="bcff9-130">相关主题</span><span class="sxs-lookup"><span data-stu-id="bcff9-130">Related topics</span></span>

[<span data-ttu-id="bcff9-131">协作治理规划分步规划</span><span class="sxs-lookup"><span data-stu-id="bcff9-131">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="bcff9-132">创建协作管理计划</span><span class="sxs-lookup"><span data-stu-id="bcff9-132">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="bcff9-133">管理管理中心Microsoft 365组成员身份</span><span class="sxs-lookup"><span data-stu-id="bcff9-133">Manage Group membership in the Microsoft 365 admin center</span></span>](../admin/create-groups/add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="bcff9-134">Azure Active Directory访问评审</span><span class="sxs-lookup"><span data-stu-id="bcff9-134">Azure Active Directory access reviews</span></span>](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="bcff9-135">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="bcff9-135">Set-AzureADUser</span></span>](/powershell/module/azuread/set-azureaduser)