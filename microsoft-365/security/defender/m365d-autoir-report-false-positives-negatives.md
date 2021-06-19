---
title: 解决邮件中的误报或Microsoft 365 Defender
description: AIR 在设备中是否遗漏或Microsoft 365 Defender？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
keywords: 自动化， 调查， 警报， 修正， 误报， 漏报
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: how-to
ms.custom: autoir
ms.reviewer: evaldm, isco
ms.technology: m365d
ms.openlocfilehash: f60208b06e66c1e9803e05ee1fc41376824e9b56
ms.sourcegitcommit: bc64d9f619259bd0a94e43a9010aae5cffb4d6c4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/19/2021
ms.locfileid: "53022530"
---
# <a name="address-false-positives-or-false-negatives-in-microsoft-365-defender"></a><span data-ttu-id="03262-105">解决邮件中的误报或Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03262-105">Address false positives or false negatives in Microsoft 365 Defender</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="03262-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="03262-106">**Applies to:**</span></span>
- <span data-ttu-id="03262-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03262-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="03262-108">任何威胁防护解决方案偶尔会出现误报或负面影响。</span><span class="sxs-lookup"><span data-stu-id="03262-108">False positives or negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="03262-109">如果[自动调查和响应功能Microsoft 365 Defender](m365d-autoir.md)检测错误，则安全运营团队可以采取以下步骤：</span><span class="sxs-lookup"><span data-stu-id="03262-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- [<span data-ttu-id="03262-110">向 Microsoft 报告误报/负数</span><span class="sxs-lookup"><span data-stu-id="03262-110">Report a false positive/negative to Microsoft</span></span>](#report-a-false-positivenegative-to-microsoft-for-analysis)
- <span data-ttu-id="03262-111">[根据需要调整](#adjust-an-alert-to-prevent-false-positives-from-recurring) (通知) </span><span class="sxs-lookup"><span data-stu-id="03262-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed)</span></span>
- [<span data-ttu-id="03262-112">撤消对设备采取的修正操作</span><span class="sxs-lookup"><span data-stu-id="03262-112">Undo remediation actions that were taken on devices</span></span>](#undo-a-remediation-action-that-was-taken-on-a-device)

<span data-ttu-id="03262-113">以下各节介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="03262-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="03262-114">向 Microsoft 报告误报/负数以进行分析</span><span class="sxs-lookup"><span data-stu-id="03262-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="03262-115">未接或检测错误的项目</span><span class="sxs-lookup"><span data-stu-id="03262-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="03262-116">服务</span><span class="sxs-lookup"><span data-stu-id="03262-116">Service</span></span>  |<span data-ttu-id="03262-117">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="03262-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="03262-118">- 电子邮件</span><span class="sxs-lookup"><span data-stu-id="03262-118">- Email message</span></span> <br/><span data-ttu-id="03262-119">- 电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="03262-119">- Email attachment</span></span> <br/><span data-ttu-id="03262-120">- 电子邮件中的 URL</span><span class="sxs-lookup"><span data-stu-id="03262-120">- URL in an email message</span></span><br/><span data-ttu-id="03262-121">- 文件Office URL</span><span class="sxs-lookup"><span data-stu-id="03262-121">- URL in an Office file</span></span>      |[<span data-ttu-id="03262-122">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="03262-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="03262-123">将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft 进行扫描</span><span class="sxs-lookup"><span data-stu-id="03262-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="03262-124">设备上的文件或应用</span><span class="sxs-lookup"><span data-stu-id="03262-124">File or app on a device</span></span>    |[<span data-ttu-id="03262-125">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="03262-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="03262-126">将文件提交给 Microsoft 进行恶意软件分析</span><span class="sxs-lookup"><span data-stu-id="03262-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="03262-127">调整警报以防止误报重复发生</span><span class="sxs-lookup"><span data-stu-id="03262-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="03262-128">应用场景</span><span class="sxs-lookup"><span data-stu-id="03262-128">Scenario</span></span> |<span data-ttu-id="03262-129">服务</span><span class="sxs-lookup"><span data-stu-id="03262-129">Service</span></span> |<span data-ttu-id="03262-130">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="03262-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="03262-131">- 通过合法使用触发警报</span><span class="sxs-lookup"><span data-stu-id="03262-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="03262-132">- 警报不准确</span><span class="sxs-lookup"><span data-stu-id="03262-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="03262-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="03262-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="03262-134">或者</span><span class="sxs-lookup"><span data-stu-id="03262-134">or</span></span> <br/>[<span data-ttu-id="03262-135">Azure 威胁防护</span><span class="sxs-lookup"><span data-stu-id="03262-135">Azure threat protection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="03262-136">管理 云应用安全 门户中的警报</span><span class="sxs-lookup"><span data-stu-id="03262-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="03262-137">文件、IP 地址、URL 或域在设备上被视为恶意软件，即使安全</span><span class="sxs-lookup"><span data-stu-id="03262-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="03262-138">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="03262-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="03262-139">使用"允许"操作创建自定义指示器</span><span class="sxs-lookup"><span data-stu-id="03262-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="03262-140">撤消在设备上采取的修正操作</span><span class="sxs-lookup"><span data-stu-id="03262-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="03262-141">如果对实体（如设备或电子邮件 (）采取修正操作) 并且受影响的实体实际上不是威胁，则安全运营团队可以在操作中心撤消修正 [操作](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="03262-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="03262-142">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="03262-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="03262-143">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="03262-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="03262-144">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="03262-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="03262-145">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="03262-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="03262-146">在飞出窗格中， **选择撤消**。</span><span class="sxs-lookup"><span data-stu-id="03262-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="03262-147">请参阅 [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions)。</span><span class="sxs-lookup"><span data-stu-id="03262-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="03262-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="03262-148">See also</span></span>

- [<span data-ttu-id="03262-149">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="03262-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="03262-150">通过高级搜寻主动搜寻Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="03262-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
