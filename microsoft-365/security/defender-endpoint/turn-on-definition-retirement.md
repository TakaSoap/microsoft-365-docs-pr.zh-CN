---
title: 打开定义停用以用于Microsoft Defender 防病毒
description: 打开定义停用以用于Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 定义停用
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: 07248f2945e817dc7bdca6240d1de30830abd1e4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207735"
---
# <a name="turn-on-definition-retirement"></a>启用定义停用

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用组策略配置定义停用。 定义停用检查计算机是否具有必要的安全更新，以保护计算机免受特定漏洞的影响。 如果系统不易受定义检测到的漏洞攻击，则该定义将"停用"。 如果给定协议的所有安全智能已停用，则不再分析该协议。 启用此功能有助于提高性能。 在具有所有最新安全更新的计算机上，网络保护不会影响网络性能。

## <a name="use-group-policy-to-configure-definition-retirement"></a>使用组策略配置定义停用

1. 在组策略管理终结点上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 转到计算机 **配置** \> **网络检查系统** \> **Windows管理Microsoft Defender 防病毒** \>  \> **组件**。

3. 选择 **启用定义停用**。 默认情况下，启用此策略。 如果设置为 **"未配置"，** 则启用定义停用。

4. 若要编辑策略，请选择 **"编辑策略设置"** 链接。

5. 选择 **"已启用**"，然后选择"确定 **"。**

6. 部署更新的组策略对象。 请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> 是否在本地使用组策略对象？ 查看它们在云中如何转换。 [在预览版中，使用](/mem/intune/configuration/group-policy-analytics)组策略分析分析Microsoft Endpoint Manager组策略对象。
