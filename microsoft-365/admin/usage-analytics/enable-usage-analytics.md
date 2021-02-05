---
title: 启用 Microsoft 365 使用情况分析
f1.keywords:
- CSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
- Adm_TOC
ms.custom: AdminSurgePortfolio
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9db96e9f-a622-4d5d-b134-09dcace55b6a
description: 了解如何使用 Power BI 中的 Microsoft 365 使用情况分析模板应用开始收集租户数据。
ms.openlocfilehash: 98ae107b6777ac97d0be3b37847117c6e20be63d
ms.sourcegitcommit: 0d709e9ab0d8d56c5fc11a921298f82e40e122c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/05/2021
ms.locfileid: "50114233"
---
# <a name="enable-microsoft-365-usage-analytics"></a>启用 Microsoft 365 使用情况分析

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。

::: moniker-end

Microsoft 365 使用情况分析尚不可用于 Microsoft 365 美国政府社区版。
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>启用 Microsoft 365 使用情况分析的步骤

若要开始使用 Microsoft 365 使用情况分析，必须先在 Microsoft 365 管理中心提供数据，然后在 Power BI 中启动模板应用。
  
### <a name="get-power-bi"></a>获取 Power BI

如果还没有 Power BI，可以注册 Power [BI Pro。](https://go.microsoft.com/fwlink/p/?linkid=845347) 选择 **"免费试用** 以注册试用版" **或"立即** 购买"获取 Power BI Pro。
  
  
也可展开" **产品**"，购买某一版 Power BI。 

> [!NOTE]
> 你需要 Power BI Pro 许可证才能安装、自定义和分发模板应用。 有关详细信息，[请参阅先决条件。](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)

要共享你的数据，你和你共享数据的人、需要 Power BI Pro 许可证，或者内容需要在 Power BI Premium 服务中的工作区 [中](https://docs.microsoft.com/power-bi/service-premium-what-is)。 
  
### <a name="enable-the-template-app"></a>启用模板应用

若要启用模板应用，你必须是全局 **管理员**。
  
有关详细信息 [，请参阅管理员](../add-users/about-admin-roles.md) 角色。 
  
1. 在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
    
2. 在"**使用情况**"页上，找到 **Microsoft 365 使用情况分析** 卡，然后选择"**开始使用"。**
    
3. 在打开的"报告"面板上，将 Power BI 的 **Microsoft 365** 使用情况分析数据设置为 **"保存** \> **"。** 
  
数据收集过程将在两到 48 小时内完成，具体取决于租户的大小。 数据收集 **完成后，"转到 Power BI"** 按钮 (，) 不再灰显。 
    
### <a name="start-the-template-app"></a>启动模板应用

若要启动模板应用程序，你必须是全局管理员、报告读取者 **、Exchange 管理员****、Skype for Business 管理员** 或 **SharePoint 管理员**。  
  
1. 复制租户 ID，然后选择 **"转到 Power BI"。**
    
2.  转到 Power BI 后，请进行登录。 然后 **从** -> **导航菜单中选择"** 应用获取应用"。    
  
3. 在 **"应用"** 选项卡中，在搜索框中键入 Microsoft 365，然后选择 **Microsoft 365 使用情况** 分析 \> **"现在获取它"。**

    [![选择"现在获取"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  安装应用后。 选择磁贴将其打开。

5.  选择 **"浏览** "应用以查看包含示例数据的应用。 选择 **"** 连接"将应用连接到组织的数据。

6.  Choose **Connect**， on the **Connect to Microsoft 365 usage analytics** screen， then type in the tenant ID (without dashes) you copied in step (1) ， and select **Next**.
    
7. 下一个屏幕上，选择 **OAuth2** 作为 **身份验证方法** \> **登录**。 如果选择任何其他身份验证方法，则与模板应用的连接将失败。
    
    ![选择 Microsoft 帐户作为身份验证方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. 实例化模板应用后，Microsoft 365 使用情况分析仪表板将在 Power BI 网页版中提供。 仪表板的初始加载需要 2 到 30 分钟。
  
选择加入后，租户级别聚合将在所有报告中可用。 **用户级别的详细信息仅在** 选择加入后的下一个日历月的第 5 日左右可用。 这将影响"用户活动" (查看"导航"，并利用 [Microsoft 365](navigate-and-utilize-reports.md) 使用情况分析中的报告，获取有关如何查看和使用这些报告的) 。
    
## <a name="make-the-collected-data-anonymous"></a>使收集的数据匿名

若要使收集的所有报表数据匿名，你必须是全局管理员。 这将在报表和模板应用中隐藏可识别的信息，如用户、组和网站名称。
  
1. 在管理中心，转到 **"设置** \> **组织** 设置"，在"服务"选项卡下，选择"**报告"。**
    
2. 选择 **"** 报告"，然后选择 **"显示匿名标识符"。** 此设置同时应用于使用情况报表和模板应用。
  
3. 选择“**保存更改**”。
