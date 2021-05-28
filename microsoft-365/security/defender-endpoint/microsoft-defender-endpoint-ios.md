---
title: iOS 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 iOS 上安装和使用 Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 概述， 安装， 部署， 卸载， intune
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
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 4a051742775c3d4e8b36bf0ba7a4fd2502763014
ms.sourcegitcommit: 5377b00703b6f559092afe44fb61462e97968a60
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/27/2021
ms.locfileid: "52694457"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 上的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**iOS 上的 Microsoft Defender for Endpoint** 将提供针对网站、电子邮件和应用中的网络钓鱼和不安全网络连接的防护。 所有警报都将通过警报窗格中的单个Microsoft Defender 安全中心。 该门户为安全团队提供了 iOS 设备上威胁的集中视图以及其他平台。

> [!CAUTION]
> 在 iOS 上运行其他第三方终结点保护产品以及 Defender for Endpoint 可能会导致性能问题和不可预知的系统错误。

## <a name="pre-requisites"></a>先决条件

**对于最终用户**

- 分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。 请参阅 [Microsoft Defender for Endpoint 许可要求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。

- 设备 (应用) 注册，[以Intune 公司门户](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios)Intune 设备合规性策略。 这要求为最终用户分配一个Microsoft Intune许可证。
    - Intune 公司门户应用可以从[Apple App Store 下载](https://apps.apple.com/us/app/intune-company-portal/id719171358)。
    - 请注意，Apple 不允许重定向用户从应用商店下载其他应用，因此在载入 Microsoft Defender for Endpoint 应用之前，需要由用户完成此步骤。

- 若要详细了解如何分配许可证，请参阅 [向用户分配许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。

**对于管理员**

- 访问 Microsoft Defender 安全中心 门户。

    > [!NOTE]
    > Microsoft Intune在 iOS 上部署 Microsoft Defender for Endpoint (MDM) 唯一受支持的移动设备管理解决方案。 目前，仅支持在 Intune 中对与 iOS 相关的设备合规性策略强制实施 Defender for Endpoint 的设备。

- 访问[Microsoft Endpoint Manager](https://go.microsoft.com/fwlink/?linkid=2109431)管理中心 ，以将应用部署到组织中注册的用户组。

**系统要求**

- 运行 iOS 11.0 及以上设备的 iOS 设备。 iPad版本 1.1.15010101 之后正式支持的设备。

- 设备已注册Intune 公司门户[应用](https://apps.apple.com/us/app/intune-company-portal/id719171358)。

> [!NOTE]
> **适用于 iOS 上的终结点的 Microsoft Defender 在 [Apple App Store 上可用](https://aka.ms/mdatpiosappstore)。**

## <a name="installation-instructions"></a>安装说明

在 iOS 上部署 Microsoft Defender for Endpoint Microsoft Intune (MDM) 且受监督的设备和不受监督的设备都受支持。
有关详细信息，请参阅在[iOS 上部署 Microsoft Defender for Endpoint。](ios-install.md)

## <a name="resources"></a>资源

- 通过访问 [iOS](ios-whatsnew.md) 版 Microsoft Defender for Endpoint 中的新增功能或博客，随时了解即将发布的 [版本](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。

- 通过应用内反馈系统或 [SecOps 门户提供反馈](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>后续步骤

- [在 iOS 上部署 Microsoft Defender for Endpoint](ios-install.md)
- [在 iOS 功能上配置 Microsoft Defender for Endpoint](ios-configure-features.md)
