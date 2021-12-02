---
title: 使用 Microsoft Endpoint Manager 管理设备上的 Microsoft Defender for Endpoint 配置设置
description: 了解如何通过 Microsoft Defender for Endpoint 在 Microsoft Endpoint Manager中启用安全设置。
keywords: 设备管理，为终结点设备配置 Microsoft Defender，Microsoft Endpoint Manager
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: a8a57b14480c45ddbc154d71bc4f2ded315c83ae
ms.sourcegitcommit: 0251d5c6cb141055c93c83a402c3dc52c7a70dcc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/02/2021
ms.locfileid: "61262835"
---
# <a name="manage-microsoft-defender-for-endpoint-configuration-settings-on-devices-with-microsoft-endpoint-manager"></a>使用 Microsoft Endpoint Manager 管理设备上的 Microsoft Defender for Endpoint 配置设置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [在设备上使用 Microsoft Defender for Endpoint 管理Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



[!include[Prerelease information](../../includes/prerelease.md)]


> 想要体验适用于终结点的 Defender？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)。


Microsoft Defender for Endpoint 的安全管理是一项功能，适用于不由 Microsoft Endpoint Manager（Microsoft Intune 或 Microsoft Endpoint Configuration Manager）管理的设备，用于接收 Microsoft Defender 的安全配置直接从Endpoint Manager。


有关安全配置管理（包括先决条件、支持的平台等）详细信息，请参阅使用安全配置管理在设备上管理[Microsoft Defender for Endpoint Microsoft Endpoint Manager。](/mem/intune/protect/mde-security-integration)



[!INCLUDE [Prerequisites](../../includes/security-config-mgt-prerequisites.md)]

>[!NOTE]
>此功能将逐步推出。 

有关安全配置管理详细信息，请参阅使用安全配置管理在设备上管理[Microsoft Defender Microsoft Endpoint Manager。](/mem/intune/protect/mde-security-integration)

如果遇到注册问题，请参阅解决 [安全配置管理载入问题](troubleshoot-security-config-mgt.md)。

> [!NOTE]
> 此功能不适用于已注册 Intune 或 Configuration Manager Microsoft Endpoint Manager (的设备) 。 注册到 Intune 的设备将继续通过已建立的管理渠道接收策略。

## <a name="identify-onboarded-devices"></a>标识载入的设备

使用以下步骤验证终结点是否成功完成了 Microsoft Defender 终结点载入过程的安全管理。

1.  验证设备是否显示在设备的"设备清单"[部分Microsoft 365 Defender。](https://security.microsoft.com/)

2.  在[Azure Active Directory门户](https://aad.portal.azure.com/#blade/Microsoft_AAD_Devices/DevicesMenuBlade/Devices/menuId/)中，验证设备已成功注册。

3.  在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/mDMDevicesPreview)管理中心 中，通过在所有设备中查找设备，验证>**注册** 成功。


## <a name="offboard-devices"></a>载出设备
若要通过适用于终结点的 Microsoft Defender 安全管理载入的载出设备，请参阅 [Microsoft Defender for Endpoint 服务中的载出设备](offboard-machines.md)。

>[!NOTE]
>如果启用了防 [篡改保护，](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) 则将其禁用。

## <a name="troubleshooting-security-management"></a>安全管理疑难解答 
若要解决适用于终结点注册问题的 Microsoft Defender 安全管理，请参阅解决与 [Microsoft Defender for Endpoint 的安全管理相关的载入问题](troubleshoot-security-config-mgt.md)。

## <a name="related-topic"></a>相关主题
- [解决与 Microsoft Defender for Endpoint 的安全管理相关的载入问题](troubleshoot-security-config-mgt.md)
- [在设备上使用 Microsoft Defender for Endpoint 管理Microsoft Endpoint Manager](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-mde-security-configuration-management)
