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
ms.openlocfilehash: 20228b0e2070065834ce203e22af619480311367
ms.sourcegitcommit: 1b83b6bcacb997324bc4be355deba6daf319591d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/28/2020
ms.locfileid: "46502945"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="b4573-103">启用 Microsoft 365 使用情况分析</span><span class="sxs-lookup"><span data-stu-id="b4573-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="b4573-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="b4573-104">The admin center is changing.</span></span> <span data-ttu-id="b4573-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="b4573-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="b4573-106">Microsoft 365 的使用情况分析尚不可用于 Microsoft 365 美国政府社区版。</span><span class="sxs-lookup"><span data-stu-id="b4573-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="b4573-107">启用 Microsoft 365 使用情况分析的步骤</span><span class="sxs-lookup"><span data-stu-id="b4573-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="b4573-108">若要开始使用 Microsoft 365 使用情况分析，您必须先使数据在 Microsoft 365 管理中心中可用，然后在 Power BI 中启动模板应用。</span><span class="sxs-lookup"><span data-stu-id="b4573-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="b4573-109">获取 Power BI</span><span class="sxs-lookup"><span data-stu-id="b4573-109">Get Power BI</span></span>

<span data-ttu-id="b4573-110">如果你尚不具有 Power BI，则可以[注册 POWER Bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="b4573-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="b4573-111">选择 "**免费试用**" 注册试用版，或**立即购买**以获取 Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="b4573-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="b4573-112">也可展开" **产品**"，购买某一版 Power BI。</span><span class="sxs-lookup"><span data-stu-id="b4573-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="b4573-113">您需要使用 Power BI Pro 许可证来安装、自定义和分发模板应用程序。</span><span class="sxs-lookup"><span data-stu-id="b4573-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="b4573-114">有关详细信息，请参阅[先决条件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="b4573-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="b4573-115">你需要使用 Power BI Pro 许可证来共享你的内容，以及你将其与之共享的人员，或者内容需要位于[高级容量](https://docs.microsoft.com/power-bi/service-premium-what-is)的工作区中。</span><span class="sxs-lookup"><span data-stu-id="b4573-115">You need a Power BI Pro license to share your content, and the people you share it with do too, or the content needs to be in a workspace in a [Premium capacity](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="b4573-116">启用模板应用程序</span><span class="sxs-lookup"><span data-stu-id="b4573-116">Enable the template app</span></span>

<span data-ttu-id="b4573-117">若要启用模板应用程序，您必须是**全局管理员**、**报告读者**、 **Exchange 管理员**、 **Skype for business 管理员**或**SharePoint 管理员**。</span><span class="sxs-lookup"><span data-stu-id="b4573-117">To enable the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
<span data-ttu-id="b4573-118">有关详细信息，请参阅[关于管理员角色](../add-users/about-admin-roles.md)。</span><span class="sxs-lookup"><span data-stu-id="b4573-118">See [About admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="b4573-119">在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。</span><span class="sxs-lookup"><span data-stu-id="b4573-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="b4573-120">在 "**使用情况**" 页上，找到 " **Microsoft 365 使用情况分析**卡"，然后选择 "**开始**"。</span><span class="sxs-lookup"><span data-stu-id="b4573-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="b4573-121">在打开的 "报告" 面板中，设置 "将**数据提供给 Microsoft 365 使用情况分析以供 Power BI** **On** \> **保存**"。</span><span class="sxs-lookup"><span data-stu-id="b4573-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="b4573-122">这将启动数据收集过程，并将在2到48小时内完成，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="b4573-122">This initiates the data collection process and will complete in 2 to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="b4573-123">数据收集完成后，"**转到 POWER BI** " 按钮将处于启用状态（不再为灰色）。</span><span class="sxs-lookup"><span data-stu-id="b4573-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="initiate-the-template-app"></a><span data-ttu-id="b4573-124">启动模板应用程序</span><span class="sxs-lookup"><span data-stu-id="b4573-124">Initiate the template app</span></span>

<span data-ttu-id="b4573-125">若要启动模板应用程序，您必须是**全局管理员**、**报告读者**、 **Exchange 管理员**、 **Skype for business 管理员**或**SharePoint 管理员**。</span><span class="sxs-lookup"><span data-stu-id="b4573-125">To initiate the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="b4573-126">复制租户 Id，然后选择 "**转到 POWER BI**"。</span><span class="sxs-lookup"><span data-stu-id="b4573-126">Copy the tenant Id and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="b4573-127">转到 Power BI 后，请进行登录。</span><span class="sxs-lookup"><span data-stu-id="b4573-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="b4573-128">选择 "应用-从导航菜单 >获取应用程序"。</span><span class="sxs-lookup"><span data-stu-id="b4573-128">Select Apps->Get apps from the navigation menu.</span></span>    
  
3. <span data-ttu-id="b4573-129">在 "**应用程序**" 选项卡中，在 "搜索" 框中键入 microsoft 365，然后选择 " **microsoft 365 使用率分析** \> **现在获取它**"。</span><span class="sxs-lookup"><span data-stu-id="b4573-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="b4573-130">[![选择 "立即获取"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="b4573-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="b4573-131">安装应用程序后。</span><span class="sxs-lookup"><span data-stu-id="b4573-131">Once the app is installed.</span></span> <span data-ttu-id="b4573-132">单击磁贴以打开它。</span><span class="sxs-lookup"><span data-stu-id="b4573-132">Click on the tile to open it.</span></span>

5.  <span data-ttu-id="b4573-133">单击 "**浏览应用**程序" 以查看包含示例数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="b4573-133">Click **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="b4573-134">单击 "**连接**" 将应用程序连接到您的组织的数据。</span><span class="sxs-lookup"><span data-stu-id="b4573-134">Click **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="b4573-135">单击 "**连接**" 后，在 "**连接到 Microsoft 365 使用情况分析**" 屏幕上，键入在步骤（1）中复制的租户 Id （不带短划线），然后选择 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="b4573-135">After clicking **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, type in the tenant Id (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="b4573-136">在下一个屏幕上，选择 " **oAuth2** " 作为**身份验证方法** \> **登录**。</span><span class="sxs-lookup"><span data-stu-id="b4573-136">On the next screen, select **oAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="b4573-137">如果选择任何其他身份验证方法，则与模板应用程序的连接将失败。</span><span class="sxs-lookup"><span data-stu-id="b4573-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![Choose oAuth2 as authentication method](../../media/ac85a360-c278-4c60-8aa3-68f4828f1d96.png)
  
8. <span data-ttu-id="b4573-139">模板应用程序实例化后，Microsoft 365 使用情况分析仪表板将在 Power BI 网页版中提供。</span><span class="sxs-lookup"><span data-stu-id="b4573-139">Once the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="b4573-140">仪表板的初始加载将需要2到30分钟时间。</span><span class="sxs-lookup"><span data-stu-id="b4573-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="b4573-141">租户级别聚合将在所有报告中可用。</span><span class="sxs-lookup"><span data-stu-id="b4573-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="b4573-142">**用户级别的详细信息仅在选择 "日历" 月的第一天或第15天后才会变为可用**。</span><span class="sxs-lookup"><span data-stu-id="b4573-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="b4573-143">这将影响 "用户活动" 下的所有报告（有关如何查看和使用这些报告的提示，请参阅[在 Microsoft 365 使用情况分析中导航和利用报告](navigate-and-utilize-reports.md)）。</span><span class="sxs-lookup"><span data-stu-id="b4573-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="b4573-144">使收集的数据匿名</span><span class="sxs-lookup"><span data-stu-id="b4573-144">Make the collected data anonymous</span></span>

<span data-ttu-id="b4573-145">若要使收集的所有报表数据匿名，你必须是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="b4573-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="b4573-146">这将在报告中和模板应用程序中隐藏可识别信息，如用户、组和网站名称。</span><span class="sxs-lookup"><span data-stu-id="b4573-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="b4573-147">在管理中心中，转到 "**设置** \> **组织设置**"，在 "**服务**" 选项卡下，选择 "**报告**"。</span><span class="sxs-lookup"><span data-stu-id="b4573-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="b4573-148">选择 "**报告**"，然后选择 "**显示匿名标识符**"。</span><span class="sxs-lookup"><span data-stu-id="b4573-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="b4573-149">此设置既可应用于使用情况报告，也可应用于模板应用。</span><span class="sxs-lookup"><span data-stu-id="b4573-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="b4573-150">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="b4573-150">Select **Save changes**.</span></span>
