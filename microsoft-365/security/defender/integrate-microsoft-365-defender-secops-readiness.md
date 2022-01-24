---
title: 步骤 2. 使用零信任框架执行 SOC 集成准备情况评估
description: 将 SOC 集成准备情况评估集成到安全操作时，使用零信任框架Microsoft 365 Defender的基础知识。
keywords: 事件， 警报， 调查， 关联， 攻击， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击， secops， 安全操作， soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-m365dsecops
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: ca58d56e9caf6aa8a359a0776fc160cca04fec8a
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62171786"
---
# <a name="step-2-perform-a-soc-integration-readiness-assessment-using-the-zero-trust-framework"></a>步骤 2. 使用零信任框架执行 SOC 集成准备情况评估

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

定义安全操作中心 (SOC) 团队的核心功能后，组织的下一步是准备通过零信任方法采用[Microsoft 365 Defender。](/security/zero-trust/) 采用可以帮助您确定使用现代行业领先的Microsoft 365 Defender部署解决方案所需的要求，同时根据Microsoft 365 Defender评估组织的功能。

此方法基于强大的保护基础，包括标识、终结点、 (设备) 、数据、应用、基础结构和网络等关键方面。 准备情况评估团队将确定尚未满足启用Microsoft 365 Defender的基本要求并需要修正的领域。

以下是一些需要修正的项目，SOC 才能完全优化 SOC 中的进程：

- **标识：** 旧版本地 Active Directory 域服务 (AD DS) 、无 MFA 计划、特权帐户清单等。
- **终结点 (设备) ：** 大量旧版操作系统、有限的设备清单和其他操作系统。
- **数据和应用：**  缺少数据管理标准，没有无法集成自定义应用的清单。
- **基础结构：** 大量未批准的 SaaS 许可证、没有容器安全等。
- **网络：** 低带宽、网络扁平化、无线安全问题等导致性能问题。

组织还应按照[打开Microsoft 365 Defender](m365d-enable.md)文章来捕获一组基线配置要求。 这些步骤反过来将确定 SOC 团队必须执行以有效开发用例的修正活动。 

采用过程和用例创建在步骤 3 和 4 中进行了介绍。

## <a name="next-step"></a>后续步骤

[步骤 3.规划Microsoft 365 Defender服务目录的集成](integrate-microsoft-365-defender-secops-services.md)
