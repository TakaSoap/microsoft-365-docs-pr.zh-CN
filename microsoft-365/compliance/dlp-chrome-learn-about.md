---
title: 了解 Microsoft 合规性扩展
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
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
description: Microsoft 合规性扩展可扩展对 Google Chrome 浏览器文件活动和保护操作的监视和控制
ms.openlocfilehash: b8d9be88f42cce736cdbf66a97f4363106fa5820
ms.sourcegitcommit: e8f5d88f0fe54620308d3bec05263568f9da2931
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/03/2021
ms.locfileid: "52730482"
---
# <a name="learn-about-the-microsoft-compliance-extension"></a><span data-ttu-id="72fde-103">了解 Microsoft 合规性扩展</span><span class="sxs-lookup"><span data-stu-id="72fde-103">Learn about the Microsoft Compliance Extension</span></span>

<span data-ttu-id="72fde-104">[终结点数据丢失防护（终结点 DLP）](endpoint-dlp-learn-about.md) 将[Microsoft 365 数据丢失防护 (DLP)](dlp-learn-about-dlp.md) 的活动监视和保护功能扩展到 Windows 10 设备上的敏感项目。</span><span class="sxs-lookup"><span data-stu-id="72fde-104">[Endpoint data loss prevention (endpoint DLP)](endpoint-dlp-learn-about.md) extends the activity monitoring and protection capabilities of [Microsoft 365 data loss prevention (DLP)](dlp-learn-about-dlp.md) to sensitive items that are on Windows 10 devices.</span></span> <span data-ttu-id="72fde-105">将设备加入 Microsoft 365 合规性解决方案中后，即可在[活动资源管理器](data-classification-activity-explorer.md)中看到有关用户对敏感项目执行的操作的信息，你可以通过 [DLP 策略](create-test-tune-dlp-policy.md)对这些项目执行保护性操作。</span><span class="sxs-lookup"><span data-stu-id="72fde-105">Once devices are onboarded into the Microsoft 365 compliance solutions, the information about what users are doing with sensitive items is made visible in [activity explorer](data-classification-activity-explorer.md) and you can enforce protective actions on those items via [DLP policies](create-test-tune-dlp-policy.md).</span></span>

<span data-ttu-id="72fde-106">在 Windows 10 设备上安装 Microsoft 合规性扩展后，组织可以在用户尝试使用 Google Chrome 访问或将敏感项目上传到云服务时进行监视，并可通过 DLP 执行保护操作。</span><span class="sxs-lookup"><span data-stu-id="72fde-106">Once the Microsoft Compliance Extension is installed on a Windows 10 device, organizations can monitor when a user attempts to access or upload a sensitive item to a cloud service using Google Chrome and enforce protective actions via DLP.</span></span>  

## <a name="activities-you-can-monitor-and-take-action-on"></a><span data-ttu-id="72fde-107">可以监视并对其执行操作的活动</span><span class="sxs-lookup"><span data-stu-id="72fde-107">Activities you can monitor and take action on</span></span>

<span data-ttu-id="72fde-108">Microsoft 终结点 DLP 使你可以审核和管理用户对运行 Windows 10 设备上的敏感项目进行的以下类型活动。</span><span class="sxs-lookup"><span data-stu-id="72fde-108">The Microsoft Compliance Extension enables you to audit and manage the following types of activities users take on sensitive items on devices running Windows 10.</span></span>

<span data-ttu-id="72fde-109">活动</span><span class="sxs-lookup"><span data-stu-id="72fde-109">activity</span></span> |<span data-ttu-id="72fde-110">说明</span><span class="sxs-lookup"><span data-stu-id="72fde-110">description</span></span>  | <span data-ttu-id="72fde-111">受支持的策略操作</span><span class="sxs-lookup"><span data-stu-id="72fde-111">supported policy actions</span></span>|
|---------|---------|---------|
|<span data-ttu-id="72fde-112">文件复制到云</span><span class="sxs-lookup"><span data-stu-id="72fde-112">file copied to cloud</span></span>  | <span data-ttu-id="72fde-113">用户尝试通过 Chrome 浏览器将敏感项目上传到受限服务域时进行检测</span><span class="sxs-lookup"><span data-stu-id="72fde-113">Detects when a user attempts to upload a sensitive item to a restricted service domain through the Chrome browser</span></span> |<span data-ttu-id="72fde-114">审核、阻止</span><span class="sxs-lookup"><span data-stu-id="72fde-114">audit, block</span></span>|
|<span data-ttu-id="72fde-115">文件打印</span><span class="sxs-lookup"><span data-stu-id="72fde-115">file printed</span></span>  |<span data-ttu-id="72fde-116">用户尝试将 Chrome 浏览器中打开的敏感项目打印到本地或网络打印机时进行检测</span><span class="sxs-lookup"><span data-stu-id="72fde-116">Detects when a user attempts to print a sensitive item that is open in the Chrome browser to a local or network printer</span></span> |<span data-ttu-id="72fde-117">审核、通过覆盖阻止、阻止</span><span class="sxs-lookup"><span data-stu-id="72fde-117">audit, block with override, block</span></span>|
|<span data-ttu-id="72fde-118">文件复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="72fde-118">file copied to clipboard</span></span> |<span data-ttu-id="72fde-119">用户尝试从在 Chrome 浏览器中查看的敏感项目中复制信息，然后将其粘贴到另一应用、进程或项目时进行检测。</span><span class="sxs-lookup"><span data-stu-id="72fde-119">Detects when a user attempts to copy information from a sensitive item that is being viewed in the Chrome browser and then paste it into another app, process, or item.</span></span> |<span data-ttu-id="72fde-120">审核、通过覆盖阻止、阻止</span><span class="sxs-lookup"><span data-stu-id="72fde-120">audit, block with override, block</span></span>|
|<span data-ttu-id="72fde-121">文件复制到可移动存储器</span><span class="sxs-lookup"><span data-stu-id="72fde-121">file copied to removable storage</span></span>    | <span data-ttu-id="72fde-122">用户尝试将敏感项目或信息从在 Chrome 浏览器中打开的敏感项目复制到可移动媒体或 USB 设备时进行检测</span><span class="sxs-lookup"><span data-stu-id="72fde-122">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser to removable media or USB device</span></span> |<span data-ttu-id="72fde-123">审核、通过覆盖阻止、阻止</span><span class="sxs-lookup"><span data-stu-id="72fde-123">audit, block with override, block</span></span>|
|<span data-ttu-id="72fde-124">文件复制到网络共享</span><span class="sxs-lookup"><span data-stu-id="72fde-124">file copied to network share</span></span>  |<span data-ttu-id="72fde-125">用户尝试将敏感项目或信息从 Chrome 浏览器中打开的敏感项目复制到网络共享或映射的网络驱动器时进行检测。</span><span class="sxs-lookup"><span data-stu-id="72fde-125">Detects when a user attempts to copy a sensitive item or information from a sensitive item that is open in the Chrome browser  to a network share or mapped network drive.</span></span>|<span data-ttu-id="72fde-126">审核、通过覆盖阻止、阻止</span><span class="sxs-lookup"><span data-stu-id="72fde-126">audit, block with override, block</span></span> |

