---
title: 为试用实验室环境配置 Microsoft 威胁防护支柱
description: 为你的试用实验室环境配置 Microsoft 威胁防护支柱、Office 365 ATP、Azure ATP、Microsoft 云应用安全和 Microsoft Defender ATP
keywords: 配置 Microsoft 威胁防护试用，Microsoft 威胁防护试用版配置，配置 Microsoft 威胁防护支柱，Microsoft 威胁防护支柱
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
ms.openlocfilehash: 68d8f06803d75c3f89cae6fa7998734fd54084ca
ms.sourcegitcommit: 5476c2578400894640ae74bfe8e93c3319f685bd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44049505"
---
# <a name="configure-microsoft-threat-protection-pillars-for-your-trial-lab-environment"></a><span data-ttu-id="e9a17-104">为试用版实验室环境配置 Microsoft 威胁防护支柱</span><span class="sxs-lookup"><span data-stu-id="e9a17-104">Configure Microsoft Threat Protection pillars for your trial lab environment</span></span>

<span data-ttu-id="e9a17-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="e9a17-105">**Applies to:**</span></span>
- <span data-ttu-id="e9a17-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="e9a17-106">Microsoft Threat Protection</span></span>


<span data-ttu-id="e9a17-107">创建 Microsoft 威胁 Protection 试用实验室环境并部署它的过程分为三个阶段：</span><span class="sxs-lookup"><span data-stu-id="e9a17-107">Creating a Microsoft Threat Protection trial lab environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" >
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval?view=o365-worldwide"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft Threat Protection trial lab environment" title="准备你的 Microsoft 威胁防护试用实验室环境" />
      <br/><span data-ttu-id="e9a17-109">第1阶段：准备</a></span><span class="sxs-lookup"><span data-stu-id="e9a17-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval?view=o365-worldwide">
        <img src="../../media/setup.png" alt="Set up your Microsoft Threat Protection trial lab environment" title="设置你的 Microsoft 威胁防护试用实验室环境" />
      <br/><span data-ttu-id="e9a17-111">阶段2：安装程序</a></span><span class="sxs-lookup"><span data-stu-id="e9a17-111">Phase 2: Setup </a></span></span><br>
    </td>
    <td align="center" bgcolor="#d5f5e3">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval?view=o365-worldwide">
        <img src="../../media/config-onboard.png" alt="Configure & Onboard" title="为 Microsoft 威胁防护试用实验室环境和板载终结点配置每个 Microsoft 威胁防护支柱" />
      <br/><span data-ttu-id="e9a17-113">第3阶段： Configure & 板载</a></span><span class="sxs-lookup"><span data-stu-id="e9a17-113">Phase 3: Configure & Onboard </a></span></span><br>
</td>


  </tr>
</table>

<span data-ttu-id="e9a17-114">你当前正在配置阶段。</span><span class="sxs-lookup"><span data-stu-id="e9a17-114">You are currently in the configuration phase.</span></span>


<span data-ttu-id="e9a17-115">准备工作是任何成功部署的关键。</span><span class="sxs-lookup"><span data-stu-id="e9a17-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="e9a17-116">在本文中，您将指导您在准备部署 Microsoft Defender ATP 时需要考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="e9a17-116">In this article, you'll be guided on the points you'll need to consider as you prepare to deploy Microsoft Defender ATP.</span></span>


## <a name="microsoft-threat-protection-pillars"></a><span data-ttu-id="e9a17-117">Microsoft 威胁防护支柱</span><span class="sxs-lookup"><span data-stu-id="e9a17-117">Microsoft Threat Protection pillars</span></span>
<span data-ttu-id="e9a17-118">Microsoft 威胁防护由四个支柱组成。</span><span class="sxs-lookup"><span data-stu-id="e9a17-118">Microsoft Threat Protection consists of four pillars.</span></span> <span data-ttu-id="e9a17-119">尽管一个支柱可以为你的网络组织的安全性提供价值，但启用四个 Microsoft 威胁防护支柱将为你的组织提供最大价值。</span><span class="sxs-lookup"><span data-stu-id="e9a17-119">Although one pillar can already provide value to your network organization's security, enabling the four Microsoft Threat Protection pillars will give your organization the most value.</span></span>

