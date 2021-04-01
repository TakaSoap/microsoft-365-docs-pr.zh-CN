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
ms.openlocfilehash: 734712994d47fcb234ba988bb4d185d09f3267d0
ms.sourcegitcommit: d4604e333507c6f57d5bf327531a241b649052de
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/31/2021
ms.locfileid: "51471053"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="a3657-103">启用 Microsoft 365 使用情况分析</span><span class="sxs-lookup"><span data-stu-id="a3657-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="a3657-104">Microsoft 365 美国政府版社区版尚未提供 Microsoft 365 使用情况分析。</span><span class="sxs-lookup"><span data-stu-id="a3657-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>
  
## <a name="steps-to-enable-microsoft-365-usage-analytics"></a><span data-ttu-id="a3657-105">启用 Microsoft 365 使用情况分析的步骤</span><span class="sxs-lookup"><span data-stu-id="a3657-105">Steps to enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="a3657-106">若要开始使用 Microsoft 365 使用情况分析，必须先在 Microsoft 365 管理中心提供数据，然后在 Power BI 中启动模板应用。</span><span class="sxs-lookup"><span data-stu-id="a3657-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>
  
### <a name="get-power-bi"></a><span data-ttu-id="a3657-107">获取 Power BI</span><span class="sxs-lookup"><span data-stu-id="a3657-107">Get Power BI</span></span>

<span data-ttu-id="a3657-108">如果还没有 Power BI，可以注册 Power [BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347)。</span><span class="sxs-lookup"><span data-stu-id="a3657-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="a3657-109">选择 **"免费试用** "以注册试用版， **或选择"** 立即购买"获取 Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="a3657-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>
  
  
<span data-ttu-id="a3657-110">也可展开" **产品**"，购买某一版 Power BI。</span><span class="sxs-lookup"><span data-stu-id="a3657-110">You can also expand **Products** to buy a version of Power BI.</span></span> 

> [!NOTE]
> <span data-ttu-id="a3657-111">需要 Power BI Pro 许可证才能安装、自定义和分发模板应用。</span><span class="sxs-lookup"><span data-stu-id="a3657-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="a3657-112">有关详细信息，请参阅 [先决条件](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="a3657-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="a3657-113">若要共享数据，你和共享数据的人都需要 Power BI Pro 许可证，或者内容需要在 Power BI 高级服务 [中的工作区中](/power-bi/service-premium-what-is)。</span><span class="sxs-lookup"><span data-stu-id="a3657-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span> 
  
### <a name="enable-the-template-app"></a><span data-ttu-id="a3657-114">启用模板应用</span><span class="sxs-lookup"><span data-stu-id="a3657-114">Enable the template app</span></span>

<span data-ttu-id="a3657-115">若要启用模板应用，你必须是全局 **管理员**。</span><span class="sxs-lookup"><span data-stu-id="a3657-115">To enable the template app, you have to be a **Global administrator**.</span></span>
  
<span data-ttu-id="a3657-116">有关详细信息 [，请参阅有关](../add-users/about-admin-roles.md) 管理员角色的信息。</span><span class="sxs-lookup"><span data-stu-id="a3657-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span> 
  
1. <span data-ttu-id="a3657-117">在管理中心，转到“**报表**”\> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">使用情况</a>页面。</span><span class="sxs-lookup"><span data-stu-id="a3657-117">In the admin center, go to the **Reports** \> <a href="https://go.microsoft.com/fwlink/p/?linkid=2074756" target="_blank">Usage</a> page.</span></span> 
    
2. <span data-ttu-id="a3657-118">在使用情况 **页面上** ，找到 **Microsoft 365 使用情况分析卡** ，然后选择 **入门**。</span><span class="sxs-lookup"><span data-stu-id="a3657-118">On the **Usage** page, locate the **Microsoft 365 usage analytics** card, and select **Get started**.</span></span>
    
3. <span data-ttu-id="a3657-119">在打开的"报告"面板上，将"为 **Power BI 的 Microsoft 365** 使用情况分析提供数据"设置为 **"保存** \> **时"。**</span><span class="sxs-lookup"><span data-stu-id="a3657-119">On the Reports panel that opens, set **Make data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span> 
  
<span data-ttu-id="a3657-120">数据收集过程将在 2 到 48 小时内完成，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="a3657-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="a3657-121">数据收集 **完成后，"转到 Power BI"** 按钮 (不再灰显) "按钮。</span><span class="sxs-lookup"><span data-stu-id="a3657-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span> 
    
### <a name="start-the-template-app"></a><span data-ttu-id="a3657-122">启动模板应用</span><span class="sxs-lookup"><span data-stu-id="a3657-122">Start the template app</span></span>

