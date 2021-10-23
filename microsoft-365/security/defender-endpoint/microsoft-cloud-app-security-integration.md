---
title: Microsoft Cloud App Security 集成概述
ms.reviewer: ''
description: Microsoft Defender for Endpoint 通过转发云应用安全云应用网络活动与应用集成。
keywords: 云， 应用， 网络， 可见性， 使用情况
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
ms.topic: conceptual
ms.date: 10/18/2018
ms.technology: mde
ms.openlocfilehash: 40eda96b350a5801c732842c0e9a64f29badcc27
ms.sourcegitcommit: 3140e2866de36d57a27d27f70d47e8167c9cc907
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/23/2021
ms.locfileid: "60555580"
---
# <a name="microsoft-cloud-app-security-in-defender-for-endpoint-overview"></a>Microsoft Cloud App Security Defender for Endpoint 概述

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

[!include[Prerelease information](../../includes/prerelease.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

Microsoft Cloud App Security (云应用安全) 是一个全面的解决方案，让你能够控制和限制对云应用的访问权限，同时强制执行对云中存储数据的合规性要求，从而了解云应用和服务。 有关详细信息，[请参阅云应用安全。](/cloud-app-security/what-is-cloud-app-security)

> [!NOTE]
> 此功能随 E5 许可证提供[，企业移动性 + 安全性版本](https://www.microsoft.com/cloud-platform/enterprise-mobility-security)1809 或更高版本Windows 10或 Windows 11。

## <a name="microsoft-defender-for-endpoint-and-cloud-app-security-integration"></a>Microsoft Defender for Endpoint 和 云应用安全 集成

云应用安全依赖于从企业防火墙和代理服务器转发到它的云流量日志。 Microsoft Defender for Endpoint 通过收集和转发云应用安全云应用网络活动，从而与云应用集成，从而对云应用使用情况的可见性提高。 监控功能内置于设备中，可提供网络活动的完全覆盖。

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4r4yQ]

集成对现有发现提供了以下主要云应用安全改进：

- 可在任何位置使用 - 由于网络活动直接从终结点收集，因此无论设备位于公司网络内部还是外部，设备都可用，因为它不再依赖于通过企业防火墙或代理服务器路由的流量。

- 开箱即用，无需配置 - 将云流量日志转发云应用安全防火墙和代理服务器配置。 使用 Defender for Endpoint 和 云应用安全 集成，无需任何配置。 只需在Microsoft Defender 安全中心中打开它，你一开始操作就大了。

- 设备上下文 - 云流量日志缺少设备上下文。 Defender for Endpoint 网络活动通过设备上下文报告 (哪些设备访问云应用) ，以便你能够准确了解 (设备) 网络活动的发生位置，以及由谁 (用户) 执行。

有关云发现详细信息，请参阅 [使用发现的应用](/cloud-app-security/discovered-apps)。

## <a name="related-topic"></a>相关主题

- [配置 Microsoft Cloud App Security 集成](microsoft-cloud-app-security-config.md)
