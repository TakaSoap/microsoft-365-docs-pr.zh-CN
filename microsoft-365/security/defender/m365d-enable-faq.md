---
title: 打开Microsoft 365 Defender时常见问题解答
description: 获取有关许可、权限、初始设置以及与启用Microsoft 365 Defender相关的其他产品和服务的最常见问题的解答
keywords: 常见问题解答、常见问题解答、GCC、入门、启用Microsoft 365 Defender、Microsoft 365 Defender、M365、安全性、数据位置、所需权限、许可证资格、设置页
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
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 73dddcfc1389eb5bb0b0115f0666c413dc7d2a01
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663195"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>打开Microsoft 365 Defender时常见问题解答

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

阅读对有关启用[Microsoft 365 Defender](microsoft-365-defender.md)的最常见问题的回复，包括所需的许可证和权限、部署支持服务和初始设置。

有关如何打开服务的说明，[请阅读"打开Microsoft 365 Defender](m365d-enable.md)"。

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>我没有Microsoft 365 E5许可证。 我还能使用Microsoft 365 Defender吗？

具有以下非 E5 许可证的客户可以使用Microsoft 365 Defender：

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Defender for Office 365 (计划 2)

有关支持的许可证的完整列表， [请阅读许可要求](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>是否需要安装或部署任何内容才能开始使用Microsoft 365 Defender？

否，Microsoft 365 Defender合并已部署Microsoft 365安全服务的数据。 打开后，事件、自动化和搜寻体验将在已部署产品范围内开始工作。 如果这些产品均未正确部署，Microsoft 365 Defender将不会显示任何数据，也无法采取任何操作。

为了优化Microsoft 365 Defender体验，建议部署 *所有* 受支持的 [Microsoft 365安全产品和服务](deploy-supported-services.md)。

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>Microsoft 365 Defender在哪里处理和存储我的数据？

Microsoft 365 Defender自动为处理和存储合并数据的数据中心选择最佳位置。 如果已Microsoft Defender for Endpoint，则会选择 Defender for Endpoint 使用的相同位置。

>[!NOTE]
>Microsoft Defender for Endpoint通过Microsoft Defender for Cloud启用时，欧盟 (欧盟) 数据中心自动预配数据。 Microsoft 365 Defender将自动为以这种方式预配Microsoft Defender for Endpoint的客户在同一欧盟数据中心进行预配。

在Microsoft 365 Defender (设置 > Microsoft 365 Defender) 的设置页中预配服务之前和之后，将显示数据中心位置。 如果希望使用其他数据中心位置，请在Microsoft 365 Defender门户中选择 **"需要帮助"** 以联系 Microsoft 支持部门。

## <a name="where-can-i-access-microsoft-365-defender"></a>在哪里可以访问Microsoft 365 Defender？

Microsoft 365 Defender提供： <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a>.

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender"></a>需要哪些权限才能访问Microsoft 365 Defender？

分配了以下Azure Active Directory (Azure AD) 角色的帐户可以访问Microsoft 365 Defender功能和数据：

- 全局管理员
- 安全管理员
- 安全操作员
- 全局读取者
- 安全读取者
- 合规管理员
- 合规数据管理员
-  应用程序管理员
- 云 应用程序管理员


> [!NOTE]
> Microsoft Defender for Endpoint 中基于角色的访问控制设置会影响对数据的访问。 有关详细信息，请阅读[管理对 Microsoft 365 Defender 的访问](m365d-permissions.md)。

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>默认Microsoft 365 Defender哪些时区？

默认情况下，Microsoft 365 Defender在 UTC 时区中显示时间信息。 可以更改此设置以使用本地时区。 [了解如何设置时区](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>如何了解新的Microsoft 365 Defender功能和 UI 更新？

Microsoft 定期通过各种渠道提供信息，包括：

- Microsoft 365 管理中心中[的消息中心](../../admin/manage/message-center.md)
- [Microsoft 365安全&合规性技术社区](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)中的博客文章

通过启用 [预览功能](preview.md)来获取最新的公开体验。

## <a name="related-topics"></a>相关主题

- [Microsoft 365 Defender概述](microsoft-365-defender.md)
- [打开Microsoft 365 Defender](m365d-enable.md)。
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [启用预览功能](preview.md)
