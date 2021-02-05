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
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="06492-103">启用 Microsoft 365 使用情况分析</span><span class="sxs-lookup"><span data-stu-id="06492-103">Enable Microsoft 365 usage analytics</span></span>

::: moniker range="o365-21vianet"

> [!NOTE]
> <span data-ttu-id="06492-104">管理中心正在发生改变。</span><span class="sxs-lookup"><span data-stu-id="06492-104">The admin center is changing.</span></span> <span data-ttu-id="06492-105">如果你的体验与此处提供的详细信息不匹配，请参阅[有关新版 Microsoft 365 管理中心](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true)。</span><span class="sxs-lookup"><span data-stu-id="06492-105">If your experience doesn't match the details presented here, see [About the new Microsoft 365 admin center](https://docs.microsoft.com/microsoft-365/admin/microsoft-365-admin-center-preview?view=o365-21vianet&preserve-view=true).</span></span>

::: moniker-end

<span data-ttu-id="06492-106">Microsoft 365 使用情况分析尚不可用于 Microsoft 365 美国政府社区版。</span><span class="sxs-lookup"><span data-stu-id="06492-106">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="06492-107">启用 Microsoft 365 使用情况分析的步骤</span><span class="sxs-lookup"><span data-stu-id="06492-107">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="06492-108">若要开始使用 Microsoft 365 使用情况分析，必须先在 Microsoft 365 管理中心提供数据，然后在 Power BI 中启动模板应用。</span><span class="sxs-lookup"><span data-stu-id="06492-108">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="06492-109">获取 Power BI</span><span class="sxs-lookup"><span data-stu-id="06492-109">Get Power BI</span></span>

