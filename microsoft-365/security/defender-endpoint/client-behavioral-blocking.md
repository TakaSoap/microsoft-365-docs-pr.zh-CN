---
title: 客户端阻止
description: 客户端行为阻止是 Microsoft Defender for Endpoint 中的行为阻止和包含功能的一部分
keywords: 行为阻止， 快速保护， 客户端行为， Microsoft Defender for Endpoint
search.product: eADQiWindows 10XVcnh
ms.pagetype: security
author: denisebmsft
ms.author: deniseb
manager: dansimp
ms.reviewer: shwetaj
audience: ITPro
ms.topic: article
ms.prod: m365-security
localization_priority: Normal
ms.custom:
- next-gen
- edr
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.technology: mde
ms.openlocfilehash: c58c81cd4623ec03850c167cad285e052413174c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51933417"
---
# <a name="client-behavioral-blocking"></a>客户端阻止

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

## <a name="overview"></a>概述

客户端行为阻止是 Defender for Endpoint 中行为阻止 [和](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/behavioral-blocking-containment) 包含功能的一个组件。 由于在设备上检测到可疑行为 (也称为客户端或终结点) ，因此 (或应用程序等项目) 自动阻止、检查和修正。 

:::image type="content" source="images/pre-execution-and-post-execution-detection-engines.png" alt-text="云和客户端保护":::

防病毒保护在与云保护配对时效果最佳。

## <a name="how-client-behavioral-blocking-works"></a>客户端行为阻止的工作原理

[Microsoft Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)检测设备上可疑行为、恶意代码、无文件攻击和内存中攻击等。 当检测到可疑行为时，Microsoft Defender 防病毒监控这些可疑行为并将其进程树发送到云保护服务。 机器学习在毫秒内区分恶意应用程序和良好行为，并分类每个项目。 在几乎实时中，只要发现项目是恶意项目，就会在设备上被阻止。 

只要检测到可疑行为，就会生成[警报](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/alerts-queue)，并且该警报 [https://securitycenter.windows.com](https://securitycenter.windows.com) Microsoft Defender 安全中心 () 。

客户端行为阻止非常有效，因为它不仅有助于防止攻击启动，还有助于阻止已开始执行的攻击。 此外， [通过反馈循环](feedback-loop-blocking.md) (行为阻止和) 功能，可以阻止组织中其他设备的攻击。

## <a name="behavior-based-detections"></a>基于行为的检测

基于行为的检测根据[MITRE ATT&CK 矩阵进行命名Enterprise。](https://attack.mitre.org/matrices/enterprise) 命名约定有助于识别观测到恶意行为的攻击阶段：


|策略 |   检测威胁名称 |
|----|----|
|初始访问 | Behavior：Win32/InitialAccess.*！ml |
|执行  | Behavior：Win32/Execution.*！ml |
|持久性    | Behavior：Win32/Persistence.*！ml |
|特权提升   | Behavior：Win32/PrivilegeEscalation.*！ml |
|防御者    | Behavior：Win32/DefenseEvasion.*！ml |
|凭据访问  | Behavior：Win32/CredentialAccess.*！ml |
|发现  | Behavior：Win32/Discovery.*！ml |
|横向移动 | Behavior：Win32/LateralMovement.*！ml |
|集合 |   Behavior：Win32/Collection.*！ml |
|命令和控件 | Behavior：Win32/CommandAndControl.*！ml |
|Exfiltration   | Behavior：Win32/Exfiltration.*！ml |
|影响 | Behavior：Win32/Impact.*！ml |
|未分类  | Behavior：Win32/Generic.*！ml |

> [!TIP]
> 若要了解有关特定威胁的信息，请参阅最近的 **[全球威胁活动](https://www.microsoft.com/wdsi/threats)**。


## <a name="configuring-client-behavioral-blocking"></a>配置客户端行为阻止

如果你的组织对 Endpoint 使用 Defender，则默认情况下会启用客户端行为阻止。 但是，若要从所有 Defender for Endpoint 功能[](behavioral-blocking-containment.md)（包括行为阻止和抑制）中获益，请确保已启用并配置了 Defender for Endpoint 的以下特性和功能：

- [Defender for Endpoint 基线](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [载入到适用于终结点的 Defender 的设备](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/onboard-configure)

- [块模式下的 EDR](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [减少攻击面](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [下一代保护](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (防病毒) 

## <a name="related-articles"></a>相关文章

- [行为阻止和控制](behavioral-blocking-containment.md)

- [反馈循环阻止](feedback-loop-blocking.md)

- [ (博客) 行为阻止和抑制：将光学镜头转换为保护](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [适用于终结点资源的有用 Defender](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/helpful-resources)
