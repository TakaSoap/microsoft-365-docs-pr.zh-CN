---
title: 将Microsoft Teams类与管理学习超集成
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
description: 将Microsoft Teams类与管理学习超集成
ms.openlocfilehash: da98fae3fa5d6be2513147be58747512bea99e16
ms.sourcegitcommit: 8b0718f5607ab509092cb80bda854010d885c54f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53314485"
---
# <a name="use-microsoft-teams-classes-with-blackboard-learn-ultra"></a><span data-ttu-id="214c3-103">将Microsoft Teams类与具有"Learn 超"的类一同使用</span><span class="sxs-lookup"><span data-stu-id="214c3-103">Use Microsoft Teams classes with Blackboard Learn Ultra</span></span>

<span data-ttu-id="214c3-104">团队合作是每个现代组织的核心。</span><span class="sxs-lookup"><span data-stu-id="214c3-104">Teamwork is at the core of every modern organization.</span></span> <span data-ttu-id="214c3-105">通过促进协作，这是每个成功机构的定义特征。</span><span class="sxs-lookup"><span data-stu-id="214c3-105">By fostering collaboration, it’s a defining characteristic of every successful institution.</span></span> <span data-ttu-id="214c3-106">通过将它们与一些类配对，可以增强功能与Microsoft Teams功能。</span><span class="sxs-lookup"><span data-stu-id="214c3-106">You can enhance all the capabilities and features of Blackboard Learn Ultra by pairing them up with Microsoft Teams classes.</span></span>

<span data-ttu-id="214c3-107">你的课程可能包括实时对话、视频会议或异步交互。</span><span class="sxs-lookup"><span data-stu-id="214c3-107">Your classes might include real-time conversations, video meetings, or asynchronous interactions.</span></span> <span data-ttu-id="214c3-108">可以在一个地方为学生添加文件共享和共同创建体验。</span><span class="sxs-lookup"><span data-stu-id="214c3-108">You can add file sharing and cocreation experiences for your students, all in one place.</span></span> <span data-ttu-id="214c3-109">Microsoft Teams超学习课程重新定义了教学的动态性以及有效的学习方式。</span><span class="sxs-lookup"><span data-stu-id="214c3-109">Microsoft Teams classes with Learn Ultra redefine the dynamics of teaching and what effective learning means.</span></span>

> [!IMPORTANT]
> <span data-ttu-id="214c3-110">确保你已成功在学生信息系统和 SIS (机构电子邮件) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span><span class="sxs-lookup"><span data-stu-id="214c3-110">Ensure that you have successfully set up the Institution Email field in your Student Information System (SIS) `help.blackboard.com/Learn/Administrator/SaaS/Integrations/Student\_Information\_System/SIS\_Planning`</span></span>
>
><span data-ttu-id="214c3-111">Microsoft Teams类集成依赖 SIS 中的机构电子邮件字段映射到正确的 Microsoft Azure Active Directory 的 AAD (用户主体) 名称 (UPN) 。</span><span class="sxs-lookup"><span data-stu-id="214c3-111">The Microsoft Teams classes integration relies on the institution email field in your SIS to map to the correct Microsoft Azure Active Directory’s (AAD) User Principal Name (UPN).</span></span> <span data-ttu-id="214c3-112">如果未设置机构电子邮件，这将默认为现有电子邮件。</span><span class="sxs-lookup"><span data-stu-id="214c3-112">If no institution email has been provisioned, this will default to the existing email.</span></span> <span data-ttu-id="214c3-113">建议为每个用户设置此字段，以确保其数据正确同步，并且 Microsoft AAD 和 Microsoft Learn Ultra 之间的电子邮件数据没有冲突。</span><span class="sxs-lookup"><span data-stu-id="214c3-113">It’s recommended that this field be set for every user to ensure their data is synchronized correctly and that there is no conflict of email data between Microsoft AAD and Blackboard Learn Ultra.</span></span>
>
> <span data-ttu-id="214c3-114">如果未在 SIS 映射中正确设置此字段，则集成将继续工作，但用户可能不会显示在创建的 Teams 类中，并且可能会发生错误。</span><span class="sxs-lookup"><span data-stu-id="214c3-114">If you haven’t set this field appropriately in your SIS mapping, the integration will continue to work, but users might not appear in the Teams classes created, and errors could occur.</span></span>

