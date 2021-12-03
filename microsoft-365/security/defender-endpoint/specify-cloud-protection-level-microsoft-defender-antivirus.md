---
title: 指定云保护级别的Microsoft Defender 防病毒
description: 为用户设置云保护Microsoft Defender 防病毒。
keywords: Microsoft Defender 防病毒， 反恶意软件， 安全性， defender， 云， 攻击性， 保护级别
ms.pagetype: security
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.date: 08/26/2021
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 4723b84e285e508e33ca4b54a1897bbed036a897
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300702"
---
# <a name="specify-the-cloud-protection-level"></a>指定云保护级别

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

云保护与 Microsoft Defender 防病毒一起为终结点提供保护，这比通过传统安全智能更新快得多。 可以使用推荐策略或组策略Microsoft Endpoint Manager (云) 级别。

> [!NOTE]
> 选择 **"高****、高 +"** 或"**零容** 限"可能会导致检测某些合法文件。 如果发生这种情况，可以在门户中取消阻止检测到的文件或Microsoft 365 Defender争议。

## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-protection"></a>使用 Microsoft Endpoint Manager 指定云保护级别

1. 转到管理Microsoft Endpoint Manager中心 [https://endpoint.microsoft.com](https://endpoint.microsoft.com) () 登录。

2. 选择 **终结点安全** \> **防病毒**。

3. 选择防病毒配置文件。  (如果还没有配置文件，或者要创建新的配置文件，请参阅配置 Microsoft Intune 中的[设备Microsoft Intune。](/intune/device-restrictions-configure)

4. 选择“属性”。 然后，在"配置 **设置"旁边，** 选择"编辑 **"。**

5. 展开 **"云** 保护"，然后在" **云提供的** 保护级别"列表中，选择下列选项之一：

    - **未配置**：默认状态。
    - **高**：应用强级别的检测。
    - **高加**：使用 **高级别** ，并应用额外的保护措施 (可能会影响客户端性能) 。
    - **零容** 限：阻止所有未知可执行文件。

6. 选择 **"审阅 + 保存"，** 然后选择"保存 **"。**

> [!TIP]
> 需要一些帮助？ 参阅以下资源：
>
> - [配置终结点保护](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [在 Intune 中添加终结点保护设置](/mem/intune/protect/endpoint-protection-configure)

## <a name="use-group-policy-to-specify-the-level-of-cloud-protection"></a>使用组策略指定云保护级别

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 右键单击要配置的组策略对象， **然后选择编辑**。

3. 在组 **策略管理编辑器中** ，转到计算机 **配置** \> **管理模板**。

4. 展开树以Windows  \>  \> **MpEngine Microsoft Defender 防病毒组件"。**

5. 双击选择云 **保护级别** 设置，将其设置为 **已启用**。 选择保护级别：

    - **未配置**：默认状态。
    - **默认阻止级别** 提供强检测，而不会增加检测合法文件的风险。
    - **中等阻止级别** 仅为高可信度检测提供中等
    - **高阻止级别** 可在优化客户端性能 (同时应用强大的检测级别，但也可以为您提供更大的机会) 。
    - **高 +** 阻止级别会应用额外的保护措施 (可能会影响客户端性能并增加误报的可能性) 。
    - **零容限阻止级别** 可阻止所有未知可执行文件。

6. 选择“**确定**”。

7. 部署更新的组策略对象。 请参阅 [组策略管理控制台](/windows/win32/srvnodes/group-policy)

> [!TIP]
> 是否在本地使用组策略对象？ 查看它们在云中如何转换。 [在预览版中，使用](/mem/intune/configuration/group-policy-analytics)组策略分析分析Microsoft Endpoint Manager组策略对象。
  
## <a name="see-also"></a>另请参阅

[为什么应为云保护启用Microsoft Defender 防病毒](why-cloud-protection-should-be-on-mdav.md)
