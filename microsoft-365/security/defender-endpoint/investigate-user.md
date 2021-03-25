---
title: 调查 Microsoft Defender ATP 中的用户帐户
description: 调查用户帐户以在调查期间潜在泄露的凭据或透视关联的用户帐户。
keywords: 调查， 帐户， 用户， 用户实体， 警报， microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- m365-security-compliance
- m365initiative-defender-endpoint
ms.topic: article
ms.date: 04/24/2018
ms.technology: mde
ms.openlocfilehash: e79e558a7d256c46178e91b89bff27bfa6893ce9
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186709"
---
# <a name="investigate-a-user-account-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="035a7-104">调查 Microsoft Defender for Endpoint 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="035a7-104">Investigate a user account in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="035a7-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="035a7-105">**Applies to:**</span></span>
- [<span data-ttu-id="035a7-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="035a7-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="035a7-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="035a7-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="035a7-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="035a7-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="035a7-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="035a7-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatgeuser-abovefoldlink)

## <a name="investigate-user-account-entities"></a><span data-ttu-id="035a7-110">调查用户帐户实体</span><span class="sxs-lookup"><span data-stu-id="035a7-110">Investigate user account entities</span></span>

<span data-ttu-id="035a7-111">识别在仪表板上显示为"处于风险中的用户" (最活跃警报的用户帐户) 调查凭据可能遭到入侵的情况，或在调查警报或设备时透视关联的用户帐户，以确定具有该用户帐户的设备之间可能的横向移动。</span><span class="sxs-lookup"><span data-stu-id="035a7-111">Identify user accounts with the most active alerts (displayed on dashboard as "Users at risk") and investigate cases of potential compromised credentials, or pivot on the associated user account when investigating an alert or device to identify possible lateral movement between devices with that user account.</span></span>

<span data-ttu-id="035a7-112">您可以在以下视图中找到用户帐户信息：</span><span class="sxs-lookup"><span data-stu-id="035a7-112">You can find user account information in the following views:</span></span>

- <span data-ttu-id="035a7-113">仪表板</span><span class="sxs-lookup"><span data-stu-id="035a7-113">Dashboard</span></span>
- <span data-ttu-id="035a7-114">警报队列</span><span class="sxs-lookup"><span data-stu-id="035a7-114">Alert queue</span></span>
- <span data-ttu-id="035a7-115">设备详细信息页面</span><span class="sxs-lookup"><span data-stu-id="035a7-115">Device details page</span></span>

<span data-ttu-id="035a7-116">这些视图中提供了一个可单击的用户帐户链接，可让你访问显示有关用户帐户的更多详细信息的用户帐户详细信息页面。</span><span class="sxs-lookup"><span data-stu-id="035a7-116">A clickable user account link is available in these views, that will take you to the user account details page where more details about the user account are shown.</span></span>

<span data-ttu-id="035a7-117">调查用户帐户实体时，你将看到：</span><span class="sxs-lookup"><span data-stu-id="035a7-117">When you investigate a user account entity, you'll see:</span></span>

- <span data-ttu-id="035a7-118">用户帐户详细信息、Azure 高级威胁防护 (Azure ATP) 警报以及登录的设备、角色、登录类型和其他详细信息</span><span class="sxs-lookup"><span data-stu-id="035a7-118">User account details, Azure Advanced Threat Protection (Azure ATP) alerts, and logged on devices, role, logon type, and other details</span></span>
- <span data-ttu-id="035a7-119">事件和用户设备概述</span><span class="sxs-lookup"><span data-stu-id="035a7-119">Overview of the incidents and user's devices</span></span>
- <span data-ttu-id="035a7-120">与此用户相关的警报</span><span class="sxs-lookup"><span data-stu-id="035a7-120">Alerts related to this user</span></span>
- <span data-ttu-id="035a7-121">在组织中观测 (登录到) </span><span class="sxs-lookup"><span data-stu-id="035a7-121">Observed in organization (devices logged on to)</span></span>

![用户帐户实体详细信息页面的图像](images/atp-user-details-view.png)

### <a name="user-details"></a><span data-ttu-id="035a7-123">用户详细信息</span><span class="sxs-lookup"><span data-stu-id="035a7-123">User details</span></span>

