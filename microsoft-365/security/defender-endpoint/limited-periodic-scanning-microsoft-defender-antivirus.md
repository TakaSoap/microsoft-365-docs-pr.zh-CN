---
title: 启用有限的定期Microsoft Defender 防病毒扫描功能
description: 通过有限的定期扫描，除了其他已安装的 AV 提供程序外，还可以使用Microsoft Defender 防病毒
keywords: lps， limited， 定期， 扫描， 扫描， 兼容性， 第三方， 其他 av， 禁用
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.date: 10/18/2018
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 5201366ee003efab1edd5a0a536c45db4ec7aabc
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64788889"
---
# <a name="use-limited-periodic-scanning-in-microsoft-defender-antivirus"></a>在 Microsoft Defender 防病毒程序内使用有限的定期扫描

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

有限定期扫描是一种特殊类型的威胁检测和修正，可以在Windows 10或Windows 11设备上安装其他防病毒产品时启用。

它只能在某些情况下启用。 有关有限定期扫描以及Microsoft Defender 防病毒如何与其他防病毒产品配合工作的详细信息，[请参阅Microsoft Defender 防病毒兼容性](microsoft-defender-antivirus-compatibility.md)。

**Microsoft 不建议在企业环境中使用此功能。此功能主要面向使用者。** 此功能仅使用Microsoft Defender 防病毒功能的有限子集来检测恶意软件，并且无法检测到大多数恶意软件和可能不需要的软件。 此外，管理和报告功能将受到限制。 Microsoft 建议企业选择其主要防病毒解决方案，并专门使用它。

## <a name="how-to-enable-limited-periodic-scanning"></a>如何启用有限的定期扫描

默认情况下，如果未安装其他防病毒产品，或者其他产品过期、过期或无法正常工作，Microsoft Defender 防病毒将在Windows 10或Windows 11设备上启用自身。

如果启用了Microsoft Defender 防病毒，则通常的选项将显示在该设备上对其进行配置：

:::image type="content" source="images/vtp-wdav.png" alt-text="显示 Microsoft Defender AV 选项（包括扫描选项、设置和更新选项）的Windows 安全中心应用" lightbox="images/vtp-wdav.png":::

如果安装并正常运行另一个防病毒产品，Microsoft Defender 防病毒将禁用自身。 Windows 安全中心应用将更改 **“病毒&威胁防护**”部分，以显示有关 AV 产品的状态，并提供指向产品的配置选项的链接。

在任何第三方 AV 产品下面，新链接将显示为 **Microsoft Defender 防病毒选项**。 单击此链接将展开以显示启用有限定期扫描的切换。 请注意，有限的定期选项是用于启用或禁用定期扫描的开关。 

将开关滑动到 **On** 将显示第三方 AV 产品下的标准 Microsoft Defender AV 选项。 有限的定期扫描选项将显示在页面底部。

## <a name="related-articles"></a>相关文章

- [配置方案、高要求和实时保护](configure-protection-features-microsoft-defender-antivirus.md)
- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)