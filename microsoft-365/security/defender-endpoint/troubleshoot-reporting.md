---
title: 排查报告工具Microsoft Defender 防病毒的问题
description: 在更新合规性中尝试报告Microsoft Defender 防病毒保护状态时，确定并解决常见问题
keywords: 故障排除，错误，修复，更新符合性，oms，监视器，报表，Microsoft Defender 防病毒
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
ms.localizationpriority: medium
ms.topic: article
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.collection: m365-security-compliance
ms.openlocfilehash: 8059668e5ac13b506f91a91a7088ffc6ffc0e63d
ms.sourcegitcommit: 4f56b4b034267b28c7dd165e78ecfb4b5390087d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/12/2022
ms.locfileid: "64787547"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>解决更新合规性中的 Microsoft Defender 防病毒软件报告问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender 防病毒

**平台**
- Windows

> [!IMPORTANT]
> 2020 年 3 月 31 日，将删除更新合规性Microsoft Defender 防病毒报告功能。 可以继续使用[Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)定义和查看安全合规性策略，这样可以更精细地控制安全功能和更新。

可以将Microsoft Defender 防病毒与更新符合性结合使用。 你将看到 E3、B、F1、VL 和Pro许可证的状态。 但是，对于 E5 许可证，需要使用[Microsoft Defender for Endpoint门户](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。 若要详细了解许可选项，请[参阅Windows 10产品许可选项](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)。

使用 [Windows Analytics 更新符合性获取对网络中使用Microsoft Defender 防病毒的设备或终结点的保护状态的报告](/windows/deployment/update/update-compliance-using#wdav-assessment)时，可能会遇到问题或问题。

通常，问题最常见的指标是：

- 你只看到希望看到的所有设备的少量或子集
- 你根本看不到任何设备
- 您看到的报表和信息已过时 (早于几天) 

有关与更新符合性无关的Microsoft Defender 防病毒服务相关的常见错误代码和事件 ID，请参阅[Microsoft Defender 防病毒事件](troubleshoot-microsoft-defender-antivirus.md)。

排查这些问题有三个步骤：

1. 确认已满足所有先决条件
2. 检查与基于云Windows Defender服务的连接
3. 提交支持日志

> [!IMPORTANT]
> 设备通常需要 3 天才能开始显示在更新符合性中。

## <a name="confirm-prerequisites"></a>确认先决条件

为了使设备能够正确显示在更新合规性中，必须满足更新合规性服务和Microsoft Defender 防病毒的某些先决条件：

>[!div class="checklist"]
>
> - 终结点使用Microsoft Defender 防病毒作为唯一的防病毒保护应用。 [使用任何其他防病毒应用将导致Microsoft Defender 防病毒禁用自身](microsoft-defender-antivirus-compatibility.md)，并且不会在更新符合性中报告终结点。
> - [已启用云传递的保护](enable-cloud-protection-microsoft-defender-antivirus.md)。
> - 终结点可以[连接到Microsoft Defender 防病毒云](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - 如果终结点运行Windows 10版本 1607 或更低版本，[则Windows 10诊断数据必须设置为增强级别](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。
> - 满足所有要求已经 3 天了

“可以将Microsoft Defender 防病毒与更新符合性结合使用。 你将看到 E3、B、F1、VL 和Pro许可证的状态。 但是，对于 E5 许可证，需要使用Microsoft Defender for Endpoint门户 (/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) 。 若要了解有关许可选项的详细信息，请参阅Windows 10产品许可选项”

如果满足上述先决条件，可能需要继续执行下一步，收集诊断信息并将其发送给我们。

> [!div class="nextstepaction"]
> [收集诊断数据以进行更新符合性故障排除](collect-diagnostic-data.md)

> [!TIP]
> 如果要查找其他平台的防病毒相关信息，请参阅：
> - [在 macOS 上设置Microsoft Defender for Endpoint首选项](mac-preferences.md)
> - [Mac 上的 Microsoft Defender for Endpoint](microsoft-defender-endpoint-mac.md)
> - [适用于Intune的Microsoft Defender 防病毒的 macOS 防病毒策略设置](/mem/intune/protect/antivirus-microsoft-defender-settings-macos)
> - [在 Linux 上设置Microsoft Defender for Endpoint首选项](linux-preferences.md)
> - [Microsoft Defender for Endpoint on Linux](microsoft-defender-endpoint-linux.md)
> - [在 Android 功能上配置 Defender for Endpoint](android-configure.md)
> - [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)

## <a name="related-topics"></a>相关主题

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [部署Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)
