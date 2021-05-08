---
title: 在管理中心中为 Microsoft Viva Learning (Preview) 配置Microsoft 365源
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: chrisarnoldmsft
ms.date: 04/30/2021
audience: admin
ms.topic: article
ms.service: ''
ms.prod: microsoft-365-enterprise
search.appverid: ''
ms.collection:
- enabler-strategic
- m365initiative-viva-learning
localization_priority: None
description: 了解如何在管理中心为 Microsoft Viva Learning (Preview) 配置Microsoft 365源。
ROBOTS: NOINDEX, NOFOLLOW
ms.openlocfilehash: b2e6ab6306db9a5ac9d91226431e5876cc244499
ms.sourcegitcommit: ff20f5b4e3268c7c98a84fb1cbe7db7151596b6d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2021
ms.locfileid: "52245416"
---
# <a name="configure-learning-content-sources-for-microsoft-viva-learning-preview-in-the-microsoft-365-admin-center"></a><span data-ttu-id="fa67a-103">在管理中心中为 Microsoft Viva Learning (Preview) 配置Microsoft 365源</span><span class="sxs-lookup"><span data-stu-id="fa67a-103">Configure learning content sources for Microsoft Viva Learning (Preview) in the Microsoft 365 admin center</span></span>

> [!NOTE]
> <span data-ttu-id="fa67a-104">本文中的信息与在商业发行之前可能会进行重大修改的预览产品相关。</span><span class="sxs-lookup"><span data-stu-id="fa67a-104">The information in this article relates to a preview product that may be substantially modified before it's commercially released.</span></span> 

<span data-ttu-id="fa67a-105">Microsoft 365 管理中心的管理员可以管理与 Viva Learning (Preview) 相关的设置，并可以配置学习内容源。</span><span class="sxs-lookup"><span data-stu-id="fa67a-105">The administrators for the Microsoft 365 admin center—either by themselves or by assigning the knowledge admin role to selected individuals in your organization—can manage settings related to Viva Learning (Preview) and can configure the learning content sources.</span></span>

<span data-ttu-id="fa67a-106">管理员选择哪些其他学习内容源 (例如，SharePoint或受支持的第三方内容提供程序源) 可供 Viva Learning (Preview) 用户使用。</span><span class="sxs-lookup"><span data-stu-id="fa67a-106">The administrator selects which other learning content sources (for example, SharePoint or supported third-party content provider sources) will be available to users of Viva Learning (Preview).</span></span> <span data-ttu-id="fa67a-107">然后，管理员配置这些源以确保内容可用于搜索和发现，并且可供使用 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="fa67a-107">The admin then configures those sources to make sure the content is available for search and discovery and can be browsed by the employees who use Viva Learning (Preview).</span></span>

> [!NOTE]
>  <span data-ttu-id="fa67a-108">用户登录到非 Microsoft 和 LinkedIn Learning Pro浏览器或嵌入式查看器中学习。</span><span class="sxs-lookup"><span data-stu-id="fa67a-108">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="fa67a-109">此配置的学习受组织和第三方之间的单独许可证、隐私和服务条款的约束，而不是 Viva Learning (Preview) 条款。</span><span class="sxs-lookup"><span data-stu-id="fa67a-109">This configured learning is subject to the separate license, privacy and service terms between your organization and the third party, and not the Viva Learning (Preview) terms.</span></span> <span data-ttu-id="fa67a-110">在选择这种类型的学习之前，请验证你已就组织和用户达成一致。</span><span class="sxs-lookup"><span data-stu-id="fa67a-110">Before selecting this type of learning, verify you have an agreement in place for your organization and users.</span></span>

## <a name="assign-the-knowledge-admin-role-optional"></a><span data-ttu-id="fa67a-111">将知识管理员角色分配 (可选) </span><span class="sxs-lookup"><span data-stu-id="fa67a-111">Assign the knowledge admin role (Optional)</span></span>

<span data-ttu-id="fa67a-112">您必须是全局Microsoft 365才能执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="fa67a-112">You must be a Microsoft 365 global administrator to perform these tasks.</span></span>

