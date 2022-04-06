---
title: Android 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 Android 上安装和使用Microsoft Defender for Endpoint
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
ms.openlocfilehash: ea1c551c216dffe8d9ac4e0cedd5679146483e5e
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64666231"
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
> 在 Android 上将其他第三方终结点保护产品与 Defender for Endpoint 一起运行可能会导致性能问题和不可预测的系统错误。

## <a name="how-to-install-microsoft-defender-for-endpoint-on-android"></a>如何在 Android 上安装Microsoft Defender for Endpoint

### <a name="prerequisites"></a>先决条件

- **对于最终用户**：
  - 分配给应用的最终用户 () 的Microsoft Defender for Endpoint许可证。 请参阅[Microsoft Defender for Endpoint许可要求](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)
  - Intune 公司门户应用可以从 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 下载，可在 Android 设备上使用。
  - 此外，可以通过Intune 公司门户应用[注册](/mem/intune/user-help/enroll-device-android-company-portal)设备 () ，以强制实施Intune设备符合性策略。 这要求为最终用户分配Microsoft Intune许可证。
  - 有关如何分配许可证的详细信息，请参阅 [向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

- **对于管理员**
   - 访问Microsoft 365 Defender门户。
   - 访问[Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)
       - 将应用部署到组织中已注册的用户组。
       - 在应用保护策略中配置Microsoft Defender for Endpoint风险信号。
  
    > [!NOTE]
    > - Microsoft Defender for Endpoint现在为未使用移动设备管理 (MDM) 注册但使用Intune管理移动应用程序的设备，将保护扩展到托管应用程序 (MAM) 中的组织数据。 它还向使用其他企业移动性管理解决方案的客户提供此支持，同时仍使用Intune进行[移动应用程序管理 (MAM) ](/mem/intune/apps/mam-faq)。
    > - 此外，Microsoft Defender for Endpoint已支持使用 Intune 移动设备管理 (MDM) 注册的设备。


### <a name="network-requirements"></a>网络要求

- 若要使 Android 上的Microsoft Defender for Endpoint在连接到网络时正常运行，需要将防火墙/代理配置为[启用对Microsoft Defender for Endpoint服务 URL 的访问](configure-proxy-internet.md#enable-access-to-microsoft-defender-for-endpoint-service-urls-in-the-proxy-server)。

### <a name="system-requirements"></a>系统要求

- 运行 Android 6.0 及更高版本的移动电话。 **目前不支持运行 Android go、平板电脑和其他运行 Android 的移动设备的移动电话。**
- Intune 公司门户应用从 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.windowsintune.companyportal) 下载并安装。 要强制执行Intune设备符合性策略，需要进行设备注册。

### <a name="installation-instructions"></a>安装说明

Android 上的Microsoft Defender for Endpoint支持在已注册设备的两种模式上安装 - 旧版设备管理员和 Android Enterprise模式。 **目前，Android Enterprise支持个人拥有的具有工作配置文件和公司拥有的完全托管用户设备注册的设备。准备好后，将宣布对其他 Android Enterprise模式的支持。**

- 在 Android 上部署Microsoft Defender for Endpoint是通过 Microsoft Intune (MDM) 。 有关详细信息，请参阅[使用 Microsoft Intune 在 Android 上部署Microsoft Defender for Endpoint](android-intune.md)。
- 在未使用 Intune 移动设备管理 (MDM) 注册的设备上安装Microsoft Defender for Endpoint，请参阅[应用保护策略 (MAM) 中配置Microsoft Defender for Endpoint风险信号](android-configure-mam.md)。

> [!NOTE]
> **Android 上的Microsoft Defender for Endpoint现已在 [Google Play](https://play.google.com/store/apps/details?id=com.microsoft.scmx) 上提供。**
>
> 可以从Intune连接到 Google Play，跨设备管理员和 Android Enterprise 注册模式部署Microsoft Defender for Endpoint应用。

## <a name="how-to-configure-microsoft-defender-for-endpoint-on-android"></a>如何在 Android 上配置Microsoft Defender for Endpoint

在配置 Android 功能的Microsoft Defender for Endpoint中提供了有关如何在 [Android 功能上配置Microsoft Defender for Endpoint的](android-configure.md)指南。

## <a name="related-topics"></a>相关主题

- [使用 Microsoft Intune 在 Android 上部署 Microsoft Defender for Endpoint](android-intune.md)
- [在 Android 功能上配置 Microsoft Defender for Endpoint](android-configure.md)
- [移动应用程序管理 (MAM) 基础知识](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
