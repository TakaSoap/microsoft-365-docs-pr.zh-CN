---
title: 隐藏Microsoft Defender 防病毒接口
description: 可以在Windows 安全中心应用中隐藏病毒和威胁防护磁贴。
keywords: ui 锁定，无头模式，隐藏应用，隐藏设置，隐藏接口
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2021
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.topic: article
ms.collection: M365-security-compliance
ms.openlocfilehash: fdd212efd50d55bbcdae80275f5d2ca8a97cdeb3
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787657"
---
# <a name="prevent-users-from-seeing-or-interacting-with-the-microsoft-defender-antivirus-user-interface"></a>阻止用户查看或与Microsoft Defender 防病毒用户界面交互

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

可以使用组策略阻止终结点上的用户看到Microsoft Defender 防病毒接口。 还可以防止它们暂停扫描。

## <a name="hide-the-microsoft-defender-antivirus-interface"></a>隐藏Microsoft Defender 防病毒接口

在Windows 10版本 1703 中，隐藏接口将隐藏Microsoft Defender 防病毒通知，并防止病毒&威胁防护磁贴出现在Windows 安全中心应用中。

设置为 **“已启用**”后：

:::image type="content" source="../../media/wdav-headless-mode-off-1703.png" alt-text="没有防护图标、病毒和威胁防护部分的Windows 安全中心" lightbox="../../media/wdav-headless-mode-off-1703.png":::

设置为 **“已禁** 用”或未配置：

:::image type="content" source="../../media/wdav-headless-mode-1703.png" alt-text="包含防护图标和威胁防护部分的Windows 安全中心" lightbox="../../media/wdav-headless-mode-1703.png":::

> [!NOTE]
> 隐藏接口还会阻止Microsoft Defender 防病毒通知出现在终结点上。 仍将显示Microsoft Defender for Endpoint通知。 还可以单独 [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)

在早期版本的Windows 10中，设置将隐藏Windows Defender客户端接口。 如果用户尝试打开它，他们将收到一条警告，显示“你的系统管理员对此应用的访问受到限制。

:::image type="content" source="../../media/wdav-headless-mode-1607.png" alt-text="在 1703 之前的Windows 10版本中启用无头模式时的警告消息" lightbox="../../media/wdav-headless-mode-1607.png":::

## <a name="use-group-policy-to-hide-the-microsoft-defender-av-interface-from-users"></a>使用组策略向用户隐藏 Microsoft Defender AV 界面

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 使用 **组策略管理编辑器** 转到 **计算机配置**。

3. 单击 **“管理模板**”。

4. 将树展开到 **客户端接口> Microsoft Defender 防病毒 > Windows组件**。

5. 双击 **“启用无头 UI 模式** ”设置，并将选项设置为 **“已启用**”。 单击“确定”。

请参阅 [“阻止用户在本地修改策略设置”](configure-local-policy-overrides-microsoft-defender-antivirus.md) ，了解有关阻止用户在电脑上形成修改保护的更多选项。

## <a name="prevent-users-from-pausing-a-scan"></a>防止用户暂停扫描

可以防止用户暂停扫描，这有助于确保计划或按需扫描不会被用户中断。

> [!NOTE]
> Windows 10不支持此设置。

### <a name="use-group-policy-to-prevent-users-from-pausing-a-scan"></a>使用组策略防止用户暂停扫描

1. 在组策略管理计算机上，打开 [组策略管理控制台](/previous-versions/windows/desktop/gpmc/group-policy-management-console-portal)，右键单击要配置的组策略对象，然后单击 **“编辑**”。

2. 使用 **组策略管理编辑器** 转到 **计算机配置**。

3. 单击 **“管理模板**”。

4. 将树展开到 **扫描** Microsoft Defender 防病毒 **Windows** \> **组件**\>。

5. 双击 **“允许用户暂停扫描** 设置”并将选项设置为 **“已禁用**”。 单击“确定”。

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

- [配置终结点上显示的通知](configure-notifications-microsoft-defender-antivirus.md)
- [配置最终用户与Microsoft Defender 防病毒交互](configure-end-user-interaction-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
