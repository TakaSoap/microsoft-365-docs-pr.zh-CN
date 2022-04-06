---
title: 步骤 4. 定义Microsoft 365 Defender角色、职责和监督
description: 将Microsoft 365 Defender集成到安全操作中时定义角色、职责和监督的基础知识。
keywords: 事件， 警报， 调查， 关联， 攻击， 设备， 用户， 标识， 标识， 邮箱， 电子邮件， 365， microsoft， Microsoft 365， 事件响应， 网络攻击， secops， 安全操作， soc
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
ms.openlocfilehash: 5410db413ece81a39453070985e6c744e8b684a6
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664053"
---
# <a name="step-4-define-microsoft-365-defender-roles-responsibilities-and-oversight"></a>步骤 4. 定义Microsoft 365 Defender角色、职责和监督

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

组织必须将Microsoft 365 Defender许可证、配置和管理作为初始任务建立所有权和责任，然后才能定义任何操作角色。 通常，许可证所有权、订阅成本以及Microsoft 365和Enterprise安全性 + 移动性 (EMS) 服务的所有权 (可能包括安全运营中心 (SOC) 团队之外Microsoft 365 Defender) 。 SOC 团队应与这些人合作，确保正确监督Microsoft 365 Defender。 

许多新式 SOC 根据其技能集和功能将其团队成员分配到类别。 例如：

- 分配给与威胁和分析函数的生命周期管理相关的任务的威胁情报团队。
- 一个由 SOC 分析师组成的监视团队，负责维护日志、警报、事件和监视功能。
- 一个工程&运营团队，负责设计和优化安全设备。

SOC 团队角色和Microsoft 365 Defender职责自然会集成到这些团队中。

下表列出了每个 SOC 团队的角色和职责，以及他们的角色如何与Microsoft 365 Defender集成。

| SOC 团队 | 角色和职责 | Microsoft 365 Defender任务  |
|:-------|:-----|:-------|
| SOC 监督 | <ul><li>执行 SOC 治理</li><li>建立每日、每周、每月流程</li><li>提供培训和意识</li><li>雇用员工、参与对等组和会议</li><li>进行蓝色、红色、紫色团队练习</ul>  | <ul><li>Microsoft 365 Defender门户访问控制</li><li>维护功能/URL 和许可更新寄存器</li><li>与 IT、法律、合规性和隐私利益干系人保持沟通</li><li>参与新Microsoft 365或Microsoft Azure计划的变更控制会议</ul> |
| 威胁智能&分析  | <ul><li>威胁情报源管理</li><li>病毒和恶意软件归因</li><li>威胁建模&威胁事件分类</li><li>内部威胁属性开发 </li><li>威胁 Intel 与风险管理计划的集成</li><li>跨 HR、法律、IT 和安全团队将数据见解与数据科学、BI 和分析集成<ul> | <ul><li>维护Microsoft Defender for Identity威胁建模</li><li>维护Microsoft Defender for Office 365威胁建模</li><li>维护Microsoft Defender for Endpoint威胁建模</ul> |
| 监控 | <ul><li>第 1 层、第 2 层、第 3 层分析师</li><li>日志源维护和工程</li><li>数据源引入 </li><li>SIEM 分析、警报、关联、优化</li><li>事件和警报生成</li><li>事件和警报分析</li><li>事件和警报报告</li><li>票证系统维护</ul> | 使用： <ul><li>安全与合规中心</li><li>Microsoft 365 Defender 门户</ul> |
| 工程& SecOps | <ul><li>应用、系统和终结点的漏洞管理</li><li>XDR/SOAR 自动化</li><li>合规性测试</li><li>网络钓鱼和 DLP 工程</li><li>工程</li><li>坐标更改控件</li><li>坐标 Runbook 更新</li><li>渗透测试<ul> | <ul><li>Microsoft Defender for Cloud Apps</li><li>Defender for Endpoint</li><li>Defender for Identity</ul> |
| 计算机安全事件响应团队 (CSIRT)  | <ul><li>调查和响应网络事件</li><li>执行取证</li><li>**可能经常与 SOC 隔离**</ul> | 协作和维护Microsoft 365 Defender事件响应 playbook |
||||


## <a name="next-step"></a>后续步骤

[步骤 5.开发和测试用例](integrate-microsoft-365-defender-secops-use-cases.md)
