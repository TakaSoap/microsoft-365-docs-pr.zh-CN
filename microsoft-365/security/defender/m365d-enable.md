---
title: 打开Microsoft 365 Defender安全Microsoft 365中的安全中心
description: 了解如何启用安全Microsoft 365 Defender开始集成安全事件和响应。
keywords: 入门， 启用 Microsoft 365 Defender， Microsoft 365 Defender， M365， 安全性， 数据位置， 所需权限， 许可证资格， 设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 6b17bbdb11f66a9a7b01fb6cebecdce23348770870d4f43160cf5c77a3d5e83a
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53888628"
---
# <a name="turn-on-microsoft-365-defender"></a>打开 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md)集成 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Cloud App Security 和 Microsoft Defender for Identity 的关键功能，统一事件响应流程。 这种统一的体验增加了可在 Microsoft 365 安全中心访问的强大功能。

Microsoft 365 Defender具有所需权限的合格客户访问安全中心时，Microsoft 365启用。 阅读本文，了解各种先决条件以及如何Microsoft 365 Defender配置。

## <a name="check-license-eligibility-and-required-permissions"></a>检查许可证资格和所需权限

安全产品的许可证Microsoft 365你有权在安全Microsoft 365 Defender Microsoft 365使用许可证，而无需支付额外的许可费用。 我们建议获取一个Microsoft 365 E5、E5 安全、A5 或 A5 安全许可证，或提供访问所有受支持的服务的有效许可证组合。

有关许可的详细信息， [请阅读许可要求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>检查角色

您必须是 **全局管理员** 或安全管理员Azure Active Directory才能启用Microsoft 365 Defender。 [在 Azure AD 中查看角色](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>支持的服务

Microsoft 365 Defender聚合已部署的各种受支持服务的数据。 它将集中处理和存储数据，以确定新的见解，并尽可能使用集中式响应工作流。 它这样做不会影响与集成服务关联的现有部署、设置或数据。

为了获得最佳保护并优化Microsoft 365 Defender，我们建议在你的网络上部署所有适用的受支持服务。 有关详细信息，请阅读 [有关部署受支持的服务的信息](deploy-supported-services.md)。

## <a name="onboard-to-the-service"></a>载入到服务
载入Microsoft 365 Defender非常简单。 从导航菜单中，选择任何项目，如事件&**警报、搜寻**、操作中心或威胁分析，以启动载入过程。  

### <a name="data-center-location"></a>数据中心位置

Microsoft 365 Defender将在 Microsoft Defender for Endpoint 使用的相同位置[存储和处理数据](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。 如果你没有 Microsoft Defender for Endpoint，则根据活动安全服务的位置自动选择Microsoft 365位置。 所选数据中心位置将显示在屏幕中。

在 **安全中心选择**"需要帮助Microsoft 365联系 Microsoft 支持人员，Microsoft 365 Defender不同的数据中心位置预配服务。

> [!NOTE]
> 过去，Microsoft Defender for Endpoint 在通过 Azure Defender (欧盟) 数据中心自动预配。 Microsoft 365 Defender将在同一欧盟数据中心为过去以此方式预配 Defender for Endpoint 的客户自动预配。

### <a name="confirm-that-the-service-is-on"></a>确认服务已开启

设置服务后，它将添加：

- [事件管理](incidents-overview.md)
- [警报队列](investigate-alerts.md)
- 用于管理[自动调查和响应](m365d-autoir.md)的操作中心
- [高级搜寻](advanced-hunting-overview.md) 功能
- 威胁分析

![安全Microsoft 365导航窗格的图像，Microsoft 365 Defender事件Microsoft 365和其他安全中心功能的安全 ](../../media/overview-incident.png)
 *Microsoft 365 Defender窗格*

### <a name="getting-microsoft-defender-for-identity-data"></a>获取 Microsoft Defender for Identity 数据 
若要启用与Microsoft Cloud App Security集成，至少需要登录Microsoft Cloud App Security登录一次。

## <a name="get-assistance"></a>获取帮助

若要获取有关打开"打开"的最常见问题的解答，Microsoft 365 Defender[常见问题解答](m365d-enable-faq.md)。

Microsoft 支持人员可帮助在租户上设置或取消设置服务和相关资源。 为获得 **帮助，请选择** 安全中心Microsoft 365需要帮助？"。 联系支持人员时，请提及Microsoft 365 Defender。

## <a name="related-topics"></a>相关主题

- [常见问题](m365d-enable-faq.md)
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [Microsoft 365 Defender概述](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint 概述](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365 概述](../office-365-security/defender-for-office-365.md)
- [Microsoft Cloud App Security 概述](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity 概述](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender for Endpoint 数据存储](../defender-endpoint/data-storage-privacy.md)
