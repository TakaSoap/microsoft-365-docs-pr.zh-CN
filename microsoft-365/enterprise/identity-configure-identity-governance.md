---
title: 步骤 7：配置标识治理
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/20/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 租户的标识治理。
ms.openlocfilehash: 5b7b1c91735611046133a0247ae028ed090106fd
ms.sourcegitcommit: 6c8edbc54b193e964cf93aec48c51cb79231f1d9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/05/2020
ms.locfileid: "42543991"
---
# <a name="step-6-configure-identity-governance"></a>步骤 6：配置标识治理

![第 2 阶段 - 标识](../media/deploy-foundation-infrastructure/identity_icon-small.png)

标识治理的功能就是保护、监视和审核对关键资产的访问，同时确保员工高效工作。 例如，借助标识治理，可以确保相应的用户有权访问正确的资源，并确定该访问权限是否随时间而变化。

有关 Azure Active Directory (Azure AD) 标识治理的更多信息，请参阅[本文](https://docs.microsoft.com/azure/active-directory/governance/identity-governance-overview)。


*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*


<a name="identity-access-reviews"></a>
## <a name="set-up-azure-ad-access-reviews"></a>设置 Azure AD 访问评审

*这是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*

在此步骤中，将设置 Azure AD 访问评审，以便查看用户的访问权限，以确保只有合适的人员才能继续访问。 例如：

- 当新员工加入组织时，需要确保他们有正确的访问权限以实现高效工作。
- 当该员工换到其他团队、地点或部门时，需要确保根据需要删除对先前团队、位置或部门的访问权限。
- 当该员工或来宾离开组织时，需要确保删除其访问权限。

如果组织需要接受安全审核以确定用户帐户是否拥有过多访问权限，这一点尤其重要，如果违反行业或地区法规，可能会导致罚款。

有关 Azure AD 访问评审的更多信息，请参阅[本文](https://docs.microsoft.com/azure/active-directory/governance/access-reviews-overview)。

Azure AD Privileged Identity Management (PIM) 提供用于保护 Azure AD、Azure 和其他 Microsoft 云服务中的资源访问权限的其他定制控制措施。 Azure AD PIM 提供了一套全面的治理控件，以帮助保护公司的资源（如目录、Office 365 和 Azure 资源角色）的安全。 与处理其他形式的访问权限一样，组织可以使用访问评审来针对充当管理员角色的所有用户配置定期的访问权限重新认证。 Azure AD PIM 仅适用于 Microsoft 365 企业版的 E5 版本。

请参阅以下文章，配置不同类型的访问评审：

- [组和应用](https://docs.microsoft.com/azure/active-directory/governance/create-access-review)
- [Azure AD 角色](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-how-to-start-security-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)
- [Azure 资源角色](https://docs.microsoft.com/azure/active-directory/privileged-identity-management/pim-resource-roles-start-access-review?toc=%2fazure%2factive-directory%2fgovernance%2ftoc.json)

作为临时检查点，可查看这部分的[退出条件](identity-exit-criteria.md#crit-identity-access-reviews)。

## <a name="next-step"></a>后续步骤

[身份基础结构退出条件](identity-exit-criteria.md)