![图像 of_page](../../media/mtp-eval-31.png) <br>

<span data-ttu-id="e9a17-121">本部分将指导您配置：</span><span class="sxs-lookup"><span data-stu-id="e9a17-121">This section will guide you to configure:</span></span>
-   <span data-ttu-id="e9a17-122">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="e9a17-122">Office 365 Advanced Threat Protection</span></span>
-   <span data-ttu-id="e9a17-123">Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="e9a17-123">Azure Advanced Threat Protection</span></span> 
-   <span data-ttu-id="e9a17-124">Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="e9a17-124">Microsoft Cloud App Security</span></span>
-   <span data-ttu-id="e9a17-125">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="e9a17-125">Microsoft Defender Advanced Threat Protection</span></span>


## <a name="configure-office-365-advanced-threat-protection"></a><span data-ttu-id="e9a17-126">配置 Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="e9a17-126">Configure Office 365 Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="e9a17-127">如果已启用 Office 365 高级威胁防护，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="e9a17-127">Skip this step if you have already enabled Office 365 Advanced Threat Protection.</span></span> 

<span data-ttu-id="e9a17-128">有一个称为*Office 365 高级威胁防护建议配置分析器（ORCA）* 的 PowerShell 模块可帮助确定其中一些设置。</span><span class="sxs-lookup"><span data-stu-id="e9a17-128">There is a PowerShell Module called the *Office 365 Advanced Threat Protection Recommended Configuration Analyzer (ORCA)* that helps determine some of these settings.</span></span> <span data-ttu-id="e9a17-129">在租户中以管理员身份运行时，ORCAReport 将帮助生成反垃圾邮件、反网络钓鱼和其他邮件清洁设置的评估。</span><span class="sxs-lookup"><span data-stu-id="e9a17-129">When run as an administrator in your tenant, get-ORCAReport will help generate an assessment of the anti-spam, anti-phish, and other message hygiene settings.</span></span> <span data-ttu-id="e9a17-130">您可以从https://www.powershellgallery.com/packages/ORCA/下载此模块。</span><span class="sxs-lookup"><span data-stu-id="e9a17-130">You can download this module from https://www.powershellgallery.com/packages/ORCA/.</span></span> 

