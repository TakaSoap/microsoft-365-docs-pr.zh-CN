---
title: 自动化 Microsoft 365 企业版测试环境的许可和组成员身份
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
ms.openlocfilehash: facff7eb556299c0312fa7488a35a96151bb1882
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40802117"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="00532-103">自动化 Microsoft 365 企业版测试环境的许可和组成员身份</span><span class="sxs-lookup"><span data-stu-id="00532-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="00532-104">*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="00532-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="00532-105">基于组的许可根据组成员身份自动分配或删除用户帐户的许可证。</span><span class="sxs-lookup"><span data-stu-id="00532-105">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="00532-106">动态组成员身份根据用户帐户属性（如部门或国家/地区）添加或删除组中的成员。</span><span class="sxs-lookup"><span data-stu-id="00532-106">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="00532-107">本文将指导您完成 Microsoft 365 企业版测试环境中的两个演示。</span><span class="sxs-lookup"><span data-stu-id="00532-107">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="00532-108">在 Microsoft 365 企业版测试环境中设置自动许可和动态组成员身份有两个阶段：</span><span class="sxs-lookup"><span data-stu-id="00532-108">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="00532-109">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="00532-109">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="00532-110">配置和测试动态组成员身份和自动许可。</span><span class="sxs-lookup"><span data-stu-id="00532-110">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="00532-112">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="00532-112">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="00532-113">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="00532-113">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="00532-114">如果只想使用最低要求以轻型方式测试自动许可和组成员身份，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="00532-114">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="00532-115">如果要在模拟的企业中测试自动授权和组成员身份，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="00532-115">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="00532-116">测试自动许可和组成员身份不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="00532-116">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="00532-117">此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="00532-117">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="00532-118">第2阶段：配置和测试动态组成员身份和自动许可</span><span class="sxs-lookup"><span data-stu-id="00532-118">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="00532-119">首先，创建一个新的 Sales 组并添加一个动态组成员身份规则，以便将部门设置为 "销售" 的用户帐户自动添加到 "销售" 组中。</span><span class="sxs-lookup"><span data-stu-id="00532-119">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="00532-120">使用 Internet 浏览器的专用实例， [https://portal.office.com](https://portal.office.com)使用 Microsoft 365 E5 测试实验室订阅的全局管理员帐户登录到 Office 365 门户。</span><span class="sxs-lookup"><span data-stu-id="00532-120">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Microsoft 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="00532-121">在浏览器的一个单独的选项卡上，转到 Azure [https://portal.azure.com](https://portal.azure.com)门户处。</span><span class="sxs-lookup"><span data-stu-id="00532-121">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="00532-122">在 Azure 门户中，在搜索框中键入**组**，然后单击 "**组**"。</span><span class="sxs-lookup"><span data-stu-id="00532-122">In the Azure portal, type **groups** in the search box, and then click **Groups**.</span></span>
4. <span data-ttu-id="00532-123">在 "**所有组**" 窗格中，单击 "**新建组**"。</span><span class="sxs-lookup"><span data-stu-id="00532-123">in the **All groups** pane, click **New group**.</span></span>
5. <span data-ttu-id="00532-124">在 "**组类型**" 中，选择 " **Office 365**"。</span><span class="sxs-lookup"><span data-stu-id="00532-124">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="00532-125">在 "**组名称**" 中，键入**Sales**。</span><span class="sxs-lookup"><span data-stu-id="00532-125">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="00532-126">在 "**成员身份类型**" 中，选择 "**动态用户**"。</span><span class="sxs-lookup"><span data-stu-id="00532-126">In **Membership type**, select **Dynamic user**.</span></span>
8. <span data-ttu-id="00532-127">单击 "**动态用户成员**"。</span><span class="sxs-lookup"><span data-stu-id="00532-127">Click **Dynamic user members**.</span></span>
9. <span data-ttu-id="00532-128">在 "**动态成员身份规则**" 窗格中：</span><span class="sxs-lookup"><span data-stu-id="00532-128">In the **Dynamic membership rules** pane:</span></span> 
   - <span data-ttu-id="00532-129">选择 "**部门**" 属性。</span><span class="sxs-lookup"><span data-stu-id="00532-129">Select the **department** property.</span></span>
   - <span data-ttu-id="00532-130">选择 "**等于**" 运算符。</span><span class="sxs-lookup"><span data-stu-id="00532-130">Select the **Equals** operator.</span></span>
   - <span data-ttu-id="00532-131">键入**值**中的**销售额**。</span><span class="sxs-lookup"><span data-stu-id="00532-131">Type **Sales** in **Value**.</span></span>
