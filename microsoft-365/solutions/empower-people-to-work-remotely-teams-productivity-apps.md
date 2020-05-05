---
title: 4. 部署远程工作者生产力应用和服务
f1.keywords:
- NOCSH
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 05/01/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- remotework
ms.custom:
- M365solutions
description: 使用户可通过 Teams、Exchange、SharePoint 和其他 Microsoft 365 服务高效工作。
ms.openlocfilehash: dddc3cac8a6cb955e8a337eed07279ba75c029aa
ms.sourcegitcommit: 101084f9c81616342d78493232d8f13f5ffa4ddf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/01/2020
ms.locfileid: "44002588"
---
# <a name="4-deploy-remote-worker-productivity-apps-and-services"></a><span data-ttu-id="0bd42-103">4. 部署远程工作者生产力应用和服务</span><span class="sxs-lookup"><span data-stu-id="0bd42-103">4. Deploy remote worker productivity apps and services</span></span>

<span data-ttu-id="0bd42-104">为了提高工作效率，人们需要相互沟通和协作。</span><span class="sxs-lookup"><span data-stu-id="0bd42-104">To be productive, people need to communicate and collaborate with one another.</span></span> <span data-ttu-id="0bd42-105">他们需要举行会议、通过语音和文本聊天、创建新内容、共享信息和文件、进行电子邮件往来以及管理日历和任务。</span><span class="sxs-lookup"><span data-stu-id="0bd42-105">They need to meet, chat by voice and text, create new content and share information and files, exchange email, and manage calendars and tasks.</span></span> <span data-ttu-id="0bd42-106">Microsoft 365 提供基于云的服务来实现所有这些关键功能：</span><span class="sxs-lookup"><span data-stu-id="0bd42-106">Microsoft 365 provides cloud-based services for all of these key functions:</span></span>

- <span data-ttu-id="0bd42-107">要使用户在远程工作的同时保持连接，请使用 Microsoft Teams，它为组织、部门、小型团队和个人提供用于会议、聊天和文件存储的通用通信中心。</span><span class="sxs-lookup"><span data-stu-id="0bd42-107">To keep people connected while they work apart, use Microsoft Teams, which provides a common hub of communication for meetings, chats, and file storage for the organization, departments, and for small teams and individuals.</span></span> 
- <span data-ttu-id="0bd42-108">要进行电子邮件往来和管理日历、联系人和任务，请使用 Exchange Online 和 Outlook 客户端。</span><span class="sxs-lookup"><span data-stu-id="0bd42-108">For exchanging email and managing calendars, contacts, and tasks, use Exchange Online and the Outlook client.</span></span>
- <span data-ttu-id="0bd42-109">要存储和协作处理文件，请使用 SharePoint 和 OneDrive。</span><span class="sxs-lookup"><span data-stu-id="0bd42-109">For storing and collaborating on files, use SharePoint and OneDrive.</span></span> <span data-ttu-id="0bd42-110">可通过 Web 浏览器或在 Teams 内部使用它们。</span><span class="sxs-lookup"><span data-stu-id="0bd42-110">You can use them with a web browser or within Teams.</span></span>
- <span data-ttu-id="0bd42-111">要创建新内容或协作处理现有内容，请使用 Microsoft 365 应用，它是安装在本地计算机上的 Word、PowerPoint、Excel 和 Outlook 的版本，并能持续接收功能和安全更新。</span><span class="sxs-lookup"><span data-stu-id="0bd42-111">For creating new content or collaborating on existing content, Microsoft 365 Apps are versions of Word, PowerPoint, Excel, and Outlook that are installed on your local computer and receive ongoing feature and security updates.</span></span>

## <a name="keep-people-connected-with-microsoft-teams"></a><span data-ttu-id="0bd42-112">通过 Microsoft Teams 让人们保持联系</span><span class="sxs-lookup"><span data-stu-id="0bd42-112">Keep people connected with Microsoft Teams</span></span>

<span data-ttu-id="0bd42-113">Teams 让你可以在一个位置聊天、开会、呼叫和协作。</span><span class="sxs-lookup"><span data-stu-id="0bd42-113">Teams allows you to chat, meet, call, and collaborate all in one place.</span></span> <span data-ttu-id="0bd42-114">数百万人每天在 Teams 中完成自己的工作，因为它能将远程工作所需的所有内容整合到一个中心，以进行团队合作。</span><span class="sxs-lookup"><span data-stu-id="0bd42-114">Millions of people get their work done in Teams every day because it brings together everything you need to work remotely into a hub for teamwork.</span></span> 

