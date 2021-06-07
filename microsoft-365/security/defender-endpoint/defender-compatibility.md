---
title: 防病毒解决方案与 Defender for Endpoint 的兼容性
description: 了解Windows Defender Microsoft Defender for Endpoint 的工作原理，以及它如何使用第三方反恶意软件客户端。
keywords: windows defender 兼容性， defender， 适用于终结点的 Microsoft Defender， 终结点的 defender， 防病毒， mde
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
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f5a0db755f919cb47c4cd284857ddf4e27d16996
ms.sourcegitcommit: 3b9fab82d63aea41d5f544938868c5d2cbf52d7a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/05/2021
ms.locfileid: "52782881"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>防病毒解决方案与 Microsoft Defender for Endpoint 的兼容性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-defendercompat-abovefoldlink)

Microsoft Defender for Endpoint 代理依赖于Microsoft Defender 防病毒某些功能（如文件扫描）的功能。

>[!IMPORTANT]
>Defender for Endpoint 不遵循"Microsoft Defender 防病毒排除"设置。 

你必须在 Defender for Endpoint 设备上配置安全智能更新，Microsoft Defender 防病毒反恶意软件是否有效。 有关详细信息，请参阅管理更新[Microsoft Defender 防病毒应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

如果载入的设备受第三方反恶意软件客户端保护，Microsoft Defender 防病毒上的设备将进入被动模式。

Microsoft Defender 防病毒接收更新，mspeng.exe进程将列为正在运行的服务，但它不会执行扫描，并且不会替换正在运行的第三方反恶意软件客户端。

设备Microsoft Defender 防病毒将禁用，并且设备上的用户将Microsoft Defender 防病毒执行按需扫描或配置大多数选项。

有关详细信息，请参阅适用于终结点的[Microsoft Defender 防病毒和 Defender 兼容性主题](microsoft-defender-antivirus-compatibility.md)。
