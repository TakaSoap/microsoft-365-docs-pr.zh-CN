---
title: 针对 Microsoft 365 的标识和设备访问测试环境
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 04/23/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: ''
description: 创建一个 Microsoft 365 环境来测试标识和设备访问情况。
ms.openlocfilehash: 84af7747fc1d0e80e933397f4f0f96018ed246c3
ms.sourcegitcommit: 04c4252457d9b976d31f53e0ba404e8f5b80d527
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2020
ms.locfileid: "48327803"
---
# <a name="identity-and-device-access-for-your-microsoft-365-test-environment"></a>针对 Microsoft 365 的标识和设备访问测试环境

*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*

[标识和设备访问配置](microsoft-365-policies-configurations.md) 是一组功能和条件访问策略，用于保护与 Azure Active Directory (azure AD) 集成的所有服务的访问权限。

若要创建具有通用标识和设备访问配置的测试环境，请执行以下操作：

1. 根据所选的标识模型和身份验证方法，使用必备标识和安全功能来配置测试环境：

  - [仅限云](cloud-only-prereqs-m365-test-environment.md)
  - [ (PHS) 的密码哈希同步 ](phs-prereqs-m365-test-environment.md)
  - [直通身份验证 (PTA)](pta-prereqs-m365-test-environment.md)

2. 使用 [通用标识和设备访问策略](identity-access-policies.md) 来配置基于为测试环境配置的先决条件的策略，并探索并验证身份和设备的保护。

## <a name="see-also"></a>另请参阅

[其他标识测试实验室指南](m365-enterprise-test-lab-guides.md#identity)

[标识路线图](identity-roadmap-microsoft-365.md)

[Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[适用于企业的 Microsoft 365 文档](https://docs.microsoft.com/microsoft-365-enterprise/)
