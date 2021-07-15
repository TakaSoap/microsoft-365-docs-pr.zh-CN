---
title: 调查异常检测警报
f1.keywords:
- NOCSH
ms.author: v-tophillips
author: v-tophillips
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.collection: m365-security-compliance
localization_priority: Priority
search.appverid:
- MOE150
- MET150
description: 调查异常检测警报。
ms.openlocfilehash: 6797cdcbfd2a2d3c32768a158a5f8cd0fc579d56
ms.sourcegitcommit: 41c7f7bd5c808ee5ceca0f6efe13d4e67da0262b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/14/2021
ms.locfileid: "53420117"
---
# <a name="investigate-anomaly-detection-alerts"></a><span data-ttu-id="6bb1a-103">调查异常检测警报</span><span class="sxs-lookup"><span data-stu-id="6bb1a-103">Investigate anomaly detection alerts</span></span>

 <span data-ttu-id="6bb1a-104">Microsoft 应用治理提供针对恶意活动的安全检测和警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-104">Microsoft app governance provides security detections and alerts for malicious activities.</span></span> <span data-ttu-id="6bb1a-105">本指南旨在为你提供有关每个警报的一般和实用信息，以帮助你完成调查和修正任务。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-105">The purpose of this guide is to provide you with general and practical information on each alert, to help with your investigation and remediation tasks.</span></span> <span data-ttu-id="6bb1a-106">本指南包含有关触发警报的条件的一般信息。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-106">Included in this guide is general information about the conditions for triggering alerts.</span></span> <span data-ttu-id="6bb1a-107">由于异常检测本质上不可确定，因此只有当存在偏离规范的行为时，才会触发异常检测。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-107">Because anomaly detections are non-deterministic by nature, they're only triggered when there's behavior that deviates from the norm.</span></span> <span data-ttu-id="6bb1a-108">最后，由于一些警报可能处于预览状态，因此请定期查看官方文档以了解更新的警报状态。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-108">Finally, some alerts may be in preview, so regularly review the official documentation for updated alert status.</span></span>

## <a name="mitre-attck"></a><span data-ttu-id="6bb1a-109">MITRE ATT&CK</span><span class="sxs-lookup"><span data-stu-id="6bb1a-109">MITRE ATT&CK</span></span>

<span data-ttu-id="6bb1a-110">为了更轻松地映射 Microsoft 应用治理警报和熟悉的 MITRE ATT&CK 矩阵之间的关系，我们已按其相应的 MITRE ATT&CK 策略对警报进行了分类。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-110">To make it easier to map the relationship between Microsoft app governance alerts and the familiar MITRE ATT&CK Matrix, we've categorized the alerts by their corresponding MITRE ATT&CK tactic.</span></span> <span data-ttu-id="6bb1a-111">借助此附加参考，可以更轻松地了解触发 Microsoft 应用程序安全和治理警报时可能使用的可疑攻击技术。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-111">This additional reference makes it easier to understand the suspected attacks technique potentially in use when Microsoft Application Security and Governance alert is triggered.</span></span>

<span data-ttu-id="6bb1a-112">本指南提供有关调查和修正以下类别中的 Microsoft 应用治理警报的信息。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-112">This guide provides information about investigating and remediating Microsoft app governance alerts in the following categories.</span></span>

- <span data-ttu-id="6bb1a-113">初始访问</span><span class="sxs-lookup"><span data-stu-id="6bb1a-113">Initial Access</span></span>
- <span data-ttu-id="6bb1a-114">执行</span><span class="sxs-lookup"><span data-stu-id="6bb1a-114">Execution</span></span>
- <span data-ttu-id="6bb1a-115">持久性</span><span class="sxs-lookup"><span data-stu-id="6bb1a-115">Persistence</span></span>
- <span data-ttu-id="6bb1a-116">特权提升</span><span class="sxs-lookup"><span data-stu-id="6bb1a-116">Privilege Escalation</span></span>
- <span data-ttu-id="6bb1a-117">防御规避</span><span class="sxs-lookup"><span data-stu-id="6bb1a-117">Defense Evasion</span></span>
- <span data-ttu-id="6bb1a-118">凭据访问</span><span class="sxs-lookup"><span data-stu-id="6bb1a-118">Credential Access</span></span>
- <span data-ttu-id="6bb1a-119">集合</span><span class="sxs-lookup"><span data-stu-id="6bb1a-119">Collection</span></span>
- <span data-ttu-id="6bb1a-120">外泄</span><span class="sxs-lookup"><span data-stu-id="6bb1a-120">Exfiltration</span></span>
- <span data-ttu-id="6bb1a-121">影响</span><span class="sxs-lookup"><span data-stu-id="6bb1a-121">Impact</span></span>

