---
title: 下一代保护
description: 了解如何管理、配置和使用 Microsoft Defender 防病毒内置反恶意软件和防病毒保护。
keywords: Microsoft Defender 防病毒， windows defender， 反恶意软件， scep， system center endpoint protection， system center configuration manager， 病毒， 恶意软件， 威胁， 检测， 保护， 安全
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: high
author: denisebmsft
ms.author: deniseb
ms.reviewer: ''
manager: dansimp
ms.custom: nextgen
ms.technology: mde
ms.openlocfilehash: 9d8ab5be45e671fb07df0d9d1f46eb626d9dd149
ms.sourcegitcommit: 3fe7eb32c8d6e01e190b2b782827fbadd73a18e6
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2021
ms.locfileid: "51689930"
---
# <a name="next-generation-protection"></a>下一代保护

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

## <a name="microsoft-defender-antivirus-your-next-generation-protection"></a>Microsoft Defender 防病毒：你的下一代保护

Microsoft Defender 防病毒是 Microsoft Defender for Endpoint 的下一代保护组件。 此保护将机器学习、大数据分析、深度威胁防范研究和 Microsoft 云基础结构汇集在一起，以保护企业组织的设备。 下一代保护服务包括以下功能：

- 基于行为的[启发](configure-protection-features-microsoft-defender-antivirus.md)式实时防病毒保护，其中包括使用文件和进程行为监视以及其他启发式 (扫描，也称为实时保护) 。  它还包括检测和阻止被视为不安全但可能未检测为恶意软件的应用。
- [云提供的保护](cloud-protection-microsoft-defender-antivirus.md)，包括快速检测和阻止新出现的威胁。
- [专用保护和产品更新](manage-updates-baselines-microsoft-defender-antivirus.md)，其中包括与使 Microsoft Defender 防病毒保持最新相关的更新。

## <a name="try-a-demo"></a>试用演示！

访问 [Microsoft Defender for Endpoint 演示网站](https://demo.wd.microsoft.com?ocid=cx-wddocs-testground) 以确认以下保护功能是否正常工作，然后使用演示方案探索它们：
- 云保护
- 在 BAFS 保护 (首次看到) 阻止
- PUA 保护 (可能不需要) 的应用程序

## <a name="minimum-system-requirements"></a>最低系统要求

从 Windows 10 起，Microsoft Defender 防病毒具有相同的硬件要求。 有关更多信息，请参阅以下资源：

- [最低硬件要求](/windows-hardware/design/minimum/minimum-hardware-requirements-overview)
- [硬件组件指南](/windows-hardware/design/component-guidelines/components)

## <a name="configure-next-generation-protection-services"></a>配置下一代保护服务

若要了解如何配置下一代保护服务，请参阅配置 [Microsoft Defender 防病毒功能](configure-microsoft-defender-antivirus-features.md)。

> [!Note]  
> 配置和管理在 Windows Server 2016 和 Windows Server 2019 中基本相同，同时运行 Microsoft Defender 防病毒;但是，存在一些差异。 若要了解更多信息，请参阅 [Windows Server 2016 和 Windows Server 2019 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)。

## <a name="see-also"></a>另请参阅

- [Windows Server 2016 和 2019 上的 Microsoft Defender 防病毒](microsoft-defender-antivirus-on-windows-server.md)
- [Microsoft Defender 防病毒管理和配置](configuration-management-reference-microsoft-defender-antivirus.md)
- [评估 Microsoft Defender 防病毒保护](evaluate-microsoft-defender-antivirus.md)