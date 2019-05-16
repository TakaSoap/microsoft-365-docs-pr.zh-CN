---
title: 为 Microsoft 365 企业版测试环境增加了 Microsoft 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 04/10/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: M365-security-compliance
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南可启用 Microsoft 365 企业版测试环境中的其他 Microsoft 365 安全设置。
ms.openlocfilehash: d51f9ada68969823eadbb4fad55392358a6ddee8
ms.sourcegitcommit: 66bb5af851947078872a4d31d3246e69f7dd42bb
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/15/2019
ms.locfileid: "34072132"
---
# <a name="increased-microsoft-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c70b9-103">为 Microsoft 365 企业版测试环境增加了 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="c70b9-103">Increased Microsoft 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c70b9-104">使用本文中的说明, 您可以配置其他 Microsoft 365 设置以提高 Microsoft 365 企业版测试环境的安全性。</span><span class="sxs-lookup"><span data-stu-id="c70b9-104">With the instructions in this article, you configure additional Microsoft 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c70b9-106">单击[此处](https://aka.ms/m365etlgstack)，即可获得 Microsoft 365 企业版测试实验室指南堆栈中所有文章的直观目录图。</span><span class="sxs-lookup"><span data-stu-id="c70b9-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c70b9-107">第1阶段: 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="c70b9-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c70b9-108">如果只想使用最低要求以轻型方式配置增加的 Microsoft 365 安全, 请按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="c70b9-108">If you just want to configure increased Microsoft 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c70b9-109">如果要在模拟的企业中配置增加的 Microsoft 365 安全, 请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明进行操作。</span><span class="sxs-lookup"><span data-stu-id="c70b9-109">If you want to configure increased Microsoft 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c70b9-110">测试增强的 Microsoft 365 安全不需要模拟企业测试环境, 其中包括连接到 Internet 的模拟 intranet 和 Active Directory 域服务 (AD DS) 林的目录同步。</span><span class="sxs-lookup"><span data-stu-id="c70b9-110">Testing increased Microsoft 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for an Active Directory Domain Services (AD DS) forest.</span></span> <span data-ttu-id="c70b9-111">此处提供了此选项, 以便您可以测试自动授权和组成员身份, 并在代表典型组织的环境中进行试验。</span><span class="sxs-lookup"><span data-stu-id="c70b9-111">It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-microsoft-365-security"></a><span data-ttu-id="c70b9-112">第2阶段: 配置增强的 Microsoft 365 安全性</span><span class="sxs-lookup"><span data-stu-id="c70b9-112">Phase 2: Configure increased Microsoft 365 security</span></span>

