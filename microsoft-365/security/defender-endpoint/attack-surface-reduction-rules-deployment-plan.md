---
title: 计划攻击面减少 (ASR) 规则部署
description: 提供有关规划攻击面减少 (ASR) 规则部署的指导。
keywords: 攻击面减少规则部署、ASR 部署、启用 asr 规则、配置 ASR、主机入侵防护系统、保护规则、防攻击规则、反攻击规则、攻击规则、感染预防规则、Pertahanan Microsoft untuk Titik Akhir、配置 ASR 规则
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
audience: ITPro
author: jweston-1
ms.author: v-jweston
ms.reviewer: oogunrinde, sugamar
manager: dansimp
ms.custom: asr
ms.technology: mde
ms.topic: article
ms.collection:
- m365solution-scenario
- M365-security-compliance
ms.date: 1/18/2022
ms.openlocfilehash: 07388ab8f1aac89991423c07fb442017aafb73e6
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705288"
---
# <a name="plan-attack-surface-reduction-asr-rules-deployment"></a>计划攻击面减少 (ASR) 规则部署

测试攻击面减少 (ASR) 规则时，请务必从正确的业务单元开始。 你将希望从特定业务部门中的一小群人员开始。 你可以识别特定业务部门中的一些 ASR 支持者，这些支持者可以提供对 ASR 规则的实际影响，并帮助你优化实现。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-rules-planning-steps.png" alt-text="ASR 规则规划步骤" lightbox="images/asr-rules-planning-steps.png":::

## <a name="start-with-the-right-business-unit"></a>从正确的业务单元开始

如何选择业务部门来推出 ASR 规则部署将取决于以下因素：

- 业务单位的大小
- ASR 规则冠军的可用性  
- 分发和使用情况：
  - 软件
  - 共享文件夹
  - 脚本的使用
  - Office宏
  - 受 ASR 规则影响的其他实体

根据业务需求，可以决定包括多个业务单位，以获取软件、共享文件夹、脚本、宏等的广泛采样。相反，你可能决定将首次推出 ASR 规则的范围限制为单个业务部门，然后将整个 ASR 规则推出过程一次性重复到其他业务部门。

## <a name="identify-asr--rules-champions"></a>确定 ASR 规则支持者

ASR 规则支持者是组织中的成员，可在初步测试和实施阶段帮助你推出初始 ASR 规则。 你的拥护者通常是技术更熟练、不会因间歇性工作流中断而脱轨的员工。 在整个 ASR 规则部署向组织扩展过程中，冠军的参与将继续。 ASR 规则支持者将首先体验 ASR 规则推出的每一个级别。

请务必为 ASR 规则支持者提供反馈和响应渠道，提醒你注意与 ASR 规则相关的工作中断，并接收 ASR 规则推出的相关通信。

## <a name="get-inventory-of-line-of-business-apps-and-understand-the-business-unit-processes"></a>获取业务线应用清单并了解业务部门流程

全面了解组织中使用的应用程序和每业务单元流程对于成功部署 ASR 规则至关重要。 此外，必须了解如何在组织中的各种业务单元中使用这些应用。
首先，应获取已批准在组织范围内使用的应用的清单。 可以使用Microsoft 365 应用版管理中心等工具来帮助你清点软件应用程序。 请参阅：[Microsoft 365 应用版管理中心的清单概述](/deployoffice/admincenter/inventory)。

## <a name="define-reporting-and-response-team-roles-and-responsibilities"></a>定义报告和响应团队角色和职责

明确阐明负责监视和传达 ASR 规则状态和活动的人员的角色和职责是 ASR 维护的核心活动。 因此，必须确定：

- 负责收集报表的人员或团队
- 如何与谁共享报表
- 如何解决 ASR 规则导致的新标识的威胁或不需要的阻塞的升级问题

典型的角色和职责包括：

- IT 管理员：实现 ASR 规则，管理排除项。 在应用和流程上使用不同的业务单位。 将报表汇集和共享给利益干系人
- 经认证的安全运营中心 (CSOC) 分析师：负责投资高优先级、受阻的流程，以确定威胁是否有效
- CISO)  (首席信息安全官：负责组织的整体安全状况和运行状况

## <a name="ring-deployment"></a>环形部署

对于大型企业，Microsoft 建议在"环"中部署 ASR 规则。 环是以视觉方式表示为同心圆的设备组，它们像非重叠的树环一样向外辐射。 成功部署最内层环时，可以将下一个环转换为测试阶段。 对业务单位、ASR 规则支持者、应用和流程进行彻底评估对于定义环势在必行。
在大多数情况下，组织会为分阶段推出Windows更新设计部署圈。 可以使用现有的环形设计来实现 ASR 规则。
请参阅：[为Windows创建部署计划](/windows/deployment/update/create-deployment-plan)

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[攻击面减少 (ASR) 规则部署概述](attack-surface-reduction-rules-deployment.md)

[测试攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-test.md)

[启用攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-implement.md)

[操作攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-operationalize.md)

[ASR) 规则引用 (攻击面减少](attack-surface-reduction-rules-reference.md)
