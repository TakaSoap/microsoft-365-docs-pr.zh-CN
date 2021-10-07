---
title: 启用有限定期Microsoft Defender 防病毒扫描功能
description: 有限定期扫描使你除了Microsoft Defender 防病毒安装的 AV 提供程序之外，还可以使用
keywords: lps， 受限， 定期， 扫描， 兼容性， 第三方， 其他 av， 禁用
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 09/03/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: b2ad3b7d1ff4ae2be4aff5e970395a9db2dc42de
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60174683"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>在 Microsoft Defender 防病毒程序内使用有限的定期扫描

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

有限定期扫描是一种特殊类型的威胁检测和修正，当你在设备上安装了其他防病毒产品Windows 10可启用。

它只能在特定情况下启用。 有关有限定期扫描以及Microsoft Defender 防病毒防病毒产品的工作方式的详细信息，请参阅Microsoft Defender 防病毒[兼容性](microsoft-defender-antivirus-compatibility.md)。

**Microsoft 不建议在企业环境中使用此功能。这是一项主要面向消费者的功能。** 此功能仅使用有限的部分Microsoft Defender 防病毒检测恶意软件，并且无法检测大多数恶意软件和可能不需要的软件。 此外，管理和报告功能将受到限制。 Microsoft 建议企业选择其主防病毒解决方案，并专门使用它。

## <a name="how-to-enable-limited-periodic-scanning"></a>如何启用有限定期扫描

默认情况下，Microsoft Defender 防病毒如果尚未安装其他防病毒产品，或者其他产品已过期、过期或无法正常工作，Windows 10 设备自行启用。

如果Microsoft Defender 防病毒，将显示常用选项以在该设备上配置它：

![Windows 安全中心 Microsoft Defender AV 选项（包括扫描选项、设置和更新选项）的应用。](images/vtp-wdav.png)

如果安装了另一个防病毒产品并正常运行，Microsoft Defender 防病毒将自行禁用。 该Windows 安全中心应用将更改病毒&威胁防护部分以显示有关 AV 产品的状态，并提供指向产品配置选项的链接。

在任何第三方 AV 产品下，新链接将显示为Microsoft Defender 防病毒 **选项**。 单击此链接将展开以显示启用有限定期扫描的切换。 请注意，有限定期选项是启用或禁用定期扫描的开关。 

将开关滑动到 **开** 将显示第三方 AV 产品下方的标准 Microsoft Defender AV 选项。 有限定期扫描选项将显示在页面底部。

## <a name="related-articles"></a>相关文章

- [配置方案、高要求和实时保护](configure-protection-features-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)