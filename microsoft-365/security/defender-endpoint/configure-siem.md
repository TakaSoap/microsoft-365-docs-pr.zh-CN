---
title: 将 SIEM 工具与Microsoft Defender for Endpoint
description: 了解如何接收事件和警报，以及如何集成 SIEM 工具。
keywords: 配置 siem， 安全信息和事件管理工具， splunk， arcsight， 自定义指示器， rest api， 警报定义， 泄露指示器
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
ms.openlocfilehash: ed88048b506ecfcddb8394667e7d800927fc1d83
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634902"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>将 SIEM 工具与Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>使用 SIEM 工具中的安全信息和事件管理 (接收) 警报

> [!NOTE]
>
> [Microsoft Defender for Endpoint警报](alerts.md)由设备上发生的一个或多个可疑或恶意事件及其相关详细信息组成。 警报Microsoft Defender for Endpoint API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。 有关详细信息，请参阅 [Alert 方法和属性和](alerts.md) [List alerts](get-alerts.md)。

Microsoft Defender for Endpoint使用注册租户的 OAuth 2.0 身份验证协议在 Azure Active Directory (AAD) 中支持安全信息和事件管理 (SIEM) 工具从企业租户AAD 表示环境中安装的特定 SIEM 解决方案或连接器的应用程序。

有关更多信息，请参阅：

- [Microsoft Defender for Endpoint API 许可证和使用条款](api-terms-of-use.md) 
- [访问 Microsoft Defender for Endpoint API](apis-intro.md)
- [Hello World示例 (介绍如何在应用程序中注册Azure Active Directory) ](api-hello-world.md)
- [ 通过应用上下文获得访问权限](exposed-apis-create-app-webapp.md)


Microsoft Defender for Endpoint目前支持以下 SIEM 解决方案集成： 

- [从事件和警报 REST API Microsoft 365 Defender Microsoft Defender for Endpoint事件和警报](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [从 Microsoft Defender for Endpoint事件流 API Microsoft 365 Defender事件](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>从事件和警报 REST API Microsoft 365 Defender Microsoft Defender for Endpoint事件和警报

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>从事件 REST API Microsoft 365 Defender事件

有关事件 API Microsoft 365 Defender，请参阅[事件方法和属性](../defender/api-incident.md)。

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>从警报 REST API Microsoft Defender for Endpoint警报

有关通知 API Microsoft Defender for Endpoint，请参阅[通知方法和属性](alerts.md)。

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>SIEM 工具与 Microsoft Defender for Endpoint

### <a name="splunk"></a>Splunk

使用Microsoft 365 Defender Splunk 的加载项：

- Ingesting Microsoft Defender for Endpoint alerts
- 从 Splunk 中Microsoft Defender for Endpoint警报

有关 Splunk Microsoft 365 Defender加载项的信息，请参阅 [splunkbase](https://splunkbase.splunk.com/app/4959/)。

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

适用于 Microsoft 365 Defender 的新 SmartConnector 将包含来自所有 Microsoft 365 Defender 产品（包括 Microsoft Defender for Endpoint）的警报的事件映射到 ArcSight，并映射到其通用事件框架 (CEF) 。

有关新的 ArcSight SmartConnector for Microsoft 365 Defender，请参阅 [ArcSight 产品文档](https://www.microfocus.com/documentation/arcsight/arcsight-smartconnectors/microsoft-365-defender/index.html)。

SmartConnector 替换了之前为 Microsoft 365 Defender。

### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>IBM QRadar 与 Microsoft 365 Defender 集成，Microsoft Defender for Endpoint) [ (Microsoft 365 Defender现在受调用Microsoft 365 Defender流式处理 API](../defender/streaming-api.md)，允许从 Microsoft 365 Defender 产品（包括流式传输）Microsoft Defender for Endpoint。 有关新的 QRadar Microsoft 365 Defender DSM，请参阅 [IBM QRadar 产品](https://www.ibm.com/docs/en/dsm?topic=microsoft-365-defender)文档，有关流式 API 支持的事件类型详细信息，请参阅受支持的[事件类型](../defender/supported-event-types.md)。

不再使用之前的 QRadar Microsoft Defender ATP 设备支持模块 (DSM) 载入新客户，建议现有客户采用新的 Microsoft 365 Defender DSM 作为他们与所有 Microsoft 365 Defender 产品的单一集成点。

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>从 Microsoft Defender for Endpoint事件流 API Microsoft 365 Defender事件

Microsoft 365 Defender流式处理事件数据包括来自其他 Microsoft Defender Microsoft Defender for Endpoint的警报和其他事件。 这些事件可以流式处理到Azure 存储帐户或Azure 事件中心。 Splunk 和 IBM QRadar 当前支持通过事件中心的集成模型。

有关详细信息，请参阅 [siEM Microsoft 365 Defender SIEM 集成](../defender/configure-siem-defender.md)。
