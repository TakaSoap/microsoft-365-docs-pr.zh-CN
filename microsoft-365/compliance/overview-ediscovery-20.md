---
title: Microsoft 365 中的高级电子数据展示解决方案概述
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
- m365solution-aed
- m365initiative-compliance
- m365solution-overview
search.appverid:
- MOE150
- MET150
description: 了解 Microsoft 365 中的高级电子数据展示解决方案。 本文概述了 Microsoft 365 中的高级电子数据展示，这是一种可帮助您管理内部和外部调查的工具。 它还包含使用高级电子数据展示管理法律调查的业务原因。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0f6ae536f84190f81248bbf68ff66f438727e068
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50927642"
---
# <a name="overview-of-microsoft-365-advanced-ediscovery"></a>Microsoft 365 高级电子数据展示概述

Microsoft 365 中的高级电子数据展示解决方案基于现有 Microsoft 电子数据展示和分析功能构建。 高级电子数据展示提供端到端工作流，以保留、收集、分析、审阅、分析和导出对组织内部和外部调查做出响应的内容。 它还允许法律团队管理整个法定保留通知工作流，以与案件涉及的保管人进行通信。

## <a name="advanced-ediscovery-capabilities"></a>高级电子数据展示功能

高级电子数据展示可通过发现组织所存储的数据来帮助组织对法律事务或内部调查做出响应。 您可以通过识别感兴趣的人员及其数据源无缝管理电子数据展示工作流，无缝应用保留以保留数据，然后管理合法保留通信过程。 通过从源收集数据，你可以搜索实时 Microsoft 365 平台以快速找到所需的内容。 智能的机器学习功能（如深度索引、电子邮件线程和近重复检测）还有助于将大量的数据减少为相关的数据集。

以下各节介绍这些高级电子数据展示功能如何帮助你的组织。

![高级电子数据展示功能](../media/advanced-ediscovery-capabilities.png)

### <a name="discover-and-collect-data-in-place"></a>就地发现和收集数据

通常，依赖于多个第三方电子数据展示解决方案的组织需要从 Microsoft 365 复制大量数据以处理数据，并且必须承载重复数据。 这一要求会增加查找相关数据的时间，以及管理多个解决方案的风险、成本和复杂性。

通过 Microsoft 365 中的高级电子数据展示，你可以发现源数据并一直位于 Microsoft 365 安全性和合规性边界内。  通过从实时系统就地收集数据，高级电子数据展示可以减少返回到源的接触，并减少查找缺少的内容的不必要工作，在传统电子数据展示解决方案中记录滞后时通常会发生此情况。

Teams、Yammer、SharePoint Online、OneDrive for Business 和 Exchange Online 中数据的本机搜索和收集功能进一步增强了数据发现。 例如，高级电子数据展示：

- 重新构造 Teams 对话 (而不是从用户对话中返回) 。

- 收集使用电子邮件和 Teams 聊天中的链接或新式附件与用户共享的基于云的内容。

- 具有对数百种非 Microsoft 365 文件类型的内置支持。

- 从数据连接器导入 (Microsoft 365 中导入和存档的第三方源（如) 、Facebook、Slack 和 Zoom 会议） [收集数据](archiving-third-party-data.md)。

### <a name="manage-ediscovery-workflow-in-one-platform"></a>在一个平台中管理电子数据展示工作流

高级电子数据展示可帮助你减少需要依赖的电子数据展示解决方案的数量。 它提供了简化的端到端工作流，所有这些都发生在 Microsoft 365 中。 高级电子数据展示通过自动将唯一和共享数据源映射到感兴趣的人员 (称为保管人 *) ，* 以及提供对潜在相关信息的报告和分析，在收集这些数据进行分析和审阅之前，有助于减少识别和收集潜在相关信息源的接触。

此外，Microsoft Graph API 还可以帮助您自动执行电子数据展示工作流，并扩展自定义解决方案的高级电子数据展示。

### <a name="cull-data-intelligently"></a>智能剔除数据

高级电子数据展示中的智能机器学习功能可帮助你减少要查看的数据量。 这些智能功能可帮助你减少大量的数据并剔除到相关集合。 例如，内置审阅集查询通过标识几乎重复项来帮助仅筛选唯一内容。 此功能可显著减少要审阅的数据量。

其他机器学习功能可以使用智能标记和技术辅助审阅工具（如相关性模块）进一步优化和识别数据。

## <a name="advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model"></a>电子数据展示与电子数据展示参考模型保持一致

Microsoft 365 中高级电子数据展示的内置工作流与电子数据展示模型 EDRM (概述的电子数据展示) 。

![电子数据发现参考模型 (EDRM) ](../media/EDRMv1.png)

 (图像源的 edrm.net。 源图像在 Creative Commons Attribution 3.0 未ported License.) 

高级电子数据展示在高级别上如何支持 EDRM 工作流：

