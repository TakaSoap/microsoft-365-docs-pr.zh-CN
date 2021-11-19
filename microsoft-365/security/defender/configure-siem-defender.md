---
title: 将 SIEM 工具与 Microsoft 365 Defender 集成
description: 了解如何使用 REST API 并配置支持的安全信息和事件管理工具以接收和拉取检测。
keywords: 配置 siem， 安全信息和事件管理工具， splunk， arcsight， 自定义指示器， rest api， 警报定义， 泄露指示器
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 210705bd3392e4aeeadd815ed8c1840e772f6ad9
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110423"
---
# <a name="integrate-your-siem-tools-with-microsoft-365-defender"></a>将 SIEM 工具与 Microsoft 365 Defender 集成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

## <a name="pull-microsoft-365-defender-incidents-and-streaming-event-data-using-security-information-and-events-management-siem-tools"></a>使用 SIEM Microsoft 365 Defender工具中的安全信息和事件管理拉取事件和 (事件) 数据

> [!NOTE]
>
> - [Microsoft 365 Defender事件](incident-queue.md)由相关警报及其证据的集合组成。
> - [Microsoft 365 Defender流式处理 API](streaming-api.md)将事件数据Microsoft 365 Defender事件中心或 Azure 存储帐户。

Microsoft 365 Defender使用注册租户的 OAuth 2.0 身份验证协议，支持安全信息和事件管理 (SIEM) 工具从 Azure Active Directory (AAD) 中的企业租户获取AAD 表示环境中安装的特定 SIEM 解决方案或连接器的应用程序。 

有关更多信息，请参阅：

- [Microsoft 365 Defender API 许可证和使用条款](api-terms.md)
- [访问Microsoft 365 Defender API](api-access.md)
- [Hello World 示例](api-hello-world.md)
- [ 通过应用上下文获得访问权限](api-create-app-web.md)

有两种主要模型可获取安全信息： 

1.  从 Azure Microsoft 365 Defender REST API 获取事件及其包含的警报。 

2.  通过 Azure 事件中心或帐户获取流Azure 存储数据。 

Microsoft 365 Defender目前支持以下 SIEM 解决方案集成： 

- [从事件 REST API 中提供事件](#ingesting-incidents-from-the-incidents-rest-api)
- [通过事件中心获取流事件数据](#ingesting-streaming-event-data-via-event-hubs)

## <a name="ingesting-incidents-from-the-incidents-rest-api"></a>从事件 REST API 中提供事件

### <a name="incident-schema"></a>事件架构
有关事件属性Microsoft 365 Defender包括警报和证据实体元数据）详细信息，请参阅架构[映射](../defender/api-list-incidents.md#schema-mapping)。

### <a name="splunk"></a>Splunk

使用Microsoft 365 Defender Splunk 加载项支持：

- 包含以下产品警报的接收事件，这些事件映射到 Splunk 的 Common Information Model (CIM) ：

  - Microsoft 365 Defender
  - Microsoft Defender for Endpoint
  - 用于标识和标识保护Azure Active Directory Microsoft Defender
  - Microsoft Defender for Cloud Apps

- 从 Splunk Microsoft 365 Defender事件

- 从 Defender for Endpoint 的 Azure (为终结点启用 Defender for Endpoint) 并更新这些警报

有关 Splunk Microsoft 365 Defender加载项的信息，请参阅[splunkbase](https://splunkbase.splunk.com/app/4959/)。

### <a name="micro-focus-arcsight"></a>Micro Focus ArcSight

新的 SmartConnector 用于将Microsoft 365 Defender事件集成到 ArcSight 中，并映射到其 Common Event Framework (CEF) 。

有关用于安装的新 ArcSight SmartConnector Microsoft 365 Defender，请参阅[ArcSight 产品文档](https://community.microfocus.com/cyberres/productdocs/w/connector-documentation/39246/smartconnector-for-microsoft-365-defender)。

SmartConnector 取代了 Microsoft Defender for Endpoint 的上一个 FlexConnector。
  

## <a name="ingesting-streaming-event-data-via-event-hubs"></a>通过事件中心获取流事件数据

首先，你需要将事件从 AAD 租户流式传输至事件中心或Azure 存储帐户。 有关详细信息，请参阅流[式处理 API。](../defender/streaming-api.md)

有关流式处理 API 支持的事件类型详细信息，请参阅支持的 [流式处理事件类型](../defender/supported-event-types.md)。

### <a name="splunk"></a>Splunk
使用 Microsoft 云服务的 Splunk 加载项从 Azure 事件中心获取事件。  


有关适用于 Microsoft 云服务的 Splunk 加载项详细信息，请参阅 [splunkbase](https://splunkbase.splunk.com/app/3110/)。
  

### <a name="ibm-qradar"></a>IBM QRadar
>使用新的 IBM QRadar Microsoft 365 Defender 设备支持模块 (DSM) ，该模块调用允许从 Microsoft 365 Defender 产品中采用流式传输事件数据的 Microsoft 365 Defender 流式处理[API。](streaming-api.md) 有关受支持的事件类型详细信息，请参阅支持 [的事件类型](supported-event-types.md)。
