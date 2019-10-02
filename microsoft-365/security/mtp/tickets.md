---
title: 通过 ServiceNow 创建和跟踪票证
description: Microsoft 365 安全中心已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。 这允许安全管理员将安全得分建议直接发送到 ServiceNow 并创建票证。
keywords: security、Microsoft 365、M365、安全分数、安全中心、ServiceNow、票证、任务
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b0b8cda81bb6cec3958e7b2a758da191d803a0ed
ms.sourcegitcommit: acf29701bfba3e4843e49a79fde012f3c7a7024a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/01/2019
ms.locfileid: "37350324"
---
# <a name="manage-tickets-through-servicenow"></a>通过 ServiceNow 管理票证

Microsoft 365 安全中心已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。 这使安全管理员能够直接向 ServiceNow 发送[Microsoft Secure 得分](microsoft-secure-score.md)改进操作，并创建一个票证。 可以创建事件管理和变更管理票证。

## <a name="prerequisites"></a>先决条件

有权访问 Microsoft 365 安全中心和 ServiceNow 实例，请执行以下操作：  

* Kingston 或更高版本
* 拥有管理员的高凭据
* 拥有对目标供应商实例的管理员权限

ServiceNow 建议用户在你的 ServiceNow 实例中保留现成设置（默认）。  进行自定义可能会导致完成安装清单中的错误并与 Microsoft 365 安全中心集成。

## <a name="data-exchange"></a>数据交换

当你将 Microsoft 365 安全中心连接到 ServiceNow 时，Microsoft 将收到以下其他数据：

* ServiceNow 实例名称
* ServiceNow 客户端 ID
* ServiceNow 客户端密码
* ServiceNow 访问 & 刷新令牌

从 Microsoft 365 安全中心创建 ServiceNow 票证时，会将以下数据发送到 ServiceNow：

* 启动创建票证的用户 ID
* 任务名称
* 任务说明
* 优先级
* 截止日期
* 建议源（用户建议或 Microsoft 推荐）
* 建议类别（设备、数据、应用、标识、基础结构）

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>将 Microsoft 365 安全中心连接到 ServiceNow

导航到 Microsoft 365 安全中心主页，你将看到一个卡片，询问你是否使用 ServiceNow。

![您是否使用 ServiceNow](../images/do-you-use-servicenow-250.png)

在这里，将会发送到 ServiceNow 设置页面，在此页面中，你将按照说明授权 Microsoft 365 连接器应用。

在授权 Microsoft 365 安全中心与 ServiceNow 之间的连接时，请确保使用在安装步骤中创建的集成用户登录名和密码，而不是您的个人凭据。

按照说明操作并授权连接后，你可以在 Microsoft 365 安全中心连接页和 ServiceNow Microsoft 365 票证发放连接器应用体验中查看连接状态。 现在，你已设置为开始创建任务！

## <a name="create-a-task-and-share-it-to-servicenow"></a>创建一个任务并将其共享到 ServiceNow

建立集成后，可以基于特定 Microsoft 安全得分改进操作创建 ServiceNow 任务。 转到 Microsoft 365 安全中心门户中安全得分的任何改进措施，并选择 "共享" 图标。 其中一个下拉选项是 ServiceNow。

![安全分数中的 ServiceNow 共享](../images/servicenow-share.png)

然后，将生成一个任务，您可以在其中设置优先级并编辑名称、说明或截止日期。 填写所有必填字段后，即可将该任务发送到 ServiceNow。

该任务将在 ServiceNow 中显示为 Microsoft 365 安全和配置更改请求。

## <a name="track-tickets"></a>跟踪票证

一旦创建了 ServiceNow 更改管理和事件管理票证，它们将显示在 Microsoft 365 安全中心主页上的卡片上。 通过这些卡，您可以创建一个票证、查看所有票证或管理 ServiceNow 配置。

![ServiceNow 更改管理票证](../images/change-management-375.png)  ![ServiceNow 事件管理票证](../images/incident-management-375.png)

若要在 Microsoft 365 安全中心中重新设置或管理你的 ServiceNow 集成，请选择任一卡片上的 "**管理 servicenow 配置**"。 您可以从中删除当前 ServiceNow 连接并自定义票证状态名称。

使用 Microsoft 365 安全中心中显示的 ServiceNow 票证，您的任务将处于活动状态，可在其中跟踪和操作其他安全仪表板项目的位置。

## <a name="frequently-asked-questions"></a>常见问题

### <a name="i-am-receiving-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>在安装清单的第一步中收到错误（OAuth 创建）

**错误消息**：由于表的跨范围访问策略，对作用域 "x_mioms_m365ticket" 中的 "oauth_entity" 执行的读取操作已被拒绝

我们的应用程序假定 ServiceNow 实例上的任何管理员都可以创建和读取 OAuth 实体。 此错误可能是由于对 ServiceNow 实例的自定义设置造成的，这会限制可创建/读取 OAuth 实体的用户。 ServiceNow 建议用户保持 "开箱即用" 功能（默认）。

将 "应用程序注册表" 表配置设置为默认值：

* Label = Application Registeries
* Name = oauth_entity
* 可从 = 所有应用程序范围访问
* 可以读取 = 复选框处于选中状态

**ServiceNow 建议用户保持 "开箱即用" 功能（默认）。**

### <a name="how-do-i-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>如何验证为 Microsoft 365 Security & 合规性连接器创建的 OAuth 实体？

转到 ServiceNow 中的 "应用程序注册表" 表（菜单 > 系统 OAuth > 应用程序注册表），并查找您创建的 OAuth 实体（您为其分配的名称）。

### <a name="how-do-i-validate-the-integration-user-created-in-step-two-of-installation-checklist-for-microsoft-365-security--compliance-connector"></a>如何验证在 Microsoft 365 Security & 合规性连接器的第2步安装清单中创建的集成用户？

转到 ServiceNow 中的 "用户" 表（菜单 > 用户管理 > 用户），并查找您创建的集成用户（您为其分配的名称）。

在授权 Microsoft 365 安全中心与 ServiceNow 之间的连接时，请确保使用在安装步骤中创建的集成用户登录名和密码，而不是您的个人凭据。

### <a name="i-have-completed-the-installation-and-set-up-steps-but-i-am-unable-to-see-the-servicenow-cards-on-the-home-page-and-cannot-see-the-share-icon-in-microsoft-secure-score"></a>我已完成安装并设置了步骤，但我无法在主页上看到 ServiceNow 卡，也无法在 Microsoft 安全分数中看到共享图标

通过转到来https://security.microsoft.com/ticketProvisioning检查设置页面的状态。 选择 "**保存**" 并返回到主页。 应显示卡片。
