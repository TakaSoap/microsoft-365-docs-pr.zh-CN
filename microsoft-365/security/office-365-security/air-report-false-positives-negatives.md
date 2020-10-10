---
title: 如何在 Microsoft Defender for Office 365 中进行自动调查后报告误报或漏报
description: Microsoft Defender for Office 365 中的无线检测到缺少或错误地检测到了什么？ 了解如何向 Microsoft 提交误报或漏报以进行分析。
keywords: 自动化、调查、警报、触发器、操作、修正、误报、假负
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
ms.date: 09/29/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365-initiative-defender-office365
ms.topic: conceptual
ms.custom:
- autoir
ms.openlocfilehash: b9f037e3e6d798122b8d3c7ffd3476e34bd5a76b
ms.sourcegitcommit: 5e1b8c959a081022826fb09358730096248507ed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/09/2020
ms.locfileid: "48411958"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="9550b-105">如何报告自动调查和响应功能中的误报/否定</span><span class="sxs-lookup"><span data-stu-id="9550b-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


<span data-ttu-id="9550b-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="9550b-106">**Applies to:**</span></span>
- <span data-ttu-id="9550b-107">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9550b-107">Microsoft Defender for Office 365</span></span>

<span data-ttu-id="9550b-108">[Office 365 中的自动调查和响应 (空中) 功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)是否丢失或错误地检测到了什么？</span><span class="sxs-lookup"><span data-stu-id="9550b-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="9550b-109">您可以采取一些步骤来修复它。</span><span class="sxs-lookup"><span data-stu-id="9550b-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="9550b-110">可执行下列操作：</span><span class="sxs-lookup"><span data-stu-id="9550b-110">You can:</span></span>
- <span data-ttu-id="9550b-111">[向 Microsoft 报告误报/负数，](#report-a-false-positivenegative-to-microsoft-for-analysis)或者</span><span class="sxs-lookup"><span data-stu-id="9550b-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="9550b-112">根据需要[调整通知](#adjust-an-alert-to-prevent-false-positives-from-recurring) () ;并</span><span class="sxs-lookup"><span data-stu-id="9550b-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="9550b-113">[撤消所执行的修正操作](#undo-a-remediation-action)。</span><span class="sxs-lookup"><span data-stu-id="9550b-113">[Undo remediation actions that were taken](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="9550b-114">将本文用作指南。</span><span class="sxs-lookup"><span data-stu-id="9550b-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="9550b-115">将误报/负数报告给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="9550b-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="9550b-116">如果 Microsoft Defender for Office 365 中的无线版错过了电子邮件、电子邮件附件、电子邮件中的 URL 或 Office 文件中的 URL，则可以 [将可疑的垃圾邮件、网络钓鱼、url 和文件提交到 Microsoft For office 365 扫描](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)。</span><span class="sxs-lookup"><span data-stu-id="9550b-116">If AIR in Microsoft Defender for Office 365 missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="9550b-117">您还可以 [将文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="9550b-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="9550b-118">调整警报以防止定期误报</span><span class="sxs-lookup"><span data-stu-id="9550b-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="9550b-119">如果某个警报由合法使用触发，或者该警报不准确，则可以 [在云应用安全门户中管理警报](https://docs.microsoft.com/cloud-app-security/managing-alerts)。</span><span class="sxs-lookup"><span data-stu-id="9550b-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="9550b-120">如果您的组织使用的是 [Microsoft Defender For Endpoint](https://docs.microsoft.com/windows/security/threat-protection) （除了 Office 365），并且文件、IP 地址、URL 或域在设备上被视为恶意软件，尽管它是安全的，但您可以 [使用设备的 "允许" 操作创建自定义指示器](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="9550b-120">If your organization is using [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="9550b-121">撤消修正操作</span><span class="sxs-lookup"><span data-stu-id="9550b-121">Undo a remediation action</span></span>

<span data-ttu-id="9550b-122">在大多数情况下，如果对电子邮件、电子邮件附件或 URL 执行了修正操作，而该项目实际上并不是威胁，则安全操作团队可以撤消修正操作并采取措施以防止误报定期发生。</span><span class="sxs-lookup"><span data-stu-id="9550b-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="9550b-123">您可以使用 " [威胁资源管理器](#undo-an-action-using-threat-explorer) " 或 " [操作" 选项卡进行调查](#undo-an-action-using-the-actions-tab-for-an-investigation) 以撤消某项操作。</span><span class="sxs-lookup"><span data-stu-id="9550b-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="9550b-124">在尝试执行以下任务之前，请确保您具有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="9550b-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="9550b-125">使用威胁资源管理器撤消操作</span><span class="sxs-lookup"><span data-stu-id="9550b-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="9550b-126">通过威胁浏览器，安全操作团队可以找到受操作影响的电子邮件，并可能撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="9550b-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

****

|<span data-ttu-id="9550b-127">方案</span><span class="sxs-lookup"><span data-stu-id="9550b-127">Scenario</span></span>|<span data-ttu-id="9550b-128">撤消选项</span><span class="sxs-lookup"><span data-stu-id="9550b-128">Undo Options</span></span>|<span data-ttu-id="9550b-129">了解详细信息</span><span class="sxs-lookup"><span data-stu-id="9550b-129">Learn more</span></span>|
|---|---|---|
|<span data-ttu-id="9550b-130">将电子邮件路由到用户的 "垃圾邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="9550b-130">An email message was routed to a user's Junk Email folder</span></span>|<span data-ttu-id="9550b-131">-将邮件移动到用户的 "已删除邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="9550b-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="9550b-132">-将邮件移动到用户的收件箱</span><span class="sxs-lookup"><span data-stu-id="9550b-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="9550b-133">-删除邮件</span><span class="sxs-lookup"><span data-stu-id="9550b-133">- Delete the message</span></span>|[<span data-ttu-id="9550b-134">查找并调查 Office 365 中提供的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="9550b-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered)|
|<span data-ttu-id="9550b-135">已隔离电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="9550b-135">An email message or a file was quarantined</span></span>|<span data-ttu-id="9550b-136">-释放电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="9550b-136">- Release the email or file</span></span> <br/><span data-ttu-id="9550b-137">-删除电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="9550b-137">- Delete the email or file</span></span>|[<span data-ttu-id="9550b-138">以 Office 365 中的管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="9550b-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files)|
|

### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="9550b-139">使用 "操作" 选项卡进行调查以撤消操作</span><span class="sxs-lookup"><span data-stu-id="9550b-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="9550b-140">在操作中心中，你可以看到已执行的更正操作，并且可能会撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="9550b-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="9550b-141">转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="9550b-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="9550b-142">这将转到安全 & 合规中心。</span><span class="sxs-lookup"><span data-stu-id="9550b-142">This takes you to the Security & Compliance Center.</span></span>

2. <span data-ttu-id="9550b-143">转到**威胁管理**  >  **调查**。</span><span class="sxs-lookup"><span data-stu-id="9550b-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="9550b-144">在调查列表中，选择项目 ID 旁边的 " **在新窗口中打开** " 图标。</span><span class="sxs-lookup"><span data-stu-id="9550b-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="9550b-145">选择 " **操作** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="9550b-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="9550b-146">选择 "已**完成**" 状态的项目，并在 "**决策**" 列中查找链接（如 "**已批准**"）。</span><span class="sxs-lookup"><span data-stu-id="9550b-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="9550b-147">这将打开一个浮出控件，其中包含有关操作的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="9550b-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="9550b-148">若要撤消操作，请选择 " **删除修正**"。</span><span class="sxs-lookup"><span data-stu-id="9550b-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="9550b-149">相关文章</span><span class="sxs-lookup"><span data-stu-id="9550b-149">Related articles</span></span>

[<span data-ttu-id="9550b-150">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="9550b-150">Microsoft Defender for Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="9550b-151">Microsoft Defender for Office 365 中的空气</span><span class="sxs-lookup"><span data-stu-id="9550b-151">AIR in Microsoft Defender for Office 365</span></span>](office-365-air.md)
