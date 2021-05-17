---
title: 适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/21/2019
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
description: 摘要：配置和测试适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录。
ms.openlocfilehash: 7fcbc82cfb35c598358c8160dd06427c2a9c59a2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50904860"
---
# <a name="azure-ad-seamless-single-sign-on-for-your-microsoft-365-test-environment"></a><span data-ttu-id="39f06-103">适用于 Microsoft 365 测试环境的 Azure AD 无缝单一登录</span><span class="sxs-lookup"><span data-stu-id="39f06-103">Azure AD Seamless Single Sign-on for your Microsoft 365 test environment</span></span>

<span data-ttu-id="39f06-104">*本测试实验室指南可用于企业Microsoft 365和Office 365 企业版环境。*</span><span class="sxs-lookup"><span data-stu-id="39f06-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="39f06-105">Azure AD 无缝Sign-On (无缝 SSO) 当用户在连接到其组织网络的 PC 或设备上时自动登录。</span><span class="sxs-lookup"><span data-stu-id="39f06-105">Azure AD Seamless Single Sign-On (Seamless SSO) automatically signs in users when they are on their PCs or devices that are connected to their organization network.</span></span> <span data-ttu-id="39f06-106">Azure AD 无缝 SSO 使用户能够轻松访问基于云的应用程序，而无需任何其他本地组件。</span><span class="sxs-lookup"><span data-stu-id="39f06-106">Azure AD Seamless SSO provides users with easy access to cloud-based applications without needing any additional on-premises components.</span></span>

<span data-ttu-id="39f06-107">本文介绍如何为 Azure AD Microsoft 365 SSO 配置测试环境。</span><span class="sxs-lookup"><span data-stu-id="39f06-107">This article describes how to configure your Microsoft 365 test environment for Azure AD Seamless SSO.</span></span>

