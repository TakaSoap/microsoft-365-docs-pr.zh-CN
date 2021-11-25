---
title: 与 Microsoft Defender for Cloud 集成
description: 了解 Microsoft Defender for Endpoint 与 Microsoft Defender 云的集成
keywords: 集成， 服务器， azure， 2012r2， 2016， 2019， 服务器载入， 设备管理， 配置适用于终结点服务器的 Microsoft Defender， 载入适用于终结点服务器的 Microsoft Defender， 载入适用于终结点服务器的 Microsoft Defender
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
author: mjcaparas
ms.author: macapara
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 4364855120524f7b6e993a3827a03a3bd5f79d96
ms.sourcegitcommit: 2b9d40e888ff2f2b3385e2a90b50d719bba1e653
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/25/2021
ms.locfileid: "61170501"
---
# <a name="integration-with-microsoft-defender-for-cloud"></a>与 Microsoft Defender for Cloud 集成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- Microsoft Defender for Cloud

Microsoft Defender for Endpoint 可以与 Microsoft Defender for Cloud 集成，以提供全面的Windows服务器保护解决方案。 通过此集成，Microsoft Defender for Cloud 可以使用 Defender for Endpoint 功能为 Windows 服务器提供改进的威胁检测。

此集成中包含以下功能：

- 自动载入 - 在已载入到 Microsoft Defender for Cloud 的 Windows 服务器上自动启用 Defender for Endpoint 传感器。 有关云载入的 Microsoft Defender 详细信息，请参阅使用集成的 [Microsoft Defender for Endpoint 许可证](/azure/security-center/security-center-wdatp)。

    > [!NOTE]
    > 适用于服务器的 Microsoft Defender 与 Microsoft Defender for Endpoint 之间的集成已扩展为支持[Windows Server 2019 和 Windows Virtual Desktop (WVD) ](/azure/security-center/release-notes#microsoft-defender-for-endpoint-integration-with-azure-defender-now-supports-windows-server-2019-and-windows-10-virtual-desktop-wvd-in-preview)。

- Windows Microsoft Defender for Cloud 监视的服务器也将在 Defender for Endpoint 中可用 - Microsoft Defender for Cloud 无缝连接到 Defender for Endpoint 租户，跨客户端和服务器提供单一视图。  此外，适用于终结点的 Defender 警报将在 Microsoft Defender 云控制台中提供。
- 服务器调查 - Microsoft Defender 云客户可以访问Microsoft Defender 安全中心执行详细调查，以发现潜在泄露的范围。

> [!IMPORTANT]
> - 当你使用 Microsoft Defender for Cloud 监视服务器时，会自动在美国为美国用户 (，在欧盟为欧洲和英国用户创建 Defender) 。<br>
Defender for Endpoint 收集的数据存储在预配期间标识的租户地理位置中。
> - 如果在使用 Microsoft Defender for Cloud 之前使用 Defender for Endpoint，则数据将存储在创建租户时指定的位置，即使以后与 Microsoft Defender for Cloud 集成。
> - 配置后，你无法更改数据存储的位置。 如果需要将数据移动到其他位置，需要联系 Microsoft 支持部门来重置租户。 <br>
已针对客户禁用利用此集成的服务器终结点Office 365 GCC监视。



## <a name="related-topics"></a>相关主题
- [载入以前版本的 Windows](onboard-downlevel.md)
- [载入Windows Server 2012 R2、2016、SAC 版本 1803 和 2019](configure-server-endpoints.md)
