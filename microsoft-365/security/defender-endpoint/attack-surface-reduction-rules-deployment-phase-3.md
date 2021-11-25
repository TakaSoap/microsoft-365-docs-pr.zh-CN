---
title: 攻击面减少规则部署阶段 3 - 实施
description: 提供实现攻击面减少规则部署的指南。
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
ms.openlocfilehash: 8489e31f0178fb4c0ab8e5159a71bc0691276689
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61171727"
---
# <a name="attack-surface-reduction-rules-deployment-phase-3-implement"></a>攻击面减少规则部署阶段 3：实施

实现阶段将环从测试移动到功能状态。

> [!div class="mx-imgBorder"]
> ![ASR 规则实现步骤](images/asr-rules-implementation-steps.png)

## <a name="step-1-transition-asr-rules-from-audit-to-block"></a>步骤 1：将 ASR 规则从审核转换为阻止

1. 在审核模式下确定所有排除项后，开始将某些 ASR 规则设置为"阻止"模式，从触发事件数最小的规则开始。 请参阅"[启用攻击面减少规则"。](enable-attack-surface-reduction.md)
2. 查看报告门户中的报告Microsoft 365 Defender，请参阅 Microsoft Defender [for Endpoint 中的威胁防护报告](threat-protection-reports.md)。 此外，查看来自 ASR 冠军的反馈。
3. 精简排除项或在必要时创建新的排除项。
4. 将有问题的规则切换回审核。

  >[!Note]
  >对于有问题的规则 (规则产生过多干扰) ，最好创建排除项，而不是关闭规则或切换回审核。 您必须确定最适合您的环境。

  >[!Tip]
  >如果可用，利用规则中的警告模式设置来限制中断。 在"警告"模式下启用 ASR 规则，可以捕获触发的事件并查看其潜在的中断，而不会实际阻止最终用户的访问。 了解更多： [针对用户发出警告模式](attack-surface-reduction.md#warn-mode-for-users)。

### <a name="how-does-warn-mode-work"></a>警告模式如何工作？

警告模式实际上是阻止指令，但用户可以选择"取消阻止"给定流或应用的后续执行。 在设备、用户、文件和进程组合上取消阻止警告模式。 警告模式信息存储在本地，持续时间为 24 小时。

### <a name="step-2-expand-deployment-to-ring-n--1"></a>步骤 2：展开部署以圈 n + 1

当你确信已正确配置圈 1 的 ASR 规则时，你可以将部署范围扩大到下一个圈 (n + 1) 。

每个后续圈的部署过程步骤 1 – 3 基本相同：

1. 审核中的测试规则
2. 在管理门户中查看 ASR 触发的Microsoft 365 Defender事件
3. 创建排除项
4. 查看：根据需要优化、添加或删除排除项
5. 将规则设置为"阻止"
6. 查看报告门户中的Microsoft 365 Defender页面。
7. 创建排除项。
8. 禁用有问题的规则或将其切换回审核。

## <a name="additional-topics-in-this-deployment-collection"></a>此部署集合中的其他主题

[攻击面减少规则部署指南 - 概述](attack-surface-reduction-rules-deployment.md)

[攻击面减少规则部署阶段 1 - 计划](attack-surface-reduction-rules-deployment-phase-1.md)

[攻击面减少规则部署阶段 2 - 测试](attack-surface-reduction-rules-deployment-phase-2.md)

[攻击面减少规则部署阶段 4 - 可操作](attack-surface-reduction-rules-deployment-phase-4.md)
