---
title: Microsoft Defender for Endpoint 中的 API 资源管理器
ms.reviewer: ''
description: 使用 API 资源管理器构造和执行 API 查询、测试和发送任何可用 API 的请求
keywords: api， 资源管理器， 发送， 请求， 获取， 发布，
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 3235ed9e3b4f51b9156267e324573f04443eccc6
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60210037"
---
# <a name="api-explorer"></a>API 资源管理器

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

Microsoft Defender for Endpoint API Explorer 是一款工具，可帮助你以交互方式浏览各种 Defender for Endpoint API。

通过 API 资源管理器，可以轻松构造和执行 API 查询、测试和发送任何可用的 Defender for Endpoint API 终结点的请求。 使用 API 资源管理器执行操作或查找可能尚未通过用户界面提供的数据。

该工具在应用开发过程中很有用。 它允许你执行遵守用户访问设置的 API 查询，从而减少生成访问令牌的需要。

您还可以使用该工具浏览示例查询库、复制结果代码示例并生成调试信息。

借助 API 资源管理器，你可以：

- 运行任意方法的请求并实时查看响应
- 快速浏览 API 示例并了解它们支持的参数
- 轻松进行 API 调用;无需在管理门户登录之外进行身份验证

## <a name="access-api-explorer"></a>Access API 资源管理器

从左侧导航菜单中，选择"合作伙伴 **& API** \> **资源管理器"。**

## <a name="supported-apis"></a>受支持的 API

API 资源管理器支持 Defender for Endpoint 提供的所有 API。

API 文档中提供了受支持的 [API 列表](apis-intro.md)。

## <a name="get-started-with-the-api-explorer"></a>API 资源管理器入门

1. 在左窗格中，有一个可以使用的示例请求列表。
2. 按照链接操作，然后单击"**运行查询"。**

一些示例可能需要在 URL 中指定参数，例如 {machine- ID}。

## <a name="faq"></a>常见问题

**我是否需要具有 API 令牌以使用 API 资源管理器？** <br>
不需要访问 API 的凭据。 API 资源管理器在提出请求时使用 Defender for Endpoint 管理门户令牌。

登录的用户身份验证凭据用于验证 API 资源管理器是否有权代表你访问数据。

特定 API 请求根据 RBAC 权限受到限制。 例如，对"提交指示器"的请求仅限于安全管理员角色。
