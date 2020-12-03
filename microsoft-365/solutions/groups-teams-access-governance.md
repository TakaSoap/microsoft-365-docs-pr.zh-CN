---
title: 在 Microsoft 365 组、团队和 SharePoint 中管理访问权限
ms.reviewer: ''
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
description: 了解如何在 Microsoft 365 组、团队和 SharePoint 中管理访问权限。
ms.openlocfilehash: 2a3a5a126a340a8ec1036eaebd22a0a0a81cf6c3
ms.sourcegitcommit: c1dd5be42fe0c5dcc7c05817c941edd9076febf8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2020
ms.locfileid: "49558218"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a><span data-ttu-id="6fb5d-103">在 Microsoft 365 组、团队和 SharePoint 中管理访问权限</span><span class="sxs-lookup"><span data-stu-id="6fb5d-103">Governing access in Microsoft 365 groups, Teams, and SharePoint</span></span>

<span data-ttu-id="6fb5d-104">有很多控件使您能够控制用户访问组、团队和 SharePoint 中的资源的方式。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-104">There are many controls that enable you to govern how people access resources in groups, teams, and SharePoint.</span></span> <span data-ttu-id="6fb5d-105">查看这些选项并考虑它们如何映射到您的业务需求、数据的敏感性以及用户需要与之协作的人员的范围。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-105">Review these options and consider how they map to your business needs, the sensitivity of your data, and the scope of people that your users need to collaborate with.</span></span>

<span data-ttu-id="6fb5d-106">下表提供了对 Microsoft 365 中提供的访问控制的快速参考。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-106">The following table provides a quick reference for the access controls available in Microsoft 365.</span></span> <span data-ttu-id="6fb5d-107">以下各节提供了详细信息。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-107">Further information is provided in the following sections.</span></span>

