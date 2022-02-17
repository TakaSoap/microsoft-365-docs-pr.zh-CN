---
title: iOS 上的 Microsoft Defender for Endpoint
ms.reviewer: ''
description: 介绍如何在 iOS 上安装和使用 Microsoft Defender for Endpoint
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
ms.openlocfilehash: c144eb3cd0cec2d96f20294475618e7e9c49c816
ms.sourcegitcommit: 007822d16e332522546e948f5c216327254a4d49
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/17/2022
ms.locfileid: "62879152"
---
# <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 上的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

**iOS 上的 Microsoft Defender for Endpoint** 可抵御来自网站、电子邮件和应用的网络钓鱼和不安全的网络连接。 所有警报都将通过 Microsoft 365 Defender 门户中的一个窗格提供。 该门户为安全团队提供了 iOS 设备上威胁的集中视图以及其他平台。

> [!CAUTION]
> 在 iOS 上运行其他第三方终结点保护产品以及 Defender for Endpoint 可能会导致性能问题和不可预知的系统错误。

## <a name="pre-requisites"></a>先决条件

**对于最终用户**

- 分配给最终用户的 Microsoft Defender for Endpoint 许可证 (应用的) 许可证。 请参阅 [Microsoft Defender for Endpoint 许可要求](/microsoft-365/security/defender-endpoint/minimum-requirements#licensing-requirements)。

- **对于注册的设备**：
    - 设备 (通过) 应用注册，Intune 公司门户强制执行 Intune [](/mem/intune/user-help/enroll-your-device-in-intune-ios) 设备合规性策略。 这需要为最终用户分配一个Microsoft Intune许可证。
    - Intune 公司门户应用可以从 [Apple App Store 下载](https://apps.apple.com/us/app/intune-company-portal/id719171358)。
    
    >[!NOTE]
    >Apple 不允许重定向用户从应用商店下载其他应用，因此在载入 Microsoft Defender for Endpoint 应用之前，用户需要完成此步骤。) 
    
    - 设备 () 注册到 Azure Active Directory。 这要求最终用户通过 Microsoft Authenticator [登录](https://apps.apple.com/app/microsoft-authenticator/id983156458)。

- **对于注销的设备**：设备 (注册) 注册Azure Active Directory。 这要求最终用户通过 Microsoft Authenticator [登录](https://apps.apple.com/app/microsoft-authenticator/id983156458)。

- 若要详细了解如何分配许可证，请参阅 [向用户分配许可证](/azure/active-directory/users-groups-roles/licensing-groups-assign)。

**对于管理员**

- 访问 Microsoft 365 Defender 门户。

- 访问[Microsoft Endpoint Manager中心，](https://go.microsoft.com/fwlink/?linkid=2109431)以：
   - 将应用部署到组织中注册的用户组。
   - 在 MAM 应用保护策略中配置 Microsoft Defender 的终结点 (风险) 


    > [!NOTE]
    > - Microsoft Defender for Endpoint 现在为未使用移动设备管理 (MDM) 但正在使用 Intune 管理移动应用程序的受管理应用程序内的组织数据扩展保护。 它还向使用其他企业移动性管理解决方案的客户扩展了此支持，同时仍使用 Intune 在 [MAM (移动应用程序) ](/mem/intune/apps/mam-faq)。
    > - 此外，Microsoft Defender for Endpoint 已支持使用 Intune 移动设备管理或 MDM (注册) 。  

**系统要求**

- 运行 iOS 12.0 及以上的 iOS 设备。 也支持 iPad。 *请注意，从 2022 年 3 月 31 日至 2022 年 3 月，Microsoft Defender for Endpoint 支持的最低 iOS 版本将为 iOS 13.0。*

- 设备已注册到 Intune 公司门户 [应用，Azure Active Directory](https://apps.apple.com/us/app/intune-company-portal/id719171358)[通过Microsoft Authenticator](https://apps.apple.com/app/microsoft-authenticator/id983156458)注册。

## <a name="installation-instructions"></a>安装说明

可通过 MEM Microsoft Endpoint Manager (在 iOS 上部署 Microsoft Defender for Endpoint) 并且支持受监督设备以及不受监督的设备。 最终用户还可以直接从 Apple 应用商店安装 [应用](https://aka.ms/mdatpiosappstore)。

- 有关通过 iOS 或 Intune 在已注册设备上Microsoft Endpoint Manager的信息，请参阅[在 iOS 上部署 Microsoft Defender for Endpoint](ios-install.md)。
- 有关在 MAM 应用保护策略 (使用 Defender for Endpoint) 的信息，请参阅配置应用保护策略以将 [Defender for Endpoint 风险信号 (MAM) ](ios-install-unmanaged.md)

## <a name="resources"></a>资源

- 通过访问 [iOS 上的 Microsoft Defender for Endpoint](ios-whatsnew.md) 中的新增功能或我们的博客，随时了解即将发布的 [版本](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。

- 通过应用内反馈系统或统一安全控制台 [提供反馈](https://security.microsoft.com)

## <a name="next-steps"></a>后续步骤

- [通过 Intune 为已注册的设备在 iOS 上部署 Microsoft Defender for Endpoint](ios-install.md)
- [配置应用保护策略，以将 Defender for Endpoint 风险信号 (MAM) ](ios-install-unmanaged.md)
- [在 iOS 功能上配置 Microsoft Defender for Endpoint](ios-configure-features.md)
- [根据 Microsoft Defender for Endpoint 中的设备风险评分配置条件访问策略](ios-configure-features.md#conditional-access-with-defender-for-endpoint-on-ios)
- [移动应用程序管理 (MAM) 基础知识](/mem/intune/apps/app-management#mobile-application-management-mam-basics)