<span data-ttu-id="06492-110">如果还没有 Power BI，可以注册 Power [BI Pro。](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="06492-110">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="06492-111">选择 **"免费试用** 以注册试用版" **或"立即** 购买"获取 Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="06492-111">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="06492-112">也可展开" **产品**"，购买某一版 Power BI。</span><span class="sxs-lookup"><span data-stu-id="06492-112">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="06492-113">你需要 Power BI Pro 许可证才能安装、自定义和分发模板应用。</span><span class="sxs-lookup"><span data-stu-id="06492-113">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="06492-114">有关详细信息，[请参阅先决条件。](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)</span><span class="sxs-lookup"><span data-stu-id="06492-114">For more information, please see [Prerequisites](https://docs.microsoft.com/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="06492-115">要共享你的数据，你和你共享数据的人、需要 Power BI Pro 许可证，或者内容需要在 Power BI Premium 服务中的工作区 [中](https://docs.microsoft.com/power-bi/service-premium-what-is)。</span><span class="sxs-lookup"><span data-stu-id="06492-115">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](https://docs.microsoft.com/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="06492-116">启用模板应用</span><span class="sxs-lookup"><span data-stu-id="06492-116">Enable the template app</span></span>

<span data-ttu-id="06492-117">若要启用模板应用，你必须是全局 **管理员**。</span><span class="sxs-lookup"><span data-stu-id="06492-117">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="06492-118">有关详细信息 [，请参阅管理员](../add-users/about-admin-roles.md) 角色。</span><span class="sxs-lookup"><span data-stu-id="06492-118">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="06492-119">在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。</span><span class="sxs-lookup"><span data-stu-id="06492-119">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="06492-120">在"**使用情况**"页上，找到 **Microsoft 365 使用情况分析** 卡，然后选择"**开始使用"。**</span><span class="sxs-lookup"><span data-stu-id="06492-120">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="06492-121">在打开的"报告"面板上，将 Power BI 的 **Microsoft 365** 使用情况分析数据设置为 **"保存** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="06492-121">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="06492-122">数据收集过程将在两到 48 小时内完成，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="06492-122">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="06492-123">数据收集 **完成后，"转到 Power BI"** 按钮 (，) 不再灰显。</span><span class="sxs-lookup"><span data-stu-id="06492-123">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="06492-124">启动模板应用</span><span class="sxs-lookup"><span data-stu-id="06492-124">Start the template app</span></span>

<span data-ttu-id="06492-125">若要启动模板应用程序，你必须是全局管理员、报告读取者 **、Exchange 管理员\*\*\*\*、Skype for Business 管理员** 或 **SharePoint 管理员**。 </span><span class="sxs-lookup"><span data-stu-id="06492-125">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="06492-126">复制租户 ID，然后选择 **"转到 Power BI"。**</span><span class="sxs-lookup"><span data-stu-id="06492-126">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="06492-127">转到 Power BI 后，请进行登录。</span><span class="sxs-lookup"><span data-stu-id="06492-127">When you get to Power BI, sign in.</span></span> <span data-ttu-id="06492-128">然后 **从** -> **导航菜单中选择"** 应用获取应用"。</span><span class="sxs-lookup"><span data-stu-id="06492-128">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="06492-129">在 **"应用"** 选项卡中，在搜索框中键入 Microsoft 365，然后选择 **Microsoft 365 使用情况** 分析 \> **"现在获取它"。**</span><span class="sxs-lookup"><span data-stu-id="06492-129">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="06492-130">[![选择"现在获取"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="06492-130">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="06492-131">安装应用后。</span><span class="sxs-lookup"><span data-stu-id="06492-131">Once the app is installed.</span></span> <span data-ttu-id="06492-132">选择磁贴将其打开。</span><span class="sxs-lookup"><span data-stu-id="06492-132">Select the tile to open it.</span></span>

5.  <span data-ttu-id="06492-133">选择 **"浏览** "应用以查看包含示例数据的应用。</span><span class="sxs-lookup"><span data-stu-id="06492-133">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="06492-134">选择 **"** 连接"将应用连接到组织的数据。</span><span class="sxs-lookup"><span data-stu-id="06492-134">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="06492-135">Choose **Connect**， on the **Connect to Microsoft 365 usage analytics** screen， then type in the tenant ID (without dashes) you copied in step (1) ， and select **Next**.</span><span class="sxs-lookup"><span data-stu-id="06492-135">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="06492-136">下一个屏幕上，选择 **OAuth2** 作为 **身份验证方法** \> **登录**。</span><span class="sxs-lookup"><span data-stu-id="06492-136">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="06492-137">如果选择任何其他身份验证方法，则与模板应用的连接将失败。</span><span class="sxs-lookup"><span data-stu-id="06492-137">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![选择 Microsoft 帐户作为身份验证方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="06492-139">实例化模板应用后，Microsoft 365 使用情况分析仪表板将在 Power BI 网页版中提供。</span><span class="sxs-lookup"><span data-stu-id="06492-139">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="06492-140">仪表板的初始加载需要 2 到 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="06492-140">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="06492-141">选择加入后，租户级别聚合将在所有报告中可用。</span><span class="sxs-lookup"><span data-stu-id="06492-141">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="06492-142">**用户级别的详细信息仅在** 选择加入后的下一个日历月的第 5 日左右可用。</span><span class="sxs-lookup"><span data-stu-id="06492-142">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="06492-143">这将影响"用户活动" (查看"导航"，并利用 [Microsoft 365](navigate-and-utilize-reports.md) 使用情况分析中的报告，获取有关如何查看和使用这些报告的) 。</span><span class="sxs-lookup"><span data-stu-id="06492-143">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="06492-144">使收集的数据匿名</span><span class="sxs-lookup"><span data-stu-id="06492-144">Make the collected data anonymous</span></span>

<span data-ttu-id="06492-145">若要使收集的所有报表数据匿名，你必须是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="06492-145">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="06492-146">这将在报表和模板应用中隐藏可识别的信息，如用户、组和网站名称。</span><span class="sxs-lookup"><span data-stu-id="06492-146">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="06492-147">在管理中心，转到 **"设置** \> **组织** 设置"，在"服务"选项卡下，选择"**报告"。**</span><span class="sxs-lookup"><span data-stu-id="06492-147">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="06492-148">选择 **"** 报告"，然后选择 **"显示匿名标识符"。**</span><span class="sxs-lookup"><span data-stu-id="06492-148">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="06492-149">此设置同时应用于使用情况报表和模板应用。</span><span class="sxs-lookup"><span data-stu-id="06492-149">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="06492-150">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="06492-150">Select **Save changes**.</span></span>
