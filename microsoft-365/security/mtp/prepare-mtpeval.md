---
title: 准备你的 Microsoft 365 Defender 试用实验室环境
description: 在设置 Microsoft 365 Defender 试用版实验室或试点环境时，准备利益干系人签署、时间线、环境注意事项和采用顺序
keywords: MTP 试用准备、MTP 试点准备、准备运行 MTP 试点项目、运行试点 MTP 项目、部署、准备、利益干系人、日程表、环境、终结点、服务器、管理、采用
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
ms.openlocfilehash: a255c74db030325ba22c2095fba732a93b8c269c
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48844844"
---
# <a name="prepare-your-microsoft-365-defender-trial-lab-or-pilot-environment"></a><span data-ttu-id="b948e-104">准备 Microsoft 365 Defender 试用版实验室或试点环境</span><span class="sxs-lookup"><span data-stu-id="b948e-104">Prepare your Microsoft 365 Defender trial lab or pilot environment</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="b948e-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="b948e-105">**Applies to:**</span></span>
- <span data-ttu-id="b948e-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="b948e-106">Microsoft 365 Defender</span></span>

<span data-ttu-id="b948e-107">创建 Microsoft 365 Defender 试用版实验室或试点环境并对其进行部署的过程分为三个阶段：</span><span class="sxs-lookup"><span data-stu-id="b948e-107">Creating a Microsoft 365 Defender trial lab or pilot environment and deploying it is a three-phase process:</span></span>

<br>
<table border="0" width="100%" align="center">
  <tr style="text-align:center;">
    <td align="center" style="width:25%; border:0;" bgcolor="#d5f5e3">
      <a href= "https://docs.microsoft.com/microsoft-365/security/mtp/prepare-mtpeval"> 
        <img src="../../media/prepare.png" alt="Prepare your Microsoft 365 Defender trial lab environment" title="准备 Microsoft 365 Defender 试用版实验室或试点环境" />
      <br/><span data-ttu-id="b948e-109">第1阶段：准备 </a></span><span class="sxs-lookup"><span data-stu-id="b948e-109">Phase 1: Prepare </a></span></span><br>
    </td>
     <td align="center"  >
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/setup-mtpeval">
        <img src="../../media/setup.png" alt="Set up your Microsoft 365 Defender trial lab environment" title="设置你的 Microsoft 365 Defender 试用版实验室或试点环境" />
      <br/><span data-ttu-id="b948e-111">阶段2：安装程序 </a></span><span class="sxs-lookup"><span data-stu-id="b948e-111">Phase 2: Setup </a></span></span><br>
        </td>
    <td align="center">
      <a href="https://docs.microsoft.com/microsoft-365/security/mtp/config-mtpeval">
        <img src="../../media/config-onboard.png" alt="Configure each Microsoft 365 Defender pillar" title="配置每个 Microsoft 365 Defender 支柱和终结点的板载" />
      <br/><span data-ttu-id="b948e-113">第3阶段： Configure & 板载</a></span><span class="sxs-lookup"><span data-stu-id="b948e-113">Phase 3: Configure & Onboard</a></span></span><br>
</td>
  </tr>
  <tr>
    <td style="width:25%; border:0;">
   
    </td>
    <td valign="top" style="width:25%; border:0;">
    
</td>
    <td valign="top" style="width:25%; border:0;">

</td>    
  </tr>
</table>

<span data-ttu-id="b948e-114">你当前正在准备阶段。</span><span class="sxs-lookup"><span data-stu-id="b948e-114">You're currently in the preparation phase.</span></span>


<span data-ttu-id="b948e-115">准备工作是任何成功部署的关键。</span><span class="sxs-lookup"><span data-stu-id="b948e-115">Preparation is key to any successful deployment.</span></span> <span data-ttu-id="b948e-116">本部分将指导您在准备为 Microsoft 365 Defender 部署创建试用实验室或试点环境时需要考虑的事项。</span><span class="sxs-lookup"><span data-stu-id="b948e-116">This section will guide you through what you need to consider as you prepare to create a trial lab or pilot environment for your Microsoft 365 Defender deployment.</span></span>