<span data-ttu-id="39f06-108">设置 Azure AD 无缝 SSO 涉及两个阶段：</span><span class="sxs-lookup"><span data-stu-id="39f06-108">Setting up Azure AD Seamless SSO involves two phases:</span></span>
- [<span data-ttu-id="39f06-109">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="39f06-109">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>](#phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment)
- [<span data-ttu-id="39f06-110">阶段 2：为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO</span><span class="sxs-lookup"><span data-stu-id="39f06-110">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>](#phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso)
   
![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png) 
    
> [!TIP]
> <span data-ttu-id="39f06-112">有关企业测试实验室指南堆栈中Microsoft 365文章的直观映射，请转到 Microsoft 365[企业测试实验室指南堆栈](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="39f06-112">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, go to [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>
  
## <a name="phase-1-configure-password-hash-synchronization-for-your-microsoft-365-test-environment"></a><span data-ttu-id="39f06-113">阶段 1：为 Microsoft 365 测试环境配置密码哈希同步</span><span class="sxs-lookup"><span data-stu-id="39f06-113">Phase 1: Configure password hash synchronization for your Microsoft 365 test environment</span></span>

<span data-ttu-id="39f06-114">按照密码哈希[同步中的说明操作Microsoft 365。](password-hash-sync-m365-ent-test-environment.md)</span><span class="sxs-lookup"><span data-stu-id="39f06-114">Follow the instructions in [password hash synchronization for Microsoft 365](password-hash-sync-m365-ent-test-environment.md).</span></span> 

<span data-ttu-id="39f06-115">生成的配置如下所示：</span><span class="sxs-lookup"><span data-stu-id="39f06-115">Your resulting configuration looks like this:</span></span>
  
![使用密码哈希同步测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)
  
<span data-ttu-id="39f06-117">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="39f06-117">This configuration consists of:</span></span>
  
- <span data-ttu-id="39f06-118">Microsoft 365 E5 试用版或付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="39f06-118">A Microsoft 365 E5 trial or paid subscription.</span></span>
- <span data-ttu-id="39f06-119">连接到 Internet 的简化的组织 Intranet，由 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机组成。</span><span class="sxs-lookup"><span data-stu-id="39f06-119">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="39f06-120">Azure AD 连接 APP1 上运行，以定期将 TESTLAB Active Directory 域服务 (AD DS) 域同步到 Microsoft 365 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="39f06-120">Azure AD Connect runs on APP1 to periodically synchronize the TESTLAB Active Directory Domain Services (AD DS) domain to the Azure AD tenant of your Microsoft 365 subscription.</span></span>

## <a name="phase-2-configure-azure-ad-connect-on-app1-for-azure-ad-seamless-sso"></a><span data-ttu-id="39f06-121">阶段 2：为 APP1 上的 Azure AD Connect 配置 Azure AD 无缝 SSO</span><span class="sxs-lookup"><span data-stu-id="39f06-121">Phase 2: Configure Azure AD Connect on APP1 for Azure AD Seamless SSO</span></span>

<span data-ttu-id="39f06-122">在此阶段，在 APP1 连接 Azure AD 无缝 SSO 配置 Azure AD 策略，然后验证其是否正常工作。</span><span class="sxs-lookup"><span data-stu-id="39f06-122">In this phase, configure Azure AD Connect on APP1 for Azure AD Seamless SSO, and then verify that it works.</span></span>

### <a name="configure-azure-ad-connect-on-app1"></a><span data-ttu-id="39f06-123">在 APP1 上配置 Azure AD Connect</span><span class="sxs-lookup"><span data-stu-id="39f06-123">Configure Azure AD Connect on APP1</span></span>

1. <span data-ttu-id="39f06-124">在 [Azure 门户](https://portal.azure.com)中，使用全局管理员帐户进行登录，然后使用 TESTLAB\User1 帐户连接到 APP1。</span><span class="sxs-lookup"><span data-stu-id="39f06-124">From the [Azure portal](https://portal.azure.com), sign in with your global administrator account, and then connect to APP1 with the TESTLAB\User1 account.</span></span>

2. <span data-ttu-id="39f06-125">从 APP1 桌面运行 Azure AD 连接。</span><span class="sxs-lookup"><span data-stu-id="39f06-125">From the APP1 desktop, run Azure AD Connect.</span></span>

3. <span data-ttu-id="39f06-126">在"**欢迎"页上，** 选择"**配置"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-126">On the **Welcome page**, select **Configure**.</span></span>

4. <span data-ttu-id="39f06-127">在"**其他任务"** 页上，选择 **"更改用户登录"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-127">On the **Additional tasks** page, select **Change user sign-in**, and then select **Next**.</span></span>

5. <span data-ttu-id="39f06-128">在 **"连接 Azure AD"** 页上，输入全局管理员帐户凭据，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-128">On the **Connect to Azure AD** page, enter your global administrator account credentials, and then select **Next**.</span></span>

6. <span data-ttu-id="39f06-129">在"**用户登录"页上**，选择 **"启用单一登录"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-129">On the **User sign-in** page, select **Enable single sign-on**, and then select **Next**.</span></span>

7. <span data-ttu-id="39f06-130">在"**启用单一登录"页上**，选择 **"输入凭据"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-130">On the **Enable single sign-on** page, select **Enter credentials**.</span></span>

8. <span data-ttu-id="39f06-131">在 **"Windows 安全中心"** 对话框中，输入 **user1** 和 user1 帐户的密码，选择"**确定**"，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-131">In the **Windows Security** dialog box, enter **user1** and the password of the user1 account, select **OK**, and then select **Next**.</span></span>

9. <span data-ttu-id="39f06-132">在"**准备配置"页上，** 选择"配置 **"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-132">On the **Ready to Configure** page, select **Configure**.</span></span>

10. <span data-ttu-id="39f06-133">在"**配置完成"页上**，选择"退出 **"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-133">On the **Configuration complete** page, select **Exit**.</span></span>

11. <span data-ttu-id="39f06-134">从 Azure 门户的左侧窗格中，选择"Azure Active Directory   >  **Azure AD 连接"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-134">From the Azure portal, in the left pane, select **Azure Active Directory** > **Azure AD Connect**.</span></span> <span data-ttu-id="39f06-135">验证无缝 **单一登录** 功能是否显示为 **已启用**。</span><span class="sxs-lookup"><span data-stu-id="39f06-135">Verify that the **Seamless single sign-on** feature appears as **Enabled**.</span></span>

<span data-ttu-id="39f06-136">接下来，测试能否使用 user1@testlab <strong>登录订阅。</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="39f06-136">Next, test the ability to sign in to your subscription with the <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="39f06-137">测试能否登录订阅。</span><span class="sxs-lookup"><span data-stu-id="39f06-137">user name of the User1 account.</span></span>

1. <span data-ttu-id="39f06-138">From Internet Explorer on APP1， select the settings icon， and then select **Internet Options**.</span><span class="sxs-lookup"><span data-stu-id="39f06-138">From Internet Explorer on APP1, select the settings icon, and then select **Internet Options**.</span></span>
 
2. <span data-ttu-id="39f06-139">在 **"Internet 选项"** 中，选择 **"安全"** 选项卡。</span><span class="sxs-lookup"><span data-stu-id="39f06-139">In **Internet Options**, select the **Security** tab.</span></span>

3. <span data-ttu-id="39f06-140">选择 **"本地 Intranet"，** 然后选择"**网站"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-140">Select **Local intranet**, and then select **Sites**.</span></span>

4. <span data-ttu-id="39f06-141">在本地 **Intranet 中**，选择"**高级"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-141">In **Local intranet**, select **Advanced**.</span></span>

5. <span data-ttu-id="39f06-142">在 **"将此网站添加到区域"中**，输入 **https <span>：//</span>autologon.microsoftazuread-sso.com**，选择 **"添加**  >  **关闭**  >  **确定**  >  **"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-142">In **Add this website to the zone**, enter **https <span>://</span>autologon.microsoftazuread-sso.com**, select **Add** > **Close** > **OK** > **OK**.</span></span>

6. <span data-ttu-id="39f06-143">注销，再重新登录，这次指定不同的帐户。</span><span class="sxs-lookup"><span data-stu-id="39f06-143">Sign out, and then sign in again, this time specifying a different account.</span></span>

7. <span data-ttu-id="39f06-144">当系统提示登录时，指定 <strong>user1@testlab。</strong>\<*your public domain*></span><span class="sxs-lookup"><span data-stu-id="39f06-144">When prompted to sign in, specify <strong>user1@testlab.</strong>\<*your public domain*></span></span> <span data-ttu-id="39f06-145">name，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="39f06-145">name, and then select **Next**.</span></span> <span data-ttu-id="39f06-146">应能够以 User1 身份成功登录，且不会看到密码输入提示。</span><span class="sxs-lookup"><span data-stu-id="39f06-146">You should successfully sign in as User1 without being prompted for a password.</span></span> <span data-ttu-id="39f06-147">这就证明无缝 SSO 能正常运行。</span><span class="sxs-lookup"><span data-stu-id="39f06-147">This proves that Azure AD Seamless SSO is working.</span></span>

<span data-ttu-id="39f06-148">请注意，虽然 User1 具有 TESTLAB AD DS 域的域管理员权限，但它不是 Azure AD 全局管理员。</span><span class="sxs-lookup"><span data-stu-id="39f06-148">Notice that although User1 has domain administrator permissions for the TESTLAB AD DS domain, it is not a global administrator for Azure AD.</span></span> <span data-ttu-id="39f06-149">因此，不会看到作为一个选项的 **管理员** 图标。</span><span class="sxs-lookup"><span data-stu-id="39f06-149">Therefore, you will not see the **Admin** icon as an option.</span></span>

<span data-ttu-id="39f06-150">下面是生成的配置：</span><span class="sxs-lookup"><span data-stu-id="39f06-150">Here is your resulting configuration:</span></span>

![使用传递身份验证测试环境的模拟企业配置](../media/pass-through-auth-m365-ent-test-environment/Phase1.png)

<span data-ttu-id="39f06-152">此配置包括：</span><span class="sxs-lookup"><span data-stu-id="39f06-152">This configuration consists of:</span></span>

- <span data-ttu-id="39f06-153">使用Microsoft 365 E5测试标签试用或付费订阅。\<*your domain name*></span><span class="sxs-lookup"><span data-stu-id="39f06-153">A Microsoft 365 E5 trial or paid subscriptions with the DNS domain testlab.\<*your domain name*></span></span> <span data-ttu-id="39f06-154">。</span><span class="sxs-lookup"><span data-stu-id="39f06-154">registered.</span></span>
- <span data-ttu-id="39f06-155">连接到 Internet 的简化的组织 Intranet，由 Azure 虚拟网络子网中的 DC1、APP1 和 CLIENT1 虚拟机组成。</span><span class="sxs-lookup"><span data-stu-id="39f06-155">A simplified organization intranet connected to the internet, consisting of the DC1, APP1, and CLIENT1 virtual machines on a subnet of an Azure virtual network.</span></span>
- <span data-ttu-id="39f06-156">在 APP1 上运行的 Azure AD Connect，用于将 Azure AD 租户中的帐户和组列表从 Microsoft 365 订阅同步到 TESTLAB AD DS 域。</span><span class="sxs-lookup"><span data-stu-id="39f06-156">Azure AD Connect runs on APP1 to synchronize the list of accounts and groups from the Azure AD tenant of your Microsoft 365 subscription to the TESTLAB AD DS domain.</span></span>
- <span data-ttu-id="39f06-157">Azure AD 无缝 SSO 已启用，这样模拟 Intranet 上的计算机无需指定用户帐户密码Microsoft 365即可登录到云资源。</span><span class="sxs-lookup"><span data-stu-id="39f06-157">Azure AD Seamless SSO is enabled so that computers on the simulated intranet can sign in to Microsoft 365 cloud resources without specifying a user account password.</span></span>

## <a name="next-step"></a><span data-ttu-id="39f06-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="39f06-158">Next step</span></span>

<span data-ttu-id="39f06-159">在测试环境中探索其他[标识](m365-enterprise-test-lab-guides.md#identity)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="39f06-159">Explore additional [identity](m365-enterprise-test-lab-guides.md#identity) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="39f06-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="39f06-160">See also</span></span>

[<span data-ttu-id="39f06-161">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="39f06-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="39f06-162">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="39f06-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="39f06-163">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="39f06-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)