---
title: LTI 应用概述
ms.author: heidip
author: MicrosoftHeidi
manager: serdars
ms.reviewer: amitman, sovaish
ms.date: 06/15/2021
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- M365-modern-desktop
localization_priority: None
description: 了解 M365 中的 Learning Tools Interoperability (LTI) Office 应用，以及他们将 Office 应用集成到其 Learning Management System (LMS) 时如何帮助教师。
ms.openlocfilehash: 34956eac57a7e3af44ca1c8cf8ae2714327e3e96
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322337"
---
# <a name="integrating-microsoft-products-with-your-learning-management-system-lms"></a><span data-ttu-id="dd2e5-103">将 Microsoft 产品与 Learning Management System (LMS) </span><span class="sxs-lookup"><span data-stu-id="dd2e5-103">Integrating Microsoft products with your Learning Management System (LMS)</span></span>

> [!IMPORTANT]
> <span data-ttu-id="dd2e5-104">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="dd2e5-105">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

- [<span data-ttu-id="dd2e5-106">OneDriveLTI 与 Canvas</span><span class="sxs-lookup"><span data-stu-id="dd2e5-106">OneDrive LTI with Canvas</span></span>](#onedrive-lti-with-canvas)
- [<span data-ttu-id="dd2e5-107">Teams会议 LTI 与画布</span><span class="sxs-lookup"><span data-stu-id="dd2e5-107">Teams Meetings LTI with Canvas</span></span>](#teams-meetings-lti-with-canvas)
- [<span data-ttu-id="dd2e5-108">Teams类 LTI</span><span class="sxs-lookup"><span data-stu-id="dd2e5-108">Teams Classes LTI</span></span>](#teams-classes-lti)

<span data-ttu-id="dd2e5-109">Microsoft 教育部和第三方合作伙伴了解，教学和学习流程跨越了解决方案边界。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-109">Microsoft Education and our third-party partners understand that the flow of teaching and learning invariably crosses solution boundaries.</span></span> <span data-ttu-id="dd2e5-110">我们正在努力提供更加无缝的体验，让教师和教师专注于他们的目标，而不是必须拼接工具。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-110">We're working on providing more seamless experiences, keeping educators and learners focused on their goals, rather than having to juggle tools.</span></span> <span data-ttu-id="dd2e5-111">我们将在任何进行教学和学习的地方集成 Microsoft 产品，包括 LMS Learning Management Systems () 。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-111">We're integrating Microsoft products wherever teaching and learning occurs, including within and alongside Learning Management Systems (LMS).</span></span> <span data-ttu-id="dd2e5-112">我们已与 LMS 合作伙伴合作，使用[Learning Tools Interoperability (LTI) 标准](https://www.imsglobal.org/activity/learning-tools-interoperability)创建一套工具，将 Microsoft 的最佳功能直接引入 LMS。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-112">We've worked with our LMS partners to create a suite of tools using the [Learning Tools Interoperability (LTI) standard](https://www.imsglobal.org/activity/learning-tools-interoperability) that brings the best of Microsoft directly into your LMS.</span></span>

<span data-ttu-id="dd2e5-113">这些工具包括新的 OneDrive LTI 应用、新的 Teams 会议 LTI 应用和新的 Teams LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-113">These tools include a new OneDrive LTI app, a new Teams Meetings LTI app, and a new Class Teams LTI app.</span></span> <span data-ttu-id="dd2e5-114">这些新工具高度安全，与 LTI 1.3 和 LTI 优势标准完全兼容。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-114">These new tools are highly secure and fully compatible with LTI 1.3 and LTI Advantage standards.</span></span> <span data-ttu-id="dd2e5-115">使用 OneDrive LTI 应用，教师和学生可以直接将OneDrive云存储和Office 365文件引入 LMS 中的作业和内容创建工作流。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-115">The OneDrive LTI app allows educators and students to bring OneDrive cloud storage and Office 365 files directly into assignment and content creation workflows within an LMS.</span></span> <span data-ttu-id="dd2e5-116">通过Teams会议 LTI 应用，教师和学生可以管理、安排和访问其 Teams 会议，这些会议位于 LMS 的会议中心内。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-116">The Teams Meetings LTI app allows educators and students to manage, schedule, and access their Teams Meetings from within a meetings hub in their LMS.</span></span> <span data-ttu-id="dd2e5-117">课堂Teams LTI 应用允许教师使用 LMS 课程名单和每日名单更新，在其 LMS 内为课程创建团队。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-117">The Class Teams LTI app allows educators to create a team for their course within their LMS using the LMS course roster with daily roster updates.</span></span> <span data-ttu-id="dd2e5-118">然后，学生可以从 LMS 内访问团队。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-118">Students can then access the team right from within the LMS.</span></span> <span data-ttu-id="dd2e5-119">我们很高兴将这些新工具引入客户，并根据你的反馈继续改进我们的解决方案。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-119">We are excited to bring these new tools to customers and continue to improve our solutions according to your feedback.</span></span>

## <a name="onedrive-lti-with-canvas"></a><span data-ttu-id="dd2e5-120">OneDriveLTI 与 Canvas</span><span class="sxs-lookup"><span data-stu-id="dd2e5-120">OneDrive LTI with Canvas</span></span>

<span data-ttu-id="dd2e5-121">详细了解如何对 LMS Microsoft OneDrive使用 Learning Management System () 。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-121">Learn more about using Microsoft OneDrive with your Learning Management System (LMS).</span></span>

- <span data-ttu-id="dd2e5-122">**将Microsoft Office 365直接引入工作流**</span><span class="sxs-lookup"><span data-stu-id="dd2e5-122">**Brings Microsoft Office 365 directly into your workflows**</span></span>

<span data-ttu-id="dd2e5-123">该Microsoft OneDrive LTI 应用与 LMS 集成，Microsoft OneDrive Microsoft Office 365集成到最重要的工作流中，包括：</span><span class="sxs-lookup"><span data-stu-id="dd2e5-123">The Microsoft OneDrive LTI app integrates with your LMS to bring Microsoft OneDrive and Microsoft Office 365 directly into your most important workflows that include:</span></span>

- <span data-ttu-id="dd2e5-124">附加资源并组织内容。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-124">Attaching resources and organizing content.</span></span>
- <span data-ttu-id="dd2e5-125">启动协作文档。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-125">Starting collaborative documents.</span></span>
- <span data-ttu-id="dd2e5-126">创建工作分配并评分。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-126">Creating and grading assignments.</span></span>

- <span data-ttu-id="dd2e5-127">**安全且完全符合最新的 LTI 标准**</span><span class="sxs-lookup"><span data-stu-id="dd2e5-127">**Secure and fully compliant with latest LTI standards**</span></span>

<span data-ttu-id="dd2e5-128">该Microsoft OneDrive LTI 应用与 LTI 1.3 和 LTI 优势兼容。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-128">The Microsoft OneDrive LTI App is compatible with LTI 1.3 and LTI Advantage.</span></span> <span data-ttu-id="dd2e5-129">此优势可实现高度安全且紧密集成的用户体验。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-129">This advantage allows for a highly secure and tightly integrated user experience.</span></span>

- <span data-ttu-id="dd2e5-130">**新式和丰富用户体验**</span><span class="sxs-lookup"><span data-stu-id="dd2e5-130">**Modern and Rich User Experience**</span></span>

<span data-ttu-id="dd2e5-131">MICROSOFT ONEDRIVE LTI 应用将 Microsoft 的最佳功能融入到你的 LMS 体验中。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-131">The Microsoft OneDrive LTI App brings the best of Microsoft right into your LMS experience.</span></span> <span data-ttu-id="dd2e5-132">我们正在改进 LMS 中现有的 Office 365 集成，提供更现代用户体验，包括新的扩展 Microsoft OneDrive 文件选取器以及更丰富的 Office 文件编辑体验。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-132">We're improving upon the existing Office 365 integration in your LMS by delivering a more modern user experience, complete with a new and expanded Microsoft OneDrive file picker and richer editing experiences for Office files.</span></span> <span data-ttu-id="dd2e5-133">Microsoft 还将完全拥有 Microsoft OneDrive LTI 应用，这意味着你始终自动获得最新且最最好的 LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-133">Microsoft will also fully own the Microsoft OneDrive LTI App going forward, which means you’ll always get the latest and greatest from Microsoft automatically.</span></span>

<span data-ttu-id="dd2e5-134">使用 Microsoft OneDrive LTI 应用，你可以：</span><span class="sxs-lookup"><span data-stu-id="dd2e5-134">The Microsoft OneDrive LTI App allows you to:</span></span>

- <span data-ttu-id="dd2e5-135">从Office 365内容编辑器附加 PowerPoint 文件，PowerPoint Excel演示文稿和文档。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-135">Attach Office 365 files including Word documents, PowerPoint presentations, and Excel from the Rich Content Editor.</span></span>
- <span data-ttu-id="dd2e5-136">分配Office 365分配。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-136">Distribute Office 365 cloud assignments.</span></span>
- <span data-ttu-id="dd2e5-137">查看和组织你的个人和课程Microsoft OneDrive文件。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-137">View and organize your personal and course Microsoft OneDrive files.</span></span>
- <span data-ttu-id="dd2e5-138">创建协作，课程成员可以实时协作处理共享文档。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-138">Create collaborations where course members can work together on shared documents in real time.</span></span>
- <span data-ttu-id="dd2e5-139">访问多个Microsoft OneDrive帐户，包括个人帐户和学校帐户。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-139">Access multiple Microsoft OneDrive accounts, including personal and school accounts.</span></span>
- <span data-ttu-id="dd2e5-140">将Office 365文件与课程模块集成。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-140">Integrate Office 365 files with your course modules.</span></span>
- <span data-ttu-id="dd2e5-141">使用 Microsoft 帐户对 LMS 进行单一登录。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-141">Use your Microsoft account for single sign-on with your LMS.</span></span>

<span data-ttu-id="dd2e5-142">有关配置步骤，请参阅将[Microsoft OneDrive LTI 与 Canvas 一同使用](use-onedrive-with-lms.md)。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-142">For configuration steps, see [Use Microsoft OneDrive LTI with Canvas](use-onedrive-with-lms.md).</span></span>

## <a name="teams-lti-apps"></a><span data-ttu-id="dd2e5-143">TeamsLTI 应用</span><span class="sxs-lookup"><span data-stu-id="dd2e5-143">Teams LTI apps</span></span>

### <a name="teams-meetings-lti-with-canvas"></a><span data-ttu-id="dd2e5-144">Teams会议 LTI 与画布</span><span class="sxs-lookup"><span data-stu-id="dd2e5-144">Teams Meetings LTI with Canvas</span></span>

<span data-ttu-id="dd2e5-145">Microsoft Teams会议 LTI 应用可帮助管理员将Teams合并到教育机构的 LMS 课程。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-145">Microsoft Teams meetings LTI app helps admins incorporate Teams meetings into their educational institution's LMS course.</span></span> <span data-ttu-id="dd2e5-146">教师和学生可以查看过去和即将召开的会议、安排个人或定期会议，以及加入与课程相关的团队会议，所有这些都来自 LMS。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-146">Educators and students can view past and upcoming meetings, schedule individual or recurring meetings, and join team meetings related to the course, all from within their LMS.</span></span>

<span data-ttu-id="dd2e5-147">有关配置步骤，请参阅使用[Microsoft Teams Canvas 会议](teams-meetings-with-canvas.md)。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-147">For configuration steps, see [Use Microsoft Teams meetings with Canvas](teams-meetings-with-canvas.md).</span></span>

### <a name="teams-classes-lti"></a><span data-ttu-id="dd2e5-148">Teams类 LTI</span><span class="sxs-lookup"><span data-stu-id="dd2e5-148">Teams Classes LTI</span></span>

<span data-ttu-id="dd2e5-149">学习Microsoft Teams LTI 应用可帮助教师和学生在 LMS 和 Teams。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-149">The Microsoft Teams classes LTI app helps educators and students navigate between their LMS and Teams.</span></span> <span data-ttu-id="dd2e5-150">用户可以直接从 LMS 中访问与其课程关联的课堂团队。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-150">Users can access their class teams associated with their course directly from within their LMS.</span></span> <span data-ttu-id="dd2e5-151">你可以找到下面的配置步骤：</span><span class="sxs-lookup"><span data-stu-id="dd2e5-151">You can find configuration steps below:</span></span>

- <span data-ttu-id="dd2e5-152">**Teams类 LTI 与 Canvas** [一Microsoft Teams使用 Canvas 类](teams-classes-with-canvas.md)。</span><span class="sxs-lookup"><span data-stu-id="dd2e5-152">**Teams Classes LTI with Canvas** [Use Microsoft Teams classes with Canvas](teams-classes-with-canvas.md).</span></span>

- <span data-ttu-id="dd2e5-153">**Teams类 LTI with 使用具有 Microsoft Teams** [Learn 超的类](teams-classes-with-blackboard.md)</span><span class="sxs-lookup"><span data-stu-id="dd2e5-153">**Teams Classes LTI with Blackboard** [Use Microsoft Teams classes with Blackboard Learn Ultra](teams-classes-with-blackboard.md)</span></span>