<span data-ttu-id="035a7-124">左侧的用户详细信息窗格提供有关用户的信息，例如相关打开事件、活动警报、SAM 名称、SID、Azure ATP 警报、用户登录的设备数、首次看到和最后一次看到用户时、角色和登录类型。</span><span class="sxs-lookup"><span data-stu-id="035a7-124">The **User details** pane on left provides information about the user, such as related open incidents, active alerts, SAM name, SID, Azure ATP alerts, number of devices the user is logged on to, when the user was first and last seen, role, and logon types.</span></span> <span data-ttu-id="035a7-125">根据你已启用的集成功能，你将看到其他详细信息。</span><span class="sxs-lookup"><span data-stu-id="035a7-125">Depending on the integration features you've enabled, you'll see other details.</span></span> <span data-ttu-id="035a7-126">例如，如果你启用 Skype for Business 集成，你将能够从门户联系用户。</span><span class="sxs-lookup"><span data-stu-id="035a7-126">For example, if you enable the Skype for business integration, you'll be able to contact the user from the portal.</span></span> <span data-ttu-id="035a7-127">Azure **ATP 警报** 部分包含一个链接，如果已启用 Azure ATP 功能，并且存在与用户相关的警报，该链接将你访问 Azure ATP 页面。</span><span class="sxs-lookup"><span data-stu-id="035a7-127">The **Azure ATP alerts** section contains a link that will take you to the Azure ATP page, if you have enabled the Azure ATP feature, and there are alerts related to the user.</span></span> <span data-ttu-id="035a7-128">Azure ATP 页面将提供有关警报详细信息。</span><span class="sxs-lookup"><span data-stu-id="035a7-128">The Azure ATP page will provide more information about the alerts.</span></span>

>[!NOTE]
><span data-ttu-id="035a7-129">你需要在 Azure ATP 和 Defender for Endpoint 上启用集成才能使用此功能。</span><span class="sxs-lookup"><span data-stu-id="035a7-129">You'll need to enable the integration on both Azure ATP and Defender for Endpoint to use this feature.</span></span> <span data-ttu-id="035a7-130">在 Defender for Endpoint 中，可以在高级功能中启用此功能。</span><span class="sxs-lookup"><span data-stu-id="035a7-130">In Defender for Endpoint, you can enable this feature in advanced features.</span></span> <span data-ttu-id="035a7-131">若要详细了解如何启用高级功能，请参阅 [启用高级功能](advanced-features.md)。</span><span class="sxs-lookup"><span data-stu-id="035a7-131">For more information on how to enable advanced features, see [Turn on advanced features](advanced-features.md).</span></span>

<span data-ttu-id="035a7-132">组织中"概述"、"警报"和"观测到"是显示有关用户帐户的各种属性的不同选项卡。</span><span class="sxs-lookup"><span data-stu-id="035a7-132">The Overview, Alerts, and Observed in organization are different tabs that display various attributes about the user account.</span></span>

### <a name="overview"></a><span data-ttu-id="035a7-133">概述</span><span class="sxs-lookup"><span data-stu-id="035a7-133">Overview</span></span>

<span data-ttu-id="035a7-134">" **概述** "选项卡显示事件详细信息以及用户已登录的设备列表。</span><span class="sxs-lookup"><span data-stu-id="035a7-134">The **Overview** tab shows the incidents details and a list of the devices that the user has logged on to.</span></span> <span data-ttu-id="035a7-135">你可以展开它们以查看每个设备的登录事件的详细信息。</span><span class="sxs-lookup"><span data-stu-id="035a7-135">You can expand these to see details of the log-on events for each device.</span></span>

### <a name="alerts"></a><span data-ttu-id="035a7-136">警报</span><span class="sxs-lookup"><span data-stu-id="035a7-136">Alerts</span></span>

<span data-ttu-id="035a7-137">" **警报** "选项卡提供与用户帐户关联的警报列表。</span><span class="sxs-lookup"><span data-stu-id="035a7-137">The **Alerts** tab provides a list of alerts that are associated with the user account.</span></span> <span data-ttu-id="035a7-138">此列表是警报队列的筛选视图，它[](alerts-queue.md)显示用户上下文为所选用户帐户的警报、检测到最后一个活动的日期、警报的简短描述、与警报关联的设备、警报的严重性、队列中警报的状态以及分配了警报的用户。</span><span class="sxs-lookup"><span data-stu-id="035a7-138">This list is a filtered view of the [Alert queue](alerts-queue.md), and shows alerts where the user context is the selected user account, the date when the last activity was detected, a short description of the alert, the device associated with the alert, the alert's severity, the alert's status in the queue, and who is assigned the alert.</span></span>

