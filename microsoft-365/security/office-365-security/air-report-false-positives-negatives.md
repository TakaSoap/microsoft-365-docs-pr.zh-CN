---
title: 如何在 Microsoft Defender for Office 365 中自动调查后报告误报或漏报
description: MICROSOFT Defender for Office 365 中的 AIR 是否遗漏或错误地检测到了某些内容？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 误报， 漏报
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 01/29/2021
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 4ccc023a72ca450b1f0a433410206ccce59cb5f1
ms.sourcegitcommit: d739f48b991793c08522a3d5323beba27f0111b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/08/2021
ms.locfileid: "50142971"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="313b6-105">如何在自动调查和响应功能中报告误报/负面影响</span><span class="sxs-lookup"><span data-stu-id="313b6-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="313b6-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="313b6-106">**Applies to:**</span></span>
- <span data-ttu-id="313b6-107">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="313b6-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="313b6-108">如果 [自动调查和响应 (OFFICE 365 中的 AIR) ](automated-investigation-response-office.md) 功能未检测到或错误检测到某些内容，则安全运营团队可以采取一些步骤来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="313b6-108">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="313b6-109">此类操作包括：</span><span class="sxs-lookup"><span data-stu-id="313b6-109">Such actions include:</span></span>

- <span data-ttu-id="313b6-110">[向 Microsoft 报告误报/负数](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="313b6-110">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="313b6-111">[根据需要调整警报](#adjust-an-alert-to-prevent-false-positives-from-recurring) (调整) ;and</span><span class="sxs-lookup"><span data-stu-id="313b6-111">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="313b6-112">[撤消已采取的修正操作](#undo-a-remediation-action)。</span><span class="sxs-lookup"><span data-stu-id="313b6-112">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="313b6-113">使用本文作为指南。</span><span class="sxs-lookup"><span data-stu-id="313b6-113">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="313b6-114">向 Microsoft 报告误报/负数进行分析</span><span class="sxs-lookup"><span data-stu-id="313b6-114">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="313b6-115">如果 Microsoft Defender for Office 365 中的 AIR 错过电子邮件、电子邮件附件、电子邮件中的 URL 或 Office 文件的 URL，可以将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft 进行 [Office 365](admin-submission.md)扫描。</span><span class="sxs-lookup"><span data-stu-id="313b6-115">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="313b6-116">还可以将 [文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="313b6-116">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="313b6-117">调整警报以防止误报重复发生</span><span class="sxs-lookup"><span data-stu-id="313b6-117">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="313b6-118">如果警报是由合法使用触发的，或者警报不准确，可以在云应用安全门户中管理 [警报](https://docs.microsoft.com/cloud-app-security/managing-alerts)。</span><span class="sxs-lookup"><span data-stu-id="313b6-118">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="313b6-119">如果你的组织除了使用 Office 365 之外还使用[Microsoft Defender for Endpoint，](https://docs.microsoft.com/windows/security/threat-protection)并且文件、IP 地址、URL 或域在设备上被视为恶意软件，即使安全，你可以为设备创建一个包含"允许"操作自定义[指示器。](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="313b6-119">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="313b6-120">撤消修正操作</span><span class="sxs-lookup"><span data-stu-id="313b6-120">Undo a remediation action</span></span>

<span data-ttu-id="313b6-121">在大多数情况下，如果对电子邮件、电子邮件附件或 URL 采取修正操作，但项目实际上不是威胁，则安全运营团队可以撤消修正操作，并采取措施防止误报重复发生。</span><span class="sxs-lookup"><span data-stu-id="313b6-121">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="313b6-122">可以使用威胁资源管理器 [或](#undo-an-action-using-threat-explorer) "操作" [选项卡进行调查](#undo-an-action-in-the-action-center) 以撤消操作。</span><span class="sxs-lookup"><span data-stu-id="313b6-122">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="313b6-123">在尝试执行以下任务之前，请确保你拥有必要的权限。</span><span class="sxs-lookup"><span data-stu-id="313b6-123">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="313b6-124">使用威胁资源管理器撤消操作</span><span class="sxs-lookup"><span data-stu-id="313b6-124">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="313b6-125">借助威胁资源管理器，安全运营团队可以查找受操作影响的电子邮件，并可能撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="313b6-125">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="313b6-126">应用场景</span><span class="sxs-lookup"><span data-stu-id="313b6-126">Scenario</span></span>|<span data-ttu-id="313b6-127">撤消选项</span><span class="sxs-lookup"><span data-stu-id="313b6-127">Undo Options</span></span>|<span data-ttu-id="313b6-128">了解更多</span><span class="sxs-lookup"><span data-stu-id="313b6-128">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="313b6-129">电子邮件已路由到用户的"垃圾邮件"文件夹</span><span class="sxs-lookup"><span data-stu-id="313b6-129">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="313b6-130">- 将邮件移动到用户的"已删除邮件"文件夹</span><span class="sxs-lookup"><span data-stu-id="313b6-130">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="313b6-131">- 将邮件移动到用户的收件箱</span><span class="sxs-lookup"><span data-stu-id="313b6-131">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="313b6-132">- 删除邮件</span><span class="sxs-lookup"><span data-stu-id="313b6-132">- Delete the message</span></span>|[<span data-ttu-id="313b6-133">查找并调查在 Office 365 中传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="313b6-133">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="313b6-134">电子邮件或文件被隔离</span><span class="sxs-lookup"><span data-stu-id="313b6-134">An email message or a file was quarantined</span></span>|<span data-ttu-id="313b6-135">- 释放电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="313b6-135">- Release the email or file</span></span><br/><span data-ttu-id="313b6-136">- 删除电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="313b6-136">- Delete the email or file</span></span>|[<span data-ttu-id="313b6-137">以管理员角色管理隔离邮件</span><span class="sxs-lookup"><span data-stu-id="313b6-137">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="313b6-138">撤消操作中心中的操作</span><span class="sxs-lookup"><span data-stu-id="313b6-138">Undo an action in the Action center</span></span>

<span data-ttu-id="313b6-139">在操作中心，你可以看到已采取的修正操作并可能撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="313b6-139">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="313b6-140">转到 Microsoft 365 安全中心 [https://security.microsoft.com](https://security.microsoft.com) () 。</span><span class="sxs-lookup"><span data-stu-id="313b6-140">Go to the Microsoft 365 security center ([https://security.microsoft.com](https://security.microsoft.com)).</span></span>
2. <span data-ttu-id="313b6-141">在导航窗格中，选择 **操作中心**。</span><span class="sxs-lookup"><span data-stu-id="313b6-141">In the navigation pane, select **Action center**.</span></span> 
3. <span data-ttu-id="313b6-142">选择 **"历史记录** "选项卡以查看已完成操作的列表。</span><span class="sxs-lookup"><span data-stu-id="313b6-142">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="313b6-143">选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="313b6-143">Select an item.</span></span> <span data-ttu-id="313b6-144">随即打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="313b6-144">Its flyout pane opens.</span></span> 
5. <span data-ttu-id="313b6-145">在飞出窗格中，选择"撤消 **"。**</span><span class="sxs-lookup"><span data-stu-id="313b6-145">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="313b6-146"> (只有可以撤消的操作才 **具有"撤消** "按钮。) </span><span class="sxs-lookup"><span data-stu-id="313b6-146">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="313b6-147">另请参阅</span><span class="sxs-lookup"><span data-stu-id="313b6-147">See also</span></span>

- [<span data-ttu-id="313b6-148">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="313b6-148">Microsoft Defender for Office 365</span></span>](office-365-atp.md)
- [<span data-ttu-id="313b6-149">Microsoft Defender for Office 365 中的自动调查</span><span class="sxs-lookup"><span data-stu-id="313b6-149">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
