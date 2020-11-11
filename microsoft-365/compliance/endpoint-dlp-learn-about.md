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
description: 'Microsoft 365 终结点数据丢失阻止将对文件活动的监视和对这些文件的保护性操作扩展到终结点。可在 Microsoft 365 合规性解决方案中看到文件 '
ms.openlocfilehash: 966e201acb8038d85f0d06c0800c9845fd79097e
ms.sourcegitcommit: 89f56c3e0b619a4700a75a21927d9ffc90658632
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2020
ms.locfileid: "48984926"
---
# <a name="learn-about-microsoft-365-endpoint-data-loss-prevention"></a><span data-ttu-id="dc54f-104">了解 Microsoft 365 终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="dc54f-104">Learn about Microsoft 365 Endpoint data loss prevention</span></span>

<span data-ttu-id="dc54f-p102">可使用 Microsoft 365 数据丢失防护（DLP）监视对已确定为敏感的项目执行的操作，并帮助防止无意间共享这些项目。有关 DLP 的详细信息，请参阅 [数据丢失防护](data-loss-prevention-policies.md)概述。</span><span class="sxs-lookup"><span data-stu-id="dc54f-p102">You can use Microsoft 365 data loss prevention (DLP) to monitor the actions that are being taken on items you've determined to be sensitive and to help prevent the unintentional sharing of those items. For more information on DLP, see [Overview of data loss prevention](data-loss-prevention-policies.md).</span></span>

<span data-ttu-id="dc54f-p103">**终结点数据丢失防护** （终结点 DLP）可将 DLP 的活动监视和保护功能扩展到 Windows 10 设备上的敏感项目。将设备加入 Microsoft 365 合规性解决方案中后，即可在 [活动资源管理器](data-classification-activity-explorer.md)中看到有关用户对敏感项目执行的操作的信息，你可以通过 [DLP 策略](create-test-tune-dlp-policy.md)对这些项目执行保护性操作。</span><span class="sxs-lookup"><span data-stu-id="dc54f-p103">**Endpoint data loss prevention** (Endpoint DLP) extends the activity monitoring and protection capabilities of DLP to sensitive items that are on Windows 10 devices. Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

## <a name="endpoint-activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="dc54f-109">可监视并对其执行操作的终结点活动</span><span class="sxs-lookup"><span data-stu-id="dc54f-109">Endpoint activities you can monitor and take action on</span></span>

<span data-ttu-id="dc54f-p104">Microsoft 终结点 DLP 使你可以审核和管理用户对运行 Windows 10 的设备上的敏感项目进行的以下类型的活动。这包括：</span><span class="sxs-lookup"><span data-stu-id="dc54f-p104">Microsoft Endpoint DLP enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10. This includes:</span></span>


