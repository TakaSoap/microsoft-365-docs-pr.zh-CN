---
title: 高级电子数据展示与 EDRM 的对齐方式
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- m365-security-compliance
search.appverid:
- MOE150
- MET150
description: Microsoft 365 中高级电子数据展示的内置工作流与电子数据展示模型 EDRM (概述的电子数据展示) 。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: f2e7886eb67a58b43e9fb638fafb358fd9ee832c
ms.sourcegitcommit: 3d48e198e706f22ac903b346cadda06b2368dd1e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/11/2021
ms.locfileid: "50727485"
---
# <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>电子数据展示与电子数据展示参考模型保持一致

Microsoft 365 中高级电子数据展示的内置工作流与电子数据展示模型 EDRM (概述的电子数据展示) 。

![电子数据发现参考模型 (EDRM) ](../media/EDRMv1.png)

 (图像源的edrm.net。 源图像在 Creative Commons Attribution 3.0 未ported License.) 

高级电子数据展示在高级别上如何支持 EDRM 工作流：

- **标识。** 在确定了调查感兴趣的潜在人员后，可以添加他们作为保管人 (也称为数据保管人，因为他们可能拥有与调查) 高级电子数据展示案例有关的信息。 将用户添加为保管人后，可轻松保留、收集和查看保管人文档。

- **保留。** 为了保留和保护与调查相关的数据，高级电子数据展示允许您对与案例保管人关联的数据源进行合法保留。 还可以将非安全数据放在保留状态。 高级电子数据展示还内置了通信工作流，因此你可以向保管人发送合法保留通知并跟踪其确认。

- **集合。** 标识 (并保留) 调查相关的数据源后，可以使用高级电子数据展示搜索中的内置搜索工具，从可能与案例相关的主要数据源 () 和非实时数据源（如果适用）中收集实时数据。

- **处理。** 收集与案例相关的所有数据后，下一步是处理该数据以进一步查看和分析。 在高级电子数据展示中，你在收集阶段标识的就地数据将复制到 Azure 存储位置 (称为审阅集 *) ，* 它提供案例数据的静态视图。 

- **查看。** 将数据添加到审阅集后，您可以查看特定文档并运行其他查询，以将数据减少为与案例最相关的内容。 此外，还可以为特定文档添加批注和标记。

- **分析。** 高级电子数据展示提供了集成的分析工具，可帮助你进一步从你确定与调查不相关的审阅集剔除数据。 除了减少数据量外，高级电子数据展示还可以帮助您节省法律审阅成本，通过组织内容使审阅过程更加轻松和高效。

- **生产和****演示。** 准备就绪后，可以从审阅集导出文档进行法律审阅。 您可以以本机格式或 EDRM 指定格式导出文档，以便它们可以导入到第三方审阅应用程序中。

## <a name="more-information"></a>更多信息

若要开始使用高级电子数据展示，请参阅：

- [设置高级电子数据展示](get-started-with-advanced-ediscovery.md)

- [创建和管理高级电子数据展示案例](create-and-manage-advanced-ediscoveryv2-case.md)