10. <span data-ttu-id="00532-132">单击 **“保存”**。</span><span class="sxs-lookup"><span data-stu-id="00532-132">Click **Save**.</span></span>
11. <span data-ttu-id="00532-133">单击“**创建**”。</span><span class="sxs-lookup"><span data-stu-id="00532-133">Click **Create**.</span></span>

<span data-ttu-id="00532-134">接下来，配置 "销售" 组，以便自动向成员分配 Microsoft 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="00532-134">Next, you configure the Sales group so that members are automatically assigned the Microsoft 365 E5 license.</span></span>

1. <span data-ttu-id="00532-135">单击 "**销售**" 组，然后单击 "**许可证**"。</span><span class="sxs-lookup"><span data-stu-id="00532-135">Click the **Sales** group, and then click **Licenses**.</span></span>
2. <span data-ttu-id="00532-136">在 "**更新许可证分配**" 窗格中，选择 " **Microsoft 365 E5**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="00532-136">In the **Update license assignments** pane, select **Microsoft 365 E5**, and then click **Save**.</span></span>
3. <span data-ttu-id="00532-137">关闭浏览器中的 Azure 门户选项卡。</span><span class="sxs-lookup"><span data-stu-id="00532-137">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="00532-138">接下来，在用户4帐户上测试动态组成员身份和自动许可。</span><span class="sxs-lookup"><span data-stu-id="00532-138">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="00532-139">在浏览器中的 " **Microsoft Office 主页**" 选项卡上，单击 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="00532-139">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="00532-140">在 " **Microsoft 365 管理中心**" 选项卡上，单击 "**活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="00532-140">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="00532-141">在 "**活动用户**" 页上，单击 "**用户 4** " 帐户。</span><span class="sxs-lookup"><span data-stu-id="00532-141">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="00532-142">在 "**用户 4** " 窗格中，单击 "**产品许可证**" 的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="00532-142">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="00532-143">在 "**产品许可证**" 窗格上，禁用**Microsoft 365 E5**许可证，然后单击 "**保存" > "关闭**"。</span><span class="sxs-lookup"><span data-stu-id="00532-143">On the **Product licenses** pane, disable the **Microsoft 365 E5** license, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="00532-144">在 "User 4" 帐户的 "属性" 中，确认未分配任何产品许可证，并且没有组成员身份。</span><span class="sxs-lookup"><span data-stu-id="00532-144">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="00532-145">单击\*\*\*\* "编辑**联系人信息**"。</span><span class="sxs-lookup"><span data-stu-id="00532-145">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="00532-146">在 "**编辑联系人信息**" 窗格中，单击 "**联系人信息**"。</span><span class="sxs-lookup"><span data-stu-id="00532-146">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="00532-147">在 "**部门**" 字段中，键入**Sales**，然后单击 "**保存" > "关闭**"。</span><span class="sxs-lookup"><span data-stu-id="00532-147">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="00532-148">等待几分钟，然后定期单击 "用户 4" 帐户窗格右上角的 "刷新" 图标。</span><span class="sxs-lookup"><span data-stu-id="00532-148">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="00532-149">您应该会看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="00532-149">In time you should see the:</span></span>

- <span data-ttu-id="00532-150">更新了**Sales**组的**组成员身份**属性。</span><span class="sxs-lookup"><span data-stu-id="00532-150">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="00532-151">使用**Microsoft 365 E5**许可证更新的 "**产品许可证**" 属性。</span><span class="sxs-lookup"><span data-stu-id="00532-151">**Product licenses** property updated with the **Microsoft 365 E5** license.</span></span>

<span data-ttu-id="00532-152">请参阅 Identity 阶段的这些步骤，了解在生产中部署动态组成员身份和自动许可的信息和链接：</span><span class="sxs-lookup"><span data-stu-id="00532-152">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="00532-153">设置自动许可</span><span class="sxs-lookup"><span data-stu-id="00532-153">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="00532-154">设置动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="00532-154">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="00532-155">后续步骤</span><span class="sxs-lookup"><span data-stu-id="00532-155">Next step</span></span>

<span data-ttu-id="00532-156">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="00532-156">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="00532-157">另请参阅</span><span class="sxs-lookup"><span data-stu-id="00532-157">See also</span></span>

[<span data-ttu-id="00532-158">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="00532-158">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="00532-159">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="00532-159">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="00532-160">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="00532-160">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="00532-161">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="00532-161">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
