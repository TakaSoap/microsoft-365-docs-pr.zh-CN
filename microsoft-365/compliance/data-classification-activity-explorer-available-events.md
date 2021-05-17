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
description: 活动资源管理器中可用的标签操作列表。
ms.openlocfilehash: ed51c908d6968e3aeae0adbe06d9ba55887bcf83
ms.sourcegitcommit: 1c53f114a810e7aaa2dc876b84d66348492ea36c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51902940"
---
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="c4bc6-103">活动资源管理器中可用的标记活动</span><span class="sxs-lookup"><span data-stu-id="c4bc6-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="c4bc6-104">应用的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="c4bc6-104">Sensitivity label applied</span></span>

<span data-ttu-id="c4bc6-105">每次标记未标记的文档或发送带有标签的电子邮件时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-105">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span> 

- <span data-ttu-id="c4bc6-106">在本机应用程序和 Web 应用程序中保存Office捕获它。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="c4bc6-107">在 Azure 信息保护加载项中出现时捕获它。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="c4bc6-108">还可以通过"标签"事件类型字段和筛选器监视升级和 *降级标签操作* 。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="c4bc6-109">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-109">Source</span></span>  |<span data-ttu-id="c4bc6-110">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-110">Reported in activity explorer</span></span> | <span data-ttu-id="c4bc6-111">注释</span><span class="sxs-lookup"><span data-stu-id="c4bc6-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="c4bc6-112">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="c4bc6-113">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-113">yes</span></span> |
|<span data-ttu-id="c4bc6-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-114">Outlook</span></span>| <span data-ttu-id="c4bc6-115">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-115">yes</span></span> |<span data-ttu-id="c4bc6-116">从 Win 32</span><span class="sxs-lookup"><span data-stu-id="c4bc6-116">from Win 32</span></span> |
|<span data-ttu-id="c4bc6-117">SharePoint联机，OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="c4bc6-118">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-118">yes</span></span> | |
|<span data-ttu-id="c4bc6-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-119">Exchange</span></span>        |<span data-ttu-id="c4bc6-120">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-120">yes</span></span>         | |
|<span data-ttu-id="c4bc6-121">Azure 信息保护 (AIP) 统一客户端和 AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="c4bc6-122">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-122">yes</span></span> |<span data-ttu-id="c4bc6-123">AIP *新标签* 操作映射到活动 *资源管理器中* 应用的标签</span><span class="sxs-lookup"><span data-stu-id="c4bc6-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="c4bc6-124">Microsoft 信息保护 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="c4bc6-125">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-125">yes</span></span>|<span data-ttu-id="c4bc6-126">AIP *新标签* 操作映射到活动 *资源管理器中* 应用的标签</span><span class="sxs-lookup"><span data-stu-id="c4bc6-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="c4bc6-127">权限管理服务 (RMS) </span><span class="sxs-lookup"><span data-stu-id="c4bc6-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="c4bc6-128">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-128">not applicable</span></span>         | |
|<span data-ttu-id="c4bc6-129">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-129">Power BI desktop and web</span></span>        | <span data-ttu-id="c4bc6-130">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-130">no</span></span>| <span data-ttu-id="c4bc6-131">在审核日志中Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="c4bc6-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="c4bc6-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="c4bc6-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="c4bc6-133">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="c4bc6-134">敏感度标签已更改</span><span class="sxs-lookup"><span data-stu-id="c4bc6-134">Sensitivity label changed</span></span>

<span data-ttu-id="c4bc6-135">每次更新文档或电子邮件的标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-135">This event is generated each time a label is updated on the document or email.</span></span>

