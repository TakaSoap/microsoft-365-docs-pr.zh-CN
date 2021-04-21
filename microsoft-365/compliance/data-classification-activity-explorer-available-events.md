---
title: 活动资源管理器中报告的标记操作
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
# <a name="labeling-activities-that-are-available-in-activity-explorer"></a><span data-ttu-id="4ea79-103">活动资源管理器中可用的标记活动</span><span class="sxs-lookup"><span data-stu-id="4ea79-103">Labeling activities that are available in Activity explorer</span></span>

## <a name="sensitivity-label-applied"></a><span data-ttu-id="4ea79-104">应用的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="4ea79-104">Sensitivity label applied</span></span>

<span data-ttu-id="4ea79-105">每次标记未标记的文档或发送带有标签的电子邮件时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-105">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span> 

- <span data-ttu-id="4ea79-106">它在 Office 本机应用程序和 Web 应用程序中保存时捕获。</span><span class="sxs-lookup"><span data-stu-id="4ea79-106">It is captured at the time of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="4ea79-107">在 Azure 信息保护加载项中出现时捕获它。</span><span class="sxs-lookup"><span data-stu-id="4ea79-107">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="4ea79-108">还可以通过"标签"事件类型字段和筛选器监视升级和 *降级标签操作* 。</span><span class="sxs-lookup"><span data-stu-id="4ea79-108">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span>   


|<span data-ttu-id="4ea79-109">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-109">Source</span></span>  |<span data-ttu-id="4ea79-110">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-110">Reported in activity explorer</span></span> | <span data-ttu-id="4ea79-111">注释</span><span class="sxs-lookup"><span data-stu-id="4ea79-111">Note</span></span>  |
|---------|---------|---------|
| <span data-ttu-id="4ea79-112">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-112">Word, Excel, PowerPoint</span></span>|<span data-ttu-id="4ea79-113">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-113">yes</span></span> |
|<span data-ttu-id="4ea79-114">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-114">Outlook</span></span>| <span data-ttu-id="4ea79-115">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-115">yes</span></span> |<span data-ttu-id="4ea79-116">从 Win 32</span><span class="sxs-lookup"><span data-stu-id="4ea79-116">from Win 32</span></span> |
|<span data-ttu-id="4ea79-117">SharePoint online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-117">SharePoint online, OneDrive</span></span>|<span data-ttu-id="4ea79-118">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-118">yes</span></span> | |
|<span data-ttu-id="4ea79-119">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-119">Exchange</span></span>        |<span data-ttu-id="4ea79-120">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-120">yes</span></span>         | |
|<span data-ttu-id="4ea79-121">Azure 信息保护 (AIP) 统一客户端和 AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-121">Azure Information Protection (AIP) unified client and AIP unified scanner</span></span> |<span data-ttu-id="4ea79-122">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-122">yes</span></span> |<span data-ttu-id="4ea79-123">AIP *新标签* 操作映射到活动 *资源管理器中* 应用的标签</span><span class="sxs-lookup"><span data-stu-id="4ea79-123">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>   |
|<span data-ttu-id="4ea79-124">Microsoft 信息保护 (MIP) SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-124">Microsoft information protection (MIP) SDK</span></span>         |<span data-ttu-id="4ea79-125">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-125">yes</span></span>|<span data-ttu-id="4ea79-126">AIP *新标签* 操作映射到活动 *资源管理器中* 应用的标签</span><span class="sxs-lookup"><span data-stu-id="4ea79-126">the AIP *new label* action is mapped to *label applied* in activity explorer</span></span>|
|<span data-ttu-id="4ea79-127">权限管理服务 (RMS) </span><span class="sxs-lookup"><span data-stu-id="4ea79-127">Rights Management Service (RMS)</span></span>         |<span data-ttu-id="4ea79-128">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-128">not applicable</span></span>         | |
|<span data-ttu-id="4ea79-129">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-129">Power BI desktop and web</span></span>        | <span data-ttu-id="4ea79-130">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-130">no</span></span>| <span data-ttu-id="4ea79-131">可在 Microsoft 365 审核日志中访问</span><span class="sxs-lookup"><span data-stu-id="4ea79-131">accessible in the Microsoft 365 audit logs</span></span>         |
|<span data-ttu-id="4ea79-132">Microsoft Cloud App Security (MCAS)</span><span class="sxs-lookup"><span data-stu-id="4ea79-132">Microsoft Cloud App Security (MCAS)</span></span>         |<span data-ttu-id="4ea79-133">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-133">no</span></span>|         |

## <a name="sensitivity-label-changed"></a><span data-ttu-id="4ea79-134">敏感度标签已更改</span><span class="sxs-lookup"><span data-stu-id="4ea79-134">Sensitivity label changed</span></span>

<span data-ttu-id="4ea79-135">每次更新文档或电子邮件的标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-135">This event is generated each time a label is updated on the document or email.</span></span>

