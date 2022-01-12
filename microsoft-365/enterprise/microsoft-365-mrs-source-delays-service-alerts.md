---
title: MRS 服务警报
ms.author: markjjo
author: markjjo
manager: scotv
ms.date: ''
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
search.appveyor:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
f1.keywords:
- NOCSH
description: 使用邮箱迁移服务警报监视组织中邮箱迁移请求的延迟。
ms.openlocfilehash: 25c569030bd5da914dc6eb7ec0e58ebadfe4d766
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61937862"
---
# <a name="service-alerts-for-mrs-source-delays-in-exchange-online-monitoring"></a>用于监控中 MRS 源延迟的服务Exchange Online警报

邮箱复制服务 (MRS) 源延迟服务警报会通知您租户端 (迁移源) 上的存储限制或处理器使用率高问题，这些问题可能会延迟 Microsoft 365 组织的邮箱迁移。 这些服务警报还包括指向 Microsoft 资源的链接，可帮助你解决这些问题。

这些服务警报显示在Microsoft 365 管理中心。 若要查看这些服务警报，请转到运行状况服务  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=842900" target="_blank">**运行状况**</a>Exchange Online  >  然后单击"**活动问题"** 选项卡。

## <a name="what-do-these-service-alerts-indicate"></a>这些服务警报表示什么？

此服务警报会告知您组织中邮箱迁移的潜在延迟。 这包括跨林迁移、载入迁移和载出迁移。 服务警报包含一个表，其中包含有关组织中当前迁移的信息。 下面是包含有关迁移延迟信息的表示例。

| BatchName | ExchangeGuid | RequestGuid | DelayReason |QueuedHours | DelayInHours | SourceServer | RemoteDatabaseName |
|:---------|:---------|:---------|:---------|:---------|:---------|:---------|:---------|
|MRS 迁移|246c21f7-ca3c-4bba-ab5d-23456558c52a|3d7fab16-7d8e-4c81-a849-e0795054292a|DiskLatency|35.2|27.3|RD1GBL01EXCH003|GBL01EDAG001-db002|
|MRS 租户监视|21e9a608-78c3-44ef-a4dd-d5e7222aae82|9974aeb4-2aa4-4a2c-aeb6-d94d78cc25c9|DiskLatency|0.4|0.9|RD1GBL01EXCH010|GBL01EDAG010-db003|

下面的列表描述了上一示例中的每个列。

- **BatchName：** 迁移作业的唯一名称。

- **ExchangeGuid：** 要 (的用户) GUID 的全局唯一标识符。

- **RequestGuid**：迁移请求的 GUID。

- **DelayReason：** 延迟迁移的原因。

- **QueueHours：** 迁移已排队等待的持续时间。

- **DelayInHours：** 迁移延迟的持续时间。

- **SourceServer：** 迁移源自本地服务器。

- **RemoteDatabaseName：** 迁移源自的数据库名称。

## <a name="more-information"></a>更多信息

有关 MRS 和邮箱迁移详细信息，请参阅以下文章：

- [邮箱在Exchange](/exchange/recipients/mailbox-moves)

- [Microsoft 365和Office 365迁移性能和最佳做法](/exchange/mailbox-migration/office-365-migration-best-practices)

- [邮箱迁移性能分析](https://techcommunity.microsoft.com/t5/exchange-team-blog/mailbox-migration-performance-analysis/ba-p/587134)

- [缓慢迁移疑难解答](https://techcommunity.microsoft.com/t5/exchange-team-blog/troubleshooting-slow-migrations/ba-p/1795706)

- [将多个电子邮件帐户迁移到 Microsoft 365 的方法](/exchange/mailbox-migration/mailbox-migration)
