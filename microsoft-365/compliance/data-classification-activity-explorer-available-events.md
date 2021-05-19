---
title: 标记活动资源管理器中报告的操作
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 活动资源管理器中可用的标签活动列表。
ms.openlocfilehash: d4f6884ad39b16aeb0345f0c976d6ad87f03c05a
ms.sourcegitcommit: f780de91bc00caeb1598781e0076106c76234bad
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/19/2021
ms.locfileid: "52532250"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="4bacf-103">活动资源管理器中可用的标记活动</span><span class="sxs-lookup"><span data-stu-id="4bacf-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="4bacf-104">应用的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="4bacf-104">Sensitivity label applied</span></span>

<span data-ttu-id="4bacf-105">每次标记未标记的文档或发送带有敏感度标签的电子邮件时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-105">This event is generated each time an unlabeled document is labeled or an email is sent with a sensitivity label.</span></span> 

- <span data-ttu-id="4bacf-106">在本机应用程序和 Web 应用程序中保存Office捕获它。</span><span class="sxs-lookup"><span data-stu-id="4bacf-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="4bacf-107">在 Azure 信息保护加载项中出现时捕获它。</span><span class="sxs-lookup"><span data-stu-id="4bacf-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="4bacf-108">还可以通过"标签"事件类型字段和筛选器监视升级和 *降级标签操作* 。</span><span class="sxs-lookup"><span data-stu-id="4bacf-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="4bacf-109">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-109">Source</span></span>  |<span data-ttu-id="4bacf-110">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-110">Reported in activity explorer</span></span> | <span data-ttu-id="4bacf-111">注释</span><span class="sxs-lookup"><span data-stu-id="4bacf-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="4bacf-112">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="4bacf-113">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-113">yes</span></span> |
|<span data-ttu-id="4bacf-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-114">Outlook</span></span>| <span data-ttu-id="4bacf-115">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-115">yes</span></span> |<span data-ttu-id="4bacf-116">从 Win 32</span><span class="sxs-lookup"><span data-stu-id="4bacf-116">from Win 32</span></span> |
|<span data-ttu-id="4bacf-117">SharePoint联机，OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="4bacf-118">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-118">yes</span></span> | |
|<span data-ttu-id="4bacf-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-119">Exchange</span></span>        |<span data-ttu-id="4bacf-120">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-120">yes</span></span>         | |
|<span data-ttu-id="4bacf-121">Azure 信息保护 (AIP) 统一客户端和 AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="4bacf-122">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-122">yes</span></span> |<span data-ttu-id="4bacf-123">AIP *新标签* 操作映射到活动 *资源管理器中* 应用的标签</span><span class="sxs-lookup"><span data-stu-id="4bacf-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="4bacf-124">Microsoft 信息保护 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="4bacf-125">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-125">yes</span></span>|<span data-ttu-id="4bacf-126">AIP *新标签* 操作映射到活动 *资源管理器中* 应用的标签</span><span class="sxs-lookup"><span data-stu-id="4bacf-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="4bacf-127">权限管理服务 (RMS) </span><span class="sxs-lookup"><span data-stu-id="4bacf-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="4bacf-128">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-128">not applicable</span></span>         | |
|<span data-ttu-id="4bacf-129">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-129">Power BI desktop and web</span></span>        | <span data-ttu-id="4bacf-130">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-130">no</span></span>| <span data-ttu-id="4bacf-131">在审核日志中Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="4bacf-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="4bacf-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="4bacf-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="4bacf-133">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="4bacf-134">敏感度标签已更改</span><span class="sxs-lookup"><span data-stu-id="4bacf-134">Sensitivity label changed</span></span>

<span data-ttu-id="4bacf-135">每次更新文档或电子邮件的敏感度标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-135">This event is generated each time a sensitivity label is updated on the document or email.</span></span>