- <span data-ttu-id="4ea79-136">对于 AIP 统一客户端、统一扫描程序和 MIP  SDK 源，AIP 升级标签和 *降级* 标签操作映射到活动资源管理器 *标签已更改*</span><span class="sxs-lookup"><span data-stu-id="4ea79-136">For the AIP Unified client, Unified Scanner and MIP SDK sources, the AIP *upgrade label* and *downgrade label* action maps to activity explorer *label changed*</span></span>

- <span data-ttu-id="4ea79-137">它在 Office 本机应用程序和 Web 应用程序中的保存点捕获。</span><span class="sxs-lookup"><span data-stu-id="4ea79-137">It is captured at the point of save in Office native applications and web applications.</span></span> 
- <span data-ttu-id="4ea79-138">在 Azure 信息保护统一客户端加载项和扫描程序实施中出现时捕获</span><span class="sxs-lookup"><span data-stu-id="4ea79-138">It is captured at the time of occurrence in Azure Information protection unified client add-ins and scanner enforcements</span></span>
- <span data-ttu-id="4ea79-139">还可以通过"标签"事件类型字段和筛选器监视升级和 *降级标签操作* 。</span><span class="sxs-lookup"><span data-stu-id="4ea79-139">Upgrade and downgrade labels actions can also be monitored via the *Label event type* field and filter.</span></span> <span data-ttu-id="4ea79-140">还将 *捕获* 理由文本，SharePoint Online 和 OneDrive 除外。</span><span class="sxs-lookup"><span data-stu-id="4ea79-140">The *justification* text is also captured except for SharePoint Online and OneDrive.</span></span>
- <span data-ttu-id="4ea79-141">在 Outlook 上的 Office 本机应用中完成敏感度标记会收集在文件保存/电子邮件发送操作之前生成的最后一个操作。</span><span class="sxs-lookup"><span data-stu-id="4ea79-141">Sensitivity labeling done in Office native apps on Outlook collects the last action that was generated before file save/email send actions.</span></span> <span data-ttu-id="4ea79-142">例如，如果用户在发送电子邮件之前多次更改电子邮件的标签，电子邮件发送时在电子邮件上找到的最后一个标签将捕获到 审核日志 然后在活动资源管理器中报告。</span><span class="sxs-lookup"><span data-stu-id="4ea79-142">For example, if the user changes label on an email multiple times before sending, the last label found on the email when it is sent is captured in the audit log and then reported in activity explorer.</span></span> 


|<span data-ttu-id="4ea79-143">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-143">Source</span></span>  |<span data-ttu-id="4ea79-144">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-144">Reported in activity explorer</span></span>|<span data-ttu-id="4ea79-145">注释</span><span class="sxs-lookup"><span data-stu-id="4ea79-145">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4ea79-146">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-146">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4ea79-147">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-147">yes</span></span>         |
|<span data-ttu-id="4ea79-148">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-148">Outlook</span></span>         |<span data-ttu-id="4ea79-149">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-149">yes</span></span>         |<span data-ttu-id="4ea79-150">Win 32</span><span class="sxs-lookup"><span data-stu-id="4ea79-150">Win 32</span></span>|
|<span data-ttu-id="4ea79-151">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-151">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4ea79-152">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-152">yes</span></span>         |
|<span data-ttu-id="4ea79-153">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-153">Exchange</span></span>         |<span data-ttu-id="4ea79-154">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-154">yes</span></span>         |
|<span data-ttu-id="4ea79-155">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4ea79-155">AIP unified client</span></span>         |<span data-ttu-id="4ea79-156">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-156">yes</span></span>         |
|<span data-ttu-id="4ea79-157">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-157">AIP unified scanner</span></span>         |<span data-ttu-id="4ea79-158">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-158">yes</span></span>         |
|<span data-ttu-id="4ea79-159">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-159">MIP SDK</span></span>         |<span data-ttu-id="4ea79-160">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-160">yes</span></span>         |
|<span data-ttu-id="4ea79-161">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4ea79-161">RMS service</span></span>         |<span data-ttu-id="4ea79-162">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-162">not applicable</span></span>         |
|<span data-ttu-id="4ea79-163">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-163">Power BI desktop and Web</span></span>         |<span data-ttu-id="4ea79-164">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-164">no</span></span>         |<span data-ttu-id="4ea79-165">可在 Microsoft 365 审核日志中访问</span><span class="sxs-lookup"><span data-stu-id="4ea79-165">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="4ea79-166">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-166">MCAS</span></span>     |<span data-ttu-id="4ea79-167">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-167">no</span></span>         |         |

## <a name="sensitivity-label-removed"></a><span data-ttu-id="4ea79-168">删除了敏感度标签</span><span class="sxs-lookup"><span data-stu-id="4ea79-168">Sensitivity label removed</span></span>