- <span data-ttu-id="c4bc6-136">对于 AIP 统一客户端、统一扫描程序和 MIP  SDK 源，AIP 升级标签和 *降级* 标签操作映射到活动资源管理器 *标签已更改*</span><span class="sxs-lookup"><span data-stu-id="c4bc6-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="c4bc6-137">在本机应用程序和 Web 应用程序中的保存Office捕获它。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="c4bc6-138">在 Azure 信息保护统一客户端加载项和扫描程序实施中出现时捕获</span><span class="sxs-lookup"><span data-stu-id="c4bc6-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="c4bc6-139">还可以通过"标签"事件类型字段和筛选器监视升级和 *降级标签操作* 。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="c4bc6-140">对齐 *文本* 也会捕获，但 SharePoint Online 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="c4bc6-141">在应用上Office本机应用中Outlook敏感度标记会收集在文件保存/电子邮件发送操作之前生成的最后一个操作。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="c4bc6-142">例如，如果用户在发送电子邮件之前多次更改电子邮件的标签，电子邮件发送时在电子邮件上找到的最后一个标签将捕获到 审核日志 然后在活动资源管理器中报告。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="c4bc6-143">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-143">Source</span></span>  |<span data-ttu-id="c4bc6-144">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-144">Reported in activity explorer</span></span>|<span data-ttu-id="c4bc6-145">注释</span><span class="sxs-lookup"><span data-stu-id="c4bc6-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="c4bc6-146">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="c4bc6-147">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-147">yes</span></span>         |
|<span data-ttu-id="c4bc6-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-148">Outlook</span></span>         |<span data-ttu-id="c4bc6-149">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-149">yes</span></span>         |<span data-ttu-id="c4bc6-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="c4bc6-150">Win 32</span></span>|
|<span data-ttu-id="c4bc6-151">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="c4bc6-152">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-152">yes</span></span>         |
|<span data-ttu-id="c4bc6-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-153">Exchange</span></span>         |<span data-ttu-id="c4bc6-154">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-154">yes</span></span>         |
|<span data-ttu-id="c4bc6-155">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="c4bc6-155">AIP unified client</span></span>         |<span data-ttu-id="c4bc6-156">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-156">yes</span></span>         |
|<span data-ttu-id="c4bc6-157">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-157">AIP unified scanner</span></span>         |<span data-ttu-id="c4bc6-158">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-158">yes</span></span>         |
|<span data-ttu-id="c4bc6-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-159">MIP SDK</span></span>         |<span data-ttu-id="c4bc6-160">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-160">yes</span></span>         |
|<span data-ttu-id="c4bc6-161">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="c4bc6-161">RMS service</span></span>         |<span data-ttu-id="c4bc6-162">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-162">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-163">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="c4bc6-164">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-164">no</span></span>         |<span data-ttu-id="c4bc6-165">在审核日志中Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="c4bc6-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="c4bc6-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-166">MCAS</span></span>     |<span data-ttu-id="c4bc6-167">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="c4bc6-168">删除了敏感度标签</span><span class="sxs-lookup"><span data-stu-id="c4bc6-168">Sensitivity label removed</span></span>

<span data-ttu-id="c4bc6-169">每次从文件或文档中删除标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-169">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="c4bc6-170">在本机应用程序和 Web 应用程序中保存Office捕获此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="c4bc6-171">在 Azure 信息保护加载项中出现时捕获它。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="c4bc6-172">敏感度标签（Office本机 MIP 标签Outlook收集上次在文件保存/电子邮件发送操作之前生成的标记事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="c4bc6-173">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-173">Source</span></span>  |<span data-ttu-id="c4bc6-174">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-174">Reported in activity explorer</span></span> | <span data-ttu-id="c4bc6-175">注释</span><span class="sxs-lookup"><span data-stu-id="c4bc6-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="c4bc6-176">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="c4bc6-177">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-177">yes</span></span>         |
|<span data-ttu-id="c4bc6-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-178">Outlook</span></span>         |<span data-ttu-id="c4bc6-179">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-179">yes</span></span>         |<span data-ttu-id="c4bc6-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="c4bc6-180">Win 32</span></span>|
|<span data-ttu-id="c4bc6-181">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="c4bc6-182">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-182">yes</span></span>         |
|<span data-ttu-id="c4bc6-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-183">Exchange</span></span>         |<span data-ttu-id="c4bc6-184">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-184">yes</span></span>         |
|<span data-ttu-id="c4bc6-185">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="c4bc6-185">AIP unified client</span></span>         |<span data-ttu-id="c4bc6-186">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-186">yes</span></span>         |<span data-ttu-id="c4bc6-187">AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作</span><span class="sxs-lookup"><span data-stu-id="c4bc6-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="c4bc6-188">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-188">AIP unified scanner</span></span>         |<span data-ttu-id="c4bc6-189">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-189">yes</span></span>         |<span data-ttu-id="c4bc6-190">AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作</span><span class="sxs-lookup"><span data-stu-id="c4bc6-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="c4bc6-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-191">MIP SDK</span></span>         |<span data-ttu-id="c4bc6-192">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-192">yes</span></span>         |<span data-ttu-id="c4bc6-193">AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作</span><span class="sxs-lookup"><span data-stu-id="c4bc6-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="c4bc6-194">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="c4bc6-194">RMS service</span></span>         |<span data-ttu-id="c4bc6-195">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-195">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-196">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="c4bc6-197">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-197">no</span></span>         |<span data-ttu-id="c4bc6-198">在审核日志中Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="c4bc6-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="c4bc6-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-199">MCAS</span></span>     |<span data-ttu-id="c4bc6-200">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="c4bc6-201">已读取敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="c4bc6-201">Sensitivity label file read</span></span>

