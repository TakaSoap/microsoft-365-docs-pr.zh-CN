---
title: 设备时间线中的技术
description: 了解 Microsoft Defender for Endpoint 中的设备时间线
keywords: 设备时间线， 终结点， MITRE， MITRE ATT&CK， 技术， 策略
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: 6b080c209292c8cac1aa64d748926734f4be964c
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51185463"
---
# <a name="techniques-in-the-device-timeline"></a><span data-ttu-id="e5e3b-104">设备时间线中的技术</span><span class="sxs-lookup"><span data-stu-id="e5e3b-104">Techniques in the device timeline</span></span>


<span data-ttu-id="e5e3b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e5e3b-105">**Applies to:**</span></span>
- [<span data-ttu-id="e5e3b-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="e5e3b-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)


<span data-ttu-id="e5e3b-107">通过分析特定设备上发生的事件，你可以获取调查的更多见解。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-107">You can gain more insight in an investigation by analyzing the events that happened on a specific device.</span></span> <span data-ttu-id="e5e3b-108">首先，从设备列表中选择 [感兴趣的设备](machines-view-overview.md)。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-108">First, select the device of interest from the [Devices list](machines-view-overview.md).</span></span> <span data-ttu-id="e5e3b-109">在设备页面上，可以选择"时间线"选项卡以查看设备上发生的所有事件。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-109">On the device page, you can select the **Timeline** tab to view all the events that occurred on the device.</span></span>

## <a name="understand-techniques-in-the-timeline"></a><span data-ttu-id="e5e3b-110">了解时间线中的技术</span><span class="sxs-lookup"><span data-stu-id="e5e3b-110">Understand techniques in the timeline</span></span>

