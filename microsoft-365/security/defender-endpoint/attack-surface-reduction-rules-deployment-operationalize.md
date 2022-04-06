---
title: 通过 ASR 规则 (操作攻击) 面减少
description: 提供操作攻击面减少规则部署的指导。
keywords: 攻击面减少规则部署， ASR 部署， 启用 asr 规则， 配置 ASR， 主机入侵防护系统， 保护规则， 反攻击规则， 反攻击， 攻击规则， 感染防护规则， Microsoft Defender for Endpoint， 配置 ASR 规则
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
ms.openlocfilehash: 73597ff3b56189952999993df05f13a0caeacb0c
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63683090"
---
# <a name="step-4-operationalize-asr-rules"></a>步骤 4：操作 ASR 规则

在通过 ASR (规则 (攻击面减少) ，必须制定流程来监视和响应与 ASR 相关的活动，这一点至关重要。

## <a name="managing-false-positives"></a>管理误报

任何威胁防护解决方案都可能发生误报/负面影响。 误报是检测到实体 (进程或进程) 被检测并标识为恶意实体的情况，尽管实体实际上不是威胁。 相比之下，漏报是未检测为威胁但恶意的实体。 有关误报和漏报信息，请参阅： [在 Microsoft Defender for Endpoint 中解决误报/负数](defender-endpoint-false-positives-negatives.md)

## <a name="keeping-up-with-reports"></a>保持与报告保持一起

一致、定期地审阅报告是维护 ASR 规则部署和保持新出现的威胁的一个基本方面。 贵组织应按节奏安排对 ASR 规则事件进行审阅，以使用 ASR 规则报告的事件保持最新。 根据组织的规模，评价可能是每天、每小时或持续监视。

## <a name="hunting"></a>搜寻

搜索功能最强大的功能[之一Microsoft 365 Defender](https://security.microsoft.com)高级搜寻。 如果你不熟悉高级搜寻，请参阅：使用高级搜寻主动 [搜寻威胁](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高级搜寻](images/asr-defender365-advanced-hunting2.png)

高级搜寻是基于查询的 (Kusto 查询语言) 威胁搜寻工具，允许你浏览 Microsoft Defender ATP 终结点检测和响应 (EDR) 从你的所有计算机中收集的最多 30 天的已捕获 (原始) 数据。 通过高级搜寻，你可以主动检查事件，以便找到有趣的指示器和实体。 灵活访问数据有助于无约束搜寻已知威胁和潜在威胁。

通过高级搜寻，可以提取 ASR 规则信息、创建报告，并获取有关给定 ASR 规则审核或阻止事件的上下文的深入信息。

 你可以查询应用门户高级搜寻部分中 DeviceEvents 表中的 ASR 规则Microsoft 365 Defender事件。 例如，如下所示的简单查询可以报告过去 30 天内将 ASR 规则作为数据源的所有事件，并按 ActionType 计数汇总这些事件，在这种情况下，它将是 ASR 规则的实际代码名。

前进搜寻门户中显示的 ASR 事件被限制到每小时看到的唯一进程。 ASR 事件的时间是该小时内首次看到该事件的时间。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高级搜寻查询命令行](images/asr-defender365-advanced-hunting3.png)

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高级搜寻查询结果](images/asr-defender365-advanced-hunting4.png)

以上显示为 AsrLsassCredentialTheft 注册了 187 个事件：

- 102 表示被阻止
- 85 表示已审核
- AsrOfficeChildProcess 事件 2 个 (个事件，1 个事件用于审核，1 个事件用于阻止) 
- AsrPsexecWmiChildProcessAudited 的 8 个事件

如果您想重点关注 AsrOfficeChildProcess 规则并获取有关实际文件和过程的详细信息，请更改 ActionType 的筛选器，将汇总行替换为对需要字段 (的投影，在这种情况下它们是 DeviceName、FileName、FolderPath 等 ) 。

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高级搜寻查询](images/asr-defender365-advanced-hunting4b.png)

> [!div class="mx-imgBorder"]
> ![Microsoft 365 Defender高级搜寻查询焦点结果](images/asr-defender365-advanced-hunting5b.png)

高级搜寻的真正好处是，你可以将查询塑造成喜欢的形状。 通过确定查询的定形，你可以查看所发生事情的确切情景，无论你是想要在单台计算机中定位某些内容，还是想要从整个环境中提取见解。

有关搜寻选项的详细信息，请参阅：验证攻击面减少 [规则 - 第 3 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)。

## <a name="topics-in-this-deployment-collection"></a>此部署集合中的主题

[ASR 规则部署先决条件](attack-surface-reduction-rules-deployment.md)

[步骤 1：规划 ASR 规则部署](attack-surface-reduction-rules-deployment-plan.md)

[步骤 2：测试 ASR 规则](attack-surface-reduction-rules-deployment-test.md)

[步骤 3：实现 ASR 规则](attack-surface-reduction-rules-deployment-implement.md)
