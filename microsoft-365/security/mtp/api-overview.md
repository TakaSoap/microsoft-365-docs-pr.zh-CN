---
title: Microsoft 365 Defender API 概述
description: 了解 Microsoft 365 Defender 中的可用 API
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
ms.openlocfilehash: 0fbe8751a9f82a8e264f1a38207744d091b57474
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922182"
---
# <a name="overview-of--microsoft-365-defender-apis"></a>Microsoft 365 Defender API 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

> [!IMPORTANT]
> 某些信息与预发布产品相关，该产品在商业发行之前可能会进行重大修改。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

Microsoft 365 Defender 基于集成就绪平台构建。

使用 Microsoft 365 Defender API 根据共享事件和高级搜寻表自动执行工作流。

- **[组合事件队列](api-incident.md)** - 通过按事件 API 将整个攻击范围和所有影响的资产分组在一起，重点关注关键内容。

- **[跨产品威胁搜寻](api-advanced-hunting.md)** - 通过创建自己的自定义查询来筛选跨多个保护产品收集的原始数据，利用安全团队的组织知识搜寻泄露的迹象。

除了这些特定于 Microsoft 365 Defender 的 API 外，我们每个[](api-articles.md)其他安全产品都公开了其他 API，以帮助你充分利用它们的独特功能。

## <a name="learn-more"></a>了解更多

| **了解如何访问 API** |
|-|
| [了解 API 配额和许可](api-terms.md) |
| [访问 Microsoft 365 Defender API](api-access.md) |
| **构建应用程序** |
| [创建"Hello world"应用](api-hello-world.md) |
| [创建应用以代表用户访问 Microsoft 365 Defender API](api-create-app-user-context.md) |
| [创建应用以在没有用户的情况下访问 Microsoft 365 Defender](api-create-app-web.md) |
| [创建具有对 Microsoft 365 Defender API 的多租户合作伙伴访问权限的应用](api-partner-access.md) |
| **对应用进行故障排除和维护** |
| [了解 API 错误代码](api-error-codes.md) |
| [使用 Azure Key Vault 管理应用中的密钥](/learn/modules/manage-secrets-with-azure-key-vault/) |
| [为用户登录实现 OAuth 2.0 授权](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code) |