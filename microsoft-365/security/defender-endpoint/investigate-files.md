---
title: 调查适用于终结点的 Microsoft Defender 文件
description: 使用调查选项获取有关与警报、行为或事件相关联的文件的详细信息。
keywords: 调查， 调查， 文件， 恶意活动， 攻击动机， 深度分析， 深度分析报告
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
ms.openlocfilehash: b509ab6d0c3e5183b99173e950198bad0ccd8ee0
ms.sourcegitcommit: 6f2288e0c863496dfd0ee38de754bd43096ab3e1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/24/2021
ms.locfileid: "51186061"
---
# <a name="investigate-a-file-associated-with-a-microsoft-defender-for-endpoint-alert"></a><span data-ttu-id="4f57f-104">调查与 Microsoft Defender for Endpoint 警报关联的文件</span><span class="sxs-lookup"><span data-stu-id="4f57f-104">Investigate a file associated with a Microsoft Defender for Endpoint alert</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="4f57f-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="4f57f-105">**Applies to:**</span></span>
- [<span data-ttu-id="4f57f-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="4f57f-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="4f57f-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="4f57f-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)


><span data-ttu-id="4f57f-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="4f57f-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="4f57f-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="4f57f-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-investigatefiles-abovefoldlink)

<span data-ttu-id="4f57f-110">调查与特定警报、行为或事件相关联的文件的详细信息，以帮助确定文件是否呈现恶意活动、确定攻击动机并了解漏洞的潜在范围。</span><span class="sxs-lookup"><span data-stu-id="4f57f-110">Investigate the details of a file associated with a specific alert, behavior, or event to help determine if the file exhibits malicious activities, identify the attack motivation, and understand the potential scope of the breach.</span></span>

<span data-ttu-id="4f57f-111">有许多方法可以访问特定文件的详细配置文件页。</span><span class="sxs-lookup"><span data-stu-id="4f57f-111">There are many ways to access the detailed profile page of a specific file.</span></span> <span data-ttu-id="4f57f-112">例如，可以使用搜索功能、单击警报进程树中的链接、事件 **图**、项目时间线，或选择设备时间线中列出的 **事件**。</span><span class="sxs-lookup"><span data-stu-id="4f57f-112">For example, you can  use the search feature, click on a link from the **Alert process tree**, **Incident graph**, **Artifact timeline**, or select an event listed in the **Device timeline**.</span></span>

<span data-ttu-id="4f57f-113">进入详细的配置文件页面后，可以通过切换新的文件页面在新的和旧的页面布局 **之间切换**。</span><span class="sxs-lookup"><span data-stu-id="4f57f-113">Once on the detailed profile page, you can switch between the new and old page layouts by toggling **new File page**.</span></span> <span data-ttu-id="4f57f-114">本文的其余部分介绍了较新的页面布局。</span><span class="sxs-lookup"><span data-stu-id="4f57f-114">The rest of this article describes the newer page layout.</span></span>

<span data-ttu-id="4f57f-115">可以从文件视图中的以下部分获取信息：</span><span class="sxs-lookup"><span data-stu-id="4f57f-115">You can get information from the following sections in the file view:</span></span>

- <span data-ttu-id="4f57f-116">文件详细信息， 恶意软件检测， 文件普遍程度</span><span class="sxs-lookup"><span data-stu-id="4f57f-116">File details, Malware detection, File prevalence</span></span>
- <span data-ttu-id="4f57f-117">深度分析</span><span class="sxs-lookup"><span data-stu-id="4f57f-117">Deep analysis</span></span>
- <span data-ttu-id="4f57f-118">警报</span><span class="sxs-lookup"><span data-stu-id="4f57f-118">Alerts</span></span>
- <span data-ttu-id="4f57f-119">在组织中观测到</span><span class="sxs-lookup"><span data-stu-id="4f57f-119">Observed in organization</span></span>
- <span data-ttu-id="4f57f-120">深度分析</span><span class="sxs-lookup"><span data-stu-id="4f57f-120">Deep analysis</span></span>
- <span data-ttu-id="4f57f-121">文件名</span><span class="sxs-lookup"><span data-stu-id="4f57f-121">File names</span></span>

