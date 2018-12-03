---
title: 第 3 步：设置按需全局管理员
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 03/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解并配置 Azure AD Privileged Identity Management。
ms.openlocfilehash: 659beff3c31d17afa03d3ecf754c581f3ca2e230
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865590"
---
# <a name="step-3-set-up-on-demand-global-administrators"></a>第 3 步：设置按需全局管理员

*此步骤是可选的，仅适用于 Microsoft 365 企业版的 E5 版本*

![](./media/deploy-foundation-infrastructure/identity_icon-small.png)

在此步骤中，将安装 Azure AD Privileged Identity Management (PIM)，以减少全局管理员帐户易受恶意用户攻击的时间。PIM 将在必要时按需、实时分配全局管理员角色。  

全局管理员帐户成为符合条件的管理员，而不再是永久管理员。有人需要全局管理员角色时，才会激活它。然后完成激活过程，以将全局管理员角色在特定时间内添加到全局管理员帐户。当时间到期后，PIM 会从全局管理员帐户删除全局管理员角色。

可从 Microsoft 365 Enterprise E5 包含的 Azure Active Directory Premium P2 中获取 PIM。或者可以为全局管理员帐户单独购买 Azure Active Directory Premium P2 许可证。

若要为 Azure AD 租户和全局管理员帐户启用 Azure PIM，请参阅 [PIM 配置步骤](https://docs.microsoft.com/azure/active-directory/active-directory-privileged-identity-management-configure)。

可参阅[确保 Azure AD 中混合部署和云部署的特权访问安全性](https://docs.microsoft.com/azure/active-directory/admin-roles-best-practices)来制定全面的路线图，以确保特权访问能够防止网络攻击者。

作为临时检查点，可查看这一步的[退出条件](identity-exit-criteria.md#crit-identity-pim)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step4.png)| [简化密码重置](identity-password-reset.md) |

