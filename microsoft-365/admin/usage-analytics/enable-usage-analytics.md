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
ms.openlocfilehash: c0e39a307ee75c661e0f91fcbbcfeae3d95c7257
ms.sourcegitcommit: 00f001019c653269d85718d410f970887d904304
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/12/2021
ms.locfileid: "53394745"
---
# <a name="enable-microsoft-365-usage-analytics"></a><span data-ttu-id="43261-103">启用 Microsoft 365 使用情况分析</span><span class="sxs-lookup"><span data-stu-id="43261-103">Enable Microsoft 365 usage analytics</span></span>

<span data-ttu-id="43261-104">Microsoft 365使用情况分析尚不可用于美国政府Microsoft 365 Community。</span><span class="sxs-lookup"><span data-stu-id="43261-104">Microsoft 365 usage analytics is not yet available for Microsoft 365 US Government Community.</span></span>

## <a name="before-you-begin"></a><span data-ttu-id="43261-105">准备工作</span><span class="sxs-lookup"><span data-stu-id="43261-105">Before you begin</span></span>

<span data-ttu-id="43261-106">若要开始使用Microsoft 365分析，你必须先在应用中提供Microsoft 365 管理中心，然后在 Power BI 中启动模板应用。</span><span class="sxs-lookup"><span data-stu-id="43261-106">To get started with Microsoft 365 usage analytics you must first make the data available in the Microsoft 365 admin center, then initiate the template app in Power BI.</span></span>

## <a name="get-power-bi"></a><span data-ttu-id="43261-107">获取 Power BI</span><span class="sxs-lookup"><span data-stu-id="43261-107">Get Power BI</span></span>

