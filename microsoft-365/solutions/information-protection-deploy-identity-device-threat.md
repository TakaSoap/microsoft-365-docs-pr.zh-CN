---
title: 对数据隐私法规使用标识、设备和威胁防护
ms.author: bcarter
author: brendacarter
f1.keywords:
- NOCSH
manager: laurawi
ms.date: 06/09/2020
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
- m365solution-infoprotection
- m365solution-scenario
ms.custom: ''
description: 使用 Microsoft 365 的标识、设备和威胁防护服务防止个人数据泄露。
ms.openlocfilehash: 321b60efbdabe62b14502df4a16dd2dcec4b9cef
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847174"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="e0483-103">对数据隐私法规使用标识、设备和威胁防护</span><span class="sxs-lookup"><span data-stu-id="e0483-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="e0483-104">Microsoft 365 提供了大量标识、设备和威胁防护功能，组织可以使用这些功能来帮助遵守与数据隐私相关的合规性管理法规。</span><span class="sxs-lookup"><span data-stu-id="e0483-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="e0483-105">本文介绍了这些方面的数据隐私法规所需的内容，并提供了相关 Microsoft 365 功能和服务的列表，并提供了可帮助您解决实现要求的详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="e0483-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="e0483-106">标识、设备和威胁防护与数据隐私法规的关系</span><span class="sxs-lookup"><span data-stu-id="e0483-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="e0483-107">尽管数据隐私条例的具体程度各不相同，但它们调用的内容的本质是在 GDPR 的文章 5 (1) # B2 f) 中体现，这表明：</span><span class="sxs-lookup"><span data-stu-id="e0483-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span> 

