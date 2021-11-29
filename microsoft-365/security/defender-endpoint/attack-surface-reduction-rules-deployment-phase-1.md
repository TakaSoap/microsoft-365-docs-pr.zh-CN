---
title: ASR 规则部署阶段 1 - 计划
description: 提供规划攻击面减少规则部署的指南。
keywords: 攻击面减少规则部署， ASR 部署， 启用 asr 规则， 配置 ASR， 主机入侵防护系统， 保护规则， 反攻击规则， 反攻击， 攻击规则， 感染防护规则， Microsoft Defender for Endpoint， 配置 ASR 规则
search.product: eADQiWindows 10XVcnh
ms.reviewer: ''
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: ca6c7ed6265a1c68a513d6025227780fa429f6e8
ms.sourcegitcommit: dfa9f28a5a5055a9530ec82c7f594808bf28d0dc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/29/2021
ms.locfileid: "61217394"
---
# <a name="attack-surface-reduction-rules-deployment-phase-1-plan"></a>攻击面减少规则部署阶段 1：计划

开始测试 ASR 规则涉及从正确的业务部门开始。 您需要从特定业务部门中的一小组人员开始。 你可以确定特定业务部门中的一些 ASR 冠军，这些冠军可以为 ASR 规则提供实际影响，并帮助你调整实现。

> [!div class="mx-imgBorder"]
> ![ASR 规则规划步骤](images/asr-rules-planning-steps.png)

## <a name="start-with-the-right-business-unit"></a>从正确的业务部门开始

选择业务部门以推出 ASR 规则部署将取决于以下因素：

- 业务部门的大小
- ASR 规则冠军的可用性  
- 分发和使用：
  - 软件
  - 共享文件夹
  - 脚本的使用
  - Office宏
  - 受 ASR 规则影响的其他实体

根据您的业务需求，您可能决定包含多个业务单位，以广泛采样软件、共享文件夹、脚本、宏等。相反，您可能会决定将首次推出 ASR 规则的范围限制为一个业务部门，然后将整个 ASR 规则推出过程重复到其他业务单位，一次一个。

## <a name="identify-asr--rules-champions"></a>确定 ASR 规则冠军

ASR 规则冠军是贵组织的成员，有助于在初步测试和实施阶段推出初始 ASR 规则。 你的冠军通常是在技术上更擅长的员工，并且不会因间歇性的工作流程中断而受阻碍。 在向组织广泛扩展 ASR 规则部署过程中，冠军的参与将继续。 ASR 规则冠军将首先体验每个级别的 ASR 规则推出。

为 ASR 规则支持者提供反馈和响应渠道非常重要，以提醒你 ASR 规则相关的工作中断，并接收与 ASR 规则推出相关的通信。

## <a name="get-inventory-of-line-of-business-apps-and-understand-the-business-unit-processes"></a>获取业务线应用的清单并了解业务部门流程

全面了解整个组织中使用的应用程序和每个业务部门的过程对于成功部署 ASR 规则至关重要。 此外，必须了解在组织的各个业务部门中如何使用这些应用。
首先，你应该获得经批准在整个组织范围使用的应用的清单。 可以使用管理中心等工具Microsoft 365 应用版软件应用程序清单。 请参阅：[管理中心中的Microsoft 365 应用版概述](/deployoffice/admincenter/inventory)。

## <a name="define-reporting-and-response-team--roles-and-responsibilities"></a>定义报告和响应团队角色和责任

明确分配负责监视和传达 ASR 规则状态和活动的人员的角色和职责是 ASR 维护的核心活动。 因此，确定：

- 负责收集报告的人或团队
- 如何共享报告以及与谁共享报告
- 如何处理由 ASR 规则导致的新标识的威胁或不需要的阻止问题进行升级

典型角色和职责包括：

- IT 管理员：实施 ASR 规则，管理排除项。 在应用和流程上使用不同的业务部门。 组合报告并共享给利益干系人
- CSOC (安全运营) ：负责投资高优先级的阻止流程，以确定威胁是否有效
- CISO (首席信息安全) ：负责组织的整体安全状况和运行状况

## <a name="ring-deployment"></a>环形部署

对于大型企业，Microsoft 建议在"圈"中部署 ASR 规则。 圈是视觉上表示为像不重叠树圈一样向外延伸的同心圆的设备组。 成功部署最里层的圈后，你可以将下一个圈转换到测试阶段。 对业务部门、ASR 规则冠军、应用和流程进行全面评估对定义圈至关重要。
在大多数情况下，你的组织将设计部署圈，用于分阶段推出Windows更新。 可以使用现有的圈设计来实现 ASR 规则。
请参阅：[为部署环境创建Windows](/windows/deployment/update/create-deployment-plan)

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[ASR 规则部署指南 - 概述](attack-surface-reduction-rules-deployment.md)

[ASR 规则部署阶段 2 - 测试](attack-surface-reduction-rules-deployment-phase-2.md)

[ASR 规则部署阶段 3 - 实现](attack-surface-reduction-rules-deployment-phase-3.md)

[ASR 规则部署阶段 4 - 可操作](attack-surface-reduction-rules-deployment-phase-4.md)
