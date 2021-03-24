---
title: 适用于 iOS 的 Microsoft Defender ATP 概述
ms.reviewer: ''
description: 介绍如何安装和使用适用于 iOS 的 Microsoft Defender ATP
keywords: microsoft， defender， atp， ios， 概述， 安装， 部署， 卸载， intune
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
ms.openlocfilehash: 6e5aae9dcb361caf9133c1270a16711fc43033bb
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055964"
---
# <a name="microsoft-defender-for-endpoint-for-ios"></a>适用于 iOS 的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验 Microsoft Defender for Endpoint？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

**Microsoft Defender for Endpoint for iOS** 将提供针对网站、电子邮件和应用中的网络钓鱼和不安全网络连接的防护。 所有警报都将通过 Microsoft Defender 安全中心中的单个窗口窗格提供。 该门户为安全团队提供了 iOS 设备上威胁的集中视图以及其他平台。

> [!CAUTION]
> 将其他第三方终结点保护产品与 Defender for Endpoint for iOS 一起运行可能会导致性能问题和不可预知的系统错误。

## <a name="pre-requisites"></a>先决条件

**对于最终用户**

- 分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。 请参阅 [Microsoft Defender for Endpoint 许可要求](https://docs.microsoft.com/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。

- 设备 (设备) Intune 公司门户[](https://docs.microsoft.com/mem/intune/user-help/enroll-your-device-in-intune-ios)应用注册，以强制执行 Intune 设备合规性策略。 这需要为最终用户分配 Microsoft Intune 许可证。
    - 可以从 Apple App Store 下载 Intune 公司 [门户应用](https://apps.apple.com/us/app/intune-company-portal/id719171358)。
    - 请注意，Apple 不允许重定向用户从应用商店下载其他应用，因此在载入 Microsoft Defender for Endpoint 应用之前，需要由用户完成此步骤。

- 若要详细了解如何分配许可证，请参阅 [向用户分配许可证](https://docs.microsoft.com/azure/active-directory/users-groups-roles/licensing-groups-assign)。

**对于管理员**

- 访问 Microsoft Defender 安全中心门户。

    > [!NOTE]
    > Microsoft Intune 是部署适用于 iOS 的 Microsoft Defender (MDM) 唯一受支持的移动设备管理解决方案。 目前，仅支持在 Intune 中强制执行适用于 iOS 相关设备合规性策略的 Defender for Endpoint 的设备。

- 访问 [Microsoft Endpoint Manager 管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，以将应用部署到组织中注册的用户组。

**系统要求**

- 运行 iOS 11.0 及以上设备的 iOS 设备。 从版本 1.1.15010101 开始，正式支持 iPad 设备。

- 设备已注册 [Intune 公司门户应用](https://apps.apple.com/us/app/intune-company-portal/id719171358)。

> [!NOTE]
> **Microsoft Defender ATP (适用于适用于 iOS) 的 Microsoft Defender ATP 现已在 [Apple App Store 上提供](https://aka.ms/mdatpiosappstore)。**

## <a name="installation-instructions"></a>安装说明

适用于 iOS 的 Microsoft Defender for Endpoint 部署通过 Microsoft Intune (MDM) 且受监督的设备和不受监督的设备均受支持。
有关详细信息，请参阅 [部署适用于 iOS](ios-install.md)的 Microsoft Defender 终结点。

## <a name="resources"></a>资源

- 访问我们的博客 ，随时了解即将发布的 [版本](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。

- 通过应用内反馈系统或 [SecOps 门户提供反馈](https://securitycenter.microsoft.com)

## <a name="next-steps"></a>后续步骤

- [部署适用于 iOS 的 Microsoft Defender for Endpoint](ios-install.md)
- [配置适用于 iOS 功能的 Microsoft Defender for Endpoint](ios-configure-features.md)
