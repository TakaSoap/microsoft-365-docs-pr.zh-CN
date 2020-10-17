---
title: 轻型基本配置
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 11/14/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
- seo-marvel-apr2020
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 使用此测试实验室指南创建用于测试适用于企业的 Microsoft 365 的轻型测试环境。
ms.openlocfilehash: 2b8505e142c3c1b87578db7342ed299b95d8c049
ms.sourcegitcommit: 53ff1fe6d6143b0bf011031eea9b85dc01ae4f74
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/16/2020
ms.locfileid: "48487384"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="41185-103">轻型基本配置</span><span class="sxs-lookup"><span data-stu-id="41185-103">The lightweight base configuration</span></span>

<span data-ttu-id="41185-104">*此测试实验室指南可用于适用于企业和 Office 365 企业测试环境的 Microsoft 365。*</span><span class="sxs-lookup"><span data-stu-id="41185-104">*This Test Lab Guide can be used for both Microsoft 365 for enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="41185-105">本文介绍如何使用 Microsoft 365 E5 订阅和运行 Windows 10 企业版的计算机创建简化的环境。</span><span class="sxs-lookup"><span data-stu-id="41185-105">This article describes how to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span>

![轻量级 Microsoft 365 企业版测试环境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="41185-107">创建轻型测试环境涉及五个阶段：</span><span class="sxs-lookup"><span data-stu-id="41185-107">Creating a lightweight test environment involves five phases:</span></span>
- [<span data-ttu-id="41185-108">第1阶段：创建 Microsoft 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="41185-108">Phase 1: Create your Microsoft 365 E5 subscription</span></span>](#phase-1-create-your-microsoft-365-e5-subscription)
- [<span data-ttu-id="41185-109">第 2 阶段：配置 Office 365 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="41185-109">Phase 2: Configure your Office 365 trial subscription</span></span>](#phase-2-configure-your-office-365-trial-subscription)
- [<span data-ttu-id="41185-110">第 3 阶段：添加 Microsoft 365 E5 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="41185-110">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>](#phase-3-add-a-microsoft-365-e5-trial-subscription)
- [<span data-ttu-id="41185-111">第 4 阶段：创建 Windows 10 企业版计算机</span><span class="sxs-lookup"><span data-stu-id="41185-111">Phase 4: Create a Windows 10 Enterprise computer</span></span>](#phase-4-create-a-windows-10-enterprise-computer)
- [<span data-ttu-id="41185-112">第 5 阶段：将 Windows 10 计算机加入到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="41185-112">Phase 5: Join your Windows 10 computer to Azure AD</span></span>](#phase-5-join-your-windows-10-computer-to-azure-ad)

<span data-ttu-id="41185-113">使用生成的环境测试 [适用于企业的 Microsoft 365](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="41185-113">Use the resulting environment to test the features and functionality of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="41185-115">有关指向 Microsoft 365 for 企业版测试实验室指南堆栈中的所有文章的可视化地图，请参阅 [适用于企业测试实验室指南堆栈的 microsoft 365](../downloads/Microsoft365EnterpriseTLGStack.pdf)。</span><span class="sxs-lookup"><span data-stu-id="41185-115">For a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack, see [Microsoft 365 for enterprise Test Lab Guide Stack](../downloads/Microsoft365EnterpriseTLGStack.pdf).</span></span>

>[!NOTE]
><span data-ttu-id="41185-116">不妨打印这篇文章，以便记录在 30 天的 Office 365 试用版订阅期内需要对此环境使用的特定信息。</span><span class="sxs-lookup"><span data-stu-id="41185-116">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="41185-117">可以轻松地将该订阅的试用期再延长 30 天。</span><span class="sxs-lookup"><span data-stu-id="41185-117">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="41185-118">对于永久性测试环境，请创建一个包含单独 Azure AD 租户和少量许可证的新付费订阅。</span><span class="sxs-lookup"><span data-stu-id="41185-118">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

## <a name="phase-1-create-your-microsoft-365-e5-subscription"></a><span data-ttu-id="41185-119">第1阶段：创建 Microsoft 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="41185-119">Phase 1: Create your Microsoft 365 E5 subscription</span></span>

<span data-ttu-id="41185-120">我们首先使用 Microsoft 365 E5 试用订阅，然后向其添加 Microsoft 365 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="41185-120">We start with an Microsoft 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

>[!NOTE]
><span data-ttu-id="41185-121">我们建议您创建 Office 365 的试用订阅，以便您的测试环境具有来自您当前拥有的任何付费订阅的单独的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="41185-121">We recommend that you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="41185-122">这种分离意味着您可以在不影响生产订阅的情况下，在测试租户中添加和删除用户和组。</span><span class="sxs-lookup"><span data-stu-id="41185-122">This separation means that you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>

<span data-ttu-id="41185-123">要启动 Microsoft 365 E5 试用版订阅，你首先需要一个虚构公司名称和一个新的 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="41185-123">To start your Microsoft 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="41185-p103">我们建议你将公司名称 Contoso 的变体用作你的公司名称，它是 Microsoft 示例内容中使用的虚构公司，但这并不是必需的。在此记录虚构的公司名称：</span><span class="sxs-lookup"><span data-stu-id="41185-p103">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![折线图](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="41185-p104">要注册新的 Microsoft 帐户，请转到 [https://outlook.com](https://outlook.com)，然后使用新的电子邮件帐户和地址创建一个帐户。此帐户将用于注册 Office 365。</span><span class="sxs-lookup"><span data-stu-id="41185-p104">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
    - <span data-ttu-id="41185-129">在此记录新帐户的名字和姓氏：</span><span class="sxs-lookup"><span data-stu-id="41185-129">Record the first and last name of your new account here:</span></span> ![折线图](../media/Common-Images/TableLine.png)
    
    - <span data-ttu-id="41185-131">在此记录新的电子邮件帐户地址：</span><span class="sxs-lookup"><span data-stu-id="41185-131">Record the new email account address here:</span></span> ![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="41185-133">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="41185-133">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="41185-134">注册 Office 365 E5 试用订阅</span><span class="sxs-lookup"><span data-stu-id="41185-134">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="41185-135">在浏览器中，转到 [https://aka.ms/e5trial](https://aka.ms/e5trial) 。</span><span class="sxs-lookup"><span data-stu-id="41185-135">In your browser, go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="41185-136">在 " **感谢您选择 Office 365 E5** " 页的步骤1中，输入新的电子邮件帐户地址。</span><span class="sxs-lookup"><span data-stu-id="41185-136">In step 1 of the **Thank you for choosing Office 365 E5** page, enter your new email account address.</span></span>
3. <span data-ttu-id="41185-137">在跟踪订阅过程的第2步中，输入请求的信息，然后执行验证。</span><span class="sxs-lookup"><span data-stu-id="41185-137">In step 2 of the trail subscription process, enter the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="41185-138">在步骤3中，输入组织名称，然后输入将成为订阅全局管理员的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="41185-138">In step 3, enter an organization name and then an account name that will be the global admin for the subscription.</span></span>
5. <span data-ttu-id="41185-139">在第 4 步中，在此记录登录页面（选择并复制）：</span><span class="sxs-lookup"><span data-stu-id="41185-139">For step 4, record the sign-in page here (select and copy):</span></span> ![折线图](../media/Common-Images/TableLine.png)
6. <span data-ttu-id="41185-141">在此记录用户 ID：![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="41185-141">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="41185-142">记录您在安全位置输入的密码。</span><span class="sxs-lookup"><span data-stu-id="41185-142">Record the password that you entered in a secure location.</span></span>
   <span data-ttu-id="41185-143">此值被称为 **“全局管理员名称”**。</span><span class="sxs-lookup"><span data-stu-id="41185-143">This value will be referred to as the **global administrator name**.</span></span>
7. <span data-ttu-id="41185-144">选择 " **转到安装程序**"。</span><span class="sxs-lookup"><span data-stu-id="41185-144">Select **Go to Setup**.</span></span>
8. <span data-ttu-id="41185-145">在 "Office 365 E5 设置" 中，选择 " **继续使用 *您的组织*onmicrosoft.com 电子邮件并登录**"，然后选择 " **退出并继续**"。</span><span class="sxs-lookup"><span data-stu-id="41185-145">In Office 365 E5 Setup, select **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then select **Exit and continue later**.</span></span>

<span data-ttu-id="41185-146">你应当查看 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="41185-146">You should see the Microsoft 365 admin center.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="41185-147">第 2 阶段：配置 Office 365 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="41185-147">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="41185-148">在这个阶段，你为订阅配置其他用户，并向这些用户分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="41185-148">In this phase, you configure your subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="41185-149">若要从计算机连接到使用 Azure Active Directory PowerShell for Graph 模块的订阅，请按照 [connect To Microsoft 365 With PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module)中的说明操作。</span><span class="sxs-lookup"><span data-stu-id="41185-149">To connect to your subscription with the Azure Active Directory PowerShell for Graph module from your computer, use the instructions in [Connect to Microsoft 365 with PowerShell](connect-to-microsoft-365-powershell.md#connect-with-the-azure-active-directory-powershell-for-graph-module).</span></span>
    
<span data-ttu-id="41185-150">在 " **Windows PowerShell 凭据请求** " 对话框中，输入全局管理员名称 (例如，" *Jdoe@contosotoycompany.onmicrosoft.com* ") 和 "密码"。</span><span class="sxs-lookup"><span data-stu-id="41185-150">In the **Windows PowerShell Credential Request** dialog box, enter the global administrator name (for example, *jdoe@contosotoycompany.onmicrosoft.com*) and password.</span></span>
  
<span data-ttu-id="41185-151">填写你的组织名称 (例如， *contosotoycompany*) ，用于您的位置的双字符国家/地区代码，一个公用帐户密码，然后从 PowerShell 提示符处运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="41185-151">Fill in your organization name (for example, *contosotoycompany*), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

```powershell
$orgName="<organization name>"
$loc="<two-character country code, such as US>"
$commonPW="<common user account password>"
$PasswordProfile=New-Object -TypeName Microsoft.Open.AzureAD.Model.PasswordProfile
$PasswordProfile.Password=$commonPW

$userUPN= "user2@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 2" -GivenName User -SurName 2 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user2"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user3@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 3" -GivenName User -SurName 3 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user3"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign

$userUPN= "user4@" + $orgName + ".onmicrosoft.com"
New-AzureADUser -DisplayName "User 4" -GivenName User -SurName 4 -UserPrincipalName $userUPN -UsageLocation $loc -AccountEnabled $true -PasswordProfile $PasswordProfile -MailNickName "user4"
$License = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicense
$License.SkuId = (Get-AzureADSubscribedSku | Where-Object -Property SkuPartNumber -Value "ENTERPRISEPREMIUM" -EQ).SkuID
$LicensesToAssign = New-Object -TypeName Microsoft.Open.AzureAD.Model.AssignedLicenses
$LicensesToAssign.AddLicenses = $License
Set-AzureADUserLicense -ObjectId $userUPN -AssignedLicenses $LicensesToAssign
```
> [!NOTE]
> <span data-ttu-id="41185-152">此处使用公用密码旨在自动配置测试环境，简化配置过程。</span><span class="sxs-lookup"><span data-stu-id="41185-152">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="41185-153">显然，对于生产订阅，这是非常不鼓励的。</span><span class="sxs-lookup"><span data-stu-id="41185-153">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="41185-154">记录关键信息供将来参考</span><span class="sxs-lookup"><span data-stu-id="41185-154">Record key information for future reference</span></span>

<span data-ttu-id="41185-155">如果尚未记录这些值，请立即记录这些值：</span><span class="sxs-lookup"><span data-stu-id="41185-155">If you haven't already recorded these values, record them now:</span></span>
  
- <span data-ttu-id="41185-156">全局管理员名称：</span><span class="sxs-lookup"><span data-stu-id="41185-156">Global administrator name:</span></span> ![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="41185-158">.onmicrosoft.com（在第 1 阶段的第 6 步中）</span><span class="sxs-lookup"><span data-stu-id="41185-158">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="41185-159">此外，还应将此帐户的密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="41185-159">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="41185-160">试用订阅组织名称：</span><span class="sxs-lookup"><span data-stu-id="41185-160">Your trial subscription organization name:</span></span> ![折线图](../media/Common-Images/TableLine.png) <span data-ttu-id="41185-162">（在第 1 阶段的第 4 步中）</span><span class="sxs-lookup"><span data-stu-id="41185-162">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="41185-163">要列出 User 2、User 3、User 4 和 User 5 的帐户，从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="41185-163">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="41185-164">在此记录帐户名称：</span><span class="sxs-lookup"><span data-stu-id="41185-164">Record the account names here:</span></span>
    
  - <span data-ttu-id="41185-165">用户 2 帐户名：user2@</span><span class="sxs-lookup"><span data-stu-id="41185-165">User 2 account name: user2@</span></span>![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="41185-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="41185-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="41185-168">用户 3 帐户名：user3@</span><span class="sxs-lookup"><span data-stu-id="41185-168">User 3 account name: user3@</span></span>![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="41185-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="41185-170">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="41185-171">用户 4 帐户名：user4@</span><span class="sxs-lookup"><span data-stu-id="41185-171">User 4 account name: user4@</span></span>![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="41185-173">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="41185-173">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="41185-174">用户 5 帐户名：user5@</span><span class="sxs-lookup"><span data-stu-id="41185-174">User 5 account name: user5@</span></span>![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="41185-176">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="41185-176">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="41185-177">此外，在安全位置记录这些帐户的公用密码。</span><span class="sxs-lookup"><span data-stu-id="41185-177">Also record the common password for these accounts in a secure location.</span></span>
   
### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="41185-178">使用 Office 365 测试环境</span><span class="sxs-lookup"><span data-stu-id="41185-178">Using an Office 365 test environment</span></span>

<span data-ttu-id="41185-179">如果只需要 Office 365 测试环境，则无需阅读本文的其余部分。</span><span class="sxs-lookup"><span data-stu-id="41185-179">If you need only an Office 365 test environment, you do not need to read the rest of this article.</span></span>

<span data-ttu-id="41185-180">有关适用于 Office 365 和 Microsoft 365 的其他测试实验室指南，请参阅适用于 [企业测试实验室指南的 microsoft 365](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="41185-180">For additional Test Lab Guides that apply to both Office 365 and Microsoft 365, see [Microsoft 365 for enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md).</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="41185-181">第 3 阶段：添加 Microsoft 365 E5 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="41185-181">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="41185-182">在该阶段中，可注册 Microsoft 365 E5 试用版订阅，并将其添加到 Office 365 E5 试用版订阅所在的组织中。</span><span class="sxs-lookup"><span data-stu-id="41185-182">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="41185-183">首先，请添加 Microsoft 365 E5 试用版订阅并向全局管理员帐户分配一个新的 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="41185-183">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="41185-184">在 internet 浏览器专用窗口中，使用全局管理员帐户凭据登录到 Microsoft 365 管理中心 [https://admin.microsoft.com](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="41185-184">In an internet browser private window, use your global administrator account credentials to sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com).</span></span>
    
2. <span data-ttu-id="41185-185">在 " **Microsoft 365 管理中心** " 页的左侧导航栏中，选择 " **付费 > 购买服务**"。</span><span class="sxs-lookup"><span data-stu-id="41185-185">On the **Microsoft 365 admin center** page, in the left navigation, select **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="41185-186">在 " **购买服务** " 页上，选择 " **Microsoft 365 E5**"，然后选择 " **获取免费试用版**"。</span><span class="sxs-lookup"><span data-stu-id="41185-186">On the **Purchase services** page, select **Microsoft 365 E5**, and then select **Get free trial**.</span></span>

4. <span data-ttu-id="41185-187">在 **Microsoft 365 E5 试用** 页面上，决定接收短信或电话呼叫，输入你的电话号码，然后选择 "向 **我发出文本** " 或 " **呼叫我**"。</span><span class="sxs-lookup"><span data-stu-id="41185-187">On the **Microsoft 365 E5 Trial** page, decide to receive a text message or a phone call, enter your phone number, and then select **Text me** or **Call me**.</span></span> <span data-ttu-id="41185-188">执行验证。</span><span class="sxs-lookup"><span data-stu-id="41185-188">Perform the verification.</span></span>

5. <span data-ttu-id="41185-189">在 " **确认订单** " 页上，选择 " **立即试用**"。</span><span class="sxs-lookup"><span data-stu-id="41185-189">On the **Confirm your order** page, select **Try now**.</span></span>

6. <span data-ttu-id="41185-190">在 " **订单接收** " 页上，选择 " **继续**"。</span><span class="sxs-lookup"><span data-stu-id="41185-190">On the **Order receipt** page, select **Continue**.</span></span>

7. <span data-ttu-id="41185-191">在 Microsoft 365 管理中心，选择 " **用户" > 活动用户**"。</span><span class="sxs-lookup"><span data-stu-id="41185-191">In the Microsoft 365 admin center, select **Users > Active users**.</span></span>

8. <span data-ttu-id="41185-192">在 " **活动用户**" 中，选择管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="41185-192">In **Active users**, select your administrator account.</span></span>

9. <span data-ttu-id="41185-193">选择 " **许可证和应用**"。</span><span class="sxs-lookup"><span data-stu-id="41185-193">Select **Licenses and apps**.</span></span>

10. <span data-ttu-id="41185-194">禁用 Office 365 企业版 E5 的许可证，并启用 Microsoft 365 E5 的许可证。</span><span class="sxs-lookup"><span data-stu-id="41185-194">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="41185-195">选择 " **保存更改**"，然后关闭 "用户帐户信息" 窗格。</span><span class="sxs-lookup"><span data-stu-id="41185-195">Select **Save changes**, and then close the user account information pane.</span></span>

<span data-ttu-id="41185-196">接下来，对其他所有帐户（用户 2、用户 3、用户 4 和用户 5）重复执行上面过程的第 8 步到第 11 步。</span><span class="sxs-lookup"><span data-stu-id="41185-196">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="41185-197">Microsoft 365 E5 试用订阅的长度为30天。</span><span class="sxs-lookup"><span data-stu-id="41185-197">The length of the Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="41185-198">对于永久测试环境，将此试用版订阅转换为带少量许可证的付费订阅。</span><span class="sxs-lookup"><span data-stu-id="41185-198">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span>
  
<span data-ttu-id="41185-199">测试环境现在包含：</span><span class="sxs-lookup"><span data-stu-id="41185-199">Your test environment now has:</span></span>
  
- <span data-ttu-id="41185-200">Microsoft 365 E5 试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="41185-200">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="41185-201">所有适当的用户帐户（无论是全局管理员帐户还是全部五个用户帐户）都可以使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="41185-201">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="41185-202">生成的配置（添加 Microsoft 365 E5）如下所示：</span><span class="sxs-lookup"><span data-stu-id="41185-202">Your resulting configuration, which adds Microsoft 365 E5, looks like this:</span></span>
  
![Microsoft 365 企业版测试环境的第 3 阶段](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="41185-204">第 4 阶段：创建 Windows 10 企业版计算机</span><span class="sxs-lookup"><span data-stu-id="41185-204">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="41185-205">在这一阶段，将运行 Windows 10 企业版的独立计算机创建为物理计算机、虚拟机或 Azure 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="41185-205">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="41185-206">物理计算机</span><span class="sxs-lookup"><span data-stu-id="41185-206">Physical computer</span></span>

<span data-ttu-id="41185-207">在个人计算机上，安装 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="41185-207">On a personal computer, install Windows 10 Enterprise.</span></span> <span data-ttu-id="41185-208">你可以在 [此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用版。</span><span class="sxs-lookup"><span data-stu-id="41185-208">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="41185-209">虚拟机</span><span class="sxs-lookup"><span data-stu-id="41185-209">Virtual machine</span></span>

<span data-ttu-id="41185-210">使用您选择的虚拟机管理程序创建虚拟机，然后在其上安装 Windows 10 企业版。</span><span class="sxs-lookup"><span data-stu-id="41185-210">Use the hypervisor of your choice to create a virtual machine, and then install Windows 10 Enterprise on it.</span></span> <span data-ttu-id="41185-211">你可以在 [此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用版。</span><span class="sxs-lookup"><span data-stu-id="41185-211">You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="41185-212">Azure 中的虚拟机</span><span class="sxs-lookup"><span data-stu-id="41185-212">Virtual machine in Azure</span></span>

<span data-ttu-id="41185-p111">要在 Microsoft Azure 中创建 Windows 10 虚拟机，***你必须拥有基于 Visual Studio 的订阅***，以便有权访问 Windows 10 企业版的映像。其他类型的 Azure 订阅（如试用版和付费订阅）均无权访问此映像。有关最新信息，请参阅[在 Azure 中使用 Windows 客户端实现开发/测试方案](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)。</span><span class="sxs-lookup"><span data-stu-id="41185-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="41185-216">[!注意] 下面的命令集使用最新版 Azure PowerShell。</span><span class="sxs-lookup"><span data-stu-id="41185-216">The following command sets use the latest version of Azure PowerShell.</span></span> <span data-ttu-id="41185-217">请参阅 [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)（Azure PowerShell cmdlet 使用入门）。</span><span class="sxs-lookup"><span data-stu-id="41185-217">See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/).</span></span> <span data-ttu-id="41185-218">这些命令集构建一个名为 WIN10 的 Windows 10 企业版虚拟机及其所有所需的基础结构，包括资源组、存储帐户和虚拟网络。</span><span class="sxs-lookup"><span data-stu-id="41185-218">These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network.</span></span> <span data-ttu-id="41185-219">如果你已熟悉 Azure 基础结构服务，请修改这些说明以适应当前部署的基础结构。</span><span class="sxs-lookup"><span data-stu-id="41185-219">If you are already familiar with Azure infrastructure services, adapt these instructions to suit your currently deployed infrastructure.</span></span>
  
<span data-ttu-id="41185-220">首先，启动 Microsoft PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="41185-220">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="41185-221">使用此命令登录 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="41185-221">Sign in to your Azure account with this command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="41185-222">使用此命令获取订阅名称。</span><span class="sxs-lookup"><span data-stu-id="41185-222">Get your subscription name using this  command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="41185-223">设置 Azure 订阅。</span><span class="sxs-lookup"><span data-stu-id="41185-223">Set your Azure subscription.</span></span> <span data-ttu-id="41185-224">使用正确的名称替换引号内的所有内容（包括 \< and > 字符）。</span><span class="sxs-lookup"><span data-stu-id="41185-224">Replace everything within the quotation marks, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="41185-225">接下来，创建一个新的资源组。</span><span class="sxs-lookup"><span data-stu-id="41185-225">Next, create a new resource group.</span></span> <span data-ttu-id="41185-226">要确定一个唯一的资源组名称，请使用此命令列出你现有的资源组。</span><span class="sxs-lookup"><span data-stu-id="41185-226">To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="41185-227">使用这些命令创建新的资源组。</span><span class="sxs-lookup"><span data-stu-id="41185-227">Create your new resource group with these commands.</span></span> <span data-ttu-id="41185-228">使用正确的名称替换引号内的所有内容（包括 \< and > 字符）。</span><span class="sxs-lookup"><span data-stu-id="41185-228">Replace everything within the quotation marks, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="41185-229">接下来，使用这些命令创建新的虚拟网络和 WIN10 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="41185-229">Next, create a new virtual network and the WIN10 virtual machine with these commands.</span></span> <span data-ttu-id="41185-230">出现提示时，提供 WIN10 的本地管理员帐户的名称和密码，并将它们存储在安全位置。</span><span class="sxs-lookup"><span data-stu-id="41185-230">When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
```powershell
$corpnetSubnet=New-AzVirtualNetworkSubnetConfig -Name Corpnet -AddressPrefix 10.0.0.0/24
New-AzVirtualNetwork -Name "M365Ent-TestLab" -ResourceGroupName $rgName -Location $locName -AddressPrefix 10.0.0.0/8 -Subnet $corpnetSubnet
$rule1=New-AzNetworkSecurityRuleConfig -Name "RDPTraffic" -Description "Allow RDP to all VMs on the subnet" -Access Allow -Protocol Tcp -Direction Inbound -Priority 100 -SourceAddressPrefix Internet -SourcePortRange * -DestinationAddressPrefix * -DestinationPortRange 3389
New-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName -Location $locName -SecurityRules $rule1
$vnet=Get-AzVirtualNetwork -ResourceGroupName $rgName -Name "M365Ent-TestLab"
$nsg=Get-AzNetworkSecurityGroup -Name Corpnet -ResourceGroupName $rgName
Set-AzVirtualNetworkSubnetConfig -VirtualNetwork $vnet -Name Corpnet -AddressPrefix "10.0.0.0/24" -NetworkSecurityGroup $nsg
$vnet | Set-AzVirtualNetwork
$pip=New-AzPublicIpAddress -Name WIN10-PIP -ResourceGroupName $rgName -Location $locName -AllocationMethod Dynamic
$nic=New-AzNetworkInterface -Name WIN10-NIC -ResourceGroupName $rgName -Location $locName -SubnetId $vnet.Subnets[0].Id -PublicIpAddressId $pip.Id
$vm=New-AzVMConfig -VMName WIN10 -VMSize Standard_A2_V2
$cred=Get-Credential -Message "Type the name and password of the local administrator account for WIN10."
$vm=Set-AzVMOperatingSystem -VM $vm -Windows -ComputerName WIN10 -Credential $cred -ProvisionVMAgent -EnableAutoUpdate
$vm=Set-AzVMSourceImage -VM $vm -PublisherName MicrosoftWindowsDesktop -Offer Windows-10 -Skus RS3-Pro -Version "latest"
$vm=Add-AzVMNetworkInterface -VM $vm -Id $nic.Id
$vm=Set-AzVMOSDisk -VM $vm -Name WIN10-TestLab-OSDisk -DiskSizeInGB 128 -CreateOption FromImage
New-AzVM -ResourceGroupName $rgName -Location $locName -VM $vm
```

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="41185-231">第 5 阶段：将 Windows 10 计算机加入到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="41185-231">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="41185-232">在创建具有 Windows 10 企业版的物理计算机或虚拟机之后，使用本地管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="41185-232">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="41185-233">对于 Azure 中的虚拟机，请使用  [以下说明](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) 连接到它。</span><span class="sxs-lookup"><span data-stu-id="41185-233">For a virtual machine in Azure, use  [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon) to connect to it.</span></span>
  
<span data-ttu-id="41185-234">接下来，将 WIN10 计算机联接到 Microsoft 365 E5 订阅的 Azure AD 租户中。</span><span class="sxs-lookup"><span data-stu-id="41185-234">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="41185-235">在 WIN10 计算机的桌面上，选择 " **开始 > 设置" > 帐户 > 访问 "工作或学校 > 连接**"。</span><span class="sxs-lookup"><span data-stu-id="41185-235">On the desktop of the WIN10 computer, select **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="41185-236">在 " **设置工作或学校帐户** " 对话框中，选择 "将 **此设备加入 Azure Active Directory**"。</span><span class="sxs-lookup"><span data-stu-id="41185-236">In the **Set up a work or school account** dialog box, select **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="41185-237">在 " **工作或学校帐户**" 中，输入 Microsoft 365 E5 订阅的全局管理员帐户名称，然后选择 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="41185-237">In **Work or school account**, enter the global administrator account name of your Microsoft 365 E5 subscription, and then select **Next**.</span></span>
    
4. <span data-ttu-id="41185-238">在 " **输入密码**" 中，输入全局管理员帐户的密码，然后选择 " **登录**"。</span><span class="sxs-lookup"><span data-stu-id="41185-238">In **Enter password**, enter the password for your global administrator account, and then select **Sign in**.</span></span>
    
5. <span data-ttu-id="41185-239">当系统提示您确保这是你的组织时，请选择 " **加入**"，然后选择 " **完成**"。</span><span class="sxs-lookup"><span data-stu-id="41185-239">When prompted to make sure that this is your organization, select **Join**, and then select **Done**.</span></span>
    
6. <span data-ttu-id="41185-240">关闭“设置”窗口。</span><span class="sxs-lookup"><span data-stu-id="41185-240">Close the settings window.</span></span>
    
<span data-ttu-id="41185-241">接下来，在 WIN10 计算机上安装适用于企业的 Microsoft 365 应用程序：</span><span class="sxs-lookup"><span data-stu-id="41185-241">Next, install Microsoft 365 Apps for enterprise on the WIN10 computer:</span></span>
  
1. <span data-ttu-id="41185-242">打开 Microsoft Edge 浏览器，并使用全局管理员帐户凭据登录 [Microsoft 365 管理中心](https://admin.microsoft.com) 。</span><span class="sxs-lookup"><span data-stu-id="41185-242">Open the Microsoft Edge browser and sign in to the [Microsoft 365 admin center](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="41185-243">在 " **Microsoft Office 主页** " 选项卡上，选择 " **安装 Office**"。</span><span class="sxs-lookup"><span data-stu-id="41185-243">On the **Microsoft Office Home** tab, select **Install Office**.</span></span>
    
3. <span data-ttu-id="41185-244">在系统提示时，选择 "**运行**"，然后为 "**用户帐户控制** **" 选择 "是"** 。</span><span class="sxs-lookup"><span data-stu-id="41185-244">When prompted with what to do, select **Run**, and then select **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="41185-245">等待 Office 完成安装。</span><span class="sxs-lookup"><span data-stu-id="41185-245">Wait for Office to complete its installation.</span></span> <span data-ttu-id="41185-246">如果看到 " **全是**"，请选择 " **关闭** " 两次。</span><span class="sxs-lookup"><span data-stu-id="41185-246">When you see **You're all set!**, select **Close** twice.</span></span>
    
<span data-ttu-id="41185-247">生成的环境如下所示：</span><span class="sxs-lookup"><span data-stu-id="41185-247">Your resulting environment looks like this:</span></span>

![Microsoft 365 企业版测试环境的第 5 阶段](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="41185-249">这包括符合以下条件的 WIN10 计算机：</span><span class="sxs-lookup"><span data-stu-id="41185-249">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="41185-250">已联接 Microsoft 365 E5 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="41185-250">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="41185-251">已注册为 Microsoft Intune (EMS) 中的 Azure AD 设备。</span><span class="sxs-lookup"><span data-stu-id="41185-251">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="41185-252">安装了适用于企业的 Microsoft 365 应用程序。</span><span class="sxs-lookup"><span data-stu-id="41185-252">Microsoft 365 Apps for enterprise installed.</span></span>
  
<span data-ttu-id="41185-253">现在，你可以试用 [Microsoft 365 for 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="41185-253">You are now ready to experiment with additional features of [Microsoft 365 for enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="41185-254">后续步骤</span><span class="sxs-lookup"><span data-stu-id="41185-254">Next steps</span></span>

<span data-ttu-id="41185-255">浏览下面这些附加的一系列测试实验室指南：</span><span class="sxs-lookup"><span data-stu-id="41185-255">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="41185-256">标识</span><span class="sxs-lookup"><span data-stu-id="41185-256">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="41185-257">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="41185-257">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="41185-258">信息保护</span><span class="sxs-lookup"><span data-stu-id="41185-258">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="41185-259">另请参阅</span><span class="sxs-lookup"><span data-stu-id="41185-259">See also</span></span>

[<span data-ttu-id="41185-260">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="41185-260">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="41185-261">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="41185-261">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="41185-262">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="41185-262">Microsoft 365 for enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
