---
title: 使用标识、设备和威胁防护进行数据隐私管理
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
description: 使用用户标识、设备和威胁防护服务防止个人数据Microsoft 365。
ms.openlocfilehash: 5e08ef574e199769e572b3836b3323dc88fc4bbd
ms.sourcegitcommit: dcb97fbfdae52960ae62b6faa707a05358193ed5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2021
ms.locfileid: "51199461"
---
# <a name="use-identity-device-and-threat-protection-for-data-privacy-regulation"></a><span data-ttu-id="7536e-103">使用标识、设备和威胁防护进行数据隐私管理</span><span class="sxs-lookup"><span data-stu-id="7536e-103">Use identity, device, and threat protection for data privacy regulation</span></span>

<span data-ttu-id="7536e-104">Microsoft 365提供了许多标识、设备和威胁防护功能，组织可以使用这些功能来帮助遵守与数据隐私相关的合规性法规。</span><span class="sxs-lookup"><span data-stu-id="7536e-104">Microsoft 365 provides a number of identity, device, and threat protection capabilities that organizations can employ to help comply with data privacy-related compliance regulations.</span></span> <span data-ttu-id="7536e-105">本文介绍数据隐私法规在这些方面要求哪些内容，并提供相关功能Microsoft 365列表，并提供了可帮助您满足实现要求详细信息的链接。</span><span class="sxs-lookup"><span data-stu-id="7536e-105">This article describes what the data privacy regulations require in these areas and provides a listing of related Microsoft 365 features and services with links to more information to help you address implementation requirements.</span></span>

## <a name="how-identity-device-and-threat-protection-relate-to-data-privacy-regulation"></a><span data-ttu-id="7536e-106">标识、设备和威胁防护与数据隐私法规如何关联</span><span class="sxs-lookup"><span data-stu-id="7536e-106">How identity, device, and threat protection relate to data privacy regulation</span></span>

<span data-ttu-id="7536e-107">虽然数据隐私法规的特有性有所不同，但它们所要求的本质是，GDPR 第 5 (1)  (f) 条，其中规定：</span><span class="sxs-lookup"><span data-stu-id="7536e-107">While the data privacy regulations vary in their specificity, the essence of what they call for is embodied in the GDPR’s Article 5(1)(f), which states that:</span></span>

- <span data-ttu-id="7536e-108">个人数据的处理方式应可确保个人数据的适当安全性，包括防止未经授权的或非法处理，以及防止意外丢失、销毁或损坏，使用适当的技术或组织措施 (完整性和保密性) 。</span><span class="sxs-lookup"><span data-stu-id="7536e-108">Personal data shall be processed in a manner that ensures appropriate security of the personal data, including protection against unauthorized or unlawful processing and against accidental loss, destruction or damage, using appropriate technical or organizational measures ('integrity and confidentiality').</span></span>

<span data-ttu-id="7536e-109">因为个人数据泄露通常是由管理帐户或最终用户帐户泄露和恶意系统访问造成的。</span><span class="sxs-lookup"><span data-stu-id="7536e-109">Because personal data breaches are often caused by administrative or end-user account compromise and malicious system access.</span></span> <span data-ttu-id="7536e-110">例如，管理员帐户黑客攻击可能会导致客户信用卡号或其他个人信息的窃取。</span><span class="sxs-lookup"><span data-stu-id="7536e-110">For example, an admin account hack can result in exfiltration of customer credit card numbers or other personal information.</span></span> <span data-ttu-id="7536e-111">应实施所有可与 Microsoft 365一起提供的身份、设备和威胁防护，这些将反映在合规性分数中，可在合规性管理器中找到。</span><span class="sxs-lookup"><span data-stu-id="7536e-111">All the generally advisable identity, device, and threat protection available with Microsoft 365 potentially should be implemented, which will be reflected in your compliance score, found in Compliance Manager.</span></span>

## <a name="using-the-results-of-your-assessment-work-and-compliance-manager"></a><span data-ttu-id="7536e-112">使用评估工作和合规性管理器的结果</span><span class="sxs-lookup"><span data-stu-id="7536e-112">Using the results of your assessment work and Compliance Manager</span></span>

<span data-ttu-id="7536e-113">合规性管理器包括使用以下类别的标识、设备和威胁防护：</span><span class="sxs-lookup"><span data-stu-id="7536e-113">Compliance Manager includes identity, device, and threat protection using these categories:</span></span>