<span data-ttu-id="0bd42-115">可使用[本文](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams)获得通过 Teams 为远程工作者提供支持的指南。</span><span class="sxs-lookup"><span data-stu-id="0bd42-115">You can use [this article](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams) for guidance on supporting your remote workers with Teams.</span></span> 

### <a name="chat-and-conversations"></a><span data-ttu-id="0bd42-116">聊天和对话</span><span class="sxs-lookup"><span data-stu-id="0bd42-116">Chat and conversations</span></span>

<span data-ttu-id="0bd42-117">聊天和按线索组织的对话是 Teams 的中心，支持单个一对一聊天以及群组聊天和对话。</span><span class="sxs-lookup"><span data-stu-id="0bd42-117">Chat and threaded conversations are at the center of Teams with support for individual 1:1 chats and group chats and conversations.</span></span> <span data-ttu-id="0bd42-118">远程工作者可以通过在群组聊天或一对一邮件中使用 gif、贴纸和表情符号来共享信息、意见和个性。</span><span class="sxs-lookup"><span data-stu-id="0bd42-118">Remote workers can share information, opinions, and personality by using gifs, stickers, and emojis in group chats or one-to-one messages.</span></span>

### <a name="meetings-and-conferencing"></a><span data-ttu-id="0bd42-119">会议和电话会议</span><span class="sxs-lookup"><span data-stu-id="0bd42-119">Meetings and conferencing</span></span> 

<span data-ttu-id="0bd42-120">Teams 无疑有助于维护与远程工作者之间的通信和信息共享，尤其是在支持多达 250 人的会议中。</span><span class="sxs-lookup"><span data-stu-id="0bd42-120">Teams can certainly help maintain communications and information sharing with remote workers, especially with meetings that support up to 250 people.</span></span> <span data-ttu-id="0bd42-121">Teams 会议可实现与组织内外部人员的交互式协作会议。</span><span class="sxs-lookup"><span data-stu-id="0bd42-121">Teams meetings enable interactive, collaborative meetings with people inside and outside your organization.</span></span> <span data-ttu-id="0bd42-122">远程工作者可使用 Teams 会议进行日常活动，包括设置定期项目检查点、追赶同事进度、讨论会话和促进与客户的对话。</span><span class="sxs-lookup"><span data-stu-id="0bd42-122">Remote workers can use Teams meetings for day-to-day activities including recurring project checkpoints, catching-up with colleagues, brainstorming sessions, and facilitating conversations with customers.</span></span> 

### <a name="calling"></a><span data-ttu-id="0bd42-123">通话</span><span class="sxs-lookup"><span data-stu-id="0bd42-123">Calling</span></span>

<span data-ttu-id="0bd42-124">Teams 支持在用户，甚至是使用联合身份验证的其他组织之间直接进行 VoIP 呼叫。</span><span class="sxs-lookup"><span data-stu-id="0bd42-124">Teams supports direct VoIP calling between users and even other organizations using federation.</span></span> <span data-ttu-id="0bd42-125">它使用与会议相同的编解码器，在全球范围内提供出色的音频，无需额外的 PSTN 费用。</span><span class="sxs-lookup"><span data-stu-id="0bd42-125">It uses the same codecs as meetings and provide great audio world-wide without additional PSTN charges.</span></span> <span data-ttu-id="0bd42-126">但是，某些用户可能需要在远程工作时使用专用的电话号码进行外部呼叫。</span><span class="sxs-lookup"><span data-stu-id="0bd42-126">However, some users may need a dedicated phone number to take external calls when working remotely.</span></span> <span data-ttu-id="0bd42-127">Teams 可以为这些用户快速提供云电话服务，以便其拨打和接听电话。</span><span class="sxs-lookup"><span data-stu-id="0bd42-127">Teams can quickly provide cloud phone service for these users to make and receive phone calls.</span></span>

### <a name="apps-and-workflows"></a><span data-ttu-id="0bd42-128">应用和工作流</span><span class="sxs-lookup"><span data-stu-id="0bd42-128">Apps and workflows</span></span>

