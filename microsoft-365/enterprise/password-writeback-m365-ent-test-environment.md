---
title: Microsoft 365 测试环境的密码写回
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/20/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom:
- TLGS
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置 Microsoft 365 测试环境的密码写回。
ms.openlocfilehash: 748ccaf8601d9e9564d176f2368e3cc71f926208
ms.sourcegitcommit: 369f07db4e457334900314a2575f2f75cff5ce9c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/07/2018
ms.locfileid: "27201606"
---
# <a name="password-writeback-for-your-microsoft-365-test-environment"></a><span data-ttu-id="bc616-103">Microsoft 365 测试环境的密码写回</span><span class="sxs-lookup"><span data-stu-id="bc616-103">Password writeback for your Microsoft 365 test environment</span></span>

<span data-ttu-id="bc616-p101">密码写回将允许用户通过 Azure Active Directory (AD) 更新其密码，然后复制到本地 Windows Server Active Directory (AD)。通过密码写回，用户不需要通过本地 Windows Server AD（原始用户帐户的存储位置）更新其密码。这非常适用于对本地网络没有远程访问连接的漫游或远程用户。</span><span class="sxs-lookup"><span data-stu-id="bc616-p101">Password writeback allows users to update their passwords through Azure Active Directory (AD), which is then replicated to your local Windows Server Active Directory (AD). With password writeback, users don’t need to update their passwords through the on-premises Windows Server AD where their original user accounts are stored. This helps roaming or remote users who do not have a remote access connection to their on-premises network.</span></span>

<span data-ttu-id="bc616-107">本文介绍了如何为 Microsoft 365 测试环境配置密码写回。</span><span class="sxs-lookup"><span data-stu-id="bc616-107">This article describes how you can configure your Microsoft 365 test environment for password writeback.</span></span>

<span data-ttu-id="bc616-108">此设置包含两个阶段：</span><span class="sxs-lookup"><span data-stu-id="bc616-108">There are two phases to setting this up:</span></span>

1.  <span data-ttu-id="bc616-109">创建采用密码哈希同步的 Microsoft 365 模拟企业测试环境。</span><span class="sxs-lookup"><span data-stu-id="bc616-109">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="bc616-110">为 TESTLAB Windows Server AD 域启用密码写回。</span><span class="sxs-lookup"><span data-stu-id="bc616-110">Enable password writeback for the TESTLAB Windows Server AD domain.</span></span>
    
