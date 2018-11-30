---
title: 第 12 步：设置自动授权
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
description: 理解并配置 Azure AD 组基于组的许可。
ms.openlocfilehash: 82e4192f2ef9ba3d1d5ed7bd99a8cf603d7d4cc9
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865381"
---
# <a name="step-12-set-up-automatic-licensing"></a>第 12 步：设置自动授权

** 此步骤是可选的，适用于 Microsoft 365 企业版的 E3 和 E5 版本

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将在 Azure AD 中配置安全组，以将许可证从一组订阅自动分配到组的所有成员。这被称为*基于组的许可*。如果将某个用户帐户添加到组或从组中删除，则该组订阅的许可证将被自动分配或从该用户帐户中删除。

对于 Microsoft 365 企业版，将配置 Azure AD 安全组，以分配这两种许可证：

- Office 365 企业版 E3 或 E5
- 企业移动性 + 安全性 (EMS) E3 或 E5

使用在步骤 2 中标识的组，查找包含该组中所有用户必须同时具有 Office 365 和 EMS 许可证的帐户列表的组。请确保对所有组成员具有足够的许可证。一旦许可证用完，将无法向新用户分配许可证，直到有可用的许可证为止。

>[!Note]
>不应为包含 Azure 企业到企业 (B2B) 帐户的组配置“基于组的许可”**。
>

有关更多信息，请参阅 [Azure Active Directory 中基于组的许可基础知识](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-whatis-azure-portal)。

请参阅[为 Azure 安全组配置基于组的许可的步骤](https://docs.microsoft.com/azure/active-directory/active-directory-licensing-group-assignment-azure-portal)。

此步骤结果是：

- 已标识哪些安全组适用于基于组的许可。
- 已为基于组的许可配置了这些组。

|||
|:-------|:-----|
|![Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon-small.png)| [测试实验室指南：自动化许可和组成员身份](automate-licenses-group-membership-microsoft-365-test-environment.md) |
|||

作为临时检查点，请查看对应于此步骤的[退出条件](identity-exit-criteria.md#crit-identity-group-license)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step13.png)| [监控租户和登录活动](identity-azure-ad-access-usage-reporting.md) |