|<span data-ttu-id="dc54f-112">项目活动</span><span class="sxs-lookup"><span data-stu-id="dc54f-112">activity on item</span></span> |<span data-ttu-id="dc54f-113">可审核/可限制</span><span class="sxs-lookup"><span data-stu-id="dc54f-113">auditable/restrictable</span></span>  |
|---------|---------|
|<span data-ttu-id="dc54f-114">已创建</span><span class="sxs-lookup"><span data-stu-id="dc54f-114">created</span></span>    | <span data-ttu-id="dc54f-115">可审核</span><span class="sxs-lookup"><span data-stu-id="dc54f-115">auditable</span></span>      |
|<span data-ttu-id="dc54f-116">已重命名</span><span class="sxs-lookup"><span data-stu-id="dc54f-116">renamed</span></span>    |  <span data-ttu-id="dc54f-117">可审核</span><span class="sxs-lookup"><span data-stu-id="dc54f-117">auditable</span></span>       |
|<span data-ttu-id="dc54f-118">已复制到可移动媒体或已在可移动媒体上创建</span><span class="sxs-lookup"><span data-stu-id="dc54f-118">copied to or created on removable media</span></span>     |     <span data-ttu-id="dc54f-119">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="dc54f-119">auditable and restrictable</span></span>|
|<span data-ttu-id="dc54f-120">已复制到网络共享，例如 \\my-server\fileshare</span><span class="sxs-lookup"><span data-stu-id="dc54f-120">copied to network share, e.g. \\my-server\fileshare</span></span>   |     <span data-ttu-id="dc54f-121">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="dc54f-121">auditable and restrictable</span></span>    |
|<span data-ttu-id="dc54f-122">已打印</span><span class="sxs-lookup"><span data-stu-id="dc54f-122">printed</span></span> |    <span data-ttu-id="dc54f-123">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="dc54f-123">auditable and restrictable</span></span>       |
|<span data-ttu-id="dc54f-124">已通过 Microsoft Chromium Edge 复制到云</span><span class="sxs-lookup"><span data-stu-id="dc54f-124">copied to cloud via Chromium Edge</span></span>    |   <span data-ttu-id="dc54f-125">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="dc54f-125">auditable and restrictable</span></span>        |
|<span data-ttu-id="dc54f-126">由不允许的应用和浏览器访问</span><span class="sxs-lookup"><span data-stu-id="dc54f-126">accessed by unallowed apps and browsers</span></span>    |  <span data-ttu-id="dc54f-127">可审核且可限制</span><span class="sxs-lookup"><span data-stu-id="dc54f-127">auditable and restrictable</span></span>       |

## <a name="whats-different-in-endpoint-dlp"></a><span data-ttu-id="dc54f-128">终结点 DLP 中的区别</span><span class="sxs-lookup"><span data-stu-id="dc54f-128">What's different in Endpoint DLP</span></span>

<span data-ttu-id="dc54f-129">在深入研究终结点 DLP 之前，你需要了解一些其他概念。</span><span class="sxs-lookup"><span data-stu-id="dc54f-129">There are a few extra concepts that you need to be aware of before you dig into Endpoint DLP.</span></span>

### <a name="enabling-device-management"></a><span data-ttu-id="dc54f-130">启用设备管理</span><span class="sxs-lookup"><span data-stu-id="dc54f-130">Enabling Device management</span></span>

<span data-ttu-id="dc54f-p105">设备管理是一项功能，可从设备收集遥测并将其纳入 Microsoft 365 合规解决方案，如终结点 DLP 和[内部风险管理](insider-risk-management.md)。你需要载入所有要用作 DLP 策略中位置的设备。</span><span class="sxs-lookup"><span data-stu-id="dc54f-p105">Device management is the functionality that enables the collection of telemetry from devices and brings it into Microsoft 365 compliance solutions like Endpoint DLP and [Insider Risk management](insider-risk-management.md). You'll need to onboard all devices you want to use as locations in DLP policies.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dc54f-133">![启用设备管理](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span><span class="sxs-lookup"><span data-stu-id="dc54f-133">![enable device management](../media/endpoint-dlp-learn-about-1-enable-device-management.png)</span></span>

<span data-ttu-id="dc54f-p106">加入和载出通过你从设备管理中心下载的脚本来处理。中心为每种部署方法提供了自定义脚本：</span><span class="sxs-lookup"><span data-stu-id="dc54f-p106">Onboarding and offboarding are handled via scripts you download from the Device management center. The center has custom scripts for each of these deployment methods:</span></span>

