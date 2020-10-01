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
ms.custom: AdminSurgePortfolio
search.appverid:
- MET150
- MOE150
ms.assetid: 9de497a9-2f5c-43d6-ae18-767f2e6fe6e0
description: 了解如何将来宾添加到 Microsoft 365 组，查看来宾用户，以及如何使用 PowerShell 控制来宾访问。
ms.openlocfilehash: 640a35cbb1a3eb395453b224cadcf0d0db82fab8
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326515"
---
# <a name="manage-guest-access-in-microsoft-365-groups"></a><span data-ttu-id="71e12-103">在 Microsoft 365 组中管理来宾访问</span><span class="sxs-lookup"><span data-stu-id="71e12-103">Manage guest access in Microsoft 365 groups</span></span>

<span data-ttu-id="71e12-104">默认情况下，为您的组织启用对 Microsoft 365 组的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="71e12-104">By default, guest access for Microsoft 365 groups is turned on for your organization.</span></span> <span data-ttu-id="71e12-105">管理员可以控制是否允许来宾访问整个组织或单个组的组。</span><span class="sxs-lookup"><span data-stu-id="71e12-105">Admins can control whether to allow guest access to groups for their whole organization or for individual groups.</span></span>

<span data-ttu-id="71e12-106">当它打开时，组成员可以通过 Web 上的 Outlook 将来宾用户邀请到 Microsoft 365 组。</span><span class="sxs-lookup"><span data-stu-id="71e12-106">When it's turned on, group members can invite guest users to a Microsoft 365 group through Outlook on Web.</span></span> <span data-ttu-id="71e12-107">邀请将发送给组所有者以供审批。</span><span class="sxs-lookup"><span data-stu-id="71e12-107">Invitations are sent to the group owner for approval.</span></span>

<span data-ttu-id="71e12-108">批准后，会将来宾用户添加到目录和组中。</span><span class="sxs-lookup"><span data-stu-id="71e12-108">Once approved, the guest user is added to the directory and the group.</span></span>

