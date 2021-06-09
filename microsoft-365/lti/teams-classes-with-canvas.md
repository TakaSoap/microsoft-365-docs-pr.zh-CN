---
title: 将Microsoft Teams与 Canvas 一同使用
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 将Microsoft Teams与 Canvas 集成
ms.openlocfilehash: 1a16d6a4f5e0cfbb592c335163bb4e33fd3c1301
ms.sourcegitcommit: 50908a93554290ff1157b58d0a868a33e012513c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/08/2021
ms.locfileid: "52821869"
---
# <a name="use-microsoft-teams-classes-with-canvas"></a><span data-ttu-id="7ab53-103">将Microsoft Teams与 Canvas 一同使用</span><span class="sxs-lookup"><span data-stu-id="7ab53-103">Use Microsoft Teams classes with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="7ab53-104">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="7ab53-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="7ab53-105">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="7ab53-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="7ab53-106">Microsoft Teams课程是学习工具互操作性 (LTI) 应用，可帮助教师和学生轻松地在学习管理系统 (LMS) 和 Teams 之间导航。</span><span class="sxs-lookup"><span data-stu-id="7ab53-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="7ab53-107">用户可以直接从 LMS 中访问与其课程关联的课堂团队。</span><span class="sxs-lookup"><span data-stu-id="7ab53-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="microsoft-office-365-admin"></a><span data-ttu-id="7ab53-108">Microsoft Office 365管理员</span><span class="sxs-lookup"><span data-stu-id="7ab53-108">Microsoft Office 365 Admin</span></span>

<span data-ttu-id="7ab53-109">在内部结构 Canvas 中管理 Microsoft Teams 集成之前，必须让 Microsoft Azure 租户中的机构 Microsoft Office 365 管理员批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用，然后再完成 Canvas 管理员设置。</span><span class="sxs-lookup"><span data-stu-id="7ab53-109">Before managing the Microsoft Teams integration within Instructure Canvas, it is important to have Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app approved by your institution’s Microsoft Office 365 admin in your Microsoft Azure tenant before completing the Canvas admin setup.</span></span>

1. <span data-ttu-id="7ab53-110">登录到 Canvas。</span><span class="sxs-lookup"><span data-stu-id="7ab53-110">Sign in to Canvas.</span></span>
 
2. <span data-ttu-id="7ab53-111">选择全局 **导航** 中的"管理员"链接，然后选择您的帐户。</span><span class="sxs-lookup"><span data-stu-id="7ab53-111">Select the **Admin** link in the global navigation, and then select your account.</span></span>

3. <span data-ttu-id="7ab53-112">在管理员导航中 **，选择**"设置"链接，然后选择"**集成"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="7ab53-112">In the admin navigation, select the **Settings** link, and then the **Integrations** tab.</span></span> 

4. <span data-ttu-id="7ab53-113">输入你的 Microsoft 租户名称和登录属性。</span><span class="sxs-lookup"><span data-stu-id="7ab53-113">Enter your Microsoft tenant name and login attribute.</span></span> 

   <span data-ttu-id="7ab53-114">login 属性将用于将 Canvas 用户与用户Azure Active Directory关联。</span><span class="sxs-lookup"><span data-stu-id="7ab53-114">The login attribute will be used for associating the Canvas user with an Azure Active Directory user.</span></span> 

5. <span data-ttu-id="7ab53-115">选择 **"完成设置** 更新"。</span><span class="sxs-lookup"><span data-stu-id="7ab53-115">Select **Update Settings** once done.</span></span>

6. <span data-ttu-id="7ab53-116">若要批准 Canvas 的 **Microsoft-Teams-Sync-for-Canvas** Azure 应用的访问权限，请选择"授予 **租户访问权限"** 链接。</span><span class="sxs-lookup"><span data-stu-id="7ab53-116">To approve access for Canvas’s **Microsoft-Teams-Sync-for-Canvas** Azure app, select the **Grant tenant access** link.</span></span> <span data-ttu-id="7ab53-117">你将被重定向到 Microsoft 标识平台管理员同意终结点。</span><span class="sxs-lookup"><span data-stu-id="7ab53-117">You'll be redirected to the Microsoft Identity Platform Admin Consent Endpoint.</span></span>

   ![权限](media/permissions.png)

7. <span data-ttu-id="7ab53-119">选择 **接受**。</span><span class="sxs-lookup"><span data-stu-id="7ab53-119">Select **Accept**.</span></span>
 
8. <span data-ttu-id="7ab53-120">通过打开Microsoft Teams启用同步。</span><span class="sxs-lookup"><span data-stu-id="7ab53-120">Enable the Microsoft Teams sync by turning the toggle on.</span></span>

   ![teams-sync](media/teams-sync.png)

## <a name="canvas-admin"></a><span data-ttu-id="7ab53-122">Canvas 管理</span><span class="sxs-lookup"><span data-stu-id="7ab53-122">Canvas Admin</span></span>

<span data-ttu-id="7ab53-123">设置 Microsoft Teams LTI 1.3 集成。</span><span class="sxs-lookup"><span data-stu-id="7ab53-123">Set up the Microsoft Teams LTI 1.3 Integration.</span></span>

<span data-ttu-id="7ab53-124">作为 Canvas 管理员，你需要在你的环境中添加Microsoft Teams类 LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="7ab53-124">As a Canvas Admin, you'll need to add the Microsoft Teams classes LTI app within your environment.</span></span> <span data-ttu-id="7ab53-125">记下应用的 LTI 客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="7ab53-125">Make a note of the LTI Client ID for the app.</span></span>

 - <span data-ttu-id="7ab53-126">Microsoft Teams类 - 170000000000570</span><span class="sxs-lookup"><span data-stu-id="7ab53-126">Microsoft Teams classes - 170000000000570</span></span>

1. <span data-ttu-id="7ab53-127">访问 **管理员设置**  >  **应用**。</span><span class="sxs-lookup"><span data-stu-id="7ab53-127">Access **Admin settings** > **Apps**.</span></span>

2. <span data-ttu-id="7ab53-128">选择 **+ 应用** 以添加Teams LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="7ab53-128">Select **+ App** to add the Teams LTI apps.</span></span> 
 
   ![external-apps](media/external-apps.png)

3. <span data-ttu-id="7ab53-130">为 **配置类型选择"** 按客户端 ID"。</span><span class="sxs-lookup"><span data-stu-id="7ab53-130">Select **By Client ID** for configuration type.</span></span>

   ![添加应用](media/add-app.png)

4. <span data-ttu-id="7ab53-132">输入提供的客户端 ID，然后选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="7ab53-132">Enter the Client ID provided, and then select **Submit**.</span></span>
   
   <span data-ttu-id="7ab53-133">你会注意到客户端 ID 的Microsoft Teams LTI 应用名称，用于确认。</span><span class="sxs-lookup"><span data-stu-id="7ab53-133">You'll notice the Microsoft Teams classes LTI app name for the Client ID for confirmation.</span></span> 

5. <span data-ttu-id="7ab53-134">选择“**安装**”。</span><span class="sxs-lookup"><span data-stu-id="7ab53-134">Select **Install**.</span></span>

   <span data-ttu-id="7ab53-135">the Microsoft Teams classes LTI app will be added to the list of external apps.</span><span class="sxs-lookup"><span data-stu-id="7ab53-135">The Microsoft Teams classes LTI app will be added to the list of external apps.</span></span>
