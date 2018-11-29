---
title: Contoso Corporation 的 Microsoft 365 企业版安全性摘要
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/13/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: Contoso 如何使用 Microsoft 365 企业版的安全功能。
ms.openlocfilehash: 2cbabb04c79816684f4c566b92003bb64471d22b
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865791"
---
# <a name="summary-of-microsoft-365-enterprise-security-for-the-contoso-corporation"></a><span data-ttu-id="59a30-103">Contoso Corporation 的 Microsoft 365 企业版安全性摘要</span><span class="sxs-lookup"><span data-stu-id="59a30-103">Summary of Microsoft 365 Enterprise security for the Contoso Corporation</span></span>

<span data-ttu-id="59a30-104">**摘要：** Contoso 如何使用 Microsoft 365 企业版的安全功能。</span><span class="sxs-lookup"><span data-stu-id="59a30-104">**Summary:** How Contoso is using the security features across Microsoft 365 Enterprise.</span></span>

<span data-ttu-id="59a30-p101">若要获取 IT 安全部门签核的 Microsoft 365 企业版部署，需要执行彻底的安全审阅。以下是 Contoso 针对云的安全要求：</span><span class="sxs-lookup"><span data-stu-id="59a30-p101">To obtain the sign-off of the deployment of Microsoft 365 Enterprise by the IT security department, a thorough security review was conducted. Here are Contoso's security requirements for the cloud:</span></span>

- <span data-ttu-id="59a30-107">对访问云资源的员工使用最强身份验证方法</span><span class="sxs-lookup"><span data-stu-id="59a30-107">Use the strongest methods of authentication for employee access to cloud resources</span></span>
- <span data-ttu-id="59a30-108">确保电脑和移动设备以安全的方式连接和访问应用程序</span><span class="sxs-lookup"><span data-stu-id="59a30-108">Ensure that PCs and mobile devices connect and access applications in secure ways</span></span>
- <span data-ttu-id="59a30-109">保护电脑和电子邮件免受恶意软件的攻击</span><span class="sxs-lookup"><span data-stu-id="59a30-109">PCs and email are protected from malware</span></span>
- <span data-ttu-id="59a30-110">对基于云的数字资产的权限定义哪些用户可访问哪些内容及他们可执行哪些操作，并被设计为最小特权访问权限</span><span class="sxs-lookup"><span data-stu-id="59a30-110">Permissions on cloud-based digital assets define who can access what and what they can do and are designed for least privilege access</span></span>
- <span data-ttu-id="59a30-111">对敏感和高度管控的数字资产进行标记和加密，并将其存储在安全位置</span><span class="sxs-lookup"><span data-stu-id="59a30-111">Sensitive and highly regulated digital assets are labeled, encrypted, and stored in secure locations</span></span>
- <span data-ttu-id="59a30-112">通过权限对高度管控的数字资产进行保护</span><span class="sxs-lookup"><span data-stu-id="59a30-112">Highly regulated digital assets are protected with permissions</span></span>
- <span data-ttu-id="59a30-113">IT 安全可从中央仪表板监控安全状态，并收到有关安全事件的通知，以做出快速响应和采取缓解措施。</span><span class="sxs-lookup"><span data-stu-id="59a30-113">IT security can monitor security posture from central dashboards and get notified of security events for quick response and mitigation</span></span>

## <a name="contosos-path-to-microsoft-365-security-readiness"></a><span data-ttu-id="59a30-114">Contoso 实现 Microsoft 365 安全就绪情况的方式</span><span class="sxs-lookup"><span data-stu-id="59a30-114">Contoso's path to Microsoft 365 security readiness</span></span>

<span data-ttu-id="59a30-115">Contoso 使用以下步骤为其 Microsoft 365 企业版部署的安全性做准备：</span><span class="sxs-lookup"><span data-stu-id="59a30-115">Contoso used the following steps to ready their security for their deployment of Microsoft 365 Enterprise:</span></span>

