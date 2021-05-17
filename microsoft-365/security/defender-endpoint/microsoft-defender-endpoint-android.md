---
title: Android 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Android 上安装和使用 Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， android， 安装， 部署， 卸载， intune
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 3f8a8c04f608096e5c226d6899fbbd983bd8d8c1
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52246424"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Android 上的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

本主题介绍如何在 Android 上安装、配置、更新和使用 Defender for Endpoint。

> [!CAUTION]
> 在 Android 上运行其他第三方终结点保护产品以及 Defender for Endpoint 可能会导致性能问题和不可预知的系统错误。


## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>如何在 Android 上安装 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>必备条件

-   **对于最终用户**

    -   分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。 请参阅 [适用于终结点的 Microsoft Defender 许可要求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   Intune 公司门户应用可以从 Google Play 下载[，](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)并且可在 Android 设备上使用。

        -   此外， (应用) 注册设备策略，Intune 公司门户强制执行 Intune 设备合规性策略。 [](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal) 这要求为最终用户分配一个Microsoft Intune许可证。

    -   若要详细了解如何分配许可证，请参阅 [向用户分配许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。
        

-   **对于管理员**

    -   访问 Microsoft Defender 安全中心 门户。

        > [!NOTE]
        > Microsoft Intune在 Android 上部署 Microsoft Defender for Endpoint (MDM) 唯一受支持的移动设备管理解决方案。 目前，仅支持在 Intune 中对 Android 相关设备合规性策略强制实施 Defender for Endpoint 的设备。 

    -   访问[Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心 ，将应用部署到组织中注册的用户组。
        
### <a name="network-requirements"></a>网络要求

- 为了使 Android 上的 Microsoft Defender for Endpoint 在连接到网络时正常运行，需要将防火墙/代理配置为允许访问[Microsoft Defender for Endpoint 服务 URL。](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)

### <a name="system-requirements"></a>系统要求

-   运行 Android 6.0 及以上操作系统的 Android 设备。
-   Intune 公司门户 Google [Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)下载并安装应用。 必须注册设备才能强制执行 Intune 设备合规性策略。

### <a name="installation-instructions"></a>安装说明

Android 上的 Microsoft Defender for Endpoint 支持在已注册的设备的两种模式（旧版设备管理员和 Android Enterprise安装。
**目前，具有工作配置文件的个人拥有设备和公司拥有的完全托管用户设备注册在 Android Enterprise。其他 Android Enterprise模式的支持将在准备就绪后公布。**

Android 上的 Microsoft Defender for Endpoint 部署通过 mdm Microsoft Intune (进行) 。
有关详细信息，请参阅使用 Microsoft Intune 在 Android 上[部署 Microsoft Defender for Endpoint。](android-intune.md)


> [!NOTE]
> **Android 上的 Microsoft Defender for Endpoint 现已在 [Google Play 上](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 可用。** <br> 你可以从 Intune 连接到 Google Play，以跨设备管理员和 Android Enterprise应用部署 Microsoft Defender for Endpoint 应用。 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>如何在 Android 上配置适用于终结点的 Microsoft Defender

有关如何在 Android 上配置适用于终结点功能的 Microsoft Defender 的指南可在在 Android 功能上配置 [Microsoft Defender for Endpoint 中提供](android-configure.md)。



## <a name="related-topics"></a>相关主题
- [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)
- [在 Android 功能上配置 Microsoft Defender for Endpoint](android-configure.md)

