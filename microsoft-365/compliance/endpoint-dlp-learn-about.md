---
title: 了解 Microsoft 365 终结点数据丢失防护
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
localization_priority: Priority
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: 'Microsoft 365 终结点数据丢失防护可将对文件活动的监视和针对这些文件的保护措施扩展到终结点。 在 Microsoft 365 合规解决方案中将文件设为可见 '
ms.openlocfilehash: 3da15f1ac35ca448a76638c31f047c6a2132ad7a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454001"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="6821c-104">了解 Microsoft 365 终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="6821c-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="6821c-105">可以使用 Microsoft 365 数据丢失防护 (DLP) 来监视对确定为敏感的项目执行的操作，并帮助防止意外共享这些项目。</span><span class="sxs-lookup"><span data-stu-id="6821c-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="6821c-106">有关 DLP 的更多详细信息，请参阅 [了解数据丢失防护（预览版）](dlp-learn-about-dlp.md)。</span><span class="sxs-lookup"><span data-stu-id="6821c-106">For more information on DLP, see [Learn about data loss prevention](dlp-learn-about-dlp.md).</span></span>

<span data-ttu-id="6821c-107">**终结点数据丢失防护**（终结点 DLP）可将 DLP 的活动监视和保护功能扩展到 Windows 10 设备上的敏感项目。</span><span class="sxs-lookup"><span data-stu-id="6821c-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="6821c-108">将设备加入 Microsoft 365 合规性解决方案中后，即可在[活动资源管理器](data-classification-activity-explorer.md)中看到有关用户对敏感项目执行的操作的信息，你可以通过 [DLP 策略](create-test-tune-dlp-policy.md)对这些项目执行保护性操作。</span><span class="sxs-lookup"><span data-stu-id="6821c-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

