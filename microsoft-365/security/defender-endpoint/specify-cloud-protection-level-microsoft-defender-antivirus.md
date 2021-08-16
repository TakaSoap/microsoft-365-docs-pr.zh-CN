---
title: 为用户指定云提供的Microsoft Defender 防病毒
description: 为云解决方案设置云保护Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， Defender， 云， 主动性， 保护级别
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
localization_priority: normal
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 10/26/2020
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 6b7ef857e09e01a1a9ba550dc679708c88dfce1751cd2644156ce38d1b8f42c6
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53863483"
---
# <a name="specify-the-cloud-delivered-protection-level"></a>指定云传递的保护级别

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

可以使用推荐策略或组策略Microsoft Defender 防病毒云提供的Microsoft Endpoint Manager (保护) 级别。

> [!TIP]
> 云保护不仅仅是对存储在云中的文件的保护。 Microsoft Defender 防病毒云服务是一种机制，用于向网络和设备（也称为 (终结点）提供更新) 。 云保护Microsoft Defender 防病毒分布式资源和机器学习，以比传统安全智能更新快得多的速度为终结点提供保护。 Microsoft Intune 和 Microsoft Endpoint Manager 现在是 Microsoft Endpoint Manager[的一Microsoft Endpoint Manager。](/mem/endpoint-manager-overview) 


## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-delivered-protection"></a>使用 Microsoft Endpoint Manager 指定云提供的保护级别

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。

2. 选择 **终结点安全**  >  **防病毒**。

3. 选择防病毒配置文件。  (如果还没有配置文件，或者要创建新的配置文件，请参阅配置 Microsoft Intune 中的[设备限制设置](/intune/device-restrictions-configure)。

4. 选择 **"属性"。** 然后，在"配置 **设置"旁边，选择**"编辑 **"。**

5. 展开 **"云** 保护"，然后在" **云提供的** 保护级别"列表中，选择下列选项之一：

    1. **高**：应用强级别的检测。
    2. **高加**： **使用高级别** ，并应用其他保护措施 (可能会影响客户端性能) 。
    3. **零容** 限：阻止所有未知可执行文件。

6. 选择 **"审阅 + 保存"，** 然后选择"保存 **"。** 

> [!TIP]
> 需要一些帮助？ 参阅以下资源：
> - [配置Endpoint Protection](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [在 Intune 中添加终结点保护设置](/mem/intune/protect/endpoint-protection-configure)
  

## <a name="use-group-policy-to-specify-the-level-of-cloud-delivered-protection"></a>使用组策略指定云提供的保护级别

1.  在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 右键单击要配置的组策略对象，然后单击编辑 **。**

3.  在组 **策略管理编辑器中**，转到计算机 **配置**  >  **管理模板**。

4.  展开树以Windows   >    >  **MpEngine Microsoft Defender 防病毒组件。**

5.  双击选择云 **保护级别** 设置，将其设置为 **已启用**。 选择保护级别：
    - **默认阻止级别** 提供强检测，而不会增加检测合法文件的风险。
    - **中等阻止级别** 仅为高可信度检测提供中等
    - **高阻止级别** 可在优化客户端性能 (同时应用强大的检测级别，但也可以为您提供更大的误报) 。
    - **高 +** 阻止级别会应用其他保护措施 (可能会影响客户端性能并增加误报的可能性) 。
    - **零容限阻止级别** 可阻止所有未知可执行文件。
    
    > [!WARNING]
    > 虽然不太可能，但将此开关设置为"高"或"高 **+"** 可能会导致检测到一些合法 (尽管你可选择取消阻止或争议该检测) 。

6. 单击“**确定**”。

7. 部署更新的组策略对象。 请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)

> [!TIP]
> 是否在本地使用组策略对象？ 查看它们在云中如何转换。 [在预览版中，使用组策略分析Microsoft Endpoint Manager本地组策略对象](/mem/intune/configuration/group-policy-analytics)。 
  
## <a name="related-articles"></a>相关文章

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [启用云保护](enable-cloud-protection-microsoft-defender-antivirus.md)
- [如何创建和部署反恶意软件策略：云保护服务](/configmgr/protect/deploy-use/endpoint-antimalware-policies#cloud-protection-service)