> [!TIP]
> <span data-ttu-id="fa67a-113">知识管理员应具有中等技术水平，并且具有SharePoint管理员凭据，最好是在组织的教育、学习、培训或员工体验方面表现良好的人员。</span><span class="sxs-lookup"><span data-stu-id="fa67a-113">The knowledge admin should be moderately technical and have existing SharePoint admin credentials, preferably someone who is well-versed in the education, learning, training, or employee experience part of the organization.</span></span>

### <a name="add-a-knowledge-admin"></a><span data-ttu-id="fa67a-114">添加知识管理员</span><span class="sxs-lookup"><span data-stu-id="fa67a-114">Add a knowledge admin</span></span>

<span data-ttu-id="fa67a-115">若要为 Viva Learning (Preview) 知识管理员，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="fa67a-115">To add a knowledge admin for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="fa67a-116">在管理中心的左侧导航Microsoft 365，转到"角色 **"。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-116">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="fa67a-117">在"**角色"** 页上的 **"Azure AD"** 选项卡上，选择"**知识管理员"。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-117">On the **Roles** page, on the **Azure AD** tab, select **Knowledge Administrator**.</span></span>
 
3.  <span data-ttu-id="fa67a-118">在"**知识管理员"** 面板上，选择"**分配的管理员**"，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-118">On the **Knowledge Administrator** panel, select **Assigned admins**, and then select **Add**.</span></span>

     ![管理中心中Microsoft 365"角色"页面，其中显示"知识管理员"面板以添加用户。](../media/learning/learning-add-knowledge-admin-1.png)

3.  <span data-ttu-id="fa67a-120">在 **"添加管理员"** 面板上，选择你为角色选择的人，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-120">On the **Add admins** panel, select the person you choose for the role, and then select **Add**.</span></span>

     ![管理中心中Microsoft 365"角色"页面，其中显示"添加管理员"面板以添加用户。](../media/learning/learning-add-knowledge-admin-2.png)

### <a name="remove-a-knowledge-admin"></a><span data-ttu-id="fa67a-122">删除知识管理员</span><span class="sxs-lookup"><span data-stu-id="fa67a-122">Remove a knowledge admin</span></span>

<span data-ttu-id="fa67a-123">若要删除 Viva Learning (Preview) 知识管理员，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="fa67a-123">To remove a knowledge admin for Viva Learning (Preview), follow these steps:</span></span>

1.  <span data-ttu-id="fa67a-124">在管理中心的左侧导航Microsoft 365，转到"角色 **"。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-124">In the left navigation of the Microsoft 365 admin center, go to **Roles**.</span></span>

2.  <span data-ttu-id="fa67a-125">在"**角色"** 页上的 **"Azure AD"** 选项卡上，然后选择"**知识管理员"。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-125">On the **Roles** page, on the **Azure AD** tab, and then select **Knowledge Administrator**.</span></span>
 
3.  <span data-ttu-id="fa67a-126">在 **"知识管理员**"面板上的"**分配的** 管理员"选项卡上，选择"删除"，然后选择要从角色中删除的人。</span><span class="sxs-lookup"><span data-stu-id="fa67a-126">On the **Knowledge Administrator** panel, on the **Assigned Admins** tab, select **Remove**, and then select the person you want to remove from the role.</span></span> <span data-ttu-id="fa67a-127">若要确认，请选择"删除 **"。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-127">To confirm, select **Remove**.</span></span>

     ![管理中心中Microsoft 365"角色"页面，其中显示"已分配管理员"面板以删除用户。](../media/learning/learning-remove-knowledge-admin-1.png)

## <a name="configure-settings-for-the-learning-content-sources"></a><span data-ttu-id="fa67a-129">配置学习内容源的设置</span><span class="sxs-lookup"><span data-stu-id="fa67a-129">Configure settings for the learning content sources</span></span>

<span data-ttu-id="fa67a-130">您必须是全局Microsoft 365管理员或知识管理员才能执行这些任务。</span><span class="sxs-lookup"><span data-stu-id="fa67a-130">You must be a Microsoft 365 global administrator or knowledge admin to perform these tasks.</span></span>