<span data-ttu-id="4f57f-122">您还可以从此页对文件采取操作。</span><span class="sxs-lookup"><span data-stu-id="4f57f-122">You can also take action on a file from this page.</span></span>

## <a name="file-actions"></a><span data-ttu-id="4f57f-123">文件操作</span><span class="sxs-lookup"><span data-stu-id="4f57f-123">File actions</span></span>

<span data-ttu-id="4f57f-124">在配置文件页面顶部，在文件信息卡上方。</span><span class="sxs-lookup"><span data-stu-id="4f57f-124">Along the top of the profile page, above the file information cards.</span></span> <span data-ttu-id="4f57f-125">可在此处执行的操作包括：</span><span class="sxs-lookup"><span data-stu-id="4f57f-125">Actions you can perform here include:</span></span>

- <span data-ttu-id="4f57f-126">停止和隔离</span><span class="sxs-lookup"><span data-stu-id="4f57f-126">Stop and quarantine</span></span>
- <span data-ttu-id="4f57f-127">添加/编辑指示器</span><span class="sxs-lookup"><span data-stu-id="4f57f-127">Add/edit indicator</span></span>
- <span data-ttu-id="4f57f-128">下载文件</span><span class="sxs-lookup"><span data-stu-id="4f57f-128">Download file</span></span>
- <span data-ttu-id="4f57f-129">咨询威胁专家</span><span class="sxs-lookup"><span data-stu-id="4f57f-129">Consult a threat expert</span></span>
- <span data-ttu-id="4f57f-130">操作中心</span><span class="sxs-lookup"><span data-stu-id="4f57f-130">Action center</span></span>

<span data-ttu-id="4f57f-131">有关这些操作详细信息，请参阅 [对文件执行响应操作](respond-file-alerts.md)。</span><span class="sxs-lookup"><span data-stu-id="4f57f-131">For more information on these actions, see [Take response action on a file](respond-file-alerts.md).</span></span>

## <a name="file-details-malware-detection-and-file-prevalence"></a><span data-ttu-id="4f57f-132">文件详细信息、恶意软件检测和文件普遍程度</span><span class="sxs-lookup"><span data-stu-id="4f57f-132">File details, Malware detection, and File prevalence</span></span>

<span data-ttu-id="4f57f-133">文件详细信息、事件、恶意软件检测和文件流行卡片显示有关文件的各种属性。</span><span class="sxs-lookup"><span data-stu-id="4f57f-133">The file details, incident, malware detection, and file prevalence cards display various attributes about the file.</span></span>

<span data-ttu-id="4f57f-134">你将看到详细信息，如文件的 MD5、病毒总检测比率和 Microsoft Defender AV 检测（如果可用）以及文件的普遍程度。</span><span class="sxs-lookup"><span data-stu-id="4f57f-134">You'll see details such as the file’s MD5, the Virus Total detection ratio, and Microsoft Defender AV detection if available, and the file’s prevalence.</span></span>

<span data-ttu-id="4f57f-135">文件流行卡片显示文件在组织和全球的设备中的显示位置。</span><span class="sxs-lookup"><span data-stu-id="4f57f-135">The file prevalence card shows where the file was seen in devices in the organization and worldwide.</span></span> 

