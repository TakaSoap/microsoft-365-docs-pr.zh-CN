---
title: 针对 Microsoft 365 的标识和设备访问测试环境
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况。
ms.openlocfilehash: 53c9db06b27f0e697eb57525b563f11b819a6812
ms.sourcegitcommit: e269371de759a1a747c9f292775463aa11415f25
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/16/2021
ms.locfileid: "58356512"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>针对 Microsoft 365 的标识和设备访问测试环境

*本测试实验室指南只能用于Microsoft 365测试环境。*

[标识和设备访问配置](../security/office-365-security/microsoft-365-policies-configurations.md)是一组建议配置和条件访问策略，用于保护对与 Azure AD Azure Active Directory (集成的所有服务) 。

若要创建具有通用标识和设备访问配置的测试环境，请执行以下操作：

1. 根据所选的标识模型和身份验证方法，使用必备标识和安全功能来配置测试环境：

  - [仅限云](cloud-only-prereqs-m365-test-environment.md)
  - [PHS (密码哈希) ](phs-prereqs-m365-test-environment.md)
  - [直通身份验证 (PTA)](pta-prereqs-m365-test-environment.md)

2. 使用 [通用标识和设备](../security/office-365-security/identity-access-policies.md) 访问策略配置基于为测试环境配置的先决条件构建的策略，并探索并验证标识和设备保护。

## <a name="see-also"></a>另请参阅

[其他标识测试实验室指南](m365-enterprise-test-lab-guides.md#identity)

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](/microsoft-365-enterprise/)
