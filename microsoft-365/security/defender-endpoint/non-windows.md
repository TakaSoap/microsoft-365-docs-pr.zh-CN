---
title: 适用于非 Windows 平台的 Microsoft Defender for Endpoint
description: 了解适用于非终结点平台的 Microsoft Defender Windows功能
keywords: 非 Windows， mac， macos， linux， android
search.product: eADQiWindows 10XVcnh
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
- M365-security-compliance
- m365solution-evalutatemtp
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 9348e0de384850a24a9173c46ab331466f26f912
ms.sourcegitcommit: eb8c600d3298dca1940259998de61621e6505e69
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/24/2021
ms.locfileid: "61163466"
---
# <a name="microsoft-defender-for-endpoint-for-non-windows-platforms"></a>适用于非 Windows 平台的 Microsoft Defender for Endpoint

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

Microsoft 一直在向 macOS、Linux、Android 和 iOS 扩展除 Windows 和 Windows Server 以外的行业领先的终结点安全功能。

组织面临各种平台和设备的威胁。 Our teams have committed to building security solutions not just *for* Microsoft， and also *from* Microsoft to enable our customers to protect and secure their heterogenous environments. 我们期待聆听客户反馈，并与客户密切合作，以构建满足其需求的解决方案。

借助 Microsoft Defender for Endpoint，客户可以跨 Windows 和非 Windows 平台从 Microsoft Defender 安全中心 中所有威胁和警报的统一视图中获益，从而全面了解环境中发生的情况，从而帮助他们更快速地评估和响应威胁。

## <a name="microsoft-defender-for-endpoint-on-macos"></a>macOS 上的 Microsoft Defender for Endpoint

macOS 上的 Microsoft Defender for Endpoint 为三个最新发布的 macOS (EDR) 和 漏洞管理 防病毒、终结点检测和响应功能。 客户可以通过 Microsoft Endpoint Manager 和 Jamf 部署和管理解决方案。 与 macOS Microsoft Office一样，Microsoft 自动更新用于管理 Mac 上的 Microsoft Defender for Endpoint 更新。 有关关键功能和优势的信息，请阅读 [我们的公告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/macOS)。

若要详细了解如何开始使用，请访问 macOS 上的 Defender for Endpoint [文档](microsoft-defender-endpoint-mac.md)。

> [!NOTE]
> macOS 终结点当前不支持以下功能：
>
> - 数据丢失防护
> - 实时响应

## <a name="microsoft-defender-for-endpoint-on-linux"></a>Linux 版 Microsoft Defender for Endpoint

Linux 上的 Microsoft Defender for Endpoint 为 Linux (AV) 、终结点检测和响应 (EDR) ，漏洞管理 Linux 服务器提供预防性功能。 这包括配置和管理代理、启动扫描和管理威胁的完整命令行体验。 我们支持六个最常见的 Linux Server 分发的最新版本：RHEL 7.2+、CentOS Linux 7.2+、Ubuntu 16 LTS 或更高版本 LTS、SLES 12+、Debian 9+和 Oracle Linux 7.2。 可以使用部署和配置 Linux 上的 Microsoft Defender for Endpoint、Ansible 或现有的 Linux 配置管理工具进行部署和配置。 有关关键功能和优势的信息，请阅读 [我们的公告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Linux)。

若要详细了解如何开始使用，请访问 Linux 上的 Microsoft Defender for Endpoint [文档](microsoft-defender-endpoint-linux.md)。

> [!NOTE]
> Linux 终结点当前不支持以下功能：
>
> - 数据丢失防护
> - 实时响应

> [!NOTE]
> Linux 终结点当前不支持以下功能：
>
> - 数据丢失防护
> - 实时响应
> - SIEM

## <a name="microsoft-defender-for-endpoint-on-android"></a>Android 上的 Microsoft Defender for Endpoint

Android 版 Microsoft Defender for Endpoint 是适用于运行 Android 6.0 及更高版本的设备的移动威胁防护解决方案。 Android Enterprise (工作配置文件) 和设备管理员模式均受支持。 在 Android 上，我们提供 Web 保护，包括防钓鱼、阻止不安全连接以及设置自定义指示器。 该解决方案扫描 PUA (恶意软件和可能不需要的应用程序) 通过与 MICROSOFT ENDPOINT MANAGER 和条件访问集成，提供其他泄露防护功能。 有关关键功能和优势的信息，请阅读 [我们的公告](https://techcommunity.microsoft.com/t5/microsoft-defender-atp/bg-p/MicrosoftDefenderATPBlog/label-name/Android)。

若要详细了解如何开始使用，请访问 Android 版 Microsoft Defender for Endpoint [文档](microsoft-defender-endpoint-android.md)。

## <a name="microsoft-defender-for-endpoint-on-ios"></a>iOS 上的 Microsoft Defender for Endpoint

iOS 上的 Microsoft Defender for Endpoint 是适用于运行 iOS 11.0 及更高版本的设备的移动威胁防护解决方案。 支持在客户的租户中注册的设备 (注册或注销) 注册。 受监督的注册设备和未监管注册设备均受支持。 在 iOS 上，我们提供 Web 保护，包括防钓鱼、阻止不安全连接和设置自定义指示器以及越狱检测。 有关主要功能和优点详细信息，请阅读 [我们的公告](https://techcommunity.microsoft.com/t5/microsoft-defender-for-endpoint/bg-p/MicrosoftDefenderATPBlog/label-name/iOS)。

若要详细了解如何开始使用，请访问 iOS 上的 Microsoft Defender for Endpoint [文档](microsoft-defender-endpoint-ios.md)。

## <a name="licensing-requirements"></a>许可要求

符合条件的许可用户可以在最多五台并发设备上使用 Microsoft Defender for Endpoint。 Microsoft Defender for Endpoint 还可从云解决方案提供商云解决方案提供商 (购买) 。

客户可以通过独立 Microsoft Defender for Endpoint 许可证（作为 Microsoft 365 A5/E5 的一部分）或 Microsoft 365 MacOS 上的 Microsoft Defender for Endpoint。

上述产品/服务中包含了 Android 和 iOS 上最近宣布的适用于终结点的 Microsoft Defender 功能，这些功能是适用于合格许可用户的五个合格设备的一部分。

Linux 上的 Defender for Endpoint 通过 Defender for Endpoint Server SKU 提供，适用于商业和教育客户。

有关定价和其他资格要求，请联系你的帐户团队或云解决方案提供商。
