---
title: 为试用版实验室或试点环境配置 Microsoft 365 Defender 支柱
description: 为你的试用实验室或试点环境配置 Microsoft 365 Defender 支柱，例如 Microsoft Defender for Office 365、Microsoft Defender for Identity、Microsoft 云应用安全和 Microsoft Defender for Endpoint。
keywords: 配置 Microsoft 威胁防护试用版，Microsoft 威胁防护试用版配置，配置 Microsoft 威胁 Protection 试点项目，配置 Microsoft 威胁防护支柱，Microsoft 威胁防护支柱
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
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
ms.openlocfilehash: 88db2182ec1a3250d2f4308858026fec97a2f91b
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844100"
---
# <a name="configure-microsoft-365-defender-pillars-for-your-trial-lab-or-pilot-environment"></a><span data-ttu-id="00c9b-104">为试用版实验室或试点环境配置 Microsoft 365 Defender 支柱</span><span class="sxs-lookup"><span data-stu-id="00c9b-104">Configure Microsoft 365 Defender pillars for your trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="00c9b-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="00c9b-105">**Applies to:**</span></span>
- <span data-ttu-id="00c9b-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="00c9b-106">Microsoft 365 Defender</span></span>


<span data-ttu-id="00c9b-107">创建 Microsoft 365 Defender 试用版实验室或试点环境并对其进行部署的过程分为三个阶段：</span><span class="sxs-lookup"><span data-stu-id="00c9b-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab or pilot environment" title="准备 Microsoft 365 Defender 试用版实验室或试点环境" />
      <br/><span data-ttu-id="00c9b-109">第1阶段：准备 </a></span><span class="sxs-lookup"><span data-stu-id="00c9b-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab or pilot environment" title="设置你的 Microsoft 365 Defender 试用版实验室或试点环境" />
      <br/><span data-ttu-id="00c9b-111">阶段2：安装程序 </a></span><span class="sxs-lookup"><span data-stu-id="00c9b-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="为 Microsoft 365 Defender 试用版实验室或试点环境以及板载终结点配置每个 Microsoft 365 Defender 支柱" />
      <br/><span data-ttu-id="00c9b-113">第3阶段： Configure & 板载 </a></span><span class="sxs-lookup"><span data-stu-id="00c9b-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>
  </tr>
</table>

<span data-ttu-id="00c9b-114">你当前正在配置阶段。</span><span class="sxs-lookup"><span data-stu-id="00c9b-114">You're currently in the configuration phase.</span></span>


<span data-ttu-id="00c9b-115">准备工作是任何成功部署的关键。</span><span class="sxs-lookup"><span data-stu-id="00c9b-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="00c9b-116">在本文中，你将指导你在准备部署 Microsoft Defender for Endpoint 时需要考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="00c9b-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender for Endpoint.</span></span>


## <a name="microsoft-365-defender-pillars"></a><span data-ttu-id="00c9b-117">Microsoft 365 Defender 支柱</span><span class="sxs-lookup"><span data-stu-id="00c9b-117">Microsoft 365 Defender pillars</span></span>
<span data-ttu-id="00c9b-118">Microsoft 365 Defender 由四个支柱组成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-118">Microsoft 365 Defender consists of four pillars.</span></span> <span data-ttu-id="00c9b-119">尽管一个支柱可以为你的网络组织的安全性提供价值，但启用四个 Microsoft 365 Defender 个支柱将为你的组织提供最大价值。</span><span class="sxs-lookup"><span data-stu-id="00c9b-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft 365 Defender pillars will give your organization the most value.</span></span>

![Image of_Microsoft 365 Defender 解决方案，适用于用户、Microsoft Defender for a Endpoint for Microsoft Defender for Endpoint、云应用、Microsoft 云应用安全性和数据、Microsoft Defender for Office 365](../../media/mtp-eval-31.png)

<span data-ttu-id="00c9b-121">本部分将指导您配置：</span><span class="sxs-lookup"><span data-stu-id="00c9b-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="00c9b-122">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="00c9b-122">Microsoft Defender for Office 365</span></span>
-   <span data-ttu-id="00c9b-123">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="00c9b-123">Microsoft Defender for Identity</span></span> 
-   <span data-ttu-id="00c9b-124">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="00c9b-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="00c9b-125">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="00c9b-125">Microsoft Defender for Endpoint</span></span>


