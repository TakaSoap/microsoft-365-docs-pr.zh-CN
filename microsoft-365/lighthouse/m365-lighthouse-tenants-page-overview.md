---
title: Microsoft 365 Lighthouse租户页概述
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
description: 对于使用Microsoft 365 Lighthouse (MSP) 托管服务提供商，请了解“租户”页。
ms.openlocfilehash: 44111d62a9b8df9bf3b05ddbaa9cb4f3937159a4
ms.sourcegitcommit: 195e4734d9a6e8e72bd355ee9f8bca1f18577615
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/13/2022
ms.locfileid: "64823512"
---
# <a name="microsoft-365-lighthouse-tenants-page-overview"></a>Microsoft 365 Lighthouse租户页概述

Microsoft 365 Lighthouse允许你通过在左侧导航窗格中选择 **租户** 来打开“租户”页来管理租户帐户。 “租户”页包含所有租户的列表。 可以选择租户以查看详细信息，包括联系人详细信息和部署状态。

“租户”页还包括以下选项：

- **出口：** 选择将租户数据导出到Excel逗号分隔值 (.csv) 文件。
- **管理标记：** 选择以添加、编辑或删除标记。
- **分配标记：** 选择此选项可将标记分配给租户。
- **搜索：** 输入关键字以快速找到列表中的特定租户。

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-page-overview.png" alt-text="“租户”页的屏幕截图。":::

## <a name="tenant-list"></a>租户列表

租户列表提供与之签订合同的不同租户（包括租户 Lighthouse 载入状态）的见解。 租户列表还允许你标记租户以在整个 Lighthouse 中提供不同的筛选器，并向下钻取以详细了解给定租户及其部署计划的状态。

租户满足 [Lighthouse 载入要求](m365-lighthouse-requirements.md)后，其状态将在租户列表中显示为 **“活动** ”。

租户列表允许你：

- 按活动、非活动和不合格自动对租户进行排序。
- 导出租户列表。
- 分配和管理标记。
- 按名称搜索租户。
- 按状态、委派的管理权限 (DAP) 和标记筛选租户。

若要停用租户或查看和管理标记，请选择三个点 (租户名称旁边) 的更多操作。 可以通过选择租户名称或选择分配给租户的标记之一来查看单个租户。

## <a name="tenant-status"></a>租户状态

下表显示了不同的状态及其含义。<br><br>

| 状态                                   | 说明                                                                                             |
|------------------------------------------|---------------------------------------------------------------------------------------------------------|
| 活动                                   | 租户载入和数据流已启动。                                                           |
| 无效                                 | 租户是应 MSP 的要求卸载的，并且不再在 Lighthouse 中进行管理。           |
| 正在处理中                               | 已发现但未完全载入的租户。                                                              |
| 不符合条件 - 未设置 DAP 或 GDAP    | 合作伙伴必须已委托 (DAP) 或粒度委派 (GDAP) 与租户一起设置的管理员权限。 |
| 不符合条件 - 缺少所需的许可证 | 租户没有所需的许可证。                                                               |
| 不符合条件 - 超出用户计数         | 租户的用户数超过允许的数。                                                                     |
| 不符合条件 - 异地检查失败            | 合作伙伴和客户必须驻留在同一地理位置。                                       |

停用租户后，在停用过程完成之前，无法对租户采取措施。 停用可能需要长达 48 小时才能完成。 如果决定重新激活租户，数据可能需要长达 48 小时才能重新出现。

## <a name="tenant-tags"></a>租户标记

若要帮助组织租户并轻松筛选现有视图，可以创建标记并向租户分配标记。 若要了解详细信息，请参阅 [“管理租户”列表](m365-lighthouse-manage-tenant-list.md)。

> [!NOTE]
> 可以在所有租户中创建最多 30 个标记。

## <a name="tenant-details-page"></a>租户详细信息页

若要查看详细的租户信息，请从租户列表中选择租户。 租户详细信息页包含联系人信息和部署计划状态。

:::image type="content" source="../media/m365-lighthouse-tenants-page-overview/tenant-details-page.png" alt-text="“租户详细信息”页的屏幕截图。":::

### <a name="overview-tab"></a>“概述”选项卡

在“概述”选项卡上，可以查看租户概述、联系信息和Microsoft 365服务使用情况。

#### <a name="tenant-overview-card"></a>租户概述卡

租户概述卡从其Microsoft 365帐户提供有关租户的信息。<br><br>

| 租户信息    | 说明|
|-----------------------|------------------|
| 总部    | 租户所在的位置。|
| 行业    |组织的行业。|
| 网站    |组织的网站。 如果未提供任何数据，则可以编辑此字段。|
| 客户域    |组织的域。|
| 用户总数    |在租户中分配的用户数。 可以选择此号码以打开该租户的“用户”页。|
| 设备总数|租户中注册的设备数。 可以选择此数字以打开该租户的“设备”页。|

#### <a name="contacts-card"></a>联系人卡片

借助联系人卡片，可在所管理的租户中输入关键联系人的信息，例如：

- 名称
- 标题
- Phone
- 电子邮件
- 注释

“备注”部分是一个文本字段，可用于记录租户的关键信息，例如参与首选项、位置、时区及其在组织中的角色的详细信息。

若要编辑详细信息或删除现有联系人，请从列表中选择联系人姓名。 在 **“编辑联系人** ”窗格中，编辑或删除联系人。 若要添加另一个联系人，请选择 **“+添加联系人**”。

#### <a name="microsoft-365-usage-card"></a>Microsoft 365使用卡

Lighthouse 提供Microsoft 365服务使用情况的见解，包括租户中有多少用户获得许可并主动使用每个服务。 Active 指示在过去 28 天内至少登录服务一次的用户或设备的数量。 更改指示自上个月以来活动用户和设备的变化。

Microsoft 365用法卡包含两个部分：

- **已启用Microsoft 365 Lighthouse的服务：** 可在 Lighthouse 门户中管理的服务。
- **其他Microsoft 365服务：** Microsoft 365套件中包含但目前无法在Microsoft 365 Lighthouse门户中管理的服务。

### <a name="deployment-plans-tab"></a>“部署计划”选项卡

“部署计划”选项卡提供租户部署计划的状态。 列表中的部署步骤基于应用于租户的基线。 若要查看部署步骤详细信息，请从列表中选择部署步骤。

“部署计划”选项卡还包括以下选项：

- **出口：** 选择此选项可将部署步骤数据导出到Excel逗号分隔值 (.csv) 文件。
- **刷新：** 选择此选项可检索最新的部署步骤数据。
- **搜索：** 输入关键字以快速找到列表中的特定部署步骤。

## <a name="related-content"></a>相关内容

[Microsoft 365 Lighthouse (](m365-lighthouse-requirements.md)文章) \ 的要求
[Microsoft 365 Lighthouse常见问题解](m365-lighthouse-faq.yml)答 (文章) \
[管理租户列表](m365-lighthouse-manage-tenant-list.md) (文章) \
使用[基线部署标准租户配置的概述](m365-lighthouse-deploy-standard-tenant-configurations-overview.md) (文章) \
[部署Microsoft 365 Lighthouse基线](m365-lighthouse-deploy-baselines.md) (文章) 
