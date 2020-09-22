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
ms.openlocfilehash: 7403f20fa7c97c63be0e5001e8d3f5b37b409eee
ms.sourcegitcommit: fdb5f9d865037c0ae23aae34a5c0f06b625b2f69
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/18/2020
ms.locfileid: "48131544"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention-preview"></a><span data-ttu-id="6bc6a-104">了解 Microsoft 365 终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="6bc6a-104">Learn about Microsoft 365 Endpoint data loss prevention (preview)</span></span>

<span data-ttu-id="6bc6a-105">可以使用 Microsoft 365 数据丢失防护 (DLP) 来监视对确定为敏感的项目执行的操作，并帮助防止意外共享这些项目。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-105">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items.</span></span> <span data-ttu-id="6bc6a-106">有关 DLP 的更多信息，请参阅[数据丢失防护概述](data-loss-prevention-policies.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-106">For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="6bc6a-107">**终结点数据丢失防护**（终结点 DLP）可将 DLP 的活动监视和保护功能扩展到 Windows 10 设备上的敏感项目。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-107">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="6bc6a-108">将设备加入 Microsoft 365 合规性解决方案中后，即可在[活动资源管理器](data-classification-activity-explorer.md)中看到有关用户对敏感项目执行的操作的信息，你可以通过 [DLP 策略](create-test-tune-dlp-policy.md)对这些项目执行保护性操作。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-108">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="6bc6a-109">可监视并对其执行操作的终结点活动</span><span class="sxs-lookup"><span data-stu-id="6bc6a-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="6bc6a-110">Microsoft 终结点 DLP 使你可以审核和管理用户对运行 Windows 10 的设备上的敏感项目进行的以下类型的活动。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-110">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span> <span data-ttu-id="6bc6a-111">这包括：</span><span class="sxs-lookup"><span data-stu-id="6bc6a-111">This includes:</span></span>


|<span data-ttu-id="6bc6a-112">项目活动</span><span class="sxs-lookup"><span data-stu-id="6bc6a-112">activity on item</span></span> |<span data-ttu-id="6bc6a-113">可审核/可限制</span><span class="sxs-lookup"><span data-stu-id="6bc6a-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="6bc6a-114">已创建</span><span class="sxs-lookup"><span data-stu-id="6bc6a-114">created</span></span>    | <span data-ttu-id="6bc6a-115">可审核</span><span class="sxs-lookup"><span data-stu-id="6bc6a-115">auditable</span></span>      |
|<span data-ttu-id="6bc6a-116">已重命名</span><span class="sxs-lookup"><span data-stu-id="6bc6a-116">renamed</span></span>    |  <span data-ttu-id="6bc6a-117">可审核</span><span class="sxs-lookup"><span data-stu-id="6bc6a-117">auditable</span></span>       |
|<span data-ttu-id="6bc6a-118">已复制到可移动媒体或已在可移动媒体上创建</span><span class="sxs-lookup"><span data-stu-id="6bc6a-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="6bc6a-119">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6bc6a-119">auditable and restrictable</span></span>|
|<span data-ttu-id="6bc6a-120">已复制到网络共享，例如 \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="6bc6a-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="6bc6a-121">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6bc6a-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="6bc6a-122">已打印</span><span class="sxs-lookup"><span data-stu-id="6bc6a-122">printed</span></span> |    <span data-ttu-id="6bc6a-123">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6bc6a-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="6bc6a-124">已通过 Microsoft Chromium Edge 复制到云</span><span class="sxs-lookup"><span data-stu-id="6bc6a-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="6bc6a-125">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6bc6a-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="6bc6a-126">由不允许的应用和浏览器访问</span><span class="sxs-lookup"><span data-stu-id="6bc6a-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="6bc6a-127">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="6bc6a-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="6bc6a-128">终结点 DLP 中的区别</span><span class="sxs-lookup"><span data-stu-id="6bc6a-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="6bc6a-129">在深入研究终结点 DLP 之前，你需要了解一些其他概念。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="6bc6a-130">启用设备管理</span><span class="sxs-lookup"><span data-stu-id="6bc6a-130">Enabling Device management</span></span>

<span data-ttu-id="6bc6a-131">设备管理是一项功能，可从设备收集遥测并将其纳入 Microsoft 365 合规解决方案，如终结点 DLP 和[内部风险管理](insider-risk-management.md)。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-131">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md).</span></span> <span data-ttu-id="6bc6a-132">你需要载入所有要用作 DLP 策略中位置的设备。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-132">You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

![启用设备管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)

