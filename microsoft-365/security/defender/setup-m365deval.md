---
title: 设置 Microsoft 365 Defender 试用实验室或试验环境
description: 访问 Microsoft 365 安全中心，然后设置 Microsoft 365 Defender 试用实验室环境
keywords: Microsoft 365 Defender 试用设置， Microsoft 365 Defender 试点设置， 试用 Microsoft 365 Defender， Microsoft 365 Defender 评估实验室设置
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: dolmont
author: DulceMontemayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.technology: m365d
ms.openlocfilehash: ae81f6be0a83d5d0141f0f0c8c89f8f2207cc56c
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935421"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="fd725-104">设置 Microsoft 365 Defender 试用实验室环境</span><span class="sxs-lookup"><span data-stu-id="fd725-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="fd725-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="fd725-105">**Applies to:**</span></span>
- <span data-ttu-id="fd725-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fd725-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="fd725-107">创建 Microsoft 365 Defender 试用实验室或试验环境并部署它的过程分三个阶段：</span><span class="sxs-lookup"><span data-stu-id="fd725-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="fd725-108">[![阶段 1：准备](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="fd725-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="fd725-109">阶段 1：准备</span><span class="sxs-lookup"><span data-stu-id="fd725-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |![阶段 2：设置](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="fd725-111">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="fd725-111">Phase 2: Set up</span></span> |<span data-ttu-id="fd725-112">[![阶段 3：开始使用](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="fd725-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-m365d-eval.md)</span></span><br/>[<span data-ttu-id="fd725-113">阶段 3：开始使用</span><span class="sxs-lookup"><span data-stu-id="fd725-113">Phase 3: Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="fd725-114">[![返回到试点](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="fd725-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="fd725-115">返回到试点手册</span><span class="sxs-lookup"><span data-stu-id="fd725-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="fd725-116">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="fd725-116">*You are here!*</span></span>  | | |


<span data-ttu-id="fd725-117">你当前处于设置阶段。</span><span class="sxs-lookup"><span data-stu-id="fd725-117">You're currently in the set up phase.</span></span> <span data-ttu-id="fd725-118">执行初始步骤以访问 Microsoft 365 安全中心，然后设置试用实验室或试验环境。</span><span class="sxs-lookup"><span data-stu-id="fd725-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="fd725-119">注册 Office 365 或 Azure Active Directory 订阅以生成可用于注册 Microsoft 365 E5 许可证的 *.onmicrosoft.com* 租户。</span><span class="sxs-lookup"><span data-stu-id="fd725-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="fd725-120">如果已有 Office 365 或 Azure Active Directory 订阅，可以跳过 Office 365 E5 试用版或试点租户创建步骤。</span><span class="sxs-lookup"><span data-stu-id="fd725-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="fd725-121">在此阶段，将指导你：</span><span class="sxs-lookup"><span data-stu-id="fd725-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="fd725-122">创建 Office 365 E5 试用租户</span><span class="sxs-lookup"><span data-stu-id="fd725-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="fd725-123">启用 Microsoft 365 试用订阅</span><span class="sxs-lookup"><span data-stu-id="fd725-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="fd725-124">创建 Office 365 E5 试用租户</span><span class="sxs-lookup"><span data-stu-id="fd725-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="fd725-125">如果已有 Office 365 或 Azure Active Directory 订阅，可以跳过 Office 365 E5 试用租户创建步骤。</span><span class="sxs-lookup"><span data-stu-id="fd725-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="fd725-126">转到 [Office 365 E5 产品门户，](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) 然后选择 **免费试用**。</span><span class="sxs-lookup"><span data-stu-id="fd725-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![图像of_Office 365 E5 免费试用版页面](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="fd725-128">通过向个人或公司用户 (电子邮件地址完成) 。</span><span class="sxs-lookup"><span data-stu-id="fd725-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="fd725-129">单击 **"设置帐户"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-129">Click **Set up account**.</span></span>

   ![图像of_Office 365 E5 试用注册设置页面](../../media/mtp-eval-10.png)

3. <span data-ttu-id="fd725-131">填写你的名字、姓氏、公司电话号码、公司名称、公司规模以及国家/地区。</span><span class="sxs-lookup"><span data-stu-id="fd725-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![要求of_Office、电话和公司详细信息的 365 E5 试用注册设置页面的图像](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="fd725-133">你在此处设置的一个或多个国家/地区决定了 Office 365 将托管的数据中心区域。</span><span class="sxs-lookup"><span data-stu-id="fd725-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="fd725-134">选择验证首选项：通过短信或呼叫。</span><span class="sxs-lookup"><span data-stu-id="fd725-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="fd725-135">单击 **"发送验证码"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-135">Click **Send Verification Code**.</span></span> 

   ![要求of_Office首选项的 365 E5 试用注册设置页面的图像](../../media/mtp-eval-12.png)

5. <span data-ttu-id="fd725-137">为租户设置自定义域名，然后单击"下一步 **"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5 trial registration setup page where you can set up your custom domain name](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="fd725-139">设置第一个标识，即租户的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="fd725-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="fd725-140">填写名称和 **密码**。</span><span class="sxs-lookup"><span data-stu-id="fd725-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="fd725-141">单击 **"注册"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-141">Click **Sign up**.</span></span>

   ![Image of_Office 365 E5 trial registration setup page where you can set your business identity](../../media/mtp-eval-14.png)

7. <span data-ttu-id="fd725-143">单击 **"转到设置"** 以完成 Office 365 E5 试用租户预配。</span><span class="sxs-lookup"><span data-stu-id="fd725-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Office 365 E5 试用注册设置页面提示单击"开始设置"按钮的图像](../../media/mtp-eval-15.png)

8. <span data-ttu-id="fd725-145">将公司域连接到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="fd725-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="fd725-146">[可选]选择 **"连接你已拥有的域"，** 然后键入你的域名。</span><span class="sxs-lookup"><span data-stu-id="fd725-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="fd725-147">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="fd725-147">Click **Next**.</span></span>

   ![图像of_Office 365 E5 设置页面，应在其中个性化设置登录和电子邮件](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="fd725-149">添加 TXT 或 MX 记录以验证域所有权。</span><span class="sxs-lookup"><span data-stu-id="fd725-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="fd725-150">将 TXT 或 MX 记录添加到域后，选择"验证 **"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![图像of_Office 365 E5 设置页面，应在其中添加 MX 记录的 TXT 以验证域](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="fd725-152">[可选]为租户创建多个用户帐户。</span><span class="sxs-lookup"><span data-stu-id="fd725-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="fd725-153">可以通过单击"下一步"跳过 **此步骤**。</span><span class="sxs-lookup"><span data-stu-id="fd725-153">You can skip this step by clicking **Next**.</span></span>

    ![图像of_Office 365 E5 设置页面，可在其中添加更多用户](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="fd725-155">[可选]下载 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="fd725-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="fd725-156">单击 **"下一** 步"跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="fd725-156">Click **Next** to skip this step.</span></span> 

    ![Image of_Office 365 E5 page where you can install your Office apps](../../media/mtp-eval-19.png)

12. <span data-ttu-id="fd725-158">[可选]迁移电子邮件。</span><span class="sxs-lookup"><span data-stu-id="fd725-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="fd725-159">同样，可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="fd725-159">Again, you can skip this step.</span></span>

    ![图像of_Office 365 E5 中可以设置是否迁移电子邮件](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="fd725-161">选择"联机服务"。</span><span class="sxs-lookup"><span data-stu-id="fd725-161">Choose online services.</span></span> <span data-ttu-id="fd725-162">选择 **"Exchange"，** 然后单击"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-162">Select **Exchange** and click **Next**.</span></span> 

    ![图像of_Office 365 E5，可在其中选择联机服务](../../media/mtp-eval-21.png)

14. <span data-ttu-id="fd725-164">将 MX、CNAME 和 TXT 记录添加到你的域。</span><span class="sxs-lookup"><span data-stu-id="fd725-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="fd725-165">完成后，选择"验证 **"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-165">When completed, select **Verify**.</span></span>

    ![图像of_Office 365 E5，可以在此处添加 DNS 记录](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="fd725-167">恭喜！你已完成 Office 365 租户的预配。</span><span class="sxs-lookup"><span data-stu-id="fd725-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![图像of_Office 365 E5 设置完成确认页](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="fd725-169">启用 Microsoft 365 试用订阅</span><span class="sxs-lookup"><span data-stu-id="fd725-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="fd725-170">注册试用版可为你提供 25 个用户许可证，供一个月使用。</span><span class="sxs-lookup"><span data-stu-id="fd725-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="fd725-171">有关详细信息 [，请参阅试用或购买 M365](../../commerce/try-or-buy-microsoft-365.md) 订阅。</span><span class="sxs-lookup"><span data-stu-id="fd725-171">See [Try or Buy an M365 subscription](../../commerce/try-or-buy-microsoft-365.md) for details.</span></span>

1. <span data-ttu-id="fd725-172">在 [Microsoft 365 管理中心中](https://admin.microsoft.com/)，单击 **"计费**"，然后导航到"**购买服务"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="fd725-173">选择 **"Microsoft 365 E5"，** 然后单击"**开始免费试用"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![图像of_Microsoft 365 E5 开始免费试用页面](../../media/mtp-eval-24.png)

3. <span data-ttu-id="fd725-175">选择验证首选项：通过短信或呼叫。</span><span class="sxs-lookup"><span data-stu-id="fd725-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="fd725-176">决定后，输入电话号码，选择"为我发 **短信** "或" **呼叫** 我"，具体取决于你的选择。</span><span class="sxs-lookup"><span data-stu-id="fd725-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![图像of_Microsoft 365 E5 开始免费试用页面，请求联系人详细信息发送代码以证明你并非机器人](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="fd725-178">输入验证码，然后单击 **开始免费试用**。</span><span class="sxs-lookup"><span data-stu-id="fd725-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![图像of_Microsoft 365 E5 开始免费试用页面，你可以填写系统发送的验证码以证明你并非机器人](../../media/mtp-eval-26.png)

5. <span data-ttu-id="fd725-180">单击 **立即试用** 以确认 Microsoft 365 E5 试用版。</span><span class="sxs-lookup"><span data-stu-id="fd725-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 Start free trial page where you should clock the Try now button to start](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="fd725-182">转到 **Microsoft 365 管理中心**  >  **用户**  >  **活动用户**。</span><span class="sxs-lookup"><span data-stu-id="fd725-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="fd725-183">选择用户帐户，选择管理 **产品许可证**，然后将许可证从 Office 365 E5 交换为 **Microsoft 365 E5。**</span><span class="sxs-lookup"><span data-stu-id="fd725-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="fd725-184">单击“保存”。</span><span class="sxs-lookup"><span data-stu-id="fd725-184">Click **Save**.</span></span>

   ![图像of_Microsoft 365 管理中心页面，可在其中选择 Microsoft 365 E5 许可证](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="fd725-186">再次选择全局管理员帐户，然后单击"**管理用户名"。**</span><span class="sxs-lookup"><span data-stu-id="fd725-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![图像of_Microsoft 365 管理中心页面，可在其中选择"帐户"，然后选择"管理用户名"](../../media/mtp-eval-29.png)

8. <span data-ttu-id="fd725-188">[可选]根据你在之前 *onmicrosoft.com* 选择的不同，将域从一个域更改为你自己的域。</span><span class="sxs-lookup"><span data-stu-id="fd725-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="fd725-189">单击“**保存更改**”。</span><span class="sxs-lookup"><span data-stu-id="fd725-189">Click **Save changes**.</span></span>

   ![图像of_Microsoft 365 管理中心页面，可在其中更改域首选项](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="fd725-191">后续步骤</span><span class="sxs-lookup"><span data-stu-id="fd725-191">Next step</span></span>
|[<span data-ttu-id="fd725-192">阶段 3：配置&载入</span><span class="sxs-lookup"><span data-stu-id="fd725-192">Phase 3: Configure & Onboard</span></span>](config-m365d-eval.md) | <span data-ttu-id="fd725-193">为 Microsoft 365 Defender 试用实验室或试点环境配置每个 Microsoft 365 Defender 支柱，并载入终结点。</span><span class="sxs-lookup"><span data-stu-id="fd725-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
