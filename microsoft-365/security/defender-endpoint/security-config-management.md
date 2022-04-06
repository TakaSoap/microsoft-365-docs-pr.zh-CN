---
title: 使用 Microsoft Endpoint Manager 管理设备上的 Microsoft Defender for Endpoint 配置设置
description: 了解如何通过Microsoft Defender for Endpoint在Microsoft Endpoint Manager中启用安全设置。
keywords: 设备管理，配置Microsoft Defender for Endpoint设备，Microsoft Endpoint Manager
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
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 272425ede6895c84c88aa1c4ea165bc0787238bb
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665879"
---
# <a name="manage-microsoft-defender-for-endpoint-configuration-settings-on-devices-with-microsoft-endpoint-manager"></a>使用 Microsoft Endpoint Manager 管理设备上的 Microsoft Defender for Endpoint 配置设置

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**

- [使用Microsoft Endpoint Manager管理设备上的Microsoft Defender for Endpoint](/mem/intune/protect/mde-security-integration)
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)



[!include[Prerelease information](../../includes/prerelease.md)]


> 想要体验 Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-configureendpointsscript-abovefoldlink)。


Microsoft Defender for Endpoint的安全管理是未由Microsoft Endpoint Manager管理的设备的功能，Microsoft Intune或Microsoft Endpoint Configuration Manager，直接从Endpoint Manager接收 Microsoft Defender 的安全配置。


有关安全配置管理的详细信息，包括先决条件、支持的平台等，请参阅[使用Microsoft Endpoint Manager管理设备上的Microsoft Defender for Endpoint](/mem/intune/protect/mde-security-integration)。



[!INCLUDE [Prerequisites](../../includes/security-config-mgt-prerequisites.md)]

>[!NOTE]
>此功能正在逐步推出。 

有关安全配置管理的详细信息，请参阅[使用Microsoft Endpoint Manager管理设备上的Microsoft Defender for Endpoint](/mem/intune/protect/mde-security-integration)。

如果遇到注册问题，请参阅 [安全配置管理载入问题疑难解答](troubleshoot-security-config-mgt.md)。

> [!NOTE]
> 此功能不适用于已注册到Microsoft Endpoint Manager (Intune或Configuration Manager) 的设备。 注册到Intune的设备将继续通过其已建立的管理渠道接收策略。

## <a name="identify-onboarded-devices"></a>标识载入设备

使用以下步骤验证终结点是否已成功完成Microsoft Defender for Endpoint载入过程的安全管理。

1.  验证设备是否显示在Microsoft 365 Defender的"设备清单["](https://security.microsoft.com/)部分。

2.  在[Azure Active Directory门户](https://aad.portal.azure.com/#blade/Microsoft_AAD_Devices/DevicesMenuBlade/Devices/menuId/)中，验证设备是否已成功注册。

3.  在 [Microsoft Endpoint Manager管理中心](https://endpoint.microsoft.com/#blade/Microsoft_Intune_DeviceSettings/DevicesMenu/mDMDevicesPreview)，通过在 **"设备>所有设备**"部分查找设备，验证设备是否已成功注册。


## <a name="offboard-devices"></a>载入设备
若要将已通过安全管理载入的设备载入Microsoft Defender for Endpoint，请[参阅Microsoft Defender for Endpoint服务中的"载入"设备](offboard-machines.md)。

>[!NOTE]
>如果启用 [了"篡改保护](prevent-changes-to-security-settings-with-tamper-protection.md#manage-tamper-protection-for-your-organization-using-the-microsoft-365-defender-portal) "，则禁用禁用它。

## <a name="troubleshooting-security-management"></a>安全管理疑难解答 
若要排查Microsoft Defender for Endpoint注册问题的安全管理问题，请参阅Microsoft Defender for Endpoint[安全管理相关载入问题疑难解答](troubleshoot-security-config-mgt.md)。

## <a name="related-topic"></a>相关主题
- [排查与Microsoft Defender for Endpoint的安全管理相关的载入问题](troubleshoot-security-config-mgt.md)
- [使用Microsoft Endpoint Manager管理设备上的Microsoft Defender for Endpoint](/mem/intune/protect/mde-security-integration#configure-your-tenant-to-support-mde-security-configuration-management)
