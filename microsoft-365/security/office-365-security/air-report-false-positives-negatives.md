---
title: 如何在 Microsoft Defender for Office 365 中自动调查后报告误报或漏报
description: Microsoft Defender for Office 365 中的 AIR 是否遗漏或错误地检测到了某些内容？ 了解如何将误报或漏报提交给 Microsoft 进行分析。
keywords: 自动化， 调查， 警报， 触发器， 操作， 修正， 误报， 漏报
search.appverid: met150
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.prod: m365-security
ms.date: 01/29/2021
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
ms.topic: how-to
ms.custom:
- autoir
ms.technology: mdo
ms.openlocfilehash: 4476578939f2ece90c638c919c7e4d134ea2d9ec
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51203899"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="67452-105">如何在自动调查和响应功能中报告误报/负面影响</span><span class="sxs-lookup"><span data-stu-id="67452-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="67452-106">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="67452-106">**Applies to**</span></span>
- [<span data-ttu-id="67452-107">适用于 Office 365 计划 2 的 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="67452-107">Microsoft Defender for Office 365 plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="67452-108">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="67452-108">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="67452-109">如果 [自动调查和响应 (OFFICE 365](automated-investigation-response-office.md) 中的 AIR) 功能未检测到或错误检测到某些内容，则安全运营团队可以采取一些措施来解决此问题。</span><span class="sxs-lookup"><span data-stu-id="67452-109">If [automated investigation and response (AIR) capabilities in Office 365](automated-investigation-response-office.md) missed or wrongly detected something, there are steps your security operations team can take to fix it.</span></span> <span data-ttu-id="67452-110">此类操作包括：</span><span class="sxs-lookup"><span data-stu-id="67452-110">Such actions include:</span></span>

- <span data-ttu-id="67452-111">[向 Microsoft 报告误报/负数](#report-a-false-positivenegative-to-microsoft-for-analysis);</span><span class="sxs-lookup"><span data-stu-id="67452-111">[Reporting a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="67452-112">[根据需要调整警报](#adjust-an-alert-to-prevent-false-positives-from-recurring) (调整) ;和</span><span class="sxs-lookup"><span data-stu-id="67452-112">[Adjusting alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span>
- <span data-ttu-id="67452-113">[撤消已采取的修正操作](#undo-a-remediation-action)。</span><span class="sxs-lookup"><span data-stu-id="67452-113">[Undoing remediation actions that were taken](#undo-a-remediation-action).</span></span>

<span data-ttu-id="67452-114">使用本文作为指南。</span><span class="sxs-lookup"><span data-stu-id="67452-114">Use this article as a guide.</span></span>

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="67452-115">向 Microsoft 报告误报/负数以进行分析</span><span class="sxs-lookup"><span data-stu-id="67452-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="67452-116">如果 Microsoft Defender for Office 365 中的 AIR 错过电子邮件、电子邮件附件、电子邮件中的 URL 或 Office 文件的 URL，你可以将可疑的垃圾邮件、网络钓鱼、URL 和文件提交给 Microsoft 进行 [Office 365](admin-submission.md)扫描。</span><span class="sxs-lookup"><span data-stu-id="67452-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](admin-submission.md).</span></span>

<span data-ttu-id="67452-117">还可以将 [文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="67452-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="67452-118">调整警报以防止误报重复发生</span><span class="sxs-lookup"><span data-stu-id="67452-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="67452-119">如果警报是由合法使用触发，或者警报不准确，可以在 [Cloud App Security](/cloud-app-security/managing-alerts)门户中管理警报。</span><span class="sxs-lookup"><span data-stu-id="67452-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="67452-120">如果你的组织除 Office 365 外还使用[Microsoft Defender for Endpoint，](/windows/security/threat-protection)并且文件、IP 地址、URL 或域在设备上被视为恶意软件，即使安全，也可以为设备创建包含"允许"操作的自定义[指示器。](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)</span><span class="sxs-lookup"><span data-stu-id="67452-120">If your organization is using [Microsoft Defender for Endpoint](/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="67452-121">撤消修正操作</span><span class="sxs-lookup"><span data-stu-id="67452-121">Undo a remediation action</span></span>

<span data-ttu-id="67452-122">在大多数情况下，如果对电子邮件、电子邮件附件或 URL 采取修正操作，并且该项目实际上不是威胁，则安全运营团队可以撤消修正操作，并采取措施防止误报重复发生。</span><span class="sxs-lookup"><span data-stu-id="67452-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="67452-123">可以使用威胁资源管理器 [或](#undo-an-action-using-threat-explorer) "操作" [选项卡进行调查](#undo-an-action-in-the-action-center) 以撤消操作。</span><span class="sxs-lookup"><span data-stu-id="67452-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-in-the-action-center) to undo an action.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="67452-124">在尝试执行以下任务之前，请确保你拥有必要的权限。</span><span class="sxs-lookup"><span data-stu-id="67452-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="67452-125">使用威胁资源管理器撤消操作</span><span class="sxs-lookup"><span data-stu-id="67452-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="67452-126">借助威胁资源管理器，安全运营团队可以查找受操作影响的电子邮件，并可能撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="67452-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="67452-127">方案</span><span class="sxs-lookup"><span data-stu-id="67452-127">Scenario</span></span>|<span data-ttu-id="67452-128">撤消选项</span><span class="sxs-lookup"><span data-stu-id="67452-128">Undo Options</span></span>|<span data-ttu-id="67452-129">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="67452-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="67452-130">电子邮件已路由到用户的"垃圾邮件"文件夹</span><span class="sxs-lookup"><span data-stu-id="67452-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="67452-131">- 将邮件移动到用户的"已删除邮件"文件夹</span><span class="sxs-lookup"><span data-stu-id="67452-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="67452-132">- 将邮件移动到用户的收件箱</span><span class="sxs-lookup"><span data-stu-id="67452-132">- Move the message to the user's Inbox</span></span><br/><span data-ttu-id="67452-133">- 删除邮件</span><span class="sxs-lookup"><span data-stu-id="67452-133">- Delete the message</span></span>|[<span data-ttu-id="67452-134">查找并调查在 Office 365 中传递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="67452-134">Find and investigate malicious email that was delivered in Office 365</span></span>](investigate-malicious-email-that-was-delivered.md)|
|<span data-ttu-id="67452-135">已隔离电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="67452-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="67452-136">- 释放电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="67452-136">- Release the email or file</span></span><br/><span data-ttu-id="67452-137">- 删除电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="67452-137">- Delete the email or file</span></span>|[<span data-ttu-id="67452-138">以管理员角色管理隔离邮件</span><span class="sxs-lookup"><span data-stu-id="67452-138">Manage quarantined messages as an admin</span></span>](manage-quarantined-messages-and-files.md)|
|

### <a name="undo-an-action-in-the-action-center"></a><span data-ttu-id="67452-139">撤消操作中心中的操作</span><span class="sxs-lookup"><span data-stu-id="67452-139">Undo an action in the Action center</span></span>

<span data-ttu-id="67452-140">在操作中心，你可以看到已采取的修正操作并可能撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="67452-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="67452-141">转到 Microsoft 365 安全中心 <https://security.microsoft.com> () 。</span><span class="sxs-lookup"><span data-stu-id="67452-141">Go to the Microsoft 365 security center (<https://security.microsoft.com>).</span></span>
2. <span data-ttu-id="67452-142">在导航窗格中，选择操作 **中心**。</span><span class="sxs-lookup"><span data-stu-id="67452-142">In the navigation pane, select **Action center**.</span></span>
3. <span data-ttu-id="67452-143">选择 **"历史记录** "选项卡以查看已完成操作的列表。</span><span class="sxs-lookup"><span data-stu-id="67452-143">Select the **History** tab to view the list of completed actions.</span></span>
4. <span data-ttu-id="67452-144">选择一个项目。</span><span class="sxs-lookup"><span data-stu-id="67452-144">Select an item.</span></span> <span data-ttu-id="67452-145">将打开其飞出窗格。</span><span class="sxs-lookup"><span data-stu-id="67452-145">Its flyout pane opens.</span></span>
5. <span data-ttu-id="67452-146">在飞出窗格中， **选择撤消**。</span><span class="sxs-lookup"><span data-stu-id="67452-146">In the flyout pane, select **Undo**.</span></span> <span data-ttu-id="67452-147"> (只有可以撤消的操作才 **具有"撤消** "按钮。) </span><span class="sxs-lookup"><span data-stu-id="67452-147">(Only actions that can be undone will have an **Undo** button.)</span></span>

## <a name="see-also"></a><span data-ttu-id="67452-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="67452-148">See also</span></span>

- [<span data-ttu-id="67452-149">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="67452-149">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="67452-150">Microsoft Defender for Office 365 中的自动调查</span><span class="sxs-lookup"><span data-stu-id="67452-150">Automated investigations in Microsoft Defender for Office 365</span></span>](office-365-air.md)