<span data-ttu-id="43261-108">如果尚未注册Power BI，可以[注册Power BI Pro。](https://go.microsoft.com/fwlink/p/?linkid=845347)</span><span class="sxs-lookup"><span data-stu-id="43261-108">If you don't already have Power BI, you can [sign up for Power BI Pro](https://go.microsoft.com/fwlink/p/?linkid=845347).</span></span> <span data-ttu-id="43261-109">选择 **"免费试用**"以注册试用版，**或选择"** 立即购买"Power BI Pro。</span><span class="sxs-lookup"><span data-stu-id="43261-109">Select **Try free** to sign up for a trial, or **Buy now** to get Power BI Pro.</span></span>


<span data-ttu-id="43261-110">也可展开" **产品**"，购买某一版 Power BI。</span><span class="sxs-lookup"><span data-stu-id="43261-110">You can also expand **Products** to buy a version of Power BI.</span></span>

> [!NOTE]
> <span data-ttu-id="43261-111">你需要一个Power BI Pro许可证来安装、自定义和分发模板应用。</span><span class="sxs-lookup"><span data-stu-id="43261-111">You need a Power BI Pro license to install, customize, and distribute a template app.</span></span> <span data-ttu-id="43261-112">有关详细信息，请参阅 [先决条件](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites)。</span><span class="sxs-lookup"><span data-stu-id="43261-112">For more information, please see [Prerequisites](/power-bi/service-template-apps-install-distribute?source=docs#prerequisites).</span></span>

<span data-ttu-id="43261-113">若要共享数据，你和共享数据的人都需要 Power BI Pro 许可证，或者内容需要Power BI[工作区中](/power-bi/service-premium-what-is)。</span><span class="sxs-lookup"><span data-stu-id="43261-113">To share your data, both you and the people who you share the data with, need a Power BI Pro license, or the content needs to be in a workspace in a [Power BI premium service](/power-bi/service-premium-what-is).</span></span>

## <a name="enable-the-template-app"></a><span data-ttu-id="43261-114">启用模板应用</span><span class="sxs-lookup"><span data-stu-id="43261-114">Enable the template app</span></span>

<span data-ttu-id="43261-115">若要启用模板应用，你必须是全局 **管理员**。</span><span class="sxs-lookup"><span data-stu-id="43261-115">To enable the template app, you have to be a **Global administrator**.</span></span>

<span data-ttu-id="43261-116">有关详细信息 [，请参阅有关](../add-users/about-admin-roles.md) 管理员角色的信息。</span><span class="sxs-lookup"><span data-stu-id="43261-116">See [about admin roles](../add-users/about-admin-roles.md) for more information.</span></span>

1. <span data-ttu-id="43261-117">在管理中心，转到 \> **"设置"组织设置** \> **""服务"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="43261-117">In the admin center, go to the **Settings** \> **Org settings** \> **Services** tab.</span></span>

2. <span data-ttu-id="43261-118">在"**服务"选项卡** 上，选择"报告 **"。**</span><span class="sxs-lookup"><span data-stu-id="43261-118">On the **Services** tab, select  **Reports**.</span></span>

3. <span data-ttu-id="43261-119">在打开的"报告"面板上，将"报告数据可供Microsoft 365 **使用情况** 分析 **"Power BI"保存** \> **"。**</span><span class="sxs-lookup"><span data-stu-id="43261-119">On the Reports panel that opens, set **Make report data available to Microsoft 365 usage analytics for Power BI** to **On** \> **Save**.</span></span>

<span data-ttu-id="43261-120">数据收集过程将在 2 到 48 小时内完成，具体取决于租户的大小。</span><span class="sxs-lookup"><span data-stu-id="43261-120">The data collection process will complete in two to 48 hours depending on the size of your tenant.</span></span> <span data-ttu-id="43261-121">数据收集 **完成后Power BI"** 转到 ("按钮) 不再灰显。</span><span class="sxs-lookup"><span data-stu-id="43261-121">The **Go to Power BI** button will be enabled (no longer gray) when data collection is complete.</span></span>

## <a name="start-the-template-app"></a><span data-ttu-id="43261-122">启动模板应用</span><span class="sxs-lookup"><span data-stu-id="43261-122">Start the template app</span></span>

<span data-ttu-id="43261-123">若要启动模板应用，你必须是全局管理员、报告读取者、Exchange管理员、Skype for Business **管理员** SharePoint **管理员**。</span><span class="sxs-lookup"><span data-stu-id="43261-123">To start the template app, you have to be either a **global administrator**, **report reader**, **Exchange administrator**, **Skype for Business administrator**, or **SharePoint administrator**.</span></span>

1. <span data-ttu-id="43261-124">复制租户 ID，然后选择"**转到Power BI"。**</span><span class="sxs-lookup"><span data-stu-id="43261-124">Copy the tenant ID and select **Go to Power BI**.</span></span>

2. <span data-ttu-id="43261-125">转到 Power BI 后，请进行登录。</span><span class="sxs-lookup"><span data-stu-id="43261-125">When you get to Power BI, sign in.</span></span> <span data-ttu-id="43261-126">然后 **从** -> **导航菜单中选择"应用**""获取应用"。</span><span class="sxs-lookup"><span data-stu-id="43261-126">Then **Select Apps**->**Get apps** from the navigation menu.</span></span>

3. <span data-ttu-id="43261-127">在"**应用"** 选项卡Microsoft 365搜索框中键入"应用"，然后选择"Microsoft 365 **使用情况分析** \> **""现在获取它"。**</span><span class="sxs-lookup"><span data-stu-id="43261-127">In the **Apps** tab, type Microsoft 365 in the search box and then select **Microsoft 365 usage analytics** \> **Get it now**.</span></span>

    <span data-ttu-id="43261-128">[![选择"现在获取"](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span><span class="sxs-lookup"><span data-stu-id="43261-128">[![Select Get it now](../../media/78102250-9874-4a32-8365-436f13560b52.png)](https://app.powerbi.com/groups/me/getapps/services/cia_microsoft365.microsoft-365-usage-analytics)</span></span>

4. <span data-ttu-id="43261-129">安装应用后。</span><span class="sxs-lookup"><span data-stu-id="43261-129">Once the app is installed.</span></span> <span data-ttu-id="43261-130">选择磁贴将其打开。</span><span class="sxs-lookup"><span data-stu-id="43261-130">Select the tile to open it.</span></span>

5. <span data-ttu-id="43261-131">选择 **"浏览** 应用"以查看包含示例数据的应用。</span><span class="sxs-lookup"><span data-stu-id="43261-131">Select **Explore app** to view the app with sample data.</span></span> <span data-ttu-id="43261-132">选择 **连接** 以将应用连接到组织的数据。</span><span class="sxs-lookup"><span data-stu-id="43261-132">Choose **Connect** to connect the app to your organization’s data.</span></span>

6. <span data-ttu-id="43261-133">选择 **"连接"，** 在"连接 到 **Microsoft 365** 使用情况分析"屏幕上，键入在步骤 (1) 中复制的租户 ID (不带短划线) ) ，然后选择"下一步"。</span><span class="sxs-lookup"><span data-stu-id="43261-133">Choose **Connect**, on the **Connect to Microsoft 365 usage analytics** screen, then type in the tenant ID (without dashes) you copied in step (1), and select **Next**.</span></span>

7. <span data-ttu-id="43261-134">下一个屏幕上，选择 **"OAuth2"\*\*\*\*作为"身份验证方法** \> **""登录"。**</span><span class="sxs-lookup"><span data-stu-id="43261-134">On the next screen, select **OAuth2** as the **Authentication method** \> **Sign in**.</span></span> <span data-ttu-id="43261-135">如果选择任何其他身份验证方法，则与模板应用的连接将失败。</span><span class="sxs-lookup"><span data-stu-id="43261-135">If you choose any other authentication method, the connection to the template app will fail.</span></span>

    ![选择 Microsoft 帐户作为身份验证方法](../../media/ab6f0463-c3f7-4088-a605-67c699fa86adnew.png)

8. <span data-ttu-id="43261-137">实例化模板应用后，Microsoft 365使用情况分析仪表板将在Power BI中可用。</span><span class="sxs-lookup"><span data-stu-id="43261-137">After the template app is instantiated the Microsoft 365 usage analytics dashboard will be available in Power BI on the web.</span></span> <span data-ttu-id="43261-138">仪表板的初始加载需要 2 到 30 分钟。</span><span class="sxs-lookup"><span data-stu-id="43261-138">The initial loading of the dashboard will take between 2 to 30 minutes.</span></span>

<span data-ttu-id="43261-139">选择加入后，租户级别聚合将在所有报告中可用。</span><span class="sxs-lookup"><span data-stu-id="43261-139">Tenant level aggregates will be available in all reports after opting in.</span></span> <span data-ttu-id="43261-140">**用户级别的详细信息将仅在** 选择加入后的下一日历月 5 日左右可用。</span><span class="sxs-lookup"><span data-stu-id="43261-140">**User-level details will only become available around the 5th of the next calendar month after opting in**.</span></span> <span data-ttu-id="43261-141">这将影响"用户活动"下的所有 (请参阅导航和利用[Microsoft 365 使用情况](navigate-and-utilize-reports.md)分析中的报告，获取有关如何查看和使用这些报告的) 。</span><span class="sxs-lookup"><span data-stu-id="43261-141">This will impact all reports under User Activity (See [Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) for tips on how to view and use these reports).</span></span>

## <a name="make-the-collected-data-anonymous"></a><span data-ttu-id="43261-142">使收集的数据匿名</span><span class="sxs-lookup"><span data-stu-id="43261-142">Make the collected data anonymous</span></span>

<span data-ttu-id="43261-143">若要使收集的所有报表数据匿名，你必须是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="43261-143">To make the data that is collected for all reports anonymous, you have to be a global administrator.</span></span> <span data-ttu-id="43261-144">这将在报告和模板应用中隐藏可识别信息，如用户、组和网站名称。</span><span class="sxs-lookup"><span data-stu-id="43261-144">This will hide identifiable information such as user, group and site names in reports and in the template app .</span></span>

1. <span data-ttu-id="43261-145">在管理中心中，转到"设置 \> **组织设置"，在"服务"选项卡** 下，选择"报告 **"。**</span><span class="sxs-lookup"><span data-stu-id="43261-145">In the admin center, go to the **Settings** \> **Org Settings**, and under **Services** tab, choose **Reports**.</span></span>

2. <span data-ttu-id="43261-146">选择 **"报告**"，然后选择"**显示匿名标识符"。**</span><span class="sxs-lookup"><span data-stu-id="43261-146">Select **Reports**, and then choose to **Display anonymous identifiers**.</span></span> <span data-ttu-id="43261-147">此设置既适用于使用情况报告，也适用于模板应用。</span><span class="sxs-lookup"><span data-stu-id="43261-147">This setting gets applied both to the usage reports as well as to the template app.</span></span>

3. <span data-ttu-id="43261-148">选择“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="43261-148">Select **Save changes**.</span></span>

## <a name="related-content"></a><span data-ttu-id="43261-149">相关内容</span><span class="sxs-lookup"><span data-stu-id="43261-149">Related content</span></span>

<span data-ttu-id="43261-150">[关于使用情况分析](usage-analytics.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="43261-150">[About usage analytics](usage-analytics.md) (article)</span></span>\
<span data-ttu-id="43261-151">[获取使用情况分析的最新版本](get-the-latest-version-of-usage-analytics.md) (文章) </span><span class="sxs-lookup"><span data-stu-id="43261-151">[Get the latest version of usage analytics](get-the-latest-version-of-usage-analytics.md) (article)</span></span>\
<span data-ttu-id="43261-152">[导航和利用 Microsoft 365 使用情况分析 (](navigate-and-utilize-reports.md)中的) </span><span class="sxs-lookup"><span data-stu-id="43261-152">[Navigate and utilize the reports in Microsoft 365 usage analytics](navigate-and-utilize-reports.md) (article)</span></span>