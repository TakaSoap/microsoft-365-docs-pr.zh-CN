---
title: 启用 Microsoft 365 使用情况分析
f1.keywords:
- CSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom:
- AdminSurgePortfolio
- AdminTemplateSet
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: 了解如何使用 Power BI 中的"使用率分析"Microsoft 365开始收集租户Power BI。
ms.openlocfilehash: 836ff4cea69f0feef2c94980a48c9202ce57dd6891ef4a7dd76cea26fc3d2cc4
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53901155"
---
# <a name="enable-microsoft-365-usage-analytics"></a>启用 Microsoft 365 使用情况分析

Microsoft 365使用情况分析尚不可用于美国政府Microsoft 365 Community。

## <a name="before-you-begin"></a>准备工作

若要开始使用Microsoft 365分析，你必须先在应用中提供Microsoft 365 管理中心，然后在 Power BI 中启动模板应用。

## <a name="get-power-bi"></a>获取 Power BI

如果尚未注册Power BI，可以[注册Power BI Pro。](https://go.microsoft.com/fwlink/p/?linkid=845347) 选择 **"免费试用**"以注册试用版，**或选择"** 立即购买"Power BI Pro。


也可展开" **产品**"，购买某一版 Power BI。

> [!NOTE]
> 你需要一个Power BI Pro许可证来安装、自定义和分发模板应用。 有关详细信息，请参阅 [先决条件](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。

若要共享数据，你和共享数据的人都需要 Power BI Pro 许可证，或者内容需要Power BI[工作区中](/power-bi/service-premium-what-is)。

## <a name="enable-the-template-app"></a>启用模板应用

若要启用模板应用，你必须是全局 **管理员**。

有关详细信息 [，请参阅有关](../add-users/about-admin-roles.md) 管理员角色的信息。

1. 在管理中心，转到 \> **"设置"组织设置** \> **""服务"** 选项卡。

2. 在"**服务"选项卡** 上，选择"报告 **"。**

3. 在打开的"报告"面板上，将"报告数据可供Microsoft 365 **使用情况** 分析 **"Power BI"保存** \> **"。**

数据收集过程将在 2 到 48 小时内完成，具体取决于租户的大小。 数据收集 **完成后Power BI"** 转到 ("按钮) 不再灰显。

## <a name="start-the-template-app"></a>启动模板应用

若要启动模板应用，你必须是全局管理员、报告读取者、Exchange管理员、Skype for Business **管理员** SharePoint **管理员**。

1. 复制租户 ID，然后选择"**转到Power BI"。**

2. 转到 Power BI 后，请进行登录。 然后 **从** -> **导航菜单中选择"应用**""获取应用"。

3. 在"**应用"** 选项卡Microsoft 365搜索框中键入"应用"，然后选择"Microsoft 365 **使用情况分析** \> **""现在获取它"。**

    [![选择"现在获取"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)

4. 安装应用后。 选择磁贴将其打开。

5. 选择 **"浏览** 应用"以查看包含示例数据的应用。 选择 **连接** 以将应用连接到组织的数据。

6. 选择 **"连接"，** 在"连接 到 **Microsoft 365** 使用情况分析"屏幕上，键入在步骤 (1) 中复制的租户 ID (不带短划线) ) ，然后选择"下一步"。

7. 下一个屏幕上，选择 **"OAuth2"****作为"身份验证方法** \> **""登录"。** 如果选择任何其他身份验证方法，则与模板应用的连接将失败。

    ![选择 Microsoft 帐户作为身份验证方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. 实例化模板应用后，Microsoft 365使用情况分析仪表板将在Power BI中可用。 仪表板的初始加载需要 2 到 30 分钟。

选择加入后，租户级别聚合将在所有报告中可用。 **用户级别的详细信息将仅在** 选择加入后的下一日历月 5 日左右可用。 这将影响"用户活动"下的所有 (请参阅导航和利用[Microsoft 365 使用情况](navigate-and-utilize-reports.md)分析中的报告，获取有关如何查看和使用这些报告的) 。

## <a name="make-the-collected-data-anonymous"></a>使收集的数据匿名

若要使收集的所有报表数据匿名，你必须是全局管理员。 这将在报告和模板应用中隐藏可识别信息，如用户、组和网站名称。

1. 在管理中心中，转到"设置 \> **组织设置"，在"服务"选项卡** 下，选择"报告 **"。**

2. 选择 **"报告**"，然后选择"**显示匿名标识符"。** 此设置既适用于使用情况报告，也适用于模板应用。

3. 选择“**保存更改**”。

## <a name="related-content"></a>相关内容

[关于使用情况分析](usage-analytics.md) (文章) \
[获取使用情况分析的最新版本](get-the-latest-version-of-usage-analytics.md) (文章) \
[导航和利用 Microsoft 365 使用情况分析 (](navigate-and-utilize-reports.md)中的) 