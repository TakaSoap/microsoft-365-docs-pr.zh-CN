---
title: 轻型基本配置
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
ms.openlocfilehash: fce612000fac79fe9552fa9882d6c48fdacda1c2
ms.sourcegitcommit: ea48c86c727dcd9d4b3b970b14a4260337f158f9
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2019
ms.locfileid: "38694119"
---
# <a name="the-lightweight-base-configuration"></a><span data-ttu-id="833d8-103">轻型基本配置</span><span class="sxs-lookup"><span data-stu-id="833d8-103">The lightweight base configuration</span></span>

<span data-ttu-id="833d8-104">*本测试实验室指南可用于 Microsoft 365 企业版和 Office 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="833d8-104">*This Test Lab Guide can be used for both Microsoft 365 Enterprise and Office 365 Enterprise test environments.*</span></span>

<span data-ttu-id="833d8-105">本文分步说明了如何使用 Microsoft 365 E5 订阅和运行 Windows 10 企业版的计算机创建简化的环境。</span><span class="sxs-lookup"><span data-stu-id="833d8-105">This article provides you with step-by-step instructions to create a simplified environment with a Microsoft 365 E5 subscription and a computer running Windows 10 Enterprise.</span></span> 

![轻量级 Microsoft 365 企业版测试环境](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="833d8-107">使用生成的环境来测试 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的特性和功能。</span><span class="sxs-lookup"><span data-stu-id="833d8-107">Use the resulting environment to test the features and functionality of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>

![适用于 Microsoft 云的测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)
  
> [!TIP]
> <span data-ttu-id="833d8-109">单击[此处](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="833d8-109">Click [here](media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>

## <a name="phase-1-create-your-office-365-e5-subscription"></a><span data-ttu-id="833d8-110">第 1 阶段：创建 Office 365 E5 订阅</span><span class="sxs-lookup"><span data-stu-id="833d8-110">Phase 1: Create your Office 365 E5 subscription</span></span>

<span data-ttu-id="833d8-111">我们首先使用 Office 365 E5 试用版订阅，然后向其添加 Microsoft 365 E5 订阅。</span><span class="sxs-lookup"><span data-stu-id="833d8-111">We start with an Office 365 E5 trial subscription and then add the Microsoft 365 E5 subscription to it.</span></span>

<span data-ttu-id="833d8-112">要启动 Office 365 E5 试用订阅，你首先需要一个虚构公司名称和一个新的 Microsoft 帐户。</span><span class="sxs-lookup"><span data-stu-id="833d8-112">To start your Office 365 E5 trial subscription, you first need a fictitious company name and a new Microsoft account.</span></span>
  
1. <span data-ttu-id="833d8-p101">我们建议你将公司名称 Contoso 的变体用作你的公司名称，它是 Microsoft 示例内容中使用的虚构公司，但这并不是必需的。在此记录虚构的公司名称：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="833d8-p101">We recommend that you use a variant of the company name Contoso for your company name, which is a fictitious company used in Microsoft sample content, but it isn't required. Record your fictitious company name here: ![](./media/Common-Images/TableLine.png)</span></span>
    
2. <span data-ttu-id="833d8-p102">要注册新的 Microsoft 帐户，请转到 [https://outlook.com](https://outlook.com)，然后使用新的电子邮件帐户和地址创建一个帐户。此帐户将用于注册 Office 365。</span><span class="sxs-lookup"><span data-stu-id="833d8-p102">To sign up for a new Microsoft account, go to [https://outlook.com](https://outlook.com) and create an account with a new email account and address. You will use this account to sign up for Office 365.</span></span>
    
  - <span data-ttu-id="833d8-117">在此记录新帐户的名字和姓氏：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="833d8-117">Record the first and last name of your new account here: ![](./media/Common-Images/TableLine.png)</span></span>
    
  - <span data-ttu-id="833d8-118">在此记录新的电子邮件帐户地址：![](./media/Common-Images/TableLine.png)@outlook.com</span><span class="sxs-lookup"><span data-stu-id="833d8-118">Record the new email account address here: ![](./media/Common-Images/TableLine.png)@outlook.com</span></span>
    
### <a name="sign-up-for-an-office-365-e5-trial-subscription"></a><span data-ttu-id="833d8-119">注册 Office 365 E5 试用订阅</span><span class="sxs-lookup"><span data-stu-id="833d8-119">Sign up for an Office 365 E5 trial subscription</span></span>

1. <span data-ttu-id="833d8-120">在计算机上打开 Internet 浏览器，转到 [https://aka.ms/e5trial](https://aka.ms/e5trial)。</span><span class="sxs-lookup"><span data-stu-id="833d8-120">Open the Internet browser on your computer and go to [https://aka.ms/e5trial](https://aka.ms/e5trial).</span></span>
    
2. <span data-ttu-id="833d8-121">在“欢迎，很高兴认识你”\*\*\*\* 页上，请指定：</span><span class="sxs-lookup"><span data-stu-id="833d8-121">On the **Welcome, let's get to know you** page, specify:</span></span>
    
  - <span data-ttu-id="833d8-122">你的实际位置</span><span class="sxs-lookup"><span data-stu-id="833d8-122">Your physical location</span></span>
    
  - <span data-ttu-id="833d8-123">你新的 Microsoft 帐户的名字和姓氏</span><span class="sxs-lookup"><span data-stu-id="833d8-123">The first and last name of your new Microsoft account</span></span>
    
  - <span data-ttu-id="833d8-124">你新的电子邮件帐户地址</span><span class="sxs-lookup"><span data-stu-id="833d8-124">Your new email account address</span></span>
    
  - <span data-ttu-id="833d8-125">业务电话号码</span><span class="sxs-lookup"><span data-stu-id="833d8-125">A business phone number</span></span>
    
  - <span data-ttu-id="833d8-126">你虚构的公司名称</span><span class="sxs-lookup"><span data-stu-id="833d8-126">Your fictional company name</span></span>
    
  - <span data-ttu-id="833d8-127">规模达 250-999 人的组织</span><span class="sxs-lookup"><span data-stu-id="833d8-127">An organization size of 250-999 people</span></span>
    
3. <span data-ttu-id="833d8-128">单击“只需再执行一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-128">Click **Just one more step**.</span></span>
    
4. <span data-ttu-id="833d8-129">在“**创建你的用户 ID**”页上，基于你新的电子邮件地址、@ 符号之后你的虚构公司（删除名称中的所有空格）键入用户名，然后为此新的 Office 365 帐户键入密码（两次）。</span><span class="sxs-lookup"><span data-stu-id="833d8-129">On the **Create your user ID** page, type a user name based on your new email address, your fictional company after the @ sign (remove all spaces in the name), then a password (twice) for this new Office 365 account.</span></span>
    
    <span data-ttu-id="833d8-130">将你键入的密码记录在安全的位置。</span><span class="sxs-lookup"><span data-stu-id="833d8-130">Record the password that you typed in a secure location.</span></span>
    
    <span data-ttu-id="833d8-131">在此记录你的虚构公司名称，将其称为“组织名称”\*\*\*\*：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="833d8-131">Record your fictional company name, to be referred to as the **organization name**, here: ![](./media/Common-Images/TableLine.png)</span></span>
    
5. <span data-ttu-id="833d8-132">单击“创建我的帐户”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-132">Click **Create my account**.</span></span>
    
6. <span data-ttu-id="833d8-p103">在“证明你不是机器人”\*\*\*\* 页上，键入可发短信的手机号码，然后单击“给我发短信”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-p103">On the **Prove. You're. Not. A. Robot.** page, type the phone number of your text-capable phone, and then click **Text me**.</span></span>
    
7. <span data-ttu-id="833d8-135">键入短信中收到的验证代码，然后单击“下一步”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-135">Type the verification code from the received text message, and then click **Next**.</span></span>
    
8. <span data-ttu-id="833d8-136">在此记录登录页面 URL（选择并复制）：![](./media/Common-Images/TableLine.png)</span><span class="sxs-lookup"><span data-stu-id="833d8-136">Record the sign-in page URL here (select and copy): ![](./media/Common-Images/TableLine.png)</span></span>
    
9. <span data-ttu-id="833d8-137">在此记录用户 ID（选择并复制）：![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="833d8-137">Record the user ID here (select and copy): ![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="833d8-138">此值将被称为“Office 365 全局管理员名称”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-138">This value will be referred to as the **Office 365 global administrator name**.</span></span>
    
10. <span data-ttu-id="833d8-139">看到“你已准备就绪”\*\*\*\* 时，请单击它。</span><span class="sxs-lookup"><span data-stu-id="833d8-139">When you see **You're ready to go**, click it.</span></span>
    
11. <span data-ttu-id="833d8-140">在下一页，等到 Office 365 完成设置并且显示所有标题。</span><span class="sxs-lookup"><span data-stu-id="833d8-140">On the next page, wait until Office 365 completes setting up and all the tiles are available.</span></span>
    
<span data-ttu-id="833d8-141">你应可看到 Office 365 门户主页，可从该页访问 Office 服务和 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="833d8-141">You should see main Office 365 portal page from which you can access Office services and the Microsoft 365 admin center.</span></span>
  
<span data-ttu-id="833d8-142">我们为你创建了 Office 365 的试用版订阅，以便你的开发/测试环境具有与你当前拥有的任何付费版订阅分开的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="833d8-142">We have you create a trial subscription of Office 365 so that your dev/test environment has a separate Azure AD tenant from any paid subscriptions you currently have.</span></span> <span data-ttu-id="833d8-143">这样分开意味着你可在测试租户中添加和删除用户和组，而不影响生产订阅。</span><span class="sxs-lookup"><span data-stu-id="833d8-143">This separation means you can add and remove users and groups in the test tenant without affecting your production subscriptions.</span></span>
    
## <a name="phase-2-configure-your-office-365-trial-subscription"></a><span data-ttu-id="833d8-144">第 2 阶段：配置 Office 365 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="833d8-144">Phase 2: Configure your Office 365 trial subscription</span></span>

<span data-ttu-id="833d8-145">在这个阶段，配置包含其他用户的 Office 365 订阅，并为这些用户分配 Office 365 E5 许可证。</span><span class="sxs-lookup"><span data-stu-id="833d8-145">In this phase, you configure your Office 365 subscription with additional users and assign them Office 365 E5 licenses.</span></span>
  
<span data-ttu-id="833d8-146">按照[连接到 Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) 中的说明，使用计算机中的 Azure Active Directory PowerShell for Graph 模块连接到 Office 365 订阅。</span><span class="sxs-lookup"><span data-stu-id="833d8-146">Use the instructions in [Connect to Office 365 PowerShell](https://docs.microsoft.com/office365/enterprise/powershell/connect-to-office-365-powershell#connect-with-the-azure-active-directory-powershell-for-graph-module) to connect to your Office 365 subscription with the Azure Active Directory PowerShell for Graph module from your computer.</span></span>
    
<span data-ttu-id="833d8-147">在“Windows PowerShell 凭据请求”对话框中，键入 Office 365 全局管理员名称（示例：jdoe@contosotoycompany.onmicrosoft.com）和密码。</span><span class="sxs-lookup"><span data-stu-id="833d8-147">In the Windows PowerShell Credential Request dialog box, type the Office 365 global administrator name (example: jdoe@contosotoycompany.onmicrosoft.com) and password.</span></span>
  
<span data-ttu-id="833d8-148">填写组织名称（示例：contosotoycompany）、你所在位置的两位字符的国家/地区代码以及通用帐户密码，然后 PowerShell 提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="833d8-148">Fill in your organization name (example: contosotoycompany), the two-character country code for your location, a common account password, and then run the following commands from the PowerShell prompt:</span></span>

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
> <span data-ttu-id="833d8-149">此处使用公用密码旨在自动配置开发/测试环境，简化配置过程。</span><span class="sxs-lookup"><span data-stu-id="833d8-149">The use of a common password here is for automation and ease of configuration for a dev/test environment.</span></span> <span data-ttu-id="833d8-150">显然，对于生产订阅，这是非常不鼓励的。</span><span class="sxs-lookup"><span data-stu-id="833d8-150">Obviously, this is highly discouraged for production subscriptions.</span></span> 

### <a name="record-key-information-for-future-reference"></a><span data-ttu-id="833d8-151">记录关键信息供将来参考</span><span class="sxs-lookup"><span data-stu-id="833d8-151">Record key information for future reference</span></span>

<span data-ttu-id="833d8-152">不妨打印这篇文章，以便记录在 30 天的 Office 365 试用版订阅期内需要对此环境使用的特定信息。</span><span class="sxs-lookup"><span data-stu-id="833d8-152">You might want to print this article to record the specific information that you will need for this environment over the 30 days of the Office 365 trial subscription.</span></span> <span data-ttu-id="833d8-153">可以轻松地将该订阅的试用期再延长 30 天。</span><span class="sxs-lookup"><span data-stu-id="833d8-153">You can easily extend the trail subscription for another 30 days.</span></span> <span data-ttu-id="833d8-154">对于永久性开发/测试环境，请创建一个包含单独 Azure AD 租户和少量许可证的新付费订阅。</span><span class="sxs-lookup"><span data-stu-id="833d8-154">For a permanent dev/test environment, create a new paid subscription with a separate Azure AD tenant and a small number of licenses.</span></span>

<span data-ttu-id="833d8-155">请记录以下值：</span><span class="sxs-lookup"><span data-stu-id="833d8-155">Record these values:</span></span>
  
- <span data-ttu-id="833d8-156">Office 365 全局管理员名称：![](./media/Common-Images/TableLine.png).onmicrosoft.com（在第 2 阶段的第 9 步中）</span><span class="sxs-lookup"><span data-stu-id="833d8-156">Office 365 global administrator name: ![](./media/Common-Images/TableLine.png).onmicrosoft.com (from step 9 of Phase 2)</span></span>
    
    <span data-ttu-id="833d8-157">此外，还应将此帐户的密码记录在安全位置。</span><span class="sxs-lookup"><span data-stu-id="833d8-157">Also record the password for this account in a secure location.</span></span>
    
- <span data-ttu-id="833d8-158">试用订阅组织名称：![](./media/Common-Images/TableLine.png)（在第 2 阶段的第 4 步中）</span><span class="sxs-lookup"><span data-stu-id="833d8-158">Your trial subscription organization name: ![](./media/Common-Images/TableLine.png) (from step 4 of Phase 2)</span></span>
    
- <span data-ttu-id="833d8-159">要列出 User 2、User 3、User 4 和 User 5 的帐户，从用于 Windows PowerShell 的 Windows Azure Active Directory 模块提示符中运行以下命令：</span><span class="sxs-lookup"><span data-stu-id="833d8-159">To list the accounts for User 2, User 3, User 4, and User 5, run the following command from the Windows Azure Active Directory Module for Windows PowerShell prompt:</span></span>
    
  ```powershell
  Get-AzureADUser | Sort UserPrincipalName | Select UserPrincipalName
  ```

    <span data-ttu-id="833d8-160">在此记录帐户名称：</span><span class="sxs-lookup"><span data-stu-id="833d8-160">Record the account names here:</span></span>
    
  - <span data-ttu-id="833d8-161">User 2 的帐户名称：user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="833d8-161">User 2 account name: user2@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="833d8-162">User 3 的帐户名称：user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="833d8-162">User 3 account name: user3@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="833d8-163">User 4 的帐户名称：user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="833d8-163">User 4 account name: user4@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
  - <span data-ttu-id="833d8-164">User 5 的帐户名称：user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span><span class="sxs-lookup"><span data-stu-id="833d8-164">User 5 account name: user5@![](./media/Common-Images/TableLine.png).onmicrosoft.com</span></span>
    
    <span data-ttu-id="833d8-165">此外，在安全位置记录这些帐户的公用密码。</span><span class="sxs-lookup"><span data-stu-id="833d8-165">Also record the common password for these accounts in a secure location.</span></span>
   

### <a name="using-an-office-365-devtest-environment"></a><span data-ttu-id="833d8-166">使用 Office 365 开发/测试环境</span><span class="sxs-lookup"><span data-stu-id="833d8-166">Using an Office 365 dev/test environment</span></span>

<span data-ttu-id="833d8-167">如果你只需要一个 Office 365 开发/测试环境，则可以在此处停止。</span><span class="sxs-lookup"><span data-stu-id="833d8-167">If all you need is an Office 365 dev/test environment, you can stop here.</span></span> 

<span data-ttu-id="833d8-168">有关同时适用于 Office 365 和 Microsoft 365 的其他测试实验室指南，请参阅 [Microsoft 365 企业版测试实验室指南](m365-enterprise-test-lab-guides.md)。</span><span class="sxs-lookup"><span data-stu-id="833d8-168">See [Microsoft 365 Enterprise Test Lab Guides](m365-enterprise-test-lab-guides.md) for additional Test Lab Guides that apply to both Office 365 and Microsoft 365.</span></span>
  
## <a name="phase-3-add-a-microsoft-365-e5-trial-subscription"></a><span data-ttu-id="833d8-169">第 3 阶段：添加 Microsoft 365 E5 试用版订阅</span><span class="sxs-lookup"><span data-stu-id="833d8-169">Phase 3: Add a Microsoft 365 E5 trial subscription</span></span>

<span data-ttu-id="833d8-170">在该阶段中，可注册 Microsoft 365 E5 试用版订阅，并将其添加到 Office 365 E5 试用版订阅所在的组织中。</span><span class="sxs-lookup"><span data-stu-id="833d8-170">In this phase, you sign up for the Microsoft 365 E5 trial subscription and add it to the same organization as your Office 365 E5 trial subscription.</span></span>
  
<span data-ttu-id="833d8-171">首先，请添加 Microsoft 365 E5 试用版订阅并向全局管理员帐户分配一个 Microsoft 365 许可证。</span><span class="sxs-lookup"><span data-stu-id="833d8-171">First, add the Microsoft 365 E5 trial subscription and assign a Microsoft 365 license to your global administrator account.</span></span>
  
1. <span data-ttu-id="833d8-172">通过 Internet 浏览器的专用实例，使用全局管理员帐户凭据登录 [https://admin.microsoft.com](https://admin.microsoft.com) 上的 Microsoft 365 管理中心。</span><span class="sxs-lookup"><span data-stu-id="833d8-172">With a private instance of an Internet browser, sign in to the Microsoft 365 admin center at [https://admin.microsoft.com](https://admin.microsoft.com) with your global administrator account credentials.</span></span>
    
2. <span data-ttu-id="833d8-173">在“**Microsoft 365 管理中心**”页面上的左侧导航栏中，单击“**计费 > 购买服务**”。</span><span class="sxs-lookup"><span data-stu-id="833d8-173">On the **Microsoft 365 admin center** page, in the left navigation, click **Billing > Purchase services**.</span></span>
    
3. <span data-ttu-id="833d8-174">在“**购买服务**”页面上，找到“**Microsoft 365 E5**”项目。</span><span class="sxs-lookup"><span data-stu-id="833d8-174">On the **Purchase services** page, find the **Microsoft 365 E5** item.</span></span> <span data-ttu-id="833d8-175">将鼠标指针悬停在该项目上方并单击“**开始免费试用**”。</span><span class="sxs-lookup"><span data-stu-id="833d8-175">Hover your mouse pointer over it and click **Start free trial**.</span></span>

4. <span data-ttu-id="833d8-176">在“**Microsoft 365 E5 试用版**”页面上，选择接收短信或通话，输入你的电话号码，然后单击“**发短信给我**”或“**打电话给我**”。</span><span class="sxs-lookup"><span data-stu-id="833d8-176">On the **Microsoft 365 E5 Trial** page, choose to receive a text or a call, enter your phone number, then click **Text me** or **Call me**.</span></span>

5. <span data-ttu-id="833d8-177">在“确认订单”页上，单击“立即试用”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-177">On the **Confirm your order** page, click **Try now**.</span></span>

6. <span data-ttu-id="833d8-178">在“订单签收”页中，单击“继续”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-178">On the **Order receipt** page, click **Continue**.</span></span>

7. <span data-ttu-id="833d8-179">在 Microsoft 365 管理中心中，单击“**活动用户**”，然后单击管理员帐户。</span><span class="sxs-lookup"><span data-stu-id="833d8-179">In the Microsoft 365 admin center, click **Active users**, and then your administrator account.</span></span>

8. <span data-ttu-id="833d8-180">对于**产品许可证**，请单击“**编辑**”。</span><span class="sxs-lookup"><span data-stu-id="833d8-180">Click **Edit** for **Product licenses**.</span></span>

9. <span data-ttu-id="833d8-181">关闭 Office 365 企业版 E5 的许可证，并打开 Microsoft 365 E5 的许可证。</span><span class="sxs-lookup"><span data-stu-id="833d8-181">Turn off the license for Office 365 Enterprise E5 and turn on the license for Microsoft 365 E5.</span></span>

10. <span data-ttu-id="833d8-182">单击“**保存 > 关闭 > 关闭**”。</span><span class="sxs-lookup"><span data-stu-id="833d8-182">Click **Save > Close > Close**.</span></span>

<span data-ttu-id="833d8-183">接下来，对其他所有帐户（用户 2、用户 3、用户 4 和用户 5）重复执行上面过程的第 8 步到第 11 步。</span><span class="sxs-lookup"><span data-stu-id="833d8-183">Next, repeat steps 8 through 11 of the previous procedure for all of your other accounts (User 2, User 3, User 4, and User 5).</span></span>
  
> [!NOTE]
> <span data-ttu-id="833d8-184">Microsoft 365 E5 试用版订阅的有效期为 30 天。</span><span class="sxs-lookup"><span data-stu-id="833d8-184">The Microsoft 365 E5 trial subscription is 30 days.</span></span> <span data-ttu-id="833d8-185">对于永久性测试环境，请将此试用版订阅转换为包含少量许可证的付费版订阅。</span><span class="sxs-lookup"><span data-stu-id="833d8-185">For a permanent test environment, convert this trial subscription to a paid subscription with a small number of licenses.</span></span> 
  
<span data-ttu-id="833d8-186">测试环境现在包含：</span><span class="sxs-lookup"><span data-stu-id="833d8-186">Your test environment now has:</span></span>
  
- <span data-ttu-id="833d8-187">Microsoft 365 E5 试用版订阅。</span><span class="sxs-lookup"><span data-stu-id="833d8-187">A Microsoft 365 E5 trial subscription.</span></span>
- <span data-ttu-id="833d8-188">所有适当的用户帐户（无论是全局管理员帐户还是全部五个用户帐户）都可以使用 Microsoft 365 E5。</span><span class="sxs-lookup"><span data-stu-id="833d8-188">All your appropriate user accounts (either just the global administrator or all five user accounts) are enabled to use Microsoft 365 E5.</span></span>
    
<span data-ttu-id="833d8-189">下面是所得到的配置，它添加了 Microsoft 365 E5，还同时包含了 Office 365 和企业安全性 + 管理 (EMS)。</span><span class="sxs-lookup"><span data-stu-id="833d8-189">Here is your resulting configuration, which adds Microsoft 365 E5, which includes both Office 365 and Enterprise Security + Management (EMS).</span></span>
  
![Microsoft 365 企业版测试环境的第 2 阶段](media/lightweight-base-configuration-microsoft-365-enterprise/Phase2.png)
  
## <a name="phase-4-create-a-windows-10-enterprise-computer"></a><span data-ttu-id="833d8-191">第 4 阶段：创建 Windows 10 企业版计算机</span><span class="sxs-lookup"><span data-stu-id="833d8-191">Phase 4: Create a Windows 10 Enterprise computer</span></span>

<span data-ttu-id="833d8-192">在这一阶段，将运行 Windows 10 企业版的独立计算机创建为物理计算机、虚拟机或 Azure 虚拟机。</span><span class="sxs-lookup"><span data-stu-id="833d8-192">In this phase, you create a standalone computer running Windows 10 Enterprise as either a physical computer, a virtual machine, or an Azure virtual machine.</span></span>
  
### <a name="physical-computer"></a><span data-ttu-id="833d8-193">物理计算机</span><span class="sxs-lookup"><span data-stu-id="833d8-193">Physical computer</span></span>

<span data-ttu-id="833d8-p109">获取个人计算机并在其上安装 Windows 10 企业版。你可在[此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用。</span><span class="sxs-lookup"><span data-stu-id="833d8-p109">Obtain a personal computer and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine"></a><span data-ttu-id="833d8-196">虚拟机</span><span class="sxs-lookup"><span data-stu-id="833d8-196">Virtual machine</span></span>

<span data-ttu-id="833d8-p110">使用你选择的虚拟机监控程序创建一个虚拟机并在其上安装 Windows 10 企业版。你可在[此处](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise)下载 Windows 10 企业版试用。</span><span class="sxs-lookup"><span data-stu-id="833d8-p110">Create a virtual machine using the hypervisor of your choice and install Windows 10 Enterprise on it. You can download the Windows 10 Enterprise trial [here](https://www.microsoft.com/evalcenter/evaluate-windows-10-enterprise).</span></span>
  
### <a name="virtual-machine-in-azure"></a><span data-ttu-id="833d8-199">Azure 中的虚拟机</span><span class="sxs-lookup"><span data-stu-id="833d8-199">Virtual machine in Azure</span></span>

<span data-ttu-id="833d8-p111">要在 Microsoft Azure 中创建 Windows 10 虚拟机，***你必须拥有基于 Visual Studio 的订阅***，以便有权访问 Windows 10 企业版的映像。其他类型的 Azure 订阅（如试用版和付费订阅）均无权访问此映像。有关最新信息，请参阅[在 Azure 中使用 Windows 客户端实现开发/测试方案](https://docs.microsoft.com/azure/virtual-machines/windows/client-images)。</span><span class="sxs-lookup"><span data-stu-id="833d8-p111">To create a Windows 10 virtual machine in Microsoft Azure, ***you must have a Visual Studio-based subscription***, which has access to the image for Windows 10 Enterprise. Other types of Azure subscriptions, such as trial and paid subscriptions, do not have access to this image. For the latest information, see [Use Windows client in Azure for dev/test scenarios](https://docs.microsoft.com/azure/virtual-machines/windows/client-images).</span></span>
  
> [!NOTE]
> <span data-ttu-id="833d8-p112">下面的命令集使用最新版 Azure PowerShell。请参阅 [Azure PowerShell cmdlet 入门](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/)。这些命令集构建了名为 WIN10 的 Windows 10 企业版虚拟机及其所需的全部基础架构，其中包括资源组、存储帐户和虚拟网络。如果你已熟悉 Azure 基础架构服务，请修改这些说明以适应当前部署的基础架构。</span><span class="sxs-lookup"><span data-stu-id="833d8-p112">The following command sets use the latest version of Azure PowerShell. See [Get started with Azure PowerShell cmdlets](https://docs.microsoft.com/powershell/azureps-cmdlets-docs/). These command sets build a Windows 10 Enterprise virtual machine named WIN10 and all of its required infrastructure, including a resource group, a storage account, and a virtual network. If you are already familiar with Azure infrastructure services, please adapt these instructions to suit your currently deployed infrastructure.</span></span> 
  
<span data-ttu-id="833d8-207">首先，启动 Microsoft PowerShell 提示符。</span><span class="sxs-lookup"><span data-stu-id="833d8-207">First, start a Microsoft PowerShell prompt.</span></span>
  
<span data-ttu-id="833d8-208">使用以下命令登录 Azure 帐户。</span><span class="sxs-lookup"><span data-stu-id="833d8-208">Sign in to your Azure account with the following command.</span></span>
  
```powershell
Connect-AzAccount
```

<span data-ttu-id="833d8-209">使用以下命令获得订阅名称。</span><span class="sxs-lookup"><span data-stu-id="833d8-209">Get your subscription name using the following command.</span></span>
  
```powershell
Get-AzSubscription | Sort Name | Select Name
```

<span data-ttu-id="833d8-p113">设置 Azure 订阅。使用正确的名称替换引号内的所有内容（包括 \< 和 > 字符）。</span><span class="sxs-lookup"><span data-stu-id="833d8-p113">Set your Azure subscription. Replace everything within the quotes, including the \< and > characters, with the correct name.</span></span>
  
```powershell
$subscr="<subscription name>"
Get-AzSubscription -SubscriptionName $subscr | Select-AzSubscription
```

<span data-ttu-id="833d8-p114">接下来，创建一个新的资源组。要确定一个唯一的资源组名称，请使用此命令列出你现有的资源组。</span><span class="sxs-lookup"><span data-stu-id="833d8-p114">Next, create a new resource group. To determine a unique resource group name, use this command to list your existing resource groups.</span></span>
  
```powershell
Get-AzResourceGroup | Sort ResourceGroupName | Select ResourceGroupName
```

<span data-ttu-id="833d8-p115">使用这些命令创建新的资源组。使用正确的名称替换引号内的所有内容（包括 \< 和 > 字符）。</span><span class="sxs-lookup"><span data-stu-id="833d8-p115">Create your new resource group with these commands. Replace everything within the quotes, including the \< and > characters, with the correct names.</span></span>
  
```powershell
$rgName="<resource group name>"
$locName="<location name, such as West US>"
New-AzResourceGroup -Name $rgName -Location $locName
```

<span data-ttu-id="833d8-p116">接下来，使用这些命令创建新的虚拟网络和 WIN10 虚拟机。出现提示时，为 WIN10 提供本地管理员帐户的名称和密码，并将这些名称和密码存储在安全位置。</span><span class="sxs-lookup"><span data-stu-id="833d8-p116">Next, you create a new virtual network and the WIN10 virtual machine with these commands. When prompted, provide the name and password of the local administrator account for WIN10 and store these in a secure location.</span></span>
  
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

## <a name="phase-5-join-your-windows-10-computer-to-azure-ad"></a><span data-ttu-id="833d8-218">第 5 阶段：将 Windows 10 计算机加入到 Azure AD</span><span class="sxs-lookup"><span data-stu-id="833d8-218">Phase 5: Join your Windows 10 computer to Azure AD</span></span>

<span data-ttu-id="833d8-219">在创建具有 Windows 10 企业版的物理计算机或虚拟机之后，使用本地管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="833d8-219">After the physical or virtual machine with Windows 10 Enterprise is created, sign in with a local administrator account.</span></span>
  
> [!NOTE]
> <span data-ttu-id="833d8-220">对于 Azure 中的虚拟机，使用[这些说明](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon)进行连接。</span><span class="sxs-lookup"><span data-stu-id="833d8-220">For a virtual machine in Azure, connect to it using [these instructions](https://docs.microsoft.com/azure/virtual-machines/windows/connect-logon).</span></span>
  
<span data-ttu-id="833d8-221">接下来，将 WIN10 计算机联接到 Microsoft 365 E5 订阅的 Azure AD 租户中。</span><span class="sxs-lookup"><span data-stu-id="833d8-221">Next, join the WIN10 computer to the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
  
1. <span data-ttu-id="833d8-222">在 WIN10 计算机的桌面上，依次单击“开始”>“设置”>“帐户”>“访问单位或学校”>“连接”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-222">At the desktop of the WIN10 computer, click **Start > Settings > Accounts > Access work or school > Connect**.</span></span>
    
2. <span data-ttu-id="833d8-223">在“设置工作或学校帐户”\*\*\*\* 对话框中，单击“将此设备加入到 Azure Active Directory”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-223">In the **Set up a work or school account** dialog box, click **Join this device to Azure Active Directory**.</span></span>
    
3. <span data-ttu-id="833d8-224">在**工作或学校帐户**中，键入 Microsoft 365 E5 订阅的全局管理员帐户名称，然后单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="833d8-224">In **Work or school account**, type the global administrator account name of your Microsoft 365 E5 subscription, and then click **Next**.</span></span>
    
4. <span data-ttu-id="833d8-225">在“输入密码”\*\*\*\* 中，键入全局管理员帐户的密码，然后单击“登录”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-225">In **Enter password**, type the password for your global administrator account, and then click **Sign in**.</span></span>
    
5. <span data-ttu-id="833d8-226">当提示你确定这是你的组织时，单击“加入”\*\*\*\*，然后单击“完成”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-226">When prompted to make sure this is your organization, click **Join**, and then click **Done**.</span></span>
    
6. <span data-ttu-id="833d8-227">关闭“设置”窗口。</span><span class="sxs-lookup"><span data-stu-id="833d8-227">Close the settings window.</span></span>
    
<span data-ttu-id="833d8-228">接下来，在 WIN10 计算机上安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="833d8-228">Next, install Office 365 ProPlus on the WIN10 computer.</span></span>
  
1. <span data-ttu-id="833d8-229">打开 Microsoft Edge 浏览器，使用全局管理员帐户凭据登录到 Office 门户。</span><span class="sxs-lookup"><span data-stu-id="833d8-229">Open the Microsoft Edge browser and sign in to the Office portal with your global administrator account credentials.</span></span> <span data-ttu-id="833d8-230">如需帮助，请参阅[如何登录到 Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4)。</span><span class="sxs-lookup"><span data-stu-id="833d8-230">For help, see [Where to sign in to Office 365](https://support.office.com/Article/Where-to-sign-in-to-Office-365-e9eb7d51-5430-4929-91ab-6157c5a050b4).</span></span>
    
2. <span data-ttu-id="833d8-231">在“**Microsoft Office 家庭版**”选项卡上，单击“**安装 Office**”。</span><span class="sxs-lookup"><span data-stu-id="833d8-231">On the **Microsoft Office Home** tab, click **Install Office**.</span></span>
    
3. <span data-ttu-id="833d8-232">出现应执行的操作提示时，单击“运行”\*\*\*\*，然后针对“用户帐户控制”单击“是”\*\*\*\*\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="833d8-232">When prompted with what to do, click **Run**, and then click **Yes** for **User Account Control**.</span></span>
    
4. <span data-ttu-id="833d8-p118">等待 Office 完成安装。当看到“**你已设置完毕!**”时，单击“**关闭**”两次。</span><span class="sxs-lookup"><span data-stu-id="833d8-p118">Wait for Office to complete its installation. When you see **You're all set!**, click **Close** twice.</span></span>
    
<span data-ttu-id="833d8-235">下面是生成的环境。</span><span class="sxs-lookup"><span data-stu-id="833d8-235">Here is your resulting environment.</span></span>

![Microsoft 365 企业版测试环境的第 5 阶段](media/lightweight-base-configuration-microsoft-365-enterprise/Phase4.png)

<span data-ttu-id="833d8-237">这包括符合以下条件的 WIN10 计算机：</span><span class="sxs-lookup"><span data-stu-id="833d8-237">This includes the WIN10 computer that has:</span></span>

- <span data-ttu-id="833d8-238">已联接 Microsoft 365 E5 订阅的 Azure AD 租户。</span><span class="sxs-lookup"><span data-stu-id="833d8-238">Joined the Azure AD tenant of your Microsoft 365 E5 subscription.</span></span>
- <span data-ttu-id="833d8-239">已注册为 Microsoft Intune (EMS) 中的 Azure AD 设备。</span><span class="sxs-lookup"><span data-stu-id="833d8-239">Enrolled as an Azure AD device in Microsoft Intune (EMS).</span></span>
- <span data-ttu-id="833d8-240">已安装 Office 365 专业增强版。</span><span class="sxs-lookup"><span data-stu-id="833d8-240">Has Office 365 ProPlus installed.</span></span>
  
<span data-ttu-id="833d8-241">现在可以试验 [Microsoft 365 企业版](https://www.microsoft.com/microsoft-365/enterprise)的其他功能。</span><span class="sxs-lookup"><span data-stu-id="833d8-241">You are now ready to experiment with additional features of [Microsoft 365 Enterprise](https://www.microsoft.com/microsoft-365/enterprise).</span></span>
  
## <a name="next-steps"></a><span data-ttu-id="833d8-242">后续步骤</span><span class="sxs-lookup"><span data-stu-id="833d8-242">Next steps</span></span>

<span data-ttu-id="833d8-243">浏览下面这些附加的一系列测试实验室指南：</span><span class="sxs-lookup"><span data-stu-id="833d8-243">Explore these additional sets of Test Lab Guides:</span></span>
  
- [<span data-ttu-id="833d8-244">标识</span><span class="sxs-lookup"><span data-stu-id="833d8-244">Identity</span></span>](m365-enterprise-test-lab-guides.md#identity)
- [<span data-ttu-id="833d8-245">移动设备管理</span><span class="sxs-lookup"><span data-stu-id="833d8-245">Mobile device management</span></span>](m365-enterprise-test-lab-guides.md#mobile-device-management)
- [<span data-ttu-id="833d8-246">信息保护</span><span class="sxs-lookup"><span data-stu-id="833d8-246">Information protection</span></span>](m365-enterprise-test-lab-guides.md#information-protection)
   

## <a name="see-also"></a><span data-ttu-id="833d8-247">另请参阅</span><span class="sxs-lookup"><span data-stu-id="833d8-247">See also</span></span>

[<span data-ttu-id="833d8-248">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="833d8-248">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="833d8-249">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="833d8-249">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="833d8-250">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="833d8-250">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