## <a name="security-alert-classifications"></a><span data-ttu-id="6bb1a-122">安全警报分类</span><span class="sxs-lookup"><span data-stu-id="6bb1a-122">Security alert classifications</span></span>

<span data-ttu-id="6bb1a-123">经过适当调查后，所有 Microsoft 应用治理警报都可以归类为以下活动类型之一:</span><span class="sxs-lookup"><span data-stu-id="6bb1a-123">Following proper investigation, all Microsoft app governance alerts can be classified as one of the following activity types:</span></span>

- <span data-ttu-id="6bb1a-124">真阳性(TP): 针对确认为恶意活动的警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-124">True positive (TP): An alert on a confirmed malicious activity.</span></span>
- <span data-ttu-id="6bb1a-125">良性真阳性(B-TP): 针对可疑但非恶意活动的警报，例如渗透测试或其他授权的可疑操作。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-125">Benign true positive (B-TP): An alert on suspicious but not malicious activity, such as a penetration test or other authorized suspicious action.</span></span>
- <span data-ttu-id="6bb1a-126">假阳性(FP): 针对非恶意活动的警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-126">False positive (FP): An alert on a non-malicious activity.</span></span>

## <a name="general-investigation-steps"></a><span data-ttu-id="6bb1a-127">一般调查步骤</span><span class="sxs-lookup"><span data-stu-id="6bb1a-127">General investigation steps</span></span>

<span data-ttu-id="6bb1a-128">在调查任何类型的警报时，请使用以下一般准则，从而在应用推荐操作之前更清楚地了解潜在威胁。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-128">Use the following general guidelines when investigating any type of alert to gain a clearer understanding of the potential threat before applying the recommended action.</span></span>

- <span data-ttu-id="6bb1a-129">查看应用严重性级别，并与租户中的其余应用进行比较。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-129">Review the App severity level and compare with the rest of the app in your tenant.</span></span> <span data-ttu-id="6bb1a-130">这样的查看将帮助识别租户中会带来更大风险的应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-130">This review will help you identify which Apps in your tenant pose the greater risk.</span></span>
- <span data-ttu-id="6bb1a-131">如果识别出 TP，请查看所有应用活动以了解影响。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-131">If you identify a TP, review all the App activities to gain an understanding of the impact.</span></span> <span data-ttu-id="6bb1a-132">例如，查看以下应用信息:</span><span class="sxs-lookup"><span data-stu-id="6bb1a-132">For example, review the following App information:</span></span>

  - <span data-ttu-id="6bb1a-133">授予访问权限的范围</span><span class="sxs-lookup"><span data-stu-id="6bb1a-133">Scopes granted access</span></span>
  - <span data-ttu-id="6bb1a-134">异常行为</span><span class="sxs-lookup"><span data-stu-id="6bb1a-134">Unusual behavior</span></span>  
  - <span data-ttu-id="6bb1a-135">IP 地址和位置</span><span class="sxs-lookup"><span data-stu-id="6bb1a-135">IP address and location</span></span>

## <a name="initial-access-alerts"></a><span data-ttu-id="6bb1a-136">初始访问警报</span><span class="sxs-lookup"><span data-stu-id="6bb1a-136">Initial access alerts</span></span>

<span data-ttu-id="6bb1a-137">本部分介绍了表明恶意应用可能试图保持其在组织中的立足点的警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-137">This section describes alerts indicating that a malicious app may be attempting to maintain their foothold in your organization.</span></span>  

### <a name="encoded-app-name-with-suspicious-consent-scopes"></a><span data-ttu-id="6bb1a-138">具有可疑同意范围的已编码应用名称</span><span class="sxs-lookup"><span data-stu-id="6bb1a-138">Encoded app name with suspicious consent scopes</span></span>

