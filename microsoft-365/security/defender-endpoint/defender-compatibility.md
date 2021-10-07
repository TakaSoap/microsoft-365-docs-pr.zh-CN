---
title: 防病毒解决方案与 Defender for Endpoint 的兼容性
description: 了解如何Windows Defender适用于终结点的 Microsoft Defender。 此外，了解使用第三方反恶意软件客户端时 Defender for Endpoint 的工作原理。
keywords: windows defender 兼容性， defender， 适用于终结点的 Microsoft Defender， 终结点的 defender， 防病毒， mde
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.date: 05/06/2021
ms.technology: mde
ms.openlocfilehash: f4fd2046e9fdeb7e0832577effb8d445232bb543
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150254"
---
# <a name="antivirus-solution-compatibility-with-microsoft-defender-for-endpoint"></a>防病毒解决方案与 Microsoft Defender for Endpoint 的兼容性

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-defendercompat-abovefoldlink)。

Microsoft Defender for Endpoint 代理依赖于Microsoft Defender 防病毒某些功能（如文件扫描）的功能。

> [!IMPORTANT]
> Defender for Endpoint 不遵循Microsoft Defender 防病毒排除设置。

你必须在 Defender for Endpoint 设备上配置安全智能更新Microsoft Defender 防病毒是否处于活动状态的反恶意软件。 有关详细信息，请参阅管理更新[Microsoft Defender 防病毒应用基线](manage-updates-baselines-microsoft-defender-antivirus.md)。

如果已载入的设备受第三方反恶意软件客户端保护，Microsoft Defender 防病毒上的设备将进入被动模式。

Microsoft Defender 防病毒将继续接收更新，mspeng.exe *进程将* 列为正在运行的服务。 但是，它不会执行扫描，也不会替换正在运行的第三方反恶意软件客户端。

the Microsoft Defender 防病毒 interface will be disabled. 设备上的用户将无法使用 Microsoft Defender 防病毒执行按需扫描或配置大多数选项。

有关详细信息，请参阅适用于终结点的[Microsoft Defender 防病毒和 Defender 兼容性主题](microsoft-defender-antivirus-compatibility.md)。