>[!IMPORTANT]
><span data-ttu-id="e5e3b-111">某些信息与公共预览版中预发布的产品功能相关，在商业发行之前可能会对其进行重大修改。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-111">Some information relates to a prereleased product feature in public preview which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="e5e3b-112">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-112">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="e5e3b-113">在 Microsoft Defender for Endpoint 中 **，** 技术是数据类型时间线中的附加功能。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-113">In Microsoft Defender for Endpoint, **Techniques** are an additional data type in the event timeline.</span></span> <span data-ttu-id="e5e3b-114">技术提供有关与 [MITRE ATT](https://attack.mitre.org/) 和 CK 技术&子技术相关的活动的更多见解。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-114">Techniques provide more insight on activities associated with [MITRE ATT&CK](https://attack.mitre.org/) techniques or sub-techniques.</span></span> 

<span data-ttu-id="e5e3b-115">此功能通过帮助分析员了解在设备上观察到的活动来简化调查体验。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-115">This feature simplifies the investigation experience by helping analysts understand the activities that were observed on a device.</span></span> <span data-ttu-id="e5e3b-116">然后，分析员可以决定进一步进行调查。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-116">Analysts can then decide to investigate further.</span></span>

<span data-ttu-id="e5e3b-117">对于公共预览，技术默认可用，在查看设备的时间线时与事件一起显示。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-117">For public preview, Techniques are available by default and shown together with events when a device's timeline is viewed.</span></span> 

![设备时间线屏幕截图中的技术](images/device-timeline-2.png)

<span data-ttu-id="e5e3b-119">技术以粗体文本突出显示，左侧显示蓝色图标。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-119">Techniques are highlighted in bold text and appear with a blue icon on the left.</span></span> <span data-ttu-id="e5e3b-120">相应的 MITRE ATT&CK ID 和技术名称也显示为其他信息下的标记。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-120">The corresponding MITRE ATT&CK ID and technique name also appear as tags under Additional information.</span></span> 

<span data-ttu-id="e5e3b-121">搜索和导出选项还可用于技术。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-121">Search and Export options are also available for Techniques.</span></span>

## <a name="investigate-using-the-side-pane"></a><span data-ttu-id="e5e3b-122">使用侧窗格进行调查</span><span class="sxs-lookup"><span data-stu-id="e5e3b-122">Investigate using the side pane</span></span>

<span data-ttu-id="e5e3b-123">选择一种技术以打开其对应的侧窗格。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-123">Select a Technique to open its corresponding side pane.</span></span> <span data-ttu-id="e5e3b-124">你可以在此处查看其他信息和见解，如相关的 ATT&CK 技术、策略和说明。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-124">Here you can see additional information and insights like related ATT&CK techniques, tactics, and descriptions.</span></span> 

<span data-ttu-id="e5e3b-125">选择特定 *攻击技术* 以打开相关 ATT&CK 技术页面，可在其中找到有关它的信息。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-125">Select the specific *Attack technique* to open the related ATT&CK technique page where you can find more information about it.</span></span>

<span data-ttu-id="e5e3b-126">在右侧看到蓝色图标时，可以复制实体的详细信息。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-126">You can copy an entity's details when you see a blue icon on the right.</span></span> <span data-ttu-id="e5e3b-127">例如，若要复制相关文件的 SHA1，请选择蓝色页面图标。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-127">For instance, to copy a related file's SHA1, select the blue page icon.</span></span>

![复制实体详细信息](images/techniques-side-pane-clickable.png)

<span data-ttu-id="e5e3b-129">您可以对命令行执行相同的操作。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-129">You can do the same for command lines.</span></span>

![复制命令行](images/techniques-side-pane-command.png)


## <a name="investigate-related-events"></a><span data-ttu-id="e5e3b-131">调查相关事件</span><span class="sxs-lookup"><span data-stu-id="e5e3b-131">Investigate related events</span></span>

<span data-ttu-id="e5e3b-132">若要使用 [高级搜寻](advanced-hunting-overview.md) 查找与所选技术相关的事件，请选择 **"搜寻"查找相关事件**。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-132">To use [advanced hunting](advanced-hunting-overview.md) to find events related to the selected Technique, select **Hunt for related events**.</span></span> <span data-ttu-id="e5e3b-133">这将导致高级搜寻页面，该页面包含一个查询，用于查找与技术相关的事件。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-133">This leads to the advanced hunting page with a query to find events related to the Technique.</span></span>

![搜寻相关事件](images/techniques-hunt-for-related-events.png)

>[!NOTE]
><span data-ttu-id="e5e3b-135">使用"技术"侧窗格中的 **"搜寻** 相关事件"按钮进行查询将显示与标识的技术相关的所有事件，但不包括技术本身在查询结果中。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-135">Querying using the **Hunt for related events** button from a Technique side pane displays all the events related to the identified technique but does not include the Technique itself in the query results.</span></span>


## <a name="customize-your-device-timeline"></a><span data-ttu-id="e5e3b-136">自定义设备时间线</span><span class="sxs-lookup"><span data-stu-id="e5e3b-136">Customize your device timeline</span></span>

<span data-ttu-id="e5e3b-137">在设备时间线的右上角，你可以选择一个日期范围来限制时间线中的事件和技术数量。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-137">On the upper right-hand side of the device timeline, you can choose a date range to limit the number of events and techniques in the timeline.</span></span> 

<span data-ttu-id="e5e3b-138">您可以自定义要公开哪些列。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-138">You can customize which columns to expose.</span></span> <span data-ttu-id="e5e3b-139">您还可以按事件组或事件组数据类型标记的事件。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-139">You can also filter for flagged events by data type or by event group.</span></span>

### <a name="choose-columns-to-expose"></a><span data-ttu-id="e5e3b-140">选择要公开列</span><span class="sxs-lookup"><span data-stu-id="e5e3b-140">Choose columns to expose</span></span>
<span data-ttu-id="e5e3b-141">可以通过选择"选择列"按钮选择要在日程表 **中公开哪些** 列。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-141">You can choose which columns to expose in the timeline by selecting the **Choose columns** button.</span></span>

![自定义列](images/filter-customize-columns.png)

<span data-ttu-id="e5e3b-143">可以从中选择要包含的信息集。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-143">From there you can select which information set to include.</span></span>

### <a name="filter-to-view-techniques-or-events-only"></a><span data-ttu-id="e5e3b-144">筛选以仅查看技术或事件</span><span class="sxs-lookup"><span data-stu-id="e5e3b-144">Filter to view techniques or events only</span></span>

<span data-ttu-id="e5e3b-145">若要仅查看事件或技术， **请从设备** 时间线选择筛选器，然后选择要查看的首选数据类型。</span><span class="sxs-lookup"><span data-stu-id="e5e3b-145">To view only either events or techniques, select **Filters** from the device timeline and choose your preferred Data type to view.</span></span>

![筛选器屏幕截图](images/device-timeline-filters.png)



## <a name="see-also"></a><span data-ttu-id="e5e3b-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e5e3b-147">See also</span></span>
- [<span data-ttu-id="e5e3b-148">查看和组织"设备"列表</span><span class="sxs-lookup"><span data-stu-id="e5e3b-148">View and organize the Devices list</span></span>](machines-view-overview.md)
- [<span data-ttu-id="e5e3b-149">Microsoft Defender for Endpoint 设备时间线事件标志</span><span class="sxs-lookup"><span data-stu-id="e5e3b-149">Microsoft Defender for Endpoint device timeline event flags</span></span>](device-timeline-event-flag.md) 


 
