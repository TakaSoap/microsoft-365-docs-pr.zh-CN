---
title: 打开定义停用功能Microsoft Defender 防病毒
description: 为定义启用停用Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 定义停用
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.date: 06/10/2021
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.topic: article
ms.collection: m365-security-compliance
ms.openlocfilehash: 48636954f3f9127d5c79047ad160cf5a0133efd5
ms.sourcegitcommit: 6968594dc8cf8b30a4c958df6d65dfd0cd2cfae1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/23/2021
ms.locfileid: "59490939"
---
# <a name="turn-on-definition-retirement"></a>启用定义停用

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用组策略配置定义停用。 定义停用检查计算机是否具有必要的安全更新，以保护计算机免受特定漏洞的影响。 如果系统不易受定义检测到的漏洞攻击，则该定义将"停用"。 如果给定协议的所有安全智能都停用，则不再分析该协议。 启用此功能有助于提高性能。 在具有所有最新安全更新的计算机上，网络保护不会影响网络性能。

## <a name="use-group-policy-to-configure-definition-retirement"></a>使用组策略配置定义停用

1. 在组策略管理终结点上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 转到计算机 **配置**  >  **网络检查Windows**  >  **管理Microsoft Defender 防病毒**  >    >  **组件**。 

3. 选择 **启用定义停用**。 默认情况下，启用此策略。 如果设置为 **"未配置"，** 则启用定义停用。 

4. 若要编辑策略，请选择 **"编辑策略设置"** 链接。

5. 选择 **"已启用**"，然后选择"确定 **"。**

6. 部署更新的组策略对象。 请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> 是否在本地使用组策略对象？ 查看它们在云中如何转换。 [在预览版中，使用](/mem/intune/configuration/group-policy-analytics)组策略分析分析Microsoft Endpoint Manager组策略对象。 
  
