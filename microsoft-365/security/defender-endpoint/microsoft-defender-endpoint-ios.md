---
title: iOS 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 iOS 上安装和使用Microsoft Defender for Endpoint
keywords: microsoft， defender， Microsoft Defender for Endpoint， ios， 概述， 安装， 部署， 卸载， intune
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365-initiative-defender-endpoint
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: dcc67b2d2a9ad03dc1235eebd577e3525ab07a03
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665923"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 上的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

**iOS 上的Microsoft Defender for Endpoint** 可防止来自网站、电子邮件和应用的网络钓鱼和不安全的网络连接。 所有警报都将通过Microsoft 365 Defender门户中的单个玻璃窗格提供。 门户为安全团队提供了 iOS 设备和其他平台上威胁的集中视图。

> [!CAUTION]
> 在 iOS 上将其他第三方终结点保护产品与 Defender for Endpoint 一起运行可能会导致性能问题和不可预测的系统错误。

## <a name="pre-requisites"></a>先决条件

**对于最终用户**

- 分配给应用的最终用户 () 的Microsoft Defender for Endpoint许可证。 请参阅[Microsoft Defender for Endpoint许可要求](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。

- **对于已注册的设备**：
    - 设备 () 通过Intune 公司门户应用[注册](/mem/intune/user-help/enroll-your-device-in-intune-ios)，以强制实施Intune设备符合性策略。 这要求为最终用户分配Microsoft Intune许可证。
    - Intune 公司门户应用可以从 [Apple App Store](https://apps.apple.com/us/app/intune-company-portal/id719171358) 下载。
    
    >[!NOTE]
    >Apple 不允许重定向用户从应用商店下载其他应用，因此，用户需要先执行此步骤，然后才能加入到 Microsoft Defender for Endpoint app.) 
    
    - 设备 () 已注册到Azure Active Directory。 这要求最终用户通过[Microsoft Authenticator应用](https://apps.apple.com/app/microsoft-authenticator/id983156458)登录。

- **对于未注册的设备**：设备 () 已注册到Azure Active Directory。 这要求最终用户通过[Microsoft Authenticator应用](https://apps.apple.com/app/microsoft-authenticator/id983156458)登录。

- 有关如何分配许可证的详细信息，请参阅 [向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

**对于管理员**

- 访问Microsoft 365 Defender门户。

- 访问[Microsoft Endpoint Manager管理中心](https://go.microsoft.com/fwlink/?linkid=2109431)，以执行以下操作：
   - 将应用部署到组织中已注册的用户组。
   - 在应用保护策略中配置Microsoft Defender for Endpoint风险信号 (MAM) 


    > [!NOTE]
    > - Microsoft Defender for Endpoint现在为未使用移动设备管理 (MDM) 但使用Intune管理移动应用程序的用户，将保护扩展到托管应用程序中的组织数据。 它还向使用其他企业移动性管理解决方案的客户提供此支持，同时仍使用Intune进行[移动应用程序管理 (MAM) ](/mem/intune/apps/mam-faq)。
    > - 此外，Microsoft Defender for Endpoint已支持使用 Intune 移动设备管理 (MDM) 注册的设备。  

**系统要求**

- 运行 iOS 12.0 及更高版本的 iOS 设备。 还支持 iPad。 *请注意，从 2022 年 3 月 31 日开始，Microsoft Defender for Endpoint支持的最小 iOS 版本将是 iOS 13.0。*

- 设备已注册[到Intune 公司门户应用](https://apps.apple.com/us/app/intune-company-portal/id719171358)，或者通过使用同一帐户[Microsoft Authenticator向Azure Active Directory](https://apps.apple.com/app/microsoft-authenticator/id983156458)注册。

## <a name="installation-instructions"></a>安装说明

可通过 Microsoft Endpoint Manager (MEM) 在 iOS 上部署Microsoft Defender for Endpoint，同时支持监督设备和非监督设备。 最终用户还可以直接从 [Apple 应用商店安装应用](https://aka.ms/mdatpiosappstore)。

- 有关通过Microsoft Endpoint Manager或Intune在已注册设备上部署的信息，请参阅[在 iOS 上部署Microsoft Defender for Endpoint](ios-install.md)。
- 有关在应用保护策略 (MAM) 中使用 Defender for Endpoint 的信息，请参阅 [配置应用保护策略以包括 DEFENDER for Endpoint 风险信号 (MAM) ](ios-install-unmanaged.md)

## <a name="resources"></a>资源

- 通过访问 iOS [或博客](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)[上的Microsoft Defender for Endpoint](ios-whatsnew.md)新增功能，随时了解即将发布的版本。

- 通过应用内反馈系统或[统一安全控制台](https://security.microsoft.com)提供反馈

## <a name="next-steps"></a>后续步骤

- [通过已注册设备的Intune在 iOS 上部署Microsoft Defender for Endpoint](ios-install.md)
- [将应用保护策略配置为包含 Defender for Endpoint 风险信号 (MAM) ](ios-install-unmanaged.md)
- [在 iOS 功能上配置Microsoft Defender for Endpoint](ios-configure-features.md)
- [根据Microsoft Defender for Endpoint中的设备风险评分配置条件访问策略](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)
- [移动应用程序管理 (MAM) 基础知识](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
