---
title: 自动化 Microsoft 365 企业版测试环境的许可和组成员身份
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 在 Microsoft 365 企业版测试环境中配置基于组的许可和动态组成员身份。
ms.openlocfilehash: 26840e2884202a0fa9c4bb563f3d7c653482ef87
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50905364"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4f980-103">自动化 Microsoft 365 企业版测试环境的许可和组成员身份</span><span class="sxs-lookup"><span data-stu-id="4f980-103">Automate licensing and group membership for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4f980-104">*本测试实验室指南仅适用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="4f980-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="4f980-105">基于组的许可根据组成员身份自动分配或删除用户帐户的许可证。</span><span class="sxs-lookup"><span data-stu-id="4f980-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="4f980-106">动态组成员身份基于用户帐户属性（如部门或国家/地区）向组添加或删除 **成员**。 </span><span class="sxs-lookup"><span data-stu-id="4f980-106">Dynamic group membership adds or removes members to a group based on user account properties, such as **Department** or **Country**.</span></span> <span data-ttu-id="4f980-107">本文将分步演示在 Microsoft 365 企业版测试环境中添加和删除组的成员。</span><span class="sxs-lookup"><span data-stu-id="4f980-107">This article steps you through demonstrations of both adding and removing group members in your Microsoft 365 for enterprise test environment.</span></span>

<span data-ttu-id="4f980-108">在 Microsoft 365 企业版测试环境中设置自动许可和动态组成员身份包括两个阶段：</span><span class="sxs-lookup"><span data-stu-id="4f980-108">Setting up auto-licensing and dynamic group membership in your Microsoft 365 for enterprise test environment involves two phases:</span></span>