<span data-ttu-id="4ea79-169">每次从文件或文档中删除标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-169">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="4ea79-170">此事件在 Office 本机应用程序和 Web 应用程序中保存时捕获。</span><span class="sxs-lookup"><span data-stu-id="4ea79-170">This event is captured at the time of save in Office native applications and web applications.</span></span>
- <span data-ttu-id="4ea79-171">在 Azure 信息保护加载项中出现时捕获它。</span><span class="sxs-lookup"><span data-stu-id="4ea79-171">It is captured at the time of occurrence in Azure Information protection add-ins.</span></span> 
- <span data-ttu-id="4ea79-172">Outlook 上的敏感度标签（带有 Office 本机 MIP 标签）收集在文件保存/电子邮件发送操作之前生成的最后一个标签事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-172">Sensitivity labeling, with Office native MIP label, on Outlook collects the last labeling event that was generated before file save/email send actions.</span></span>

|<span data-ttu-id="4ea79-173">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-173">Source</span></span>  |<span data-ttu-id="4ea79-174">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-174">Reported in activity explorer</span></span> | <span data-ttu-id="4ea79-175">注释</span><span class="sxs-lookup"><span data-stu-id="4ea79-175">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4ea79-176">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-176">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4ea79-177">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-177">yes</span></span>         |
|<span data-ttu-id="4ea79-178">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-178">Outlook</span></span>         |<span data-ttu-id="4ea79-179">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-179">yes</span></span>         |<span data-ttu-id="4ea79-180">Win 32</span><span class="sxs-lookup"><span data-stu-id="4ea79-180">Win 32</span></span>|
|<span data-ttu-id="4ea79-181">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-181">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4ea79-182">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-182">yes</span></span>         |
|<span data-ttu-id="4ea79-183">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-183">Exchange</span></span>         |<span data-ttu-id="4ea79-184">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-184">yes</span></span>         |
|<span data-ttu-id="4ea79-185">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4ea79-185">AIP unified client</span></span>         |<span data-ttu-id="4ea79-186">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-186">yes</span></span>         |<span data-ttu-id="4ea79-187">AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作</span><span class="sxs-lookup"><span data-stu-id="4ea79-187">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span>|
|<span data-ttu-id="4ea79-188">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-188">AIP unified scanner</span></span>         |<span data-ttu-id="4ea79-189">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-189">yes</span></span>         |<span data-ttu-id="4ea79-190">AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作</span><span class="sxs-lookup"><span data-stu-id="4ea79-190">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="4ea79-191">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-191">MIP SDK</span></span>         |<span data-ttu-id="4ea79-192">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-192">yes</span></span>         |<span data-ttu-id="4ea79-193">AIP *删除标签* 操作已映射到活动资源管理器 *中的标签* 删除操作</span><span class="sxs-lookup"><span data-stu-id="4ea79-193">the AIP *remove label* action is mapped to the *label removed* action in activity explorer</span></span> |
|<span data-ttu-id="4ea79-194">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4ea79-194">RMS service</span></span>         |<span data-ttu-id="4ea79-195">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-195">not applicable</span></span>         |
|<span data-ttu-id="4ea79-196">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-196">Power BI desktop and Web</span></span>         |<span data-ttu-id="4ea79-197">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-197">no</span></span>         |<span data-ttu-id="4ea79-198">可在 Microsoft 365 审核日志中访问</span><span class="sxs-lookup"><span data-stu-id="4ea79-198">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="4ea79-199">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-199">MCAS</span></span>     |<span data-ttu-id="4ea79-200">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-200">no</span></span>         |         |
 

## <a name="sensitivity-label-file-read"></a><span data-ttu-id="4ea79-201">已读取敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="4ea79-201">Sensitivity label file read</span></span>

<span data-ttu-id="4ea79-202">每次打开已标记或受保护的文档时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-202">This event is generated each time a labeled or protected document is opened.</span></span>

|<span data-ttu-id="4ea79-203">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-203">Source</span></span>  |<span data-ttu-id="4ea79-204">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-204">Reported in activity explorer</span></span> | <span data-ttu-id="4ea79-205">注释</span><span class="sxs-lookup"><span data-stu-id="4ea79-205">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4ea79-206">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-206">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4ea79-207">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-207">yes</span></span>         |
|<span data-ttu-id="4ea79-208">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-208">Outlook</span></span>         |<span data-ttu-id="4ea79-209">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-209">no</span></span>         |
|<span data-ttu-id="4ea79-210">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-210">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4ea79-211">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-211">no</span></span>         |
|<span data-ttu-id="4ea79-212">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-212">Exchange</span></span>         |<span data-ttu-id="4ea79-213">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-213">no</span></span>         |
|<span data-ttu-id="4ea79-214">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4ea79-214">AIP unified client</span></span>         |<span data-ttu-id="4ea79-215">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-215">yes</span></span>         |<span data-ttu-id="4ea79-216">AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="4ea79-216">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="4ea79-217">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-217">AIP unified scanner</span></span>         |<span data-ttu-id="4ea79-218">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-218">yes</span></span>         |<span data-ttu-id="4ea79-219">AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="4ea79-219">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="4ea79-220">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-220">MIP SDK</span></span>         |<span data-ttu-id="4ea79-221">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-221">yes</span></span>         |<span data-ttu-id="4ea79-222">AIP *访问* 操作映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="4ea79-222">the AIP *access* action is mapped to the *file read* action in activity explorer</span></span>|
|<span data-ttu-id="4ea79-223">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4ea79-223">RMS service</span></span>         |<span data-ttu-id="4ea79-224">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-224">yes</span></span>         |<span data-ttu-id="4ea79-225">访问 *操作* 映射到活动 *资源管理器中的文件读取* 操作</span><span class="sxs-lookup"><span data-stu-id="4ea79-225">the *access* action is mapped to the *file read* action in activity explorer</span></span> |
|<span data-ttu-id="4ea79-226">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-226">Power BI desktop and Web</span></span>         |<span data-ttu-id="4ea79-227">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-227">no</span></span>         |<span data-ttu-id="4ea79-228">可在 Microsoft 365 审核日志中访问</span><span class="sxs-lookup"><span data-stu-id="4ea79-228">accessible in the Microsoft 365 audit logs</span></span> |
|<span data-ttu-id="4ea79-229">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-229">MCAS</span></span>     |<span data-ttu-id="4ea79-230">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-230">no</span></span>         |         |