## <a name="supporting-institutional-data-mapping--institution-email-sis-field"></a><span data-ttu-id="214c3-115">支持机构数据映射 – 机构电子邮件 SIS 字段</span><span class="sxs-lookup"><span data-stu-id="214c3-115">Supporting Institutional Data Mapping – Institution Email SIS Field</span></span>

<span data-ttu-id="214c3-116">作为云提供商集成演变的一部分，在学生信息系统框架集成和公共 REST  API 中，为学生信息系统框架集成和公共 REST API 创建了一个新的机构电子邮件字段，让机构可以有效地在"完成学习"和 Microsoft AAD 之间管理数据同步过程。</span><span class="sxs-lookup"><span data-stu-id="214c3-116">As part of the evolution with Cloud provider integrations, Blackboard Learn Ultra has created a new **Institution Email** field, in both the Student Information System Framework integration and public REST APIs, allowing institutions to manage the data synchronization process effectively between Blackboard Learn Ultra and Microsoft AAD.</span></span>

### <a name="what-does-the-institution-email-mean-and-what-does-it-support"></a><span data-ttu-id="214c3-117">机构电子邮件意味着什么，它支持什么？</span><span class="sxs-lookup"><span data-stu-id="214c3-117">What does the Institution Email mean and what does it support?</span></span>

<span data-ttu-id="214c3-118">" **机构电子邮件** "字段允许在客户端的外部支持的数据源和用户学习超之间的自定义字段映射。</span><span class="sxs-lookup"><span data-stu-id="214c3-118">The **Institution Email** field allows customized field mappings between a client’s externally supported data sources and Blackboard Learn Ultra.</span></span> <span data-ttu-id="214c3-119">如果数据源是云提供商（如 Microsoft），则用户原则名称 (UPN) 是每个用户的主要唯一标识符，其中包括 UPN 前缀 (用户帐户名) 和 UPN 后缀 (DNS 域名) 与 @ 符号联接在一起。</span><span class="sxs-lookup"><span data-stu-id="214c3-119">If data sources are cloud providers, such as Microsoft, the User Principle Name (UPN) is a primary unique identifier for each user consisting of a UPN prefix (the user’s account name) and a UPN suffix (a DNS domain name) joined together with an @ symbol.</span></span> <span data-ttu-id="214c3-120">这将为用户内每个特定用户创建一个唯一Microsoft Azure Active Directory。</span><span class="sxs-lookup"><span data-stu-id="214c3-120">This creates a unique email address for each specific user within the Microsoft Azure Active Directory.</span></span>

<span data-ttu-id="214c3-121">为了确保数据准确无误，并确保正确实现在"完成学习超"和"Microsoft Teams"类之间的注册或成员身份，用户的电子邮件地址必须在这两个系统之间匹配。</span><span class="sxs-lookup"><span data-stu-id="214c3-121">To ensure data is accurate and enrollments or memberships between Blackboard Learn Ultra and Microsoft Teams classes are correctly achieved, a user’s email address must match between both systems.</span></span> <span data-ttu-id="214c3-122">在"完成学习"中，用户可以在用户界面中更改或替代其现有电子邮件地址，这可能会导致发生同步错误，并且用户未正确添加到课堂团队。</span><span class="sxs-lookup"><span data-stu-id="214c3-122">In Blackboard Learn Ultra, users can change or override their existing email address in the user interface, which could result in sync errors occurring and the user not being correctly added to a Class Team.</span></span> <span data-ttu-id="214c3-123">机构 **电子邮件** 字段映射可确保正确管理此级别的安全和验证检查，而无论用户是否更改了在将用户的电子邮件发送到了使用"功能超"功能的用户。</span><span class="sxs-lookup"><span data-stu-id="214c3-123">The **Institution Email** field mapping ensures this level of security and validation checking can be correctly managed, regardless if users have changed their email within Blackboard Learn Ultra or not.</span></span>

 <span data-ttu-id="214c3-124">当两个电子邮件地址不同时，可以是：</span><span class="sxs-lookup"><span data-stu-id="214c3-124">When two email addresses are different, either:</span></span>

