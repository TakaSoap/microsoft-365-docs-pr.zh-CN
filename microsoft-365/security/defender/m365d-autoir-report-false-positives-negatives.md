---
title: 在 defender 的 AIR 中处理误报Microsoft 365漏报
description: DEFENDER 中的 AIR 是否遗漏或Microsoft 365错误？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
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
ms.openlocfilehash: 727ca529dc1a16af778e01a08c9adcfe42b9b974
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245464"
---
# <a name="handle-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="87807-105">处理自动调查和响应功能中的误报/负面影响</span><span class="sxs-lookup"><span data-stu-id="87807-105">Handle false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

<span data-ttu-id="87807-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="87807-106">**Applies to:**</span></span>
- <span data-ttu-id="87807-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="87807-107">Microsoft 365 Defender</span></span>

<span data-ttu-id="87807-108">任何威胁防护解决方案偶尔会出现误报/负面影响。</span><span class="sxs-lookup"><span data-stu-id="87807-108">False positives/negatives can occasionally occur with any threat protection solution.</span></span> <span data-ttu-id="87807-109">如果[Defender 中的](m365d-autoir.md)自动调查和响应功能Microsoft 365或错误检测到某些内容，则安全操作团队可以采取以下步骤：</span><span class="sxs-lookup"><span data-stu-id="87807-109">If [automated investigation and response capabilities](m365d-autoir.md) in Microsoft 365 Defender missed or wrongly detected something, there are steps your security operations team can take:</span></span>

