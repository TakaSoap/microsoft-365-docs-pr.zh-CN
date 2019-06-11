---
title: 步骤 5 - 安全性和合规性注意事项
ms.author: jogruszc
author: JGruszczyk
manager: jemed
ms.date: 05/20/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Windows 和 Office 重要的安全性和合规性注意事项。
ms.openlocfilehash: 791006a6a836f28adb8d71b20e0e887b903752ba
ms.sourcegitcommit: 7e806db3d44ec223754efe1e9613b2c7117c4788
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2019
ms.locfileid: "34814583"
---
# <a name="step-5-security-and-compliance-considerations"></a><span data-ttu-id="109fa-103">步骤 5：安全性和合规性注意事项</span><span class="sxs-lookup"><span data-stu-id="109fa-103">Step 5: Security and Compliance Considerations</span></span>

![](media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-1.png)

<table>
<thead>
<td><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-8.png" alt="Step 5" height="135" width="135" /></td>
<td><p><span data-ttu-id="109fa-104"><strong>步骤 5：安全性和合规性注意事项</strong></span><span class="sxs-lookup"><span data-stu-id="109fa-104"><strong>Step 5: Security and Compliance Considerations</strong></span></span></p>
<p><span data-ttu-id="109fa-p101">使用 Windows 10 和 Office 365 专业增强版，可通过新方法来保护数据、设备和用户，并快速检测和响应威胁。此外，还请了解在迁移到 Windows 10 时，如何处理与磁盘加密、防恶意软件应用和策略相关的常见问题。</span><span class="sxs-lookup"><span data-stu-id="109fa-p101">Windows 10 and Office 365 ProPlus provide new ways to protect your data, devices and users and quickly detect and respond to threats. Also, learn how to deal with common problems associated with disk encryption, anti-malware apps and policies when moving to Windows 10.</span></span></p></td>
<td><a href="https://aka.ms/ddev5" target="_blank"><img src="media/desktop-deployment-center-home-media/desktop-deployment-center-home-media-18.png" alt="Step 5" height="130" width="231" /></a></td>
</thead>
</table>

