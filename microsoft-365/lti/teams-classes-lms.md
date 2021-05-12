---
title: 使用Microsoft Teams管理系统中的课程
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
description: 在Microsoft Teams管理系统中集成课程
ms.openlocfilehash: 18d33225dd57932af20421c6b3b5dc4fe3b397b8
ms.sourcegitcommit: 68383240ef7a673d5f28e2ecfab9f105bf1d8c8f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/11/2021
ms.locfileid: "52327703"
---
# <a name="use-microsoft-teams-classes-in-your-learning-management-system"></a><span data-ttu-id="684eb-103">使用Microsoft Teams管理系统中的课程</span><span class="sxs-lookup"><span data-stu-id="684eb-103">Use Microsoft Teams classes in your Learning Management System</span></span>

> [!IMPORTANT]
> <span data-ttu-id="684eb-104">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="684eb-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="684eb-105">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="684eb-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

<span data-ttu-id="684eb-106">Microsoft Teams课堂团队是学习工具互操作性 (LTI) 应用，可帮助教师和学生轻松地在学习管理系统 (LMS) 和 Teams 之间导航。</span><span class="sxs-lookup"><span data-stu-id="684eb-106">Microsoft Teams class teams is a Learning Tools Interoperability (LTI) app that helps educators and students easily navigate between their Learning Management System (LMS) and Teams.</span></span> <span data-ttu-id="684eb-107">用户可以直接从 LMS 中访问与其课程关联的课堂团队。</span><span class="sxs-lookup"><span data-stu-id="684eb-107">Users can access their class teams associated with their course directly from within their LMS.</span></span>

## <a name="approve-the-app-in-the-microsoft-azure-tenant"></a><span data-ttu-id="684eb-108">在租户中批准Microsoft Azure应用程序</span><span class="sxs-lookup"><span data-stu-id="684eb-108">Approve the app in the Microsoft Azure tenant</span></span>

<span data-ttu-id="684eb-109">以下任务由应用管理员和 Microsoft Office 365 Learn 超管理员完成。</span><span class="sxs-lookup"><span data-stu-id="684eb-109">The following tasks are completed by the Microsoft Office 365 admin and the Blackboard Learn Ultra admin.</span></span>

<span data-ttu-id="684eb-110">在管理在Microsoft Office 365 Learn 超 中的集成之前，Microsoft Office 365管理员必须批准适用于机构 Microsoft Azure 租户的适用于 **Learn 超 Azure** 应用的适用于 Learn 超 Azure Teams。</span><span class="sxs-lookup"><span data-stu-id="684eb-110">Before managing the integration within Blackboard Learn Ultra, the Microsoft Office 365 admin must approve the Blackboard **MSFT Teams for Learn Ultra Azure** app for the institution’s Microsoft Azure tenant.</span></span>

1. <span data-ttu-id="684eb-111">查找你的 Microsoft 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="684eb-111">Find your Microsoft Tenant ID.</span></span> <span data-ttu-id="684eb-112">请参阅 [如何查找租户](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant)。</span><span class="sxs-lookup"><span data-stu-id="684eb-112">See [how to find the tenant](/azure/active-directory/fundamentals/active-directory-how-to-find-tenant).</span></span>