- <span data-ttu-id="4bacf-136">对于 AIP 统一客户端、统一扫描程序和 MIP  SDK 源，AIP 升级标签和 *降级* 标签操作映射到活动资源管理器 *标签已更改*</span><span class="sxs-lookup"><span data-stu-id="4bacf-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="4bacf-137">在本机应用程序和 Web 应用程序中的保存Office捕获它。</span><span class="sxs-lookup"><span data-stu-id="4bacf-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="4bacf-138">在 Azure 信息保护统一客户端加载项和扫描程序实施中出现时捕获</span><span class="sxs-lookup"><span data-stu-id="4bacf-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="4bacf-139">还可以通过"标签"事件类型字段和筛选器监视升级和 *降级标签操作* 。</span><span class="sxs-lookup"><span data-stu-id="4bacf-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="4bacf-140">对齐 *文本* 也会捕获，但 SharePoint Online 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="4bacf-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="4bacf-141">在应用上Office本机应用中Outlook敏感度标记会收集在文件保存/电子邮件发送操作之前生成的最后一个操作。</span><span class="sxs-lookup"><span data-stu-id="4bacf-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="4bacf-142">例如，如果用户在发送电子邮件之前多次更改电子邮件的标签，电子邮件发送时在电子邮件上找到的最后一个标签将捕获到 审核日志 然后在活动资源管理器中报告。</span><span class="sxs-lookup"><span data-stu-id="4bacf-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="4bacf-143">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-143">Source</span></span>  |<span data-ttu-id="4bacf-144">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-144">Reported in activity explorer</span></span>|<span data-ttu-id="4bacf-145">注释</span><span class="sxs-lookup"><span data-stu-id="4bacf-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4bacf-146">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4bacf-147">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-147">yes</span></span>         |
|<span data-ttu-id="4bacf-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-148">Outlook</span></span>         |<span data-ttu-id="4bacf-149">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-149">yes</span></span>         |<span data-ttu-id="4bacf-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="4bacf-150">Win 32</span></span>|
|<span data-ttu-id="4bacf-151">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4bacf-152">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-152">yes</span></span>         |
|<span data-ttu-id="4bacf-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-153">Exchange</span></span>         |<span data-ttu-id="4bacf-154">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-154">yes</span></span>         |
|<span data-ttu-id="4bacf-155">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4bacf-155">AIP unified client</span></span>         |<span data-ttu-id="4bacf-156">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-156">yes</span></span>         |
|<span data-ttu-id="4bacf-157">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-157">AIP unified scanner</span></span>         |<span data-ttu-id="4bacf-158">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-158">yes</span></span>         |
|<span data-ttu-id="4bacf-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-159">MIP SDK</span></span>         |<span data-ttu-id="4bacf-160">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-160">yes</span></span>         |
|<span data-ttu-id="4bacf-161">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4bacf-161">RMS service</span></span>         |<span data-ttu-id="4bacf-162">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-162">not applicable</span></span>         |
|<span data-ttu-id="4bacf-163">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="4bacf-164">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-164">no</span></span>         |<span data-ttu-id="4bacf-165">在审核日志中Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="4bacf-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="4bacf-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-166">MCAS</span></span>     |<span data-ttu-id="4bacf-167">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="4bacf-168">删除了敏感度标签</span><span class="sxs-lookup"><span data-stu-id="4bacf-168">Sensitivity label removed</span></span>

<span data-ttu-id="4bacf-169">每次从文件或文档中删除敏感度标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-169">This event is generated each time a sensitivity label is removed from a file or document.</span></span>