<span data-ttu-id="6bc6a-134">载入和载出通过你从设备管理中心下载的脚本来处理。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-134">Onboarding and offboarding are handled via scripts you download from the Device management center.</span></span> <span data-ttu-id="6bc6a-135">中心为每种部署方法提供了自定义脚本：</span><span class="sxs-lookup"><span data-stu-id="6bc6a-135">The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="6bc6a-136">本地脚本（最多 10 台机器）</span><span class="sxs-lookup"><span data-stu-id="6bc6a-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="6bc6a-137">组策略</span><span class="sxs-lookup"><span data-stu-id="6bc6a-137">Group policy</span></span>
- <span data-ttu-id="6bc6a-138">System Center Configuration Manager（版本 1610 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="6bc6a-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="6bc6a-139">移动设备管理/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="6bc6a-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="6bc6a-140">非持久性计算机的 VDI 载入脚本</span><span class="sxs-lookup"><span data-stu-id="6bc6a-140">VDI onboarding scripts for non-persistent machines</span></span>

![设备载入页面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)

 <span data-ttu-id="6bc6a-142">使用 [Microsoft 365 终结点 DLP入门](endpoint-dlp-getting-started.md)中的程序载入设备。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="6bc6a-143">如果你通过 [Microsoft Defender 高级威胁防护 (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/)载入设备，则这些设备将自动显示在设备列表中。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-143">If you have onboarded devices through [Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

![托管设备列表](../media/endpoint-dlp-learn-about-2-device-list.png)

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="6bc6a-145">查看终结点 DLP 数据</span><span class="sxs-lookup"><span data-stu-id="6bc6a-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="6bc6a-146">终结点 DLP 会监视基于活动的 om MIME 类型，因此，即使文件扩展名已更改也会捕获活动。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-146">Endpoint DLP monitors activity based om MIME type, so activities will be captured even if the file extension is changed.</span></span> <span data-ttu-id="6bc6a-147">在公共预览版中，它会监视所有：</span><span class="sxs-lookup"><span data-stu-id="6bc6a-147">At public preview it watches all:</span></span>

- <span data-ttu-id="6bc6a-148">Word 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-148">Word files</span></span>
- <span data-ttu-id="6bc6a-149">PowerPoint 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-149">PowerPoint files</span></span>
- <span data-ttu-id="6bc6a-150">Excel 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-150">Excel files</span></span>
- <span data-ttu-id="6bc6a-151">PDF 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-151">PDF files</span></span>
- <span data-ttu-id="6bc6a-152">.csv 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-152">.csv files</span></span>
- <span data-ttu-id="6bc6a-153">.tsv 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-153">.tsv files</span></span>
- <span data-ttu-id="6bc6a-154">c 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-154">c files</span></span>
- <span data-ttu-id="6bc6a-155">class 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-155">class files</span></span>
- <span data-ttu-id="6bc6a-156">cpp 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-156">cpp files</span></span>
- <span data-ttu-id="6bc6a-157">cs 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-157">cs files</span></span>
- <span data-ttu-id="6bc6a-158">h 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-158">h files</span></span>
- <span data-ttu-id="6bc6a-159">java 文件</span><span class="sxs-lookup"><span data-stu-id="6bc6a-159">java files</span></span>

> [!NOTE]
> <span data-ttu-id="6bc6a-160">默认情况下，不会审核 .txt 和源代码文件，DLP 根据应用的策略对其进行评估，然后相应地审核或阻止用户操作。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-160">.txt and source code files are not audited by default, DLP evaluates them against the applied policies and then user actions are audited or blocked accordingly.</span></span>

<span data-ttu-id="6bc6a-161">设备一旦载入，有关已审核活动的信息就会流入活动资源管理器，即使在配置和部署将设备作为位置的任何 DLP 策略之前也不例外。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-161">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

![活动资源管理器中的终结点 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)

<span data-ttu-id="6bc6a-163">终结点 DLP 会收集有关已审核活动的大量信息。</span><span class="sxs-lookup"><span data-stu-id="6bc6a-163">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="6bc6a-164">例如，如果将文件复制到可移动 USB 媒体，你将在活动详细信息中看到以下属性：</span><span class="sxs-lookup"><span data-stu-id="6bc6a-164">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="6bc6a-165">活动类型</span><span class="sxs-lookup"><span data-stu-id="6bc6a-165">activity type</span></span>
- <span data-ttu-id="6bc6a-166">客户端 IP</span><span class="sxs-lookup"><span data-stu-id="6bc6a-166">client IP</span></span>
- <span data-ttu-id="6bc6a-167">目标文件路径</span><span class="sxs-lookup"><span data-stu-id="6bc6a-167">target file path</span></span>
- <span data-ttu-id="6bc6a-168">发生时间戳</span><span class="sxs-lookup"><span data-stu-id="6bc6a-168">happened timestamp</span></span>
- <span data-ttu-id="6bc6a-169">文件名</span><span class="sxs-lookup"><span data-stu-id="6bc6a-169">file name</span></span>
- <span data-ttu-id="6bc6a-170">用户</span><span class="sxs-lookup"><span data-stu-id="6bc6a-170">user</span></span>
- <span data-ttu-id="6bc6a-171">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="6bc6a-171">file extension</span></span>
- <span data-ttu-id="6bc6a-172">文件大小</span><span class="sxs-lookup"><span data-stu-id="6bc6a-172">file size</span></span>
- <span data-ttu-id="6bc6a-173">敏感信息类型定义（如适用）</span><span class="sxs-lookup"><span data-stu-id="6bc6a-173">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="6bc6a-174">sha1 值</span><span class="sxs-lookup"><span data-stu-id="6bc6a-174">sha1 value</span></span>
- <span data-ttu-id="6bc6a-175">sha256 值</span><span class="sxs-lookup"><span data-stu-id="6bc6a-175">sha256 value</span></span>
- <span data-ttu-id="6bc6a-176">以前的文件名</span><span class="sxs-lookup"><span data-stu-id="6bc6a-176">previous file name</span></span>
- <span data-ttu-id="6bc6a-177">位置</span><span class="sxs-lookup"><span data-stu-id="6bc6a-177">location</span></span>
- <span data-ttu-id="6bc6a-178">父级</span><span class="sxs-lookup"><span data-stu-id="6bc6a-178">parent</span></span>
- <span data-ttu-id="6bc6a-179">filepath</span><span class="sxs-lookup"><span data-stu-id="6bc6a-179">filepath</span></span>
- <span data-ttu-id="6bc6a-180">源位置类型</span><span class="sxs-lookup"><span data-stu-id="6bc6a-180">source location type</span></span>
- <span data-ttu-id="6bc6a-181">平台</span><span class="sxs-lookup"><span data-stu-id="6bc6a-181">platform</span></span>
- <span data-ttu-id="6bc6a-182">设备名称</span><span class="sxs-lookup"><span data-stu-id="6bc6a-182">device name</span></span>
- <span data-ttu-id="6bc6a-183">目标位置类型</span><span class="sxs-lookup"><span data-stu-id="6bc6a-183">destination location type</span></span>
- <span data-ttu-id="6bc6a-184">执行了副本的应用程序</span><span class="sxs-lookup"><span data-stu-id="6bc6a-184">application that performed the copy</span></span>
- <span data-ttu-id="6bc6a-185">Microsoft Defender for Endpoint 设备 ID （如适用）</span><span class="sxs-lookup"><span data-stu-id="6bc6a-185">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="6bc6a-186">可移动媒体设备制造商</span><span class="sxs-lookup"><span data-stu-id="6bc6a-186">removable media device manufacturer</span></span>
- <span data-ttu-id="6bc6a-187">可移动媒体设备模型</span><span class="sxs-lookup"><span data-stu-id="6bc6a-187">removable media device model</span></span>
- <span data-ttu-id="6bc6a-188">可移动媒体设备序列号</span><span class="sxs-lookup"><span data-stu-id="6bc6a-188">removable media device serial number</span></span>

![复制到 USB 活动属性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)

## <a name="next-steps"></a><span data-ttu-id="6bc6a-190">后续步骤</span><span class="sxs-lookup"><span data-stu-id="6bc6a-190">Next steps</span></span>

<span data-ttu-id="6bc6a-191">现在，你已了解有关终结点 DLP 的内容，接下来要学习：</span><span class="sxs-lookup"><span data-stu-id="6bc6a-191">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="6bc6a-192">Microsoft 终结点数据丢失防护（预览）入门</span><span class="sxs-lookup"><span data-stu-id="6bc6a-192">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="6bc6a-193">使用 Microsoft 终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="6bc6a-193">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="6bc6a-194">另请参阅</span><span class="sxs-lookup"><span data-stu-id="6bc6a-194">See also</span></span>

- [<span data-ttu-id="6bc6a-195">Microsoft 终结点数据丢失防护（预览）入门</span><span class="sxs-lookup"><span data-stu-id="6bc6a-195">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="6bc6a-196">使用 Microsoft 终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="6bc6a-196">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="6bc6a-197">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="6bc6a-197">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="6bc6a-198">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="6bc6a-198">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="6bc6a-199">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="6bc6a-199">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="6bc6a-200">Microsoft Defender 高级威胁防护 (Microsoft Defender ATP)</span><span class="sxs-lookup"><span data-stu-id="6bc6a-200">Microsoft Defender Advanced Threat Protection (Microsoft Defender ATP)</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="6bc6a-201">内部风险管理</span><span class="sxs-lookup"><span data-stu-id="6bc6a-201">Insider Risk management</span></span>](insider-risk-management.md)