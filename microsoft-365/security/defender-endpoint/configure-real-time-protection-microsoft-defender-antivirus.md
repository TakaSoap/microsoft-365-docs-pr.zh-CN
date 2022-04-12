---
title: 启用和配置Microsoft Defender 防病毒保护功能
description: 启用和配置Microsoft Defender 防病毒实时保护功能，例如行为监视、启发式和机器学习
keywords: 防病毒，实时保护，rtp，机器学习，行为监视，启发
ms.prod: m365-security
ms.technology: mde
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
author: denisebmsft
ms.author: deniseb
ms.topic: article
ms.date: 10/22/2021
manager: dansimp
ms.custom: nextgen
ms.collection: M365-security-compliance
ms.openlocfilehash: 744aaa887bfbfafd29b9e3bedb8dc49791b43137
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790165"
---
# <a name="enable-and-configure-microsoft-defender-antivirus-always-on-protection-in-group-policy"></a>在组策略中启用和配置 Microsoft Defender 防病毒软件始终启用保护

**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

Always-on 保护包括实时保护、行为监视和启发式保护，用于基于已知的可疑和恶意活动来识别恶意软件。

这些活动包括事件，例如对现有文件进行异常更改的过程、修改或创建自动启动注册表项和启动位置 (也称为自动启动扩展点或 ASEP) ，以及对文件系统或文件结构进行其他更改。

## <a name="enable-and-configure-always-on-protection-in-group-policy"></a>在组策略中启用和配置 Always-on 保护

可以使用 **本地组策略编辑器** 启用和配置Microsoft Defender 防病毒始终可用的保护设置。

若要启用和配置 Always-on 保护，请执行以下操作：

1. 打开 **本地组策略编辑器**，如下所示：

    1. 在Windows 10或Windows 11任务栏搜索框中，键 **入 gpedit**。

    2. 在 **“最佳匹配**”下，选择 **“编辑组策略**”以启动 **“本地组策略编辑器**”。
    
       :::image type="content" source="images/gpedit-search.png" alt-text="控制面板中的 GPEdit 任务栏搜索结果" lightbox="images/gpedit-search.png":::

2. 在 **“本地组策略编辑** 器”的左窗格中，将树展开为 **计算机配置** \> **管理模板** \> **Windows组件** \> **Microsoft Defender 防病毒**。

3. 配置Microsoft Defender 防病毒反恶意软件服务策略设置。

   在右侧 **的“Microsoft Defender 防病毒** 详细信息”窗格中，双击“**允许反恶意软件服务以正常优先级启动**”，并将其设置为 **“已启用**”。

   然后，选择“**确定**”。

