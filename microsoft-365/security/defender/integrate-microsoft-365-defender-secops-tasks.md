---
title: 步骤 6. 确定 SOC 维护任务
description: 将 SOC 维护任务与Microsoft 365 Defender集成在一起时确定。
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
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 96f7c95f645f0544b0bcd80a0cd0e3f9b595733e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60197973"
---
# <a name="step-6-identify-soc-maintenance-tasks"></a>步骤 6. 确定 SOC 维护任务

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

下面是维护 SOC 的定期任务或所需Microsoft 365 Defender。

| 活动  | 说明 | Cadence | 已分配团队 |
|:-------|:-----|:-------|:-------|
| 服务管理与 SOC Teams   | 管理外围服务，如资产跟踪 (CMDB) 、应用程序许可 (新 SaaS 许可证) 、设备购买 (升级或续订设备部署) Microsoft 365，以及可能影响 Microsoft 365 Defender 产品的部署的 (Intune、Microsoft 365 和其他) 租户范围内的其他更改。 | 每周和根据需要   | 工程& SecOps | 
| 更新防钓鱼和数据丢失防护活动 | 将 SOC 用例和与扩展的组织一起 (HR、法律、培训和其他) 。  | 每月和根据需要 | SOC 监督 |
| 在适当时部署自动化脚本和服务 | 从批准的 Microsoft 网站下载和测试自动化脚本和配置文件，以改进Microsoft 365 Defender操作。 | 每周和根据需要 | 工程和 SecOps | 
| 门户或许可证管理 | 检查公告和 Microsoft 消息 中心Microsoft 365 Defender Microsoft 更新和新功能来了解门户或许可需求。 | 每周 | SOC 监督| 
| 更新 SOC 升级票证 | 所有 SOC 团队更新 (票证，例如 Sentinel、ServiceNow 票证) 分配给他们。 | 每天 | 所有 SOC 团队 | 
| 跟踪Microsoft 365 Defender威胁&漏洞修正活动 | 生成 TvM 安全分数修正活动，并通过 Intranet 门户向资产所有者报告。 | 每天 | 监控 | 
| 生成安全分数报告 | 监视团队跟踪和报告安全分数改进。 | 每周 SOC | 监控 | 
| 运行 IR 桌面练习 | 在桌面练习中测试 SOC 团队手册。 | (视需要) | 所有 SOC 团队 | 
|||||

将这些任务集成到当前的 SOC 进程中。

## <a name="next-steps"></a>后续步骤

您应查看此内容和 Microsoft 365 Defender 库中引用的指南，以确定如何[](/microsoft-365/security/defender)构建和集成Microsoft 365 Defender实现。
