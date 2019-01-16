---
title: 在 Microsoft 365 企业版测试环境中实现更高的 Office 365 安全性
ms.author: josephd
author: JoeDavies-MSFT
manager: laurawi
ms.date: 09/16/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Normal
ms.collection: Ent_O365
ms.custom: Ent_TLGs
ms.assetid: 1aa9639b-2862-49c4-bc33-1586dda636b8
description: 使用此测试实验室指南启用其他 Office 365 安全设置 Microsoft 365 企业版测试环境。
ms.openlocfilehash: 62cf2347d3e003e9368c987912e7748029241501
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865666"
---
# <a name="increased-office-365-security-for-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c8fc3-103">在 Microsoft 365 企业版测试环境中实现更高的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="c8fc3-103">Increased Office 365 security for your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c8fc3-104">使用本文中的说明，您可以配置其他 Office 365 设置，以提高 Microsoft 365 企业版测试环境中的安全性。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-104">With the instructions in this article, you configure additional Office 365 settings to increase security in your Microsoft 365 Enterprise test environment.</span></span>

![Microsoft 云测试实验室指南](media/m365-enterprise-test-lab-guides/cloud-tlg-icon.png)

> [!TIP]
> <span data-ttu-id="c8fc3-106">单击[此处](https://aka.ms/m365etlgstack)可查看 Microsoft 365 企业版测试实验室指南集合中所有文章的直观图。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-106">Click [here](https://aka.ms/m365etlgstack) for a visual map to all the articles in the Microsoft 365 Enterprise Test Lab Guide stack.</span></span>
  
## <a name="phase-1-build-out-your-microsoft-365-enterprise-test-environment"></a><span data-ttu-id="c8fc3-107">第 1 阶段： 构建 Microsoft 365 企业版测试环境</span><span class="sxs-lookup"><span data-stu-id="c8fc3-107">Phase 1: Build out your Microsoft 365 Enterprise test environment</span></span>

<span data-ttu-id="c8fc3-108">如果您只想要配置的最低硬件要求与轻型方式增加的 Office 365 安全，按照[轻型基本配置](lightweight-base-configuration-microsoft-365-enterprise.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-108">If you just want to configure increased Office 365 security in a lightweight way with the minimum requirements, follow the instructions in [Lightweight base configuration](lightweight-base-configuration-microsoft-365-enterprise.md).</span></span>
  
<span data-ttu-id="c8fc3-109">如果您想要在模拟企业中配置增加的 Office 365 安全性，请按照[传递身份验证](pass-through-auth-m365-ent-test-environment.md)中的说明。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-109">If you want to configure increased Office 365 security in a simulated enterprise, follow the instructions in [Pass-through authentication](pass-through-auth-m365-ent-test-environment.md).</span></span>
  
> [!NOTE]
> <span data-ttu-id="c8fc3-p101">测试增加的 Office 365 安全不需要模拟的企业测试环境，其中包括连接到 Internet 模拟的 intranet 和 Windows Server AD 林目录同步。它提供此处作为一个选项，以便可以测试自动许可和组成员身份并与之试验环境值，该值代表典型组织中。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-p101">Testing increased Office 365 security does not require the simulated enterprise test environment, which includes a simulated intranet connected to the Internet and directory synchronization for a Windows Server AD forest. It is provided here as an option so that you can test automated licensing and group membership and experiment with it in an environment that represents a typical organization.</span></span> 


## <a name="phase-2-configure-increased-office-365-security"></a><span data-ttu-id="c8fc3-112">第 2 阶段： 配置增加的 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="c8fc3-112">Phase 2: Configure increased Office 365 security</span></span>

<span data-ttu-id="c8fc3-p102">在此阶段，您为 Microsoft 365 企业版测试环境中启用增加的 Office 365 安全。有关其他详细信息和设置，请参阅[Configure Office 365 租户为了提高安全性](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security)。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-p102">In this phase, you enable increased Office 365 security for your Microsoft 365 Enterprise test environment. For additional details and settings, see [Configure your Office 365 tenant for increased security](https://docs.microsoft.com/office365/securitycompliance/tenant-wide-setup-for-increased-security).</span></span>

### <a name="configure-sharepoint-online-to-block-apps-that-dont-support-modern-authentication"></a><span data-ttu-id="c8fc3-115">配置 SharePoint Online，从而阻止应用程序不支持现代身份验证</span><span class="sxs-lookup"><span data-stu-id="c8fc3-115">Configure SharePoint Online to block apps that don’t support modern authentication</span></span>

<span data-ttu-id="c8fc3-116">不支持现代的身份验证的应用程序不能具有[标识和设备访问配置](microsoft-365-policies-configurations.md)应用于它们，这是保护您的 Microsoft 365 订阅和其数字资产的重要组成部分。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-116">Apps that do not support modern authentication cannot have [identity and device access configurations](microsoft-365-policies-configurations.md) applied to them, which is an important element of securing your Microsoft 365 subscription and its digital assets.</span></span> 

1. <span data-ttu-id="c8fc3-117">转到 Office 门户 ([https://office.com](https://office.com)) 和 Office 365 试用版订阅与全局管理员帐户登录。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-117">Go to the Office portal ([https://office.com](https://office.com)) and sign in to your Office 365 trial subscription with your global administrator account.</span></span>
    
  - <span data-ttu-id="c8fc3-118">如果您使用的轻型 Microsoft 365 测试环境，登录本地计算机中。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-118">If you are using the lightweight Microsoft 365 test environment, sign in from your local computer.</span></span>
    
  - <span data-ttu-id="c8fc3-119">如果您使用模拟的企业 Microsoft 365 测试环境，使用[Azure 门户网站](https://portal.azure.com)连接到 CLIENT1 虚拟机，并然后登录从 CLIENT1。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-119">If you are using the simulated enterprise Microsoft 365 test environment, use the [Azure portal](https://portal.azure.com) to connect to the CLIENT1 virtual machine, and then sign in from CLIENT1.</span></span>
 
2. <span data-ttu-id="c8fc3-120">从**Microsoft 365 管理中心**选项卡，单击**管理**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-120">From the **Microsoft 365 admin center** tab, click **Admin**.</span></span>
3. <span data-ttu-id="c8fc3-121">在新的**Microsoft 365 管理中心**选项卡上，单击**管理中心 > SharePoint**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-121">On the new **Microsoft 365 admin center** tab, click **Admin centers > SharePoint**.</span></span>
4. <span data-ttu-id="c8fc3-122">在新的**SharePoint 管理中心**选项卡上，单击**访问控制**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-122">On the new **SharePoint admin center** tab, click **Access control**.</span></span>
5. <span data-ttu-id="c8fc3-123">下**应用程序不支持现代身份验证**，单击**阻止**，然后单击**确定**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-123">Under **Apps that don’t support modern authentication**, click **Block**, and then click **OK**.</span></span>


### <a name="enable-advanced-threat-protection-for-sharepoint-onedrive-for-business-and-microsoft-teams"></a><span data-ttu-id="c8fc3-124">启用高级威胁保护） SharePoint、 OneDrive for Business 和 Microsoft 团队</span><span class="sxs-lookup"><span data-stu-id="c8fc3-124">Enable Advanced Threat Protection) for SharePoint, OneDrive for Business, and Microsoft Teams</span></span>

<span data-ttu-id="c8fc3-p103">Office 365 高级威胁保护 (ATP) 是一项功能的 Exchange Online Protection (EOP)，可帮助保持利用您的电子邮件的恶意软件。与 ATP，在 Exchange 管理中心 (EAC) 或安全创建策略和合规性中心，帮助确保您的用户访问仅链接或在标识为不恶意的电子邮件中的附件。有关详细信息，请参阅[高级的威胁保护安全的附件和安全的链接](https://docs.microsoft.com/office365/securitycompliance/office-365-atp)。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-p103">Office 365 Advanced Threat Protection (ATP) is a feature of Exchange Online Protection (EOP) that helps keep malware out of your email. With ATP, you create policies in the Exchange Admin center (EAC) or the Security & Compliance center that help ensure your users access only links or attachments in emails that are identified as not malicious. For more information, see [Advanced threat protection for safe attachments and safe links](https://docs.microsoft.com/office365/securitycompliance/office-365-atp).</span></span>

1. <span data-ttu-id="c8fc3-128">在浏览器的**Microsoft 365 管理中心**选项卡上，单击**管理中心 > 安全和合规性**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-128">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="c8fc3-129">在新的**安全和合规性**选项卡，单击**威胁管理 > 策略**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-129">On the new **Security & Compliance** tab, click **Threat management > Policy**.</span></span>
3. <span data-ttu-id="c8fc3-130">单击**ATP 安全附件**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-130">Click **ATP safe attachments**.</span></span>
4. <span data-ttu-id="c8fc3-131">在**安全附件**窗格中，选择**SharePoint、 OneDrive 和 Microsoft 团队 ATP 打开**，，然后单击**保存**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-131">In the **Safe attachments** pane, select **Turn on ATP for SharePoint, OneDrive, and Microsoft Teams**, and then click **Save**.</span></span>

### <a name="enable-anti-malware"></a><span data-ttu-id="c8fc3-132">启用反恶意软件</span><span class="sxs-lookup"><span data-stu-id="c8fc3-132">Enable anti-malware</span></span>

<span data-ttu-id="c8fc3-p104">恶意软件组成病毒和间谍软件。病毒感染其他程序和数据，并在您要查找程序感染的计算机整个传播。间谍软件是指收集您的个人信息，例如登录信息和个人数据，并将其发送回恶意软件作者的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-p104">Malware is comprised of viruses and spyware. Viruses infect other programs and data, and they spread throughout your computer looking for programs to infect. Spyware refers to malware that gathers your personal information, such as sign-in information and personal data, and sends it back to the malware author.</span></span> 

<span data-ttu-id="c8fc3-p105">Office 365 具有内置的恶意软件和垃圾邮件筛选功能，帮助防止恶意软件的入站和出站邮件，并帮助您免受垃圾邮件。有关详细信息，请参阅[Office 365 中的反垃圾邮件和反恶意软件保护](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span><span class="sxs-lookup"><span data-stu-id="c8fc3-p105">Office 365 has built-in malware and spam filtering capabilities that help protect inbound and outbound messages from malicious software and help protect you from spam. For more information, see [Anti-spam & anti-malware protection in Office 365](https://docs.microsoft.com/office365/securitycompliance/anti-spam-and-anti-malware-protection)</span></span>

<span data-ttu-id="c8fc3-138">若要确保正在执行的反恶意软件处理对与常见的附件文件类型的文件：</span><span class="sxs-lookup"><span data-stu-id="c8fc3-138">To ensure that anti-malware processing is being performed on files with common attachment file types:</span></span>

1. <span data-ttu-id="c8fc3-139">单击浏览器以返回到**策略**页上的后退按钮。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-139">Click the back button on your browser to get back to the **Policy** page.</span></span>
2. <span data-ttu-id="c8fc3-140">单击**反恶意软件**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-140">Click **Anti-malware**.</span></span>
3. <span data-ttu-id="c8fc3-141">双击名为**Default**的策略。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-141">Double-click the policy named **Default**.</span></span>
4. <span data-ttu-id="c8fc3-142">在**反恶意软件策略**窗口中，单击**设置**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-142">In the **Anti-malware policy** window, click **Settings**.</span></span>
4. <span data-ttu-id="c8fc3-143">下**常见附件类型筛选器**中，单击**上 > 保存**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-143">Under **Common Attachment Types filter**, click **On > Save**.</span></span>


## <a name="phase-3-examine-office-365-security-tools-and-logs"></a><span data-ttu-id="c8fc3-144">第 3 阶段： 检查 Office 365 安全工具和日志</span><span class="sxs-lookup"><span data-stu-id="c8fc3-144">Phase 3: Examine Office 365 security tools and logs</span></span>

<span data-ttu-id="c8fc3-145">在此阶段中，您查看内置服务，通知您关于安全事件和测量总体安全状况。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-145">In this phase, you look at built-in services that inform you about security events and measure your overall security posture.</span></span>

### <a name="threat-management-dashboard"></a><span data-ttu-id="c8fc3-146">威胁管理仪表板</span><span class="sxs-lookup"><span data-stu-id="c8fc3-146">Threat management dashboard</span></span>

<span data-ttu-id="c8fc3-p106">Office 365 威胁管理可以帮助您控制和管理移动设备访问您组织的数据，帮助保护您的组织免受数据丢失，帮助防止恶意软件和垃圾邮件的入站和出站邮件。您还使用从您的域帐户管理以保护您的域的声誉并确定恶意欺骗发件人的威胁。有关详细信息，请参阅[Office 365 安全性和合规性中心中的威胁 management](https://docs.microsoft.com/office365/securitycompliance/threat-management)。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-p106">Office 365 Threat management can help you control and manage mobile device access to your organization's data, help protect your organization from data loss, and help protect inbound and outbound messages from malicious software and spam. You also use threat management to protect your domain's reputation and to determine whether or not senders are maliciously spoofing accounts from your domain. For more information, see [Threat management in the Office 365 Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/threat-management).</span></span>

<span data-ttu-id="c8fc3-150">使用以下步骤查看 Office 365 威胁管理仪表板：</span><span class="sxs-lookup"><span data-stu-id="c8fc3-150">Use these steps to view the Office 365 Threat management dashboard:</span></span>

1. <span data-ttu-id="c8fc3-151">在浏览器的**Microsoft 365 管理中心**选项卡上，单击**管理中心 > 安全和合规性**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-151">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="c8fc3-152">在新的**安全和合规性**选项卡，单击**威胁管理 > 仪表板**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-152">On the new **Security & Compliance** tab, click **Threat management > Dashboard**.</span></span>
3. <span data-ttu-id="c8fc3-153">在新**仪表板**选项卡在浏览器中，记下的恶意软件趋势、 见解和其他部分的仪表板。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-153">On the new **Dashboard** tab in your browser, note the malware trends, insights, and other sections of the dashboard.</span></span>

### <a name="office-365-cloud-app-security-dashboard"></a><span data-ttu-id="c8fc3-154">Office 365 云应用程序安全性仪表板</span><span class="sxs-lookup"><span data-stu-id="c8fc3-154">Office 365 Cloud App Security dashboard</span></span>

<span data-ttu-id="c8fc3-p107">Office 365 云应用程序安全性，以前称为 Office 365 高级安全管理，允许您创建的监视和通知您在 Office 365 订阅中，可疑活动，以便可以调查，并采取可能的策略修复操作。有关详细信息，请参阅[概述的 Office 365 云应用程序安全性](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview)。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-p107">Office 365 Cloud App Security, previously known as Office 365 Advanced Security Management, allows you to create policies that monitor for and inform you of suspicious activities in your Office 365 subscription, so that you can investigate and take possible remediation action. For more information, see [Overview of Office 365 Cloud App Security](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview).</span></span>

1. <span data-ttu-id="c8fc3-157">在浏览器的**Microsoft 365 管理中心**选项卡上，单击**管理中心 > 安全和合规性**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-157">On the **Microsoft 365 admin center** tab of your browser, click **Admin centers > Security & Compliance**.</span></span>
2. <span data-ttu-id="c8fc3-158">在新的**安全和合规性**选项卡，单击**通知 > 管理高级通知 > 转到 Office 365 云应用程序安全性**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-158">On the new **Security & Compliance** tab, click **Alerts > Manage advanced alerts > Go to Office 365 Cloud App Security**.</span></span>
3. <span data-ttu-id="c8fc3-159">在新的**云应用程序安全性**选项卡上，记下仪表板视图和列表的监视的 Office 365 订阅中的各种活动的默认策略。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-159">On the new **Cloud App Security** tab, note the dashboard view and the list of default policies that that monitor for various activities in your Office 365 subscription.</span></span>
4. <span data-ttu-id="c8fc3-160">单击仪表板图标可查看正在跟踪的云应用程序安全性活动摘要。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-160">Click the dashboard icon to see a summary of Cloud App Security activities that are being tracked.</span></span>
5. <span data-ttu-id="c8fc3-161">单击**调查**（眼镜图标），然后选择**活动日志**以查看最新登录的列表和其他活动。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-161">Click **Investigate** (the eyeglasses icon) and then **Activity log** to see the list of recent sign-ins and other activities.</span></span>

### <a name="secure-score"></a><span data-ttu-id="c8fc3-162">安全分数</span><span class="sxs-lookup"><span data-stu-id="c8fc3-162">Secure Score</span></span>

1. <span data-ttu-id="c8fc3-163">在浏览器中创建新选项卡，并转到**securescore.office.com**。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-163">Create a new tab in your browser and go to **securescore.office.com**.</span></span>
2. <span data-ttu-id="c8fc3-164">在**仪表板选项卡**上，记下您当前的安全排名和队列中的操作列表来提高您的分数。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-164">On the **Dashboard tab**, note your current Secure Score and the list of actions in the queue to increase your score.</span></span>

<span data-ttu-id="c8fc3-165">有关信息和链接在生产中配置这些设置的**信息保护**阶段，请参阅[Configure 增加的 Office 365 安全性](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md)步骤。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-165">See the [Configure increased security for Office 365](increased-o365-security-microsoft-365-enterprise-dev-test-environment.md) step in the **Information protection** phase for information and links to configure these settings in production.</span></span>

## <a name="next-step"></a><span data-ttu-id="c8fc3-166">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c8fc3-166">Next step</span></span>

<span data-ttu-id="c8fc3-167">浏览您的测试环境中其他[信息保护](m365-enterprise-test-lab-guides.md#information-protection)特性和功能。</span><span class="sxs-lookup"><span data-stu-id="c8fc3-167">Explore additional [information protection](m365-enterprise-test-lab-guides.md#information-protection) features and capabilities in your test environment.</span></span>

## <a name="see-also"></a><span data-ttu-id="c8fc3-168">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c8fc3-168">See also</span></span>

[<span data-ttu-id="c8fc3-169">Microsoft 365 企业版测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="c8fc3-169">Microsoft 365 Enterprise Test Lab Guides</span></span>](m365-enterprise-test-lab-guides.md)

[<span data-ttu-id="c8fc3-170">部署 Microsoft 365 企业版</span><span class="sxs-lookup"><span data-stu-id="c8fc3-170">Deploy Microsoft 365 Enterprise</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c8fc3-171">Microsoft 365 企业版文档</span><span class="sxs-lookup"><span data-stu-id="c8fc3-171">Microsoft 365 Enterprise documentation</span></span>](https://docs.microsoft.com/microsoft-365-enterprise/)

