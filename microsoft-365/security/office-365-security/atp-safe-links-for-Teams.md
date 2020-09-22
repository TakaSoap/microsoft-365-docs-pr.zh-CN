---
title: 用于团队、safelinks、安全链接、阻止恶意链接的 ATP 安全链接、office 365 atp、团队安全链接、阻止用户单击 "不良链接"、"恶意链接"
ms.author: tracyp
author: MSFTTracyP
manager: dansimp
audience: Admin
ms.date: 02/28/2020
ms.topic: overview
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.collection:
- M365-security-compliance
description: 团队现在可以在你单击时访问安全链接。 无论您是否在使用聊天1开/1 聊天、组之间或频道以及选项卡，如果您有 Office 365 ATP 的订阅，您都可以启用和使用此安全功能。
ms.openlocfilehash: 362fb37b352a77aea07b899b707dbf4ac3d440d5
ms.sourcegitcommit: c083602dda3cdcb5b58cb8aa070d77019075f765
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/22/2020
ms.locfileid: "48198747"
---
<!--06/21/2019-->

# <a name="safe-links-in-teams"></a><span data-ttu-id="85659-104">Teams 中安全链接</span><span class="sxs-lookup"><span data-stu-id="85659-104">Safe Links in Teams</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]


> [!IMPORTANT]
> <span data-ttu-id="85659-105">对于 Microsoft 团队技术采用计划中的客户，此功能处于 **公共预览版** 中， (点击) 从2020年2月28日到。</span><span class="sxs-lookup"><span data-stu-id="85659-105">This feature is in **Public Preview** for customers in the Microsoft Teams Technology Adoption Program (TAP) as of Feb 28, 2020.</span></span> <span data-ttu-id="85659-106">当团队的安全链接更广泛可用时，将从文章中删除此注释。</span><span class="sxs-lookup"><span data-stu-id="85659-106">This note will be removed from the article when Safe Links for Teams is more widely available.</span></span>

<span data-ttu-id="85659-107">Microsoft 团队（用于管理工作的 Microsoft 基于云的应用程序）已使用安全附件 (Office 365) ，但在单击时，它现在可以访问安全链接。</span><span class="sxs-lookup"><span data-stu-id="85659-107">Microsoft Teams, a Microsoft cloud-based application for managing your work, already uses Safe Attachments (for Office 365), but it will now have access to Safe Links at the time of your click.</span></span> <span data-ttu-id="85659-108">无论您是在使用聊天、群研讨、频道还是选项卡，如果您订阅了 Office 365 ATP，您都可以启用和使用此安全措施。</span><span class="sxs-lookup"><span data-stu-id="85659-108">Whether you're using Chats, Group Chats, Channels, or Tabs, if you have a subscription to Office 365 ATP, you will have the ability to enable and use this safety measure.</span></span> <span data-ttu-id="85659-109">要详细了解许可要求，请参阅 [Microsoft 365 租户级服务许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="85659-109">To learn more about licensing requirements, see [Microsoft 365 Tenant-Level Services Licensing Guidance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="85659-110">以下是相应的工作方式：</span><span class="sxs-lookup"><span data-stu-id="85659-110">Here's how it works:</span></span>

1. <span data-ttu-id="85659-111">当您启动团队应用程序时，Microsoft 365 将进行检查以确保用户属于具有 Office 365 ATP 的组织，并且该用户是已为 Microsoft 团队启用了保护的活动安全链接策略的一部分。</span><span class="sxs-lookup"><span data-stu-id="85659-111">When you start the Teams application, Microsoft 365 will check to make sure the user belongs to an organization that has Office 365 ATP, and that the user is part of an active safe links policy with its protection enabled for Microsoft Teams.</span></span>

2. <span data-ttu-id="85659-112">如果上述值为 true，则在聊天、组聊天、频道和该用户的选项卡中单击时，将对 Url 进行验证。</span><span class="sxs-lookup"><span data-stu-id="85659-112">If the above are true, then URLs will be validated at the time of click in Chats, Group Chats, Channels, and in Tabs for that user.</span></span>

