---
title: 管理 Microsoft 365 组、Teams 和 SharePoint
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
description: 了解管理组、Microsoft 365和Teams中的SharePoint。
ms.openlocfilehash: 44b90e461c81875fa5ccf728c890d5eaebf7d613
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922276"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a><span data-ttu-id="d0d47-103">管理 Microsoft 365 组、Teams 和 SharePoint</span><span class="sxs-lookup"><span data-stu-id="d0d47-103">Governing access in Microsoft 365 groups, Teams, and SharePoint</span></span>

<span data-ttu-id="d0d47-104">有许多控件使您能够控制用户如何访问组、团队和团队中的SharePoint。</span><span class="sxs-lookup"><span data-stu-id="d0d47-104">There are many controls that enable you to govern how people access resources in groups, teams, and SharePoint.</span></span> <span data-ttu-id="d0d47-105">查看这些选项，并考虑它们如何映射到业务需求、数据的敏感度以及用户需要协作的用户范围。</span><span class="sxs-lookup"><span data-stu-id="d0d47-105">Review these options and consider how they map to your business needs, the sensitivity of your data, and the scope of people that your users need to collaborate with.</span></span>

<span data-ttu-id="d0d47-106">下表提供了一个快速参考，这些访问控制可用于Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="d0d47-106">The following table provides a quick reference for the access controls available in Microsoft 365.</span></span> <span data-ttu-id="d0d47-107">以下各节提供了进一步的信息。</span><span class="sxs-lookup"><span data-stu-id="d0d47-107">Further information is provided in the following sections.</span></span>

