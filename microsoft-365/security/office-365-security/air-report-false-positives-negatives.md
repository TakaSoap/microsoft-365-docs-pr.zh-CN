---
title: 如何在 Office 365 自动调查和响应中报告误报或漏报
description: Office 365 高级威胁防护是否错过或错误地检测到了什么？ 了解如何向 Microsoft 提交误报或漏报以进行分析。
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
ms.date: 05/15/2020
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: conceptual
ms.custom: autoir
ms.openlocfilehash: 2dd67af62a400f3e217f146e6d0ee213d74ad99a
ms.sourcegitcommit: 22e9f54d0d3ead2be91a38d49325308c70f43f90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2020
ms.locfileid: "44262404"
---
# <a name="how-to-report-false-positivesnegatives-in-automated-investigation-and-response-capabilities"></a><span data-ttu-id="1a588-105">如何报告自动调查和响应功能中的误报/否定</span><span class="sxs-lookup"><span data-stu-id="1a588-105">How to report false positives/negatives in automated investigation and response capabilities</span></span>

<span data-ttu-id="1a588-106">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="1a588-106">**Applies to:**</span></span>
- <span data-ttu-id="1a588-107">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="1a588-107">Office 365 Advanced Threat Protection</span></span>

<span data-ttu-id="1a588-108">[Office 365 中的自动化调查和响应（空气）功能](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office)是否未命中或错误地检测到了什么？</span><span class="sxs-lookup"><span data-stu-id="1a588-108">Did [automated investigation and response (AIR) capabilities in Office 365](https://docs.microsoft.com/microsoft-365/security/office-365-security/automated-investigation-response-office) miss or wrongly detect something?</span></span> <span data-ttu-id="1a588-109">您可以采取一些步骤来修复它。</span><span class="sxs-lookup"><span data-stu-id="1a588-109">There are steps you can take to fix it.</span></span> <span data-ttu-id="1a588-110">可以：</span><span class="sxs-lookup"><span data-stu-id="1a588-110">You can:</span></span>
- <span data-ttu-id="1a588-111">[向 Microsoft 报告误报/负数，](#report-a-false-positivenegative-to-microsoft-for-analysis)或者</span><span class="sxs-lookup"><span data-stu-id="1a588-111">[Report a false positive/negative to Microsoft](#report-a-false-positivenegative-to-microsoft-for-analysis);</span></span>
- <span data-ttu-id="1a588-112">[调整通知](#adjust-an-alert-to-prevent-false-positives-from-recurring)（如果需要）;并</span><span class="sxs-lookup"><span data-stu-id="1a588-112">[Adjust your alerts](#adjust-an-alert-to-prevent-false-positives-from-recurring) (if needed); and</span></span> 
- <span data-ttu-id="1a588-113">[撤消对设备所执行的修正操作](#undo-a-remediation-action)。</span><span class="sxs-lookup"><span data-stu-id="1a588-113">[Undo remediation actions that were taken on devices](#undo-a-remediation-action).</span></span> 

<span data-ttu-id="1a588-114">将本文用作指南。</span><span class="sxs-lookup"><span data-stu-id="1a588-114">Use this article as a guide.</span></span> 

## <a name="report-a-false-positivenegative-to-microsoft-for-analysis"></a><span data-ttu-id="1a588-115">将误报/负数报告给 Microsoft 进行分析</span><span class="sxs-lookup"><span data-stu-id="1a588-115">Report a false positive/negative to Microsoft for analysis</span></span>

<span data-ttu-id="1a588-116">如果 Office 365 AIR 错过了电子邮件、电子邮件附件、电子邮件中的 URL 或 Office 文件中的 URL，则可以[将可疑的垃圾邮件、网络钓鱼、url 和文件提交到 Microsoft For office 365 扫描](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission)。</span><span class="sxs-lookup"><span data-stu-id="1a588-116">If Office 365 AIR missed an email message, an email attachment, a URL in an email message, or a URL in an Office file, you can [submit suspected spam, phish, URLs, and files to Microsoft for Office 365 scanning](https://docs.microsoft.com/microsoft-365/security/office-365-security/admin-submission).</span></span>

<span data-ttu-id="1a588-117">您还可以[将文件提交给 Microsoft 进行恶意软件分析](https://www.microsoft.com/wdsi/filesubmission)。</span><span class="sxs-lookup"><span data-stu-id="1a588-117">You can also [Submit a file to Microsoft for malware analysis](https://www.microsoft.com/wdsi/filesubmission).</span></span>

## <a name="adjust-an-alert-to-prevent-false-positives-from-recurring"></a><span data-ttu-id="1a588-118">调整警报以防止定期误报</span><span class="sxs-lookup"><span data-stu-id="1a588-118">Adjust an alert to prevent false positives from recurring</span></span>

<span data-ttu-id="1a588-119">如果某个警报由合法使用触发，或者该警报不准确，则可以[在云应用安全门户中管理警报](https://docs.microsoft.com/cloud-app-security/managing-alerts)。</span><span class="sxs-lookup"><span data-stu-id="1a588-119">If an alert is triggered by legitimate use, or the alert is inaccurate, you can [Manage alerts in the Cloud App Security portal](https://docs.microsoft.com/cloud-app-security/managing-alerts).</span></span>

<span data-ttu-id="1a588-120">如果您的组织使用的是除 Office 365 之外的[Microsoft Defender 高级威胁防护](https://docs.microsoft.com/windows/security/threat-protection)，并且文件、IP 地址、URL 或域在设备上被视为恶意软件，尽管它是安全的，但您可以[创建一个自定义指示器，为设备启用 "允许" 操作](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators)。</span><span class="sxs-lookup"><span data-stu-id="1a588-120">If your organization is using [Microsoft Defender Advanced Threat Protection](https://docs.microsoft.com/windows/security/threat-protection) in addition to Office 365, and a file, IP address, URL, or domain is treated as malware on a device, even though it's safe, you can [create a custom indicator with an "Allow" action for your device](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/manage-indicators).</span></span>

## <a name="undo-a-remediation-action"></a><span data-ttu-id="1a588-121">撤消修正操作</span><span class="sxs-lookup"><span data-stu-id="1a588-121">Undo a remediation action</span></span>

<span data-ttu-id="1a588-122">在大多数情况下，如果对电子邮件、电子邮件附件或 URL 执行了修正操作，而该项目实际上并不是威胁，则安全操作团队可以撤消修正操作并采取措施以防止误报定期发生。</span><span class="sxs-lookup"><span data-stu-id="1a588-122">In most cases, if a remediation action was taken on an email message, email attachment, or URL, and the item is actually not a threat, your security operations team can undo the remediation action and take steps to prevent the false positive from recurring.</span></span> <span data-ttu-id="1a588-123">您可以使用 "[威胁资源管理器](#undo-an-action-using-threat-explorer)" 或 "[操作" 选项卡进行调查](#undo-an-action-using-the-actions-tab-for-an-investigation)以撤消某项操作。</span><span class="sxs-lookup"><span data-stu-id="1a588-123">You can either use [Threat Explorer](#undo-an-action-using-threat-explorer) or the [Actions tab for an investigation](#undo-an-action-using-the-actions-tab-for-an-investigation) to undo an action.</span></span> 

> [!IMPORTANT]
> <span data-ttu-id="1a588-124">在尝试执行以下任务之前，请确保您具有所需的权限。</span><span class="sxs-lookup"><span data-stu-id="1a588-124">Make sure you have the necessary permissions before attempting to perform the following tasks.</span></span>

### <a name="undo-an-action-using-threat-explorer"></a><span data-ttu-id="1a588-125">使用威胁资源管理器撤消操作</span><span class="sxs-lookup"><span data-stu-id="1a588-125">Undo an action using Threat Explorer</span></span>

<span data-ttu-id="1a588-126">通过威胁浏览器，安全操作团队可以找到受操作影响的电子邮件，并可能撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="1a588-126">With Threat Explorer, your security operations team can find an email affected by an action and potentially undo the action.</span></span>

|<span data-ttu-id="1a588-127">应用场景</span><span class="sxs-lookup"><span data-stu-id="1a588-127">Scenario</span></span>  |<span data-ttu-id="1a588-128">撤消选项</span><span class="sxs-lookup"><span data-stu-id="1a588-128">Undo Options</span></span>  |<span data-ttu-id="1a588-129">了解更多</span><span class="sxs-lookup"><span data-stu-id="1a588-129">Learn more</span></span> |
|---------|---------|---------|
|<span data-ttu-id="1a588-130">将电子邮件路由到用户的 "垃圾邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="1a588-130">An email message was routed to a user's Junk Email folder</span></span>     |<span data-ttu-id="1a588-131">-将邮件移动到用户的 "已删除邮件" 文件夹</span><span class="sxs-lookup"><span data-stu-id="1a588-131">- Move the message to the user's Deleted Items folder</span></span><br/><span data-ttu-id="1a588-132">-将邮件移动到用户的收件箱</span><span class="sxs-lookup"><span data-stu-id="1a588-132">- Move the message to the user's Inbox</span></span> <br/><span data-ttu-id="1a588-133">-删除邮件</span><span class="sxs-lookup"><span data-stu-id="1a588-133">- Delete the message</span></span>          |[<span data-ttu-id="1a588-134">查找并调查 Office 365 中提供的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="1a588-134">Find and investigate malicious email that was delivered in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/investigate-malicious-email-that-was-delivered) |
|<span data-ttu-id="1a588-135">已隔离电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="1a588-135">An email message or a file was quarantined</span></span>     |<span data-ttu-id="1a588-136">-释放电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="1a588-136">- Release the email or file</span></span> <br/><span data-ttu-id="1a588-137">-删除电子邮件或文件</span><span class="sxs-lookup"><span data-stu-id="1a588-137">- Delete the email or file</span></span>         |[<span data-ttu-id="1a588-138">以 Office 365 中的管理员身份管理隔离的邮件和文件</span><span class="sxs-lookup"><span data-stu-id="1a588-138">Manage quarantined messages and files as an administrator in Office 365</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/manage-quarantined-messages-and-files) |


### <a name="undo-an-action-using-the-actions-tab-for-an-investigation"></a><span data-ttu-id="1a588-139">使用 "操作" 选项卡进行调查以撤消操作</span><span class="sxs-lookup"><span data-stu-id="1a588-139">Undo an action using the Actions tab for an investigation</span></span>

<span data-ttu-id="1a588-140">在操作中心中，你可以看到已执行的更正操作，并且可能会撤消该操作。</span><span class="sxs-lookup"><span data-stu-id="1a588-140">In the Action center, you can see remediation actions that were taken and potentially undo the action.</span></span>

1. <span data-ttu-id="1a588-141">转到 [https://protection.office.com](https://protection.office.com) 并登录。</span><span class="sxs-lookup"><span data-stu-id="1a588-141">Go to [https://protection.office.com](https://protection.office.com) and sign in.</span></span> <span data-ttu-id="1a588-142">这将转到安全 & 合规性中心。</span><span class="sxs-lookup"><span data-stu-id="1a588-142">This takes you to the the Security & Compliance Center.</span></span>

2. <span data-ttu-id="1a588-143">转到**威胁管理**  >  **调查**。</span><span class="sxs-lookup"><span data-stu-id="1a588-143">Go to **Threat management** > **Investigations**.</span></span>

3. <span data-ttu-id="1a588-144">在调查列表中，选择项目 ID 旁边的 "**在新窗口中打开**" 图标。</span><span class="sxs-lookup"><span data-stu-id="1a588-144">In the list of investigations, select the **Open in new window** icon next to an item's ID.</span></span>

4. <span data-ttu-id="1a588-145">选择 "**操作**" 选项卡。</span><span class="sxs-lookup"><span data-stu-id="1a588-145">Select the **Actions** tab.</span></span>

5. <span data-ttu-id="1a588-146">选择 "已**完成**" 状态的项目，并在 "**决策**" 列中查找链接（如 "**已批准**"）。</span><span class="sxs-lookup"><span data-stu-id="1a588-146">Select an item that has status of **Completed**, and look for a link, such as **Approved**, in the **Decision** column.</span></span> <span data-ttu-id="1a588-147">这将打开一个浮出控件，其中包含有关操作的更多详细信息。</span><span class="sxs-lookup"><span data-stu-id="1a588-147">This opens a flyout with more details about the action.</span></span>

6. <span data-ttu-id="1a588-148">若要撤消操作，请选择 "**删除修正**"。</span><span class="sxs-lookup"><span data-stu-id="1a588-148">To undo the action, select **Delete remediation**.</span></span>

## <a name="related-articles"></a><span data-ttu-id="1a588-149">相关文章</span><span class="sxs-lookup"><span data-stu-id="1a588-149">Related articles</span></span>

[<span data-ttu-id="1a588-150">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="1a588-150">Office 365 Advanced Threat Protection</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)

[<span data-ttu-id="1a588-151">开始在 Office 365 中使用自动调查和响应（AIR）</span><span class="sxs-lookup"><span data-stu-id="1a588-151">Get started using Automated investigation and response (AIR) in Office 365</span></span>](office-365-air.md)