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
localization_priority: Priority
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom:
- Ent_TLGs
ms.assetid: 6f916a77-301c-4be2-b407-6cec4d80df76
description: 根据本测试实验室指南，可以创建轻型测试环境来测试 Microsoft 365 企业版。
ms.openlocfilehash: 4e90cc01cb37664f3084daf7295e9d59052809af
ms.sourcegitcommit: 93e6bf1b541e22129f8c443051375d0ef1374150
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/13/2020
ms.locfileid: "42633340"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="e89eb-103">轻型基本配置</span><span class="sxs-lookup"><span data-stu-id="e89eb-103">The lightweight base configuration</span></span>

<span data-ttu-id="e89eb-104">*本测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="e89eb-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="e89eb-105">本文分步说明了如何使用 Microsoft 365 E5 订阅和运行 Windows 10 企业版的计算机创建简化的环境。</span><span class="sxs-lookup"><span data-stu-id="e89eb-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![轻量级 Microsoft 365 企业版测试环境](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="e89eb-107">使用生成的环境来测试 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="e89eb-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![适用于 Microsoft 云的测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="e89eb-109">单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="e89eb-109">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="e89eb-110">第 1 阶段：创建 Office 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="e89eb-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="e89eb-111">我们首先使用 Office 365 E5 试用版订阅，然后向其添加 Microsoft 365 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="e89eb-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="e89eb-112">要启动 Office 365 E5 试用订阅，你首先需要一个虚构公司名称和一个新的 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="e89eb-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="e89eb-p101">我们建议你将公司名称 Contoso 的变体用作你的公司名称，它是 Microsoft 示例内容中使用的虚构公司，但这并不是必需的。在此记录虚构的公司名称：</span><span class="sxs-lookup"><span data-stu-id="e89eb-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here:</span></span> ![折线图](../media/Common-Images/TableLine.png)
    
2. <span data-ttu-id="e89eb-p102">要注册新的 Microsoft 帐户，请转到 [https://outlook.com](https://outlook.com)，然后使用新的电子邮件帐户和地址创建一个帐户。此帐户将用于注册 Office 365。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="e89eb-118">在此记录新帐户的名字和姓氏：</span><span class="sxs-lookup"><span data-stu-id="e89eb-118">Record the first and last name of your new account here:</span></span> ![折线图](../media/Common-Images/TableLine.png)
    
  - <span data-ttu-id="e89eb-120">在此记录新的电子邮件帐户地址：</span><span class="sxs-lookup"><span data-stu-id="e89eb-120">Record the new email account address here:</span></span> ![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="e89eb-122">@outlook.com</span><span class="sxs-lookup"><span data-stu-id="e89eb-122">@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="e89eb-123">注册 Office 365 E5 试用订阅</span><span class="sxs-lookup"><span data-stu-id="e89eb-123">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="e89eb-124">在计算机上打开 Internet 浏览器，转到 [https://aka.ms/e5trial](https://aka.ms/e5trial)。</span><span class="sxs-lookup"><span data-stu-id="e89eb-124">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="e89eb-125">在“感谢选择 Office 365 E5”\*\*\*\* 页面上，指定第 1 步中的新电子邮件帐户地址。</span><span class="sxs-lookup"><span data-stu-id="e89eb-125">On the **Thank you for choosing Office 365 E5** page, specify, your new email account address in step 1.</span></span>
3. <span data-ttu-id="e89eb-126">在跟踪订阅过程的第 2 步中，键入请求的信息，然后执行验证。</span><span class="sxs-lookup"><span data-stu-id="e89eb-126">In step 2 of the trail subscription process, type the requested information, and then perform the verification.</span></span>
4. <span data-ttu-id="e89eb-127">在第 3 步中，依次键入组织名称和将成为该订阅的全局管理员的帐户名称。</span><span class="sxs-lookup"><span data-stu-id="e89eb-127">In step 3, type an organization name and then an account name that will be the global admin for the subscription.</span></span> 
5. <span data-ttu-id="e89eb-128">在第 4 步中，在此记录登录页面（选择并复制）：</span><span class="sxs-lookup"><span data-stu-id="e89eb-128">For step 4, record the sign-in page here (select and copy):</span></span> ![折线图](../media/Common-Images/TableLine.png) 
6. <span data-ttu-id="e89eb-130">在此记录用户 ID：![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e89eb-130">Record the user ID here: ![Line](../media/Common-Images/TableLine.png).onmicrosoft.com</span></span>  
   <span data-ttu-id="e89eb-131">将你键入的密码记录在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="e89eb-131">Record the password that you typed in a secure location.</span></span>
   <span data-ttu-id="e89eb-132">此值将被称为“Office 365 全局管理员名称”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-132">This value will be referred to as the **Office 365 global administrator name**.</span></span>
8. <span data-ttu-id="e89eb-133">选择“转到设置”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-133">Click **Go to Setup**.</span></span>
9. <span data-ttu-id="e89eb-134">在 Office 365 E5 设置中，单击邮件的“继续使用 organization **.onmicrosoft.com 并登录”*，\* 然后单击“退出**，**稍后再继续”。*\*</span><span class="sxs-lookup"><span data-stu-id="e89eb-134">In Office 365 E5 Setup, click **Continue using *your organization*.onmicrosoft.com for email and signing in**, and then click **Exit and continue later**.</span></span>

<span data-ttu-id="e89eb-135">你应当查看 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="e89eb-135">You should see the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="e89eb-136">我们为你创建了 Office 365 的试用版订阅，以便你的测试环境具有与你当前拥有的任何付费版订阅分开的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="e89eb-136">We have you create a trial subscription of Office 365 so that your test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="e89eb-137">这样分开意味着你可在测试租户中添加和删除用户和组，而不影响生产订阅。</span><span class="sxs-lookup"><span data-stu-id="e89eb-137">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="e89eb-138">第 2 阶段：配置 Office 365 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="e89eb-138">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="e89eb-139">在这个阶段，配置包含其他用户的 Office 365 订阅，并为这些用户分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="e89eb-139">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="e89eb-140">按照[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) 中的说明，使用计算机中的 Azure Active Directory PowerShell for Graph 模块连接到 Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="e89eb-140">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="e89eb-141">在“Windows PowerShell 凭据请求”\*\*\*\* 对话框中，键入 Office 365 全局管理员名称（示例：jdoe@contosotoycompany.onmicrosoft.com）和密码。</span><span class="sxs-lookup"><span data-stu-id="e89eb-141">In the **Windows PowerShell Credential Request** dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="e89eb-142">填写组织名称（示例：contosotoycompany）、你所在位置的两位字符的国家/地区代码以及通用帐户密码，然后 PowerShell 提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e89eb-142">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="e89eb-143">此处使用公用密码旨在自动配置测试环境，简化配置过程。</span><span class="sxs-lookup"><span data-stu-id="e89eb-143">The use of a common password here is for automation and ease of configuration for a test environment.</span></span> <span data-ttu-id="e89eb-144">显然，对于生产订阅，这是非常不鼓励的。</span><span class="sxs-lookup"><span data-stu-id="e89eb-144">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="e89eb-145">记录关键信息供将来参考</span><span class="sxs-lookup"><span data-stu-id="e89eb-145">Record key information for future reference</span></span>

<span data-ttu-id="e89eb-146">不妨打印这篇文章，以便记录在 30 天的 Office 365 试用版订阅期内需要对此环境使用的特定信息。</span><span class="sxs-lookup"><span data-stu-id="e89eb-146">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="e89eb-147">可以轻松地将该订阅的试用期再延长 30 天。</span><span class="sxs-lookup"><span data-stu-id="e89eb-147">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="e89eb-148">对于永久性测试环境，请创建一个包含单独 Azure AD 租户和少量许可证的新付费订阅。</span><span class="sxs-lookup"><span data-stu-id="e89eb-148">For a permanent test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="e89eb-149">请记录以下值：</span><span class="sxs-lookup"><span data-stu-id="e89eb-149">Record these values:</span></span>
  
- <span data-ttu-id="e89eb-150">Office 365 全局管理员名称： </span><span class="sxs-lookup"><span data-stu-id="e89eb-150">Office 365 global administrator name:</span></span> ![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="e89eb-152">.onmicrosoft.com（在第 1 阶段的第 6 步中）</span><span class="sxs-lookup"><span data-stu-id="e89eb-152">.onmicrosoft.com (from step 6 of Phase 1)</span></span>
    
    <span data-ttu-id="e89eb-153">此外，还应将此帐户的密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="e89eb-153">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="e89eb-154">试用订阅组织名称：</span><span class="sxs-lookup"><span data-stu-id="e89eb-154">Your trial subscription organization name:</span></span> ![折线图](../media/Common-Images/TableLine.png) <span data-ttu-id="e89eb-156">（在第 1 阶段的第 4 步中）</span><span class="sxs-lookup"><span data-stu-id="e89eb-156">(from step 4 of Phase 1)</span></span>
    
- <span data-ttu-id="e89eb-157">要列出 User 2、User 3、User 4 和 User 5 的帐户，从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="e89eb-157">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="e89eb-158">在此记录帐户名称：</span><span class="sxs-lookup"><span data-stu-id="e89eb-158">Record the account names here:</span></span>
    
  - <span data-ttu-id="e89eb-159">用户 2 帐户名：user2@</span><span class="sxs-lookup"><span data-stu-id="e89eb-159">User 2 account name: user2@</span></span>![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="e89eb-161">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e89eb-161">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="e89eb-162">用户 3 帐户名：user3@</span><span class="sxs-lookup"><span data-stu-id="e89eb-162">User 3 account name: user3@</span></span>![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="e89eb-164">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e89eb-164">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="e89eb-165">用户 4 帐户名：user4@</span><span class="sxs-lookup"><span data-stu-id="e89eb-165">User 4 account name: user4@</span></span>![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="e89eb-167">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e89eb-167">.onmicrosoft.com</span></span>
    
  - <span data-ttu-id="e89eb-168">用户 5 帐户名：user5@</span><span class="sxs-lookup"><span data-stu-id="e89eb-168">User 5 account name: user5@</span></span>![折线图](../media/Common-Images/TableLine.png)<span data-ttu-id="e89eb-170">.onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="e89eb-170">.onmicrosoft.com</span></span>
    
    <span data-ttu-id="e89eb-171">此外，在安全位置记录这些帐户的公用密码。</span><span class="sxs-lookup"><span data-stu-id="e89eb-171">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-test-environment"></a><span data-ttu-id="e89eb-172">使用 Office 365 测试环境</span><span class="sxs-lookup"><span data-stu-id="e89eb-172">Using an Office 365 test environment</span></span>

<span data-ttu-id="e89eb-173">如果你只需要一个 Office 365 测试环境，则可以在此处停止。</span><span class="sxs-lookup"><span data-stu-id="e89eb-173">If all you need is an Office 365 test environment, you can stop here.</span></span> 

<span data-ttu-id="e89eb-174">有关同时适用于 Office 365 和 Microsoft 365 的其他测试实验室指南，请参阅 [Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="e89eb-174">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="e89eb-175">第 3 阶段：添加 Microsoft 365 E5 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="e89eb-175">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="e89eb-176">在该阶段中，可注册 Microsoft 365 E5 试用版订阅，并将其添加到 Office 365 E5 试用版订阅所在的组织中。</span><span class="sxs-lookup"><span data-stu-id="e89eb-176">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="e89eb-177">首先，请添加 Microsoft 365 E5 试用版订阅并向全局管理员帐户分配一个新的 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="e89eb-177">First, add the Microsoft 365 E5 trial subscription and assign the new Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="e89eb-178">通过 Internet 浏览器的专用实例，使用全局管理员帐户凭据登录 [https://admin.microsoft.com](https://admin.microsoft.com) 上的 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="e89eb-178">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="e89eb-179">在“**Microsoft 365 管理中心**”页面上的左侧导航栏中，单击“**计费 > 购买服务**”。</span><span class="sxs-lookup"><span data-stu-id="e89eb-179">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="e89eb-180">在“采购服务”\*\*\*\* 页面上，依次单击“Microsoft 365 E5”\*\*\*\* 和“获取免费试用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-180">On the **Purchase services** page, click **Microsoft 365 E5**, and then click **Get free trial**.</span></span>

4. <span data-ttu-id="e89eb-181">在“**Microsoft 365 E5 试用版**”页面上，选择接收短信或通话，输入你的电话号码，然后单击“**发短信给我**”或“**打电话给我**”。</span><span class="sxs-lookup"><span data-stu-id="e89eb-181">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span> <span data-ttu-id="e89eb-182">执行验证。</span><span class="sxs-lookup"><span data-stu-id="e89eb-182">Perform the verification.</span></span>

5. <span data-ttu-id="e89eb-183">在“确认订单”页上，单击“立即试用”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-183">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="e89eb-184">在“订单签收”页中，单击“继续”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-184">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="e89eb-185">在“Microsoft 365 管理中心”中，单击“用户”>“活动用户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-185">In the Microsoft 365 admin center, click **Users > Active users**.</span></span>

8. <span data-ttu-id="e89eb-186">在“活动用户”\*\*\*\* 中，单击“管理员帐户”。</span><span class="sxs-lookup"><span data-stu-id="e89eb-186">In **Active users**, click your administrator account.</span></span>

9. <span data-ttu-id="e89eb-187">单击“许可证和应用”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-187">Click **Licenses and apps**.</span></span>

10. <span data-ttu-id="e89eb-188">禁用 Office 365 企业版 E5 的许可证，并启用 Microsoft 365 E5 的许可证。</span><span class="sxs-lookup"><span data-stu-id="e89eb-188">Disable the license for Office 365 Enterprise E5 and enable the license for Microsoft 365 E5.</span></span>

11. <span data-ttu-id="e89eb-189">单击“保存更改”\*\*\*\*，然后关闭“用户帐户信息”窗格。</span><span class="sxs-lookup"><span data-stu-id="e89eb-189">Click **Save changes** and then close the user account information pane.</span></span>

<span data-ttu-id="e89eb-190">接下来，对其他所有帐户（用户 2、用户 3、用户 4 和用户 5）重复执行上面过程的第 8 步到第 11 步。</span><span class="sxs-lookup"><span data-stu-id="e89eb-190">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e89eb-191">Microsoft 365 E5 试用版订阅的有效期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="e89eb-191">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="e89eb-192">对于永久测试环境，将此试用版订阅转换为带少量许可证的付费订阅。</span><span class="sxs-lookup"><span data-stu-id="e89eb-192">For a permanent test environment, convert this trial subscription into a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="e89eb-193">测试环境现在包含：</span><span class="sxs-lookup"><span data-stu-id="e89eb-193">Your test environment now has:</span></span>
  
- <span data-ttu-id="e89eb-194">Microsoft 365 E5 试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="e89eb-194">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="e89eb-195">所有适当的用户帐户（无论是全局管理员帐户还是全部五个用户帐户）都可以使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="e89eb-195">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="e89eb-196">下面是所得到的配置，它添加了 Microsoft 365 E5，还同时包含了 Office 365 和企业安全性 + 管理 (EMS)。</span><span class="sxs-lookup"><span data-stu-id="e89eb-196">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Microsoft 365 企业版测试环境的第 3 阶段](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="e89eb-198">第 4 阶段：创建 Windows 10 企业版计算机</span><span class="sxs-lookup"><span data-stu-id="e89eb-198">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="e89eb-199">在这一阶段，将运行 Windows 10 企业版的独立计算机创建为物理计算机、虚拟机或 Azure 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="e89eb-199">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="e89eb-200">物理计算机</span><span class="sxs-lookup"><span data-stu-id="e89eb-200">Physical computer</span></span>

<span data-ttu-id="e89eb-p109">获取个人计算机并在其上安装 Windows 10 企业版。你可在[此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="e89eb-203">虚拟机</span><span class="sxs-lookup"><span data-stu-id="e89eb-203">Virtual machine</span></span>

<span data-ttu-id="e89eb-p110">使用你选择的虚拟机监控程序创建一个虚拟机并在其上安装 Windows 10 企业版。你可在[此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="e89eb-206">Azure 中的虚拟机</span><span class="sxs-lookup"><span data-stu-id="e89eb-206">Virtual machine in Azure</span></span>

<span data-ttu-id="e89eb-p111">要在 Microsoft Azure 中创建 Windows 10 虚拟机，***你必须拥有基于 Visual Studio 的订阅***，以便有权访问 Windows 10 企业版的映像。其他类型的 Azure 订阅（如试用版和付费订阅）均无权访问此映像。有关最新信息，请参阅[在 Azure 中使用 Windows 客户端实现开发/测试方案](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="e89eb-p112">下面的命令集使用最新版 Azure PowerShell。请参阅 [Azure PowerShell cmdlet 入门](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)。这些命令集构建了名为 WIN10 的 Windows 10 企业版虚拟机及其所需的全部基础架构，其中包括资源组、存储帐户和虚拟网络。如果你已熟悉 Azure 基础架构服务，请修改这些说明以适应当前部署的基础架构。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="e89eb-214">首先，启动 Microsoft PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="e89eb-214">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="e89eb-215">使用以下命令登录 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="e89eb-215">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="e89eb-216">使用以下命令获得订阅名称。</span><span class="sxs-lookup"><span data-stu-id="e89eb-216">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="e89eb-p113">设置 Azure 订阅。使用正确的名称替换引号内的所有内容（包括 \< 和 > 字符）。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="e89eb-p114">接下来，创建一个新的资源组。要确定一个唯一的资源组名称，请使用此命令列出你现有的资源组。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="e89eb-p115">使用这些命令创建新的资源组。使用正确的名称替换引号内的所有内容（包括 \< 和 > 字符）。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="e89eb-p116">接下来，使用这些命令创建新的虚拟网络和 WIN10 虚拟机。出现提示时，为 WIN10 提供本地管理员帐户的名称和密码，并将这些名称和密码存储在安全位置。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="e89eb-225">第 5 阶段：将 Windows 10 计算机加入到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="e89eb-225">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="e89eb-226">在创建具有 Windows 10 企业版的物理计算机或虚拟机之后，使用本地管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="e89eb-226">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="e89eb-227">对于 Azure 中的虚拟机，使用[这些说明](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)进行连接。</span><span class="sxs-lookup"><span data-stu-id="e89eb-227">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="e89eb-228">接下来，将 WIN10 计算机联接到 Microsoft 365 E5 订阅的 Azure AD 租户中。</span><span class="sxs-lookup"><span data-stu-id="e89eb-228">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="e89eb-229">在 WIN10 计算机的桌面上，依次单击“开始”>“设置”>“帐户”>“访问单位或学校”>“连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-229">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="e89eb-230">在“设置工作或学校帐户”\*\*\*\* 对话框中，单击“将此设备加入到 Azure Active Directory”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-230">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="e89eb-231">在**工作或学校帐户**中，键入 Microsoft 365 E5 订阅的全局管理员帐户名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e89eb-231">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="e89eb-232">在“输入密码”\*\*\*\* 中，键入全局管理员帐户的密码，然后单击“登录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-232">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="e89eb-233">当提示你确定这是你的组织时，单击“加入”\*\*\*\*，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-233">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="e89eb-234">关闭“设置”窗口。</span><span class="sxs-lookup"><span data-stu-id="e89eb-234">Close the settings window.</span></span>
    
<span data-ttu-id="e89eb-235">接下来，在 WIN10 计算机上安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="e89eb-235">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="e89eb-236">打开 Microsoft Edge 浏览器，使用全局管理员帐户凭据登录到 Office 门户。</span><span class="sxs-lookup"><span data-stu-id="e89eb-236">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="e89eb-237">如需帮助，请参阅[如何登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="e89eb-237">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="e89eb-238">在“**Microsoft Office 家庭版**”选项卡上，单击“**安装 Office**”。</span><span class="sxs-lookup"><span data-stu-id="e89eb-238">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="e89eb-239">出现应执行的操作提示时，单击“运行”\*\*\*\*，然后针对“用户帐户控制”单击“是”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e89eb-239">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="e89eb-p118">等待 Office 完成安装。当看到“**你已设置完毕!**”时，单击“**关闭**”两次。</span><span class="sxs-lookup"><span data-stu-id="e89eb-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="e89eb-242">下面是生成的环境。</span><span class="sxs-lookup"><span data-stu-id="e89eb-242">Here is your resulting environment.</span></span>

![Microsoft 365 企业版测试环境的第 5 阶段](../media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="e89eb-244">这包括符合以下条件的 WIN10 计算机：</span><span class="sxs-lookup"><span data-stu-id="e89eb-244">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="e89eb-245">已联接 Microsoft 365 E5 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="e89eb-245">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="e89eb-246">已注册为 Microsoft Intune (EMS) 中的 Azure AD 设备。</span><span class="sxs-lookup"><span data-stu-id="e89eb-246">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="e89eb-247">已安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="e89eb-247">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="e89eb-248">现在可以试验 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="e89eb-248">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="e89eb-249">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e89eb-249">Next steps</span></span>

<span data-ttu-id="e89eb-250">浏览下面这些附加的一系列测试实验室指南：</span><span class="sxs-lookup"><span data-stu-id="e89eb-250">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="e89eb-251">标识</span><span class="sxs-lookup"><span data-stu-id="e89eb-251">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="e89eb-252">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="e89eb-252">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="e89eb-253">信息保护</span><span class="sxs-lookup"><span data-stu-id="e89eb-253">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="e89eb-254">另请参阅</span><span class="sxs-lookup"><span data-stu-id="e89eb-254">See also</span></span>

[<span data-ttu-id="e89eb-255">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="e89eb-255">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="e89eb-256">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="e89eb-256">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="e89eb-257">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="e89eb-257">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
