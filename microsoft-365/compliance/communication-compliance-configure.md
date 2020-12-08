---
title: 通信合规性入门
description: 设置通信合规性策略以配置用户通信以供审阅。
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
ms.openlocfilehash: e88b26fcfbcc9cbb0c2c53ed8fdb6b875ef4adc9
ms.sourcegitcommit: 98146c67a1d99db5510fa130340d3b7be8d81b21
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2020
ms.locfileid: "49585302"
---
# <a name="get-started-with-communication-compliance"></a><span data-ttu-id="b7e81-103">通信合规性入门</span><span class="sxs-lookup"><span data-stu-id="b7e81-103">Get started with communication compliance</span></span>

<span data-ttu-id="b7e81-104">使用通信合规性策略来确定内部或外部审阅者进行检查的用户通信。</span><span class="sxs-lookup"><span data-stu-id="b7e81-104">Use communication compliance policies to identify user communications for examination by internal or external reviewers.</span></span> <span data-ttu-id="b7e81-105">有关通信合规性策略如何帮助您监视组织中的通信的详细信息，请参阅 [Microsoft 365 中的通信合规性策略](communication-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e81-105">For more information about how communication compliance policies can help you monitor communications in your organization, see [communication compliance policies in Microsoft 365](communication-compliance.md).</span></span> <span data-ttu-id="b7e81-106">如果您想要查看 Contoso 如何快速将通信合规性策略配置为在 Microsoft 团队、Exchange Online 和 Yammer 通信中监视攻击性语言，请查看此 [案例研究](communication-compliance-case-study.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e81-106">If you'd like to review how Contoso quickly configured a communication compliance policy to monitor for offensive language in Microsoft Teams, Exchange Online, and Yammer communications, check out this [case study](communication-compliance-case-study.md).</span></span>

## <a name="subscriptions-and-licensing"></a><span data-ttu-id="b7e81-107">订阅和许可</span><span class="sxs-lookup"><span data-stu-id="b7e81-107">Subscriptions and licensing</span></span>

<span data-ttu-id="b7e81-108">在开始进行通信合规性之前，应确认你的 [Microsoft 365 订阅](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) 和任何加载项。</span><span class="sxs-lookup"><span data-stu-id="b7e81-108">Before you get started with communication compliance, you should confirm your [Microsoft 365 subscription](https://www.microsoft.com/microsoft-365/compare-all-microsoft-365-plans) and any add-ons.</span></span> <span data-ttu-id="b7e81-109">若要访问和使用通信合规性，您的组织必须具有以下订阅或加载项之一：</span><span class="sxs-lookup"><span data-stu-id="b7e81-109">To access and use communication compliance, your organization must have one of the following subscriptions or add-ons:</span></span>

- <span data-ttu-id="b7e81-110">Microsoft 365 E5 订阅 (付费或试用版) </span><span class="sxs-lookup"><span data-stu-id="b7e81-110">Microsoft 365 E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="b7e81-111">Microsoft 365 E3 订阅 + Microsoft 365 E5 合规性加载项</span><span class="sxs-lookup"><span data-stu-id="b7e81-111">Microsoft 365 E3 subscription + the Microsoft 365 E5 Compliance add-on</span></span>
- <span data-ttu-id="b7e81-112">Microsoft 365 E3 订阅 + Microsoft 365 E5 内幕人士风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="b7e81-112">Microsoft 365 E3 subscription + the Microsoft 365 E5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="b7e81-113">Microsoft 365 A5 订阅 (付费版或试用版) </span><span class="sxs-lookup"><span data-stu-id="b7e81-113">Microsoft 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="b7e81-114">Microsoft 365 A3 订阅 + Microsoft 365 A5 合规性加载项</span><span class="sxs-lookup"><span data-stu-id="b7e81-114">Microsoft 365 A3 subscription + the Microsoft 365 A5 Compliance add-on</span></span>
- <span data-ttu-id="b7e81-115">Microsoft 365 A3 订阅 + Microsoft 365 A5 内幕成员风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="b7e81-115">Microsoft 365 A3 subscription + the Microsoft 365 A5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="b7e81-116">Microsoft 365 G5 订阅 (付费版或试用版) </span><span class="sxs-lookup"><span data-stu-id="b7e81-116">Microsoft 365 G5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="b7e81-117">Microsoft 365 G5 订阅 + Microsoft 365 G5 合规性附加</span><span class="sxs-lookup"><span data-stu-id="b7e81-117">Microsoft 365 G5 subscription + the Microsoft 365 G5 Compliance add-on</span></span>
- <span data-ttu-id="b7e81-118">Microsoft 365 G5 订阅 + Microsoft 365 G5 内幕版风险管理加载项</span><span class="sxs-lookup"><span data-stu-id="b7e81-118">Microsoft 365 G5 subscription + the Microsoft 365 G5 Insider Risk Management add-on</span></span>
- <span data-ttu-id="b7e81-119">Office 365 企业版 E5 订阅 (付费或试用版) </span><span class="sxs-lookup"><span data-stu-id="b7e81-119">Office 365 Enterprise E5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="b7e81-120">Office 365 A5 订阅 (付费或试用版) </span><span class="sxs-lookup"><span data-stu-id="b7e81-120">Office 365 A5 subscription (paid or trial version)</span></span>
- <span data-ttu-id="b7e81-121">Office 365 企业版 E3 订阅 + Office 365 高级合规性外接程序 (不再可用于新订阅，请参阅 note) </span><span class="sxs-lookup"><span data-stu-id="b7e81-121">Office 365 Enterprise E3 subscription + the Office 365 Advanced Compliance add-on (no longer available for new subscriptions, see note)</span></span>

<span data-ttu-id="b7e81-122">必须为通信合规性策略中包含的用户分配上述许可证之一。</span><span class="sxs-lookup"><span data-stu-id="b7e81-122">Users included in communication compliance policies must be assigned one of the licenses above.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b7e81-123">Office 365 高级合规性不再作为独立订阅销售。</span><span class="sxs-lookup"><span data-stu-id="b7e81-123">Office 365 Advanced Compliance is no longer sold as a standalone subscription.</span></span> <span data-ttu-id="b7e81-124">当当前订阅过期时，客户应转换为上述订阅之一，其中包含相同或更多的合规性功能。</span><span class="sxs-lookup"><span data-stu-id="b7e81-124">When current subscriptions expire, customers should transition to one of the subscriptions above, which contain the same or additional compliance features.</span></span>

<span data-ttu-id="b7e81-125">如果您没有现成的 Office 365 企业版 E5 计划，并且想要尝试进行通信合规性，则可以 [将 Microsoft 365 添加](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) 到现有订阅或注册 Office 365 企业版 e5 的 [试用版](https://www.microsoft.com/microsoft-365/enterprise) 。</span><span class="sxs-lookup"><span data-stu-id="b7e81-125">If you don't have an existing Office 365 Enterprise E5 plan and want to try communication compliance, you can [add Microsoft 365](https://docs.microsoft.com/office365/admin/try-or-buy-microsoft-365) to your existing subscription or [sign up for a trial](https://www.microsoft.com/microsoft-365/enterprise) of Office 365 Enterprise E5.</span></span>

## <a name="step-1-required-enable-permissions-for-communication-compliance"></a><span data-ttu-id="b7e81-126">步骤 1 (必需) ：启用通信合规性的权限</span><span class="sxs-lookup"><span data-stu-id="b7e81-126">Step 1 (required): Enable permissions for communication compliance</span></span>

>[!Important]
><span data-ttu-id="b7e81-127">默认情况下，全局管理员不具有对通信合规性功能的访问权限。</span><span class="sxs-lookup"><span data-stu-id="b7e81-127">By default, Global Administrators do not have access to communication compliance features.</span></span> <span data-ttu-id="b7e81-128">在此步骤中分配的角色在所有通信合规性功能都可访问之前是必需的。</span><span class="sxs-lookup"><span data-stu-id="b7e81-128">The roles assigned in this step are required before any communication compliance features will be accessible.</span></span> <span data-ttu-id="b7e81-129">配置角色组后，最多可能需要30分钟的时间才能将角色组权限应用到组织中分配的用户。</span><span class="sxs-lookup"><span data-stu-id="b7e81-129">After configuring your role groups, it may take up to 30 minutes for the role group permissions to apply to assigned users across your organization.</span></span>

<span data-ttu-id="b7e81-130">有五个角色组用于配置管理通信合规性功能的权限。</span><span class="sxs-lookup"><span data-stu-id="b7e81-130">There are five role groups used to configure permissions to manage communication compliance features.</span></span> <span data-ttu-id="b7e81-131">为了使 **通信合规性** 在 Microsoft 365 合规性中心中可用作菜单选项，若要继续执行这些配置步骤，您必须分配给 *通信合规* 性管理员角色组或 *通信合规性管理员* 角色组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-131">To make **Communication compliance** available as a menu option in Microsoft 365 compliance center and to continue with these configuration steps, you must be assigned to the *Communication Compliance* or *Communication Compliance Admin* role groups.</span></span> <span data-ttu-id="b7e81-132">若要在初始配置后访问和管理通信合规性功能，用户必须是至少一个通信合规性角色组的成员。</span><span class="sxs-lookup"><span data-stu-id="b7e81-132">To access and manage communication compliance features after initial configuration, users must be a member of at least one communication compliance role group.</span></span>

<span data-ttu-id="b7e81-133">根据您想要管理通信策略和通知的方式，您需要将用户分配给特定角色组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-133">Depending on how you wish to manage communication policies and alerts, you'll need to assign users to specific role groups.</span></span> <span data-ttu-id="b7e81-134">您可以选择将具有不同合规性职责的用户分配给特定角色组，以管理通信合规性功能的不同方面。</span><span class="sxs-lookup"><span data-stu-id="b7e81-134">You have the option to assign users with different compliance responsibilities to specific role groups to manage different areas of communication compliance features.</span></span> <span data-ttu-id="b7e81-135">或者，您可以决定将指定管理员、分析师、调查人员和查看者的所有用户帐户分配给 *通信合规性* 角色组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-135">Or you may decide to assign all user accounts for designated administrators, analysts, investigators, and viewers to the *Communication Compliance* role group.</span></span> <span data-ttu-id="b7e81-136">使用一个或多个角色组以最大限度地满足合规性管理要求。</span><span class="sxs-lookup"><span data-stu-id="b7e81-136">Use a single role group or multiple role groups to best fit your compliance management requirements.</span></span>

<span data-ttu-id="b7e81-137">配置通信合规性时从这些角色组选项中进行选择：</span><span class="sxs-lookup"><span data-stu-id="b7e81-137">Choose from these role group options when configuring communication compliance:</span></span>

| <span data-ttu-id="b7e81-138">Role</span><span class="sxs-lookup"><span data-stu-id="b7e81-138">Role</span></span> | <span data-ttu-id="b7e81-139">角色权限</span><span class="sxs-lookup"><span data-stu-id="b7e81-139">Role permissions</span></span> |
|:-----|:-----|
| <span data-ttu-id="b7e81-140">**通信合规性**</span><span class="sxs-lookup"><span data-stu-id="b7e81-140">**Communication Compliance**</span></span> | <span data-ttu-id="b7e81-141">使用此角色组管理单个组中的组织的通信合规性。</span><span class="sxs-lookup"><span data-stu-id="b7e81-141">Use this role group to manage communication compliance for your organization in a single group.</span></span> <span data-ttu-id="b7e81-142">通过添加指定管理员、分析师、调查人员和查看者的所有用户帐户，您可以在单个组中配置通信合规性权限。</span><span class="sxs-lookup"><span data-stu-id="b7e81-142">By adding all user accounts for designated administrators, analysts, investigators, and viewers, you can configure communication compliance permissions in a single group.</span></span> <span data-ttu-id="b7e81-143">此角色组包含所有通信合规性权限角色。</span><span class="sxs-lookup"><span data-stu-id="b7e81-143">This role group contains all the communication compliance permission roles.</span></span> <span data-ttu-id="b7e81-144">此配置是快速开始使用通信合规性的最简单方法，非常适合不需要为单独的用户组定义单独权限的组织。</span><span class="sxs-lookup"><span data-stu-id="b7e81-144">This configuration is the easiest way to quickly get started with communication compliance and is a good fit for organizations that do not need separate permissions defined for separate groups of users.</span></span> |
| <span data-ttu-id="b7e81-145">**通信合规性管理员**</span><span class="sxs-lookup"><span data-stu-id="b7e81-145">**Communication Compliance Admin**</span></span> | <span data-ttu-id="b7e81-146">使用此角色组最初配置通信合规性和更高版本，以将通信合规性管理员与定义的组隔离。</span><span class="sxs-lookup"><span data-stu-id="b7e81-146">Use this role group to initially configure communication compliance and later to segregate communication compliance administrators into a defined group.</span></span> <span data-ttu-id="b7e81-147">分配到此角色组的用户可以创建、读取、更新和删除通信合规性策略、全局设置和角色组分配。</span><span class="sxs-lookup"><span data-stu-id="b7e81-147">Users assigned to this role group can create, read, update, and delete communication compliance policies, global settings, and role group assignments.</span></span> <span data-ttu-id="b7e81-148">分配到此角色组的用户无法查看邮件通知。</span><span class="sxs-lookup"><span data-stu-id="b7e81-148">Users assigned to this role group cannot view message alerts.</span></span> |
| <span data-ttu-id="b7e81-149">**通信合规性分析师**</span><span class="sxs-lookup"><span data-stu-id="b7e81-149">**Communication Compliance Analyst**</span></span> | <span data-ttu-id="b7e81-150">使用此组可将权限分配给将充当通信合规性分析员的用户。</span><span class="sxs-lookup"><span data-stu-id="b7e81-150">Use this group to assign permissions to users that will act as communication compliance analysts.</span></span> <span data-ttu-id="b7e81-151">分配到此角色组的用户可以查看将其分配为审阅者的策略、查看邮件元数据 (不是邮件内容) 、升级到其他审阅者或向用户发送通知。</span><span class="sxs-lookup"><span data-stu-id="b7e81-151">Users assigned to this role group can view policies where they are assigned as Reviewers, view message metadata (not message content), escalate to additional reviewers, or send notifications to users.</span></span> <span data-ttu-id="b7e81-152">分析师无法解决待处理的警报。</span><span class="sxs-lookup"><span data-stu-id="b7e81-152">Analysts cannot resolve pending alerts.</span></span> |
| <span data-ttu-id="b7e81-153">**通信合规调查人员**</span><span class="sxs-lookup"><span data-stu-id="b7e81-153">**Communication Compliance Investigator**</span></span> | <span data-ttu-id="b7e81-154">使用此组将权限分配给将充当通信合规性调查人员的用户。</span><span class="sxs-lookup"><span data-stu-id="b7e81-154">Use this group to assign permissions to users that will act as communication compliance investigators.</span></span> <span data-ttu-id="b7e81-155">分配到此角色组的用户可以查看邮件元数据和内容、升级到其他审阅者、升级到高级电子数据展示事例、向用户发送通知以及解决警报。</span><span class="sxs-lookup"><span data-stu-id="b7e81-155">Users assigned to this role group can view message metadata and content, escalate to additional reviewers, escalate to an Advanced eDiscovery case, send notifications to users, and resolve the alert.</span></span> |
| <span data-ttu-id="b7e81-156">**通信合规性查看器**</span><span class="sxs-lookup"><span data-stu-id="b7e81-156">**Communication Compliance Viewer**</span></span> | <span data-ttu-id="b7e81-157">使用此组可为将管理通信报告的用户分配权限。</span><span class="sxs-lookup"><span data-stu-id="b7e81-157">Use this group to assign permissions to users that will manage communication reports.</span></span> <span data-ttu-id="b7e81-158">分配到此角色组的用户可以访问通信合规性主页上的所有报告小部件，并且可以查看所有通信合规性报告。</span><span class="sxs-lookup"><span data-stu-id="b7e81-158">Users assigned to this role group can access all reporting widgets on the communication compliance home page and can view all communication compliance reports.</span></span> |

### <a name="option-1-assign-all-compliance-users-to-the-communication-compliance-role-group"></a><span data-ttu-id="b7e81-159">选项1：将所有合规性用户分配给通信合规性角色组</span><span class="sxs-lookup"><span data-stu-id="b7e81-159">Option 1: Assign all compliance users to the Communication Compliance role group</span></span>

1. <span data-ttu-id="b7e81-160">[https://protection.office.com/permissions](https://protection.office.com/permissions)在 Microsoft 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="b7e81-160">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="b7e81-161">在 "安全 &amp; 合规性中心" 中，转到 " **权限**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-161">In the Security &amp; Compliance Center, go to **Permissions**.</span></span> <span data-ttu-id="b7e81-162">选择用于查看和管理 Office 365 中的角色的链接。</span><span class="sxs-lookup"><span data-stu-id="b7e81-162">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="b7e81-163">选择 " *通信合规性* 角色组"，然后选择 " **编辑角色组**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-163">Select the *Communication Compliance* role group, then select **Edit role group**.</span></span>

4. <span data-ttu-id="b7e81-164">从左侧导航窗格中选择 " **选择成员** "，然后选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-164">Select **Choose members** from the left navigation pane, then select **Edit**.</span></span>

5. <span data-ttu-id="b7e81-165">选择 " **添加** "，然后选中要添加到 *通信合规性* 角色组的所有用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="b7e81-165">Select **Add** and then select the checkbox for all users you want to add to the *Communication Compliance* role group.</span></span>

6. <span data-ttu-id="b7e81-166">选择 " **添加**"，然后选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-166">Select **Add**, then select **Done**.</span></span>

7. <span data-ttu-id="b7e81-167">选择 " **保存** " 将用户添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-167">Select **Save** to add the users to the role group.</span></span> <span data-ttu-id="b7e81-168">选择 " **关闭** " 完成步骤</span><span class="sxs-lookup"><span data-stu-id="b7e81-168">Select **Close** to complete the steps</span></span>

### <a name="option-2-assign-users-to-specific-communication-compliance-role-groups"></a><span data-ttu-id="b7e81-169">选项2：将用户分配给特定的通信合规性角色组</span><span class="sxs-lookup"><span data-stu-id="b7e81-169">Option 2: Assign users to specific communication compliance role groups</span></span>

<span data-ttu-id="b7e81-170">使用此选项可将用户分配给特定角色组，以在组织中的不同用户之间分段通信合规性访问和责任。</span><span class="sxs-lookup"><span data-stu-id="b7e81-170">Use this option to assign users to specific role groups to segment communication compliance access and responsibilities among different users in your organization.</span></span>

1. <span data-ttu-id="b7e81-171">[https://protection.office.com/permissions](https://protection.office.com/permissions)在 Microsoft 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="b7e81-171">Sign into [https://protection.office.com/permissions](https://protection.office.com/permissions) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="b7e81-172">在 "安全 &amp; 合规性中心" 中，转到 " **权限**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-172">In the Security &amp; Compliance Center, go to **Permissions**.</span></span> <span data-ttu-id="b7e81-173">选择用于查看和管理 Office 365 中的角色的链接。</span><span class="sxs-lookup"><span data-stu-id="b7e81-173">Select the link to view and manage roles in Office 365.</span></span>

3. <span data-ttu-id="b7e81-174">选择其中一个通信合规性角色组，然后选择 " **编辑角色组**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-174">Select one of the communication compliance role groups, then select **Edit role group**.</span></span>

4. <span data-ttu-id="b7e81-175">从左侧导航窗格中选择 " **选择成员** "，然后选择 " **编辑**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-175">Select **Choose members** from the left navigation pane, then select **Edit**.</span></span>

5. <span data-ttu-id="b7e81-176">选择 " **添加** "，然后选中要添加到角色组的所有用户的复选框。</span><span class="sxs-lookup"><span data-stu-id="b7e81-176">Select **Add** and then select the checkbox for all users you want to add to the role group.</span></span>

6. <span data-ttu-id="b7e81-177">选择 " **添加**"，然后选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-177">Select **Add**, then select **Done**.</span></span>

7. <span data-ttu-id="b7e81-178">选择 " **保存** " 将用户添加到角色组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-178">Select **Save** to add the users to the role group.</span></span>

8. <span data-ttu-id="b7e81-179">选择 "下一个通信合规性角色组"，然后对每个所需的角色组重复步骤4-7。</span><span class="sxs-lookup"><span data-stu-id="b7e81-179">Select the next communication compliance role group, then repeat steps 4-7 for each required role group.</span></span>

9. <span data-ttu-id="b7e81-180">选择 " **关闭** " 完成这些步骤。</span><span class="sxs-lookup"><span data-stu-id="b7e81-180">Select **Close** to complete the steps.</span></span>

<span data-ttu-id="b7e81-181">有关角色组和权限的详细信息，请参阅 [合规性中心中的权限](../security/office-365-security/protect-against-threats.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e81-181">For more information about role groups and permissions, see [Permissions in the Compliance Center](../security/office-365-security/protect-against-threats.md).</span></span>

## <a name="step-2-required-enable-the-audit-log"></a><span data-ttu-id="b7e81-182">步骤 2 (必需) ：启用审核日志</span><span class="sxs-lookup"><span data-stu-id="b7e81-182">Step 2 (required): Enable the audit log</span></span>

<span data-ttu-id="b7e81-183">通信合规性需要审核日志来显示通知并跟踪审阅者采取的修正操作。</span><span class="sxs-lookup"><span data-stu-id="b7e81-183">Communication compliance requires audit logs to show alerts and track remediation actions taken by reviewers.</span></span> <span data-ttu-id="b7e81-184">审核日志是与定义的组织策略关联的所有活动的摘要，也是任何与通信合规性策略更改相关的活动。</span><span class="sxs-lookup"><span data-stu-id="b7e81-184">The audit logs are a summary of all activities associated with a defined organizational policy or anytime a communication compliance policy changes.</span></span>

<span data-ttu-id="b7e81-185">有关启用审核的分步说明，请参阅 [打开或关闭审核日志搜索](turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e81-185">For step-by-step instructions to turn on auditing, see [Turn audit log search on or off](turn-audit-log-search-on-or-off.md).</span></span> <span data-ttu-id="b7e81-186">启用审核后，会显示一条消息，指出正在准备审核日志，并且您可以在准备完成后的几小时内运行搜索。</span><span class="sxs-lookup"><span data-stu-id="b7e81-186">After you turn on auditing, a message is displayed that says the audit log is being prepared and that you can run a search in a couple of hours after the preparation is complete.</span></span> <span data-ttu-id="b7e81-187">您只需执行一次此操作。</span><span class="sxs-lookup"><span data-stu-id="b7e81-187">You only have to do this action once.</span></span> <span data-ttu-id="b7e81-188">有关使用审核日志的详细信息，请参阅 [Search the audit log](search-the-audit-log-in-security-and-compliance.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e81-188">For more information about the using the audit log, see [Search the audit log](search-the-audit-log-in-security-and-compliance.md).</span></span>

## <a name="step-3-optional-set-up-groups-for-communication-compliance"></a><span data-ttu-id="b7e81-189">步骤 3 (可选) ：为通信合规性设置组</span><span class="sxs-lookup"><span data-stu-id="b7e81-189">Step 3 (optional): Set up groups for communication compliance</span></span>

 <span data-ttu-id="b7e81-190">创建通信合规性策略时，您需要定义哪些用户已查看其通信，以及谁执行了评论。</span><span class="sxs-lookup"><span data-stu-id="b7e81-190">When you create a communication compliance policy, you define who has their communications reviewed and who performs reviews.</span></span> <span data-ttu-id="b7e81-191">在策略中，您将使用电子邮件地址来标识个人或用户组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-191">In the policy, you'll use email addresses to identify individuals or groups of people.</span></span> <span data-ttu-id="b7e81-192">为简化您的设置，您可以为已查看其通信的用户创建组，并为查看这些通信的用户分组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-192">To simplify your setup, you can create groups for people who have their communication reviewed and groups for people who review those communications.</span></span> <span data-ttu-id="b7e81-193">如果使用的是组，可能需要多个。</span><span class="sxs-lookup"><span data-stu-id="b7e81-193">If you're using groups, you may need several.</span></span> <span data-ttu-id="b7e81-194">例如，如果要监视两个不同的人员组之间的通信，或者要指定不受监督的组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-194">For example, if you want to monitor communications between two distinct groups of people or if you want to specify a group that isn't going to be supervised.</span></span>

<span data-ttu-id="b7e81-195">使用下图可帮助您为组织中的通信合规性策略配置组：</span><span class="sxs-lookup"><span data-stu-id="b7e81-195">Use the following chart to help you configure groups in your organization for communication compliance policies:</span></span>

| <span data-ttu-id="b7e81-196">**Policy 成员**</span><span class="sxs-lookup"><span data-stu-id="b7e81-196">**Policy Member**</span></span> | <span data-ttu-id="b7e81-197">**支持的组**</span><span class="sxs-lookup"><span data-stu-id="b7e81-197">**Supported Groups**</span></span> | <span data-ttu-id="b7e81-198">**不受支持的组**</span><span class="sxs-lookup"><span data-stu-id="b7e81-198">**Unsupported Groups**</span></span> |
|:-----|:-----|:-----|
|<span data-ttu-id="b7e81-199">受监督用户</span><span class="sxs-lookup"><span data-stu-id="b7e81-199">Supervised users</span></span> <br> <span data-ttu-id="b7e81-200">非监督用户</span><span class="sxs-lookup"><span data-stu-id="b7e81-200">Non-supervised users</span></span> | <span data-ttu-id="b7e81-201">通讯组</span><span class="sxs-lookup"><span data-stu-id="b7e81-201">Distribution groups</span></span> <br> <span data-ttu-id="b7e81-202">Microsoft 365 组</span><span class="sxs-lookup"><span data-stu-id="b7e81-202">Microsoft 365 Groups</span></span> | <span data-ttu-id="b7e81-203">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="b7e81-203">Dynamic distribution groups</span></span> <br> <span data-ttu-id="b7e81-204">嵌套的通讯组</span><span class="sxs-lookup"><span data-stu-id="b7e81-204">Nested distribution groups</span></span> <br> <span data-ttu-id="b7e81-205">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="b7e81-205">Mail-enabled security groups</span></span> |
| <span data-ttu-id="b7e81-206">Reviewers</span><span class="sxs-lookup"><span data-stu-id="b7e81-206">Reviewers</span></span> | <span data-ttu-id="b7e81-207">无</span><span class="sxs-lookup"><span data-stu-id="b7e81-207">None</span></span> | <span data-ttu-id="b7e81-208">通讯组</span><span class="sxs-lookup"><span data-stu-id="b7e81-208">Distribution groups</span></span> <br> <span data-ttu-id="b7e81-209">动态通讯组</span><span class="sxs-lookup"><span data-stu-id="b7e81-209">Dynamic distribution groups</span></span> <br> <span data-ttu-id="b7e81-210">嵌套的通讯组</span><span class="sxs-lookup"><span data-stu-id="b7e81-210">Nested distribution groups</span></span> <br> <span data-ttu-id="b7e81-211">启用邮件的安全组</span><span class="sxs-lookup"><span data-stu-id="b7e81-211">Mail-enabled security groups</span></span> |
  
<span data-ttu-id="b7e81-212">当您在策略中分配通讯组时，该策略将监视来自通讯组中每个用户的所有电子邮件和团队聊天。</span><span class="sxs-lookup"><span data-stu-id="b7e81-212">When you assign a distribution group in the policy, the policy monitors all emails and Teams chats from each user in distribution group.</span></span> <span data-ttu-id="b7e81-213">当您在策略中分配 Microsoft 365 组时，该策略将监视发送到该组的所有电子邮件和团队聊天，而不是每个组成员收到的单个电子邮件和聊天。</span><span class="sxs-lookup"><span data-stu-id="b7e81-213">When you assign a Microsoft 365 group in the policy, the policy monitors all emails and Teams chats sent to that group, not the individual emails and chats received by each group member.</span></span>

<span data-ttu-id="b7e81-214">如果您是具有 Exchange 本地部署或外部电子邮件提供商的组织，并且您要为用户监视 Microsoft 团队聊天，则必须为具有内部部署或外部邮箱的用户创建通讯组以进行监视。</span><span class="sxs-lookup"><span data-stu-id="b7e81-214">If you're an organization with an Exchange on-premises deployment or an external email provider and you want to monitor Microsoft Teams chats for your users, you must create a distribution group for the users with on-premises or external mailboxes to monitor.</span></span> <span data-ttu-id="b7e81-215">在后面的这些步骤中，您将分配此通讯组作为策略向导中的受 **监督的用户和组** 选择。</span><span class="sxs-lookup"><span data-stu-id="b7e81-215">Later in these steps, you'll assign this distribution group as the **Supervised users and groups** selection in the policy wizard.</span></span>

>[!IMPORTANT]
><span data-ttu-id="b7e81-216">你必须向 Microsoft 支持人员提交请求，以使贵组织能够使用安全与合规中心中的图形用户界面来搜索本地用户的 Teams 聊天数据。</span><span class="sxs-lookup"><span data-stu-id="b7e81-216">You must file a request with Microsoft Support to enable your organization to use the graphical user interface in the Security & Compliance Center to search for Teams chat data for on-premises users.</span></span> <span data-ttu-id="b7e81-217">有关详细信息，请参阅针对 [本地用户搜索基于云的邮箱](search-cloud-based-mailboxes-for-on-premises-users.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e81-217">For more information, see [Searching cloud-based mailboxes for on-premises users](search-cloud-based-mailboxes-for-on-premises-users.md).</span></span>

<span data-ttu-id="b7e81-218">若要在大型企业组织中管理受监督的用户，您可能需要监视跨大型组的所有用户。</span><span class="sxs-lookup"><span data-stu-id="b7e81-218">To manage supervised users in large enterprise organizations, you may need to monitor all users across large groups.</span></span> <span data-ttu-id="b7e81-219">您可以使用 PowerShell 为分配组的全局通信合规性策略配置通讯组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-219">You can use PowerShell to configure a distribution group for a global communication compliance policy for the assigned group.</span></span> <span data-ttu-id="b7e81-220">这使您可以使用单个策略监视数千个用户，并在新员工加入您的组织时更新通信合规性策略。</span><span class="sxs-lookup"><span data-stu-id="b7e81-220">This enables you to monitor thousands of users with a single policy and keep the communication compliance policy updated as new employees join your organization.</span></span>

1. <span data-ttu-id="b7e81-221">为符合以下属性的全局通信合规性策略创建专用 [通讯组](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) ：确保此通讯组不用于其他目的或其他 Office 365 服务。</span><span class="sxs-lookup"><span data-stu-id="b7e81-221">Create a dedicated [distribution group](https://docs.microsoft.com/powershell/module/exchange/new-distributiongroup) for your global communication compliance policy with the following properties: Make sure that this distribution group isn't used for other purposes or other Office 365 services.</span></span>

    - <span data-ttu-id="b7e81-222">**MemberDepartRestriction = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="b7e81-222">**MemberDepartRestriction = Closed**.</span></span> <span data-ttu-id="b7e81-223">确保用户无法将自己从通讯组中删除。</span><span class="sxs-lookup"><span data-stu-id="b7e81-223">Ensures that users cannot remove themselves from the distribution group.</span></span>
    - <span data-ttu-id="b7e81-224">**MemberJoinRestriction = 已关闭**。</span><span class="sxs-lookup"><span data-stu-id="b7e81-224">**MemberJoinRestriction = Closed**.</span></span> <span data-ttu-id="b7e81-225">确保用户无法将自己添加到通讯组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-225">Ensures that users cannot add themselves to the distribution group.</span></span>
    - <span data-ttu-id="b7e81-226">**ModerationEnabled = True**。</span><span class="sxs-lookup"><span data-stu-id="b7e81-226">**ModerationEnabled = True**.</span></span> <span data-ttu-id="b7e81-227">确保发送到此组的所有邮件都受批准，并且该组未用于通信合规性策略配置之外的通信。</span><span class="sxs-lookup"><span data-stu-id="b7e81-227">Ensures that all messages sent to this group are subject to approval and that the group is not being used to communicate outside of the communication compliance policy configuration.</span></span>

    ```PowerShell
    New-DistributionGroup -Name <your group name> -Alias <your group alias> -MemberDepartRestriction 'Closed' -MemberJoinRestriction 'Closed' -ModerationEnabled $true
    ```

2. <span data-ttu-id="b7e81-228">选择一个未使用的 [Exchange 自定义属性](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes) ，以跟踪添加到组织中的通信合规性策略的用户。</span><span class="sxs-lookup"><span data-stu-id="b7e81-228">Select an unused [Exchange custom attribute](https://docs.microsoft.com/Exchange/recipients/mailbox-custom-attributes) to track users added to the communication compliance policy in your organization.</span></span>

3. <span data-ttu-id="b7e81-229">定期对计划运行以下 PowerShell 脚本，以将用户添加到通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="b7e81-229">Run the following PowerShell script on a recurring schedule to add users to the communication compliance policy:</span></span>

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

<span data-ttu-id="b7e81-230">有关设置组的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b7e81-230">For more information about setting up groups, see:</span></span>

- [<span data-ttu-id="b7e81-231">创建和管理通讯组</span><span class="sxs-lookup"><span data-stu-id="b7e81-231">Create and manage distribution groups</span></span>](https://docs.microsoft.com/Exchange/recipients-in-exchange-online/manage-distribution-groups/manage-distribution-groups)
- [<span data-ttu-id="b7e81-232">Microsoft 365 组概述</span><span class="sxs-lookup"><span data-stu-id="b7e81-232">Overview of Microsoft 365 Groups</span></span>](https://docs.microsoft.com/office365/admin/create-groups/office-365-groups)

## <a name="step-4-optional-verify-your-yammer-tenant-is-in-native-mode"></a><span data-ttu-id="b7e81-233">步骤 4 (可选) ：验证 Yammer 租户是否处于本机模式</span><span class="sxs-lookup"><span data-stu-id="b7e81-233">Step 4 (optional): Verify your Yammer tenant is in Native Mode</span></span>

<span data-ttu-id="b7e81-234">在本机模式中，所有 Yammer 用户都在 Azure Active Directory 中 (Azure AD) 中，所有组都是 Office 365 组，并且所有文件都存储在 SharePoint Online 中。</span><span class="sxs-lookup"><span data-stu-id="b7e81-234">In Native Mode, all Yammer users are in Azure Active Directory (Azure AD), all groups are Office 365 Groups, and all files are stored in SharePoint Online.</span></span> <span data-ttu-id="b7e81-235">您的 Yammer 租户必须处于本机模式，以实现通信合规性策略，以扫描和识别 Yammer 中的私人邮件和社区对话中的有风险的对话。</span><span class="sxs-lookup"><span data-stu-id="b7e81-235">Your Yammer tenant must be in Native Mode for communication compliance policies to scan and identify risky conversations in private messages and community conversations in Yammer.</span></span>

<span data-ttu-id="b7e81-236">有关在本机模式中配置 Yammer 的详细信息，请参阅：</span><span class="sxs-lookup"><span data-stu-id="b7e81-236">For more information about configuring Yammer in Native Mode, see:</span></span>

- [<span data-ttu-id="b7e81-237">Microsoft 365 中的 Yammer 本机模式概述</span><span class="sxs-lookup"><span data-stu-id="b7e81-237">Overview of Yammer Native Mode in Microsoft 365</span></span>](https://docs.microsoft.com/yammer/configure-your-yammer-network/overview-native-mode)
- [<span data-ttu-id="b7e81-238">配置适用于 Microsoft 365 本机模式的 Yammer 网络</span><span class="sxs-lookup"><span data-stu-id="b7e81-238">Configure your Yammer network for Native Mode for Microsoft 365</span></span>](https://docs.microsoft.com/yammer/configure-your-yammer-network/native-mode)

## <a name="step-5-required-create-a-communication-compliance-policy"></a><span data-ttu-id="b7e81-239">步骤 5 (必需) ：创建通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="b7e81-239">Step 5 (required): Create a communication compliance policy</span></span>
  
>[!Important]
><span data-ttu-id="b7e81-240">不支持使用 PowerShell 创建和管理通信合规性策略。</span><span class="sxs-lookup"><span data-stu-id="b7e81-240">Using PowerShell to create and manage communication compliance policies is not supported.</span></span> <span data-ttu-id="b7e81-241">若要创建和管理这些策略，必须使用 [Microsoft 365 通信合规性解决方案](https://compliance.microsoft.com/supervisoryreview)中的策略管理控件。</span><span class="sxs-lookup"><span data-stu-id="b7e81-241">To create and manage these policies, you must use the policy management controls in the [Microsoft 365 communication compliance solution](https://compliance.microsoft.com/supervisoryreview).</span></span>

1. <span data-ttu-id="b7e81-242">[https://compliance.microsoft.com](https://compliance.microsoft.com)在 Microsoft 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="b7e81-242">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="b7e81-243">在 Microsoft 365 合规性中心中，选择 " **通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-243">In the Microsoft 365 compliance center, select **Communication compliance**.</span></span>
  
3. <span data-ttu-id="b7e81-244">选择 " **策略** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b7e81-244">Select the **Policies** tab.</span></span>

4. <span data-ttu-id="b7e81-245">选择 " **创建策略** "，从模板创建和配置新策略，或创建和配置自定义策略。</span><span class="sxs-lookup"><span data-stu-id="b7e81-245">Select **Create policy** to create and configure a new policy from a template or to create and configure a custom policy.</span></span>

    <span data-ttu-id="b7e81-246">如果选择策略模板来创建策略，您将：</span><span class="sxs-lookup"><span data-stu-id="b7e81-246">If you choose a policy template to create a policy, you will:</span></span>

    - <span data-ttu-id="b7e81-247">确认或更新策略名称。</span><span class="sxs-lookup"><span data-stu-id="b7e81-247">Confirm or update the policy name.</span></span> <span data-ttu-id="b7e81-248">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="b7e81-248">Policy names cannot be changed once the policy is created.</span></span>
    
    - <span data-ttu-id="b7e81-249">选择要监督的用户或组，包括选择要排除的用户或组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-249">Choose the users or groups to supervise, including choosing users or groups you'd like to exclude.</span></span>
    
    - <span data-ttu-id="b7e81-250">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="b7e81-250">Choose the reviewers for the policy.</span></span> <span data-ttu-id="b7e81-251">审阅者是单个用户，并且所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="b7e81-251">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span> <span data-ttu-id="b7e81-252">在这里添加的审阅者是在调查和修正工作流中上报通知时可供选择的审阅者。</span><span class="sxs-lookup"><span data-stu-id="b7e81-252">Reviewers added here are the reviewers that you can choose from when escalating an alert in the investigation and remediation workflow.</span></span> <span data-ttu-id="b7e81-253">将审阅者添加到策略时，他们将自动收到一封电子邮件，通知他们对策略的分配，并提供有关审阅过程的信息的链接。</span><span class="sxs-lookup"><span data-stu-id="b7e81-253">When reviewers are added to a policy, they automatically receive an email message that notifies them of the assignment to the policy and provides links to information about the review process.</span></span>
    
    - <span data-ttu-id="b7e81-254">选择 "受限条件" 字段，通常是要应用于策略的敏感信息类型或关键字词典。</span><span class="sxs-lookup"><span data-stu-id="b7e81-254">Choose a limited condition field, usually a sensitive info type or keyword dictionary to apply to the policy.</span></span>

    <span data-ttu-id="b7e81-255">如果您选择使用策略向导创建自定义策略，您将：</span><span class="sxs-lookup"><span data-stu-id="b7e81-255">If you choose to use the policy wizard to create a custom policy, you will:</span></span>

    - <span data-ttu-id="b7e81-256">为策略指定名称和说明。</span><span class="sxs-lookup"><span data-stu-id="b7e81-256">Give the policy a name and description.</span></span> <span data-ttu-id="b7e81-257">一旦创建了策略，便无法更改策略名称。</span><span class="sxs-lookup"><span data-stu-id="b7e81-257">Policy names can't be changed once the policy is created.</span></span>
    
    - <span data-ttu-id="b7e81-258">选择要监督的用户或组，包括组织中的所有用户、特定用户和组，或者要排除的其他用户和组。</span><span class="sxs-lookup"><span data-stu-id="b7e81-258">Choose the users or groups to supervise, including all users in your organization, specific users and groups, or other users and groups you'd like to exclude.</span></span>
    
    - <span data-ttu-id="b7e81-259">选择策略的审阅者。</span><span class="sxs-lookup"><span data-stu-id="b7e81-259">Choose the reviewers for the policy.</span></span> <span data-ttu-id="b7e81-260">审阅者是单个用户，并且所有审阅者都必须在 Exchange Online 上托管邮箱。</span><span class="sxs-lookup"><span data-stu-id="b7e81-260">Reviewers are individual users and all reviewers must have mailboxes hosted on Exchange Online.</span></span> <span data-ttu-id="b7e81-261">在这里添加的审阅者是在调查和修正工作流中上报通知时可供选择的审阅者。</span><span class="sxs-lookup"><span data-stu-id="b7e81-261">Reviewers added here are the reviewers that you can choose from when escalating an alert in the investigation and remediation workflow.</span></span> <span data-ttu-id="b7e81-262">将审阅者添加到策略时，他们将自动收到一封电子邮件，通知他们对策略的分配，并提供有关审阅过程的信息的链接。</span><span class="sxs-lookup"><span data-stu-id="b7e81-262">When reviewers are added to a policy, they automatically receive an email message that notifies them of the assignment to the policy and provides links to information about the review process.</span></span>
    
    - <span data-ttu-id="b7e81-263">选择要扫描的通信通道，包括 Exchange、Microsoft 团队、Yammer 或 Skype for Business。</span><span class="sxs-lookup"><span data-stu-id="b7e81-263">Choose the communication channels to scan, including Exchange, Microsoft Teams, Yammer, or Skype for Business.</span></span> <span data-ttu-id="b7e81-264">如果您在 Microsoft 365 中配置了连接器，您还将选择扫描第三方源。</span><span class="sxs-lookup"><span data-stu-id="b7e81-264">You'll also choose to scan third-party sources if you've configured a connector in Microsoft 365.</span></span>
    
    - <span data-ttu-id="b7e81-265">选择要监视的通信方向，包括入站、出站或内部通信。</span><span class="sxs-lookup"><span data-stu-id="b7e81-265">Choose the communication direction to monitor, including inbound, outbound, or internal communications.</span></span>
    
    - <span data-ttu-id="b7e81-266">定义通信合规性策略 [条件](communication-compliance-feature-reference.md#ConditionalSettings)。</span><span class="sxs-lookup"><span data-stu-id="b7e81-266">Define the communication compliance policy [conditions](communication-compliance-feature-reference.md#ConditionalSettings).</span></span> <span data-ttu-id="b7e81-267">您可以从 "消息地址"、"关键字"、"文件类型" 和 "大小匹配条件" 中进行选择。</span><span class="sxs-lookup"><span data-stu-id="b7e81-267">You can choose from message address, keyword, file types, and size match conditions.</span></span>
    
    - <span data-ttu-id="b7e81-268">选择是否要包含敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="b7e81-268">Choose if you'd like to include sensitive information types.</span></span> <span data-ttu-id="b7e81-269">在此步骤中，您可以选择默认和自定义的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="b7e81-269">This step is where you can select default and custom sensitive info types.</span></span> <span data-ttu-id="b7e81-270">从 "通信合规性策略向导" 中的现有自定义敏感信息类型或自定义关键字词典中进行选择。</span><span class="sxs-lookup"><span data-stu-id="b7e81-270">Pick from existing custom sensitive information types or custom keyword dictionaries in the communication compliance policy wizard.</span></span> <span data-ttu-id="b7e81-271">如果需要，可以在运行向导之前创建这些项目。</span><span class="sxs-lookup"><span data-stu-id="b7e81-271">You can create these items before running the wizard if needed.</span></span> <span data-ttu-id="b7e81-272">您还可以在 "通信合规性策略" 向导中创建新的敏感信息类型。</span><span class="sxs-lookup"><span data-stu-id="b7e81-272">You can also create new sensitive information types from within the communication compliance policy wizard.</span></span>
    
    - <span data-ttu-id="b7e81-273">选择是否要启用分类器。</span><span class="sxs-lookup"><span data-stu-id="b7e81-273">Choose if you'd like to enable classifiers.</span></span> <span data-ttu-id="b7e81-274">分类器可以检测在电子邮件正文或其他类型的文本中发送或接收的不正确的语言和图像。</span><span class="sxs-lookup"><span data-stu-id="b7e81-274">Classifiers can detect inappropriate language and images sent or received in the body of email messages or other types of text.</span></span> <span data-ttu-id="b7e81-275">您可以选择以下内置分类符： *威胁*、 *猥亵*、 *目标骚扰*、 *成人图像*、 *Racy 图像* 和 *Gory 图像*。</span><span class="sxs-lookup"><span data-stu-id="b7e81-275">You can choose the following built-in classifiers: *Threat*, *Profanity*, *Targeted harassment*, *Adult images*, *Racy images*, and *Gory images*.</span></span>

      > [!CAUTION]
      > <span data-ttu-id="b7e81-276">我们正在弃用 **冒犯性语言** 内置分类器，因为它会生成大量误报。</span><span class="sxs-lookup"><span data-stu-id="b7e81-276">We are deprecating the **Offensive Language** built-in classifier because it has been producing a high number of false positives.</span></span> <span data-ttu-id="b7e81-277">请勿使用该功能，如果您当前正在使用它，则应将业务流程移出它。</span><span class="sxs-lookup"><span data-stu-id="b7e81-277">Don't use it and if you are currently using it, you should move your business processes off of it.</span></span> <span data-ttu-id="b7e81-278">建议改为使用 **威胁**、 **猥亵** 和 **目标骚扰** 内置分类符。</span><span class="sxs-lookup"><span data-stu-id="b7e81-278">We recommend using the **Threat**, **Profanity**, and **Targeted harassment** built-in classifiers instead.</span></span>

    - <span data-ttu-id="b7e81-279">定义要查看的通信百分比。</span><span class="sxs-lookup"><span data-stu-id="b7e81-279">Define the percentage of communications to review.</span></span>
    
    - <span data-ttu-id="b7e81-280">查看策略选择并创建策略。</span><span class="sxs-lookup"><span data-stu-id="b7e81-280">Review your policy selections and create the policy.</span></span>

5. <span data-ttu-id="b7e81-281">使用 "自定义策略" 向导时，选择 "使用模板或 **提交** 时 **创建策略**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-281">Select **Create policy** when using the templates or **Submit** when using the custom policy wizard.</span></span>

6. <span data-ttu-id="b7e81-282">**您的策略已创建** 页面将显示有关何时激活策略以及将捕获哪些通信的指南。</span><span class="sxs-lookup"><span data-stu-id="b7e81-282">The **Your policy was created** page is displayed with guidelines on when policy will be activated and which communications will be captured.</span></span>

## <a name="step-6-optional-create-notice-templates-and-configure-user-anonymization"></a><span data-ttu-id="b7e81-283">步骤 6 (可选) ：创建通知模板和配置用户 anonymization</span><span class="sxs-lookup"><span data-stu-id="b7e81-283">Step 6 (optional): Create notice templates and configure user anonymization</span></span>

<span data-ttu-id="b7e81-284">如果希望通过向关联用户发送提醒通知来选择对策略警报做出响应，您需要在组织中至少创建一个通知模板。</span><span class="sxs-lookup"><span data-stu-id="b7e81-284">If you want to have the option of responding to a policy alert by sending a reminder notice to the associated user, you'll need to create at least one notice template in your organization.</span></span> <span data-ttu-id="b7e81-285">在将 "通知模板" 字段作为警报修正过程的一部分发送并为每个通信合规性策略创建自定义的通知模板之前，这些字段都是可编辑的。</span><span class="sxs-lookup"><span data-stu-id="b7e81-285">The notice template fields are editable before they're sent as part of the alert remediation process, and creating a customized notice template for each communication compliance policy is recommended.</span></span>

<span data-ttu-id="b7e81-286">您还可以选择在调查策略匹配和对邮件采取操作时为显示的用户名启用 anonymization。</span><span class="sxs-lookup"><span data-stu-id="b7e81-286">You can also choose to enable anonymization for displayed usernames when investigating policy matches and taking action on messages.</span></span>

1. <span data-ttu-id="b7e81-287">[https://compliance.microsoft.com](https://compliance.microsoft.com)在 Microsoft 365 组织中使用管理员帐户的凭据进行登录。</span><span class="sxs-lookup"><span data-stu-id="b7e81-287">Sign into [https://compliance.microsoft.com](https://compliance.microsoft.com) using credentials for an admin account in your Microsoft 365 organization.</span></span>

2. <span data-ttu-id="b7e81-288">在 Microsoft 365 合规性中心中，转到 " **通信合规性**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-288">In the Microsoft 365 compliance center, go to **Communication compliance**.</span></span>

3. <span data-ttu-id="b7e81-289">若要为用户名配置 anonymization，请选择 " **隐私** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="b7e81-289">To configure anonymization for usernames, select the **Privacy** tab.</span></span>

4. <span data-ttu-id="b7e81-290">若要启用 anonymization，请选择 " **显示匿名版本的用户名**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-290">To enable anonymization, select **Show anonymized versions of usernames**.</span></span>

5. <span data-ttu-id="b7e81-291">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b7e81-291">Select **Save**.</span></span>

6. <span data-ttu-id="b7e81-292">导航到 " **通知模板** " 选项卡，然后选择 " **创建通知模板**"。</span><span class="sxs-lookup"><span data-stu-id="b7e81-292">Navigate to the **Notice templates** tab and then select **Create notice template**.</span></span>

7. <span data-ttu-id="b7e81-293">在 " **修改通知模板** " 页上，填写下列字段：</span><span class="sxs-lookup"><span data-stu-id="b7e81-293">On the **Modify a notice template** page, complete the following fields:</span></span>

    - <span data-ttu-id="b7e81-294">模板名称 (必需) </span><span class="sxs-lookup"><span data-stu-id="b7e81-294">Template name (required)</span></span>
    - <span data-ttu-id="b7e81-295"> (必需的发送) </span><span class="sxs-lookup"><span data-stu-id="b7e81-295">Send from (required)</span></span>
    - <span data-ttu-id="b7e81-296">"抄送" 和 "密件抄送" (可选) </span><span class="sxs-lookup"><span data-stu-id="b7e81-296">Cc and Bcc (optional)</span></span>
    - <span data-ttu-id="b7e81-297">必需的主题 () </span><span class="sxs-lookup"><span data-stu-id="b7e81-297">Subject (required)</span></span>
    - <span data-ttu-id="b7e81-298">邮件正文 (必需的) </span><span class="sxs-lookup"><span data-stu-id="b7e81-298">Message body (required)</span></span>

8. <span data-ttu-id="b7e81-299">选择 " **保存** " 以创建并保存 "通知" 模板。</span><span class="sxs-lookup"><span data-stu-id="b7e81-299">Select **Save** to create and save the notice template.</span></span>

## <a name="step-7-optional-test-your-communication-compliance-policy"></a><span data-ttu-id="b7e81-300">第7步 (可选) ：测试通信合规性策略</span><span class="sxs-lookup"><span data-stu-id="b7e81-300">Step 7 (optional): Test your communication compliance policy</span></span>

<span data-ttu-id="b7e81-301">创建通信合规性策略后，最好对其进行测试，以确保策略正确地强制实施了您定义的条件。</span><span class="sxs-lookup"><span data-stu-id="b7e81-301">After you create a communication compliance policy, it's a good idea to test it to make sure that the conditions you defined are being properly enforced by the policy.</span></span> <span data-ttu-id="b7e81-302">如果通信合规性策略包含敏感信息类型，您可能还需要 [测试您的数据丢失防护 (DLP) 策略](create-test-tune-dlp-policy.md) 。</span><span class="sxs-lookup"><span data-stu-id="b7e81-302">You may also want to [test your data loss prevention (DLP) policies](create-test-tune-dlp-policy.md) if your communication compliance policies include sensitive information types.</span></span> <span data-ttu-id="b7e81-303">请确保为策略激活时间，以便捕获要测试的通信。</span><span class="sxs-lookup"><span data-stu-id="b7e81-303">Make sure you give your policies time to activate so that the communications you want to test are captured.</span></span>

<span data-ttu-id="b7e81-304">按照以下步骤测试您的通信合规性策略：</span><span class="sxs-lookup"><span data-stu-id="b7e81-304">Follow these steps to test your communication compliance policy:</span></span>

1. <span data-ttu-id="b7e81-305">在以要测试的策略中定义的受监督用户身份登录时，打开电子邮件客户端、Microsoft 团队或 Yammer。</span><span class="sxs-lookup"><span data-stu-id="b7e81-305">Open an email client, Microsoft Teams, or Yammer while signed in as a supervised user defined in the policy you want to test.</span></span>

2. <span data-ttu-id="b7e81-306">发送符合您在通信合规性策略中定义的条件的电子邮件、Microsoft 团队聊天或 Yammer 邮件。</span><span class="sxs-lookup"><span data-stu-id="b7e81-306">Send an email, Microsoft Teams chat, or Yammer message that meets the criteria you've defined in the communication compliance policy.</span></span> <span data-ttu-id="b7e81-307">此测试可以是关键字、附件大小、域等。请确保您确定策略中配置的条件设置过于严格或太 lenient。</span><span class="sxs-lookup"><span data-stu-id="b7e81-307">This test can be a keyword, attachment size, domain, etc. Make sure you determine if your configured conditional settings in the policy are too restrictive or too lenient.</span></span>

    > [!NOTE]
    > <span data-ttu-id="b7e81-308">电子邮件可能需要长达24小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="b7e81-308">Email messages can take up to 24 hours to fully process in a policy.</span></span> <span data-ttu-id="b7e81-309">Microsoft 团队、Yammer 和第三方平台中的通信可能需要最长48小时才能在策略中完全处理。</span><span class="sxs-lookup"><span data-stu-id="b7e81-309">Communications in Microsoft Teams, Yammer, and third-party platforms can take up to 48 hours to fully process in a policy.</span></span>

3. <span data-ttu-id="b7e81-310">以通信合规性策略中指定的审阅者的资格登录到 Microsoft 365。</span><span class="sxs-lookup"><span data-stu-id="b7e81-310">Sign in to Microsoft 365 as a reviewer designated in the communication compliance policy.</span></span> <span data-ttu-id="b7e81-311">导航到 "**通信合规性**  >  **警报**" 以查看策略的警报。</span><span class="sxs-lookup"><span data-stu-id="b7e81-311">Navigate to **Communication compliance** > **Alerts** to view the alerts for your policies.</span></span>

4. <span data-ttu-id="b7e81-312">使用修正控件修正警报，并验证是否正确解决了警报。</span><span class="sxs-lookup"><span data-stu-id="b7e81-312">Remediate the alert using the remediation controls and verify that the alert is properly resolved.</span></span>

## <a name="next-steps"></a><span data-ttu-id="b7e81-313">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b7e81-313">Next steps</span></span>

<span data-ttu-id="b7e81-314">完成这些步骤以创建您的第一个通信合规性策略后，您将在24-48 小时后开始收到活动指示器发出的警报。</span><span class="sxs-lookup"><span data-stu-id="b7e81-314">After you've completed these steps to create your first communication compliance policy, you'll start to receive alerts from activity indicators after 24-48 hours.</span></span> <span data-ttu-id="b7e81-315">根据需要使用本文步骤5中的指导配置其他策略。</span><span class="sxs-lookup"><span data-stu-id="b7e81-315">Configure additional policies as needed using the guidance in Step 5 of this article.</span></span>

<span data-ttu-id="b7e81-316">若要了解有关调查通信合规性警报的详细信息，请参阅 [调查和修正通信合规性警报](communication-compliance-investigate-remediate.md)。</span><span class="sxs-lookup"><span data-stu-id="b7e81-316">To learn more about investigating communication compliance alerts, see [Investigate and remediate communication compliance alerts](communication-compliance-investigate-remediate.md).</span></span>