- <span data-ttu-id="4bacf-170">在本机应用程序和 Web 应用程序中保存Office捕获此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="4bacf-171">在 Azure 信息保护加载项中出现时捕获它。</span><span class="sxs-lookup"><span data-stu-id="4bacf-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="4bacf-172">敏感度标签（Office本机 MIP 标签Outlook收集上次在文件保存/电子邮件发送操作之前生成的标记事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="4bacf-173">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-173">Source</span></span>  |<span data-ttu-id="4bacf-174">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-174">Reported in activity explorer</span></span> | <span data-ttu-id="4bacf-175">注释</span><span class="sxs-lookup"><span data-stu-id="4bacf-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4bacf-176">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4bacf-177">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-177">yes</span></span>         |
|<span data-ttu-id="4bacf-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-178">Outlook</span></span>         |<span data-ttu-id="4bacf-179">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-179">yes</span></span>         |<span data-ttu-id="4bacf-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="4bacf-180">Win 32</span></span>|
|<span data-ttu-id="4bacf-181">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4bacf-182">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-182">yes</span></span>         |
|<span data-ttu-id="4bacf-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-183">Exchange</span></span>         |<span data-ttu-id="4bacf-184">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-184">yes</span></span>         |
|<span data-ttu-id="4bacf-185">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4bacf-185">AIP unified client</span></span>         |<span data-ttu-id="4bacf-186">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-186">yes</span></span>         |<span data-ttu-id="4bacf-187">AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作</span><span class="sxs-lookup"><span data-stu-id="4bacf-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="4bacf-188">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-188">AIP unified scanner</span></span>         |<span data-ttu-id="4bacf-189">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-189">yes</span></span>         |<span data-ttu-id="4bacf-190">AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作</span><span class="sxs-lookup"><span data-stu-id="4bacf-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="4bacf-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-191">MIP SDK</span></span>         |<span data-ttu-id="4bacf-192">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-192">yes</span></span>         |<span data-ttu-id="4bacf-193">AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作</span><span class="sxs-lookup"><span data-stu-id="4bacf-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="4bacf-194">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4bacf-194">RMS service</span></span>         |<span data-ttu-id="4bacf-195">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-195">not applicable</span></span>         |
|<span data-ttu-id="4bacf-196">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="4bacf-197">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-197">no</span></span>         |<span data-ttu-id="4bacf-198">在审核日志中Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="4bacf-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="4bacf-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-199">MCAS</span></span>     |<span data-ttu-id="4bacf-200">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="4bacf-201">已读取敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="4bacf-201">Sensitivity label file read</span></span>

<span data-ttu-id="4bacf-202">每次打开标记为或受保护的文档的敏感度文档时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-202">This event is generated each time a sensitivity labeled or protected document is opened.</span></span>

|<span data-ttu-id="4bacf-203">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-203">Source</span></span>  |<span data-ttu-id="4bacf-204">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-204">Reported in activity explorer</span></span> | <span data-ttu-id="4bacf-205">注释</span><span class="sxs-lookup"><span data-stu-id="4bacf-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4bacf-206">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4bacf-207">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-207">yes</span></span>         |
|<span data-ttu-id="4bacf-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-208">Outlook</span></span>         |<span data-ttu-id="4bacf-209">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-209">no</span></span>         |
|<span data-ttu-id="4bacf-210">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4bacf-211">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-211">no</span></span>         |
|<span data-ttu-id="4bacf-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-212">Exchange</span></span>         |<span data-ttu-id="4bacf-213">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-213">no</span></span>         |
|<span data-ttu-id="4bacf-214">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4bacf-214">AIP unified client</span></span>         |<span data-ttu-id="4bacf-215">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-215">yes</span></span>         |<span data-ttu-id="4bacf-216">AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="4bacf-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="4bacf-217">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-217">AIP unified scanner</span></span>         |<span data-ttu-id="4bacf-218">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-218">yes</span></span>         |<span data-ttu-id="4bacf-219">AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="4bacf-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="4bacf-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-220">MIP SDK</span></span>         |<span data-ttu-id="4bacf-221">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-221">yes</span></span>         |<span data-ttu-id="4bacf-222">AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="4bacf-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="4bacf-223">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4bacf-223">RMS service</span></span>         |<span data-ttu-id="4bacf-224">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-224">yes</span></span>         |<span data-ttu-id="4bacf-225">访问 *操作* 映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="4bacf-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="4bacf-226">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="4bacf-227">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-227">no</span></span>         |<span data-ttu-id="4bacf-228">在审核日志中Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="4bacf-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="4bacf-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-229">MCAS</span></span>     |<span data-ttu-id="4bacf-230">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-230">no</span></span>         |         |