## <a name="sensitivity-label-files-discovered"></a><span data-ttu-id="4ea79-231">发现的敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="4ea79-231">Sensitivity label files discovered</span></span>

<span data-ttu-id="4ea79-232">每次发现文件时，当使用 AIP 扫描程序扫描不同位置的敏感数据并查找文件时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-232">This event is generated each time files are discovered when AIP Scanner is used for scanning sensitive data in various locations and finds files.</span></span>

|<span data-ttu-id="4ea79-233">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-233">Source</span></span>  |<span data-ttu-id="4ea79-234">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-234">Reported in activity explorer</span></span> | <span data-ttu-id="4ea79-235">注释</span><span class="sxs-lookup"><span data-stu-id="4ea79-235">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4ea79-236">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-236">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4ea79-237">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-237">not applicable</span></span>         |
|<span data-ttu-id="4ea79-238">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-238">Outlook</span></span>         |<span data-ttu-id="4ea79-239">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-239">not applicable</span></span>         |
|<span data-ttu-id="4ea79-240">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-240">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4ea79-241">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-241">not applicable</span></span>         |
|<span data-ttu-id="4ea79-242">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-242">Exchange</span></span>         |<span data-ttu-id="4ea79-243">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-243">not applicable</span></span>         |
|<span data-ttu-id="4ea79-244">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4ea79-244">AIP unified client</span></span>         |<span data-ttu-id="4ea79-245">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-245">not applicable</span></span>       |
|<span data-ttu-id="4ea79-246">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-246">AIP unified scanner</span></span>         |<span data-ttu-id="4ea79-247">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-247">yes</span></span>         |<span data-ttu-id="4ea79-248">AIP *发现* 操作映射到活动 *资源管理器中发现* 操作的文件</span><span class="sxs-lookup"><span data-stu-id="4ea79-248">the AIP *discover* action is mapped to the *files discovered* action in activity explorer</span></span>|
|<span data-ttu-id="4ea79-249">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-249">MIP SDK</span></span>         |<span data-ttu-id="4ea79-250">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-250">yes</span></span>         |<span data-ttu-id="4ea79-251">AIP *发现* 操作映射到活动 *资源管理器中发现* 的文件操作</span><span class="sxs-lookup"><span data-stu-id="4ea79-251">the AIP *discover* action is mapped to the *file discovered* action in activity explorer</span></span>|
|<span data-ttu-id="4ea79-252">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4ea79-252">RMS service</span></span>         |<span data-ttu-id="4ea79-253">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-253">not applicable</span></span>         |
|<span data-ttu-id="4ea79-254">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-254">Power BI desktop and Web</span></span>         |<span data-ttu-id="4ea79-255">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-255">not applicable</span></span>         |
|<span data-ttu-id="4ea79-256">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-256">MCAS</span></span>     |<span data-ttu-id="4ea79-257">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-257">not applicable</span></span>         |         |


## <a name="sensitivity-label-file-renamed"></a><span data-ttu-id="4ea79-258">已重命名敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="4ea79-258">Sensitivity label file renamed</span></span>

<span data-ttu-id="4ea79-259">每次重命名具有敏感度标签的文档时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-259">This event is generated each time a document with a sensitivity label is renamed.</span></span> 

|<span data-ttu-id="4ea79-260">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-260">Source</span></span>  | <span data-ttu-id="4ea79-261">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-261">Reported in activity explorer</span></span> | <span data-ttu-id="4ea79-262">注释</span><span class="sxs-lookup"><span data-stu-id="4ea79-262">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4ea79-263">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-263">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4ea79-264">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-264">yes</span></span>         |
|<span data-ttu-id="4ea79-265">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-265">Outlook</span></span>         |<span data-ttu-id="4ea79-266">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-266">not applicable</span></span>         |
|<span data-ttu-id="4ea79-267">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-267">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4ea79-268">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-268">no</span></span>        |
|<span data-ttu-id="4ea79-269">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-269">Exchange</span></span>         |<span data-ttu-id="4ea79-270">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-270">not applicable</span></span>         |
|<span data-ttu-id="4ea79-271">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4ea79-271">AIP unified client</span></span>         |<span data-ttu-id="4ea79-272">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-272">no</span></span>         |
|<span data-ttu-id="4ea79-273">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-273">AIP unified scanner</span></span>         |<span data-ttu-id="4ea79-274">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-274">no</span></span>         |
|<span data-ttu-id="4ea79-275">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-275">MIP SDK</span></span>         |<span data-ttu-id="4ea79-276">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-276">no</span></span>         |
|<span data-ttu-id="4ea79-277">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4ea79-277">RMS service</span></span>         |<span data-ttu-id="4ea79-278">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-278">no</span></span>      |
|<span data-ttu-id="4ea79-279">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-279">Power BI desktop and Web</span></span>         |<span data-ttu-id="4ea79-280">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-280">no</span></span>         |
|<span data-ttu-id="4ea79-281">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-281">MCAS</span></span>     |<span data-ttu-id="4ea79-282">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-282">no</span></span>         |         |


