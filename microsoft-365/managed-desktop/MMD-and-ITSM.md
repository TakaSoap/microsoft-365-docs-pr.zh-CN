---
title: Microsoft 托管桌面和 ITIL
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档，ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: 4b735ec28b655dfc01c874bc4865388d11247b67
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47947956"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft 托管桌面和 ITIL

许多组织都发现，按照正规 IT 服务模型 (ITSM) （如 [ITIL](https://www.axelos.com/best-practice-solutions/itil)）的方式来组织其 it 服务有价值。 

Microsoft 托管桌面使您的组织能够遵守此类正式 ITSM 模型的许多关键方面。 使用 ITIL 作为示例，本主题可帮助您查看常见 ITIL 阶段和过程以及等效 Microsoft 托管桌面功能之间的连接（如果适用）。 这仅适用于你的组织的 Microsoft 托管桌面部分。

若要更全面地了解 ITIL 及其阶段和过程，请参阅其 [文档](https://www.axelos.com/best-practice-solutions/itil)。


## <a name="service-design"></a>服务设计

此表介绍了 Microsoft 托管桌面功能的主要 ITIL 阶段和过程，并提供了有关详细信息的文档的链接：



|ITIL 流程 |说明  |文档 |
|---------|---------|---------|
|服务级别管理     | 为管理员支持请求和事件定义响应时间。  |  [Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md)  |
|服务目录管理     | 服务说明详细介绍了服务的组件，并将其提供给所有当前和感兴趣的客户，这是服务的状态。<br><br>先决条件详细，以了解操作服务所需的内容。  | - [Microsoft 托管桌面服务说明](service-description/index.md)<br><br>- [准备好在 Microsoft 托管桌面中进行注册](get-ready/index.md)  |
|信息安全管理     | 安全信息，包括服务的信息安全性。<br><br> 与安全相关的策略以及有关如何配置设备的其他信息。   | - [Microsoft 托管桌面中的安全性](service-description/security.md)<br><br>- [设备配置](service-description/device-policies.md)  |
|可用性管理     |  Microsoft 托管桌面负责平衡组织的责任，以确保服务的可用性。<br><br>在服务或可用性问题的情况下，管理员和用户都有针对各自支持的路由。 | - [Microsoft 托管桌面操作和监视](service-description/operations-and-monitoring.md)<br><br>- [Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md)<br>- [获取用户帮助](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>服务转换


|ITIL 流程 |说明  |文档 |
|---------|---------|---------|
|变更管理     | 定义了责任平衡、流程概述和与可用的变更管理相关的类型。  | [Microsoft 托管桌面操作和监视](service-description/operations-and-monitoring.md#change-management) |
|发布和部署管理     |  Microsoft 托管桌面管理在服务中注册的设备的更新。  | [如何在 Microsoft 托管桌面中处理更新](service-description/updates.md)        |
|服务资产和配置管理     | 有关贵组织的 Microsoft 托管桌面部署的信息在 IT 管理员门户中提供。  | [Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md) |
|知识管理     | 有关 Microsoft 托管桌面服务的信息在此网站上保持最新。   | [Microsoft 托管桌面文档更改历史记录](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>服务操作


|ITIL 流程 |说明  |文档  |
|---------|---------|---------|
|事件管理     |  提供有关设备监控的详细信息。<br><br>Microsoft 托管桌面服务的标准操作过程是详细说明。 |  - [Microsoft 托管桌面中的安全性](service-description/security.md)<br>- [Microsoft 托管桌面操作和监视](service-description/operations-and-monitoring.md)       |
|事件管理  | Microsoft 托管桌面将根据定义的严重性定义对事件进行调查和操作。  |  [支持请求严重性定义](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|请求履单管理     |  定义了与 Microsoft 托管桌面服务相关的信息和更改请求的处理过程。         |[Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md)         |
|问题管理     | 此时应将服务的任何问题定向到你的本地帐户团队。 | 开发中的文档 |
|访问管理     | 针对客户的访问管理组件和责任，以确保功能详细。  | [标识和访问管理](service-description/security.md#identity-and-access-management)        |
