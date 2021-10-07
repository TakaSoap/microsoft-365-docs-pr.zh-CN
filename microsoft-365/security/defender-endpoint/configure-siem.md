---
title: 从 Microsoft Defender for Endpoint 将检测拉取到 SIEM 工具
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
ms.openlocfilehash: 80a56ac33b11962028e6735a28d8a4692226d306
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60209953"
---
# <a name="pull-detections-to-your-siem-tools"></a>将检测拉取到 SIEM 工具

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configuresiem-abovefoldlink)。

## <a name="pull-detections-using-security-information-and-events-management-siem-tools"></a>使用 SIEM 安全工具中的安全信息和事件 (拉) 检测

> [!NOTE]
>
> - [Microsoft Defender 终结点警报](alerts.md) 由一个或多个检测组成。
> - [Microsoft Defender for Endpoint Detection](api-portal-mapping.md) 由设备上发生的可疑事件及其相关的警报详细信息组成。
> -Microsoft Defender for Endpoint 警报 API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。 有关详细信息，请参阅[警报方法和属性和](alerts.md)[列表警报](get-alerts.md)。

Defender for Endpoint 支持 SIEM (安全信息和事件) 拉取检测。 Defender for Endpoint 通过 Azure 中托管的 HTTPS 终结点公开警报。 终结点可以配置为使用 OAuth 2.0 身份验证协议从 Azure Active Directory (AAD) 中的企业租户拉取检测，此协议适用于表示环境中安装的特定 SIEM 连接器的 AAD 应用程序。

Defender for Endpoint 当前通过专用 SIEM 集成模型支持以下特定 SIEM 解决方案工具：

- IBM QRadar
- Micro Focus ArcSight

其他 SIEM 解决方案 (Splunk、RSA NetWitness) 基于新的警报 API 的不同集成模型受到支持。 有关详细信息，请参阅合作伙伴 [应用程序页面并选择](https://securitycenter.microsoft.com/interoperability/partners) 安全信息和分析部分，获取完整详细信息。

若要使用这些受支持的 SIEM 工具之一，你将需要：

- [在 Defender for Endpoint 中启用 SIEM 集成](enable-siem-integration.md)
- 配置支持的 SIEM 工具：
  - [配置 Micro Focus ArcSight 以拉取 Defender 进行终结点检测](configure-arcsight.md)
  - 配置 IBM QRadar 以拉取 Defender for Endpoint detections 有关详细信息，请参阅 [IBM 知识库](https://www.ibm.com/support/knowledgecenter/SS42VS_DSM/com.ibm.dsm.doc/c_dsm_guide_MS_Win_Defender_ATP_overview.html?cp=SS42VS_7.3.1)。

有关在检测 API 中公开的字段列表详细信息，请参阅 [Defender for Endpoint Detection fields](api-portal-mapping.md)。