<span data-ttu-id="6bb1a-139">**严重性:** 中等</span><span class="sxs-lookup"><span data-stu-id="6bb1a-139">**Severity:** Medium</span></span>

<span data-ttu-id="6bb1a-140">**说明**: 此检测会识别具有字符(例如 Unicode 或已编码字符)的 OAuth 应用，其针对可疑同意范围进行请求并通过图形 API 访问用户邮件文件夹。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-140">**Description**: This detection identifies OAuth apps with characters, such as Unicode or Encoded characters, requested for suspicious consent scopes and that accessed users mail folders through the Graph API.</span></span> <span data-ttu-id="6bb1a-141">此警报可能表明试图将恶意应用伪装成已知且受信任的应用的行为，以便攻击者可以误导用户同意恶意应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-141">This alert can indicate an attempt to camouflage a malicious app as a known and trusted app so that adversaries can mislead the users into consenting to the malicious app.</span></span>

<span data-ttu-id="6bb1a-142">**TP 还是 FP?**</span><span class="sxs-lookup"><span data-stu-id="6bb1a-142">**TP or FP?**</span></span>

- <span data-ttu-id="6bb1a-143">**TP**: 如果你可以确认 OAuth 应用已使用从未知源传递的可疑范围对显示名称进行编码，则表明为真阳性。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-143">**TP**: If you can confirm that the OAuth app has Encoded the display name with suspicious scopes delivered from unknown source, then a true positive is indicated.</span></span>  

  <span data-ttu-id="6bb1a-144">**推荐操作**: 查看此应用请求的权限级别以及授予访问权限的用户。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-144">**Recommended action**: Review the level of permission requested by this app and which users granted access.</span></span> <span data-ttu-id="6bb1a-145">根据调查，你可以选择禁止访问此应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-145">Based on your investigation you can choose to ban access to this app.</span></span>

  <span data-ttu-id="6bb1a-146">要禁止访问应用，请在 OAuth 应用页面中，在要禁止应用显示的行中，选择禁用图标。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-146">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="6bb1a-147">你可以选择是否希望告知用户其安装和授权的应用已被禁用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-147">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="6bb1a-148">此通知会告知用户应用将被禁用，且他们将无法访问已连接应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-148">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="6bb1a-149">如果不希望告知用户，请取消选择“在对话框中通知授予此禁止应用访问权限的用户”。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-149">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="6bb1a-150">我们建议你告知应用用户其应用即将被禁止使用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-150">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="6bb1a-151">**FP**: 如果你要确认应用具有已编码名称，但在组织中却具有合法的商业用途。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-151">**FP**: If you are to confirm that the app has an encoded name but has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="6bb1a-152">**推荐操作**: 关闭警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-152">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="6bb1a-153">了解泄露范围</span><span class="sxs-lookup"><span data-stu-id="6bb1a-153">Understand the scope of the breach</span></span>

<span data-ttu-id="6bb1a-154">请遵循如何 [调查危险的 OAuth 应用](/cloud-app-security/investigate-risky-oauth) 的教程。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-154">Follow the tutorial on how to [investigate risky OAuth apps](/cloud-app-security/investigate-risky-oauth).</span></span>

### <a name="oauth-app-with-read-scopes-have-suspicious-reply-url"></a><span data-ttu-id="6bb1a-155">具有读取范围的 OAuth 应用具有可疑的“回复”URL</span><span class="sxs-lookup"><span data-stu-id="6bb1a-155">OAuth App with read Scopes have suspicious Reply URL</span></span>

<span data-ttu-id="6bb1a-156">**严重性:** 中等</span><span class="sxs-lookup"><span data-stu-id="6bb1a-156">**Severity**: Medium</span></span>