- <span data-ttu-id="7536e-114">Identity 对应于" **控制访问"** 类别</span><span class="sxs-lookup"><span data-stu-id="7536e-114">Identity corresponds to the **Control Access** category</span></span>
- <span data-ttu-id="7536e-115">设备对应于 **"管理设备"** 类别</span><span class="sxs-lookup"><span data-stu-id="7536e-115">Device corresponds to the **Manage Devices** category</span></span>
- <span data-ttu-id="7536e-116">威胁防护对应于" **防范威胁"** 类别</span><span class="sxs-lookup"><span data-stu-id="7536e-116">Threat protection corresponds to the **Protect Against Threats** category</span></span>
 
<span data-ttu-id="7536e-117">如果在包含四个主要数据隐私法规的示例集合中选择了这些策略，合规性管理器会指定 90 项改进操作，其中大多数改进措施的分数为"27"。</span><span class="sxs-lookup"><span data-stu-id="7536e-117">If these are selected across our sample set of four major data privacy regulations, Compliance Manager specifies 90 improvement actions, most of which are scored a "27".</span></span> <span data-ttu-id="7536e-118">由于合规性管理器针对这些类别调用了此类数量，因此此处列出了一些更常见的数字，仅供参考。</span><span class="sxs-lookup"><span data-stu-id="7536e-118">Since such a large number are called out by Compliance Manager for these categories, some of the more common ones are listed here, for reference.</span></span>

