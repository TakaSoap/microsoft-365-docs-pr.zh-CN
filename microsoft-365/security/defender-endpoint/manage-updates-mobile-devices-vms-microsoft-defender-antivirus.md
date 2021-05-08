---
title: 定义 Microsoft Defender 防病毒如何更新移动设备
description: 使用 Microsoft Defender 防病毒保护更新管理移动设备（如笔记本电脑）的更新方式。
keywords: 更新， 保护， 计划更新， 电池， 移动设备， 笔记本电脑， 笔记本， 选择加入， Microsoft 更新， wsus， 替代
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.openlocfilehash: 143b0cb4bac1d3307e440f98fa4278f38e07c7f2
ms.sourcegitcommit: 51b316c23e070ab402a687f927e8fa01cb719c74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/07/2021
ms.locfileid: "52269536"
---
# <a name="manage-updates-for-mobile-devices-and-virtual-machines-vms"></a>管理移动设备和虚拟机 （VM） 的更新

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

移动设备和 VM 可能需要进行更多配置，以确保性能不会受更新影响。

有两个设置对这些设备有用：

- 选择在没有 WSUS 连接的情况下在移动计算机上加入 Microsoft 更新
- 使用电池电源运行时阻止安全智能更新

以下文章在这些情况下可能也很有用：
- [配置计划扫描和跟进扫描](scheduled-catch-up-scans-microsoft-defender-antivirus.md)
- [管理过期终结点的更新](manage-outdated-endpoints-microsoft-defender-antivirus.md)
- [虚拟桌面基础结构 （VDI） 环境中 Microsoft Defender 防病毒软件的部署指南](deployment-vdi-microsoft-defender-antivirus.md)

## <a name="opt-in-to-microsoft-update-on-mobile-computers-without-a-wsus-connection"></a>选择在没有 WSUS 连接的情况下在移动计算机上加入 Microsoft 更新

当运行 Microsoft Defender 防病毒的移动设备未连接到企业网络或没有 WSUS 连接时，可以使用 Microsoft 更新使这些设备的安全智能保持最新。 

这意味着，即使将 WSUS 设置为覆盖 Microsoft 更新 (Microsoft 更新) 保护更新也可以传递到设备。

可以通过以下方法之一选择在移动设备上使用 Microsoft 更新：

- 使用组策略更改设置。
- 使用 VBScript 创建脚本，然后在网络的每台计算机中运行该脚本。
- 通过"设置"菜单手动选择加入网络 **的每** 台计算机。

### <a name="use-group-policy-to-opt-in-to-microsoft-update"></a>使用组策略选择加入 Microsoft 更新

1. 在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，右键单击要配置的组策略对象， **然后选择编辑**。

2. 在组 **策略管理编辑器中** ，转到计算机 **配置**。

3. 选择 **"策略****"，然后选择"管理模板"。**

4. 将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **签名更新**。

5. 将 **"允许安全智能更新从 Microsoft 更新"设置为****"已启用"，** 然后选择"确定 **"。**


### <a name="use-a-vbscript-to-opt-in-to-microsoft-update"></a>使用 VBScript 选择加入 Microsoft 更新

1. 使用 MSDN 文章选择加入 [Microsoft Update](/windows/win32/wua_sdk/opt-in-to-microsoft-update) 中的说明创建 VBScript。

2. 运行在网络的每台计算机中创建的 VBScript。

### <a name="manually-opt-in-to-microsoft-update"></a>手动选择加入 Microsoft 更新

1. 在 **"更新****"&** 要选择加入的计算机的"更新和安全设置"中打开 Windows 更新。

2. 选择 **"高级选项** "。

3. 选中"更新 Windows **时为我提供其他 Microsoft** 产品的更新"复选框。

## <a name="prevent-security-intelligence-updates-when-running-on-battery-power"></a>使用电池电源运行时阻止安全智能更新

你可以将 Microsoft Defender 防病毒配置为仅在电脑连接到有线电源时下载保护更新。 

### <a name="use-group-policy-to-prevent-security-intelligence-updates-on-battery-power"></a>使用组策略阻止使用电池电源进行安全智能更新

1.  在组策略管理计算机上，打开组 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))，选择要配置的组策略对象，然后打开它进行编辑。

2.  在组 **策略管理编辑器中** ，转到计算机 **配置**。

3.  选择 **"策略****"，然后选择"管理模板"。**

4.  将树展开到 **Windows 组件** Microsoft Defender  >  **防病毒**  >  **签名更新**，然后将使用电池电源运行时允许安全智能更新设置为 **已禁用**。 然后，选择“**确定**”。 

此操作可防止在电脑使用电池电源时下载保护更新。

## <a name="related-articles"></a>相关文章

- [管理 Microsoft Defender 防病毒更新和应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)
- [在 Windows 10 中更新和管理 Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)