<span data-ttu-id="6bb1a-157">**说明**: 此检测会识别只具有“读取”范围(例如 User.Read、People.Read、Contacts.Read、Mail.Read、Contacts.Read.Shared)、通过图形 API 重定向到可疑的“回复”URL 的 OAuth 应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-157">**Description**: This detection identifies an OAuth app with only Read scopes such as User.Read, People.Read, Contacts.Read, Mail.Read, Contacts.Read.Shared redirects to suspicious Reply URL through Graph API.</span></span> <span data-ttu-id="6bb1a-158">此活动试图表明具有较低权限(例如“读取”范围)的恶意应用可能被用于进行用户帐户侦查。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-158">This activity attempts to indicate that malicious app with less privilege permission (such as Read scopes) could be exploited to conduct users account reconnaissance.</span></span>

<span data-ttu-id="6bb1a-159">**TP 还是 FP?**</span><span class="sxs-lookup"><span data-stu-id="6bb1a-159">**TP or FP?**</span></span>

- <span data-ttu-id="6bb1a-160">**TP**: 如果你能够确认具有读取范围的 OAuth 应用从未知源传递并重定向到可疑 URL，则表明为真阳性。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-160">**TP**: If you’re able to confirm that the OAuth app with read scope is delivered from an unknown source, and redirects to a suspicious URL, then a true positive is indicated.</span></span>

  <span data-ttu-id="6bb1a-161">**推荐操作**: 查看应用请求的“回复”URL 和范围。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-161">**Recommended action**: Review the Reply URL and scopes requested by the app.</span></span> <span data-ttu-id="6bb1a-162">根据调查，你可以选择禁止访问此应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-162">Based on your investigation you can choose to ban access to this app.</span></span> <span data-ttu-id="6bb1a-163">查看此应用请求的权限级别以及授予访问权限的用户。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-163">Review the level of permission requested by this app and which users have granted access.</span></span>

  <span data-ttu-id="6bb1a-164">要禁止访问应用，请在 OAuth 应用页面中，在要禁止应用显示的行中，选择禁用图标。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-164">To ban access to the app, on the OAuth apps page, on the row in which the app you want to ban appears, select the ban icon.</span></span> <span data-ttu-id="6bb1a-165">你可以选择是否希望告知用户其安装和授权的应用已被禁用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-165">You can choose whether you want to tell users the app they installed and authorized has been banned.</span></span> <span data-ttu-id="6bb1a-166">此通知会告知用户应用将被禁用，且他们将无法访问已连接应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-166">The notification lets users know the app will be disabled and they will not have access to the connected app.</span></span> <span data-ttu-id="6bb1a-167">如果不希望告知用户，请取消选择“在对话框中通知授予此禁止应用访问权限的用户”。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-167">If you do not want them to know, unselect Notify users who granted access to this banned app in the dialog.</span></span> <span data-ttu-id="6bb1a-168">我们建议你告知应用用户其应用即将被禁止使用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-168">We recommend that you let the app users know their app is about to be banned from use.</span></span>

- <span data-ttu-id="6bb1a-169">**B-TP**: 如果经过调查，你可以确认此应用在组织中具有合法的商业用途。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-169">**B-TP**: If after investigation, you can confirm that the app has a legitimate business use in the organization.</span></span>

  <span data-ttu-id="6bb1a-170">**推荐操作**: 关闭警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-170">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="6bb1a-171">了解泄露范围</span><span class="sxs-lookup"><span data-stu-id="6bb1a-171">Understand the scope of the breach</span></span> 

1. <span data-ttu-id="6bb1a-172">查看应用完成的所有活动。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-172">Review all activities done by the app.</span></span>
1. <span data-ttu-id="6bb1a-173">如果你怀疑某个应用可疑，我们建议你调查该应用在不同应用商店中的名称和“回复”URL。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-173">If you suspect that an app is suspicious, we recommend that you investigate the app’s name and Reply URL in different app stores.</span></span> <span data-ttu-id="6bb1a-174">在检查应用商店时，请重点关注以下类型的应用:</span><span class="sxs-lookup"><span data-stu-id="6bb1a-174">When checking app stores, focus on the following types of apps:</span></span>
   - <span data-ttu-id="6bb1a-175">最近创建的应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-175">Apps that have been created recently.</span></span>
   - <span data-ttu-id="6bb1a-176">具有可疑“回复”URL 的应用</span><span class="sxs-lookup"><span data-stu-id="6bb1a-176">Apps with a suspicious Reply URL</span></span>
   - <span data-ttu-id="6bb1a-177">最近未更新的应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-177">Apps that haven't been recently updated.</span></span> <span data-ttu-id="6bb1a-178">缺少更新可能表明该应用不再获得支持。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-178">Lack of updates might indicate the app is no longer supported.</span></span>
