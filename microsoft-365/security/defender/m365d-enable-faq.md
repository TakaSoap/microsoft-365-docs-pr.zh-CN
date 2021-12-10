---
title: 打开系统时常见问题Microsoft 365 Defender
description: 获取有关授权、权限、初始设置以及其他与启用权限相关的产品和服务的最常见Microsoft 365 Defender
keywords: 常见问题， 常见问题， GCC， 入门， 启用 Microsoft 365 Defender， Microsoft 365 Defender， M365， 安全， 数据位置， 所需权限， 许可证资格， 设置页面
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
ms.openlocfilehash: e5ed41f400c24a2522ea49f2524d0fe629bdbb9f
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374744"
---
# <a name="frequently-asked-questions-when-turning-on-microsoft-365-defender"></a>打开系统时常见问题Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


**适用于：**
- Microsoft 365 Defender

阅读对有关打开 Microsoft 365 Defender 的最常见问题的回复，包括所需的许可证和权限[、](microsoft-365-defender.md)部署支持服务和初始设置。

有关如何打开服务的说明，请阅读打开[Microsoft 365 Defender。](m365d-enable.md)

## <a name="i-dont-have-a-microsoft-365-e5-license-can-i-still-use-microsoft-365-defender"></a>我并没有Microsoft 365 E5许可证。 我是否仍可以使用Microsoft 365 Defender？

具有以下非 E5 许可证的客户可以使用Microsoft 365 Defender：

- Microsoft Defender for Endpoint
- Microsoft Defender for Identity
- Microsoft Defender for Cloud Apps
- Defender for Office 365 (计划 2)

有关受支持的许可证的完整列表， [请阅读许可要求](prerequisites.md#licensing-requirements)。

## <a name="do-i-need-to-install-or-deploy-anything-to-start-using-microsoft-365-defender"></a>是否需要安装或部署任何内容以开始使用Microsoft 365 Defender？

否，Microsoft 365 Defender已部署Microsoft 365安全服务中合并数据。 启用后，事件、自动化和搜寻体验将开始在已部署产品范围内工作。 如果没有正确部署这些产品，Microsoft 365 Defender将不会显示任何数据，并且无法执行任何操作。

若要优化你的Microsoft 365 Defender体验，我们建议部署所有受支持的Microsoft 365[安全产品和服务](deploy-supported-services.md)。 

## <a name="where-does-microsoft-365-defender-process-and-store-my-data"></a>在哪里Microsoft 365 Defender和存储我的数据？

Microsoft 365 Defender为处理和存储合并数据的数据中心自动选择一个最佳位置。 如果你有适用于终结点的 Microsoft Defender，它将选择 Defender for Endpoint 所使用的相同位置。

>[!NOTE]
>Microsoft Defender for Endpoint 通过 Microsoft Defender for Cloud (启用后) 欧盟和欧盟数据中心自动进行设置。 Microsoft 365 Defender将在同一个欧盟数据中心中为已经通过此方式预配 Microsoft Defender for Endpoint 的客户自动进行预配。

数据中心位置显示在服务预配之前和之后，位于 **Microsoft 365 Defender (设置 > Microsoft 365 Defender) 。** 如果你想要使用另一个数据中心位置，请选择"需要帮助？"，Microsoft 365 Defender联系 Microsoft 支持人员。

## <a name="where-can-i-access-microsoft-365-defender"></a>在哪里可以访问Microsoft 365 Defender？

<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank"><https://security.microsoft.com></a>Microsoft 365 Defender：。

## <a name="what-permissions-do-i-need-to-access-microsoft-365-defender"></a>我需要哪些权限才能访问Microsoft 365 Defender？

分配了以下角色Azure Active Directory (Azure AD) 帐户可以访问Microsoft 365 Defender功能和数据：

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

## <a name="what-time-zone-does-microsoft-365-defender-default-to"></a>默认为Microsoft 365 Defender时区？

默认情况下，Microsoft 365 Defender UTC 时区显示时间信息。 你可以更改此设置以使用本地时区。 [了解如何设置时区](m365d-time-zone.md)

## <a name="how-can-i-learn-about-new-microsoft-365-defender-feature-and-ui-updates"></a>如何了解新的自定义Microsoft 365 Defender和 UI 更新？

Microsoft 会定期通过各种渠道提供相关信息，包括：

- 邮件[中心](../../admin/manage/message-center.md)Microsoft 365 管理中心
- 安全与Microsoft 365技术&[博客文章](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/bg-p/securityprivacycompliance)

打开预览功能，获取最新公开 [可用体验](preview.md)。

## <a name="related-topics"></a>相关主题

- [Microsoft 365 Defender概述](microsoft-365-defender.md)
- [打开Microsoft 365 Defender。](m365d-enable.md)
- [许可要求和其他先决条件](prerequisites.md)
- [部署支持的服务](deploy-supported-services.md)
- [启用预览功能](preview.md)