- <span data-ttu-id="dc54f-136">本地脚本（最多 10 台机器）</span><span class="sxs-lookup"><span data-stu-id="dc54f-136">local script (up to 10 machines)</span></span>
- <span data-ttu-id="dc54f-137">组策略</span><span class="sxs-lookup"><span data-stu-id="dc54f-137">Group policy</span></span>
- <span data-ttu-id="dc54f-138">System Center Configuration Manager（版本 1610 或更高版本）</span><span class="sxs-lookup"><span data-stu-id="dc54f-138">System Center Configuration Manager (version 1610 or later)</span></span>
- <span data-ttu-id="dc54f-139">移动设备管理/Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="dc54f-139">Mobile Device Management/Microsoft Intune</span></span>
- <span data-ttu-id="dc54f-140">非持久性计算机的 VDI 加入脚本</span><span class="sxs-lookup"><span data-stu-id="dc54f-140">VDI onboarding scripts for non-persistent machines</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dc54f-141">![设备加入页面](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span><span class="sxs-lookup"><span data-stu-id="dc54f-141">![device onboarding page](../media/endpoint-dlp-learn-about-3-device-onboarding-page.png)</span></span>

 <span data-ttu-id="dc54f-142">按照 [Microsoft 365 终结点 DLP入门](endpoint-dlp-getting-started.md)中的程序加入设备。</span><span class="sxs-lookup"><span data-stu-id="dc54f-142">Use the procedures in [Getting started with Microsoft 365 Endpoint DLP](endpoint-dlp-getting-started.md) to onboard devices.</span></span>

<span data-ttu-id="dc54f-143">如果你已通过 [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/) 加入设备，则这些设备将自动显示在设备列表中。</span><span class="sxs-lookup"><span data-stu-id="dc54f-143">If you have onboarded devices through [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/), those devices will automatically show up in the list of devices.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dc54f-144">![托管设备列表](../media/endpoint-dlp-learn-about-2-device-list.png)</span><span class="sxs-lookup"><span data-stu-id="dc54f-144">![managed devices list](../media/endpoint-dlp-learn-about-2-device-list.png)</span></span>

### <a name="viewing-endpoint-dlp-data"></a><span data-ttu-id="dc54f-145">查看终结点 DLP 数据</span><span class="sxs-lookup"><span data-stu-id="dc54f-145">Viewing Endpoint DLP data</span></span>

 <span data-ttu-id="dc54f-p107">终结点 DLP 会监视基于活动的 om MIME 类型，因此即使文件扩展名已更改也会捕获活动。在公共预览版中，它会监视所有：</span><span class="sxs-lookup"><span data-stu-id="dc54f-p107">Endpoint DLP monitors activity-based on MIME type, so activities will be captured even if the file extension is changed. At public preview it watches all:</span></span>

- <span data-ttu-id="dc54f-148">Word 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-148">Word files</span></span>
- <span data-ttu-id="dc54f-149">PowerPoint 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-149">PowerPoint files</span></span>
- <span data-ttu-id="dc54f-150">Excel 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-150">Excel files</span></span>
- <span data-ttu-id="dc54f-151">PDF 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-151">PDF files</span></span>
- <span data-ttu-id="dc54f-152">.csv 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-152">.csv files</span></span>
- <span data-ttu-id="dc54f-153">.tsv 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-153">.tsv files</span></span>
- <span data-ttu-id="dc54f-154">.txt 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-154">.txt files</span></span>
- <span data-ttu-id="dc54f-155">.rtf 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-155">.rtf files</span></span>
- <span data-ttu-id="dc54f-156">.c 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-156">.c files</span></span>
- <span data-ttu-id="dc54f-157">.class 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-157">.class files</span></span>
- <span data-ttu-id="dc54f-158">.cpp 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-158">.cpp files</span></span>
- <span data-ttu-id="dc54f-159">.cs 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-159">.cs files</span></span>
- <span data-ttu-id="dc54f-160">.h 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-160">.h files</span></span>
- <span data-ttu-id="dc54f-161">.java 文件</span><span class="sxs-lookup"><span data-stu-id="dc54f-161">.java files</span></span>

