---
title: 通信合规性入门
description: 设置通信合规性策略，以配置用户用户通信以供审阅。
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: Admin
ms.topic: article
f1_keywords:
- ms.o365.cc.SupervisoryReview
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- Strat_O365_IP
- m365-security-compliance
- m365solution-insiderrisk
- m365initiative-compliance
search.appverid:
- MET150
- MOE150
ms.openlocfilehash: 3e84c3266dd802fb6cab12db0c20773838b4e2a9
ms.sourcegitcommit: b169f6ad3e44a7fcebf77f43be9eb5edd84ea5ef
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/28/2021
ms.locfileid: "52077185"
---
# <a name="get-started-with-communication-compliance"></a><span data-ttu-id="f96a5-103">通信合规性入门</span><span class="sxs-lookup"><span data-stu-id="f96a5-103">Get started with communication compliance</span></span>

<span data-ttu-id="f96a5-104">使用通信合规性策略，以识别用户通信，供内部或外部审阅者检查。</span><span class="sxs-lookup"><span data-stu-id="f96a5-104">Use communication compliance policies to identify user communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="f96a5-105">有关通信合规性策略如何帮助监视组织内通信的详细信息，请参阅 [Microsoft 365 中的通信合规性策略](communication-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-105">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span> <span data-ttu-id="f96a5-106">如果希望查看 Contoso 如何快速配置通信合规性策略以监视 Microsoft Teams、Exchange Online 和 Yammer 通信中的冒犯性语言，请查看此 [案例研究](communication-compliance-case-study.md)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-106">If you'd like to review how Contoso quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams, Exchange Online, and Yammer communications, check out this [case study](communication-compliance-case-study.md).</span></span>

## <a name="subscriptions-and-licensing"></a><span data-ttu-id="f96a5-107">订阅和许可</span><span class="sxs-lookup"><span data-stu-id="f96a5-107">Subscriptions and licensing</span></span>

<span data-ttu-id="f96a5-108">在开始通信合规性入门之前，应该先确认 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 以及任何加载项。</span><span class="sxs-lookup"><span data-stu-id="f96a5-108">Before you get started with communication compliance, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="f96a5-109">若要访问和使用通信合规性，组织必须具有以下订阅或加载项之一：</span><span class="sxs-lookup"><span data-stu-id="f96a5-109">To access and use communication compliance, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="f96a5-110">Microsoft 365 E5 订阅（付费或试用版本）</span><span class="sxs-lookup"><span data-stu-id="f96a5-110">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="f96a5-111">Microsoft 365 E3 订阅 + Microsoft 365 E5 合规加载项</span><span class="sxs-lookup"><span data-stu-id="f96a5-111">Microsoft 365 E3 subscription + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="f96a5-112">Microsoft 365 E3 订阅 + Microsoft 365 E5 预览体验成员风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="f96a5-112">Microsoft 365 E3 subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="f96a5-113">Microsoft 365 A5 订阅（付费或试用版本）</span><span class="sxs-lookup"><span data-stu-id="f96a5-113">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="f96a5-114">Microsoft 365 A3 订阅 + Microsoft 365 A5 合规加载项</span><span class="sxs-lookup"><span data-stu-id="f96a5-114">Microsoft 365 A3 subscription + the Microsoft 365 A5 Compliance add-on</span></span>
- <span data-ttu-id="f96a5-115">Microsoft 365 A3 订阅 + Microsoft 365 A5 预览体验成员风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="f96a5-115">Microsoft 365 A3 subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="f96a5-116">Microsoft 365 G5 订阅（付费或试用版本）</span><span class="sxs-lookup"><span data-stu-id="f96a5-116">Microsoft 365 G5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="f96a5-117">Microsoft 365 G5 订阅 + Microsoft 365 G5 合规加载项</span><span class="sxs-lookup"><span data-stu-id="f96a5-117">Microsoft 365 G5 subscription + the Microsoft 365 G5 Compliance add-on</span></span>
- <span data-ttu-id="f96a5-118">Microsoft 365 G5 订阅 + Microsoft 365 G5 预览体验成员风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="f96a5-118">Microsoft 365 G5 subscription + the Microsoft 365 G5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="f96a5-119">Office 365 企业版 E5 订阅（付费或试用版本）</span><span class="sxs-lookup"><span data-stu-id="f96a5-119">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="f96a5-120">Office 365 A5 订阅（付费或试用版本）</span><span class="sxs-lookup"><span data-stu-id="f96a5-120">Office 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="f96a5-121">Office 365 企业版 E3 订阅 + Office 365 高级合规版加载项（新订阅已不再可用，请参阅注释）</span><span class="sxs-lookup"><span data-stu-id="f96a5-121">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="f96a5-122">通信合规性策略中包括的用户必须获得以上许可证之一。</span><span class="sxs-lookup"><span data-stu-id="f96a5-122">Users included in communication compliance policies must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="f96a5-123">Office 365 高级合规版已不再作为独立订阅销售。</span><span class="sxs-lookup"><span data-stu-id="f96a5-123">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="f96a5-124">当前订阅到期后，客户应过渡到以上订阅之一，其中包含了相同的或其它合规性功能。</span><span class="sxs-lookup"><span data-stu-id="f96a5-124">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="f96a5-125">如果你没有现有的 Office 365 企业版 E5 套餐，并且想要尝试通信合规性，可以 [添加 Microsoft 365](/office365/admin/try-or-buy-microsoft-365) 到现有订阅，或 [注册试用](https://www.microsoft.com/microsoft-365/enterprise) Office 365 企业版 E5。</span><span class="sxs-lookup"><span data-stu-id="f96a5-125">If you don't have an existing Office 365 Enterprise E5 plan and want to try communication compliance, you can [add Microsoft 365](/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Office 365 Enterprise E5.</span></span>

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a><span data-ttu-id="f96a5-126">步骤 1（必选）：启用通信合规性权限</span><span class="sxs-lookup"><span data-stu-id="f96a5-126">Step 1 (required): Enable permissions for communication compliance</span></span>

>[!Important]
><span data-ttu-id="f96a5-127">默认状态下，全局管理员没有对通信合规性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="f96a5-127">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="f96a5-128">在可以访问任何通信合规性功能之前，必须在此步骤中分配角色。</span><span class="sxs-lookup"><span data-stu-id="f96a5-128">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span> <span data-ttu-id="f96a5-129">配置角色组之后，可能需要长达 30 分钟时间将角色组权限应用到整个组织的已分配用户。</span><span class="sxs-lookup"><span data-stu-id="f96a5-129">After configuring your role groups, it may take up to 30 minutes for the role group permissions to apply to assigned users across your organization.</span></span>

<span data-ttu-id="f96a5-130">共有 5 个角色组，用于配置权限以管理通信合规性功能。</span><span class="sxs-lookup"><span data-stu-id="f96a5-130">There are five role groups used to configure permissions to manage communication compliance features.</span></span> <span data-ttu-id="f96a5-131">若要在 Microsoft 365 合规中心中将 **通信合规性** 作为菜单选项提供并继续执行这些配置步骤，必须将你分配给 *通信符合性* 或 *通信符合性管理员* 角色组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-131">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center and to continue with these configuration steps, you must be assigned to the *Communication Compliance* or *Communication Compliance Admin* role groups.</span></span> <span data-ttu-id="f96a5-132">若要在初始配置后访问和管理通信合规性功能，用户必须是至少一个通信合规性角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="f96a5-132">To access and manage communication compliance features after initial configuration, users must be a member of at least one communication compliance role group.</span></span>

<span data-ttu-id="f96a5-133">根据希望管理通信策略和警报的方式，你需要将用户分配到特定的角色组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-133">Depending on how you wish to manage communication policies and alerts, you'll need to assign users to specific role groups.</span></span> <span data-ttu-id="f96a5-134">可以选择将具有不同合规性职责的用户分配给特定的角色组，以管理不同区域的通信合规性功能。</span><span class="sxs-lookup"><span data-stu-id="f96a5-134">You have the option to assign users with different compliance responsibilities to specific role groups to manage different areas of communication compliance features.</span></span> <span data-ttu-id="f96a5-135">或者可以决定将指定管理员、分析者、调查者和查看者的所有用户账户分配到 *通信合规性* 角色组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-135">Or you may decide to assign all user accounts for designated administrators, analysts, investigators, and viewers to the *Communication Compliance* role group.</span></span> <span data-ttu-id="f96a5-136">使用单个角色组或多个角色组，以充分符合你的合规性管理要求。</span><span class="sxs-lookup"><span data-stu-id="f96a5-136">Use a single role group or multiple role groups to best fit your compliance management requirements.</span></span>

<span data-ttu-id="f96a5-137">配置通信合规性时，请从这些角色组中进行选择：</span><span class="sxs-lookup"><span data-stu-id="f96a5-137">Choose from these role group options when configuring communication compliance:</span></span>

| <span data-ttu-id="f96a5-138">角色</span><span class="sxs-lookup"><span data-stu-id="f96a5-138">Role</span></span> | <span data-ttu-id="f96a5-139">角色权限</span><span class="sxs-lookup"><span data-stu-id="f96a5-139">Role permissions</span></span> |
|:-----|:-----|
| <span data-ttu-id="f96a5-140">**通信合规性**</span><span class="sxs-lookup"><span data-stu-id="f96a5-140">**Communication Compliance**</span></span> | <span data-ttu-id="f96a5-141">使用此角色组在单个组中管理组织的通信合规性。</span><span class="sxs-lookup"><span data-stu-id="f96a5-141">Use this role group to manage communication compliance for your organization in a single group.</span></span> <span data-ttu-id="f96a5-142">通过添加指定管理员、分析者、调查者和查看者的所有用户账户，可以在单个组中配置通信合规性权限。</span><span class="sxs-lookup"><span data-stu-id="f96a5-142">By adding all user accounts for designated administrators, analysts, investigators, and viewers, you can configure communication compliance permissions in a single group.</span></span> <span data-ttu-id="f96a5-143">此角色组包含所有通信合规性权限角色。</span><span class="sxs-lookup"><span data-stu-id="f96a5-143">This role group contains all the communication compliance permission roles.</span></span> <span data-ttu-id="f96a5-144">这一配置是通信合规性快速入门的最简单方式，非常适合不需要为单独用户组定义单独权限的组织。</span><span class="sxs-lookup"><span data-stu-id="f96a5-144">This configuration is the easiest way to quickly get started with communication compliance and is a good fit for organizations that do not need separate permissions defined for separate groups of users.</span></span> |
| <span data-ttu-id="f96a5-145">**通信合规性管理员**</span><span class="sxs-lookup"><span data-stu-id="f96a5-145">**Communication Compliance Admin**</span></span> | <span data-ttu-id="f96a5-146">使用此角色组进行通信合规性初始配置，后期可将通信合规性管理员隔离到已定义组中。</span><span class="sxs-lookup"><span data-stu-id="f96a5-146">Use this role group to initially configure communication compliance and later to segregate communication compliance administrators into a defined group.</span></span> <span data-ttu-id="f96a5-147">分配到此角色组的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。</span><span class="sxs-lookup"><span data-stu-id="f96a5-147">Users assigned to this role group can create, read, update, and delete communication compliance policies, global settings, and role group assignments.</span></span> <span data-ttu-id="f96a5-148">分配到此角色组的用户无法查看消息警报。</span><span class="sxs-lookup"><span data-stu-id="f96a5-148">Users assigned to this role group cannot view message alerts.</span></span> |
| <span data-ttu-id="f96a5-149">**通信合规性分析者**</span><span class="sxs-lookup"><span data-stu-id="f96a5-149">**Communication Compliance Analyst**</span></span> | <span data-ttu-id="f96a5-150">使用此组向执行通信合规性分析者操作的用户分配权限。</span><span class="sxs-lookup"><span data-stu-id="f96a5-150">Use this group to assign permissions to users that will act as communication compliance analysts.</span></span> <span data-ttu-id="f96a5-151">分配到此角色组的用户可以查看分配其为审阅者的策略，查看消息元数据（而不是消息内容）、升级到其他审阅者，或向用户发送通知。</span><span class="sxs-lookup"><span data-stu-id="f96a5-151">Users assigned to this role group can view policies where they are assigned as Reviewers, view message metadata (not message content), escalate to additional reviewers, or send notifications to users.</span></span> <span data-ttu-id="f96a5-152">分析者不能解决挂起的警报。</span><span class="sxs-lookup"><span data-stu-id="f96a5-152">Analysts cannot resolve pending alerts.</span></span> |
| <span data-ttu-id="f96a5-153">**通信合规性调查者**</span><span class="sxs-lookup"><span data-stu-id="f96a5-153">**Communication Compliance Investigator**</span></span> | <span data-ttu-id="f96a5-154">使用此组向执行通信合规性调查者操作的用户分配权限。</span><span class="sxs-lookup"><span data-stu-id="f96a5-154">Use this group to assign permissions to users that will act as communication compliance investigators.</span></span> <span data-ttu-id="f96a5-155">分配到此角色组的用户可以查看消息元数据和内容、升级到其他审阅者、升级到高级 eDiscovery 案例、向用户发送通知、以及解决警报。</span><span class="sxs-lookup"><span data-stu-id="f96a5-155">Users assigned to this role group can view message metadata and content, escalate to additional reviewers, escalate to an Advanced eDiscovery case, send notifications to users, and resolve the alert.</span></span> |
| <span data-ttu-id="f96a5-156">**通信合规性查看者**</span><span class="sxs-lookup"><span data-stu-id="f96a5-156">**Communication Compliance Viewer**</span></span> | <span data-ttu-id="f96a5-157">使用此组向管理通信报告的用户分配权限。</span><span class="sxs-lookup"><span data-stu-id="f96a5-157">Use this group to assign permissions to users that will manage communication reports.</span></span> <span data-ttu-id="f96a5-158">分配到此角色组的用户可以访问通信合规性主页上的所有报告小组件，并且可以查看所有通信合规性报告。</span><span class="sxs-lookup"><span data-stu-id="f96a5-158">Users assigned to this role group can access all reporting widgets on the communication compliance home page and can view all communication compliance reports.</span></span> |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a><span data-ttu-id="f96a5-159">选项 1： 将所有合规用户分配到通信合规性角色组</span><span class="sxs-lookup"><span data-stu-id="f96a5-159">Option 1: Assign all compliance users to the Communication Compliance role group</span></span>

1. <span data-ttu-id="f96a5-160">使用 Microsoft 365 组织中的管理员账户凭据登录 [https://protection.office.com/permissions](https://protection.office.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-160">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="f96a5-161">在安全 &amp; 合规中心中，转到“**权限**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-161">In the Security &amp; Compliance Center, go to **Permissions**.</span></span> <span data-ttu-id="f96a5-162">选择链接以查看和管理 Office 365 中的角色。</span><span class="sxs-lookup"><span data-stu-id="f96a5-162">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="f96a5-163">选择“*通信合规性*”角色组，然后选择“**编辑角色组**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-163">Select the *Communication Compliance* role group, then select **Edit role group**.</span></span>

4. <span data-ttu-id="f96a5-164">从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-164">Select **Choose members** from the left navigation pane, then select **Edit**.</span></span>

5. <span data-ttu-id="f96a5-165">选择“**添加**”，然后选中希望添加到 *通信合规性* 角色组的所有用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="f96a5-165">Select **Add** and then select the checkbox for all users you want to add to the *Communication Compliance* role group.</span></span>

6. <span data-ttu-id="f96a5-166">选择“**添加**”，然后选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-166">Select **Add**, then select **Done**.</span></span>

7. <span data-ttu-id="f96a5-167">选择“**保存**”以将用户添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-167">Select **Save** to add the users to the role group.</span></span> <span data-ttu-id="f96a5-168">选择“**关闭**”以完成步骤</span><span class="sxs-lookup"><span data-stu-id="f96a5-168">Select **Close** to complete the steps</span></span>

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a><span data-ttu-id="f96a5-169">选项 2： 将用户分配到特定通信合规性角色组</span><span class="sxs-lookup"><span data-stu-id="f96a5-169">Option 2: Assign users to specific communication compliance role groups</span></span>

<span data-ttu-id="f96a5-170">使用此选项将用户分配到特定角色组，以区分组织中不同用户的通信合规性访问和职责。</span><span class="sxs-lookup"><span data-stu-id="f96a5-170">Use this option to assign users to specific role groups to segment communication compliance access and responsibilities among different users in your organization.</span></span>

1. <span data-ttu-id="f96a5-171">使用 Microsoft 365 组织中的管理员账户凭据登录 [https://protection.office.com/permissions](https://protection.office.com/permissions)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-171">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="f96a5-172">在安全 &amp; 合规中心中，转到“**权限**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-172">In the Security &amp; Compliance Center, go to **Permissions**.</span></span> <span data-ttu-id="f96a5-173">选择链接以查看和管理 Office 365 中的角色。</span><span class="sxs-lookup"><span data-stu-id="f96a5-173">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="f96a5-174">选择通信合规性角色组之一，然后选择“**编辑角色组**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-174">Select one of the communication compliance role groups, then select **Edit role group**.</span></span>

4. <span data-ttu-id="f96a5-175">从左侧导航窗格中选择“**选择成员**”，然后选择“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-175">Select **Choose members** from the left navigation pane, then select **Edit**.</span></span>

5. <span data-ttu-id="f96a5-176">选择“**添加**”，然后选中希望添加到角色组的所有用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="f96a5-176">Select **Add** and then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="f96a5-177">选择“**添加**”，然后选择“**完成**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-177">Select **Add**, then select **Done**.</span></span>

7. <span data-ttu-id="f96a5-178">选择“**保存**”以将用户添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-178">Select **Save** to add the users to the role group.</span></span>

8. <span data-ttu-id="f96a5-179">选择下一个通信合规性角色组，然后为每个需要的角色组重复步骤 4-7。</span><span class="sxs-lookup"><span data-stu-id="f96a5-179">Select the next communication compliance role group, then repeat steps 4-7 for each required role group.</span></span>

9. <span data-ttu-id="f96a5-180">选择“**关闭**”以完成步骤。</span><span class="sxs-lookup"><span data-stu-id="f96a5-180">Select **Close** to complete the steps.</span></span>

<span data-ttu-id="f96a5-181">有关角色组和权限的详细信息，请参阅 [合规中心中的权限](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-181">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-2-required-enable-the-audit-log"></a><span data-ttu-id="f96a5-182">步骤 2（必选）：启用审核日志</span><span class="sxs-lookup"><span data-stu-id="f96a5-182">Step 2 (required): Enable the audit log</span></span>

<span data-ttu-id="f96a5-183">通信合规性需要审核日志显示警报和跟踪审阅者采取的修正操作。</span><span class="sxs-lookup"><span data-stu-id="f96a5-183">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="f96a5-184">审核日志是与已定义的组织策略，或任何时刻的通信合规性策略更改相关联的所有活动摘要。</span><span class="sxs-lookup"><span data-stu-id="f96a5-184">The audit logs are a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="f96a5-185">有关启用审核的逐步操作说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-185">For step-by-step instructions to turn on auditing, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="f96a5-186">打开审核之后，将显示一条消息，内容为正在准备审核日志，你可以在准备完成后几个小时内运行搜索。</span><span class="sxs-lookup"><span data-stu-id="f96a5-186">After you turn on auditing, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="f96a5-187">此操作只需要执行一次。</span><span class="sxs-lookup"><span data-stu-id="f96a5-187">You only have to do this action once.</span></span> <span data-ttu-id="f96a5-188">有关使用审核日志的详细信息，请参阅 [搜索审核日志](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-188">For more information about the using the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a><span data-ttu-id="f96a5-189">步骤 3（可选）：设置通信合规性组</span><span class="sxs-lookup"><span data-stu-id="f96a5-189">Step 3 (optional): Set up groups for communication compliance</span></span>

 <span data-ttu-id="f96a5-190">创建通信合规性策略时，即定义了要审阅谁的通信和谁来执行审阅。</span><span class="sxs-lookup"><span data-stu-id="f96a5-190">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="f96a5-191">在策略中，可以使用电子邮件地址来标识个人或人员组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-191">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="f96a5-192">若要简化设置，可以为接受通信审阅的人员创建组，也可以为审阅这些通信的人员创建组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-192">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="f96a5-193">如果正在使用组，可能需要若干个组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-193">If you're using groups, you may need several.</span></span> <span data-ttu-id="f96a5-194">例如，如果希望监视两个不同组人员之间的通信，或如果希望指定一个不会受到监督的组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-194">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="f96a5-195">使用下图帮助配置组织中的组以实施通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="f96a5-195">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="f96a5-196">**策略成员**</span><span class="sxs-lookup"><span data-stu-id="f96a5-196">**Policy Member**</span></span> | <span data-ttu-id="f96a5-197">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="f96a5-197">**Supported Groups**</span></span> | <span data-ttu-id="f96a5-198">**不支持的组**</span><span class="sxs-lookup"><span data-stu-id="f96a5-198">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="f96a5-199">受监督用户</span><span class="sxs-lookup"><span data-stu-id="f96a5-199">Supervised users</span></span> <br> <span data-ttu-id="f96a5-200">不受监督用户</span><span class="sxs-lookup"><span data-stu-id="f96a5-200">Non-supervised users</span></span> | <span data-ttu-id="f96a5-201">通讯组</span><span class="sxs-lookup"><span data-stu-id="f96a5-201">Distribution groups</span></span> <br> <span data-ttu-id="f96a5-202">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="f96a5-202">Microsoft 365 Groups</span></span> | <span data-ttu-id="f96a5-203">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="f96a5-203">Dynamic distribution groups</span></span> <br> <span data-ttu-id="f96a5-204">嵌套通讯组</span><span class="sxs-lookup"><span data-stu-id="f96a5-204">Nested distribution groups</span></span> <br> <span data-ttu-id="f96a5-205">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="f96a5-205">Mail-enabled security groups</span></span> <br> <span data-ttu-id="f96a5-206">Microsoft 365动态成员身份的组</span><span class="sxs-lookup"><span data-stu-id="f96a5-206">Microsoft 365 groups with dynamic membership</span></span> |
| <span data-ttu-id="f96a5-207">审阅者</span><span class="sxs-lookup"><span data-stu-id="f96a5-207">Reviewers</span></span> | <span data-ttu-id="f96a5-208">无</span><span class="sxs-lookup"><span data-stu-id="f96a5-208">None</span></span> | <span data-ttu-id="f96a5-209">通讯组</span><span class="sxs-lookup"><span data-stu-id="f96a5-209">Distribution groups</span></span> <br> <span data-ttu-id="f96a5-210">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="f96a5-210">Dynamic distribution groups</span></span> <br> <span data-ttu-id="f96a5-211">嵌套通讯组</span><span class="sxs-lookup"><span data-stu-id="f96a5-211">Nested distribution groups</span></span> <br> <span data-ttu-id="f96a5-212">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="f96a5-212">Mail-enabled security groups</span></span> |
  
<span data-ttu-id="f96a5-213">在策略中分配通讯组时，策略会监视通讯组每个用户的所有电子邮件和 Teams 聊天。</span><span class="sxs-lookup"><span data-stu-id="f96a5-213">When you assign a distribution group in the policy, the policy monitors all emails and Teams chats from each user in distribution group.</span></span> <span data-ttu-id="f96a5-214">在策略中分配 Microsoft 365 组时，策略会监视发送到该组的所有电子邮件和 Teams 聊天，而不是每个团队成员收到的单个电子邮件和聊天。</span><span class="sxs-lookup"><span data-stu-id="f96a5-214">When you assign a Microsoft 365 group in the policy, the policy monitors all emails and Teams chats sent to that group, not the individual emails and chats received by each group member.</span></span>

<span data-ttu-id="f96a5-215">如果你是具有 Exchange 本地部署或外部电子邮件提供商的组织，并且想要监视用户的 Microsoft Teams 聊天，则必须创建一个通讯组以便具有本地或外部邮箱的用户进行监视。</span><span class="sxs-lookup"><span data-stu-id="f96a5-215">If you're an organization with an Exchange on-premises deployment or an external email provider and you want to monitor Microsoft Teams chats for your users, you must create a distribution group for the users with on-premises or external mailboxes to monitor.</span></span> <span data-ttu-id="f96a5-216">在这些步骤的稍后部分，你将此通讯组分配为策略向导中的 **受监督用户和组**。</span><span class="sxs-lookup"><span data-stu-id="f96a5-216">Later in these steps, you'll assign this distribution group as the **Supervised users and groups** selection in the policy wizard.</span></span>

<span data-ttu-id="f96a5-217">若要在大型企业组织中管理受监督的用户，可能需要监视大型组的所有用户。</span><span class="sxs-lookup"><span data-stu-id="f96a5-217">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="f96a5-218">可使用 PowerShell 为已分配组配置全局通信合规性策略的通讯组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-218">You can use PowerShell to configure a distribution group for a global communication compliance policy for the assigned group.</span></span> <span data-ttu-id="f96a5-219">这样，可以使用一个策略监视成千上万个用户，并在新员工加入组织时保持通信合规性策略的更新。</span><span class="sxs-lookup"><span data-stu-id="f96a5-219">This enables you to monitor thousands of users with a single policy and keep the communication compliance policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="f96a5-220">为全局通信合规性策略创建一个专用的 [通讯组](/powershell/module/exchange/new-distributiongroup)，该策略具有以下属性：确保此通讯组未用于其他目的或其他 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="f96a5-220">Create a dedicated [distribution group](/powershell/module/exchange/new-distributiongroup) for your global communication compliance policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="f96a5-221">**MemberDepartRestriction = Closed**。</span><span class="sxs-lookup"><span data-stu-id="f96a5-221">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="f96a5-222">确保用户无法将自己从通讯组中删除。</span><span class="sxs-lookup"><span data-stu-id="f96a5-222">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="f96a5-223">**MemberJoinRestriction = Closed**。</span><span class="sxs-lookup"><span data-stu-id="f96a5-223">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="f96a5-224">确保用户无法将自己添加到通讯组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-224">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="f96a5-225">**ModerationEnabled = True**。</span><span class="sxs-lookup"><span data-stu-id="f96a5-225">**ModerationEnabled = True**.</span></span> <span data-ttu-id="f96a5-226">确保发送到此组的所有邮件都受制于审批，并且组未用于在通信合规性策略配置外部进行通信。</span><span class="sxs-lookup"><span data-stu-id="f96a5-226">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the communication compliance policy configuration.</span></span>

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. <span data-ttu-id="f96a5-227">选择未使用的 [Exchange 自定义属性](/Exchange/recipients/mailbox-custom-attributes) 以跟踪添加到组织内通信合规性策略的用户。</span><span class="sxs-lookup"><span data-stu-id="f96a5-227">Select an unused [Exchange custom attribute](/Exchange/recipients/mailbox-custom-attributes) to track users added to the communication compliance policy in your organization.</span></span>

3. <span data-ttu-id="f96a5-228">按定期计划运行以下 PowerShell 脚本，将用户添加到通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="f96a5-228">Run the following PowerShell script on a recurring schedule to add users to the communication compliance policy:</span></span>

    ```PowerShell
    $Mbx = (Get-Mailbox -RecipientTypeDetails UserMailbox -ResultSize Unlimited -Filter {CustomAttribute9 -eq $Null})
    $i = 0
    ForEach ($M in $Mbx) 
    {
      Write-Host "Adding" $M.DisplayName
      Add-DistributionGroupMember -Identity <your group name> -Member $M.DistinguishedName -ErrorAction SilentlyContinue
      Set-Mailbox -Identity $M.Alias -<your custom attribute name> SRAdded 
      $i++
    }
    Write-Host $i "Mailboxes added to supervisory review distribution group."
    ```

<span data-ttu-id="f96a5-229">有关设置组的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="f96a5-229">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="f96a5-230">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="f96a5-230">Create and manage distribution groups</span></span>](/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="f96a5-231">Microsoft 365 组概述</span><span class="sxs-lookup"><span data-stu-id="f96a5-231">Overview of Microsoft 365 Groups</span></span>](/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a><span data-ttu-id="f96a5-232">步骤 4（可选）：验证 Yammer 租户是否处于本机模式</span><span class="sxs-lookup"><span data-stu-id="f96a5-232">Step 4 (optional): Verify your Yammer tenant is in Native Mode</span></span>

<span data-ttu-id="f96a5-233">在本机模式下，所有 Yammer 用户都在 Azure Active Directory (Azure AD) 中，所有组都是 Office 365 组，并且所有文件都存储在 SharePoint Online 中。</span><span class="sxs-lookup"><span data-stu-id="f96a5-233">In Native Mode, all Yammer users are in Azure Active Directory (Azure AD), all groups are Office 365 Groups, and all files are stored in SharePoint Online.</span></span> <span data-ttu-id="f96a5-234">你的 Yammer 租户必须为本机模式，以便通信合规性策略可以扫描和识别 Yammer 中私人消息和社区对话中的风险对话。</span><span class="sxs-lookup"><span data-stu-id="f96a5-234">Your Yammer tenant must be in Native Mode for communication compliance policies to scan and identify risky conversations in private messages and community conversations in Yammer.</span></span>

<span data-ttu-id="f96a5-235">有关以本机模式配置 Yammer 详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="f96a5-235">For more information about configuring Yammer in Native Mode, see:</span></span>

- [<span data-ttu-id="f96a5-236">Microsoft 365 中 Yammer 本机模式概述</span><span class="sxs-lookup"><span data-stu-id="f96a5-236">Overview of Yammer Native Mode in Microsoft 365</span></span>](/yammer/configure-your-yammer-network/overview-native-mode)
- [<span data-ttu-id="f96a5-237">配置适用于 Microsoft 365 本机模式的 Yammer 网络</span><span class="sxs-lookup"><span data-stu-id="f96a5-237">Configure your Yammer network for Native Mode for Microsoft 365</span></span>](/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a><span data-ttu-id="f96a5-238">步骤 5（必需）：创建通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="f96a5-238">Step 5 (required): Create a communication compliance policy</span></span>
  
>[!Important]
><span data-ttu-id="f96a5-239">不支持使用 PowerShell 创建和管理通信合规性策略。</span><span class="sxs-lookup"><span data-stu-id="f96a5-239">Using PowerShell to create and manage communication compliance policies is not supported.</span></span> <span data-ttu-id="f96a5-240">若要创建和管理这些策略，必须使用 [Microsoft 365 通信合规性解决方案](https://compliance.microsoft.com/supervisoryreview) 中的策略管理控件。</span><span class="sxs-lookup"><span data-stu-id="f96a5-240">To create and manage these policies, you must use the policy management controls in the [Microsoft 365 communication compliance solution](https://compliance.microsoft.com/supervisoryreview).</span></span>

1. <span data-ttu-id="f96a5-241">使用 Microsoft 365 组织中的管理员账户凭据登录 [https://compliance.microsoft.com](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-241">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="f96a5-242">在 Microsoft 365 合规中心中，选择“**通信合规性**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-242">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="f96a5-243">选择“**策略**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="f96a5-243">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="f96a5-244">选择“**创建策略**”从模板创建和配置新策略，或创建和配置自定义策略。</span><span class="sxs-lookup"><span data-stu-id="f96a5-244">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="f96a5-245">如果选择策略模板来创建策略，将需要：</span><span class="sxs-lookup"><span data-stu-id="f96a5-245">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="f96a5-246">确认或更新策略名称。</span><span class="sxs-lookup"><span data-stu-id="f96a5-246">Confirm or update the policy name.</span></span> <span data-ttu-id="f96a5-247">创建策略后，不能更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="f96a5-247">Policy names cannot be changed once the policy is created.</span></span>

    - <span data-ttu-id="f96a5-248">选择要监督的用户或组，包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-248">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span> <span data-ttu-id="f96a5-249">使用利益冲突模板时，需要选择两个组或两个用户来进行内部通信监视。</span><span class="sxs-lookup"><span data-stu-id="f96a5-249">When using the conflict of interest template, you'll select two groups or two users to monitor for internal communications.</span></span>

    - <span data-ttu-id="f96a5-250">选择该策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="f96a5-250">Choose the reviewers for the policy.</span></span> <span data-ttu-id="f96a5-251">审阅者是单个用户，所有审阅者都必须拥有在 Exchange Online 上托管的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f96a5-251">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span> <span data-ttu-id="f96a5-252">此处添加的审阅者是可在调查和修正工作流中升级警报时选择的审阅者。</span><span class="sxs-lookup"><span data-stu-id="f96a5-252">Reviewers added here are the reviewers that you can choose from when escalating an alert in the investigation and remediation workflow.</span></span> <span data-ttu-id="f96a5-253">审阅者添加到策略时，他们会自动收到一封电子邮件，通知他们分配到此策略，并提供有关审阅过程的信息的链接。</span><span class="sxs-lookup"><span data-stu-id="f96a5-253">When reviewers are added to a policy, they automatically receive an email message that notifies them of the assignment to the policy and provides links to information about the review process.</span></span>

    - <span data-ttu-id="f96a5-254">选择有限条件字段，通常是要应用于该策略的敏感信息类型或关键字词典。</span><span class="sxs-lookup"><span data-stu-id="f96a5-254">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    >[!NOTE]
    ><span data-ttu-id="f96a5-255">如果要启用光学字符识别 [ (OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview)以扫描邮件中嵌入或附加的图像，以找到符合策略条件的打印或手写文本，请选择"自定义策略条件和百分比"，并启用"从图像中提取打印或  >  **手写** 文本"进行评估。</span><span class="sxs-lookup"><span data-stu-id="f96a5-255">If you want to enable [optical character recognition (OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) to scan embedded or attached images in messages for printed or handwritten text that match policy conditions, select **Customize policy** > **Conditions and percentage** and enable **Extract printed or handwritten text from images for evaluation**.</span></span>

    <span data-ttu-id="f96a5-256">如果选择使用策略向导创建自定义策略，将需要：</span><span class="sxs-lookup"><span data-stu-id="f96a5-256">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="f96a5-257">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="f96a5-257">Give the policy a name and description.</span></span> <span data-ttu-id="f96a5-258">创建策略后，无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="f96a5-258">Policy names can't be changed once the policy is created.</span></span>

    - <span data-ttu-id="f96a5-259">选择要监视的用户或组，包括你组织中所有用户、特定用户和组，或者希望排除的其他用户和组。</span><span class="sxs-lookup"><span data-stu-id="f96a5-259">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span>

    - <span data-ttu-id="f96a5-260">选择该策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="f96a5-260">Choose the reviewers for the policy.</span></span> <span data-ttu-id="f96a5-261">审阅者是单个用户，所有审阅者都必须拥有在 Exchange Online 上托管的邮箱。</span><span class="sxs-lookup"><span data-stu-id="f96a5-261">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span> <span data-ttu-id="f96a5-262">此处添加的审阅者是可在调查和修正工作流中升级警报时选择的审阅者。</span><span class="sxs-lookup"><span data-stu-id="f96a5-262">Reviewers added here are the reviewers that you can choose from when escalating an alert in the investigation and remediation workflow.</span></span> <span data-ttu-id="f96a5-263">审阅者添加到策略时，他们会自动收到一封电子邮件，通知他们分配到此策略，并提供有关审阅过程的信息的链接。</span><span class="sxs-lookup"><span data-stu-id="f96a5-263">When reviewers are added to a policy, they automatically receive an email message that notifies them of the assignment to the policy and provides links to information about the review process.</span></span>

    - <span data-ttu-id="f96a5-264">选择要扫描的信道，包括 Exchange、Microsoft Teams、Yammer 或 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="f96a5-264">Choose the communication channels to scan, including Exchange, Microsoft Teams, Yammer, or Skype for Business.</span></span> <span data-ttu-id="f96a5-265">如果在 Microsoft 365 中配置了连接器，还可选择扫描第三方源。</span><span class="sxs-lookup"><span data-stu-id="f96a5-265">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>

    - <span data-ttu-id="f96a5-266">选择要监视的通信方向，包括入站、出站或内部通信。</span><span class="sxs-lookup"><span data-stu-id="f96a5-266">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>

    - <span data-ttu-id="f96a5-267">定义通信合规性策略 [条件](communication-compliance-feature-reference.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-267">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="f96a5-268">可以从邮件地址、关键字、文件类型和大小匹配条件中进行选择。</span><span class="sxs-lookup"><span data-stu-id="f96a5-268">You can choose from message address, keyword, file types, and size match conditions.</span></span>

    - <span data-ttu-id="f96a5-269">选择是否希望包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="f96a5-269">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="f96a5-270">此步骤可用于选择默认和自定义敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="f96a5-270">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="f96a5-271">在通信合规性策略向导中，从现有自定义敏感信息类型或自定义关键字词典进行选取。</span><span class="sxs-lookup"><span data-stu-id="f96a5-271">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="f96a5-272">如果需要，可在运行向导前创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="f96a5-272">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="f96a5-273">还可从通信合规性策略向导中创建新的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="f96a5-273">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>

    - <span data-ttu-id="f96a5-274">选择是否启用分类器。</span><span class="sxs-lookup"><span data-stu-id="f96a5-274">Choose if you'd like to enable classifiers.</span></span> <span data-ttu-id="f96a5-275">分类器可以检测电子邮件正文或其他类型的文本中发送或接收的不当语言和图像。</span><span class="sxs-lookup"><span data-stu-id="f96a5-275">Classifiers can detect inappropriate language and images sent or received in the body of email messages or other types of text.</span></span> <span data-ttu-id="f96a5-276">可选择以下内置分类器： *威胁*、*猥亵*、*有针对性的骚扰*、*成人图像*、*色情图像* 和 *血腥图像*。</span><span class="sxs-lookup"><span data-stu-id="f96a5-276">You can choose the following built-in classifiers: *Threat*, *Profanity*, *Targeted harassment*, *Adult images*, *Racy images*, and *Gory images*.</span></span>

    - <span data-ttu-id="f96a5-277">启用 [光学字符识别 (OCR ](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview)) 扫描邮件中嵌入或附加的图像，以找到符合策略条件的打印或手写文本。</span><span class="sxs-lookup"><span data-stu-id="f96a5-277">Enable [optical character recognition (OCR)](communication-compliance-feature-reference.md#optical-character-recognition-ocr-preview) to scan embedded or attached images in messages for printed or handwritten text that match policy conditions.</span></span> <span data-ttu-id="f96a5-278">对于自定义策略，必须在策略中配置一个或多个与文本、关键字、分类器或敏感信息类型关联的条件设置，以允许选择光学字符识别扫描。</span><span class="sxs-lookup"><span data-stu-id="f96a5-278">For custom policies, one or more conditional settings associated with text, keywords, classifiers, or sensitive info types must be configured in the policy to enable the selection of optical character recognition scanning.</span></span>

    - <span data-ttu-id="f96a5-279">定义要审阅的通信的百分比。</span><span class="sxs-lookup"><span data-stu-id="f96a5-279">Define the percentage of communications to review.</span></span>

    - <span data-ttu-id="f96a5-280">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="f96a5-280">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="f96a5-281">使用模板时选择“**创建策略**”，或者使用自定义策略向导时选择“**提交**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-281">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="f96a5-282">将显示 **策略已创建** 页面，其中将包含有关何时激活策略以及捕获哪些通信的准则。</span><span class="sxs-lookup"><span data-stu-id="f96a5-282">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a><span data-ttu-id="f96a5-283">步骤 6（可选）：创建通知模板并配置用户匿名处理</span><span class="sxs-lookup"><span data-stu-id="f96a5-283">Step 6 (optional): Create notice templates and configure user anonymization</span></span>

<span data-ttu-id="f96a5-284">如果要选择通过向关联用户发送提醒通知来响应策略警报，你需要在组织中至少创建一个通知模板。</span><span class="sxs-lookup"><span data-stu-id="f96a5-284">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated user, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="f96a5-285">通知模板字段在作为警报修正过程的一部分发送之前可编辑，建议为每条通信合规性策略创建自定义通知模板。</span><span class="sxs-lookup"><span data-stu-id="f96a5-285">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

<span data-ttu-id="f96a5-286">当调查策略匹配并针对邮件采取措施时，还可以选择对显示用户名启用匿名处理。</span><span class="sxs-lookup"><span data-stu-id="f96a5-286">You can also choose to enable anonymization for displayed usernames when investigating policy matches and taking action on messages.</span></span>

1. <span data-ttu-id="f96a5-287">使用 Microsoft 365 组织中的管理员账户凭据登录 [https://compliance.microsoft.com](https://compliance.microsoft.com)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-287">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="f96a5-288">在 Microsoft 365 合规中心中，转到“**通信合规性**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-288">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="f96a5-289">若要配置用户名的匿名处理，请选择“**隐私**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="f96a5-289">To configure anonymization for usernames, select the **Privacy** tab.</span></span>

4. <span data-ttu-id="f96a5-290">若要启用匿名处理，请选择“**显示用户名的匿名版本**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-290">To enable anonymization, select **Show anonymized versions of usernames**.</span></span>

5. <span data-ttu-id="f96a5-291">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-291">Select **Save**.</span></span>

6. <span data-ttu-id="f96a5-292">导航到“**通知模板**”选项卡，然后选择“**创建通知模板**”。</span><span class="sxs-lookup"><span data-stu-id="f96a5-292">Navigate to the **Notice templates** tab and then select **Create notice template**.</span></span>

7. <span data-ttu-id="f96a5-293">在 **修改通知模板** 页面，完成以下字段：</span><span class="sxs-lookup"><span data-stu-id="f96a5-293">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="f96a5-294">模板名称（必需）</span><span class="sxs-lookup"><span data-stu-id="f96a5-294">Template name (required)</span></span>
    - <span data-ttu-id="f96a5-295">发送自（必需）</span><span class="sxs-lookup"><span data-stu-id="f96a5-295">Send from (required)</span></span>
    - <span data-ttu-id="f96a5-296">抄送和密件抄送（可选）</span><span class="sxs-lookup"><span data-stu-id="f96a5-296">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="f96a5-297">主题（必需）</span><span class="sxs-lookup"><span data-stu-id="f96a5-297">Subject (required)</span></span>
    - <span data-ttu-id="f96a5-298">邮件正文（必需）</span><span class="sxs-lookup"><span data-stu-id="f96a5-298">Message body (required)</span></span>

8. <span data-ttu-id="f96a5-299">选择“**另存为**” ，以创建并保存通知模板。</span><span class="sxs-lookup"><span data-stu-id="f96a5-299">Select **Save** to create and save the notice template.</span></span>

## <a name="step-7-optional-test-your-communication-compliance-policy"></a><span data-ttu-id="f96a5-300">步骤 7（可选）：测试通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="f96a5-300">Step 7 (optional): Test your communication compliance policy</span></span>

<span data-ttu-id="f96a5-301">创建通信合规性策略后，建议进行测试，以确保已定义的条件已由策略正确强制执行。</span><span class="sxs-lookup"><span data-stu-id="f96a5-301">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="f96a5-302">如果通信合规性策略包含敏感信息类型，也可以 [测试数据丢失防护 (DLP) 策略](create-test-tune-dlp-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-302">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="f96a5-303">请务必为策略提供激活时间，以便捕获要测试的通信。</span><span class="sxs-lookup"><span data-stu-id="f96a5-303">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="f96a5-304">请按照以下步骤测试通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="f96a5-304">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="f96a5-305">以要测试的策略中定义的受监督用户登录时，打开电子邮件客户端、Microsoft Teams 或 Yammer。</span><span class="sxs-lookup"><span data-stu-id="f96a5-305">Open an email client, Microsoft Teams, or Yammer while signed in as a supervised user defined in the policy you want to test.</span></span>

2. <span data-ttu-id="f96a5-306">发送电子邮件、Microsoft Teams 聊天或 Yammer 消息，这些内容需要满足通信合规性策略中定义的条件。</span><span class="sxs-lookup"><span data-stu-id="f96a5-306">Send an email, Microsoft Teams chat, or Yammer message that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="f96a5-307">此测试可以是关键字、附件大小、域等。请确保确定策略中已配置的条件设置是否过于严格或过于宽松。</span><span class="sxs-lookup"><span data-stu-id="f96a5-307">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="f96a5-308">在策略中完全处理电子邮件可能需要 24 小时。</span><span class="sxs-lookup"><span data-stu-id="f96a5-308">Email messages can take up to 24 hours to fully process in a policy.</span></span> <span data-ttu-id="f96a5-309">Microsoft Teams、Yammer 和第三方平台中的通信可能需要长达 48 小时才能完全执行策略处理。</span><span class="sxs-lookup"><span data-stu-id="f96a5-309">Communications in Microsoft Teams, Yammer, and third-party platforms can take up to 48 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="f96a5-310">作为通信合规性策略中指定的审阅者登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="f96a5-310">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="f96a5-311">导航到“**通信合规性**” > “**警报**”以查看策略的警报。</span><span class="sxs-lookup"><span data-stu-id="f96a5-311">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="f96a5-312">使用修正控件修正警报，并验证警报是否正确解决。</span><span class="sxs-lookup"><span data-stu-id="f96a5-312">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>

## <a name="next-steps"></a><span data-ttu-id="f96a5-313">后续步骤</span><span class="sxs-lookup"><span data-stu-id="f96a5-313">Next steps</span></span>

<span data-ttu-id="f96a5-314">完成这些步骤以创建第一个通信合规性策略后，将在 24-48 小时之后开始从活动指标接收警报。</span><span class="sxs-lookup"><span data-stu-id="f96a5-314">After you've completed these steps to create your first communication compliance policy, you'll start to receive alerts from activity indicators after 24-48 hours.</span></span> <span data-ttu-id="f96a5-315">使用本文中步骤 5 中的指南，根据需要配置其他策略。</span><span class="sxs-lookup"><span data-stu-id="f96a5-315">Configure additional policies as needed using the guidance in Step 5 of this article.</span></span>

<span data-ttu-id="f96a5-316">若要深入了解如何调查通信合规性警报，请参阅 [调查并修正通信合规性警报](communication-compliance-investigate-remediate.md)。</span><span class="sxs-lookup"><span data-stu-id="f96a5-316">To learn more about investigating communication compliance alerts, see [Investigate and remediate communication compliance alerts](communication-compliance-investigate-remediate.md).</span></span>