- <span data-ttu-id="e0483-108">应以确保个人数据的适当安全性的方式处理个人数据，包括防止未经授权或非法处理的保护，以及防止意外丢失、损坏或损坏、使用适当的技术或组织措施 ( "完整性和机密性" ) 。</span><span class="sxs-lookup"><span data-stu-id="e0483-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="e0483-109">由于个人数据泄露通常是由管理或最终用户帐户泄露和恶意系统访问导致的。</span><span class="sxs-lookup"><span data-stu-id="e0483-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="e0483-110">例如，管理员帐户黑客攻击可能会导致 exfiltration 的客户信用卡号码或其他个人信息。</span><span class="sxs-lookup"><span data-stu-id="e0483-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="e0483-111">可能应实施 Microsoft 365 提供的所有通常建议的标识、设备和威胁防护，这将反映在合规性管理器中找到的合规性分数中。</span><span class="sxs-lookup"><span data-stu-id="e0483-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="e0483-112">使用评估工作和合规性管理器的结果</span><span class="sxs-lookup"><span data-stu-id="e0483-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="e0483-113">合规性管理器包括使用以下类别的标识、设备和威胁防护：</span><span class="sxs-lookup"><span data-stu-id="e0483-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="e0483-114">标识对应于 **控件访问** 类别</span><span class="sxs-lookup"><span data-stu-id="e0483-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="e0483-115">设备对应于 " **管理设备** " 类别</span><span class="sxs-lookup"><span data-stu-id="e0483-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="e0483-116">威胁防护对应于 " **针对威胁进行保护** " 类别</span><span class="sxs-lookup"><span data-stu-id="e0483-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="e0483-117">如果在我们的四个主要数据隐私法规的示例集中选择这些选项，合规性管理器将指定90改进操作，其中大多数被评分为 "27"。</span><span class="sxs-lookup"><span data-stu-id="e0483-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="e0483-118">由于这些类别的合规性管理器会调用此类较大的数字，因此在此处列出了一些较常见的数字，以供参考。</span><span class="sxs-lookup"><span data-stu-id="e0483-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="e0483-119">使用 [Azure Active Directory (AZURE AD)](https://azure.microsoft.com/services/active-directory/) for Identity And **Control Access** 类别，您可以：</span><span class="sxs-lookup"><span data-stu-id="e0483-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="e0483-120">实施不能重放的身份验证 (以防止 "中间人" 攻击) </span><span class="sxs-lookup"><span data-stu-id="e0483-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="e0483-121">阻止旧式身份验证。</span><span class="sxs-lookup"><span data-stu-id="e0483-121">Block legacy authentication.</span></span>
- <span data-ttu-id="e0483-122">配置用户风险和用户登录风险策略。</span><span class="sxs-lookup"><span data-stu-id="e0483-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="e0483-123">为管理员和非管理员启用条件访问和多重身份验证 (MFA) 。</span><span class="sxs-lookup"><span data-stu-id="e0483-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="e0483-124">配置和强制实施密码策略。</span><span class="sxs-lookup"><span data-stu-id="e0483-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="e0483-125">使用 Azure AD 特权标识管理限制对特权帐户的访问。</span><span class="sxs-lookup"><span data-stu-id="e0483-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="e0483-126">终止时禁用访问。</span><span class="sxs-lookup"><span data-stu-id="e0483-126">Disable access upon termination.</span></span>
- <span data-ttu-id="e0483-127">审核用户帐户和状态更改。</span><span class="sxs-lookup"><span data-stu-id="e0483-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="e0483-128">审阅角色组和管理更改。</span><span class="sxs-lookup"><span data-stu-id="e0483-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="e0483-129">使用适用于设备的 [Microsoft 终结点管理器](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) 和 " **管理设备** " 类别，您可以：</span><span class="sxs-lookup"><span data-stu-id="e0483-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="e0483-130">阻止越狱断开的和根的移动设备。</span><span class="sxs-lookup"><span data-stu-id="e0483-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="e0483-131">为移动设备管理配置 Intune。</span><span class="sxs-lookup"><span data-stu-id="e0483-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="e0483-132">为 Android、iOS、macOS 和 Windows 设备创建合规性策略。</span><span class="sxs-lookup"><span data-stu-id="e0483-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="e0483-133">为 Android、iOS、macOS 和 Windows 设备创建设备配置文件。</span><span class="sxs-lookup"><span data-stu-id="e0483-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="e0483-134">为 iOS 和 Windows 创建应用保护策略。</span><span class="sxs-lookup"><span data-stu-id="e0483-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="e0483-135">使用锁屏屏蔽信息。</span><span class="sxs-lookup"><span data-stu-id="e0483-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="e0483-136">为移动设备实施密码策略。</span><span class="sxs-lookup"><span data-stu-id="e0483-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="e0483-137">要求移动设备在不活动时锁定。</span><span class="sxs-lookup"><span data-stu-id="e0483-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="e0483-138">要求移动设备在出现多个登录失败时擦除。</span><span class="sxs-lookup"><span data-stu-id="e0483-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="e0483-139">使用 [Exchange Online Protection 和 Microsoft Defender For Office 365](../security/office-365-security/office-365-atp.md) For The **防御威胁** 类别，您可以：</span><span class="sxs-lookup"><span data-stu-id="e0483-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/office-365-atp.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="e0483-140">启用 (SPF、DMARC 和 DKIM) 的发件人身份验证。</span><span class="sxs-lookup"><span data-stu-id="e0483-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="e0483-141">设置 Microsoft Defender for Office 365 反网络钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="e0483-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="e0483-142">实施安全附件。</span><span class="sxs-lookup"><span data-stu-id="e0483-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="e0483-143">实现安全链接。</span><span class="sxs-lookup"><span data-stu-id="e0483-143">Implement Safe Links.</span></span>
- <span data-ttu-id="e0483-144">实施恶意软件检测和响应策略。</span><span class="sxs-lookup"><span data-stu-id="e0483-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="e0483-145">实施出站和入站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="e0483-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="e0483-146">参照</span><span class="sxs-lookup"><span data-stu-id="e0483-146">References:</span></span>

- [<span data-ttu-id="e0483-147">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="e0483-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="e0483-148">防御 Office 365 中的威胁</span><span class="sxs-lookup"><span data-stu-id="e0483-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="e0483-149">安全附件</span><span class="sxs-lookup"><span data-stu-id="e0483-149">Safe Attachments</span></span>](../security/office-365-security/atp-safe-attachments.md)
- [<span data-ttu-id="e0483-150">安全链接</span><span class="sxs-lookup"><span data-stu-id="e0483-150">Safe Links</span></span>](../security/office-365-security/atp-safe-links.md)
- [<span data-ttu-id="e0483-151">安全文档</span><span class="sxs-lookup"><span data-stu-id="e0483-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
