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
ms.openlocfilehash: f7ff900fdbeca59a63c0acd2c2f542c6e96f367b
ms.sourcegitcommit: 8eca41cd21280ffcb1f50cafce7a934e5544f302
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/12/2021
ms.locfileid: "60950685"
---
# <a name="onboard-macos-devices-into-microsoft-365-overview-preview"></a>将 macOS 设备载入 Microsoft 365 概述（预览版）

可以使用 Intune 或 JAMF Microsoft 365 MacOS 设备载入到 Pro。 载入过程因使用的管理解决方案不同而不同。 如果你的 macOS 设备已载入 Microsoft Defender for Endpoint (MDE) ，则步骤较少。 有关 [相应](#next-steps) 过程的链接，请参阅下一步步骤。

## <a name="get-registered"></a>注册

若要获取此功能的访问权限，必须向 Microsoft 注册租户。 请参阅 注册[macOS Microsoft 365 macOS 支持](https://aka.ms/EndpointDLPIgnite21-Previews)。

**适用于：**

- [Microsoft 365 DLP (终结点数据丢失) ](./endpoint-dlp-learn-about.md)
- [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)

## <a name="before-you-begin"></a>开始之前

在加泰罗尼亚语 10.15 或更高版本 (macOS 设备上开始使用 Endpoint DLP) ，您应熟悉以下文章：

- [了解 Microsoft 365 终结点数据丢失防护](endpoint-dlp-learn-about.md#learn-about-microsoft-365-endpoint-data-loss-prevention)
- [终结点数据丢失防护入门](endpoint-dlp-getting-started.md#get-started-with-endpoint-data-loss-prevention)

如果您完全不熟悉 DLP，您也应熟悉以下文章：

- [了解数据丢失防护](dlp-learn-about-dlp.md#learn-about-data-loss-prevention)
- [规划 DLP (数据丢失) ](dlp-overview-plan-for-dlp.md#plan-for-data-loss-prevention-dlp)
- [数据丢失防护策略参考](dlp-policy-reference.md#data-loss-prevention-policy-reference)

如果您不熟悉内部风险，您应该熟悉以下文章：

 - [内部风险管理](insider-risk-management.md#learn-about-insider-risk-management-in-microsoft-365)
 - [内部风险管理计划](insider-risk-management-plan.md#plan-for-insider-risk-management)

macOS 设备必须已经通过 Intune 或 JAMF Pro。
 
- 若要载入 Intune，请参阅[部署指南：](/mem/intune/fundamentals/deployment-guide-platform-macos)在 Microsoft Intune 中管理 macOS 设备以及使用 Intune 公司门户 注册[你的 Mac。](/mem/intune/user-help/enroll-your-device-in-intune-macos-cp) 
- 若要载入 JAMF Pro请参阅[JAMF Pro 管理员](https://www.jamf.com/resources/product-documentation/jamf-pro-administrators-guide/)指南和[JAMF Pro Mac 安装和配置指南](https://www.jamf.com/resources/product-documentation/jamf-pro-installation-guide-for-mac/)
- 在 macOS 设备上安装 v95+ Edge 浏览器 

## <a name="licensing-guidance"></a>许可指南

请参阅Microsoft 365[信息保护的许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-data-loss-prevention-for-exchange-online-sharepoint-online-and-onedrive-for-business)。

## <a name="activities-that-can-be-restricted-on-macos"></a>macOS 上可以限制的活动 

将 macOS 设备载入到 Microsoft 365 合规性解决方案后，您可以使用 DLP (策略的数据丢失防护来监视) 操作。

**复制到 USB 可移动** 媒体 – 强制执行后，此操作会阻止、警告或审核将受保护的文件从终结点设备复制或移动到 USB 可移动媒体 

**复制到网络共享** - 强制执行后，此操作将阻止、警告或审核受保护文件从终结点设备复制或移动到任何网络共享 

**打印** – 当强制时，当从终结点设备打印受保护的文件时，此操作将阻止、警告或审核 

**复制到剪贴** 板 – 强制执行后，此操作会阻止、警告或审核正在复制到终结点设备上剪贴板的受保护文件的数据 

**Upload** 云 – 当受保护文件被阻止或允许根据全局设置中的允许/不允许的域列表上载到云服务时，此操作将阻止、警告或审核。 当此操作设置为警告或阻止时， ("全局设置"下的"不允许的浏览器"列表上定义) 将阻止其访问该文件。 

由不允许 **的应用** 访问 – 如果强制执行，此操作将阻止位于未允许的应用列表 (（全局设置) 中定义的）上的应用程序访问终结点设备上受保护的文件。 方案示例 

## <a name="onboarding-devices-into-device-management"></a>将设备载入设备管理

必须先启用设备监视功能并载入终结点，然后才能监视和保护设备上的敏感项目。 这两项操作都在 Microsoft 365 合规门户中完成。

当你想载入尚未载入的设备时，你需要下载适当的脚本并将其部署到那些设备上。 <!--Follow the [Onboarding devices procedure](endpoint-dlp-getting-started.md#onboarding-devices).-->

<!--If you already have devices onboarded into [Microsoft Defender for Endpoint](/windows/security/threat-protection/), they will already appear in the managed devices list.-->

1. 打开 [Microsoft 合规中心](https://compliance.microsoft.com)**"设置"** 页面，然后选择"**启用设备监视"。**

   > [!NOTE]
   > 设备载入通常需要大约 60 秒才能启用，请先等待 30 分钟，然后再与 Microsoft 支持人员接洽。

2. 打开合规中心设置页面，然后选择“**载入设备**”。

   > [!div class="mx-imgBorder"]
   > ![启用设备管理。](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

## <a name="next-steps"></a>后续步骤

要求设备载入Microsoft 365合规性解决方案，以便接收 DLP 传感器遥测并实施数据丢失防护策略。 

主题 | 说明
:---|:---
|[使用 Intune Microsoft 365预览版将 macOS 设备载入和 (合规性) ](device-onboarding-offboarding-macos-intune.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-intune-preview)|对于通过 Intune 管理的 macOS 设备
|[使用适用于 Microsoft Defender for Endpoint 客户的 Intune 将 macOS 设备载入和卸载到合规性解决方案（预览版）](device-onboarding-offboarding-macos-intune-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-intune-for-microsoft-defender-for-endpoint-customers-preview) |对于通过 Intune 管理并且将 Microsoft Defender for Endpoint (MDE) macOS 设备
|[使用 JAMF Microsoft 365预览版将 macOS 设备载入Pro (macOS) ](device-onboarding-offboarding-macos-jamfpro.md#onboard-and-offboard-macos-devices-into-microsoft-365-compliance-solutions-using-jamf-pro-preview) | 对于通过 JAMF 托管的 macOS Pro
|[使用适用于 Microsoft Defender for Endpoint 客户的 JAMF Pro 将 macOS 设备载入和卸载到合规性解决方案（预览版）](device-onboarding-offboarding-macos-jamfpro-mde.md#onboard-and-offboard-macos-devices-into-compliance-solutions-using-jamf-pro-for-microsoft-defender-for-endpoint-customers-preview)|对于通过 JAMF Pro且已部署 Microsoft Defender for Endpoint (MDE) macOS 设备


## <a name="related-topics"></a>相关主题

- [使用终结点数据丢失防护](endpoint-dlp-using.md#using-endpoint-data-loss-prevention)
- [Microsoft 应用中 DLP 策略提示的支持矩阵](dlp-policy-tips-reference.md#support-matrix-for-dlp-policy-tips-across-microsoft-apps)
