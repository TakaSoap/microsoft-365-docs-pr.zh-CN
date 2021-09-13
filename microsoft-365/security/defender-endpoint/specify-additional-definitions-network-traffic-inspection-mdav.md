---
title: 为网络通信检查指定其他定义集Microsoft Defender 防病毒
description: 为网络通信检查指定其他定义集Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， Defender， 网络流量检查
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
ms.openlocfilehash: 82568df0a6ad2225fd31b4c0fa4a654710f1e98b
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59201093"
---
# <a name="specify-additional-definition-sets-for-network-traffic-inspection"></a>为网络流量检查指定其他定义集

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用组策略为网络流量检查指定其他定义集。

## <a name="use-group-policy-to-specify-additional-definition-sets-for-network-traffic-inspection"></a>使用组策略指定用于网络流量检查的其他定义集

1. 在组策略管理终结点上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 转到 **"Windows检查**  >  **Microsoft Defender 防病毒**  >  **组件"。** 

3. 选择 **指定网络流量检查的其他定义集**。 默认情况下，此策略设置为"**未配置"。** 

4. 若要编辑策略，请选择 **"编辑策略设置"** 链接。

5. 选择 **"已启用**"，然后在"选项 **"部分**，选择"显示 **..."。**

6. 将条目添加到列表中，然后选择"确定 **"。** 

   每个条目都必须作为名称-值对列出，其中名称是定义集 GUID 的字符串表示形式。 例如，定义集 GUID 以启用测试安全智能定义为 `{b54b6ac9-a737-498e-9120-6616ad3bf590}` ：。 该值未使用，因此我们建议将该值设置为 `0` 。 

7. 选择 **"确定**"，然后部署更新的组策略对象。 请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)。

> [!TIP]
> 是否在本地使用组策略对象？ 查看它们在云中如何转换。 [在预览版中，使用](/mem/intune/configuration/group-policy-analytics)组策略分析分析Microsoft Endpoint Manager组策略对象。 
  
## <a name="related-articles"></a>相关文章

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
 
- [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)

- [如何创建和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)