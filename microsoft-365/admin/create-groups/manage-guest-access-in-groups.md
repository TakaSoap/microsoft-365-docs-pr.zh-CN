---
title: 管理来宾组中来宾Microsoft 365访问
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
ms.openlocfilehash: c52f0094e724040b71d5d72cded049fed57e3969
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52571933"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="cc8e7-103">管理来宾组中来宾Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="cc8e7-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="cc8e7-104">默认情况下，你的组织Microsoft 365组来宾访问。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="cc8e7-105">管理员可以控制是允许来宾访问整个组织组还是允许单个组访问组。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="cc8e7-106">启用后，组的成员可以通过 Web 上的Microsoft 365邀请来宾Outlook组。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="cc8e7-107">邀请将发送给组所有者进行审批。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="cc8e7-108">批准后，来宾用户将添加到目录和组中。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="cc8e7-109">Yammer Enterprise本机模式或[欧盟地理位置](/yammer/manage-security-and-compliance/manage-data-compliance)的网络不支持网络来宾。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](/yammer/manage-security-and-compliance/manage-data-compliance) do not support network guests.</span></span>
> <span data-ttu-id="cc8e7-110">Microsoft 365已Yammer组当前不支持来宾访问，但您可以在您的 Yammer 网络中创建未连接的外部组。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="cc8e7-111">有关[说明，请参阅在](/yammer/work-with-external-users/create-and-manage-external-groups)Yammer 创建和管理外部组。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-111">See [Create and manage external groups in Yammer](/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="cc8e7-112">组中的来宾访问通常用作更广泛的方案的一部分，包括SharePoint或Teams。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="cc8e7-113">这些服务具有其自己的来宾共享设置。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="cc8e7-114">有关在组、用户和用户之间设置来宾共享SharePoint的完整Teams，请参阅：</span><span class="sxs-lookup"><span data-stu-id="cc8e7-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="cc8e7-115">在网站中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="cc8e7-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="cc8e7-116">在团队中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="cc8e7-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="cc8e7-117">管理组来宾访问</span><span class="sxs-lookup"><span data-stu-id="cc8e7-117">Manage groups guest access</span></span>

<span data-ttu-id="cc8e7-118">如果要在组中启用或禁用来宾访问，可以在管理中心Microsoft 365访问。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="cc8e7-119">In the admin center， go to **Show all** \> **设置** \> **Org settings** and on the **Services** tab， select **Microsoft 365 groups**.</span><span class="sxs-lookup"><span data-stu-id="cc8e7-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="cc8e7-120">在 **"Microsoft 365** 组"页上，选择是允许组织外部人员访问组资源，还是允许组所有者将组织外部人员添加到组。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="cc8e7-121">从管理中心Microsoft 365来宾添加到组</span><span class="sxs-lookup"><span data-stu-id="cc8e7-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="cc8e7-122">如果目录中已存在来宾，你可以从管理中心将来宾Microsoft 365组。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span> <span data-ttu-id="cc8e7-123"> (动态成员身份的[组必须在](/azure/active-directory/enterprise-users/groups-create-rule).Azure Active Directory .) </span><span class="sxs-lookup"><span data-stu-id="cc8e7-123">(Groups with dynamic membership must be [managed in Azure Active Directory](/azure/active-directory/enterprise-users/groups-create-rule).)</span></span>
  
1. <span data-ttu-id="cc8e7-124">在管理中心，转到组  >  **组** 页面。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-124">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="cc8e7-125">单击要添加来宾的组，然后选择"成员"选项卡上的"查看所有和管理 **成员**"。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-125">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="cc8e7-126">选择 **"添加** 成员"，然后选择要添加的来宾的名称。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-126">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="cc8e7-127">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-127">Select **Save**.</span></span>

<span data-ttu-id="cc8e7-128">如果你想要将来宾直接添加到目录，可以在[Azure 门户Azure Active Directory B2B 协作用户。](/azure/active-directory/b2b/add-users-administrator)</span><span class="sxs-lookup"><span data-stu-id="cc8e7-128">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="cc8e7-129">如果要编辑来宾的任何信息，可以使用 "添加或更新用户个人资料[Azure Active Directory"](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="cc8e7-129">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="related-content"></a><span data-ttu-id="cc8e7-130">相关内容</span><span class="sxs-lookup"><span data-stu-id="cc8e7-130">Related content</span></span>

<span data-ttu-id="cc8e7-131">[阻止特定组的来宾用户 (](../../solutions/per-group-guest-access.md) 文章) </span><span class="sxs-lookup"><span data-stu-id="cc8e7-131">[Block guest users from a specific group](../../solutions/per-group-guest-access.md) (article)</span></span>

<span data-ttu-id="cc8e7-132">[在管理中心管理Microsoft 365管理 (](add-or-remove-members-from-groups.md)成员身份) </span><span class="sxs-lookup"><span data-stu-id="cc8e7-132">[Manage group membership in the Microsoft 365 admin center](add-or-remove-members-from-groups.md) (article)</span></span>
  
<span data-ttu-id="cc8e7-133">[Azure Active Directory访问评审](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (文章) </span><span class="sxs-lookup"><span data-stu-id="cc8e7-133">[Azure Active Directory access reviews](/azure/active-directory/active-directory-azure-ad-controls-perform-access-review) (article)</span></span>

<span data-ttu-id="cc8e7-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (文章) </span><span class="sxs-lookup"><span data-stu-id="cc8e7-134">[Set-AzureADUser](/powershell/module/azuread/set-azureaduser) (article)</span></span>