---
title: Android 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Android 上安装和使用 Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， android， 安装， 部署， 卸载， intune
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 7d4e553e89f83f9b641367bb4037b4eb7da21f8b
ms.sourcegitcommit: 6e90baef421ae06fd790b0453d3bdbf624b7f9c0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/12/2022
ms.locfileid: "62767036"
---
# <a name="microsoft-defender-for-endpoint-on-android"></a>Android 上的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

本主题介绍如何在 Android 上安装、配置、更新和使用 Defender for Endpoint。

> [!CAUTION]
> 在 Android 上运行其他第三方终结点保护产品以及 Defender for Endpoint 可能会导致性能问题和不可预知的系统错误。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>如何在 Android 上安装 Microsoft Defender for Endpoint

### <a name="prerequisites"></a>先决条件

- **对于最终用户**：
  - 分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。 请参阅 [适用于终结点的 Microsoft Defender 许可要求](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)
  - Intune 公司门户应用可以从 [Google Play 下载，](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal)并且可在 Android 设备上使用。
  - 此外， (应用) 注册设备策略，Intune 公司门户强制执行 Intune [](/mem/intune/user-help/enroll-device-android-company-portal) 设备合规性策略。 这要求为最终用户分配一个Microsoft Intune许可证。
  - 若要详细了解如何分配许可证，请参阅 [向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

- **对于管理员**
   - 访问 Microsoft 365 Defender 门户。
   - 访问[Microsoft Endpoint Manager中心](https://go.microsoft.com/fwlink/?linkid=2109431)
       - 将应用部署到组织中注册的用户组。
       - 在应用保护策略中为终结点风险信号配置 Microsoft Defender。
  
    > [!NOTE]
    > - 对于未使用移动设备管理 (MDM) 注册但正在使用 Intune 管理移动应用程序的设备，Microsoft Defender for Endpoint 现在将保护扩展到托管应用程序 (MAM) 中的组织数据。 它还向使用其他企业移动性管理解决方案的客户扩展了此支持，同时仍使用 Intune 在 [MAM (移动应用程序) ](/mem/intune/apps/mam-faq)。
    > - 此外，Microsoft Defender for Endpoint 已支持使用 In (tune 移动设备管理或 MDM) 注册的设备。


### <a name="network-requirements"></a>网络要求

- 为了使 Android 上的 Microsoft Defender for Endpoint 在连接到网络时正常运行，需要配置防火墙/代理以允许访问 [Microsoft Defender for Endpoint 服务 URL](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

### <a name="system-requirements"></a>系统要求

- 运行 Android 6.0 及以上的移动电话。 **目前不支持运行 Android go、平板电脑和其他运行 Android 的移动设备的移动电话。**
- Intune 公司门户 Google [Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 下载并安装应用。 必须注册设备才能强制执行 Intune 设备合规性策略。

### <a name="installation-instructions"></a>安装说明

Android 上的 Microsoft Defender for Endpoint 支持在已注册的设备的两种模式（ 旧版设备管理员和 Android Enterprise安装。 **目前，具有工作配置文件的个人拥有设备和公司拥有的完全托管用户设备注册在 Android Enterprise。其他 Android Enterprise模式的支持将在准备就绪后公布。**

- 在 Android 上部署 Microsoft Defender for Endpoint 是通过 mdm Microsoft Intune () 。 有关详细信息，请参阅在 [Android 上部署 Microsoft Defender for Endpoint with Microsoft Intune](android-intune.md)。
- 在未使用 Intune 移动设备管理 (MDM) 注册的设备上安装 Microsoft Defender for Endpoint，请参阅在应用保护策略 (MAM) 中为终结点风险信号 [配置 Microsoft Defender ](android-configure-mam.md)。

> [!NOTE]
> **Android 上的 Microsoft Defender for Endpoint 现已在 [Google Play 上](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 可用。**
>
> 你可以从 Intune 连接到 Google Play，以跨设备管理员和 Android Enterprise应用部署 Microsoft Defender for Endpoint 应用。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>如何在 Android 上配置适用于终结点的 Microsoft Defender

有关如何在 Android 上配置适用于终结点功能的 Microsoft Defender 的指南，可在在 Android 功能上配置 [Microsoft Defender for Endpoint 中提供](android-configure.md)。

## <a name="related-topics"></a>相关主题

- [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)
- [在 Android 功能上配置 Microsoft Defender for Endpoint](android-configure.md)
- [移动应用程序管理 (MAM) 基础知识](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
