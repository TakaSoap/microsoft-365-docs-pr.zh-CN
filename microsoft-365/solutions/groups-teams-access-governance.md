---
title: 管理 Microsoft 365 组、Teams 和 SharePoint
ms.reviewer: ''
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: Admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.localizationpriority: medium
ms.collection:
- M365-collaboration
- m365solution-collabgovernance
ms.custom:
- M365solutions
f1.keywords: NOCSH
recommendations: false
description: 了解管理组、Microsoft 365和Teams中的SharePoint。
ms.openlocfilehash: e01326093476f341c6c4c75448efbdf8c745779f
ms.sourcegitcommit: c2b5ce3150ae998e18a51bad23277cedad1f06c6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/17/2021
ms.locfileid: "61064327"
---
# <a name="governing-access-in-microsoft-365-groups-teams-and-sharepoint"></a>管理 Microsoft 365 组、Teams 和 SharePoint

有许多控件使您能够控制用户如何访问组、团队和团队中的SharePoint。 查看这些选项，并考虑它们如何映射到业务需求、数据的敏感度以及用户需要协作的用户范围。

下表提供了一个快速参考，该参考可用于Microsoft 365。 以下各节提供了进一步的信息。

|类别|说明|参考|
|:-------|:----------|:--------|
|成员身份|||
||发现私人团队|[管理专用团队在 Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)|
||基于规则的动态组成员身份|[在动态组中创建或更新Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)|
||控制谁可以共享文件、文件夹和网站。|[设置和管理访问请求](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)|
|条件访问|||
||多重身份验证|[Azure AD多重身份验证](/azure/active-directory/authentication/concept-mfa-howitworks)|
||根据组、团队或网站敏感度控制设备访问。|[使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)|
||限制非托管设备的站点访问。|[控制SharePoint非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)|
||根据位置控制网站访问|[根据网络位置控制对 SharePoint 和 OneDrive 数据的访问](/sharepoint/control-access-based-on-network-location)|
|来宾访问权限|||
||允许或阻止SharePoint域中进行共享。|[按域限制 SharePoint 和 OneDrive 内容的共享](/sharepoint/restricted-domains-sharing)|
||允许或阻止来自指定域的团队或组成员身份。|[允许或阻止特定组织向 B2B 用户发出邀请](/azure/active-directory/b2b/allow-deny-list)。|
||阻止匿名共享。|[关闭“任何人”链接](./share-limit-accidental-exposure.md#turn-off-anyone-links)|
||控制匿名访问链接的权限。|[设置"任何人"链接的链接权限](./best-practices-anonymous-sharing.md#set-link-permissions)|
||控制匿名共享链接的过期时间。|[设置“任何人”链接的到期日期](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)|
||控制默认向用户显示的共享链接的类型。|[更改网站的默认链接类型](/sharepoint/change-default-sharing-link)|
||将外部共享限制为特定人员。|[将外部共享限制为指定安全组](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)|
||根据信息敏感度控制对组、团队或网站的来宾访问。|[使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)|
||关闭共享选项。|[限制 Microsoft 365 中的共享](./microsoft-365-limit-sharing.md)|
|用户管理|||
||定期查看团队和组成员身份。|[什么是Azure AD评审？](/azure/active-directory/governance/access-reviews-overview)|
||自动管理对组和团队的访问。|[什么是Azure AD管理？](/azure/active-directory/governance/entitlement-management-overview)|
||允许或阻止用户创建私人频道Teams。|[管理频道中私人频道的Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)|

## <a name="membership"></a>成员身份

团队和组的成员身份由所有者控制。 成员可以邀请其他人，但邀请将发送给所有者进行审批。 尽管组织中任何人都可以发现公共团队和组，但你可以控制私人团队和组是否可发现：

- [管理专用团队在 Microsoft Teams](/microsoftteams/manage-discovery-of-private-teams)

你可以根据某些条件（如部门）动态管理组或团队的成员身份。 在这种情况下，成员和所有者无法邀请人员加入团队。 动态组使用在 Azure Active Directory定义的元数据来控制组的成员。 请确保你使用的元数据已完成且是最新的，因为不正确的元数据可能会导致用户被排除在组外或添加不正确的用户。

- [在动态组中创建或更新Azure Active Directory](/azure/active-directory/users-groups-roles/groups-create-rule)

SharePoint网站提供除组或团队成员身份外添加所有者、成员和访问者的能力。 根据您的要求，您可能需要限制可以邀请人员访问网站的人。 此外，根据给定网站中信息的敏感度，你可能希望限制可以共享文件和文件夹的人。 这些限制由团队、组或网站所有者配置：

- [设置和管理访问请求](https://support.microsoft.com/office/94b26e0b-2822-49d4-929a-8455698654b3)


## <a name="conditional-access"></a>条件访问

使用Microsoft 365，您可以要求对组织内外的用户进行多重身份验证。 当系统提示用户进行第二种身份验证时，有许多选项可供选择。 强烈建议您为组织部署多重身份验证：

- [Azure AD多重身份验证](/azure/active-directory/authentication/concept-mfa-howitworks)

如果你在某些组和团队中具有敏感信息，可以基于组或团队的敏感度标签强制执行设备管理策略。 你可以完全阻止来自非托管设备的访问，或允许受限的仅 Web 访问：

- [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)

在SharePoint中，您可以限制从指定的网络位置访问站点。

- [根据网络位置控制对 SharePoint 和 OneDrive 数据的访问](/sharepoint/control-access-based-on-network-location)


其他资源：

- [规划条件访问部署](/azure/active-directory/conditional-access/plan-conditional-access)

- [Microsoft Intune 概述](/mem/intune/fundamentals/what-is-intune)

- [控制SharePoint非托管设备的访问](/sharepoint/control-access-from-unmanaged-devices)


## <a name="guest-access"></a>来宾访问权限

你可以根据来宾的电子邮件地址的域来限制来宾。 SharePoint组织范围的域限制设置和特定于站点的域限制设置。 组和Teams使用域中的域允许列表或阻止Azure AD。 请确保配置这两个设置以避免不必要的共享，并确保一致的用户体验：

- [按域限制 SharePoint 和 OneDrive 内容的共享](/sharepoint/restricted-domains-sharing)

- [允许或阻止特定组织向 B2B 用户发出邀请](/azure/active-directory/b2b/allow-deny-list)。

Microsoft 365任何人共享链接允许匿名 *共享文件和文件夹*。 *可以* 转发"任何人"链接，具有该链接的任何人都可以访问共享项目。 根据数据的敏感度，考虑管理"任何人"链接的使用方式，包括完全关闭链接、将链接权限限制为只读或为链接设置过期时间：

- [关闭“任何人”链接](./share-limit-accidental-exposure.md#turn-off-anyone-links)

- [设置"任何人"链接的链接权限](./best-practices-anonymous-sharing.md#set-link-permissions)

- [设置“任何人”链接的到期日期](./best-practices-anonymous-sharing.md#set-an-expiration-date-for-anyone-links)

共享文件或文件夹时，用户可以从多个链接类型中选择。 若要降低意外不恰当的共享风险，可以更改在用户共享时显示的默认链接类型。 例如，将默认值从"任何人"链接（允许匿名访问）更改到"组织人员"链接可降低不需要的外部共享敏感信息的风险：

- [更改网站的默认链接类型](/sharepoint/change-default-sharing-link)

如果组织具有需要与来宾共享的敏感数据，但担心共享不当，可以将文件和文件夹的外部共享限制为指定安全组的成员。 这样，您可以将外部共享限制为特定组人员，或要求用户在将适当的外部共享添加到安全组之前接受有关相应外部共享的培训：

- [将外部共享限制为指定安全组](./share-limit-accidental-exposure.md#limit-sharing-of-files-folders-and-sites-with-people-outside-your-organization-to-specified-security-groups)

组和Teams具有允许或拒绝来宾访问的组织级别设置。 虽然可以使用 [Microsoft PowerShell](per-group-guest-access.md)限制来宾访问特定团队或组，但我们建议通过敏感度标签执行此操作。 使用敏感度标签，你可以根据应用的标签自动允许或拒绝来宾访问：

- [使用敏感度标签保护 Microsoft Teams、Microsoft 365 组和 SharePoint 网站中的内容](../compliance/sensitivity-labels-teams-groups-sites.md)

在经常邀请来宾加入组和团队的环境中，请考虑设置定期安排的来宾访问评审。 可以提示所有者查看其组和团队中的来宾，并批准或拒绝访问。

- [设置来宾访问评审](/microsoft-365/solutions/create-secure-guest-sharing-environment#set-up-guest-access-reviews)

Microsoft 365提供了许多不同的信息共享方法。 如果你有敏感信息并且想要限制其共享方式，请查看用于限制共享的选项：

- [限制 Microsoft 365 中的共享](./microsoft-365-limit-sharing.md)

其他资源：

- [与 Microsoft 365 建立安全协作](./setup-secure-collaboration-with-teams.md)

- [有关与未经认证用户共享文件和文件夹的最佳做法](./best-practices-anonymous-sharing.md)

- [在与组织外人员共享文件时限制意外公开信息](./share-limit-accidental-exposure.md)

- [创建安全的来宾共享环境](./create-secure-guest-sharing-environment.md)

- [启用 B2B 外部协作以及管理谁可邀请来宾](/azure/active-directory/b2b/delegate-invitations)

## <a name="user-management"></a>用户管理

随着你的组织中团队的发展，一个好的做法是定期查看团队和组成员身份。 这可能对成员身份发生变化的团队和组、包含敏感信息的团队和组或包含来宾的团队和组特别有用。 请考虑为这些团队和组设置访问评审：

- [什么是Azure AD评审？](/azure/active-directory/governance/access-reviews-overview)

许多组织与其他组织或重要供应商建立了业务合作关系，他们与之深度协作。 在这些情况下，管理用户和访问资源可能会面临挑战。 请考虑自动执行一些用户管理任务，甚至将其中一些任务转换到合作伙伴组织：

- [什么是Azure AD权限管理？](/azure/active-directory/governance/entitlement-management-overview)

专用频道Teams范围对话和团队成员子集之间的文件共享。 根据您的特定业务需求，您可能需要允许或阻止此功能。

- [Microsoft Teams 中的专用频道](/MicrosoftTeams/private-channels)

- [管理频道中私人频道的Microsoft Teams](/MicrosoftTeams/private-channels-life-cycle-management)

其他资源：

- [Azure Active Directory身份管理](/azure/active-directory/governance)

## <a name="related-topics"></a>相关主题

[协作治理规划建议](collaboration-governance-overview.md#collaboration-governance-planning-recommendations)

[创建协作管理计划](collaboration-governance-first.md)

[Microsoft Teams 中的安全性和合规性](/microsoftteams/security-compliance-overview)

[管理共享中的SharePoint](/sharepoint/turn-external-sharing-on-or-off)

[在 Yammer 中创建和管理外部网络](/yammer/work-with-external-users/create-and-manage-an-external-network)

[配置具有三层保护的 Teams](./configure-teams-three-tiers-protection.md)