---
title: Microsoft 365 测试环境的密码哈希同步
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 05/26/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-identity-device-management
- Strat_O365_Enterprise
ms.custom:
- TLG
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: ''
description: 摘要：配置和展示 Microsoft 365 测试环境的密码哈希同步和登录。
ms.openlocfilehash: 9c61745fe322dce4cb2b537b18963634a97c697a
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50921500"
---
# <a name="password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="5a3ed-103">Microsoft 365 测试环境的密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="5a3ed-103">Password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="5a3ed-104">*本测试实验室指南可用于企业Microsoft 365和Office 365 企业版环境。*</span><span class="sxs-lookup"><span data-stu-id="5a3ed-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="5a3ed-105">许多组织使用 Azure AD Connect 和密码哈希同步来同步他们内部部署的 Active Directory 域服务 (AD DS) 林帐户集与 Microsoft 365 订阅的 Azure AD 租户帐户集。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-105">Many organizations use Azure AD Connect and password hash synchronization to synchronize the set of accounts in their on-premises Active Directory Domain Services (AD DS) forest to the set of accounts in the Azure AD tenant of their Microsoft 365 subscription.</span></span> 

<span data-ttu-id="5a3ed-106">本文介绍如何将密码哈希同步添加到Microsoft 365测试环境，这将生成此配置：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-106">This article describes how you can add password hash synchronization to your Microsoft 365 test environment, which results in this configuration:</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)
  
