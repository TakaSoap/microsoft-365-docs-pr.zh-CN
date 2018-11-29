---
title: 自动为您的 Microsoft 365 企业版测试环境的许可和组成员身份
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom:
- TLG
- Ent_TLGs
description: Microsoft 365 企业版测试环境中配置基于组的许可和动态组成员身份。
ms.openlocfilehash: 46d2f0ca063b387d1a4a51b4ea97bd5d60c03fe5
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865787"
---
# <a name="automate-licensing-and-group-membership-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="393f1-103">自动为您的 Microsoft 365 企业版测试环境的许可和组成员身份</span><span class="sxs-lookup"><span data-stu-id="393f1-103">Automate licensing and group membership for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="393f1-p101">基于组的自动许可分配或删除许可证根据组成员身份的用户帐户。动态组成员身份添加或删除成员添加到一组基于用户帐户属性，如部门或国家/地区。本文将向您演示 Microsoft 365 企业版测试环境中的这两种。</span><span class="sxs-lookup"><span data-stu-id="393f1-p101">Group-based licensing automatically assigns or removes licenses for a user account based on group membership. Dynamic group membership adds or removes members to a group based on user account properties, such as Department or Country. This article steps you through a demonstration of both in your Microsoft 365 Enterprise test environment.</span></span>

<span data-ttu-id="393f1-107">有两个阶段设置 Microsoft 365 企业版测试环境中的自动许可和动态组成员身份：</span><span class="sxs-lookup"><span data-stu-id="393f1-107">There are two phases to setting up auto-licensing and dynamic group membership in your Microsoft 365 Enterprise test environment:</span></span>

1. <span data-ttu-id="393f1-108">创建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="393f1-108">Create the Microsoft 365 Enterprise test environment.</span></span>
2. <span data-ttu-id="393f1-109">配置和测试动态组成员身份和自动许可。</span><span class="sxs-lookup"><span data-stu-id="393f1-109">Configure and test dynamic group membership and automatic licensing.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="393f1-111">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="393f1-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="393f1-112">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="393f1-112">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="393f1-113">如果您只想要的最低硬件要求与轻型方式测试自动许可和组成员身份，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="393f1-113">If you just want to test automated licensing and group membership in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="393f1-114">如果您想要在模拟企业中测试自动许可和组成员身份，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="393f1-114">If you want to test automated licensing and group membership in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="393f1-p102">测试自动许可和组成员身份不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。</span><span class="sxs-lookup"><span data-stu-id="393f1-p102">Testing automated licensing and group membership does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 
  
## <a name="phase-2-configure-and-test-dynamic-group-membership-and-automatic-licensing"></a><span data-ttu-id="393f1-117">第 2 阶段： 配置和测试动态组成员身份和自动许可</span><span class="sxs-lookup"><span data-stu-id="393f1-117">Phase 2: Configure and test dynamic group membership and automatic licensing</span></span>

<span data-ttu-id="393f1-118">首先，创建一个新的销售组，并添加动态组成员资格规则，以便与设置为销售部门的用户帐户会自动添加到 Sales 组。</span><span class="sxs-lookup"><span data-stu-id="393f1-118">First, you create a new Sales group and add a dynamic group membership rule so that user accounts with the Department set to Sales are automatically added to the Sales group.</span></span>

