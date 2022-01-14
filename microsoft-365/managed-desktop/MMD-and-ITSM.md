---
title: Microsoft 托管桌面和 ITIL
description: 将 ITIL 阶段与Microsoft 托管桌面和文章关联
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、ITISM
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.openlocfilehash: b9984e308b6681512297e484817f95206283385e
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035084"
---
# <a name="microsoft-managed-desktop-and-itil"></a>Microsoft 托管桌面和 ITIL

许多组织发现，在 ITM 服务模型（如 [ITIL）](https://www.axelos.com/best-practice-solutions/itil)中，可以 (IT 服务模型) IT 服务。 

Microsoft 托管桌面使组织能够遵守此类形式化 ITSM 模型的很多关键方面。 本文以 ITIL 为例，帮助您查看常见 ITIL 阶段和流程与等效的 IT Microsoft 托管桌面功能（如果适用）之间的关联。 此信息仅适用于组织的Microsoft 托管桌面部分。

有关 ITIL 及其阶段和过程的更全面的信息，请参阅他们的 [文档](https://www.axelos.com/best-practice-solutions/itil)。


## <a name="service-design"></a>服务设计

此表将关键的 ITIL 阶段和流程与Microsoft 托管桌面功能关联，并链接到我们的文档了解详细信息：



|ITIL 过程 |说明  |文档 |
|---------|---------|---------|
|服务级别管理     | 为管理员支持请求和事件定义响应时间。  |  [Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md)  |
|服务目录管理     | 详细服务组件的服务说明将保持为服务状态，可供所有当前和感兴趣的客户使用。<br><br>详细了解运行服务所需的内容的先决条件。  | - [Microsoft 托管桌面服务说明](service-description/index.md)<br><br>- [准备好注册Microsoft 托管桌面](get-ready/index.md)  |
|信息安全管理     | 安全信息，包括服务的信息安全。<br><br> 与安全相关的策略和有关设备配置方式的其他信息。   | - [安全Microsoft 托管桌面](service-description/security.md)<br><br>- [设备配置](service-description/device-policies.md)  |
|可用性管理     |  Microsoft 托管桌面平衡与组织的责任，以确保服务的可用性。<br><br>如果存在服务或可用性问题，管理员和用户可以路由至相应的支持。 | - [Microsoft 托管桌面操作和监视](service-description/operations-and-monitoring.md)<br><br>- [管理员对 Microsoft 托管桌面](working-with-managed-desktop/admin-support.md)<br>- [获取用户帮助](working-with-managed-desktop/end-user-support.md)  |



## <a name="service-transition"></a>服务转换


|ITIL 过程 |说明  |文档 |
|---------|---------|---------|
|变更管理     | 定义的责任、流程概述和与可用变更管理相关的类型平衡。  | [Microsoft 托管桌面操作和监视](service-description/operations-and-monitoring.md#change-management) |
|发布和部署管理     |  Microsoft 托管桌面服务中注册的设备更新。  | [如何在更新中处理Microsoft 托管桌面](service-description/updates.md)        |
|服务资产和配置管理     | IT 管理门户中提供了Microsoft 托管桌面组织部署的信息。  | [Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md) |
|知识管理     | 有关 Microsoft 托管桌面 服务的信息在此网站上保持最新。   | [Microsoft 托管桌面文档更改历史记录](change-history-managed-desktop.md)        |



## <a name="service-operation"></a>服务操作


|ITIL 过程 |说明  |文档  |
|---------|---------|---------|
|事件管理     |  提供了有关监视设备的详细信息。<br><br>详细介绍了 Microsoft 托管桌面 服务的标准操作过程。 |  - [安全Microsoft 托管桌面](service-description/security.md)<br>- [Microsoft 托管桌面操作和监视](service-description/operations-and-monitoring.md)       |
|事件管理  | Microsoft 托管桌面根据定义的严重性定义调查和处理事件。  |  [支持请求严重性定义](working-with-managed-desktop/admin-support.md#support-request-severity-definitions)       |
|请求实施管理     |  定义信息请求和与服务相关的更改Microsoft 托管桌面过程。         |[Microsoft 托管桌面的管理员支持](working-with-managed-desktop/admin-support.md)         |
|问题管理     | 目前，该服务的任何问题都应定向到本地帐户团队。 | 开发中的文档 |
|访问管理     | 访问管理组件和客户确保功能的详细职责。  | [身份和访问管理](service-description/security.md#identity-and-access-management)        |
