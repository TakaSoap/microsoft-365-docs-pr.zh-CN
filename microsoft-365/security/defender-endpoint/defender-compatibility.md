---
title: Microsoft Defender 防病毒与适用于终结点的 Defender 的兼容性
description: 了解 Windows Defender Defender for Endpoint 的工作原理，以及它如何使用第三方反恶意软件客户端。
keywords: windows defender 兼容性， defender， microsoft defender atp， 适用于终结点的 defender， 防病毒， mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: 63dca2694dae5dee924c9a0a02a660003907c42b
ms.sourcegitcommit: 2a708650b7e30a53d10a2fe3164c6ed5ea37d868
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51165953"
---
# <a name="microsoft-defender-antivirus-compatibility-with-microsoft-defender-for-endpoint"></a>Microsoft Defender 防病毒与 Microsoft Defender for Endpoint 的兼容性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Microsoft Defender for Endpoint 代理依赖 Microsoft Defender 防病毒进行某些功能，如文件扫描。

>[!IMPORTANT]
>Defender for Endpoint 不遵循 Microsoft Defender 防病毒排除设置。 

你必须在 Defender for Endpoint 设备上配置安全智能更新，无论 Microsoft Defender 防病毒是否是活动的反恶意软件。 有关详细信息，请参阅管理 [Microsoft Defender 防病毒更新和应用基线](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/manage-updates-baselines-microsoft-defender-antivirus.md)。

如果载入的设备受第三方反恶意软件客户端保护，该终结点上的 Microsoft Defender 防病毒将进入被动模式。

Microsoft Defender 防病毒将继续接收更新 *，mspeng.exe* 进程将列为正在运行的服务，但它不会执行扫描，并且不会替换正在运行的第三方反恶意软件客户端。

Microsoft Defender 防病毒界面将被禁用，并且设备上的用户将不能使用 Microsoft Defender 防病毒执行按需扫描或配置大多数选项。

有关详细信息，请参阅 Microsoft [Defender 防病毒和适用于终结点的 Defender 兼容性主题](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-antivirus/microsoft-defender-antivirus-compatibility)。
