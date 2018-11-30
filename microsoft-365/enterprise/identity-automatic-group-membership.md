---
title: 第 15 步：设置动态组成员资格
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
description: 了解并根据帐户属性配置自动组成员身份。
ms.openlocfilehash: 8619179bc4e3ce17d9201cafb88e1b1c48fc7f4f
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865915"
---
# <a name="step-15-set-up-dynamic-group-membership"></a>第 15 步：设置动态组成员资格

** 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将创建一系列规则来为 Azure AD 组的成员自动添加或删除用户帐户。这就是*动态组成员身份*。这些规则将基于用户帐户属性，如部门或国家/地区。

下面是如何应用这些规则：

- 如果新用户帐户符合组的所有规则，则其会变为成员。
- 如果用户帐户不是组成员，但其属性更改，以便其匹配组的所有规则，则其会变为该组的成员。
- 如果用户帐户不匹配组的所有规则，则其不会添加到组。
- 如果用户帐户是组成员，但其属性更改，以便其不再匹配组的所有规则，则会从该组成员中将其删除。

若要使用动态成员身份，则必须先确定有一组常用的用户帐户属性。例如，销售部门的所有成员都应在“销售 Azure AD”组中，根据用户帐户属性部门设置为“Sales”。

请参阅[为动态 Azure AD 组创建并配置规则的说明](https://docs.microsoft.com/azure/active-directory/active-directory-groups-dynamic-membership-azure-portal)。

此步骤结果是：

- 可以为动态成员身份配置的 Azure AD 组集
- 每个动态组的规则集

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：自动化许可和组成员身份](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-dyn-groups)。

## <a name="next-step"></a>后续步骤

[身份基础结构退出条件](identity-exit-criteria.md)
