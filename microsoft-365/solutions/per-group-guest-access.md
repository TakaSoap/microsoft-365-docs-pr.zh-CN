---
title: 阻止特定组中的来宾用户
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
ms.custom:
- M365solutions
f1.keywords: NOCSH
description: 阻止特定组中的来宾用户
ms.openlocfilehash: 923a9e5cd09d232f377f55fd6a9f499f8f536a84
ms.sourcegitcommit: 66f1f430b3dcae5f46cb362a32d6fb7da4cff5c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2020
ms.locfileid: "46662499"
---
# <a name="block-guest-users-from-a-specific-group"></a><span data-ttu-id="df70c-103">阻止特定组中的来宾用户</span><span class="sxs-lookup"><span data-stu-id="df70c-103">Block guest users from a specific group</span></span>

<span data-ttu-id="df70c-104">如果要允许来宾访问大多数组，但要阻止来宾访问，则可以阻止单个组的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="df70c-104">If you want to allow guest access to most groups, but have some where you want to prevent guest access, you can block guest access for individual groups.</span></span>

<span data-ttu-id="df70c-105">如果您在组织中使用敏感度标签，我们建议使用它们来控制每组的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="df70c-105">If you use sensitivity labels in your organization, we recommend using them to control guest access on a per-group basis.</span></span> <span data-ttu-id="df70c-106">有关如何执行此操作的信息，请 [使用敏感度标签来保护 Microsoft 团队、microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)。</span><span class="sxs-lookup"><span data-stu-id="df70c-106">For information about how to do this, [Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites).</span></span> <span data-ttu-id="df70c-107">这是建议的方法。</span><span class="sxs-lookup"><span data-stu-id="df70c-107">This is the recommended approach.</span></span>

<span data-ttu-id="df70c-108">您还可以使用 Microsoft PowerShell 阻止对各个组的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="df70c-108">You can also block guest access to individual groups by using Microsoft PowerShell.</span></span>

