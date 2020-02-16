---
title: 为 Microsoft 365 企业版测试环境增加了 Microsoft 365 安全性
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 12/09/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南可启用 Microsoft 365 企业版测试环境中的其他 Microsoft 365 安全设置。
ms.openlocfilehash: 465e9df40e8dfe9883a81d352eabff17151df8f3
ms.sourcegitcommit: 3dd9944a6070a7f35c4bc2b57df397f844c3fe79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2020
ms.locfileid: "42067259"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ffb90-103">为 Microsoft 365 企业版测试环境增加了 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="ffb90-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ffb90-104">*此测试实验室指南仅可用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="ffb90-104">*This Test Lab Guide can only be used for Microsoft 365 Enterprise test environments.*</span></span>

<span data-ttu-id="ffb90-105">使用本文中的说明，您可以配置其他 Microsoft 365 设置以提高 Microsoft 365 企业版测试环境的安全性。</span><span class="sxs-lookup"><span data-stu-id="ffb90-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![适用于 Microsoft 云的测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="ffb90-107">单击[此处](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="ffb90-107">Click [here](../media/m365-enterprise-test-lab-guides/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="ffb90-108">阶段 1：构建 Microsoft 365 企业版测试环境。</span><span class="sxs-lookup"><span data-stu-id="ffb90-108">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="ffb90-109">如果只想使用最低要求以轻型方式配置增加的 Microsoft 365 安全，请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="ffb90-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="ffb90-110">如果要在模拟的企业中配置增加的 Microsoft 365 安全，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="ffb90-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="ffb90-111">测试增强的 Microsoft 365 安全不需要模拟企业测试环境，其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务（AD DS）林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="ffb90-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="ffb90-112">此处提供了此选项，以便您可以测试自动授权和组成员身份，并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="ffb90-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="ffb90-113">第2阶段：配置增强的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="ffb90-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="ffb90-114">在这一阶段，您为 Microsoft 365 企业版测试环境启用了增强的 Microsoft 365 安全性。</span><span class="sxs-lookup"><span data-stu-id="ffb90-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="ffb90-115">有关其他详细信息和设置，请参阅[Configure a Office 365 租户以提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。</span><span class="sxs-lookup"><span data-stu-id="ffb90-115">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="ffb90-116">配置 SharePoint Online 以阻止不支持新式身份验证的应用程序</span><span class="sxs-lookup"><span data-stu-id="ffb90-116">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="ffb90-117">不支持新式身份验证的应用程序不能对其应用[标识和设备访问配置](microsoft-365-policies-configurations.md)，这是保护 Microsoft 365 订阅及其数字资产的重要因素。</span><span class="sxs-lookup"><span data-stu-id="ffb90-117">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="ffb90-118">转到 Microsoft 365 管理中心（[https://portal.microsoft.com](https://portal.microsoft.com)），并使用全局管理员帐户登录到你的 microsoft 365 测试实验室订阅。</span><span class="sxs-lookup"><span data-stu-id="ffb90-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="ffb90-119">如果使用的是轻型 Microsoft 365 测试环境，请从你的本地计算机登录。</span><span class="sxs-lookup"><span data-stu-id="ffb90-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="ffb90-120">如果使用的是模拟企业 Microsoft 365 测试环境，请使用[Azure 门户](https://portal.azure.com)连接到 CLIENT1 虚拟机，然后从 CLIENT1 登录。</span><span class="sxs-lookup"><span data-stu-id="ffb90-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="ffb90-121">在 "新建**Microsoft 365 管理中心**" 选项卡上的左侧导航窗格中的 "**管理中心**" 下，单击 " **SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="ffb90-122">在 "新建**SharePoint 管理中心**" 选项卡上，单击 "**访问控制**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="ffb90-123">单击 "**不支持新式身份验证的应用**"，选择 "**阻止访问**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-123">Click **Apps that don’t support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="ffb90-124">为 SharePoint、OneDrive for Business 和 Microsoft 团队启用高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="ffb90-124">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="ffb90-125">适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 高级威胁防护（ATP）可防止您的组织无意中共享恶意文件。</span><span class="sxs-lookup"><span data-stu-id="ffb90-125">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="ffb90-126">转到 " [Office 365 安全 & 合规中心](https://protection.office.com)"，并使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ffb90-126">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="ffb90-127">在左侧导航窗格中的 "**威胁管理**" 下，单击 "**策略**"，然后单击 " **ATP 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **ATP safe attachments**.</span></span> 

3. <span data-ttu-id="ffb90-128">在 "**保护 SharePoint、OneDrive 和 Microsoft 团队中的文件**" 下。</span><span class="sxs-lookup"><span data-stu-id="ffb90-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="ffb90-129">选择 "**为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="ffb90-130">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="ffb90-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="ffb90-131">启用反恶意软件</span><span class="sxs-lookup"><span data-stu-id="ffb90-131">Enable anti-malware</span></span>