## <a name="sensitivity-label-file-removed"></a><span data-ttu-id="4ea79-283">删除了敏感度标签文件</span><span class="sxs-lookup"><span data-stu-id="4ea79-283">Sensitivity label file removed</span></span>

<span data-ttu-id="4ea79-284">每次 AIP 扫描程序检测到之前扫描的文件已删除时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-284">This event is generated each time the AIP scanner detects that a previously scanned file has been removed.</span></span>

|<span data-ttu-id="4ea79-285">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-285">Source</span></span>  |<span data-ttu-id="4ea79-286">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-286">Reported in activity explorer</span></span> | <span data-ttu-id="4ea79-287">注释</span><span class="sxs-lookup"><span data-stu-id="4ea79-287">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4ea79-288">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-288">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4ea79-289">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-289">not applicable</span></span>         |
|<span data-ttu-id="4ea79-290">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-290">Outlook</span></span>         |<span data-ttu-id="4ea79-291">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-291">not applicable</span></span>         |
|<span data-ttu-id="4ea79-292">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-292">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4ea79-293">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-293">not applicable</span></span>           |
|<span data-ttu-id="4ea79-294">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-294">Exchange</span></span>         |<span data-ttu-id="4ea79-295">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-295">not applicable</span></span>         |
|<span data-ttu-id="4ea79-296">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4ea79-296">AIP unified client</span></span>         |<span data-ttu-id="4ea79-297">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-297">not applicable</span></span>            |
|<span data-ttu-id="4ea79-298">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-298">AIP unified scanner</span></span>         |<span data-ttu-id="4ea79-299">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-299">yes</span></span>         |
|<span data-ttu-id="4ea79-300">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-300">MIP SDK</span></span>         |<span data-ttu-id="4ea79-301">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-301">not applicable</span></span>            |
|<span data-ttu-id="4ea79-302">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4ea79-302">RMS service</span></span>         |<span data-ttu-id="4ea79-303">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-303">not applicable</span></span>         |
|<span data-ttu-id="4ea79-304">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-304">Power BI desktop and Web</span></span>         |<span data-ttu-id="4ea79-305">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-305">not applicable</span></span>  |
|<span data-ttu-id="4ea79-306">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-306">MCAS</span></span>     |<span data-ttu-id="4ea79-307">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-307">not applicable</span></span>        |         |

### <a name="sensitivity-label-protection-applied"></a><span data-ttu-id="4ea79-308">应用的敏感度标签保护</span><span class="sxs-lookup"><span data-stu-id="4ea79-308">Sensitivity label protection applied</span></span>

<span data-ttu-id="4ea79-309">此事件生成首次保护时手动添加到没有标签的项。</span><span class="sxs-lookup"><span data-stu-id="4ea79-309">This event is generated the first-time protection is added manually to an item that does not have a label.</span></span>

|<span data-ttu-id="4ea79-310">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-310">Source</span></span>  |<span data-ttu-id="4ea79-311">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-311">Reported in activity explorer</span></span> | <span data-ttu-id="4ea79-312">注释</span><span class="sxs-lookup"><span data-stu-id="4ea79-312">Note</span></span>  |
|---------|---------|---------| 
|<span data-ttu-id="4ea79-313">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-313">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4ea79-314">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-314">no</span></span>         |
|<span data-ttu-id="4ea79-315">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-315">Outlook</span></span>         |<span data-ttu-id="4ea79-316">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-316">no</span></span>         |
|<span data-ttu-id="4ea79-317">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-317">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4ea79-318">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-318">not applicable</span></span>           |
|<span data-ttu-id="4ea79-319">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-319">Exchange</span></span>         |<span data-ttu-id="4ea79-320">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-320">no</span></span>       |
|<span data-ttu-id="4ea79-321">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4ea79-321">AIP unified client</span></span>         |<span data-ttu-id="4ea79-322">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-322">yes</span></span>            |
|<span data-ttu-id="4ea79-323">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-323">AIP unified scanner</span></span>         |<span data-ttu-id="4ea79-324">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-324">not applicable</span></span>         |
|<span data-ttu-id="4ea79-325">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-325">MIP SDK</span></span>         |<span data-ttu-id="4ea79-326">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-326">yes</span></span>            |
|<span data-ttu-id="4ea79-327">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4ea79-327">RMS service</span></span>         |<span data-ttu-id="4ea79-328">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-328">not applicable</span></span>         |
|<span data-ttu-id="4ea79-329">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-329">Power BI desktop and Web</span></span>         |<span data-ttu-id="4ea79-330">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-330">not applicable</span></span>            |
|<span data-ttu-id="4ea79-331">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-331">MCAS</span></span>     |<span data-ttu-id="4ea79-332">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-332">not applicable</span></span>        |         |