> [!NOTE]
> <span data-ttu-id="dc54f-p108">Endpoint DLP 对照 DLP 策略评估上述所有类型的文件，并相应地应用保护操作。所有符合 DLP 策略的文件都将经过审核，查看所有受支持的操作，即使这些文件未被阻止也是如此。此外在默认情况下，在任何 PowerPoint、Excel、PDF 和 .csv 文件上执行的文件活动都将经过审核，而不论 DLP 策略是否存在或是否匹配这些文件。</span><span class="sxs-lookup"><span data-stu-id="dc54f-p108">Endpoint DLP evaluates files of all the above types against the DLP policy and applies protection actions accordingly. All files that match a DLP policy are audited for all supported actions, even if they aren't blocked. In addition, file activity performed on any Word, PowerPoint, Excel, PDF, and .csv file is audited by default, independent of whether a DLP policy exists or matches these files.</span></span>

<span data-ttu-id="dc54f-165">设备一旦加入，已经过审核的活动的相关信息就会流入活动资源管理器，即使在还未配置和部署将设备作为位置的任何 DLP 策略时也是如此。</span><span class="sxs-lookup"><span data-stu-id="dc54f-165">Once a device is onboarded, information about audited activities flows into Activity explorer even before you configure and deploy any DLP policies that have devices as a location.</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dc54f-166">![活动资源管理器中的终结点 DLP 事件](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span><span class="sxs-lookup"><span data-stu-id="dc54f-166">![endpoint dlp events in activity explorer](../media/endpoint-dlp-learn-about-4-activity-explorer.png)</span></span>

<span data-ttu-id="dc54f-167">终结点 DLP 会收集已经过审核的活动的大量相关信息。</span><span class="sxs-lookup"><span data-stu-id="dc54f-167">Endpoint DLP collects extensive information on audited activity.</span></span>

<span data-ttu-id="dc54f-168">例如，如果将文件复制到可移动 USB 媒体，你将在活动详细信息中看到以下属性：</span><span class="sxs-lookup"><span data-stu-id="dc54f-168">For example, if a file is copied to removable USB media, you'd see these attributes in the activity details:</span></span>

