---
title: 调查 Microsoft Defender for Endpoint 警报
description: 使用调查选项获取有关影响网络的警报的详细信息、它们的含义以及如何解决它们。
keywords: 调查， 调查， 设备， 设备， 警报队列， 仪表板， IP 地址， 文件， 提交， 提交， 深入分析， 时间线， 搜索， 域， URL， IP
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
ms.openlocfilehash: 626be9e949170fcda1f0bcf2a88e1b9780bbe764
ms.sourcegitcommit: 4fb1226d5875bf5b9b29252596855a6562cea9ae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52841086"
---
# <a name="investigate-alerts-in-microsoft-defender-for-endpoint"></a><span data-ttu-id="b3c80-104">调查 Microsoft Defender for Endpoint 中的警报</span><span class="sxs-lookup"><span data-stu-id="b3c80-104">Investigate alerts in Microsoft Defender for Endpoint</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="b3c80-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b3c80-105">**Applies to:**</span></span>
- [<span data-ttu-id="b3c80-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b3c80-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="b3c80-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b3c80-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="b3c80-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="b3c80-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="b3c80-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="b3c80-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatealerts-abovefoldlink) 

<span data-ttu-id="b3c80-110">调查影响网络的警报，了解它们的含义以及如何解决它们。</span><span class="sxs-lookup"><span data-stu-id="b3c80-110">Investigate alerts that are affecting your network, understand what they mean, and how to resolve them.</span></span>

<span data-ttu-id="b3c80-111">从警报队列中选择警报以转到警报页面。</span><span class="sxs-lookup"><span data-stu-id="b3c80-111">Select an alert from the alerts queue to go to alert page.</span></span> <span data-ttu-id="b3c80-112">此视图包含警报标题、受影响的资产、详细信息侧窗格和警报情景。</span><span class="sxs-lookup"><span data-stu-id="b3c80-112">This view contains the alert title, the affected assets, the details side pane, and the alert story.</span></span>

<span data-ttu-id="b3c80-113">从警报页面，通过选择警报情景树视图下受影响的资产或任何实体开始调查。</span><span class="sxs-lookup"><span data-stu-id="b3c80-113">From the alert page, begin your investigation by selecting the affected assets or any of the entities under the alert story tree view.</span></span> <span data-ttu-id="b3c80-114">详细信息窗格将自动填充有关所选内容的详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3c80-114">The details pane automatically populates with further information about what you selected.</span></span> <span data-ttu-id="b3c80-115">若要查看可以在此处查看的信息类型，请阅读查看 Microsoft [Defender for Endpoint 中的警报](/microsoft-365/security/defender-endpoint/review-alerts)。</span><span class="sxs-lookup"><span data-stu-id="b3c80-115">To see what kind of information you can view here, read [Review alerts in Microsoft Defender for Endpoint](/microsoft-365/security/defender-endpoint/review-alerts).</span></span>

## <a name="investigate-using-the-alert-story"></a><span data-ttu-id="b3c80-116">使用警报情景进行调查</span><span class="sxs-lookup"><span data-stu-id="b3c80-116">Investigate using the alert story</span></span>

<span data-ttu-id="b3c80-117">警报情景详细介绍了触发警报的原因、之前和之后发生的相关事件以及其他相关实体。</span><span class="sxs-lookup"><span data-stu-id="b3c80-117">The alert story details why the alert was triggered, related events that happened before and after, as well as other related entities.</span></span>

<span data-ttu-id="b3c80-118">实体是可单击的，并且每个不是警报的实体都可用该实体卡片右侧展开图标进行扩展。</span><span class="sxs-lookup"><span data-stu-id="b3c80-118">Entities are clickable and every entity that isn't an alert is expandable using the expand icon on the right side of that entity's card.</span></span> <span data-ttu-id="b3c80-119">焦点中的实体将用该实体卡片左侧的蓝色条带指示，标题中的警报首先处于焦点。</span><span class="sxs-lookup"><span data-stu-id="b3c80-119">The entity in focus will be indicated by a blue stripe to the left side of that entity's card, with the alert in the title being in focus at first.</span></span>

<span data-ttu-id="b3c80-120">展开实体，一目了然地查看详细信息。</span><span class="sxs-lookup"><span data-stu-id="b3c80-120">Expand entities to view details at a glance.</span></span> <span data-ttu-id="b3c80-121">选择实体将详细信息窗格的上下文切换到此实体，并允许您查看详细信息以及管理该实体。</span><span class="sxs-lookup"><span data-stu-id="b3c80-121">Selecting an entity will switch the context of the details pane to this entity, and will allow you to review further information, as well as manage that entity.</span></span> <span data-ttu-id="b3c80-122">选择 *实体* 卡片右侧"..."将显示该实体的所有可用操作。</span><span class="sxs-lookup"><span data-stu-id="b3c80-122">Selecting *...* to the right of the entity card will reveal all actions available for that entity.</span></span> <span data-ttu-id="b3c80-123">当实体具有焦点时，这些相同的操作将显示在详细信息窗格中。</span><span class="sxs-lookup"><span data-stu-id="b3c80-123">These same actions appear in the details pane when that entity is in focus.</span></span>