## <a name="what-will-users-experience"></a><span data-ttu-id="85659-113">用户会遇到什么情况？</span><span class="sxs-lookup"><span data-stu-id="85659-113">What will users experience?</span></span>

<span data-ttu-id="85659-114">所有受保护的用户都将获得以下危险 Url 体验：</span><span class="sxs-lookup"><span data-stu-id="85659-114">All protected users will have this experience with hazardous URLs:</span></span>

- <span data-ttu-id="85659-115">如果从团队对话、分组聊天或频道中单击了该链接，则页面将在默认浏览器中呈现。</span><span class="sxs-lookup"><span data-stu-id="85659-115">If the link was clicked from a Teams conversation, group chat, or from channels, a page will render in the default browser.</span></span> <span data-ttu-id="85659-116">如果从固定的选项卡上单击了该链接，该页面将显示在该选项卡中的团队 GUI 中，并且出于安全考虑，将禁用在浏览器中打开的选项。</span><span class="sxs-lookup"><span data-stu-id="85659-116">If the link was clicked from a pinned tab, the page will appear in the Teams GUI within that tab, and the option to open in browser will be disabled for security purposes.</span></span>

- <span data-ttu-id="85659-117">将阻止此用户继续转到 URL 的网站。</span><span class="sxs-lookup"><span data-stu-id="85659-117">This user will be blocked from proceeding to the URL's site.</span></span>

<span data-ttu-id="85659-118">如果发送链接的用户未受到 Office 365 ATP 的保护，他/她可以随意单击其计算机上的 URL 并解决问题网站。</span><span class="sxs-lookup"><span data-stu-id="85659-118">If the user who sent the link isn't protected by Office 365 ATP, he or she is free to click the URL on his or her machine and resolve the problem site.</span></span> <span data-ttu-id="85659-119">这样，管理员就不必知道受保护的用户是谁。</span><span class="sxs-lookup"><span data-stu-id="85659-119">This makes it doubly important for administrators to be aware of who their protected users are and should be.</span></span>

![工作组的安全链接页面报告恶意链接并阻止向页面传输。](/microsoft-365/media/TP_SafelinksForTeams_Malicious.png)

<span data-ttu-id="85659-121">在团队中单击此页 *上的 "返回"* 按钮将关闭 (，也可能导致空白页用户可以关闭) 。</span><span class="sxs-lookup"><span data-stu-id="85659-121">Clicking the *Go Back* button on this page in Teams will close it out (or may result in a blank page users  can close out).</span></span> <span data-ttu-id="85659-122">但是，再次单击链接将导致 reassessment 网站的声誉，从而再次出现此页面。</span><span class="sxs-lookup"><span data-stu-id="85659-122">However, clicking on the link again will result in reassessment of the reputation of the site so that this page reappears.</span></span>

> [!NOTE]
> <span data-ttu-id="85659-123">某些 Microsoft 365 管理员将启用阻止页面上的 " **继续** " 的消息。</span><span class="sxs-lookup"><span data-stu-id="85659-123">Some Microsoft 365 admins will enable the **Continue Anyway** message on the blocking page.</span></span> <span data-ttu-id="85659-124">但是，如果安全链接测量网站的声誉并发现缺少它，则不应进一步单击。</span><span class="sxs-lookup"><span data-stu-id="85659-124">However, if Safe Links measures the reputation of a site and finds it lacking, no further click-through should be undertaken.</span></span> <span data-ttu-id="85659-125">不建议用户绕过安全措施。</span><span class="sxs-lookup"><span data-stu-id="85659-125">It is not recommended that users bypass safety measures.</span></span> <span data-ttu-id="85659-126">请将其与你的注意事项进行权衡，然后再启用 "继续"。</span><span class="sxs-lookup"><span data-stu-id="85659-126">Please weigh this into your considerations before enabling Continue Anyway.</span></span>
