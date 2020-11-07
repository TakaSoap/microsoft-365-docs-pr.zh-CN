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
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="c5f86-103">启用 Microsoft 365 使用情况分析</span><span class="sxs-lookup"><span data-stu-id="c5f86-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="c5f86-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="c5f86-104">The admin center is changing.</span></span> <span data-ttu-id="c5f86-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet)。</span><span class="sxs-lookup"><span data-stu-id="c5f86-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet).</span></span>

::: moniker-end

<span data-ttu-id="c5f86-106">Microsoft 365 的使用情况分析尚不可用于 Microsoft 365 美国政府社区版。</span><span class="sxs-lookup"><span data-stu-id="c5f86-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="c5f86-107">启用 Microsoft 365 使用情况分析的步骤</span><span class="sxs-lookup"><span data-stu-id="c5f86-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="c5f86-108">若要开始使用 Microsoft 365 使用情况分析，您必须先使数据在 Microsoft 365 管理中心中可用，然后在 Power BI 中启动模板应用。</span><span class="sxs-lookup"><span data-stu-id="c5f86-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="c5f86-109">获取 Power BI</span><span class="sxs-lookup"><span data-stu-id="c5f86-109">Get Power BI</span></span>

<span data-ttu-id="c5f86-110">如果你尚不具有 Power BI，则可以 [注册 POWER Bi Pro](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="c5f86-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="c5f86-111">选择 " **免费试用** " 注册试用版，或 **立即购买** 以获取 Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="c5f86-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="c5f86-112">也可展开" **产品** "，购买某一版 Power BI。</span><span class="sxs-lookup"><span data-stu-id="c5f86-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="c5f86-113">您需要使用 Power BI Pro 许可证来安装、自定义和分发模板应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5f86-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="c5f86-114">有关详细信息，请参阅 [先决条件](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="c5f86-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="c5f86-115">若要共享你的数据，你和与之共享数据的人员都需要使用 Power BI Pro 许可证，或者内容必须位于 [POWER bi premium service](https://docs.microsoft.com/power-bi/service-premium-what-is)的工作区中。</span><span class="sxs-lookup"><span data-stu-id="c5f86-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="c5f86-116">启用模板应用程序</span><span class="sxs-lookup"><span data-stu-id="c5f86-116">Enable the template app</span></span>

<span data-ttu-id="c5f86-117">若要启用模板应用程序，您必须是 **全局管理员** 。</span><span class="sxs-lookup"><span data-stu-id="c5f86-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="c5f86-118">有关详细信息，请参阅 [关于管理员角色](../add-users/about-admin-roles.md) 。</span><span class="sxs-lookup"><span data-stu-id="c5f86-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="c5f86-119">在管理中心，转到“ **报表** ”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。</span><span class="sxs-lookup"><span data-stu-id="c5f86-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="c5f86-120">在 " **使用情况** " 页上，找到 " **Microsoft 365 使用情况分析** 卡"，然后选择 " **开始** "。</span><span class="sxs-lookup"><span data-stu-id="c5f86-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="c5f86-121">在打开的 "报告" 面板中，设置 "将 **数据提供给 Microsoft 365 使用情况分析以供 Power BI** **On** \> **保存** "。</span><span class="sxs-lookup"><span data-stu-id="c5f86-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="c5f86-122">数据收集过程将在两到48小时内完成，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="c5f86-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="c5f86-123">" **转到 POWER BI** " 按钮将启用 (不再为灰色) 数据收集完成时。</span><span class="sxs-lookup"><span data-stu-id="c5f86-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="c5f86-124">启动模板应用程序</span><span class="sxs-lookup"><span data-stu-id="c5f86-124">Start the template app</span></span>

<span data-ttu-id="c5f86-125">若要启动模板应用程序，您必须是 **全局管理员** 、 **报告读者** 、 **Exchange 管理员** 、 **Skype for business 管理员** 或 **SharePoint 管理员** 。</span><span class="sxs-lookup"><span data-stu-id="c5f86-125">To start the template app, you have to be either a **global administrator** , **report reader** , **Exchange administrator** , **Skype for Business administrator** , or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="c5f86-126">复制租户 ID，然后选择 " **转到 POWER BI** "。</span><span class="sxs-lookup"><span data-stu-id="c5f86-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="c5f86-127">转到 Power BI 后，请进行登录。</span><span class="sxs-lookup"><span data-stu-id="c5f86-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="c5f86-128">然后 **Select Apps** -> 从导航菜单中选择 "应用程序 **获取应用** 程序"。</span><span class="sxs-lookup"><span data-stu-id="c5f86-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="c5f86-129">在 " **应用程序** " 选项卡中，在 "搜索" 框中键入 microsoft 365，然后选择 " **microsoft 365 使用率分析** \> **现在获取它** "。</span><span class="sxs-lookup"><span data-stu-id="c5f86-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="c5f86-130">[![选择 "立即获取"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="c5f86-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="c5f86-131">安装应用程序后。</span><span class="sxs-lookup"><span data-stu-id="c5f86-131">Once the app is installed.</span></span> <span data-ttu-id="c5f86-132">选择图块以将其打开。</span><span class="sxs-lookup"><span data-stu-id="c5f86-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="c5f86-133">选择 " **浏览应用程序** " 以查看包含示例数据的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c5f86-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="c5f86-134">选择 " **连接** " 以将应用程序连接到您的组织的数据。</span><span class="sxs-lookup"><span data-stu-id="c5f86-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="c5f86-135">选择 " **连接** "，在 " **连接到 Microsoft 365 使用情况分析** " 屏幕上，键入 (不带短划线的租户 ID) 您在步骤 (1) 中进行复制，然后选择 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="c5f86-135">Choose **Connect** , on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="c5f86-136">在下一个屏幕上，选择 " **OAuth2** " 作为 **身份验证方法** \> **登录** 。</span><span class="sxs-lookup"><span data-stu-id="c5f86-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="c5f86-137">如果选择任何其他身份验证方法，则与模板应用程序的连接将失败。</span><span class="sxs-lookup"><span data-stu-id="c5f86-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![选择 Microsoft 帐户作为身份验证方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="c5f86-139">模板应用程序实例化后，Microsoft 365 使用情况分析仪表板将在 Power BI 网页版中提供。</span><span class="sxs-lookup"><span data-stu-id="c5f86-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="c5f86-140">仪表板的初始加载将需要2到30分钟时间。</span><span class="sxs-lookup"><span data-stu-id="c5f86-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="c5f86-141">租户级别聚合将在所有报告中可用。</span><span class="sxs-lookup"><span data-stu-id="c5f86-141">Tenant level aggregates will be available in all reports.</span></span> <span data-ttu-id="c5f86-142">**用户级别的详细信息仅在选择 "日历" 月的第一天或第15天后才会变为可用** 。</span><span class="sxs-lookup"><span data-stu-id="c5f86-142">**User-level details will only become available after the 1st or 15th day of the calendar month after opting in**.</span></span> <span data-ttu-id="c5f86-143">这将影响 "用户活动" 下的所有报告。</span><span class="sxs-lookup"><span data-stu-id="c5f86-143">This will impact all reports under User Activity.</span></span> <span data-ttu-id="c5f86-144">有关如何查看和使用这些报告的提示，请参阅 [在 Microsoft 365 使用情况分析中导航和利用报告](navigate-and-utilize-reports.md) 。</span><span class="sxs-lookup"><span data-stu-id="c5f86-144">See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports.</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="c5f86-145">使收集的数据匿名</span><span class="sxs-lookup"><span data-stu-id="c5f86-145">Make the collected data anonymous</span></span>

<span data-ttu-id="c5f86-146">若要使收集的所有报表数据匿名，你必须是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="c5f86-146">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="c5f86-147">这将在报告中和模板应用程序中隐藏可识别信息，如用户、组和网站名称。</span><span class="sxs-lookup"><span data-stu-id="c5f86-147">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="c5f86-148">在管理中心中，转到 " **设置** \> **组织设置** "，在 " **服务** " 选项卡下，选择 " **报告** "。</span><span class="sxs-lookup"><span data-stu-id="c5f86-148">In the admin center, go to the **Settings** \> **Org Settings** , and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="c5f86-149">选择 " **报告** "，然后选择 " **显示匿名标识符** "。</span><span class="sxs-lookup"><span data-stu-id="c5f86-149">Select **Reports** , and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="c5f86-150">此设置既可应用于使用情况报告，也可应用于模板应用。</span><span class="sxs-lookup"><span data-stu-id="c5f86-150">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="c5f86-151">选择“ **保存更改** ”。</span><span class="sxs-lookup"><span data-stu-id="c5f86-151">Select **Save changes**.</span></span>
