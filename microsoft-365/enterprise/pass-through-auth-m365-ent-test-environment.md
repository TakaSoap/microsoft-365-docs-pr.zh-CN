---
title: Microsoft 365 测试环境的传递身份验证
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 08/13/2018
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
ms.assetid: ''
description: 摘要：配置 Microsoft 365 测试环境的传递身份验证。
ms.openlocfilehash: 02175054aad442584de13542eb6f711b2e18ec36
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34073382"
---
# <a name="pass-through-authentication-for-your-microsoft-365-test-environment"></a><span data-ttu-id="20e31-103">Microsoft 365 测试环境的传递身份验证</span><span class="sxs-lookup"><span data-stu-id="20e31-103">Pass-through authentication for your Microsoft 365 test environment</span></span>

<span data-ttu-id="20e31-104">想要直接使用本地 Active Directory 域服务 (AD DS) 基础结构来进行对 Microsoft 云服务的身份验证的组织可以使用直通身份验证。</span><span class="sxs-lookup"><span data-stu-id="20e31-104">Organizations that want to directly use their on-premises Active Directory Domain Services (AD DS) infrastructure for authentication to Microsoft cloud-based services and applications can use pass-through authentication.</span></span> <span data-ttu-id="20e31-105">本文介绍了如何为直通身份验证配置 Microsoft 365 测试环境，生成的配置如下：</span><span class="sxs-lookup"><span data-stu-id="20e31-105">This article describes how you can configure your Microsoft 365 test environment for pass-through authentication, resulting in the following configuration:</span></span>
  
