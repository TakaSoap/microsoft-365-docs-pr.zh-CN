---
title: Android 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Android 上安装和使用 Microsoft Defender for Endpoint
keywords: microsoft， defender， atp， android， 安装， 部署， 卸载， intune
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
ms.openlocfilehash: 8a78fc7e07f89c2e13a698ee526403989f26dd65
ms.sourcegitcommit: 4acf613587128cae27e0fd470d1216b509775529
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2021
ms.locfileid: "51768838"
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

### <a name="prerequisites"></a>先决条件

-   **对于最终用户**

    -   分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。 请参阅 [适用于终结点的 Microsoft Defender 许可要求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)

    -   可从 Google [Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 下载 Intune 公司门户应用，并且可在 Android 设备上使用。

        -   此外， (设备) 可通过 Intune 公司门户应用[](https://docs.microsoft.com/mem/intune/user-help/enroll-device-android-company-portal)注册，以强制执行 Intune 设备合规性策略。 这需要为最终用户分配 Microsoft Intune 许可证。

    -   若要详细了解如何分配许可证，请参阅 [向用户分配许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。
        

-   **对于管理员**

    -   访问 Microsoft Defender 安全中心门户。

        > [!NOTE]
        > Microsoft Intune 是唯一受支持的移动设备管理 (MDM) 解决方案，用于部署 Android 上的 Microsoft Defender for Endpoint。 目前，仅支持在 Intune 中强制执行 Android 相关设备合规性策略的 Defender for Endpoint 设备。 

    -   访问 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，将应用部署到组织中注册的用户组。

### <a name="system-requirements"></a>系统要求

-   运行 Android 6.0 及以上操作系统的 Android 设备。
-   从 Google [Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 下载并安装 Intune 公司门户应用。 必须注册设备才能强制执行 Intune 设备合规性策略。

### <a name="installation-instructions"></a>安装说明

Android 上的 Microsoft Defender for Endpoint 支持在已注册的设备的两种模式（ 旧版设备管理员模式和 Android 企业版模式）上安装。
**目前，具有工作配置文件的个人拥有设备和公司拥有的完全托管用户设备注册在 Android 企业版中受支持。其他 Android 企业版模式的支持将在准备就绪后公布。**

在 Android 上部署 Microsoft Defender for Endpoint 是通过 Microsoft Intune (MDM) 。
有关详细信息，请参阅使用 [Microsoft Intune](android-intune.md)在 Android 上部署 Microsoft Defender for Endpoint。


> [!NOTE]
> **Android 上的 Microsoft Defender for Endpoint 现已在 [Google Play 上](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 可用。** <br> 你可以从 Intune 连接到 Google Play，以跨设备管理员和 Android 企业版注册模式部署 Microsoft Defender for Endpoint 应用。 

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>如何在 Android 上配置适用于终结点的 Microsoft Defender

有关如何在 Android 上配置适用于终结点功能的 Microsoft Defender 的指南可在在 Android 功能上配置 [Microsoft Defender for Endpoint 中提供](android-configure.md)。



## <a name="related-topics"></a>相关主题
- [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)
- [在 Android 功能上配置 Microsoft Defender for Endpoint](android-configure.md)