2. <span data-ttu-id="684eb-113">根据以下示例重定向 Microsoft Identity Platform Admin Consent 终结点：</span><span class="sxs-lookup"><span data-stu-id="684eb-113">Redirect the Microsoft Identity Platform Admin Consent Endpoint according to the following example:</span></span>

   `https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

   > [!NOTE]
   > <span data-ttu-id="684eb-114">将 {tenant} 替换为组织的 Microsoft 租户 ID。</span><span class="sxs-lookup"><span data-stu-id="684eb-114">Replace {tenant} with your organization’s Microsoft tenant ID.</span></span>

## <a name="register-the-integration-apps"></a><span data-ttu-id="684eb-115">注册集成应用</span><span class="sxs-lookup"><span data-stu-id="684eb-115">Register the integration apps</span></span>

<span data-ttu-id="684eb-116">作为一名 Learn 超管理员，你需要在测试环境中注册 2 个 LTI 1.3 集成应用：</span><span class="sxs-lookup"><span data-stu-id="684eb-116">As a Blackboard Learn Ultra admin, you'll need to register 2 LTI 1.3 integration apps within your Test environment:</span></span>

- <span data-ttu-id="684eb-117">为支持名单Teams进行集成</span><span class="sxs-lookup"><span data-stu-id="684eb-117">The Blackboard Learn Class Teams integration to support the roster sync</span></span>

- <span data-ttu-id="684eb-118">Microsoft Teams课堂团队 LTI 应用</span><span class="sxs-lookup"><span data-stu-id="684eb-118">The Microsoft Teams class team LTI app</span></span>

1. <span data-ttu-id="684eb-119">记下这两个应用的以下 LTI 客户端 ID：</span><span class="sxs-lookup"><span data-stu-id="684eb-119">Make a note of the following LTI Client IDs for both Apps:</span></span>

    - <span data-ttu-id="684eb-120">美洲 - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span><span class="sxs-lookup"><span data-stu-id="684eb-120">Blackboard - f1561daa-1b21-4693-ba90-6c55f1a0eb41</span></span>

    - <span data-ttu-id="684eb-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span><span class="sxs-lookup"><span data-stu-id="684eb-121">Microsoft - 027328b7-c2e3-4c9e-aaa1-07802dae6c89</span></span>

2. <span data-ttu-id="684eb-122">访问管理面板，在 **"集成"下** 找到 LTI 工具提供程序。</span><span class="sxs-lookup"><span data-stu-id="684eb-122">Access the Admin Panel, and under **Integrations**, locate the LTI Tool Providers.</span></span>

   ![这是 LTI 工具提供程序对话框，显示提供程序列表](../media/lti-media/lti-tool-providers.png)

3. <span data-ttu-id="684eb-124">选择 **"注册 LTI1.3/优势工具"。**</span><span class="sxs-lookup"><span data-stu-id="684eb-124">Select **Register LTI1.3/Advantage Tool**.</span></span>

4. <span data-ttu-id="684eb-125">输入提供的第一个客户端 ID (或 Microsoft) ，**然后选择提交。**</span><span class="sxs-lookup"><span data-stu-id="684eb-125">Enter the first of the Client IDs provided (either Blackboard or Microsoft), and select **Submit**.</span></span>

   ![LTI 注册工具，使用字段输入客户端 ID](../media/lti-media/register-tool.png)

5. <span data-ttu-id="684eb-127">查看预填充的设置，并确保工具状态标记为已批准。</span><span class="sxs-lookup"><span data-stu-id="684eb-127">Review the pre-populated settings and ensure that the tool status is marked as approved.</span></span>

6. <span data-ttu-id="684eb-128">滚动到底部，然后选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="684eb-128">Scroll to the bottom, and then select **Submit**.</span></span>

7. <span data-ttu-id="684eb-129">重复上述步骤，在环境中注册第二个 LTI 应用。</span><span class="sxs-lookup"><span data-stu-id="684eb-129">Repeat the previous steps to register the second of the LTI apps within your environment.</span></span>

## <a name="set-up-the-rest-application-and-cross-origin-resource-sharing"></a><span data-ttu-id="684eb-130">设置 REST 应用程序和跨源资源共享</span><span class="sxs-lookup"><span data-stu-id="684eb-130">Set up the REST Application and Cross Origin Resource Sharing</span></span>

<span data-ttu-id="684eb-131">The 部署学习超管理员还需要配置 REST 应用程序和跨源资源共享配置。</span><span class="sxs-lookup"><span data-stu-id="684eb-131">The Blackboard Learn Ultra admin will also need to configure the REST Application and the Cross Origin Resource Sharing configuration.</span></span>

<span data-ttu-id="684eb-132">完成以下操作以设置 REST 应用程序</span><span class="sxs-lookup"><span data-stu-id="684eb-132">Complete the following to set up the REST Application</span></span>

1. <span data-ttu-id="684eb-133">访问"了解管理工具"，然后从"集成" **部分选择"REST API** **集成** "。</span><span class="sxs-lookup"><span data-stu-id="684eb-133">Access the Learn Administration Tools, and then select **REST API Integrations** from the **Integrations** section.</span></span>

2. <span data-ttu-id="684eb-134">选择 **"创建集成"，** 然后输入与为"适用于集成 LTI"工具的"Teams/客户端 ID 相同的应用程序/客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="684eb-134">Select **Create integrations** and enter the same Application/Client ID that you entered for the Blackboard Learn Class Teams Integration LTI tool.</span></span>

3. <span data-ttu-id="684eb-135">输入"了解用户 (这可能是你自己的学习管理员用户名) ， **或选择"** 浏览"查找。</span><span class="sxs-lookup"><span data-stu-id="684eb-135">Enter the Learn User (this could be your own learn admin username), or select **Browse** to locate.</span></span>

4. <span data-ttu-id="684eb-136">为 **"\*\*\*\*最终用户访问"选择"是"。**</span><span class="sxs-lookup"><span data-stu-id="684eb-136">Select **Yes** for **End User Access**.</span></span>

5. <span data-ttu-id="684eb-137">选择 **"是\*\*\*\*"以授权充当用户**</span><span class="sxs-lookup"><span data-stu-id="684eb-137">Select **Yes** for **Authorized to Act as User**</span></span>

6. <span data-ttu-id="684eb-138">选择 **"完成后** 提交"。</span><span class="sxs-lookup"><span data-stu-id="684eb-138">Select **Submit** once complete.</span></span>

## <a name="set-up-cross-origin-resource-sharing"></a><span data-ttu-id="684eb-139">设置跨源资源共享</span><span class="sxs-lookup"><span data-stu-id="684eb-139">Set up Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="684eb-140">访问"了解管理工具"， **然后从** "集成"部分选择"跨 **源资源共享** "。</span><span class="sxs-lookup"><span data-stu-id="684eb-140">Access the Learn Administration Tools, and select **Cross-Origin Resource Sharing** from the **Integrations** section.</span></span>

2. <span data-ttu-id="684eb-141">选择 **"创建配置"。**</span><span class="sxs-lookup"><span data-stu-id="684eb-141">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="684eb-142">在 `https://bb-ms-teams-ultra-ext.api.blackboard.com` 源中输入。</span><span class="sxs-lookup"><span data-stu-id="684eb-142">Enter `https://bb-ms-teams-ultra-ext.api.blackboard.com` in the origin.</span></span>

