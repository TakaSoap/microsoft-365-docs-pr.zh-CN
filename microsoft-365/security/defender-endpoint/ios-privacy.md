---
title: 隐私信息 - 适用于 iOS 的 Microsoft Defender 终结点
ms.reviewer: ''
description: 介绍适用于 iOS 的 Microsoft Defender 终结点的隐私信息
keywords: microsoft， defender， atp， ios， 策略， 概述
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
ms.openlocfilehash: 52694322c7f084df777a8e97fe5b84cc3cb4e6d1
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055460"
---
# <a name="privacy-information---microsoft-defender-for-endpoint-for-ios"></a>隐私信息 - 适用于 iOS 的 Microsoft Defender 终结点

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2146631)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> 想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigateip-abovefoldlink)

> [!NOTE]
> 适用于 iOS 的终结点的 Defender 使用 VPN 提供 Web 保护功能。 这不是常规 VPN，它是不接受设备外流量的本地或自循环 VPN。 **Microsoft 或你的组织看不到你的浏览活动。**

适用于 iOS 的终结点的 Defender 从已配置的 iOS 设备收集信息，并存储到具有 Defender for Endpoint 的同一租户中。 该信息的收集有助于使适用于 iOS 的 Endpoint 的 Defender 保持安全、最新、如预期运行并支持服务。

有关数据存储详细信息，请参阅适用于终结点数据存储[和隐私的 Microsoft Defender。](data-storage-privacy.md)

## <a name="required-data"></a>所需数据 

必需数据包含使适用于 iOS 的 Defender 按预期工作所需的数据。 此数据对于服务操作至关重要，可以包含与最终用户、组织、设备和应用相关的数据。 

下面列出了要收集的数据类型： 

### <a name="web-page-or-network-information"></a>网页或网络信息 

- 仅在检测到恶意连接或网页时网站的域名。 

### <a name="device-and-account-information"></a>设备和帐户信息 

- 设备信息，例如&、iOS 版本、CPU 信息和设备标识符，其中设备标识符为以下项之一： 

    - Wi-Fi适配器 MAC 地址 

    - 随机生成的全局唯一标识符 (GUID)  

- 租户、设备和用户信息 

    - Azure Active Directory (AD) 设备 ID 和 Azure 用户 ID - 唯一标识设备，分别位于 Azure Active directory 中的用户。 

    - Azure 租户 ID - 标识 Azure Active Directory 中的组织的 GUID。 

    - Microsoft Defender for Endpoint 组织 ID - 与设备所属的企业关联的唯一标识符。 允许 Microsoft 确定是否有影响一组选定企业的问题以及受到影响的企业数量。 

    - 用户主体名称 - 用户的电子邮件 ID。 

### <a name="product-and-service-usage-data"></a>产品或服务使用情况数据 

仅为设备上安装的 Microsoft Defender for Endpoint 应用收集以下信息。 

- 应用包信息，包括名称、版本以及应用升级状态。 

- 在应用中完成的操作。 

- iOS 生成的崩溃报告日志。 

- 内存使用率数据。 

## <a name="optional-data"></a>可选数据 

可选数据包括来自客户端的诊断数据和反馈数据。 可选诊断数据是一种附加数据，有助于我们改进产品并提供增强的信息来帮助检测、诊断和修复问题。 此数据仅供诊断使用，服务本身不需要。 

可选诊断数据包括： 

- 适用于终结点的 Defender 的应用、CPU 和网络使用情况。 

- 管理员为 Defender for Endpoint 配置的功能。 

反馈 通过用户提供的应用内反馈收集数据。 

- 用户的电子邮件地址（如果他们选择提供它）。

- 反馈类型 (、笑脸、想法) 以及用户提交的任何反馈评论。 

有关详细信息，请参阅关于 [隐私的更多信息](https://aka.ms/mdatpiosprivacystatement)。


