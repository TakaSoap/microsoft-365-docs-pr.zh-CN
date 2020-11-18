---
title: 设置你的 Microsoft 365 Defender 试用版实验室或试点环境
description: 访问 Microsoft 365 安全中心，然后设置你的 Microsoft 365 Defender 试用实验室环境
keywords: Microsoft 威胁防护试用版设置，Microsoft 威胁防护试点设置，尝试 Microsoft 威胁防护，Microsoft 威胁 Protection 评估实验室安装程序
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
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.topic: article
ms.openlocfilehash: 503b7a6a6b3ad6394293e9f70dbdd336f6bee9dd
ms.sourcegitcommit: ce46d1bd67091d4ed0e2b776dfed55e2d88cdbf4
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/18/2020
ms.locfileid: "49131305"
---
# <a name="set-up-your-microsoft-365-defender-trial-lab-environment"></a><span data-ttu-id="754bc-104">设置你的 Microsoft 365 Defender 试用实验室环境</span><span class="sxs-lookup"><span data-stu-id="754bc-104">Set up your Microsoft 365 Defender trial lab environment</span></span> 

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="754bc-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="754bc-105">**Applies to:**</span></span>
- <span data-ttu-id="754bc-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="754bc-106">Microsoft 365 Defender</span></span> 


<span data-ttu-id="754bc-107">创建 Microsoft 365 Defender 试用版实验室或试点环境并对其进行部署的过程分为三个阶段：</span><span class="sxs-lookup"><span data-stu-id="754bc-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="754bc-108">[![第1阶段：准备](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="754bc-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-mtpeval.md)</span></span><br/>[<span data-ttu-id="754bc-109">第1阶段：准备</span><span class="sxs-lookup"><span data-stu-id="754bc-109">Phase 1: Prepare</span></span>](prepare-mtpeval.md) |![阶段2：设置](../../media/phase-diagrams/setup.png)<br/><span data-ttu-id="754bc-111">阶段2：设置</span><span class="sxs-lookup"><span data-stu-id="754bc-111">Phase 2: Set up</span></span> |<span data-ttu-id="754bc-112">[![第3阶段：板载](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span><span class="sxs-lookup"><span data-stu-id="754bc-112">[![Phase 3: Onboard](../../media/phase-diagrams/onboard.png)](config-mtpeval.md)</span></span><br/>[<span data-ttu-id="754bc-113">第3阶段：板载</span><span class="sxs-lookup"><span data-stu-id="754bc-113">Phase 3: Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="754bc-114">[![返回试点](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="754bc-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](mtp-pilot.md)</span></span><br/>[<span data-ttu-id="754bc-115">返回试点行动手册</span><span class="sxs-lookup"><span data-stu-id="754bc-115">Back to pilot playbook</span></span>](mtp-pilot.md) |
|--|--|--|--|
||<span data-ttu-id="754bc-116">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="754bc-116">*You are here!*</span></span>  | | |


<span data-ttu-id="754bc-117">你当前正在设置阶段。</span><span class="sxs-lookup"><span data-stu-id="754bc-117">You're currently in the set up phase.</span></span> <span data-ttu-id="754bc-118">执行最初的步骤来访问 Microsoft 365 安全中心，然后设置试用版实验室或试点环境。</span><span class="sxs-lookup"><span data-stu-id="754bc-118">Take the initial steps to access Microsoft 365 Security Center then set up your trial lab or pilot environment.</span></span>

<span data-ttu-id="754bc-119">注册 Office 365 或 Azure Active Directory 订阅，以生成可用于注册 Microsoft 365 E5 许可证的 *onmicrosoft.com* 租户。</span><span class="sxs-lookup"><span data-stu-id="754bc-119">Sign up for an Office 365 or Azure Active Directory subscription to generate a *.onmicrosoft.com* tenant that you can use to sign up for your Microsoft 365 E5 license.</span></span> 

>[!NOTE]
><span data-ttu-id="754bc-120">如果已有 Office 365 或 Azure Active Directory 订阅，则可以跳过 Office 365 E5 试用版或试点租户创建步骤。</span><span class="sxs-lookup"><span data-stu-id="754bc-120">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial or pilot tenant creation steps.</span></span>

<span data-ttu-id="754bc-121">在此阶段中，将指导您执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="754bc-121">In this phase, you'll be guided to:</span></span>
- <span data-ttu-id="754bc-122">创建 Office 365 E5 试用租户</span><span class="sxs-lookup"><span data-stu-id="754bc-122">Create an Office 365 E5 trial tenant</span></span>
- <span data-ttu-id="754bc-123">启用 Microsoft 365 试用订阅</span><span class="sxs-lookup"><span data-stu-id="754bc-123">Enable Microsoft 365 trial subscription</span></span>


## <a name="create-an-office-365-e5-trial-tenant"></a><span data-ttu-id="754bc-124">创建 Office 365 E5 试用租户</span><span class="sxs-lookup"><span data-stu-id="754bc-124">Create an Office 365 E5 trial tenant</span></span>
>[!NOTE]
><span data-ttu-id="754bc-125">如果已有 Office 365 或 Azure Active Directory 订阅，则可以跳过 Office 365 E5 试用版租户创建步骤。</span><span class="sxs-lookup"><span data-stu-id="754bc-125">If you already have an existing Office 365 or Azure Active Directory subscription, you can skip the Office 365 E5 trial tenant creation steps.</span></span>

1. <span data-ttu-id="754bc-126">转到 [Office 365 E5 产品门户](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) ，并选择 " **免费试用版**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-126">Go to the [Office 365 E5 product portal](https://www.microsoft.com/microsoft-365/business/office-365-enterprise-e5-business-software?activetab=pivot%3aoverviewtab) and select **Free trial**.</span></span>

   ![Image of_Office 365 E5 免费试用页面](../../media/mtp-eval-9.png)
  
2. <span data-ttu-id="754bc-128">通过输入您的电子邮件地址 (个人或公司) 完成试用注册。</span><span class="sxs-lookup"><span data-stu-id="754bc-128">Complete the trial registration by entering your email address (personal or corporate).</span></span> <span data-ttu-id="754bc-129">单击 " **设置帐户**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-129">Click **Set up account**.</span></span>

   ![Image of_Office 365 E5 试用注册设置页](../../media/mtp-eval-10.png)

3. <span data-ttu-id="754bc-131">填写你的名字、姓氏、商务电话号码、公司名称、公司规模以及国家或地区。</span><span class="sxs-lookup"><span data-stu-id="754bc-131">Fill in your first name, last name, business phone number, company name, company size, and country or region.</span></span>  

   ![Image of_Office 365 E5 试用注册设置页面，要求输入姓名、电话和公司详细信息](../../media/mtp-eval-11.png)
   
   > [!NOTE]
   > <span data-ttu-id="754bc-133">您在此处设置的国家或地区决定了您的 Office 365 将托管的数据中心区域。</span><span class="sxs-lookup"><span data-stu-id="754bc-133">The country or region you set here determines the data center region your Office 365 will be hosted.</span></span>
  
4. <span data-ttu-id="754bc-134">选择您的验证首选项：通过短信或 call。</span><span class="sxs-lookup"><span data-stu-id="754bc-134">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="754bc-135">单击 " **发送验证代码**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-135">Click **Send Verification Code**.</span></span> 

   ![Image of_Office 365 E5 试用注册设置页面请求验证首选项](../../media/mtp-eval-12.png)

5. <span data-ttu-id="754bc-137">为租户设置自定义域名称，然后单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-137">Set the custom domain name for your tenant, then click **Next**.</span></span>

   ![Image of_Office 365 E5 试用注册安装程序页，您可以在其中设置自定义域名](../../media/mtp-eval-13.png)
 
6. <span data-ttu-id="754bc-139">设置第一个标识，这将成为租户的全局管理员。</span><span class="sxs-lookup"><span data-stu-id="754bc-139">Set up the first identity, which will be a Global Administrator for the tenant.</span></span> <span data-ttu-id="754bc-140">填写 " **名称** " 和 " **密码**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-140">Fill in **Name** and **Password**.</span></span> <span data-ttu-id="754bc-141">单击 " **注册**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-141">Click **Sign up**.</span></span>

   ![Image of_Office 365 E5 试用注册设置页，可在其中设置你的业务标识](../../media/mtp-eval-14.png)

7. <span data-ttu-id="754bc-143">单击 " **转到设置** " 以完成 Office 365 E5 试用租户设置。</span><span class="sxs-lookup"><span data-stu-id="754bc-143">Click **Go to Setup** to complete the Office 365 E5 trial tenant provisioning.</span></span>

   ![Office 365 E5 试用注册设置页面的图像提示单击 "转到设置" 按钮](../../media/mtp-eval-15.png)

8. <span data-ttu-id="754bc-145">将企业域连接到 Office 365 租户。</span><span class="sxs-lookup"><span data-stu-id="754bc-145">Connect your corporate domain to the Office 365 tenant.</span></span> <span data-ttu-id="754bc-146">Optional选择 " **连接您已拥有的域** "，并键入您的域名。</span><span class="sxs-lookup"><span data-stu-id="754bc-146">[Optional] Choose **Connect a domain you already own** and type in your domain name.</span></span> <span data-ttu-id="754bc-147">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="754bc-147">Click **Next**.</span></span>

   ![Image of_Office 365 E5 设置页面，您应在其中对登录和电子邮件进行个性化设置](../../media/mtp-eval-16.png)
 
9. <span data-ttu-id="754bc-149">添加 TXT 或 MX 记录以验证域所有权。</span><span class="sxs-lookup"><span data-stu-id="754bc-149">Add a TXT or MX record to validate the domain ownership.</span></span> <span data-ttu-id="754bc-150">将 TXT 或 MX 记录添加到域后，选择 " **验证**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-150">Once you’ve added the TXT or MX record to your domain, select **Verify**.</span></span>

   ![Image of_Office 365 E5 安装程序页，您应在其中添加 TXT 条 MX 记录以验证您的域](../../media/mtp-eval-17.png)
 
10. <span data-ttu-id="754bc-152">Optional为你的租户创建更多用户帐户。</span><span class="sxs-lookup"><span data-stu-id="754bc-152">[Optional] Create more user accounts for your tenant.</span></span> <span data-ttu-id="754bc-153">您可以通过单击 " **下一步**" 跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="754bc-153">You can skip this step by clicking **Next**.</span></span>

    ![Image of_Office 365 E5 安装程序页，您可以在其中添加更多用户](../../media/mtp-eval-18.png)
 
11. <span data-ttu-id="754bc-155">Optional下载 Office 应用。</span><span class="sxs-lookup"><span data-stu-id="754bc-155">[Optional] Download Office apps.</span></span> <span data-ttu-id="754bc-156">单击 " **下一步** " 跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="754bc-156">Click **Next** to skip this step.</span></span> 

    ![可在其中安装 Office 应用程序的 "图像 of_Office 365 E5" 页面](../../media/mtp-eval-19.png)

12. <span data-ttu-id="754bc-158">Optional迁移电子邮件。</span><span class="sxs-lookup"><span data-stu-id="754bc-158">[Optional] Migrate email messages.</span></span> <span data-ttu-id="754bc-159">同样，您可以跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="754bc-159">Again, you can skip this step.</span></span>

    ![图像 of_Office 365 E5，您可以在其中设置是否迁移电子邮件](../../media/mtp-eval-20.png)
 
13. <span data-ttu-id="754bc-161">选择 "在线服务"。</span><span class="sxs-lookup"><span data-stu-id="754bc-161">Choose online services.</span></span> <span data-ttu-id="754bc-162">选择 " **Exchange** " 并单击 " **下一步**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-162">Select **Exchange** and click **Next**.</span></span> 

    ![可以在其中选择在线服务的图像 of_Office 365 E5](../../media/mtp-eval-21.png)

14. <span data-ttu-id="754bc-164">向您的域中添加 MX、CNAME 和 TXT 记录。</span><span class="sxs-lookup"><span data-stu-id="754bc-164">Add MX, CNAME, and TXT records to your domain.</span></span> <span data-ttu-id="754bc-165">完成后，选择 " **验证**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-165">When completed, select **Verify**.</span></span>

    ![Image of_Office 365 E5 在这里，你可以添加 DNS 记录](../../media/mtp-eval-22.png)
 
15. <span data-ttu-id="754bc-167">恭喜，你已完成 Office 365 租户的预配。</span><span class="sxs-lookup"><span data-stu-id="754bc-167">Congratulations, you have completed the provisioning of your Office 365 tenant.</span></span>

    ![Image of_Office 365 E5 安装程序完成确认页](../../media/mtp-eval-23.png)

## <a name="enable-microsoft-365-trial-subscription"></a><span data-ttu-id="754bc-169">启用 Microsoft 365 试用订阅</span><span class="sxs-lookup"><span data-stu-id="754bc-169">Enable Microsoft 365 trial subscription</span></span>

>[!NOTE]
><span data-ttu-id="754bc-170">注册试用版将提供25个用户许可证用于一个月。</span><span class="sxs-lookup"><span data-stu-id="754bc-170">Signing up for a trial gives you 25 user licenses to use for a month.</span></span> <span data-ttu-id="754bc-171">有关详细信息，请参阅 [试用或购买 M365 订阅](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) 。</span><span class="sxs-lookup"><span data-stu-id="754bc-171">See [Try or Buy an M365 subscription](https://docs.microsoft.com/microsoft-365/commerce/try-or-buy-microsoft-365#try-or-buy-a-microsoft-365-subscription-1) for details.</span></span>

1. <span data-ttu-id="754bc-172">从 [Microsoft 365 管理中心](https://admin.microsoft.com/)，单击 " **帐单** "，然后导航到 " **购买服务**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-172">From [Microsoft 365 Admin Center](https://admin.microsoft.com/), click **Billing** and then navigate to **Purchase services**.</span></span>

2. <span data-ttu-id="754bc-173">选择 " **Microsoft 365 E5** "，然后单击 " **开始免费试用**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-173">Select **Microsoft 365 E5** and click **Start free trial**.</span></span> 

   ![Image of_Microsoft 365 E5 开始免费试用页面](../../media/mtp-eval-24.png)

3. <span data-ttu-id="754bc-175">选择您的验证首选项：通过短信或 call。</span><span class="sxs-lookup"><span data-stu-id="754bc-175">Choose your verification preference: through a text message or call.</span></span> <span data-ttu-id="754bc-176">确定后，请输入电话号码，选择 " **文本** " 或 " **呼叫我** "，具体取决于你的选择。</span><span class="sxs-lookup"><span data-stu-id="754bc-176">Once you have decided, enter the phone number, select **Text me** or **Call me** depending on your selection.</span></span>

   ![Image of_Microsoft 365 E5 开始免费试用页面，请求联系详细信息，以证明你不是机器人](../../media/mtp-eval-25.png)
 
4. <span data-ttu-id="754bc-178">输入验证代码，然后单击 " **开始免费试用**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-178">Enter the verification code and click **Start your free trial**.</span></span>

   ![Image of_Microsoft 365 E5 开始免费试用页面，您可以在其中填写验证代码，以证明您不是机器人的系统](../../media/mtp-eval-26.png)

5. <span data-ttu-id="754bc-180">单击 " **立即试用** " 以确认你的 Microsoft 365 E5 试用版。</span><span class="sxs-lookup"><span data-stu-id="754bc-180">Click **Try now** to confirm your Microsoft 365 E5 trial.</span></span>

   ![Image of_Microsoft 365 E5 开始免费试用页面，应在此处时钟 "立即试用" 按钮开始](../../media/mtp-eval-27.png)
 
6. <span data-ttu-id="754bc-182">转到 **Microsoft 365 管理中心**  >  **用户**  >  **活动用户**。</span><span class="sxs-lookup"><span data-stu-id="754bc-182">Go to the **Microsoft 365 Admin Center** > **Users** > **Active users**.</span></span> <span data-ttu-id="754bc-183">选择您的用户帐户，选择 " **管理产品许可证**"，然后将来自 Office 365 e5 的许可证交换为 **Microsoft 365 e5**。</span><span class="sxs-lookup"><span data-stu-id="754bc-183">Select your user account, select **Manage product licenses**, then swap the license from Office 365 E5 to **Microsoft 365 E5**.</span></span> <span data-ttu-id="754bc-184">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="754bc-184">Click **Save**.</span></span>

   ![Image of_Microsoft 365 管理中心 "页面，您可以在其中选择 Microsoft 365 E5 许可证](../../media/mtp-eval-28.png)
 
7. <span data-ttu-id="754bc-186">再次选择全局管理员帐户，然后单击 " **管理用户名**"。</span><span class="sxs-lookup"><span data-stu-id="754bc-186">Select the global administrator account again then click **Manage username**.</span></span>

   ![Image of_Microsoft 365 管理中心 "页面，您可以在其中选择" 帐户 "，然后管理用户名](../../media/mtp-eval-29.png)

8. <span data-ttu-id="754bc-188">Optional将域从 *onmicrosoft.com* 更改为您自己的域，具体取决于您在前面步骤中选择的内容。</span><span class="sxs-lookup"><span data-stu-id="754bc-188">[Optional] Change the domain from *onmicrosoft.com* to your own domain—depending on what you chose on the previous steps.</span></span> <span data-ttu-id="754bc-189">单击 **保存更改**。</span><span class="sxs-lookup"><span data-stu-id="754bc-189">Click **Save changes**.</span></span>

   ![图像 of_Microsoft 365 管理中心 "页，您可以在其中更改您的域首选项](../../media/mtp-eval-30.png)



## <a name="next-step"></a><span data-ttu-id="754bc-191">后续步骤</span><span class="sxs-lookup"><span data-stu-id="754bc-191">Next step</span></span>
|[<span data-ttu-id="754bc-192">第3阶段： Configure & 板载</span><span class="sxs-lookup"><span data-stu-id="754bc-192">Phase 3: Configure & Onboard</span></span>](config-mtpeval.md) | <span data-ttu-id="754bc-193">为 Microsoft 365 Defender 试用版实验室或试点环境配置每个 Microsoft 365 Defender 支柱，并将终结点集成在一起。</span><span class="sxs-lookup"><span data-stu-id="754bc-193">Configure each Microsoft 365 Defender pillar for your Microsoft 365 Defender trial lab or pilot environment and onboard your endpoints.</span></span>
|:-------|:-----|
