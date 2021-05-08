---
title: 计划程序Microsoft 365常见问题解答
ms.author: v-aiyengar
author: AshaIyengar21
manager: serdars
audience: Admin
ms.topic: article
ms.service: scheduler
localization_priority: Normal
description: 计划程序Microsoft 365常见问题解答
ms.openlocfilehash: 12c2c00761b9a10fac6c62bc4d7ff5909ac935a7
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/08/2021
ms.locfileid: "52286140"
---
# <a name="scheduler-for-microsoft-365-faqs"></a><span data-ttu-id="3cb66-103">计划程序Microsoft 365常见问题解答</span><span class="sxs-lookup"><span data-stu-id="3cb66-103">Scheduler for Microsoft 365 FAQs</span></span>

<span data-ttu-id="3cb66-104">**问题：** 计划程序如何与其他 Cortana 功能（如 *Cortana for Windows、* 每日简介 *电子邮件* 和播放 *我的电子邮件）集成*？</span><span class="sxs-lookup"><span data-stu-id="3cb66-104">**Question:** How does Scheduler integrate with other Cortana features, such as *Cortana for Windows*, *Daily Briefing Email*, and *Play My Emails*?</span></span></br>
<span data-ttu-id="3cb66-105">计划程序是独立于其他 Cortana 功能的服务。</span><span class="sxs-lookup"><span data-stu-id="3cb66-105">Scheduler is an independent service from other Cortana features.</span></span> <span data-ttu-id="3cb66-106">其他 Cortana 功能可以在租户级别禁用，并且仍可使用 Cortana cortana@yourdomain.com 启用计划程序。</span><span class="sxs-lookup"><span data-stu-id="3cb66-106">Other Cortana features can be disabled at the tenant level, and Scheduler can still be enabled by using the cortana@yourdomain.com email address.</span></span> <span data-ttu-id="3cb66-107">目前，用户只能通过电子邮件与计划程序交互。</span><span class="sxs-lookup"><span data-stu-id="3cb66-107">Currently, users can only interact with Scheduler via email.</span></span>

<span data-ttu-id="3cb66-108">**问题：** 这是否仅适用于Outlook？</span><span class="sxs-lookup"><span data-stu-id="3cb66-108">**Question:** Does this work only with Outlook?</span></span> <span data-ttu-id="3cb66-109">是否支持其他电子邮件产品？</span><span class="sxs-lookup"><span data-stu-id="3cb66-109">Are other email products supported?</span></span></br>
<span data-ttu-id="3cb66-110">只要你拥有许可证，除上述三项要求外，用户 cortana@yourdomain.com 任何设备上的任何电子邮件客户端发送电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3cb66-110">As long as you have a license, Other than the three requirements above, users can email cortana@yourdomain.com from any email client on any device.</span></span>

<span data-ttu-id="3cb66-111">**问题：** 联系人能否位于 Outlook GAL 或其他公司等效项上的个人联系人列表中？</span><span class="sxs-lookup"><span data-stu-id="3cb66-111">**Question:** Can contacts be in a personal contact list on Outlook and GAL or other company equivalent?</span></span></br>
<span data-ttu-id="3cb66-112">与会者可以是公司内外具有电子邮件地址的任何人。</span><span class="sxs-lookup"><span data-stu-id="3cb66-112">Meeting attendees can be anyone with an email address inside or outside the company.</span></span> <span data-ttu-id="3cb66-113">遗憾的是，计划程序无法通过现在在 GAL 中查找来自动将名称转换为电子邮件地址/别名。</span><span class="sxs-lookup"><span data-stu-id="3cb66-113">Unfortunately, Scheduler cannot automatically translate names to email addresses / alias by looking it up in the GAL today.</span></span>

