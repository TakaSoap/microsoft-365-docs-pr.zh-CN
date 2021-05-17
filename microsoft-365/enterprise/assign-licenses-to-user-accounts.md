---
title: 将Microsoft 365许可证分配给用户帐户
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
description: 介绍如何将Microsoft 365许可证分配给用户帐户，无论是单独分配还是基于组成员身份。
ms.openlocfilehash: 2fe1e2f959fae8b0bc82a7dcd4f65f33b21c368a
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051528"
---
# <a name="assign-microsoft-365-licenses-to-user-accounts"></a><span data-ttu-id="946c1-103">将Microsoft 365许可证分配给用户帐户</span><span class="sxs-lookup"><span data-stu-id="946c1-103">Assign Microsoft 365 licenses to user accounts</span></span>

<span data-ttu-id="946c1-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="946c1-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="946c1-105">对于仅云标识模型，Microsoft 365用户帐户创建时，根据用户帐户的创建方式分配这些许可证。</span><span class="sxs-lookup"><span data-stu-id="946c1-105">For the cloud-only identity model, you can assign Microsoft 365 licenses to user accounts as they are created, depending on how you create them.</span></span>

<span data-ttu-id="946c1-106">对于混合标识模型，当 Active Directory 域服务 (AD DS) 用户帐户首次同步时，不会自动为其分配位置或 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="946c1-106">For the hybrid identity model, when Active Directory Domain Services (AD DS) user accounts are synchronized for the first time, they are not automatically assigned a location or a Microsoft 365 license.</span></span> <span data-ttu-id="946c1-107">**在分配许可证之前或之前，必须使用用户位置配置每个用户帐户。**</span><span class="sxs-lookup"><span data-stu-id="946c1-107">**You must configure each user account with a user location prior to or along with assigning a license.**</span></span>

<span data-ttu-id="946c1-108">在任一情况下，都必须向用户帐户分配许可证，以便Microsoft 365访问电子邮件和Microsoft Teams。</span><span class="sxs-lookup"><span data-stu-id="946c1-108">In either case, you must assign a license to user accounts so your users can access Microsoft 365 services, such as email and Microsoft Teams.</span></span>

<span data-ttu-id="946c1-109">你可以单独或自动通过组成员身份向用户帐户分配许可证。</span><span class="sxs-lookup"><span data-stu-id="946c1-109">You can assign licenses to user accounts either individually or automatically through group membership.</span></span>

<span data-ttu-id="946c1-110">若要Microsoft 365用户帐户分配许可证，可以使用：</span><span class="sxs-lookup"><span data-stu-id="946c1-110">To assign Microsoft 365 licenses to individual user accounts, you can use:</span></span>

- [<span data-ttu-id="946c1-111">Microsoft 365 管理员中心</span><span class="sxs-lookup"><span data-stu-id="946c1-111">The Microsoft 365 admin center</span></span>](../admin/manage/assign-licenses-to-users.md)
- [<span data-ttu-id="946c1-112">PowerShell</span><span class="sxs-lookup"><span data-stu-id="946c1-112">PowerShell</span></span>](assign-licenses-to-user-accounts-with-microsoft-365-powershell.md)
- <span data-ttu-id="946c1-113">Azure AD 管理中心</span><span class="sxs-lookup"><span data-stu-id="946c1-113">The Azure AD admin center</span></span>

## <a name="group-based-licensing"></a><span data-ttu-id="946c1-114">基于组的许可</span><span class="sxs-lookup"><span data-stu-id="946c1-114">Group-based licensing</span></span>

<span data-ttu-id="946c1-115">可以在 Azure AD 中配置安全组，以自动将一组订阅中的许可证分配给组的所有成员。</span><span class="sxs-lookup"><span data-stu-id="946c1-115">You can configure security groups in Azure AD to automatically assign licenses from a set of subscriptions to all the members of the group.</span></span> <span data-ttu-id="946c1-116">这称为 *基于组的许可*。</span><span class="sxs-lookup"><span data-stu-id="946c1-116">This is known as *group-based licensing*.</span></span> <span data-ttu-id="946c1-117">如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或取消分配给该用户帐户。</span><span class="sxs-lookup"><span data-stu-id="946c1-117">If a user account is added to or removed from the group, the licenses for the group's subscriptions will be automatically assigned or unassigned from the user account.</span></span>

<span data-ttu-id="946c1-118">确保所有组成员都有足够的许可证。</span><span class="sxs-lookup"><span data-stu-id="946c1-118">Make sure you have enough licenses for all the group members.</span></span> <span data-ttu-id="946c1-119">如果许可证用完，将不会向新用户分配许可证，直到许可证可用。</span><span class="sxs-lookup"><span data-stu-id="946c1-119">If you run out of licenses, new users won't be assigned licenses until licenses become available.</span></span>

>[!Note]
><span data-ttu-id="946c1-120">不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”。</span><span class="sxs-lookup"><span data-stu-id="946c1-120">You should not configure group-based licensing for groups that contain Azure business to business (B2B) accounts.</span></span>
>

<span data-ttu-id="946c1-121">有关详细信息，请参阅 [Azure AD 中](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)基于组的许可。</span><span class="sxs-lookup"><span data-stu-id="946c1-121">For more informaion, see [group-based licensing in Azure AD](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal).</span></span>

## <a name="next-steps"></a><span data-ttu-id="946c1-122">后续步骤</span><span class="sxs-lookup"><span data-stu-id="946c1-122">Next steps</span></span>

<span data-ttu-id="946c1-123">通过已分配许可证的一组适当的用户帐户，你现在可以：</span><span class="sxs-lookup"><span data-stu-id="946c1-123">With the appropriate set of user accounts that have been assigned licenses, you are now ready to:</span></span>

- [<span data-ttu-id="946c1-124">实现安全性</span><span class="sxs-lookup"><span data-stu-id="946c1-124">Implement security</span></span>](../security/defender-365-security/security-roadmap.md)
- [<span data-ttu-id="946c1-125">部署客户端软件，例如Microsoft 365 应用版</span><span class="sxs-lookup"><span data-stu-id="946c1-125">Deploy client software, such as Microsoft 365 Apps</span></span>](/DeployOffice/deployment-guide-microsoft-365-apps)
- [<span data-ttu-id="946c1-126">设置设备管理</span><span class="sxs-lookup"><span data-stu-id="946c1-126">Set up device management</span></span>](device-management-roadmap-microsoft-365.md)
- [<span data-ttu-id="946c1-127">配置服务和应用程序</span><span class="sxs-lookup"><span data-stu-id="946c1-127">Configure services and applications</span></span>](configure-services-and-applications.md)