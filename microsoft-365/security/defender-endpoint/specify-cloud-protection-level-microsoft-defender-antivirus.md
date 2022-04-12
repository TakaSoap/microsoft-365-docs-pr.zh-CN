---
title: 指定Microsoft Defender 防病毒的云保护级别
description: 为Microsoft Defender 防病毒设置云保护级别。
keywords: Microsoft Defender 防病毒、反恶意软件、安全性、Defender、云、攻击性、保护级别
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
ms.openlocfilehash: 6e24be40b4ff9e57d896cf53769b578c482a2c6e
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787525"
---
# <a name="specify-the-cloud-protection-level"></a>指定云保护级别

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

与传统安全智能更新相比，云保护与Microsoft Defender 防病毒一起为终结点提供保护的速度要快得多。 可以使用推荐的Microsoft Endpoint Manager () 或组策略来配置云保护级别。

> [!NOTE]
> 选择 **“高**”、“ **高 +**”或 **“零”容错** 可能会导致检测到某些合法文件。 如果发生这种情况，可以在Microsoft 365 Defender门户中取消阻止检测到的文件或对检测结果提出异议。

## <a name="use-microsoft-endpoint-manager-to-specify-the-level-of-cloud-protection"></a>使用Microsoft Endpoint Manager指定云保护级别

1. 转到Microsoft Endpoint Manager管理中心 () [https://endpoint.microsoft.com](https://endpoint.microsoft.com) 并登录。

2. 选择 **终结点安全** \> **防病毒**。

3. 选择防病毒配置文件。  (如果还没有配置文件，或者要创建新配置文件，请参阅[Microsoft Intune中配置设备限制设置](/intune/device-restrictions-configure)。

4. 选择“属性”。 然后，在 **“配置设置”** 旁边选择 **“编辑**”。

5. 展开 **云保护**，然后在 **云提供的保护级别** 列表中，选择下列选项之一：

    - **未配置**：默认状态。
    - **高**：应用强级别的检测。
    - **高加**：使用 **高级** 并应用额外的保护措施 (可能会影响客户端性能) 。
    - **零容错**：阻止所有未知的可执行文件。

6. 选择 **“审阅 + 保存**”，然后选择 **“保存**”。

> [!TIP]
> 需要一些帮助？ 参阅以下资源：
>
> - [配置终结点保护](/mem/configmgr/protect/deploy-use/endpoint-protection-configure)
> - [在Intune中添加终结点保护设置](/mem/intune/protect/endpoint-protection-configure)

## <a name="use-group-policy-to-specify-the-level-of-cloud-protection"></a>使用组策略指定云保护级别

1. 在组策略管理计算机上，打开[组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 右键单击要配置的组策略对象，然后选择 **“编辑**”。

3. 在 **组策略管理编辑器** 中转到 **计算机配置** \> **管理模板**。

4. 展开树以Windows **MpEngine** **Microsoft Defender 防病毒** \> **组件**\>。

5. 双击 **“选择云保护级别** ”设置并将其设置为 **“已启用**”。 选择保护级别：

    - **未配置**：默认状态。
    - **默认阻止级别** 提供强检测，而不会增加检测合法文件的风险。
    - **中度阻塞级别** 仅为高置信度检测提供中度
    - **高阻塞级别** 在优化客户端性能 (时应用很强的检测级别，但也可为你提供更大的误报机会) 。
    - **高 + 阻塞级别** 应用额外的保护措施 (可能会影响客户端性能，并增加误报) 的可能性。
    - **零容错阻止级别** 会阻止所有未知的可执行文件。

6. 选择“确定”。

7. 部署更新的组策略对象。 请参阅[组策略管理控制台](/windows/win32/srvnodes/group-policy)

> [!TIP]
> 是否在本地使用组策略对象？ 了解它们如何在云中转换。 [使用 Microsoft Endpoint Manager - 预览版中的组策略分析分析本地组策略对象](/mem/intune/configuration/group-policy-analytics)。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)
  
## <a name="see-also"></a>另请参阅

[为何应为Microsoft Defender 防病毒启用云保护](why-cloud-protection-should-be-on-mdav.md)
