---
title: Microsoft 365仅云标识
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
description: 介绍如何在订阅使用仅云标识Microsoft 365创建用户和组。
ms.openlocfilehash: 111c42e644913a8f7f6e41d4e8bf65685263f757
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327923"
---
# <a name="microsoft-365-cloud-only-identity"></a><span data-ttu-id="94384-103">Microsoft 365仅云标识</span><span class="sxs-lookup"><span data-stu-id="94384-103">Microsoft 365 cloud-only identity</span></span>

<span data-ttu-id="94384-104">*此文章适用于 Microsoft 365 企业版和 Office 365 企业版。* </span><span class="sxs-lookup"><span data-stu-id="94384-104">*This article applies to both Microsoft 365 Enterprise and Office 365 Enterprise.*</span></span>

<span data-ttu-id="94384-105">借助仅云标识，所有用户、组和联系人都存储在 Azure Active Directory (订阅的) Azure AD Microsoft 365 租户中。</span><span class="sxs-lookup"><span data-stu-id="94384-105">With cloud-only identity, all your users, groups, and contacts are stored in the Azure Active Directory (Azure AD) tenant of your Microsoft 365 subscription.</span></span> <span data-ttu-id="94384-106">以下是仅云标识的基本组件。</span><span class="sxs-lookup"><span data-stu-id="94384-106">Here are the basic components of cloud-only identity.</span></span>
 
![仅云标识的基本组件](../media/about-microsoft-365-identity/cloud-only-identity.png)

<span data-ttu-id="94384-108">可以通过多种方式对组织中用户及其用户帐户进行分类。</span><span class="sxs-lookup"><span data-stu-id="94384-108">Users and their user accounts in organizations can be categorized in a number of ways.</span></span> <span data-ttu-id="94384-109">例如，有些是员工，并且具有永久状态。</span><span class="sxs-lookup"><span data-stu-id="94384-109">For example, some are employees and have a permanent status.</span></span> <span data-ttu-id="94384-110">一些是具有临时状态的供应商、承包商或合作伙伴。</span><span class="sxs-lookup"><span data-stu-id="94384-110">Some are vendors, contractors, or partners that have a temporary status.</span></span> <span data-ttu-id="94384-111">有些用户没有用户帐户，但仍必须被授予访问特定服务和资源的权限以支持交互和协作。</span><span class="sxs-lookup"><span data-stu-id="94384-111">Some are external users that have no user accounts but must still be granted access to specific services and resources to support interaction and collaboration.</span></span> <span data-ttu-id="94384-112">例如：</span><span class="sxs-lookup"><span data-stu-id="94384-112">For example:</span></span>

- <span data-ttu-id="94384-113">租户帐户表示组织中许可访问云服务的用户。</span><span class="sxs-lookup"><span data-stu-id="94384-113">Tenant accounts represent users within your organization that you license for cloud services</span></span>

- <span data-ttu-id="94384-114">企业到企业 (B2B) 帐户表示组织外部邀请加入协作的用户。</span><span class="sxs-lookup"><span data-stu-id="94384-114">Business to Business (B2B) accounts represent users outside your organization that you invite to participate in collaboration</span></span>

<span data-ttu-id="94384-115">盘点组织中用户的类型。</span><span class="sxs-lookup"><span data-stu-id="94384-115">Take stock of the types of users in your organization.</span></span> <span data-ttu-id="94384-116">什么是分组？</span><span class="sxs-lookup"><span data-stu-id="94384-116">What are the groupings?</span></span> <span data-ttu-id="94384-117">例如，您可以按组织的高级别职能或用途对用户进行分组。</span><span class="sxs-lookup"><span data-stu-id="94384-117">For example, you can group users by high-level function or purpose to your organization.</span></span>

<span data-ttu-id="94384-p104">此外，可以将某些云服务与组织外部没有任何用户帐户的用户共享，而且你还需要标识这些用户组。</span><span class="sxs-lookup"><span data-stu-id="94384-p104">Additionally, some cloud services can be shared with users outside your organization without any user accounts. You'll need to identify these groups of users as well.</span></span>

<span data-ttu-id="94384-120">可以将 Azure AD 中的组用于多个目的，以简化云环境的管理。</span><span class="sxs-lookup"><span data-stu-id="94384-120">You can use groups in Azure AD for several purposes that simplify management of your cloud environment.</span></span> <span data-ttu-id="94384-121">例如，对于 Azure AD 组，你可以：</span><span class="sxs-lookup"><span data-stu-id="94384-121">For example, with Azure AD groups, you can:</span></span>

- <span data-ttu-id="94384-122">使用基于组的许可，一旦添加为Microsoft 365，就会自动将用户的许可证分配给用户帐户。</span><span class="sxs-lookup"><span data-stu-id="94384-122">Use group-based licensing to assign licenses for Microsoft 365 to your user accounts automatically as soon as they are added as members.</span></span>
- <span data-ttu-id="94384-123">根据用户帐户属性（如部门名称）将用户帐户动态添加到特定组。</span><span class="sxs-lookup"><span data-stu-id="94384-123">Add user accounts to specific groups dynamically based on user account attributes, such as department name.</span></span>
- <span data-ttu-id="94384-124"> (在 SaaS) 中自动预配软件即服务用户) ，并保护使用 MFA 身份验证策略和其他条件访问策略 () 应用程序的访问权限。</span><span class="sxs-lookup"><span data-stu-id="94384-124">Automatically provision users for Software as a Service (SaaS) applications and to protect access to those applications with multi-factor authentication (MFA) and other Conditional Access policies.</span></span>
- <span data-ttu-id="94384-125">为联机团队网站设置SharePoint级别。</span><span class="sxs-lookup"><span data-stu-id="94384-125">Provision permissions and levels of access for SharePoint Online team sites.</span></span>

## <a name="next-steps-for-cloud-only-identity"></a><span data-ttu-id="94384-126">仅云标识的以下步骤</span><span class="sxs-lookup"><span data-stu-id="94384-126">Next steps for cloud-only identity</span></span>

- [<span data-ttu-id="94384-127">管理用户帐户</span><span class="sxs-lookup"><span data-stu-id="94384-127">Manage user accounts</span></span>](manage-microsoft-365-accounts.md)
- [<span data-ttu-id="94384-128">向用户帐户分配许可证</span><span class="sxs-lookup"><span data-stu-id="94384-128">Assign licenses to user accounts</span></span>](assign-licenses-to-user-accounts.md)
- [<span data-ttu-id="94384-129">管理组和组成员身份</span><span class="sxs-lookup"><span data-stu-id="94384-129">Manage groups and group membership</span></span>](manage-microsoft-365-groups.md)
- [<span data-ttu-id="94384-130">管理用户帐户密码</span><span class="sxs-lookup"><span data-stu-id="94384-130">Manage user account passwords</span></span>](manage-microsoft-365-passwords.md)