- <span data-ttu-id="214c3-125">必须决定哪个来源具有优先级，并且将被同时作为个人电子邮件和机构电子邮件。</span><span class="sxs-lookup"><span data-stu-id="214c3-125">A decision must be made as to which source has precedence and will be taken as both the Person and Institution Emails.</span></span>
  <span data-ttu-id="214c3-126">或</span><span class="sxs-lookup"><span data-stu-id="214c3-126">Or</span></span>
- <span data-ttu-id="214c3-127">机构可以在机构电子邮件中设置自定义字段映射，从而解决潜在冲突。</span><span class="sxs-lookup"><span data-stu-id="214c3-127">An institution can set a custom field mapping in its Institution Email, which can resolve a potential conflict.</span></span>

<span data-ttu-id="214c3-128">机构 **电子邮件** 字段映射现在可用于高级配置和用户了解对象类型字段映射设置所有现有 SIS  >    >  **集成类型**。</span><span class="sxs-lookup"><span data-stu-id="214c3-128">The **Institution Email** field mapping is now available for all existing SIS integration types at **Advanced Configuration Settings** > **Users Learn Object Type** > **Field Mapping**.</span></span>

> [!NOTE]
> <span data-ttu-id="214c3-129">值得注意的是，默认情况下，机构电子邮件设置为所有 SIS格式的"个人电子邮件"，并且对于每个人必须是唯一的。 </span><span class="sxs-lookup"><span data-stu-id="214c3-129">It’s important to note that, by default, the **Institution Email** is set to the **Person Email** for all SIS formats and must be unique for each person.</span></span> <span data-ttu-id="214c3-130">设置并运行的所有现有集成都将具有此数据映射，因为如果用户的电子邮件被复制，SIS 将无法导入用户。</span><span class="sxs-lookup"><span data-stu-id="214c3-130">All existing integrations that are set up and running will have this data mapping in place, as SIS will fail to import users if their email is duplicated.</span></span> <span data-ttu-id="214c3-131">如果机构需要能够将机构电子邮件更改为自定义，他们将需要通过 SIS **中的** 高级配置设置管理。</span><span class="sxs-lookup"><span data-stu-id="214c3-131">If an institution requires the ability to change the Institution Email to **custom**, they'll need to manage this through the **Advanced Configuration Settings** in the SIS.</span></span>

## <a name="requirements"></a><span data-ttu-id="214c3-132">Requirements</span><span class="sxs-lookup"><span data-stu-id="214c3-132">Requirements</span></span>

<span data-ttu-id="214c3-133">该Microsoft Teams课程集成仅适用于 **超课程视图课程**。</span><span class="sxs-lookup"><span data-stu-id="214c3-133">The Microsoft Teams classes integration is available for **Ultra Course View courses only**.</span></span> <span data-ttu-id="214c3-134">你的机构需要完成这些要求以使用它：</span><span class="sxs-lookup"><span data-stu-id="214c3-134">Your institution needs to complete these requirements to use it:</span></span>

- <span data-ttu-id="214c3-135">启用超基本导航后，让用户了解超极学习 SaaS</span><span class="sxs-lookup"><span data-stu-id="214c3-135">Have Blackboard Learn Ultra Learn SaaS with Ultra Base Navigation enabled</span></span>

- <span data-ttu-id="214c3-136">启用 LTI 以用于课程。</span><span class="sxs-lookup"><span data-stu-id="214c3-136">Enable LTI for use in courses.</span></span>

  <span data-ttu-id="214c3-137">a.</span><span class="sxs-lookup"><span data-stu-id="214c3-137">a.</span></span> <span data-ttu-id="214c3-138">转到管理员 **面板**  >  **LTI 工具提供程序**  >  **管理全局属性**。</span><span class="sxs-lookup"><span data-stu-id="214c3-138">Go to the **Administrator Panel** > **LTI Tool Providers** > **Manage Global Properties**.</span></span>

  <span data-ttu-id="214c3-139">b.</span><span class="sxs-lookup"><span data-stu-id="214c3-139">b.</span></span> <span data-ttu-id="214c3-140">在 **"课程"中选择"已启用 LTI"，** 并选择"在 **组织中启用"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-140">Select **LTI Enabled in Courses**, and optionally, select **Enabled in Organizations**.</span></span>

  <span data-ttu-id="214c3-141">c.</span><span class="sxs-lookup"><span data-stu-id="214c3-141">c.</span></span> <span data-ttu-id="214c3-142">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="214c3-142">Select **Submit**.</span></span>

