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
ms.openlocfilehash: 54dd3cc2709933ffb7b7d5fecdd181fad2abb42b
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454669"
---
# <a name="use-microsoft-teams-meetings-with-canvas"></a><span data-ttu-id="609d9-103">将Microsoft Teams与 Canvas 一同使用</span><span class="sxs-lookup"><span data-stu-id="609d9-103">Use Microsoft Teams meetings with Canvas</span></span>

<span data-ttu-id="609d9-104">Microsoft Teams会议是 Learning Tools Interoperability (LTI) 应用，可帮助教师和学生轻松地在 Learning Management System (LMS) 和 Teams 之间导航。</span><span class="sxs-lookup"><span data-stu-id="609d9-104">Microsoft Teams meetings is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="609d9-105">用户可以直接从 LMS 中访问与其课程关联的课堂团队。</span><span class="sxs-lookup"><span data-stu-id="609d9-105">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="609d9-106">Microsoft Office 365管理员</span><span class="sxs-lookup"><span data-stu-id="609d9-106">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="609d9-107">在内部结构 Canvas 中管理 Microsoft Teams 集成之前，必须让 Microsoft Azure 租户中的机构 Microsoft Office 365 管理员批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用，然后再完成 Canvas 管理员设置。</span><span class="sxs-lookup"><span data-stu-id="609d9-107">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="609d9-108">登录到 Canvas。</span><span class="sxs-lookup"><span data-stu-id="609d9-108">Sign in to Canvas.</span></span>

2. <span data-ttu-id="609d9-109">选择全局 **导航** 中的"管理员"链接，然后选择您的帐户。</span><span class="sxs-lookup"><span data-stu-id="609d9-109">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="609d9-110">在管理员导航中 **，选择**"设置"链接，然后选择"**集成"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="609d9-110">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span>

4. <span data-ttu-id="609d9-111">输入你的 Microsoft 租户名称和登录属性。</span><span class="sxs-lookup"><span data-stu-id="609d9-111">Enter your Microsoft tenant name and login attribute.</span></span>

   <span data-ttu-id="609d9-112">login 属性将用于将 Canvas 用户与用户Azure Active Directory关联。</span><span class="sxs-lookup"><span data-stu-id="609d9-112">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span>

5. <span data-ttu-id="609d9-113">选择 **"完成设置** 更新"。</span><span class="sxs-lookup"><span data-stu-id="609d9-113">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="609d9-114">若要批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用的访问权限，请选择"授予 **租户访问权限"** 链接。</span><span class="sxs-lookup"><span data-stu-id="609d9-114">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="609d9-115">你将被重定向到 Microsoft 标识平台管理员同意终结点。</span><span class="sxs-lookup"><span data-stu-id="609d9-115">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![权限](media/permissions.png)

7. <span data-ttu-id="609d9-117">选择 **接受**。</span><span class="sxs-lookup"><span data-stu-id="609d9-117">Select **Accept**.</span></span>

8. <span data-ttu-id="609d9-118">通过打开Microsoft Teams启用同步。</span><span class="sxs-lookup"><span data-stu-id="609d9-118">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="609d9-120">Canvas 管理</span><span class="sxs-lookup"><span data-stu-id="609d9-120">Canvas Admin</span></span>

<span data-ttu-id="609d9-121">设置 Microsoft Teams LTI 1.3 集成。</span><span class="sxs-lookup"><span data-stu-id="609d9-121">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="609d9-122">作为 Canvas 管理员，你需要在你的环境中Microsoft Teams会议 LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="609d9-122">As a Canvas Admin, you'll need to add the Microsoft Teams meetings LTI app within your environment.</span></span> <span data-ttu-id="609d9-123">记下应用的 LTI 客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="609d9-123">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="609d9-124">Microsoft Teams会议 - 170000000000703</span><span class="sxs-lookup"><span data-stu-id="609d9-124">Microsoft Teams meetings - 170000000000703</span></span>

1. <span data-ttu-id="609d9-125">访问 **管理员设置**  >  **应用**。</span><span class="sxs-lookup"><span data-stu-id="609d9-125">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="609d9-126">选择 **+ 应用** 以添加Teams LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="609d9-126">Select **+ App** to add the Teams LTI apps.</span></span>

   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="609d9-128">为 **配置类型选择"** 按客户端 ID"。</span><span class="sxs-lookup"><span data-stu-id="609d9-128">Select **By Client ID** for configuration type.</span></span>

   ![添加应用](media/add-app.png)

4. <span data-ttu-id="609d9-130">输入提供的客户端 ID，然后选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="609d9-130">Enter the Client ID provided, and then select **Submit**.</span></span>

   <span data-ttu-id="609d9-131">你将注意到客户端 ID Microsoft Teams会议 LTI 应用名称进行确认。</span><span class="sxs-lookup"><span data-stu-id="609d9-131">You'll notice the Microsoft Teams meetings LTI app name for the Client ID for confirmation.</span></span>

5. <span data-ttu-id="609d9-132">选择“安装”。</span><span class="sxs-lookup"><span data-stu-id="609d9-132">Select **Install**.</span></span>

   <span data-ttu-id="609d9-133">the Microsoft Teams meetings LTI app will be added to the list of external apps.</span><span class="sxs-lookup"><span data-stu-id="609d9-133">The Microsoft Teams meetings LTI app will be added to the list of external apps.</span></span>
   
## <a name="enable-for-canvas-courses"></a><span data-ttu-id="609d9-134">启用画布课程</span><span class="sxs-lookup"><span data-stu-id="609d9-134">Enable for Canvas Courses</span></span>

<span data-ttu-id="609d9-135">若要在课程内使用 LTI，Canvas 课程的讲师必须启用集成同步。每个课程必须由讲师启用，以创建Teams课程;没有用于创建全局Teams机制。</span><span class="sxs-lookup"><span data-stu-id="609d9-135">In order to use the LTI within a course, an instructor of the Canvas course must enable the integrations sync. Each course must be enabled by an instructor for a corresponding Teams to be created; there is no global mechanism for Teams creation.</span></span> <span data-ttu-id="609d9-136">这是为防止创建不需要Teams设计。</span><span class="sxs-lookup"><span data-stu-id="609d9-136">This is designed out of caution to prevent unwanted Teams being created.</span></span>

<span data-ttu-id="609d9-137">请参考教师文档，以[](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas)针对每个课程启用 LTI 并完成集成设置。</span><span class="sxs-lookup"><span data-stu-id="609d9-137">Please refer your instructors to [educator documentation](https://support.microsoft.com/en-us/topic/use-microsoft-teams-classes-in-your-lms-preview-ac6a1e34-32f7-45e6-b83e-094185a1e78a#ID0EBD=Instructure_Canvas) for enabling the LTI for each course and finishing the integration setup.</span></span>
