---
title: Microsoft Defender for Endpoint 中的设备运行状况和合规性报告
description: 使用设备运行状况和合规性报告跟踪Windows 10运行状况检测、防病毒状态、操作系统平台和版本
keywords: 运行状况状态， 防病毒， 操作系统平台， windows 10 版本， 版本， 运行状况， 合规性， 状态
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
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 35100a4b8bdaee23c427816450e948ced9ed3191
ms.sourcegitcommit: 22505ce322f68a2d0ce70d71caf3b0a657fa838a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/16/2021
ms.locfileid: "51860287"
---
# <a name="device-health-and-compliance-report-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="e769e-104">Microsoft Defender for Endpoint 中的设备运行状况和合规性报告</span><span class="sxs-lookup"><span data-stu-id="e769e-104">Device health and compliance report in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


<span data-ttu-id="e769e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e769e-105">**Applies to:**</span></span>
- [<span data-ttu-id="e769e-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e769e-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="e769e-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="e769e-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


> <span data-ttu-id="e769e-108">想要体验 Microsoft Defender for Endpoint？</span><span class="sxs-lookup"><span data-stu-id="e769e-108">Want to experience Microsoft Defender for Endpoint?</span></span> [<span data-ttu-id="e769e-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="e769e-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-exposedapis-abovefoldlink)

<span data-ttu-id="e769e-110">设备状态报告提供有关组织中设备的高级别信息。</span><span class="sxs-lookup"><span data-stu-id="e769e-110">The devices status report provides high-level information about the devices in your organization.</span></span> <span data-ttu-id="e769e-111">该报告包括显示传感器运行状况状态、防病毒状态、操作系统平台和Windows 10信息。</span><span class="sxs-lookup"><span data-stu-id="e769e-111">The report includes trending information showing the sensor health state, antivirus status, OS platforms, and Windows 10 versions.</span></span>

<span data-ttu-id="e769e-112">仪表板分为两个部分： ![ 设备报表的图像](images/device-reports.png)</span><span class="sxs-lookup"><span data-stu-id="e769e-112">The dashboard is structured into two sections: ![Image of the device report](images/device-reports.png)</span></span>
 
<span data-ttu-id="e769e-113">节</span><span class="sxs-lookup"><span data-stu-id="e769e-113">Section</span></span> | <span data-ttu-id="e769e-114">说明</span><span class="sxs-lookup"><span data-stu-id="e769e-114">Description</span></span>
:---|:---
<span data-ttu-id="e769e-115">1</span><span class="sxs-lookup"><span data-stu-id="e769e-115">1</span></span> | <span data-ttu-id="e769e-116">设备趋势</span><span class="sxs-lookup"><span data-stu-id="e769e-116">Device trends</span></span>
<span data-ttu-id="e769e-117">2</span><span class="sxs-lookup"><span data-stu-id="e769e-117">2</span></span> | <span data-ttu-id="e769e-118">设备摘要 (当天) </span><span class="sxs-lookup"><span data-stu-id="e769e-118">Device summary (current day)</span></span>
 
 
## <a name="device-trends"></a><span data-ttu-id="e769e-119">设备趋势</span><span class="sxs-lookup"><span data-stu-id="e769e-119">Device trends</span></span> 
<span data-ttu-id="e769e-120">默认情况下，设备趋势显示从 30 天到最后一整天结束的设备信息。</span><span class="sxs-lookup"><span data-stu-id="e769e-120">By default, the device trends displays device information from the 30-day period ending in the latest full day.</span></span> <span data-ttu-id="e769e-121">为了更好地了解组织中发生的趋势，您可以通过调整所显示的时间段来微调报告期间。</span><span class="sxs-lookup"><span data-stu-id="e769e-121">To gain better perspective on trends occurring in your organization, you can fine-tune the reporting period by adjusting the time period shown.</span></span> <span data-ttu-id="e769e-122">若要调整时间段，请从下拉列表选项中选择一个时间范围：</span><span class="sxs-lookup"><span data-stu-id="e769e-122">To adjust the time period, select a time range from the drop-down options:</span></span>
 
- <span data-ttu-id="e769e-123">30 天</span><span class="sxs-lookup"><span data-stu-id="e769e-123">30 days</span></span>
- <span data-ttu-id="e769e-124">3 个月</span><span class="sxs-lookup"><span data-stu-id="e769e-124">3 months</span></span>
- <span data-ttu-id="e769e-125">6 个月</span><span class="sxs-lookup"><span data-stu-id="e769e-125">6 months</span></span>
- <span data-ttu-id="e769e-126">自定义警报</span><span class="sxs-lookup"><span data-stu-id="e769e-126">Custom</span></span>

>[!NOTE]
><span data-ttu-id="e769e-127">这些筛选器仅应用于设备趋势部分。</span><span class="sxs-lookup"><span data-stu-id="e769e-127">These filters are only applied on the device trends section.</span></span> <span data-ttu-id="e769e-128">它不会影响设备摘要部分。</span><span class="sxs-lookup"><span data-stu-id="e769e-128">It doesn't affect the device summary section.</span></span>

## <a name="device-summary"></a><span data-ttu-id="e769e-129">设备摘要</span><span class="sxs-lookup"><span data-stu-id="e769e-129">Device summary</span></span> 
<span data-ttu-id="e769e-130">虽然设备趋势显示趋势设备信息，但设备摘要显示范围为当天的设备信息。</span><span class="sxs-lookup"><span data-stu-id="e769e-130">While the devices trends shows trending device information, the device summary shows device information scoped to the current day.</span></span> 

>[!NOTE]
><span data-ttu-id="e769e-131">摘要部分反映的数据的范围为当前日期之前的 180 天。</span><span class="sxs-lookup"><span data-stu-id="e769e-131">The data reflected in the summary section is scoped to 180 days prior to the current date.</span></span> <span data-ttu-id="e769e-132">例如，如果今天的日期为 2019 年 3 月 27 日，则摘要部分的数据将反映从 2018 年 9 月 28 日到 2019 年 3 月 27 日的数字。</span><span class="sxs-lookup"><span data-stu-id="e769e-132">For example if today's date is March 27, 2019, the data on the summary section will reflect numbers starting from September 28, 2018 to March 27, 2019.</span></span><br>
> <span data-ttu-id="e769e-133">对"趋势"部分应用的筛选器不会应用于摘要节。</span><span class="sxs-lookup"><span data-stu-id="e769e-133">The filter applied on the trends section is not applied on the summary section.</span></span> 
 
<span data-ttu-id="e769e-134">通过"设备趋势"部分，你可以向下钻取到应用了相应筛选器的设备列表。</span><span class="sxs-lookup"><span data-stu-id="e769e-134">The device trends section allows you to drill down to the devices list with the corresponding filter applied to it.</span></span> <span data-ttu-id="e769e-135">例如，单击"传感器运行状况状态卡"中的"非活动"栏将打开设备列表，其中仅显示其传感器状态处于非活动状态的设备。</span><span class="sxs-lookup"><span data-stu-id="e769e-135">For example, clicking on the Inactive bar in the Sensor health state card will bring you the devices list with results showing only devices whose sensor status is inactive.</span></span> 
 
 
 
## <a name="device-attributes"></a><span data-ttu-id="e769e-136">设备属性</span><span class="sxs-lookup"><span data-stu-id="e769e-136">Device attributes</span></span>
<span data-ttu-id="e769e-137">报告由显示以下设备属性的卡片所决定：</span><span class="sxs-lookup"><span data-stu-id="e769e-137">The report is made up of cards that display the following device attributes:</span></span>
 
- <span data-ttu-id="e769e-138">**运行状况：** 显示有关设备上传感器状态的信息，提供活动、通信受损、非活动或未看到传感器数据的设备的聚合视图。</span><span class="sxs-lookup"><span data-stu-id="e769e-138">**Health state**: shows information about the sensor state on devices, providing an aggregated view of devices that are active, experiencing impaired communications, inactive, or where no sensor data is seen.</span></span>
  
- <span data-ttu-id="e769e-139">**活动Windows 10防病毒状态**：显示设备数量和Microsoft Defender 防病毒。</span><span class="sxs-lookup"><span data-stu-id="e769e-139">**Antivirus status for active Windows 10 devices**: shows the number of devices and status of Microsoft Defender Antivirus.</span></span>
    
- <span data-ttu-id="e769e-140">**操作系统** 平台 ：显示存在于您的组织中的操作系统平台的分布。</span><span class="sxs-lookup"><span data-stu-id="e769e-140">**OS platforms**: shows the distribution of OS platforms that exists within your organization.</span></span> 
 
- <span data-ttu-id="e769e-141">**Windows 10版本**： 显示组织中Windows 10设备及其版本的分布。</span><span class="sxs-lookup"><span data-stu-id="e769e-141">**Windows 10 versions**: shows the distribution of Windows 10 devices and their versions in your organization.</span></span>
 
 
 
## <a name="filter-data"></a><span data-ttu-id="e769e-142">筛选数据</span><span class="sxs-lookup"><span data-stu-id="e769e-142">Filter data</span></span>
 
<span data-ttu-id="e769e-143">使用提供的筛选器包含或排除具有特定属性的设备。</span><span class="sxs-lookup"><span data-stu-id="e769e-143">Use the provided filters to include or exclude devices with certain attributes.</span></span>

<span data-ttu-id="e769e-144">你可以从设备属性中选择多个要应用筛选器。</span><span class="sxs-lookup"><span data-stu-id="e769e-144">You can select multiple filters to apply from the device attributes.</span></span> 
 
>[!NOTE]
><span data-ttu-id="e769e-145">这些筛选器适用于 **报告中** 的所有卡片。</span><span class="sxs-lookup"><span data-stu-id="e769e-145">These filters apply to **all** the cards in the report.</span></span>
 
<span data-ttu-id="e769e-146">例如，若要显示有关Windows 10传感器运行状况状态的设备的数据：</span><span class="sxs-lookup"><span data-stu-id="e769e-146">For example, to show data about Windows 10 devices with Active sensor health state:</span></span>
 
1. <span data-ttu-id="e769e-147">在 **筛选器>传感器运行状况状态>处于活动状态。**</span><span class="sxs-lookup"><span data-stu-id="e769e-147">Under **Filters > Sensor health state > Active**.</span></span>
2. <span data-ttu-id="e769e-148">然后选择操作系统 **平台> Windows 10。**</span><span class="sxs-lookup"><span data-stu-id="e769e-148">Then select **OS platforms > Windows 10**.</span></span>
3. <span data-ttu-id="e769e-149">选择 **应用**。</span><span class="sxs-lookup"><span data-stu-id="e769e-149">Select **Apply**.</span></span>


## <a name="related-topic"></a><span data-ttu-id="e769e-150">相关主题</span><span class="sxs-lookup"><span data-stu-id="e769e-150">Related topic</span></span>
- [<span data-ttu-id="e769e-151">威胁防护报告</span><span class="sxs-lookup"><span data-stu-id="e769e-151">Threat protection report</span></span>](threat-protection-reports.md)