1. <span data-ttu-id="59a30-116">限制云的管理员帐户</span><span class="sxs-lookup"><span data-stu-id="59a30-116">Limited administrator accounts for the cloud</span></span>

   <span data-ttu-id="59a30-117"> Contoso 对现有的 Windows Sever AD 管理员帐户进行了广泛审阅，并设置了一系列的云管理员帐户和组。</span><span class="sxs-lookup"><span data-stu-id="59a30-117">Contoso did an extensive review of the existing Windows Server AD administrator accounts and set up a series of cloud administrator accounts and groups.</span></span>

2. <span data-ttu-id="59a30-118">按三个级别执行数据分类分析</span><span class="sxs-lookup"><span data-stu-id="59a30-118">Performed data classification analysis into three levels</span></span>

   <span data-ttu-id="59a30-119">Contoso 进行了仔细的审阅并确定了三个用来确定 Microsoft 365 企业版功能的级别，以保护 Contoso 最有价值的数据。</span><span class="sxs-lookup"><span data-stu-id="59a30-119">Contoso performed a careful review and determined the three levels, which was used to determine the Microsoft 365 Enterprise features to protect Contoso's most valuable data.</span></span>

3. <span data-ttu-id="59a30-120">确定数据级别的访问策略、保留策略和信息保护策略</span><span class="sxs-lookup"><span data-stu-id="59a30-120">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="59a30-121">基于数据级别，Contoso 已确定将用于限定转移到云的未来 IT 工作负载的详细要求。</span><span class="sxs-lookup"><span data-stu-id="59a30-121">Based on the data levels, Contoso determined detailed requirements, which will be used to qualify future IT workloads being moved to the cloud.</span></span>

<span data-ttu-id="59a30-122">根据安全最佳做法和 Microsoft 365 企业版部署要求，Contoso 的安全管理员和 IT 部门已部署许多安全特性和功能，如以下部分中所述。</span><span class="sxs-lookup"><span data-stu-id="59a30-122">In accordance with security best practices and Microsoft 365 Enterprise deployment requirements, Contoso's security administrators and IT department have deployed many security features and capabilities, as described in the following sections.</span></span>

## <a name="identity--access-management"></a><span data-ttu-id="59a30-123">标识和访问管理</span><span class="sxs-lookup"><span data-stu-id="59a30-123">Identity & access management</span></span> 

