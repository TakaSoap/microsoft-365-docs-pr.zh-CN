---
title: 获取载入到 Microsoft Defender for Endpoint 的设备
description: 跟踪将 Intune 托管的设备载入到 Microsoft Defender for Endpoint 并增加载入率。
keywords: 载入， Intune 管理， MDATP， WDATP， Microsoft Defender， Windows Defender， 高级威胁防护， 配置管理
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 09ca9fb466efd7764f7459a4754cfb30c8100bdb
ms.sourcegitcommit: 13ce4b31303a1a21ca53700a54bcf8d91ad2f8c1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51904136"
---
# <a name="get-devices-onboarded-to-microsoft-defender-for-endpoint"></a>获取载入到 Microsoft Defender for Endpoint 的设备

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-abovefoldlink)

每个载入的设备在 EDR (添加额外的终结点检测和响应) ，并提升对网络中泄露活动的可见性。 载入还确保可以检查设备是否具有易受攻击的组件以及安全配置问题，并可在攻击期间接收关键修正操作。

在你可以跟踪和管理设备的载入之前：
- [将设备注册到 Intune 管理](configure-machines.md#enroll-devices-to-intune-management)
- [确保您具有必要的权限](configure-machines.md#obtain-required-permissions)

## <a name="discover-and-track-unprotected-devices"></a>发现和跟踪未受保护的设备

载入卡通过将已实际载入 Defender for Endpoint 的 Windows 10 设备数与 Intune 管理的 Windows 10 设备的总数进行比较，提供载入率的简要概述。

![设备配置管理载入卡](images/secconmgmt_onboarding_card.png)<br>
*显示已载入设备与 Intune 管理的 Windows 10 设备总数比较的卡片*

>[!NOTE]
>如果你使用安全中心配置管理器、载入脚本或其他不使用 Intune 配置文件的载入方法，你可能会遇到数据差异。 若要解决这些差异，请为 Defender for Endpoint 载入创建相应的 Intune 配置文件，并将该配置文件分配给你的设备。

## <a name="onboard-more-devices-with-intune-profiles"></a>使用 Intune 配置文件载入更多设备

Defender for Endpoint 提供了几个用于载入 [Windows 10 设备的便捷选项](onboard-configure.md)。 但是，对于 Intune 托管的设备，你可以利用 Intune 配置文件便捷地部署 Defender for Endpoint 传感器以选择设备，从而有效地将这些设备载入服务。

从 **载入卡中** ， **选择载入更多设备** 以在 Intune 上创建和分配配置文件。 该链接将你指向 Intune 上的设备合规性页面，该页面提供了载入状态类似的概述。

![Intune 设备管理上的 Microsoft Defender for Endpoint 设备合规性页面](images/secconmgmt_onboarding_1deviceconfprofile.png)<br>
   *Intune 设备管理上的 Microsoft Defender for Endpoint 设备合规性页面*

>[!TIP]
>或者，你可以从 [Microsoft Defender](https://portal.azure.com/) ATP 的所有服务 > Intune > 设备合规性> Microsoft Azure 门户中的 Defender for **Endpoint 载入合规性页面**。

>[!NOTE]
> 如果你想要查看最新的设备数据，请单击没有 **ATP 传感器的设备列表**。

从设备合规性页面，专门为部署 Defender for Endpoint 传感器创建配置文件，并将该配置文件分配给你想要载入的设备。 为此，您可以：

- 选择 **"创建设备配置文件"将 ATP 传感器** 配置为从预定义的设备配置文件开始。
- 从头开始创建设备配置文件。

有关详细信息，请阅读 [有关使用 Intune 设备](https://docs.microsoft.com/intune/advanced-threat-protection#onboard-devices-by-using-a-configuration-profile)配置文件将设备载入 Defender for Endpoint 的信息。

>想要体验 Microsoft Defender ATP？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-onboardconfigure-belowfoldlink)

## <a name="related-topics"></a>相关主题
- [确保设备配置正确](configure-machines.md)
- [提高 Defender for Endpoint 安全基线的合规性](configure-machines-security-baseline.md)
- [优化 ASR 规则部署和检测](configure-machines-asr.md)