<span data-ttu-id="7536e-119">将 [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/)用于标识 **和控制** 访问类别，可以使用这些类别：</span><span class="sxs-lookup"><span data-stu-id="7536e-119">Use [Azure Active Directory (Azure AD)](https://azure.microsoft.com/services/active-directory/) for identity and the **Control Access** category, with which you can:</span></span>

- <span data-ttu-id="7536e-120">实施防重播的 (，以防止"中间人"攻击) </span><span class="sxs-lookup"><span data-stu-id="7536e-120">Implement replay-resistant authentication (to prevent “Man in the middle” attacks)</span></span>
- <span data-ttu-id="7536e-121">阻止旧式身份验证。</span><span class="sxs-lookup"><span data-stu-id="7536e-121">Block legacy authentication.</span></span>
- <span data-ttu-id="7536e-122">配置用户风险和用户登录风险策略。</span><span class="sxs-lookup"><span data-stu-id="7536e-122">Configure user risk and user sign-in risk policies.</span></span>
- <span data-ttu-id="7536e-123">为管理员和非管理员启用 MFA (条件) 多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="7536e-123">Enable Conditional Access and multi-factor authentication (MFA) for admins and non-admins.</span></span>
- <span data-ttu-id="7536e-124">配置和强制实施密码策略。</span><span class="sxs-lookup"><span data-stu-id="7536e-124">Configure and enforce password policies.</span></span>
- <span data-ttu-id="7536e-125">使用 Azure AD 策略限制对特权帐户Privileged Identity Management。</span><span class="sxs-lookup"><span data-stu-id="7536e-125">Restrict access to privileged accounts with Azure AD Privileged Identity Management.</span></span>
- <span data-ttu-id="7536e-126">终止时禁用访问。</span><span class="sxs-lookup"><span data-stu-id="7536e-126">Disable access upon termination.</span></span>
- <span data-ttu-id="7536e-127">审核用户帐户和状态更改。</span><span class="sxs-lookup"><span data-stu-id="7536e-127">Audit user accounts and status changes.</span></span>
- <span data-ttu-id="7536e-128">查看角色组和管理更改。</span><span class="sxs-lookup"><span data-stu-id="7536e-128">Review role group and administrative changes.</span></span>

<span data-ttu-id="7536e-129">使用 [Microsoft Endpoint Manager"](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager)管理 **设备**"类别，可进行以下操作：</span><span class="sxs-lookup"><span data-stu-id="7536e-129">Use [Microsoft Endpoint Manager](https://www.microsoft.com/microsoft-365/microsoft-endpoint-manager) for devices and the **Manage Devices** category, with which you can:</span></span>

- <span data-ttu-id="7536e-130">阻止已越狱且具有 root 权限的移动设备。</span><span class="sxs-lookup"><span data-stu-id="7536e-130">Block jail broken and rooted mobile devices.</span></span>
- <span data-ttu-id="7536e-131">配置 Intune 进行移动设备管理。</span><span class="sxs-lookup"><span data-stu-id="7536e-131">Configure Intune for mobile device management.</span></span>
- <span data-ttu-id="7536e-132">为 Android、iOS、macOS 和 Windows合规性策略。</span><span class="sxs-lookup"><span data-stu-id="7536e-132">Create compliance policies for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="7536e-133">为 Android、iOS、macOS 和 Windows配置文件。</span><span class="sxs-lookup"><span data-stu-id="7536e-133">Create a device configuration profile for Android, iOS, macOS and Windows devices.</span></span>
- <span data-ttu-id="7536e-134">创建适用于 iOS 和 Windows 的应用保护策略。</span><span class="sxs-lookup"><span data-stu-id="7536e-134">Create app protection policies for iOS and Windows.</span></span>
- <span data-ttu-id="7536e-135">使用锁屏界面隐藏信息。</span><span class="sxs-lookup"><span data-stu-id="7536e-135">Conceal information with lock screen.</span></span>
- <span data-ttu-id="7536e-136">为移动设备实施密码策略。</span><span class="sxs-lookup"><span data-stu-id="7536e-136">Implement password policies for mobile devices.</span></span>
- <span data-ttu-id="7536e-137">要求移动设备在处于非活动状态时锁定。</span><span class="sxs-lookup"><span data-stu-id="7536e-137">Require mobile devices to lock upon inactivity.</span></span>
- <span data-ttu-id="7536e-138">要求移动设备在多个登录失败时进行擦除。</span><span class="sxs-lookup"><span data-stu-id="7536e-138">Require mobile devices to wipe on multiple sign-in failures.</span></span>

<span data-ttu-id="7536e-139">将 [Exchange Online Protection 和 Microsoft Defender 用于Office 365](../security/office-365-security/defender-for-office-365.md)威胁防护 **"** 类别，你可以借助这些类别：</span><span class="sxs-lookup"><span data-stu-id="7536e-139">Use [Exchange Online Protection and Microsoft Defender for Office 365](../security/office-365-security/defender-for-office-365.md) for the **Protect Against Threats** category, with which you can:</span></span>

- <span data-ttu-id="7536e-140">启用 SPF (DMARC 和 DKIM 身份验证) 。</span><span class="sxs-lookup"><span data-stu-id="7536e-140">Enable sender authentication (SPF, DMARC and DKIM).</span></span>
- <span data-ttu-id="7536e-141">设置 Microsoft Defender Office 365防钓鱼策略。</span><span class="sxs-lookup"><span data-stu-id="7536e-141">Set up Microsoft Defender for Office 365 anti-phishing policies.</span></span>
- <span data-ttu-id="7536e-142">实现保险箱附件。</span><span class="sxs-lookup"><span data-stu-id="7536e-142">Implement Safe Attachments.</span></span>
- <span data-ttu-id="7536e-143">实现保险箱链接。</span><span class="sxs-lookup"><span data-stu-id="7536e-143">Implement Safe Links.</span></span>
- <span data-ttu-id="7536e-144">实施恶意软件检测和响应策略。</span><span class="sxs-lookup"><span data-stu-id="7536e-144">Implement malware detection and response policies.</span></span>
- <span data-ttu-id="7536e-145">实施出站和入站垃圾邮件策略。</span><span class="sxs-lookup"><span data-stu-id="7536e-145">Implement outbound and inbound spam policies.</span></span>

### <a name="references"></a><span data-ttu-id="7536e-146">引用：</span><span class="sxs-lookup"><span data-stu-id="7536e-146">References:</span></span>

- [<span data-ttu-id="7536e-147">常见标识和设备访问策略</span><span class="sxs-lookup"><span data-stu-id="7536e-147">Common identity and device access policies</span></span>](../security/office-365-security/identity-access-policies.md)
- [<span data-ttu-id="7536e-148">防范威胁Office 365</span><span class="sxs-lookup"><span data-stu-id="7536e-148">Protect against threats in Office 365</span></span>](https://support.office.com/article/protect-against-threats-in-office-365-b10023f6-f30f-45d3-b3ad-b71aa4aa0d58)
- [<span data-ttu-id="7536e-149">安全附件</span><span class="sxs-lookup"><span data-stu-id="7536e-149">Safe Attachments</span></span>](../security/office-365-security/safe-attachments.md)
- [<span data-ttu-id="7536e-150">安全链接</span><span class="sxs-lookup"><span data-stu-id="7536e-150">Safe Links</span></span>](../security/office-365-security/safe-links.md)
- [<span data-ttu-id="7536e-151">安全文档</span><span class="sxs-lookup"><span data-stu-id="7536e-151">Safe Documents</span></span>](../security/office-365-security/safe-docs.md)
