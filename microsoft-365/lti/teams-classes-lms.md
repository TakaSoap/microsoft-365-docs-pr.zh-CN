---
title: 将Microsoft Teams类与管理
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
description: 在 Microsoft Teams 管理系统中集成Learning类
ms.openlocfilehash: 940c5c695d602ddce6ea49b1f914f2345fbeb7e5
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083239"
---
# <a name="use-microsoft-teams-classes-with-blackboard"></a><span data-ttu-id="2802a-103">将Microsoft Teams类与管理</span><span class="sxs-lookup"><span data-stu-id="2802a-103">Use Microsoft Teams classes with Blackboard</span></span>

> [!IMPORTANT]
> <span data-ttu-id="2802a-104">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="2802a-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="2802a-105">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="2802a-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="2802a-106">Microsoft Teams课程是 Learning Tools Interoperability (LTI) 应用，可帮助教师和学生轻松地在 Learning Management System (LMS) 和 Teams 之间导航。</span><span class="sxs-lookup"><span data-stu-id="2802a-106">Microsoft Teams classes is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="2802a-107">用户可以直接从 LMS 中访问与其课程关联的课堂团队。</span><span class="sxs-lookup"><span data-stu-id="2802a-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="2802a-108">在租户中批准Microsoft Azure应用程序</span><span class="sxs-lookup"><span data-stu-id="2802a-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="2802a-109">以下任务由应用管理员和 Microsoft Office 365 Learn 超管理员完成。</span><span class="sxs-lookup"><span data-stu-id="2802a-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="2802a-110">在管理在Microsoft Office 365 Learn 超 中的集成之前，Microsoft Office 365管理员必须批准适用于机构 Microsoft Azure 租户的适用于 **Learn 超 Azure** 应用的适用于 Learn 超 Azure Teams。</span><span class="sxs-lookup"><span data-stu-id="2802a-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="2802a-111">查找你的 Microsoft 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="2802a-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="2802a-112">请参阅 [如何查找租户](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)。</span><span class="sxs-lookup"><span data-stu-id="2802a-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="2802a-113">根据以下示例重定向 Microsoft Identity Platform Admin Consent 终结点：</span><span class="sxs-lookup"><span data-stu-id="2802a-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="2802a-114">将 {tenant} 替换为组织的 Microsoft 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="2802a-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="2802a-115">注册集成应用</span><span class="sxs-lookup"><span data-stu-id="2802a-115">Register the integration apps</span></span>

