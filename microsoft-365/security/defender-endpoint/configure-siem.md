---
title: 将 SIEM 工具与Microsoft Defender for Endpoint集成
description: 了解如何引入事件和警报，以及如何集成 SIEM 工具。
keywords: 配置 siem、安全信息和事件管理工具、splunk、arcsight、自定义指示器、rest api、警报定义、入侵指示器
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: d679ac0d01a7e922e49b72b574a43e6f684179f9
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64664493"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>将 SIEM 工具与Microsoft Defender for Endpoint集成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>使用安全信息和事件管理 (SIEM) 工具引入警报

> [!NOTE]
>
> [Microsoft Defender for Endpoint警报](alerts.md)由设备上发生的一个或多个可疑或恶意事件及其相关详细信息组成。 Microsoft Defender for Endpoint警报 API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。 有关详细信息，请参阅[警报方法、属性和](alerts.md)[列表警报](get-alerts.md)。

Microsoft Defender for Endpoint支持使用已注册AAD的 OAuth 2.0 身份验证协议 (SIEM) 工具Azure Active Directory (AAD) 从企业租户引入信息的安全信息和事件管理AAD 表示环境中安装的特定 SIEM 解决方案或连接器的应用程序。

有关更多信息，请参阅：

- [Microsoft Defender for Endpoint API 许可证和使用条款](api-terms-of-use.md) 
- [访问 Microsoft Defender for Endpoint API](apis-intro.md)
- [Hello World示例 (介绍如何在Azure Active Directory) 中注册应用程序](api-hello-world.md)
- [ 通过应用上下文获得访问权限](exposed-apis-create-app-webapp.md)


Microsoft Defender for Endpoint当前支持以下 SIEM 解决方案集成： 

- [从Microsoft 365 Defender引入事件和警报，Microsoft Defender for Endpoint事件和警报 REST API](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [从Microsoft 365 Defender事件流式处理 API 引入Microsoft Defender for Endpoint事件](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>从Microsoft 365 Defender引入事件和警报，Microsoft Defender for Endpoint事件和警报 REST API

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>从Microsoft 365 Defender事件中引入事件 REST API

有关Microsoft 365 Defender事件 API 的详细信息，请参阅[事件方法和属性](../defender/api-incident.md)。

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>从 Microsoft Defender for Endpoint 警报 REST API 引入警报

有关Microsoft Defender for Endpoint警报 API 的详细信息，[请参阅警报方法和属性](alerts.md)。

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>SIEM 工具与Microsoft Defender for Endpoint集成

### <a name="splunk"></a>Splunk

使用支持以下内容的 Splunk 的Microsoft 365 Defender加载项：

- 引入Microsoft Defender for Endpoint警报
- 从 Splunk 内部更新Microsoft Defender for Endpoint中的警报

有关 splunk Microsoft 365 Defender加载项的详细信息，请参阅 [splunkbase](https://splunkbase.splunk.com/app/4959/)。

### <a name="micro-focus-arcsight"></a>微焦点 ArcSight

新的 SmartConnector 用于Microsoft 365 Defender引入事件，这些事件包含来自所有Microsoft 365 Defender产品的警报（包括从Microsoft Defender for Endpoint）到 ArcSight，并将这些警报映射到其 Common Event Framework (CEF) 。

有关新的 ArcSight SmartConnector for Microsoft 365 Defender 的详细信息，请参阅 [ArcSight 产品文档](https://www.microfocus.com/documentation/arcsight/arcsight-smartconnectors/microsoft-365-defender/index.html)。

SmartConnector 将替换上一个 FlexConnector for Microsoft 365 Defender。

### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>IBM QRadar 与 Microsoft 365 Defender 集成（包括 Microsoft Defender for Endpoint）现在受调[用 DSM) 的新Microsoft 365 Defender设备支持模块 (支持Microsoft 365 Defender流式处理 API](../defender/streaming-api.md)，允许从Microsoft 365 Defender产品（包括Microsoft Defender for Endpoint）引入流式处理事件数据。 有关新的 QRadar Microsoft 365 Defender DSM 的详细信息，请参阅 [IBM QRadar 产品文档](https://www.ibm.com/docs/en/dsm?topic=microsoft-365-defender)，有关流式处理 API 支持的事件类型的详细信息，请参阅[支持的事件类型](../defender/supported-event-types.md)。

不再使用以前的 QRadar Microsoft Defender ATP 设备支持模块 (DSM) 载入新客户，建议现有客户采用新的 Microsoft 365 Defender DSM 作为与所有Microsoft 365 Defender产品的单一集成点。

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>从Microsoft 365 Defender事件流式处理 API 引入Microsoft Defender for Endpoint事件

Microsoft 365 Defender流式处理事件数据包括来自 Microsoft Defender for Endpoint 和其他 Microsoft Defender 产品的警报和其他事件。 这些事件可以流式传输到Azure 存储帐户或Azure 事件中心。 Splunk 和 IBM QRadar 目前支持通过事件中心的集成模型。

有关详细信息，请参阅 [MICROSOFT 365 DEFENDER SIEM 集成](../defender/configure-siem-defender.md)。
