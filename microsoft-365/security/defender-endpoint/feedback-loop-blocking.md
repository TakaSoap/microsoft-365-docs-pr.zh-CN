---
title: 反馈循环阻止
description: 反馈循环阻止（也称为快速保护）是Microsoft Defender for Endpoint中的行为阻止和遏制功能的一部分
keywords: 行为阻止、快速保护、反馈阻止、Microsoft Defender for Endpoint
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
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: f68345b97d49adce2f55cffd837ca17e5b028953
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787987"
---
# <a name="feedback-loop-blocking"></a>反馈循环阻止

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

## <a name="overview"></a>概述

反馈循环阻塞（也称为快速保护）是[Microsoft Defender for Endpoint](/windows/security/threat-protection/)[中行为阻止和遏制功能](/microsoft-365/security/defender-endpoint/behavioral-blocking-containment)的组成部分。 由于反馈循环受阻，组织中的设备可以更好地免受攻击。 

## <a name="how-feedback-loop-blocking-works"></a>反馈循环阻止的工作原理

检测到可疑行为或文件（如[通过Microsoft Defender 防病毒](/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-in-windows-10)）时，有关该项目的信息将发送到多个分类器。 快速保护循环引擎检查信息并将其与其他信号相关联，以决定是否阻止文件。 快速检查和分类项目。 它会导致快速阻止确认的恶意软件，并推动整个生态系统的保护。 

在实施快速保护后，攻击可以在设备、组织中的其他设备和其他组织中的设备上停止，因为攻击试图扩大其立足点。


## <a name="configuring-feedback-loop-blocking"></a>配置反馈循环阻止

如果组织使用 Defender for Endpoint，则默认情况下会启用反馈循环阻止。 但是，通过跨 Microsoft 安全服务的 Defender for Endpoint 功能、机器学习保护功能和信号共享的组合来实现快速保护。 确保启用并配置了 Defender for Endpoint 的以下功能：

- [Microsoft Defender for Endpoint基线](/microsoft-365/security/defender-endpoint/configure-machines-security-baseline)

- [载入到Microsoft Defender for Endpoint的设备](/microsoft-365/security/defender-endpoint/onboard-configure)

- [块模式下的 EDR](/microsoft-365/security/defender-endpoint/edr-in-block-mode)

- [减少攻击面](/microsoft-365/security/defender-endpoint/attack-surface-reduction)

- [下一代保护](/windows/security/threat-protection/microsoft-defender-antivirus/configure-microsoft-defender-antivirus-features) (防病毒) 

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

- [行为阻止和控制](behavioral-blocking-containment.md)

- [ (博客) 行为阻塞和遏制：将光学转换为保护](https://www.microsoft.com/security/blog/2020/03/09/behavioral-blocking-and-containment-transforming-optics-into-protection/)

- [有用的Microsoft Defender for Endpoint资源](/microsoft-365/security/defender-endpoint/helpful-resources)