- <span data-ttu-id="87807-110">[向 Microsoft 报告误报/负数](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="87807-110">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="87807-111">[根据需要调整警报](#adjust-an-alert-to-prevent-false-positives-from-recurring) (调整) ;和</span><span class="sxs-lookup"><span data-stu-id="87807-111">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="87807-112">[撤消对设备采取的修正操作](#undo-a-remediation-action-that-was-taken-on-a-device)。</span><span class="sxs-lookup"><span data-stu-id="87807-112">[Undo remediation actions that were taken on devices](#undo-a-remediation-action-that-was-taken-on-a-device).</span></span> 

<span data-ttu-id="87807-113">以下各节介绍如何执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="87807-113">The following sections describe how to perform these tasks.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="87807-114">向 Microsoft 报告误报/负数以进行分析</span><span class="sxs-lookup"><span data-stu-id="87807-114">Report a false positive/negative to Microsoft for analysis</span></span>

|<span data-ttu-id="87807-115">未接或检测错误的项目</span><span class="sxs-lookup"><span data-stu-id="87807-115">Item missed or wrongly detected</span></span> |<span data-ttu-id="87807-116">服务</span><span class="sxs-lookup"><span data-stu-id="87807-116">Service</span></span>  |<span data-ttu-id="87807-117">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="87807-117">What to do</span></span>  |
|---------|---------|---------|
|<span data-ttu-id="87807-118">- 电子邮件</span><span class="sxs-lookup"><span data-stu-id="87807-118">- Email message</span></span> <br/><span data-ttu-id="87807-119">- 电子邮件附件</span><span class="sxs-lookup"><span data-stu-id="87807-119">- Email attachment</span></span> <br/><span data-ttu-id="87807-120">- 电子邮件中的 URL</span><span class="sxs-lookup"><span data-stu-id="87807-120">- URL in an email message</span></span><br/><span data-ttu-id="87807-121">- 文件Office URL</span><span class="sxs-lookup"><span data-stu-id="87807-121">- URL in an Office file</span></span>      |[<span data-ttu-id="87807-122">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="87807-122">Microsoft Defender for Office 365</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365)        |[<span data-ttu-id="87807-123">将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft 进行扫描</span><span class="sxs-lookup"><span data-stu-id="87807-123">Submit suspected spam, phish, URLs, and files to Microsoft for scanning</span></span>](../office-365-security/admin-submission.md)         |
|<span data-ttu-id="87807-124">设备上的文件或应用</span><span class="sxs-lookup"><span data-stu-id="87807-124">File or app on a device</span></span>    |[<span data-ttu-id="87807-125">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="87807-125">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection)         |[<span data-ttu-id="87807-126">将文件提交给 Microsoft 进行恶意软件分析</span><span class="sxs-lookup"><span data-stu-id="87807-126">Submit a file to Microsoft for malware analysis</span></span>](https://www.microsoft.com/wdsi/filesubmission)         |

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="87807-127">调整警报以防止误报重复发生</span><span class="sxs-lookup"><span data-stu-id="87807-127">Adjust an alert to prevent false positives from recurring</span></span>

|<span data-ttu-id="87807-128">应用场景</span><span class="sxs-lookup"><span data-stu-id="87807-128">Scenario</span></span> |<span data-ttu-id="87807-129">服务</span><span class="sxs-lookup"><span data-stu-id="87807-129">Service</span></span> |<span data-ttu-id="87807-130">需执行的操作</span><span class="sxs-lookup"><span data-stu-id="87807-130">What to do</span></span> |
|--------|--------|--------|
|<span data-ttu-id="87807-131">- 通过合法使用触发警报</span><span class="sxs-lookup"><span data-stu-id="87807-131">- An alert is triggered by legitimate use</span></span> <br/><span data-ttu-id="87807-132">- 警报不准确</span><span class="sxs-lookup"><span data-stu-id="87807-132">- An alert is inaccurate</span></span>    |[<span data-ttu-id="87807-133">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="87807-133">Microsoft Cloud App Security</span></span>](/cloud-app-security)<br/> <span data-ttu-id="87807-134">或</span><span class="sxs-lookup"><span data-stu-id="87807-134">or</span></span> <br/>[<span data-ttu-id="87807-135">Azure 高级威胁检测</span><span class="sxs-lookup"><span data-stu-id="87807-135">Azure Advanced Threat Detection</span></span>](/azure/security/fundamentals/threat-detection)         |[<span data-ttu-id="87807-136">管理 云应用安全 门户中的警报</span><span class="sxs-lookup"><span data-stu-id="87807-136">Manage alerts in the Cloud App Security portal</span></span>](/cloud-app-security/managing-alerts)         |
|<span data-ttu-id="87807-137">文件、IP 地址、URL 或域在设备上被视为恶意软件，即使安全</span><span class="sxs-lookup"><span data-stu-id="87807-137">A file, IP address, URL, or domain is treated as malware on a device, even though it's safe</span></span>|[<span data-ttu-id="87807-138">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="87807-138">Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection) |[<span data-ttu-id="87807-139">使用"允许"操作创建自定义指示器</span><span class="sxs-lookup"><span data-stu-id="87807-139">Create a custom indicator with an "Allow" action</span></span>](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators) |

## <a name="undo-a-remediation-action-that-was-taken-on-a-device"></a><span data-ttu-id="87807-140">撤消在设备上采取的修正操作</span><span class="sxs-lookup"><span data-stu-id="87807-140">Undo a remediation action that was taken on a device</span></span>

<span data-ttu-id="87807-141">如果对实体（如设备或电子邮件 (）采取修正操作) 并且受影响的实体实际上不是威胁，则安全运营团队可以在操作中心撤消修正 [操作](m365d-action-center.md)。</span><span class="sxs-lookup"><span data-stu-id="87807-141">If a remediation action was taken on an entity (such as a device or an email message) and the affected entity is not actually a threat, your security operations team can undo the remediation action in the [Action center](m365d-action-center.md).</span></span>

1. <span data-ttu-id="87807-142">转到 [https://security.microsoft.com](https://security.microsoft.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="87807-142">Go to [https://security.microsoft.com](https://security.microsoft.com) and sign in.</span></span> 
2. <span data-ttu-id="87807-143">在“导航”窗格中，选择“操作中心”。</span><span class="sxs-lookup"><span data-stu-id="87807-143">In the navigation pane, choose **Action center**.</span></span> 
3. <span data-ttu-id="87807-144">在 **"历史记录** "选项卡上，选择要撤消的操作。</span><span class="sxs-lookup"><span data-stu-id="87807-144">On the **History** tab, select an action that you want to undo.</span></span> <span data-ttu-id="87807-145">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="87807-145">Its flyout pane opens.</span></span>
4. <span data-ttu-id="87807-146">在飞出窗格中， **选择撤消**。</span><span class="sxs-lookup"><span data-stu-id="87807-146">In the flyout pane, select **Undo**.</span></span>

> [!TIP]
> <span data-ttu-id="87807-147">请参阅 [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions)。</span><span class="sxs-lookup"><span data-stu-id="87807-147">See [Undo completed actions](m365d-autoir-actions.md#undo-completed-actions).</span></span>

## <a name="see-also"></a><span data-ttu-id="87807-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="87807-148">See also</span></span>

- [<span data-ttu-id="87807-149">查看自动调查的详细信息和结果</span><span class="sxs-lookup"><span data-stu-id="87807-149">View the details and results of an automated investigation</span></span>](m365d-autoir-results.md)
- [<span data-ttu-id="87807-150">在 defender 中通过高级搜寻主动Microsoft 365威胁</span><span class="sxs-lookup"><span data-stu-id="87807-150">Proactively hunt for threats with advanced hunting in Microsoft 365 Defender</span></span>](advanced-hunting-overview.md)
- [<span data-ttu-id="87807-151">解决 Microsoft Defender for Endpoint 中的误报/漏报</span><span class="sxs-lookup"><span data-stu-id="87807-151">Address false positives/negatives in Microsoft Defender for Endpoint</span></span>](/windows/security/threat-protection/microsoft-defender-atp/defender-endpoint-false-positives-negatives)