<span data-ttu-id="c4bc6-202">每次打开已标记或受保护的文档时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-202">This event is generated each time a labeled or protected document is opened.</span></span>

|<span data-ttu-id="c4bc6-203">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-203">Source</span></span>  |<span data-ttu-id="c4bc6-204">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-204">Reported in activity explorer</span></span> | <span data-ttu-id="c4bc6-205">注释</span><span class="sxs-lookup"><span data-stu-id="c4bc6-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="c4bc6-206">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="c4bc6-207">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-207">yes</span></span>         |
|<span data-ttu-id="c4bc6-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-208">Outlook</span></span>         |<span data-ttu-id="c4bc6-209">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-209">no</span></span>         |
|<span data-ttu-id="c4bc6-210">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="c4bc6-211">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-211">no</span></span>         |
|<span data-ttu-id="c4bc6-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-212">Exchange</span></span>         |<span data-ttu-id="c4bc6-213">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-213">no</span></span>         |
|<span data-ttu-id="c4bc6-214">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="c4bc6-214">AIP unified client</span></span>         |<span data-ttu-id="c4bc6-215">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-215">yes</span></span>         |<span data-ttu-id="c4bc6-216">AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="c4bc6-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="c4bc6-217">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-217">AIP unified scanner</span></span>         |<span data-ttu-id="c4bc6-218">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-218">yes</span></span>         |<span data-ttu-id="c4bc6-219">AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="c4bc6-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="c4bc6-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-220">MIP SDK</span></span>         |<span data-ttu-id="c4bc6-221">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-221">yes</span></span>         |<span data-ttu-id="c4bc6-222">AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="c4bc6-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="c4bc6-223">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="c4bc6-223">RMS service</span></span>         |<span data-ttu-id="c4bc6-224">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-224">yes</span></span>         |<span data-ttu-id="c4bc6-225">访问 *操作* 映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="c4bc6-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="c4bc6-226">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="c4bc6-227">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-227">no</span></span>         |<span data-ttu-id="c4bc6-228">在审核日志中Microsoft 365访问</span><span class="sxs-lookup"><span data-stu-id="c4bc6-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="c4bc6-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-229">MCAS</span></span>     |<span data-ttu-id="c4bc6-230">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-230">no</span></span>         |         |


## <a name="sensitivity-label-files-discovered"></a><span data-ttu-id="c4bc6-231">发现的敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="c4bc6-231">Sensitivity label files discovered</span></span>