### <a name="observed-in-organization"></a><span data-ttu-id="035a7-139">在组织中观测到</span><span class="sxs-lookup"><span data-stu-id="035a7-139">Observed in organization</span></span>

<span data-ttu-id="035a7-140">通过"在组织中观测到"选项卡，你可以指定一个日期范围，以查看观测到此用户登录的设备列表、其中每台设备的登录频率最多和登录频率最少的用户帐户，以及每台设备上观测到的用户总数。</span><span class="sxs-lookup"><span data-stu-id="035a7-140">The **Observed in organization** tab allows you to specify a date range to see a list of devices where this user was observed logged on to, the most frequent and least frequent logged on user account for each of these devices, and total observed users on each device.</span></span>

<span data-ttu-id="035a7-141">选择"组织中观测到的项目"表上的项目将展开该项目，显示有关设备的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="035a7-141">Selecting an item on the Observed in organization table will expand the item, revealing more details about the device.</span></span> <span data-ttu-id="035a7-142">直接选择项目内的链接将发送给相应的页面。</span><span class="sxs-lookup"><span data-stu-id="035a7-142">Directly selecting a link within an item will send you to the corresponding page.</span></span>

## <a name="search-for-specific-user-accounts"></a><span data-ttu-id="035a7-143">搜索特定用户帐户</span><span class="sxs-lookup"><span data-stu-id="035a7-143">Search for specific user accounts</span></span>

1. <span data-ttu-id="035a7-144">从 **搜索** 栏 **下拉菜单中选择** 用户。</span><span class="sxs-lookup"><span data-stu-id="035a7-144">Select **User** from the **Search bar** drop-down menu.</span></span>
2. <span data-ttu-id="035a7-145">在"搜索"字段中 **输入** 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="035a7-145">Enter the user account in the **Search** field.</span></span>
3. <span data-ttu-id="035a7-146">单击搜索图标或按 **Enter。**</span><span class="sxs-lookup"><span data-stu-id="035a7-146">Click the search icon or press **Enter**.</span></span>

<span data-ttu-id="035a7-147">将显示与查询文本匹配的用户列表。</span><span class="sxs-lookup"><span data-stu-id="035a7-147">A list of users matching the query text is displayed.</span></span> <span data-ttu-id="035a7-148">你将看到用户帐户的域和名称、上次看到用户帐户的时间，以及过去 30 天内观测到它登录到的设备总数。</span><span class="sxs-lookup"><span data-stu-id="035a7-148">You'll see the user account's domain and name, when the user account was last seen, and the total number of devices it was observed logged on to in the last 30 days.</span></span>

<span data-ttu-id="035a7-149">可以按以下时间段筛选结果：</span><span class="sxs-lookup"><span data-stu-id="035a7-149">You can filter the results by the following time periods:</span></span>

- <span data-ttu-id="035a7-150">1 天</span><span class="sxs-lookup"><span data-stu-id="035a7-150">1 day</span></span>
- <span data-ttu-id="035a7-151">3 天</span><span class="sxs-lookup"><span data-stu-id="035a7-151">3 days</span></span>
- <span data-ttu-id="035a7-152">7 天</span><span class="sxs-lookup"><span data-stu-id="035a7-152">7 days</span></span>
- <span data-ttu-id="035a7-153">30 天</span><span class="sxs-lookup"><span data-stu-id="035a7-153">30 days</span></span>
- <span data-ttu-id="035a7-154">6 个月</span><span class="sxs-lookup"><span data-stu-id="035a7-154">6 months</span></span>

## <a name="related-topics"></a><span data-ttu-id="035a7-155">相关主题</span><span class="sxs-lookup"><span data-stu-id="035a7-155">Related topics</span></span>

- [<span data-ttu-id="035a7-156">查看和组织 Microsoft Defender 终结点警报队列</span><span class="sxs-lookup"><span data-stu-id="035a7-156">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="035a7-157">管理 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="035a7-157">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="035a7-158">调查 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="035a7-158">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="035a7-159">调查与 Defender for Endpoint 警报关联的文件</span><span class="sxs-lookup"><span data-stu-id="035a7-159">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="035a7-160">调查 Defender for Endpoint Devices 列表中的设备</span><span class="sxs-lookup"><span data-stu-id="035a7-160">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="035a7-161">调查与 Defender for Endpoint 警报关联的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="035a7-161">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="035a7-162">调查与 Defender for Endpoint 警报关联的域</span><span class="sxs-lookup"><span data-stu-id="035a7-162">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