## <a name="files-discovered"></a><span data-ttu-id="4bacf-231">发现的文件</span><span class="sxs-lookup"><span data-stu-id="4bacf-231">Files discovered</span></span>

<span data-ttu-id="4bacf-232">每次发现文件时，当使用 AIP 扫描程序扫描不同位置的敏感数据并查找文件时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="4bacf-233">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-233">Source</span></span>  |<span data-ttu-id="4bacf-234">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-234">Reported in activity explorer</span></span> | <span data-ttu-id="4bacf-235">注释</span><span class="sxs-lookup"><span data-stu-id="4bacf-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4bacf-236">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4bacf-237">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-237">not applicable</span></span>         |
|<span data-ttu-id="4bacf-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-238">Outlook</span></span>         |<span data-ttu-id="4bacf-239">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-239">not applicable</span></span>         |
|<span data-ttu-id="4bacf-240">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4bacf-241">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-241">not applicable</span></span>         |
|<span data-ttu-id="4bacf-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-242">Exchange</span></span>         |<span data-ttu-id="4bacf-243">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-243">not applicable</span></span>         |
|<span data-ttu-id="4bacf-244">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4bacf-244">AIP unified client</span></span>         |<span data-ttu-id="4bacf-245">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-245">not applicable</span></span>       |
|<span data-ttu-id="4bacf-246">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-246">AIP unified scanner</span></span>         |<span data-ttu-id="4bacf-247">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-247">yes</span></span>         |<span data-ttu-id="4bacf-248">AIP *发现* 操作映射到活动 *资源管理器中发现* 操作的文件</span><span class="sxs-lookup"><span data-stu-id="4bacf-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="4bacf-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-249">MIP SDK</span></span>         |<span data-ttu-id="4bacf-250">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-250">yes</span></span>         |<span data-ttu-id="4bacf-251">AIP *发现* 操作映射到活动 *资源管理器中发现* 的文件操作</span><span class="sxs-lookup"><span data-stu-id="4bacf-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="4bacf-252">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4bacf-252">RMS service</span></span>         |<span data-ttu-id="4bacf-253">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-253">not applicable</span></span>         |
|<span data-ttu-id="4bacf-254">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="4bacf-255">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-255">not applicable</span></span>         |
|<span data-ttu-id="4bacf-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-256">MCAS</span></span>     |<span data-ttu-id="4bacf-257">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="4bacf-258">已重命名敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="4bacf-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="4bacf-259">每次重命名具有敏感度标签的文档时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="4bacf-260">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-260">Source</span></span>  | <span data-ttu-id="4bacf-261">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-261">Reported in activity explorer</span></span> | <span data-ttu-id="4bacf-262">注释</span><span class="sxs-lookup"><span data-stu-id="4bacf-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4bacf-263">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4bacf-264">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-264">yes</span></span>         |
|<span data-ttu-id="4bacf-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-265">Outlook</span></span>         |<span data-ttu-id="4bacf-266">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-266">not applicable</span></span>         |
|<span data-ttu-id="4bacf-267">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4bacf-268">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-268">no</span></span>        |
|<span data-ttu-id="4bacf-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-269">Exchange</span></span>         |<span data-ttu-id="4bacf-270">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-270">not applicable</span></span>         |
|<span data-ttu-id="4bacf-271">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4bacf-271">AIP unified client</span></span>         |<span data-ttu-id="4bacf-272">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-272">no</span></span>         |
|<span data-ttu-id="4bacf-273">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-273">AIP unified scanner</span></span>         |<span data-ttu-id="4bacf-274">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-274">no</span></span>         |
|<span data-ttu-id="4bacf-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-275">MIP SDK</span></span>         |<span data-ttu-id="4bacf-276">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-276">no</span></span>         |
|<span data-ttu-id="4bacf-277">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4bacf-277">RMS service</span></span>         |<span data-ttu-id="4bacf-278">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-278">no</span></span>      |
|<span data-ttu-id="4bacf-279">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="4bacf-280">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-280">no</span></span>         |
|<span data-ttu-id="4bacf-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-281">MCAS</span></span>     |<span data-ttu-id="4bacf-282">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-282">no</span></span>         |         |