<span data-ttu-id="c4bc6-232">每次发现文件时，当使用 AIP 扫描程序扫描不同位置的敏感数据并查找文件时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="c4bc6-233">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-233">Source</span></span>  |<span data-ttu-id="c4bc6-234">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-234">Reported in activity explorer</span></span> | <span data-ttu-id="c4bc6-235">注释</span><span class="sxs-lookup"><span data-stu-id="c4bc6-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="c4bc6-236">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="c4bc6-237">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-237">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-238">Outlook</span></span>         |<span data-ttu-id="c4bc6-239">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-239">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-240">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="c4bc6-241">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-241">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-242">Exchange</span></span>         |<span data-ttu-id="c4bc6-243">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-243">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-244">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="c4bc6-244">AIP unified client</span></span>         |<span data-ttu-id="c4bc6-245">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-245">not applicable</span></span>       |
|<span data-ttu-id="c4bc6-246">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-246">AIP unified scanner</span></span>         |<span data-ttu-id="c4bc6-247">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-247">yes</span></span>         |<span data-ttu-id="c4bc6-248">AIP *发现* 操作映射到活动 *资源管理器中发现* 操作的文件</span><span class="sxs-lookup"><span data-stu-id="c4bc6-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="c4bc6-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-249">MIP SDK</span></span>         |<span data-ttu-id="c4bc6-250">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-250">yes</span></span>         |<span data-ttu-id="c4bc6-251">AIP *发现* 操作映射到活动 *资源管理器中发现* 的文件操作</span><span class="sxs-lookup"><span data-stu-id="c4bc6-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="c4bc6-252">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="c4bc6-252">RMS service</span></span>         |<span data-ttu-id="c4bc6-253">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-253">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-254">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="c4bc6-255">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-255">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-256">MCAS</span></span>     |<span data-ttu-id="c4bc6-257">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="c4bc6-258">已重命名敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="c4bc6-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="c4bc6-259">每次重命名具有敏感度标签的文档时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="c4bc6-260">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-260">Source</span></span>  | <span data-ttu-id="c4bc6-261">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-261">Reported in activity explorer</span></span> | <span data-ttu-id="c4bc6-262">注释</span><span class="sxs-lookup"><span data-stu-id="c4bc6-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="c4bc6-263">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="c4bc6-264">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-264">yes</span></span>         |
|<span data-ttu-id="c4bc6-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-265">Outlook</span></span>         |<span data-ttu-id="c4bc6-266">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-266">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-267">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="c4bc6-268">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-268">no</span></span>        |
|<span data-ttu-id="c4bc6-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-269">Exchange</span></span>         |<span data-ttu-id="c4bc6-270">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-270">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-271">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="c4bc6-271">AIP unified client</span></span>         |<span data-ttu-id="c4bc6-272">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-272">no</span></span>         |
|<span data-ttu-id="c4bc6-273">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-273">AIP unified scanner</span></span>         |<span data-ttu-id="c4bc6-274">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-274">no</span></span>         |
|<span data-ttu-id="c4bc6-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-275">MIP SDK</span></span>         |<span data-ttu-id="c4bc6-276">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-276">no</span></span>         |
|<span data-ttu-id="c4bc6-277">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="c4bc6-277">RMS service</span></span>         |<span data-ttu-id="c4bc6-278">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-278">no</span></span>      |
|<span data-ttu-id="c4bc6-279">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="c4bc6-280">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-280">no</span></span>         |
|<span data-ttu-id="c4bc6-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-281">MCAS</span></span>     |<span data-ttu-id="c4bc6-282">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-282">no</span></span>         |         |


## <a name="sensitivity-label-file-removed"></a><span data-ttu-id="c4bc6-283">删除了敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="c4bc6-283">Sensitivity label file removed</span></span>

<span data-ttu-id="c4bc6-284">每次 AIP 扫描程序检测到之前扫描的文件已删除时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="c4bc6-285">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-285">Source</span></span>  |<span data-ttu-id="c4bc6-286">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-286">Reported in activity explorer</span></span> | <span data-ttu-id="c4bc6-287">注释</span><span class="sxs-lookup"><span data-stu-id="c4bc6-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="c4bc6-288">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="c4bc6-289">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-289">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-290">Outlook</span></span>         |<span data-ttu-id="c4bc6-291">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-291">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-292">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="c4bc6-293">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-293">not applicable</span></span>           |
|<span data-ttu-id="c4bc6-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-294">Exchange</span></span>         |<span data-ttu-id="c4bc6-295">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-295">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-296">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="c4bc6-296">AIP unified client</span></span>         |<span data-ttu-id="c4bc6-297">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-297">not applicable</span></span>            |
|<span data-ttu-id="c4bc6-298">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-298">AIP unified scanner</span></span>         |<span data-ttu-id="c4bc6-299">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-299">yes</span></span>         |
|<span data-ttu-id="c4bc6-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-300">MIP SDK</span></span>         |<span data-ttu-id="c4bc6-301">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-301">not applicable</span></span>            |
|<span data-ttu-id="c4bc6-302">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="c4bc6-302">RMS service</span></span>         |<span data-ttu-id="c4bc6-303">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-303">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-304">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="c4bc6-305">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-305">not applicable</span></span>  |
|<span data-ttu-id="c4bc6-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-306">MCAS</span></span>     |<span data-ttu-id="c4bc6-307">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-307">not applicable</span></span>        |         |

### <a name="sensitivity-label-protection-applied"></a><span data-ttu-id="c4bc6-308">应用的敏感度标签保护</span><span class="sxs-lookup"><span data-stu-id="c4bc6-308">Sensitivity label protection applied</span></span>