<span data-ttu-id="3cb66-114">**问题：** 能否将计划程序与已安装的版本 (本地) 版本Outlook？</span><span class="sxs-lookup"><span data-stu-id="3cb66-114">**Question:** Can I use Scheduler with my installed version (on-premises) version of Outlook?</span></span></br>
<span data-ttu-id="3cb66-115">计划程序需要Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="3cb66-115">Scheduler requires Exchange Online.</span></span> <span data-ttu-id="3cb66-116">不能与 Exchange Server (On-Prem) 。</span><span class="sxs-lookup"><span data-stu-id="3cb66-116">Does not work with Exchange Server (On-Prem).</span></span> <span data-ttu-id="3cb66-117">适用于任何电子邮件客户端、Outlook桌面、OWA、iOS、android、gmail 等。</span><span class="sxs-lookup"><span data-stu-id="3cb66-117">Works with any email client, Outlook Desktop, OWA, iOS, android, gmail, and so on.</span></span>

<span data-ttu-id="3cb66-118">**问题：** Outlook必须在后台打开吗？</span><span class="sxs-lookup"><span data-stu-id="3cb66-118">**Question:** Does Outlook have to be open in the background?</span></span></br>
<span data-ttu-id="3cb66-119">Outlook不需要在后台打开。</span><span class="sxs-lookup"><span data-stu-id="3cb66-119">Outlook doesn't need to be open in the background.</span></span> <span data-ttu-id="3cb66-120">你只需向 Cortana 发送一个邮件，并依靠它完成大部分工作。</span><span class="sxs-lookup"><span data-stu-id="3cb66-120">All you need to do is send Cortana a mail and rely on it to do the bulk of the work.</span></span>

## <a name="frequently-asked-trust-and-privacy-questions"></a><span data-ttu-id="3cb66-121">常见信任和隐私问题</span><span class="sxs-lookup"><span data-stu-id="3cb66-121">Frequently Asked Trust and Privacy Questions</span></span>

<span data-ttu-id="3cb66-122">**问题：** 计划程序如何工作？</span><span class="sxs-lookup"><span data-stu-id="3cb66-122">**Question:** How does Scheduler work?</span></span></br>
<span data-ttu-id="3cb66-123">计划程序使用日程安排智能 (AI) 人员助理进行扩充。</span><span class="sxs-lookup"><span data-stu-id="3cb66-123">Scheduler uses Scheduling Intelligence (AI) augmented with human assistants.</span></span> <span data-ttu-id="3cb66-124">如果 AI 模型需要以与 Cortana 通信的自然语言提供支持，会议请求将升级为人工审阅和完成。</span><span class="sxs-lookup"><span data-stu-id="3cb66-124">If AI models generate a need for support in the natural language of communication with Cortana, the meeting request escalates to a human for review and completion.</span></span>

<span data-ttu-id="3cb66-125">**问题** Who审阅已升级请求的人吗？</span><span class="sxs-lookup"><span data-stu-id="3cb66-125">**Question:** Who are the humans that review escalated requests?</span></span> </br>
<span data-ttu-id="3cb66-126">计划程序助理是 Microsoft 供应商安全和隐私保证 (SSPA) 个人信息和高度机密信息认证的 SSPA。</span><span class="sxs-lookup"><span data-stu-id="3cb66-126">Scheduler assistants are Microsoft Supplier Security and Privacy Assurance (SSPA) certified for personal and highly confidential information.</span></span> 

<span data-ttu-id="3cb66-127">**问题：** SSPA 助理可以查看哪些信息？</span><span class="sxs-lookup"><span data-stu-id="3cb66-127">**Question:** What can SSPA Assistants view?</span></span></br>
<span data-ttu-id="3cb66-128">计划程序与 SSPA 助理可以查看发送到 Cortana 的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3cb66-128">Scheduler and the SSPA Assistants can view  the emails that are addressed to Cortana.</span></span> <span data-ttu-id="3cb66-129">在线程电子邮件交换中，只会处理包含 Cortana 电子邮件地址的电子邮件，不会处理主题中添加 Cortana 之前之前的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3cb66-129">In a threaded email exchange, only the emails that include Cortana’s email address will be processed, not the previous emails in the thread before Cortana was added.</span></span>   

