---
title: 设置你的Microsoft 365 Defender试验实验室或试验环境
description: 然后Microsoft 365安全中心设置Microsoft 365 Defender实验室环境
keywords: Microsoft 365 Defender试验设置，Microsoft 365 Defender试验设置，请尝试Microsoft 365 Defender、Microsoft 365 Defender实验室设置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: v-lsaldanha
author: lovina-saldanha
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: 6db3003aa6465df90a3d2e4af55b28ccccf44100
ms.sourcegitcommit: 718759c7146062841f7eb4a0a9a8bdddce0139b0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/15/2021
ms.locfileid: "53454729"
---
# <a name="set-up-your-microsoft-365-defender-trial-in-a-lab-environment"></a><span data-ttu-id="d83cb-104">在实验室Microsoft 365 Defender设置试用</span><span class="sxs-lookup"><span data-stu-id="d83cb-104">Set up your Microsoft 365 Defender trial in a lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="d83cb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="d83cb-105">**Applies to:**</span></span>
- <span data-ttu-id="d83cb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d83cb-106">Microsoft 365 Defender</span></span> 

<span data-ttu-id="d83cb-107">本主题指导您设置专用实验室环境。</span><span class="sxs-lookup"><span data-stu-id="d83cb-107">This topic guides you to set up a dedicated lab environment.</span></span> <span data-ttu-id="d83cb-108">有关在生产中设置试用版的信息，请参阅新的评估和试点Microsoft 365 Defender[指南。](eval-overview.md)</span><span class="sxs-lookup"><span data-stu-id="d83cb-108">For information on setting up a trial in production, see the new [Evaluate and pilot Microsoft 365 Defender](eval-overview.md) guide.</span></span> 

## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="d83cb-109">创建Office 365 E5试用租户</span><span class="sxs-lookup"><span data-stu-id="d83cb-109">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="d83cb-110">如果你已拥有现有 Office 365 或 Azure Active Directory 订阅，可以跳过Office 365 E5租户创建步骤。</span><span class="sxs-lookup"><span data-stu-id="d83cb-110">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="d83cb-111">转到产品Office 365 E5 [并选择](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab)免费 **试用版**。</span><span class="sxs-lookup"><span data-stu-id="d83cb-111">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![图像of_Office 365 E5 免费试用版页面](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="d83cb-113">通过向个人或公司用户 (电子邮件地址完成) 。</span><span class="sxs-lookup"><span data-stu-id="d83cb-113">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="d83cb-114">单击 **"设置帐户"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-114">Click **Set up account**.</span></span>

   ![图像of_Office 365 E5 试用注册设置页面](../../media/mtp-eval-10.png)

