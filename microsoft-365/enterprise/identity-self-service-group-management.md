---
title: 步骤 14：允许用户创建和管理自己的组
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/01/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD 自助服务组管理。
ms.openlocfilehash: d46e82fd72b8eef896a223229a2cc3d25ae56c76
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865728"
---
# <a name="step-14-allow-users-to-create-and-manage-their-own-groups"></a>步骤 14：允许用户创建和管理自己的组

** 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将标识可由组所有者而不是 IT 管理员来管理的 Azure Active Directory (AD) 组。此功能称为*自助服务组管理*，允许未分配管理角色的组所有者创建和管理安全组。 

用户可以请求安全组中的成员身份，该请求将转到组所有者而不是 IT 管理员。这可将组成员身份的日常控制委托给团队、项目或业务所有者，他们了解组的商业用途，可更好地管理其成员身份。

>[!Note]
>自助服务组管理仅适用于 Azure AD 安全和 Office 365 组。不适用于启用邮件的组、通讯组列表或已从本地 Windows Server Active Directory (AD) 同步的任何组。
>

有关详细信息，请参阅[配置 Azure AD 组进行自助服务管理的说明](https://docs.microsoft.com/azure/active-directory/active-directory-accessmanagement-self-service-group-management)。

作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-self-service-groups)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step15.png)| [设置动态组成员身份](identity-automatic-group-membership.md) |
