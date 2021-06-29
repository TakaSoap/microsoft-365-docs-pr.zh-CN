---
title: 租户隔离Microsoft 365
ms.author: robmazz
author: robmazz
manager: laurawi
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
ms.collection:
- Strat_O365_IP
- M365-security-compliance
f1.keywords:
- NOCSH
description: 本文汇总了 Microsoft 如何在云服务（如 Microsoft 365）中强制执行租户Microsoft 365。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b52d936bb00ac0adef0baf428cbc5f9a8f8aba49
ms.sourcegitcommit: 6749455c52b0f98a92f6fffbc2bb86caf3538bd8
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/29/2021
ms.locfileid: "53194645"
---
# <a name="tenant-isolation-in-microsoft-365"></a>租户隔离Microsoft 365

云计算的主要好处之一是同时跨多个客户共享、通用的基础结构的概念，这导致规模下降。 此概念称为 *"多租户"。* Microsoft 持续致力于确保云服务的多租户体系结构支持企业级安全性、机密性、隐私性、完整性和可用性标准。

根据从可信赖计算和安全开发生命周期中[](https://www.microsoft.com/trust-center)收集的重要投资与[](https://www.microsoft.com/securityengineering/sdl/)经验，Microsoft 云服务的设计假定所有租户都可能对所有其他租户具有危害，并且我们实施了安全措施，以防止一个租户的操作影响另一个租户的安全或服务，或访问另一个租户的内容。

在多租户环境中维护租户隔离的两个主要目标是：

1.    防止跨租户泄露客户内容或未经授权访问客户内容;和
2.    防止一个租户的操作对另一个租户的服务造成负面影响

在整个 Microsoft 365 中实施了多种形式的保护，以防止客户危害 Microsoft 365 服务或应用程序，或获取对其他租户或 Microsoft 365 系统本身信息的未经授权的访问，包括：

- 通过基于授权和基于角色的访问控制Microsoft 365租户中的客户内容Azure Active Directory逻辑隔离。
- SharePointOnline 在存储级别提供数据隔离机制。
- Microsoft 使用严格的物理安全、背景屏蔽和多层加密策略来保护客户内容的机密性和完整性。 数据中心Microsoft 365均具有生物识别访问控制，大多数要求使用打印的指纹才能获得物理访问权限。 此外，作为招聘过程的一部分，所有美国 Microsoft 员工都需要成功完成标准背景检查。 有关在管理中用于管理访问的控件Microsoft 365，请参阅Microsoft 365[访问控制"。](/compliance/assurance/assurance-administrative-access-controls-overview)
- Microsoft 365使用对静态和传输中的客户内容进行加密的服务器端技术，包括 BitLocker、每个文件加密、传输层安全性 (TLS) 和 Internet 协议安全性 (IPsec) 。 有关加密中加密的特定Microsoft 365，请参阅数据[加密技术Microsoft 365。](../compliance/office-365-encryption-in-the-microsoft-cloud-overview.md)

同时，上面列出的保护提供了强大的逻辑隔离控件，提供与单独由物理隔离提供的威胁保护和缓解等效。

## <a name="related-links"></a>相关链接

- [Azure Active Directory 中的隔离和访问控制](microsoft-365-isolation-in-azure-active-directory.md)
- [Office Graph 和 Delve 中的租户隔离](microsoft-365-isolation-in-graph-and-delve.md)
- [Microsoft 365 搜索中的租户隔离](microsoft-365-isolation-in-microsoft-365-search.md)
- [资源限制](/compliance/assurance/assurance-resource-limits)
- [监视和测试租户边界](/compliance/assurance/assurance-monitoring-and-testing)
- [Microsoft 365 中的隔离和访问控制](microsoft-365-isolation-in-microsoft-365.md)