1. <span data-ttu-id="e9a17-131">导航到[Office 365 Security & 合规性中心](https://protection.office.com/homepage) > **威胁管理** > **策略**。</span><span class="sxs-lookup"><span data-stu-id="e9a17-131">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Policy**.</span></span>
<span data-ttu-id="e9a17-132">![图像 of_page](../../media/mtp-eval-32.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-132">![Image of_page](../../media/mtp-eval-32.png)</span></span> <br>
 
2. <span data-ttu-id="e9a17-133">单击 " **ATP 反网络钓鱼**"，选择 "**创建**并填写策略名称和说明"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-133">Click **ATP anti-phishing**, select **Create** and fill in the policy name and description.</span></span> <span data-ttu-id="e9a17-134">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9a17-134">Click **Next**.</span></span>
<span data-ttu-id="e9a17-135">![图像 of_page](../../media/mtp-eval-33.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-135">![Image of_page](../../media/mtp-eval-33.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="e9a17-136">编辑高级 ATP 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="e9a17-136">Edit your Advanced ATP anti-phishing policy.</span></span> <span data-ttu-id="e9a17-137">将**高级网络钓鱼阈值**更改为**2-主动**。</span><span class="sxs-lookup"><span data-stu-id="e9a17-137">Change **Advanced Phishing Threshold** to **2 - Aggressive**.</span></span>
<br>

3. <span data-ttu-id="e9a17-138">单击 "**添加条件**" 下拉菜单，并选择您的域作为 "收件人域"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-138">Click the **Add a condition** drop-down menu and select your domain(s) as recipient domain.</span></span> <span data-ttu-id="e9a17-139">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9a17-139">Click **Next**.</span></span>
<span data-ttu-id="e9a17-140">![图像 of_page](../../media/mtp-eval-34.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-140">![Image of_page](../../media/mtp-eval-34.png)</span></span> <br>
 
4. <span data-ttu-id="e9a17-141">查看您的设置。</span><span class="sxs-lookup"><span data-stu-id="e9a17-141">Review your settings.</span></span> <span data-ttu-id="e9a17-142">单击 "**创建此策略**" 以确认。</span><span class="sxs-lookup"><span data-stu-id="e9a17-142">Click **Create this policy** to confirm.</span></span> 
<span data-ttu-id="e9a17-143">![图像 of_page](../../media/mtp-eval-35.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-143">![Image of_page](../../media/mtp-eval-35.png)</span></span> <br>
 
5. <span data-ttu-id="e9a17-144">选择 " **ATP 安全附件**"，然后选择 "**启用 SharePoint、OneDrive 和 MICROSOFT 团队的 atp** " 选项。</span><span class="sxs-lookup"><span data-stu-id="e9a17-144">Select **ATP Safe attachments** and select the **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams** option.</span></span>  
<span data-ttu-id="e9a17-145">![图像 of_page](../../media/mtp-eval-36.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-145">![Image of_page](../../media/mtp-eval-36.png)</span></span> <br>

6. <span data-ttu-id="e9a17-146">单击 "+" 图标创建新的 "安全附件策略"，将其作为 "收件人域" 应用到域。</span><span class="sxs-lookup"><span data-stu-id="e9a17-146">Click the + icon to create a new safe attachment policy, apply it as recipient domain to your domains.</span></span> <span data-ttu-id="e9a17-147">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e9a17-147">Click **Save**.</span></span>
<span data-ttu-id="e9a17-148">![图像 of_page](../../media/mtp-eval-37.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-148">![Image of_page](../../media/mtp-eval-37.png)</span></span> <br>
 
7. <span data-ttu-id="e9a17-149">接下来，选择**ATP 安全链接**策略，然后单击铅笔图标以编辑默认策略。</span><span class="sxs-lookup"><span data-stu-id="e9a17-149">Next, select the **ATP Safe Links** policy, then click the pencil icon to edit the default policy.</span></span>

8. <span data-ttu-id="e9a17-150">请确保未选中 "**如果用户单击安全链接时不进行跟踪**" 选项，而其余选项则处于选中状态。</span><span class="sxs-lookup"><span data-stu-id="e9a17-150">Make sure that the **Do not track when users click safe links** option is not selected, while the rest of the options are selected.</span></span> <span data-ttu-id="e9a17-151">有关详细信息，请参阅[安全链接设置](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide)。</span><span class="sxs-lookup"><span data-stu-id="e9a17-151">See [Safe Links settings](https://docs.microsoft.com/microsoft-365/security/office-365-security/recommended-settings-for-eop-and-office365-atp?view=o365-worldwide) for details.</span></span> <span data-ttu-id="e9a17-152">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e9a17-152">Click **Save**.</span></span> 
<span data-ttu-id="e9a17-153">![图像 of_page](../../media/mtp-eval-38.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-153">![Image of_page](../../media/mtp-eval-38.png)</span></span> <br>

9. <span data-ttu-id="e9a17-154">接下来，选择**反恶意软件**策略，选择默认设置，然后选择 "铅笔" 图标。</span><span class="sxs-lookup"><span data-stu-id="e9a17-154">Next select the **Anti-malware** policy, select the default, and choose the pencil icon.</span></span>

10. <span data-ttu-id="e9a17-155">单击 "**设置**" 并选择 **"是"，并使用默认通知文本**启用**恶意软件检测响应**。</span><span class="sxs-lookup"><span data-stu-id="e9a17-155">Click **Settings** and select **Yes and use the default notification text** to enable **Malware Detection Response**.</span></span> <span data-ttu-id="e9a17-156">打开**常用附件类型筛选器**。</span><span class="sxs-lookup"><span data-stu-id="e9a17-156">Turn the **Common Attachment Types Filter** on.</span></span> <span data-ttu-id="e9a17-157">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e9a17-157">Click **Save**.</span></span>
<br><span data-ttu-id="e9a17-158">![图像 of_page](../../media/mtp-eval-39.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-158">![Image of_page](../../media/mtp-eval-39.png)</span></span> <br>
  
11. <span data-ttu-id="e9a17-159">导航到[Office 365 安全 & 合规性中心](https://protection.office.com/homepage) > **搜索** > **审核日志搜索**，然后启用审核。</span><span class="sxs-lookup"><span data-stu-id="e9a17-159">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Search** > **Audit log search** and turn Auditing on.</span></span>  
<span data-ttu-id="e9a17-160">![图像 of_page](../../media/mtp-eval-40.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-160">![Image of_page](../../media/mtp-eval-40.png)</span></span> <br>

12. <span data-ttu-id="e9a17-161">将 Office 365 ATP 与 Microsoft Defender ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="e9a17-161">Integrate Office 365 ATP with Microsoft Defender ATP.</span></span> <span data-ttu-id="e9a17-162">导航到[Office 365 Security & 合规性中心](https://protection.office.com/homepage) > "**威胁管理** > **资源管理器**，然后选择屏幕右上角的" **WDATP 设置**"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-162">Navigate to [Office 365 Security & Compliance Center](https://protection.office.com/homepage) > **Threat management** > **Explorer** and select **WDATP Settings** on the upper right corner of the screen.</span></span> <span data-ttu-id="e9a17-163">在 "Microsoft Defender ATP 连接" 对话框中，启用 "**连接到 WINDOWS ATP**"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-163">In the Microsoft Defender ATP connection dialog box, turn on **Connect to Windows ATP**.</span></span>
<span data-ttu-id="e9a17-164">![图像 of_page](../../media/mtp-eval-41.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-164">![Image of_page](../../media/mtp-eval-41.png)</span></span> <br>

## <a name="configure-azure-advanced-threat-protection"></a><span data-ttu-id="e9a17-165">配置 Azure 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="e9a17-165">Configure Azure Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="e9a17-166">如果已启用 Azure 高级威胁防护，请跳过此步骤</span><span class="sxs-lookup"><span data-stu-id="e9a17-166">Skip this step if you have already enabled Azure Advanced Threat Protection</span></span>


1. <span data-ttu-id="e9a17-167">导航到[Microsoft 365 安全中心](https://security.microsoft.com/info)> 选择**更多资源** > **Azure 高级威胁防护**。</span><span class="sxs-lookup"><span data-stu-id="e9a17-167">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > select **More Resources** > **Azure Advanced Threat Protection**.</span></span>
<span data-ttu-id="e9a17-168">![图像 of_page](../../media/mtp-eval-42.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-168">![Image of_page](../../media/mtp-eval-42.png)</span></span> <br>

2. <span data-ttu-id="e9a17-169">单击 "**创建**" 以启动 Azure 高级威胁防护向导。</span><span class="sxs-lookup"><span data-stu-id="e9a17-169">Click **Create** to start the Azure Advanced Threat Protection wizard.</span></span> 
<br><span data-ttu-id="e9a17-170">![图像 of_page](../../media/mtp-eval-43.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-170">![Image of_page](../../media/mtp-eval-43.png)</span></span> <br>

3. <span data-ttu-id="e9a17-171">选择 "**提供用户名和密码" 以连接到你的 Active Directory 林**。</span><span class="sxs-lookup"><span data-stu-id="e9a17-171">Choose **Provide a username and password to connect to your Active Directory forest**.</span></span>  
<span data-ttu-id="e9a17-172">![图像 of_page](../../media/mtp-eval-44.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-172">![Image of_page](../../media/mtp-eval-44.png)</span></span> <br>

4. <span data-ttu-id="e9a17-173">输入你的 Active Directory 本地凭据。</span><span class="sxs-lookup"><span data-stu-id="e9a17-173">Enter your Active Directory on-premises credentials.</span></span> <span data-ttu-id="e9a17-174">可以是具有 Active Directory 的读访问权限的任何用户帐户。</span><span class="sxs-lookup"><span data-stu-id="e9a17-174">This can be any user account that has read access to Active Directory.</span></span>
<span data-ttu-id="e9a17-175">![图像 of_page](../../media/mtp-eval-45.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-175">![Image of_page](../../media/mtp-eval-45.png)</span></span> <br>

5. <span data-ttu-id="e9a17-176">接下来，选择 "**下载传感器设置**并将文件传输到域控制器"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-176">Next, choose **Download Sensor Setup** and transfer file to your domain controller.</span></span> 
<span data-ttu-id="e9a17-177">![图像 of_page](../../media/mtp-eval-46.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-177">![Image of_page](../../media/mtp-eval-46.png)</span></span> <br>

6. <span data-ttu-id="e9a17-178">执行 Azure ATP 传感器设置并开始遵循向导。</span><span class="sxs-lookup"><span data-stu-id="e9a17-178">Execute the Azure ATP Sensor Setup and begin following the wizard.</span></span>
<br><span data-ttu-id="e9a17-179">![图像 of_page](../../media/mtp-eval-47.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-179">![Image of_page](../../media/mtp-eval-47.png)</span></span> <br>
 
7. <span data-ttu-id="e9a17-180">在传感器部署类型中，单击 "**下一步**"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-180">Click **Next** at the sensor deployment type.</span></span>
<br><span data-ttu-id="e9a17-181">![图像 of_page](../../media/mtp-eval-48.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-181">![Image of_page](../../media/mtp-eval-48.png)</span></span> <br>
 
8. <span data-ttu-id="e9a17-182">复制访问密钥，因为在向导的下一步需要输入访问密钥。</span><span class="sxs-lookup"><span data-stu-id="e9a17-182">Copy the access key as you will need to enter it next in the Wizard.</span></span>
<span data-ttu-id="e9a17-183">![图像 of_page](../../media/mtp-eval-49.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-183">![Image of_page](../../media/mtp-eval-49.png)</span></span> <br>
 
9. <span data-ttu-id="e9a17-184">将访问键复制到向导中，然后单击 "**安装**"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-184">Copy the access key into the Wizard and click **Install**.</span></span> 
<br><span data-ttu-id="e9a17-185">![图像 of_page](../../media/mtp-eval-50.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-185">![Image of_page](../../media/mtp-eval-50.png)</span></span> <br>

10. <span data-ttu-id="e9a17-186">恭喜，你已在域控制器上成功配置了 Azure 高级威胁防护。</span><span class="sxs-lookup"><span data-stu-id="e9a17-186">Congratulations, you have successfully configured Azure Advanced Threat Protection on your domain controller.</span></span>
<span data-ttu-id="e9a17-187">![图像 of_page](../../media/mtp-eval-51.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-187">![Image of_page](../../media/mtp-eval-51.png)</span></span> <br>
 
11. <span data-ttu-id="e9a17-188">在 " [Azure AZURE ATP](https://go.microsoft.com/fwlink/?linkid=2040449)设置" 部分下，选择 " **Windows Defender atp**"，然后打开 "开启"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-188">Under the [Azure Azure ATP](https://go.microsoft.com/fwlink/?linkid=2040449) settings section, select **Windows Defender ATP**, then turn the toggle on.</span></span> <span data-ttu-id="e9a17-189">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e9a17-189">Click **Save**.</span></span> 
<span data-ttu-id="e9a17-190">![图像 of_page](../../media/mtp-eval-52.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-190">![Image of_page](../../media/mtp-eval-52.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="e9a17-191">Windows Defender ATP 已被 rebranded 为 Microsoft Defender ATP。</span><span class="sxs-lookup"><span data-stu-id="e9a17-191">Windows Defender ATP has been rebranded as Microsoft Defender ATP.</span></span> <span data-ttu-id="e9a17-192">所有门户的重塑更改都是为了实现一致性而推出的。</span><span class="sxs-lookup"><span data-stu-id="e9a17-192">Rebranding changes across all of our portals are being rolled out the for consistency.</span></span>


## <a name="configure-microsoft-cloud-app-security"></a><span data-ttu-id="e9a17-193">配置 Microsoft 云应用安全</span><span class="sxs-lookup"><span data-stu-id="e9a17-193">Configure Microsoft Cloud App Security</span></span>
>[!NOTE]
><span data-ttu-id="e9a17-194">如果已启用 Microsoft 云应用安全性，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="e9a17-194">Skip this step if you have already enabled Microsoft Cloud App Security.</span></span> 

1. <span data-ttu-id="e9a17-195">导航到 microsoft**云应用安全性**的[microsoft 365 安全中心](https://security.microsoft.com/info) > **更多资源** > 。</span><span class="sxs-lookup"><span data-stu-id="e9a17-195">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Cloud App Security**.</span></span>
<span data-ttu-id="e9a17-196">![图像 of_page](../../media/mtp-eval-53.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-196">![Image of_page](../../media/mtp-eval-53.png)</span></span> <br>

2. <span data-ttu-id="e9a17-197">在信息提示符下集成 Azure ATP 时，选择 "**启用 AZURE atp 数据集成**"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-197">At the information prompt to integrate Azure ATP, select **Enable Azure ATP data integration**.</span></span> 
<br><span data-ttu-id="e9a17-198">![图像 of_page](../../media/mtp-eval-54.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-198">![Image of_page](../../media/mtp-eval-54.png)</span></span> <br>

>[!NOTE]
><span data-ttu-id="e9a17-199">如果你未看到此提示，则可能意味着你的 Azure ATP 数据集成已启用。</span><span class="sxs-lookup"><span data-stu-id="e9a17-199">If you don’t see this prompt, it might mean that your Azure ATP data integration has already been enabled.</span></span> <span data-ttu-id="e9a17-200">但是，如果你不确定，请联系你的 IT 管理员进行确认。</span><span class="sxs-lookup"><span data-stu-id="e9a17-200">However, if you are not sure, contact your IT Administrator to confirm.</span></span> 

3. <span data-ttu-id="e9a17-201">转到 "**设置**"，将**Azure ATP 集成**切换为打开，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-201">Go to **Settings**, turn the **Azure ATP integration** toggle on, then click **Save**.</span></span> 
<span data-ttu-id="e9a17-202">![图像 of_page](../../media/mtp-eval-55.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-202">![Image of_page](../../media/mtp-eval-55.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="e9a17-203">对于新的 Azure ATP 实例，此集成切换将自动打开。</span><span class="sxs-lookup"><span data-stu-id="e9a17-203">For new Azure ATP instances, this integration toggle is automatically turned on.</span></span> <span data-ttu-id="e9a17-204">在继续下一步之前，请确认已启用 Azure ATP 集成。</span><span class="sxs-lookup"><span data-stu-id="e9a17-204">Confirm that your Azure ATP integration has been enabled before you proceed to the next step.</span></span>
 
4. <span data-ttu-id="e9a17-205">在 "云发现设置" 下，选择 " **Microsoft DEFENDER ATP 集成**"，然后启用集成。</span><span class="sxs-lookup"><span data-stu-id="e9a17-205">Under the Cloud discovery settings, select **Microsoft Defender ATP integration**, then enable the integration.</span></span> <span data-ttu-id="e9a17-206">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="e9a17-206">Click **Save**.</span></span>
<span data-ttu-id="e9a17-207">![图像 of_page](../../media/mtp-eval-56.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-207">![Image of_page](../../media/mtp-eval-56.png)</span></span> <br>

5. <span data-ttu-id="e9a17-208">在 "云发现设置" 下，选择 "**用户扩充**"，然后启用与 Azure Active Directory 的集成。</span><span class="sxs-lookup"><span data-stu-id="e9a17-208">Under Cloud discovery settings, select **User enrichment**, then enable the integration with Azure Active Directory.</span></span>
<span data-ttu-id="e9a17-209">![图像 of_page](../../media/mtp-eval-57.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-209">![Image of_page](../../media/mtp-eval-57.png)</span></span> <br>

## <a name="configure-microsoft-defender-advanced-threat-protection"></a><span data-ttu-id="e9a17-210">配置 Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="e9a17-210">Configure Microsoft Defender Advanced Threat Protection</span></span>
>[!NOTE]
><span data-ttu-id="e9a17-211">如果已启用 Microsoft Defender 高级威胁防护，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="e9a17-211">Skip this step if you have already enabled Microsoft Defender Advanced Threat Protection.</span></span>

1. <span data-ttu-id="e9a17-212">导航到 microsoft**Defender 安全中心**的[microsoft 365 安全中心](https://security.microsoft.com/info) > **更多资源** > 。</span><span class="sxs-lookup"><span data-stu-id="e9a17-212">Navigate to [Microsoft 365 Security Center](https://security.microsoft.com/info) > **More Resources** > **Microsoft Defender Security Center**.</span></span> <span data-ttu-id="e9a17-213">单击“打开”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="e9a17-213">Click **Open**.</span></span>
<br><span data-ttu-id="e9a17-214">![图像 of_page](../../media/mtp-eval-58.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-214">![Image of_page](../../media/mtp-eval-58.png)</span></span> <br>
 
2. <span data-ttu-id="e9a17-215">遵循 Microsoft Defender 高级威胁防护向导。</span><span class="sxs-lookup"><span data-stu-id="e9a17-215">Follow the Microsoft Defender Advanced Threat Protection wizard.</span></span> <span data-ttu-id="e9a17-216">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9a17-216">Click **Next**.</span></span> 
<br><span data-ttu-id="e9a17-217">![图像 of_page](../../media/mtp-eval-59.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-217">![Image of_page](../../media/mtp-eval-59.png)</span></span> <br>

3. <span data-ttu-id="e9a17-218">选择 "基于您的首选数据存储位置"、"数据保留策略"、"组织大小" 和 "选择性加入预览" 功能。</span><span class="sxs-lookup"><span data-stu-id="e9a17-218">Choose based on your preferred data storage location, data retention policy, organization size, and opt-in for preview features.</span></span> 
<br><span data-ttu-id="e9a17-219">![图像 of_page](../../media/mtp-eval-60.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-219">![Image of_page](../../media/mtp-eval-60.png)</span></span> <br>
>[!NOTE]
><span data-ttu-id="e9a17-220">之后，您无法更改某些设置，如数据存储位置。</span><span class="sxs-lookup"><span data-stu-id="e9a17-220">You cannot change some of the settings, like data storage location, afterwards.</span></span> 
<br>

<span data-ttu-id="e9a17-221">单击“**下一步**”。</span><span class="sxs-lookup"><span data-stu-id="e9a17-221">Click **Next**.</span></span> 

4. <span data-ttu-id="e9a17-222">单击 "**继续**"，它将预配你的 MICROSOFT Defender ATP 租户。</span><span class="sxs-lookup"><span data-stu-id="e9a17-222">Click **Continue** and it will provision your Microsoft Defender ATP tenant.</span></span>
<br><span data-ttu-id="e9a17-223">![图像 of_page](../../media/mtp-eval-61.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-223">![Image of_page](../../media/mtp-eval-61.png)</span></span> <br>

5. <span data-ttu-id="e9a17-224">通过组策略、Microsoft 终结点管理器或通过运行本地脚本到 Microsoft Defender ATP 来集成你的终结点。</span><span class="sxs-lookup"><span data-stu-id="e9a17-224">Onboard your endpoints through Group Policies, Microsoft Endpoint Manager or by running a local script to Microsoft Defender ATP.</span></span> <span data-ttu-id="e9a17-225">为简单起见，本指南使用本地脚本。</span><span class="sxs-lookup"><span data-stu-id="e9a17-225">For simplicity, this guide uses the local script.</span></span>

6. <span data-ttu-id="e9a17-226">单击 "**下载包**"，并将载入脚本复制到终结点。</span><span class="sxs-lookup"><span data-stu-id="e9a17-226">Click **Download package** and copy the onboarding script to your endpoint(s).</span></span>  
<br><span data-ttu-id="e9a17-227">![图像 of_page](../../media/mtp-eval-62.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-227">![Image of_page](../../media/mtp-eval-62.png)</span></span> <br>

7. <span data-ttu-id="e9a17-228">在终结点上，以管理员身份运行载入脚本，然后选择 "Y"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-228">On your endpoint, run the onboarding script as Administrator and choose Y.</span></span>
<br><span data-ttu-id="e9a17-229">![图像 of_page](../../media/mtp-eval-63.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-229">![Image of_page](../../media/mtp-eval-63.png)</span></span> <br>

8. <span data-ttu-id="e9a17-230">恭喜，你已载入你的第一个终结点。</span><span class="sxs-lookup"><span data-stu-id="e9a17-230">Congratulations, you have onboarded your first endpoint.</span></span>  
<br>![图像 of_page](../../media/mtp-eval-64.png) <br>

9. <span data-ttu-id="e9a17-232">从 Microsoft Defender ATP 向导复制并粘贴检测测试。</span><span class="sxs-lookup"><span data-stu-id="e9a17-232">Copy-paste the detection test from the Microsoft Defender ATP wizard.</span></span>
<br><span data-ttu-id="e9a17-233">![图像 of_page](../../media/mtp-eval-65.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-233">![Image of_page](../../media/mtp-eval-65.png)</span></span> <br>

10. <span data-ttu-id="e9a17-234">将 PowerShell 脚本复制到提升的命令提示符，然后运行它。</span><span class="sxs-lookup"><span data-stu-id="e9a17-234">Copy the PowerShell script to an elevated command prompt and run it.</span></span> 
<br><span data-ttu-id="e9a17-235">![图像 of_page](../../media/mtp-eval-66.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-235">![Image of_page](../../media/mtp-eval-66.png)</span></span> <br>

11. <span data-ttu-id="e9a17-236">从向导中选择 "**开始使用 Microsoft DEFENDER ATP** "。</span><span class="sxs-lookup"><span data-stu-id="e9a17-236">Select **Start using Microsoft Defender ATP** from the Wizard.</span></span>
<br><span data-ttu-id="e9a17-237">![图像 of_page](../../media/mtp-eval-67.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-237">![Image of_page](../../media/mtp-eval-67.png)</span></span> <br>
 
12. <span data-ttu-id="e9a17-238">访问[Microsoft Defender 安全中心](https://securitycenter.windows.com/)。</span><span class="sxs-lookup"><span data-stu-id="e9a17-238">Visit the [Microsoft Defender Security Center](https://securitycenter.windows.com/).</span></span> <span data-ttu-id="e9a17-239">转到 "**设置**"，然后选择 "**高级功能**"。</span><span class="sxs-lookup"><span data-stu-id="e9a17-239">Go to **Settings** and then select **Advanced features**.</span></span> 
<br><span data-ttu-id="e9a17-240">![图像 of_page](../../media/mtp-eval-68.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-240">![Image of_page](../../media/mtp-eval-68.png)</span></span> <br>

13. <span data-ttu-id="e9a17-241">启用与**Azure 高级威胁防护**的集成。</span><span class="sxs-lookup"><span data-stu-id="e9a17-241">Turn on the integration with **Azure Advanced Threat Protection**.</span></span>  
<br><span data-ttu-id="e9a17-242">![图像 of_page](../../media/mtp-eval-69.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-242">![Image of_page](../../media/mtp-eval-69.png)</span></span> <br>

14. <span data-ttu-id="e9a17-243">启用与**Office 365 威胁智能**的集成。</span><span class="sxs-lookup"><span data-stu-id="e9a17-243">Turn on the integration with **Office 365 Threat Intelligence**.</span></span>
<br><span data-ttu-id="e9a17-244">![图像 of_page](../../media/mtp-eval-70.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-244">![Image of_page](../../media/mtp-eval-70.png)</span></span> <br>

15. <span data-ttu-id="e9a17-245">启用与**Microsoft 云应用安全性**的集成。</span><span class="sxs-lookup"><span data-stu-id="e9a17-245">Turn on integration with **Microsoft Cloud App Security**.</span></span>
<br><span data-ttu-id="e9a17-246">![图像 of_page](../../media/mtp-eval-71.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-246">![Image of_page](../../media/mtp-eval-71.png)</span></span> <br>

16. <span data-ttu-id="e9a17-247">向下滚动，然后单击 "**保存首选项**" 以确认新的集成。</span><span class="sxs-lookup"><span data-stu-id="e9a17-247">Scroll down and click **Save preferences** to confirm the new integrations.</span></span>
<br><span data-ttu-id="e9a17-248">![图像 of_page](../../media/mtp-eval-72.png)</span><span class="sxs-lookup"><span data-stu-id="e9a17-248">![Image of_page](../../media/mtp-eval-72.png)</span></span> <br>

## <a name="next-steps"></a><span data-ttu-id="e9a17-249">后续步骤</span><span class="sxs-lookup"><span data-stu-id="e9a17-249">Next steps</span></span>
<span data-ttu-id="e9a17-250">[打开 Microsoft 威胁防护](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service)，然后[生成测试警报](generate-test-alert.md)。</span><span class="sxs-lookup"><span data-stu-id="e9a17-250">[Turn on Microsoft Threat Protection](https://docs.microsoft.com/microsoft-365/security/mtp/mtp-enable?view=o365-worldwide#start-using-the-service) and then [generate a test alert](generate-test-alert.md).</span></span>