1. <span data-ttu-id="6bb1a-179">如果你仍然怀疑某个应用可疑，可以联机研究应用名称、发布者名称以及“回复”URL</span><span class="sxs-lookup"><span data-stu-id="6bb1a-179">If you still suspect that an app is suspicious, you can research the app name, publisher name, and reply URL online</span></span>  

## <a name="persistence-alerts"></a><span data-ttu-id="6bb1a-180">持久性警报</span><span class="sxs-lookup"><span data-stu-id="6bb1a-180">Persistence alerts</span></span>

<span data-ttu-id="6bb1a-181">本部分介绍了表明恶意行动者可能试图保持其在组织中的立足点的警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-181">This section describes alerts indicating that a malicious actor may be attempting to maintain their foothold in your organization.</span></span>

### <a name="app-with-suspicious-oauth-scope-creates-inbox-rule"></a><span data-ttu-id="6bb1a-182">具有可疑 OAuth 范围的应用创建收件箱规则</span><span class="sxs-lookup"><span data-stu-id="6bb1a-182">App with Suspicious OAuth scope creates Inbox Rule</span></span>  

<span data-ttu-id="6bb1a-183">**严重性:** 中等</span><span class="sxs-lookup"><span data-stu-id="6bb1a-183">**Severity**: Medium</span></span>

<span data-ttu-id="6bb1a-184">**MITRE ID 的**: T1137.005、T1114</span><span class="sxs-lookup"><span data-stu-id="6bb1a-184">**MITRE ID’s**: T1137.005, T1114</span></span>  

<span data-ttu-id="6bb1a-185">此检测会识别同意可疑范围、创建可疑的收件箱规则，然后通过图形 API 访问用户邮件文件夹和邮件的 OAuth 应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-185">This detection identifies an OAuth App that consented to suspicious scopes, creates a suspicious inbox rule, and then accessed users mail folders and messages through the Graph API.</span></span> <span data-ttu-id="6bb1a-186">收件箱规则(例如将所有或特定电子邮件转发到另一电子邮件帐户)以及访问电子邮件并发送到另一电子邮件帐户的图形调用可能会试图泄露组织中的信息。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-186">Inbox rules, such as forwarding all or specific emails to another email account, and Graph calls to access emails and send to another email account, may be an attempt to exfiltrate information from your organization.</span></span>  

<span data-ttu-id="6bb1a-187">**TP 还是 FP?**</span><span class="sxs-lookup"><span data-stu-id="6bb1a-187">**TP or FP?**</span></span>

- <span data-ttu-id="6bb1a-188">**TP**: 如果你可以确认收件箱规则由具有从未知源传递的可疑范围的 OAuth 第三方应用创建，则表明为真阳性。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-188">**TP**: If you can confirm that inbox rule was created by an OAuth third-party app with suspicious scopes delivered from an unknown source, then a true positive is indicated.</span></span>

  <span data-ttu-id="6bb1a-189">**推荐操作**: 禁用和删除应用，重置密码，并删除收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-189">**Recommended action**:  Disable and remove the app, reset the password, and remove the inbox rule.</span></span>

  <span data-ttu-id="6bb1a-190">请遵循如何使用 Azure Active Directory 重置密码的教程以及如何删除收件箱规则的教程。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-190">Follow the tutorial on how to Reset a password using Azure Active Directory and follow the tutorial on how to remove the inbox rule.</span></span>

- <span data-ttu-id="6bb1a-191">**FP**: 如果你可以确认应用出于合法原因为新的或个人外部电子邮件帐户创建收件箱规则。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-191">**FP**: If you can confirm that app created an inbox rule to a new or personal external email account for legitimate reasons.</span></span>

  <span data-ttu-id="6bb1a-192">**推荐操作**: 关闭警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-192">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="6bb1a-193">了解泄露范围</span><span class="sxs-lookup"><span data-stu-id="6bb1a-193">Understand the scope of the breach</span></span>

