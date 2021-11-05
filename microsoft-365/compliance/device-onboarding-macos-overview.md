---
title: 将 macOS 设备载入 Microsoft 365 概述（预览版）
f1.keywords: NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MET150
description: 了解如何将 macOS 设备载入合规性解决方案
ms.openlocfilehash: b24fd172224e0d1f8080ddd22cb3532dce0afe2b
ms.sourcegitcommit: 27bf284b3bfe334eb98847798734625bd2ffafb1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/05/2021
ms.locfileid: "60792288"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview-preview"></a>将 macOS 设备载入 Microsoft 365 概述（预览版）

可以使用 Intune 或 JAMF Microsoft 365 MacOS 设备载入到 Pro。 载入过程因使用的管理解决方案不同而不同。 如果你的 macOS 设备已载入 Microsoft Defender for Endpoint (MDE) ，则步骤较少。 有关 [相应](#next-steps) 过程的链接，请参阅下一步步骤。

## <a name="get-registered"></a>注册

若要获取此功能的访问权限，必须向 Microsoft 注册租户。 请参阅 注册[macOS Microsoft 365。](https://aka.ms/EndpointDLPIgnite21-Previews)

**适用于：**

- [Microsoft 365DLP (终结点数据丢失) ](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
<!--- [Insider risk management](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)-->

## <a name="before-you-begin"></a>准备工作

在加泰罗尼亚语 10.15 或更高版本 (macOS 设备上开始使用 Endpoint DLP) ，您应熟悉以下文章：

- [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
- [终结点数据丢失防护入门](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)

如果您完全不熟悉 DLP，您也应熟悉以下文章：

- [了解数据丢失防护](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [规划 DLP (数据丢失) ](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [数据丢失防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference)

macOS 设备必须已经通过 Intune 或 JAMF Pro。
 
- 若要载入 Intune，请参阅[部署指南：](/mem/intune/fundamentals/deployment-guide-platform-macos)在 Microsoft Intune 中管理 macOS 设备以及使用 Intune 公司门户 注册[你的 Mac。](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) 
- 若要载入 JAMF Pro请参阅[JAMF Pro 管理员](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)指南和 JAMF Pro [Mac 安装和配置指南](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
- 在 macOS 设备上安装 v95+ Edge 浏览器 

## <a name="licensing-guidance"></a>许可指南

请参阅[Microsoft 365信息保护的许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection)

## <a name="activities-that-can-be-restricted-on-macos"></a>macOS 上可以限制的活动 

将 macOS 设备载入到 Microsoft 365 合规性解决方案后，可以使用 DLP (策略监视和限制) 操作。

**复制到 USB 可移动** 媒体 – 强制执行后，此操作会阻止、警告或审核将受保护的文件从终结点设备复制或移动到 USB 可移动媒体 

**复制到网络共享** – 强制执行后，此操作将阻止、警告或审核受保护文件从终结点设备复制或移动到任何网络共享 

**打印** – 当强制时，当从终结点设备打印受保护的文件时，此操作将阻止、警告或审核 

**复制到剪贴** 板 – 强制执行后，此操作会阻止、警告或审核正在复制到终结点设备上剪贴板的受保护文件的数据 

**Upload** 云 – 当受保护文件被阻止或允许根据全局设置中的允许/不允许的域列表上载到云服务时，此操作将阻止、警告或审核。 当此操作设置为警告或阻止时， ("全局设置"下的"不允许) 定义的其他浏览器将阻止访问该文件。 

由不允许 **的应用** 访问 – 如果强制执行，此操作将阻止位于未允许的应用列表 (（全局设置) 中定义的）上的应用程序访问终结点设备上受保护的文件。 方案示例 

## <a name="next-steps"></a>后续步骤

要求设备载入Microsoft 365合规性解决方案，以便接收 DLP 传感器遥测并实施数据丢失防护策略。 

- 对于通过 Intune 管理的 macOS 设备，请参阅使用 Intune (预览版将 macOS 设备载入和Microsoft 365 [macOS) ](device-onboarding-offboarding-macos-intune.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview)

- 对于通过 Intune 管理并且已部署 Microsoft Defender for Endpoint (MDE) 的 macOS 设备，请参阅使用适用于 Endpoint 客户的 Intune 将 macOS 设备载入和载出到合规性解决方案中 ([预览版](device-onboarding-offboarding-macos-intune-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview)) 

- 对于通过 JAMF Pro管理的 macOS 设备，请参阅使用[JAMF](device-onboarding-offboarding-macos-jamfpro.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview) Pro (预览版将 macOS 设备载入和载出 Microsoft 365 合规性解决方案) 

- 对于通过 JAMF Pro 进行管理并且部署了 Microsoft Defender for Endpoint (MDE) 的 macOS 设备，请参阅使用适用于 Endpoint 客户的[JAMF Pro](device-onboarding-offboarding-macos-jamfpro-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview)将 macOS 设备载入和载出到合规性解决方案中 (预览版) 


## <a name="related-topics"></a>相关主题

- [使用终结点数据丢失防护](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Microsoft 应用中 DLP 策略提示的支持矩阵](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
