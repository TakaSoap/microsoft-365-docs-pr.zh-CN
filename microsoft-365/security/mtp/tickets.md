---
title: 将 ServiceNow 票证集成到 Microsoft 365 安全中心和合规性中心
description: 了解如何从 Microsoft 365 安全中心和合规中心在 ServiceNow 中创建和跟踪票证。
keywords: security、Microsoft 365、M365、合规性、合规性中心、安全中心、ServiceNow、票证、任务、雪、connection
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
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: a2650efbac0966b84e6fbfd6ce78cb732f4933b3
ms.sourcegitcommit: bd36c88e731e3fee2a3a5cb3564fdc94f11bab94
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/27/2020
ms.locfileid: "48769649"
---
# <a name="integrate-servicenow-tickets-into-the-microsoft-365-security-center-and-compliance-center"></a>将 ServiceNow 票证集成到 Microsoft 365 安全中心和合规性中心

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

>[!CAUTION]
>**ServiceNow 连接器的预览周期即将结束**<br>
>此功能将在11月2020结束后不再可用。 感谢你的反馈，并在我们确定后续步骤时继续提供支持。

ServiceNow 是一款受欢迎的云计算平台，可帮助公司管理企业运营的数字工作流。 他们的 Now 平台具有 IT 工作流、员工工作流和客户工作流。 [了解有关 ServiceNow 的详细信息](https://www.servicenow.com/)

Microsoft 已与 ServiceNow 合作，使 IT 管理员可以更轻松地管理两个平台中的票证和任务。 [Microsoft 365 安全中心](overview-security-center.md) 和 [microsoft 365 合规性中心](https://docs.microsoft.com/microsoft-365/compliance/microsoft-365-compliance-center) 已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。

- [**在安全中心中管理 ServiceNow 票证**](tickets-security-center.md)
- **在合规中心中管理 ServiceNow 票证** (即将推出) 

## <a name="prerequisites"></a>必备条件

有权访问 Microsoft 365 安全中心或合规性中心和包含以下内容的 ServiceNow 实例：  

* Kingston 或更高版本
* 拥有管理员的高凭据
* 拥有对目标供应商实例的管理员权限

ServiceNow 建议用户在你的 ServiceNow 实例中保留默认设置。 在完成安装清单并与 Microsoft 365 安全中心集成时，具有自定义可能会导致错误。

## <a name="data-exchange"></a>数据交换

当您将 Microsoft 365 安全中心或合规中心连接到 ServiceNow 时，Microsoft 会收到以下附加数据：

* ServiceNow 实例名称
* ServiceNow 客户端 ID
* ServiceNow 客户端密码
* ServiceNow 访问 & 刷新令牌

当您从 Microsoft 365 安全中心或合规中心创建 ServiceNow 票证时，会将以下数据发送到 ServiceNow：

* 启动创建票证的用户 ID
* 任务名称
* 任务说明
* Priority
* 截止日期
* 建议源 (用户建议或 Microsoft 建议) 
*  (设备、数据、应用程序、标识、基础结构) 的建议类别

## <a name="connect-to-servicenow"></a>连接到 ServiceNow

请转到 [Microsoft 365 安全中心中的创建和跟踪 ServiceNow 票证](tickets-security-center.md) ，了解如何连接到 ServiceNow。 即将推出从 Microsoft 365 合规中心进行连接。

## <a name="troubleshooting"></a>故障排除

### <a name="you-receive-an-error-in-the-first-step-of-the-installation-checklist-oauth-creation"></a>您将在安装清单 (OAuth 创建的第一步中收到错误) 

**错误消息** ：由于表的跨范围访问策略，对作用域 "x_mioms_m365ticket" 中的 "oauth_entity" 执行的读取操作已被拒绝

应用程序假定 ServiceNow 实例上的任何管理员都可以创建和读取 OAuth 实体。 此错误可能是由您的 ServiceNow 实例中的自定义项导致的，用于限制可创建或读取 OAuth 实体的用户。

**ServiceNow 建议用户保留默认功能。**

将 "应用程序注册表" 表配置设置为默认值：

* Label = Application Registeries
* Name = oauth_entity
* 可从 = 所有应用程序范围访问
* 可以读取 = 复选框处于选中状态

### <a name="how-to-validate-the-oauth-entity-created-for-microsoft-365-security--compliance-connector"></a>如何验证为 Microsoft 365 安全 & 合规性连接器创建的 OAuth 实体

转到 "应用程序注册表" 表 ( **Menu > 系统 OAuth > 应用程序注册表** ) 在 ServiceNow 中。 使用您为其分配的名称查找您创建的 OAuth 实体。

### <a name="signing-in-as-the-integration-user"></a>以集成用户的登录

在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用在安装步骤中创建的集成用户登录和密码。 请勿使用你的个人凭据。

1. 转到 ServiceNow 中的 "授权" 页面。
2. 如果你使用个人凭据登录，请选择右上角的 " **不** 链接"。
3. 登录到 ServiceNow，将其作为您以前从安装清单创建的集成用户。  
4. 在 ServiceNow 页面中选择 " **允许** "，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。
5. 继续执行安装步骤。

### <a name="how-to-validate-the-integration-user-created-with-the-installation-checklist-for-microsoft-365-security--compliance-connector"></a>如何验证在安装清单中创建的集成用户是否符合 Microsoft 365 安全 & 合规性连接器

转到 "用户" 表 **(菜单中 > 用户管理 > 用户** ) 在 ServiceNow 中，并使用您为其分配的名称查找您创建的集成用户。

### <a name="your-company-has-single-sign-on-enabled-which-prevents-you-from-connecting-to-servicenow-through-the-microsoft-365-security-center"></a>你的公司启用了单一登录，这将阻止你通过 Microsoft 365 安全中心连接到 ServiceNow

如果您的公司启用了单一登录，但您收到错误或登录失败，请按照以下两个解决方案之一进行操作。

#### <a name="sign-in-to-servicenow-as-the-integration-user"></a>以集成用户的形式登录到 ServiceNow

1. 导航回 ServiceNow 中的 "授权" 页面。
2. 选择右上角的 " **不向您** 链接"。
3. 登录到 ServiceNow，将其作为您以前从安装清单创建的集成用户。  
4. 在 ServiceNow 页面中选择 " **允许** "，询问安全 + 合规性连接器是否可以连接到你的 ServiceNow 帐户。
5. 继续执行安装步骤。

#### <a name="create-a-security-admin-user"></a>创建安全管理员用户

1. 在 Azure Active Directory 中创建具有安全管理员权限的用户。 用户需要与您在安装清单中创建的集成用户具有相同的名称和电子邮件地址。 登录和连接完成后，可以删除安全管理员角色。
2. 作为此用户登录到 Microsoft 365 安全中心，并按照安装步骤进行操作。

### <a name="ip-filtering"></a>IP 筛选

如果已启用 IP 筛选，则可能需要显式允许 IP 地址。 有关如何允许 ServiceNow 中的 IP 范围的信息，请参阅 [IP 地址访问控制](https://docs.servicenow.com/bundle/orlando-platform-administration/page/administer/login/task/t_AccessControl.html) 。 有关允许的 IP 地址列表，请参阅 [AZURE IP 范围和服务标记-公共云](https://www.microsoft.com/en-us/download/details.aspx?id=56519) 。

### <a name="installation-is-complete-but-dont-see-tickets-and-cant-share"></a>安装已完成，但看不到票证且无法共享

如果已完成安装和设置步骤，但您在主页上看不到 ServiceNow 卡，并且无法从 Microsoft 安全分数中共享到 ServiceNow，请在处检查设置页面的状态 https://security.microsoft.com/ticketProvisioning 。 选择 " **授权** " 并返回到主页。 应显示卡片。

## <a name="resources"></a>资源

- [在安全中心中管理 ServiceNow 票证](tickets-security-center.md)