1. <span data-ttu-id="393f1-119">使用专用的 Internet 浏览器实例时，登录到 Office 365 门户[https://portal.office.com](https://portal.office.com)与您的 Office 365 E5 试用订阅的全局管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="393f1-119">Using a private instance of your Internet browser, sign in to the Office 365 portal at [https://portal.office.com](https://portal.office.com) with the global administrator account of your Office 365 E5 trial subscription.</span></span>
2. <span data-ttu-id="393f1-120">在浏览器的独立选项卡上，转到在 Azure 门户[https://portal.azure.com](https://portal.azure.com)。</span><span class="sxs-lookup"><span data-stu-id="393f1-120">On a separate tab of your browser, go to the Azure portal at [https://portal.azure.com](https://portal.azure.com).</span></span>
3. <span data-ttu-id="393f1-121">在 Azure 门户中，单击“Azure Active Directory”>“用户和组”>“所有组”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="393f1-121">In the Azure portal, click **Azure Active Directory > Users and groups > All groups**.</span></span>
4. <span data-ttu-id="393f1-122">在**所有组**刀片中，单击**新组**。</span><span class="sxs-lookup"><span data-stu-id="393f1-122">On the **All groups** blade, click **New group**.</span></span>
5. <span data-ttu-id="393f1-123">在**组类型**中，选择**Office 365**。</span><span class="sxs-lookup"><span data-stu-id="393f1-123">In **Group type**, select **Office 365**.</span></span>
6. <span data-ttu-id="393f1-124">在**组名**框中，键入**销售**。</span><span class="sxs-lookup"><span data-stu-id="393f1-124">In **Group name**, type **Sales**.</span></span>
7. <span data-ttu-id="393f1-125">在**成员资格类型**中，选择**动态用户**。</span><span class="sxs-lookup"><span data-stu-id="393f1-125">In **Membership type**, select **Dynamic user** .</span></span>
8. <span data-ttu-id="393f1-126">单击“添加动态查询”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="393f1-126">Click **Add dynamic query**.</span></span>
9. <span data-ttu-id="393f1-127">在“添加以下位置的用户”\*\*\*\* 中，选择“部门”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="393f1-127">In **Add users where**, select **department**.</span></span>
10. <span data-ttu-id="393f1-128">在下一个字段中，选择“等于”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="393f1-128">In the next field, select **Equals**.</span></span>
11. <span data-ttu-id="393f1-129">在下一步字段中，键入**销售**。</span><span class="sxs-lookup"><span data-stu-id="393f1-129">In the next field, type **Sales**.</span></span>
12. <span data-ttu-id="393f1-130">单击“添加查询”\*\*\*\*，然后单击“创建”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="393f1-130">Click **Add query**, and then click **Create**.</span></span>
13. <span data-ttu-id="393f1-131">关闭**组**和**组的所有组**刀片。</span><span class="sxs-lookup"><span data-stu-id="393f1-131">Close the **Group** and **Groups-All groups** blades.</span></span>

<span data-ttu-id="393f1-132">接下来，您配置 Sales 组，以便 Office 365 E5 和企业移动多个安全 E5 许可证自动分配成员。</span><span class="sxs-lookup"><span data-stu-id="393f1-132">Next, you configure the Sales group so that members are automatically assigned Office 365 E5 and Enterprise Mobility + Security E5 licenses.</span></span>

1. <span data-ttu-id="393f1-133">在 Azure Active Directory**概述**刀片中，单击**许可证 > 所有产品**。</span><span class="sxs-lookup"><span data-stu-id="393f1-133">On the **Overview** blade for Azure Active Directory, click **Licenses > All products**.</span></span>
2. <span data-ttu-id="393f1-134">在列表中，选择“**企业移动性 + 安全性 E5**”和“**Office 365 企业版 E5**”，然后单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="393f1-134">In the list, select **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5**, and then click **Assign**.</span></span>
3. <span data-ttu-id="393f1-135">在**分配许可证**刀片中，单击**用户和组**。</span><span class="sxs-lookup"><span data-stu-id="393f1-135">On the **Assign license** blade, click **Users and groups**.</span></span>
4. <span data-ttu-id="393f1-136">在组列表中，选择**销售**组。</span><span class="sxs-lookup"><span data-stu-id="393f1-136">In the list of groups, select the **Sales** group.</span></span>
5. <span data-ttu-id="393f1-137">单击“**选择**”，然后单击“**分配**”。</span><span class="sxs-lookup"><span data-stu-id="393f1-137">Click **Select**, and then click **Assign**.</span></span>
6. <span data-ttu-id="393f1-138">关闭浏览器中的 Azure 门户选项卡。</span><span class="sxs-lookup"><span data-stu-id="393f1-138">Close the Azure portal tab in your browser.</span></span>

<span data-ttu-id="393f1-139">接下来，测试动态组成员身份和用户 4 帐户自动许可。</span><span class="sxs-lookup"><span data-stu-id="393f1-139">Next, you test dynamic group membership and automatic licensing on the User 4 account.</span></span> 

1. <span data-ttu-id="393f1-140">从**Microsoft Office Home**选项卡上的在浏览器中，单击**管理**。</span><span class="sxs-lookup"><span data-stu-id="393f1-140">From the **Microsoft Office Home** tab in your browser, click **Admin**.</span></span>
2. <span data-ttu-id="393f1-141">从**Office Admin center**选项卡，单击**活动用户**。</span><span class="sxs-lookup"><span data-stu-id="393f1-141">From the **Office Admin center** tab, click **Active users**.</span></span>
3. <span data-ttu-id="393f1-142">在**活动用户**页上，单击**用户 4**帐户。</span><span class="sxs-lookup"><span data-stu-id="393f1-142">On the **Active users** page, click the **User 4** account.</span></span>
4. <span data-ttu-id="393f1-143">在**用户 4**窗格中，单击**产品**许可证的**编辑**。</span><span class="sxs-lookup"><span data-stu-id="393f1-143">On the **User 4** pane, click **Edit** for **Product licenses**.</span></span>
5. <span data-ttu-id="393f1-144">在**产品许可证**窗格中，打开**企业移动 + 安全 E5**和**Office 365 企业 E5**许可证关闭，然后单击**保存 > 关闭**。</span><span class="sxs-lookup"><span data-stu-id="393f1-144">On the **Product licenses** pane, turn the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses off, and then click **Save > Close**.</span></span>
6. <span data-ttu-id="393f1-145">在用户 4 帐户的属性，确认没有产品许可证已分配不有任何组成员身份。</span><span class="sxs-lookup"><span data-stu-id="393f1-145">In the properties of the User 4 account, verify that no product licenses have been assigned and there are no group memberships.</span></span>
7. <span data-ttu-id="393f1-146">**联系人**信息，请单击**编辑**。</span><span class="sxs-lookup"><span data-stu-id="393f1-146">Click **Edit** for **Contact information**.</span></span>
8. <span data-ttu-id="393f1-147">在**编辑联系人信息**窗格中，单击**联系人信息**。</span><span class="sxs-lookup"><span data-stu-id="393f1-147">In the **Edit Contact information** pane, click **Contact information**.</span></span>
9. <span data-ttu-id="393f1-148">在**部门**字段中，键入**销售**、，然后单击**保存 > 关闭**。</span><span class="sxs-lookup"><span data-stu-id="393f1-148">In the **Department** field, type **Sales**, and then click **Save > Close**.</span></span>
10. <span data-ttu-id="393f1-149">等待几分钟，然后定期单击右上角用户 4 帐户窗格中的刷新图标。</span><span class="sxs-lookup"><span data-stu-id="393f1-149">Wait a few minutes, and then periodically click the refresh icon in the upper-right of the User 4 account pane.</span></span> 

<span data-ttu-id="393f1-150">您应看到时间:</span><span class="sxs-lookup"><span data-stu-id="393f1-150">In time you should see the:</span></span>

- <span data-ttu-id="393f1-151">使用**销售**组进行了更新的**组成员身份**属性。</span><span class="sxs-lookup"><span data-stu-id="393f1-151">**Group memberships** property updated with the **Sales** group.</span></span>
- <span data-ttu-id="393f1-152">更新了**企业移动 + 安全 E5**和**Office 365 企业 E5**许可证**产品许可证**属性。</span><span class="sxs-lookup"><span data-stu-id="393f1-152">**Product licenses** property updated with the **Enterprise Mobility + Security E5** and **Office 365 Enterprise E5** licenses.</span></span>

<span data-ttu-id="393f1-153">有关信息和链接部署动态组成员身份和生产环境中自动许可的标识阶段，请参阅以下步骤：</span><span class="sxs-lookup"><span data-stu-id="393f1-153">See these steps in the Identity phase for information and links to deploy dynamic group membership and automatic licensing in production:</span></span>

- [<span data-ttu-id="393f1-154">设置自动许可</span><span class="sxs-lookup"><span data-stu-id="393f1-154">Set up automatic licensing</span></span>](identity-group-based-licensing.md)
- [<span data-ttu-id="393f1-155">设置动态组成员身份</span><span class="sxs-lookup"><span data-stu-id="393f1-155">Set up dynamic group membership</span></span>](identity-automatic-group-membership.md)

## <a name="next-step"></a><span data-ttu-id="393f1-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="393f1-156">Next step</span></span>

<span data-ttu-id="393f1-157">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="393f1-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="393f1-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="393f1-158">See also</span></span>

[<span data-ttu-id="393f1-159">阶段 2：标识</span><span class="sxs-lookup"><span data-stu-id="393f1-159">Phase 2: Identity</span></span>](identity-infrastructure.md)

[<span data-ttu-id="393f1-160">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="393f1-160">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="393f1-161">Microsoft 365 企业版部署</span><span class="sxs-lookup"><span data-stu-id="393f1-161">Microsoft 365 Enterprise deployment</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="393f1-162">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="393f1-162">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
