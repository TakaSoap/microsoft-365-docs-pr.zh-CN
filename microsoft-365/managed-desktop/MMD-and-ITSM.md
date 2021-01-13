---
title: Microsoft 托管桌面和 ITIL
description: 将 ITIL 阶段与 Microsoft 托管桌面信息和文章关联
keywords: Microsoft 托管桌面， Microsoft 365， 服务， 文档， ITISM
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.openlocfilehash: e545b64670bb92c40465f1c50b2cb46b9fd7a8d8
ms.sourcegitcommit: 83a40facd66e14343ad3ab72591cab9c41ce6ac0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2021
ms.locfileid: "49841431"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft 托管桌面和 ITIL

许多组织发现，沿 ITM 服务模型（如 [ITIL）](https://www.axelos.com/best-practice-solutions/itil)的规范化 IT 服务模型 (IT 服务) 非常有价值。 

Microsoft 托管桌面使组织能够遵守此类形式化 ITSM 模型的许多关键方面。 以 ITIL 为例，本文将帮助您查看常见 ITIL 阶段和流程与等效 Microsoft 托管桌面功能（如果适用）之间的连接。 此信息仅适用于组织的 Microsoft 托管桌面部分。

有关 ITIL 及其阶段和过程的更全面的信息，请参阅他们的 [文档](https://www.axelos.com/best-practice-solutions/itil)。


## <a name="service-design"></a>服务设计

此表将关键 ITIL 阶段和流程与 Microsoft 托管桌面功能关联，并链接到我们的文档，了解详细信息：



|ITIL 进程 |说明  |文档 |
|---------|---------|---------|
|服务级别管理     | 为管理员支持请求和事件定义响应时间。  |  [Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md)  |
|服务目录管理     | 服务说明详细说明服务组件与服务状态保持一样，可供所有当前和感兴趣的客户使用。<br><br>详细了解运行服务所需内容的先决条件。  | - [Microsoft 托管桌面服务说明](service-description/index.md)<br><br>- [准备好在 Microsoft 托管桌面中注册](get-ready/index.md)  |
|信息安全管理     | 安全信息，包括服务的信息安全。<br><br> 与安全相关的策略和有关设备配置方式的其他信息。   | - [Microsoft 托管桌面中的安全性](service-description/security.md)<br><br>- [设备配置](service-description/device-policies.md)  |
|可用性管理     |  Microsoft 托管桌面在责任与组织之间取得平衡，以确保服务的可用性。<br><br>如果存在服务或可用性问题，管理员和用户可以路由到相应的支持。 | - [Microsoft 托管桌面操作和监视](service-description/operations-and-monitoring.md)<br><br>- [Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md)<br>- [获取用户帮助](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>服务转换


|ITIL 进程 |说明  |文档 |
|---------|---------|---------|
|变更管理     | 定义责任、流程概述和与变更管理相关的可用类型之间的平衡。  | [Microsoft 托管桌面操作和监视](service-description/operations-and-monitoring.md#change-management) |
|发布和部署管理     |  Microsoft 托管桌面管理服务中注册设备的更新。  | [如何在 Microsoft 托管桌面中处理更新](service-description/updates.md)        |
|服务资产和配置管理     | 有关组织的 Microsoft 托管桌面部署的信息，请参阅 IT 管理门户。  | [Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md) |
|信息管理     | 有关 Microsoft 托管桌面服务的信息在此网站上保持最新。   | [Microsoft 托管桌面文档更改历史记录](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>服务操作


|ITIL 进程 |说明  |文档  |
|---------|---------|---------|
|事件管理     |  提供了有关监视设备的详细信息。<br><br>详细介绍了 Microsoft 托管桌面服务的标准操作过程。 |  - [Microsoft 托管桌面中的安全性](service-description/security.md)<br>- [Microsoft 托管桌面操作和监视](service-description/operations-and-monitoring.md)       |
|事件管理  | Microsoft 托管桌面将根据定义的严重性定义调查和处理事件。  |  [支持请求严重性定义](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|请求实施管理     |  定义信息请求和与 Microsoft 托管桌面服务相关的更改请求的过程。         |[Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md)         |
|问题管理     | 目前，该服务的任何问题都应定向到本地帐户团队。 | 开发中的文档 |
|访问管理     | 访问管理组件和客户在确保功能方面的责任是详细的。  | [标识和访问管理](service-description/security.md#identity-and-access-management)        |
