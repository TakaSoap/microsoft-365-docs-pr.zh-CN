---
title: 打开 Defender 时Microsoft 365常见问题
description: 获取有关授权、权限、初始设置以及其他与启用 Defender 相关的产品和服务的最常见Microsoft 365解答
keywords: 常见问题， 常见问题， GCC， 入门， 启用 Microsoft 365 Defender， Microsoft 365 Defender， M365， 安全， 数据位置， 所需权限， 许可证资格， 设置页面
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
ms.openlocfilehash: 008e3cc6ee65597a032aa932b74a64ac591927f2
ms.sourcegitcommit: 0936f075a1205b8f8a71a7dd7761a2e2ce6167b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52572761"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>打开 Defender 时Microsoft 365常见问题

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

阅读对有关启用[Microsoft 365 Defender](microsoft-365-defender.md)的最常见问题的回复，包括所需的许可证和权限、部署支持服务和初始设置。

有关如何打开该服务的说明，请阅读打开 Microsoft 365 [Defender。](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>我并没有许可证Microsoft 365 E5许可证。 我是否仍可以使用 Microsoft 365 Defender？

具有以下非 E5 许可证的客户可以使用 Microsoft 365 Defender：

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Cloud App Security
- Defender for Office 365 (计划 2)
 
有关受支持的许可证的完整列表， [请阅读许可要求](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>是否需要安装或部署任何内容以开始使用 Microsoft 365 Defender？

否，Microsoft 365 Defender 会合并Microsoft 365部署的安全服务的数据。 启用后，事件、自动化和搜寻体验将开始在已部署产品范围内工作。 如果未正确部署这些产品，Microsoft 365 Defender 将不会显示任何数据，并且无法执行任何操作。

若要优化你的 Microsoft 365 Defender 体验，*我们建议部署所有* 受支持的Microsoft 365 [安全产品和服务](deploy-supported-services.md)。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Defender Microsoft 365处理和存储我的数据的位置？
Microsoft 365Defender 会自动为处理和存储合并数据的数据中心选择一个最佳位置。 如果你有适用于终结点的 Microsoft Defender，它将选择 Defender for Endpoint 所使用的相同位置。

>[!NOTE]
>Microsoft Defender for Endpoint 在通过 Azure Defender (欧盟) 数据中心自动设置。 Microsoft 365Defender 将在同一欧盟数据中心中自动为已预配 Microsoft Defender for Endpoint 的客户进行预配。 

数据中心位置显示在 Defender (Defender Microsoft 365 设置页面之前和之后设置 > Microsoft 365 **服务**) 。 如果你希望使用另一个数据中心位置，请选择安全中心Microsoft 365需要帮助？"，联系 Microsoft 支持人员。

## <a name="where-can-i-access-microsoft-365-defender"></a>在哪里可以访问 Microsoft 365 Defender？

Microsoft 365Defender 在安全Microsoft 365可用。 若要转到安全中心，请浏览到 URL [https://security.microsoft.com](https://security.microsoft.com) 。

##  <a name="what-permissions-do-i-need-to-access-microsoft-365-defender-in-microsoft-365-security-center"></a>我需要哪些权限才能访问安全Microsoft 365 Defender Microsoft 365 Defender？

在 Azure AD Azure Active Directory (分配) 的帐户可以访问Microsoft 365 Defender 功能和数据：

- 全局管理员
- 安全管理员
- 安全操作员
- 全局读取者
- 安全读取者

>[!NOTE]
>Microsoft Defender for Endpoint 中基于角色的访问控制设置会影响对数据的访问。 有关详细信息，请阅读有关管理对[Microsoft 365 Defender 的访问权限](m365d-permissions.md)。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>Defender 默认Microsoft 365什么时区？
默认情况下，Microsoft 365 Defender 以 UTC 时区显示时间信息。 你可以更改此设置以使用本地时区。 [了解如何设置时区](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>如何了解有关 Defender Microsoft 365 UI 更新的信息？

Microsoft 会定期通过各种渠道提供相关信息，包括：

- 管理[中心](../../admin/manage/message-center.md)Microsoft 365中心
- 安全与Microsoft 365[技术&博客文章](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

打开预览功能，获取最新公开 [可用体验](preview.md)。

## <a name="is-microsoft-365-defender-available-for-us-government-community-cloud-gcc-or-gcc-high"></a>Microsoft 365 Defender 是否适用于美国政府社区云 (GCC) 或GCC高？
目前不可用。

## <a name="related-topics"></a>相关主题

- [Microsoft 365Defender 概述](microsoft-365-defender.md)
- [打开 Microsoft 365 Defender](m365d-enable.md)。
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [启用预览功能](preview.md)
