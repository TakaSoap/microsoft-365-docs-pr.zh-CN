---
title: 管理Microsoft 365身份管理
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
audience: Admin
ms.topic: overview
ms.prod: office-online-server
ms.localizationpriority: medium
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
description: 了解如何使用标识Microsoft 365功能。
ms.openlocfilehash: 35b2092412ddbeacd5d6962e110de1931b2d0f4b
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150746"
---
# <a name="manage-microsoft-365-identity-governance"></a>管理Microsoft 365身份管理

标识治理的功能就是保护、监视和审核对关键资产的访问，同时确保员工高效工作。 例如，借助标识治理，可以确保相应的用户有权访问正确的资源，并确定该访问权限是否随时间而变化。

有关详细信息，请参阅 Azure [AD Azure Active Directory (的标识) 。 ](/azure/active-directory/governance/identity-governance-overview)

## <a name="set-up-azure-ad-access-reviews"></a>设置 Azure AD 访问评审

Azure AD 访问评审允许你查看用户的访问权限，以确保只有合适的人员才能继续访问。 例如：

- 当新员工加入组织时，需要确保他们有正确的访问权限以实现高效工作。
- 当该员工换到其他团队、地点或部门时，需要确保根据需要删除对先前团队、位置或部门的访问权限。
- 当该员工或来宾离开组织时，需要确保删除其访问权限。

如果组织需要接受安全审核以确定用户帐户是否拥有过多访问权限，这一点尤其重要，如果违反行业或地区法规，可能会导致罚款。

有关详细信息，请参阅 [访问评审概述](/azure/active-directory/governance/access-reviews-overview)。

请参阅以下文章，配置不同类型的访问评审：

- [组和应用](/azure/active-directory/governance/create-access-review)
- [Azure AD 角色](/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure 资源角色](/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

## <a name="set-up-azure-ad-entitlement-management"></a>设置 Azure AD 权利管理

Wiht Azure AD 权利管理，可以通过自动执行访问请求工作流、访问分配、审阅和过期来大规模管理标识和访问生命周期。

员工需要访问各种组、应用程序和网站才能执行他们的工作。 管理此访问可能充满挑战，因为要求发生变化、添加了新应用程序，或者用户需要其他访问权限。 与其他组织协作时，您可能不知道其他组织中的哪些人员需要访问组织的资源，外部用户将不知道组织正在使用哪些应用程序、组或网站。

Azure AD 权利管理可帮助你更高效地管理对内部和外部SharePoint组、应用程序和网站的访问权限。
 
有关详细信息，请参阅 Azure [AD 权利管理概述](/azure/active-directory/governance/entitlement-management-overview)。