## <a name="deployment-process"></a><span data-ttu-id="72fde-127">部署过程</span><span class="sxs-lookup"><span data-stu-id="72fde-127">Deployment process</span></span>
1. [<span data-ttu-id="72fde-128">终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="72fde-128">Get started with endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
2. [<span data-ttu-id="72fde-129">Windows 10 设备的装载工具和方法</span><span class="sxs-lookup"><span data-stu-id="72fde-129">Onboarding tools and methods for Windows 10 devices</span></span>](dlp-configure-endpoints.md)
3. [<span data-ttu-id="72fde-130">在 Windows 10 设备上安装扩展</span><span class="sxs-lookup"><span data-stu-id="72fde-130">Install the extension on your Windows 10 devices</span></span>](dlp-chrome-get-started.md)
4. <span data-ttu-id="72fde-131">[创建或编辑 DLP 策略](create-test-tune-dlp-policy.md)，这些策略限制上传到云服务，或者通过不允许的浏览器操作访问云服务，并将其应用到 Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="72fde-131">[Create or edit DLP policies](create-test-tune-dlp-policy.md) that restrict upload to cloud service, or access by unallowed browsers actions and apply them to your Windows 10 devices</span></span>

## <a name="next-steps"></a><span data-ttu-id="72fde-132">后续步骤</span><span class="sxs-lookup"><span data-stu-id="72fde-132">Next steps</span></span>

<span data-ttu-id="72fde-133">请参阅 [Microsoft 合规性扩展入门](dlp-chrome-get-started.md)，了解完整的部署过程和方案。</span><span class="sxs-lookup"><span data-stu-id="72fde-133">See [Get started with the Microsoft Compliance Extension](dlp-chrome-get-started.md) for complete deployment procedures and scenarios.</span></span>

## <a name="see-also"></a><span data-ttu-id="72fde-134">另请参阅</span><span class="sxs-lookup"><span data-stu-id="72fde-134">See also</span></span>

- [<span data-ttu-id="72fde-135">Microsoft 合规性扩展入门</span><span class="sxs-lookup"><span data-stu-id="72fde-135">Get started with Microsoft Compliance Extension</span></span>](dlp-chrome-get-started.md)
- [<span data-ttu-id="72fde-136">了解 Microsoft 365 终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="72fde-136">Learn about Microsoft 365 Endpoint data loss prevention</span></span>](endpoint-dlp-learn-about.md)
- [<span data-ttu-id="72fde-137">Microsoft 终结点数据丢失防护入门</span><span class="sxs-lookup"><span data-stu-id="72fde-137">Getting started with Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-getting-started.md)
- [<span data-ttu-id="72fde-138">使用 Microsoft 终结点数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="72fde-138">Using Microsoft Endpoint data loss prevention</span></span>](endpoint-dlp-using.md)
- [<span data-ttu-id="72fde-139">了解数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="72fde-139">Learn about data loss prevention</span></span>](dlp-learn-about-dlp.md)
- [<span data-ttu-id="72fde-140">创建、测试和优化 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="72fde-140">Create, test, and tune a DLP policy</span></span>](create-test-tune-dlp-policy.md)
- [<span data-ttu-id="72fde-141">活动资源管理器入门</span><span class="sxs-lookup"><span data-stu-id="72fde-141">Get started with Activity explorer</span></span>](data-classification-activity-explorer.md)
- [<span data-ttu-id="72fde-142">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="72fde-142">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)
- [<span data-ttu-id="72fde-143">内部风险管理</span><span class="sxs-lookup"><span data-stu-id="72fde-143">Insider Risk management</span></span>](insider-risk-management.md)
