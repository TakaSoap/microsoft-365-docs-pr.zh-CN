---
title: 阶段 2：身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/06/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom: ''
description: 部署 Microsoft 365 企业版的身份基础结构的步骤。
ms.openlocfilehash: 07f95a249912826b80e0654cac4063b3d5763267
ms.sourcegitcommit: 91ff1d4339f0f043c2b43997d87d84677c79e279
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/14/2019
ms.locfileid: "36981944"
---
# <a name="phase-2-identity"></a>阶段 2：身份

![](./media/deploy-foundation-infrastructure/identity_icon.png)

在 Microsoft 365 企业版中，精心计划和执行的身份基础结构将有助于实现更强的安全性，并仅允许通过身份验证的用户和设备访问生产力工作负载和数据。

观看此视频，以获取 Microsoft 365 企业版身份模型和身份验证的概述。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE2Pjwu]

>[!Note]
>如果已部署身份基础结构，请参阅[身份退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版的必需条件和可选条件。
>

有关每个 Microsoft 365 企业版计划的身份功能、Azure Active Directory (Azure AD) 的角色、本地和基于云的组件，以及最常见的身份验证配置，请参阅[身份基础结构海报](media/identity-infrastructure/M365E-ID-Infra.pdf)。

[![身份基础结构海报](./media/identity-infrastructure/m365e-identity-arch-poster.png)](media/identity-infrastructure/M365E-ID-Infra.pdf)

此海报包含两页内容，可借助它快速实施 Microsoft 365 企业版的身份概念和配置。

还可以[下载此海报](https://github.com/MicrosoftDocs/microsoft-365-docs/raw/public/microsoft-365/enterprise/media/identity-infrastructure/M365E-ID-Infra.pdf)并按 letter、legal 或 tabloid (11 x 17) 格式打印。

## <a name="plan-and-deploy-your-microsoft-365-enterprise-identity-infrastructure"></a>计划和部署 Microsoft 365 企业版身份基础结构 

使用以下步骤在云中计划和部署新身份基础结构。此外，还可用这些步骤调整现有本地或混合身份基础结构，以与 Microsoft 365 企业版一起使用。 

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [计划用户和组](identity-plan-users-groups.md) |
|![](./media/stepnumbers/Step2.png)| [保护你的特权标识](identity-designate-protect-admin-accounts.md) |
|![](./media/stepnumbers/Step3.png)| [配置混合标识](identity-azure-ad-connect.md) |
|![](./media/stepnumbers/Step4.png)| [配置安全的用户身份验证](identity-multi-factor-authentication.md) |
|![](./media/stepnumbers/Step5.png)| [简化用户访问权限](identity-password-reset.md) |
|![](./media/stepnumbers/Step6.png)| [使用组实现更轻松地管理](identity-self-service-group-management.md) |
|![](./media/stepnumbers/Step7.png)| [配置标识治理](identity-governance.md) |

在完成这些步骤后，请转到这一阶段的[退出条件](identity-exit-criteria.md)，以确保满足 Microsoft 365 企业版标识的必备条件和可选条件。

## <a name="identity-and-device-access-recommendations"></a>标识和设备访问建议

Microsoft 提供了一组有关[标识和设备访问](microsoft-365-policies-configurations.md)的建议，以确保全体员工安全且高效地工作。对于标识，请使用下列文章中的建议和设置以及此阶段中的步骤：

- [先决条件](identity-access-prerequisites.md)
- [常见标识和设备访问策略](identity-access-policies.md)

## <a name="how-microsoft-does-microsoft-365-enterprise"></a>Microsoft 如何对 Microsoft 365 企业版执行操作

了解 Microsoft 的 IT 专家如何[管理标识和安全访问](https://www.microsoft.com/zh-CN/itshowcase/deploying-and-managing-microsoft-365#primaryR5)。

## <a name="how-contoso-did-microsoft-365-enterprise"></a>Contoso 是如何使用 Microsoft 365 企业版的

了解 Contoso Corporation（虚构但具代表性的跨国企业）如何为 Microsoft 365 云服务[部署混合身份基础结构](contoso-identity.md)。

![](./media/contoso-overview/contoso-icon.png)


## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step1.png)| [计划用户和组](identity-plan-users-groups.md) |