## <a name="prerequisites"></a><span data-ttu-id="b948e-117">必备条件</span><span class="sxs-lookup"><span data-stu-id="b948e-117">Prerequisites</span></span>
<span data-ttu-id="b948e-118">了解有关设置和使用 Microsoft 365 Defender 的许可、硬件和软件要求以及其他配置设置。</span><span class="sxs-lookup"><span data-stu-id="b948e-118">Learn about the licensing, hardware and software requirements, and other configuration settings to provision and use Microsoft 365 Defender.</span></span> <span data-ttu-id="b948e-119">请参阅 [microsoft 365 defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites)、 [Microsoft defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements)、 [microsoft defender For Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description)、 [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)、 [microsoft 云应用安全性](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites)的最低要求。</span><span class="sxs-lookup"><span data-stu-id="b948e-119">See the minimum requirements for [Microsoft 365 Defender](https://docs.microsoft.com/microsoft-365/security/mtp/prerequisites), [Microsoft Defender for Endpoint](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/minimum-requirements), [Microsoft Defender for Office 365](https://docs.microsoft.com/office365/servicedescriptions/office-365-advanced-threat-protection-service-description), [Microsoft Defender for Identity](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites), [Microsoft Cloud App Security](https://docs.microsoft.com/azure-advanced-threat-protection/atp-prerequisites).</span></span>

## <a name="stakeholders-and-sign-off"></a><span data-ttu-id="b948e-120">利益干系人和签署</span><span class="sxs-lookup"><span data-stu-id="b948e-120">Stakeholders and sign-off</span></span>
<span data-ttu-id="b948e-121">确定项目中涉及的所有利益干系人以及可能需要签署、查看或随时通知的所有利益干系人，无论是评估还是运行试点项目。</span><span class="sxs-lookup"><span data-stu-id="b948e-121">Identify all the stakeholders that are involved in the project and who may need to sign-off, review, or stay informed, whether for evaluation or running a pilot project.</span></span>

>[!NOTE]
><span data-ttu-id="b948e-122">并非所有组织都可能具有此类角色的安全组织成熟度。</span><span class="sxs-lookup"><span data-stu-id="b948e-122">Not all organizations might have the security organization maturity to have such roles.</span></span> <span data-ttu-id="b948e-123">在这种情况下，请与您的领导团队联系，了解审阅和批准责任。</span><span class="sxs-lookup"><span data-stu-id="b948e-123">In such case, consult with your leadership team on review and approval accountabilities.</span></span>

<span data-ttu-id="b948e-124">根据您的组织的需要，向下表中添加利益干系人。</span><span class="sxs-lookup"><span data-stu-id="b948e-124">Add stakeholders to the table below as appropriate for your organization.</span></span>

-   <span data-ttu-id="b948e-125">SO = 此项目上的注销</span><span class="sxs-lookup"><span data-stu-id="b948e-125">SO = Sign-off on this project</span></span>

-   <span data-ttu-id="b948e-126">R = 查看此项目并提供输入</span><span class="sxs-lookup"><span data-stu-id="b948e-126">R = Review this project and provide input</span></span>

-   <span data-ttu-id="b948e-127">I = 此项目的通知</span><span class="sxs-lookup"><span data-stu-id="b948e-127">I = Informed of this project</span></span>

| <span data-ttu-id="b948e-128">名称</span><span class="sxs-lookup"><span data-stu-id="b948e-128">Name</span></span>                 | <span data-ttu-id="b948e-129">Role</span><span class="sxs-lookup"><span data-stu-id="b948e-129">Role</span></span>                                                                                                                                                                                                          | <span data-ttu-id="b948e-130">Action</span><span class="sxs-lookup"><span data-stu-id="b948e-130">Action</span></span> |
|----------------------|---------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|--------|
| <span data-ttu-id="b948e-131">输入名称和电子邮件</span><span class="sxs-lookup"><span data-stu-id="b948e-131">Enter name and email</span></span> | <span data-ttu-id="b948e-132">**首席信息安全专员 (CISO)** *作为新技术部署的组织中充当承办人的执行者。*</span><span class="sxs-lookup"><span data-stu-id="b948e-132">**Chief Information Security Officer (CISO)** *An executive representative who serves as sponsor inside the organization for the new technology deployment.*</span></span>                                                  | <span data-ttu-id="b948e-133">就</span><span class="sxs-lookup"><span data-stu-id="b948e-133">SO</span></span>     |
| <span data-ttu-id="b948e-134">输入名称和电子邮件</span><span class="sxs-lookup"><span data-stu-id="b948e-134">Enter name and email</span></span> | <span data-ttu-id="b948e-135">" **网络防护运营中心" (CDOC)** *来自 CDOC 团队的代表，负责定义如何将此更改与客户安全操作团队中的过程相一致。*</span><span class="sxs-lookup"><span data-stu-id="b948e-135">**Head of Cyber Defense Operations Center (CDOC)** *A representative from the CDOC team in charge of defining how this change is aligned with the processes in the customers security operations team.*</span></span>       | <span data-ttu-id="b948e-136">就</span><span class="sxs-lookup"><span data-stu-id="b948e-136">SO</span></span>     |
| <span data-ttu-id="b948e-137">输入名称和电子邮件</span><span class="sxs-lookup"><span data-stu-id="b948e-137">Enter name and email</span></span> | <span data-ttu-id="b948e-138">\**安全\*\*\*团队中的一名代表，负责定义如何将此更改与组织中的核心安全体系结构保持一致。*</span><span class="sxs-lookup"><span data-stu-id="b948e-138">**Security Architect** *A representative from the Security team in charge of defining how this change is aligned with the core Security architecture in the organization.*</span></span>                         | <span data-ttu-id="b948e-139">R</span><span class="sxs-lookup"><span data-stu-id="b948e-139">R</span></span>      |
| <span data-ttu-id="b948e-140">输入名称和电子邮件</span><span class="sxs-lookup"><span data-stu-id="b948e-140">Enter name and email</span></span> | <span data-ttu-id="b948e-141">\**工作场所架构师\*\*\*由 IT 团队负责定义此更改与组织中的核心工作区体系结构的对齐方式。*</span><span class="sxs-lookup"><span data-stu-id="b948e-141">**Workplace Architect** *A representative from the IT team in charge of defining how this change is aligned with the core workplace architecture in the organization.*</span></span>                             | <span data-ttu-id="b948e-142">R</span><span class="sxs-lookup"><span data-stu-id="b948e-142">R</span></span>      |
| <span data-ttu-id="b948e-143">输入名称和电子邮件</span><span class="sxs-lookup"><span data-stu-id="b948e-143">Enter name and email</span></span> | <span data-ttu-id="b948e-144">\**安全分析员\*\*\*来自 CDOC 团队的代表，可提供有关安全操作透视的检测功能、用户体验以及此更改的总体有用性的反馈。*</span><span class="sxs-lookup"><span data-stu-id="b948e-144">**Security Analyst** *A representative from the CDOC team who can provide feedback on the detection capabilities, user experience, and overall usefulness of this change from a security operations perspective.*</span></span> | <span data-ttu-id="b948e-145">I</span><span class="sxs-lookup"><span data-stu-id="b948e-145">I</span></span>      |

## <a name="prepare-your-azure-active-directory"></a><span data-ttu-id="b948e-146">准备 Azure Active Directory</span><span class="sxs-lookup"><span data-stu-id="b948e-146">Prepare your Azure Active Directory</span></span>
<span data-ttu-id="b948e-147">如果已启用本地 Active directory 和 Azure Active Directory 之间的同步，请跳过此步骤。</span><span class="sxs-lookup"><span data-stu-id="b948e-147">Skip this step if you have already enabled synchronization between Active Directory and Azure Active Directory on premises.</span></span> <span data-ttu-id="b948e-148">查看 Azure Active Directory 中现有的最佳实践文档。</span><span class="sxs-lookup"><span data-stu-id="b948e-148">Review existing best practices documentation from Azure Active Directory.</span></span> <span data-ttu-id="b948e-149">以下步骤经过优化，可评估或运行试点 Microsoft 365 Defender 项目。</span><span class="sxs-lookup"><span data-stu-id="b948e-149">The following steps are optimized to evaluate or run a pilot Microsoft 365 Defender project.</span></span>

1. <span data-ttu-id="b948e-150">请转到 [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) 门户 > **azure AD Connect** 。</span><span class="sxs-lookup"><span data-stu-id="b948e-150">Go to the [Azure Active Directory](https://portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade) portal > **Azure AD Connect**.</span></span> 
<span data-ttu-id="b948e-151">![Azure Active Directory 门户页面的图像](../../media/mtp-eval-1.png)</span><span class="sxs-lookup"><span data-stu-id="b948e-151">![Image of Azure Active Directory portal page](../../media/mtp-eval-1.png)</span></span> <br> 

2. <span data-ttu-id="b948e-152">单击 **"** 从 **Microsoft Azure Active Directory 连接** "，并将其传输到域控制器。</span><span class="sxs-lookup"><span data-stu-id="b948e-152">Click **Download** from **Microsoft Azure Active Directory Connect** and transfer it to your Domain Controller.</span></span>
<span data-ttu-id="b948e-153">![Azure Active Directoru Connect 下载页面的图像](../../media/mtp-eval-2.png)</span><span class="sxs-lookup"><span data-stu-id="b948e-153">![Image of Azure Active Directoru Connect download page](../../media/mtp-eval-2.png)</span></span> <br>

3. <span data-ttu-id="b948e-154">在域控制器上，按照 Azure Active Directory 连接向导。</span><span class="sxs-lookup"><span data-stu-id="b948e-154">On the domain controller, follow the Azure Active Directory Connect wizard.</span></span> <span data-ttu-id="b948e-155">阅读许可条款和隐私声明，如果同意，请选中此复选框。</span><span class="sxs-lookup"><span data-stu-id="b948e-155">Read the license terms and privacy notice and select the checkbox if you agree.</span></span> <span data-ttu-id="b948e-156">单击"继续"。</span><span class="sxs-lookup"><span data-stu-id="b948e-156">Click **Continue**.</span></span>
<span data-ttu-id="b948e-157">![Azure AD Connect "欢迎" 页面的图像](../../media/mtp-eval-3.png)</span><span class="sxs-lookup"><span data-stu-id="b948e-157">![Image of Azure AD Connect welcome page](../../media/mtp-eval-3.png)</span></span> <br>

4. <span data-ttu-id="b948e-158">导航到 " **Express 设置** "。</span><span class="sxs-lookup"><span data-stu-id="b948e-158">Navigate to **Express Settings**.</span></span>
<span data-ttu-id="b948e-159">![快速设置页面的图像](../../media/mtp-eval-4.png)</span><span class="sxs-lookup"><span data-stu-id="b948e-159">![Image of Express Settings page](../../media/mtp-eval-4.png)</span></span> <br>

5. <span data-ttu-id="b948e-160">输入全局管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="b948e-160">Enter your global administrator credentials.</span></span> <span data-ttu-id="b948e-161">单击“ **下一步** ”。</span><span class="sxs-lookup"><span data-stu-id="b948e-161">Click **Next**.</span></span>
<span data-ttu-id="b948e-162">![应在其中输入全局管理员凭据的 "连接到 Azure AD" 页面的图像](../../media/mtp-eval-5.png)</span><span class="sxs-lookup"><span data-stu-id="b948e-162">![Image of Connect to Azure AD page where you should enter your global administrator credentials](../../media/mtp-eval-5.png)</span></span> <br>

6. <span data-ttu-id="b948e-163">输入你的 Active Directory 域服务企业管理员凭据。</span><span class="sxs-lookup"><span data-stu-id="b948e-163">Enter your Active Directory Domain Services enterprise administrator credentials.</span></span> <span data-ttu-id="b948e-164">单击“ **下一步** ”。</span><span class="sxs-lookup"><span data-stu-id="b948e-164">Click **Next**.</span></span>
<span data-ttu-id="b948e-165">![应在其中输入凭据的 "连接到 AD DS" 页的图像](../../media/mtp-eval-6.png)</span><span class="sxs-lookup"><span data-stu-id="b948e-165">![Image of Connect to AD DS page where you should enter your credentials](../../media/mtp-eval-6.png)</span></span> <br>

7. <span data-ttu-id="b948e-166">单击 " **安装** " 以确认配置。</span><span class="sxs-lookup"><span data-stu-id="b948e-166">Click **Install** to confirm the configuration.</span></span>
<span data-ttu-id="b948e-167">![配置确认页的图像](../../media/mtp-eval-7.png)</span><span class="sxs-lookup"><span data-stu-id="b948e-167">![Image of configuration confirmation page](../../media/mtp-eval-7.png)</span></span> <br>

8. <span data-ttu-id="b948e-168">恭喜，你已成功配置 Azure Active Directory Connect。</span><span class="sxs-lookup"><span data-stu-id="b948e-168">Congratulations, you have successfully configured Azure Active Directory Connect.</span></span>
<span data-ttu-id="b948e-169">![成功配置的 Azure Active Directory Connect 页面的图像](../../media/mtp-eval-8.png)</span><span class="sxs-lookup"><span data-stu-id="b948e-169">![Image of a successfully configured Azure Active Directory Connect page](../../media/mtp-eval-8.png)</span></span> <br>

<span data-ttu-id="b948e-170">您现在可以 [向 Active Directory 中添加用户和组](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) ，并 [配置 SAM-R 策略](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc)。</span><span class="sxs-lookup"><span data-stu-id="b948e-170">You can now [add users and groups to Active Directory](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#bkmk_hydrate) and [configure a SAM-R policy](https://docs.microsoft.com/azure-advanced-threat-protection/atp-playbook-setup-lab#configure-sam-r-capabilities-from-contosodc).</span></span>  


## <a name="configuration-order"></a><span data-ttu-id="b948e-171">配置顺序</span><span class="sxs-lookup"><span data-stu-id="b948e-171">Configuration order</span></span>
<span data-ttu-id="b948e-172">下表显示 Microsoft 建议为试用版实验室或试点环境部署配置 Microsoft 365 Defender 组件的顺序。</span><span class="sxs-lookup"><span data-stu-id="b948e-172">The following table indicates the order Microsoft recommends for configuring the Microsoft 365 Defender components for your trial lab or pilot environment deployment.</span></span>

| <span data-ttu-id="b948e-173">组件</span><span class="sxs-lookup"><span data-stu-id="b948e-173">Component</span></span>                               | <span data-ttu-id="b948e-174">说明</span><span class="sxs-lookup"><span data-stu-id="b948e-174">Description</span></span>                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                                              | <span data-ttu-id="b948e-175">配置顺序排名</span><span class="sxs-lookup"><span data-stu-id="b948e-175">Configuration order rank</span></span> |
|-----------------------------------------|----------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------------|---------------------|
|<span data-ttu-id="b948e-176">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="b948e-176">Microsoft Defender for Office 365</span></span>|<span data-ttu-id="b948e-177">Microsoft Defender for Office 365 保护您的组织免受电子邮件、链接 (Url) 和协作工具带来的恶意威胁的侵扰。</span><span class="sxs-lookup"><span data-stu-id="b948e-177">Microsoft Defender for Office 365 safeguards your organization against malicious threats posed by email messages, links (URLs), and collaboration tools.</span></span> <br> [<span data-ttu-id="b948e-178">了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="b948e-178">Learn more.</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp)                                                                                                                                                                                                                                             | <span data-ttu-id="b948e-179">1</span><span class="sxs-lookup"><span data-stu-id="b948e-179">1</span></span>                   |
|<span data-ttu-id="b948e-180">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="b948e-180">Microsoft Defender for Identity</span></span>|<span data-ttu-id="b948e-181">Microsoft Defender for Identity 使用 Active Directory 信号识别、检测和调查组织中的高级威胁、已泄露身份和恶意内幕活动。</span><span class="sxs-lookup"><span data-stu-id="b948e-181">Microsoft Defender for Identity uses Active Directory signals to identify, detect, and investigate advanced threats, compromised identities, and malicious insider actions directed at your organization.</span></span> <br> <span data-ttu-id="b948e-182">[了解详细信息](https://docs.microsoft.com/azure-advanced-threat-protection/)。</span><span class="sxs-lookup"><span data-stu-id="b948e-182">[Learn more](https://docs.microsoft.com/azure-advanced-threat-protection/).</span></span>| <span data-ttu-id="b948e-183">双面</span><span class="sxs-lookup"><span data-stu-id="b948e-183">2</span></span> |
|<span data-ttu-id="b948e-184">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="b948e-184">Microsoft Cloud App Security</span></span>| <span data-ttu-id="b948e-185">Microsoft 云应用安全是一个云访问安全代理 (CASB) ，可在多个云上运行。</span><span class="sxs-lookup"><span data-stu-id="b948e-185">Microsoft Cloud App Security is a Cloud Access Security Broker (CASB) that operates on multiple clouds.</span></span> <span data-ttu-id="b948e-186">它提供丰富的可见性、控制数据旅行和完善的分析，以跨所有云服务识别和防御威胁。</span><span class="sxs-lookup"><span data-stu-id="b948e-186">It provides rich visibility, control over data travel, and sophisticated analytics to identify and combat cyberthreats across all your cloud services.</span></span> <br> <span data-ttu-id="b948e-187">[了解详细信息](https://docs.microsoft.com/cloud-app-security/)。</span><span class="sxs-lookup"><span data-stu-id="b948e-187">[Learn more](https://docs.microsoft.com/cloud-app-security/).</span></span>                                                                                                                                                                                                                                                                                                                                                                       |<span data-ttu-id="b948e-188">第三章</span><span class="sxs-lookup"><span data-stu-id="b948e-188">3</span></span>                   |
|<span data-ttu-id="b948e-189">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="b948e-189">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="b948e-190">Microsoft Defender for Endpoint endpoint endpoint 检测和响应功能提供了接近实时且可操作的高级攻击检测。</span><span class="sxs-lookup"><span data-stu-id="b948e-190">Microsoft Defender for Endpoint endpoint detection and response capabilities provide advanced attack detections that are near real-time and actionable.</span></span> <span data-ttu-id="b948e-191">安全分析员可以有效地确定警报的优先级，了解整个泄露范围，并采取响应措施来修正威胁。</span><span class="sxs-lookup"><span data-stu-id="b948e-191">Security analysts can prioritize alerts effectively, gain visibility into the full scope of a breach, and take response actions to remediate threats.</span></span> <br> [<span data-ttu-id="b948e-192">了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="b948e-192">Learn more.</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)                                     |<span data-ttu-id="b948e-193">4 </span><span class="sxs-lookup"><span data-stu-id="b948e-193">4</span></span>                   |                                                                                                                                                                                                                                    

## <a name="next-step"></a><span data-ttu-id="b948e-194">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b948e-194">Next step</span></span>
|<span data-ttu-id="b948e-195">![阶段2：安装程序](../../media/setup.png)</span><span class="sxs-lookup"><span data-stu-id="b948e-195">![Phase 2: Setup](../../media/setup.png)</span></span> <br>[<span data-ttu-id="b948e-196">阶段2：安装程序</span><span class="sxs-lookup"><span data-stu-id="b948e-196">Phase 2: Setup</span></span>](setup-mtpeval.md) | <span data-ttu-id="b948e-197">设置你的 Microsoft 365 Defender 试用版实验室或试点环境</span><span class="sxs-lookup"><span data-stu-id="b948e-197">Set up your Microsoft 365 Defender trial lab or pilot environment</span></span>
|:-------|:-----|

