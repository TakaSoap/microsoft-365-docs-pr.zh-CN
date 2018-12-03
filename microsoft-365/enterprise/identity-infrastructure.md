---
title: 阶段 2：身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 部署 Microsoft 365 企业版的身份基础结构的步骤。
ms.openlocfilehash: 7b5d62f5c09a1ea6d46449b113bff59dbf07ebad
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865804"
---
# <a name="phase-2-identity"></a>阶段 2：身份

![](./media/deploy-foundation-infrastructure/identity_icon.png)

在 Microsoft 365 企业版中，精心计划和执行的身份基础结构将有助于实现更强的安全性，并仅允许通过身份验证的用户和设备访问生产力工作负载和数据。

>[!Note]
>如果已部署身份基础结构，请参阅[身份退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必需条件和可选条件。
>

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>计划和部署 Microsoft 365 企业版身份基础结构 

使用以下步骤在云中计划和部署新身份基础结构。此外，还可用这些步骤调整现有本地或混合身份基础结构，以与 Microsoft 365 企业版一起使用。 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [计划用户和组](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [保护全局管理员帐户](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [设置按需全局管理员](identity-privileged-identity-management.md) |
|![](./media/stepnumbers/Step4.png)| [简化密码重置](identity-password-reset.md) |
|![](./media/stepnumbers/Step5.png)| [设置多重身份验证](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step6.png)| [防止凭据泄露](identity-azure-ad-identity-protection.md) |
|![](./media/stepnumbers/Step7.png)| [同步目录](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step8.png)| [监控同步运行状况](identity-azure-ad-connect-health.md) |
|![](./media/stepnumbers/Step9.png)| [简化密码更新](identity-password-writeback.md) |
|![](./media/stepnumbers/Step10.png)| [简化用户登录](identity-single-sign-on.md) |
|![](./media/stepnumbers/Step11.png)| [自定义 Office 365 登录页](identity-customize-office-365-sign-in.md) |
|![](./media/stepnumbers/Step12.png)| [设置自动许可](identity-group-based-licensing.md) |
|![](./media/stepnumbers/Step13.png)| [监控租户和登录活动](identity-azure-ad-access-usage-reporting.md) |
|![](./media/stepnumbers/Step14.png)| [允许用户创建和管理自己的组](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step15.png)| [设置动态组成员身份](identity-automatic-group-membership.md) |

在完成这些步骤后，请转到这一阶段的[退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必备条件和可选条件。

## <a name="identity-and-device-access-recommendations"></a>标识和设备访问建议

Microsoft 提供了一组有关[标识和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。对于标识，请使用下列文章中的建议和设置以及此阶段中的步骤：

- [先决条件](identity-access-prerequisites.md)
- [常见标识和设备访问策略](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何使用 Microsoft 365 企业版

了解 Microsoft 的 IT 专家如何使用以下这些资源来计划和部署 Microsoft 365 企业版的标识功能：

- [管理 Microsoft 用户标识和安全访问](https://www.microsoft.com/itshowcase/Article/Content/931/Managing-user-identities-and-secure-access-at-Microsoft)
- [使用 Azure AD Privileged Identity Management 进行提升的访问](https://www.microsoft.com/itshowcase/Article/Content/887/Using-Azure-AD-Privileged-Identity-Management-for-elevated-access)

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 如何使用 Microsoft 365 企业版

了解 Contoso Corporation（虚构但具代表性的跨国企业）如何为 Microsoft 365 云服务[部署混合身份基础结构](contoso-identity.md)。

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [计划用户和组](identity-plan-users-groups.md) |
