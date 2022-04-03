---
title: 打开 Microsoft 365 Defender
description: 了解如何启用安全Microsoft 365 Defender开始集成安全事件和响应。
keywords: 入门， 启用 Microsoft 365 Defender， Microsoft 365 Defender， M365， 安全性， 数据位置， 所需权限， 许可证资格， 设置页面
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 2a99dbaf50b582df4203fc9c8e1d04e0a3f6d807
ms.sourcegitcommit: 3b8e009ea1ce928505b8fc3b8926021fb91155f3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/28/2022
ms.locfileid: "64498625"
---
# <a name="turn-on-microsoft-365-defender"></a>打开 Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

[Microsoft 365 Defender](microsoft-365-defender.md)集成 Microsoft Defender for Endpoint、Microsoft Defender for Office 365、Microsoft Defender for Cloud Apps 和 Microsoft Defender for Identity 的关键功能，统一事件响应流程。 这种统一体验添加了可在企业门户中访问Microsoft 365 Defender功能。

Microsoft 365 Defender具有所需权限的合格客户访问门户时，Microsoft 365 Defender启用。 阅读本文，了解各种先决条件以及如何Microsoft 365 Defender配置。

## <a name="check-license-eligibility-and-required-permissions"></a>检查许可证资格和所需权限

安全产品Microsoft 365通常授权你使用Microsoft 365 Defender许可费用。 我们建议获取一个Microsoft 365 E5、E5 安全、A5 或 A5 安全许可证，或提供访问所有受支持的服务的有效许可证组合。

有关详细许可信息，[读取许可要求](prerequisites.md#licensing-requirements)。

### <a name="check-your-role"></a>检查角色

你必须是以下角色之一，以启用Microsoft 365 Defender：

- 全局管理员
- 安全管理员
- 安全操作员
- 全局读取者
- 安全读取者
- 合规管理员
- 合规数据管理员
-  应用程序管理员
- 云 应用程序管理员

[在角色视图中Azure AD](/azure/active-directory/users-groups-roles/directory-manage-roles-portal)

## <a name="supported-services"></a>支持的服务

Microsoft 365 Defender 聚合已部署的各种受支持服务中的数据。 它将集中处理和存储数据，以识别新的见解，并使集中响应工作流成为可能。 这样做不会影响与集成服务关联的现有部署、设置或数据。

为了获得最佳保护和优化Microsoft 365 Defender，我们建议在你的网络上部署所有适用的受支持服务。 有关详细信息， [请阅读有关部署支持的服务的信息](deploy-supported-services.md)。

## <a name="onboard-to-the-service"></a>载入到服务
载入Microsoft 365 Defender非常简单。 从导航菜单中，选择任何项目，如事件&**警报、搜寻**、操作中心或威胁分析，以启动载入过程。 

### <a name="data-center-location"></a>数据中心位置

Microsoft 365 Defender将在 [Microsoft Defender for Endpoint 使用的相同位置存储和处理数据](/windows/security/threat-protection/microsoft-defender-atp/data-storage-privacy)。 如果你没有 Microsoft Defender for Endpoint，则根据活动安全服务的位置自动选择Microsoft 365位置。 所选数据中心位置将显示在屏幕中。

选择 **"需要帮助？"**，Microsoft 365 Defender联系 Microsoft 支持部门，以Microsoft 365 Defender不同的数据中心位置进行预配。

> [!NOTE]
> 过去，通过 Microsoft Defender for Cloud 启用后，Microsoft Defender for Endpoint (欧盟) 数据中心自动预配。 Microsoft 365 Defender在过去以此方式预配了 Defender for Endpoint 的客户，系统将自动在同一欧盟数据中心进行预配。

### <a name="confirm-that-the-service-is-on"></a>确认服务已开启

设置服务后，它将添加：

- [事件管理](incidents-overview.md)
- [警报队列](investigate-alerts.md)
- 用于管理[自动调查和响应](m365d-autoir.md)的操作中心
- [高级搜寻](advanced-hunting-overview.md) 功能
- 威胁分析

:::image type="content" source="../../media/overview-incident.png" alt-text="具有新功能的 Microsoft 365 Defender 门户中的Microsoft 365 Defender窗格" lightbox="../../media/overview-incident.png":::
*Microsoft 365 Defender事件管理和其他功能创建门户*

### <a name="getting-microsoft-defender-for-identity-data"></a>获取 Microsoft Defender for Identity 数据 
若要启用与适用于云应用的 Microsoft Defender 的集成，你至少需要登录到 Microsoft Defender 云应用一次。

## <a name="get-assistance"></a>获取帮助

若要获取有关打开"打开"的最常见问题的解答，Microsoft 365 Defender[常见问题解答](m365d-enable-faq.md)。

Microsoft 支持人员可帮助在租户上设置或取消设置服务和相关资源。 为获得帮助，请选择"需要帮助 **？"**，Microsoft 365 Defender门户。 联系支持人员时，Microsoft 365 Defender。

## <a name="related-topics"></a>相关主题

- [常见问题](m365d-enable-faq.md)
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [Microsoft 365 Defender概述](microsoft-365-defender.md)
- [Microsoft Defender for Endpoint 概述](../defender-endpoint/microsoft-defender-endpoint.md)
- [Defender for Office 365 概述](../office-365-security/defender-for-office-365.md)
- [Microsoft Defender for Cloud Apps 概述](/cloud-app-security/what-is-cloud-app-security)
- [Microsoft Defender for Identity 概述](/azure-advanced-threat-protection/what-is-atp)
- [Microsoft Defender for Endpoint 数据存储](../defender-endpoint/data-storage-privacy.md)
