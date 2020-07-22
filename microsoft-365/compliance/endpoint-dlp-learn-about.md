---
title: 了解 Microsoft 365 终结点数据丢失防护（预览）
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
- SPO_Content
search.appverid:
- MET150
description: 'Microsoft 365 终结点数据丢失防护可将对文件活动的监视和针对这些文件的保护措施扩展到终结点。 在 Microsoft 365 合规解决方案中将文件设为可见 '
ms.openlocfilehash: 5dfe8fae1e000b97d7c2a17d3d7582fd1b24934e
ms.sourcegitcommit: a08103bc120bdec7cfeaf67c1be4e221241e69ad
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45199980"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="1bee2-104">了解 Microsoft 365 终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="1bee2-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="1bee2-105">可以使用 Microsoft 365 数据丢失防护 (DLP) 来监视对确定为敏感的项目执行的操作，并帮助防止意外共享这些项目。</span><span class="sxs-lookup"><span data-stu-id="1bee2-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="1bee2-106">有关 DLP 的更多信息，请参阅[数据丢失防护概述](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="1bee2-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="1bee2-107">**终结点数据丢失防护**（终结点 DLP）可将 DLP 的活动监视和保护功能扩展到 Windows 10 设备上的敏感项目。</span><span class="sxs-lookup"><span data-stu-id="1bee2-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="1bee2-108">将设备加入设备管理后，即可在[活动资源管理器](data-classification-activity-explorer.md)中看到有关用户对敏感项目执行的操作的信息，你可以通过 [DLP 策略](create-test-tune-dlp-policy.md)对那些项目执行保护性操作。</span><span class="sxs-lookup"><span data-stu-id="1bee2-108">Once devices are onboarded into device management, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="1bee2-109">可监视并对其执行操作的终结点活动</span><span class="sxs-lookup"><span data-stu-id="1bee2-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="1bee2-110">Microsoft 终结点 DLP 使你可以审核和管理用户对运行 Windows 10 的设备上的敏感项目进行的以下类型的活动。</span><span class="sxs-lookup"><span data-stu-id="1bee2-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="1bee2-111">这包括：</span><span class="sxs-lookup"><span data-stu-id="1bee2-111">This includes:</span></span>


|<span data-ttu-id="1bee2-112">项目活动</span><span class="sxs-lookup"><span data-stu-id="1bee2-112">activity on item</span></span> |<span data-ttu-id="1bee2-113">可审核/可限制</span><span class="sxs-lookup"><span data-stu-id="1bee2-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="1bee2-114">已创建</span><span class="sxs-lookup"><span data-stu-id="1bee2-114">created</span></span>    | <span data-ttu-id="1bee2-115">可审核</span><span class="sxs-lookup"><span data-stu-id="1bee2-115">auditable</span></span>      |
|<span data-ttu-id="1bee2-116">已重命名</span><span class="sxs-lookup"><span data-stu-id="1bee2-116">renamed</span></span>    |  <span data-ttu-id="1bee2-117">可审核</span><span class="sxs-lookup"><span data-stu-id="1bee2-117">auditable</span></span>       |
|<span data-ttu-id="1bee2-118">已复制到可移动媒体或已在可移动媒体上创建</span><span class="sxs-lookup"><span data-stu-id="1bee2-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="1bee2-119">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="1bee2-119">auditable and restrictable</span></span>|
|<span data-ttu-id="1bee2-120">已复制到网络共享，例如 \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="1bee2-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="1bee2-121">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="1bee2-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="1bee2-122">已打印</span><span class="sxs-lookup"><span data-stu-id="1bee2-122">printed</span></span> |    <span data-ttu-id="1bee2-123">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="1bee2-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="1bee2-124">已通过 Microsoft Chromium Edge 复制到云</span><span class="sxs-lookup"><span data-stu-id="1bee2-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="1bee2-125">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="1bee2-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="1bee2-126">由不允许的应用和浏览器访问</span><span class="sxs-lookup"><span data-stu-id="1bee2-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="1bee2-127">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="1bee2-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="1bee2-128">终结点 DLP 中的区别</span><span class="sxs-lookup"><span data-stu-id="1bee2-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="1bee2-129">在深入研究终结点 DLP 之前，你需要了解一些其他概念。</span><span class="sxs-lookup"><span data-stu-id="1bee2-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="1bee2-130">启用设备管理</span><span class="sxs-lookup"><span data-stu-id="1bee2-130">Enabling Device management</span></span>