## <a name="file-removed"></a><span data-ttu-id="4bacf-283">文件已删除</span><span class="sxs-lookup"><span data-stu-id="4bacf-283">File removed</span></span>

<span data-ttu-id="4bacf-284">每次 AIP 扫描程序检测到之前扫描的文件已删除时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="4bacf-285">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-285">Source</span></span>  |<span data-ttu-id="4bacf-286">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-286">Reported in activity explorer</span></span> | <span data-ttu-id="4bacf-287">注释</span><span class="sxs-lookup"><span data-stu-id="4bacf-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4bacf-288">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4bacf-289">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-289">not applicable</span></span>         |
|<span data-ttu-id="4bacf-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-290">Outlook</span></span>         |<span data-ttu-id="4bacf-291">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-291">not applicable</span></span>         |
|<span data-ttu-id="4bacf-292">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4bacf-293">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-293">not applicable</span></span>           |
|<span data-ttu-id="4bacf-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-294">Exchange</span></span>         |<span data-ttu-id="4bacf-295">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-295">not applicable</span></span>         |
|<span data-ttu-id="4bacf-296">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4bacf-296">AIP unified client</span></span>         |<span data-ttu-id="4bacf-297">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-297">not applicable</span></span>            |
|<span data-ttu-id="4bacf-298">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-298">AIP unified scanner</span></span>         |<span data-ttu-id="4bacf-299">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-299">yes</span></span>         |
|<span data-ttu-id="4bacf-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-300">MIP SDK</span></span>         |<span data-ttu-id="4bacf-301">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-301">not applicable</span></span>            |
|<span data-ttu-id="4bacf-302">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4bacf-302">RMS service</span></span>         |<span data-ttu-id="4bacf-303">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-303">not applicable</span></span>         |
|<span data-ttu-id="4bacf-304">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="4bacf-305">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-305">not applicable</span></span>  |
|<span data-ttu-id="4bacf-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-306">MCAS</span></span>     |<span data-ttu-id="4bacf-307">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-307">not applicable</span></span>        |         |

### <a name="protection-applied"></a><span data-ttu-id="4bacf-308">已应用保护</span><span class="sxs-lookup"><span data-stu-id="4bacf-308">Protection applied</span></span>

<span data-ttu-id="4bacf-309">此事件生成首次保护时手动添加到没有标签的项。</span><span class="sxs-lookup"><span data-stu-id="4bacf-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="4bacf-310">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-310">Source</span></span>  |<span data-ttu-id="4bacf-311">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-311">Reported in activity explorer</span></span> | <span data-ttu-id="4bacf-312">注释</span><span class="sxs-lookup"><span data-stu-id="4bacf-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4bacf-313">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4bacf-314">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-314">no</span></span>         |
|<span data-ttu-id="4bacf-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-315">Outlook</span></span>         |<span data-ttu-id="4bacf-316">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-316">no</span></span>         |
|<span data-ttu-id="4bacf-317">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4bacf-318">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-318">not applicable</span></span>           |
|<span data-ttu-id="4bacf-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-319">Exchange</span></span>         |<span data-ttu-id="4bacf-320">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-320">no</span></span>       |
|<span data-ttu-id="4bacf-321">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4bacf-321">AIP unified client</span></span>         |<span data-ttu-id="4bacf-322">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-322">yes</span></span>            |
|<span data-ttu-id="4bacf-323">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-323">AIP unified scanner</span></span>         |<span data-ttu-id="4bacf-324">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-324">not applicable</span></span>         |
|<span data-ttu-id="4bacf-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-325">MIP SDK</span></span>         |<span data-ttu-id="4bacf-326">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-326">yes</span></span>            |
|<span data-ttu-id="4bacf-327">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4bacf-327">RMS service</span></span>         |<span data-ttu-id="4bacf-328">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-328">not applicable</span></span>         |
|<span data-ttu-id="4bacf-329">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="4bacf-330">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-330">not applicable</span></span>            |
|<span data-ttu-id="4bacf-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-331">MCAS</span></span>     |<span data-ttu-id="4bacf-332">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-332">not applicable</span></span>        |         |