<span data-ttu-id="a3657-123">若要启动模板应用，你必须是全局管理员、报告读取者 **、Exchange 管理员\*\*\*\*、Skype for Business 管理员** 或 **SharePoint 管理员**。 </span><span class="sxs-lookup"><span data-stu-id="a3657-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span> 
  
1. <span data-ttu-id="a3657-124">复制租户 ID，然后选择 **"转到 Power BI"。**</span><span class="sxs-lookup"><span data-stu-id="a3657-124">Copy the tenant ID and select **Go to Power BI**.</span></span>
    
2.  <span data-ttu-id="a3657-125">转到 Power BI 后，请进行登录。</span><span class="sxs-lookup"><span data-stu-id="a3657-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="a3657-126">然后 **从** -> **导航菜单中选择"应用**""获取应用"。</span><span class="sxs-lookup"><span data-stu-id="a3657-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>    
  
3. <span data-ttu-id="a3657-127">在"**应用"** 选项卡中，在搜索框中键入 Microsoft 365，然后选择 **"Microsoft 365 使用情况** 分析 \> **""现在获取它"。**</span><span class="sxs-lookup"><span data-stu-id="a3657-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="a3657-128">[![选择"现在获取"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="a3657-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>
    
4.  <span data-ttu-id="a3657-129">安装应用后。</span><span class="sxs-lookup"><span data-stu-id="a3657-129">Once the app is installed.</span></span> <span data-ttu-id="a3657-130">选择磁贴将其打开。</span><span class="sxs-lookup"><span data-stu-id="a3657-130">Select the tile to open it.</span></span>

5.  <span data-ttu-id="a3657-131">选择 **"浏览** 应用"以查看包含示例数据的应用。</span><span class="sxs-lookup"><span data-stu-id="a3657-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="a3657-132">选择 **"** 连接"以将应用连接到组织的数据。</span><span class="sxs-lookup"><span data-stu-id="a3657-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6.  <span data-ttu-id="a3657-133">选择 **"连接**"，在"连接到 **Microsoft 365** 使用情况分析"屏幕上，键入租户 ID (不带短划线) 在步骤 (1) 中复制，然后选择"下一步"。 </span><span class="sxs-lookup"><span data-stu-id="a3657-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>
    
7. <span data-ttu-id="a3657-134">下一个屏幕上，选择 **"OAuth2"\*\*\*\*作为"身份验证方法** \> **""登录"。**</span><span class="sxs-lookup"><span data-stu-id="a3657-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="a3657-135">如果选择任何其他身份验证方法，则与模板应用的连接将失败。</span><span class="sxs-lookup"><span data-stu-id="a3657-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>
    
    ![选择 Microsoft 帐户作为身份验证方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)
  
8. <span data-ttu-id="a3657-137">实例化模板应用后，Microsoft 365 使用情况分析仪表板将在 Power BI 网页版中可用。</span><span class="sxs-lookup"><span data-stu-id="a3657-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="a3657-138">仪表板的初始加载需要 2 到 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="a3657-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>
  
<span data-ttu-id="a3657-139">选择加入后，租户级别聚合将在所有报告中可用。</span><span class="sxs-lookup"><span data-stu-id="a3657-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="a3657-140">**用户级别的详细信息将仅在** 选择加入后的下一日历月 5 日左右可用。</span><span class="sxs-lookup"><span data-stu-id="a3657-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="a3657-141">这将影响"用户活动"下的所有 (请参阅导航和利用 [Microsoft 365](navigate-and-utilize-reports.md) 使用情况分析中的报告，获取有关如何查看和使用这些报告的) 。</span><span class="sxs-lookup"><span data-stu-id="a3657-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>
    
## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="a3657-142">使收集的数据匿名</span><span class="sxs-lookup"><span data-stu-id="a3657-142">Make the collected data anonymous</span></span>

<span data-ttu-id="a3657-143">若要使收集的所有报表数据匿名，你必须是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="a3657-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="a3657-144">这将在报告和模板应用中隐藏可识别信息，如用户、组和网站名称。</span><span class="sxs-lookup"><span data-stu-id="a3657-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>
  
1. <span data-ttu-id="a3657-145">在管理中心中，转到 **"设置** \> **""组织设置"，** 在"服务 **"** 选项卡下，选择"报告 **"。**</span><span class="sxs-lookup"><span data-stu-id="a3657-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>
    
2. <span data-ttu-id="a3657-146">选择 **"报告**"，然后选择"**显示匿名标识符"。**</span><span class="sxs-lookup"><span data-stu-id="a3657-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="a3657-147">此设置既适用于使用情况报告，也适用于模板应用。</span><span class="sxs-lookup"><span data-stu-id="a3657-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>
  
3. <span data-ttu-id="a3657-148">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="a3657-148">Select **Save changes**.</span></span>