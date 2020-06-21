---
title: 设置你的 Microsoft 威胁防护试用实验室环境
description: 访问 Microsoft 365 安全中心，然后设置你的 Microsoft 威胁防护试用实验室环境
keywords: Microsoft 威胁防护试用版安装程序，请尝试 Microsoft 威胁防护，Microsoft 威胁防护评估实验室安装程序
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: w10
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.openlocfilehash: 6cba773d0c4bea259db151d5a8f1d8e03954a045
ms.sourcegitcommit: f80c6c52e5b08290f74baec1d64c4070046c32e4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/12/2020
ms.locfileid: "44717291"
---
# <a name="set-up-your-microsoft-threat-protection-trial-lab-environment"></a><span data-ttu-id="07e02-104">设置你的 Microsoft 威胁防护试用实验室环境</span><span class="sxs-lookup"><span data-stu-id="07e02-104">Set up your Microsoft Threat Protection trial lab environment</span></span> 

<span data-ttu-id="07e02-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="07e02-105">**Applies to:**</span></span>
- <span data-ttu-id="07e02-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="07e02-106">Microsoft Threat Protection</span></span> 


<span data-ttu-id="07e02-107">创建 Microsoft 威胁 Protection 试用实验室环境并部署它的过程分为三个阶段：</span><span class="sxs-lookup"><span data-stu-id="07e02-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="准备 Microsoft 威胁防护评估实验室" />
      <br/><span data-ttu-id="07e02-109">第1阶段：准备</a></span><span class="sxs-lookup"><span data-stu-id="07e02-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="设置你的 Microsoft 威胁防护评估实验室" />
      <br/><span data-ttu-id="07e02-111">阶段2：安装程序</a></span><span class="sxs-lookup"><span data-stu-id="07e02-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="
Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection trial lab environment and onboard your endpoints" title="
为 Microsoft 威胁防护试用实验室环境配置每个 Microsoft 威胁防护支柱，并将终结点集成在一起" />
      <br/><span data-ttu-id="07e02-113">第3阶段： Configure & 板载</a></span><span class="sxs-lookup"><span data-stu-id="07e02-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="07e02-114">你当前处于 "设置" 阶段。</span><span class="sxs-lookup"><span data-stu-id="07e02-114">You are currently in the set up phase.</span></span> <span data-ttu-id="07e02-115">执行最初的步骤来访问 Microsoft 365 安全中心，然后设置你的试用实验室环境。</span><span class="sxs-lookup"><span data-stu-id="07e02-115">Take the initial steps to access Microsoft 365 Security Center then setup your trial lab environment.</span></span>

<span data-ttu-id="07e02-116">注册 Office 365 或 Azure Active Directory 订阅，以生成可用于注册 Microsoft 365 E5 许可证的*onmicrosoft.com*租户。</span><span class="sxs-lookup"><span data-stu-id="07e02-116">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="07e02-117">如果已有 Office 365 或 Azure Active Directory 订阅，则可以跳过 Office 365 E5 试用版租户创建步骤。</span><span class="sxs-lookup"><span data-stu-id="07e02-117">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

