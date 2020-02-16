---
title: 通过 ServiceNow 创建和跟踪票证
description: Microsoft 365 安全中心已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。 安全管理员可以将安全得分建议直接发送到 ServiceNow 并创建票证。
keywords: security、Microsoft 365、M365、安全分数、安全中心、ServiceNow、票证、任务
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 240e153c43c7dc52d67d35eeca36def2f76b08e2
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42086915"
---
# <a name="manage-tickets-through-servicenow"></a>通过 ServiceNow 管理票证

Microsoft 365 安全中心已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。 安全管理员可以直接向 ServiceNow 发送[Microsoft Secure 得分](microsoft-secure-score.md)改进操作，并创建一个票证。 可以创建事件管理和变更管理票证。

## <a name="prerequisites"></a>先决条件

有权访问 Microsoft 365 安全中心和 ServiceNow 实例，请执行以下操作：  

* Kingston 或更高版本
* 拥有管理员的高凭据
* 拥有对目标供应商实例的管理员权限

ServiceNow 建议用户在你的 ServiceNow 实例中保留默认设置。 在完成安装清单并与 Microsoft 365 安全中心集成时，具有自定义可能会导致错误。

## <a name="data-exchange"></a>数据交换

当您将 Microsoft 365 安全中心连接到 ServiceNow 时，Microsoft 会收到以下附加数据：

* ServiceNow 实例名称
* ServiceNow 客户端 ID
* ServiceNow 客户端密码
* ServiceNow 访问 & 刷新令牌

当您从 Microsoft 365 安全中心创建 ServiceNow 票证时，会将以下数据发送到 ServiceNow：

* 启动创建票证的用户 ID
* 任务名称
* 任务说明
* 优先级
* 截止日期
* 建议源（用户建议或 Microsoft 推荐）
* 建议类别（设备、数据、应用、标识、基础结构）

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>将 Microsoft 365 安全中心连接到 ServiceNow

导航到 Microsoft 365 安全中心主页以查看 ServiceNow 连接卡。

![您是否使用 ServiceNow](../../media/do-you-use-servicenow-250.png)

选择 "连接到 ServiceNow" 以转到 "ServiceNow 设置" 页。 按照说明授权 Microsoft 365 连接器应用。

> [!NOTE]
> 在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。 请勿使用你的个人凭据。

按照说明进行操作并授权连接后，请查看 Microsoft 365 安全中心连接页和 ServiceNow Microsoft 365 票证发放连接器应用程序体验中的连接状态。 现在，你已设置为开始创建任务！

## <a name="create-a-task-and-share-it-to-servicenow"></a>创建一个任务并将其共享到 ServiceNow

建立集成后，基于特定 Microsoft 安全得分改进操作创建 ServiceNow 任务。 转到 Microsoft 365 安全中心门户中安全得分的任何改进措施，并选择 "共享" 图标。 其中一个下拉选项是 ServiceNow。

![安全分数中的 ServiceNow 共享](../../media/servicenow-share.png)

将生成一个任务，您可以在其中设置优先级并编辑名称、说明或截止日期。 填写所有必填字段后，将该任务发送到 ServiceNow。

在 ServiceNow 中，此任务显示为 Microsoft 365 安全性和配置更改请求。

## <a name="track-tickets"></a>跟踪票证

一旦创建了 ServiceNow 更改管理和事件管理票证，它们就会显示在 Microsoft 365 安全中心主页上的卡片上。 通过这些卡，您可以创建一个票证、查看所有票证或管理 ServiceNow 配置。

![ServiceNow 更改管理票证](../../media/change-management-375.png)  ![ServiceNow 事件管理票证](../../media/incident-management-375.png)

若要在 Microsoft 365 安全中心中重新设置或管理你的 ServiceNow 集成，请选择任一卡片上的 "**管理 servicenow 配置**"。 在此处，删除当前的 ServiceNow 连接并自定义票证状态名称。

借助 Microsoft 365 security center 中显示的 ServiceNow 票证，你的任务可以在某个位置进行跟踪，并在你的其他安全仪表板项目旁边进行操作。

## <a name="troubleshooting"></a>故障排除

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>您在安装清单（OAuth 创建）的第一步中收到错误

**错误消息**：由于表的跨范围访问策略，对作用域 "x_mioms_m365ticket" 中的 "oauth_entity" 执行的读取操作已被拒绝

应用程序假定 ServiceNow 实例上的任何管理员都可以创建和读取 OAuth 实体。 此错误可能是由于对 ServiceNow 实例的自定义设置造成的，这会限制可创建/读取 OAuth 实体的用户。

**ServiceNow 建议用户保留默认功能。**

将 "应用程序注册表" 表配置设置为默认值：

* Label = Application Registeries
* Name = oauth_entity
* 可从 = 所有应用程序范围访问
* 可以读取 = 复选框处于选中状态

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>如何验证为 Microsoft 365 安全 & 合规性连接器创建的 OAuth 实体

转到 ServiceNow 中的 "应用程序注册表" 表（**菜单 > 系统 OAuth > 应用程序注册表**），并使用您为其分配的名称查找您创建的 OAuth 实体。

### <a name="logging-in-as-the-integration-user"></a>作为集成用户登录

在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。 请勿使用你的个人凭据。

1. 转到 ServiceNow 中的 "授权" 页面。
2. 如果使用个人凭据登录，请选择右上角的 "**不**链接"。
3. 以您以前从安装清单创建的集成用户的形式登录到 ServiceNow。  
4. 在 ServiceNow 页面中选择 "**允许**"，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。
5. 继续执行设置步骤。

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>如何验证在安装清单中创建的集成用户是否符合 Microsoft 365 安全 & 合规性连接器

转到 ServiceNow 中的 "用户" 表 **（菜单 > 用户管理 > 用户**），并使用您为其分配的名称查找您创建的集成用户。

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>你的公司启用了单一登录，这将阻止你通过 Microsoft 365 安全中心连接到 ServiceNow

如果贵公司已启用单一登录，但您收到错误或登录失败，请按照这两个解决方案之一。

#### <a name="log-into-servicenow-as-the-integration-user"></a>以集成用户的形式登录到 ServiceNow

1. 导航回 ServiceNow 中的 "授权" 页面。
2. 选择右上角的 "**不向您**链接"。
3. 以您以前从安装清单创建的集成用户的形式登录到 ServiceNow。  
4. 在 ServiceNow 页面中选择 "**允许**"，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。
5. 继续执行设置步骤。

#### <a name="create-a-security-admin-user"></a>创建安全管理员用户

1. 在 Azure Active Directory 中创建具有安全管理员权限的用户。 用户需要与您在安装清单中创建的集成用户具有相同的名称和电子邮件地址。 登录和连接完成后，可以删除安全管理员角色。
2. 作为此用户登录到 Microsoft 365 安全中心，并按照安装步骤进行操作。

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>安装已完成，但看不到票证且无法共享

如果已完成安装和设置步骤，但您在主页上看不到 ServiceNow 卡，并且无法从 Microsoft 安全分数中共享到 ServiceNow，请在处https://security.microsoft.com/ticketProvisioning检查设置页面的状态。 选择 "**授权**" 并返回到主页。 应显示卡片。