> [!NOTE] 
> <span data-ttu-id="4f57f-136">不同的用户可能会看到不同值在文件流行卡片的"组织单位"部分中。</span><span class="sxs-lookup"><span data-stu-id="4f57f-136">Different users may see dissimilar values in the *devices in organization* section of the file prevalence card.</span></span> <span data-ttu-id="4f57f-137">这是因为卡片显示基于用户具有的 RBAC 范围的信息。</span><span class="sxs-lookup"><span data-stu-id="4f57f-137">This is because the card displays information based on the RBAC scope that a user has.</span></span> <span data-ttu-id="4f57f-138">这意味着，如果用户已被授予对一组特定设备的可见性，他们只会看到这些设备上的文件组织普遍程度。</span><span class="sxs-lookup"><span data-stu-id="4f57f-138">Meaning, if a user has been granted visibility on a specific set of devices, they will only see the file organizational prevalence on those devices.</span></span>

![文件信息的图像](images/atp-file-information.png)

## <a name="alerts"></a><span data-ttu-id="4f57f-140">警报</span><span class="sxs-lookup"><span data-stu-id="4f57f-140">Alerts</span></span>

<span data-ttu-id="4f57f-141">" **警报** "选项卡提供与文件关联的警报列表。</span><span class="sxs-lookup"><span data-stu-id="4f57f-141">The **Alerts** tab provides a list of alerts that are associated with the file.</span></span> <span data-ttu-id="4f57f-142">此列表涵盖了大部分与警报队列相同的信息，但受影响的设备所属的设备组（如果有）除外。</span><span class="sxs-lookup"><span data-stu-id="4f57f-142">This list covers much of the same information as the Alerts queue, except for the device group, if any, the affected device belongs to.</span></span> <span data-ttu-id="4f57f-143">您可以通过从列标题上方的工具栏中选择"自定义列"来选择显示的信息类型。</span><span class="sxs-lookup"><span data-stu-id="4f57f-143">You can choose what kind of information is shown by selecting **Customize columns** from the toolbar above the column headers.</span></span>

![与文件部分相关的警报的图像](images/atp-alerts-related-to-file.png)

## <a name="observed-in-organization"></a><span data-ttu-id="4f57f-145">在组织中观测到</span><span class="sxs-lookup"><span data-stu-id="4f57f-145">Observed in organization</span></span>

<span data-ttu-id="4f57f-146">" **在组织中观测** 到"选项卡允许你指定日期范围，以查看已使用该文件观测到哪些设备。</span><span class="sxs-lookup"><span data-stu-id="4f57f-146">The **Observed in organization** tab allows you to specify a date range to see which devices have been observed with the file.</span></span>

>[!NOTE]
><span data-ttu-id="4f57f-147">此选项卡将显示最多 100 台设备。</span><span class="sxs-lookup"><span data-stu-id="4f57f-147">This tab will show a maximum number of 100 devices.</span></span> <span data-ttu-id="4f57f-148">To see _all_ devices with the file， export the tab to a CSV file， by selecting **Export** from the action menu above the tab's column headers.</span><span class="sxs-lookup"><span data-stu-id="4f57f-148">To see _all_ devices with the file, export the tab to a CSV file, by selecting **Export** from the action menu above the tab's column headers.</span></span>

![最新观察到的设备与文件的图像](images/atp-observed-machines.png)

<span data-ttu-id="4f57f-150">使用滑块或范围选择器快速指定要检查与文件有关的事件的时间段。</span><span class="sxs-lookup"><span data-stu-id="4f57f-150">Use the slider or the range selector to quickly specify a time period that you want to check for events involving the file.</span></span> <span data-ttu-id="4f57f-151">可以将时间窗口指定为一天。</span><span class="sxs-lookup"><span data-stu-id="4f57f-151">You can specify a time window as small as a single day.</span></span> <span data-ttu-id="4f57f-152">这样一来，你只能看到当时与该 IP 地址通信的文件，从而大大减少了不必要的滚动和搜索。</span><span class="sxs-lookup"><span data-stu-id="4f57f-152">This will allow you to see only files that communicated with that IP Address at that time, drastically reducing unnecessary scrolling and searching.</span></span>

## <a name="deep-analysis"></a><span data-ttu-id="4f57f-153">深度分析</span><span class="sxs-lookup"><span data-stu-id="4f57f-153">Deep analysis</span></span>

