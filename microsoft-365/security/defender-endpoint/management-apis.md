---
title: 管理和 API 概述
ms.reviewer: ''
description: 了解 Microsoft Defender for Endpoint 中的管理工具和 API 类别
keywords: 载入， api， siem， rbac， 访问， 门户， 集成， 调查， 响应， 实体， 实体， 用户上下文， 应用程序上下文， 流
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 196c517c20e80b753bf6065c1c4e3014c0e16638
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154769"
---
# <a name="overview-of-management-and-apis"></a>管理和 API 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-mgt-apis-abovefoldlink)。


Defender for Endpoint 支持多种选项，以确保客户可以轻松采用平台。

确认客户环境和结构可能会有所不同，创建 Defender for Endpoint 时具有灵活性和精细控制，以满足不同的客户要求。

## <a name="endpoint-onboarding-and-portal-access"></a>终结点载入和门户访问

设备载入已完全集成到 Microsoft Endpoint Manager 和 Microsoft Intune 客户端设备和适用于服务器设备的 Azure Defender 中，从而提供配置、部署和监视的完整端到端体验。 此外，Microsoft Defender for Endpoint 还支持用于设备管理的组策略和其他第三方工具。

Defender for Endpoint 提供对有权访问门户的用户的精细控制，可通过基于角色的访问控制和 RBAC (灵活查看和) 。 RBAC 模型支持所有安全团队结构：

- 全局分布的组织和安全团队
- 分层模型安全运营团队
- 具有单个集中式全局安全运营团队的完全隔离的部门

## <a name="available-apis"></a>可用的 API

Microsoft Defender for Endpoint 解决方案基于集成就绪平台构建。

Defender for Endpoint 通过一组编程 API 公开其大部分数据和操作。 这些 API 将使您能够基于 Defender for Endpoint 功能自动执行工作流创新。

![Microsoft Defender for Endpoint 中可用 API 和集成的图像。](images/mdatp-apis.png)

Defender for Endpoint API 可以分为三组：

- 适用于终结点的 Microsoft Defender API
- 原始数据流式处理 API
- SIEM 集成

## <a name="microsoft-defender-for-endpoint-apis"></a>适用于终结点的 Microsoft Defender API

Defender for Endpoint 提供分层 API 模型，在结构化、清晰且易于使用的模型中公开数据和功能，该模型通过基于 Azure AD 的标准身份验证和授权模型公开，从而允许用户或 SaaS 应用程序上下文访问。 API 模型旨在以一致的形式公开实体和功能。

观看此视频，快速概览 Defender for Endpoint 的 API。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4d73M]

调查 **API** 公开了适用于终结点的 Defender 的丰富功能 - 公开计算实体或"配置文件"实体 (例如设备、用户和文件) 和离散事件 (例如进程创建和文件创建) 这通常描述与实体相关的行为，从而允许通过调查界面访问数据，从而允许基于查询的数据访问。 有关详细信息，请参阅受支持的[API。](exposed-apis-list.md)

响应 **API** 公开了在服务和设备上采取操作的功能，使客户能够接收指示器、管理设置、警报状态，以及以编程方式对设备执行响应操作，如将设备与网络隔离、隔离文件和其他操作。

## <a name="raw-data-streaming-api"></a>原始数据流式处理 API

Defender for Endpoint 原始数据流 API 使客户能够在单个数据流中发生时从其实例传送实时事件和警报，从而提供低延迟、高吞吐量的传送机制。

Defender for Endpoint 事件信息直接推送到 Azure 存储以用于长期数据保留，或推送到 Azure 事件中心，供可视化服务或其他数据处理引擎使用。

有关详细信息，请参阅 [Raw data streaming API](raw-data-export.md)。

新的流式Microsoft 365 Defender API 包括电子邮件和警报事件以及设备事件。
有关详细信息，请参阅流式[Microsoft 365 Defender API。](../defender/streaming-api.md)

## <a name="siem-api"></a>SIEM API

在 SIEM (启用安全信息和事件) 集成时，它允许你使用 SIEM 解决方案或直接连接到检测 REST API 从 Microsoft Defender 安全中心 拉取检测。 这会使用预填充的值激活 SIEM 连接器访问详细信息部分，并且应用程序是在 Azure AD Azure Active Directory (租户) 创建的。 有关详细信息，请参阅 [SIEM 集成](enable-siem-integration.md)。

## <a name="related-topics"></a>相关主题

- [访问 Microsoft Defender for Endpoint API](apis-intro.md)
- [受支持的 API](exposed-apis-list.md)
- [技术合作伙伴商机](partner-integration.md)