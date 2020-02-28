---
title: Microsoft 安全分数中的情况如何？
description: 介绍 microsoft 365 安全中心中的 Microsoft 安全分数、如何计算详细信息以及安全管理员可预期的内容。
keywords: 安全性、恶意软件、Microsoft 365、M365、安全分数、安全中心、改进操作
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4d445d4c917a46b12592308f599570725ace8e9d
ms.sourcegitcommit: 6c7f6ef98c321c80a9254c10bbbb917895b5c156
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/27/2020
ms.locfileid: "42322561"
---
# <a name="whats-coming-in-microsoft-secure-score"></a><span data-ttu-id="330c7-104">Microsoft 安全分数中的情况如何？</span><span class="sxs-lookup"><span data-stu-id="330c7-104">What's coming in Microsoft Secure Score?</span></span>

<span data-ttu-id="330c7-105">为了使 Microsoft 安全得分更好地代表安全状况并提高可用性，我们在不久的将来进行一些更改。</span><span class="sxs-lookup"><span data-stu-id="330c7-105">To make Microsoft Secure Score a better representative of your security posture and improve usability, we are making some changes in the near future.</span></span> <span data-ttu-id="330c7-106">你的分数和可能的最大分数都将发生变化。</span><span class="sxs-lookup"><span data-stu-id="330c7-106">Your score and the maximum possible score will change.</span></span> <span data-ttu-id="330c7-107">但是，这并不意味着您的安全状况发生了变化。</span><span class="sxs-lookup"><span data-stu-id="330c7-107">However, this does not imply a change in your security posture.</span></span>

