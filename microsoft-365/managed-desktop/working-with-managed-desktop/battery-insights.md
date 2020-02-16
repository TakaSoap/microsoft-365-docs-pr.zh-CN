---
title: 电池洞察力
description: ''
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 056685cbd49e6fb247a92357b3483b479d705c90
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42085723"
---
# <a name="battery-insights"></a><span data-ttu-id="fdd9c-103">电池洞察力</span><span class="sxs-lookup"><span data-stu-id="fdd9c-103">Battery insights</span></span>
<span data-ttu-id="fdd9c-104">此视图提供 Microsoft 托管桌面设备的电源、电池和应用使用指标。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-104">This view provides power, battery, and app usage metrics for your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fdd9c-105">出于这些目的，如果应用程序正在运行且处于焦点，则会被视为 "正在使用中"。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-105">For these purposes, an app is considered "in use" if it is running and in focus.</span></span>

<span data-ttu-id="fdd9c-106">若要查看使用率数据，请选择 "**电池**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-106">To view usage data, select the **Battery** tab.</span></span>

![电池窗格：左上角的每设备型号预测电池使用寿命（按应用）在底部右侧的 insights 表格中。](../../media/insights_battery.png)

## <a name="predicted-battery-life"></a><span data-ttu-id="fdd9c-109">预测电池寿命</span><span class="sxs-lookup"><span data-stu-id="fdd9c-109">Predicted battery life</span></span>

<span data-ttu-id="fdd9c-110">在**预测电池寿命**区域，我们根据设备型号对设备的预期电池寿命提供预测。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-110">In the **Predicted battery life** area, we provide predictions for the expected battery life for your devices, organized by device model.</span></span>

> [!NOTE]
> <span data-ttu-id="fdd9c-111">此数据源自 Microsoft 托管桌面部署中随机<em>选择</em>的设备（也报告数据）中的采样能源使用、使用时间和电池容量。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-111">This data is derived from sampling energy usage, usage time, and battery capacity from a random <em>selection</em> of the devices in your Microsoft Managed Desktop deployment that are also reporting data.</span></span>

<span data-ttu-id="fdd9c-112">该表提供了预计的电池寿命（以小时为单位）、其他 Microsoft 托管桌面部署中相同型号的平均电池寿命以及在您的环境中报告此数据的设备数量。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-112">The table provides the predicted battery life (in hours), average battery life for the same models in other Microsoft Managed Desktop deployments, and the number of devices reporting this data in your environment.</span></span> <span data-ttu-id="fdd9c-113">通过选择列标题对数据进行排序。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-113">Sort the data by selecting the column headings.</span></span>



## <a name="top-energy-consumers"></a><span data-ttu-id="fdd9c-114">热门能源消费者</span><span class="sxs-lookup"><span data-stu-id="fdd9c-114">Top energy consumers</span></span>

<span data-ttu-id="fdd9c-115">在 "**热门能源使用者**" 区域中，你将发现环境中的应用程序在 milliWatt 小时（mWh）内消耗最多能源。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-115">In the **Top energy consumers** area you’ll find the apps in your environment that consume the most energy in milliWatt-hours (mWh).</span></span> <span data-ttu-id="fdd9c-116">显示的应用程序以每个特定设备为依据，在左侧的**预测电池寿命**部分中选择。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-116">The apps shown are per specific device, which you select in the **Predicted battery life** section to the left.</span></span> <span data-ttu-id="fdd9c-117">例如，若要查看 Microsoft Surface Book 2 设备的每应用程序的消耗量，请在电池寿命区域中选择该行。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-117">For example, to see the per-app consumption for your Microsft Surface Book 2 devices, select that row in the battery life area.</span></span> <span data-ttu-id="fdd9c-118">如果不选择任何模型，则显示的应用程序使用数据适用于我们具有共同数据的所有应用程序。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-118">If you don't select any model, the app consumption data shown is for all apps that we have data for collectively.</span></span>

 <span data-ttu-id="fdd9c-119">对于每个应用程序，彩色网段显示了应用在这些类别中的能源使用情况：</span><span class="sxs-lookup"><span data-stu-id="fdd9c-119">For each app, colored segments show you the distribution of the app's energy use among these categories:</span></span>