<span data-ttu-id="0bd42-129">Teams 提供了一个可从桌面版、Web 版和移动版 Teams 访问应用和工作流的平台。</span><span class="sxs-lookup"><span data-stu-id="0bd42-129">Teams provides a platform for apps and workflows that can be accessed from the desktop, web, and mobile versions of Teams.</span></span> <span data-ttu-id="0bd42-130">Teams 提供了数百个由 Microsoft 和第三方发布的应用来吸引用户、支持高效工作，并在 Teams 中集成了常用的业务服务。</span><span class="sxs-lookup"><span data-stu-id="0bd42-130">Teams provides hundreds of apps published by Microsoft and by third parties to engage users, support productivity, and integrate commonly used business services into Teams.</span></span> <span data-ttu-id="0bd42-131">用户和管理员还可以使用低代码 Power Apps 和 Power Automate 开发工具为 Teams 创建自定义应用和自动化工作流。</span><span class="sxs-lookup"><span data-stu-id="0bd42-131">Users and Admins can also create custom apps and automated workflows for Teams using the low-code Power Apps and Power Automate development tools.</span></span>

<span data-ttu-id="0bd42-132">应用和工作流可通过收集和共享关键信息、自动化重复性任务以及允许远程工作者与交互式机器人聊天来提高他们在 Teams 中的工作效率。</span><span class="sxs-lookup"><span data-stu-id="0bd42-132">Apps and workflows let remote workers be more productive in Teams, by collecting and sharing critical information, automating repetitive tasks, and allowing them to chat with interactive bot.</span></span> <span data-ttu-id="0bd42-133">将应用固定到频道或 Teams 应用栏是使用户在相关空间轻松访问这些应用的好方法，管理员可以固定应用，以促进对每个用户应使用的应用程序的认识和采纳。</span><span class="sxs-lookup"><span data-stu-id="0bd42-133">Pinning apps to a channel or the Teams app bar is a great way for users to make these apps easily accessible in a relevant space, and admins can pin apps to drive awareness and adoption of the apps that everyone should be using.</span></span>

## <a name="exchange-email-and-manage-calendars-contacts-and-tasks-with-exchange-online-and-outlook"></a><span data-ttu-id="0bd42-134">使用 Exchange Online 和 Outlook 进行电子邮件往来和管理日历、联系人和任务</span><span class="sxs-lookup"><span data-stu-id="0bd42-134">Exchange email and manage calendars, contacts, and tasks with Exchange Online and Outlook</span></span>

<span data-ttu-id="0bd42-135">借助 Outlook，远程工作者可以在同一位置通过电子邮件、日历、联系人、任务等保持联系，并且有条不紊。</span><span class="sxs-lookup"><span data-stu-id="0bd42-135">With Outlook, remote workers can stay connected and organized with email, calendars, contacts, tasks, and more—together in one place.</span></span> <span data-ttu-id="0bd42-136">Outlook 可帮助你根据与你相关的内容，随时跟踪日常工作并确定其优先级。</span><span class="sxs-lookup"><span data-stu-id="0bd42-136">Outlook helps you stay on track and prioritize your day based on what’s relevant to you.</span></span> <span data-ttu-id="0bd42-137">通过 Outlook，你能够直接从 OneDrive 共享附件、计划和加入 Teams 会议、查看和共享日历，以及向其他人提供委派权限。</span><span class="sxs-lookup"><span data-stu-id="0bd42-137">Outlook enables you to share attachments right from OneDrive, plan and join Teams meetings, view and share calendars, and provide delegate permissions to others.</span></span> <span data-ttu-id="0bd42-138">了解工作和个人承诺方面的后续发展以及需要关注的内容可以帮助远程工作者专注于重要事项。</span><span class="sxs-lookup"><span data-stu-id="0bd42-138">Knowing what’s coming up next across both work and personal commitments and what needs attention can help remote workers focus on what matters.</span></span> <span data-ttu-id="0bd42-139">Outlook 为远程工作者提供了有用的方式来管理其时间和查找所需内容（包括文件、组织中的人员等）。</span><span class="sxs-lookup"><span data-stu-id="0bd42-139">Outlook provides helpful ways for remote workers to manage their time and to find what they need easily, including files, people in the organization, and more.</span></span> 

## <a name="store-and-collaborate-on-files-with-sharepoint-online-and-onedrive"></a><span data-ttu-id="0bd42-140">使用 SharePoint Online 和 OneDrive 存储和协作处理文件</span><span class="sxs-lookup"><span data-stu-id="0bd42-140">Store and collaborate on files with SharePoint Online and OneDrive</span></span>