- <span data-ttu-id="214c3-143">必须配置 LTI</span><span class="sxs-lookup"><span data-stu-id="214c3-143">Must have LTI configured</span></span>

- <span data-ttu-id="214c3-144">添加具有超强Teams课程 LTI 集成</span><span class="sxs-lookup"><span data-stu-id="214c3-144">Add Blackboard Learn Ultra Teams Classes LTI Integration</span></span>

- <span data-ttu-id="214c3-145">添加Microsoft Teams类 LTI 1.3 工具</span><span class="sxs-lookup"><span data-stu-id="214c3-145">Add Microsoft Teams Classes LTI 1.3 Tool</span></span>

- <span data-ttu-id="214c3-146">添加 REST API 工具和跨源资源共享</span><span class="sxs-lookup"><span data-stu-id="214c3-146">Add the REST API Tool and Cross-Origin Resource Sharing</span></span>

- <span data-ttu-id="214c3-147">配置和批准Microsoft Teams类集成</span><span class="sxs-lookup"><span data-stu-id="214c3-147">Configure and approve Microsoft Teams classes Integration</span></span>

## <a name="add-the-blackboard-learn-ultra-teams-classes-lti-13-tool"></a><span data-ttu-id="214c3-148">添加"为"Teams学习"LTI 1.3 类工具</span><span class="sxs-lookup"><span data-stu-id="214c3-148">Add the Blackboard Learn Ultra Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="214c3-149">从管理员 **面板中，** 选择 **LTI 工具提供程序**。</span><span class="sxs-lookup"><span data-stu-id="214c3-149">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="214c3-150">选择 **注册 LTI 1.3 工具**。</span><span class="sxs-lookup"><span data-stu-id="214c3-150">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="214c3-151">在" **客户端 ID"** 字段中，键入或复制并粘贴此 ID：</span><span class="sxs-lookup"><span data-stu-id="214c3-151">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="214c3-152">查看已预先填充的所有设置，然后在"工具状态"中选择"已启用 **"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-152">Review all settings that have been pre-populated and in **Tool Status**, and then select **Enabled**.</span></span>

5. <span data-ttu-id="214c3-153">在 **"机构策略"** 中，在 **"课程、** 名称和电子邮件地址"中选择"角色"，然后为两者选择 **"是**"。</span><span class="sxs-lookup"><span data-stu-id="214c3-153">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**, and then select **Yes** for both.</span></span>

6. <span data-ttu-id="214c3-154">选择 **"允许成绩服务访问"\*\*\*\*和"允许成员身份服务访问"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-154">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-microsoft-teams-classes-lti-13-tool"></a><span data-ttu-id="214c3-155">添加Microsoft Teams类 LTI 1.3 工具</span><span class="sxs-lookup"><span data-stu-id="214c3-155">Add the Microsoft Teams Classes LTI 1.3 Tool</span></span>

1. <span data-ttu-id="214c3-156">从管理员 **面板中，** 选择 **LTI 工具提供程序**。</span><span class="sxs-lookup"><span data-stu-id="214c3-156">From the **Administrator Panel**, select **LTI Tool Providers**.</span></span>

2. <span data-ttu-id="214c3-157">选择 **注册 LTI 1.3 工具**。</span><span class="sxs-lookup"><span data-stu-id="214c3-157">Select **register LTI 1.3 Tool**.</span></span>

3. <span data-ttu-id="214c3-158">在" **客户端 ID"** 字段中，键入或复制并粘贴此 ID：</span><span class="sxs-lookup"><span data-stu-id="214c3-158">In the **Client ID** field, type or copy and paste this ID:</span></span>

   `027328b7-c2e3-4c9e-aaa1-07802dae6c89`

4. <span data-ttu-id="214c3-159">查看已预先填充的所有设置，在"工具状态 *"中选择* "已启用 *"。*</span><span class="sxs-lookup"><span data-stu-id="214c3-159">Review all settings that have been pre-populated and in *Tool Status* and select *Enabled.*</span></span>

