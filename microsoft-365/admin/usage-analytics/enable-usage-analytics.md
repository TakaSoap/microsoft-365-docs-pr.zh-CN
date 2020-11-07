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
description: 了解如何使用 Power BI 中的 Microsoft 365 使用情况分析模板应用来开始收集租户的数据。
ms.openlocfilehash: 347256fa7acaae18cd31f0c8c6b7eca20ad2e9dd
ms.sourcegitcommit: 36795a6735cd3fc678c7d5db71ddc97fac3f6f8a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/06/2020
ms.locfileid: "48941327"
---
# <a name="enable-microsoft-365-usage-analytics"></a>启用 Microsoft 365 使用情况分析

::: moniker range="o365-21vianet"

> [!NOTE]
> 管理中心正在发生改变。 如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。

::: moniker-end

Microsoft 365 的使用情况分析尚不可用于 Microsoft 365 美国政府社区版。
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a>启用 Microsoft 365 使用情况分析的步骤

若要开始使用 Microsoft 365 使用情况分析，您必须先使数据在 Microsoft 365 管理中心中可用，然后在 Power BI 中启动模板应用。
  
### <a name="get-power-bi"></a>获取 Power BI

如果你尚不具有 Power BI，则可以 [注册 POWER Bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347)。 选择 " **免费试用** " 注册试用版，或 **立即购买** 以获取 Power BI Pro。
  
  
也可展开" **产品** "，购买某一版 Power BI。 

> [!NOTE]
> 您需要使用 Power BI Pro 许可证来安装、自定义和分发模板应用程序。 有关详细信息，请参阅 [先决条件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。

若要共享你的数据，你和与之共享数据的人员都需要使用 Power BI Pro 许可证，或者内容必须位于 [POWER bi premium service](https://docs.microsoft.com/power-bi/service-premium-what-is)的工作区中。 
  
### <a name="enable-the-template-app"></a>启用模板应用程序

若要启用模板应用程序，您必须是 **全局管理员** 。
  
有关详细信息，请参阅 [关于管理员角色](../add-users/about-admin-roles.md) 。 
  
1. 在管理中心，转到“ **报表** ”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。 
    
2. 在 " **使用情况** " 页上，找到 " **Microsoft 365 使用情况分析** 卡"，然后选择 " **开始** "。
    
3. 在打开的 "报告" 面板中，设置 "将 **数据提供给 Microsoft 365 使用情况分析以供 Power BI** **On** \> **保存** "。 
  
数据收集过程将在两到48小时内完成，具体取决于租户的大小。 " **转到 POWER BI** " 按钮将启用 (不再为灰色) 数据收集完成时。 
    
### <a name="start-the-template-app"></a>启动模板应用程序

若要启动模板应用程序，您必须是 **全局管理员** 、 **报告读者** 、 **Exchange 管理员** 、 **Skype for business 管理员** 或 **SharePoint 管理员** 。 
  
1. 复制租户 ID，然后选择 " **转到 POWER BI** "。
    
2.  转到 Power BI 后，请进行登录。 然后 **Select Apps** -> 从导航菜单中选择 "应用程序 **获取应用** 程序"。    
  
3. 在 " **应用程序** " 选项卡中，在 "搜索" 框中键入 microsoft 365，然后选择 " **microsoft 365 使用率分析** \> **现在获取它** "。

    [![选择 "立即获取"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)
    
4.  安装应用程序后。 选择图块以将其打开。

5.  选择 " **浏览应用程序** " 以查看包含示例数据的应用程序。 选择 " **连接** " 以将应用程序连接到您的组织的数据。

6.  选择 " **连接** "，在 " **连接到 Microsoft 365 使用情况分析** " 屏幕上，键入 (不带短划线的租户 ID) 您在步骤 (1) 中进行复制，然后选择 " **下一步** "。
    
7. 在下一个屏幕上，选择 " **OAuth2** " 作为 **身份验证方法** \> **登录** 。 如果选择任何其他身份验证方法，则与模板应用程序的连接将失败。
    
    ![选择 Microsoft 帐户作为身份验证方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. 模板应用程序实例化后，Microsoft 365 使用情况分析仪表板将在 Power BI 网页版中提供。 仪表板的初始加载将需要2到30分钟时间。
  
租户级别聚合将在所有报告中可用。 **用户级别的详细信息仅在选择 "日历" 月的第一天或第15天后才会变为可用** 。 这将影响 "用户活动" 下的所有报告。 有关如何查看和使用这些报告的提示，请参阅 [在 Microsoft 365 使用情况分析中导航和利用报告](navigate-and-utilize-reports.md) 。
    
## <a name="make-the-collected-data-anonymous"></a>使收集的数据匿名

若要使收集的所有报表数据匿名，你必须是全局管理员。 这将在报告中和模板应用程序中隐藏可识别信息，如用户、组和网站名称。
  
1. 在管理中心中，转到 " **设置** \> **组织设置** "，在 " **服务** " 选项卡下，选择 " **报告** "。
    
2. 选择 " **报告** "，然后选择 " **显示匿名标识符** "。 此设置既可应用于使用情况报告，也可应用于模板应用。
  
3. 选择“ **保存更改** ”。