## <a name="configure-microsoft-defender-for-office-365"></a><span data-ttu-id="00c9b-126">配置 Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="00c9b-126">Configure Microsoft Defender for Office 365</span></span>

>[!NOTE]
><span data-ttu-id="00c9b-127">如果已经启用了适用于 Office 365 的 Defender，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="00c9b-127">Skip this step if you've already enabled Defender for Office 365.</span></span> 

<span data-ttu-id="00c9b-128">有一个 PowerShell 模块称为 *Office 365 高级威胁防护建议的配置分析器 (ORCA)* ，可帮助确定其中一些设置。</span><span class="sxs-lookup"><span data-stu-id="00c9b-128">There's a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="00c9b-129">在租户中以管理员身份运行时，ORCAReport 将帮助生成反垃圾邮件、反网络钓鱼和其他邮件清洁设置的评估。</span><span class="sxs-lookup"><span data-stu-id="00c9b-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="00c9b-130">您可以从下载此模块 https://www.powershellgallery.com/packages/ORCA/ 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="00c9b-131">导航到 [Office 365 Security & 合规性中心](https://protection.office.com/homepage)  >  **威胁管理**  >  **策略** 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>

   ![Image of_Office 365 Security & 合规性中心威胁管理策略页](../../media/mtp-eval-32.png)
 
2. <span data-ttu-id="00c9b-133">单击 " **反网络钓鱼** "，选择 " **创建** 并填写策略名称和说明"。</span><span class="sxs-lookup"><span data-stu-id="00c9b-133">Click **Anti-phishing** , select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="00c9b-134">单击“ **下一步** ”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-134">Click **Next**.</span></span>

   ![Image of_Office 365 Security & 合规中心 "反网络钓鱼策略" 页，可在其中命名策略](../../media/mtp-eval-33.png)

   > [!NOTE]
   > <span data-ttu-id="00c9b-136">在 Microsoft Defender for Office 365 中编辑高级反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="00c9b-136">Edit your Advanced anti-phishing policy in Microsoft Defender for Office 365.</span></span> <span data-ttu-id="00c9b-137">将 **高级网络钓鱼阈值** 更改为 **2-主动** 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>

3. <span data-ttu-id="00c9b-138">单击 " **添加条件** " 下拉菜单，并选择您的域 (s) 作为 "收件人域"。</span><span class="sxs-lookup"><span data-stu-id="00c9b-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="00c9b-139">单击“ **下一步** ”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-139">Click **Next**.</span></span>

   ![Image of_Office 365 Security & 合规中心 "反网络钓鱼策略" 页，可在其中为其应用程序添加条件](../../media/mtp-eval-34.png)
 
4. <span data-ttu-id="00c9b-141">查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="00c9b-141">Review your settings.</span></span> <span data-ttu-id="00c9b-142">单击 " **创建此策略** " 以确认。</span><span class="sxs-lookup"><span data-stu-id="00c9b-142">Click **Create this policy** to confirm.</span></span> 

   ![Image of_Office 365 Security & 合规性中心 "反网络钓鱼策略" 页，您可以在其中查看设置，然后单击 "创建此策略" 按钮](../../media/mtp-eval-35.png)
 
5. <span data-ttu-id="00c9b-144">选择 " **安全附件** "，然后选择 " **启用 SharePoint、OneDrive 和 MICROSOFT 团队的 ATP** " 选项。</span><span class="sxs-lookup"><span data-stu-id="00c9b-144">Select **Safe Attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>

   ![Image of_Office 365 Security & 合规中心页，可在其中为 SharePoint、OneDrive 和 Microsoft 团队打开 ATP](../../media/mtp-eval-36.png)

6. <span data-ttu-id="00c9b-146">单击 "+" 图标创建新的 "安全附件策略"，将其作为 "收件人域" 应用到域。</span><span class="sxs-lookup"><span data-stu-id="00c9b-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="00c9b-147">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-147">Click **Save**.</span></span>

   ![Image of_Office 365 Security & 合规中心页，可在其中创建新的 "新建安全附件" 策略](../../media/mtp-eval-37.png)
 
