---
title: 在 Microsoft 365 组中管理来宾访问
ms.reviewer: arvaradh
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 了解如何将来宾添加到 Microsoft 365 组、查看来宾用户和使用 PowerShell 控制来宾访问。
ms.openlocfilehash: 9a713684bb9a2401316dbb3289115be19b220cff
ms.sourcegitcommit: 375168ee66be862cf3b00f2733c7be02e63408cf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50453653"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="86176-103">在 Microsoft 365 组中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="86176-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="86176-104">默认情况下，为组织启用 Microsoft 365 组的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="86176-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="86176-105">管理员可以控制是允许来宾访问整个组织组还是允许单个组访问组。</span><span class="sxs-lookup"><span data-stu-id="86176-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="86176-106">启用后，组成员可以通过 Outlook 网页版邀请来宾用户加入 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="86176-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="86176-107">邀请将发送给组所有者进行审批。</span><span class="sxs-lookup"><span data-stu-id="86176-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="86176-108">批准后，来宾用户将添加到目录和组。</span><span class="sxs-lookup"><span data-stu-id="86176-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="86176-109">本机模式或欧盟地理位置中的 Yammer Enterprise [网络不支持](https://go.microsoft.com/fwlink/?linkid=2107357) 网络来宾。</span><span class="sxs-lookup"><span data-stu-id="86176-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="86176-110">Microsoft 365 连接的 Yammer 组当前不支持来宾访问，但您可以在 Yammer 网络中创建未连接的外部组。</span><span class="sxs-lookup"><span data-stu-id="86176-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="86176-111">有关 [说明，请参阅在 Yammer 中](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) 创建和管理外部组。</span><span class="sxs-lookup"><span data-stu-id="86176-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="86176-112">组中的来宾访问通常用作包括 SharePoint 或 Teams 的更广泛的方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="86176-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="86176-113">这些服务有其自己的来宾共享设置。</span><span class="sxs-lookup"><span data-stu-id="86176-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="86176-114">有关跨组、SharePoint 和 Teams 设置来宾共享的完整说明，请参阅：</span><span class="sxs-lookup"><span data-stu-id="86176-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="86176-115">在网站中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="86176-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="86176-116">在团队中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="86176-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="86176-117">管理组来宾访问</span><span class="sxs-lookup"><span data-stu-id="86176-117">Manage groups guest access</span></span>

<span data-ttu-id="86176-118">如果要在组中启用或禁用来宾访问，可以在 Microsoft 365 管理中心中启用或禁用来宾访问。</span><span class="sxs-lookup"><span data-stu-id="86176-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="86176-119">在管理中心中，转到"显示 **所有** 设置组织设置"，在"服务"选项卡上，选择 \>  \> **Microsoft 365 组**。 </span><span class="sxs-lookup"><span data-stu-id="86176-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="86176-120">在 **"Microsoft 365** 组"页上，选择是允许组织外部人员访问组资源，还是允许组所有者将组织外部人员添加到组。</span><span class="sxs-lookup"><span data-stu-id="86176-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="86176-121">从管理中心向 Microsoft 365 组添加来宾</span><span class="sxs-lookup"><span data-stu-id="86176-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="86176-122">如果目录中已存在来宾，可以从 Microsoft 365 管理中心将其添加到组。</span><span class="sxs-lookup"><span data-stu-id="86176-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="86176-123"> (动态成员身份的组必须在 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).) </span><span class="sxs-lookup"><span data-stu-id="86176-123">(Groups with dynamic membership must be [managed in Azure Active Directory](https://docs.microsoft.com/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="86176-124">在管理中心，转到"组  >  **组"** 页。</span><span class="sxs-lookup"><span data-stu-id="86176-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="86176-125">单击要添加来宾的组，然后选择"成员"选项卡上的"查看所有和管理 **成员**"。</span><span class="sxs-lookup"><span data-stu-id="86176-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="86176-126">选择 **"** 添加成员"，然后选择要添加的来宾的名称。</span><span class="sxs-lookup"><span data-stu-id="86176-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="86176-127">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="86176-127">Select **Save**.</span></span>

<span data-ttu-id="86176-128">如果要直接向目录添加来宾，可以在 Azure 门户中添加 Azure [Active Directory B2B 协作用户](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)。</span><span class="sxs-lookup"><span data-stu-id="86176-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="86176-129">如果要编辑任何来宾信息，可以使用 [Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)添加或更新用户配置文件信息。</span><span class="sxs-lookup"><span data-stu-id="86176-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="86176-130">另请参阅</span><span class="sxs-lookup"><span data-stu-id="86176-130">See also</span></span>

[<span data-ttu-id="86176-131">阻止特定组的来宾用户</span><span class="sxs-lookup"><span data-stu-id="86176-131">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="86176-132">在 Microsoft 365 管理中心管理组成员身份</span><span class="sxs-lookup"><span data-stu-id="86176-132">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="86176-133">Azure Active Directory 访问评审</span><span class="sxs-lookup"><span data-stu-id="86176-133">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="86176-134">Set-AzureADUser</span><span class="sxs-lookup"><span data-stu-id="86176-134">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