<span data-ttu-id="c70b9-113">在这一阶段, 您为 Microsoft 365 企业版测试环境启用了增强的 Microsoft 365 安全性。</span><span class="sxs-lookup"><span data-stu-id="c70b9-113">In this phase, you enable increased Microsoft 365 security for your Microsoft 365 Enterprise test environment.</span></span> <span data-ttu-id="c70b9-114">有关其他详细信息和设置, 请参阅[Configure a Office 365 租户以提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。</span><span class="sxs-lookup"><span data-stu-id="c70b9-114">For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="c70b9-115">配置 SharePoint Online 以阻止不支持新式身份验证的应用程序</span><span class="sxs-lookup"><span data-stu-id="c70b9-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="c70b9-116">不支持新式身份验证的应用程序不能对其应用[标识和设备访问配置](microsoft-365-policies-configurations.md), 这是保护 Microsoft 365 订阅及其数字资产的重要因素。</span><span class="sxs-lookup"><span data-stu-id="c70b9-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="c70b9-117">转到 Microsoft 365 管理中心 ([https://portal.microsoft.com](https://portal.microsoft.com)), 并使用全局管理员帐户登录到你的 Office 365 测试实验室订阅。</span><span class="sxs-lookup"><span data-stu-id="c70b9-117">Go to the Microsoft 365 admin center ([https://portal.microsoft.com](https://portal.microsoft.com)) and sign in to your Office 365 test lab subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="c70b9-118">如果使用的是轻型 Microsoft 365 测试环境, 请从你的本地计算机登录。</span><span class="sxs-lookup"><span data-stu-id="c70b9-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="c70b9-119">如果使用的是模拟企业 Microsoft 365 测试环境, 请使用[Azure 门户](https://portal.azure.com)连接到 CLIENT1 虚拟机, 然后从 CLIENT1 登录。</span><span class="sxs-lookup"><span data-stu-id="c70b9-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="c70b9-120">在 "新建**Microsoft 365 管理中心**" 选项卡上, 单击 "**管理中心中心 > SharePoint**"。</span><span class="sxs-lookup"><span data-stu-id="c70b9-120">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
3. <span data-ttu-id="c70b9-121">在 "新建**SharePoint 管理中心**" 选项卡上, 单击 "**访问控制**"。</span><span class="sxs-lookup"><span data-stu-id="c70b9-121">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
4. <span data-ttu-id="c70b9-122">在**不支持新式身份验证的应用**下, 单击 "**阻止**", 然后单击 **"确定"**。</span><span class="sxs-lookup"><span data-stu-id="c70b9-122">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="c70b9-123">为 SharePoint、OneDrive for Business 和 Microsoft 团队启用高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="c70b9-123">Enable Advanced Threat Protection for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="c70b9-124">适用于 SharePoint、OneDrive 和 Microsoft 团队的 Office 365 高级威胁防护 (ATP) 可防止您的组织无意中共享恶意文件。</span><span class="sxs-lookup"><span data-stu-id="c70b9-124">Office 365 Advanced Threat Protection (ATP) for SharePoint, OneDrive, and Microsoft Teams protects your organization from inadvertently sharing malicious files.</span></span>

1. <span data-ttu-id="c70b9-125">转到 " [Office 365 安全 _AMP_ 合规中心](https://protection.office.com)", 并使用全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c70b9-125">Go to the [Office 365 Security & Compliance Center](https://protection.office.com) and sign in with your global administrator account.</span></span>

2. <span data-ttu-id="c70b9-126">在左侧导航窗格中的 "**威胁管理**" 下, 选择 "**策略 > 安全附件**"。</span><span class="sxs-lookup"><span data-stu-id="c70b9-126">In the left navigation pane, under **Threat management**, choose **Policy > Safe Attachments**.</span></span> 

3. <span data-ttu-id="c70b9-127">选择 "**为 SharePoint、OneDrive 和 Microsoft 团队启用 ATP**"。</span><span class="sxs-lookup"><span data-stu-id="c70b9-127">Select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**.</span></span>

4. <span data-ttu-id="c70b9-128">单击“保存”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="c70b9-128">Click **Save**.</span></span>


### <a name="enable-anti-malware"></a><span data-ttu-id="c70b9-129">启用反恶意软件</span><span class="sxs-lookup"><span data-stu-id="c70b9-129">Enable anti-malware</span></span>

<span data-ttu-id="c70b9-130">"恶意软件"包括病毒和间谍软件。</span><span class="sxs-lookup"><span data-stu-id="c70b9-130">Malware is comprised of viruses and spyware.</span></span> <span data-ttu-id="c70b9-131">"病毒"会感染其他程序与数据，且会在整个计算机中寻找程序进行感染。</span><span class="sxs-lookup"><span data-stu-id="c70b9-131">Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect.</span></span> <span data-ttu-id="c70b9-132">“间谍软件”指收集您的个人信息（如登录信息和个人数据），并将其发送给恶意软件作者的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="c70b9-132">Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="c70b9-133">Office 365 具有内置的恶意软件和垃圾邮件筛选功能, 可帮助保护入站和出站邮件免受恶意软件的攻击, 并帮助保护您免受垃圾邮件的攻击。</span><span class="sxs-lookup"><span data-stu-id="c70b9-133">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam.</span></span> <span data-ttu-id="c70b9-134">有关详细信息, 请参阅[反垃圾邮件 _AMP_ Office 365 中的反恶意软件保护](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="c70b9-134">For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="c70b9-135">若要确保正在对具有常见附件文件类型的文件执行反恶意软件处理, 请执行以下操作:</span><span class="sxs-lookup"><span data-stu-id="c70b9-135">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="c70b9-136">单击浏览器上的 "后退" 按钮返回到 "**策略**" 页。</span><span class="sxs-lookup"><span data-stu-id="c70b9-136">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="c70b9-137">单击 "**反恶意软件**"。</span><span class="sxs-lookup"><span data-stu-id="c70b9-137">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="c70b9-138">双击名为 "**默认**" 的策略。</span><span class="sxs-lookup"><span data-stu-id="c70b9-138">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="c70b9-139">在 "**反恶意软件策略**" 窗口中, 单击 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="c70b9-139">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="c70b9-140">在 "**常用附件类型筛选器**" 下, 单击 **"> 保存**"。</span><span class="sxs-lookup"><span data-stu-id="c70b9-140">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-the-threat-management-dashboard"></a><span data-ttu-id="c70b9-141">第3阶段: 检查威胁管理仪表板</span><span class="sxs-lookup"><span data-stu-id="c70b9-141">Phase 3: Examine the threat management dashboard</span></span>

<span data-ttu-id="c70b9-142">Office 365 的威胁管理可帮助您控制和管理对组织数据的移动设备访问, 帮助保护组织不会丢失数据, 并帮助保护入站和出站邮件免受恶意软件和垃圾邮件的攻击。</span><span class="sxs-lookup"><span data-stu-id="c70b9-142">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam.</span></span> <span data-ttu-id="c70b9-143">您还可以使用威胁管理来保护您的域的信誉, 并确定发件人是否是您的域中的恶意欺骗帐户。</span><span class="sxs-lookup"><span data-stu-id="c70b9-143">You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain.</span></span> <span data-ttu-id="c70b9-144">有关详细信息, 请参阅[Microsoft 365 安全中心中的威胁管理](https://docs.microsoft.com/office365/securitycompliance/threat-management)。</span><span class="sxs-lookup"><span data-stu-id="c70b9-144">For more information, see [Threat management in the Microsoft 365 security center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<!--
### Office 365 Cloud App Security dashboard

Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).

### Microsoft 365 Secure Score

1. Create a new tab in your browser and go to the [Microsoft 365 security center](https://security.microsoft.com/), and then click **Secure score**.
2. On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.
!-->


## <a name="next-steps"></a><span data-ttu-id="c70b9-145">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c70b9-145">Next steps</span></span>

<span data-ttu-id="c70b9-146">有关信息**保护**阶段中的 "为[Microsoft 365 配置增强的安全性](infoprotect-configure-increased-security-office-365.md)" 步骤, 请参阅在生产中配置这些设置的信息和链接。</span><span class="sxs-lookup"><span data-stu-id="c70b9-146">See the [Configure increased security for Microsoft 365](infoprotect-configure-increased-security-office-365.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

<span data-ttu-id="c70b9-147">在您的测试环境中浏览其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="c70b9-147">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c70b9-148">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c70b9-148">See also</span></span>

[<span data-ttu-id="c70b9-149">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="c70b9-149">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c70b9-150">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="c70b9-150">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c70b9-151">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="c70b9-151">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

