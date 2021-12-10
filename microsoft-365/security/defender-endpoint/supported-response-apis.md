---
title: 支持的 Microsoft Defender 终结点响应 API
description: 了解与特定响应相关的 Microsoft Defender 终结点 API 调用。
keywords: 响应 api， 图形 api， 受支持的 api， 参与者， 警报， 设备， 用户， 域， ip， 文件
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
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
ms.openlocfilehash: dcf73669ab780ec23cbd5551039dc8c74f0502ef
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61165782"
---
# <a name="supported-microsoft-defender-for-endpoint-query-apis"></a>支持的 Microsoft Defender for Endpoint 查询 API

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> [!TIP]
> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-supported-response-apis-abovefoldlink)。

了解可以运行的受支持的与响应相关的 API 调用，以及所需请求标头和来自调用的预期响应等详细信息。

## <a name="in-this-section"></a>本节内容

<br>

****

|主题|说明|
|---|---|
|收集调查程序包|运行此 API 从设备收集调查包。|
|隔离设备|运行此 API 以将设备与网络隔离。|
|Unisolate 设备|从隔离中删除设备。|
|限制代码执行|通过停止恶意进程运行此 API 以包含攻击。 还可以锁定设备并阻止潜在恶意程序的后续尝试运行。|
|无限制代码执行|在验证损坏的设备已修复后，运行此功能可撤消应用程序策略的限制。|
|运行防病毒扫描|远程启动防病毒扫描，以帮助识别和修正可能存在于受到威胁的设备的恶意软件。|
|停止和隔离文件|运行此调用以停止正在运行的进程、隔离文件并删除持久性（如注册表项）。|
|请求示例|运行此调用，从特定设备请求文件示例。 文件会从设备中收集并上载到安全存储。|
|阻止文件|运行此 API，通过禁止潜在恶意文件或可疑恶意软件，防止攻击在组织中进一步传播。|
|取消阻止文件|允许文件在组织中使用 Microsoft Defender 防病毒。|
|获取程序包 SAS URI|运行此 API 获取允许下载调查包的 URI。|
|获取 MachineAction 对象|运行此 API 获取 MachineAction 对象。|
|获取 MachineActions 集合|运行它可获取 MachineAction 集合。|
|获取 FileActions 集合|运行此 API 获取 FileActions 集合。|
|获取 FileMachineAction 对象|运行此 API 获取 FileMachineAction 对象。|
|获取 FileMachineActions 集合|运行此 API 获取 FileMachineAction 集合。|
|
