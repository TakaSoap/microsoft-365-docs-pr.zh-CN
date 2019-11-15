---
title: 自动化 Microsoft 365 企业版测试环境的许可和组成员身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-identity-device-management
ms.custom:
- TLG
- Ent_TLGs
description: 在 Microsoft 365 企业版测试环境中配置基于组的许可和动态组成员身份。
ms.openlocfilehash: c3b515a9b453275f9b79ba2b90d5a4c14611c2aa
ms.sourcegitcommit: 2c2248b03f7753d64490f2f7e56ec644a235b65a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38639792"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="42539-103">自动化 Microsoft 365 企业版测试环境的许可和组成员身份</span><span class="sxs-lookup"><span data-stu-id="42539-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="42539-104">基于组的许可根据组成员身份自动分配或删除用户帐户的许可证。</span><span class="sxs-lookup"><span data-stu-id="42539-104">Group-based licensing automatically assigns or removes licenses for a user account based on group membership.</span></span> <span data-ttu-id="42539-105">动态组成员身份根据用户帐户属性（如部门或国家/地区）添加或删除组中的成员。</span><span class="sxs-lookup"><span data-stu-id="42539-105">Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country.</span></span> <span data-ttu-id="42539-106">本文将指导您完成 Microsoft 365 企业版测试环境中的两个演示。</span><span class="sxs-lookup"><span data-stu-id="42539-106">This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="42539-107">在 Microsoft 365 企业版测试环境中设置自动许可和动态组成员身份有两个阶段：</span><span class="sxs-lookup"><span data-stu-id="42539-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="42539-108">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="42539-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="42539-109">配置和测试动态组成员身份和自动许可。</span><span class="sxs-lookup"><span data-stu-id="42539-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="42539-111">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="42539-111">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="42539-112">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="42539-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="42539-113">如果只想使用最低要求以轻型方式测试自动许可和组成员身份，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="42539-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="42539-114">如果要在模拟的企业中测试自动授权和组成员身份，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="42539-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="42539-115">测试自动许可和组成员身份不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="42539-115">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="42539-116">此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="42539-116">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="42539-117">第2阶段：配置和测试动态组成员身份和自动许可</span><span class="sxs-lookup"><span data-stu-id="42539-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="42539-118">首先，创建一个新的 Sales 组并添加一个动态组成员身份规则，以便将部门设置为 "销售" 的用户帐户自动添加到 "销售" 组中。</span><span class="sxs-lookup"><span data-stu-id="42539-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="42539-119">使用 Internet 浏览器的专用实例， [https://portal.office.com](https://portal.office.com)使用 Office 365 E5 测试实验室订阅的全局管理员帐户登录到 office 365 门户。</span><span class="sxs-lookup"><span data-stu-id="42539-119">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 test lab subscription.</span></span>
2. <span data-ttu-id="42539-120">在浏览器的一个单独的选项卡上，转到 Azure [https://portal.azure.com](https://portal.azure.com)门户处。</span><span class="sxs-lookup"><span data-stu-id="42539-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="42539-121">在 Azure 门户中，单击“Azure Active Directory”>“用户和组”>“所有组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42539-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="42539-122">在 "**所有组**" 边栏选项卡上，单击 "**新建组**"。</span><span class="sxs-lookup"><span data-stu-id="42539-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="42539-123">在 "**组类型**" 中，选择 " **Office 365**"。</span><span class="sxs-lookup"><span data-stu-id="42539-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="42539-124">在 "**组名称**" 中，键入**Sales**。</span><span class="sxs-lookup"><span data-stu-id="42539-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="42539-125">在 "**成员身份类型**" 中，选择 "**动态用户**"。</span><span class="sxs-lookup"><span data-stu-id="42539-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="42539-126">单击“添加动态查询”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42539-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="42539-127">在“添加以下位置的用户”\*\*\*\* 中，选择“部门”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42539-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="42539-128">在下一个字段中，选择“等于”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42539-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="42539-129">在下一个字段中，键入**Sales**。</span><span class="sxs-lookup"><span data-stu-id="42539-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="42539-130">单击“添加查询”\*\*\*\*，然后单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="42539-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="42539-131">关闭 "**组**" 和 "**组"-"所有组**" 刀片。</span><span class="sxs-lookup"><span data-stu-id="42539-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="42539-132">接下来，配置 Sales 组，以便自动为成员分配 Office 365 E5 和企业移动性 + 安全 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="42539-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="42539-133">在 "适用于 Azure Active Directory 的**概述**刀片" 中，单击 "**许可证 > 所有产品**"。</span><span class="sxs-lookup"><span data-stu-id="42539-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="42539-134">在列表中，选择“**企业移动性 + 安全性 E5**”和“**Office 365 企业版 E5**”，然后单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="42539-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="42539-135">在 "**分配许可证**" 边栏选项卡上，单击 "**用户和组**"。</span><span class="sxs-lookup"><span data-stu-id="42539-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="42539-136">在组列表中，选择 "**销售**" 组。</span><span class="sxs-lookup"><span data-stu-id="42539-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="42539-137">单击“**选择**”，然后单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="42539-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="42539-138">关闭浏览器中的 Azure 门户选项卡。</span><span class="sxs-lookup"><span data-stu-id="42539-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="42539-139">接下来，在用户4帐户上测试动态组成员身份和自动许可。</span><span class="sxs-lookup"><span data-stu-id="42539-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="42539-140">在浏览器中的 " **Microsoft Office 主页**" 选项卡上，单击 "**管理**"。</span><span class="sxs-lookup"><span data-stu-id="42539-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="42539-141">在 " **Microsoft 365 管理中心**" 选项卡上，单击 "**活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="42539-141">From the **Microsoft 365 admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="42539-142">在 "**活动用户**" 页上，单击 "**用户 4** " 帐户。</span><span class="sxs-lookup"><span data-stu-id="42539-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="42539-143">在 "**用户 4** " 窗格中，单击 "**产品许可证**" 的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="42539-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="42539-144">在 "**产品许可证**" 窗格中，关闭**企业移动性 + 安全 E5**和**Office 365 企业版 E5**许可证，然后单击 "**保存" > "关闭**"。</span><span class="sxs-lookup"><span data-stu-id="42539-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="42539-145">在 "User 4" 帐户的 "属性" 中，确认未分配任何产品许可证，并且没有组成员身份。</span><span class="sxs-lookup"><span data-stu-id="42539-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="42539-146">单击\*\*\*\* "编辑**联系人信息**"。</span><span class="sxs-lookup"><span data-stu-id="42539-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="42539-147">在 "**编辑联系人信息**" 窗格中，单击 "**联系人信息**"。</span><span class="sxs-lookup"><span data-stu-id="42539-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="42539-148">在 "**部门**" 字段中，键入**Sales**，然后单击 "**保存" > "关闭**"。</span><span class="sxs-lookup"><span data-stu-id="42539-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="42539-149">等待几分钟，然后定期单击 "用户 4" 帐户窗格右上角的 "刷新" 图标。</span><span class="sxs-lookup"><span data-stu-id="42539-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="42539-150">您应该会看到以下内容：</span><span class="sxs-lookup"><span data-stu-id="42539-150">In time you should see the:</span></span>

- <span data-ttu-id="42539-151">更新了**Sales**组的**组成员身份**属性。</span><span class="sxs-lookup"><span data-stu-id="42539-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="42539-152">使用**企业移动性 + 安全 E5**和**Office 365 企业版 e5**许可证更新的**产品许可证**属性。</span><span class="sxs-lookup"><span data-stu-id="42539-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="42539-153">请参阅 Identity 阶段的这些步骤，了解在生产中部署动态组成员身份和自动许可的信息和链接：</span><span class="sxs-lookup"><span data-stu-id="42539-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="42539-154">设置自动许可</span><span class="sxs-lookup"><span data-stu-id="42539-154">Set up automatic licensing</span></span>](identity-use-group-management.md#identity-group-license)
- [<span data-ttu-id="42539-155">设置动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="42539-155">Set up dynamic group membership</span></span>](identity-use-group-management.md#identity-dyn-groups)

## <a name="next-step"></a><span data-ttu-id="42539-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="42539-156">Next step</span></span>

<span data-ttu-id="42539-157">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="42539-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="42539-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="42539-158">See also</span></span>

[<span data-ttu-id="42539-159">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="42539-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="42539-160">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="42539-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="42539-161">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="42539-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="42539-162">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="42539-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
