---
title: 将 Microsoft 365 许可证分配给用户帐户
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/30/2020
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- O365p_AddUsersWithDirSync
- O365M_AddUsersWithDirSync
- O365E_HRCSetupAADConnectAboutLM617031
- O365E_AddUsersWithDirSync
ms.collection:
- Ent_O365
- M365-identity-device-management
search.appverid:
- MET150
- MOP150
- MOE150
- MBS150
ms.assetid: 01920974-9e6f-4331-a370-13aea4e82b3e
description: 介绍如何将 Microsoft 365 许可证单独或基于组成员身份分配给用户帐户。
ms.openlocfilehash: a2eed7b3597dcc2531834456a9b05f5aa1b07a23
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48326503"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="6fbc9-103">将 Microsoft 365 许可证分配给用户帐户</span><span class="sxs-lookup"><span data-stu-id="6fbc9-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="6fbc9-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="6fbc9-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="6fbc9-105">对于仅限云的标识模型，可以根据创建的方式将 Microsoft 365 许可证分配给用户帐户，具体取决于您的创建方式。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="6fbc9-106">对于混合标识模型，如果 Active Directory 域服务 (AD DS) 用户帐户首次同步，则不会自动为其分配位置或 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="6fbc9-107">**在分配许可证之前或之前，必须使用用户位置配置每个用户帐户。**</span><span class="sxs-lookup"><span data-stu-id="6fbc9-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="6fbc9-108">在这两种情况下，都必须将许可证分配给用户帐户，以便您的用户可以访问 Microsoft 365 服务，例如电子邮件和 Microsoft 团队。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="6fbc9-109">您可以通过组成员身份单独或自动将许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="6fbc9-110">若要将 Microsoft 365 许可证分配给单个用户帐户，您可以使用：</span><span class="sxs-lookup"><span data-stu-id="6fbc9-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="6fbc9-111">Microsoft 365 管理员中心</span><span class="sxs-lookup"><span data-stu-id="6fbc9-111">The Microsoft 365 admin center</span></span>](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)
- [<span data-ttu-id="6fbc9-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="6fbc9-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="6fbc9-113">Azure AD 管理中心</span><span class="sxs-lookup"><span data-stu-id="6fbc9-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="6fbc9-114">基于组的许可</span><span class="sxs-lookup"><span data-stu-id="6fbc9-114">Group-based licensing</span></span>

<span data-ttu-id="6fbc9-115">您可以在 Azure AD 中配置安全组，以自动将一组订阅中的许可证分配给该组的所有成员。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="6fbc9-116">这称为*基于组的许可*。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="6fbc9-117">如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或取消分配给该用户帐户。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="6fbc9-118">确保所有组成员都有足够的许可证。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="6fbc9-119">如果许可证用完，将不会向新用户分配许可证，直到许可证可用。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="6fbc9-120">不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="6fbc9-121">有关更多 informaion，请参阅 [AZURE AD 中的基于组的许可](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)。</span><span class="sxs-lookup"><span data-stu-id="6fbc9-121">For more informaion, see [group-based licensing in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="6fbc9-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6fbc9-122">Next steps</span></span>

<span data-ttu-id="6fbc9-123">对于已分配有许可证的一组适当的用户帐户，您现在可以执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="6fbc9-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="6fbc9-124">实施安全性</span><span class="sxs-lookup"><span data-stu-id="6fbc9-124">Implement security</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-roadmap)
- [<span data-ttu-id="6fbc9-125">部署客户端软件，例如 Microsoft 365 应用程序</span><span class="sxs-lookup"><span data-stu-id="6fbc9-125">Deploy client software, such as Microsoft 365 Apps</span></span>](https://docs.microsoft.com/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="6fbc9-126">设置设备管理</span><span class="sxs-lookup"><span data-stu-id="6fbc9-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="6fbc9-127">配置服务和应用程序</span><span class="sxs-lookup"><span data-stu-id="6fbc9-127">Configure services and applications</span></span>](configure-services-and-applications.md)