<span data-ttu-id="ffb90-132">"恶意软件"包括病毒和间谍软件。</span><span class="sxs-lookup"><span data-stu-id="ffb90-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="ffb90-133">"病毒"会感染其他程序与数据，且会在整个计算机中寻找程序进行感染。</span><span class="sxs-lookup"><span data-stu-id="ffb90-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="ffb90-134">“间谍软件”指收集您的个人信息（如登录信息和个人数据），并将其发送给恶意软件作者的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="ffb90-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="ffb90-135">Microsoft 365 具有内置的恶意软件和垃圾邮件筛选功能，可帮助保护入站和出站邮件免受恶意软件的攻击，并帮助保护您免受垃圾邮件的攻击。</span><span class="sxs-lookup"><span data-stu-id="ffb90-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="ffb90-136">有关详细信息，请参阅[反垃圾邮件 & Office 365 中的反恶意软件保护](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="ffb90-136">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="ffb90-137">若要确保正在对具有常见附件文件类型的文件执行反恶意软件处理，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="ffb90-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="ffb90-138">单击浏览器上的 "后退" 按钮返回到 "**策略**" 页。</span><span class="sxs-lookup"><span data-stu-id="ffb90-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="ffb90-139">单击 "**反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="ffb90-140">双击名为 "**默认**" 的策略。</span><span class="sxs-lookup"><span data-stu-id="ffb90-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="ffb90-141">在 "**反恶意软件策略**" 窗口中，单击 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="ffb90-142">在 "**常用附件类型筛选器**" 下，选择 **"启用**"，然后单击 "**保存**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="ffb90-143">第3阶段：检查安全仪表板</span><span class="sxs-lookup"><span data-stu-id="ffb90-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="ffb90-144">Office 365 的威胁管理可帮助您控制和管理对组织数据的移动设备访问，帮助保护组织不会丢失数据，并帮助保护入站和出站邮件免受恶意软件和垃圾邮件的攻击。</span><span class="sxs-lookup"><span data-stu-id="ffb90-144">Office 365 threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="ffb90-145">您还可以使用威胁管理来保护您的域的信誉，并确定发件人是否是您的域中的恶意欺骗帐户。</span><span class="sxs-lookup"><span data-stu-id="ffb90-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="ffb90-146">若要查看安全仪表板：</span><span class="sxs-lookup"><span data-stu-id="ffb90-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="ffb90-147">如果需要，请转到[Office 365 Security & 合规性中心](https://protection.office.com)，并使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="ffb90-147">If needed, go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="ffb90-148">在左侧导航窗格中的 "**威胁管理**" 下，单击 "**仪表板**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="ffb90-149">仔细查看仪表板上的所有卡片以熟悉提供的信息。</span><span class="sxs-lookup"><span data-stu-id="ffb90-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="ffb90-150">有关详细信息，请参阅[安全仪表板](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard)。</span><span class="sxs-lookup"><span data-stu-id="ffb90-150">For more information, see [Security Dashboard](https://docs.microsoft.com/microsoft-365/security/office-365-security/security-dashboard).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="ffb90-151">第4阶段：检查 Microsoft 安全分数</span><span class="sxs-lookup"><span data-stu-id="ffb90-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="ffb90-152">Microsoft 安全分数将安全状态显示为一个数字，表示您的当前级别相对于订阅中可用的功能。</span><span class="sxs-lookup"><span data-stu-id="ffb90-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="ffb90-153">此外，它还提供了可执行的改进操作的列表，以提高成绩。</span><span class="sxs-lookup"><span data-stu-id="ffb90-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="ffb90-154">在浏览器中创建新的选项卡，然后转到[Microsoft 365 安全中心](https://security.microsoft.com/)，然后单击 "**安全得分**"。</span><span class="sxs-lookup"><span data-stu-id="ffb90-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="ffb90-155">在 "**概述**" 选项卡上，记下当前安全分数以及它与全局平均和订阅（具有相似数量的许可证）的比较方式。</span><span class="sxs-lookup"><span data-stu-id="ffb90-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="ffb90-156">在 "**改进操作**" 选项卡上，阅读可执行的操作列表，以增加成绩。</span><span class="sxs-lookup"><span data-stu-id="ffb90-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="ffb90-157">有关详细信息，请参阅[Microsoft 安全分数](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score)。</span><span class="sxs-lookup"><span data-stu-id="ffb90-157">For more information, see [Microsoft Secure Score](https://docs.microsoft.com/microsoft-365/security/mtp/microsoft-secure-score).</span></span>

## <a name="next-steps"></a><span data-ttu-id="ffb90-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="ffb90-158">Next steps</span></span>

<span data-ttu-id="ffb90-159">有关信息**保护**阶段中的 "为[Microsoft 365 配置增强的安全性](infoprotect-configure-increased-security-office-365.md)" 步骤，请参阅在生产中配置这些设置的信息和链接。</span><span class="sxs-lookup"><span data-stu-id="ffb90-159">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="ffb90-160">在您的测试环境中浏览其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="ffb90-160">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="ffb90-161">另请参阅</span><span class="sxs-lookup"><span data-stu-id="ffb90-161">See also</span></span>

[<span data-ttu-id="ffb90-162">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="ffb90-162">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="ffb90-163">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="ffb90-163">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="ffb90-164">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="ffb90-164">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)