<span data-ttu-id="4f57f-154">"**深度** 分析"选项卡允许您提交 [](respond-file-alerts.md#deep-analysis)文件进行深入分析，以发现有关文件行为的更多详细信息，以及文件在组织中的影响。</span><span class="sxs-lookup"><span data-stu-id="4f57f-154">The **Deep analysis** tab allows you to [submit the file for deep analysis](respond-file-alerts.md#deep-analysis), to uncover more details about the file's behavior, as well as the effect it is having within your organizations.</span></span> <span data-ttu-id="4f57f-155">提交文件后，一旦结果可用，深入分析报告将显示在此选项卡中。</span><span class="sxs-lookup"><span data-stu-id="4f57f-155">After you submit the file, the deep analysis report will appear in this tab once results are available.</span></span> <span data-ttu-id="4f57f-156">如果深度分析找不到任何内容，则报告将为空，并且结果空间将保留为空。</span><span class="sxs-lookup"><span data-stu-id="4f57f-156">If deep analysis did not find anything, the report will be empty and the results space will remain blank.</span></span>

![深入分析选项卡的图像](images/submit-file.png)

## <a name="file-names"></a><span data-ttu-id="4f57f-158">文件名</span><span class="sxs-lookup"><span data-stu-id="4f57f-158">File names</span></span>

<span data-ttu-id="4f57f-159">" **文件名** "选项卡列出了观测到的文件在组织中使用的所有名称。</span><span class="sxs-lookup"><span data-stu-id="4f57f-159">The **File names** tab lists all names the file has been observed to use, within your organizations.</span></span>

![文件名选项卡的图像](images/atp-file-names.png)

## <a name="related-topics"></a><span data-ttu-id="4f57f-161">相关主题</span><span class="sxs-lookup"><span data-stu-id="4f57f-161">Related topics</span></span>

- [<span data-ttu-id="4f57f-162">查看和组织 Microsoft Defender 终结点队列</span><span class="sxs-lookup"><span data-stu-id="4f57f-162">View and organize the Microsoft Defender for Endpoint queue</span></span>](alerts-queue.md)
- [<span data-ttu-id="4f57f-163">管理 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="4f57f-163">Manage Microsoft Defender for Endpoint alerts</span></span>](manage-alerts.md)
- [<span data-ttu-id="4f57f-164">调查 Microsoft Defender for Endpoint 警报</span><span class="sxs-lookup"><span data-stu-id="4f57f-164">Investigate Microsoft Defender for Endpoint alerts</span></span>](investigate-alerts.md)
- [<span data-ttu-id="4f57f-165">调查 Microsoft Defender 终结点设备列表中的设备</span><span class="sxs-lookup"><span data-stu-id="4f57f-165">Investigate devices in the Microsoft Defender for Endpoint Devices list</span></span>](investigate-machines.md)
- [<span data-ttu-id="4f57f-166">调查与 Microsoft Defender for Endpoint 警报关联的 IP 地址</span><span class="sxs-lookup"><span data-stu-id="4f57f-166">Investigate an IP address associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-ip.md)
- [<span data-ttu-id="4f57f-167">调查与 Microsoft Defender for Endpoint 警报关联的域</span><span class="sxs-lookup"><span data-stu-id="4f57f-167">Investigate a domain associated with a Microsoft Defender for Endpoint alert</span></span>](investigate-domain.md)
- [<span data-ttu-id="4f57f-168">调查 Microsoft Defender for Endpoint 中的用户帐户</span><span class="sxs-lookup"><span data-stu-id="4f57f-168">Investigate a user account in Microsoft Defender for Endpoint</span></span>](investigate-user.md)
- [<span data-ttu-id="4f57f-169">对文件执行响应操作</span><span class="sxs-lookup"><span data-stu-id="4f57f-169">Take response actions on a file</span></span>](respond-file-alerts.md)