>[!NOTE]
><span data-ttu-id="109fa-107">安全性和合规性是我们涉及 Windows 10 和 Office 365 专业增强版安全性和合规性注意事项的建议部署过程的第五个步骤。</span><span class="sxs-lookup"><span data-stu-id="109fa-107">Security and Compliance is the fifth step in our recommended deployment process wheel covering Windows 10 and Office 365 ProPlus security and compliance considerations.</span></span> <span data-ttu-id="109fa-108">若要查看的完整桌面部署过程，请访问[桌面部署中心](https://aka.ms/HowToShift)。</span><span class="sxs-lookup"><span data-stu-id="109fa-108">To see the full desktop deployment process, visit the [Desktop Deployment Center](https://aka.ms/HowToShift).</span></span>
>

<span data-ttu-id="109fa-109">在从以前版本的 Windows 和 Office 迁移时，是时候查看作为 Windows 10 和 Office 365 专业增强版部署的一部分的面向新的安全性和合规性功能的选项，并查看注意事项和常见障碍。</span><span class="sxs-lookup"><span data-stu-id="109fa-109">Now it's time to review options for targeting new security and compliance capabilities as part of your Windows 10 and Office 365 ProPlus deployment, along with the considerations and common blockers when moving from previous versions of Windows and Office.</span></span> <span data-ttu-id="109fa-110">仅 Windows 10 中的许多安全相关功能就在推动向更新平台迁移。</span><span class="sxs-lookup"><span data-stu-id="109fa-110">Many of the security-related capabilities in Windows 10 alone are driving the shift to the newer platform.</span></span> <span data-ttu-id="109fa-111">另外，与 Office 365 云服务和 Azure Active Directory 标识选项集成，可以为数据、设备和用户提供持续更新的新保护。</span><span class="sxs-lookup"><span data-stu-id="109fa-111">Also, integration with cloud services in Office 365 and identity options using Azure Active Directory brings access to new and continually updated protections for your data, devices and users.</span></span>

## <a name="overcoming-potential-security-related-deployment-blockers"></a><span data-ttu-id="109fa-112">克服潜在的安全性相关的部署障碍</span><span class="sxs-lookup"><span data-stu-id="109fa-112">Overcoming Potential Security-Related Deployment Blockers</span></span>

<span data-ttu-id="109fa-113">在介绍迁移到 Windows 10 和 Office 365 专业增强版并将这些体验连接到云时可以添加的新功能之前，先来看看可能会经常中断部署过程的一些趋势。</span><span class="sxs-lookup"><span data-stu-id="109fa-113">Before explaining new capabilities that you can add as you move to Windows 10 and Office 365 ProPlus and connect those experiences to the cloud, let’s start with a few trends we’re seeing that can often interrupt deployment progress.</span></span>

### <a name="disk-encryption"></a><span data-ttu-id="109fa-114">磁盘加密</span><span class="sxs-lookup"><span data-stu-id="109fa-114">Disk Encryption</span></span>

<span data-ttu-id="109fa-p104">可能遇到的第一个初始挑战是硬盘加密。许多硬盘加密解决方案无法轻松地从以前版本的 Windows 升级到较新版本的 Windows。</span><span class="sxs-lookup"><span data-stu-id="109fa-p104">First one of the initial challenges you might encounter is hard disk encryption. Many solutions for hard disk encryption cannot easily be upgraded from a previous version of Windows to a newer version of Windows.</span></span>

<span data-ttu-id="109fa-p105">使用某些磁盘加密解决方案，可以在某些版本的平台上使用 Windows 安装程序的“/reflectdrivers”选项时执行升级，但其他版本可能要求在部署之前解密驱动器，然后在安装 Windows 10 后重新加密。另外，部分解决方案不允许使用传统 BIOS 从主启动记录 (MBR) 迁移到 UEFI 所需的 GUID 分区表 (GPT)。这一点很重要，因为 Windows 10 中基于虚拟化的新安全功能需要 64 位版本且带 UEFI 的 Windows 10，下面将对此进行说明。</span><span class="sxs-lookup"><span data-stu-id="109fa-p105">Some disk encryption solutions allow you to perform the upgrades when using the ‘/reflectdrivers’ option with Windows Setup on certain versions of their platforms, but others may require you to unencrypt the drive prior to deployment, then re-encrypt after Windows 10 is installed. Some solutions also do not allow you to move from Master Boot Record (MBR), using legacy BIOS, to GUID Partition Table (GPT), required for UEFI. This is important because a 64-bit version of Windows 10 with UEFI is required for the new virtualization-based security capabilities in Windows 10 and those are explained below.</span></span>

<span data-ttu-id="109fa-p106">解决这些问题的一种方法是在 Windows 10 中使用 BitLocker，它包含在 Windows 10 专业版和更高版本中。使用 BitLocker 可以在此过程中暂停对 OS 升级和功能更新的保护。</span><span class="sxs-lookup"><span data-stu-id="109fa-p106">One option to resolve these issues is using BitLocker in Windows 10, which is included in Windows 10 Pro and higher editions. BitLocker allows you to suspend protection for OS upgrades and Feature Updates as part of the process.</span></span>

<span data-ttu-id="109fa-122">
  [Bitlocker 基本部署](https://docs.microsoft.com/zh-CN/windows/security/information-protection/bitlocker/bitlocker-basic-deployment)</span><span class="sxs-lookup"><span data-stu-id="109fa-122">[Bitlocker basic deployment](https://docs.microsoft.com/en-us/windows/security/information-protection/bitlocker/bitlocker-basic-deployment)</span></span>

### <a name="antivirus-and-antimalware-application-compatibility"></a><span data-ttu-id="109fa-123">防病毒和反恶意软件应用程序兼容性</span><span class="sxs-lookup"><span data-stu-id="109fa-123">Antivirus and Antimalware Application Compatibility</span></span>

<span data-ttu-id="109fa-p107">其次，虽然我们已经看到 Windows 7 和 Windows 10 之间超过 [99% 的 Windows 应用程序具有兼容性](https://www.microsoft.com/en-us/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/)，但防病毒 (AV) 应用或虚拟专用网络 (VPN) 客户端通常属例外情况。这些应用程序通常使用未记录的方式实现非标准开发实践和 API，从而保护你的系统或将你连接到网络资源。</span><span class="sxs-lookup"><span data-stu-id="109fa-p107">Second, while we’ve seen that more than [99% of Windows applications are compatible](https://www.microsoft.com/en-us/microsoft-365/blog/2018/09/06/helping-customers-shift-to-a-modern-desktop/) between Windows 7 and Windows 10, the exceptions are often anti-virus (AV) apps or Virtual Private Network (VPN) clients. These applications often implement non-standard development practices and APIs, using often undocumented ways to protect your system or connect you to network resources.</span></span>

<span data-ttu-id="109fa-p108">因此，当转换到新版本的 Windows 时，这些应用本质上不怎么发生变化。如果你的 AV 或 VPN 软件在 Windows 10 中或升级后无法运行，修复方法通常是使用 Windows 10 上经测试受支持的内容替换你正在使用的应用。</span><span class="sxs-lookup"><span data-stu-id="109fa-p108">As a result, these apps by nature can be fragile to changes when shifting to a new version of Windows. If your AV or VPN software doesn’t work in Windows 10 or after upgrading, the fix is typically to replace the app you’re using with something supported and tested on Windows 10.</span></span>

### <a name="security-policies"></a><span data-ttu-id="109fa-128">安全策略</span><span class="sxs-lookup"><span data-stu-id="109fa-128">Security Policies</span></span>

<span data-ttu-id="109fa-p109">用于旧版 Windows 和 Office 的 Active Directory 组策略设置可能无法直接转换为 Windows 10 和 Office 365 专业增强版，并且对更新的安全性和合规性功能有不同的注意事项。最好使用 Microsoft Security Compliance Toolkit 获取当前版本的 Windows 和 Office 的安全策略基准。另外，作为 Microsoft Intune 的一部分，值得研究移动设备管理策略。</span><span class="sxs-lookup"><span data-stu-id="109fa-p109">Your Active Directory Group Policy settings used for older versions of Windows and Office may not translate directly to Windows 10 and Office 365 ProPlus, and there are different considerations with newer security and compliance capabilities. It’s a good idea to use the Microsoft Security Compliance Toolkit to get a baseline of the security policies for current versions of Windows and Office. Additionally, it’s worth looking into Mobile Device Management policies as part of Microsoft Intune.</span></span>

![](media/step-5-security-and-compliance-media/step-5-security-and-compliance-media-3.png)

## 

## <a name="new-security-and-compliance-capabilities-in-microsoft-365"></a><span data-ttu-id="109fa-132">Microsoft 365 新安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="109fa-132">New Security and Compliance Capabilities in Microsoft 365</span></span>

<span data-ttu-id="109fa-p110">下面介绍在推进当前保护时的注意事项以及在迁移之前要注意的事项。现在我们来看看在从 EMS 及更高版本迁移到 Windows 10、Office 365 专业增强版和基于云的选项时可以利用的新功能。</span><span class="sxs-lookup"><span data-stu-id="109fa-p110">Now, those were considerations for moving your current protections forward and things to be aware of before your shift. Now let’s take a look at new capabilities that you can take advantage of when moving to Windows 10, Office 365 ProPlus and cloud-based options from EMS and beyond.</span></span>

### <a name="identity-and-access-management"></a><span data-ttu-id="109fa-135">身份和访问管理</span><span class="sxs-lookup"><span data-stu-id="109fa-135">Identity and Access Management</span></span>

<span data-ttu-id="109fa-p111">首先是身份和访问管理。Azure Active Directory 是适用于应用、设备和云服务的身份控制平台，也是连接 Office 365 和其他云服务的新式方式。使用条件访问可以根据登录的位置、正在使用的设备以及异常行为等内容定义不同的身份验证要求。</span><span class="sxs-lookup"><span data-stu-id="109fa-p111">Starting with identity and access management. Azure Active Directory is the identity control plane for apps, devices and Cloud services and is the modern way to connect to Office 365 and other Cloud services. Conditional access allows you to define different authentication requirements based on where you are logging in from, which device you're using, as well as things like anomalous behaviors.</span></span>

<span data-ttu-id="109fa-p112">生物识别技术可以在设备级别提供唯一标识符，帮助你在朝着消除密码的目标迈进时实现更简单、更安全地访问设备和应用。Windows Hello 提供基于设备的多重身份验证。它依赖于设备本身、你的 PIN 或唯一生物识别标识符（例如，你的面部或指纹），可以通过策略强制执行。</span><span class="sxs-lookup"><span data-stu-id="109fa-p112">At the device level, biometrics can provide unique identifiers for simpler and more secure access to your devices and apps - as you move toward the goal of eliminating passwords. Windows Hello offers device-based, multi-factor authentication. It relies on the device itself, your PIN, or unique biometric identifier such as your face or fingerprint, which you can enforce via policy.</span></span>

<span data-ttu-id="109fa-142">
  [Azure 身份管理基础知识](https://docs.microsoft.com/zh-CN/azure/active-directory/fundamentals/identity-fundamentals)</span><span class="sxs-lookup"><span data-stu-id="109fa-142">[Fundamentals of Azure identity management](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/identity-fundamentals)</span></span>

<span data-ttu-id="109fa-143">
  [了解 Azure 标识解决方案](https://docs.microsoft.com/zh-CN/azure/active-directory/fundamentals/understand-azure-identity-solutions)</span><span class="sxs-lookup"><span data-stu-id="109fa-143">[Understand Azure identity solutions](https://docs.microsoft.com/en-us/azure/active-directory/fundamentals/understand-azure-identity-solutions)</span></span>

<span data-ttu-id="109fa-144">
  [Azure Active Directory 条件访问](https://docs.microsoft.com/zh-CN/azure/active-directory/conditional-access/overview)</span><span class="sxs-lookup"><span data-stu-id="109fa-144">[Azure Active Directory Conditional Access](https://docs.microsoft.com/en-us/azure/active-directory/conditional-access/overview)</span></span>

<span data-ttu-id="109fa-145">
  [Windows Hello 企业版](https://docs.microsoft.com/zh-CN/windows/security/identity-protection/hello-for-business/hello-identity-verification)</span><span class="sxs-lookup"><span data-stu-id="109fa-145">[Windows Hello for Business](https://docs.microsoft.com/en-us/windows/security/identity-protection/hello-for-business/hello-identity-verification)</span></span>

### <a name="virtualization-based-security"></a><span data-ttu-id="109fa-146">基于虚拟化的安全性</span><span class="sxs-lookup"><span data-stu-id="109fa-146">Virtualization-based security</span></span>

<span data-ttu-id="109fa-p113">现在，除了身份之外，还可以针对已知威胁和未知威胁启用持续保护，为此，Windows 10 使用起核心作用的基于虚拟化的安全性，通过安全启动确保启动完整性和代码完整性。我们还可以通过保持独立于 Windows 的用户机密来帮助借助 Credential Guard 阻止凭据窃取。此外，应用程序防护可以通过在隔离容器中运行浏览器来隔离和缓解基于浏览器的威胁。所有这些技术都使用 Windows 10 基于虚拟化的安全性，并且是无法在 Windows 7 系统上复制的基础更改。请注意，这些功能也需要带 UEFI 的 64 位 Windows 和 SLAT 的虚拟化扩展支持（硬件级别）。</span><span class="sxs-lookup"><span data-stu-id="109fa-p113">Now beyond identity, you can also enable continuous protection against both known and unknown threats and to do this Windows 10 uses virtualization-based security at the core to ensure boot integrity and code integrity using Secure Boot. We can help also stop credential theft with Credential Guard by maintaining user secrets in isolation from Windows. And, Application Guard can isolate and mitigate browser-based threats by running the browser in an isolated container. All of these technologies use virtualization-based security in Windows 10 and are foundational changes that cannot be replicated on a Windows 7 system – note that these also require UEFI, 64-bit Windows and virtualization extension support with SLAT – at the hardware level.</span></span>

<span data-ttu-id="109fa-151">
  [有关基于虚拟化的安全性的详细信息](https://docs.microsoft.com/zh-CN/windows-hardware/design/device-experiences/oem-vbs)</span><span class="sxs-lookup"><span data-stu-id="109fa-151">[More on Virtualization-based Security](https://docs.microsoft.com/en-us/windows-hardware/design/device-experiences/oem-vbs)</span></span>

### <a name="security-enhancements-from-cloud-services"></a><span data-ttu-id="109fa-152">云服务的安全增强功能</span><span class="sxs-lookup"><span data-stu-id="109fa-152">Security enhancements from cloud services</span></span>

<span data-ttu-id="109fa-p114">云服务提供另一层可选保护以提高 Windows 和 Office 安全性。这些可以为你提供新级别的始终实时控制，可以即时检测、抵制和响应新的攻击和攻击类型，在与响应和更新部署时间本身就更慢的传统软件更新和 AV 签名文件相比之下，这些作用尤为显著。</span><span class="sxs-lookup"><span data-stu-id="109fa-p114">Cloud services provide another layer of optional protection to improve Windows and Office security. These can give you a new level of often real-time control that can instantly detect, resist and respond to new attacks and attack types – especially compared to traditional software updating and AV signature files – where response and update deployment times are inherently slower.</span></span>

<span data-ttu-id="109fa-p115">借助 Microsoft Intelligent Security Graph，可以更快速地访问来自新出现的威胁的信息和保护。可以借助下面的一些示例开始使用 Office。</span><span class="sxs-lookup"><span data-stu-id="109fa-p115">Along with the Microsoft Intelligent Security Graph, you have faster access to both information and protections from emerging threats. Here are a few examples of what you can take advantage of, starting with Office.</span></span>

<span data-ttu-id="109fa-p116">
  **
  [数据丢失防护](https://docs.microsoft.com/zh-CN/office365/securitycompliance/data-loss-prevention-policies)\*\* 内置于 Office 365 专业增强版中，可帮助在检测到信用卡或标识号等高风险内容时通知用户相关的安全策略。通知用户后，策略可以通知或阻止发送和共享。</span><span class="sxs-lookup"><span data-stu-id="109fa-p116">**[Data Loss Prevention](https://docs.microsoft.com/en-us/office365/securitycompliance/data-loss-prevention-policies)** built into Office 365 ProPlus, helps inform users of security policies when high risk content like credit card or identification numbers are detected. Policies can inform or block sending and sharing after notifying users.</span></span>

<span data-ttu-id="109fa-p117">
  **
  [Azure 信息保护](https://docs.microsoft.com/zh-CN/azure/information-protection/rms-client/client-admin-guide)\*\* 是一项可与 Office 一起使用的补充服务，使用户能够轻松地对 Office 文件进行分类和标记。它可以触发对标记文件的自动操作，例如加密或锁定共享。</span><span class="sxs-lookup"><span data-stu-id="109fa-p117">**[Azure Information Protection](https://docs.microsoft.com/en-us/azure/information-protection/rms-client/client-admin-guide)** is a complementary service that can be used with Office, allowing users to easily classify and label their Office files. It can trigger automatic action on labeled files, such as encryption or locking down sharing.</span></span>

<span data-ttu-id="109fa-161">我们还在 Office 应用中引入了**[安全链接](https://docs.microsoft.com/zh-CN/office365/securitycompliance/atp-safe-links)** 保护，保护你免受已知恶意网站的动态列表的侵害。</span><span class="sxs-lookup"><span data-stu-id="109fa-161">We've also introduced **[Safe Links](https://docs.microsoft.com/en-us/office365/securitycompliance/atp-safe-links)** protection across Office apps to protect you against a dynamic list of known malicious websites.</span></span>

<span data-ttu-id="109fa-p118">此外，Outlook 中的**[安全附件](https://docs.microsoft.com/zh-CN/office365/securitycompliance/atp-safe-attachments)** 作为 Exchange Online 的一部分，不仅仅是通过电子邮件筛选来检查附件。如果识别出高风险附件，安全附件将通知用户已知的恶意附件并将其从电子邮件中删除。</span><span class="sxs-lookup"><span data-stu-id="109fa-p118">Additionally, **[Safe Attachments](https://docs.microsoft.com/en-us/office365/securitycompliance/atp-safe-attachments)** in Outlook and as part of Exchange Online goes beyond email filtering to inspect attachments. If a high-risk attachment is identified, Safe Attachments will inform the user of known malicious attachments and remove them from email.</span></span>

<span data-ttu-id="109fa-p119">
  **
  [Office 365 邮件加密](https://docs.microsoft.com/zh-CN/office365/securitycompliance/encryption)\*\* (OME) 也可用于保护发送的电子邮件和附件，确保只有目标收件人才能查看电子邮件内容。OME 与 Google、Yahoo 和 Microsoft 使用者帐户身份验证无缝协作，一次性密码使其他电子邮件服务的用户也可以安全地接收电子邮件。</span><span class="sxs-lookup"><span data-stu-id="109fa-p119">**[Office 365 Message Encryption](https://docs.microsoft.com/en-us/office365/securitycompliance/encryption)** (OME) can also be used to safeguard email and attachments sent, ensuring only intended recipients can view email content. OME works seamlessly with Google, Yahoo, and Microsoft consumer account authentication, and one-time passcodes allow users of other email services to securely receive email as well.</span></span>

#### <a name="additional-windows-10-protections"></a><span data-ttu-id="109fa-166">其他 Windows 10 保护</span><span class="sxs-lookup"><span data-stu-id="109fa-166">Additional Windows 10 protections</span></span>

<span data-ttu-id="109fa-167">Windows 10 中的 **[Windows Defender 应用程序控制](https://docs.microsoft.com/zh-CN/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** 执行 Microsoft 已检查过安全性的已批准允许和拒绝应用程序列表，所有这些都使用 Microsoft Intune 通过终结点保护策略进行管理。</span><span class="sxs-lookup"><span data-stu-id="109fa-167">**[Windows Defender Application Control](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-application-control/windows-defender-application-control)** in Windows 10 operates off an approved allow and deny list of applications that Microsoft has checked for safety and all that is managed by endpoint protection policies using Microsoft Intune.</span></span>

<span data-ttu-id="109fa-p120">
  **
  [Windows Defender 高级威胁防护](https://docs.microsoft.com/zh-CN/windows/security/threat-protection/windows-defender-atp/overview)\*\* 是一个用于预防性保护、破坏后检测、自动调查和响应的统一平台。它可以保护终结点免受网络威胁；检测高级攻击和数据泄露，自动执行安全事件并改善安全状况。</span><span class="sxs-lookup"><span data-stu-id="109fa-p120">**[Windows Defender Advanced Threat Protection](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-atp/overview)** is a unified platform for preventative protection, post-breach detection, automated investigation, and response. It protects endpoints from cyber threats; detects advanced attacks and data breaches, automates security incidents and improves security posture.</span></span>

<span data-ttu-id="109fa-170">
  **
  [攻击防护](https://docs.microsoft.com/zh-CN/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)\*\* 通过阻止恶意软件进入 Windows 并阻止不受信任的进程访问受保护的文件夹，帮助减小运行应用程序的攻击面。</span><span class="sxs-lookup"><span data-stu-id="109fa-170">**[Exploit Guard](https://docs.microsoft.com/en-us/windows/security/threat-protection/windows-defender-exploit-guard/windows-defender-exploit-guard)** helps reduce the attack surface for running applications by preventing malware from getting into Windows and blocking untrusted processes from accessing protected folders.</span></span>

#### <a name="microsoft-intune"></a><span data-ttu-id="109fa-171">Microsoft Intune</span><span class="sxs-lookup"><span data-stu-id="109fa-171">Microsoft Intune</span></span>

<span data-ttu-id="109fa-p121">
  [Microsoft Intune](https://docs.microsoft.com/zh-CN/intune/introduction-intune) 作为基于云的管理服务，用于包括 IOS、Android 和 Windows 设备在内的移动应用场景，现在可以配置为共同管理，以补充和扩展由 System Center Configuration Manager 管理的特定工作负载的控件。这里涉及到一个优势：访问受保护资源的设备可能必须注册到设备管理（甚至是非托管、非加入域或非加入 Azure AD 的设备）。用户还可以在操作系统和应用程序级别利用粒度配置和符合性策略实施。可以使用 Microsoft Intune 集中配置应用程序策略和设置，并对 Windows 10 中的 Office 365 专业增强版和应用商店应用强制执行应用程序策略和设置。</span><span class="sxs-lookup"><span data-stu-id="109fa-p121">[Microsoft Intune](https://docs.microsoft.com/en-us/intune/introduction-intune) serves as a Cloud based management service for mobile scenarios, including IOS, Android and Windows devices, and can now be configured for co-management to complement and extend controls for specific workloads managed by System Center Configuration Manager. One advantage here is that, devices accessing protected resources can be required to enroll into device management – even non-managed, non-domain joined or non-Azure AD joined devices. You can also take advantage of granular configuration and compliance policy enforcement at the operating system and application level. Application policies and settings can be configured centrally and enforced for Office 365 ProPlus and Store apps in Windows 10 using Microsoft Intune.</span></span>

## <a name="next-step"></a><span data-ttu-id="109fa-176">后续步骤</span><span class="sxs-lookup"><span data-stu-id="109fa-176">Next Step</span></span>

## <a name="step-6-os-deployment-and-feature-updateshttpsakamsmdd6"></a>[<span data-ttu-id="109fa-177">步骤 6：OS 部署和功能更新</span><span class="sxs-lookup"><span data-stu-id="109fa-177">Step 6: OS Deployment and Feature Updates</span></span>](https://aka.ms/mdd6)

## <a name="previous-step"></a><span data-ttu-id="109fa-178">上一步</span><span class="sxs-lookup"><span data-stu-id="109fa-178">Previous Step</span></span> 

## <a name="step-4-user-files-and-settingshttpsakamsmdd4"></a>[<span data-ttu-id="109fa-179">步骤 4：用户文件和设置</span><span class="sxs-lookup"><span data-stu-id="109fa-179">Step 4: User Files and Settings</span></span>](https://aka.ms/mdd4)
