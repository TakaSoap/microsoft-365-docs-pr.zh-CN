---
title: 客户端行为阻止
description: 客户端行为阻止是 Microsoft Defender for Endpoint 的行为阻止和包含功能的一部分
keywords: 行为阻止， 快速保护， 客户端行为， Microsoft Defender for Endpoint
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
ms.openlocfilehash: 8da3f04af66568bbe79dd6a74c38b30a8a1ab891
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64470210"
---
# <a name="client-behavioral-blocking"></a>客户端行为阻止

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-assignaccess-abovefoldlink)。

## <a name="overview"></a>概述

客户端行为阻止是 Defender for Endpoint 中行为阻止 [和](behavioral-blocking-containment.md) 包含功能的一个组件。 由于在设备上检测到可疑行为 (也称为客户端或终结点) ，因此 (项目（如文件或应用程序) ）将被自动阻止、检查和修正。

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="云和客户端保护" lightbox="images/pre-execution-and-post-execution-detection-engines.png":::

防病毒保护在与云保护配对时效果最佳。

## <a name="how-client-behavioral-blocking-works"></a>客户端行为阻止的工作原理

[Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)可以检测设备的可疑行为、恶意代码、无文件攻击和内存中攻击等。 当检测到可疑行为时，Microsoft Defender 防病毒监控这些可疑行为及其进程树并将其发送到云保护服务。 机器学习在毫秒内区分恶意应用程序和良好行为，并分类每个项目。 在几乎实时中，只要发现项目是恶意项目，就会在设备上被阻止。

只要检测到可疑行为，就会生成警报[](alerts-queue.md)，且在检测到并停止攻击时可见，警报（如"初始访问警报）"将触发并出现在 [Microsoft 365 Defender](/microsoft-365/security/defender/microsoft-365-defender) 门户中 (以前Microsoft 365 Defender) 。

客户端行为阻止非常有效，因为它不仅有助于防止攻击启动，还有助于阻止已开始执行的攻击。 此外， [通过反馈循环](feedback-loop-blocking.md) (行为阻止和) 功能，可以阻止组织中其他设备的攻击。

## <a name="behavior-based-detections"></a>基于行为的检测

基于行为的检测根据 [MITRE ATT&CK 矩阵进行命名Enterprise](https://attack.mitre.org/matrices/enterprise)。 命名约定有助于识别观测到恶意行为的攻击阶段：

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
|命令和控件|`Behavior:Win32/CommandAndControl.*!ml`|
|外泄|`Behavior:Win32/Exfiltration.*!ml`|
|影响|`Behavior:Win32/Impact.*!ml`|
|未分类|`Behavior:Win32/Generic.*!ml`|

> [!TIP]
> 若要了解有关特定威胁的信息，请参阅 **[最近的全球威胁活动](https://www.microsoft.com/wdsi/threats)**。

## <a name="configuring-client-behavioral-blocking"></a>配置客户端行为阻止

如果你的组织对 Endpoint 使用 Defender，则默认情况下将启用客户端行为阻止。 但是，若要从所有 Defender for Endpoint 功能（包括行为阻止[](behavioral-blocking-containment.md)和抑制）中获益，请确保启用和配置 Defender for Endpoint 的以下特性和功能：

- [Defender for Endpoint 基线](configure-machines-security-baseline.md)
- [载入到适用于终结点的 Defender 的设备](onboard-configure.md)
- [块模式下的 EDR](edr-in-block-mode.md)
- [减少攻击面](attack-surface-reduction.md)
- [下一代 (](configure-microsoft-defender-antivirus-features.md) 防病毒、反恶意软件和其他威胁防护功能) 