## <a name="protection-changed"></a><span data-ttu-id="4bacf-333">保护已更改</span><span class="sxs-lookup"><span data-stu-id="4bacf-333">Protection changed</span></span>

<span data-ttu-id="4bacf-334">每次手动更改未标记文档的保护时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="4bacf-335">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-335">Source</span></span>  |<span data-ttu-id="4bacf-336">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4bacf-337">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4bacf-338">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-338">no</span></span>         |
|<span data-ttu-id="4bacf-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-339">Outlook</span></span>         |<span data-ttu-id="4bacf-340">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-340">no</span></span>         |
|<span data-ttu-id="4bacf-341">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4bacf-342">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-342">not applicable</span></span>           |
|<span data-ttu-id="4bacf-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-343">Exchange</span></span>         |<span data-ttu-id="4bacf-344">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-344">no</span></span>       |
|<span data-ttu-id="4bacf-345">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4bacf-345">AIP unified client</span></span>         |<span data-ttu-id="4bacf-346">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-346">yes</span></span>            |
|<span data-ttu-id="4bacf-347">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-347">AIP unified scanner</span></span>         |<span data-ttu-id="4bacf-348">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-348">not applicable</span></span>         |
|<span data-ttu-id="4bacf-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-349">MIP SDK</span></span>         |<span data-ttu-id="4bacf-350">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-350">yes</span></span>            |
|<span data-ttu-id="4bacf-351">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4bacf-351">RMS service</span></span>         |<span data-ttu-id="4bacf-352">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-352">not applicable</span></span>         |
|<span data-ttu-id="4bacf-353">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="4bacf-354">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-354">not applicable</span></span>            |
|<span data-ttu-id="4bacf-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-355">MCAS</span></span>     |<span data-ttu-id="4bacf-356">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-356">not applicable</span></span>        |

## <a name="protection-removed"></a><span data-ttu-id="4bacf-357">已删除保护</span><span class="sxs-lookup"><span data-stu-id="4bacf-357">Protection removed</span></span>

<span data-ttu-id="4bacf-358">每次手动更改未标记文档的保护时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="4bacf-359">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-359">Source</span></span>  |<span data-ttu-id="4bacf-360">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4bacf-361">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4bacf-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4bacf-362">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-362">no</span></span>         |
|<span data-ttu-id="4bacf-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="4bacf-363">Outlook</span></span>         |<span data-ttu-id="4bacf-364">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-364">no</span></span>         |
|<span data-ttu-id="4bacf-365">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4bacf-366">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-366">not applicable</span></span>           |
|<span data-ttu-id="4bacf-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-367">Exchange</span></span>         |<span data-ttu-id="4bacf-368">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-368">no</span></span>       |
|<span data-ttu-id="4bacf-369">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4bacf-369">AIP unified client</span></span>         |<span data-ttu-id="4bacf-370">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-370">yes</span></span>            |
|<span data-ttu-id="4bacf-371">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4bacf-371">AIP unified scanner</span></span>         |<span data-ttu-id="4bacf-372">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-372">not applicable</span></span>         |
|<span data-ttu-id="4bacf-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4bacf-373">MIP SDK</span></span>         |<span data-ttu-id="4bacf-374">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-374">yes</span></span>            |
|<span data-ttu-id="4bacf-375">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4bacf-375">RMS service</span></span>         |<span data-ttu-id="4bacf-376">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-376">not applicable</span></span>         |
|<span data-ttu-id="4bacf-377">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4bacf-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="4bacf-378">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-378">not applicable</span></span>            |
|<span data-ttu-id="4bacf-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-379">MCAS</span></span>     |<span data-ttu-id="4bacf-380">不适用</span><span class="sxs-lookup"><span data-stu-id="4bacf-380">not applicable</span></span>        |