> [!Note]
> <span data-ttu-id="71e12-109">处于本机模式或 [欧盟地区](https://go.microsoft.com/fwlink/?linkid=2107357) 的 Yammer 企业网络不支持网络来宾。</span><span class="sxs-lookup"><span data-stu-id="71e12-109">Yammer Enterprise networks that are in Native Mode or the [EU Geo](https://go.microsoft.com/fwlink/?linkid=2107357) do not support network guests.</span></span>
> <span data-ttu-id="71e12-110">Microsoft 365 连接的 Yammer 组目前不支持来宾访问，但你可以在 Yammer 网络中创建未连接的外部组。</span><span class="sxs-lookup"><span data-stu-id="71e12-110">Microsoft 365 Connected Yammer groups do not currently support guest access, but you can create non-connected, external groups in your Yammer network.</span></span> <span data-ttu-id="71e12-111">有关说明，请参阅 [在 Yammer 中创建和管理外部组](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) 。</span><span class="sxs-lookup"><span data-stu-id="71e12-111">See [Create and manage external groups in Yammer](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-external-groups) for instructions.</span></span>

<span data-ttu-id="71e12-112">组中的来宾访问通常用作包括 SharePoint 或团队的更广泛方案的一部分。</span><span class="sxs-lookup"><span data-stu-id="71e12-112">Guest access in groups is often used as part of a broader scenario that includes SharePoint or Teams.</span></span> <span data-ttu-id="71e12-113">这些服务具有自己的来宾共享设置。</span><span class="sxs-lookup"><span data-stu-id="71e12-113">These services have their own guest sharing settings.</span></span> <span data-ttu-id="71e12-114">有关在组、SharePoint 和团队中设置来宾共享的完整说明，请参阅：</span><span class="sxs-lookup"><span data-stu-id="71e12-114">For complete instructions for setting up guest sharing across groups, SharePoint, and Teams, see:</span></span>

- [<span data-ttu-id="71e12-115">在网站中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="71e12-115">Collaborate with guests in a site</span></span>](../../solutions/collaborate-in-site.md)
- [<span data-ttu-id="71e12-116">在团队中与来宾协作</span><span class="sxs-lookup"><span data-stu-id="71e12-116">Collaborate with guests in a team</span></span>](../../solutions/collaborate-as-team.md)

## <a name="manage-groups-guest-access"></a><span data-ttu-id="71e12-117">管理组来宾访问</span><span class="sxs-lookup"><span data-stu-id="71e12-117">Manage groups guest access</span></span>

<span data-ttu-id="71e12-118">如果要启用或禁用组中的来宾访问，可以在 Microsoft 365 管理中心中执行此操作。</span><span class="sxs-lookup"><span data-stu-id="71e12-118">If you want to enable or disable guest access in groups, you can do so in the Microsoft 365 admin center.</span></span>

1. <span data-ttu-id="71e12-119">在管理中心中，转到 " **显示所有** \> **设置**" " \> **组织设置** "，并在 " **服务** " 选项卡上选择 " **Microsoft 365 组**"。</span><span class="sxs-lookup"><span data-stu-id="71e12-119">In the admin center, go to **Show all** \> **Settings** \> **Org settings** and on the **Services** tab, select **Microsoft 365 groups**.</span></span>
  
2. <span data-ttu-id="71e12-120">在 " **Microsoft 365 组** " 页上，选择是否要让组织外部的用户访问组资源，或允许组所有者将组织外部的人员添加到组中。</span><span class="sxs-lookup"><span data-stu-id="71e12-120">On the **Microsoft 365 Groups** page, choose whether you want to let people outside your organization access group resources or let group owners add people outside your organization to groups.</span></span>

## <a name="add-guests-to-a-microsoft-365-group-from-the-admin-center"></a><span data-ttu-id="71e12-121">从管理中心向 Microsoft 365 组添加来宾</span><span class="sxs-lookup"><span data-stu-id="71e12-121">Add guests to a Microsoft 365 group from the admin center</span></span>

<span data-ttu-id="71e12-122">如果来宾已经存在于目录中，则可以从 Microsoft 365 管理中心将其添加到你的组。</span><span class="sxs-lookup"><span data-stu-id="71e12-122">If the guest already exists in your directory, you can add them to your groups from the Microsoft 365 admin center.</span></span>
  
1. <span data-ttu-id="71e12-123">在 "管理中心" 中，转到 "**组**  >  **组**" 页面。</span><span class="sxs-lookup"><span data-stu-id="71e12-123">In the admin center, go to the **Groups** > **Groups** page.</span></span>
  
2. <span data-ttu-id="71e12-124">单击要向其添加来宾的组，然后选择 "**成员**" 选项卡上的 "**查看全部和管理成员**"。</span><span class="sxs-lookup"><span data-stu-id="71e12-124">Click the group you want to add the guest to, and select **View all and manage members** on the **Members** tab.</span></span> 
  
4. <span data-ttu-id="71e12-125">选择 " **添加成员**"，然后选择要添加的来宾的名称。</span><span class="sxs-lookup"><span data-stu-id="71e12-125">Select **Add members**, and choose the name of the guest you want to add.</span></span>
    
5. <span data-ttu-id="71e12-126">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="71e12-126">Select **Save**.</span></span>

<span data-ttu-id="71e12-127">如果要直接将来宾添加到目录中，可以 [在 azure 门户中添加 Azure Active DIRECTORY B2B 协作用户](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator)。</span><span class="sxs-lookup"><span data-stu-id="71e12-127">If you want to add a guest to the directory directly, you can [Add Azure Active Directory B2B collaboration users in the Azure portal](https://docs.microsoft.com/azure/active-directory/b2b/add-users-administrator).</span></span>

<span data-ttu-id="71e12-128">如果要编辑任何来宾的信息，可以 [使用 Azure Active Directory 添加或更新用户的配置文件信息](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="71e12-128">If you want to edit any of a guest's information, you can [Add or update a user's profile information using Azure Active Directory](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-users-profile-azure-portal).</span></span>

## <a name="see-also"></a><span data-ttu-id="71e12-129">另请参阅</span><span class="sxs-lookup"><span data-stu-id="71e12-129">See also</span></span>

[<span data-ttu-id="71e12-130">阻止特定组中的来宾用户</span><span class="sxs-lookup"><span data-stu-id="71e12-130">Block guest users from a specific group</span></span>](https://docs.microsoft.com/microsoft-365/solutions/per-group-guest-access)

[<span data-ttu-id="71e12-131">在 Microsoft 365 管理中心中管理组成员身份</span><span class="sxs-lookup"><span data-stu-id="71e12-131">Manage group membership in the Microsoft 365 admin center</span></span>](add-or-remove-members-from-groups.md)
  
[<span data-ttu-id="71e12-132">Azure Active Directory 访问审核</span><span class="sxs-lookup"><span data-stu-id="71e12-132">Azure Active Directory access reviews</span></span>](https://docs.microsoft.com/azure/active-directory/active-directory-azure-ad-controls-perform-access-review)

[<span data-ttu-id="71e12-133">AzureADUser</span><span class="sxs-lookup"><span data-stu-id="71e12-133">Set-AzureADUser</span></span>](https://docs.microsoft.com/powershell/module/azuread/set-azureaduser)