1. <span data-ttu-id="6bb1a-194">查看应用完成的所有活动。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-194">Review all activities done by the app.</span></span>
1. <span data-ttu-id="6bb1a-195">查看应用授予的范围。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-195">Review the scopes granted by the app.</span></span>
1. <span data-ttu-id="6bb1a-196">查看应用创建的收件箱规则操作和条件。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-196">Review the inbox rule action and condition created by the app.</span></span>

## <a name="collection-alerts"></a><span data-ttu-id="6bb1a-197">集合警报</span><span class="sxs-lookup"><span data-stu-id="6bb1a-197">Collection alerts</span></span>

<span data-ttu-id="6bb1a-198">本部分介绍了表明恶意行动者可能试图从组织收集与其目标相关的数据的警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-198">This section describes alerts indicating that a malicious actor may be attempting to gather data of interest to their goal from your organization.</span></span>

### <a name="app-made-anomalous-graph-calls-to-read-e-mail"></a><span data-ttu-id="6bb1a-199">应用执行异常图形调用以读取电子邮件</span><span class="sxs-lookup"><span data-stu-id="6bb1a-199">App made anomalous Graph calls to read e-mail</span></span>

<span data-ttu-id="6bb1a-200">**严重性:** 中等</span><span class="sxs-lookup"><span data-stu-id="6bb1a-200">**Severity**: Medium</span></span>

<span data-ttu-id="6bb1a-201">**MITRE ID**: T1114</span><span class="sxs-lookup"><span data-stu-id="6bb1a-201">**MITRE ID**: T1114</span></span>

<span data-ttu-id="6bb1a-202">此检测会识别业务线(LOB) OAuth 应用通过图形 API 访问异常大量用户的邮件文件夹和邮件的时间，这可能表明试图泄露组织信息的行为。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-202">This detection identifies when Line of Business (LOB) OAuth App accesses an unusual and high volume of user's mail folders and messages through the Graph API, which can indicate an attempted breach of your organization.</span></span>

<span data-ttu-id="6bb1a-203">**TP 还是 FP?**</span><span class="sxs-lookup"><span data-stu-id="6bb1a-203">**TP or FP?**</span></span>

- <span data-ttu-id="6bb1a-204">**TP**: 如果你可以确认异常图形活动由业务线(LOB) OAuth 应用执行，则表明为正阳性。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-204">**TP**: If you can confirm that the unusual graph activity was performed by the Line of Business (LOB) OAuth App, then a true positive is indicated.</span></span>

  <span data-ttu-id="6bb1a-205">**推荐操作**: 暂时禁用应用并重置密码，然后重启应用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-205">**Recommend actions**: Temporarily disable the app and reset the password and then re-enable the app.</span></span>

  <span data-ttu-id="6bb1a-206">请遵循如何使用 Azure Active Directory 重置密码的教程。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-206">Follow the tutorial on how to Reset a password using Azure Active Directory.</span></span>

- <span data-ttu-id="6bb1a-207">**FP**： 如果你可以确认应用旨在执行异常大量的图形调用。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-207">**FP**: If you can confirm that the app is intended to do unusually high volume of graph calls.</span></span>

  <span data-ttu-id="6bb1a-208">**推荐操作**: 关闭警报。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-208">**Recommended action**: Dismiss the alert.</span></span>

#### <a name="understand-the-scope-of-the-breach"></a><span data-ttu-id="6bb1a-209">了解泄露范围</span><span class="sxs-lookup"><span data-stu-id="6bb1a-209">Understand the scope of the breach</span></span>

1. <span data-ttu-id="6bb1a-210">查看此应用执行的事件的活动日志，从而更好地了解其他读取电子邮件并尝试收集用户敏感电子邮件信息的图形活动。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-210">Review the activity log for events performed by this app to gain a better understanding of other Graph activities to read emails and attempt to collect users sensitive email information.</span></span>
1. <span data-ttu-id="6bb1a-211">监视向应用添加的意外凭据。</span><span class="sxs-lookup"><span data-stu-id="6bb1a-211">Monitor for unexpected credential being added to the app.</span></span>