4. <span data-ttu-id="684eb-143">在允许的标头中添加 **单词** **Authorization。**</span><span class="sxs-lookup"><span data-stu-id="684eb-143">Add the word **Authorization** in the **Allowed Headers**.</span></span>

5. <span data-ttu-id="684eb-144">设置为 **"可用**"**为"是"。**</span><span class="sxs-lookup"><span data-stu-id="684eb-144">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="684eb-145">选择 **"完成后** 提交"。</span><span class="sxs-lookup"><span data-stu-id="684eb-145">Select **Submit** once complete.</span></span>

## <a name="enable-class-teams-in-blackboard-learn"></a><span data-ttu-id="684eb-146">在"Teams中启用课堂学习"</span><span class="sxs-lookup"><span data-stu-id="684eb-146">Enable Class Teams in Blackboard Learn</span></span>

<span data-ttu-id="684eb-147">启用 LTI 工具后，下一步是从你自己的 Teams 租户设置 Microsoft 类Microsoft Office 365集成。</span><span class="sxs-lookup"><span data-stu-id="684eb-147">Once you've enabled the LTI tools, your next step will be to set up the Microsoft Class Teams integration from your own Microsoft Office 365 tenant.</span></span> <span data-ttu-id="684eb-148">为此，你可以按照以下步骤操作，作为"完成""学习""超"管理员。</span><span class="sxs-lookup"><span data-stu-id="684eb-148">You can do this by following these steps as the Blackboard Learn Ultra admin.</span></span>

1. <span data-ttu-id="684eb-149">在 **"了解**  >  **管理工具和实用程序"中**，Microsoft Teams **集成管理员"。**</span><span class="sxs-lookup"><span data-stu-id="684eb-149">In **Learn Admin** > **Tools and Utilities**, select **Microsoft Teams Integration Admin**.</span></span>

   ![包含可用工具列表的工具和实用程序对话框](../media/lti-media/tools-utilities.png)

2. <span data-ttu-id="684eb-151">选中"启用"复选框 **Microsoft Teams。**</span><span class="sxs-lookup"><span data-stu-id="684eb-151">Select the checkbox for **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="684eb-152">输入 Microsoft O365 管理员下部分中引用的租户 ID</span><span class="sxs-lookup"><span data-stu-id="684eb-152">Enter your tenant ID as referenced in the section under Microsoft O365 Admin</span></span>

 > [!NOTE]
 > <span data-ttu-id="684eb-153">在 O365 管理员批准应用之前，无法保存设置。请参阅[批准租户中的Microsoft Azure。](#approve-the-app-in-the-microsoft-azure-tenant)</span><span class="sxs-lookup"><span data-stu-id="684eb-153">You won't be able to save the settings until the app has been approved by the O365 admin. See [Approve the app in Microsoft Azure tenant](#approve-the-app-in-the-microsoft-azure-tenant).</span></span>

4. <span data-ttu-id="684eb-154">当全局 O365 管理员批准 Microsoft 租户中的"Teams应用程序"后，选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="684eb-154">When the global O365 admin has approved the Blackboard Teams application in your Microsoft Tenant, select **Submit**.</span></span>