<span data-ttu-id="df70c-109">必须使用预览版本的 [Azure Active Directory PowerShell For Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (Module name **AzureADPreview**) 更改组级别的来宾访问设置：</span><span class="sxs-lookup"><span data-stu-id="df70c-109">You must use the preview version of [Azure Active Directory PowerShell for Graph](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2) (module name **AzureADPreview**) to change the group-level guest access setting:</span></span>

- <span data-ttu-id="df70c-110">如果之前未安装任何 Azure AD PowerShell 模块版本，请参阅[安装 Azure AD 模块](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module)并按照说明安装公共预览版。</span><span class="sxs-lookup"><span data-stu-id="df70c-110">If you haven't installed any version of the Azure AD PowerShell module before, see [Installing the Azure AD Module](https://docs.microsoft.com/powershell/azure/active-directory/install-adv2?view=azureadps-2.0-preview#installing-the-azure-ad-module) and follow the instructions to install the public preview release.</span></span>

- <span data-ttu-id="df70c-111">如果已安装 Azure AD PowerShell 模块 (AzureAD) 的 2.0 正式发布版本，则必须通过在 PowerShell 会话中运行 `Uninstall-Module AzureAD` 来卸载它，然后通过运行 `Install-Module AzureADPreview` 来安装预览版。</span><span class="sxs-lookup"><span data-stu-id="df70c-111">If you have the 2.0 general availability version of the Azure AD PowerShell module (AzureAD) installed, you must uninstall it by running `Uninstall-Module AzureAD` in your PowerShell session, and then install the preview version by running `Install-Module AzureADPreview`.</span></span>

- <span data-ttu-id="df70c-112">如果已安装预览版，请运行 `Install-Module AzureADPreview`，确保它是此模块的最新版本。</span><span class="sxs-lookup"><span data-stu-id="df70c-112">If you have already installed the preview version, run `Install-Module AzureADPreview` to make sure it's the latest version of this module.</span></span>

> [!NOTE]
> <span data-ttu-id="df70c-113">您必须具有全局管理员权限才能运行这些命令。</span><span class="sxs-lookup"><span data-stu-id="df70c-113">You must have global admin rights to run these commands.</span></span> 

<span data-ttu-id="df70c-114">运行以下脚本， */<GroupName/>* 将其更改为要阻止来宾访问的组的名称。</span><span class="sxs-lookup"><span data-stu-id="df70c-114">Run the following script, changing */<GroupName/>* to the name of the group where you want to block guest access.</span></span>

```PowerShell
$GroupName = "<GroupName>"

Connect-AzureAD

$template = Get-AzureADDirectorySettingTemplate | ? {$_.displayname -eq "group.unified.guest"}
$settingsCopy = $template.CreateDirectorySetting()
$settingsCopy["AllowToAddGuests"]=$False
$groupID= (Get-AzureADGroup -SearchString $GroupName).ObjectId
New-AzureADObjectSetting -TargetType Groups -TargetObjectId $groupID -DirectorySetting $settingsCopy
```

<span data-ttu-id="df70c-115">若要验证设置，请运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="df70c-115">To verify your settings, run this command:</span></span>

```PowerShell
Get-AzureADObjectSetting -TargetObjectId $groupID -TargetType Groups | fl Values
```

<span data-ttu-id="df70c-116">验证如下所示：</span><span class="sxs-lookup"><span data-stu-id="df70c-116">The verification looks like this:</span></span>
    
![显示 "来宾组访问已设置为 false" 的 PowerShell 窗口的屏幕截图。](../media/09ebfb4f-859f-44c3-a29e-63a59fd6ef87.png)
  
## <a name="allow-or-block-guest-access-based-on-their-domain"></a><span data-ttu-id="df70c-118">根据其域允许或阻止来宾访问</span><span class="sxs-lookup"><span data-stu-id="df70c-118">Allow or block guest access based on their domain</span></span>

<span data-ttu-id="df70c-119">您可以允许或阻止使用特定域的来宾用户。</span><span class="sxs-lookup"><span data-stu-id="df70c-119">You can allow or block guest users who are using a specific domain.</span></span> <span data-ttu-id="df70c-120">例如，如果您的企业 (Contoso) 与另一个业务 (Fabrikam) 有合作关系，则可以将 Fabrikam 添加到您的允许列表，以便您的用户可以将这些来宾添加到他们的组中。</span><span class="sxs-lookup"><span data-stu-id="df70c-120">For example, if your business (Contoso) has a partnership with another business (Fabrikam), you can add Fabrikam to your Allow list so your users can add those guests to their groups.</span></span>

<span data-ttu-id="df70c-121">有关详细信息，请参阅 [允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="df70c-121">For more information, see [Allow or block invitations to B2B users from specific organizations](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list).</span></span>

## <a name="add-guests-to-the-global-address-list"></a><span data-ttu-id="df70c-122">将来宾添加到全局地址列表</span><span class="sxs-lookup"><span data-stu-id="df70c-122">Add guests to the global address list</span></span>

<span data-ttu-id="df70c-123">默认情况下，来宾在 Exchange 全局地址列表中不可见。</span><span class="sxs-lookup"><span data-stu-id="df70c-123">By default, guests aren't visible in the Exchange Global Address List.</span></span> <span data-ttu-id="df70c-124">使用下面列出的步骤使来宾在全局地址列表中可见。</span><span class="sxs-lookup"><span data-stu-id="df70c-124">Use the steps listed below to make a guest visible in the global address list.</span></span>

<span data-ttu-id="df70c-125">通过运行以下命令查找来宾用户的 ObjectID：</span><span class="sxs-lookup"><span data-stu-id="df70c-125">Find the guest user's ObjectID by running:</span></span>

```PowerShell
Get-AzureADUser -Filter "userType eq 'Guest'"
```

<span data-ttu-id="df70c-126">然后，使用适用于 ObjectID、GivenName、姓、DisplayName 和 TelephoneNumber 的值运行以下各项。</span><span class="sxs-lookup"><span data-stu-id="df70c-126">Then run the following using the appropriate values for ObjectID, GivenName, Surname, DisplayName, and TelephoneNumber.</span></span>

```PowerShell
Set-AzureADUser -ObjectId cfcbd1a0-ed18-4210-9b9d-cf0ba93cf6b2 -ShowInAddressList $true -GivenName 'Megan' -Surname 'Bowen' -DisplayName 'Megan Bowen' -TelephoneNumber '555-555-5555'
```

## <a name="related-articles"></a><span data-ttu-id="df70c-127">相关文章</span><span class="sxs-lookup"><span data-stu-id="df70c-127">Related articles</span></span>

[<span data-ttu-id="df70c-128">在 Microsoft 365 管理中心中管理组成员身份</span><span class="sxs-lookup"><span data-stu-id="df70c-128">Manage Group membership in the Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/create-groups/add-or-remove-members-from-groups)
  
[<span data-ttu-id="df70c-129">Azure Active Directory 访问审核</span><span class="sxs-lookup"><span data-stu-id="df70c-129">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="df70c-130">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="df70c-130">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)