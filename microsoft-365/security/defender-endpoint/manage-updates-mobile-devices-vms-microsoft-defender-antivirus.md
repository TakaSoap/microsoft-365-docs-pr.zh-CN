---
title: 定义移动设备如何通过Microsoft Defender 防病毒更新
description: 管理如何使用Microsoft Defender 防病毒保护更新更新移动设备（如笔记本电脑）。
keywords: 更新， 保护， 计划更新， 电池， 移动设备， 笔记本电脑， 笔记本， 选择加入， microsoft 更新， wsus， 替代
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: f582e33f2d77c8560b773b79d54026e38bcde8c9
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790363"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>管理移动设备和虚拟机 （VM） 的更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

移动设备和 VM 可能需要更多配置，以确保性能不会受到更新的影响。

有两个设置对这些设备非常有用：

- 在没有 WSUS 连接的情况下选择在移动计算机上加入 Microsoft 更新
- 在电池电源上运行时阻止安全智能更新

在以下情况下，以下文章可能也很有用：
- [配置计划扫描和追赶扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [虚拟桌面基础结构 （VDI） 环境中 Microsoft Defender 防病毒软件的部署指南](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>在没有 WSUS 连接的情况下选择在移动计算机上加入 Microsoft 更新

当移动设备未连接到公司网络或未建立 WSUS 连接时，可以使用 Microsoft 更新来使运行Microsoft Defender 防病毒的移动设备上的安全智能保持最新。

这意味着，即使已将 WSUS 设置为替代 Microsoft 更新，也可以通过 Microsoft 更新) 将保护更新传递到 (设备。

可以通过以下方式之一选择加入移动设备上的 Microsoft 更新：

- 使用组策略更改设置。
- 使用 VBScript 创建脚本，然后在网络中的每台计算机上运行它。
- 通过 **设置** 菜单手动选择加入网络上的每台计算机。

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>使用组策略选择加入 Microsoft 更新

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象，然后选择 **“编辑**”。

2. 在 **组策略管理编辑器** 中转到 **计算机配置**。

3. 选择 **“策略** ”，然后选择 **管理模板**。

4. 展开树以Microsoft Defender 防病毒 **签名更新****Windows** \> **组件**\>。

5. 将 **“允许”安全智能更新从 Microsoft 更新** 设置为 **“已启用**”，然后选择  **“确定**”。

### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>使用 VBScript 选择加入 Microsoft 更新

1. 使用 MSDN 文章 [“选择加入 Microsoft 更新](/windows/win32/wua_sdk/opt-in-to-microsoft-update) ”中的说明创建 VBScript。

2. 运行在网络中的每台计算机上创建的 VBScript。

### <a name="manually-opt-in-to-microsoft-update"></a>手动选择加入 Microsoft 更新

1. **在要** 选择加入的计算机上的 **更新&安全** 设置中打开Windows 更新。

2. 选择 **“高级** ”选项。

3. 在更新Windows时，选中“**为我提供其他 Microsoft 产品的更新**”复选框。

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>在电池电源上运行时阻止安全智能更新

可将Microsoft Defender 防病毒配置为仅在电脑连接到有线电源时下载保护更新。

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>使用组策略阻止电池电源的安全智能更新

1. 在组策略管理计算机上，打开[组策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，选择要配置的组策略对象，然后将其打开进行编辑。

2. 在 **组策略管理编辑器** 中转到 **计算机配置**。

3. 选择 **“策略** ”，然后选择 **管理模板**。

4. 展开树以 **Windows组件** \> **Microsoft Defender 防病毒** \> **签名更新**，然后在 **电池电源上运行时将“允许安全智能更新**”设置为 **“已禁用**”。 然后，选择“**确定**”。

此操作可防止在电脑使用电池电源时下载保护更新。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-articles"></a>相关文章

- [管理Microsoft Defender 防病毒更新并应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [在Windows 10中更新和管理Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)