5. <span data-ttu-id="214c3-160">在 **"机构策略"** 中，选择 **"课程、名称和\*\*\*\*电子邮件地址"中的"角色"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-160">In **Institution Policies**, select **Role in Course, Name,** and **Email Address**.</span></span> <span data-ttu-id="214c3-161">为 **两者选择"** 是"。</span><span class="sxs-lookup"><span data-stu-id="214c3-161">Select **Yes** for both.</span></span>

6. <span data-ttu-id="214c3-162">选择 **"允许成绩服务访问"\*\*\*\*和"允许成员身份服务访问"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-162">Select **Allow grade service access** and **Allow Membership Service Access**.</span></span>

## <a name="add-the-rest-api-tool"></a><span data-ttu-id="214c3-163">添加 REST API 工具</span><span class="sxs-lookup"><span data-stu-id="214c3-163">Add the REST API tool</span></span>

1. <span data-ttu-id="214c3-164">从管理员 **面板中**，导航到 **"集成"，** 然后选择 **"Rest API 集成"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-164">From the **Administrator Panel**, navigate to **Integrations** and select **Rest API Integrations**.</span></span>

2. <span data-ttu-id="214c3-165">选择 **"创建集成"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-165">Select **Create Integration**.</span></span>

3. <span data-ttu-id="214c3-166">在" **应用程序 ID"** 字段中，键入或复制并粘贴此 ID：</span><span class="sxs-lookup"><span data-stu-id="214c3-166">In the **Application ID** field, type or copy and paste this ID:</span></span>

   `f1561daa-1b21-4693-ba90-6c55f1a0eb41`

4. <span data-ttu-id="214c3-167">为此集成键入用户。</span><span class="sxs-lookup"><span data-stu-id="214c3-167">Type a user for this integration.</span></span>

   <span data-ttu-id="214c3-168">此用户将具有与应用程序关联的家庭 API 访问权限。</span><span class="sxs-lookup"><span data-stu-id="214c3-168">This user will be the one with home API access from which the application is associated.</span></span>

5. <span data-ttu-id="214c3-169">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="214c3-169">Select **Submit**.</span></span>

## <a name="add-the-cross-origin-resource-sharing"></a><span data-ttu-id="214c3-170">添加跨源资源共享</span><span class="sxs-lookup"><span data-stu-id="214c3-170">Add the Cross-Origin Resource Sharing</span></span>

1. <span data-ttu-id="214c3-171">从"**管理员"面板** 中，导航 **到"集成"，** 然后选择"\**跨源资源共享"。*</span><span class="sxs-lookup"><span data-stu-id="214c3-171">From the **Administrator panel**, navigate to **Integrations** and select \**Cross-origin Resource Sharing*.</span></span>

2. <span data-ttu-id="214c3-172">选择 **"创建配置"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-172">Select **Create Configuration**.</span></span>

3. <span data-ttu-id="214c3-173">在" **源** "字段中，键入复制并粘贴此 URL：</span><span class="sxs-lookup"><span data-stu-id="214c3-173">In the **Origin** field, type of copy and paste this URL:</span></span>

   `https://bb-ms-teams-ultra-ext.api.blackboard.com`

4. <span data-ttu-id="214c3-174">在" **允许的标题"** 字段中，键入 **Authorization**。</span><span class="sxs-lookup"><span data-stu-id="214c3-174">In the **Allowed Headers** field, type **Authorization**.</span></span>

5. <span data-ttu-id="214c3-175">设置为 **"可用**"**为"是"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-175">Set **Available** to **Yes**.</span></span>

6. <span data-ttu-id="214c3-176">选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="214c3-176">Select **Submit**.</span></span>

## <a name="configure-and-approve-microsoft-teams-classes-integration"></a><span data-ttu-id="214c3-177">配置和批准Microsoft Teams类集成</span><span class="sxs-lookup"><span data-stu-id="214c3-177">Configure and Approve Microsoft Teams classes Integration</span></span>

