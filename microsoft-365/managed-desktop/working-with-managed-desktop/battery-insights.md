---
title: 电池见解
description: 显示有关预计电池使用时间以及最高功率消耗者的数据的报告
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 32ab3a984d5ab46aac26989518cd3e570082d688
ms.sourcegitcommit: cebbdd393dcfd93ff43a1ab66ad70115853f83e7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52739760"
---
# <a name="battery-insights"></a><span data-ttu-id="f6dc2-104">电池见解</span><span class="sxs-lookup"><span data-stu-id="f6dc2-104">Battery insights</span></span>
<span data-ttu-id="f6dc2-105">此视图可为你的设备提供电源、电池Microsoft 托管桌面指标。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-105">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f6dc2-106">出于这些目的，如果应用正在运行且具有焦点，则该应用将被视为"使用中"。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-106">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="f6dc2-107">若要查看使用情况数据，请选择" **电池"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-107">To view usage data, select the **Battery** tab.</span></span>

![电池窗格：预测左上角每个设备型号的电池使用时间，顶部能耗 (按应用) 右上角的见解表显示。](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="f6dc2-110">预计电池使用时间</span><span class="sxs-lookup"><span data-stu-id="f6dc2-110">Predicted battery life</span></span>

<span data-ttu-id="f6dc2-111">在 **"预测电池使用时间** "区域中，我们按设备模型组织，提供设备的预期电池使用时间预测。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-111">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="f6dc2-112">此数据派生自随机选择并报告数据的 Microsoft 托管桌面 部署中的设备所采样的能耗<em></em>、使用时间和电池容量。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-112">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="f6dc2-113">该表提供预计的电池使用时间 (小时) 、其他 Microsoft 托管桌面 部署中相同型号的平均电池使用时间，以及环境中报告此数据的设备数量。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-113">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="f6dc2-114">通过选择列标题对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-114">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="f6dc2-115">顶级能源使用者</span><span class="sxs-lookup"><span data-stu-id="f6dc2-115">Top energy consumers</span></span>

<span data-ttu-id="f6dc2-116">在 **主要能源** 使用者区域中，你将发现环境中消耗最多能耗的应用以每千米 (mWh) 。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-116">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="f6dc2-117">显示的应用是按特定设备显示的，你在左侧的"预测电池使用 **时间"部分中** 选择这些应用。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-117">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="f6dc2-118">例如，若要查看 Microsoft Surface Book 2 设备每应用消耗，请在电池使用时间区域中选择该行。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-118">For example, to see the per-app consumption for your Microsoft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="f6dc2-119">如果未选择任何模型，则显示的应用使用数据适用于我们具有共同数据的所有应用。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-119">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="f6dc2-120">对于每个应用，彩色分段显示应用在以下类别中的能耗使用分布：</span><span class="sxs-lookup"><span data-stu-id="f6dc2-120">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="f6dc2-121">CPU</span><span class="sxs-lookup"><span data-stu-id="f6dc2-121">CPU</span></span>
- <span data-ttu-id="f6dc2-122">显示器</span><span class="sxs-lookup"><span data-stu-id="f6dc2-122">Display</span></span>
- <span data-ttu-id="f6dc2-123">网络</span><span class="sxs-lookup"><span data-stu-id="f6dc2-123">Network</span></span>
- <span data-ttu-id="f6dc2-124">其他</span><span class="sxs-lookup"><span data-stu-id="f6dc2-124">Other</span></span>

<span data-ttu-id="f6dc2-125">"其他"可能包括各种来源的能耗，如磁盘活动、移动宽带使用情况和内部抵制消耗的能耗。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-125">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="f6dc2-126">可以使用右上角的菜单筛选此视图以仅显示前台应用和/或后台应用。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-126">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="f6dc2-127">前台应用是过去 28 天内具有用户交互的应用，例如使用鼠标选择内容。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-127">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="f6dc2-128">见解</span><span class="sxs-lookup"><span data-stu-id="f6dc2-128">Insights</span></span>

<span data-ttu-id="f6dc2-129">**Insights** 区域显示了 CPU 和网络类别中前三个能源使用者。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-129">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="f6dc2-130">这些项目消耗的能耗高于所有部署Microsoft 托管桌面消耗。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-130">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="f6dc2-131">我们不显示显示资源，因为它很大程度上取决于设备使用时间和屏幕亮度设置。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-131">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="f6dc2-132">有关详细信息，请选择" **详细信息"** 列中的一览。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-132">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="f6dc2-133">电池优化</span><span class="sxs-lookup"><span data-stu-id="f6dc2-133">Battery optimization</span></span>

<span data-ttu-id="f6dc2-134">Windows 10提供[大量设备设置](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)，以改进电源使用并提高设备Microsoft 托管桌面时间。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-134">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="f6dc2-135">其中某些设置可能会降低Windows功能，因此你还必须考虑其他因素，例如设备在组织中的角色。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-135">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="f6dc2-136">Windows维护这些电池节省提示[的列表](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-136">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="f6dc2-137">用户可以自行调整某些设置，而无需管理员提升或支持。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-137">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="f6dc2-138">其他设置需要组织的 IT 管理员提供支持。</span><span class="sxs-lookup"><span data-stu-id="f6dc2-138">Other settings require support from your organization's IT administrator.</span></span>
