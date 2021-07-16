---
title: 将Microsoft Teams与 Canvas 一同使用
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: sovaish
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 将Microsoft Teams与 Canvas 集成
ms.openlocfilehash: e8ab45de84fe8325f6d5b349deb96aa831d54e36
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454681"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="c8f5f-103">将Microsoft Teams与 Canvas 一同使用</span><span class="sxs-lookup"><span data-stu-id="c8f5f-103">Use Microsoft Teams classes with Canvas</span></span>

<span data-ttu-id="c8f5f-104">Microsoft Teams课程是 Learning Tools Interoperability (LTI) 应用，可帮助教师和学生轻松地在 Learning Management System (LMS) 和 Teams 之间导航。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-104">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="c8f5f-105">用户可以直接从 LMS 中访问与其课程关联的课堂团队。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="prerequisites-before-deployment"></a><span data-ttu-id="c8f5f-106">部署前的先决条件</span><span class="sxs-lookup"><span data-stu-id="c8f5f-106">Prerequisites Before Deployment</span></span>

> [!NOTE]
> <span data-ttu-id="c8f5f-107">当前的 Class Teams LTI 仅支持将 Canvas 用户与 Microsoft Azure Active Directory (AAD) 在有限范围内同步。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-107">The current Class Teams LTI only supports syncing Canvas users with Microsoft Azure Active Directory (AAD) in a limited scope.</span></span> 
> - <span data-ttu-id="c8f5f-108">你的租户必须在 Canvas 字段与 Microsoft AAD (电子邮件、用户 ID 或 SIS ID) UPN 之间完全匹配。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-108">Your tenant must have an exact match between a Canvas field (email, user ID, or SIS ID) and the UPN in Microsoft AAD.</span></span> <span data-ttu-id="c8f5f-109">我们正在努力扩展同步功能的灵活性，但与此同时，Canvas 中与 AAD 中的 UPN 不匹配的任何用户将不会添加到与 Canvas 同步的 Teams 类。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-109">We are working to expand flexibility to the syncing functionality, but in the meantime, any users in Canvas not matched to a UPN in AAD will not be added to the Teams class synced with Canvas.</span></span> 
> - <span data-ttu-id="c8f5f-110">只有一个 Microsoft 租户可用于在 Canvas 和 Microsoft 之间映射用户。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-110">Only a single Microsoft tenant can be used for mapping users between Canvas and Microsoft.</span></span>
> - <span data-ttu-id="c8f5f-111">在将 Class Teams LTI 之前，必须关闭 SDS，以避免重复组。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-111">You will have to turn off SDS before using the Class Teams LTI in order to avoid duplication of groups.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="c8f5f-112">Microsoft Office 365管理员</span><span class="sxs-lookup"><span data-stu-id="c8f5f-112">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="c8f5f-113">在内部结构 Canvas 中管理 Microsoft Teams 集成之前，必须让 Microsoft Azure 租户中的机构 Microsoft Office 365 管理员批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用，然后再完成 Canvas 管理员设置。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-113">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="c8f5f-114">登录到 Canvas。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-114">Sign in to Canvas.</span></span>

2. <span data-ttu-id="c8f5f-115">选择全局 **导航** 中的"管理员"链接，然后选择您的帐户。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-115">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="c8f5f-116">在管理员导航中 **，选择**"设置"链接，然后选择"**集成"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-116">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="c8f5f-117">通过Microsoft Teams启用"同步"。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-117">Enable Microsoft Teams Sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

5. <span data-ttu-id="c8f5f-119">输入你的 Microsoft 租户名称和登录属性。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-119">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="c8f5f-120">login 属性将用于将 Canvas 用户与用户Azure Active Directory关联。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-120">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

6. <span data-ttu-id="c8f5f-121">选择 **"完成设置** 更新"。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-121">Select **Update Settings** once done.</span></span>

7. <span data-ttu-id="c8f5f-122">若要批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用的访问权限，请选择"授予 **租户访问权限"** 链接。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-122">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="c8f5f-123">你将被重定向到 Microsoft 标识平台管理员同意终结点。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-123">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![权限](media/permissions.png)

8. <span data-ttu-id="c8f5f-125">选择 **接受**。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-125">Select **Accept**.</span></span>

## <a name="canvas-admin"></a><span data-ttu-id="c8f5f-126">Canvas 管理</span><span class="sxs-lookup"><span data-stu-id="c8f5f-126">Canvas Admin</span></span>

<span data-ttu-id="c8f5f-127">设置 Microsoft Teams LTI 1.3 集成。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-127">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="c8f5f-128">作为 Canvas 管理员，你需要在你的环境中添加Microsoft Teams类 LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-128">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="c8f5f-129">记下应用的 LTI 客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-129">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="c8f5f-130">Microsoft Teams类 - 170000000000570</span><span class="sxs-lookup"><span data-stu-id="c8f5f-130">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="c8f5f-131">访问 **管理员设置**  >  **应用**。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-131">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="c8f5f-132">选择 **+ 应用** 以添加Teams LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-132">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="c8f5f-134">为 **配置类型选择"** 按客户端 ID"。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-134">Select **By Client ID** for configuration type.</span></span>

   ![添加应用](media/add-app.png)

4. <span data-ttu-id="c8f5f-136">输入提供的客户端 ID，然后选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="c8f5f-136">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="c8f5f-137">你会注意到客户端 ID 的Microsoft Teams LTI 应用名称，用于确认。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-137">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="c8f5f-138">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-138">Select **Install**.</span></span>

   <span data-ttu-id="c8f5f-139">the Microsoft Teams classes LTI app will be added to the list of external apps.</span><span class="sxs-lookup"><span data-stu-id="c8f5f-139">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
   
## <a name="enabling-the-lti-app-for-canvas-courses"></a><span data-ttu-id="c8f5f-140">为 Canvas 课程启用 LTI 应用</span><span class="sxs-lookup"><span data-stu-id="c8f5f-140">Enabling the LTI app for Canvas courses</span></span>

<span data-ttu-id="c8f5f-141">若要在课程内使用 LTI 应用，Canvas 课程的讲师必须启用集成同步。每个课程必须由讲师启用，以创建相应的团队;没有用于团队创建的全球机制。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-141">To use the LTI app within a course, an instructor of the Canvas course must enable integrations sync. Each course must be enabled by an instructor for a corresponding team to be created; there is no global mechanism for teams creation.</span></span> <span data-ttu-id="c8f5f-142">这是为了防止创建不需要的团队的预防措施。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-142">This is designed as a precautionary measure to prevent unwanted teams from being created.</span></span>

<span data-ttu-id="c8f5f-143">请查阅教师文档，[](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)以针对每个课程启用 LTI 应用并完成集成设置。</span><span class="sxs-lookup"><span data-stu-id="c8f5f-143">Refer your instructors to the [educator documentation](https://support.microsoft.com/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI app for each course and completing the integration setup.</span></span>
