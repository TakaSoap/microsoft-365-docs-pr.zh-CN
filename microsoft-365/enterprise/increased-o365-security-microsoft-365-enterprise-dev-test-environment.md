---
title: 为 Microsoft 365 企业版测试环境增强 Microsoft 365 安全性
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
description: 使用此测试实验室指南启用 Microsoft 365 企业版测试环境的其他 Microsoft 365 安全设置。
ms.openlocfilehash: 928deae34dc16c70776eb512188d1a36ae169da5
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50909782"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b9569-103">为 Microsoft 365 企业版测试环境增强 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="b9569-103">Increased Microsoft 365 security for your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b9569-104">*本测试实验室指南仅适用于 Microsoft 365 企业版测试环境。*</span><span class="sxs-lookup"><span data-stu-id="b9569-104">*This Test Lab Guide can only be used for Microsoft 365 for enterprise test environments.*</span></span>

<span data-ttu-id="b9569-105">按照本文中的说明，配置其他 Microsoft 365 设置以提高 Microsoft 365 企业版测试环境中的安全性。</span><span class="sxs-lookup"><span data-stu-id="b9569-105">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 for enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](../media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="b9569-107">单击[此处](../downloads/Microsoft365EnterpriseTLGStack.pdf)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="b9569-107">Click [here](../downloads/Microsoft365EnterpriseTLGStack.pdf) for a visual map to all the articles in the Microsoft 365 for enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-for-enterprise-test-environment"></a><span data-ttu-id="b9569-108">第 1 阶段：构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="b9569-108">Phase 1: Build out your Microsoft 365 for enterprise test environment</span></span>

<span data-ttu-id="b9569-109">如果你只想按最低要求以轻型方式配置增强的 Microsoft 365 安全性，请按照轻型基本配置 [中的说明操作](lightweight-base-configuration-microsoft-365-enterprise.md)。</span><span class="sxs-lookup"><span data-stu-id="b9569-109">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="b9569-110">如果要在模拟的企业中配置增强的 Microsoft 365 安全性，请按照传递身份验证 [中的说明操作](pass-through-auth-m365-ent-test-environment.md)。</span><span class="sxs-lookup"><span data-stu-id="b9569-110">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="b9569-111">测试提高了 Microsoft 365 安全性不需要模拟的企业测试环境，该环境中包括连接到 Internet 的模拟 Intranet 和 Active Directory 域服务 (AD DS) 目录同步。</span><span class="sxs-lookup"><span data-stu-id="b9569-111">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="b9569-112">它在此处作为一个选项提供，以便你可以测试自动许可和组成员身份，并尝试在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="b9569-112">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 

## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="b9569-113">第 2 阶段：配置增强的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="b9569-113">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="b9569-114">在此阶段，你将为 Microsoft 365 企业版测试环境启用增强的 Microsoft 365 安全性。</span><span class="sxs-lookup"><span data-stu-id="b9569-114">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 for enterprise test environment.</span></span> <span data-ttu-id="b9569-115">有关其他详细信息和设置，请参阅 [配置租户以提升安全性](/office365/securitycompliance/tenant-wide-setup-for-increased-security)。</span><span class="sxs-lookup"><span data-stu-id="b9569-115">For additional details and settings, see [Configure your tenant for increased security](/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="b9569-116">配置 SharePoint Online 以阻止不支持新式验证的应用</span><span class="sxs-lookup"><span data-stu-id="b9569-116">Configure SharePoint Online to block apps that don't support modern authentication</span></span>

<span data-ttu-id="b9569-117">不支持新式身份验证的应用无法应用 [标识](../security/office-365-security/microsoft-365-policies-configurations.md) 和设备访问配置，这是保护 Microsoft 365 订阅及其数字资产的重要元素。</span><span class="sxs-lookup"><span data-stu-id="b9569-117">Apps that do not support modern authentication cannot have [identity and device access configurations](../security/office-365-security/microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="b9569-118">转到 Microsoft 365 管理中心 () 全局管理员帐户登录 [https://portal.microsoft.com](https://portal.microsoft.com) Microsoft 365 测试实验室订阅。</span><span class="sxs-lookup"><span data-stu-id="b9569-118">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Microsoft 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="b9569-119">如果你使用的是轻型 Microsoft 365 测试环境，请从本地计算机登录。</span><span class="sxs-lookup"><span data-stu-id="b9569-119">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="b9569-120">如果你使用的是模拟的企业 Microsoft 365 测试环境，请使用 [Azure](https://portal.azure.com) 门户连接到 CLIENT1 虚拟机，然后从 CLIENT1 登录。</span><span class="sxs-lookup"><span data-stu-id="b9569-120">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="b9569-121">在新的 **Microsoft 365 管理** 中心选项卡上，在左侧导航窗格中的"管理中心"下，单击 **"SharePoint"。** </span><span class="sxs-lookup"><span data-stu-id="b9569-121">On the new **Microsoft 365 admin center** tab, under **Admin centers** in the left navigation pane, click **SharePoint**.</span></span>
3. <span data-ttu-id="b9569-122">在新的 **"SharePoint 管理中心"选项卡** 上，单击">**访问控制"。**</span><span class="sxs-lookup"><span data-stu-id="b9569-122">On the new **SharePoint admin center** tab, click **Policies > Access control**.</span></span>
4. <span data-ttu-id="b9569-123">单击 **不支持新式验证的应用，选择**"**阻止访问**"，然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9569-123">Click **Apps that don't support modern authentication**, select **Block access**, and then click **Save**.</span></span>


### <a name="enable-defender-for-office-365-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="b9569-124">为 SharePoint、OneDrive for Business 和 Microsoft Teams 启用适用于 Office 365 的 Defender</span><span class="sxs-lookup"><span data-stu-id="b9569-124">Enable Defender for Office 365 for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="b9569-125">适用于 SharePoint、OneDrive 和 Microsoft Teams 的 Office 365 Defender 可保护你的组织避免无意中共享恶意文件。</span><span class="sxs-lookup"><span data-stu-id="b9569-125">Defender for Office 365 for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="b9569-126">转到安全 [与&](https://protection.office.com) 中心，然后使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b9569-126">Go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="b9569-127">在左侧导航窗格中的 **"威胁管理**"下，单击"**策略**"，然后单击"**安全附件"。**</span><span class="sxs-lookup"><span data-stu-id="b9569-127">In the left navigation pane, under **Threat management**, click **Policy**, and then click **Safe Attachments**.</span></span> 

3. <span data-ttu-id="b9569-128">在 **"保护 SharePoint、OneDrive 和 Microsoft Teams 中的文件"下**。</span><span class="sxs-lookup"><span data-stu-id="b9569-128">Under **Protect files in SharePoint, OneDrive, and Microsoft Teams**.</span></span> <span data-ttu-id="b9569-129">选择 **"打开适用于 SharePoint、OneDrive 和 Microsoft Teams 的 ATP"。**</span><span class="sxs-lookup"><span data-stu-id="b9569-129">select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="b9569-130">单击“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="b9569-130">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="b9569-131">启用反恶意软件</span><span class="sxs-lookup"><span data-stu-id="b9569-131">Enable anti-malware</span></span>

<span data-ttu-id="b9569-132">"恶意软件"包括病毒和间谍软件。</span><span class="sxs-lookup"><span data-stu-id="b9569-132">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="b9569-133">"病毒"会感染其他程序与数据，且会在整个计算机中寻找程序进行感染。</span><span class="sxs-lookup"><span data-stu-id="b9569-133">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="b9569-134">“间谍软件”指收集您的个人信息（如登录信息和个人数据），并将其发送给恶意软件作者的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="b9569-134">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="b9569-135">Microsoft 365 具有内置的恶意软件和垃圾邮件筛选功能，可帮助保护入站和出站邮件免受恶意软件的攻击，并保护您免受垃圾邮件的侵害。</span><span class="sxs-lookup"><span data-stu-id="b9569-135">Microsoft 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="b9569-136">有关详细信息，请参阅 [反垃圾邮件&反恶意软件保护](../security/office-365-security/anti-spam-and-anti-malware-protection.md)。</span><span class="sxs-lookup"><span data-stu-id="b9569-136">For more information, see [Anti-spam & anti-malware protection](../security/office-365-security/anti-spam-and-anti-malware-protection.md).</span></span>

<span data-ttu-id="b9569-137">为确保对具有常见附件文件类型的文件执行反恶意软件处理：</span><span class="sxs-lookup"><span data-stu-id="b9569-137">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="b9569-138">单击浏览器上的后退按钮返回到"策略 **"** 页面。</span><span class="sxs-lookup"><span data-stu-id="b9569-138">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="b9569-139">单击 **"反恶意软件"。**</span><span class="sxs-lookup"><span data-stu-id="b9569-139">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="b9569-140">双击名为"默认" **的策略**。</span><span class="sxs-lookup"><span data-stu-id="b9569-140">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="b9569-141">在"**反恶意软件策略"窗口中**，单击"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9569-141">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="b9569-142">在"**常见附件类型"筛选器** 下，选择 **"打开"，** 然后单击"保存 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9569-142">Under **Common Attachment Types filter**, select **On**, and then click **Save**.</span></span>


## <a name="phase-3-examine-the-security-dashboard"></a><span data-ttu-id="b9569-143">阶段 3：检查安全仪表板</span><span class="sxs-lookup"><span data-stu-id="b9569-143">Phase 3: Examine the security dashboard</span></span>

<span data-ttu-id="b9569-144">Microsoft 365 中的威胁管理可帮助您控制和管理对组织数据的移动设备访问，帮助保护组织免受数据丢失，并帮助保护入站和出站邮件免受恶意软件和垃圾邮件的攻击。</span><span class="sxs-lookup"><span data-stu-id="b9569-144">Threat management in Microsoft 365 can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="b9569-145">您还可以使用威胁管理来保护域的信誉，并确定发件人是否恶意欺骗域中的帐户。</span><span class="sxs-lookup"><span data-stu-id="b9569-145">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> 

<span data-ttu-id="b9569-146">查看安全仪表板：</span><span class="sxs-lookup"><span data-stu-id="b9569-146">To see the security dashboard:</span></span>

1. <span data-ttu-id="b9569-147">如果需要，请转到安全与 [&](https://protection.office.com) 中心，然后使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="b9569-147">If needed, go to the [Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="b9569-148">在左侧导航窗格中的 **"威胁管理**"下，单击"仪表板 **"。**</span><span class="sxs-lookup"><span data-stu-id="b9569-148">In the left navigation pane, under **Threat management**, click **Dashboard**.</span></span>

<span data-ttu-id="b9569-149">仔细查看仪表板上的所有卡片，以熟悉提供的信息。</span><span class="sxs-lookup"><span data-stu-id="b9569-149">Take a close look at all the cards on the dashboard to familiarize yourself with the information provided.</span></span>

<span data-ttu-id="b9569-150">有关详细信息，请参阅安全 [仪表板](../security/office-365-security/security-dashboard.md)。</span><span class="sxs-lookup"><span data-stu-id="b9569-150">For more information, see [Security Dashboard](../security/office-365-security/security-dashboard.md).</span></span>


## <a name="phase-4-examine-microsoft-secure-score"></a><span data-ttu-id="b9569-151">阶段 4：检查 Microsoft 安全分数</span><span class="sxs-lookup"><span data-stu-id="b9569-151">Phase 4: Examine Microsoft Secure Score</span></span>

<span data-ttu-id="b9569-152">Microsoft 安全功能分数以数字显示安全状态，它指明了相对于订阅中可用功能的当前级别。</span><span class="sxs-lookup"><span data-stu-id="b9569-152">Microsoft Secure Score shows your security posture as a number, which indicates your current level relative to the features that are available in your subscription.</span></span> <span data-ttu-id="b9569-153">它还为你提供了可用于提高分数的改进操作列表。</span><span class="sxs-lookup"><span data-stu-id="b9569-153">It also gives you a list of improvement actions you can take to improve your score.</span></span>

1. <span data-ttu-id="b9569-154">在浏览器中创建新选项卡，然后转到 [Microsoft 365](https://security.microsoft.com/)安全中心，然后单击"安全 **分数"。**</span><span class="sxs-lookup"><span data-stu-id="b9569-154">Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.</span></span>
2. <span data-ttu-id="b9569-155">在" **概述**  "选项卡上，记下当前的安全分数及其与全局平均值和许可证数量相似的订阅之间的比较方式。</span><span class="sxs-lookup"><span data-stu-id="b9569-155">On the **Overview**  tab, note your current Secure Score and how it compares with the global average and subscriptions with a similar number of licenses.</span></span>
3. <span data-ttu-id="b9569-156">在 **"改进操作** "选项卡上，通读可采取的操作列表以提高分数。</span><span class="sxs-lookup"><span data-stu-id="b9569-156">On the **Improvement actions** tab, read through the list of actions you can take to increase your score.</span></span>

<span data-ttu-id="b9569-157">有关详细信息，请参阅 [Microsoft 安全分数](../security/mtp/microsoft-secure-score.md)。</span><span class="sxs-lookup"><span data-stu-id="b9569-157">For more information, see [Microsoft Secure Score](../security/mtp/microsoft-secure-score.md).</span></span>

## <a name="next-steps"></a><span data-ttu-id="b9569-158">后续步骤</span><span class="sxs-lookup"><span data-stu-id="b9569-158">Next steps</span></span>

<span data-ttu-id="b9569-159">探索 [测试环境中](m365-enterprise-test-lab-guides.md#information-protection) 的其他信息保护特性和功能。</span><span class="sxs-lookup"><span data-stu-id="b9569-159">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="b9569-160">另请参阅</span><span class="sxs-lookup"><span data-stu-id="b9569-160">See also</span></span>

[<span data-ttu-id="b9569-161">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="b9569-161">Microsoft 365 for enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="b9569-162">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="b9569-162">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="b9569-163">适用于企业的 Microsoft 365 文档</span><span class="sxs-lookup"><span data-stu-id="b9569-163">Microsoft 365 for enterprise documentation</span></span>](/microsoft-365-enterprise/)