<span data-ttu-id="3cb66-130">**问题：** 客户数据是否保留在计划程序的数据记录Flow？</span><span class="sxs-lookup"><span data-stu-id="3cb66-130">**Question:** Is customer data retained in the Scheduler’s Data Flow?</span></span> </br>
<span data-ttu-id="3cb66-131">计划程序根据 GDPR 准则、Microsoft 365信任&策略和租户电子邮件策略，在租户边界内存储所有客户内容并保留数据。</span><span class="sxs-lookup"><span data-stu-id="3cb66-131">Scheduler stores all customer content within the tenant boundaries and retains data in accordance with GDPR guidelines, Microsoft 365 Trust & Privacy policies, and tenant email policies.</span></span>

<span data-ttu-id="3cb66-132">**问题：** 计划程序如何处理内部与会者的忙/闲数据？</span><span class="sxs-lookup"><span data-stu-id="3cb66-132">**Question:** How does Scheduler process the free/busy data of internal attendees?</span></span> </br>
<span data-ttu-id="3cb66-133">计划程序自动化使用 *findMeetingTimes* 服务来标识与会者和组织者可相互使用的时间。</span><span class="sxs-lookup"><span data-stu-id="3cb66-133">Scheduler’s automation uses the *findMeetingTimes* service to identify times that are mutually available for attendees and the organizer.</span></span> <span data-ttu-id="3cb66-134">此服务支持Outlook *会议表单中的* 建议时间Outlook体验。</span><span class="sxs-lookup"><span data-stu-id="3cb66-134">This service powers other Outlook experiences such as *Suggested Times* in the Outlook meeting form.</span></span> <span data-ttu-id="3cb66-135">忙/闲与会者信息不会明确用作忙/闲块。</span><span class="sxs-lookup"><span data-stu-id="3cb66-135">Free/busy attendee information is not consumed explicitly as free/busy blocks.</span></span> 

<span data-ttu-id="3cb66-136">**问题：** 计划程序 GDPR 是否符合？</span><span class="sxs-lookup"><span data-stu-id="3cb66-136">**Question:** Is Scheduler GDPR Compliant?</span></span> </br>
<span data-ttu-id="3cb66-137">对。</span><span class="sxs-lookup"><span data-stu-id="3cb66-137">Yes.</span></span>

<span data-ttu-id="3cb66-138">**问题：Who** Cortana 邮箱的访问权限？</span><span class="sxs-lookup"><span data-stu-id="3cb66-138">**Question:** Who has access to the Cortana mailbox?</span></span> </br>
<span data-ttu-id="3cb66-139">计划程序处理发送到租户的 Cortana 邮箱的会议请求和关联电子邮件。</span><span class="sxs-lookup"><span data-stu-id="3cb66-139">Scheduler processes meeting requests and associated emails that are sent to your tenant’s Cortana mailbox.</span></span> <span data-ttu-id="3cb66-140">Microsoft 对 Cortana 邮箱没有任何其他访问权限，除非根据租户管理员的请求通过密码箱审批。</span><span class="sxs-lookup"><span data-stu-id="3cb66-140">Microsoft does not have any other access to the Cortana mailbox except through Lockbox approval at the request of the tenant admin.</span></span>  

<span data-ttu-id="3cb66-141">**问题：** 客户数据是否用于培训 AI 模型？</span><span class="sxs-lookup"><span data-stu-id="3cb66-141">**Question:** Is customer data used for training AI models?</span></span></br>
<span data-ttu-id="3cb66-142">计划程序的客户内容Microsoft 365数据培训集。</span><span class="sxs-lookup"><span data-stu-id="3cb66-142">No customer content from Scheduler for Microsoft 365 can be used for data training sets.</span></span> <span data-ttu-id="3cb66-143">所有客户内容都驻留在客户租户中。</span><span class="sxs-lookup"><span data-stu-id="3cb66-143">All customer content resides in the customer tenant.</span></span>  

<span data-ttu-id="3cb66-144">**问题：** 计划程序将处理加密邮件吗？</span><span class="sxs-lookup"><span data-stu-id="3cb66-144">**Question:** Will Scheduler process encrypted mail?</span></span></br>
<span data-ttu-id="3cb66-145">否，计划程序工作流将拒绝加密邮件。</span><span class="sxs-lookup"><span data-stu-id="3cb66-145">No, encrypted mail will be rejected by the Scheduler workflow.</span></span> 




