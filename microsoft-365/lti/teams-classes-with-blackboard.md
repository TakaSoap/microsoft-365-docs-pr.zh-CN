---
title: 将Microsoft Teams类与具有"Learn 超"的类一同使用
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
description: 将Microsoft Teams类与具有"Learn 超"的类一同使用
ms.openlocfilehash: a97d5bf56e1e045ccb0ef7cc66ecef7dfba4041a
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454624"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="f14ba-103">将Microsoft Teams类与具有"Learn 超"的类一同使用</span><span class="sxs-lookup"><span data-stu-id="f14ba-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="f14ba-104">团队合作是每个现代组织的核心。</span><span class="sxs-lookup"><span data-stu-id="f14ba-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="f14ba-105">通过促进协作，这是每个成功机构的定义特征。</span><span class="sxs-lookup"><span data-stu-id="f14ba-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="f14ba-106">通过将它们与一些类配对，可以增强功能与Microsoft Teams功能。</span><span class="sxs-lookup"><span data-stu-id="f14ba-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="f14ba-107">你的课程可能包括实时对话、视频会议或异步交互。</span><span class="sxs-lookup"><span data-stu-id="f14ba-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="f14ba-108">可以在一个地方为学生添加文件共享和共同创建体验。</span><span class="sxs-lookup"><span data-stu-id="f14ba-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="f14ba-109">Microsoft Teams超学习课程重新定义了教学的动态性以及有效的学习方式。</span><span class="sxs-lookup"><span data-stu-id="f14ba-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="f14ba-110">确保你已成功在学生信息系统和 SIS 中设置 ([电子邮件) ](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)</span><span class="sxs-lookup"><span data-stu-id="f14ba-110">Ensure that you have successfully set up the Institution Email field in your [Student Information System (SIS)](https://help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student_Information_System/SIS_Planning)</span></span>
>
><span data-ttu-id="f14ba-111">the Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory's (AAD) [User Principle Name (UPN) ](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes).</span><span class="sxs-lookup"><span data-stu-id="f14ba-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) [User Principle Name (UPN)](/azure/active-directory/hybrid/howto-troubleshoot-upn-changes).</span></span> <span data-ttu-id="f14ba-112">如果未设置机构电子邮件，这将默认为现有电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f14ba-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="f14ba-113">建议为每个用户设置此字段，以确保其数据正确同步，并且 AAD 和用户 Learn 超 之间不存在电子邮件数据冲突。</span><span class="sxs-lookup"><span data-stu-id="f14ba-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="f14ba-114">如果未在 SIS 映射中正确设置此字段，则集成将继续工作，但用户可能不会显示在创建的 Teams 类中，并且可能会发生错误。</span><span class="sxs-lookup"><span data-stu-id="f14ba-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="f14ba-115">支持机构数据映射 – 机构电子邮件 SIS 字段</span><span class="sxs-lookup"><span data-stu-id="f14ba-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="f14ba-116">作为云提供商集成演变的一部分，在学生信息系统框架集成和公共 REST  API 中，为学生信息系统框架集成和公共 REST API 创建了一个新的机构电子邮件字段，让机构可以有效地在"完成学习"和 AAD 之间管理数据同步过程。</span><span class="sxs-lookup"><span data-stu-id="f14ba-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="f14ba-117">机构电子邮件意味着什么，它支持什么？</span><span class="sxs-lookup"><span data-stu-id="f14ba-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="f14ba-118">" **机构电子邮件** "字段允许在客户端的外部支持的数据源和用户学习超之间的自定义字段映射。</span><span class="sxs-lookup"><span data-stu-id="f14ba-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="f14ba-119">如果数据源是云提供商（如 Microsoft），则用户原则名称 (UPN) 是每个用户的主要唯一标识符，其中包括 UPN 前缀 (用户帐户名) 和 UPN 后缀 (DNS 域名) 与 @ 符号联接在一起。</span><span class="sxs-lookup"><span data-stu-id="f14ba-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="f14ba-120">这将为用户内每个特定用户创建一个唯一Microsoft Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="f14ba-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="f14ba-121">为了确保数据准确无误，并确保正确实现在"完成学习超"和"Microsoft Teams"类之间的注册或成员身份，用户的电子邮件地址必须在这两个系统之间匹配。</span><span class="sxs-lookup"><span data-stu-id="f14ba-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="f14ba-122">在"完成学习"中，用户可以在用户界面中更改或替代其现有电子邮件地址，这可能会导致发生同步错误，并且用户未正确添加到课堂团队。</span><span class="sxs-lookup"><span data-stu-id="f14ba-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="f14ba-123">机构 **电子邮件** 字段映射可确保正确管理此级别的安全和验证检查，而无论用户是否更改了在将用户的电子邮件发送到了使用"功能超"功能的用户。</span><span class="sxs-lookup"><span data-stu-id="f14ba-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="f14ba-124">当两个电子邮件地址不同时，可以是：</span><span class="sxs-lookup"><span data-stu-id="f14ba-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="f14ba-125">必须决定哪个来源具有优先级，并且将被同时作为个人电子邮件和机构电子邮件。</span><span class="sxs-lookup"><span data-stu-id="f14ba-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="f14ba-126">或</span><span class="sxs-lookup"><span data-stu-id="f14ba-126">Or</span></span>
- <span data-ttu-id="f14ba-127">机构可以在机构电子邮件中设置自定义字段映射，从而解决潜在冲突。</span><span class="sxs-lookup"><span data-stu-id="f14ba-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="f14ba-128">机构 **电子邮件** 字段映射现在可用于高级配置和用户了解对象类型字段映射设置所有现有 SIS  >    >  **集成类型**。</span><span class="sxs-lookup"><span data-stu-id="f14ba-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="f14ba-129">值得注意的是，默认情况下，机构电子邮件设置为所有 SIS格式的"个人电子邮件"，并且对于每个人必须是唯一的。 </span><span class="sxs-lookup"><span data-stu-id="f14ba-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="f14ba-130">设置并运行的所有现有集成都将具有此数据映射，因为如果用户的电子邮件被复制，SIS 将无法导入用户。</span><span class="sxs-lookup"><span data-stu-id="f14ba-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="f14ba-131">如果机构需要能够将机构电子邮件更改为自定义，他们将需要通过 SIS **中的** 高级配置设置管理。</span><span class="sxs-lookup"><span data-stu-id="f14ba-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="f14ba-132">Requirements</span><span class="sxs-lookup"><span data-stu-id="f14ba-132">Requirements</span></span>

<span data-ttu-id="f14ba-133">该Microsoft Teams课程集成仅适用于 **超课程视图课程**。</span><span class="sxs-lookup"><span data-stu-id="f14ba-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="f14ba-134">你的机构需要完成这些要求以使用它：</span><span class="sxs-lookup"><span data-stu-id="f14ba-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="f14ba-135">启用超基本导航后，让用户了解超极学习 SaaS</span><span class="sxs-lookup"><span data-stu-id="f14ba-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

  ![在课程内启用此功能的示例](media/feature-availability.png)

- <span data-ttu-id="f14ba-137">启用 LTI 以用于课程。</span><span class="sxs-lookup"><span data-stu-id="f14ba-137">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="f14ba-138">a.</span><span class="sxs-lookup"><span data-stu-id="f14ba-138">a.</span></span> <span data-ttu-id="f14ba-139">转到管理员 **面板**  >  **LTI 工具提供程序**  >  **管理全局属性**。</span><span class="sxs-lookup"><span data-stu-id="f14ba-139">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="f14ba-140">b.</span><span class="sxs-lookup"><span data-stu-id="f14ba-140">b.</span></span> <span data-ttu-id="f14ba-141">在 **"课程"中选择"已启用 LTI"，** 并选择"在 **组织中启用"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-141">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="f14ba-142">c.</span><span class="sxs-lookup"><span data-stu-id="f14ba-142">c.</span></span> <span data-ttu-id="f14ba-143">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f14ba-143">Select **Submit**.</span></span>

- <span data-ttu-id="f14ba-144">必须配置 LTI</span><span class="sxs-lookup"><span data-stu-id="f14ba-144">Must have LTI configured</span></span>

- <span data-ttu-id="f14ba-145">添加具有超强Teams课程 LTI 集成</span><span class="sxs-lookup"><span data-stu-id="f14ba-145">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="f14ba-146">添加Microsoft Teams类 LTI 1.3 工具</span><span class="sxs-lookup"><span data-stu-id="f14ba-146">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="f14ba-147">添加 REST API 工具和跨源资源共享</span><span class="sxs-lookup"><span data-stu-id="f14ba-147">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="f14ba-148">配置和批准Microsoft Teams类集成</span><span class="sxs-lookup"><span data-stu-id="f14ba-148">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="f14ba-149">添加"为"Teams学习"LTI 1.3 类工具</span><span class="sxs-lookup"><span data-stu-id="f14ba-149">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="f14ba-150">从管理员 **面板中，** 选择 **LTI 工具提供程序**。</span><span class="sxs-lookup"><span data-stu-id="f14ba-150">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="f14ba-151">选择 **注册 LTI 1.3 工具**。</span><span class="sxs-lookup"><span data-stu-id="f14ba-151">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="f14ba-152">在" **客户端 ID"** 字段中，键入或复制并粘贴此 ID：</span><span class="sxs-lookup"><span data-stu-id="f14ba-152">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="f14ba-153">查看已预先填充的所有设置，然后在"工具状态"中选择"已启用 **"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-153">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="f14ba-154">在 **"机构策略"** 中，在 **"课程、** 名称和电子邮件地址"中选择"角色"，然后为两者选择 **"是**"。</span><span class="sxs-lookup"><span data-stu-id="f14ba-154">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="f14ba-155">选择 **"允许成绩服务访问"\*\*\*\*和"允许成员身份服务访问"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-155">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="f14ba-156">添加Microsoft Teams类 LTI 1.3 工具</span><span class="sxs-lookup"><span data-stu-id="f14ba-156">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="f14ba-157">从管理员 **面板中，** 选择 **LTI 工具提供程序**。</span><span class="sxs-lookup"><span data-stu-id="f14ba-157">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="f14ba-158">选择 **注册 LTI 1.3 工具**。</span><span class="sxs-lookup"><span data-stu-id="f14ba-158">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="f14ba-159">在" **客户端 ID"** 字段中，键入或复制并粘贴此 ID：</span><span class="sxs-lookup"><span data-stu-id="f14ba-159">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="f14ba-160">查看已预先填充的所有设置，在"工具状态 *"中选择* "已启用 *"。*</span><span class="sxs-lookup"><span data-stu-id="f14ba-160">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="f14ba-161">在 **"机构策略"** 中，选择 **"课程、名称和\*\*\*\*电子邮件地址"中的"角色"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-161">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="f14ba-162">为 **两者选择"** 是"。</span><span class="sxs-lookup"><span data-stu-id="f14ba-162">Select **Yes** for both.</span></span>

6. <span data-ttu-id="f14ba-163">选择 **"允许成绩服务访问"\*\*\*\*和"允许成员身份服务访问"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-163">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="f14ba-164">添加 REST API 工具</span><span class="sxs-lookup"><span data-stu-id="f14ba-164">Add the REST API tool</span></span>

1. <span data-ttu-id="f14ba-165">从管理员 **面板中**，导航到 **"集成"，** 然后选择 **"Rest API 集成"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-165">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="f14ba-166">选择 **"创建集成"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-166">Select **Create Integration**.</span></span>

3. <span data-ttu-id="f14ba-167">在" **应用程序 ID"** 字段中，键入或复制并粘贴此 ID：</span><span class="sxs-lookup"><span data-stu-id="f14ba-167">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="f14ba-168">为此集成键入用户。</span><span class="sxs-lookup"><span data-stu-id="f14ba-168">Type a user for this integration.</span></span>

   <span data-ttu-id="f14ba-169">此用户将具有与应用程序关联的家庭 API 访问权限。</span><span class="sxs-lookup"><span data-stu-id="f14ba-169">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="f14ba-170">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f14ba-170">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="f14ba-171">添加跨源资源共享</span><span class="sxs-lookup"><span data-stu-id="f14ba-171">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="f14ba-172">从"**管理员"面板** 中，导航 **到"集成"，** 然后选择"\**跨源资源共享"。*</span><span class="sxs-lookup"><span data-stu-id="f14ba-172">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="f14ba-173">选择 **"创建配置"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-173">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="f14ba-174">在" **源** "字段中，键入复制并粘贴此 URL：</span><span class="sxs-lookup"><span data-stu-id="f14ba-174">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="f14ba-175">在" **允许的标题"** 字段中，键入 **Authorization**。</span><span class="sxs-lookup"><span data-stu-id="f14ba-175">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="f14ba-176">设置为 **"可用**"**为"是"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-176">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="f14ba-177">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f14ba-177">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="f14ba-178">配置和批准Microsoft Teams类集成</span><span class="sxs-lookup"><span data-stu-id="f14ba-178">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="f14ba-179">若要成功将你的"完成学习超"实例与Microsoft Teams类集成，你需要确保批准使用"完成"功能租户中访问的"Microsoft Azure应用程序"。</span><span class="sxs-lookup"><span data-stu-id="f14ba-179">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="f14ba-180">这一过程将需要由你的机构的全局管理员Microsoft 365完成。</span><span class="sxs-lookup"><span data-stu-id="f14ba-180">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="f14ba-181">此过程可以在你在你的"你的"学习超实例"中配置 LTI 应用程序之前或之后完成。</span><span class="sxs-lookup"><span data-stu-id="f14ba-181">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="f14ba-182">配置 LTI 应用程序之前</span><span class="sxs-lookup"><span data-stu-id="f14ba-182">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="f14ba-183">如果你在配置 LTI 集成之前选择批准"完成学习超极Teams类 Azure"应用，则需要重定向到 Microsoft Identity Platform Admin **Consent Endpoint**。</span><span class="sxs-lookup"><span data-stu-id="f14ba-183">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="f14ba-184">将显示 URL：</span><span class="sxs-lookup"><span data-stu-id="f14ba-184">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="f14ba-185">将 **{Tenant}** 替换为特定机构Microsoft Azure租户 ID。</span><span class="sxs-lookup"><span data-stu-id="f14ba-185">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

<span data-ttu-id="f14ba-186">你将看到一个权限窗口，说明你正在授予为用户授予访问 Microsoft Teams 的权限。</span><span class="sxs-lookup"><span data-stu-id="f14ba-186">You'll see a permissions window that explains you're giving permission to Blackboard Learn Ultra to access Microsoft Teams.</span></span>

![Microsoft 和 Microsoft 和 Microsoft 的"权限"窗口](media/permissions1.png)

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="f14ba-188">配置 LTI 应用程序后</span><span class="sxs-lookup"><span data-stu-id="f14ba-188">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="f14ba-189">在管理员 **面板上**，导航到"**工具和** 实用程序"，然后选择 **"Microsoft Teams管理员"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-189">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="f14ba-190">选择 **"启用Microsoft Teams"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-190">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="f14ba-191">将 **Microsoft 租户 ID** 添加到可用文本字段中。</span><span class="sxs-lookup"><span data-stu-id="f14ba-191">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="f14ba-192">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="f14ba-192">Choose one of the following options:</span></span>

   - <span data-ttu-id="f14ba-193">如果应用已预先同意，将显示一个小的选中标记。</span><span class="sxs-lookup"><span data-stu-id="f14ba-193">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="f14ba-194">如果显示选中标记，请选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-194">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="f14ba-195">如果同意尚未获得批准，请按照所述的步骤生成许可 URL 并将其发送给全局管理员Microsoft 365进行审批。</span><span class="sxs-lookup"><span data-stu-id="f14ba-195">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="f14ba-196">确认审批后，选择"**重试** 以确认"，然后选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="f14ba-196">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>

   ![指示您的访问已被阻止的对话框](media/blocked-access.png)