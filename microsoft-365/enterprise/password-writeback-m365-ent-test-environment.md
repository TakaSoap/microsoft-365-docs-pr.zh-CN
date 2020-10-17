---
title: Microsoft 365 测试环境的密码写回
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/22/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置 Microsoft 365 测试环境的密码写回。
ms.openlocfilehash: b999d50b0e98b11638199327bd7ffe7269b261ce
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487124"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e1dc0-103">Microsoft 365 测试环境的密码写回</span><span class="sxs-lookup"><span data-stu-id="e1dc0-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e1dc0-104">*此测试实验室指南仅可用于企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="e1dc0-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="e1dc0-p101">用户可以使用密码写回通过 Azure Active Directory (Azure AD) （然后将其复制到本地 Active Directory 域服务 (AD DS) ）更新其密码。通过密码写回，用户无需通过内部部署 AD DS （其中存储其原始用户帐户）来更新其密码。这有助于不具有到本地网络的远程访问连接的漫游或远程用户。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-p101">Users can use password writeback to update their passwords through Azure Active Directory (Azure AD), which is then replicated to your local Active Directory Domain Services (AD DS). With password writeback, users don't have to update their passwords through the on-premises AD DS where their original user accounts are stored. This helps roaming or remote users who don't have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="e1dc0-108">本文介绍如何为您的 Microsoft 365 测试环境配置密码写回。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-108">This article describes how to configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="e1dc0-109">配置密码写回的测试环境包括两个阶段：</span><span class="sxs-lookup"><span data-stu-id="e1dc0-109">Configuring your test environment for password writeback involves two phases:</span></span>
- [<span data-ttu-id="e1dc0-110">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="e1dc0-110">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="e1dc0-111">阶段 2：为 TESTLAB AD DS 域启用密码写回</span><span class="sxs-lookup"><span data-stu-id="e1dc0-111">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>](#phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain)
  
![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="e1dc0-113">若要了解到 Microsoft 365 for 企业测试实验室指南堆栈中的所有文章的可视化地图，请转到 [microsoft 365 for Enterprise Test Lab Guide stack](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-113">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="e1dc0-114">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="e1dc0-114">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="e1dc0-p102">首先，按照 " [密码哈希同步](password-hash-sync-m365-ent-test-environment.md)" 中的说明操作。生成的配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="e1dc0-p102">First, follow the instructions in [password hash synchronization](password-hash-sync-m365-ent-test-environment.md). Your resulting configuration looks like this:</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="e1dc0-118">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="e1dc0-118">This configuration consists of:</span></span>
  
- <span data-ttu-id="e1dc0-119">Microsoft 365 E5 试用版或付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-119">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="e1dc0-120">连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-120">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="e1dc0-121">在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB AD DS 域同步到 Microsoft 365 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-121">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-ad-ds-domain"></a><span data-ttu-id="e1dc0-122">阶段 2：为 TESTLAB AD DS 域启用密码写回</span><span class="sxs-lookup"><span data-stu-id="e1dc0-122">Phase 2: Enable password writeback for the TESTLAB AD DS domain</span></span>

<span data-ttu-id="e1dc0-123">首先，使用全局管理员角色配置用户 1 帐户。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-123">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="e1dc0-124">通过 [Microsoft 365 管理中心](https://portal.microsoft.com)使用全局管理员帐户进行登录。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-124">From the [Microsoft 365 admin center](https://portal.microsoft.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="e1dc0-125">选择 " **活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-125">Select **Active users**.</span></span>
 
3. <span data-ttu-id="e1dc0-126">在 " **活动用户** " 页上，选择 **user1** 帐户，</span><span class="sxs-lookup"><span data-stu-id="e1dc0-126">On the **Active users** page, select the **user1** account,</span></span>

4. <span data-ttu-id="e1dc0-127">在 " **user1** " 窗格中，选择 "**角色**" 旁边的 "**编辑**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-127">On the **user1** pane, select **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="e1dc0-128">在用户1的 " **编辑用户角色** " 窗格中，选择 " **全局管理员**"，选择 " **保存**"，然后选择 " **关闭**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-128">On the **Edit user roles** pane for user1, select **Global administrator**, select **Save**, and then select **Close**.</span></span>

<span data-ttu-id="e1dc0-129">接下来，使用允许用户 1 代表 TESTLAB AD DS 域中的其他用户更改密码的安全设置来配置用户 1 帐户。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-129">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB AD DS domain.</span></span>

1. <span data-ttu-id="e1dc0-130">在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-130">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="e1dc0-131">在 APP1 的桌面上，选择 " **开始**"，输入 " **活动**"，然后选择 " **active Directory 用户和计算机**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-131">From the desktop of APP1, select **Start**, enter **active**, and then select **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="e1dc0-132">在菜单栏上，选择 " **查看**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-132">On the menu bar, select **View**.</span></span> <span data-ttu-id="e1dc0-133">如果未启用 **高级功能** ，请选择该功能以启用它。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-133">If **Advanced features** is not enabled, select it to enable it.</span></span>

4. <span data-ttu-id="e1dc0-134">在树窗格中，选择并按住 (或右键单击) 您的域，选择 " **属性**"，然后选择 " **安全** " 选项卡。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-134">In the tree pane, select and hold (or right-click) your domain, select **Properties**, and then select the **Security** tab.</span></span>

5. <span data-ttu-id="e1dc0-135">选择“高级”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-135">Select **Advanced**.</span></span>

6. <span data-ttu-id="e1dc0-136">在 " **权限** " 选项卡上，选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-136">On the **Permissions** tab, select **Add**.</span></span>

7. <span data-ttu-id="e1dc0-137">选择 " **选择主体**"，输入 **User1**，然后选择 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-137">Select **Select a principal**, enter **User1**, and then select **OK**.</span></span>

8. <span data-ttu-id="e1dc0-138">在“**适用于**”中，选择“**后代用户对象**”。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-138">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="e1dc0-139">在“**权限**”下，选择以下内容：</span><span class="sxs-lookup"><span data-stu-id="e1dc0-139">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="e1dc0-140">**更改密码**</span><span class="sxs-lookup"><span data-stu-id="e1dc0-140">**Change password**</span></span>
    - <span data-ttu-id="e1dc0-141">**重置密码**</span><span class="sxs-lookup"><span data-stu-id="e1dc0-141">**Reset password**</span></span>

10. <span data-ttu-id="e1dc0-142">在“**属性**”下，选择以下内容：</span><span class="sxs-lookup"><span data-stu-id="e1dc0-142">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="e1dc0-143">**写入 lockoutTime**</span><span class="sxs-lookup"><span data-stu-id="e1dc0-143">**Write lockoutTime**</span></span>
    - <span data-ttu-id="e1dc0-144">**写入 pwdLastSet**</span><span class="sxs-lookup"><span data-stu-id="e1dc0-144">**Write pwdLastSet**</span></span>

11. <span data-ttu-id="e1dc0-145">选择 **"确定"** 三次，以保存更改。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-145">Select **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="e1dc0-146">关闭 **Active Directory 用户和计算机**。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-146">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="e1dc0-147">接下来，在 APP1 上对 Azure AD Connect 进行密码写回配置。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-147">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="e1dc0-148">如果需要，使用 TESTLAB \ User1 帐户连接到 APP1。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-148">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="e1dc0-149">在 APP1 的桌面上，双击“**Azure AD Connect**”。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-149">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="e1dc0-150">在 " **欢迎" 页**上，选择 " **配置**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-150">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="e1dc0-151">在 " **其他任务** " 页上，选择 " **自定义同步选项**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-151">On the **Additional tasks** page, select **Customize synchronization options**, and then select **Next**.</span></span>

5. <span data-ttu-id="e1dc0-152">在 " **连接到 AZURE AD** " 页上，输入全局管理员帐户凭据，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-152">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="e1dc0-153">在 " **连接目录** 和 **域/OU 筛选** " 页上，选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-153">On the **Connect directories** and **Domain/OU filtering** pages, select **Next**.</span></span>

7. <span data-ttu-id="e1dc0-154">在 " **可选功能** " 页上，选择 " **密码写回**"，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-154">On the **Optional features** page, select **Password writeback**, and then select **Next**.</span></span>

8. <span data-ttu-id="e1dc0-155">在 " **准备配置** " 页上，选择 " **配置** 并等待该过程完成"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-155">On the **Ready to configure** page, select **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="e1dc0-156">当您看到配置完成时，选择 " **退出**"。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-156">When you see the configuration finish, select **Exit**.</span></span>

<span data-ttu-id="e1dc0-157">现在，您可以为未连接到模拟 intranet 的虚拟网络的计算机上的用户测试密码写回。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-157">You are now ready to test password writeback for users on computers that aren't connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="e1dc0-158">生成的配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="e1dc0-158">Your resulting configuration looks like this:</span></span>

![使用传递身份验证测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="e1dc0-160">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="e1dc0-160">This configuration consists of:</span></span>

- <span data-ttu-id="e1dc0-161">使用 DNS 域 TESTLAB 的 Microsoft 365 E5 试用版或付费订阅。\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="e1dc0-161">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.\<*your domain name*></span></span> <span data-ttu-id="e1dc0-162">。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-162">registered.</span></span>
- <span data-ttu-id="e1dc0-163">连接到 internet 的简化的组织 intranet，由 Azure 虚拟网络的子网上的 DC1、APP1 和 CLIENT1 虚拟机组成。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-163">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="e1dc0-164">在 APP1 上运行的 Azure AD Connect，用于将 Azure AD 租户中的帐户和组列表从 Microsoft 365 订阅同步到 TESTLAB AD DS 域。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="e1dc0-165">已启用密码写回，因此用户可以通过 Azure AD 更改其密码，而无需连接到简化的 Intranet。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

## <a name="next-step"></a><span data-ttu-id="e1dc0-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e1dc0-166">Next step</span></span>

<span data-ttu-id="e1dc0-167">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="e1dc0-167">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="e1dc0-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e1dc0-168">See also</span></span>

[<span data-ttu-id="e1dc0-169">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="e1dc0-169">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e1dc0-170">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="e1dc0-170">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="e1dc0-171">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="e1dc0-171">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


