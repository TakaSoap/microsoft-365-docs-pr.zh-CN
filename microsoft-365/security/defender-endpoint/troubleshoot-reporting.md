---
title: Microsoft Defender AV 报告工具问题疑难解答
description: 确定并解决尝试在更新合规性中报告 Microsoft Defender AV 保护状态的常见问题
keywords: 疑难解答， 错误， 修复， 更新合规性， oms， 监视器， 报告， Microsoft Defender AV
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: manage
ms.sitesec: library
ms.pagetype: security
localization_priority: normal
author: denisebmsft
ms.author: deniseb
ms.custom: nextgen
ms.reviewer: ''
manager: dansimp
ms.technology: mde
ms.openlocfilehash: 50136c620450861c41513650f27bf24fc782e968
ms.sourcegitcommit: 7a339c9f7039825d131b39481ddf54c57b021b11
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/14/2021
ms.locfileid: "51764527"
---
# <a name="troubleshoot-microsoft-defender-antivirus-reporting-in-update-compliance"></a>解决更新合规性中的 Microsoft Defender 防病毒软件报告问题

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**适用于：**

- [Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/)

> [!IMPORTANT]
> 2020 年 3 月 31 日，将删除更新合规性的 Microsoft Defender 防病毒报告功能。 你可以继续使用 [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)定义和查看安全合规性策略，从而可以更精细地控制安全功能和更新。

可以将 Microsoft Defender 防病毒与更新合规性一同使用。 你将看到 E3、B、F1、VL 和 Pro 许可证的状态。 但是，对于 E5 许可证，你需要使用 [Microsoft Defender for Endpoint 门户](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。 若要了解有关许可选项的详细信息，请参阅 [Windows 10 产品许可选项](https://www.microsoft.com/licensing/product-licensing/windows10.aspx)。

当你使用 [Windows Analytics 更新](/windows/deployment/update/update-compliance-using#wdav-assessment) 合规性获取有关网络中使用 Microsoft Defender 防病毒的设备或终结点的保护状态的报告时，你可能会遇到问题。

通常，最常见的问题指标是：
- 你只能看到预期看到的所有设备的一小部分或一部分
- 你完全看不到任何设备
- 您看到的报告和信息已过时 (超过几天) 

有关与 Microsoft Defender 防病毒服务相关的与更新合规性不相关的常见错误代码和事件 ID，请参阅 [Microsoft Defender 防病毒事件](troubleshoot-microsoft-defender-antivirus.md)。 

解决这些问题有三个步骤：

1. 确认已满足所有先决条件
2. 检查与基于云的Windows Defender的连接
3. 提交支持日志

>[!IMPORTANT]
>设备通常需要 3 天时间开始在更新合规性中显示。


## <a name="confirm-prerequisites"></a>确认先决条件

为了使设备正确显示在更新合规性中，必须满足更新合规性服务和 Microsoft Defender 防病毒的某些先决条件：

>[!div class="checklist"]
>- 终结点使用 Microsoft Defender 防病毒作为唯一的防病毒保护应用。 [使用任何其他防病毒应用将导致 Microsoft Defender AV](microsoft-defender-antivirus-compatibility.md) 自行禁用，并且不会在更新合规性中报告终结点。
> - [云提供的保护已启用](enable-cloud-protection-microsoft-defender-antivirus.md)。
> - 终结点可以 [连接到 Microsoft Defender AV 云](configure-network-connections-microsoft-defender-antivirus.md#validate-connections-between-your-network-and-the-cloud)
> - 如果终结点运行的是 Windows 10 版本 1607 或更早版本，则必须将 [Windows 10 诊断数据设置为增强级别](/windows/configuration/configure-windows-diagnostic-data-in-your-organization#enhanced-level)。
> - 已满足所有要求 3 天

"你可以将 Microsoft Defender 防病毒与更新合规性一同使用。 你将看到 E3、B、F1、VL 和 Pro 许可证的状态。 但是，对于 E5 许可证，你需要使用 Microsoft Defender for Endpoint 门户 https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints) (。 若要了解有关许可选项的详细信息，请参阅 Windows 10 产品许可选项"

如果满足上述所有先决条件，您可能需要继续执行下一步以收集诊断信息并将其发送给我们。

> [!div class="nextstepaction"]
> [收集诊断数据以进行更新合规性疑难解答](collect-diagnostic-data.md)  

## <a name="related-topics"></a>相关主题

- [Windows 10 中的 Microsoft Defender 防病毒](microsoft-defender-antivirus-in-windows-10.md)
- [部署 Microsoft Defender 防病毒](deploy-manage-report-microsoft-defender-antivirus.md)