![使用传递身份验证测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="20e31-107">此测试环境的设置分为以下两个阶段：</span><span class="sxs-lookup"><span data-stu-id="20e31-107">There are two phases to setting up this test environment:</span></span>

1.  <span data-ttu-id="20e31-108">通过密码哈希同步创建 Microsoft 365 模拟企业测试环境。</span><span class="sxs-lookup"><span data-stu-id="20e31-108">Create the Microsoft 365 simulated enterprise test environment with password hash synchronization.</span></span>
2.  <span data-ttu-id="20e31-109">在 APP1 上对 Azure AD Connect 进行传递身份验证配置。</span><span class="sxs-lookup"><span data-stu-id="20e31-109">Configure Azure AD Connect on APP1 for pass-through authentication.</span></span>
    
![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="20e31-111">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="20e31-111">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="20e31-112">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="20e31-112">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="20e31-p102">按照 [Microsoft 365 的密码哈希同步](password-hash-sync-m365-ent-test-environment.md)中的说明操作。下面是生成的配置。</span><span class="sxs-lookup"><span data-stu-id="20e31-p102">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md). Here is your resulting configuration.</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="20e31-116">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="20e31-116">This configuration consists of:</span></span> 
  
- <span data-ttu-id="20e31-117">Office 365 E5 和 EMS E5 试用订阅或付费订阅。</span><span class="sxs-lookup"><span data-stu-id="20e31-117">Office 365 E5 and EMS E5 trial or paid subscriptions.</span></span>
- <span data-ttu-id="20e31-118">连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="20e31-118">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="20e31-119">在 APP1 上运行的 Azure AD Connect，用于将 TESTLAB AD DS 域周期性同步到 Office 365 和 EMS E5 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="20e31-119">Azure AD Connect runs on APP1 to synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Office 365 and EMS E5 subscriptions periodically.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-pass-through-authentication"></a><span data-ttu-id="20e31-120">阶段 2：在 APP1 上对 Azure AD Connect 进行传递身份验证配置</span><span class="sxs-lookup"><span data-stu-id="20e31-120">Phase 2: Configure Azure AD Connect on APP1 for pass-through authentication</span></span>

<span data-ttu-id="20e31-121">在该阶段，需在 APP1 上将 Azure AD Connect 配置为使用传递身份验证，然后验证该功能能否正常工作。</span><span class="sxs-lookup"><span data-stu-id="20e31-121">In this phase, you configure Azure AD Connect on APP1 to use pass-through authentication, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="20e31-122">在 APP1 上配置 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="20e31-122">Configure Azure AD Connect on APP1</span></span>

1.  <span data-ttu-id="20e31-123">在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。</span><span class="sxs-lookup"><span data-stu-id="20e31-123">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2.  <span data-ttu-id="20e31-124">在 APP1 的桌面上，运行 Azure AD Connect。</span><span class="sxs-lookup"><span data-stu-id="20e31-124">From the desktop of APP1, run Azure AD Connect.</span></span>

3.  <span data-ttu-id="20e31-125">在“**欢迎页**”上，单击“**配置**”。</span><span class="sxs-lookup"><span data-stu-id="20e31-125">On the **Welcome page**, click **Configure**.</span></span>

4.  <span data-ttu-id="20e31-126">在“其他任务”页面上，依次单击“**更改用户登录**”和“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="20e31-126">On the Additional tasks page, click **Change user sign-in**, and then click **Next**.</span></span>

5.  <span data-ttu-id="20e31-127">在“**连接到 Azure AD**”页面上，键入全局管理员帐户凭据，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="20e31-127">On the **Connect to Azure AD** page, type your global administrator account credentials, and then click **Next**.</span></span>

6.  <span data-ttu-id="20e31-128">在“**用户登录**”页面上，单击“**传递身份验证**”，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="20e31-128">On the **User sign-in** page, click **Pass-through authentication**, and then click **Next**.</span></span>

7.  <span data-ttu-id="20e31-129">在“**准备配置**”页面上，单击“**配置**”。</span><span class="sxs-lookup"><span data-stu-id="20e31-129">On the **Ready to configure** page, click **Configure**.</span></span>

8.  <span data-ttu-id="20e31-130">在“**配置完成**”页面上，单击“**退出**”。</span><span class="sxs-lookup"><span data-stu-id="20e31-130">On the **Configuration complete** page, click **Exit**.</span></span>

9.  <span data-ttu-id="20e31-p104">在 Azure 门户的左窗格中，单击“**Azure Active Directory > Azure AD Connect**”。请验证**传递身份验证**功能的状态为“**已启用**”。</span><span class="sxs-lookup"><span data-stu-id="20e31-p104">From the Azure portal, in the left pane, click **Azure Active Directory > Azure AD Connect**. Verify that the **Pass-through authentication** feature appears as **Enabled**.</span></span>

10. <span data-ttu-id="20e31-p105">单击“**传递身份验证**”。“**传递身份验证**”窗格中会列出身份验证代理所安装到的服务器。APP1 应该会出现在该列表中。关闭“**传递身份验证**”窗格。</span><span class="sxs-lookup"><span data-stu-id="20e31-p105">Click **Pass-through authentication**. The **Pass-through authentication** pane lists the servers where your Authentication Agents are installed. You should see APP1 in the list. Close the **Pass-through authentication** pane.</span></span>

<span data-ttu-id="20e31-137">接下来，测试能否使用 User1 帐户的用户名 <strong>user1@testlab.</strong>\<公共域名> 登录 Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="20e31-137">Next, test the ability to sign in to your Office 365 subscription with the <strong>user1@testlab.</strong>\<your public domain> user name of the User1 account.</span></span>

1. <span data-ttu-id="20e31-138">在 APP1 中，注销 Office 365，再重新登录，这次指定不同的帐户。</span><span class="sxs-lookup"><span data-stu-id="20e31-138">From APP1, sign out of Office 365, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="20e31-139">当系统提示输入用户名和密码时，指定 <strong>user1@testlab.</strong>\<公共域> 和 User1 密码。</span><span class="sxs-lookup"><span data-stu-id="20e31-139">When prompted for a user name and password, specify <strong>user1@testlab.</strong>\<your public domain> and the User1 password.</span></span> <span data-ttu-id="20e31-140">你应该能以 User1 身份成功登录。</span><span class="sxs-lookup"><span data-stu-id="20e31-140">You should successfully sign in as User1.</span></span>

<span data-ttu-id="20e31-141">请注意，虽然 User1 具有 TESTLAB AD DS 域的域管理员权限，但它不是 Office 365 全局管理员。</span><span class="sxs-lookup"><span data-stu-id="20e31-141">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not an Office 365 global administrator.</span></span> <span data-ttu-id="20e31-142">因此，不会看到作为一个选项的**管理员**图标。</span><span class="sxs-lookup"><span data-stu-id="20e31-142">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="20e31-143">下面是生成的配置：</span><span class="sxs-lookup"><span data-stu-id="20e31-143">Here is your resulting configuration:</span></span>

![使用传递身份验证测试环境的模拟企业配置](media/pass-through-auth-m365-ent-test-environment/Phase2.png)
 
<span data-ttu-id="20e31-145">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="20e31-145">This configuration consists of:</span></span>

- <span data-ttu-id="20e31-146">包含已注册 DNS 域 testlab.\<你的域名> 的 Office 365 E5 和 EMS E5 试用订阅或付费订阅。</span><span class="sxs-lookup"><span data-stu-id="20e31-146">Office 365 E5 and EMS E5 trial or paid subscriptions with the DNS domain testlab.\<your domain name> registered.</span></span>
- <span data-ttu-id="20e31-p108">连接到 Internet 的简化的组织 Intranet，包含 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机。身份验证代理在 APP1 上运行，以便处理你的 Office 365 和 EMS E5 订阅的 Azure AD 租户所发起的传递身份验证请求。</span><span class="sxs-lookup"><span data-stu-id="20e31-p108">A simplified organization intranet connected to the Internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network. An Authentication Agent runs on APP1 to handle pass-through authentication requests from the Azure AD tenant of your Office 365 and EMS E5 subscriptions.</span></span>

## <a name="next-step"></a><span data-ttu-id="20e31-149">后续步骤</span><span class="sxs-lookup"><span data-stu-id="20e31-149">Next step</span></span>

<span data-ttu-id="20e31-150">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="20e31-150">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="20e31-151">另请参阅</span><span class="sxs-lookup"><span data-stu-id="20e31-151">See also</span></span>

[<span data-ttu-id="20e31-152">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="20e31-152">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="20e31-153">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="20e31-153">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="20e31-154">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="20e31-154">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)