- <span data-ttu-id="59a30-124">使用 MFA 和 PIM 的专用全局管理员帐户</span><span class="sxs-lookup"><span data-stu-id="59a30-124">Dedicated global administrator accounts with MFA and PIM</span></span>

  <span data-ttu-id="59a30-125">Contoso 创建三种专用全局管理员帐户，它们使用极强密码，并使用多重身份验证 (MFA) 和 Azure AD Privileged Identity Management (PIM) 对其进行保护，而非向日常用户帐户分配全局管理员角色。</span><span class="sxs-lookup"><span data-stu-id="59a30-125">Rather than assign the global admin role to everyday user accounts, Contoso created three, dedicated global administrator accounts with very strong passwords and protected them with multi-factor authentication (MFA) and Azure AD Privileged Identity Management (PIM).</span></span> 

  <span data-ttu-id="59a30-126">仅针对特定管理任务执行使用全局管理员帐户登录，只有指定人员才知道密码，且只能在使用 Azure AD PIM 配置的时间范围内使用。</span><span class="sxs-lookup"><span data-stu-id="59a30-126">Signing in with a global administrator account is only done for specific administrative tasks, the passwords are only known to designated staff, and can only be used within the time configured with Azure AD PIM.</span></span> 

  <span data-ttu-id="59a30-127">对于适合该 IT 人员的作业功能和职责的帐户，Contoso 的安全管理员向其分配了更低的管理员角色。</span><span class="sxs-lookup"><span data-stu-id="59a30-127">Contoso's security administrators have assigned lesser admin roles to accounts that are appropriate to that IT person's job function and responsibility.</span></span>

  <span data-ttu-id="59a30-128">有关详细信息，请参阅[关于 Office 365 管理员角色](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d)。</span><span class="sxs-lookup"><span data-stu-id="59a30-128">For more information, see [About Office 365 admin roles](https://support.office.com/article/about-office-365-admin-roles-da585eea-f576-4f55-a1e0-87090b6aaa9d).</span></span>

- <span data-ttu-id="59a30-129">用于所有用户帐户的 MFA</span><span class="sxs-lookup"><span data-stu-id="59a30-129">MFA for all user accounts</span></span>

  <span data-ttu-id="59a30-p102">MFA 通过要求用户在正确输入密码后在其智能手机上确认电话呼叫、短信或应用通知为登录过程添加了额外的保护。使用 MFA，即使帐户密码被泄露，也可针对未授权登录保护 Azure AD 用户帐户。</span><span class="sxs-lookup"><span data-stu-id="59a30-p102">MFA adds an additional layer of protection to the sign-in process by requiring users to acknowledge a phone call, text message, or an app notification on their smart phone after correctly entering their password. With MFA, Azure AD user accounts are protected against unauthorized sign-in even if an account password is compromised.</span></span>

   - <span data-ttu-id="59a30-132">若要防止 Microsoft 365 订阅泄漏，Contoso 要求对所有全局管理员帐户使用 MFA。</span><span class="sxs-lookup"><span data-stu-id="59a30-132">To protect against a compromise of the Microsoft 365 subscription, Contoso requires MFA on all global administrator accounts.</span></span>
   - <span data-ttu-id="59a30-133">为防止钓鱼攻击（攻击者会泄露组织中受信任的个人的凭据并发送恶意电子邮件），Contoso 对所有用户帐户（包括经理和行政人员）都启用了 MFA。</span><span class="sxs-lookup"><span data-stu-id="59a30-133">To protect against phishing attacks, in which an attacker compromises the credentials of a trusted person in the organization and sends malicious emails, Contoso enabled MFA on all user accounts, including manager and executive staff.</span></span> 

- <span data-ttu-id="59a30-134">使用条件访问策略更安全地访问设备和应用程序</span><span class="sxs-lookup"><span data-stu-id="59a30-134">Safer device and application access with conditional access policies</span></span>

  <span data-ttu-id="59a30-p103">Contoso 将[条件访问策略](microsoft-365-policies-configurations.md)用于标识、设备、Exchange Online 和 SharePoint Online。标识条件访问策略包括对高风险用户要求进行密码更改以及阻止客户端使用不支持新式身份验证的应用。设备条件策略包括定义批准的应用和要求使用合规的电脑和移动设备。Exchange Online 条件访问策略包括阻止 ActiveSync 客户端和设置 Office 365 邮件加密。SharePoint Online 条件访问策略包括对敏感和高度管控的网站提供额外的保护。</span><span class="sxs-lookup"><span data-stu-id="59a30-p103">Contoso is using [conditional access policies](microsoft-365-policies-configurations.md) for identity, devices, Exchange Online, and SharePoint Online. Identity conditional access policies include requiring password changes for high-risk users and blocking clients from using apps that don’t support modern authentication. Device conditional policies include the definition of approved apps and requiring compliant PCs and mobile devices. Exchange Online conditional access policies include blocking ActiveSync clients and setting up Office 365 message encryption. SharePoint Online conditional access policies include additional protection for sensitive and highly regulated sites.</span></span>

- <span data-ttu-id="59a30-140">Windows Hello 企业版</span><span class="sxs-lookup"><span data-stu-id="59a30-140">Windows Hello for Business</span></span>

  <span data-ttu-id="59a30-141">Contoso 已部署并要求 [Windows Hello 企业版](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification)通过对在运行 Windows 10 企业版的电脑和移动设备使用强双因素身份验证来消除输入密码的需要。</span><span class="sxs-lookup"><span data-stu-id="59a30-141">Contoso has deployed and requires [Windows Hello for Business](https://docs.microsoft.com/windows/security/identity-protection/hello-for-business/hello-identity-verification) to eventually eliminate the need for passwords with strong two-factor authentication on PCs and mobile devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="59a30-142">Windows Defender Credential Guard</span><span class="sxs-lookup"><span data-stu-id="59a30-142">Windows Defender Credential Guard</span></span>

  <span data-ttu-id="59a30-143">为了使用管理权限阻止在操作系统中运行的目标攻击和恶意软件，Contoso 通过 Windows Server AD 组策略启用了 [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard)。</span><span class="sxs-lookup"><span data-stu-id="59a30-143">To block targeted attacks and malware running in the operating system with administrative privileges, Contoso has enabled [Windows Defender Credential Guard](https://docs.microsoft.com/windows/security/identity-protection/credential-guard/credential-guard) through Windows Server AD group policy.</span></span>

## <a name="threat-protection"></a><span data-ttu-id="59a30-144">威胁防护</span><span class="sxs-lookup"><span data-stu-id="59a30-144">Threat protection</span></span>

- <span data-ttu-id="59a30-145">使用 Windows Defender 防病毒防止恶意软件的攻击</span><span class="sxs-lookup"><span data-stu-id="59a30-145">Protection from malware with Windows Defender Antivirus</span></span>

  <span data-ttu-id="59a30-146">Contoso 使用 [Windows Defender 防病毒](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10)对运行 Windows 10 企业版的电脑和设备进行恶意软件保护和反恶意软件管理。</span><span class="sxs-lookup"><span data-stu-id="59a30-146">Contoso is using [Windows Defender Antivirus](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-antivirus/windows-defender-antivirus-in-windows-10) for malware protection and anti-malware management for PCs and devices running Windows 10 Enterprise.</span></span>

- <span data-ttu-id="59a30-147">使用 Office 365 高级威胁防护保护电子邮件流和邮箱审核日志记录</span><span class="sxs-lookup"><span data-stu-id="59a30-147">Secure email flow and mailbox audit logging with Office 365 Advanced Threat Protection</span></span> 

  <span data-ttu-id="59a30-148">Contoso 使用 Exchange Online Protection 和 [Office 365 高级威胁防护 (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) 来抵御通过电子邮件传输的未知恶意软件、病毒和恶意 URL。</span><span class="sxs-lookup"><span data-stu-id="59a30-148">Contoso is using Exchange Online Protection and [Office 365 Advanced Threat Protection (ATP)](https://docs.microsoft.com/office365/securitycompliance/office-365-atp) to protect against unknown malware, viruses, and malicious URLs transmitted through emails.</span></span> 

  <span data-ttu-id="59a30-149">Contoso 还启用了邮箱审核日志记录，以确定登录用户邮箱、发送邮件的用户，以及由邮箱所有者、受委派用户或管理员执行的其他活动。</span><span class="sxs-lookup"><span data-stu-id="59a30-149">Contoso has also enabled mailbox audit logging to determine who has logged into user mailboxes, sent messages, and other activities performed by the mailbox owner, a delegated user, or an administrator.</span></span>

- <span data-ttu-id="59a30-150">使用 Office 365 威胁智能进行威胁监控和防护</span><span class="sxs-lookup"><span data-stu-id="59a30-150">Attack monitoring and prevention with Office 365 Threat Intelligence</span></span>

  <span data-ttu-id="59a30-151">Contoso 使用 [Office 365 威胁智能](https://docs.microsoft.com/office365/securitycompliance/office-365-ti)保护其 Office 365 用户，使其能够轻松地标识和解决攻击，并防止进一步攻击。</span><span class="sxs-lookup"><span data-stu-id="59a30-151">Contoso uses [Office 365 Threat Intelligence](https://docs.microsoft.com/office365/securitycompliance/office-365-ti) to protect their Office 365 users by making it easy to identify and address attacks, and to prevent future attacks.</span></span>

- <span data-ttu-id="59a30-152">使用 Advanced Threat Analytics 防止复杂攻击</span><span class="sxs-lookup"><span data-stu-id="59a30-152">Protection from sophisticated attacks with Advanced Threat Analytics</span></span>

  <span data-ttu-id="59a30-p104">Contoso 使用 [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) 保护自己免受高级目标攻击。ATA 自动分析、学习和标识正常和异常实体（用户、设备和资源）行为。</span><span class="sxs-lookup"><span data-stu-id="59a30-p104">Contoso is using [Advanced Threat Analytics (ATA)](https://docs.microsoft.com/advanced-threat-analytics/what-is-ata) to protect itself from advanced targeted attacks.  ATA automatically analyzes, learns, and identifies normal and abnormal entity (user, devices, and resources) behavior.</span></span> 

## <a name="information-protection"></a><span data-ttu-id="59a30-155">信息保护</span><span class="sxs-lookup"><span data-stu-id="59a30-155">Information protection</span></span>

- <span data-ttu-id="59a30-156">使用 Azure 信息保护来保护敏感和高度管控的数字资产</span><span class="sxs-lookup"><span data-stu-id="59a30-156">Protect sensitive and highly regulated digital assets with Azure Information Protection</span></span>

  <span data-ttu-id="59a30-p105">Contoso 确定数据保护的三个级别并部署用户应用于数字资产的 [Azure 信息保护](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)标签。对于其商业秘密和其他知识产权，Contoso 在作用域内策略中对加密内容的高度管控数据使用 Azure 信息保护子标签，并限制对特定安全组的访问。</span><span class="sxs-lookup"><span data-stu-id="59a30-p105">Contoso determined three levels of data protection and deployed [Azure Information Protection](https://docs.microsoft.com/azure/information-protection/what-is-information-protection) labels that users apply to digital assets. For its trade secrets and other intellectual property, Contoso uses Azure Information Protection sub-labels in a scoped policy for highly regulated data that encrypts content and restricts access to specific security groups.</span></span>

- <span data-ttu-id="59a30-159">使用 Office 365 数据丢失防护阻止 intranet 数据泄露</span><span class="sxs-lookup"><span data-stu-id="59a30-159">Prevent intranet data leaks with Office 365 Data Loss Prevention</span></span>

  <span data-ttu-id="59a30-160">Contoso 为 Exchange Online、SharePoint Online 和 OneDrive for Business 配置了[数据丢失防护](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)，以阻止用户无意或有意共享敏感数据。</span><span class="sxs-lookup"><span data-stu-id="59a30-160">Contoso has configured [Data Loss Prevention](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies) policies for Exchange Online, SharePoint Online, and OneDrive for Business to prevent users from accidentally or intentionally sharing sensitive data.</span></span>

- <span data-ttu-id="59a30-161">使用 Windows 信息保护防止设备数据泄露</span><span class="sxs-lookup"><span data-stu-id="59a30-161">Prevent device data leaks Windows Information Protection</span></span>

  <span data-ttu-id="59a30-162">Contoso 使用 [Windows 信息保护 (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) 防止数据通过基于 Internet 的应用和服务、企业所有的设备上的企业应用和数据、以及员工工作时所使用的个人设备泄露。</span><span class="sxs-lookup"><span data-stu-id="59a30-162">Contoso is using [Windows Information Protection (WIP)](https://docs.microsoft.com/windows/security/information-protection/windows-information-protection/protect-enterprise-data-using-wip) to protect against data leakage through Internet-based apps and services and enterprise apps and data on enterprise-owned devices and personal devices that employees bring to work.</span></span>

- <span data-ttu-id="59a30-163">使用 Microsoft Cloud App Security 进行云监视</span><span class="sxs-lookup"><span data-stu-id="59a30-163">Cloud monitoring with Microsoft Cloud App Security</span></span>

  <span data-ttu-id="59a30-164">Contoso 使用 [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) 来映射其云环境、监视其使用情况，并检测安全事件和事件。</span><span class="sxs-lookup"><span data-stu-id="59a30-164">Contoso is using [Microsoft Cloud App Security](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) to map their cloud environment, monitor its usage, and detect security events and incidents.</span></span> 

- <span data-ttu-id="59a30-165">使用 Office 365 云应用安全监控 Office 365 安全性</span><span class="sxs-lookup"><span data-stu-id="59a30-165">Office 365 security monitoring with Office 365 Cloud App Security</span></span>

  <span data-ttu-id="59a30-166">Contoso 安全管理员使用 [Office 365 云应用安全 (CAS)](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview) 来设置警报，以收到异常或存在风险的用户活动的通知，例如，从 SharePoint Online 或 OneDrive for Business 下载大量数据、多次失败的登录尝试，或从未知或危险的 IP 地址登录。</span><span class="sxs-lookup"><span data-stu-id="59a30-166">Contoso security administrators set up alerts with [Office 365 Cloud App Security (CAS)](https://docs.microsoft.com/office365/securitycompliance/office-365-cas-overview) to be notified of unusual or risky user activity, such as downloading large amounts of data from SharePoint Online or OneDrive for Business, multiple failed sign-in attempts, or sign-ins from unknown or dangerous IP addresses.</span></span>

- <span data-ttu-id="59a30-167">使用 Microsoft Intune 的设备管理</span><span class="sxs-lookup"><span data-stu-id="59a30-167">Device management with Microsoft Intune</span></span>

  <span data-ttu-id="59a30-p106">作为企业管理 + 安全性 (EMS) 套件的一部分，Contoso 使用 [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) 来注册、管理和配置对移动设备的以及在这些设备上运行的应用的访问权限。基于设备的条件访问策略还要求使用获得批准的应用和合规的电脑和移动设备。</span><span class="sxs-lookup"><span data-stu-id="59a30-p106">As part of the Enterprise Management + Security (EMS) suite, Contoso uses [Microsoft Intune](https://docs.microsoft.com/intune/introduction-intune) to enroll, manage, and configure access to mobile devices and the apps that run on them. Device-based conditional access policies also require approved apps and compliant PCs and mobile devices.</span></span>

## <a name="security-management"></a><span data-ttu-id="59a30-170">安全管理</span><span class="sxs-lookup"><span data-stu-id="59a30-170">Security management</span></span>

- <span data-ttu-id="59a30-171">Azure 安全中心适用于 IT 人员的安全中心仪表板</span><span class="sxs-lookup"><span data-stu-id="59a30-171">Central security dashboard for IT with Azure Security Center</span></span>

  <span data-ttu-id="59a30-172">Contoso 使用 [Azure 安全中心](https://docs.microsoft.com/intune/introduction-intune)来获取统一的安全和威胁防护视图，以跨其工作负载管理安全策略，并响应网络攻击。</span><span class="sxs-lookup"><span data-stu-id="59a30-172">Contoso uses the [Azure Security Center](https://docs.microsoft.com/intune/introduction-intune) for a unified view of security and threat protection, to manage security policies across its workloads, and to respond to cyberattacks.</span></span>

- <span data-ttu-id="59a30-173">Windows Defender 安全中心适用于用户的安全中心仪表板</span><span class="sxs-lookup"><span data-stu-id="59a30-173">Central security dashboard for users with Windows Defender Security Center</span></span>

  <span data-ttu-id="59a30-174">Contoso 已将 [Windows Defender 安全中心应用](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center)部署到运行 Windows 10 企业版的电脑和设备，以便用户能够对其安全状态一目了然并采取操作。</span><span class="sxs-lookup"><span data-stu-id="59a30-174">Contoso has deployed the [Windows Defender Security Center app](https://docs.microsoft.com/windows/security/threat-protection/windows-defender-security-center/windows-defender-security-center) to its PCs and devices running Windows 10 Enterprise so that users can see their security posture at a glance and take action.</span></span>


## <a name="next-step"></a><span data-ttu-id="59a30-175">后续步骤</span><span class="sxs-lookup"><span data-stu-id="59a30-175">Next step</span></span>

<span data-ttu-id="59a30-176">[了解](contoso-sharepoint-online-site-for-highly-confidential-assets.md) Contoso 如何对高度受管制数据创建 SharePoint Online 网站，以推动研究团队之间的协作。</span><span class="sxs-lookup"><span data-stu-id="59a30-176">[Learn](contoso-sharepoint-online-site-for-highly-confidential-assets.md) how Contoso created a SharePoint Online site for highly regulated data to enable collaboration among its research teams.</span></span>