<span data-ttu-id="c4bc6-309">此事件生成首次保护时手动添加到没有标签的项。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="c4bc6-310">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-310">Source</span></span>  |<span data-ttu-id="c4bc6-311">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-311">Reported in activity explorer</span></span> | <span data-ttu-id="c4bc6-312">注释</span><span class="sxs-lookup"><span data-stu-id="c4bc6-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="c4bc6-313">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="c4bc6-314">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-314">no</span></span>         |
|<span data-ttu-id="c4bc6-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-315">Outlook</span></span>         |<span data-ttu-id="c4bc6-316">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-316">no</span></span>         |
|<span data-ttu-id="c4bc6-317">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="c4bc6-318">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-318">not applicable</span></span>           |
|<span data-ttu-id="c4bc6-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-319">Exchange</span></span>         |<span data-ttu-id="c4bc6-320">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-320">no</span></span>       |
|<span data-ttu-id="c4bc6-321">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="c4bc6-321">AIP unified client</span></span>         |<span data-ttu-id="c4bc6-322">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-322">yes</span></span>            |
|<span data-ttu-id="c4bc6-323">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-323">AIP unified scanner</span></span>         |<span data-ttu-id="c4bc6-324">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-324">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-325">MIP SDK</span></span>         |<span data-ttu-id="c4bc6-326">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-326">yes</span></span>            |
|<span data-ttu-id="c4bc6-327">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="c4bc6-327">RMS service</span></span>         |<span data-ttu-id="c4bc6-328">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-328">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-329">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="c4bc6-330">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-330">not applicable</span></span>            |
|<span data-ttu-id="c4bc6-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-331">MCAS</span></span>     |<span data-ttu-id="c4bc6-332">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-332">not applicable</span></span>        |         |

## <a name="sensitivity-label-protection-changed"></a><span data-ttu-id="c4bc6-333">敏感度标签保护已更改</span><span class="sxs-lookup"><span data-stu-id="c4bc6-333">Sensitivity label protection changed</span></span>

<span data-ttu-id="c4bc6-334">每次手动更改未标记文档的保护时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="c4bc6-335">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-335">Source</span></span>  |<span data-ttu-id="c4bc6-336">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="c4bc6-337">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="c4bc6-338">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-338">no</span></span>         |
|<span data-ttu-id="c4bc6-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-339">Outlook</span></span>         |<span data-ttu-id="c4bc6-340">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-340">no</span></span>         |
|<span data-ttu-id="c4bc6-341">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="c4bc6-342">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-342">not applicable</span></span>           |
|<span data-ttu-id="c4bc6-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-343">Exchange</span></span>         |<span data-ttu-id="c4bc6-344">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-344">no</span></span>       |
|<span data-ttu-id="c4bc6-345">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="c4bc6-345">AIP unified client</span></span>         |<span data-ttu-id="c4bc6-346">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-346">yes</span></span>            |
|<span data-ttu-id="c4bc6-347">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-347">AIP unified scanner</span></span>         |<span data-ttu-id="c4bc6-348">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-348">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-349">MIP SDK</span></span>         |<span data-ttu-id="c4bc6-350">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-350">yes</span></span>            |
|<span data-ttu-id="c4bc6-351">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="c4bc6-351">RMS service</span></span>         |<span data-ttu-id="c4bc6-352">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-352">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-353">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="c4bc6-354">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-354">not applicable</span></span>            |
|<span data-ttu-id="c4bc6-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-355">MCAS</span></span>     |<span data-ttu-id="c4bc6-356">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-356">not applicable</span></span>        |

## <a name="sensitivity-label-protection-removed"></a><span data-ttu-id="c4bc6-357">删除了敏感度标签保护</span><span class="sxs-lookup"><span data-stu-id="c4bc6-357">Sensitivity label protection removed</span></span>

