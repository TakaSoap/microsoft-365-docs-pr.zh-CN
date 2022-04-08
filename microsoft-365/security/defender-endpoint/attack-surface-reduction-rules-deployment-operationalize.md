---
title: 操作攻击面减少 (ASR) 规则
description: 提供操作攻击面减少规则部署的指导。
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
ms.openlocfilehash: 2c666a8b31308fb3cfb18a9a35211e49d886eab0
ms.sourcegitcommit: 5c9137f98e688ab23c144e75687399e390bb2601
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/07/2022
ms.locfileid: "64705376"
---
# <a name="operationalize-attack-surface-reduction-asr-rules"></a>操作攻击面减少 (ASR) 规则

在 ASR) 规则 (完全部署攻击面减少后，必须制定相应的流程来监视和响应与 ASR 相关的活动。

## <a name="managing-false-positives"></a>管理误报

任何威胁防护解决方案都可能发生误报/阴性。 误报是实体 (（如文件或进程) ）被检测并标识为恶意的情况，尽管实体实际上不是威胁。 相比之下，假负值是未检测为威胁但是恶意的实体。 有关误报和误报的详细信息，请参阅：[在Pertahanan Microsoft untuk Titik Akhir中处理误报/负](defender-endpoint-false-positives-negatives.md)数

## <a name="keeping-up-with-reports"></a>跟上报表

一致、定期查看报表是维护 ASR 规则部署和及时应对新出现的威胁的一个重要方面。 你的组织应该根据与 ASR 规则报告的事件保持最新状态的节奏对 ASR 规则事件进行计划评审。 根据组织的规模，评审可能为每日、每小时或持续监视。

## <a name="hunting"></a>搜寻

[Microsoft 365 Defender](https://security.microsoft.com)最强大的功能之一是高级搜寻。 如果你不熟悉高级狩猎，请参阅： [通过高级搜寻主动搜寻威胁](/windows/security/threat-protection/microsoft-defender-atp/advanced-hunting-overview)。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting2.png" alt-text="Microsoft 365 Defender门户中的&quot;高级搜寻&quot;页" lightbox="images/asr-defender365-advanced-hunting2.png":::

高级搜寻是基于查询的 (Kusto 查询语言) 威胁搜寻工具，可用于浏览 Microsoft Defender ATP 终结点检测和响应 (EDR) 从所有计算机收集的最多 30 天的捕获 (原始) 数据。 通过高级搜寻，可以主动检查事件，以便找到有趣的指示器和实体。 灵活访问数据有助于无约束搜寻已知威胁和潜在威胁。

通过高级搜寻，可以提取 ASR 规则信息，创建报表，并获取有关给定 ASR 规则审核或阻止事件上下文的深入信息。

 可以在Microsoft 365 Defender门户的高级搜寻部分中的 DeviceEvents 表中查询 ASR 规则事件。 例如，一个简单的查询（如下面的查询）可以报告过去 30 天内具有 ASR 规则作为数据源的所有事件，并按 ActionType 计数对其进行汇总，在这种情况下，它将是 ASR 规则的实际代码名。

前进的搜寻门户中显示的 ASR 事件限制为每小时看到的唯一进程。 ASR 事件的时间是首次在该小时内看到该事件。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting3.png" alt-text="Microsoft 365 Defender门户中的高级搜寻查询命令行" lightbox="images/asr-defender365-advanced-hunting3.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting4.png" alt-text="高级搜寻查询在Microsoft 365 Defender门户中生成" lightbox="images/asr-defender365-advanced-hunting4.png":::

以上显示为 AsrLsassCredentialTheft 注册了 187 个事件：

- 102 for Blocked
- 85（用于审核）
- AsrOfficeChildProcess 的 2 个事件 (1 个用于审核，1 个事件用于阻止) 
- AsrPsexecWmiChildProcessAudited 的 8 个事件

如果想要专注于 AsrOfficeChildProcess 规则并获取涉及的实际文件和过程的详细信息，请更改 ActionType 的筛选器，并将汇总行替换为所需字段的投影 (在这种情况下，它们是 DeviceName、FileName、FolderPath 等) 。

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting4b.png" alt-text="Microsoft 365 Defender门户中以高级搜寻查询为重点的示例" lightbox="images/asr-defender365-advanced-hunting4b.png":::

> [!div class="mx-imgBorder"]
> :::image type="content" source="images/asr-defender365-advanced-hunting5b.png" alt-text="高级搜寻查询集中在Microsoft 365 Defender门户中" lightbox="images/asr-defender365-advanced-hunting5b.png":::

高级搜寻的真正好处是，你可以根据自己的喜好来塑造查询。 通过调整查询，可以查看所发生情况的确切情况，无论你是要在单台计算机上确定某些内容，还是要从整个环境中提取见解。

有关搜寻选项的详细信息，请参阅： [揭开攻击面减少规则的神秘性 - 第 3 部分](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/demystifying-attack-surface-reduction-rules-part-3/ba-p/1360968)。

## <a name="topics-in-this-deployment-collection"></a>此部署集合中的主题

[攻击面减少 (ASR) 规则部署概述](attack-surface-reduction-rules-deployment.md)

[计划攻击面减少 (ASR) 规则部署](attack-surface-reduction-rules-deployment-plan.md)

[测试攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-test.md)

[启用攻击面减少 (ASR) 规则](attack-surface-reduction-rules-deployment-implement.md)

[ASR) 规则引用 (攻击面减少](attack-surface-reduction-rules-reference.md)
