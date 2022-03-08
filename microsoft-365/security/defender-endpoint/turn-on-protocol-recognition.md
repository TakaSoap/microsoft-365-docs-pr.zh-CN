---
title: 打开协议识别Microsoft Defender 防病毒
description: 打开协议识别Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 协议识别
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 02/21/2022
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: 221eff4af6bf8e77f29db84694bf3a683107fc8c
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63325161"
---
# <a name="turn-on-protocol-recognition"></a>打开协议识别

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

此策略设置允许你配置协议识别，以抵御已知漏洞攻击的网络保护。 如果启用或不配置此设置，将启用协议识别。 如果禁用此设置，将禁用协议识别。

[!IMPORTANT]
此设置现已弃用。 

## <a name="use-group-policy-to-configure-protocol-recognition"></a>使用组策略配置协议识别

1. 在组策略管理终结点上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 转到计算机 **配置** \> **网络检查Windows** \> **管理** \> \> Microsoft Defender 防病毒 **组件**。

3. 选择 **协议识别**。 默认情况下，启用此策略。 如果设置 **未配置，** 则启用定义停用。

4. 若要编辑策略，请选择 **"编辑策略设置"** 链接。

5. 选择 **"已启用**"，然后选择" **确定"**。

6. 部署更新的组策略对象。 请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> 是否在本地使用组策略对象？ 查看它们在云中如何转换。 [使用 Microsoft Endpoint Manager 预览版中的](/mem/intune/configuration/group-policy-analytics)组策略分析分析本地组策略对象。

## <a name="related-articles"></a>相关文章

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)
- [如何创建和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)
