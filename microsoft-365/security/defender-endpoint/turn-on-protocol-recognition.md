---
title: 打开协议识别Microsoft Defender 防病毒
description: 打开协议识别以识别Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 协议识别
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 05/07/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: da8b7c2949e594fc461ca6a8ac65467bb207aae4
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2021
ms.locfileid: "59489578"
---
# <a name="turn-on-protocol-recognition"></a>打开协议识别 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

此策略设置允许你配置协议识别，以抵御已知漏洞攻击的网络保护。 如果启用或不配置此设置，将启用协议识别。 如果禁用此设置，将禁用协议识别。

## <a name="use-group-policy-to-configure-protocol-recognition"></a>使用组策略配置协议识别

1. 在组策略管理终结点上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 转到计算机 **配置** 管理模板  >    >  **Windows组件**  >  **Microsoft Defender 防病毒**  >  **网络检查系统**。 

3. 选择 **协议识别**。 默认情况下，启用此策略。 如果设置为 **"未配置"，** 则启用定义停用。 

4. 若要编辑策略，请选择 **"编辑策略设置"** 链接。

5. 选择 **"已启用**"，然后选择"确定 **"。**

6. 部署更新的组策略对象。 请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> 是否在本地使用组策略对象？ 查看它们在云中如何转换。 [在预览版中，使用](/mem/intune/configuration/group-policy-analytics)组策略分析分析Microsoft Endpoint Manager组策略对象。 
  
## <a name="related-articles"></a>相关文章

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
 
- [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)

- [如何创建和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)