- **标识。** 在确定了调查感兴趣的潜在人员后，可以添加他们作为保管人 (也称为数据保管人，因为他们可能拥有与调查) 高级电子数据展示案例有关的信息。 将用户添加为保管人后，可轻松保留、收集和查看保管人文档。

- **保留。** 为了保留和保护与调查相关的数据，高级电子数据展示允许您对与案例保管人关联的数据源进行合法保留。 还可以将非安全数据放在保留状态。 高级电子数据展示还内置了通信工作流，因此你可以向保管人发送合法保留通知并跟踪其确认。

- **集合。** 标识 (并保留) 调查相关的数据源后，可以使用高级电子数据展示搜索中的内置搜索工具，从可能与案例相关的主要数据源 () 和非实时数据源（如果适用）中收集实时数据。

- **处理。** 收集与案例相关的所有数据后，下一步是处理该数据以进一步查看和分析。 在高级电子数据展示中，你在收集阶段标识的就地数据将复制到 Azure 存储位置 (称为审阅集 *) ，* 它提供案例数据的静态视图。 

- **查看。** 将数据添加到审阅集后，您可以查看特定文档并运行其他查询，以将数据减少为与案例最相关的内容。 此外，还可以为特定文档添加批注和标记。

- **分析。** 高级电子数据展示提供了集成的分析工具，可帮助你进一步从你确定与调查不相关的审阅集剔除数据。 除了减少数据量外，高级电子数据展示还可以帮助您节省法律审阅成本，通过组织内容使审阅过程更加轻松和高效。

- **生产和****演示。** 准备就绪后，可以从审阅集导出文档进行法律审阅。 您可以以本机格式或 EDRM 指定格式导出文档，以便它们可以导入到第三方审阅应用程序中。

## <a name="subscriptions-and-licensing"></a>订阅和许可

高级电子数据展示的许可需要相应的组织订阅和每用户许可。

- **组织订阅：** 若要访问 Microsoft 365 合规中心中的高级电子数据展示，你的组织必须具有以下项之一：

  - Microsoft 365 E5 或 Office 365 E5 订阅
  
  - 具有 E5 合规性附加设备的 Microsoft 365 E3 订阅

  - 具有 E5 电子数据展示和审核加载项的 Microsoft 365 E3 订阅

  如果你没有现有的 Microsoft 365 E5 计划，并且想要试用高级电子数据展示，可以将[Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365)添加到现有订阅或注册 Microsoft [](https://www.microsoft.com/microsoft-365/enterprise) 365 E5 试用版。

- **每用户许可：** 若要在高级电子数据展示案例中将用户添加为保管人，必须为该用户分配以下许可证之一，具体取决于你的组织订阅：

  - Microsoft 365：必须为用户分配 Microsoft 365 E5 许可证、E5 合规性附加许可证或 E5 电子数据展示和审核加载项许可证。

  - Office 365：必须为用户分配 Office 365 E5 许可证。

   若要了解如何分配许可证，请参阅 [向用户分配许可证](https://docs.microsoft.com/microsoft-365/admin/manage/assign-licenses-to-users)。

> [!NOTE]
> 用户只需要 E5 许可证 (或相应的附加许可证) 作为保管人添加到高级电子数据展示案例。 使用高级电子数据展示来管理事例和审查事例数据的 IT 管理员、电子数据展示管理员、律师、律师或律师不需要 E5 或附加许可证。

## <a name="get-started-with-advanced-ediscovery"></a>高级电子数据展示入门

高级电子数据展示有两个快速而简单的入门步骤。

![高级电子数据展示工作流入门](../media/get-started-AeD.png)

|步骤  |说明  |
|:---------|:---------|
|[设置高级电子数据展示](get-started-with-advanced-ediscovery.md)| 在验证订阅和许可要求后，您可以分配权限并配置组织范围的设置以开始使用高级电子数据展示。|
|[创建和管理事例](create-and-manage-advanced-ediscoveryv2-case.md) | 创建案例以管理组织中所有法律和其他类型的调查的高级电子数据展示工作流。|
|||

## <a name="advanced-ediscovery-architecture"></a>高级电子数据展示体系结构

下面的高级电子数据展示体系结构图显示了单地理位置环境和多地理位置环境中端到端工作流，以及与 [EDRM](#advanced-ediscovery-alignment-with-the-electronic-discovery-reference-model)一致的端到端数据流。

[![模型海报：Microsoft 365 中的高级电子数据展示体系结构](../media/solutions-architecture-center/ediscovery-poster-thumb.png)](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[以图像视图](../media/solutions-architecture-center/m365-advanced-ediscovery-architecture.png)

[下载为 PDF 文件](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.pdf)

[下载为 Visio 文件](https://download.microsoft.com/download/d/1/c/d1ce536d-9bcf-4d31-b75b-fcf0dc560665/m365-advanced-ediscovery-architecture.vsdx)