<span data-ttu-id="1bee2-131">设备管理是一项功能，可从设备收集遥测并将其纳入 Microsoft 365 合规解决方案，如终结点 DLP 和[内部风险管理](insider-risk-management.md)。</span><span class="sxs-lookup"><span data-stu-id="1bee2-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="1bee2-132">你需要载入所有要用作 DLP 策略中位置的设备。</span><span class="sxs-lookup"><span data-stu-id="1bee2-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![启用设备管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="1bee2-134">载入和载出通过你从设备管理中心下载的脚本来处理。</span><span class="sxs-lookup"><span data-stu-id="1bee2-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="1bee2-135">中心为每种部署方法提供了自定义脚本：</span><span class="sxs-lookup"><span data-stu-id="1bee2-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="1bee2-136">本地脚本（最多 10 台机器）</span><span class="sxs-lookup"><span data-stu-id="1bee2-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="1bee2-137">组策略</span><span class="sxs-lookup"><span data-stu-id="1bee2-137">Group policy</span></span>
- <span data-ttu-id="1bee2-138">System Center Configuration Manager（版本 1610 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="1bee2-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="1bee2-139">移动设备管理/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="1bee2-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="1bee2-140">非持久性计算机的 VDI 载入脚本</span><span class="sxs-lookup"><span data-stu-id="1bee2-140">VDI onboarding scripts for non-persistent machines</span></span>

![设备载入页面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="1bee2-142">使用 [Microsoft 365 终结点 DLP入门](endpoint-dlp-getting-started.md)中的程序载入设备。</span><span class="sxs-lookup"><span data-stu-id="1bee2-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="1bee2-143">如果你通过 [Microsoft Defender 高级威胁防护 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)载入设备，则这些设备将自动显示在设备列表中。</span><span class="sxs-lookup"><span data-stu-id="1bee2-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![托管设备列表](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="1bee2-145">查看终结点 DLP 数据</span><span class="sxs-lookup"><span data-stu-id="1bee2-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="1bee2-146">终结点 DLP 会监视基于活动的 om MIME 类型，因此，即使文件扩展名已更改也会捕获活动。</span><span class="sxs-lookup"><span data-stu-id="1bee2-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="1bee2-147">在公共预览版中，它会监视所有：</span><span class="sxs-lookup"><span data-stu-id="1bee2-147">At public preview it watches all:</span></span>

- <span data-ttu-id="1bee2-148">Word 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-148">Word files</span></span>
- <span data-ttu-id="1bee2-149">PowerPoint 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-149">PowerPoint files</span></span>
- <span data-ttu-id="1bee2-150">Excel 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-150">Excel files</span></span>
- <span data-ttu-id="1bee2-151">PDF 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-151">PDF files</span></span>
- <span data-ttu-id="1bee2-152">.csv 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-152">.csv files</span></span>
- <span data-ttu-id="1bee2-153">.tsv 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-153">.tsv files</span></span>
- <span data-ttu-id="1bee2-154">c 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-154">c files</span></span>
- <span data-ttu-id="1bee2-155">class 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-155">class files</span></span>
- <span data-ttu-id="1bee2-156">cpp 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-156">cpp files</span></span>
- <span data-ttu-id="1bee2-157">cs 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-157">cs files</span></span>
- <span data-ttu-id="1bee2-158">h 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-158">h files</span></span>
- <span data-ttu-id="1bee2-159">java 文件</span><span class="sxs-lookup"><span data-stu-id="1bee2-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="1bee2-160">默认情况下，不会审核 .txt 和源代码文件，DLP 根据应用的策略对其进行评估，然后相应地审核或阻止用户操作。</span><span class="sxs-lookup"><span data-stu-id="1bee2-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="1bee2-161">设备一旦载入，有关已审核活动的信息就会流入活动资源管理器，即使在配置和部署将设备作为位置的任何 DLP 策略之前也不例外。</span><span class="sxs-lookup"><span data-stu-id="1bee2-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![活动资源管理器中的终结点 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="1bee2-163">终结点 DLP 会收集有关已审核活动的大量信息。</span><span class="sxs-lookup"><span data-stu-id="1bee2-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="1bee2-164">例如，如果将文件复制到可移动 USB 媒体，你将在活动详细信息中看到以下属性：</span><span class="sxs-lookup"><span data-stu-id="1bee2-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="1bee2-165">活动类型</span><span class="sxs-lookup"><span data-stu-id="1bee2-165">activity type</span></span>
- <span data-ttu-id="1bee2-166">客户端 IP</span><span class="sxs-lookup"><span data-stu-id="1bee2-166">client IP</span></span>
- <span data-ttu-id="1bee2-167">目标文件路径</span><span class="sxs-lookup"><span data-stu-id="1bee2-167">target file path</span></span>
- <span data-ttu-id="1bee2-168">发生时间戳</span><span class="sxs-lookup"><span data-stu-id="1bee2-168">happened timestamp</span></span>
- <span data-ttu-id="1bee2-169">文件名</span><span class="sxs-lookup"><span data-stu-id="1bee2-169">file name</span></span>
- <span data-ttu-id="1bee2-170">用户</span><span class="sxs-lookup"><span data-stu-id="1bee2-170">user</span></span>
- <span data-ttu-id="1bee2-171">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="1bee2-171">file extension</span></span>
- <span data-ttu-id="1bee2-172">文件大小</span><span class="sxs-lookup"><span data-stu-id="1bee2-172">file size</span></span>
- <span data-ttu-id="1bee2-173">敏感信息类型定义（如适用）</span><span class="sxs-lookup"><span data-stu-id="1bee2-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="1bee2-174">sha1 值</span><span class="sxs-lookup"><span data-stu-id="1bee2-174">sha1 value</span></span>
- <span data-ttu-id="1bee2-175">sha256 值</span><span class="sxs-lookup"><span data-stu-id="1bee2-175">sha256 value</span></span>
- <span data-ttu-id="1bee2-176">以前的文件名</span><span class="sxs-lookup"><span data-stu-id="1bee2-176">previous file name</span></span>
- <span data-ttu-id="1bee2-177">位置</span><span class="sxs-lookup"><span data-stu-id="1bee2-177">location</span></span>
- <span data-ttu-id="1bee2-178">父级</span><span class="sxs-lookup"><span data-stu-id="1bee2-178">parent</span></span>
- <span data-ttu-id="1bee2-179">filepath</span><span class="sxs-lookup"><span data-stu-id="1bee2-179">filepath</span></span>
- <span data-ttu-id="1bee2-180">源位置类型</span><span class="sxs-lookup"><span data-stu-id="1bee2-180">source location type</span></span>
- <span data-ttu-id="1bee2-181">平台</span><span class="sxs-lookup"><span data-stu-id="1bee2-181">platform</span></span>
- <span data-ttu-id="1bee2-182">设备名称</span><span class="sxs-lookup"><span data-stu-id="1bee2-182">device name</span></span>
- <span data-ttu-id="1bee2-183">目标位置类型</span><span class="sxs-lookup"><span data-stu-id="1bee2-183">destination location type</span></span>
- <span data-ttu-id="1bee2-184">执行了副本的应用程序</span><span class="sxs-lookup"><span data-stu-id="1bee2-184">application that performed the copy</span></span>
- <span data-ttu-id="1bee2-185">DATP 设备 ID（如适用）</span><span class="sxs-lookup"><span data-stu-id="1bee2-185">MDATP device ID (if applicable)</span></span>
- <span data-ttu-id="1bee2-186">可移动媒体设备制造商</span><span class="sxs-lookup"><span data-stu-id="1bee2-186">removable media device manufacturer</span></span>
- <span data-ttu-id="1bee2-187">可移动媒体设备模型</span><span class="sxs-lookup"><span data-stu-id="1bee2-187">removable media device model</span></span>
- <span data-ttu-id="1bee2-188">可移动媒体设备序列号</span><span class="sxs-lookup"><span data-stu-id="1bee2-188">removable media device serial number</span></span>

![复制到 USB 活动属性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="1bee2-190">后续步骤</span><span class="sxs-lookup"><span data-stu-id="1bee2-190">Next steps</span></span>

<span data-ttu-id="1bee2-191">现在，你已了解有关终结点 DLP 的内容，接下来要学习：</span><span class="sxs-lookup"><span data-stu-id="1bee2-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="1bee2-192">Microsoft 终结点数据丢失防护（预览）入门</span><span class="sxs-lookup"><span data-stu-id="1bee2-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="1bee2-193">使用 Microsoft 终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="1bee2-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="1bee2-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="1bee2-194">See also</span></span>

- [<span data-ttu-id="1bee2-195">Microsoft 终结点数据丢失防护（预览）入门</span><span class="sxs-lookup"><span data-stu-id="1bee2-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="1bee2-196">使用 Microsoft 终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="1bee2-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="1bee2-197">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="1bee2-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="1bee2-198">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="1bee2-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="1bee2-199">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="1bee2-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="1bee2-200">Microsoft Defender 高级威胁防护 (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="1bee2-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="1bee2-201">内部风险管理</span><span class="sxs-lookup"><span data-stu-id="1bee2-201">Insider Risk management</span></span>](insider-risk-management.md)