<span data-ttu-id="5a3ed-108">设置此测试环境包括三个阶段：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-108">Setting up this test environment involves three phases:</span></span>
- [<span data-ttu-id="5a3ed-109">第 1 阶段：创建 Microsoft 365 模拟企业测试环境</span><span class="sxs-lookup"><span data-stu-id="5a3ed-109">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>](#phase-1-create-the-microsoft-365-simulated-enterprise-test-environment)
- [<span data-ttu-id="5a3ed-110">第 2 阶段：创建和注册 testlab 域</span><span class="sxs-lookup"><span data-stu-id="5a3ed-110">Phase 2: Create and register the testlab domain</span></span>](#phase-2-create-and-register-the-testlab-domain)
- [<span data-ttu-id="5a3ed-111">第 3 阶段：在 APP1 上安装 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="5a3ed-111">Phase 3: Install Azure AD Connect on APP1</span></span>](#phase-3-install-azure-ad-connect-on-app1)
    
> [!TIP]
> <span data-ttu-id="5a3ed-112">有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365[企业测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-create-the-microsoft-365-simulated-enterprise-test-environment"></a><span data-ttu-id="5a3ed-113">第 1 阶段：创建 Microsoft 365 模拟企业测试环境</span><span class="sxs-lookup"><span data-stu-id="5a3ed-113">Phase 1: Create the Microsoft 365 simulated enterprise test environment</span></span>

<span data-ttu-id="5a3ed-114">按照模拟企业[基础配置中的说明操作Microsoft 365。](simulated-ent-base-configuration-microsoft-365-enterprise.md)</span><span class="sxs-lookup"><span data-stu-id="5a3ed-114">Follow the instructions in [simulated enterprise base configuration for Microsoft 365](simulated-ent-base-configuration-microsoft-365-enterprise.md).</span></span> <span data-ttu-id="5a3ed-115">生成的配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-115">Your resulting configuration looks like this:</span></span>
  
![模拟企业基础配置](../media/password-hash-sync-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="5a3ed-117">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="5a3ed-118">Microsoft 365 E5 试用版或付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="5a3ed-119">连接到 Internet 的简化的组织 Intranet，由 Azure 虚拟网络中的 DC1、APP1 和 CLIENT1 虚拟机组成。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines in an Azure virtual network.</span></span> <span data-ttu-id="5a3ed-120">DC1 是 testlab.<AD DS域中>域控制器。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-120">DC1 is a domain controller for the testlab.<*your public domain name*> AD DS domain.</span></span>

## <a name="phase-2-create-and-register-the-testlab-domain"></a><span data-ttu-id="5a3ed-121">第 2 阶段：创建和注册 testlab 域</span><span class="sxs-lookup"><span data-stu-id="5a3ed-121">Phase 2: Create and register the testlab domain</span></span>

<span data-ttu-id="5a3ed-122">在此阶段，添加公共 DNS 域，然后将其添加到订阅。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-122">In this phase, add a public DNS domain, and then add it to your subscription.</span></span>

<span data-ttu-id="5a3ed-123">首先，与公共 DNS 注册提供商合作，创建一个基于当前域名的新公共 DNS 域名，然后将其添加到订阅中。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-123">First, work with your public DNS registration provider to create a new public DNS domain name that's based on your current domain name, and then add it to your subscription.</span></span> <span data-ttu-id="5a3ed-124">我们建议使用名称 \**testlab.<*公共域\* >\*\*。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-124">We recommend using the name **testlab.<*your public domain*>**.</span></span> <span data-ttu-id="5a3ed-125">例如，如果公共域名是 **<span>contoso</span>.com，** 请添加公共域名 **<span>：testlab</span>.contoso.com**。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-125">For example, if your public domain name is **<span>contoso</span>.com**, add the public domain name: **<span>testlab</span>.contoso.com**.</span></span>
  
<span data-ttu-id="5a3ed-126">接下来，通过<注册过程，将你的公共域Microsoft 365 **testlab.Microsoft 365 >** 或付费订阅。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-126">Next, add the **testlab.<*your public domain*>** domain to your Microsoft 365 trial or paid subscription by going through the domain registration process.</span></span> <span data-ttu-id="5a3ed-127">这包括向公共域的 **testlab.<*添加其他 DNS\* >*\* 记录。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-127">This consists of adding additional DNS records to the **testlab.<*your public domain*>** domain.</span></span> <span data-ttu-id="5a3ed-128">有关详细信息，请参阅将[域添加到Microsoft 365。](../admin/setup/add-domain.md)</span><span class="sxs-lookup"><span data-stu-id="5a3ed-128">For more information, see [Add a domain to Microsoft 365](../admin/setup/add-domain.md).</span></span>

<span data-ttu-id="5a3ed-129">生成的配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-129">Your resulting configuration looks like this:</span></span>
  
![注册 testlab 域名](../media/password-hash-sync-m365-ent-test-environment/Phase2.png)
  
<span data-ttu-id="5a3ed-131">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-131">This configuration consists of:</span></span>

- <span data-ttu-id="5a3ed-132">注册Microsoft 365 E5域名为 dns 域 testlab.<*试用* 或付费>订阅。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-132">A Microsoft 365 E5 trial or paid subscription with the DNS domain testlab.<*your public domain name*> registered.</span></span>
- <span data-ttu-id="5a3ed-133">连接到 Internet 的简化的组织 Intranet，由 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机组成。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-133">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>

<span data-ttu-id="5a3ed-134">请注意您的公共域名<*testlab.>* 现在如何：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-134">Notice how the testlab.<*your public domain name*> is now:</span></span>

- <span data-ttu-id="5a3ed-135">受公共 DNS 记录支持。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-135">Supported by public DNS records.</span></span>
- <span data-ttu-id="5a3ed-136">已在 Microsoft 365 订阅中注册。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-136">Registered in your Microsoft 365 subscriptions.</span></span>
- <span data-ttu-id="5a3ed-137">是模拟 Intranet 上的 AD DS 域。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-137">The AD DS domain on your simulated intranet.</span></span>
     
## <a name="phase-3-install-azure-ad-connect-on-app1"></a><span data-ttu-id="5a3ed-138">第 3 阶段：在 APP1 上安装 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="5a3ed-138">Phase 3: Install Azure AD Connect on APP1</span></span>

<span data-ttu-id="5a3ed-139">在此阶段，在 APP1 上安装和配置 Azure AD 连接工具，然后验证它是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-139">In this phase, install and configure the Azure AD Connect tool on APP1, and then verify that it works.</span></span>
  
<span data-ttu-id="5a3ed-140">首先，在 APP1 上安装和连接 Azure AD 应用。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-140">First, install and configure Azure AD Connect on APP1.</span></span>

1. <span data-ttu-id="5a3ed-141">在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，再使用 TESTLAB\\User1 帐户连接到 APP1。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-141">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\\User1 account.</span></span>
    
2. <span data-ttu-id="5a3ed-142">在 APP1 的桌面中，打开管理员级 Windows PowerShell 命令提示符，然后运行下面这些命令来禁用 Internet Explorer 增强安全：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-142">From the desktop of APP1, open an administrator-level Windows PowerShell command prompt, and then run these commands to disable Internet Explorer Enhanced Security:</span></span>
    
   ```powershell
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A7-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Set-ItemProperty -Path "HKLM:\SOFTWARE\Microsoft\Active Setup\Installed Components\{A509B1A8-37EF-4b3f-8CFC-4F3A74704073}" -Name "IsInstalled" -Value 0
   Stop-Process -Name Explorer -Force
   ```

3. <span data-ttu-id="5a3ed-143">从任务栏中选择 **"Internet Explorer"，** 然后转到 [https://aka.ms/aadconnect](https://aka.ms/aadconnect) 。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-143">From the taskbar, select **Internet Explorer** and go to [https://aka.ms/aadconnect](https://aka.ms/aadconnect).</span></span>
    
4. <span data-ttu-id="5a3ed-144">在"Microsoft Azure Active Directory 连接"页上，选择 **"下载"，** 然后选择"运行 **"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-144">On the Microsoft Azure Active Directory Connect page, select **Download**, and then select **Run**.</span></span>
    
5. <span data-ttu-id="5a3ed-145">在"**欢迎使用 Azure AD 连接** 页面上，选择 **"我同意"，** 然后选择"继续 **"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-145">On the **Welcome to Azure AD Connect** page, select **I agree**, and then select **Continue**.</span></span>
    
6. <span data-ttu-id="5a3ed-146">在 Express **设置** 页面上，选择 **"使用快速设置"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-146">On the **Express Settings** page, select **Use express settings**.</span></span>
    
7. <span data-ttu-id="5a3ed-147">在 **"连接 Azure AD"** 页面上，在"用户名"中输入全局管理员帐户名称，在"密码"中输入其密码，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-147">On the **Connect to Azure AD** page, enter your global administrator account name in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
8. <span data-ttu-id="5a3ed-148">在 **"连接 AD DS"** 页上，在"用户名"中输入 **TESTLAB \\ User1，** 在"密码"中输入其密码，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-148">On the **Connect to AD DS** page, enter **TESTLAB\\User1** in **Username,** enter its password in **Password**, and then select **Next**.</span></span>
    
9. <span data-ttu-id="5a3ed-149">在"**准备配置"页上，** 选择"安装 **"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-149">On the **Ready to configure** page, select **Install**.</span></span>
    
10. <span data-ttu-id="5a3ed-150">在"**配置完成"页上**，选择"退出 **"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-150">On the **Configuration complete** page, select **Exit**.</span></span>
    
11. <span data-ttu-id="5a3ed-151">在 Internet Explorer 中，转到 Microsoft 365 管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com))。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-151">In Internet Explorer, go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)).</span></span>
    
12. <span data-ttu-id="5a3ed-152">在左侧导航窗格中，选择"活动 **>用户"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-152">In the left navigation pane, select **Users > Active users**.</span></span>
    
    <span data-ttu-id="5a3ed-153">请注意，该帐户名为 **用户 1**。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-153">Note the account named **User1**.</span></span> <span data-ttu-id="5a3ed-154">此帐户来自 TESTLAB AD DS 域，证明目录同步已正常工作。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-154">This account is from the TESTLAB AD DS domain and is proof that directory synchronization has worked.</span></span>
    
13. <span data-ttu-id="5a3ed-155">选择 **User1 帐户**，然后选择"**许可证和应用"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-155">Select the **User1** account, and then select **Licenses and apps**.</span></span>
    
14. <span data-ttu-id="5a3ed-156">在 **"产品许可证**"中，根据需要选择 (位置) 禁用 Office 365 **E5** 许可证，然后启用 **Microsoft 365 E5许可证。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-156">In **Product licenses**, select your location (if needed), disable the **Office 365 E5** license, and then enable the **Microsoft 365 E5** license.</span></span> 

15. <span data-ttu-id="5a3ed-157">选择 **页面** 底部的"保存"，然后选择"关闭 **"。**</span><span class="sxs-lookup"><span data-stu-id="5a3ed-157">Select **Save** at the bottom of the page, and then select **Close**.</span></span>
    
<span data-ttu-id="5a3ed-158">接下来，测试能否使用 **user1@testlab.< >** User1 帐户的域名用户名登录订阅：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-158">Next, test the ability to sign in to your subscription with the **user1@testlab.<*your domain name*>** user name of the User1 account:</span></span>

1. <span data-ttu-id="5a3ed-159">在 APP1 中，注销，再重新登录，这次指定不同的帐户。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-159">From APP1, sign out, and then sign in again, this time specifying a different account.</span></span>

2. <span data-ttu-id="5a3ed-160">当系统提示输入用户名和密码时 **，user1@testlab.<*您的域名\* >*\* 和 User1 密码。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-160">When prompted for a user name and password, specify **user1@testlab.<*your domain name*>** and the User1 password.</span></span> <span data-ttu-id="5a3ed-161">你应该能以 User1 身份成功登录。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-161">You should successfully sign in as User1.</span></span>
 
<span data-ttu-id="5a3ed-162">请注意，虽然 User1 具有 TESTLAB AD DS 域的域管理员权限，但它不是全局管理员。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-162">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator.</span></span> <span data-ttu-id="5a3ed-163">因此，不会看到作为一个选项的 **管理员** 图标。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-163">Therefore, you will not see the **Admin** icon as an option.</span></span> 

<span data-ttu-id="5a3ed-164">生成的配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-164">Your resulting configuration looks like this:</span></span>

![使用密码哈希同步测试环境的模拟企业配置](../media/password-hash-sync-m365-ent-test-environment/Phase3.png)

<span data-ttu-id="5a3ed-166">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="5a3ed-166">This configuration consists of:</span></span> 
  
- <span data-ttu-id="5a3ed-167">Microsoft 365 E5注册Office 365 DNS 域 TESTLAB.<注册的 E5 试用版或付费>订阅。 </span><span class="sxs-lookup"><span data-stu-id="5a3ed-167">Microsoft 365 E5 or Office 365 E5 trial or paid subscriptions with the DNS domain TESTLAB.<*your domain name*> registered.</span></span>
- <span data-ttu-id="5a3ed-168">连接到 Internet 的简化的组织 Intranet，由 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机组成。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-168">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span> <span data-ttu-id="5a3ed-169">Azure AD 连接 APP1 上运行，以定期将 TESTLAB AD DS 域同步到你的 Microsoft 365 租户。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-169">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB AD DS domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>
- <span data-ttu-id="5a3ed-170">TESTLAB  AD DS 域中的 User1 帐户已与 Azure AD 租户同步。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-170">The User1 account in the TESTLAB  AD DS domain has been synchronized with the Azure AD tenant.</span></span>

## <a name="next-step"></a><span data-ttu-id="5a3ed-171">后续步骤</span><span class="sxs-lookup"><span data-stu-id="5a3ed-171">Next step</span></span>

<span data-ttu-id="5a3ed-172">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="5a3ed-172">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="5a3ed-173">另请参阅</span><span class="sxs-lookup"><span data-stu-id="5a3ed-173">See also</span></span>

[<span data-ttu-id="5a3ed-174">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="5a3ed-174">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="5a3ed-175">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="5a3ed-175">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="5a3ed-176">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="5a3ed-176">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)