## <a name="sensitivity-label-protection-changed"></a><span data-ttu-id="4ea79-333">敏感度标签保护已更改</span><span class="sxs-lookup"><span data-stu-id="4ea79-333">Sensitivity label protection changed</span></span>

<span data-ttu-id="4ea79-334">每次手动更改未标记文档的保护时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-334">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="4ea79-335">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-335">Source</span></span>  |<span data-ttu-id="4ea79-336">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-336">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4ea79-337">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-337">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4ea79-338">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-338">no</span></span>         |
|<span data-ttu-id="4ea79-339">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-339">Outlook</span></span>         |<span data-ttu-id="4ea79-340">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-340">no</span></span>         |
|<span data-ttu-id="4ea79-341">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-341">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4ea79-342">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-342">not applicable</span></span>           |
|<span data-ttu-id="4ea79-343">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-343">Exchange</span></span>         |<span data-ttu-id="4ea79-344">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-344">no</span></span>       |
|<span data-ttu-id="4ea79-345">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4ea79-345">AIP unified client</span></span>         |<span data-ttu-id="4ea79-346">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-346">yes</span></span>            |
|<span data-ttu-id="4ea79-347">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-347">AIP unified scanner</span></span>         |<span data-ttu-id="4ea79-348">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-348">not applicable</span></span>         |
|<span data-ttu-id="4ea79-349">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-349">MIP SDK</span></span>         |<span data-ttu-id="4ea79-350">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-350">yes</span></span>            |
|<span data-ttu-id="4ea79-351">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4ea79-351">RMS service</span></span>         |<span data-ttu-id="4ea79-352">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-352">not applicable</span></span>         |
|<span data-ttu-id="4ea79-353">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-353">Power BI desktop and Web</span></span>         |<span data-ttu-id="4ea79-354">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-354">not applicable</span></span>            |
|<span data-ttu-id="4ea79-355">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-355">MCAS</span></span>     |<span data-ttu-id="4ea79-356">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-356">not applicable</span></span>        |

## <a name="sensitivity-label-protection-removed"></a><span data-ttu-id="4ea79-357">删除了敏感度标签保护</span><span class="sxs-lookup"><span data-stu-id="4ea79-357">Sensitivity label protection removed</span></span>

<span data-ttu-id="4ea79-358">每次手动更改未标记文档的保护时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-358">This event is generated each time the protection on an unlabeled document is changed manually.</span></span>

|<span data-ttu-id="4ea79-359">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-359">Source</span></span>  |<span data-ttu-id="4ea79-360">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-360">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4ea79-361">Word、Excel、PowerPoint</span><span class="sxs-lookup"><span data-stu-id="4ea79-361">Word, Excel, PowerPoint</span></span>         |<span data-ttu-id="4ea79-362">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-362">no</span></span>         |
|<span data-ttu-id="4ea79-363">Outlook</span><span class="sxs-lookup"><span data-stu-id="4ea79-363">Outlook</span></span>         |<span data-ttu-id="4ea79-364">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-364">no</span></span>         |
|<span data-ttu-id="4ea79-365">SharePoint Online、OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-365">SharePoint Online, OneDrive</span></span>         |<span data-ttu-id="4ea79-366">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-366">not applicable</span></span>           |
|<span data-ttu-id="4ea79-367">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-367">Exchange</span></span>         |<span data-ttu-id="4ea79-368">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-368">no</span></span>       |
|<span data-ttu-id="4ea79-369">AIP 统一客户端</span><span class="sxs-lookup"><span data-stu-id="4ea79-369">AIP unified client</span></span>         |<span data-ttu-id="4ea79-370">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-370">yes</span></span>            |
|<span data-ttu-id="4ea79-371">AIP 统一扫描程序</span><span class="sxs-lookup"><span data-stu-id="4ea79-371">AIP unified scanner</span></span>         |<span data-ttu-id="4ea79-372">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-372">not applicable</span></span>         |
|<span data-ttu-id="4ea79-373">MIP SDK</span><span class="sxs-lookup"><span data-stu-id="4ea79-373">MIP SDK</span></span>         |<span data-ttu-id="4ea79-374">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-374">yes</span></span>            |
|<span data-ttu-id="4ea79-375">RMS 服务</span><span class="sxs-lookup"><span data-stu-id="4ea79-375">RMS service</span></span>         |<span data-ttu-id="4ea79-376">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-376">not applicable</span></span>         |
|<span data-ttu-id="4ea79-377">Power BI 桌面和 Web</span><span class="sxs-lookup"><span data-stu-id="4ea79-377">Power BI desktop and Web</span></span>         |<span data-ttu-id="4ea79-378">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-378">not applicable</span></span>            |
|<span data-ttu-id="4ea79-379">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-379">MCAS</span></span>     |<span data-ttu-id="4ea79-380">不适用</span><span class="sxs-lookup"><span data-stu-id="4ea79-380">not applicable</span></span>        |

