---
title: 适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/21/2018
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
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录。
ms.openlocfilehash: 10444b094e09705e93cb32c10cd0d41c19913985
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865950"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c3e42-103">适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="c3e42-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c3e42-p101">Azure AD 无缝单一登录 (SSO) 自动将连接到组织网络的 PC 或设备上的用户登入。借助 Azure AD 无缝 SSO，用户无需使用其他任何本地组件，即可轻松访问基于云的应用程序。</span><span class="sxs-lookup"><span data-stu-id="c3e42-p101">Azure AD Seamless Single Sign-On (SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network. Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="c3e42-106">本文介绍了如何为 Microsoft 365 测试环境配置 Azure AD 无缝 SSO。</span><span class="sxs-lookup"><span data-stu-id="c3e42-106">This article describes how you can configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="c3e42-107">此测试环境的设置过程分为以下两个阶段：</span><span class="sxs-lookup"><span data-stu-id="c3e42-107">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="c3e42-108">创建采用密码哈希同步的 Microsoft 365 模拟企业测试环境。</span><span class="sxs-lookup"><span data-stu-id="c3e42-108">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="c3e42-109">为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO。</span><span class="sxs-lookup"><span data-stu-id="c3e42-109">Configure Azure AD Connect on APP1 for Azure AD Seamless SSO.</span></span>
    
![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="c3e42-111">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="c3e42-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-create-the-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="c3e42-112">阶段 1：为 Microsoft 365 测试环境创建密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="c3e42-112">Phase 1: Create the password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="c3e42-p102">按照 [Microsoft 365 的密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="c3e42-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="c3e42-116">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="c3e42-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="c3e42-117">Office 365 E5 和 EMS E5 试用订阅或永久订阅。</span><span class="sxs-lookup"><span data-stu-id="c3e42-117">Office 365 E5 and EMS E5 trial or permanent subscriptions.</span></span>
- <span data-ttu-id="c3e42-118">连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="c3e42-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="c3e42-119">在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB Windows Server AD 域定期同步到 Office 365 和 EMS E5 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="c3e42-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB Windows Server AD domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="c3e42-120">阶段 2：为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO</span><span class="sxs-lookup"><span data-stu-id="c3e42-120">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="c3e42-121">在这一阶段，为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO，再验证此功能是否正常运行。</span><span class="sxs-lookup"><span data-stu-id="c3e42-121">In this phase, you configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="c3e42-122">配置 APP1 上的 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="c3e42-122">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="c3e42-123">在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。</span><span class="sxs-lookup"><span data-stu-id="c3e42-123">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="c3e42-124">在 APP1 的桌面上，运行 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="c3e42-124">From the desktop of APP1, run Azure AD Connect.</span></span>

3. <span data-ttu-id="c3e42-125">在“**欢迎页**”上，单击“**配置**”。</span><span class="sxs-lookup"><span data-stu-id="c3e42-125">On the **Welcome page**, click **Configure**.</span></span>

4. <span data-ttu-id="c3e42-126">在“其他任务”页面上，依次单击“**更改用户登录**”和“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="c3e42-126">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5. <span data-ttu-id="c3e42-127">在“连接到 Azure AD”\*\*\*\* 页上，键入全局管理员帐户凭据，再单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-127">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6. <span data-ttu-id="c3e42-128">在“用户登录”\*\*\*\* 页上，选择“启用单一登录”\*\*\*\*，再单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-128">On the **User sign-in** page, select **Enable single sign-on**, and then click **Next**.</span></span>

7. <span data-ttu-id="c3e42-129">在“启用单一登录”\*\*\*\* 页上，单击“输入凭据”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-129">On the **Enable single sign-on** page, click **Enter credentials**.</span></span>

8. <span data-ttu-id="c3e42-p103">在“Windows 安全中心”\*\*\*\* 对话框中，键入“user1”\*\*\*\* 和 user1 帐户的密码，再依次单击“确定”\*\*\*\* 和“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-p103">In the **Windows Security** dialog box, type **user1** and the password of the user1 account, and then click **OK**. Click **Next**.</span></span>

9. <span data-ttu-id="c3e42-132">在“准备配置”\*\*\*\* 页上，单击“配置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-132">On the **Ready to Configure** page, click **Configure**.</span></span>

10. <span data-ttu-id="c3e42-133">在“配置完成”\*\*\*\* 页上，单击“退出”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-133">On the **Configuration complete** page, click **Exit**.</span></span>

11. <span data-ttu-id="c3e42-p104">在 Azure 门户内的左侧窗格中，依次单击“Azure Active Directory”和“Azure AD Connect”\*\*\*\*。验证“无缝单一登录”\*\*\*\* 功能的状态是否为“已启用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="c3e42-136">接下来，测试能否使用 User1 帐户的用户名 <strong>user1@testlab.</strong>\<公共域名> 登录 Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="c3e42-136">Next, test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="c3e42-137">在 APP1 上，依次单击 Internet Explorer 中的设置图标和“Internet 选项”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-137">From Internet Explorer on APP1, click the settings icon, and then click **Internet Options**.</span></span>
 
2. <span data-ttu-id="c3e42-138">单击“Internet 选项”\*\*\*\* 中的“安全”\*\*\*\* 选项卡。</span><span class="sxs-lookup"><span data-stu-id="c3e42-138">In **Internet Options**, click the **Security** tab.</span></span>

3. <span data-ttu-id="c3e42-139">依次单击“本地 Intranet”\*\*\*\* 和“网站”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-139">Click **Local intranet**, and then click **Sites**.</span></span>

4. <span data-ttu-id="c3e42-140">单击“本地 Intranet”\*\*\*\* 中的“高级”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-140">In **Local intranet**, click **Advanced**.</span></span>

5. <span data-ttu-id="c3e42-141">在“将此网站添加到区域”\*\*\*\* 中，键入“https**<span>://autologon.microsoftazuread-sso.com</span>**”，再依次单击“添加”、“关闭”、“确定”和“确定”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c3e42-141">In **Add this website to the zone**, type **https<span>://</span>autologon.microsoftazuread-sso.com**, click **Add > Close > OK > OK**.</span></span>

6. <span data-ttu-id="c3e42-142">注销 Office 365，再重新登录，这次指定不同的帐户。</span><span class="sxs-lookup"><span data-stu-id="c3e42-142">Sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="c3e42-p105">当出现登录提示时，指定用户名 <strong>user1@testlab.</strong>\<公共域名>，再单击“下一步”\*\*\*\*。应能够以 User1 身份成功登录，且不会看到密码输入提示。这就证明无缝 SSO 能正常运行。</span><span class="sxs-lookup"><span data-stu-id="c3e42-p105">When prompted to sign in, specify <strong>user1@testlab.</strong>\<your public domain> name, and then click **Next**. You should successfully sign in as User1 without being prompted for a password. This proves that Seamless SSO is working.</span></span>

<span data-ttu-id="c3e42-p106">请注意，尽管 User1 对 TESTLAB Windows Server AD 域拥有域管理员权限，但它不是 Office 365 全局管理员。因此，看不到“**管理员**”图标选项。</span><span class="sxs-lookup"><span data-stu-id="c3e42-p106">Notice that although User1 has domain administrator permissions for the TESTLAB Windows Server AD domain, it is not an Office 365 global administrator. Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="c3e42-148">下面是生成的配置：</span><span class="sxs-lookup"><span data-stu-id="c3e42-148">Here is your resulting configuration:</span></span>

![使用传递身份验证测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)

 
<span data-ttu-id="c3e42-150">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="c3e42-150">This configuration consists of:</span></span>

- <span data-ttu-id="c3e42-151">包含已注册 DNS 域 TESTLAB.\<域名> 的 Office 365 E5 和 EMS E5 试用订阅或永久订阅。</span><span class="sxs-lookup"><span data-stu-id="c3e42-151">Office 365 E5 and EMS E5 trial or permanent subscriptions with the DNS domain TESTLAB.\<your domain name> registered.</span></span>
- <span data-ttu-id="c3e42-152">连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="c3e42-152">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> 
- <span data-ttu-id="c3e42-153">在 APP1 上运行的 Azure AD Connect，用于将 Azure AD 租户中的帐户和组列表从 Office 365 和 EMS E5 订阅同步到 TESTLAB Windows Server AD 域。</span><span class="sxs-lookup"><span data-stu-id="c3e42-153">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Office 365 and EMS E5 subscriptions to the TESTLAB Windows Server AD domain.</span></span> 
- <span data-ttu-id="c3e42-154">已启用的 Azure AD 无缝 SSO，这样模拟 Intranet 上的计算机无需指定用户帐户密码，即可登录 Microsoft 365 云资源。</span><span class="sxs-lookup"><span data-stu-id="c3e42-154">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign on to Microsoft 365 cloud resources without specifing a user account password.</span></span>

<span data-ttu-id="c3e42-155">若要了解如何在生产中配置 Azure AD 无缝 SSO 和相关链接，请参阅“标识”阶段中的[简化用户登录](identity-single-sign-on.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="c3e42-155">See the [Simplify user sign-in](identity-single-sign-on.md) step in the Identity phase for information and links to configure Azure AD Seamless SSO in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="c3e42-156">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c3e42-156">Next step</span></span>

<span data-ttu-id="c3e42-157">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="c3e42-157">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c3e42-158">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c3e42-158">See also</span></span>

[<span data-ttu-id="c3e42-159">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="c3e42-159">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c3e42-160">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="c3e42-160">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c3e42-161">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="c3e42-161">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