7. <span data-ttu-id="00c9b-149">接下来，选择 " **安全链接** " 策略，然后单击铅笔图标以编辑默认策略。</span><span class="sxs-lookup"><span data-stu-id="00c9b-149">Next, select the **Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="00c9b-150">请确保未选中 " **如果用户单击安全链接时不进行跟踪** " 选项，而其余选项则处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="00c9b-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="00c9b-151">有关详细信息，请参阅 [安全链接设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp) for details.</span></span> <span data-ttu-id="00c9b-152">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-152">Click **Save**.</span></span> 

   ![Image of_Office 365 Security & 合规中心页面，该页面显示当用户单击 "安全" 未选中时选项不会进行跟踪](../../media/mtp-eval-38.png)

9. <span data-ttu-id="00c9b-154">接下来，选择 **反恶意软件** 策略，选择默认设置，然后选择 "铅笔" 图标。</span><span class="sxs-lookup"><span data-stu-id="00c9b-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="00c9b-155">单击 " **设置** " 并选择 **"是"，并使用默认通知文本** 启用 **恶意软件检测响应** 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="00c9b-156">打开 **常用附件类型筛选器** 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="00c9b-157">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-157">Click **Save**.</span></span>

    ![Image of_Office 365 Security & 合规中心页面，该页面显示在启用恶意软件检测响应时启用默认通知并启用常用附件类型筛选器](../../media/mtp-eval-39.png)
  