## <a name="sensitivity-label-dlp-policy-matched"></a><span data-ttu-id="4ea79-381">已匹配的敏感度标签 DLP 策略</span><span class="sxs-lookup"><span data-stu-id="4ea79-381">Sensitivity label DLP policy matched</span></span>

<span data-ttu-id="4ea79-382">每次匹配 DLP 策略时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-382">This event is generated each time a DLP policy is matched.</span></span>

|<span data-ttu-id="4ea79-383">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-383">Source</span></span>  |<span data-ttu-id="4ea79-384">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-384">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4ea79-385">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-385">Exchange</span></span>         |<span data-ttu-id="4ea79-386">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-386">yes</span></span>       |
|<span data-ttu-id="4ea79-387">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4ea79-387">SharePoint Online</span></span>|<span data-ttu-id="4ea79-388">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-388">yes</span></span>          |
|<span data-ttu-id="4ea79-389">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-389">OneDrive</span></span> |<span data-ttu-id="4ea79-390">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-390">yes</span></span>|
|<span data-ttu-id="4ea79-391">Teams</span><span class="sxs-lookup"><span data-stu-id="4ea79-391">Teams</span></span> |<span data-ttu-id="4ea79-392">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-392">yes</span></span>   |
|<span data-ttu-id="4ea79-393">Windows 10 设备</span><span class="sxs-lookup"><span data-stu-id="4ea79-393">Windows 10 devices</span></span>         |<span data-ttu-id="4ea79-394">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-394">yes</span></span> |
|<span data-ttu-id="4ea79-395">MAC</span><span class="sxs-lookup"><span data-stu-id="4ea79-395">MAC</span></span>         |<span data-ttu-id="4ea79-396">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-396">no</span></span>     |
|<span data-ttu-id="4ea79-397">本地</span><span class="sxs-lookup"><span data-stu-id="4ea79-397">on-premises</span></span>         |<span data-ttu-id="4ea79-398">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-398">no</span></span>|
|<span data-ttu-id="4ea79-399">MCAS</span><span class="sxs-lookup"><span data-stu-id="4ea79-399">MCAS</span></span>     |<span data-ttu-id="4ea79-400">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-400">no</span></span>        | 

<span data-ttu-id="4ea79-401">适用于 Windows 10 设备 (终结点 DLP) 为：</span><span class="sxs-lookup"><span data-stu-id="4ea79-401">The events for Windows 10 Devices (Endpoint DLP) are:</span></span>

- <span data-ttu-id="4ea79-402">文件已删除</span><span class="sxs-lookup"><span data-stu-id="4ea79-402">file deleted</span></span>
- <span data-ttu-id="4ea79-403">已创建文件</span><span class="sxs-lookup"><span data-stu-id="4ea79-403">file created</span></span>
- <span data-ttu-id="4ea79-404">文件复制到剪贴板</span><span class="sxs-lookup"><span data-stu-id="4ea79-404">file copied to clipboard</span></span>
- <span data-ttu-id="4ea79-405">已修改文件</span><span class="sxs-lookup"><span data-stu-id="4ea79-405">file modified</span></span>
- <span data-ttu-id="4ea79-406">文件读取</span><span class="sxs-lookup"><span data-stu-id="4ea79-406">file read</span></span>
- <span data-ttu-id="4ea79-407">文件打印</span><span class="sxs-lookup"><span data-stu-id="4ea79-407">file printed</span></span>
- <span data-ttu-id="4ea79-408">文件重命名</span><span class="sxs-lookup"><span data-stu-id="4ea79-408">file renamed</span></span>
- <span data-ttu-id="4ea79-409">文件复制到网络共享</span><span class="sxs-lookup"><span data-stu-id="4ea79-409">file copied to network share</span></span>
- <span data-ttu-id="4ea79-410">未允许的应用访问的文件</span><span class="sxs-lookup"><span data-stu-id="4ea79-410">file accessed by unallowed app</span></span>


## <a name="retention-label-applied"></a><span data-ttu-id="4ea79-411">应用的保留标签</span><span class="sxs-lookup"><span data-stu-id="4ea79-411">Retention label applied</span></span> 

<span data-ttu-id="4ea79-412">每次标记未标记的文档或发送带有标签的电子邮件时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-412">This event is generated each time an unlabeled document is labeled or an email is sent with a label.</span></span>

- <span data-ttu-id="4ea79-413">它在 Office 本机应用程序和 Web 应用程序中保存时捕获。</span><span class="sxs-lookup"><span data-stu-id="4ea79-413">It is captured at the time of save in Office native applications and web applications.</span></span>