<span data-ttu-id="214c3-178">若要成功将你的"完成学习超"实例与Microsoft Teams类集成，你需要确保批准使用"完成"功能租户中访问的"Microsoft Azure应用程序"。</span><span class="sxs-lookup"><span data-stu-id="214c3-178">To successfully integrate your Blackboard Learn Ultra instance with Microsoft Teams classes, you'll need to make sure the Blackboard Learn Ultra application is approved for access within your Microsoft Azure tenant.</span></span> <span data-ttu-id="214c3-179">这一过程将需要由你的机构的全局管理员Microsoft 365完成。</span><span class="sxs-lookup"><span data-stu-id="214c3-179">This is a process that will need to be completed by your institution’s Microsoft 365 Global Admin.</span></span>

<span data-ttu-id="214c3-180">此过程可以在你在你的"你的"学习超实例"中配置 LTI 应用程序之前或之后完成。</span><span class="sxs-lookup"><span data-stu-id="214c3-180">This process can be done either before or after you have configured the LTI applications in your Blackboard Learn Ultra Instance.</span></span>

### <a name="before-configuring-the-lti-applications"></a><span data-ttu-id="214c3-181">配置 LTI 应用程序之前</span><span class="sxs-lookup"><span data-stu-id="214c3-181">Before Configuring the LTI Applications</span></span>

<span data-ttu-id="214c3-182">如果你在配置 LTI 集成之前选择批准"完成学习超极Teams类 Azure"应用，则需要重定向到 Microsoft Identity Platform Admin **Consent Endpoint**。</span><span class="sxs-lookup"><span data-stu-id="214c3-182">If you choose to approve the Blackboard Learn Ultra Teams Classes Azure app before configuring the LTI integrations, you'll need to redirect to the **Microsoft Identity Platform Admin Consent Endpoint**.</span></span> <span data-ttu-id="214c3-183">将显示 URL：</span><span class="sxs-lookup"><span data-stu-id="214c3-183">The URL is shown:</span></span>

`https://login.microsoftonline.com/{tenant}/adminconsent?client\_id=2d94989f-457a-47c1-a637-e75acdb11568`

> [!NOTE]
> <span data-ttu-id="214c3-184">将 **{Tenant}** 替换为特定机构Microsoft Azure租户 ID。</span><span class="sxs-lookup"><span data-stu-id="214c3-184">You’ll replace **{Tenant}** with your specific institutional Microsoft Azure tenant ID.</span></span>

### <a name="after-configuring-the-lti-applications"></a><span data-ttu-id="214c3-185">配置 LTI 应用程序后</span><span class="sxs-lookup"><span data-stu-id="214c3-185">After Configuring the LTI Applications</span></span>

1. <span data-ttu-id="214c3-186">在管理员 **面板上**，导航到"**工具和** 实用程序"，然后选择 **"Microsoft Teams管理员"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-186">On the **Administrator Panel**, navigate to **Tools and Utilities** and select **Microsoft Teams Integration Admin**.</span></span>

2. <span data-ttu-id="214c3-187">选择 **"启用Microsoft Teams"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-187">Select **Enable Microsoft Teams**.</span></span>

3. <span data-ttu-id="214c3-188">将 **Microsoft 租户 ID** 添加到可用文本字段中。</span><span class="sxs-lookup"><span data-stu-id="214c3-188">Add your **Microsoft Tenant ID** into the available text field.</span></span>

4. <span data-ttu-id="214c3-189">选择下列选项之一：</span><span class="sxs-lookup"><span data-stu-id="214c3-189">Choose one of the following options:</span></span>

   - <span data-ttu-id="214c3-190">如果应用已预先同意，将显示一个小的选中标记。</span><span class="sxs-lookup"><span data-stu-id="214c3-190">If the app has pre-consent, it will show a small checkmark.</span></span> <span data-ttu-id="214c3-191">如果显示选中标记，请选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-191">If the checkmark appears, select **Submit**.</span></span>

   - <span data-ttu-id="214c3-192">如果同意尚未获得批准，请按照所述的步骤生成许可 URL 并将其发送给全局管理员Microsoft 365进行审批。</span><span class="sxs-lookup"><span data-stu-id="214c3-192">If consent hasn’t been approved, follow the steps described to generate the URL for consent and send it to the Microsoft 365 Global Admin for approval.</span></span>

5. <span data-ttu-id="214c3-193">确认审批后，选择"**重试** 以确认"，然后选择"提交 **"。**</span><span class="sxs-lookup"><span data-stu-id="214c3-193">Once you've confirmation of approval, select **Retry** to confirm, and then select **Submit**.</span></span>
