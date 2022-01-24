---
title: 将 SIEM 工具与 Microsoft Defender for Endpoint 集成
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
ms.openlocfilehash: 4c0462bcfae77677fca05132aaf0895b897bf788
ms.sourcegitcommit: 6f3bc00a5cf25c48c61eb3835ac069e9f41dc4db
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/24/2022
ms.locfileid: "62172243"
---
# <a name="integrate-your-siem-tools-with-microsoft-defender-for-endpoint"></a>将 SIEM 工具与 Microsoft Defender for Endpoint 集成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


## <a name="ingest-alerts-using-security-information-and-events-management-siem-tools"></a>使用 SIEM 工具中的安全信息和事件 (接收) 警报

> [!NOTE]
>
> [Microsoft Defender 终结点警报](alerts.md) 由设备上发生的一个或多个可疑或恶意事件及其相关详细信息组成。 Microsoft Defender for Endpoint 警报 API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。 有关详细信息，请参阅[警报方法和属性和](alerts.md)[列表警报](get-alerts.md)。

Microsoft Defender for Endpoint 支持安全信息和事件管理 (SIEM) 工具使用 OAuth 2.0 身份验证协议从 Azure Active Directory (AAD) 中的企业租户获取信息，此协议适用于表示环境中安装的特定 SIEM 解决方案或连接器的注册 AAD 应用程序。

有关更多信息，请参阅：

- [适用于终结点 API 的 Microsoft Defender 许可证和使用条款](api-terms-of-use.md) 
- [访问 Microsoft Defender for Endpoint API](apis-intro.md)
- [Hello World 示例 (介绍如何在应用程序中注册Azure Active Directory) ](api-hello-world.md)
- [ 通过应用上下文获得访问权限](exposed-apis-create-app-webapp.md)


Microsoft Defender for Endpoint 当前支持以下 SIEM 解决方案集成： 

- [从 Microsoft Defender 和 Microsoft Defender 为终结点事件和警报 REST API Microsoft 365 Defender事件和警报](#ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis)
- [从事件流 API 中为终结点事件Microsoft 365 Defender Microsoft Defender](#ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api)

## <a name="ingesting-incidents-and-alerts-from-the-microsoft-365-defender-and-microsoft-defender-for-endpoint-incidents-and-alerts-rest-apis"></a>从 Microsoft Defender 和 Microsoft Defender 为终结点事件和警报 REST API Microsoft 365 Defender事件和警报

### <a name="ingesting-incidents-from-the-microsoft-365-defender-incidents-rest-api"></a>从事件 REST API Microsoft 365 Defender事件

有关事件 API Microsoft 365 Defender，请参阅[事件方法和属性](../defender/api-incident.md)。

### <a name="ingesting-alerts-from-the-microsoft-defender-for-endpoint-alerts-rest-api"></a>从 Microsoft Defender for Endpoint 警报 REST API 中接收警报

有关适用于终结点警报 API 的 Microsoft Defender 详细信息，请参阅 [警报方法和属性](alerts.md)。

## <a name="siem-tool-integration-with-microsoft-defender-for-endpoint"></a>SIEM 工具与 Microsoft Defender for Endpoint 集成

### <a name="splunk"></a>Splunk

使用Microsoft 365 Defender Splunk 加载项支持：

- 为终结点警报接收 Microsoft Defender
- 在 Microsoft Defender for Endpoint 中从 Splunk 更新警报

有关 Splunk 加载项Microsoft 365 Defender，请参阅[splunkbase](https://splunkbase.splunk.com/app/4959/)。

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

适用于 Microsoft 365 Defender 的新 SmartConnector 将包含来自所有 Microsoft 365 Defender 产品（包括来自 Microsoft Defender for Endpoint）的警报的事件映射到 ArcSight，并映射到其通用事件框架 (CEF) 。

有关用于安装的新 ArcSight SmartConnector Microsoft 365 Defender，请参阅[ArcSight 产品文档](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender)。

SmartConnector 替换了之前为 Microsoft 365 Defender。

### <a name="ibm-qradar"></a>IBM QRadar

>[!NOTE]
>IBM QRadar 与 Microsoft 365 Defender 集成，其中包括 Microsoft Defender for Endpoint，现在受新的 Microsoft 365 Defender 设备支持模块 (DSM) 支持，该模块调用允许从中纳入流式传输事件数据的[Microsoft 365 Defender 流](../defender/streaming-api.md)式处理 APIMicrosoft 365 Defender产品，包括 Microsoft Defender for Endpoint。 有关新的 QRadar Microsoft 365 Defender DSM 的信息，请参阅[IBM QRadar 产品](https://www.ibm.com/docs/en/dsm?topic=microsoft-365-defender)文档，有关流式 API 支持的事件类型详细信息，请参阅支持[的事件类型](../defender/supported-event-types.md)。

不再使用之前的 QRadar Microsoft Defender ATP 设备支持模块 (DSM) 载入新客户，建议现有客户采用新的 Microsoft 365 Defender DSM 作为他们与所有 Microsoft 365 Defender 产品的单一集成点。

## <a name="ingesting-microsoft-defender-for-endpoint-events-from-the-microsoft-365-defender-event-streaming-api"></a>从事件流 API 中为终结点事件Microsoft 365 Defender Microsoft Defender

Microsoft 365 Defender流事件数据包括来自 Microsoft Defender for Endpoint 和其他 Microsoft Defender 产品的警报和其他事件。 这些事件可能会流式处理到 Azure 存储 帐户或 Azure 事件中心。 Splunk 和 IBM QRadar 当前支持通过事件中心的集成模型。

有关详细信息，请参阅[SIEM Microsoft 365 Defender集成](../defender/configure-siem-defender.md)。