<span data-ttu-id="fa67a-131">若要在 Viva Learning 中配置用于学习内容源的设置，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="fa67a-131">To configure settings for learning content sources in Viva Learning, follow these steps:</span></span>

1.  <span data-ttu-id="fa67a-132">在管理中心左侧导航Microsoft 365，**转到"设置**  >  **组织设置"。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-132">In the left navigation of the Microsoft 365 admin center, go to **Settings** > **Org settings**.</span></span>

2.  <span data-ttu-id="fa67a-133">在"**组织设置"** 页上的"服务 **"选项卡上**，选择 **"Viva Learning (Preview) "。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-133">On the **Org settings** page, on the **Services** tab, select **Viva Learning (Preview)**.</span></span>

     ![设置管理中心中的Microsoft 365"页面，其中列出了"学习"应用。](../media/learning/learning-sharepoint-configure1.png)

3.  <span data-ttu-id="fa67a-135">在 **"Viva 学习 (预览**) 面板上，选择要为组织配置的学习内容源，然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="fa67a-135">On the **Viva Learning (Preview)** panel, select the learning content sources you want to configure for the organization, and then select **Save**.</span></span>

     ![管理中心中的学习Microsoft 365显示内容源选项。](../media/learning/learning-sharepoint-configure2.png)

<span data-ttu-id="fa67a-137">在所有存在的学习源中，默认情况下将启用一些学习源。</span><span class="sxs-lookup"><span data-stu-id="fa67a-137">Among all the learning sources that exist, some will be enabled by default.</span></span> <span data-ttu-id="fa67a-138">这些学习源包括：</span><span class="sxs-lookup"><span data-stu-id="fa67a-138">These learning sources include:</span></span>

- <span data-ttu-id="fa67a-139">LinkedIn Learning (免费内容) </span><span class="sxs-lookup"><span data-stu-id="fa67a-139">LinkedIn Learning (free content)</span></span>
- <span data-ttu-id="fa67a-140">Microsoft Learn</span><span class="sxs-lookup"><span data-stu-id="fa67a-140">Microsoft Learn</span></span>
- <span data-ttu-id="fa67a-141">Microsoft 365培训</span><span class="sxs-lookup"><span data-stu-id="fa67a-141">Microsoft 365 Training</span></span>

> [!NOTE]
> <span data-ttu-id="fa67a-142">LinkedIn 免费内容根据 LinkedIn 隐私策略和用户协议提供给用户。</span><span class="sxs-lookup"><span data-stu-id="fa67a-142">LinkedIn free content is provided to users under the LinkedIn privacy policies and user agreement.</span></span> <span data-ttu-id="fa67a-143">LinkedIn 将接收用户的 IP 地址（以前由 LinkedIn 设置的任何 Cookie）并设置一个新的 Cookie 来跟踪免费内容的使用。</span><span class="sxs-lookup"><span data-stu-id="fa67a-143">LinkedIn will receive the user’s IP address, any cookies previously set by LinkedIn, and will set a new cookie to track use of free content.</span></span> <span data-ttu-id="fa67a-144">用户无需登录 LinkedIn 来接收免费内容。</span><span class="sxs-lookup"><span data-stu-id="fa67a-144">Users are not required to sign in with LinkedIn to receive free content.</span></span><br><br>
<span data-ttu-id="fa67a-145">对于 LinkedIn 高级内容，你的组织需要订阅团队来访问该内容。</span><span class="sxs-lookup"><span data-stu-id="fa67a-145">For LinkedIn premium content, your organization needs a subscription for your team to access that content.</span></span> <span data-ttu-id="fa67a-146">用户需要登录到 LinkedIn 以访问该学习，该学习根据组织的条款以及 LinkedIn 的用户条款提供。</span><span class="sxs-lookup"><span data-stu-id="fa67a-146">Users will need to sign into LinkedIn to access that learning, which is provided under the terms of your organization’s and user terms with LinkedIn.</span></span><br><br> <span data-ttu-id="fa67a-147">对于非 Microsoft (（免费 LinkedIn 内容) 除外），请确保你的组织订阅了用户使用工作帐户访问该内容，然后再将内容连接到 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="fa67a-147">For non-Microsoft content (except free LinkedIn content), ensure your organization has a subscription for your users to access that content using a work account before connecting it to Viva Learning (Preview).</span></span> <span data-ttu-id="fa67a-148">用户对非 Microsoft 学习提供商的个人订阅不会与 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="fa67a-148">Users’ personal subscriptions to non-Microsoft learning providers will not be integrated with Viva Learning (Preview).</span></span> <span data-ttu-id="fa67a-149">用户登录到非 Microsoft 和 LinkedIn Learning Pro浏览器或嵌入式查看器中学习。</span><span class="sxs-lookup"><span data-stu-id="fa67a-149">Users sign in to non-Microsoft and LinkedIn Learning Pro learnings in a browser or embedded viewer.</span></span> <span data-ttu-id="fa67a-150">如果用户导航到没有组织订阅的内容，他们可能会看到一个提供商页面，可以在其中注册单个订阅。</span><span class="sxs-lookup"><span data-stu-id="fa67a-150">If users navigate to content where they do not have an organizational subscription, they may see a provider page where they could sign up for an individual subscription.</span></span> <span data-ttu-id="fa67a-151">所有非 Microsoft 学习都根据非 Microsoft 提供商的条款提供，而不是作为 Viva 学习的一部分提供。</span><span class="sxs-lookup"><span data-stu-id="fa67a-151">All non-Microsoft learning is provided under the non-Microsoft provider’s terms and not as part of Viva Learning.</span></span> 

<span data-ttu-id="fa67a-152">若要启用或禁用学习内容源，请选中该源旁边的复选框。</span><span class="sxs-lookup"><span data-stu-id="fa67a-152">To enable or disable a learning content source, select the check box next to the source.</span></span> <span data-ttu-id="fa67a-153">如果启用源，则显示一个选中标记。</span><span class="sxs-lookup"><span data-stu-id="fa67a-153">If a source is enabled, a check mark will be visible.</span></span>

## <a name="third-party-content-providers"></a><span data-ttu-id="fa67a-154">第三方内容提供程序</span><span class="sxs-lookup"><span data-stu-id="fa67a-154">Third-party content providers</span></span> 

<span data-ttu-id="fa67a-155">可用的连接学习提供程序集可能随时更改。</span><span class="sxs-lookup"><span data-stu-id="fa67a-155">The set of available connected learning providers might change at any time.</span></span> <span data-ttu-id="fa67a-156">随着计划的发展，将有更多的提供商加入。</span><span class="sxs-lookup"><span data-stu-id="fa67a-156">More providers will join as the program grows.</span></span> <span data-ttu-id="fa67a-157">可用提供商还可以选择中断与 Viva Learning (Preview) 。</span><span class="sxs-lookup"><span data-stu-id="fa67a-157">Available providers might also choose to discontinue their connection with Viva Learning (Preview).</span></span>

### <a name="skillsoft-as-a-content-source"></a><span data-ttu-id="fa67a-158">将 Skillsoft 作为内容源</span><span class="sxs-lookup"><span data-stu-id="fa67a-158">Skillsoft as a content source</span></span>  

<span data-ttu-id="fa67a-159">对于 Viva Learning (Preview) ，启用了"技能"并选择查看"技能"内容的用户将登录 Percipio 页面，要求他们输入组织的 Percipio 网站名称。</span><span class="sxs-lookup"><span data-stu-id="fa67a-159">For Viva Learning (Preview), users who have Skillsoft enabled and choose to view Skillsoft content will land on a Percipio page that asks them to input your organization's Percipio site name.</span></span> <span data-ttu-id="fa67a-160">用户输入组织的网站名称后，他们将被定向到页面以登录到组织的 Percipio 网站。</span><span class="sxs-lookup"><span data-stu-id="fa67a-160">After users input your organization's site name, they will be directed to page to sign in to your organization's Percipio site.</span></span> <span data-ttu-id="fa67a-161">用户将使用其现有凭据登录并查看他们最初选择的内容。</span><span class="sxs-lookup"><span data-stu-id="fa67a-161">Users will sign in by using their existing credentials and see the content they originally selected.</span></span> <span data-ttu-id="fa67a-162">用户只需输入一次 Percipio 网站名称，直到清除其浏览器缓存。</span><span class="sxs-lookup"><span data-stu-id="fa67a-162">Users will be asked to input the Percipio site name only once, until their browser cache is cleared.</span></span> <span data-ttu-id="fa67a-163">若要为用户简化此体验，我们建议在发送的有关 Viva Learning (Preview) 的内部通信中包括您的 Percipio 站点) 。</span><span class="sxs-lookup"><span data-stu-id="fa67a-163">To streamline this experience for your users, we recommend including your Percipio site name in internal communications you send about Viva Learning (Preview).</span></span>

<span data-ttu-id="fa67a-164">这是用于预览的临时体验，我们正在与 Skillsoft 合作，以实现租户特定的集成以实现常规可用性，这将绕过要求用户提供组织的 Percipio 网站名称的步骤。</span><span class="sxs-lookup"><span data-stu-id="fa67a-164">This is intended to be a temporary experience for preview, and we are working with Skillsoft to enable tenant-specific integration for general availability, which will bypass the step that requires users to provide your organization's Percipio site name.</span></span> 

### <a name="details-on-microsoft-substrate"></a><span data-ttu-id="fa67a-165">有关 Microsoft 产品的详细信息</span><span class="sxs-lookup"><span data-stu-id="fa67a-165">Details on Microsoft substrate</span></span>  

<span data-ttu-id="fa67a-166">对于从非 Microsoft 服务 (学习提供程序或学习管理系统) 复制到 Viva Learning (Preview) 的数据，你无法直接在 Viva Learning (Preview) 中提取、更正或删除该数据。</span><span class="sxs-lookup"><span data-stu-id="fa67a-166">For data that you copy to Viva Learning (Preview) from a non-Microsoft service (learning provider or learning management system), you are not able to directly extract, correct, or delete that data in Viva Learning (Preview).</span></span> <span data-ttu-id="fa67a-167">我们立即刷新从非 Microsoft 提供程序导入的数据，以反映非 Microsoft 源数据中的更改和删除。</span><span class="sxs-lookup"><span data-stu-id="fa67a-167">We refresh the data you import from non-Microsoft providers promptly to reflect changes and deletions in the non-Microsoft source data.</span></span>

<span data-ttu-id="fa67a-168">您需要与非 Microsoft 服务的供应商合作，以根据非 Microsoft 服务的许可证、服务或隐私条款访问、更正、删除或提取数据。</span><span class="sxs-lookup"><span data-stu-id="fa67a-168">You need to work with the supplier of the non-Microsoft service to access, correct, delete or extract data under the license, service, or privacy terms of the non-Microsoft service.</span></span> <span data-ttu-id="fa67a-169">完成非 Microsoft 服务的数据更新周期和 Viva Learning (Preview) 后，在 Viva Learning (Preview) 中处理的数据中将反映所做的更改。</span><span class="sxs-lookup"><span data-stu-id="fa67a-169">The changes made there will be reflected in the data processed for your use in Viva Learning (Preview) upon completion of the data update cycles of the non-Microsoft service and Viva Learning (Preview).</span></span> <span data-ttu-id="fa67a-170">如果关闭 Viva Learning (Preview) 和非 Microsoft 服务之间的连接，则之前从该服务导入的所有数据都将被删除。</span><span class="sxs-lookup"><span data-stu-id="fa67a-170">If you turn off the connection between Viva Learning (Preview) and a non-Microsoft service, all data you had previously imported from that service will be deleted.</span></span> 

## <a name="next-step"></a><span data-ttu-id="fa67a-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fa67a-171">Next step</span></span>

[<span data-ttu-id="fa67a-172">将 SharePoint 配置为 Microsoft Viva Learning (Preview) </span><span class="sxs-lookup"><span data-stu-id="fa67a-172">Configure SharePoint as a learning content source for Microsoft Viva Learning (Preview)</span></span>](configure-sharepoint-content-source.md)