<span data-ttu-id="2802a-116">作为一名 Learn 超管理员，你需要在测试环境中注册 2 个 LTI 1.3 集成应用：</span><span class="sxs-lookup"><span data-stu-id="2802a-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="2802a-117">为支持名单Teams进行集成</span><span class="sxs-lookup"><span data-stu-id="2802a-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="2802a-118">Microsoft Teams课堂团队 LTI 应用</span><span class="sxs-lookup"><span data-stu-id="2802a-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="2802a-119">记下这两个应用的以下 LTI 客户端 ID：</span><span class="sxs-lookup"><span data-stu-id="2802a-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="2802a-120">美洲 - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="2802a-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="2802a-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="2802a-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="2802a-122">访问管理面板，在 **"集成"下** 找到 LTI 工具提供程序。</span><span class="sxs-lookup"><span data-stu-id="2802a-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![这是 LTI 工具提供程序对话框，显示提供程序列表](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="2802a-124">选择 **"注册 LTI1.3/优势工具"。**</span><span class="sxs-lookup"><span data-stu-id="2802a-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="2802a-125">输入提供的第一个客户端 ID (或 Microsoft) ，**然后选择提交。**</span><span class="sxs-lookup"><span data-stu-id="2802a-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

5. <span data-ttu-id="2802a-126">查看预填充的设置，并确保工具状态标记为已批准。</span><span class="sxs-lookup"><span data-stu-id="2802a-126">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="2802a-127">滚动到底部，然后选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="2802a-127">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="2802a-128">重复上述步骤，在环境中注册第二个 LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="2802a-128">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="2802a-129">设置 REST 应用程序和跨源资源共享</span><span class="sxs-lookup"><span data-stu-id="2802a-129">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="2802a-130">The 部署学习超管理员还需要配置 REST 应用程序和跨源资源共享配置。</span><span class="sxs-lookup"><span data-stu-id="2802a-130">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="2802a-131">完成以下操作以设置 REST 应用程序</span><span class="sxs-lookup"><span data-stu-id="2802a-131">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="2802a-132">访问"了解管理工具"，然后从"集成" **部分选择"REST API** **集成** "。</span><span class="sxs-lookup"><span data-stu-id="2802a-132">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="2802a-133">选择 **"创建集成"，** 然后输入与为"适用于集成 LTI"工具的"Teams/客户端 ID 相同的应用程序/客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="2802a-133">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="2802a-134">输入"了解用户 (这可能是你自己的学习管理员用户名) ， **或选择"** 浏览"查找。</span><span class="sxs-lookup"><span data-stu-id="2802a-134">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="2802a-135">为 **"\*\*\*\*最终用户访问"选择"是"。**</span><span class="sxs-lookup"><span data-stu-id="2802a-135">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="2802a-136">选择 **"是\*\*\*\*"以授权充当用户**</span><span class="sxs-lookup"><span data-stu-id="2802a-136">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="2802a-137">选择 **"完成后** 提交"。</span><span class="sxs-lookup"><span data-stu-id="2802a-137">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="2802a-138">设置跨源资源共享</span><span class="sxs-lookup"><span data-stu-id="2802a-138">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="2802a-139">访问"了解管理工具"， **然后从** "集成"部分选择"跨 **源资源共享** "。</span><span class="sxs-lookup"><span data-stu-id="2802a-139">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="2802a-140">选择 **"创建配置"。**</span><span class="sxs-lookup"><span data-stu-id="2802a-140">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="2802a-141">在 `https://bb-ms-teams-ultra-ext.api.blackboard.com` 源中输入。</span><span class="sxs-lookup"><span data-stu-id="2802a-141">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="2802a-142">在允许的标头中添加 **单词** **Authorization。**</span><span class="sxs-lookup"><span data-stu-id="2802a-142">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="2802a-143">设置为 **"可用**"**为"是"。**</span><span class="sxs-lookup"><span data-stu-id="2802a-143">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="2802a-144">选择 **"完成后** 提交"。</span><span class="sxs-lookup"><span data-stu-id="2802a-144">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="2802a-145">在"Teams中启用课堂学习"</span><span class="sxs-lookup"><span data-stu-id="2802a-145">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="2802a-146">启用 LTI 工具后，下一步是从你自己的 Teams 租户设置 Microsoft 类Microsoft Office 365集成。</span><span class="sxs-lookup"><span data-stu-id="2802a-146">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="2802a-147">为此，你可以按照以下步骤操作，作为"完成""学习""超"管理员。</span><span class="sxs-lookup"><span data-stu-id="2802a-147">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="2802a-148">在 **"了解**  >  **管理工具和实用程序"中**，Microsoft Teams **集成管理员"。**</span><span class="sxs-lookup"><span data-stu-id="2802a-148">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![包含可用工具列表的工具和实用程序对话框](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="2802a-150">选中"启用"复选框 **Microsoft Teams。**</span><span class="sxs-lookup"><span data-stu-id="2802a-150">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="2802a-151">输入 Microsoft O365 管理员下部分中引用的租户 ID</span><span class="sxs-lookup"><span data-stu-id="2802a-151">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="2802a-152">在 O365 管理员批准应用之前，无法保存设置。请参阅[批准租户中的Microsoft Azure。](#approve-the-app-in-the-microsoft-azure-tenant)</span><span class="sxs-lookup"><span data-stu-id="2802a-152">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="2802a-153">当全局 O365 管理员批准 Microsoft 租户中的"Teams应用程序"后，选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="2802a-153">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