<span data-ttu-id="0bd42-141">对于内容协作，远程工作者可将 SharePoint Online 和 OneDrive 文件夹用作云中的中心位置，以便存储和共享文件、共同创作、通信和协作。</span><span class="sxs-lookup"><span data-stu-id="0bd42-141">For content collaboration, remote workers can use SharePoint Online and OneDrive folders as a central place in the cloud to store and share files, co-author, communicate, and collaborate.</span></span> <span data-ttu-id="0bd42-142">远程工作者可通过 Web 浏览器、Teams 和 Office 应用从任意位置安全地进行工作。</span><span class="sxs-lookup"><span data-stu-id="0bd42-142">Remote workers can securely work from anywhere from a web browser, from Teams, and from Office apps.</span></span>

## <a name="create-and-collaborate-on-content-with-microsoft-365-apps"></a><span data-ttu-id="0bd42-143">使用 Microsoft 365 应用创建和协作处理内容</span><span class="sxs-lookup"><span data-stu-id="0bd42-143">Create and collaborate on content with Microsoft 365 Apps</span></span>

<span data-ttu-id="0bd42-144">Microsoft 365 应用是适用于企业的最高效、最安全的 Office 体验，可让用户随时随地无缝协同工作。</span><span class="sxs-lookup"><span data-stu-id="0bd42-144">Microsoft 365 Apps is the most productive and most secure Office experience for enterprises, allowing people to work together seamlessly from anywhere, anytime.</span></span> <span data-ttu-id="0bd42-145">远程工作者可与多人同时协作处理文档、实时查看编辑和更改，以及在任何便携式电脑、电脑或移动设备上与其他人共同创作。</span><span class="sxs-lookup"><span data-stu-id="0bd42-145">Remote workers can collaborate on a document with multiple people simultaneously, see edits and changes in real time, and coauthor with others on any laptop, PC, or mobile device.</span></span>

## <a name="admin-technical-resources-for-productivity-apps-and-services"></a><span data-ttu-id="0bd42-146">面向生产力应用和服务的管理员技术资源</span><span class="sxs-lookup"><span data-stu-id="0bd42-146">Admin technical resources for productivity apps and services</span></span>

- [<span data-ttu-id="0bd42-147">使用 Microsoft Teams 支持远程工作者</span><span class="sxs-lookup"><span data-stu-id="0bd42-147">Support remote workers using Microsoft Teams</span></span>](https://docs.microsoft.com/microsoftteams/support-remote-work-with-teams)
- [<span data-ttu-id="0bd42-148">Teams 客户成功工具包下载</span><span class="sxs-lookup"><span data-stu-id="0bd42-148">Teams Customer Success Kit download</span></span>](https://www.microsoft.com/download/details.aspx?id=54244)
- [<span data-ttu-id="0bd42-149">用于促进 Teams 采用的工具</span><span class="sxs-lookup"><span data-stu-id="0bd42-149">Tools for driving Teams adoption</span></span>](https://docs.microsoft.com/microsoftteams/adopt-tools-and-downloads) 
- [<span data-ttu-id="0bd42-150">为 Microsoft Teams 创建变更管理策略</span><span class="sxs-lookup"><span data-stu-id="0bd42-150">Create a change management strategy for Microsoft Teams</span></span>](https://docs.microsoft.com/MicrosoftTeams/change-management-strategy)
- [<span data-ttu-id="0bd42-151">部署具有三层保护的 Teams</span><span class="sxs-lookup"><span data-stu-id="0bd42-151">Teams with three tiers of protection</span></span>](configure-teams-three-tiers-protection.md)

- [<span data-ttu-id="0bd42-152">对用户进行 Office 和 Office 365 方面的培训</span><span class="sxs-lookup"><span data-stu-id="0bd42-152">Train your users on Office and Office 365</span></span>](https://support.office.com/article/train-your-users-on-office-and-microsoft-365-7cba3c97-7f19-46ed-a1c6-763971a26c2)
- [<span data-ttu-id="0bd42-153">使用 Office 网页版</span><span class="sxs-lookup"><span data-stu-id="0bd42-153">Use Office for the web</span></span>](https://support.microsoft.com/office/get-started-with-office-for-the-web-in-microsoft-365-5622c7c9-721d-4b3d-8cb9-a7276c2470e5)

## <a name="next-step"></a><span data-ttu-id="0bd42-154">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0bd42-154">Next step</span></span>

<span data-ttu-id="0bd42-155">继续执行[步骤 5](empower-people-to-work-remotely-communication-venues.md)，创建可满足 COVID-19 危机独特需求的其他交流平台。</span><span class="sxs-lookup"><span data-stu-id="0bd42-155">Continue with [Step 5](empower-people-to-work-remotely-communication-venues.md) to create additional communication venues that serve the unique requirements of the COVID-19 crisis.</span></span>