- <span data-ttu-id="dc54f-169">活动类型</span><span class="sxs-lookup"><span data-stu-id="dc54f-169">activity type</span></span>
- <span data-ttu-id="dc54f-170">客户端 IP</span><span class="sxs-lookup"><span data-stu-id="dc54f-170">client IP</span></span>
- <span data-ttu-id="dc54f-171">目标文件路径</span><span class="sxs-lookup"><span data-stu-id="dc54f-171">target file path</span></span>
- <span data-ttu-id="dc54f-172">发生时间戳</span><span class="sxs-lookup"><span data-stu-id="dc54f-172">happened timestamp</span></span>
- <span data-ttu-id="dc54f-173">文件名</span><span class="sxs-lookup"><span data-stu-id="dc54f-173">file name</span></span>
- <span data-ttu-id="dc54f-174">用户</span><span class="sxs-lookup"><span data-stu-id="dc54f-174">user</span></span>
- <span data-ttu-id="dc54f-175">文件扩展名</span><span class="sxs-lookup"><span data-stu-id="dc54f-175">file extension</span></span>
- <span data-ttu-id="dc54f-176">文件大小</span><span class="sxs-lookup"><span data-stu-id="dc54f-176">file size</span></span>
- <span data-ttu-id="dc54f-177">敏感信息类型定义（如适用）</span><span class="sxs-lookup"><span data-stu-id="dc54f-177">sensitive information type (if applicable)</span></span>
- <span data-ttu-id="dc54f-178">sha1 值</span><span class="sxs-lookup"><span data-stu-id="dc54f-178">sha1 value</span></span>
- <span data-ttu-id="dc54f-179">sha256 值</span><span class="sxs-lookup"><span data-stu-id="dc54f-179">sha256 value</span></span>
- <span data-ttu-id="dc54f-180">以前的文件名</span><span class="sxs-lookup"><span data-stu-id="dc54f-180">previous file name</span></span>
- <span data-ttu-id="dc54f-181">位置</span><span class="sxs-lookup"><span data-stu-id="dc54f-181">location</span></span>
- <span data-ttu-id="dc54f-182">父级</span><span class="sxs-lookup"><span data-stu-id="dc54f-182">parent</span></span>
- <span data-ttu-id="dc54f-183">filepath</span><span class="sxs-lookup"><span data-stu-id="dc54f-183">filepath</span></span>
- <span data-ttu-id="dc54f-184">源位置类型</span><span class="sxs-lookup"><span data-stu-id="dc54f-184">source location type</span></span>
- <span data-ttu-id="dc54f-185">平台</span><span class="sxs-lookup"><span data-stu-id="dc54f-185">platform</span></span>
- <span data-ttu-id="dc54f-186">设备名称</span><span class="sxs-lookup"><span data-stu-id="dc54f-186">device name</span></span>
- <span data-ttu-id="dc54f-187">目标位置类型</span><span class="sxs-lookup"><span data-stu-id="dc54f-187">destination location type</span></span>
- <span data-ttu-id="dc54f-188">执行了副本的应用程序</span><span class="sxs-lookup"><span data-stu-id="dc54f-188">application that performed the copy</span></span>
- <span data-ttu-id="dc54f-189">Microsoft Defender for Endpoint 设备 ID （如适用）</span><span class="sxs-lookup"><span data-stu-id="dc54f-189">Microsoft Defender for Endpoint device ID (if applicable)</span></span>
- <span data-ttu-id="dc54f-190">可移动媒体设备制造商</span><span class="sxs-lookup"><span data-stu-id="dc54f-190">removable media device manufacturer</span></span>
- <span data-ttu-id="dc54f-191">可移动媒体设备模型</span><span class="sxs-lookup"><span data-stu-id="dc54f-191">removable media device model</span></span>
- <span data-ttu-id="dc54f-192">可移动媒体设备序列号</span><span class="sxs-lookup"><span data-stu-id="dc54f-192">removable media device serial number</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="dc54f-193">![复制到 USB 活动属性](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span><span class="sxs-lookup"><span data-stu-id="dc54f-193">![copy to usb activity attributes](../media/endpoint-dlp-learn-about-5-activity-attributes.png)</span></span>

## <a name="next-steps"></a><span data-ttu-id="dc54f-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="dc54f-194">Next steps</span></span>

<span data-ttu-id="dc54f-195">现在，你已了解有关终结点 DLP 的内容，接下来要学习：</span><span class="sxs-lookup"><span data-stu-id="dc54f-195">Now that you've learned about Endpoint DLP, your next steps are:</span></span>

1) [<span data-ttu-id="dc54f-196">Microsoft 终结点数据丢失防护（预览）入门</span><span class="sxs-lookup"><span data-stu-id="dc54f-196">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
2) [<span data-ttu-id="dc54f-197">使用 Microsoft 终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="dc54f-197">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)

## <a name="see-also"></a><span data-ttu-id="dc54f-198">另请参阅</span><span class="sxs-lookup"><span data-stu-id="dc54f-198">See also</span></span>

- [<span data-ttu-id="dc54f-199">Microsoft 终结点数据丢失防护（预览）入门</span><span class="sxs-lookup"><span data-stu-id="dc54f-199">Getting started with Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="dc54f-200">使用 Microsoft 终结点数据丢失防护（预览）</span><span class="sxs-lookup"><span data-stu-id="dc54f-200">Using Microsoft Endpoint data loss prevention (preview)</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="dc54f-201">数据丢失防护概述</span><span class="sxs-lookup"><span data-stu-id="dc54f-201">Overview of data loss prevention</span></span>](data-loss-prevention-policies.md)
- [<span data-ttu-id="dc54f-202">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="dc54f-202">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="dc54f-203">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="dc54f-203">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="dc54f-204">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="dc54f-204">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="dc54f-205">内部风险管理</span><span class="sxs-lookup"><span data-stu-id="dc54f-205">Insider Risk management</span></span>](insider-risk-management.md)
