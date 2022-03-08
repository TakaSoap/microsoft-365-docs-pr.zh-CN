---
title: 步骤 4. 定义Microsoft 365 Defender角色、职责和监管
description: 将安全管理集成到安全操作时定义角色Microsoft 365 Defender监督的基础知识。
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
ms.openlocfilehash: 7562eca50b905bf70f17844cf8fe3079fbf3fc14
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63314275"
---
# <a name="step-4-define-microsoft-365-defender-roles-responsibilities-and-oversight"></a>步骤 4. 定义Microsoft 365 Defender角色、职责和监管

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**
- Microsoft 365 Defender

在定义任何操作角色之前，组织必须Microsoft 365 Defender许可证、配置和管理作为初始任务的所有权和责任。 通常，Microsoft 365 和 Enterprise 安全 + 移动性 (EMS) 服务 (（可能包括 Microsoft 365 Defender) ）的许可证的所有权、订阅成本和管理位于安全运营中心 (SOC) 团队之外。 SOC 团队应该与这些人合作，以确保正确监控Microsoft 365 Defender。 

许多现代 SOC 都基于其技能集和功能将其团队成员分配到类别。 例如：

- 分配给与威胁和分析功能的生命周期管理相关的任务的威胁智能团队。
- 由负责维护日志、警报、事件和监视功能的 SOC 分析师组成的监视团队。
- 一个&运营团队，负责设计并优化安全设备。

SOC 团队角色和团队Microsoft 365 Defender自然地集成到这些团队中。

下表列出了每个 SOC 团队的角色和职责，以及他们的角色如何与Microsoft 365 Defender。

| SOC 团队 | 角色和职责 | Microsoft 365 Defender任务  |
|:-------|:-----|:-------|
| SOC 监督 | <ul><li>执行 SOC 管理</li><li>建立每日、每周、每月流程</li><li>提供培训和意识</li><li>雇用员工，参与对等组和会议</li><li>执行蓝、红、紫色团队练习</ul>  | <ul><li>Microsoft 365 Defender门户访问控制</li><li>维护功能/URL 和许可更新注册</li><li>与 IT、法律、合规性和隐私利益干系人保持通信</li><li>参加新计划或新计划Microsoft 365变更Microsoft Azure会议</ul> |
| 威胁智能&分析  | <ul><li>威胁情报源管理</li><li>病毒和恶意软件属性</li><li>威胁&模型化威胁事件分类</li><li>预览体验成员威胁属性开发 </li><li>威胁 Intel 与风险管理计划集成</li><li>跨人力资源、法律、IT 和安全团队将数据见解与数据科学、BI 和分析集成<ul> | <ul><li>维护 Microsoft Defender for Identity 威胁建模</li><li>维护 Microsoft Defender Office 365威胁建模</li><li>维护 Microsoft Defender 终结点威胁建模</ul> |
| 监控 | <ul><li>第 1 层、第 2 层、3 名分析师</li><li>日志源维护和工程</li><li>数据源的输入 </li><li>SIEM 分析、警报、关联、优化</li><li>事件和警报生成</li><li>事件和警报分析</li><li>事件和警报报告</li><li>票证系统维护</ul> | 使用： <ul><li>安全与合规中心</li><li>Microsoft 365 Defender 门户</ul> |
| 工程 & SecOps | <ul><li>应用、系统和终结点的漏洞管理</li><li>XDR/SOAR 自动化</li><li>合规性测试</li><li>网络钓鱼和 DLP 工程</li><li>工程</li><li>坐标更改控件</li><li>协调 Runbook 更新</li><li>渗透测试<ul> | <ul><li>Microsoft Defender for Cloud Apps</li><li>Defender for Endpoint</li><li>Defender for Identity</ul> |
| 计算机安全事件响应团队 (CSIRT)  | <ul><li>调查和响应网络事件</li><li>执行取证</li><li>**可能经常与 SOC 隔离**</ul> | 协作和维护Microsoft 365 Defender事件响应手册 |
||||


## <a name="next-step"></a>后续步骤

[步骤 5.开发和测试用例](integrate-microsoft-365-defender-secops-use-cases.md)
