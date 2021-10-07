---
title: 部署阶段
description: 了解如何通过准备、设置和载入适用于终结点的终结点来部署 Microsoft Defender for Endpoint
keywords: 部署， 准备， 设置， 载入， 阶段， 部署， 部署， 采用， 配置
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-endpointprotect
- m365solution-overview
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b7c9c4389506e59998609f7d960016abf694ebc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190529"
---
# <a name="deployment-phases"></a>部署阶段

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

了解如何部署 Microsoft Defender for Endpoint，以便企业可以利用预防性保护、攻破后检测、自动调查和响应。

本指南可帮助你跨利益干系人一起准备环境，然后采用有条理的方式载入设备，从评估到有意义的试点，到完全部署。

每个部分对应于此解决方案中的一篇单独的文章。

![包含表中详细信息的部署阶段的图像。](images/deployment-guide-phases.png)


![部署阶段摘要：准备、设置、载入。](images/phase-diagrams/deployment-phases.png)

<br>

****

|阶段|说明|
|---|---|
|[阶段 1：准备](prepare-deployment.md)|了解部署适用于终结点的 Defender 时需要考虑的问题，例如利益干系人审批、环境注意事项、访问权限和功能采用顺序。|
|[阶段 2：设置](production-deployment.md)|获取有关需要执行的初始步骤的指导，以便你可以访问门户，例如验证许可、完成设置向导和网络配置。|
|[阶段 3：开始使用](onboarding.md)|了解如何使用部署圈、基于终结点类型支持的载入工具以及配置可用功能。|
|

完成本指南后，你将使用正确的访问权限进行设置，你的终结点将载入，并且向服务报告传感器数据，下一代保护和攻击面减少等功能将就位。

无论选择的环境体系结构和部署方法如何，规划部署指南中概述，[](deployment-strategy.md)本指南都将在载入终结点方面支持你。

## <a name="key-capabilities"></a>关键功能

虽然 Microsoft Defender for Endpoint 提供了许多功能，但此部署指南的主要目的是通过载入设备入门。 除了载入，本指南还让你开始使用以下功能。

<br>

****

|功能|说明|
|---|---|
|终结点检测和响应|终结点检测和响应功能已到位，以检测、调查和响应入侵尝试和主动泄露。|
|下一代保护|为了进一步巩固你的网络的安全外围，Microsoft Defender for Endpoint 使用下一代保护来捕获所有类型的新兴威胁。|
|攻击面减少|在堆栈中提供第一道防线。 通过确保正确设置配置设置并应用攻击缓解技术，这些功能可抵御攻击和利用。|
|

所有这些功能都适用于适用于终结点许可证持有者的 Microsoft Defender。 有关详细信息，请参阅 [许可要求](minimum-requirements.md#licensing-requirements)。

## <a name="scope"></a>范围

### <a name="in-scope"></a>在作用域内

- 使用 Microsoft Endpoint Manager 和 Microsoft Endpoint Manager将终结点载入服务并配置功能
- 启用 Defender 终结点检测和响应 (EDR) 功能
- 启用适用于终结点保护平台的 Defender (EPP) 功能
  - 下一代保护
  - 攻击面减少

### <a name="out-of-scope"></a>超出范围

以下超出了此部署指南的范围：

- 可能与 Defender for Endpoint 集成的第三方解决方案的配置
- 生产环境中的渗透测试

## <a name="see-also"></a>另请参阅

- [阶段 1：准备](prepare-deployment.md)
- [阶段 2：设置](production-deployment.md)
- [阶段 3：开始使用](onboarding.md)
- [计划部署](deployment-strategy.md)