![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="bc616-112">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="bc616-112">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="bc616-113">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="bc616-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="bc616-p102">按照 [Microsoft 365 的密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="bc616-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="bc616-117">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="bc616-117">This configuration consists of:</span></span> 
  
- <span data-ttu-id="bc616-118">Office 365 E5 和 EMS E5 试用订阅或永久订阅。</span><span class="sxs-lookup"><span data-stu-id="bc616-118">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="bc616-119">连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="bc616-119">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="bc616-120">在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB Windows Server AD 域同步到 Office 365 和 EMS E5 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="bc616-120">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="phase-2-enable-password-writeback-for-the-testlab-windows-server-ad-domain"></a><span data-ttu-id="bc616-121">阶段 2：为 TESTLAB Windows Server AD 域启用密码写回</span><span class="sxs-lookup"><span data-stu-id="bc616-121">Phase 2: Enable password writeback for the TESTLAB Windows Server AD domain</span></span>

<span data-ttu-id="bc616-122">首先，使用全局管理员角色配置用户 1 帐户。</span><span class="sxs-lookup"><span data-stu-id="bc616-122">First, configure the User 1 account with the global administrator role.</span></span>

1. <span data-ttu-id="bc616-123">在 [Office 门户](https://office.com)中，使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="bc616-123">From the [Office portal](https://office.com), sign in with your global administrator account.</span></span>

2. <span data-ttu-id="bc616-p103">单击“**管理**”磁贴。从浏览器的新“**Microsoft 365 管理中心**”选项卡中，单击“**活跃用户**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-p103">Click the **Admin** tile. From the new **Microsoft 365 admin center** tab of your browser, click **Active users**.</span></span>
 
3. <span data-ttu-id="bc616-126">在“**活跃用户**”页面上，单击 **user1** 帐户，</span><span class="sxs-lookup"><span data-stu-id="bc616-126">On the **Active users** page, click the **user1** account,</span></span>

4. <span data-ttu-id="bc616-127">在 **user1** 窗格中，单击“**角色**”旁边的“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-127">On the **user1** pane, click **Edit** next to **Roles**.</span></span>

5. <span data-ttu-id="bc616-p104">在 user1 的“**编辑用户角色**”窗格上，单击“**全局管理员**”。单击“**保存**”，然后单击“**关闭**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-p104">On the **Edit user roles** pane for user1, click **Global administrator**. Click **Save**, and then click **Close**.</span></span>

<span data-ttu-id="bc616-130">接下来，使用允许用户 1 代表 TESTLAB Windows Server AD 域中的其他用户更改密码的安全设置来配置用户 1 帐户。</span><span class="sxs-lookup"><span data-stu-id="bc616-130">Next, configure the User 1 account with the security settings that allow it to change passwords on behalf of other users in the TESTLAB Windows Server AD domain.</span></span>

1. <span data-ttu-id="bc616-131">在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。</span><span class="sxs-lookup"><span data-stu-id="bc616-131">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="bc616-132">在 APP1 的桌面上，单击“**开始**”，键入 **active**，然后单击“**Active Directory 用户和计算机**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-132">From the desktop of APP1, click **Start**, type **active**, and then click **Active Directory Users and Computers**.</span></span>

3. <span data-ttu-id="bc616-p105">单击菜单栏中的“**视图**”。如果未启用“**高级功能**”，请单击启用该功能。</span><span class="sxs-lookup"><span data-stu-id="bc616-p105">Click **View** in the menu bar. If **Advanced features** is not enabled, click it to enable it.</span></span>

4. <span data-ttu-id="bc616-135">在树窗格中，右键单击你的域，再单击“**属性**”，然后单击“**安全**”选项卡。</span><span class="sxs-lookup"><span data-stu-id="bc616-135">In the tree pane, right-click your domain, click **Properties**, and then click the **Security** tab.</span></span>

5. <span data-ttu-id="bc616-136">单击“**高级**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-136">Click **Advanced**.</span></span>

6. <span data-ttu-id="bc616-137">在“**权限**”选项卡上，单击“**添加**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-137">On the **Permissions** tab, click **Add**.</span></span>

7. <span data-ttu-id="bc616-138">单击“**选择主体**”，键入 **User1**，然后单击“**确定**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-138">Click **Select a principal**, type **User1**, and then click **OK**.</span></span>

8. <span data-ttu-id="bc616-139">在“**适用于**”中，选择“**后代用户对象**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-139">In **Applies to**, select **Descendant User objects**.</span></span>

9. <span data-ttu-id="bc616-140">在“**权限**”下，选择以下内容：</span><span class="sxs-lookup"><span data-stu-id="bc616-140">Under **Permissions**, select the following:</span></span>

    - <span data-ttu-id="bc616-141">更改密码</span><span class="sxs-lookup"><span data-stu-id="bc616-141">Change password</span></span>
    - <span data-ttu-id="bc616-142">重置密码</span><span class="sxs-lookup"><span data-stu-id="bc616-142">Reset password</span></span>

10. <span data-ttu-id="bc616-143">在“**属性**”下，选择以下内容：</span><span class="sxs-lookup"><span data-stu-id="bc616-143">Under **Properties**, select the following:</span></span>
    - <span data-ttu-id="bc616-144">写入 lockoutTime</span><span class="sxs-lookup"><span data-stu-id="bc616-144">Write lockoutTime</span></span>
    - <span data-ttu-id="bc616-145">写入 pwdLastSet</span><span class="sxs-lookup"><span data-stu-id="bc616-145">Write pwdLastSet</span></span>

11. <span data-ttu-id="bc616-146">单击“**确定**”三次，以保存更改。</span><span class="sxs-lookup"><span data-stu-id="bc616-146">Click **OK** three times to save the changes.</span></span>

12. <span data-ttu-id="bc616-147">关闭 **Active Directory 用户和计算机**。</span><span class="sxs-lookup"><span data-stu-id="bc616-147">Close **Active Directory Users and Computers**.</span></span>

<span data-ttu-id="bc616-148">接下来，在 APP1 上对 Azure AD Connect 进行密码写回配置。</span><span class="sxs-lookup"><span data-stu-id="bc616-148">Next, configure Azure AD Connect on APP1 for password writeback.</span></span>

1. <span data-ttu-id="bc616-149">如果需要，使用 TESTLAB \ User1 帐户连接到 APP1。</span><span class="sxs-lookup"><span data-stu-id="bc616-149">If needed, connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="bc616-150">在 APP1 的桌面上，双击“**Azure AD Connect**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-150">From the desktop of APP1, double-click **Azure AD Connect**.</span></span>

3. <span data-ttu-id="bc616-151">在“**欢迎页**”上，单击“**配置**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-151">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="bc616-152">在“**其他任务**”页上，选择“**自定义同步选项**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-152">On the **Additional tasks** page, click **Customize synchronization options**, and then click **Next**.</span></span>

5. <span data-ttu-id="bc616-153">在“**连接到 Azure AD**”页上，键入“用户 1”帐户凭据，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-153">On the **Connect to Azure AD** page, type the User 1 account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="bc616-154">在“**连接目录**”和“**域/OU 筛选**”页上，单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-154">On the **Connect directories** and **Domain/OU filtering** pages, click **Next**.</span></span>

7. <span data-ttu-id="bc616-155">在“**可选功能**”页上，选择“**密码写回**”，然后单击“下一步”。</span><span class="sxs-lookup"><span data-stu-id="bc616-155">On the **Optional features** page, select **Password writeback** and click Next.</span></span> 

8. <span data-ttu-id="bc616-156">在“**准备配置**”页上，单击“**配置**”并等待该过程完成。</span><span class="sxs-lookup"><span data-stu-id="bc616-156">On the **Ready to configure** page, click **Configure** and wait for the process to finish.</span></span>

9. <span data-ttu-id="bc616-157">当看到配置完成后，单击“**退出**”。</span><span class="sxs-lookup"><span data-stu-id="bc616-157">When you see the configuration finish, click **Exit**.</span></span>

<span data-ttu-id="bc616-158">你现在可以在未连接到模拟 Intranet 的虚拟网络的计算机上测试用户的密码写回。</span><span class="sxs-lookup"><span data-stu-id="bc616-158">You are now ready to test password writeback for users on computers that are not connected to the virtual network of your simulated intranet.</span></span>

<span data-ttu-id="bc616-159">下面是生成的配置：</span><span class="sxs-lookup"><span data-stu-id="bc616-159">Here is your resulting configuration:</span></span>

![使用传递身份验证测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="bc616-161">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="bc616-161">This configuration consists of:</span></span>

- <span data-ttu-id="bc616-162">包含已注册 DNS 域 TESTLAB.\<域名> 的 Office 365 E5 和 EMS E5 试用订阅或永久订阅。</span><span class="sxs-lookup"><span data-stu-id="bc616-162">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="bc616-163">连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="bc616-163">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="bc616-164">在 APP1 上运行的 Azure AD Connect，用于将 Azure AD 租户中的帐户和组列表从 Office 365 和 EMS E5 订阅同步到 TESTLAB Windows Server AD 域。</span><span class="sxs-lookup"><span data-stu-id="bc616-164">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB Windows Server AD domain.</span></span> 
- <span data-ttu-id="bc616-165">已启用密码写回，因此用户可以通过 Azure AD 更改其密码，而无需连接到简化的 Intranet。</span><span class="sxs-lookup"><span data-stu-id="bc616-165">Password writeback is enabled so that users can change their passwords through Azure AD without having to be connected to the simplified intranet.</span></span>

<span data-ttu-id="bc616-166">有关在生产中配置密码写回的信息和相关链接，请参阅“标识”阶段中的[简化密码更新](identity-password-writeback.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="bc616-166">See the [Simplify password updates](identity-password-writeback.md) step in the Identity phase for information and links to configure password writeback in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="bc616-167">后续步骤</span><span class="sxs-lookup"><span data-stu-id="bc616-167">Next step</span></span>

<span data-ttu-id="bc616-168">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="bc616-168">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="bc616-169">另请参阅</span><span class="sxs-lookup"><span data-stu-id="bc616-169">See also</span></span>

[<span data-ttu-id="bc616-170">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="bc616-170">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="bc616-171">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="bc616-171">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="bc616-172">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="bc616-172">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