3. <span data-ttu-id="d83cb-116">填写你的名字、姓氏、公司电话号码、公司名称、公司规模以及国家/地区。</span><span class="sxs-lookup"><span data-stu-id="d83cb-116">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![要求of_Office、电话和公司详细信息的 365 E5 试用注册设置页面的图像](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="d83cb-118">你在此处设置的一个或多个国家/地区决定了你的Office 365将托管的数据中心区域。</span><span class="sxs-lookup"><span data-stu-id="d83cb-118">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="d83cb-119">选择验证首选项：通过短信或呼叫。</span><span class="sxs-lookup"><span data-stu-id="d83cb-119">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="d83cb-120">单击 **"发送验证码"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-120">Click **Send Verification Code**.</span></span> 

   ![要求of_Office首选项的 365 E5 试用注册设置页面的图像](../../media/mtp-eval-12.png)

5. <span data-ttu-id="d83cb-122">为租户设置自定义域名，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-122">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="d83cb-124">设置第一个标识，即租户的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="d83cb-124">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="d83cb-125">填写名称和 **密码**。</span><span class="sxs-lookup"><span data-stu-id="d83cb-125">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="d83cb-126">单击“**注册**”。</span><span class="sxs-lookup"><span data-stu-id="d83cb-126">Click **Sign up**.</span></span>

   ![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)

7. <span data-ttu-id="d83cb-128">单击 **"转到设置**"以完成Office 365 E5租户预配。</span><span class="sxs-lookup"><span data-stu-id="d83cb-128">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![试用Office 365 E5设置页面提示单击"开始设置"按钮的图像](../../media/mtp-eval-15.png)

8. <span data-ttu-id="d83cb-130">连接公司域注册到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="d83cb-130">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="d83cb-131">[可选]选择 **连接已拥有的域，** 然后键入你的域名。</span><span class="sxs-lookup"><span data-stu-id="d83cb-131">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="d83cb-132">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="d83cb-132">Click **Next**.</span></span>

   ![图像of_Office 365 E5 设置页面，应在其中个性化设置登录和电子邮件](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="d83cb-134">添加 TXT 或 MX 记录以验证域所有权。</span><span class="sxs-lookup"><span data-stu-id="d83cb-134">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="d83cb-135">将 TXT 或 MX 记录添加到域后，选择"验证 **"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-135">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![图像of_Office 365 E5 设置页面，应在其中添加 MX 记录的 TXT 以验证域](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="d83cb-137">[可选]为租户创建多个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="d83cb-137">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="d83cb-138">可以通过单击"下一步"跳过 **此步骤**。</span><span class="sxs-lookup"><span data-stu-id="d83cb-138">You can skip this step by clicking **Next**.</span></span>

    ![图像of_Office 365 E5 设置页面，可在其中添加更多用户](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="d83cb-140">[可选]下载Office应用。</span><span class="sxs-lookup"><span data-stu-id="d83cb-140">[Optional] Download Office apps.</span></span> <span data-ttu-id="d83cb-141">单击 **"下一** 步"跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="d83cb-141">Click **Next** to skip this step.</span></span> 

    ![图像of_Office 365 E5 页面，可在其中安装 Office 应用](../../media/mtp-eval-19.png)

12. <span data-ttu-id="d83cb-143">[可选]迁移电子邮件。</span><span class="sxs-lookup"><span data-stu-id="d83cb-143">[Optional] Migrate email messages.</span></span> <span data-ttu-id="d83cb-144">同样，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="d83cb-144">Again, you can skip this step.</span></span>

    ![图像of_Office 365 E5 中可以设置是否迁移电子邮件](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="d83cb-146">选择"联机服务"。</span><span class="sxs-lookup"><span data-stu-id="d83cb-146">Choose online services.</span></span> <span data-ttu-id="d83cb-147">选择 **"Exchange"，** 然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-147">Select **Exchange** and click **Next**.</span></span> 

    ![图像of_Office 365 E5，可在其中选择联机服务](../../media/mtp-eval-21.png)

14. <span data-ttu-id="d83cb-149">将 MX、CNAME 和 TXT 记录添加到你的域。</span><span class="sxs-lookup"><span data-stu-id="d83cb-149">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="d83cb-150">完成后，选择"验证 **"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-150">When completed, select **Verify**.</span></span>

    ![图像of_Office 365 E5，可以在此处添加 DNS 记录](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="d83cb-152">恭喜！你已完成预配你的 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="d83cb-152">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![图像of_Office 365 E5 设置完成确认页](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="d83cb-154">启用Microsoft 365试用版订阅</span><span class="sxs-lookup"><span data-stu-id="d83cb-154">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="d83cb-155">注册试用版可为你提供 25 个用户许可证，供一个月使用。</span><span class="sxs-lookup"><span data-stu-id="d83cb-155">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="d83cb-156">有关详细信息 [，请参阅试用或购买 M365](../../commerce/try-or-buy-microsoft-365.md) 订阅。</span><span class="sxs-lookup"><span data-stu-id="d83cb-156">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="d83cb-157">从 [Microsoft 365 管理中心，](https://admin.microsoft.com/)单击 **"计费**"，然后导航到"**购买服务"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-157">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="d83cb-158">选择 **"Microsoft 365 E5"，** 然后单击 **"开始免费试用"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-158">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![图像of_Microsoft 365 E5 开始免费试用页面](../../media/mtp-eval-24.png)

3. <span data-ttu-id="d83cb-160">选择验证首选项：通过短信或呼叫。</span><span class="sxs-lookup"><span data-stu-id="d83cb-160">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="d83cb-161">决定后，输入电话号码，选择"为我发 **短信** "或" **呼叫** 我"，具体取决于你的选择。</span><span class="sxs-lookup"><span data-stu-id="d83cb-161">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![图像of_Microsoft 365 E5 开始免费试用页面，请求联系人详细信息发送代码以证明你并非机器人](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="d83cb-163">输入验证码，然后单击 **开始免费试用**。</span><span class="sxs-lookup"><span data-stu-id="d83cb-163">Enter the verification code and click **Start your free trial**.</span></span>

   ![图像of_Microsoft 365 E5 开始免费试用页面，你可以填写系统发送的验证码以证明你并非机器人](../../media/mtp-eval-26.png)

5. <span data-ttu-id="d83cb-165">单击 **"立即试用**"确认Microsoft 365 E5试用版。</span><span class="sxs-lookup"><span data-stu-id="d83cb-165">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="d83cb-167">转到"Microsoft 365 管理 **中心**  >  **用户**  >  **""活动用户"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-167">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="d83cb-168">选择用户帐户，选择管理 **产品许可证**，然后将许可证从 Office 365 E5 交换为 **Microsoft 365 E5。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-168">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="d83cb-169">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="d83cb-169">Click **Save**.</span></span>

   ![图像of_Microsoft 365 管理中心页面，可在其中选择Microsoft 365 E5许可证](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="d83cb-171">再次选择全局管理员帐户，然后单击"**管理用户名"。**</span><span class="sxs-lookup"><span data-stu-id="d83cb-171">Select the global administrator account again then click **Manage username**.</span></span>

   ![图像of_Microsoft 365 管理中心页面，可在其中选择"帐户"，然后选择"管理用户名"](../../media/mtp-eval-29.png)

8. <span data-ttu-id="d83cb-173">[可选]根据你在之前 *onmicrosoft.com* 选择的不同，将域从一个域更改为你自己的域。</span><span class="sxs-lookup"><span data-stu-id="d83cb-173">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="d83cb-174">单击 **保存更改**。</span><span class="sxs-lookup"><span data-stu-id="d83cb-174">Click **Save changes**.</span></span>

   ![图像of_Microsoft 365 管理中心页面，可在其中更改域首选项](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="d83cb-176">下一步</span><span class="sxs-lookup"><span data-stu-id="d83cb-176">Next step</span></span>
|[<span data-ttu-id="d83cb-177">阶段 3：配置&载入</span><span class="sxs-lookup"><span data-stu-id="d83cb-177">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="d83cb-178">为测试Microsoft 365 Defender环境配置Microsoft 365 Defender功能支柱，并载入终结点。</span><span class="sxs-lookup"><span data-stu-id="d83cb-178">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
