---
title: Microsoft 365 Defender API 概述
description: 了解 Microsoft 365 Defender
keywords: api， api， 概述， 事件， 事件， 威胁搜寻， microsoft 365 defender
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2ce2e6e1efc87f0bcbfdbe6d650f35ea91da8422
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213561"
---
# <a name="overview-of-microsoft-365-defender-apis"></a>Microsoft 365 Defender API 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布的产品有关，在商业发布之前可能有重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

Microsoft 365 Defender构建于集成就绪平台的顶部。

使用 Microsoft 365 Defender API 根据共享事件和高级搜寻表自动执行工作流。

- **[组合事件队列](api-incident.md)** - 通过按事件 API 将整个攻击范围和所有影响的资产分组在一起，重点关注关键内容。

- **[跨产品威胁搜寻](api-advanced-hunting.md)** - 通过创建自己的自定义查询来筛选跨多个保护产品收集的原始数据，利用安全团队的组织知识搜寻泄露的迹象。

- **[事件流式处理 API](streaming-api.md)** - 在单个数据流中提供实时事件和警报。

除了这些Microsoft 365 Defender API 外，我们的每个其他安全产品都公开了其他[API，](api-articles.md)以帮助你充分利用它们的独特功能。

> [!NOTE]
> 转换到统一门户应该不会影响基于 Microsoft Defender for Endpoint API 的 PowerBi 仪表板。 无论交互式门户转换如何，都可以继续使用现有 API。

## <a name="learn-more"></a>了解详细信息

| **了解如何访问 API** |
|-|
| [了解 API 配额和许可](api-terms.md) |
| [访问Microsoft 365 Defender API](api-access.md) |
| **构建应用程序** |
| [创建"Hello world"应用](api-hello-world.md) |
| [创建应用以Microsoft 365 Defender访问 API](api-create-app-user-context.md) |
| [创建应用以在没有Microsoft 365 Defender的情况下访问用户](api-create-app-web.md) |
| [创建具有对应用程序 API 的多租户Microsoft 365 Defender应用程序](api-partner-access.md) |
| **对应用进行故障排除和维护** |
| [了解 API 错误代码](api-error-codes.md) |
| [使用 Azure Key Vault 管理应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [为用户登录实现 OAuth 2.0 授权](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |
