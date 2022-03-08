---
title: 实时响应库方法和属性
description: 了解如何使用实时响应库方法和属性。
keywords: api， 图形 api， 受支持的 api， 获取， 设备
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
localization_priority: normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: reference
ms.technology: m365d
ms.openlocfilehash: 74f4fbe69135433597492854428b34449fbd0260
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318987"
---
#  <a name="live-response-library-methods-and-properties"></a>实时响应库方法和属性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**[Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)

[!include[Prerelease information](../../includes/prerelease.md)]

- 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)。 

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]


## <a name="methods"></a>方法

| **方法**          | **返回类型**         | **说明**                         |
|---------------------|-------------------------|-----------------------------------------|
| 列表库文件  | 库文件集合 | 列表库文件实体              |
| Upload库   | 库文件实体     | Upload文件到实时响应库 |
| 从库中删除 | 无内容              | 删除库文件实体              |

## <a name="properties"></a>属性

| **属性** | **类型**                         | **说明**                                        |
|--------------|----------------------------------|--------------------------------------------------------|
| 命令     | 实时响应命令集合 | Command 对象的数组。 请参阅 [实时响应命令](live-response.md#live-response-commands)。 |

