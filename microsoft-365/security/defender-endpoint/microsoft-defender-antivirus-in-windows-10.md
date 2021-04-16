---
title: 下一代保护
description: 了解如何管理、配置和使用 Microsoft Defender 防病毒、内置反恶意软件和防病毒保护。
keywords: Microsoft Defender 防病毒、Windows Defender、反恶意软件、SCEP、System Center 端点保护、System Center Configuration Manager、病毒、恶意软件、威胁、检测、保护、安全
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: Priority
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 6fc6ad69df554cf20fbae0d97fcb30f211f48705
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768790"
---
# <a name="next-generation-protection"></a>下一代保护

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a>Windows Defender 防病毒：你的下一代保护

Microsoft Defender 防病毒是下一代 Microsoft Defender for Endpoint 的保护组件。 此保护结合机器学习、大数据分析、深度威胁抵御研究和 Microsoft 云基础结构来保护你的企业组织中的设备。 下一代保护服务包括以下功能：

- [基于行为、启发式和实时防病毒保护](configure-protection-features-microsoft-defender-antivirus.md)，包括使用文件、进程行为监视和其他启发式（也称为 *实时保护*）始终进行的扫描。 它还包括检测和阻止被视为不安全、但可能不会被检测为恶意软件的应用。
- [云提供的保护](cloud-protection-microsoft-defender-antivirus.md)，包括对新兴威胁近乎即时的检测和阻止。
- [专用保护和产品更新](manage-updates-baselines-microsoft-defender-antivirus.md)，包括与保持 Microsoft Defender 防病毒最新相关的更新。

## <a name="try-a-demo"></a>尝试演示！

请访问 [Microsoft Defender for Endpoint 演示网站](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground)，确认以下保护功能正常工作，并使用演示场景对其进行探索：
- 云端保护
- 首次看到时 (BAFS) 保护
- 潜在有害应用程序 (PUA) 保护

## <a name="minimum-system-requirements"></a>最低系统需求

Microsoft Defender 防病毒的硬件要求与 Windows 10 相同。 有关详细信息，请参阅以下资源：

- [最低硬件要求](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [硬件组件准则](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a>配置下一代保护服务

有关如何配置下一代保护服务的信息，请参阅[配置 Microsoft Defender 防病毒功能](configure-microsoft-defender-antivirus-features.md)。

> [!Note]  
> 在运行 Microsoft Defender 防病毒时，Windows Server 2016 和 Windows Server 2019 中的配置和管理基本相同；但也存在一些差异。 要了解更多信息，请参阅[Windows Server 2016 和 2019 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)。

## <a name="see-also"></a>另请参阅

- [Windows Server 2016 和 2019 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender 防病毒管理和配置](configuration-management-reference-microsoft-defender-antivirus.md)
- [评估 Microsoft Defender 防病毒保护](evaluate-microsoft-defender-antivirus.md)