## <a name="dlp-policy-matched"></a><span data-ttu-id="4bacf-381">匹配的 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="4bacf-381">DLP policy matched</span></span>

<span data-ttu-id="4bacf-382">每次在文档或电子邮件上匹配 DLP 策略时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-382">This event is generated each time a DLP policy is matched on a document or an email.</span></span>

|<span data-ttu-id="4bacf-383">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-383">Source</span></span>  |<span data-ttu-id="4bacf-384">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4bacf-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-385">Exchange</span></span>         |<span data-ttu-id="4bacf-386">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-386">yes</span></span>       |
|<span data-ttu-id="4bacf-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4bacf-387">SharePoint Online</span></span>|<span data-ttu-id="4bacf-388">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-388">yes</span></span>          |
|<span data-ttu-id="4bacf-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-389">OneDrive</span></span> |<span data-ttu-id="4bacf-390">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-390">yes</span></span>|
|<span data-ttu-id="4bacf-391">Teams</span><span class="sxs-lookup"><span data-stu-id="4bacf-391">Teams</span></span> |<span data-ttu-id="4bacf-392">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-392">yes</span></span>   |
|<span data-ttu-id="4bacf-393">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="4bacf-393">Windows 10 devices</span></span>         |<span data-ttu-id="4bacf-394">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-394">yes</span></span> |
|<span data-ttu-id="4bacf-395">MAC</span><span class="sxs-lookup"><span data-stu-id="4bacf-395">MAC</span></span>         |<span data-ttu-id="4bacf-396">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-396">no</span></span>     |
|<span data-ttu-id="4bacf-397">本地</span><span class="sxs-lookup"><span data-stu-id="4bacf-397">on-premises</span></span>         |<span data-ttu-id="4bacf-398">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-398">no</span></span>|
|<span data-ttu-id="4bacf-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="4bacf-399">MCAS</span></span>     |<span data-ttu-id="4bacf-400">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-400">no</span></span>        | 

<span data-ttu-id="4bacf-401">终结点 DLP Windows 10 设备 (事件) 为：</span><span class="sxs-lookup"><span data-stu-id="4bacf-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="4bacf-402">文件已删除</span><span class="sxs-lookup"><span data-stu-id="4bacf-402">file deleted</span></span>
- <span data-ttu-id="4bacf-403">已创建文件</span><span class="sxs-lookup"><span data-stu-id="4bacf-403">file created</span></span>
- <span data-ttu-id="4bacf-404">文件复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="4bacf-404">file copied to clipboard</span></span>
- <span data-ttu-id="4bacf-405">已修改文件</span><span class="sxs-lookup"><span data-stu-id="4bacf-405">file modified</span></span>
- <span data-ttu-id="4bacf-406">文件读取</span><span class="sxs-lookup"><span data-stu-id="4bacf-406">file read</span></span>
- <span data-ttu-id="4bacf-407">文件打印</span><span class="sxs-lookup"><span data-stu-id="4bacf-407">file printed</span></span>
- <span data-ttu-id="4bacf-408">文件重命名</span><span class="sxs-lookup"><span data-stu-id="4bacf-408">file renamed</span></span>
- <span data-ttu-id="4bacf-409">文件复制到网络共享</span><span class="sxs-lookup"><span data-stu-id="4bacf-409">file copied to network share</span></span>
- <span data-ttu-id="4bacf-410">未允许的应用访问的文件</span><span class="sxs-lookup"><span data-stu-id="4bacf-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="4bacf-411">应用的保留标签</span><span class="sxs-lookup"><span data-stu-id="4bacf-411">Retention label applied</span></span> 