> [!NOTE]
> <span data-ttu-id="b3c80-124">警报情景部分可能包含多个警报，与相同执行树相关的其他警报显示在所选警报之前或之后。</span><span class="sxs-lookup"><span data-stu-id="b3c80-124">The alert story section may contain more than one alert, with additional alerts related to the same execution tree appearing before or after the alert you've selected.</span></span>

![具有焦点的警报和一些扩展卡片的警报情景示例](images/alert-story-tree.png)

## <a name="take-action-from-the-details-pane"></a><span data-ttu-id="b3c80-126">从详细信息窗格中采取操作</span><span class="sxs-lookup"><span data-stu-id="b3c80-126">Take action from the details pane</span></span>

<span data-ttu-id="b3c80-127">选择感兴趣的实体后，详细信息窗格将更改为显示有关所选实体类型的信息、可用时的历史信息，并提供直接从警报页面对此实体采取措施的控件。 </span><span class="sxs-lookup"><span data-stu-id="b3c80-127">Once you've selected an entity of interest, the details pane will change to display information about the selected entity type, historic information when it's available, and offer controls to **take action** on this entity directly from the alert page.</span></span>

<span data-ttu-id="b3c80-128">完成调查后，返回到开始使用的警报，将警报状态标记为"已解决"，然后将其分类为 **"False 警报**"或"**真警报"。** </span><span class="sxs-lookup"><span data-stu-id="b3c80-128">Once you're done investigating, go back to the alert you started with, mark the alert's status as **Resolved** and classify it as either **False alert** or **True alert**.</span></span> <span data-ttu-id="b3c80-129">对警报进行分类有助于调整此功能，以提供更多真实警报和更少的假警报。</span><span class="sxs-lookup"><span data-stu-id="b3c80-129">Classifying alerts helps tune this capability to provide more true alerts and less false alerts.</span></span>

<span data-ttu-id="b3c80-130">如果将其分类为真正的警报，则还可以选择一个决定，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="b3c80-130">If you classify it as a true alert, you can also select a determination, as shown in the image below.</span></span>

![详细信息窗格的代码段，其中展开已解决警报和确定下拉列表](images/alert-details-resolved-true.png)

<span data-ttu-id="b3c80-132">如果业务线应用程序遇到错误警报，请创建抑制规则以避免将来出现此类型的警报。</span><span class="sxs-lookup"><span data-stu-id="b3c80-132">If you are experiencing a false alert with a line-of-business application, create a suppression rule to avoid this type of alert in the future.</span></span>

![突出显示抑制规则的详细信息窗格中的操作和分类](images/alert-false-suppression-rule.png)

> [!TIP]
> <span data-ttu-id="b3c80-134">如果遇到上面未介绍的任何问题，请使用按钮 🙂 提供反馈或打开支持票证。</span><span class="sxs-lookup"><span data-stu-id="b3c80-134">If you're experiencing any issues not described above, use the 🙂 button to provide feedback or open a support ticket.</span></span>


## <a name="related-topics"></a><span data-ttu-id="b3c80-135">相关主题</span><span class="sxs-lookup"><span data-stu-id="b3c80-135">Related topics</span></span>
- [<span data-ttu-id="b3c80-136">查看和组织 Microsoft Defender 终结点警报队列</span><span class="sxs-lookup"><span data-stu-id="b3c80-136">View and organize the Microsoft Defender for Endpoint Alerts queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="b3c80-137">管理 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="b3c80-137">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="b3c80-138">调查与 Defender for Endpoint 警报关联的文件</span><span class="sxs-lookup"><span data-stu-id="b3c80-138">Investigate a file associated with a Defender for Endpoint alert</span></span>](investigate-files.md)
- [<span data-ttu-id="b3c80-139">调查 Defender for Endpoint Devices 列表中的设备</span><span class="sxs-lookup"><span data-stu-id="b3c80-139">Investigate devices in the Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="b3c80-140">调查与 Defender for Endpoint 警报关联的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="b3c80-140">Investigate an IP address associated with a Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="b3c80-141">调查与 Defender for Endpoint 警报关联的域</span><span class="sxs-lookup"><span data-stu-id="b3c80-141">Investigate a domain associated with a Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="b3c80-142">调查 Defender for Endpoint 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="b3c80-142">Investigate a user account in Defender for Endpoint</span></span>](investigate-user.md)


