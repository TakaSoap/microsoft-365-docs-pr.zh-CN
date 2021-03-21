---
title: Microsoft 365 隔离控件
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
description: 了解隔离控制在 Microsoft 365 中如何工作，从而允许服务根据需要进行互操作或保持自治。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 514b12e44d9e81a18b691ebf3196a3d21157e71b
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50918938"
---
# <a name="microsoft-365-isolation-controls"></a>Microsoft 365 隔离控件 

Microsoft 持续致力于确保 Microsoft 365 的多租户体系结构支持企业级安全性、机密性、隐私、完整性、本地、国际和可用性 [标准](https://www.microsoft.com/TrustCenter/Compliance?service=Office#Icons)。 Microsoft 提供的服务规模和范围使得管理 Microsoft 365 时出现大量人机交互困难且经济实惠。 Microsoft 365 服务通过多个全球分布的数据中心提供，每个数据中心都通过几个需要人员触摸或客户内容访问的操作实现高度自动化。 我们的员工使用自动化工具和高度安全的远程访问支持这些服务和数据中心。 

Microsoft 365 由多项服务组成，这些服务提供重要的业务功能并有助于实现整个 Microsoft 365 体验。 其中每个服务都是独立的，旨在相互集成。

Microsoft 365 的设计原则如下：

 - **[面向服务的体系结构](/previous-versions/aa480021(v=msdn.10))：** 以提供明确定义的业务功能的可互操作服务的形式设计和开发软件。
 - **[操作](https://www.microsoft.com/download/details.aspx?id=40872)** 安全保证 ：一个框架，包含通过 [Microsoft](https://www.microsoft.com/sdl/default.aspx)特有的各种功能获得的知识，包括 Microsoft 安全开发生命周期 [、Microsoft 安全](https://technet.microsoft.com/library/dn440717.aspx)响应中心，以及网络安全威胁形势的深入感知。

Microsoft 365 服务相互操作，但设计和实现后，它们可部署和运行为自治服务，相互独立。 Microsoft 隔离 Microsoft 365 的职责和职责范围，以减少未经授权或无意修改或滥用组织资产的机会。 Microsoft 365 团队将角色定义为全面的基于角色的访问控制机制的一部分。

## <a name="customer-content-isolation"></a>客户内容隔离

租户中所有客户内容都与其他租户以及 Microsoft 365 管理中使用的操作和系统数据隔离。 Microsoft 365 中实施了多种形式的保护，以最大限度地降低任何 Microsoft 365 服务或应用程序泄露的风险。 多种形式的保护还可以防止未经授权访问租户或 Microsoft 365 系统本身的信息。

有关 Microsoft 如何在 Microsoft 365 中实现租户数据的逻辑隔离的信息，请参阅 [Microsoft 365](microsoft-365-tenant-isolation-overview.md)中的租户隔离。