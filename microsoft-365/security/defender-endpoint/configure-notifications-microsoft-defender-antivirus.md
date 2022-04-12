---
title: 配置Microsoft Defender 防病毒通知
description: 了解如何在终结点上配置和自定义标准通知和其他Microsoft Defender 防病毒通知。
keywords: notifications， defender， 防病毒， 终结点， 管理， 管理员
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.topic: article
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.collection: M365-security-compliance
ms.openlocfilehash: e38a8e9de3bef132dfdf3d2a088190a5038a2941
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790187"
---
# <a name="configure-microsoft-defender-antivirus-notifications-that-appear-on-endpoints"></a>配置终结点上显示的Microsoft Defender 防病毒通知

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

在Windows 10和Windows 11中，有关恶意软件检测和修正的应用程序通知更加可靠、一致和简洁。 Microsoft Defender 防病毒扫描完成并检测到威胁时，会在终结点上显示通知。 通知遵循计划扫描和手动触发的扫描。 这些通知也会显示在 **通知中心**，扫描和威胁检测摘要会定期显示。

如果你是组织安全团队的一员，则可以配置通知在终结点上的显示方式，例如提示重新启动系统或指示已检测到威胁并修正的通知。

## <a name="configure-antivirus-notifications-using-group-policy-or-the-windows-security-app"></a>使用组策略或Windows 安全中心应用配置防病毒通知

可以在[Windows 安全中心应用和组策略](microsoft-defender-security-center-antivirus.md)中配置其他通知的显示，例如最近的威胁检测摘要。

> [!NOTE]
> 在Windows 10版本 1607 中，该功能称为 **增强通知**，并在 **Windows 设置更新&** \> **安全** \> **Windows Defender** 下进行配置。 在所有Windows 10和Windows 11版本的组策略设置中，通知功能称为 **增强通知**。

### <a name="use-group-policy-to-disable-additional-notifications"></a>使用组策略禁用其他通知

1. 在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 右键单击要配置的组策略对象，然后选择 **“编辑**”。

3. 在 **组策略管理编辑器** 中转到 **计算机配置**。

4. 选择 **管理模板**。

5. 将树展开为 **Windows组件** \> **Microsoft Defender 防病毒** > **报表**。

6. 双击 **“关闭增强的通知**”，并将选项设置为 **“已启用**”。 然后，选择“**确定**”。 这将防止出现其他通知。

> [!IMPORTANT]
> 禁用其他通知不会禁用关键通知，例如威胁检测和修正警报。

### <a name="use-the-windows-security-app-to-disable-additional-notifications"></a>使用Windows 安全中心应用禁用其他通知

1. 通过单击任务栏中的“盾牌”图标或搜索“开始”菜单以获取 **安全** 性，打开Windows 安全中心应用。

2. 选择 **“病毒&威胁防护**”磁贴 (或左侧菜单栏) 的“防护”图标，然后选择 **“病毒&威胁防护设置**”

3. 滚动到 **“通知”** 部分，然后选择 **“更改通知设置**”。

4. 将开关滑动到 **“关闭** ”或 **“打开”** 以禁用或启用其他通知。

> [!IMPORTANT]
> 禁用其他通知不会禁用关键通知，例如威胁检测和修正警报。

## <a name="configure-standard-notifications-on-endpoints-using-group-policy"></a>使用组策略在终结点上配置标准通知

可以使用组策略执行以下操作：

- 当用户需要执行操作时，在终结点上显示其他自定义文本
- 隐藏终结点上的所有通知
- 隐藏终结点上的重新启动通知

在无法隐藏整个Microsoft Defender 防病毒接口的情况下，隐藏通知可能很有用。 有关详细信息，请参阅[阻止用户查看或与Microsoft Defender 防病毒用户界面交互](prevent-end-user-interaction-microsoft-defender-antivirus.md)。 隐藏通知只会在策略已部署到的终结点上发生。 与必须 (执行的操作（如重启) ）相关的通知仍将显示在[Microsoft Endpoint Manager Endpoint Protection监视仪表板和报表](/configmgr/protect/deploy-use/monitor-endpoint-protection)上。 

若要将自定义联系人信息添加到终结点通知，请参阅[自定义组织的Windows 安全中心应用](/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)。

### <a name="use-group-policy-to-hide-notifications"></a>使用组策略隐藏通知

1. 在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 右键单击要配置的组策略对象，然后选择 **“编辑**”。

3. 在 **组策略管理编辑器** 中转到 **计算机配置**，然后选择 **管理模板**。

4. 将树展开到客户端 **接口****Microsoft Defender 防病毒Windows** \> **组件**\>。 

5. 双击 **“禁止所有通知** ”，并将选项设置为 **“已启用**”。 

6. 选择“确定”。 这将防止出现其他通知。

### <a name="use-group-policy-to-hide-reboot-notifications"></a>使用组策略隐藏重启通知

1. 在组策略管理计算机上，打开 [策略管理控制台](/previous-versions/windows/it-pro/windows-server-2008-R2-and-2008/cc731212(v=ws.11))。

2. 右键单击要配置的组策略对象，然后选择 **“编辑**”。

2. 在 **组策略管理编辑器** 中转到 **计算机配置**。

3. 单击 **“管理模板**”。

4. 将树展开到客户端 **接口****Microsoft Defender 防病毒Windows** \> **组件**\>。

5. 双击 **“禁止重启”通知** ，并将选项设置为 **“已启用**”。 

5. 选择“确定”。 这将防止出现其他通知。

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)