4. 配置Microsoft Defender 防病毒实时保护策略设置，如下所示：

    1. 在 **Microsoft Defender 防病毒** 详细信息窗格中，双击 **“实时保护**”。 或者，在左窗格的 **Microsoft Defender 防病毒** 树中，选择 **“实时保护**”。

    2. 在右侧 **的“实时保护** 详细信息”窗格中，双击本文后面 (实时 [保护策略设置](#real-time-protection-policy-settings) 中指定的策略设置) 。

    3. 根据需要配置设置，然后选择 **“确定**”。

    4. 对表中的每个设置重复前面的步骤。

5. 配置Microsoft Defender 防病毒扫描策略设置，如下所示：

    1. 在左窗格的 **Microsoft Defender 防病毒** 树中，选择 **“扫描**”。
    
   2. 在右侧的 **“扫描** 详细信息”窗格中，双击 **“打开启发式”**，并将其设置为 **“已启用**”。 

   3. 选择“确定”。

6. 关闭 **本地组策略编辑器**。

### <a name="real-time-protection-policy-settings"></a>实时保护策略设置

|设置|默认设置|
|---|---|
|启用行为监视 <p> 防病毒引擎将监视终结点上的文件进程、文件和注册表更改以及其他事件，以防可疑且已知的恶意活动。|已启用|
|扫描所有下载的文件和附件 <p> 将自动扫描下载的文件和附件。 除了在下载前和下载期间扫描文件的Windows Defender SmartScreen 筛选器外，此扫描还会运行。|已启用|
|监视计算机上的文件和程序活动 <p> Microsoft Defender 防病毒引擎会记下文件写入 (的任何文件更改，例如移动、复制或修改) 和常规程序活动 (打开或运行的程序，并导致其他程序运行) 。|已启用|
|打开原始卷写入通知 <p> 有关原始卷写入的信息将通过行为监视进行分析。|已启用|
|启用实时保护时启用进程扫描 <p> 可以独立启用Microsoft Defender 防病毒引擎来扫描正在运行的进程是否存在可疑的修改或行为。 如果暂时禁用了实时保护，并且想要自动扫描在禁用时启动的进程，这非常有用。|已启用|
|定义要扫描的下载文件和附件的最大大小 <p> 可以定义大小（以千字节为单位）。|已启用|
|配置本地设置替代以启用行为监视 <p> 为行为监视的配置配置配置本地重写。 此设置只能通过组策略进行设置。 如果启用此设置，则本地首选项设置将优先于组策略。 如果禁用或未配置此设置，组策略将优先于本地首选项设置。|已启用|
|配置本地设置替代以扫描所有下载的文件和附件 <p> 为所有下载的文件和附件的扫描配置配置本地重写。 此设置只能通过组策略进行设置。 如果启用此设置，则本地首选项设置将优先于组策略。 如果禁用或未配置此设置，组策略将优先于本地首选项设置。|已启用|
|配置本地设置替代以监视计算机上的文件和程序活动 <p> 为计算机上的文件和程序活动的监视配置配置本地替代。 此设置只能通过组策略进行设置。 如果启用此设置，则本地首选项设置将优先于组策略。 如果禁用或未配置此设置，组策略将优先于本地首选项设置。|已启用|
|配置本地设置替代以启用实时保护 <p> 为配置配置本地重写以启用实时保护。 此设置只能通过组策略进行设置。 如果启用此设置，则本地首选项设置将优先于组策略。 如果禁用或未配置此设置，组策略将优先于本地首选项设置。|已启用|
|配置本地设置替代以监视传入和传出文件活动 <p> 为传入和传出文件活动的监视配置配置本地重写。 此设置只能通过组策略进行设置。 如果启用此设置，则本地首选项设置将优先于组策略。 如果禁用或未配置此设置，组策略将优先于本地首选项设置。|已启用|
|为传入和传出文件和程序活动配置监视 <p> 指定是否应在传入、传出或两个方向上进行监视。 此操作与Windows服务器安装相关，你已定义特定服务器或服务器角色，这些服务器或角色仅在一个方向上看到大量文件更改，并且希望提高网络性能。 完全更新的终结点 (以及网络上) 的服务器，无论文件更改的数量或方向如何，都不会对性能产生什么影响。|已 (两个方向启用) |

## <a name="disable-real-time-protection-in-group-policy"></a>在组策略中禁用实时保护

> [!WARNING]
> 禁用实时保护可大幅减少对终结点的保护，不建议这样做。

默认情况下启用了主实时保护功能，但可以使用 **本地组策略编辑器** 禁用它。

### <a name="to-disable-real-time-protection-in-group-policy"></a>在组策略中禁用实时保护

1. 打开 **本地组策略编辑器**。

   1. 在Windows 10或Windows 11任务栏搜索框中，键 **入 gpedit**。
   2. 在 **“最佳匹配**”下，选择 **“编辑组策略**”以启动 **“本地组策略编辑器**”。

2. 在 **“本地组策略编辑** 器”的左窗格中，将树扩展到 **计算机配置** \> **管理模板** \> **Windows组件** \> **Microsoft Defender 防病毒** \> **实时保护**。

3. 在右侧 **的“实时保护** 详细信息”窗格中，双击 **“关闭实时保护**”。

4. 在 **“关闭实时保护** 设置”窗口中，将选项设置为 **“已启用**”。
   
5. 选择“确定”。

6. 关闭 **本地组策略编辑器**。

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

- [配置方案、高要求和实时保护](configure-protection-features-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