- [<span data-ttu-id="4f980-109">第 1 阶段：构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="4f980-109">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>](#phase-1-build-out-your-microsoft-365-for-enterprise-test-environment)
- [<span data-ttu-id="4f980-110">阶段 2：配置和测试动态组成员身份和自动许可</span><span class="sxs-lookup"><span data-stu-id="4f980-110">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>](#phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing)

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="4f980-112">有关 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观地图，请转到 [Microsoft 365 企业版测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="4f980-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="4f980-113">第 1 阶段：构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="4f980-113">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="4f980-114">如果你希望仅测试具有最低要求的轻型自动许可和组成员身份，请按照轻型基本配置 [中的说明进行操作](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="4f980-114">If you want to only test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="4f980-115">如果要在模拟的企业中测试自动许可和组成员身份，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="4f980-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="4f980-116">测试自动许可和组成员身份不需要模拟的企业测试环境，该环境包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="4f980-116">Testing automated licensing and group membership doesn't require the simulated enterprise test environment, which includes a simulated intranet connected to the internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="4f980-117">它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并尝试在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="4f980-117">It's provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span>
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="4f980-118">阶段 2：配置和测试动态组成员身份和自动许可</span><span class="sxs-lookup"><span data-stu-id="4f980-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="4f980-119">首先，创建一个名为 Sales 的新组，并添加动态组成员身份规则，以便部门设置为 **Sales** 的用户帐户自动加入销售组。</span><span class="sxs-lookup"><span data-stu-id="4f980-119">First, create a new group named Sales, and add a dynamic group membership rule so that user accounts with the **Department** set to **Sales** automatically join the Sales group.</span></span>

1. <span data-ttu-id="4f980-120">在 Internet 浏览器的专用实例中，使用 [Microsoft 365](https://admin.microsoft.com) E5 测试实验室订阅的全局管理员帐户登录 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="4f980-120">In a private instance of your internet browser, sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="4f980-121">在浏览器的单独选项卡上，转到 Azure 门户，位于 [https://portal.azure.com](https://portal.azure.com) 。</span><span class="sxs-lookup"><span data-stu-id="4f980-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="4f980-122">在 Azure 门户中，在 **搜索** 框中输入组， **然后选择组**。</span><span class="sxs-lookup"><span data-stu-id="4f980-122">In the Azure portal, enter **groups** in the search box, and then select **Groups**.</span></span>
4. <span data-ttu-id="4f980-123">在"**所有组"** 窗格中，选择"**新建组"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-123">in the **All groups** pane, select **New group**.</span></span>
5. <span data-ttu-id="4f980-124">在 **"组类型"** 中，选择 **"Microsoft 365"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-124">In **Group type**, select **Microsoft 365**.</span></span>
6. <span data-ttu-id="4f980-125">在 **"组名称"** 中，输入 **"销售"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-125">In **Group name**, enter **Sales**.</span></span>
7. <span data-ttu-id="4f980-126">在 **"成员身份类型"** 中，选择 **"动态用户"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="4f980-127">选择 **"动态用户成员"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-127">Select **Dynamic user members**.</span></span>
9. <span data-ttu-id="4f980-128">在" **动态成员资格规则"** 窗格中：</span><span class="sxs-lookup"><span data-stu-id="4f980-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="4f980-129">选择 **部门** 属性。</span><span class="sxs-lookup"><span data-stu-id="4f980-129">Select the **department** property.</span></span>
   - <span data-ttu-id="4f980-130">选择 **"等于"** 运算符。</span><span class="sxs-lookup"><span data-stu-id="4f980-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="4f980-131">在"**值"** 框中，输入 **"销售"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-131">In the **Value** box, enter **Sales**.</span></span>
10. <span data-ttu-id="4f980-132">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="4f980-132">Select **Save**.</span></span>
11. <span data-ttu-id="4f980-133">选择“创建”。</span><span class="sxs-lookup"><span data-stu-id="4f980-133">Select **Create**.</span></span>

<span data-ttu-id="4f980-134">接下来，配置"销售"组，以便自动为成员分配 Microsoft 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="4f980-134">Next, configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="4f980-135">选择"**销售"** 组，然后选择"许可证 **"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-135">Select the **Sales** group, and then select **Licenses**.</span></span>
2. <span data-ttu-id="4f980-136">在"**更新许可证分配"** 窗格中，选择 **"Microsoft 365 E5"，** 然后选择"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then select **Save**.</span></span>
3. <span data-ttu-id="4f980-137">在浏览器中，关闭 Azure 门户选项卡。</span><span class="sxs-lookup"><span data-stu-id="4f980-137">In your browser, close the Azure portal tab.</span></span>

<span data-ttu-id="4f980-138">接下来，在 User 4 帐户上测试动态组成员身份和自动许可：</span><span class="sxs-lookup"><span data-stu-id="4f980-138">Next, test dynamic group membership and automatic licensing on the User 4 account:</span></span>

1. <span data-ttu-id="4f980-139">从浏览器 **Microsoft Office** 主页"选项卡中，选择"管理员 **"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-139">From the **Microsoft Office Home** tab in your browser, select **Admin**.</span></span>
2. <span data-ttu-id="4f980-140">从 **"Microsoft 365 管理中心"选项卡中**，选择"**活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-140">From the **Microsoft 365 admin center** tab, select **Active users**.</span></span>
3. <span data-ttu-id="4f980-141">在" **活动用户"** 页上，选择 **"用户 4"** 帐户。</span><span class="sxs-lookup"><span data-stu-id="4f980-141">On the **Active users** page, select the **User 4** account.</span></span>
4. <span data-ttu-id="4f980-142">在"**用户 4"** 窗格中，为 **"产品许可证\*\*\*\*"选择"编辑"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-142">On the **User 4** pane, select **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="4f980-143">在产品 **许可证窗格中**，禁用 **Microsoft 365 E5** 许可证，然后选择保存  >  **关闭**。</span><span class="sxs-lookup"><span data-stu-id="4f980-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then select **Save** > **Close**.</span></span>
6. <span data-ttu-id="4f980-144">在 User 4 帐户的属性中，确认尚未分配任何产品许可证，并且没有组成员身份。</span><span class="sxs-lookup"><span data-stu-id="4f980-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="4f980-145">对于 **"联系人信息"，** 选择"编辑 **"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-145">For **Contact information**, select **Edit**.</span></span>
8. <span data-ttu-id="4f980-146">在"**编辑联系人信息"窗格中**，选择"**联系人信息"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-146">In the **Edit Contact information** pane, select **Contact information**.</span></span>
9. <span data-ttu-id="4f980-147">在"**部门"** 框中，输入 **"销售"，** 然后选择"**保存""**  >  **关闭"。**</span><span class="sxs-lookup"><span data-stu-id="4f980-147">In the **Department** box, enter **Sales**, and then select **Save** > **Close**.</span></span>
10. <span data-ttu-id="4f980-148">等待几分钟，然后定期选择"用户 4"帐户窗格右上方的"刷新"图标。 </span><span class="sxs-lookup"><span data-stu-id="4f980-148">Wait a few minutes, and then periodically select the **Refresh** icon in the upper-right of the User 4 account pane.</span></span>

<span data-ttu-id="4f980-149">随着时间的推移，你应该会看到：</span><span class="sxs-lookup"><span data-stu-id="4f980-149">In time, you should see the:</span></span>

- <span data-ttu-id="4f980-150">**使用 Sales 组** 更新的组 **成员身份** 属性。</span><span class="sxs-lookup"><span data-stu-id="4f980-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="4f980-151">**使用** **Microsoft 365 E5** 许可证更新了产品许可证属性。</span><span class="sxs-lookup"><span data-stu-id="4f980-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="4f980-152">请参阅以下文章以在生产中部署动态组成员身份和自动许可：</span><span class="sxs-lookup"><span data-stu-id="4f980-152">See these articles to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="4f980-153">Azure Active Directory 中基于组的许可</span><span class="sxs-lookup"><span data-stu-id="4f980-153">Group-based licensing in Azure Active Directory</span></span>](/azure/active-directory/fundamentals/active-directory-licensing-whatis-azure-portal)
- [<span data-ttu-id="4f980-154">Azure Active Directory 中的动态组</span><span class="sxs-lookup"><span data-stu-id="4f980-154">Dynamic groups in Azure Active Directory</span></span>](/azure/active-directory/users-groups-roles/groups-create-rule)

## <a name="next-step"></a><span data-ttu-id="4f980-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="4f980-155">Next step</span></span>

<span data-ttu-id="4f980-156">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="4f980-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="4f980-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="4f980-157">See also</span></span>

[<span data-ttu-id="4f980-158">标识路线图</span><span class="sxs-lookup"><span data-stu-id="4f980-158">Identity roadmap</span></span>](identity-roadmap-microsoft-365.md)

[<span data-ttu-id="4f980-159">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="4f980-159">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="4f980-160">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="4f980-160">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="4f980-161">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="4f980-161">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)