|<span data-ttu-id="6fb5d-108">类别</span><span class="sxs-lookup"><span data-stu-id="6fb5d-108">Category</span></span>|<span data-ttu-id="6fb5d-109">说明</span><span class="sxs-lookup"><span data-stu-id="6fb5d-109">Description</span></span>|<span data-ttu-id="6fb5d-110">参考</span><span class="sxs-lookup"><span data-stu-id="6fb5d-110">Reference</span></span>|
|:-------|:----------|:--------|
|<span data-ttu-id="6fb5d-111">成员身份</span><span class="sxs-lookup"><span data-stu-id="6fb5d-111">Membership</span></span>|||
||<span data-ttu-id="6fb5d-112">专用团队发现</span><span class="sxs-lookup"><span data-stu-id="6fb5d-112">Discovery of private teams</span></span>|[<span data-ttu-id="6fb5d-113">在 Microsoft 团队中管理专用团队的发现</span><span class="sxs-lookup"><span data-stu-id="6fb5d-113">Manage discovery of private teams in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||<span data-ttu-id="6fb5d-114">基于规则的动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="6fb5d-114">Dynamic group membership based on rules</span></span>|[<span data-ttu-id="6fb5d-115">在 Azure Active Directory 中创建或更新动态组</span><span class="sxs-lookup"><span data-stu-id="6fb5d-115">Create or update a dynamic group in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||<span data-ttu-id="6fb5d-116">控制谁可以共享文件、文件夹和网站。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-116">Control who can share files, folders, and sites.</span></span>|[<span data-ttu-id="6fb5d-117">设置和管理访问请求</span><span class="sxs-lookup"><span data-stu-id="6fb5d-117">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|<span data-ttu-id="6fb5d-118">条件访问</span><span class="sxs-lookup"><span data-stu-id="6fb5d-118">Conditional access</span></span>|||
||<span data-ttu-id="6fb5d-119">多因素身份验证</span><span class="sxs-lookup"><span data-stu-id="6fb5d-119">Multi-Factor Authentication</span></span>|[<span data-ttu-id="6fb5d-120">Azure AD Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="6fb5d-120">Azure AD Multi-Factor Authentication</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||<span data-ttu-id="6fb5d-121">根据组、团队或站点敏感度控制设备访问。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-121">Control device access based on group, team, or site sensitivity.</span></span>|[<span data-ttu-id="6fb5d-122">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="6fb5d-122">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||<span data-ttu-id="6fb5d-123">限制非托管设备的网站访问权限。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-123">Limit site access for unmanaged devices.</span></span>|[<span data-ttu-id="6fb5d-124">控制来自非托管设备的 SharePoint 访问</span><span class="sxs-lookup"><span data-stu-id="6fb5d-124">Control SharePoint access from unmanaged devices</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||<span data-ttu-id="6fb5d-125">基于位置控制网站访问</span><span class="sxs-lookup"><span data-stu-id="6fb5d-125">Control site access based on location</span></span>|[<span data-ttu-id="6fb5d-126">根据网络位置控制对 SharePoint 和 OneDrive 数据的访问</span><span class="sxs-lookup"><span data-stu-id="6fb5d-126">Control access to SharePoint and OneDrive data based on network location</span></span>](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|<span data-ttu-id="6fb5d-127">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="6fb5d-127">Guest access</span></span>|||
||<span data-ttu-id="6fb5d-128">允许或阻止来自指定域的 SharePoint 共享。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-128">Allow or block SharePoint sharing from specified domains.</span></span>|[<span data-ttu-id="6fb5d-129">限制 SharePoint 和 OneDrive 内容的共享（按域）</span><span class="sxs-lookup"><span data-stu-id="6fb5d-129">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||<span data-ttu-id="6fb5d-130">允许或阻止来自指定域的团队或组成员身份。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-130">Allow or block team or group membership from specified domains.</span></span>|[<span data-ttu-id="6fb5d-131">允许或阻止来自特定组织的 B2B 用户的邀请</span><span class="sxs-lookup"><span data-stu-id="6fb5d-131">Allow or block invitations to B2B users from specific organizations</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||<span data-ttu-id="6fb5d-132">阻止匿名共享。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-132">Prevent anonymous sharing.</span></span>|[<span data-ttu-id="6fb5d-133">关闭“任何人”链接</span><span class="sxs-lookup"><span data-stu-id="6fb5d-133">Turn off Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||<span data-ttu-id="6fb5d-134">控制匿名访问链接的权限。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-134">Control the permissions for anonymous access links.</span></span>|[<span data-ttu-id="6fb5d-135">为任何人的链接设置链接权限</span><span class="sxs-lookup"><span data-stu-id="6fb5d-135">Set link permissions for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||<span data-ttu-id="6fb5d-136">控制匿名共享链接的过期。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-136">Control the expiration of anonymous sharing links.</span></span>|[<span data-ttu-id="6fb5d-137">设置“任何人”链接的到期日期</span><span class="sxs-lookup"><span data-stu-id="6fb5d-137">Set an expiration date for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||<span data-ttu-id="6fb5d-138">控制默认情况下显示给用户的共享链接的类型。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-138">Control the type of sharing link shown to users by default.</span></span>|[<span data-ttu-id="6fb5d-139">更改网站的默认链接类型</span><span class="sxs-lookup"><span data-stu-id="6fb5d-139">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||<span data-ttu-id="6fb5d-140">将外部共享限制为特定人员。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-140">Limit external sharing to specific people.</span></span>|[<span data-ttu-id="6fb5d-141">将外部共享限制为指定的安全组</span><span class="sxs-lookup"><span data-stu-id="6fb5d-141">Limit external sharing to specified security groups</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||<span data-ttu-id="6fb5d-142">根据信息敏感度控制对组、团队或网站的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-142">Control guest access to a group, team, or site based on information sensitivity.</span></span>|[<span data-ttu-id="6fb5d-143">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="6fb5d-143">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||<span data-ttu-id="6fb5d-144">请关闭共享选项。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-144">Turn off sharing options.</span></span>|[<span data-ttu-id="6fb5d-145">限制 Microsoft 365 中的共享</span><span class="sxs-lookup"><span data-stu-id="6fb5d-145">Limit sharing in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|<span data-ttu-id="6fb5d-146">用户管理</span><span class="sxs-lookup"><span data-stu-id="6fb5d-146">User management</span></span>|||
||<span data-ttu-id="6fb5d-147">定期查看团队和组成员身份。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-147">Review team and group membership on a regular basis.</span></span>|[<span data-ttu-id="6fb5d-148">什么是 Azure AD 访问审查？</span><span class="sxs-lookup"><span data-stu-id="6fb5d-148">What are Azure AD access reviews?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||<span data-ttu-id="6fb5d-149">自动化对组和团队的访问管理。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-149">Automate access management to groups and teams.</span></span>|[<span data-ttu-id="6fb5d-150">什么是 Azure AD 权限管理？</span><span class="sxs-lookup"><span data-stu-id="6fb5d-150">What is Azure AD entitlement management?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||<span data-ttu-id="6fb5d-151">允许或阻止人员在团队中创建专用频道。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-151">Allow or block people from creating private channels in Teams.</span></span>|[<span data-ttu-id="6fb5d-152">在 Microsoft 团队中管理专用频道的生命周期</span><span class="sxs-lookup"><span data-stu-id="6fb5d-152">Manage the life cycle of private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a><span data-ttu-id="6fb5d-153">成员身份</span><span class="sxs-lookup"><span data-stu-id="6fb5d-153">Membership</span></span>

<span data-ttu-id="6fb5d-154">团队和组的成员身份由所有者控制。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-154">Membership of teams and groups is controlled by owners.</span></span> <span data-ttu-id="6fb5d-155">成员可以邀请其他人，但会将邀请发送给所有者进行审批。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-155">Members can invite others, but the invitations are sent to owners for approval.</span></span> <span data-ttu-id="6fb5d-156">虽然组织中的任何人都可以发现公共团队和组，但您可以控制是否可发现专用团队和组：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-156">While public teams and groups are discoverable by anyone in the organization, you can control whether private teams and groups are discoverable:</span></span>

- [<span data-ttu-id="6fb5d-157">在 Microsoft 团队中管理专用团队的发现</span><span class="sxs-lookup"><span data-stu-id="6fb5d-157">Manage discovery of private teams in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

<span data-ttu-id="6fb5d-158">您可以根据某些条件（如部门）动态管理组或团队的成员资格。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-158">You can manage membership of a group or team dynamically based on some criteria, such as department.</span></span> <span data-ttu-id="6fb5d-159">在这种情况下，成员和所有者无法邀请人员加入团队。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-159">In this case, members and owners cannot invite people to the team.</span></span>

- [<span data-ttu-id="6fb5d-160">在 Azure Active Directory 中创建或更新动态组</span><span class="sxs-lookup"><span data-stu-id="6fb5d-160">Create or update a dynamic group in Azure Active Directory</span></span>](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

<span data-ttu-id="6fb5d-161">SharePoint 网站能够将所有者、成员和访问者与组或团队成员身份分开。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-161">SharePoint sites provide the ability to add owners, members, and visitors apart from group or team membership.</span></span> <span data-ttu-id="6fb5d-162">根据您的要求，您可能希望限制谁可以邀请人员加入网站。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-162">Depending on your requirements, you may want to restrict who can invite people to the site.</span></span> <span data-ttu-id="6fb5d-163">此外，根据给定网站中信息的敏感度，您可能希望限制可以共享文件和文件夹的用户。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-163">Also, depending on the sensitivity of the information in a given site, you may want to restrict who can share files and folder.</span></span> <span data-ttu-id="6fb5d-164">这些限制由团队、组或网站所有者配置：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-164">These restrictions are configured by the team, group, or site owner:</span></span>

- [<span data-ttu-id="6fb5d-165">设置和管理访问请求</span><span class="sxs-lookup"><span data-stu-id="6fb5d-165">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a><span data-ttu-id="6fb5d-166">条件访问</span><span class="sxs-lookup"><span data-stu-id="6fb5d-166">Conditional access</span></span>

<span data-ttu-id="6fb5d-167">使用 Microsoft 365，您可以对组织内部和外部的人员要求多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-167">With Microsoft 365, you can require multi-factor authentication for both people inside and outside your organization.</span></span> <span data-ttu-id="6fb5d-168">在提示用户第二种身份验证因素的情况下，有许多选项。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-168">There are many options for the circumstances when people are prompted for a second factor of authentication.</span></span> <span data-ttu-id="6fb5d-169">强烈建议您为您的组织部署多因素身份验证：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-169">We highly recommend that you deploy multi-factor authentication for your organization:</span></span>

- [<span data-ttu-id="6fb5d-170">Azure AD Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="6fb5d-170">Azure AD Multi-Factor Authentication</span></span>](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

<span data-ttu-id="6fb5d-171">如果您的某些组和团队中包含敏感信息，则可以根据组或团队的敏感度标签强制实施设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-171">If you have sensitive information in some of your groups and teams, you can enforce device management policies based on a group or team's sensitivity label.</span></span> <span data-ttu-id="6fb5d-172">您可以完全阻止来自非托管设备的访问，或允许仅限 web 的访问权限：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-172">You can block access entirely from unmanaged devices, or allow limited, web only access:</span></span>

- [<span data-ttu-id="6fb5d-173">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="6fb5d-173">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

<span data-ttu-id="6fb5d-174">在 SharePoint 中，可以限制对指定网络位置中的网站的访问。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-174">In SharePoint, you can restrict access to sites from specified network locations.</span></span>

- [<span data-ttu-id="6fb5d-175">根据网络位置控制对 SharePoint 和 OneDrive 数据的访问</span><span class="sxs-lookup"><span data-stu-id="6fb5d-175">Control access to SharePoint and OneDrive data based on network location</span></span>](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


<span data-ttu-id="6fb5d-176">其他资源：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-176">Additional resources:</span></span>

- [<span data-ttu-id="6fb5d-177">规划条件访问部署</span><span class="sxs-lookup"><span data-stu-id="6fb5d-177">Plan a Conditional Access deployment</span></span>](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [<span data-ttu-id="6fb5d-178">Microsoft Intune 概述</span><span class="sxs-lookup"><span data-stu-id="6fb5d-178">Microsoft Intune overview</span></span>](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [<span data-ttu-id="6fb5d-179">控制来自非托管设备的 SharePoint 访问</span><span class="sxs-lookup"><span data-stu-id="6fb5d-179">Control SharePoint access from unmanaged devices</span></span>](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a><span data-ttu-id="6fb5d-180">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="6fb5d-180">Guest access</span></span>

<span data-ttu-id="6fb5d-181">您可以根据其电子邮件地址的域来限制来宾。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-181">You can restrict guests based on the domain of their email address.</span></span> <span data-ttu-id="6fb5d-182">SharePoint 提供组织范围和特定于站点的域限制设置。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-182">SharePoint offers organization-wide and site-specific domain restriction settings.</span></span> <span data-ttu-id="6fb5d-183">组和团队使用 Azure AD 中的域允许和拒绝列表。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-183">Groups and Teams use the domain allow and deny lists in Azure AD.</span></span> <span data-ttu-id="6fb5d-184">请务必配置这两个设置以避免不必要的共享，并确保用户体验一致：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-184">Be sure to configure both settings to avoid unwanted sharing and ensure a consistent user experience:</span></span>

- [<span data-ttu-id="6fb5d-185">限制 SharePoint 和 OneDrive 内容的共享（按域）</span><span class="sxs-lookup"><span data-stu-id="6fb5d-185">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [<span data-ttu-id="6fb5d-186">允许或阻止来自特定组织的 B2B 用户的邀请</span><span class="sxs-lookup"><span data-stu-id="6fb5d-186">Allow or block invitations to B2B users from specific organizations</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

<span data-ttu-id="6fb5d-187">Microsoft 365 允许使用共享链接的 *任何人* 匿名共享文件和文件夹。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-187">Microsoft 365 allows anonymous sharing of files and folders by using *Anyone* sharing links.</span></span> <span data-ttu-id="6fb5d-188">*任何人都* 可以转发任何链接，并且具有链接的任何人都可以访问共享项目。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-188">*Anyone* links can be forwarded and anyone with the link can access the shared item.</span></span> <span data-ttu-id="6fb5d-189">根据数据的敏感度，考虑如何使用 *任何人* 的链接，包括将其完全关闭、将链接权限限制为只读或为其设置过期时间：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-189">Depending on the sensitivity of your data, consider governing how *Anyone* links are used - including turning them off entirely, restricting link permissions to read-only, or setting an expiration time for them:</span></span>

- [<span data-ttu-id="6fb5d-190">关闭“任何人”链接</span><span class="sxs-lookup"><span data-stu-id="6fb5d-190">Turn off Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [<span data-ttu-id="6fb5d-191">为任何人的链接设置链接权限</span><span class="sxs-lookup"><span data-stu-id="6fb5d-191">Set link permissions for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [<span data-ttu-id="6fb5d-192">设置“任何人”链接的到期日期</span><span class="sxs-lookup"><span data-stu-id="6fb5d-192">Set an expiration date for Anyone links</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

<span data-ttu-id="6fb5d-193">共享文件或文件夹时，用户有几种链接类型可供选择。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-193">When sharing files or folders, users have several link types to choose from.</span></span> <span data-ttu-id="6fb5d-194">若要降低意外共享的风险，可以在用户共享时更改提供给用户的默认链接类型。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-194">To reduce the risk of accidental inappropriate sharing, you can change the default link type presented to users when they share.</span></span> <span data-ttu-id="6fb5d-195">例如，在 " *任何人* " 链接中更改默认值（允许对 *组织中的用户* 进行匿名访问）可能会降低敏感信息的不需要外部共享的风险：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-195">For example, changing the default from *Anyone* links - which allow anonymous access - to *People in your organization* links can reduce the risk of unwanted external sharing of sensitive information:</span></span>

- [<span data-ttu-id="6fb5d-196">更改网站的默认链接类型</span><span class="sxs-lookup"><span data-stu-id="6fb5d-196">Change the default link type for a site</span></span>](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

<span data-ttu-id="6fb5d-197">如果你的组织具有需要与来宾共享的敏感数据，但你担心不恰当的共享，则可以将文件和文件夹的外部共享限制为指定安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-197">If your organization has sensitive data that you need to share with guests, but you're concerned about inappropriate sharing, you can limit external sharing of files and folders to the members of specified security groups.</span></span> <span data-ttu-id="6fb5d-198">通过这种方式，您可以限制外部与特定人员组的共享，或要求您的用户在将其添加到安全组之前先针对适当的外部共享进行培训：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-198">In this way, you can restrict sharing externally to a specific group of people, or require your users to take training around appropriate external sharing before adding them to the security group:</span></span>

- [<span data-ttu-id="6fb5d-199">将外部共享限制为指定的安全组</span><span class="sxs-lookup"><span data-stu-id="6fb5d-199">Limit external sharing to specified security groups</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

<span data-ttu-id="6fb5d-200">组和团队具有允许或拒绝来宾访问的组织级别设置。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-200">Groups and Teams have organization-level setting that allow or deny guest access.</span></span> <span data-ttu-id="6fb5d-201">虽然您可以 [使用 Microsoft PowerShell 限制对特定团队或组的来宾访问](per-group-guest-access.md)，但我们建议通过灵敏度标签执行此操作。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-201">While you can [restrict guest access to specific teams or groups by using Microsoft PowerShell](per-group-guest-access.md), we recommend doing this by means of a sensitivity label.</span></span> <span data-ttu-id="6fb5d-202">使用敏感度标签，可以根据应用的标签自动允许或拒绝来宾访问：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-202">With sensitivity labels you can automatically allow or deny guest access based on the label applied:</span></span>

- [<span data-ttu-id="6fb5d-203">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="6fb5d-203">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

<span data-ttu-id="6fb5d-204">Microsoft 365 提供了多种不同的信息共享方法。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-204">Microsoft 365 offers many different methods of sharing information.</span></span> <span data-ttu-id="6fb5d-205">如果您有敏感信息，并且希望限制其共享方式，请查看限制共享的选项：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-205">If you have sensitive information and you want to restrict how it's shared, review the options for limiting sharing:</span></span>

- [<span data-ttu-id="6fb5d-206">限制 Microsoft 365 中的共享</span><span class="sxs-lookup"><span data-stu-id="6fb5d-206">Limit sharing in Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

<span data-ttu-id="6fb5d-207">其他资源：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-207">Additional resources:</span></span>

- [<span data-ttu-id="6fb5d-208">与 Microsoft 365 建立安全协作</span><span class="sxs-lookup"><span data-stu-id="6fb5d-208">Set up secure collaboration with Microsoft 365</span></span>](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [<span data-ttu-id="6fb5d-209">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="6fb5d-209">Best practices for sharing files and folders with unauthenticated users</span></span>](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [<span data-ttu-id="6fb5d-210">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="6fb5d-210">Limit accidental exposure to files when sharing with people outside your organization</span></span>](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [<span data-ttu-id="6fb5d-211">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="6fb5d-211">Create a secure guest sharing environment</span></span>](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [<span data-ttu-id="6fb5d-212">启用 B2B 外部协作并管理可邀请来宾的人士</span><span class="sxs-lookup"><span data-stu-id="6fb5d-212">Enable B2B external collaboration and manage who can invite guests</span></span>](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a><span data-ttu-id="6fb5d-213">用户管理</span><span class="sxs-lookup"><span data-stu-id="6fb5d-213">User management</span></span>

<span data-ttu-id="6fb5d-214">随着组织中的组和团队的发展，一种很好的做法是定期查看团队和组成员资格。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-214">As groups and teams evolve in your organization, a good practice is to review team and group membership on a regular basis.</span></span> <span data-ttu-id="6fb5d-215">对于具有不断变化的成员身份、包含敏感信息的团队和组，或者包含来宾的团队和组，这可能尤其有用。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-215">This may be particularly useful for teams and groups with a changing membership, those that contain sensitive information, or those that include guests.</span></span> <span data-ttu-id="6fb5d-216">考虑为这些团队和组设置访问评审：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-216">Consider setting up access reviews for these teams and groups:</span></span>

- [<span data-ttu-id="6fb5d-217">什么是 Azure AD 访问审查？</span><span class="sxs-lookup"><span data-stu-id="6fb5d-217">What are Azure AD access reviews?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

<span data-ttu-id="6fb5d-218">许多组织与其他组织或主要供应商的业务合作关系，他们的深度与他们进行协作。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-218">Many organizations have business partnerships with other organizations or key vendors with whom they collaborate in depth.</span></span> <span data-ttu-id="6fb5d-219">在这些方案中管理用户管理和资源访问可能是很困难的。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-219">User management and access to resources can be challenging to manage in these scenarios.</span></span> <span data-ttu-id="6fb5d-220">请考虑自动执行某些用户管理任务，甚至将其中一些用户转换为合作伙伴组织：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-220">Consider automating some of the user management tasks and even transitioning some of them to your partner organization:</span></span>

- [<span data-ttu-id="6fb5d-221">什么是 Azure AD 权限管理？</span><span class="sxs-lookup"><span data-stu-id="6fb5d-221">What is Azure AD entitlement management?</span></span>](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

<span data-ttu-id="6fb5d-222">团队中的专用通道允许范围内的对话和团队成员的子集之间共享文件。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-222">Private channels in Teams allow for scoped conversations and file sharing between a subset of team members.</span></span> <span data-ttu-id="6fb5d-223">根据您的特定业务需求，您可能希望允许或阻止此功能。</span><span class="sxs-lookup"><span data-stu-id="6fb5d-223">Depending on your specific business needs, you may want to allow or block this capability.</span></span>

- [<span data-ttu-id="6fb5d-224">Microsoft 团队中的专用通道</span><span class="sxs-lookup"><span data-stu-id="6fb5d-224">Private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [<span data-ttu-id="6fb5d-225">在 Microsoft 团队中管理专用频道的生命周期</span><span class="sxs-lookup"><span data-stu-id="6fb5d-225">Manage the life cycle of private channels in Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

<span data-ttu-id="6fb5d-226">其他资源：</span><span class="sxs-lookup"><span data-stu-id="6fb5d-226">Additional resources:</span></span>

- [<span data-ttu-id="6fb5d-227">Azure Active Directory 标识管理</span><span class="sxs-lookup"><span data-stu-id="6fb5d-227">Azure Active Directory Identity Governance</span></span>](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a><span data-ttu-id="6fb5d-228">相关主题</span><span class="sxs-lookup"><span data-stu-id="6fb5d-228">Related topics</span></span>

[<span data-ttu-id="6fb5d-229">Microsoft Teams 中的安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="6fb5d-229">Security and compliance in Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[<span data-ttu-id="6fb5d-230">在 SharePoint 中管理共享设置</span><span class="sxs-lookup"><span data-stu-id="6fb5d-230">Manage sharing settings in SharePoint</span></span>](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[<span data-ttu-id="6fb5d-231">在 Yammer 中创建和管理外部网络</span><span class="sxs-lookup"><span data-stu-id="6fb5d-231">Create and manage an external network in Yammer</span></span>](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[<span data-ttu-id="6fb5d-232">配置具有三层保护的 Teams</span><span class="sxs-lookup"><span data-stu-id="6fb5d-232">Configure Teams with three tiers of protection</span></span>](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
