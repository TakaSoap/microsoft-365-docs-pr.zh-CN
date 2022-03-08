---
title: Microsoft 365 Lighthouse租户页面概述
f1.keywords: NOCSH
ms.author: sharik
author: SKjerland
manager: scotv
audience: Admin
ms.topic: article
ms.prod: microsoft-365-lighthouse
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- M365-Lighthouse
search.appverid: MET150
description: 对于托管服务提供商 (使用) 托管服务提供商Microsoft 365 Lighthouse，请了解"租户"页面。
ms.openlocfilehash: 23f151664455c35bb2fcc191d774ead00927e830
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63329987"
---
# <a name="microsoft-365-lighthouse-tenants-page-overview"></a>Microsoft 365 Lighthouse租户页面概述

Microsoft 365 Lighthouse通过选择左侧导航窗格中的"租户"打开"租户"页面来管理租户帐户。 "租户"页包含所有租户的列表。 可以选择租户以查看详细信息，包括联系人详细信息和部署状态。

"租户"页还包括以下选项：

- **导出：** 选择将租户数据导出到Excel逗号分隔值 (.csv) 文件。
- **管理标记：** 选择添加、编辑或删除标记。
- **分配标记：** 选择以向租户分配标记。
- **搜索：** 输入关键字以快速找到列表中的特定租户。

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-page-overview.png" alt-text="&quot;租户&quot;页面的屏幕截图。":::

## <a name="tenant-list"></a>租户列表

租户列表提供你与不同租户签订合同的见解，包括租户 Lighthouse 载入状态。 租户列表还允许你标记租户以在整个 Lighthouse 中提供不同的筛选器，并向下钻取以了解有关给定租户及其部署计划状态的信息。

在租户满足 [Lighthouse](m365-lighthouse-requirements.md) 载入要求后，其状态将在租户 **列表中** 显示为"活动"。

租户列表允许你：

- 按活动、非活动或不符合条件的方式自动对租户进行排序。
- 导出租户列表。
- 分配和管理标记。
- 按名称搜索租户。
- 按状态、委派的管理权限、DAP (和) 筛选租户。

若要停用租户或查看和管理标记，请选择三个点 (租户) 旁边的更多操作。 可以通过选择租户名称或选择分配给租户的标记之一来查看各个租户。

## <a name="tenant-status"></a>租户状态

下表显示了不同的状态及其含义。<br><br>

| 状态                                   | 说明                                                                                             |
|------------------------------------------|---------------------------------------------------------------------------------------------------------|
| 活动                                   | 租户载入和数据流已启动。                                                           |
| 非活动                                 | 应 MSP 的请求，租户已离开，不再在 Lighthouse 中进行管理。           |
| 进程内                               | 租户已发现，但尚未完全载入。                                                              |
| 不符合 - 未设置 DAP 或 GDAP    | 合作伙伴必须拥有委派 (DAP) 或精细委派 (GDAP) 租户设置的管理员权限。 |
| 不符合资格 - 缺少所需的许可证 | 租户没有所需的许可证。                                                               |
| 不符合标准 - 已超出用户计数         | 租户具有的用户数多于允许的用户数。                                                                     |
| 不符合资格 - 地理位置检查失败            | 合作伙伴和客户必须位于同一地理位置。                                       |

停用租户后，在停用过程完成之前，无法对租户采取措施。 停用可能需要 48 小时才能完成。 如果决定重新激活租户，可能需要 48 小时才能重新显示数据。

## <a name="tenant-tags"></a>租户标记

为了帮助组织租户并轻松筛选现有视图，你可以创建标记并将其分配给租户。 若要了解更多信息，请参阅 [管理租户列表](m365-lighthouse-manage-tenant-list.md)。

> [!NOTE]
> 你可在所有租户中最多创建 30 个标记。

## <a name="tenant-details-page"></a>租户详细信息页面

若要查看详细的租户信息，请从租户列表中选择一个租户。 租户详细信息页面包含联系人信息和部署计划状态。

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-details-page.png" alt-text="&quot;租户详细信息&quot;页面的屏幕截图。":::

### <a name="overview-tab"></a>"概述"选项卡

在"概述"选项卡上，可以查看租户概述、联系人信息和Microsoft 365使用情况。

#### <a name="tenant-overview-card"></a>租户概述卡片

租户概述卡片从租户的租户帐户Microsoft 365相关信息。<br><br>

| 租户信息    | 说明|
|-----------------------|------------------|
| 总部    | 租户所在的位置。|
| 行业    |组织的行业。|
| 网站    |组织的网站。 如果未提供数据，可以编辑此字段。|
| 客户域    |组织的域。|
| 用户总数    |租户中分配的用户数。 您可以选择此号码打开该租户的"用户"页面。|
| 设备总数|租户中注册的设备数。 您可以选择此号码打开该租户的"设备"页面。|

#### <a name="contacts-card"></a>联系人卡片

通过联系人卡片，你可以输入你管理的租户内的关键联系人的信息，例如：

- 名称
- 标题
- Phone
- 电子邮件
- 注释

"备注"部分是一个文本字段，可用于记录租户的关键信息，例如服务活动首选项、位置、时区和有关他们在组织中的角色的详细信息。

若要编辑详细信息或删除现有联系人，请从列表中选择联系人姓名。 在" **编辑联系人"** 窗格中，编辑或删除联系人。 若要添加其他联系人，请选择 **"+添加联系人"**。

#### <a name="microsoft-365-usage-card"></a>Microsoft 365使用卡

Lighthouse 提供对 Microsoft 365服务使用情况的见解，包括租户中有多少用户获得许可并主动使用每项服务。 Active 指示在过去 28 天内至少登录服务一次的用户或设备数。 更改指示自上个月以来活动用户和设备中的更改。

The Microsoft 365 Usage card contains two sections：

- **Microsoft 365 Lighthouse启用的服务：** 可以在 Lighthouse 门户内管理的服务。
- **其他Microsoft 365服务**：包含在 Microsoft 365 套件中但当前无法Microsoft 365 Lighthouse管理的服务。

### <a name="deployment-plans-tab"></a>"部署计划"选项卡

"部署计划"选项卡提供租户部署计划的状态。 列表中的部署步骤基于应用于租户的基线。 若要查看部署步骤详细信息，请从列表中选择部署步骤。

"部署计划"选项卡还包括以下选项：

- **导出：** 选择将部署步骤数据导出到Excel逗号分隔值 (.csv) 文件中。
- **刷新：** 选择以检索最新的部署步骤数据。
- **搜索：** 输入关键字以快速找到列表中的特定部署步骤。

## <a name="related-content"></a>相关内容

[本文Microsoft 365 Lighthouse (](m365-lighthouse-requirements.md)的要求) \
[Microsoft 365 Lighthouse常见问题](m365-lighthouse-faq.yml) (文章) \
[管理租户列表 (](m365-lighthouse-manage-tenant-list.md) 文章) \
[使用基线部署标准租户配置的](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) 概述 (文章) \
[Microsoft 365 Lighthouse文章 (](m365-lighthouse-deploy-baselines.md)部署) 
