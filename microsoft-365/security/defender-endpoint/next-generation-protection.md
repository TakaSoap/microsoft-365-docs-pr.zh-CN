---
title: Microsoft Defender for Endpoint 中的下一代保护概述
description: 获取 Microsoft Defender for Endpoint 中下一代保护的概述。 通过使用旨在捕获所有类型新威胁的下一代保护，巩固网络的安全外围。
keywords: Microsoft Defender 防病毒、windows defender、反恶意软件、病毒、恶意软件、威胁、检测、保护、安全
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.reviewer: mkaminska
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.collection: M365-security-compliance
ms.openlocfilehash: 71cfbfe44525d67362ad7acc2c9d063ef0bb9ffd
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64790341"
---
# <a name="next-generation-protection-overview"></a>下一代保护概述

**适用对象**

- Microsoft Defender 防病毒
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)

**平台**
- Windows

Microsoft Defender for Endpoint 包括加强网络安全外围的下一代保护。 下一代保护旨在捕获所有类型的新威胁。 除了 Microsoft Defender 防病毒，下一代保护服务还包括以下功能：

- [基于行为、启发式和实时防病毒保护](configure-protection-features-microsoft-defender-antivirus.md)，包括使用文件、进程行为监视和其他启发式（也称为 *实时保护*）始终进行的扫描。 它还包括检测和阻止被视为不安全、但可能不会被检测为恶意软件的应用。
- [云提供的保护](cloud-protection-microsoft-defender-antivirus.md)，包括对新兴威胁近乎即时的检测和阻止。
- [专用保护和产品更新](manage-updates-baselines-microsoft-defender-antivirus.md)，包括与保持 Microsoft Defender 防病毒最新相关的更新。

> [!TIP]
> 下一代保护包含在 Microsoft Defender for Endpoint 计划 1 和计划 2 中。 [了解有关 Defender for Endpoint 计划 1 和计划 2 的详细信息](defender-endpoint-plan-1-2.md)

## <a name="try-a-demo"></a>尝试演示！

请访问 [Microsoft Defender for Endpoint 演示网站](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)，确认以下保护功能正常工作，并使用演示场景对其进行探索：

- 云端保护
- 首次看到时 (BAFS) 保护
- 潜在有害应用程序 (PUA) 保护

> [!NOTE]
> 位于 demo.wd.microsoft.com 处的 Defender for Endpoint 演示网站已弃用，并将在未来删除。

## <a name="configure-next-generation-protection-services"></a>配置下一代保护服务

有关如何配置下一代保护服务的信息，请参阅[配置 Microsoft Defender 防病毒功能](configure-microsoft-defender-antivirus-features.md)。

> [!NOTE]
> 在 Windows Server 中，配置和管理与在 Windows 客户端中大致相同。但存在一些差异。 

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [设置 macOS 上 Microsoft Defender for Endpoint 的首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于 Intune 的 Microsoft Defender 防病毒软件的 macOS 防病毒程序策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [设置 Linux 上 Microsoft Defender for Endpoint 的首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置 Microsoft Defender for Endpoint](ios-configure-features.md)