<span data-ttu-id="330c7-108">若要了解最近所做的更改，请参阅[Microsoft 安全分数中的新增功能？](microsoft-secure-score.md#whats-new)</span><span class="sxs-lookup"><span data-stu-id="330c7-108">To learn about recent changes, see [What's new in Microsoft Secure Score?](microsoft-secure-score.md#whats-new)</span></span>

## <a name="march-2nd-2020"></a><span data-ttu-id="330c7-109">第2月2日2020</span><span class="sxs-lookup"><span data-stu-id="330c7-109">March 2nd 2020</span></span>

### <a name="removing-improvement-actions-from-intune"></a><span data-ttu-id="330c7-110">从 Intune 删除改进操作</span><span class="sxs-lookup"><span data-stu-id="330c7-110">Removing improvement actions from Intune</span></span>

<span data-ttu-id="330c7-111">评估了 Intune 提供的 Microsoft 安全得分改进操作后，它决定了它们不提供组织中设备的安全状态的有用表示形式。</span><span class="sxs-lookup"><span data-stu-id="330c7-111">After an evaluation of the Microsoft Secure Score improvement actions supplied from Intune, it was decided that they do not provide a useful representation of the security posture of devices in organizations.</span></span> <span data-ttu-id="330c7-112">我们正在努力引入可直接评估设备配置状态的安全控制，而不是重点关注策略。</span><span class="sxs-lookup"><span data-stu-id="330c7-112">Instead of focusing on policies, we are working to bring in security controls that directly assess the configuration state of the devices.</span></span>

<span data-ttu-id="330c7-113">将删除以下 Intune 改进操作：</span><span class="sxs-lookup"><span data-stu-id="330c7-113">The following Intune improvement actions will be removed:</span></span>

- <span data-ttu-id="330c7-114">启用 Microsoft Intune 移动设备管理</span><span class="sxs-lookup"><span data-stu-id="330c7-114">Enable Microsoft Intune Mobile Device Management</span></span>
- <span data-ttu-id="330c7-115">创建适用于 Android 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="330c7-115">Create a Microsoft Intune Compliance Policy for Android</span></span>
- <span data-ttu-id="330c7-116">创建适用于 Android 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="330c7-116">Create a Microsoft Intune Compliance Policy for Android for Work</span></span>
- <span data-ttu-id="330c7-117">创建适用于 Android 的 Microsoft Intune 应用保护策略</span><span class="sxs-lookup"><span data-stu-id="330c7-117">Create a Microsoft Intune App Protection Policy for Android</span></span>
- <span data-ttu-id="330c7-118">创建适用于 iOS 的 Microsoft Intune 应用保护策略</span><span class="sxs-lookup"><span data-stu-id="330c7-118">Create a Microsoft Intune App Protection Policy for iOS</span></span>
- <span data-ttu-id="330c7-119">标记不符合 Microsoft Intune 合规性策略的设备（未分配为不合规）</span><span class="sxs-lookup"><span data-stu-id="330c7-119">Mark devices with no Microsoft Intune Compliance Policy assigned as not compliant</span></span>
- <span data-ttu-id="330c7-120">创建适用于 iOS 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="330c7-120">Create a Microsoft Intune Compliance Policy for iOS</span></span>
- <span data-ttu-id="330c7-121">为 macOS 创建 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="330c7-121">Create a Microsoft Intune Compliance Policy for macOS</span></span>
- <span data-ttu-id="330c7-122">创建适用于 Windows 的 Microsoft Intune 合规性策略</span><span class="sxs-lookup"><span data-stu-id="330c7-122">Create a Microsoft Intune Compliance Policy for Windows</span></span>
- <span data-ttu-id="330c7-123">创建适用于 Android 的 Microsoft Intune 配置配置文件</span><span class="sxs-lookup"><span data-stu-id="330c7-123">Create a Microsoft Intune Configuration Profile for Android</span></span>
- <span data-ttu-id="330c7-124">为适用于 Android 的工作创建 Microsoft Intune 配置配置文件</span><span class="sxs-lookup"><span data-stu-id="330c7-124">Create a Microsoft Intune Configuration Profile for Android for Work</span></span>
- <span data-ttu-id="330c7-125">为 macOS 创建 Microsoft Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="330c7-125">Create a Microsoft Intune Configuration Profile for macOS</span></span>
- <span data-ttu-id="330c7-126">为 iOS 创建 Microsoft Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="330c7-126">Create a Microsoft Intune Configuration Profile for iOS</span></span>
- <span data-ttu-id="330c7-127">为 Windows 创建 Microsoft Intune 配置文件</span><span class="sxs-lookup"><span data-stu-id="330c7-127">Create a Microsoft Intune Configuration Profile for Windows</span></span>
- <span data-ttu-id="330c7-128">在 Microsoft Intune 中启用增强型 jailbreak 检测</span><span class="sxs-lookup"><span data-stu-id="330c7-128">Enable enhanced jailbreak detection in Microsoft Intune</span></span>
- <span data-ttu-id="330c7-129">要求对所有设备进行修补，并启用防病毒和防火墙</span><span class="sxs-lookup"><span data-stu-id="330c7-129">Require all devices to be patched, have anti-virus, and firewalls enabled</span></span>
- <span data-ttu-id="330c7-130">启用 Microsoft Intune 中的 Windows Defender ATP 集成</span><span class="sxs-lookup"><span data-stu-id="330c7-130">Enable Windows Defender ATP integration into Microsoft Intune</span></span>
- <span data-ttu-id="330c7-131">创建 Microsoft Intune Windows 信息保护策略</span><span class="sxs-lookup"><span data-stu-id="330c7-131">Create a Microsoft Intune Windows Information Protection Policy</span></span>
- <span data-ttu-id="330c7-132">要求所有设备都具有高级安全配置</span><span class="sxs-lookup"><span data-stu-id="330c7-132">Require all devices to have advanced security configurations</span></span>
- <span data-ttu-id="330c7-133">每周查看阻止的设备报告</span><span class="sxs-lookup"><span data-stu-id="330c7-133">Review blocked devices report weekly</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement"></a><span data-ttu-id="330c7-134">删除不符合可靠测量预期的改进措施</span><span class="sxs-lookup"><span data-stu-id="330c7-134">Removing improvement actions that don't meet expectations for reliable measurement</span></span> 

<span data-ttu-id="330c7-135">为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。</span><span class="sxs-lookup"><span data-stu-id="330c7-135">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="330c7-136">启用审核数据记录</span><span class="sxs-lookup"><span data-stu-id="330c7-136">Turn on audit data recording</span></span>
- <span data-ttu-id="330c7-137">发现有风险和不兼容的卷影 IT 应用程序</span><span class="sxs-lookup"><span data-stu-id="330c7-137">Discover risky and non-compliant shadow IT applications</span></span>
- <span data-ttu-id="330c7-138">查看权限 & 阻止连接到您的环境的有风险的 OAuth 应用程序</span><span class="sxs-lookup"><span data-stu-id="330c7-138">Review permissions & block risky OAuth applications connected to your environment</span></span>
- <span data-ttu-id="330c7-139">在 SharePoint online 文档库中设置版本控制</span><span class="sxs-lookup"><span data-stu-id="330c7-139">Set up versioning on SharePoint online document libraries</span></span>

### <a name="mfa-improvement-action-updates"></a><span data-ttu-id="330c7-140">MFA 改进操作更新</span><span class="sxs-lookup"><span data-stu-id="330c7-140">MFA improvement action updates</span></span>

<span data-ttu-id="330c7-141">为了反映企业在应用使用其业务的策略时确保 upmost 安全性的需求，Microsoft 安全记分将删除围绕多重身份验证的三个改进操作，并添加两个。</span><span class="sxs-lookup"><span data-stu-id="330c7-141">To reflect the need for businesses to ensure the upmost security while applying policies that work with their business, Microsoft Secure Score is removing three improvement actions centered around multi-factor authentication, and adding two.</span></span>

<span data-ttu-id="330c7-142">将删除的三个：</span><span class="sxs-lookup"><span data-stu-id="330c7-142">The three that will be removed:</span></span>

- <span data-ttu-id="330c7-143">为多因素身份验证注册所有用户</span><span class="sxs-lookup"><span data-stu-id="330c7-143">Register all users for multi-factor authentication</span></span>
- <span data-ttu-id="330c7-144">要求对所有用户进行 MFA</span><span class="sxs-lookup"><span data-stu-id="330c7-144">Require MFA for all users</span></span>
- <span data-ttu-id="330c7-145">需要对 Azure AD 特权角色进行 MFA</span><span class="sxs-lookup"><span data-stu-id="330c7-145">Require MFA for Azure AD privileged roles</span></span>

<span data-ttu-id="330c7-146">添加了新的改进操作：</span><span class="sxs-lookup"><span data-stu-id="330c7-146">New improvement actions added:</span></span>

- <span data-ttu-id="330c7-147">确保所有用户都可以完成多重身份验证以实现安全访问</span><span class="sxs-lookup"><span data-stu-id="330c7-147">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="330c7-148">需要对管理角色进行 MFA</span><span class="sxs-lookup"><span data-stu-id="330c7-148">Require MFA for administrative roles</span></span>

 <span data-ttu-id="330c7-149">这些新的改进操作需要为你的用户或管理员在你的目录中注册多重身份验证（MFA），并建立符合你的组织需求的一组适当的策略。</span><span class="sxs-lookup"><span data-stu-id="330c7-149">These new improvement actions will require registering your users or admins for multi-factor authentication (MFA) across your directory and establishing the right set of policies that fit your organizational needs.</span></span> <span data-ttu-id="330c7-150">主要目标具有灵活性，同时确保所有用户和管理员都可以通过多个因素或基于风险的身份验证提示进行身份验证。</span><span class="sxs-lookup"><span data-stu-id="330c7-150">The main goal is have flexibility while ensuring all your users and admins can authenticate with multiple factors or risk-based identity verification prompts.</span></span> <span data-ttu-id="330c7-151">这可以采用具有多个策略的形式，这些策略将应用范围决定，或者设置安全默认值（即将3月16日），让 Microsoft 决定何时对用户进行 MFA 质询。</span><span class="sxs-lookup"><span data-stu-id="330c7-151">That can take the form of having multiple policies that apply scoped decisions, or setting security defaults (coming March 16th) that let Microsoft decide when to challenge users for MFA.</span></span>

### <a name="removing-review-improvement-actions"></a><span data-ttu-id="330c7-152">删除 "审阅" 改进操作</span><span class="sxs-lookup"><span data-stu-id="330c7-152">Removing “review” improvement actions</span></span>

<span data-ttu-id="330c7-153">安全得分的原则之一是，分数应标准化且易于关联。</span><span class="sxs-lookup"><span data-stu-id="330c7-153">One of the principles of Secure Score is that the score should be standardized and easy to relate to.</span></span> <span data-ttu-id="330c7-154">具有不可衡量或可操作的改进操作已导致混淆。</span><span class="sxs-lookup"><span data-stu-id="330c7-154">Having improvement actions that are not measurable or actionable has been causing confusion.</span></span> <span data-ttu-id="330c7-155">仅当每个建议都可以清楚地影响分数时，一条 Microsoft 安全分数才有意义。</span><span class="sxs-lookup"><span data-stu-id="330c7-155">One Microsoft Secure Score only makes sense when every recommendation can have a clear effect on the score.</span></span> <span data-ttu-id="330c7-156">与其他改进操作相比，评审改进操作的计算方式不是相同标准。</span><span class="sxs-lookup"><span data-stu-id="330c7-156">Review improvement actions are not measured to the same standard as other improvement actions.</span></span>  

<span data-ttu-id="330c7-157">出于这些原因，需要审阅节奏的所有改进操作都将暂时删除。</span><span class="sxs-lookup"><span data-stu-id="330c7-157">For these reasons, all improvement actions that required a review cadence will be temporarily removed.</span></span> <span data-ttu-id="330c7-158">您的部件不需要执行任何操作。</span><span class="sxs-lookup"><span data-stu-id="330c7-158">No action is needed on your part.</span></span>

## <a name="march-16th-2020"></a><span data-ttu-id="330c7-159">3月16日2020</span><span class="sxs-lookup"><span data-stu-id="330c7-159">March 16th 2020</span></span>

### <a name="removing-improvement-actions-that-dont-meet-expectations-for-reliable-measurement-or-dont-provide-a-useful-representation-of-security-posture"></a><span data-ttu-id="330c7-160">删除不符合可靠测量预期的改进操作或不提供安全状态的有用表示形式</span><span class="sxs-lookup"><span data-stu-id="330c7-160">Removing improvement actions that don't meet expectations for reliable measurement or don't provide a useful representation of security posture</span></span>

<span data-ttu-id="330c7-161">为了确保 Microsoft 安全分数是有意义的，并且每个改进操作都是可衡量和可靠的，我们将删除以下改进操作。</span><span class="sxs-lookup"><span data-stu-id="330c7-161">To ensure that the Microsoft Secure Score is meaningful and that every improvement action is measurable and reliable, we are removing the following improvement actions.</span></span>

- <span data-ttu-id="330c7-162">将用户文档存储在 OneDrive for Business 中</span><span class="sxs-lookup"><span data-stu-id="330c7-162">Store user documents in OneDrive for Business</span></span>
- <span data-ttu-id="330c7-163">设置 Office 365 ATP 安全附件策略</span><span class="sxs-lookup"><span data-stu-id="330c7-163">Set up Office 365 ATP Safe Attachment policies</span></span>
- <span data-ttu-id="330c7-164">设置 Office 365 安全链接以验证 Url</span><span class="sxs-lookup"><span data-stu-id="330c7-164">Set up Office 365 Safe Links to verify URLs</span></span>
- <span data-ttu-id="330c7-165">不允许邮箱委派</span><span class="sxs-lookup"><span data-stu-id="330c7-165">Do not allow mailbox delegation</span></span>
- <span data-ttu-id="330c7-166">允许匿名来宾共享网站和文档的链接</span><span class="sxs-lookup"><span data-stu-id="330c7-166">Allow anonymous guest sharing links for sites and docs</span></span>
- <span data-ttu-id="330c7-167">启用云应用安全控制台</span><span class="sxs-lookup"><span data-stu-id="330c7-167">Turn on Cloud App Security Console</span></span>

### <a name="supporting-security-defaults-for-azure-ad-improvement-actions"></a><span data-ttu-id="330c7-168">支持 Azure AD 改进操作的安全默认值</span><span class="sxs-lookup"><span data-stu-id="330c7-168">Supporting security defaults for Azure AD improvement actions</span></span>

<span data-ttu-id="330c7-169">Microsoft 安全分数将更新改进操作以支持[AZURE AD 中的安全默认](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults)设置，这使组织可以更轻松地使用预配置的常见攻击安全设置来保护组织。</span><span class="sxs-lookup"><span data-stu-id="330c7-169">Microsoft Secure Score will be updating improvement actions to support [security defaults in Azure AD](https://docs.microsoft.com/azure/active-directory/fundamentals/concept-fundamentals-security-defaults), which make it easier to help protect your organization with pre-configured security settings for common attacks.</span></span>

<span data-ttu-id="330c7-170">这将影响以下改进操作：</span><span class="sxs-lookup"><span data-stu-id="330c7-170">It will affect the following improvement actions:</span></span>

- <span data-ttu-id="330c7-171">确保所有用户都可以完成多重身份验证以实现安全访问</span><span class="sxs-lookup"><span data-stu-id="330c7-171">Ensure all users can complete multi-factor authentication for secure access</span></span>
- <span data-ttu-id="330c7-172">需要对管理角色进行 MFA</span><span class="sxs-lookup"><span data-stu-id="330c7-172">Require MFA for administrative roles</span></span>
- <span data-ttu-id="330c7-173">启用策略以阻止旧版身份验证</span><span class="sxs-lookup"><span data-stu-id="330c7-173">Enable policy to block legacy authentication</span></span>
