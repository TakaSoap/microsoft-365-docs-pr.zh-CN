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
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>在 Microsoft 365 组、团队和 SharePoint 中管理访问权限

有很多控件使您能够控制用户访问组、团队和 SharePoint 中的资源的方式。 查看这些选项并考虑它们如何映射到您的业务需求、数据的敏感性以及用户需要与之协作的人员的范围。

下表提供了对 Microsoft 365 中提供的访问控制的快速参考。 以下各节提供了详细信息。

|类别|说明|参考|
|:-------|:----------|:--------|
|成员身份|||
||专用团队发现|[在 Microsoft 团队中管理专用团队的发现](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)|
||基于规则的动态组成员身份|[在 Azure Active Directory 中创建或更新动态组](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)|
||控制谁可以共享文件、文件夹和网站。|[设置和管理访问请求](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|条件访问|||
||多因素身份验证|[Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)|
||根据组、团队或站点敏感度控制设备访问。|[使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||限制非托管设备的网站访问权限。|[控制来自非托管设备的 SharePoint 访问](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)|
||基于位置控制网站访问|[根据网络位置控制对 SharePoint 和 OneDrive 数据的访问](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)|
|来宾访问权限|||
||允许或阻止来自指定域的 SharePoint 共享。|[限制 SharePoint 和 OneDrive 内容的共享（按域）](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)|
||允许或阻止来自指定域的团队或组成员身份。|[允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)|
||阻止匿名共享。|[关闭“任何人”链接](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)|
||控制匿名访问链接的权限。|[为任何人的链接设置链接权限](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)|
||控制匿名共享链接的过期。|[设置“任何人”链接的到期日期](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)|
||控制默认情况下显示给用户的共享链接的类型。|[更改网站的默认链接类型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)|
||将外部共享限制为特定人员。|[将外部共享限制为指定的安全组](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||根据信息敏感度控制对组、团队或网站的来宾访问。|[使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)|
||请关闭共享选项。|[限制 Microsoft 365 中的共享](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)|
|用户管理|||
||定期查看团队和组成员身份。|[什么是 Azure AD 访问审查？](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)|
||自动化对组和团队的访问管理。|[什么是 Azure AD 权限管理？](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)|
||允许或阻止人员在团队中创建专用频道。|[在 Microsoft 团队中管理专用频道的生命周期](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>成员身份

团队和组的成员身份由所有者控制。 成员可以邀请其他人，但会将邀请发送给所有者进行审批。 虽然组织中的任何人都可以发现公共团队和组，但您可以控制是否可发现专用团队和组：

- [在 Microsoft 团队中管理专用团队的发现](https://docs.microsoft.com/microsoftteams/manage-discovery-of-private-teams)

您可以根据某些条件（如部门）动态管理组或团队的成员资格。 在这种情况下，成员和所有者无法邀请人员加入团队。

- [在 Azure Active Directory 中创建或更新动态组](https://docs.microsoft.com/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint 网站能够将所有者、成员和访问者与组或团队成员身份分开。 根据您的要求，您可能希望限制谁可以邀请人员加入网站。 此外，根据给定网站中信息的敏感度，您可能希望限制可以共享文件和文件夹的用户。 这些限制由团队、组或网站所有者配置：

- [设置和管理访问请求](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>条件访问

使用 Microsoft 365，您可以对组织内部和外部的人员要求多重身份验证。 在提示用户第二种身份验证因素的情况下，有许多选项。 强烈建议您为您的组织部署多因素身份验证：

- [Azure AD Multi-Factor Authentication](https://docs.microsoft.com/azure/active-directory/authentication/concept-mfa-howitworks)

如果您的某些组和团队中包含敏感信息，则可以根据组或团队的敏感度标签强制实施设备管理策略。 您可以完全阻止来自非托管设备的访问，或允许仅限 web 的访问权限：

- [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

在 SharePoint 中，可以限制对指定网络位置中的网站的访问。

- [根据网络位置控制对 SharePoint 和 OneDrive 数据的访问](https://docs.microsoft.com/sharepoint/control-access-based-on-network-location)


其他资源：

- [规划条件访问部署](https://docs.microsoft.com/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune 概述](https://docs.microsoft.com/mem/intune/fundamentals/what-is-intune)

- [控制来自非托管设备的 SharePoint 访问](https://docs.microsoft.com/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>来宾访问权限

您可以根据其电子邮件地址的域来限制来宾。 SharePoint 提供组织范围和特定于站点的域限制设置。 组和团队使用 Azure AD 中的域允许和拒绝列表。 请务必配置这两个设置以避免不必要的共享，并确保用户体验一致：

- [限制 SharePoint 和 OneDrive 内容的共享（按域）](https://docs.microsoft.com/sharepoint/restricted-domains-sharing)

- [允许或阻止来自特定组织的 B2B 用户的邀请](https://docs.microsoft.com/azure/active-directory/b2b/allow-deny-list)

Microsoft 365 允许使用共享链接的 *任何人* 匿名共享文件和文件夹。 *任何人都* 可以转发任何链接，并且具有链接的任何人都可以访问共享项目。 根据数据的敏感度，考虑如何使用 *任何人* 的链接，包括将其完全关闭、将链接权限限制为只读或为其设置过期时间：

- [关闭“任何人”链接](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#turn-off-anyone-links)

- [为任何人的链接设置链接权限](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-link-permissions)

- [设置“任何人”链接的到期日期](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing#set-an-expiration-date-for-anyone-links)

共享文件或文件夹时，用户有几种链接类型可供选择。 若要降低意外共享的风险，可以在用户共享时更改提供给用户的默认链接类型。 例如，在 " *任何人* " 链接中更改默认值（允许对 *组织中的用户* 进行匿名访问）可能会降低敏感信息的不需要外部共享的风险：

- [更改网站的默认链接类型](https://docs.microsoft.com/sharepoint/change-default-sharing-link)

如果你的组织具有需要与来宾共享的敏感数据，但你担心不恰当的共享，则可以将文件和文件夹的外部共享限制为指定安全组的成员。 通过这种方式，您可以限制外部与特定人员组的共享，或要求您的用户在将其添加到安全组之前先针对适当的外部共享进行培训：

- [将外部共享限制为指定的安全组](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

组和团队具有允许或拒绝来宾访问的组织级别设置。 虽然您可以 [使用 Microsoft PowerShell 限制对特定团队或组的来宾访问](per-group-guest-access.md)，但我们建议通过灵敏度标签执行此操作。 使用敏感度标签，可以根据应用的标签自动允许或拒绝来宾访问：

- [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](https://docs.microsoft.com/microsoft-365/compliance/sensitivity-labels-teams-groups-sites)

Microsoft 365 提供了多种不同的信息共享方法。 如果您有敏感信息，并且希望限制其共享方式，请查看限制共享的选项：

- [限制 Microsoft 365 中的共享](https://docs.microsoft.com/microsoft-365/solutions/microsoft-365-limit-sharing)

其他资源：

- [与 Microsoft 365 建立安全协作](https://docs.microsoft.com/microsoft-365/solutions/setup-secure-collaboration-with-teams)

- [有关与未经认证用户共享文件和文件夹的最佳做法](https://docs.microsoft.com/microsoft-365/solutions/best-practices-anonymous-sharing)

- [在与组织外人员共享文件时限制意外公开信息](https://docs.microsoft.com/microsoft-365/solutions/share-limit-accidental-exposure)

- [创建安全的来宾共享环境](https://docs.microsoft.com/microsoft-365/solutions/create-secure-guest-sharing-environment)

- [启用 B2B 外部协作并管理可邀请来宾的人士](https://docs.microsoft.com/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>用户管理

随着组织中的组和团队的发展，一种很好的做法是定期查看团队和组成员资格。 对于具有不断变化的成员身份、包含敏感信息的团队和组，或者包含来宾的团队和组，这可能尤其有用。 考虑为这些团队和组设置访问评审：

- [什么是 Azure AD 访问审查？](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)

许多组织与其他组织或主要供应商的业务合作关系，他们的深度与他们进行协作。 在这些方案中管理用户管理和资源访问可能是很困难的。 请考虑自动执行某些用户管理任务，甚至将其中一些用户转换为合作伙伴组织：

- [什么是 Azure AD 权限管理？](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)

团队中的专用通道允许范围内的对话和团队成员的子集之间共享文件。 根据您的特定业务需求，您可能希望允许或阻止此功能。

- [Microsoft 团队中的专用通道](https://docs.microsoft.com/MicrosoftTeams/private-channels)

- [在 Microsoft 团队中管理专用频道的生命周期](https://docs.microsoft.com/MicrosoftTeams/private-channels-life-cycle-management)

其他资源：

- [Azure Active Directory 标识管理](https://docs.microsoft.com/azure/active-directory/governance)

## <a name="related-topics"></a>相关主题

[Microsoft Teams 中的安全性和合规性](https://docs.microsoft.com/microsoftteams/security-compliance-overview)

[在 SharePoint 中管理共享设置](https://docs.microsoft.com/sharepoint/turn-external-sharing-on-or-off)

[在 Yammer 中创建和管理外部网络](https://docs.microsoft.com/yammer/work-with-external-users/create-and-manage-an-external-network)

[配置具有三层保护的 Teams](https://docs.microsoft.com/microsoft-365/solutions/configure-teams-three-tiers-protection)