> [!TIP]
> <span data-ttu-id="6821c-109">如果正在查找可移动存储的设备控制，请查看 [Microsoft Defender for Endpoint 设备控制可移动存储访问控制](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control)。</span><span class="sxs-lookup"><span data-stu-id="6821c-109">If you are looking for device control for removable storage, see [Microsoft Defender for Endpoint Device Control Removable Storage Access Control](../security/defender-endpoint/device-control-removable-storage-access-control.md#microsoft-defender-for-endpoint-device-control-removable-storage-access-control).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="6821c-110">可监视并对其执行操作的终结点活动</span><span class="sxs-lookup"><span data-stu-id="6821c-110">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="6821c-111">Microsoft 终结点 DLP 使你可以审核和管理用户对运行 Windows 10 的设备上的敏感项目进行的以下类型的活动。</span><span class="sxs-lookup"><span data-stu-id="6821c-111">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

|<span data-ttu-id="6821c-112">活动</span><span class="sxs-lookup"><span data-stu-id="6821c-112">Activity</span></span> |<span data-ttu-id="6821c-113">说明</span><span class="sxs-lookup"><span data-stu-id="6821c-113">Description</span></span>  | <span data-ttu-id="6821c-114">可审核/可限制</span><span class="sxs-lookup"><span data-stu-id="6821c-114">Auditable/restictable</span></span>|
|---------|---------|---------|
|<span data-ttu-id="6821c-115">上传到云端服务，或通过不允许的浏览器访问</span><span class="sxs-lookup"><span data-stu-id="6821c-115">upload to cloud service, or access by unallowed browsers</span></span>    | <span data-ttu-id="6821c-116">当用户试图将项目上传到受限服务域或通过浏览器访问项目时进行检测。</span><span class="sxs-lookup"><span data-stu-id="6821c-116">Detects when a user attempts to upload an item to a restricted service domain or access an item through a browser.</span></span>  <span data-ttu-id="6821c-117">若他们使用的浏览器在DLP中列为不允许的浏览器，则将阻止上传活动，并将重新定向用户到使用Edge Chromium。</span><span class="sxs-lookup"><span data-stu-id="6821c-117">If they are using a browser that is listed in DLP as an being an unallowed browser, the upload activity will be blocked and the user is redirected to use Edge Chromium.</span></span> <span data-ttu-id="6821c-118">Microsoft Edge Chromium将根据DLP策略配置，允许或阻止上传或访问。</span><span class="sxs-lookup"><span data-stu-id="6821c-118">Edge Chromium will then either allow or block the upload or access based on the DLP policy configuration</span></span>         |<span data-ttu-id="6821c-119">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6821c-119">auditable and restrictable</span></span>|
|<span data-ttu-id="6821c-120">复制至其他应用</span><span class="sxs-lookup"><span data-stu-id="6821c-120">copy to other app</span></span>    |<span data-ttu-id="6821c-121">当用户试图从受保护项目中复制信息，然后将其粘贴到另一个应用程序、进程或项目中时进行检测。</span><span class="sxs-lookup"><span data-stu-id="6821c-121">Detects when a user attempts to copy information from a protected item and then paste it into another app, process or item.</span></span> <span data-ttu-id="6821c-122">该活动无法检测到在同一应用程序、进程或项目中复制和粘贴信息。</span><span class="sxs-lookup"><span data-stu-id="6821c-122">Copying and pasting information within the same app, process, or item is not detected by this activity.</span></span>         | <span data-ttu-id="6821c-123">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6821c-123">auditable and restrictable</span></span>|
|<span data-ttu-id="6821c-124">复制到 USB 可移动媒体</span><span class="sxs-lookup"><span data-stu-id="6821c-124">copy to USB removable media</span></span> |<span data-ttu-id="6821c-125">检测用户何时尝试将项目或信息复制到可移动媒体或 USB 设备。</span><span class="sxs-lookup"><span data-stu-id="6821c-125">Detects when a user attempts to copy an item or information to removable media or USB device.</span></span>         | <span data-ttu-id="6821c-126">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6821c-126">auditable and restrictable</span></span>|
|<span data-ttu-id="6821c-127">拷贝到网络共享</span><span class="sxs-lookup"><span data-stu-id="6821c-127">copy to a network share</span></span>    |<span data-ttu-id="6821c-128">当用户试图将项目复制到网络共享或映射的网络驱动器时，检测该项目</span><span class="sxs-lookup"><span data-stu-id="6821c-128">Detects when a user attempts to copy an item to a network share or mapped network drive</span></span>         |<span data-ttu-id="6821c-129">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6821c-129">auditable and restrictable</span></span>|
|<span data-ttu-id="6821c-130">打印文档</span><span class="sxs-lookup"><span data-stu-id="6821c-130">print a document</span></span>    |<span data-ttu-id="6821c-131">当用户试图将受保护的项目打印到本地或网络打印机上时，检测该项目。</span><span class="sxs-lookup"><span data-stu-id="6821c-131">Detects when a user attempts to print a protected item to a local or network printer.</span></span>| <span data-ttu-id="6821c-132">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6821c-132">auditable and restrictable</span></span>         |
|<span data-ttu-id="6821c-133">复制到远程会话</span><span class="sxs-lookup"><span data-stu-id="6821c-133">copy to a remote session</span></span>|<span data-ttu-id="6821c-134">检测用户是否尝试将项目复制到远程桌面会话</span><span class="sxs-lookup"><span data-stu-id="6821c-134">Detects when a user attempts to copy an item to a remote desktop session</span></span> |  <span data-ttu-id="6821c-135">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6821c-135">auditable and restrictable</span></span>|
|<span data-ttu-id="6821c-136">复制到蓝牙设备</span><span class="sxs-lookup"><span data-stu-id="6821c-136">copy to a Bluetooth device</span></span>|<span data-ttu-id="6821c-137">检测用户尝试将项目复制到未启用的蓝牙应用（如在终结点 DLP 设置中不允许的蓝牙 aps 列表中所定义）。</span><span class="sxs-lookup"><span data-stu-id="6821c-137">Detects when a user attempts to copy an item to an unallowed Bluetooth app (as defined in the list of unallowed Bluetooth aps in Endpoint DLP settings).</span></span>| <span data-ttu-id="6821c-138">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6821c-138">auditable and restrictable</span></span>|
|<span data-ttu-id="6821c-139">创建项</span><span class="sxs-lookup"><span data-stu-id="6821c-139">create an item</span></span>|<span data-ttu-id="6821c-140">当用户创建项目时，检测该项目</span><span class="sxs-lookup"><span data-stu-id="6821c-140">Detects when a user creates an item</span></span>| <span data-ttu-id="6821c-141">可审核</span><span class="sxs-lookup"><span data-stu-id="6821c-141">auditable</span></span>|
|<span data-ttu-id="6821c-142">重命名项</span><span class="sxs-lookup"><span data-stu-id="6821c-142">rename an item</span></span>|<span data-ttu-id="6821c-143">当用户重命名一个项目时，检测该项目</span><span class="sxs-lookup"><span data-stu-id="6821c-143">Detects when a user renames an item</span></span>| <span data-ttu-id="6821c-144">可审核</span><span class="sxs-lookup"><span data-stu-id="6821c-144">auditable</span></span>|

## <a name="monitored-files"></a><span data-ttu-id="6821c-145">受监视的文件</span><span class="sxs-lookup"><span data-stu-id="6821c-145">Monitored files</span></span>

<span data-ttu-id="6821c-146">终结点 DLP 支持监视这些文件类型。</span><span class="sxs-lookup"><span data-stu-id="6821c-146">Endpoint DLP supports monitoring of these file types.</span></span> <span data-ttu-id="6821c-147">DLP 审核这些文件类型的活动，即使没有策略匹配。</span><span class="sxs-lookup"><span data-stu-id="6821c-147">DLP audits the activities for these file types, even if there isn't a policy match.</span></span> 

- <span data-ttu-id="6821c-148">Word 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-148">Word files</span></span>
- <span data-ttu-id="6821c-149">PowerPoint 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-149">PowerPoint files</span></span>
- <span data-ttu-id="6821c-150">Excel 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-150">Excel files</span></span>
- <span data-ttu-id="6821c-151">PDF 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-151">PDF files</span></span>
- <span data-ttu-id="6821c-152">.csv 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-152">.csv files</span></span>
- <span data-ttu-id="6821c-153">.tsv 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-153">.tsv files</span></span>
- <span data-ttu-id="6821c-154">.txt 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-154">.txt files</span></span>
- <span data-ttu-id="6821c-155">.rtf 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-155">.rtf files</span></span>
- <span data-ttu-id="6821c-156">.c 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-156">.c files</span></span>
- <span data-ttu-id="6821c-157">.class 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-157">.class files</span></span>
- <span data-ttu-id="6821c-158">.cpp 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-158">.cpp files</span></span>
- <span data-ttu-id="6821c-159">.cs 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-159">.cs files</span></span>
- <span data-ttu-id="6821c-160">.h 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-160">.h files</span></span>
- <span data-ttu-id="6821c-161">.java 文件</span><span class="sxs-lookup"><span data-stu-id="6821c-161">.java files</span></span>
 
<span data-ttu-id="6821c-162">如果只想从策略匹配项中监视数据，你可以关闭终结点 DLP 全局设置中的 **始终为设备审核文件活动**。</span><span class="sxs-lookup"><span data-stu-id="6821c-162">If you only want monitoring data from policy matches, you can turn off the **Always audit file activity for devices** in the endpoint DLP global settings.</span></span>

> [!NOTE]
> <span data-ttu-id="6821c-163">如果 **始终审核设备的审核文件活动** 设置处于打开状态，则即使设备不是任何策略的目标，也始终审核任何 Word、PowerPoint、Excel、PDF 和 .csv 文件上的活动。</span><span class="sxs-lookup"><span data-stu-id="6821c-163">If the **Always audit file activity for devices** setting is on, activities on any Word, PowerPoint, Excel, PDF, and .csv file are always audited even if the device is not targeted by any policy.</span></span>

<span data-ttu-id="6821c-164">终结点 DLP 会监视基于活动的 MIME 类型，因此即使文件扩展名已更改也会捕获活动。</span><span class="sxs-lookup"><span data-stu-id="6821c-164">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed.</span></span>

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="6821c-165">终结点 DLP 中的区别</span><span class="sxs-lookup"><span data-stu-id="6821c-165">What's different in Endpoint DLP</span></span>

<span data-ttu-id="6821c-166">在深入研究终结点 DLP 之前，你需要了解一些其他概念。</span><span class="sxs-lookup"><span data-stu-id="6821c-166">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="6821c-167">启用设备管理</span><span class="sxs-lookup"><span data-stu-id="6821c-167">Enabling Device management</span></span>

<span data-ttu-id="6821c-168">设备管理是一项功能，可从设备收集遥测并将其纳入 Microsoft 365 合规解决方案，如终结点 DLP 和[内部风险管理](insider-risk-management.md)。</span><span class="sxs-lookup"><span data-stu-id="6821c-168">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="6821c-169">你需要载入所有要用作 DLP 策略中位置的设备。</span><span class="sxs-lookup"><span data-stu-id="6821c-169">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6821c-170">![启用设备管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="6821c-170">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="6821c-171">载入和载出通过你从设备管理中心下载的脚本来处理。</span><span class="sxs-lookup"><span data-stu-id="6821c-171">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="6821c-172">中心为每种部署方法提供了自定义脚本：</span><span class="sxs-lookup"><span data-stu-id="6821c-172">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="6821c-173">本地脚本（最多 10 台机器）</span><span class="sxs-lookup"><span data-stu-id="6821c-173">local script (up to 10 machines)</span></span>
- <span data-ttu-id="6821c-174">组策略</span><span class="sxs-lookup"><span data-stu-id="6821c-174">Group policy</span></span>
- <span data-ttu-id="6821c-175">System Center Configuration Manager（版本 1610 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="6821c-175">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="6821c-176">移动设备管理/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6821c-176">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="6821c-177">非持久性计算机的 VDI 载入脚本</span><span class="sxs-lookup"><span data-stu-id="6821c-177">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6821c-178">![设备加入页面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="6821c-178">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="6821c-179">使用 [Microsoft 365 终结点 DLP入门](endpoint-dlp-getting-started.md)中的程序载入设备。</span><span class="sxs-lookup"><span data-stu-id="6821c-179">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="6821c-180">如果你已通过 [Microsoft Defender for Endpoint](/windows/security/threat-protection/) 加入设备，则这些设备将自动显示在设备列表中。</span><span class="sxs-lookup"><span data-stu-id="6821c-180">If you have onboarded devices through [Microsoft Defender for Endpoint](/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6821c-181">![托管设备列表](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="6821c-181">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="6821c-182">查看终结点 DLP 数据</span><span class="sxs-lookup"><span data-stu-id="6821c-182">Viewing Endpoint DLP data</span></span>

<span data-ttu-id="6821c-183">可通过进入 [DLP 警报管理仪表板](dlp-configure-view-alerts-policies.md)查看与在端点设备上强制实施的 DLP 策略有关的警报。</span><span class="sxs-lookup"><span data-stu-id="6821c-183">You can view alerts related to DLP policies enforced on endpoint devices by going to the [DLP Alerts Management Dashboard](dlp-configure-view-alerts-policies.md).</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6821c-184">![警报信息](../media/Alert-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="6821c-184">![Alert info](../media/Alert-info-1.png)</span></span>

<span data-ttu-id="6821c-185">你还可以在同一仪表板中查看关联事件的详细信息以及丰富元数据</span><span class="sxs-lookup"><span data-stu-id="6821c-185">You can also view details of the associated event with rich metadata in the same dashboard</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6821c-186">![事件信息](../media/Event-info-1.png)</span><span class="sxs-lookup"><span data-stu-id="6821c-186">![event info](../media/Event-info-1.png)</span></span>

<span data-ttu-id="6821c-187">设备一旦载入，有关已审核活动的信息就会流入活动资源管理器，即使在配置和部署将设备作为位置的任何 DLP 策略之前也不例外。</span><span class="sxs-lookup"><span data-stu-id="6821c-187">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6821c-188">![活动资源管理器中的终结点 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="6821c-188">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="6821c-189">终结点 DLP 会收集有关已审核活动的大量信息。</span><span class="sxs-lookup"><span data-stu-id="6821c-189">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="6821c-190">例如，如果将文件复制到可移动 USB 媒体，你将在活动详细信息中看到以下属性：</span><span class="sxs-lookup"><span data-stu-id="6821c-190">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="6821c-191">活动类型</span><span class="sxs-lookup"><span data-stu-id="6821c-191">activity type</span></span>
- <span data-ttu-id="6821c-192">客户端 IP</span><span class="sxs-lookup"><span data-stu-id="6821c-192">client IP</span></span>
- <span data-ttu-id="6821c-193">目标文件路径</span><span class="sxs-lookup"><span data-stu-id="6821c-193">target file path</span></span>
- <span data-ttu-id="6821c-194">发生时间戳</span><span class="sxs-lookup"><span data-stu-id="6821c-194">happened timestamp</span></span>
- <span data-ttu-id="6821c-195">文件名</span><span class="sxs-lookup"><span data-stu-id="6821c-195">file name</span></span>
- <span data-ttu-id="6821c-196">用户</span><span class="sxs-lookup"><span data-stu-id="6821c-196">user</span></span>
- <span data-ttu-id="6821c-197">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="6821c-197">file extension</span></span>
- <span data-ttu-id="6821c-198">文件大小</span><span class="sxs-lookup"><span data-stu-id="6821c-198">file size</span></span>
- <span data-ttu-id="6821c-199">敏感信息类型定义（如适用）</span><span class="sxs-lookup"><span data-stu-id="6821c-199">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="6821c-200">sha1 值</span><span class="sxs-lookup"><span data-stu-id="6821c-200">sha1 value</span></span>
- <span data-ttu-id="6821c-201">sha256 值</span><span class="sxs-lookup"><span data-stu-id="6821c-201">sha256 value</span></span>
- <span data-ttu-id="6821c-202">以前的文件名</span><span class="sxs-lookup"><span data-stu-id="6821c-202">previous file name</span></span>
- <span data-ttu-id="6821c-203">位置</span><span class="sxs-lookup"><span data-stu-id="6821c-203">location</span></span>
- <span data-ttu-id="6821c-204">父级</span><span class="sxs-lookup"><span data-stu-id="6821c-204">parent</span></span>
- <span data-ttu-id="6821c-205">filepath</span><span class="sxs-lookup"><span data-stu-id="6821c-205">filepath</span></span>
- <span data-ttu-id="6821c-206">源位置类型</span><span class="sxs-lookup"><span data-stu-id="6821c-206">source location type</span></span>
- <span data-ttu-id="6821c-207">平台</span><span class="sxs-lookup"><span data-stu-id="6821c-207">platform</span></span>
- <span data-ttu-id="6821c-208">设备名称</span><span class="sxs-lookup"><span data-stu-id="6821c-208">device name</span></span>
- <span data-ttu-id="6821c-209">目标位置类型</span><span class="sxs-lookup"><span data-stu-id="6821c-209">destination location type</span></span>
- <span data-ttu-id="6821c-210">执行了副本的应用程序</span><span class="sxs-lookup"><span data-stu-id="6821c-210">application that performed the copy</span></span>
- <span data-ttu-id="6821c-211">Microsoft Defender for Endpoint 设备 ID （如适用）</span><span class="sxs-lookup"><span data-stu-id="6821c-211">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="6821c-212">可移动媒体设备制造商</span><span class="sxs-lookup"><span data-stu-id="6821c-212">removable media device manufacturer</span></span>
- <span data-ttu-id="6821c-213">可移动媒体设备模型</span><span class="sxs-lookup"><span data-stu-id="6821c-213">removable media device model</span></span>
- <span data-ttu-id="6821c-214">可移动媒体设备序列号</span><span class="sxs-lookup"><span data-stu-id="6821c-214">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="6821c-215">![复制到 USB 活动属性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="6821c-215">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="6821c-216">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6821c-216">Next steps</span></span>

<span data-ttu-id="6821c-217">现在，你已了解有关终结点 DLP 的内容，接下来要学习：</span><span class="sxs-lookup"><span data-stu-id="6821c-217">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1. [<span data-ttu-id="6821c-218">Microsoft 终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="6821c-218">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="6821c-219">使用 Microsoft 终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="6821c-219">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="6821c-220">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6821c-220">See also</span></span>

- [<span data-ttu-id="6821c-221">Microsoft 终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="6821c-221">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="6821c-222">使用 Microsoft 终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="6821c-222">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="6821c-223">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="6821c-223">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="6821c-224">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="6821c-224">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="6821c-225">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="6821c-225">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="6821c-226">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="6821c-226">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/)
- [<span data-ttu-id="6821c-227">内部风险管理</span><span class="sxs-lookup"><span data-stu-id="6821c-227">Insider Risk management</span></span>](insider-risk-management.md)