<span data-ttu-id="07e02-118">在此阶段中，将指导您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="07e02-118">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="07e02-119">创建 Office 365 E5 试用租户</span><span class="sxs-lookup"><span data-stu-id="07e02-119">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="07e02-120">启用 Microsoft 365 试用订阅</span><span class="sxs-lookup"><span data-stu-id="07e02-120">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="07e02-121">创建 Office 365 E5 试用租户</span><span class="sxs-lookup"><span data-stu-id="07e02-121">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="07e02-122">如果已有 Office 365 或 Azure Active Directory 订阅，则可以跳过 Office 365 E5 试用版租户创建步骤。</span><span class="sxs-lookup"><span data-stu-id="07e02-122">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="07e02-123">转到[Office 365 E5 产品门户](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)，并选择 "**免费试用版**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-123">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>
<span data-ttu-id="07e02-124">![Image of_Office 365 E5 免费试用页面](../../media/mtp-eval-9.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-124">![Image of_Office 365 E5 free trial page](../../media/mtp-eval-9.png)</span></span> <br>
  
2. <span data-ttu-id="07e02-125">通过输入您的电子邮件地址（个人或公司）完成试用注册。</span><span class="sxs-lookup"><span data-stu-id="07e02-125">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="07e02-126">单击 "**设置帐户**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-126">Click **Set up account**.</span></span>
<span data-ttu-id="07e02-127">![Image of_Office 365 E5 试用注册设置页](../../media/mtp-eval-10.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-127">![Image of_Office 365 E5 trial registration setup page](../../media/mtp-eval-10.png)</span></span> <br> 

3. <span data-ttu-id="07e02-128">填写你的名字、姓氏、商务电话号码、公司名称、公司规模和国家或地区。</span><span class="sxs-lookup"><span data-stu-id="07e02-128">Fill in your first name, last name, business phone number, company name, company size and country or region.</span></span>  
<br>![Image of_Office 365 E5 试用注册设置页面，要求输入姓名、电话和公司详细信息](../../media/mtp-eval-11.png) <br>
>[!NOTE]
><span data-ttu-id="07e02-130">您在此处设置的国家或地区决定了您的 Office 365 将托管的数据中心区域。</span><span class="sxs-lookup"><span data-stu-id="07e02-130">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="07e02-131">选择您的验证首选项：通过短信或 call。</span><span class="sxs-lookup"><span data-stu-id="07e02-131">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="07e02-132">单击 "**发送验证代码**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-132">Click **Send Verification Code**.</span></span> 
<span data-ttu-id="07e02-133">![Image of_Office 365 E5 试用注册设置页面请求验证首选项](../../media/mtp-eval-12.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-133">![Image of_Office 365 E5 trial registration setup page asking for verification preference](../../media/mtp-eval-12.png)</span></span> <br>

5. <span data-ttu-id="07e02-134">为租户设置自定义域名称，然后单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-134">Set the custom domain name for your tenant, then click **Next**.</span></span>
<br><span data-ttu-id="07e02-135">![Image of_Office 365 E5 试用注册安装程序页，您可以在其中设置自定义域名](../../media/mtp-eval-13.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-135">![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)</span></span> <br>
 
6. <span data-ttu-id="07e02-136">设置将成为租户的全局管理员的第一个标识。</span><span class="sxs-lookup"><span data-stu-id="07e02-136">Set up the first identity which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="07e02-137">填写 "**名称**" 和 "**密码**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-137">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="07e02-138">单击 "**注册**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-138">Click **Sign up**.</span></span>
<span data-ttu-id="07e02-139">![Image of_Office 365 E5 试用注册设置页，可在其中设置你的业务标识](../../media/mtp-eval-14.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-139">![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)</span></span> <br>

7. <span data-ttu-id="07e02-140">单击 "**转到设置**" 以完成 Office 365 E5 试用租户设置。</span><span class="sxs-lookup"><span data-stu-id="07e02-140">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>
<br><span data-ttu-id="07e02-141">![Office 365 E5 试用注册设置页面的图像提示单击 "转到设置" 按钮](../../media/mtp-eval-15.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-141">![Image of Office 365 E5 trial registration setup page prompting to click Go Setup button](../../media/mtp-eval-15.png)</span></span> <br>

8. <span data-ttu-id="07e02-142">将企业域连接到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="07e02-142">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="07e02-143">Optional选择 "**连接您已拥有的域**"，并键入您的域名。</span><span class="sxs-lookup"><span data-stu-id="07e02-143">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="07e02-144">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="07e02-144">Click **Next**.</span></span>
<br><span data-ttu-id="07e02-145">![Image of_Office 365 E5 设置页面，您应在其中对登录和电子邮件进行个性化设置](../../media/mtp-eval-16.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-145">![Image of_Office 365 E5 Setup page where you should personalize your sign-in and email](../../media/mtp-eval-16.png)</span></span> <br>
 
9. <span data-ttu-id="07e02-146">您将需要添加 TXT 或 MX 记录以验证域所有权。</span><span class="sxs-lookup"><span data-stu-id="07e02-146">You will need to add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="07e02-147">将 TXT 或 MX 记录添加到域后，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-147">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>
<br><span data-ttu-id="07e02-148">![Image of_Office 365 E5 安装程序页，您应在其中添加 TXT 条 MX 记录以验证您的域](../../media/mtp-eval-17.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-148">![Image of_Office 365 E5 setup page where you should add a TXT of MX record to verify your domain](../../media/mtp-eval-17.png)</span></span> <br>
 
10. <span data-ttu-id="07e02-149">Optional为你的租户创建更多用户帐户。</span><span class="sxs-lookup"><span data-stu-id="07e02-149">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="07e02-150">您可以通过单击 "**下一步**" 跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="07e02-150">You can skip this step by clicking **Next**.</span></span>
<span data-ttu-id="07e02-151">![Image of_Office 365 E5 安装程序页，您可以在其中添加更多用户](../../media/mtp-eval-18.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-151">![Image of_Office 365 E5 setup page where you can add more users](../../media/mtp-eval-18.png)</span></span> <br>
 
11. <span data-ttu-id="07e02-152">Optional下载 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="07e02-152">[Optional] Download Office apps.</span></span> <span data-ttu-id="07e02-153">单击 "**下一步**" 跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="07e02-153">Click **Next** to skip this step.</span></span> 
<br><span data-ttu-id="07e02-154">![可在其中安装 Office 应用程序的 "图像 of_Office 365 E5" 页面](../../media/mtp-eval-19.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-154">![Image of_Office 365 E5 page where you can install your Office apps](../../media/mtp-eval-19.png)</span></span> <br>

12. <span data-ttu-id="07e02-155">Optional迁移电子邮件。</span><span class="sxs-lookup"><span data-stu-id="07e02-155">[Optional] Migrate email messages.</span></span> <span data-ttu-id="07e02-156">同样，您可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="07e02-156">Again, you can skip this step.</span></span>
<br><span data-ttu-id="07e02-157">![图像 of_Office 365 E5，您可以在其中设置是否迁移电子邮件](../../media/mtp-eval-20.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-157">![Image of_Office 365 E5 where you can set whether to migrate email messages or not](../../media/mtp-eval-20.png)</span></span> <br>
 
13. <span data-ttu-id="07e02-158">选择 "在线服务"。</span><span class="sxs-lookup"><span data-stu-id="07e02-158">Choose online services.</span></span> <span data-ttu-id="07e02-159">选择 " **Exchange** " 并单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-159">Select **Exchange** and click **Next**.</span></span> 
<br><span data-ttu-id="07e02-160">![可以在其中选择在线服务的图像 of_Office 365 E5](../../media/mtp-eval-21.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-160">![Image of_Office 365 E5 where you can choose your online services](../../media/mtp-eval-21.png)</span></span> <br>

14. <span data-ttu-id="07e02-161">向您的域中添加 MX、CNAME 和 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="07e02-161">Add MX, CNAME and TXT records to your domain.</span></span> <span data-ttu-id="07e02-162">完成后，选择 "**验证**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-162">When completed, select **Verify**.</span></span>
<br><span data-ttu-id="07e02-163">![Image of_Office 365 E5 在这里，你可以添加 DNS 记录](../../media/mtp-eval-22.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-163">![Image of_Office 365 E5 here you can add your DNS records](../../media/mtp-eval-22.png)</span></span> <br>
 
15. <span data-ttu-id="07e02-164">恭喜，你已完成 Office 365 租户的预配。</span><span class="sxs-lookup"><span data-stu-id="07e02-164">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>
<br><span data-ttu-id="07e02-165">![Image of_Office 365 E5 安装程序完成确认页](../../media/mtp-eval-23.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-165">![Image of_Office 365 E5 setup completion confirmation page](../../media/mtp-eval-23.png)</span></span> <br>

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="07e02-166">启用 Microsoft 365 试用订阅</span><span class="sxs-lookup"><span data-stu-id="07e02-166">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="07e02-167">注册试用版将提供25个用户许可证用于一个月。</span><span class="sxs-lookup"><span data-stu-id="07e02-167">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="07e02-168">有关详细信息，请参阅[试用或购买 M365 订阅](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1)。</span><span class="sxs-lookup"><span data-stu-id="07e02-168">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365?view=o365-worldwide#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="07e02-169">从[Microsoft 365 管理中心](https://admin.microsoft.com/)，单击 "**帐单**"，然后导航到 "**购买服务**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-169">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="07e02-170">选择 " **Microsoft 365 E5** "，然后单击 "**开始免费试用**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-170">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 
<span data-ttu-id="07e02-171">![Image of_Microsoft 365 E5 开始免费试用页面](../../media/mtp-eval-24.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-171">![Image of_Microsoft 365 E5 Start free trial page](../../media/mtp-eval-24.png)</span></span> <br>

3. <span data-ttu-id="07e02-172">选择您的验证首选项：通过短信或 call。</span><span class="sxs-lookup"><span data-stu-id="07e02-172">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="07e02-173">确定后，请输入电话号码，选择 "**文本**" 或 "**呼叫我**"，具体取决于你的选择。</span><span class="sxs-lookup"><span data-stu-id="07e02-173">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>
<span data-ttu-id="07e02-174">![Image of_Microsoft 365 E5 开始免费试用页面，请求联系详细信息，以证明你不是机器人](../../media/mtp-eval-25.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-174">![Image of_Microsoft 365 E5 Start free trial page asking for contact details to send code to prove you are not a robot](../../media/mtp-eval-25.png)</span></span> <br>
 
4. <span data-ttu-id="07e02-175">输入验证代码，然后单击 "**开始免费试用**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-175">Enter the verification code and click **Start your free trial**.</span></span> 
<br><span data-ttu-id="07e02-176">![Image of_Microsoft 365 E5 开始免费试用页面，您可以在其中填写验证代码，以证明您不是机器人的系统](../../media/mtp-eval-26.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-176">![Image of_Microsoft 365 E5 Start free trial page where you can fill out verification code the system sent to prove you are not a robot](../../media/mtp-eval-26.png)</span></span> <br>

5. <span data-ttu-id="07e02-177">单击 "**立即试用**" 以确认你的 Microsoft 365 E5 试用版。</span><span class="sxs-lookup"><span data-stu-id="07e02-177">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>
<br><span data-ttu-id="07e02-178">![Image of_Microsoft 365 E5 开始免费试用页面，应在此处时钟 "立即试用" 按钮开始](../../media/mtp-eval-27.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-178">![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)</span></span> <br>
 
6. <span data-ttu-id="07e02-179">转到**Microsoft 365 管理中心**  >  **用户**  >  **活动用户**。</span><span class="sxs-lookup"><span data-stu-id="07e02-179">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="07e02-180">选择您的用户帐户，选择 "**管理产品许可证**"，然后将来自 Office 365 e5 的许可证交换为**Microsoft 365 e5**。</span><span class="sxs-lookup"><span data-stu-id="07e02-180">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="07e02-181">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="07e02-181">Click **Save**.</span></span>
<span data-ttu-id="07e02-182">![Image of_Microsoft 365 管理中心 "页面，您可以在其中选择 Microsoft 365 E5 许可证](../../media/mtp-eval-28.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-182">![Image of_Microsoft 365 Admin Center page where you can select Microsoft 365 E5 license](../../media/mtp-eval-28.png)</span></span> <br>
 
7. <span data-ttu-id="07e02-183">再次选择全局管理员帐户，然后单击 "**管理用户名**"。</span><span class="sxs-lookup"><span data-stu-id="07e02-183">Select the global administrator account again then click **Manage username**.</span></span>
<br><span data-ttu-id="07e02-184">![Image of_Microsoft 365 管理中心 "页面，您可以在其中选择" 帐户 "，然后管理用户名](../../media/mtp-eval-29.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-184">![Image of_Microsoft 365 Admin Center page where you can select Account and then Manage username](../../media/mtp-eval-29.png)</span></span> <br>

8. <span data-ttu-id="07e02-185">Optional将域从*onmicrosoft.com*更改为您自己的域，具体取决于您在前面步骤中选择的内容。</span><span class="sxs-lookup"><span data-stu-id="07e02-185">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="07e02-186">单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="07e02-186">Click **Save changes**.</span></span>
<br><span data-ttu-id="07e02-187">![图像 of_Microsoft 365 管理中心 "页，您可以在其中更改您的域首选项](../../media/mtp-eval-30.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-187">![Image of_Microsoft 365 Admin Center page where you can change your domain preference](../../media/mtp-eval-30.png)</span></span> <br>



## <a name="next-step"></a><span data-ttu-id="07e02-188">后续步骤</span><span class="sxs-lookup"><span data-stu-id="07e02-188">Next step</span></span>
|||
|:-------|:-----|
|<span data-ttu-id="07e02-189">![第3阶段： Configure & 板载](../../media/config-onboard.png)</span><span class="sxs-lookup"><span data-stu-id="07e02-189">![Phase 3: Configure & Onboard](../../media/config-onboard.png)</span></span> <br>[<span data-ttu-id="07e02-190">第3阶段： Configure & 板载</span><span class="sxs-lookup"><span data-stu-id="07e02-190">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="07e02-191">为 Microsoft 威胁防护评估实验室配置每个 Microsoft 威胁防护支柱，并将终结点集成在一起。</span><span class="sxs-lookup"><span data-stu-id="07e02-191">Configure each Microsoft Threat Protection pillar for your Microsoft Threat Protection evaluation lab and onboard your endpoints.</span></span>
