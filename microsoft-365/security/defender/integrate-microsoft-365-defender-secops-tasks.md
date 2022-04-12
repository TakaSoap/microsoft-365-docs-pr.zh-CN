---
title: 步骤 6. 标识 SOC 维护任务
description: 将Microsoft 365 Defender集成到安全操作中时，确定 SOC 维护任务。
keywords: 事件， 警报， 调查， 关联， 攻击， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， m365， 事件响应， 网络攻击， secops， 安全操作， soc
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
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
ms.openlocfilehash: 6b1ee22f8176d6f682eb9e9f2134cc27db91affd
ms.sourcegitcommit: ac0ae5c2888e2b323e36bad041a4abef196c9c96
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64783592"
---
# <a name="step-6-identify-soc-maintenance-tasks"></a>步骤 6. 标识 SOC 维护任务

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

以下是维护 SOC 以进行Microsoft 365 Defender的定期或所需的任务。

|活动|说明|Cadence|分配的团队|
|---|---|---|---|
|与 SOC Teams的服务管理协作|管理外围服务，如资产跟踪 (CMDB) 、应用程序许可 (新的 SaaS 许可证) 、设备购买 (升级或续订设备部署) ，以及其他Microsoft 365租户范围的更改 (Intune、Microsoft 365和其他可能影响部署的) Microsoft 365 Defender产品。|每周和根据需要|工程& SecOps|
|更新反网络钓鱼和数据丢失防护活动|将 SOC 用例和经验教训与扩展组织 (人力资源、法律、培训和其他) 结合在一起。|每月和根据需要|SOC 监督|
|根据需要部署自动化脚本和服务|从已批准的 Microsoft 站点下载和测试自动化脚本和配置文件，以改进Microsoft 365 Defender操作。|每周和根据需要|工程和 SecOps|
|门户或许可证管理|根据 Microsoft 更新和新功能检查公告和Microsoft 消息中心Microsoft 365 Defender门户或许可需求。|每周|SOC 监督|
|更新 SOC 升级票证|所有 SOC 团队都会更新升级票 (，例如 Sentinel、ServiceNow 票证) 分配给他们。|每天|所有 SOC 团队|
|跟踪Microsoft 365 Defender威胁&漏洞修正活动|生成 TvM 安全分数修正活动，并通过 Intranet 门户向资产所有者报告。|每天|监控|
|生成安全评分报表|监视团队跟踪并报告安全分数改进。|每周 SOC|监控|
|运行 IR 表面练习|在桌面练习中测试 SOC 团队 playbook。|(视需要)|所有 SOC 团队|

将这些任务集成到当前的 SOC 进程中。

## <a name="next-steps"></a>后续步骤

应查看此内容和[Microsoft 365 Defender库](/microsoft-365/security/defender)中提到的指南，以确定如何构建和集成自己的Microsoft 365 Defender实现。
