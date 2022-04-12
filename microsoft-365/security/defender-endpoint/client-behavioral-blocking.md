---
title: 客户端行为阻止
description: 客户端行为阻止是Microsoft Defender for Endpoint的行为阻止和遏制功能的一部分
keywords: 行为阻止，快速保护，客户端行为，Microsoft Defender for Endpoint
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
ms.localizationpriority: medium
ms.custom:
- next-gen
- edr
ms.collection: m365-security-compliance
ms.technology: mde
ms.openlocfilehash: f19e354a23af03abd905591993197ff8f484ceff
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788383"
---
# <a name="client-behavioral-blocking"></a>客户端行为阻止

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)
- Microsoft Defender 防病毒

**平台**
- Windows

> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

## <a name="overview"></a>概述

客户端行为阻止是 Defender for Endpoint [中行为阻止和遏制功能](behavioral-blocking-containment.md) 的组成部分。 由于在设备上检测到可疑行为， (也称为客户端或终结点) ，因此会自动阻止、检查和修正 (项目，例如文件或应用程序) 。

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="云和客户端保护" lightbox="images/pre-execution-and-post-execution-detection-engines.png":::

与云保护配对时，防病毒保护效果最佳。

## <a name="how-client-behavioral-blocking-works"></a>客户端行为阻止的工作原理

[Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)可以在设备上检测可疑行为、恶意代码、无文件攻击和内存中攻击等。 检测到可疑行为时，Microsoft Defender 防病毒监视这些可疑行为及其进程树并将其发送到云保护服务。 机器学习在毫秒内区分恶意应用程序和良好行为，并对每个项目进行分类。 几乎实时地发现某个项目是恶意的，它就会在设备上被阻止。

每当检测到可疑行为时，就会生成[警报](alerts-queue.md)，并在检测到并停止攻击时可见：警报（如“初始访问警报”）会触发并显示在[以前Microsoft 365 Defender)  (Microsoft 365 Defender门户](/microsoft-365/security/defender/microsoft-365-defender)中。

客户端行为阻止是有效的，因为它不仅有助于防止攻击启动，还有助于阻止已开始执行的攻击。 此外，由于 [反馈循环阻止](feedback-loop-blocking.md) (行为阻止和遏制) 的其他功能，组织中的其他设备上会阻止攻击。

## <a name="behavior-based-detections"></a>基于行为的检测

基于行为的检测是根据 [MITRE ATT&CK 矩阵为Enterprise命名的](https://attack.mitre.org/matrices/enterprise)。 命名约定有助于确定观察到恶意行为的攻击阶段：

|策略|检测威胁名称|
|---|---|
|初始访问|`Behavior:Win32/InitialAccess.*!ml`|
|执行|`Behavior:Win32/Execution.*!ml`|
|持久性|`Behavior:Win32/Persistence.*!ml`|
|特权提升|`Behavior:Win32/PrivilegeEscalation.*!ml`|
|防御规避|`Behavior:Win32/DefenseEvasion.*!ml`|
|凭据访问|`Behavior:Win32/CredentialAccess.*!ml`|
|发现|`Behavior:Win32/Discovery.*!ml`|
|横向移动|`Behavior:Win32/LateralMovement.*!ml`|
|集合|`Behavior:Win32/Collection.*!ml`|
|命令和控制|`Behavior:Win32/CommandAndControl.*!ml`|
|外泄|`Behavior:Win32/Exfiltration.*!ml`|
|影响|`Behavior:Win32/Impact.*!ml`|
|未分类|`Behavior:Win32/Generic.*!ml`|

> [!TIP]
> 若要详细了解特定威胁，请参阅 **[最近的全球威胁活动](https://www.microsoft.com/wdsi/threats)**。

## <a name="configuring-client-behavioral-blocking"></a>配置客户端行为阻止

如果组织使用 Defender for Endpoint，默认情况下会启用客户端行为阻止。 但是，若要从所有 Defender for Endpoint 功能（包括 [行为阻塞和遏制）](behavioral-blocking-containment.md)中获益，请确保已启用和配置 Defender for Endpoint 的以下功能和功能：

- [Defender for Endpoint 基线](configure-machines-security-baseline.md)
- [载入到 Defender for Endpoint 的设备](onboard-configure.md)
- [块模式下的 EDR](edr-in-block-mode.md)
- [减少攻击面](attack-surface-reduction.md)
- [下一代防护](configure-microsoft-defender-antivirus-features.md) (防病毒、反恶意软件和其他威胁防护功能) 

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)