|<span data-ttu-id="4ea79-414">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-414">Source</span></span>  |<span data-ttu-id="4ea79-415">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-415">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4ea79-416">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-416">Exchange</span></span>         |<span data-ttu-id="4ea79-417">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-417">no</span></span>       |
|<span data-ttu-id="4ea79-418">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4ea79-418">SharePoint Online</span></span>|<span data-ttu-id="4ea79-419">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-419">yes</span></span>          |
|<span data-ttu-id="4ea79-420">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-420">OneDrive</span></span> |<span data-ttu-id="4ea79-421">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-421">yes</span></span>|

## <a name="retention-label-changed"></a><span data-ttu-id="4ea79-422">已更改保留标签</span><span class="sxs-lookup"><span data-stu-id="4ea79-422">Retention label changed</span></span>

<span data-ttu-id="4ea79-423">每次在文档或电子邮件上更新标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-423">This event is generated each time a label is updated on a document or email.</span></span>

- <span data-ttu-id="4ea79-424">它在保存时捕获。</span><span class="sxs-lookup"><span data-stu-id="4ea79-424">It is captured at the time of save.</span></span>

|<span data-ttu-id="4ea79-425">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-425">Source</span></span>  |<span data-ttu-id="4ea79-426">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-426">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4ea79-427">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-427">Exchange</span></span>         |<span data-ttu-id="4ea79-428">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-428">no</span></span>       |
|<span data-ttu-id="4ea79-429">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4ea79-429">SharePoint Online</span></span>|<span data-ttu-id="4ea79-430">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-430">yes</span></span>          |
|<span data-ttu-id="4ea79-431">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-431">OneDrive</span></span> |<span data-ttu-id="4ea79-432">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-432">yes</span></span>|
 
## <a name="retention-label-removed"></a><span data-ttu-id="4ea79-433">已删除保留标签</span><span class="sxs-lookup"><span data-stu-id="4ea79-433">Retention label removed</span></span>

<span data-ttu-id="4ea79-434">每次从文件或文档中删除标签时，将生成此事件。</span><span class="sxs-lookup"><span data-stu-id="4ea79-434">This event is generated each time a label is removed from a file or document.</span></span>

- <span data-ttu-id="4ea79-435">它在保存时捕获。</span><span class="sxs-lookup"><span data-stu-id="4ea79-435">It is captured at the time of save.</span></span>

|<span data-ttu-id="4ea79-436">Source</span><span class="sxs-lookup"><span data-stu-id="4ea79-436">Source</span></span>  |<span data-ttu-id="4ea79-437">在活动资源管理器中报告</span><span class="sxs-lookup"><span data-stu-id="4ea79-437">Reported in activity explorer</span></span> |
|---------|---------| 
|<span data-ttu-id="4ea79-438">Exchange</span><span class="sxs-lookup"><span data-stu-id="4ea79-438">Exchange</span></span>         |<span data-ttu-id="4ea79-439">否</span><span class="sxs-lookup"><span data-stu-id="4ea79-439">no</span></span>       |
|<span data-ttu-id="4ea79-440">SharePoint Online</span><span class="sxs-lookup"><span data-stu-id="4ea79-440">SharePoint Online</span></span>|<span data-ttu-id="4ea79-441">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-441">yes</span></span>          |
|<span data-ttu-id="4ea79-442">OneDrive</span><span class="sxs-lookup"><span data-stu-id="4ea79-442">OneDrive</span></span> |<span data-ttu-id="4ea79-443">是</span><span class="sxs-lookup"><span data-stu-id="4ea79-443">yes</span></span>|


## <a name="known-issues"></a><span data-ttu-id="4ea79-444">已知问题</span><span class="sxs-lookup"><span data-stu-id="4ea79-444">Known issues</span></span>
  
- <span data-ttu-id="4ea79-445">向最终用户显示推荐的标签工具提示时，不会捕获它。</span><span class="sxs-lookup"><span data-stu-id="4ea79-445">When the recommended label tool tip is shown to an end user, it is not captured.</span></span> <span data-ttu-id="4ea79-446">但是，如果用户选择应用建议的标签，标签将显示在"如何应用"字段下 *，显示为\*\*"推荐"*</span><span class="sxs-lookup"><span data-stu-id="4ea79-446">But if the user chooses to apply the recommended label, the label will be shown under the *How applied* field as *Recommended*</span></span>  

- <span data-ttu-id="4ea79-447">从 Sharepoint 和 OneDrive 降级敏感度标签时，目前无法提供理由文本。</span><span class="sxs-lookup"><span data-stu-id="4ea79-447">Justification text is not currently available on sensitivity label downgrade from Sharepoint and OneDrive.</span></span>  

- <span data-ttu-id="4ea79-448">敏感信息类型当前不适用于 Word、Excel、PowerPoint 和 Outlook 以及 SharePoint Online 和 OneDrive 中的自动标记活动。</span><span class="sxs-lookup"><span data-stu-id="4ea79-448">Sensitive information types are currently not available for autolabeling activities from Word, Excel, PowerPoint, and Outlook, as well as SharePoint Online, and OneDrive.</span></span>
