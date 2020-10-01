---
title: 管理 Microsoft 365 身份管理
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
localization_priority: Normal
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-mar2020
ms.collection:
- Ent_O365
- M365-subscription-management
search.appverid:
- MET150
- MOE150
- MED150
- BCS160
ms.assetid: 98ca5b3f-f720-4d8e-91be-fe656548a25a
description: 了解如何使用 Microsoft 365 身份管理功能。
ms.openlocfilehash: d5bcafb5b452e693bf3ff706c436a9986eeeae76
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48328485"
---
# <a name="manage-microsoft-365-identity-governance"></a>管理 Microsoft 365 身份管理

标识治理的功能就是保护、监视和审核对关键资产的访问，同时确保员工高效工作。 例如，借助标识治理，可以确保相应的用户有权访问正确的资源，并确定该访问权限是否随时间而变化。

有关详细信息，请参阅 [Azure Active Directory (AZURE AD) 的身份管理概述 ](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)。

## <a name="set-up-azure-ad-access-reviews"></a>设置 Azure AD 访问评审

Azure AD 访问审查允许您查看用户的访问权限，以确保只有合适的人继续访问。 例如：

- 当新员工加入组织时，需要确保他们有正确的访问权限以实现高效工作。
- 当该员工换到其他团队、地点或部门时，需要确保根据需要删除对先前团队、位置或部门的访问权限。
- 当该员工或来宾离开组织时，需要确保删除其访问权限。

如果组织需要接受安全审核以确定用户帐户是否拥有过多访问权限，这一点尤其重要，如果违反行业或地区法规，可能会导致罚款。

有关详细信息，请参阅 [访问审核概述](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)。

Azure AD Privileged Identity Management (PIM) 提供用于保护 Azure AD、Azure 和其他 Microsoft 云服务中的资源访问权限的其他定制控制措施。 Azure AD PIM 提供了一套全面的治理控件，以帮助保护公司的资源（如目录、Office 365 和 Azure 资源角色）的安全。 与处理其他形式的访问权限一样，组织可以使用访问评审来针对充当管理员角色的所有用户配置定期的访问权限重新认证。 Azure AD PIM 仅适用于 Microsoft 365 企业版的 E5 版本。

请参阅以下文章，配置不同类型的访问评审：

- [组和应用](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure 资源角色](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>设置 Azure AD 权限管理

Wiht Azure AD 权限管理，可以通过自动执行访问请求工作流、访问分配、查看和到期情况来管理标识和访问生命周期的规模。

你的员工需要访问各种组、应用程序和网站，以执行其作业。 管理此访问可能会非常困难，因为要求更改、添加新应用程序或用户需要其他访问权限。 当与其他组织进行协作时，您可能不知道其他组织中的哪些人需要访问您组织的资源，而外部用户将不知道您的组织使用的应用程序、组或站点。

Azure AD 权限管理可帮助您更有效地管理内部和外部用户对组、应用程序和 SharePoint 网站的访问权限。
 
有关详细信息，请参阅 [AZURE AD 权限管理的概述](https://docs.microsoft.com/azure/active-directory/governance/entitlement-management-overview)。