<span data-ttu-id="c4bc6-358">每次手动更改未标记文档的保护时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="c4bc6-359">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-359">Source</span></span>  |<span data-ttu-id="c4bc6-360">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="c4bc6-361">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="c4bc6-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="c4bc6-362">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-362">no</span></span>         |
|<span data-ttu-id="c4bc6-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="c4bc6-363">Outlook</span></span>         |<span data-ttu-id="c4bc6-364">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-364">no</span></span>         |
|<span data-ttu-id="c4bc6-365">SharePoint联机、OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="c4bc6-366">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-366">not applicable</span></span>           |
|<span data-ttu-id="c4bc6-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-367">Exchange</span></span>         |<span data-ttu-id="c4bc6-368">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-368">no</span></span>       |
|<span data-ttu-id="c4bc6-369">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="c4bc6-369">AIP unified client</span></span>         |<span data-ttu-id="c4bc6-370">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-370">yes</span></span>            |
|<span data-ttu-id="c4bc6-371">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="c4bc6-371">AIP unified scanner</span></span>         |<span data-ttu-id="c4bc6-372">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-372">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="c4bc6-373">MIP SDK</span></span>         |<span data-ttu-id="c4bc6-374">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-374">yes</span></span>            |
|<span data-ttu-id="c4bc6-375">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="c4bc6-375">RMS service</span></span>         |<span data-ttu-id="c4bc6-376">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-376">not applicable</span></span>         |
|<span data-ttu-id="c4bc6-377">Power BI桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="c4bc6-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="c4bc6-378">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-378">not applicable</span></span>            |
|<span data-ttu-id="c4bc6-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-379">MCAS</span></span>     |<span data-ttu-id="c4bc6-380">不适用</span><span class="sxs-lookup"><span data-stu-id="c4bc6-380">not applicable</span></span>        |

## <a name="sensitivity-label-dlp-policy-matched"></a><span data-ttu-id="c4bc6-381">已匹配的敏感度标签 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="c4bc6-381">Sensitivity label DLP policy matched</span></span>

<span data-ttu-id="c4bc6-382">每次匹配 DLP 策略时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-382">This event is generated each time a DLP policy is matched.</span></span>

|<span data-ttu-id="c4bc6-383">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-383">Source</span></span>  |<span data-ttu-id="c4bc6-384">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="c4bc6-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-385">Exchange</span></span>         |<span data-ttu-id="c4bc6-386">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-386">yes</span></span>       |
|<span data-ttu-id="c4bc6-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c4bc6-387">SharePoint Online</span></span>|<span data-ttu-id="c4bc6-388">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-388">yes</span></span>          |
|<span data-ttu-id="c4bc6-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-389">OneDrive</span></span> |<span data-ttu-id="c4bc6-390">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-390">yes</span></span>|
|<span data-ttu-id="c4bc6-391">Teams</span><span class="sxs-lookup"><span data-stu-id="c4bc6-391">Teams</span></span> |<span data-ttu-id="c4bc6-392">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-392">yes</span></span>   |
|<span data-ttu-id="c4bc6-393">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="c4bc6-393">Windows 10 devices</span></span>         |<span data-ttu-id="c4bc6-394">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-394">yes</span></span> |
|<span data-ttu-id="c4bc6-395">MAC</span><span class="sxs-lookup"><span data-stu-id="c4bc6-395">MAC</span></span>         |<span data-ttu-id="c4bc6-396">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-396">no</span></span>     |
|<span data-ttu-id="c4bc6-397">本地</span><span class="sxs-lookup"><span data-stu-id="c4bc6-397">on-premises</span></span>         |<span data-ttu-id="c4bc6-398">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-398">no</span></span>|
|<span data-ttu-id="c4bc6-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="c4bc6-399">MCAS</span></span>     |<span data-ttu-id="c4bc6-400">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-400">no</span></span>        | 

<span data-ttu-id="c4bc6-401">终结点 DLP Windows 10 设备 (事件) 为：</span><span class="sxs-lookup"><span data-stu-id="c4bc6-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="c4bc6-402">文件已删除</span><span class="sxs-lookup"><span data-stu-id="c4bc6-402">file deleted</span></span>
- <span data-ttu-id="c4bc6-403">已创建文件</span><span class="sxs-lookup"><span data-stu-id="c4bc6-403">file created</span></span>
- <span data-ttu-id="c4bc6-404">文件复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="c4bc6-404">file copied to clipboard</span></span>
- <span data-ttu-id="c4bc6-405">已修改文件</span><span class="sxs-lookup"><span data-stu-id="c4bc6-405">file modified</span></span>
- <span data-ttu-id="c4bc6-406">文件读取</span><span class="sxs-lookup"><span data-stu-id="c4bc6-406">file read</span></span>
- <span data-ttu-id="c4bc6-407">文件打印</span><span class="sxs-lookup"><span data-stu-id="c4bc6-407">file printed</span></span>
- <span data-ttu-id="c4bc6-408">文件重命名</span><span class="sxs-lookup"><span data-stu-id="c4bc6-408">file renamed</span></span>
- <span data-ttu-id="c4bc6-409">文件复制到网络共享</span><span class="sxs-lookup"><span data-stu-id="c4bc6-409">file copied to network share</span></span>
- <span data-ttu-id="c4bc6-410">未允许的应用访问的文件</span><span class="sxs-lookup"><span data-stu-id="c4bc6-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="c4bc6-411">应用的保留标签</span><span class="sxs-lookup"><span data-stu-id="c4bc6-411">Retention label applied</span></span> 