11. <span data-ttu-id="00c9b-159">导航到 [Office 365 安全 & 合规性中心](https://protection.office.com/homepage)  >  **搜索**  >  **审核日志搜索** ，然后启用审核。</span><span class="sxs-lookup"><span data-stu-id="00c9b-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>

    ![Image of_Office 365 Security & 合规中心页，可在其中打开审核日志搜索](../../media/mtp-eval-40.png)

12. <span data-ttu-id="00c9b-161">将 Microsoft Defender for Office 365 与 Microsoft Defender for Endpoint 集成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-161">Integrate Microsoft Defender for Office 365 with Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="00c9b-162">导航到 [Office 365 Security & 合规性中心](https://protection.office.com/homepage)"  >  **威胁管理**  >  **资源管理器** ，然后选择屏幕右上角的" **Microsoft Defender for Endpoint Settings 设置** "。</span><span class="sxs-lookup"><span data-stu-id="00c9b-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **Microsoft Defender for Endpoint Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="00c9b-163">在 "用于终结点连接的 Defender" 对话框中，启用 " **连接到 Microsoft Defender For endpoint** "。</span><span class="sxs-lookup"><span data-stu-id="00c9b-163">In the Defender for Endpoint connection dialog box, turn on **Connect to Microsoft Defender for Endpoint**.</span></span>

    ![Image of_Office 365 Security & 合规中心页面，可在此页面上打开 Microsoft Defender for Endpoint connection](../../media/mtp-eval-41.png)

## <a name="configure-microsoft-defender-for-identity"></a><span data-ttu-id="00c9b-165">配置 Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="00c9b-165">Configure Microsoft Defender for Identity</span></span>

>[!NOTE]
><span data-ttu-id="00c9b-166">如果已启用 Microsoft Defender for Identity，请跳过此步骤</span><span class="sxs-lookup"><span data-stu-id="00c9b-166">Skip this step if you've already enabled Microsoft Defender for Identity</span></span>

1. <span data-ttu-id="00c9b-167">导航到 [microsoft 365 安全中心](https://security.microsoft.com/info)> 选择 **更多资源**  >  **microsoft Defender for Identity** 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Microsoft Defender for Identity**.</span></span>

   ![Image of_Microsoft 365 Security Center 页面，其中有一个用于打开 Microsoft Defender for Identity 的选项](../../media/mtp-eval-42.png)

2. <span data-ttu-id="00c9b-169">单击 " **创建** " 以启动 Microsoft Defender for Identity 向导。</span><span class="sxs-lookup"><span data-stu-id="00c9b-169">Click **Create** to start the Microsoft Defender for Identity wizard.</span></span> 

   !["Of_Microsoft 用于标识向导的 Defender" 页面（应在其中单击 "创建" 按钮）的图像](../../media/mtp-eval-43.png)

3. <span data-ttu-id="00c9b-171">选择 " **提供用户名和密码" 以连接到你的 Active Directory 林** 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  

   ![适用于标识欢迎页面的 of_Microsoft Defender 的图像](../../media/mtp-eval-44.png)

4. <span data-ttu-id="00c9b-173">输入你的 Active Directory 本地凭据。</span><span class="sxs-lookup"><span data-stu-id="00c9b-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="00c9b-174">可以是具有 Active Directory 的读访问权限的任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="00c9b-174">This can be any user account that has read access to Active Directory.</span></span>

   ![Of_Microsoft 用于标识目录服务的 Defender 页面（应在其中放置凭据）的图像](../../media/mtp-eval-45.png)

5. <span data-ttu-id="00c9b-176">接下来，选择 " **下载传感器设置** 并将文件传输到域控制器"。</span><span class="sxs-lookup"><span data-stu-id="00c9b-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span>

   ![可在其中选择 "下载传感器安装" 的 "用于标识的 of_Microsoft Defender" 页面的图像](../../media/mtp-eval-46.png)

6. <span data-ttu-id="00c9b-178">执行用于标识传感器设置的 Microsoft Defender，并开始遵循向导。</span><span class="sxs-lookup"><span data-stu-id="00c9b-178">Execute the Microsoft Defender for Identity Sensor Setup and begin following the wizard.</span></span>

   ![Of_Microsoft 用于标识页面的 Defender 的图像，您应在此页面上单击 "下一步" 以遵循 Microsoft Defender for Identity 传感器向导](../../media/mtp-eval-47.png)
 
7. <span data-ttu-id="00c9b-180">在传感器部署类型中，单击 " **下一步** "。</span><span class="sxs-lookup"><span data-stu-id="00c9b-180">Click **Next** at the sensor deployment type.</span></span>

   ![图像 of_Microsoft 用于标识页面的 Defender，您应在此页面上单击 "下一步" 转到 "下一页"](../../media/mtp-eval-48.png)
 
8. <span data-ttu-id="00c9b-182">复制访问键，因为在向导的下一步需要输入它。</span><span class="sxs-lookup"><span data-stu-id="00c9b-182">Copy the access key because you need to enter it next in the Wizard.</span></span>

   !["图像 of_the 传感器" 页，应在此页面上复制您需要在下一个 Microsoft Defender for Identity 传感器安装向导页中输入的访问密钥](../../media/mtp-eval-49.png)
 
9. <span data-ttu-id="00c9b-184">将访问键复制到向导中，然后单击 " **安装** "。</span><span class="sxs-lookup"><span data-stu-id="00c9b-184">Copy the access key into the Wizard and click **Install**.</span></span> 

   ![Image of_Microsoft 用于 Identity 传感器的 Defender 向导 "页面，您应在其中提供访问密钥，然后单击" 安装 "按钮](../../media/mtp-eval-50.png)

10. <span data-ttu-id="00c9b-186">恭喜，你已在你的域控制器上成功配置 Microsoft Defender for Identity。</span><span class="sxs-lookup"><span data-stu-id="00c9b-186">Congratulations, you've successfully configured Microsoft Defender for Identity on your domain controller.</span></span>

    ![Image of_Microsoft Defender for Identity 传感器向导安装完成，您应在其中单击 "完成" 按钮](../../media/mtp-eval-51.png)
 
11. <span data-ttu-id="00c9b-188">在 " [Microsoft defender For Identity](https://go.microsoft.com/fwlink/?linkid=2040449) 设置" 部分中，选择 "\* \* microsoft Defender for Endpoint \* \*"，然后打开 "切换"。</span><span class="sxs-lookup"><span data-stu-id="00c9b-188">Under the [Microsoft Defender for Identity](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select \*\*Microsoft Defender for Endpoint \*\*, then turn on the toggle.</span></span> <span data-ttu-id="00c9b-189">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-189">Click **Save**.</span></span> 

    !["Microsoft Defender for Identity settings" 页的图像 of_the 应在其中打开 Microsoft Defender for Endpoint 切换](../../media/mtp-eval-52.png)

>[!NOTE]
><span data-ttu-id="00c9b-191">Windows Defender ATP 已 rebranded 为 Microsoft Defender for Endpoint。</span><span class="sxs-lookup"><span data-stu-id="00c9b-191">Windows Defender ATP has been rebranded as Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="00c9b-192">所有门户的重塑更改都是为了实现一致性而推出的。</span><span class="sxs-lookup"><span data-stu-id="00c9b-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="00c9b-193">配置 Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="00c9b-193">Configure Microsoft Cloud App Security</span></span>

>[!NOTE]
><span data-ttu-id="00c9b-194">如果已启用 Microsoft 云应用安全性，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="00c9b-194">Skip this step if you've already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="00c9b-195">导航到 [microsoft](https://security.microsoft.com/info)  >  **More Resources**  >  **云应用安全性** 的 microsoft 365 安全中心更多资源。</span><span class="sxs-lookup"><span data-stu-id="00c9b-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>

   ![Image of_Microsoft 365 Security Center 页面，可在其中查看 Microsoft 云应用程序卡，并应单击 "打开" 按钮](../../media/mtp-eval-53.png)

2. <span data-ttu-id="00c9b-197">在信息提示符下，集成 Microsoft Defender for Identity 时，选择 " **启用 Microsoft defender 以实现标识数据集成** "。</span><span class="sxs-lookup"><span data-stu-id="00c9b-197">At the information prompt to integrate Microsoft Defender for Identity, select **Enable Microsoft Defender for Identity data integration**.</span></span>
  
   ![Image of_the 信息提示将 Microsoft Defender 集成到您应在其中选择 "启用 Microsoft Defender for Identity data integration" 链接的标识。](../../media/mtp-eval-54.png)

   > [!NOTE]
   > <span data-ttu-id="00c9b-199">如果看不到此提示，可能意味着已为 Microsoft Defender 提供了标识数据集成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-199">If you don’t see this prompt, it might mean that your Microsoft Defender for Identity data integration has already been enabled.</span></span> <span data-ttu-id="00c9b-200">但是，如果你不确定，请联系你的 IT 管理员进行确认。</span><span class="sxs-lookup"><span data-stu-id="00c9b-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="00c9b-201">转到 " **设置** "，打开 **Microsoft Defender for Identity integration** 切换，然后单击 " **保存** "。</span><span class="sxs-lookup"><span data-stu-id="00c9b-201">Go to **Settings** , turn on the **Microsoft Defender for Identity integration** toggle, then click **Save**.</span></span> 

   !["图像 of_the 设置" 页面，您应在此页面上打开 Microsoft Defender for Identity integration 切换，然后单击 "保存"](../../media/mtp-eval-55.png)
   
   > [!NOTE]
   > <span data-ttu-id="00c9b-203">对于新的 Microsoft Defender for Identity 实例，此集成切换将自动打开。</span><span class="sxs-lookup"><span data-stu-id="00c9b-203">For new Microsoft Defender for Identity instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="00c9b-204">在继续下一步之前，请确认已启用 Microsoft Defender 身份集成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-204">Confirm that your Microsoft Defender for Identity integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="00c9b-205">在 "云发现设置" 下，选择 " **Microsoft Defender For Endpoint integration** "，然后启用集成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-205">Under the Cloud discovery settings, select **Microsoft Defender for Endpoint integration** , then enable the integration.</span></span> <span data-ttu-id="00c9b-206">单击“ **保存** ”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-206">Click **Save**.</span></span>

   !["Unsanctioned Microsoft defender for endpoint integration" 下的 "阻止应用程序" 复选框中的 "Microsoft Defender for Endpoint integration" 的 of_the 图像已选中。](../../media/mtp-eval-56.png)

5. <span data-ttu-id="00c9b-209">在 "云发现设置" 下，选择 " **用户扩充** "，然后启用与 Azure Active Directory 的集成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-209">Under Cloud discovery settings, select **User enrichment** , then enable the integration with Azure Active Directory.</span></span>

   !["用户扩充的图像" 部分，其中的 "浓缩已发现用户标识符与 Azure Active Directory 用户名" 复选框处于选中状态](../../media/mtp-eval-57.png)


## <a name="configure-microsoft-defender-for-endpoint"></a><span data-ttu-id="00c9b-211">为终结点配置 Microsoft Defender</span><span class="sxs-lookup"><span data-stu-id="00c9b-211">Configure Microsoft Defender for Endpoint</span></span>

>[!NOTE]
><span data-ttu-id="00c9b-212">如果已启用 Microsoft Defender for Endpoint，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="00c9b-212">Skip this step if you've already enabled Microsoft Defender for Endpoint.</span></span>

1. <span data-ttu-id="00c9b-213">导航到 microsoft Defender 安全中心的 [microsoft 365 安全中心](https://security.microsoft.com/info)  >  **更多资源**  >  **Microsoft Defender Security Center** 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-213">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="00c9b-214">单击“打开”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-214">Click **Open**.</span></span>

   ![Microsoft 365 安全中心页面中的 "of_Microsoft Defender 安全中心" 选项的图像](../../media/mtp-eval-58.png)
 
2. <span data-ttu-id="00c9b-216">遵循 Microsoft Defender for Endpoint 向导。</span><span class="sxs-lookup"><span data-stu-id="00c9b-216">Follow the Microsoft Defender for Endpoint wizard.</span></span> <span data-ttu-id="00c9b-217">单击“ **下一步** ”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-217">Click **Next**.</span></span> 

   ![Microsoft Defender 安全中心欢迎向导页面 of_the 的图像](../../media/mtp-eval-59.png)

3. <span data-ttu-id="00c9b-219">选择 "基于您的首选数据存储位置"、"数据保留策略"、"组织大小" 和 "选择性加入预览" 功能。</span><span class="sxs-lookup"><span data-stu-id="00c9b-219">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span>

   !["图像 of_the" 页以选择数据存储国家/地区、保留策略和组织大小。](../../media/mtp-eval-60.png)
   
   > [!NOTE]
   > <span data-ttu-id="00c9b-222">之后，您无法更改某些设置，如数据存储位置。</span><span class="sxs-lookup"><span data-stu-id="00c9b-222">You cannot change some of the settings, like data storage location, afterwards.</span></span> 

   <span data-ttu-id="00c9b-223">单击“ **下一步** ”。</span><span class="sxs-lookup"><span data-stu-id="00c9b-223">Click **Next**.</span></span> 

4. <span data-ttu-id="00c9b-224">单击 " **继续** "，它将预配你的 Microsoft Defender for Endpoint 租户。</span><span class="sxs-lookup"><span data-stu-id="00c9b-224">Click **Continue** and it will provision your Microsoft Defender for Endpoint tenant.</span></span>

   ![图像 of_the 页面提示您单击 "继续" 按钮以创建云实例](../../media/mtp-eval-61.png)

5. <span data-ttu-id="00c9b-226">通过组策略、Microsoft 终结点管理器或通过运行本地脚本到 Microsoft Defender for Endpoint 来集成你的终结点。</span><span class="sxs-lookup"><span data-stu-id="00c9b-226">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender for Endpoint.</span></span> <span data-ttu-id="00c9b-227">为简单起见，本指南使用本地脚本。</span><span class="sxs-lookup"><span data-stu-id="00c9b-227">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="00c9b-228">单击 " **下载包** "，并将载入脚本复制到终结点 (s) 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-228">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>

   ![图像 of_page 提示您单击 "下载包" 按钮以将载入脚本复制到终结点或终结点](../../media/mtp-eval-62.png)

7. <span data-ttu-id="00c9b-230">在终结点上，以管理员身份运行载入脚本，然后选择 "Y"。</span><span class="sxs-lookup"><span data-stu-id="00c9b-230">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span> 

   ![在运行载入脚本的情况下，图像 of_the 命令行，并选择 "Y" 继续](../../media/mtp-eval-63.png)

8. <span data-ttu-id="00c9b-232">恭喜，你已载入你的第一个终结点。</span><span class="sxs-lookup"><span data-stu-id="00c9b-232">Congratulations, you've onboarded your first endpoint.</span></span>

   ![图像 of_the 命令行载入，您可以在其中获取您对第一个终结点所做的确认。](../../media/mtp-eval-64.png)

9. <span data-ttu-id="00c9b-235">从 Microsoft Defender for Endpoint 向导复制并粘贴检测测试。</span><span class="sxs-lookup"><span data-stu-id="00c9b-235">Copy-paste the detection test from the Microsoft Defender for Endpoint wizard.</span></span>

   ![Image of_the 运行检测测试步骤，在此步骤中，应单击 "复制" 以复制应在命令提示符处粘贴的检测测试脚本](../../media/mtp-eval-65.png)

10. <span data-ttu-id="00c9b-237">将 PowerShell 脚本复制到提升的命令提示符，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="00c9b-237">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 

    ![图像 of_command 提示，应将 PowerShell 脚本复制到提升的命令提示符并运行它](../../media/mtp-eval-66.png)

11. <span data-ttu-id="00c9b-239">从向导中选择 " **开始使用 Microsoft Defender For Endpoint** "。</span><span class="sxs-lookup"><span data-stu-id="00c9b-239">Select **Start using Microsoft Defender for Endpoint** from the Wizard.</span></span>

    ![图像 of_the 来自向导的确认提示，应单击该向导中的 "开始使用 Microsoft Defender for Endpoint"](../../media/mtp-eval-67.png)
 
12. <span data-ttu-id="00c9b-241">访问 [Microsoft Defender 安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="00c9b-241">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="00c9b-242">转到 " **设置** "，然后选择 " **高级功能** "。</span><span class="sxs-lookup"><span data-stu-id="00c9b-242">Go to **Settings** and then select **Advanced features**.</span></span> 

    ![应在其中选择 "高级功能" of_Microsoft "Defender 安全中心设置" 菜单的图像](../../media/mtp-eval-68.png)

13. <span data-ttu-id="00c9b-244">启用与 **Microsoft Defender For Identity** 的集成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-244">Turn on the integration with **Microsoft Defender for Identity**.</span></span>  

    ![Image of_Microsoft Defender Security Center 高级功能，需要打开的 Microsoft Defender 标识选项切换](../../media/mtp-eval-69.png)

14. <span data-ttu-id="00c9b-246">启用与 **Office 365 威胁智能** 的集成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-246">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>

    ![Image of_Microsoft Defender Security Center 高级功能，需要打开的 Office 365 威胁智能选项切换](../../media/mtp-eval-70.png)

15. <span data-ttu-id="00c9b-248">启用与 **Microsoft 云应用安全性** 的集成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-248">Turn on integration with **Microsoft Cloud App Security**.</span></span>

    ![Image of_Microsoft Defender Security Center 高级功能，需要打开的 Microsoft 云应用安全选项切换](../../media/mtp-eval-71.png)

16. <span data-ttu-id="00c9b-250">向下滚动，然后单击 " **保存首选项** " 以确认新的集成。</span><span class="sxs-lookup"><span data-stu-id="00c9b-250">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>

    ![您需要单击的图像 of_Save 首选项按钮](../../media/mtp-eval-72.png)

## <a name="start-the-microsoft-365-defender-service"></a><span data-ttu-id="00c9b-252">启动 Microsoft 365 Defender 服务</span><span class="sxs-lookup"><span data-stu-id="00c9b-252">Start the Microsoft 365 Defender service</span></span>

>[!NOTE]
><span data-ttu-id="00c9b-253">从2020年6月1日开始，Microsoft 自动为所有符合条件的租户启用 Microsoft 365 Defender 功能。</span><span class="sxs-lookup"><span data-stu-id="00c9b-253">Starting June 1, 2020, Microsoft automatically enables Microsoft 365 Defender features for all eligible tenants.</span></span> <span data-ttu-id="00c9b-254">有关详细信息，请参阅本 [Microsoft 技术社区文章关于许可证资格](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) 。</span><span class="sxs-lookup"><span data-stu-id="00c9b-254">See this [Microsoft Tech Community article on license eligibility](https://techcommunity.microsoft.com/t5/security-privacy-and-compliance/microsoft-threat-protection-will-automatically-turn-on-for/ba-p/1345426) for details.</span></span> 


<span data-ttu-id="00c9b-255">转到 [Microsoft 365 安全中心](https://security.microsoft.com/homepage)。</span><span class="sxs-lookup"><span data-stu-id="00c9b-255">Go to [Microsoft 365 Security Center](https://security.microsoft.com/homepage).</span></span> <span data-ttu-id="00c9b-256">导航到 " **设置** "，然后选择 " **Microsoft 365 Defender** "。</span><span class="sxs-lookup"><span data-stu-id="00c9b-256">Navigate to **Settings** and then select **Microsoft 365 Defender**.</span></span>

![<span data-ttu-id="00c9b-257">来自 Microsoft 365 安全中心设置页面的图像 of_Microsoft 365 Defender 选项屏幕截图</span><span class="sxs-lookup"><span data-stu-id="00c9b-257">Image of_Microsoft 365 Defender option screenshot from the Microsoft 365 Security Center Settings page</span></span> ](../../media/mtp-eval-72b.png) <br>

<span data-ttu-id="00c9b-258">有关更全面的指导，请参阅 [打开 Microsoft 365 Defender](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="00c9b-258">For a more comprehensive guidance, see [Turn on Microsoft 365 Defender](mtp-enable.md).</span></span> 

<span data-ttu-id="00c9b-259">祝贺你！</span><span class="sxs-lookup"><span data-stu-id="00c9b-259">Congratulations!</span></span> <span data-ttu-id="00c9b-260">你刚刚创建了 Microsoft 365 Defender 试用版实验室或试点环境！</span><span class="sxs-lookup"><span data-stu-id="00c9b-260">You've just created your Microsoft 365 Defender trial lab or pilot environment!</span></span> <span data-ttu-id="00c9b-261">现在，你可以熟悉 Microsoft 365 Defender 用户界面！</span><span class="sxs-lookup"><span data-stu-id="00c9b-261">Now you can familiarize yourself with the Microsoft 365 Defender user interface!</span></span> <span data-ttu-id="00c9b-262">查看您可以从以下 Microsoft 365 Defender 互动版指南中了解的内容，并了解如何使用每个仪表板执行日常安全操作任务。</span><span class="sxs-lookup"><span data-stu-id="00c9b-262">See what you can learn from the following Microsoft 365 Defender interactive guide and know how to use each dashboard for your day-to-day security operation tasks.</span></span>


>[!VIDEO https://aka.ms/MTP-Interactive-Guide]

<span data-ttu-id="00c9b-263">接下来，您可以模拟攻击，并查看跨产品功能如何检测、创建警报以及自动响应对终结点的 fileless 攻击。</span><span class="sxs-lookup"><span data-stu-id="00c9b-263">Next, you can simulate an attack and see how the cross product capabilities detect, create alerts, and automatically respond to a fileless attack on an endpoint.</span></span>

## <a name="next-step"></a><span data-ttu-id="00c9b-264">后续步骤</span><span class="sxs-lookup"><span data-stu-id="00c9b-264">Next step</span></span>
|<span data-ttu-id="00c9b-265">![攻击模拟阶段](../../media/mtp/run-sim.png)</span><span class="sxs-lookup"><span data-stu-id="00c9b-265">![Attack simulation phase](../../media/mtp/run-sim.png)</span></span> <br>[<span data-ttu-id="00c9b-266">攻击模拟阶段</span><span class="sxs-lookup"><span data-stu-id="00c9b-266">Attack simulation phase</span></span>](mtp-pilot-simulate.md) | <span data-ttu-id="00c9b-267">为您的 Microsoft 365 Defender 试点环境运行攻击模拟。</span><span class="sxs-lookup"><span data-stu-id="00c9b-267">Run the attack simulation for your Microsoft 365 Defender pilot environment.</span></span>
|:-------|:-----|