<span data-ttu-id="4bacf-412">每次标记未标记的文档或发送带有保留标签的电子邮件时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-412">This event is generated each time an unlabeled document is labeled or an email is sent with a retention label.</span></span>

- <span data-ttu-id="4bacf-413">它在保存文档时和发送电子邮件时捕获。</span><span class="sxs-lookup"><span data-stu-id="4bacf-413">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="4bacf-414">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-414">Source</span></span>  |<span data-ttu-id="4bacf-415">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4bacf-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-416">Exchange</span></span>         |<span data-ttu-id="4bacf-417">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-417">no</span></span>       |
|<span data-ttu-id="4bacf-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4bacf-418">SharePoint Online</span></span>|<span data-ttu-id="4bacf-419">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-419">yes</span></span>          |
|<span data-ttu-id="4bacf-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-420">OneDrive</span></span> |<span data-ttu-id="4bacf-421">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="4bacf-422">已更改保留标签</span><span class="sxs-lookup"><span data-stu-id="4bacf-422">Retention label changed</span></span>

<span data-ttu-id="4bacf-423">每次在文档或电子邮件上更新标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="4bacf-424">它在保存文档时和发送电子邮件时捕获。</span><span class="sxs-lookup"><span data-stu-id="4bacf-424">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="4bacf-425">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-425">Source</span></span>  |<span data-ttu-id="4bacf-426">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4bacf-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-427">Exchange</span></span>         |<span data-ttu-id="4bacf-428">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-428">no</span></span>       |
|<span data-ttu-id="4bacf-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4bacf-429">SharePoint Online</span></span>|<span data-ttu-id="4bacf-430">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-430">yes</span></span>          |
|<span data-ttu-id="4bacf-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-431">OneDrive</span></span> |<span data-ttu-id="4bacf-432">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="4bacf-433">已删除保留标签</span><span class="sxs-lookup"><span data-stu-id="4bacf-433">Retention label removed</span></span>

<span data-ttu-id="4bacf-434">每次从文件或文档中删除标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4bacf-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="4bacf-435">它在保存文档时和发送电子邮件时捕获。</span><span class="sxs-lookup"><span data-stu-id="4bacf-435">It is captured at the time of save for a document and at time of sending for an email.</span></span>

|<span data-ttu-id="4bacf-436">源</span><span class="sxs-lookup"><span data-stu-id="4bacf-436">Source</span></span>  |<span data-ttu-id="4bacf-437">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4bacf-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4bacf-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="4bacf-438">Exchange</span></span>         |<span data-ttu-id="4bacf-439">否</span><span class="sxs-lookup"><span data-stu-id="4bacf-439">no</span></span>       |
|<span data-ttu-id="4bacf-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4bacf-440">SharePoint Online</span></span>|<span data-ttu-id="4bacf-441">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-441">yes</span></span>          |
|<span data-ttu-id="4bacf-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4bacf-442">OneDrive</span></span> |<span data-ttu-id="4bacf-443">是</span><span class="sxs-lookup"><span data-stu-id="4bacf-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="4bacf-444">已知问题</span><span class="sxs-lookup"><span data-stu-id="4bacf-444">Known issues</span></span>
  
- <span data-ttu-id="4bacf-445">向最终用户显示推荐的标签工具提示时，不会捕获它。</span><span class="sxs-lookup"><span data-stu-id="4bacf-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="4bacf-446">但是，如果用户选择应用建议的标签，标签将显示在"如何应用"字段下 *，显示为\*\*"推荐"*</span><span class="sxs-lookup"><span data-stu-id="4bacf-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="4bacf-447">从 Sharepoint 和 sharepoint 降级的敏感度标签降级中，当前OneDrive。</span><span class="sxs-lookup"><span data-stu-id="4bacf-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="4bacf-448">敏感信息类型当前不适用于 Word、Excel、PowerPoint 和 Outlook、SharePoint Online 和 OneDrive 中的自动标记OneDrive。</span><span class="sxs-lookup"><span data-stu-id="4bacf-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