<span data-ttu-id="c4bc6-412">每次标记未标记的文档或发送带有标签的电子邮件时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-412">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span>

- <span data-ttu-id="c4bc6-413">在本机应用程序和 Web 应用程序中保存Office捕获它。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-413">It is captured at the time of save in Office native applications and web applications.</span></span>

|<span data-ttu-id="c4bc6-414">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-414">Source</span></span>  |<span data-ttu-id="c4bc6-415">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="c4bc6-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-416">Exchange</span></span>         |<span data-ttu-id="c4bc6-417">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-417">no</span></span>       |
|<span data-ttu-id="c4bc6-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c4bc6-418">SharePoint Online</span></span>|<span data-ttu-id="c4bc6-419">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-419">yes</span></span>          |
|<span data-ttu-id="c4bc6-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-420">OneDrive</span></span> |<span data-ttu-id="c4bc6-421">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="c4bc6-422">已更改保留标签</span><span class="sxs-lookup"><span data-stu-id="c4bc6-422">Retention label changed</span></span>

<span data-ttu-id="c4bc6-423">每次在文档或电子邮件上更新标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="c4bc6-424">它在保存时捕获。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-424">It is captured at the time of save.</span></span>

|<span data-ttu-id="c4bc6-425">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-425">Source</span></span>  |<span data-ttu-id="c4bc6-426">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="c4bc6-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-427">Exchange</span></span>         |<span data-ttu-id="c4bc6-428">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-428">no</span></span>       |
|<span data-ttu-id="c4bc6-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c4bc6-429">SharePoint Online</span></span>|<span data-ttu-id="c4bc6-430">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-430">yes</span></span>          |
|<span data-ttu-id="c4bc6-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-431">OneDrive</span></span> |<span data-ttu-id="c4bc6-432">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="c4bc6-433">已删除保留标签</span><span class="sxs-lookup"><span data-stu-id="c4bc6-433">Retention label removed</span></span>

<span data-ttu-id="c4bc6-434">每次从文件或文档中删除标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="c4bc6-435">它在保存时捕获。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-435">It is captured at the time of save.</span></span>

|<span data-ttu-id="c4bc6-436">源</span><span class="sxs-lookup"><span data-stu-id="c4bc6-436">Source</span></span>  |<span data-ttu-id="c4bc6-437">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="c4bc6-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="c4bc6-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="c4bc6-438">Exchange</span></span>         |<span data-ttu-id="c4bc6-439">否</span><span class="sxs-lookup"><span data-stu-id="c4bc6-439">no</span></span>       |
|<span data-ttu-id="c4bc6-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="c4bc6-440">SharePoint Online</span></span>|<span data-ttu-id="c4bc6-441">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-441">yes</span></span>          |
|<span data-ttu-id="c4bc6-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="c4bc6-442">OneDrive</span></span> |<span data-ttu-id="c4bc6-443">是</span><span class="sxs-lookup"><span data-stu-id="c4bc6-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="c4bc6-444">已知问题</span><span class="sxs-lookup"><span data-stu-id="c4bc6-444">Known issues</span></span>
  
- <span data-ttu-id="c4bc6-445">向最终用户显示推荐的标签工具提示时，不会捕获它。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="c4bc6-446">但是，如果用户选择应用建议的标签，标签将显示在"如何应用"字段下 *，显示为\*\*"推荐"*</span><span class="sxs-lookup"><span data-stu-id="c4bc6-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="c4bc6-447">从 Sharepoint 和 sharepoint 降级的敏感度标签降级中，当前OneDrive。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="c4bc6-448">敏感信息类型当前不适用于 Word、Excel、PowerPoint 和 Outlook、SharePoint Online 和 OneDrive 中的自动标记OneDrive。</span><span class="sxs-lookup"><span data-stu-id="c4bc6-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