- <span data-ttu-id="fdd9c-120">CPU</span><span class="sxs-lookup"><span data-stu-id="fdd9c-120">CPU</span></span>
- <span data-ttu-id="fdd9c-121">显示</span><span class="sxs-lookup"><span data-stu-id="fdd9c-121">Display</span></span>
- <span data-ttu-id="fdd9c-122">网络</span><span class="sxs-lookup"><span data-stu-id="fdd9c-122">Network</span></span>
- <span data-ttu-id="fdd9c-123">其他</span><span class="sxs-lookup"><span data-stu-id="fdd9c-123">Other</span></span>

<span data-ttu-id="fdd9c-124">"其他" 可能包括各种源（如磁盘活动、移动宽带使用）和对内部电阻断电的能源消耗。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-124">"Other" could include energy consumption by a variety of sources, such as disk activity, mobile broadband usage, and energy lost to internal resistance.</span></span> 

<span data-ttu-id="fdd9c-125">您可以使用右上角的菜单筛选此视图，以仅显示前台应用程序、后台应用程序或两者。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-125">You can filter this view to show only foreground apps, background apps, or both by using the menu in the upper right.</span></span> <span data-ttu-id="fdd9c-126">前台应用是指在最近28天内具有用户交互的应用程序，例如，使用鼠标选择一些内容。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-126">Foreground apps are those that have had user interaction in the last 28 days, such as selecting something with a mouse.</span></span>

## <a name="insights"></a><span data-ttu-id="fdd9c-127">见解</span><span class="sxs-lookup"><span data-stu-id="fdd9c-127">Insights</span></span>

<span data-ttu-id="fdd9c-128">**Insights**区域显示 CPU 和网络类别中的前三个能源使用者。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-128">The **Insights** area shows the top three energy consumers in the CPU and network categories.</span></span> <span data-ttu-id="fdd9c-129">与所有 Microsoft 托管桌面部署相比，这些项目的能源消耗高于平均能源。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-129">These items are consuming higher than average energy compared to all Microsoft Managed Desktop deployments.</span></span> <span data-ttu-id="fdd9c-130">不显示 "显示" 资源，因为它严重依赖于设备使用时间和屏幕亮度设置。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-130">We don't show the display resource because it depends heavily on device usage time and screen brightness settings.</span></span> 

<span data-ttu-id="fdd9c-131">有关详细信息，请选择 "**详细**信息" 列中的列表。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-131">Select the listings in the **Details** column for more information.</span></span>

## <a name="battery-optimization"></a><span data-ttu-id="fdd9c-132">电池优化</span><span class="sxs-lookup"><span data-stu-id="fdd9c-132">Battery optimization</span></span>

<span data-ttu-id="fdd9c-133">Windows 10 提供了大量[设备设置](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)，以提高电源使用并延长 Microsoft 托管桌面设备的电池使用寿命。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-133">Windows 10 offers numerous [device settings](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips) to improve power usage and increase the battery life of your Microsoft Managed Desktop devices.</span></span> <span data-ttu-id="fdd9c-134">其中一些设置可能会降低其他 Windows 功能，因此您还必须考虑其他因素，如组织中设备的角色。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-134">Some of these settings can decrease other Windows functionality, so you'll also have to consider other factors such as the role of the device in your organization.</span></span> <span data-ttu-id="fdd9c-135">Windows 支持维护这些[电池保存提示](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips)的列表。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-135">Windows support maintains a list of these [battery saving tips](https://support.microsoft.com/help/20443/windows-10-battery-saving-tips).</span></span>

<span data-ttu-id="fdd9c-136">用户无需进行管理员提升或支持，即可自行调整某些设置。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-136">Users can adjust some settings on their own without the need for admin elevation or support.</span></span> <span data-ttu-id="fdd9c-137">其他设置需要贵组织的 IT 管理员提供支持。</span><span class="sxs-lookup"><span data-stu-id="fdd9c-137">Other settings require support from your organization's IT administrator.</span></span>
