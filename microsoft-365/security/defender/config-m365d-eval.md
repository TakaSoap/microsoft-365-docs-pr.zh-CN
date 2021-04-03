---
title: 为试用实验室或试验环境配置 Microsoft 365 Defender 支柱
description: 为试用实验室或试验环境配置 Microsoft 365 Defender 支柱，如 Microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft Cloud App Security 和 Microsoft Defender for Endpoint。
keywords: 配置 Microsoft 威胁防护试用版， Microsoft 威胁防护试用配置， 配置 Microsoft 威胁防护试点项目， 配置 Microsoft 威胁防护支柱， Microsoft 威胁防护支柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 9b192a029704d1354867b169efdf0d489345030e
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51580962"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="a6bd6-104">为试用实验室或试验环境配置 Microsoft 365 Defender 支柱</span><span class="sxs-lookup"><span data-stu-id="a6bd6-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="a6bd6-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="a6bd6-105">**Applies to:**</span></span>
- <span data-ttu-id="a6bd6-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="a6bd6-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="a6bd6-107">创建 Microsoft 365 Defender 试用实验室或试验环境并部署它的过程分三个阶段：</span><span class="sxs-lookup"><span data-stu-id="a6bd6-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

|<span data-ttu-id="a6bd6-108">[![阶段 1：准备](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span><span class="sxs-lookup"><span data-stu-id="a6bd6-108">[![Phase 1: Prepare](../../media/phase-diagrams/prepare.png)](prepare-m365d-eval.md)</span></span><br/>[<span data-ttu-id="a6bd6-109">阶段 1：准备</span><span class="sxs-lookup"><span data-stu-id="a6bd6-109">Phase 1: Prepare</span></span>](prepare-m365d-eval.md) |<span data-ttu-id="a6bd6-110">[![阶段 2：设置](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span><span class="sxs-lookup"><span data-stu-id="a6bd6-110">[![Phase 2: Set up](../../media/phase-diagrams/setup.png)](setup-m365deval.md)</span></span><br/>[<span data-ttu-id="a6bd6-111">阶段 2：设置</span><span class="sxs-lookup"><span data-stu-id="a6bd6-111">Phase 2: Set up</span></span>](setup-m365deval.md) |![阶段 3：开始使用](../../media/phase-diagrams/onboard.png)<br/><span data-ttu-id="a6bd6-113">阶段 3：开始使用</span><span class="sxs-lookup"><span data-stu-id="a6bd6-113">Phase 3: Onboard</span></span> | <span data-ttu-id="a6bd6-114">[![返回到试点](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span><span class="sxs-lookup"><span data-stu-id="a6bd6-114">[![Back to pilot](../../media/phase-diagrams/backtopilot.png)](m365d-pilot.md)</span></span><br/>[<span data-ttu-id="a6bd6-115">返回到试点手册</span><span class="sxs-lookup"><span data-stu-id="a6bd6-115">Back to pilot playbook</span></span>](m365d-pilot.md) |
|--|--|--|--|
|| |<span data-ttu-id="a6bd6-116">*你在这里！*</span><span class="sxs-lookup"><span data-stu-id="a6bd6-116">*You are here!*</span></span> | |

<span data-ttu-id="a6bd6-117">你当前处于配置阶段。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-117">You're currently in the configuration phase.</span></span>

<span data-ttu-id="a6bd6-118">准备工作是任何成功部署的关键。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-118">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="a6bd6-119">本文将指导你在准备部署适用于终结点的 Microsoft Defender 时需要考虑的要点。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-119">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="a6bd6-120">Microsoft 365 Defender 支柱</span><span class="sxs-lookup"><span data-stu-id="a6bd6-120">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="a6bd6-121">Microsoft 365 Defender 由四大支柱组成。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-121">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="a6bd6-122">尽管一个支柱已经可为网络组织的安全性提供价值，但启用四个 Microsoft 365 Defender 支柱将为组织提供最大价值。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-122">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![适用于of_Microsoft、Microsoft Defender for Identity、终结点 Microsoft Defender for Endpoint、云应用、Microsoft Cloud App Security 和数据、Microsoft Defender for Office 365 的 365 Defender 解决方案的图像](../../media/mtp/m365pillars.png)

<span data-ttu-id="a6bd6-124">本部分将指导你配置：</span><span class="sxs-lookup"><span data-stu-id="a6bd6-124">This section will guide you to configure:</span></span>
-   <span data-ttu-id="a6bd6-125">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a6bd6-125">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="a6bd6-126">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="a6bd6-126">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="a6bd6-127">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a6bd6-127">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="a6bd6-128">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a6bd6-128">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="a6bd6-129">配置 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="a6bd6-129">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="a6bd6-130">如果你已启用 Office 365 的 Defender，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-130">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="a6bd6-131">有一个称为 *Office 365* 高级威胁防护建议配置分析器 (ORCA) 的 PowerShell 模块，可帮助确定其中一些设置。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-131">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="a6bd6-132">在租户中以管理员角色运行时，get-ORCAReport 将有助于生成对反垃圾邮件、防钓鱼和其他邮件安全设置的评估。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-132">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="a6bd6-133">可以从 下载此模块 https://www.powershellgallery.com/packages/ORCA/ 。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-133">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="a6bd6-134">导航到 [Office 365 安全&合规](https://protection.office.com/homepage)  >  **中心威胁管理**  >  **策略**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-134">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![图像of_Office 365 安全&中心威胁管理策略页面](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="a6bd6-136">单击 **"防钓鱼"，** 选择" **创建** "并填写策略名称和说明。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-136">Click **Anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="a6bd6-137">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-137">Click **Next**.</span></span>

   ![图像of_Office 365 安全&合规中心防钓鱼策略页面，可在其中命名策略](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="a6bd6-139">在 Microsoft Defender for Office 365 中编辑高级防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-139">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="a6bd6-140">将 **高级网络钓鱼阈值更改为** **2 - 攻击性**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-140">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="a6bd6-141">单击" **添加条件** "下拉菜单，然后选择您的域 (") "收件人域"。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-141">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="a6bd6-142">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-142">Click **Next**.</span></span>

   ![图像of_Office 365 安全&合规中心防钓鱼策略页面，您可以在其中添加其应用程序的条件](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="a6bd6-144">查看设置。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-144">Review your settings.</span></span> <span data-ttu-id="a6bd6-145">单击 **"创建此策略** "以确认。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-145">Click **Create this policy** to confirm.</span></span> 

   ![图像of_Office 365 安全&合规中心防钓鱼策略页面，可在其中查看设置并单击"创建此策略"按钮](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="a6bd6-147">选择 **"安全附件** "，然后选择"启用 **适用于 SharePoint、OneDrive** 和 Microsoft Teams 的 ATP"选项。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-147">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![图像of_Office 365 安全&合规中心页面，可在其中打开适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP](../../media/mtp-eval-36.png)

6. <span data-ttu-id="a6bd6-149">单击 + 图标以创建新的安全附件策略，以作为收件人域应用到你的域。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-149">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="a6bd6-150">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-150">Click **Save**.</span></span>

   !["of_Office 365 安全&合规中心"页面，可在其中创建新的新建安全附件策略](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="a6bd6-152">接下来，选择 **安全链接** 策略，然后单击铅笔图标以编辑默认策略。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-152">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="a6bd6-153">确保未选中" **不跟踪用户** 单击安全链接时"选项，同时选择其余选项。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-153">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="a6bd6-154">有关详细信息 [，请参阅安全](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) 链接设置。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-154">See [Safe Links settings](/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365) for details.</span></span> <span data-ttu-id="a6bd6-155">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-155">Click **Save**.</span></span> 

   !["of_Office 365 安全&中心"页面，其中显示未选中"不跟踪用户单击时安全"选项](../../media/mtp-eval-38.png)

9. <span data-ttu-id="a6bd6-157">接下来， **选择"反恶意软件"** 策略，选择默认值，然后选择铅笔图标。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-157">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="a6bd6-158">单击 **"设置\*\*\*\*"，选择"是**"，然后使用默认通知文本启用 **恶意软件检测响应**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-158">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="a6bd6-159">打开 **"常见附件类型筛选器** "。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-159">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="a6bd6-160">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-160">Click **Save**.</span></span>

    !["of_Office 365 安全&合规中心"页面，其中显示恶意软件检测响应已打开且默认通知和常用附件类型筛选器已打开](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="a6bd6-162">导航到 [Office 365 安全](https://protection.office.com/homepage)&  >  **中心搜索**  >  **审核日志搜索** 并启用审核。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    !["of_Office 365 安全与&中心"页面，可在其中打开审核日志搜索](../../media/mtp-eval-40.png)

12. <span data-ttu-id="a6bd6-164">将适用于 Office 365 的 Microsoft Defender 与 Microsoft Defender for Endpoint 集成。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-164">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a6bd6-165">导航到 ["Office 365 安全](https://protection.office.com/homepage)与&中心威胁管理资源管理器"，然后选择屏幕右上角的"适用于终结点设置的  >    >  **Microsoft Defender"。**</span><span class="sxs-lookup"><span data-stu-id="a6bd6-165">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="a6bd6-166">在 Defender for Endpoint 连接对话框中，打开 **连接到 Microsoft Defender for Endpoint**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-166">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    !["of_Office 365 安全&合规中心"页面，可在其中打开 Microsoft Defender for Endpoint 连接](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="a6bd6-168">为标识配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="a6bd6-168">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="a6bd6-169">如果已启用 Microsoft Defender 标识，则跳过此步骤</span><span class="sxs-lookup"><span data-stu-id="a6bd6-169">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="a6bd6-170">导航到 [Microsoft 365](https://security.microsoft.com/info)安全中心 **>选择更多** Microsoft Defender  >  **标识资源**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-170">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![图像of_Microsoft 365 安全中心页面，其中提供打开 Microsoft Defender for Identity 的选项](../../media/mtp-eval-42.png)

2. <span data-ttu-id="a6bd6-172">单击 **创建** 以启动 Microsoft Defender 标识向导。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-172">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   !["of_Microsoft Defender for Identity 向导"页面，应单击"创建"按钮](../../media/mtp-eval-43.png)

3. <span data-ttu-id="a6bd6-174">选择 **"提供用户名和密码"以连接到 Active Directory 林**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-174">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![图像of_Microsoft Defender for Identity 欢迎页面](../../media/mtp-eval-44.png)

4. <span data-ttu-id="a6bd6-176">输入 Active Directory 本地凭据。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-176">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="a6bd6-177">这可以是对 Active Directory 具有读取权限的任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-177">This can be any user account that has read access to Active Directory.</span></span>

   ![Image of_Microsoft Defender for Identity Directory services 页面，你应该将凭据放在其中](../../media/mtp-eval-45.png)

5. <span data-ttu-id="a6bd6-179">接下来，选择 **"下载传感器设置** "，将文件传输至域控制器。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-179">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![Image of_Microsoft Defender for Identity 页面，可在其中选择下载传感器设置](../../media/mtp-eval-46.png)

6. <span data-ttu-id="a6bd6-181">执行 Microsoft Defender for Identity 传感器设置并开始遵循向导。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-181">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Image of_Microsoft Defender for Identity 页面，你应单击旁边的页面，按照 Microsoft Defender for Identity 传感器向导操作](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="a6bd6-183">在 **传感器** 部署类型上单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-183">Click **Next** at the sensor deployment type.</span></span>

   ![Image of_Microsoft Defender for Identity 页面，你应单击下一步转到下一页](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="a6bd6-185">复制访问键，因为你需要在向导中下一步输入它。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-185">Copy the access key because you need to enter it next in the Wizard.</span></span>

   ![映像of_the"传感器"页面，应在其中复制需要在下一个 Microsoft Defender for Identity 传感器设置向导页中输入的访问密钥](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="a6bd6-187">将访问键复制到向导中，**然后单击安装。**</span><span class="sxs-lookup"><span data-stu-id="a6bd6-187">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![映像of_Microsoft Defender for Identity 传感器向导页面，你应该提供访问密钥，然后单击安装按钮](../../media/mtp-eval-50.png)

10. <span data-ttu-id="a6bd6-189">恭喜！已成功在域控制器上配置 Microsoft Defender 的 Identity。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-189">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft Defender for Identity sensor wizard installation completion where you should click the finish button](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="a6bd6-191">在 ["Microsoft Defender 标识设置](https://go.microsoft.com/fwlink/?linkid=2040449) "部分下，选择\*\*Microsoft Defender for Endpoint \*\*，然后打开切换。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-191">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="a6bd6-192">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-192">Click **Save**.</span></span> 

    ![适用于of_the Microsoft Defender 的"设置"页面的图像，应在其中打开 Microsoft Defender for Endpoint 切换](../../media/mtp-eval-52.png)

> [!NOTE]
> <span data-ttu-id="a6bd6-194">Windows Defender ATP 已重新品牌为 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-194">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a6bd6-195">为了一致性，将推出我们所有门户中的品牌更改。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-195">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="a6bd6-196">配置 Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="a6bd6-196">Configure Microsoft Cloud App Security</span></span>

> [!NOTE]
> <span data-ttu-id="a6bd6-197">如果你已启用 Microsoft Cloud App Security，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-197">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="a6bd6-198">导航到 [Microsoft 365 安全中心](https://security.microsoft.com/info)  >  **更多**  >  **资源 Microsoft Cloud App Security**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-198">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![图像of_Microsoft 365 安全中心页面，可在其中看到 Microsoft 云应用卡，并单击打开按钮](../../media/mtp-eval-53.png)

2. <span data-ttu-id="a6bd6-200">在集成 Microsoft Defender 标识的信息提示符下，选择 **启用 Microsoft Defender 的标识数据集成**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-200">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![图像of_the信息提示，用于集成 Microsoft Defender for Identity，其中应选择"启用 Microsoft Defender for Identity 数据集成"链接](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="a6bd6-202">如果看不到此提示，这可能意味着 Microsoft Defender for Identity 数据集成已启用。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-202">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="a6bd6-203">但是，如果您不确定，请与 IT 管理员联系以确认。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-203">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="a6bd6-204">转到设置，打开 **Microsoft Defender 的标识集成** 切换，然后单击 **保存。**</span><span class="sxs-lookup"><span data-stu-id="a6bd6-204">Go to **Settings**, turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   ![图像of_the设置页面，其中你应打开 Microsoft Defender for Identity 集成切换，然后单击保存](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="a6bd6-206">对于新的 Microsoft Defender for Identity 实例，此集成切换将自动打开。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-206">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="a6bd6-207">在继续执行下一步之前，请确认 Microsoft Defender for Identity 集成已启用。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-207">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="a6bd6-208">在云发现设置下，选择 **Microsoft Defender 进行终结点集成**，然后启用集成。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-208">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration**, then enable the integration.</span></span> <span data-ttu-id="a6bd6-209">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-209">Click **Save**.</span></span>

   ![图像of_the Microsoft Defender for Endpoint 页面，其中选中了 Microsoft Defender for Endpoint 集成下的阻止未批准应用复选框。](../../media/mtp-eval-56.png)

5. <span data-ttu-id="a6bd6-212">在"云发现设置"下，选择"用户 **扩充**"，然后启用与 Azure Active Directory 的集成。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-212">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>

   ![用户扩充部分的图像，其中选中了"使用 Azure Active Directory 用户名丰富发现的用户标识符" 复选框](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="a6bd6-214">配置 Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="a6bd6-214">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="a6bd6-215">如果你已启用适用于终结点的 Microsoft Defender，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-215">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="a6bd6-216">导航到 [Microsoft 365 安全中心](https://security.microsoft.com/info)  >  **更多**  >  **资源 Microsoft Defender 安全中心**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-216">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="a6bd6-217">单击“打开”。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-217">Click **Open**.</span></span>

   ![Microsoft 365 安全中心of_Microsoft Defender 安全中心选项的图像](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="a6bd6-219">按照 Microsoft Defender for Endpoint 向导操作。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-219">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="a6bd6-220">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-220">Click **Next**.</span></span> 

   ![映像of_the Microsoft Defender 安全中心欢迎向导页面](../../media/mtp-eval-59.png)

3. <span data-ttu-id="a6bd6-222">根据首选数据存储位置、数据保留策略、组织规模和选择加入预览功能进行选择。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-222">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   ![图像of_the页面，用于选择数据存储国家/地区、保留策略和组织规模。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="a6bd6-225">之后，你无法更改某些设置，如数据存储位置。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-225">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="a6bd6-226">单击"下一步"。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-226">Click **Next**.</span></span> 

4. <span data-ttu-id="a6bd6-227">单击 **"继续** "，它将预配适用于终结点租户的 Microsoft Defender。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-227">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![图像of_the提示您单击"继续"按钮以创建云实例的页面](../../media/mtp-eval-61.png)

5. <span data-ttu-id="a6bd6-229">通过组策略、Microsoft Endpoint Manager 或运行 Microsoft Defender for Endpoint 的本地脚本载入终结点。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-229">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="a6bd6-230">为简单起见，本指南使用本地脚本。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-230">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="a6bd6-231">单击 **下载程序包** ，将载入脚本复制到你的 (程序包) 。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-231">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![提示of_page下载程序包按钮以将载入脚本复制到终结点的图像](../../media/mtp-eval-62.png)

7. <span data-ttu-id="a6bd6-233">在终结点上，以管理员角色运行载入脚本并选择"Y"。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-233">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![图像of_the运行载入脚本并选择"Y"继续操作命令行](../../media/mtp-eval-63.png)

8. <span data-ttu-id="a6bd6-235">恭喜，你已载入你的第一个终结点。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-235">Congratulations, you've onboarded your first endpoint.</span></span>

   ![图像of_the命令行，可获取已载入第一终结点的确认信息。](../../media/mtp-eval-64.png)

9. <span data-ttu-id="a6bd6-238">从 Microsoft Defender for Endpoint 向导复制粘贴检测测试。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-238">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![图像of_the运行检测测试步骤，其中应单击"复制"复制应粘贴到命令提示符中的检测测试脚本](../../media/mtp-eval-65.png)

10. <span data-ttu-id="a6bd6-240">将 PowerShell 脚本复制到提升的命令提示符并运行它。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-240">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![图像of_command提示符，应在其中将 PowerShell 脚本复制到提升的命令提示符并运行它](../../media/mtp-eval-66.png)

11. <span data-ttu-id="a6bd6-242">从 **向导中选择开始使用 Microsoft Defender for Endpoint。**</span><span class="sxs-lookup"><span data-stu-id="a6bd6-242">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![图像of_the显示来自向导的确认提示，你应单击"开始使用 Microsoft Defender for Endpoint"](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="a6bd6-244">访问 [Microsoft Defender 安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-244">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="a6bd6-245">转到"**设置"，** 然后选择"**高级功能"。**</span><span class="sxs-lookup"><span data-stu-id="a6bd6-245">Go to **Settings** and then select **Advanced features**.</span></span> 

    !["of_Microsoft Defender 安全中心设置"菜单，其中应选择"高级功能"](../../media/mtp-eval-68.png)

13. <span data-ttu-id="a6bd6-247">打开与 Microsoft **Defender 的 Identity 集成**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-247">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![映像of_Microsoft Defender 安全中心高级功能，需要打开的 Microsoft Defender for Identity 选项切换](../../media/mtp-eval-69.png)

14. <span data-ttu-id="a6bd6-249">打开与 Office **365 威胁智能的集成**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-249">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![需要of_Microsoft Defender 安全中心高级功能、Office 365 威胁智能选项切换的图像](../../media/mtp-eval-70.png)

15. <span data-ttu-id="a6bd6-251">打开与 **Microsoft Cloud App Security 的集成**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-251">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![需要of_Microsoft Defender 安全中心高级功能、Microsoft Cloud App Security 选项切换的图像](../../media/mtp-eval-71.png)

16. <span data-ttu-id="a6bd6-253">向下滚动并单击 **"保存首选项** "以确认新的集成。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-253">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![需要of_Save图像首选项按钮](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="a6bd6-255">启动 Microsoft 365 Defender 服务</span><span class="sxs-lookup"><span data-stu-id="a6bd6-255">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="a6bd6-256">从 2020 年 6 月 1 开始，Microsoft 会自动为所有符合条件的租户启用 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-256">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="a6bd6-257">有关详细信息， [请参阅此有关许可证资格的 Microsoft 技术](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 社区文章。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-257">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="a6bd6-258">转到 [Microsoft 365 安全中心](https://security.microsoft.com/homepage)。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-258">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="a6bd6-259">导航到 **设置** ，然后选择 **Microsoft 365 Defender**。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-259">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="a6bd6-260">Microsoft 365 安全中心设置页of_Microsoft 365 Defender 选项屏幕截图的图像</span><span class="sxs-lookup"><span data-stu-id="a6bd6-260">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="a6bd6-261">有关更全面的指南，请参阅打开[Microsoft 365 Defender。](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="a6bd6-261">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](m365d-enable.md).</span></span> 

<span data-ttu-id="a6bd6-262">恭喜！</span><span class="sxs-lookup"><span data-stu-id="a6bd6-262">Congratulations!</span></span> <span data-ttu-id="a6bd6-263">你刚刚创建了 Microsoft 365 Defender 试用实验室或试验环境！</span><span class="sxs-lookup"><span data-stu-id="a6bd6-263">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="a6bd6-264">现在，你可以熟悉 Microsoft 365 Defender 用户界面！</span><span class="sxs-lookup"><span data-stu-id="a6bd6-264">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="a6bd6-265">查看你可以从以下 Microsoft 365 Defender 交互式指南中了解哪些内容，并了解如何使用每个仪表板执行日常安全操作任务。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-265">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>

[<span data-ttu-id="a6bd6-266">查看交互式指南</span><span class="sxs-lookup"><span data-stu-id="a6bd6-266">Check out the interactive guide</span></span>](https://aka.ms/MTP-Interactive-Guide)

<span data-ttu-id="a6bd6-267">接下来，你可以模拟攻击，并查看跨产品功能如何检测、创建警报以及自动响应终结点上的无文件攻击。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-267">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="a6bd6-268">后续步骤</span><span class="sxs-lookup"><span data-stu-id="a6bd6-268">Next step</span></span>

- <span data-ttu-id="a6bd6-269">[生成测试警报](generate-test-alert.md) - 在 Microsoft 365 Defender 试用实验室中运行攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="a6bd6-269">[Generate a test alert](generate-test-alert.md) - Run an attack simulation in your Microsoft 365 Defender trial lab.</span></span>