|<span data-ttu-id="d0d47-108">类别</span><span class="sxs-lookup"><span data-stu-id="d0d47-108">Category</span></span>|<span data-ttu-id="d0d47-109">说明</span><span class="sxs-lookup"><span data-stu-id="d0d47-109">Description</span></span>|<span data-ttu-id="d0d47-110">参考</span><span class="sxs-lookup"><span data-stu-id="d0d47-110">Reference</span></span>|
|:-------|:----------|:--------|
|<span data-ttu-id="d0d47-111">成员身份</span><span class="sxs-lookup"><span data-stu-id="d0d47-111">Membership</span></span>|||
||<span data-ttu-id="d0d47-112">发现私人团队</span><span class="sxs-lookup"><span data-stu-id="d0d47-112">Discovery of private teams</span></span>|[<span data-ttu-id="d0d47-113">在部署中管理私人团队Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0d47-113">Manage discovery of private teams in Microsoft Teams</span></span>](/microsoftteams/manage-discovery-of-private-teams)|
||<span data-ttu-id="d0d47-114">基于规则的动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="d0d47-114">Dynamic group membership based on rules</span></span>|[<span data-ttu-id="d0d47-115">在动态组中创建或更新Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d0d47-115">Create or update a dynamic group in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)|
||<span data-ttu-id="d0d47-116">控制谁可以共享文件、文件夹和网站。</span><span class="sxs-lookup"><span data-stu-id="d0d47-116">Control who can share files, folders, and sites.</span></span>|[<span data-ttu-id="d0d47-117">设置和管理访问请求</span><span class="sxs-lookup"><span data-stu-id="d0d47-117">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|<span data-ttu-id="d0d47-118">条件访问</span><span class="sxs-lookup"><span data-stu-id="d0d47-118">Conditional access</span></span>|||
||<span data-ttu-id="d0d47-119">多重身份验证</span><span class="sxs-lookup"><span data-stu-id="d0d47-119">Multi-Factor Authentication</span></span>|[<span data-ttu-id="d0d47-120">Azure AD Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="d0d47-120">Azure AD Multi-Factor Authentication</span></span>](/azure/active-directory/authentication/concept-mfa-howitworks)|
||<span data-ttu-id="d0d47-121">根据组、团队或网站敏感度控制设备访问。</span><span class="sxs-lookup"><span data-stu-id="d0d47-121">Control device access based on group, team, or site sensitivity.</span></span>|[<span data-ttu-id="d0d47-122">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="d0d47-122">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](../compliance/sensitivity-labels-teams-groups-sites.md)|
||<span data-ttu-id="d0d47-123">限制非托管设备的站点访问。</span><span class="sxs-lookup"><span data-stu-id="d0d47-123">Limit site access for unmanaged devices.</span></span>|[<span data-ttu-id="d0d47-124">控制SharePoint非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="d0d47-124">Control SharePoint access from unmanaged devices</span></span>](/sharepoint/control-access-from-unmanaged-devices)|
||<span data-ttu-id="d0d47-125">根据位置控制网站访问</span><span class="sxs-lookup"><span data-stu-id="d0d47-125">Control site access based on location</span></span>|[<span data-ttu-id="d0d47-126">根据网络位置控制对 SharePoint 和 OneDrive 数据的访问</span><span class="sxs-lookup"><span data-stu-id="d0d47-126">Control access to SharePoint and OneDrive data based on network location</span></span>](/sharepoint/control-access-based-on-network-location)|
|<span data-ttu-id="d0d47-127">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="d0d47-127">Guest access</span></span>|||
||<span data-ttu-id="d0d47-128">允许或阻止SharePoint域中进行共享。</span><span class="sxs-lookup"><span data-stu-id="d0d47-128">Allow or block SharePoint sharing from specified domains.</span></span>|[<span data-ttu-id="d0d47-129">按域限制 SharePoint 和 OneDrive 内容的共享</span><span class="sxs-lookup"><span data-stu-id="d0d47-129">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](/sharepoint/restricted-domains-sharing)|
||<span data-ttu-id="d0d47-130">允许或阻止来自指定域的团队或组成员身份。</span><span class="sxs-lookup"><span data-stu-id="d0d47-130">Allow or block team or group membership from specified domains.</span></span>|<span data-ttu-id="d0d47-131">[允许或阻止特定组织向 B2B 用户发出邀请](/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="d0d47-131">[Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list)</span></span>|
||<span data-ttu-id="d0d47-132">阻止匿名共享。</span><span class="sxs-lookup"><span data-stu-id="d0d47-132">Prevent anonymous sharing.</span></span>|[<span data-ttu-id="d0d47-133">关闭“任何人”链接</span><span class="sxs-lookup"><span data-stu-id="d0d47-133">Turn off Anyone links</span></span>](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||<span data-ttu-id="d0d47-134">控制匿名访问链接的权限。</span><span class="sxs-lookup"><span data-stu-id="d0d47-134">Control the permissions for anonymous access links.</span></span>|[<span data-ttu-id="d0d47-135">设置"任何人"链接的链接权限</span><span class="sxs-lookup"><span data-stu-id="d0d47-135">Set link permissions for Anyone links</span></span>](./best-practices-anonymous-sharing.md#set-link-permissions)|
||<span data-ttu-id="d0d47-136">控制匿名共享链接的过期时间。</span><span class="sxs-lookup"><span data-stu-id="d0d47-136">Control the expiration of anonymous sharing links.</span></span>|[<span data-ttu-id="d0d47-137">设置“任何人”链接的到期日期</span><span class="sxs-lookup"><span data-stu-id="d0d47-137">Set an expiration date for Anyone links</span></span>](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||<span data-ttu-id="d0d47-138">控制默认向用户显示的共享链接的类型。</span><span class="sxs-lookup"><span data-stu-id="d0d47-138">Control the type of sharing link shown to users by default.</span></span>|[<span data-ttu-id="d0d47-139">更改网站的默认链接类型</span><span class="sxs-lookup"><span data-stu-id="d0d47-139">Change the default link type for a site</span></span>](/sharepoint/change-default-sharing-link)|
||<span data-ttu-id="d0d47-140">将外部共享限制为特定人员。</span><span class="sxs-lookup"><span data-stu-id="d0d47-140">Limit external sharing to specific people.</span></span>|[<span data-ttu-id="d0d47-141">将外部共享限制为指定安全组</span><span class="sxs-lookup"><span data-stu-id="d0d47-141">Limit external sharing to specified security groups</span></span>](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||<span data-ttu-id="d0d47-142">根据信息敏感度控制对组、团队或网站的来宾访问。</span><span class="sxs-lookup"><span data-stu-id="d0d47-142">Control guest access to a group, team, or site based on information sensitivity.</span></span>|[<span data-ttu-id="d0d47-143">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="d0d47-143">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](../compliance/sensitivity-labels-teams-groups-sites.md)|
||<span data-ttu-id="d0d47-144">关闭共享选项。</span><span class="sxs-lookup"><span data-stu-id="d0d47-144">Turn off sharing options.</span></span>|[<span data-ttu-id="d0d47-145">限制 Microsoft 365 中的共享</span><span class="sxs-lookup"><span data-stu-id="d0d47-145">Limit sharing in Microsoft 365</span></span>](./microsoft-365-limit-sharing.md)|
|<span data-ttu-id="d0d47-146">用户管理</span><span class="sxs-lookup"><span data-stu-id="d0d47-146">User management</span></span>|||
||<span data-ttu-id="d0d47-147">定期查看团队和组成员身份。</span><span class="sxs-lookup"><span data-stu-id="d0d47-147">Review team and group membership on a regular basis.</span></span>|[<span data-ttu-id="d0d47-148">什么是 Azure AD 访问评审？</span><span class="sxs-lookup"><span data-stu-id="d0d47-148">What are Azure AD access reviews?</span></span>](/azure/active-directory/governance/access-reviews-overview)|
||<span data-ttu-id="d0d47-149">自动管理对组和团队的访问。</span><span class="sxs-lookup"><span data-stu-id="d0d47-149">Automate access management to groups and teams.</span></span>|[<span data-ttu-id="d0d47-150">什么是 Azure AD 权利管理？</span><span class="sxs-lookup"><span data-stu-id="d0d47-150">What is Azure AD entitlement management?</span></span>](/azure/active-directory/governance/entitlement-management-overview)|
||<span data-ttu-id="d0d47-151">允许或阻止用户创建专用频道Teams。</span><span class="sxs-lookup"><span data-stu-id="d0d47-151">Allow or block people from creating private channels in Teams.</span></span>|[<span data-ttu-id="d0d47-152">管理频道中私人频道的Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0d47-152">Manage the life cycle of private channels in Microsoft Teams</span></span>](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a><span data-ttu-id="d0d47-153">成员身份</span><span class="sxs-lookup"><span data-stu-id="d0d47-153">Membership</span></span>

<span data-ttu-id="d0d47-154">团队和组的成员身份由所有者控制。</span><span class="sxs-lookup"><span data-stu-id="d0d47-154">Membership of teams and groups is controlled by owners.</span></span> <span data-ttu-id="d0d47-155">成员可以邀请其他人，但邀请将发送给所有者进行审批。</span><span class="sxs-lookup"><span data-stu-id="d0d47-155">Members can invite others, but the invitations are sent to owners for approval.</span></span> <span data-ttu-id="d0d47-156">尽管组织中任何人都可以发现公共团队和组，但你可以控制私人团队和组是否可发现：</span><span class="sxs-lookup"><span data-stu-id="d0d47-156">While public teams and groups are discoverable by anyone in the organization, you can control whether private teams and groups are discoverable:</span></span>

- [<span data-ttu-id="d0d47-157">在部署中管理私人团队Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0d47-157">Manage discovery of private teams in Microsoft Teams</span></span>](/microsoftteams/manage-discovery-of-private-teams)

<span data-ttu-id="d0d47-158">你可以根据某些条件（如部门）动态管理组或团队的成员身份。</span><span class="sxs-lookup"><span data-stu-id="d0d47-158">You can manage membership of a group or team dynamically based on some criteria, such as department.</span></span> <span data-ttu-id="d0d47-159">在这种情况下，成员和所有者无法邀请人员加入团队。</span><span class="sxs-lookup"><span data-stu-id="d0d47-159">In this case, members and owners cannot invite people to the team.</span></span> <span data-ttu-id="d0d47-160">动态组使用你在Azure Active Directory定义的元数据来控制哪些用户是该组的成员。</span><span class="sxs-lookup"><span data-stu-id="d0d47-160">Dynamic groups uses metadata that you define in Azure Active Directory to control who is a member of the group.</span></span> <span data-ttu-id="d0d47-161">请确保你使用的元数据已完成且是最新的，因为不正确的元数据可能会导致用户被排除在组外或添加不正确的用户。</span><span class="sxs-lookup"><span data-stu-id="d0d47-161">Be sure the metadata that you're using is complete and up to date as incorrect metadata can lead to users being left out of groups or incorrect users being added.</span></span>

- [<span data-ttu-id="d0d47-162">在动态组中创建或更新Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="d0d47-162">Create or update a dynamic group in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

<span data-ttu-id="d0d47-163">SharePoint网站提供除组或团队成员身份外添加所有者、成员和访问者的能力。</span><span class="sxs-lookup"><span data-stu-id="d0d47-163">SharePoint sites provide the ability to add owners, members, and visitors apart from group or team membership.</span></span> <span data-ttu-id="d0d47-164">根据您的要求，您可能需要限制可以邀请人员访问网站的人。</span><span class="sxs-lookup"><span data-stu-id="d0d47-164">Depending on your requirements, you may want to restrict who can invite people to the site.</span></span> <span data-ttu-id="d0d47-165">此外，根据给定网站中信息的敏感度，你可能希望限制可以共享文件和文件夹的人。</span><span class="sxs-lookup"><span data-stu-id="d0d47-165">Also, depending on the sensitivity of the information in a given site, you may want to restrict who can share files and folder.</span></span> <span data-ttu-id="d0d47-166">这些限制由团队、组或网站所有者配置：</span><span class="sxs-lookup"><span data-stu-id="d0d47-166">These restrictions are configured by the team, group, or site owner:</span></span>

- [<span data-ttu-id="d0d47-167">设置和管理访问请求</span><span class="sxs-lookup"><span data-stu-id="d0d47-167">Set up and manage access requests</span></span>](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a><span data-ttu-id="d0d47-168">条件访问</span><span class="sxs-lookup"><span data-stu-id="d0d47-168">Conditional access</span></span>

<span data-ttu-id="d0d47-169">使用 Microsoft 365，您可以要求对组织内外的用户进行多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="d0d47-169">With Microsoft 365, you can require multi-factor authentication for both people inside and outside your organization.</span></span> <span data-ttu-id="d0d47-170">当系统提示用户进行第二种身份验证时，有许多选项可供选择。</span><span class="sxs-lookup"><span data-stu-id="d0d47-170">There are many options for the circumstances when people are prompted for a second factor of authentication.</span></span> <span data-ttu-id="d0d47-171">强烈建议为组织部署多重身份验证：</span><span class="sxs-lookup"><span data-stu-id="d0d47-171">We highly recommend that you deploy multi-factor authentication for your organization:</span></span>

- [<span data-ttu-id="d0d47-172">Azure AD Multi-Factor Authentication</span><span class="sxs-lookup"><span data-stu-id="d0d47-172">Azure AD Multi-Factor Authentication</span></span>](/azure/active-directory/authentication/concept-mfa-howitworks)

<span data-ttu-id="d0d47-173">如果你在某些组和团队中具有敏感信息，可以基于组或团队的敏感度标签强制执行设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="d0d47-173">If you have sensitive information in some of your groups and teams, you can enforce device management policies based on a group or team's sensitivity label.</span></span> <span data-ttu-id="d0d47-174">你可以完全阻止来自非托管设备的访问，或允许受限的仅 Web 访问：</span><span class="sxs-lookup"><span data-stu-id="d0d47-174">You can block access entirely from unmanaged devices, or allow limited, web only access:</span></span>

- [<span data-ttu-id="d0d47-175">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="d0d47-175">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](../compliance/sensitivity-labels-teams-groups-sites.md)

<span data-ttu-id="d0d47-176">在SharePoint中，您可以限制从指定的网络位置访问站点。</span><span class="sxs-lookup"><span data-stu-id="d0d47-176">In SharePoint, you can restrict access to sites from specified network locations.</span></span>

- [<span data-ttu-id="d0d47-177">根据网络位置控制对 SharePoint 和 OneDrive 数据的访问</span><span class="sxs-lookup"><span data-stu-id="d0d47-177">Control access to SharePoint and OneDrive data based on network location</span></span>](/sharepoint/control-access-based-on-network-location)


<span data-ttu-id="d0d47-178">其他资源：</span><span class="sxs-lookup"><span data-stu-id="d0d47-178">Additional resources:</span></span>

- [<span data-ttu-id="d0d47-179">规划条件访问部署</span><span class="sxs-lookup"><span data-stu-id="d0d47-179">Plan a Conditional Access deployment</span></span>](/azure/active-directory/conditional-access/plan-conditional-access)

- [<span data-ttu-id="d0d47-180">Microsoft Intune概述</span><span class="sxs-lookup"><span data-stu-id="d0d47-180">Microsoft Intune overview</span></span>](/mem/intune/fundamentals/what-is-intune)

- [<span data-ttu-id="d0d47-181">控制SharePoint非托管设备的访问</span><span class="sxs-lookup"><span data-stu-id="d0d47-181">Control SharePoint access from unmanaged devices</span></span>](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a><span data-ttu-id="d0d47-182">来宾访问权限</span><span class="sxs-lookup"><span data-stu-id="d0d47-182">Guest access</span></span>

<span data-ttu-id="d0d47-183">你可以根据来宾的电子邮件地址的域来限制来宾。</span><span class="sxs-lookup"><span data-stu-id="d0d47-183">You can restrict guests based on the domain of their email address.</span></span> <span data-ttu-id="d0d47-184">SharePoint组织范围内和特定于站点的域限制设置。</span><span class="sxs-lookup"><span data-stu-id="d0d47-184">SharePoint offers organization-wide and site-specific domain restriction settings.</span></span> <span data-ttu-id="d0d47-185">组和Teams Azure AD 中的域允许和拒绝列表。</span><span class="sxs-lookup"><span data-stu-id="d0d47-185">Groups and Teams use the domain allow and deny lists in Azure AD.</span></span> <span data-ttu-id="d0d47-186">请确保配置这两个设置以避免不必要的共享，并确保一致的用户体验：</span><span class="sxs-lookup"><span data-stu-id="d0d47-186">Be sure to configure both settings to avoid unwanted sharing and ensure a consistent user experience:</span></span>

- [<span data-ttu-id="d0d47-187">按域限制 SharePoint 和 OneDrive 内容的共享</span><span class="sxs-lookup"><span data-stu-id="d0d47-187">Restrict sharing of SharePoint and OneDrive content by domain</span></span>](/sharepoint/restricted-domains-sharing)

- <span data-ttu-id="d0d47-188">[允许或阻止特定组织向 B2B 用户发出邀请](/azure/active-directory/b2b/allow-deny-list)。</span><span class="sxs-lookup"><span data-stu-id="d0d47-188">[Allow or block invitations to B2B users from specific organizations](/azure/active-directory/b2b/allow-deny-list)</span></span>

<span data-ttu-id="d0d47-189">Microsoft 365任何人共享链接允许匿名 *共享文件和文件夹*。</span><span class="sxs-lookup"><span data-stu-id="d0d47-189">Microsoft 365 allows anonymous sharing of files and folders by using *Anyone* sharing links.</span></span> <span data-ttu-id="d0d47-190">*可以* 转发"任何人"链接，具有该链接的任何人都可以访问共享项目。</span><span class="sxs-lookup"><span data-stu-id="d0d47-190">*Anyone* links can be forwarded and anyone with the link can access the shared item.</span></span> <span data-ttu-id="d0d47-191">根据数据的敏感度，考虑管理"任何人"链接的使用方式，包括完全关闭链接、将链接权限限制为只读或为链接设置过期时间：</span><span class="sxs-lookup"><span data-stu-id="d0d47-191">Depending on the sensitivity of your data, consider governing how *Anyone* links are used - including turning them off entirely, restricting link permissions to read-only, or setting an expiration time for them:</span></span>

- [<span data-ttu-id="d0d47-192">关闭“任何人”链接</span><span class="sxs-lookup"><span data-stu-id="d0d47-192">Turn off Anyone links</span></span>](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [<span data-ttu-id="d0d47-193">设置"任何人"链接的链接权限</span><span class="sxs-lookup"><span data-stu-id="d0d47-193">Set link permissions for Anyone links</span></span>](./best-practices-anonymous-sharing.md#set-link-permissions)

- [<span data-ttu-id="d0d47-194">设置“任何人”链接的到期日期</span><span class="sxs-lookup"><span data-stu-id="d0d47-194">Set an expiration date for Anyone links</span></span>](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

<span data-ttu-id="d0d47-195">共享文件或文件夹时，用户可以从多个链接类型中选择。</span><span class="sxs-lookup"><span data-stu-id="d0d47-195">When sharing files or folders, users have several link types to choose from.</span></span> <span data-ttu-id="d0d47-196">若要降低意外不当共享的风险，可以更改共享时向用户显示的默认链接类型。</span><span class="sxs-lookup"><span data-stu-id="d0d47-196">To reduce the risk of accidental inappropriate sharing, you can change the default link type presented to users when they share.</span></span> <span data-ttu-id="d0d47-197">例如，将默认值从"任何人"链接（允许匿名访问）更改到"组织人员"链接可降低不需要的外部共享敏感信息的风险：</span><span class="sxs-lookup"><span data-stu-id="d0d47-197">For example, changing the default from *Anyone* links - which allow anonymous access - to *People in your organization* links can reduce the risk of unwanted external sharing of sensitive information:</span></span>

- [<span data-ttu-id="d0d47-198">更改网站的默认链接类型</span><span class="sxs-lookup"><span data-stu-id="d0d47-198">Change the default link type for a site</span></span>](/sharepoint/change-default-sharing-link)

<span data-ttu-id="d0d47-199">如果组织具有需要与来宾共享的敏感数据，但担心共享不当，可以将文件和文件夹的外部共享限制为指定安全组的成员。</span><span class="sxs-lookup"><span data-stu-id="d0d47-199">If your organization has sensitive data that you need to share with guests, but you're concerned about inappropriate sharing, you can limit external sharing of files and folders to the members of specified security groups.</span></span> <span data-ttu-id="d0d47-200">这样，您可以将外部共享限制为特定人员组，或要求用户在将适当的外部共享添加到安全组之前接受有关相应外部共享的培训：</span><span class="sxs-lookup"><span data-stu-id="d0d47-200">In this way, you can restrict sharing externally to a specific group of people, or require your users to take training around appropriate external sharing before adding them to the security group:</span></span>

- [<span data-ttu-id="d0d47-201">将外部共享限制为指定安全组</span><span class="sxs-lookup"><span data-stu-id="d0d47-201">Limit external sharing to specified security groups</span></span>](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

<span data-ttu-id="d0d47-202">组和Teams具有允许或拒绝来宾访问的组织级别设置。</span><span class="sxs-lookup"><span data-stu-id="d0d47-202">Groups and Teams have organization-level settings that allow or deny guest access.</span></span> <span data-ttu-id="d0d47-203">虽然可以使用 [Microsoft PowerShell](per-group-guest-access.md)限制对特定团队或组的来宾访问，但我们建议通过敏感度标签执行此操作。</span><span class="sxs-lookup"><span data-stu-id="d0d47-203">While you can [restrict guest access to specific teams or groups by using Microsoft PowerShell](per-group-guest-access.md), we recommend doing this by means of a sensitivity label.</span></span> <span data-ttu-id="d0d47-204">使用敏感度标签，你可以根据应用的标签自动允许或拒绝来宾访问：</span><span class="sxs-lookup"><span data-stu-id="d0d47-204">With sensitivity labels you can automatically allow or deny guest access based on the label applied:</span></span>

- [<span data-ttu-id="d0d47-205">使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容</span><span class="sxs-lookup"><span data-stu-id="d0d47-205">Use sensitivity labels to protect content in Microsoft Teams, Microsoft 365 groups, and SharePoint sites</span></span>](../compliance/sensitivity-labels-teams-groups-sites.md)

<span data-ttu-id="d0d47-206">在经常邀请来宾加入组和团队的环境中，请考虑设置定期安排的来宾访问评审。</span><span class="sxs-lookup"><span data-stu-id="d0d47-206">In an environment where you frequently invite guests to groups and teams, consider setting up regularly scheduled guest access reviews.</span></span> <span data-ttu-id="d0d47-207">可以提示所有者查看其组和团队中的来宾，并批准或拒绝访问。</span><span class="sxs-lookup"><span data-stu-id="d0d47-207">Owners can be prompted to review guests in their groups and teams and approve or deny access.</span></span>

- [<span data-ttu-id="d0d47-208">设置来宾访问评审</span><span class="sxs-lookup"><span data-stu-id="d0d47-208">Set up guest access reviews</span></span>](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

<span data-ttu-id="d0d47-209">Microsoft 365提供了许多不同的信息共享方法。</span><span class="sxs-lookup"><span data-stu-id="d0d47-209">Microsoft 365 offers many different methods of sharing information.</span></span> <span data-ttu-id="d0d47-210">如果你有敏感信息并且想要限制其共享方式，请查看用于限制共享的选项：</span><span class="sxs-lookup"><span data-stu-id="d0d47-210">If you have sensitive information and you want to restrict how it's shared, review the options for limiting sharing:</span></span>

- [<span data-ttu-id="d0d47-211">限制 Microsoft 365 中的共享</span><span class="sxs-lookup"><span data-stu-id="d0d47-211">Limit sharing in Microsoft 365</span></span>](./microsoft-365-limit-sharing.md)

<span data-ttu-id="d0d47-212">其他资源：</span><span class="sxs-lookup"><span data-stu-id="d0d47-212">Additional resources:</span></span>

- [<span data-ttu-id="d0d47-213">与 Microsoft 365 建立安全协作</span><span class="sxs-lookup"><span data-stu-id="d0d47-213">Set up secure collaboration with Microsoft 365</span></span>](./setup-secure-collaboration-with-teams.md)

- [<span data-ttu-id="d0d47-214">有关与未经认证用户共享文件和文件夹的最佳做法</span><span class="sxs-lookup"><span data-stu-id="d0d47-214">Best practices for sharing files and folders with unauthenticated users</span></span>](./best-practices-anonymous-sharing.md)

- [<span data-ttu-id="d0d47-215">在与组织外人员共享文件时限制意外公开信息</span><span class="sxs-lookup"><span data-stu-id="d0d47-215">Limit accidental exposure to files when sharing with people outside your organization</span></span>](./share-limit-accidental-exposure.md)

- [<span data-ttu-id="d0d47-216">创建安全的来宾共享环境</span><span class="sxs-lookup"><span data-stu-id="d0d47-216">Create a secure guest sharing environment</span></span>](./create-secure-guest-sharing-environment.md)

- [<span data-ttu-id="d0d47-217">启用 B2B 外部协作以及管理谁可邀请来宾</span><span class="sxs-lookup"><span data-stu-id="d0d47-217">Enable B2B external collaboration and manage who can invite guests</span></span>](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a><span data-ttu-id="d0d47-218">用户管理</span><span class="sxs-lookup"><span data-stu-id="d0d47-218">User management</span></span>

<span data-ttu-id="d0d47-219">随着你的组织中团队的发展，一个好的做法是定期查看团队和组成员身份。</span><span class="sxs-lookup"><span data-stu-id="d0d47-219">As groups and teams evolve in your organization, a good practice is to review team and group membership on a regular basis.</span></span> <span data-ttu-id="d0d47-220">这可能对成员身份发生变化的团队和组、包含敏感信息的团队和组或包含来宾的团队和组特别有用。</span><span class="sxs-lookup"><span data-stu-id="d0d47-220">This may be particularly useful for teams and groups with a changing membership, those that contain sensitive information, or those that include guests.</span></span> <span data-ttu-id="d0d47-221">请考虑为这些团队和组设置访问评审：</span><span class="sxs-lookup"><span data-stu-id="d0d47-221">Consider setting up access reviews for these teams and groups:</span></span>

- [<span data-ttu-id="d0d47-222">什么是 Azure AD 访问评审？</span><span class="sxs-lookup"><span data-stu-id="d0d47-222">What are Azure AD access reviews?</span></span>](/azure/active-directory/governance/access-reviews-overview)

<span data-ttu-id="d0d47-223">许多组织与其他组织或重要供应商建立了业务合作关系，他们与之深度协作。</span><span class="sxs-lookup"><span data-stu-id="d0d47-223">Many organizations have business partnerships with other organizations or key vendors with whom they collaborate in depth.</span></span> <span data-ttu-id="d0d47-224">在这些情况下，管理用户和访问资源可能充满挑战。</span><span class="sxs-lookup"><span data-stu-id="d0d47-224">User management and access to resources can be challenging to manage in these scenarios.</span></span> <span data-ttu-id="d0d47-225">请考虑自动执行一些用户管理任务，甚至将其中一些任务转换到合作伙伴组织：</span><span class="sxs-lookup"><span data-stu-id="d0d47-225">Consider automating some of the user management tasks and even transitioning some of them to your partner organization:</span></span>

- [<span data-ttu-id="d0d47-226">什么是 Azure AD 权利管理？</span><span class="sxs-lookup"><span data-stu-id="d0d47-226">What is Azure AD entitlement management?</span></span>](/azure/active-directory/governance/entitlement-management-overview)

<span data-ttu-id="d0d47-227">专用频道Teams范围对话和团队成员子集之间的文件共享。</span><span class="sxs-lookup"><span data-stu-id="d0d47-227">Private channels in Teams allow for scoped conversations and file sharing between a subset of team members.</span></span> <span data-ttu-id="d0d47-228">根据您的特定业务需求，您可能需要允许或阻止此功能。</span><span class="sxs-lookup"><span data-stu-id="d0d47-228">Depending on your specific business needs, you may want to allow or block this capability.</span></span>

- [<span data-ttu-id="d0d47-229">频道中的私人Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0d47-229">Private channels in Microsoft Teams</span></span>](/MicrosoftTeams/private-channels)

- [<span data-ttu-id="d0d47-230">管理频道中私人频道的Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="d0d47-230">Manage the life cycle of private channels in Microsoft Teams</span></span>](/MicrosoftTeams/private-channels-life-cycle-management)

<span data-ttu-id="d0d47-231">其他资源：</span><span class="sxs-lookup"><span data-stu-id="d0d47-231">Additional resources:</span></span>

- [<span data-ttu-id="d0d47-232">Azure Active Directory标识治理</span><span class="sxs-lookup"><span data-stu-id="d0d47-232">Azure Active Directory Identity Governance</span></span>](/azure/active-directory/governance)

## <a name="related-topics"></a><span data-ttu-id="d0d47-233">相关主题</span><span class="sxs-lookup"><span data-stu-id="d0d47-233">Related topics</span></span>

[<span data-ttu-id="d0d47-234">协作治理规划分步规划</span><span class="sxs-lookup"><span data-stu-id="d0d47-234">Collaboration governance planning step-by-step</span></span>](collaboration-governance-overview.md#collaboration-governance-planning-step-by-step)

[<span data-ttu-id="d0d47-235">创建协作管理计划</span><span class="sxs-lookup"><span data-stu-id="d0d47-235">Create your collaboration governance plan</span></span>](collaboration-governance-first.md)

[<span data-ttu-id="d0d47-236">Microsoft Teams 中的安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="d0d47-236">Security and compliance in Microsoft Teams</span></span>](/microsoftteams/security-compliance-overview)

[<span data-ttu-id="d0d47-237">管理共享中的SharePoint</span><span class="sxs-lookup"><span data-stu-id="d0d47-237">Manage sharing settings in SharePoint</span></span>](/sharepoint/turn-external-sharing-on-or-off)

[<span data-ttu-id="d0d47-238">在 Yammer 中创建和管理外部网络</span><span class="sxs-lookup"><span data-stu-id="d0d47-238">Create and manage an external network in Yammer</span></span>](/yammer/work-with-external-users/create-and-manage-an-external-network)

[<span data-ttu-id="d0d47-239">配置具有三层保护的 Teams</span><span class="sxs-lookup"><span data-stu-id="d0d47-239">Configure Teams with three tiers of protection</span></span>](./configure-teams-three-tiers-protection.md)