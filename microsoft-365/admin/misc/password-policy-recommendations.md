---
title: Office 365 密码策略建议
f1.keywords:
- CSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Priority
ms.collection:
- Adm_O365
- Adm_NonTOC
search.appverid:
- BCS160
- MET150
- MOE150
ms.assetid: 9fa2539a-2211-41fd-85a0-bc37b9619ca4
description: 了解如何加强组织对密码攻击的防护，学习应如何禁用常见密码并实现基于风险的多重身份验证。
ms.openlocfilehash: 74f78b6abcc3e3aa7eb3c18c858afcd8e916d432
ms.sourcegitcommit: d767c288ae34431fb046f4cfe36cec485881385f
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/15/2020
ms.locfileid: "43516919"
---
# <a name="password-policy-recommendations-for-office-365"></a><span data-ttu-id="c7775-103">Office 365 密码策略建议</span><span class="sxs-lookup"><span data-stu-id="c7775-103">Password policy recommendations for Office 365</span></span>
 
<span data-ttu-id="c7775-104">作为 Office 365 组织的管理员，你负责为组织内部用户设置密码策略。</span><span class="sxs-lookup"><span data-stu-id="c7775-104">As the admin of an Office 365 organization, you're responsible for setting password policy for users in your organization.</span></span> <span data-ttu-id="c7775-105">设置密码策略可能很复杂且令人困惑，因而本文提供了加强组织对密码攻击的防护的建议。</span><span class="sxs-lookup"><span data-stu-id="c7775-105">Setting password policy can be complicated and confusing, and this article provides recommendations to make your organization more secure against password attacks.</span></span>
  
<span data-ttu-id="c7775-106">要决定 Office 365 密码在你组织中过期的频率，请参阅[设置 Office 365 的密码过期策略](../manage/set-password-expiration-policy.md)。</span><span class="sxs-lookup"><span data-stu-id="c7775-106">To determine how often Office 365 passwords expire in your organization, see [Set password expiration policy for Office 365](../manage/set-password-expiration-policy.md).</span></span>
  
## <a name="understanding-password-recommendations"></a><span data-ttu-id="c7775-107">了解密码建议</span><span class="sxs-lookup"><span data-stu-id="c7775-107">Understanding password recommendations</span></span>

<span data-ttu-id="c7775-108">好的密码实践分为下面几个大类：</span><span class="sxs-lookup"><span data-stu-id="c7775-108">Good password practices fall into a few broad categories:</span></span>
  
- <span data-ttu-id="c7775-109">**抵御常见攻击**：这涉及到选择用户在何处输入密码（具有优秀的恶意软件检测的已知受信任设备，经过验证的网站），以及选择要选用哪个密码（密码长度和唯一性）。</span><span class="sxs-lookup"><span data-stu-id="c7775-109">**Resisting common attacks** This involves the choice of where users enter passwords (known and trusted devices with good malware detection, validated sites), and the choice of what password to choose (length and uniqueness).</span></span>

- <span data-ttu-id="c7775-110">**包含成功攻击**：包含成功黑客攻击是指限制为仅向特定服务公开，或者在用户密码被盗的情况下完全阻止该项损失。</span><span class="sxs-lookup"><span data-stu-id="c7775-110">**Containing successful attacks** Containing successful hacker attacks is about limiting exposure to a specific service, or preventing that damage altogether, if a user's password gets stolen.</span></span> <span data-ttu-id="c7775-111">例如，确保社交网络凭据的泄露不会导致你的银行帐户易受攻击，也不会使防护较弱的帐户接受重要帐户的重置链接。</span><span class="sxs-lookup"><span data-stu-id="c7775-111">For example, ensuring that a breach of your social networking credentials doesn't make your bank account vulnerable, or not letting a poorly guarded account accept reset links for an important account.</span></span>

- <span data-ttu-id="c7775-112">**了解人的天性**：很多有效的密码实践都在面对自然的人类行为时失败。</span><span class="sxs-lookup"><span data-stu-id="c7775-112">**Understanding human nature** Many valid password practices fail in the face of natural human behaviors.</span></span> <span data-ttu-id="c7775-113">了解人的天性至关重要，因为研究表明，你强加于你的用户的几乎每条规则够将导致密码质量的弱化。</span><span class="sxs-lookup"><span data-stu-id="c7775-113">Understanding human nature is critical because research shows that almost every rule you impose on your users will result in a weakening of password quality.</span></span> <span data-ttu-id="c7775-114">长度要求、特殊字符要求和密码更改要求都会促使密码的标准化，而这会使攻击者更容易猜出或破解出密码。</span><span class="sxs-lookup"><span data-stu-id="c7775-114">Length requirements, special character requirements, and password change requirements all result in normalization of passwords, which makes it easier for attackers to guess or crack passwords.</span></span>

## <a name="password-guidelines-for-administrators"></a><span data-ttu-id="c7775-115">管理员密码准则</span><span class="sxs-lookup"><span data-stu-id="c7775-115">Password guidelines for administrators</span></span>

<span data-ttu-id="c7775-116">加强密码系统安全的首要目标是密码多样性。</span><span class="sxs-lookup"><span data-stu-id="c7775-116">The primary goal of a more secure password system is password diversity.</span></span> <span data-ttu-id="c7775-117">你需要你的密码策略包含多个不同且很难猜出的密码。</span><span class="sxs-lookup"><span data-stu-id="c7775-117">You want your password policy to contain lots of different and hard to guess passwords.</span></span> <span data-ttu-id="c7775-118">下面是可帮助你的组织尽可能保障安全的一些建议。</span><span class="sxs-lookup"><span data-stu-id="c7775-118">Here are a few recommendations for keeping your organization as secure as possible.</span></span>
  
- <span data-ttu-id="c7775-119">保持至少 8 个字符长度的要求（更长不一定更好）</span><span class="sxs-lookup"><span data-stu-id="c7775-119">Maintain an 8-character minimum length requirement (longer isn't necessarily better)</span></span>

- <span data-ttu-id="c7775-120">不设定字符构成要求。</span><span class="sxs-lookup"><span data-stu-id="c7775-120">Don't require character composition requirements.</span></span> <span data-ttu-id="c7775-121">例如，\*&amp;(^%$</span><span class="sxs-lookup"><span data-stu-id="c7775-121">For example, \*&amp;(^%$</span></span>

- <span data-ttu-id="c7775-122">不要求定期对用户帐户进行强制性重置</span><span class="sxs-lookup"><span data-stu-id="c7775-122">Don't require mandatory periodic password resets for user accounts</span></span>

- <span data-ttu-id="c7775-123">禁用常见密码，使系统内部不存在易受攻击的密码</span><span class="sxs-lookup"><span data-stu-id="c7775-123">Ban common passwords, to keep the most vulnerable passwords out of your system</span></span>

- <span data-ttu-id="c7775-124">说服用户不要将其组织密码重复用于与工作无关的用途</span><span class="sxs-lookup"><span data-stu-id="c7775-124">Educate your users to not re-use their organization passwords for non-work related purposes</span></span>

- <span data-ttu-id="c7775-125">强制注册使用[多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="c7775-125">Enforce registration for [multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md)</span></span>

- <span data-ttu-id="c7775-126">克服基于风险的多重身份验证挑战</span><span class="sxs-lookup"><span data-stu-id="c7775-126">Enable risk-based multi-factor authentication challenges</span></span>

### <a name="password-guidance-for-your-users"></a><span data-ttu-id="c7775-127">用户密码准则</span><span class="sxs-lookup"><span data-stu-id="c7775-127">Password guidance for your users</span></span>

<span data-ttu-id="c7775-128">下面是针对组织内部用户的一些密码准则。</span><span class="sxs-lookup"><span data-stu-id="c7775-128">Here's some password guidance for users in your organization.</span></span> <span data-ttu-id="c7775-129">请确保使你的用户了解这些建议并在组织级别上强制实施所建议的密码策略。</span><span class="sxs-lookup"><span data-stu-id="c7775-129">Make sure to let your users know about these recommendations and enforce the recommended password policies at the organizational level.</span></span>
  
- <span data-ttu-id="c7775-130">不要使用你在任何其他网站上所用的相同或相似密码</span><span class="sxs-lookup"><span data-stu-id="c7775-130">Don't use a password that is the same or similar to one you use on any other websites</span></span>

- <span data-ttu-id="c7775-131">不要只用一个单词（如 **password**），也不要用常用短语（如 **Iloveyou**）</span><span class="sxs-lookup"><span data-stu-id="c7775-131">Don't use a single word, for example, **password**, or a commonly-used phrase like **Iloveyou**</span></span>

- <span data-ttu-id="c7775-132">使密码很难被猜出，即使是很熟悉你的人也很难猜出，例如不要设为你朋友或家人的姓名和生日、你喜欢的乐队以及你爱用的短语</span><span class="sxs-lookup"><span data-stu-id="c7775-132">Make passwords hard to guess, even by those who know a lot about you, such as the names and birthdays of your friends and family, your favorite bands, and phrases you like to use</span></span>

## <a name="some-common-approaches-and-their-negative-impacts"></a><span data-ttu-id="c7775-133">一些常见方法及其负面影响</span><span class="sxs-lookup"><span data-stu-id="c7775-133">Some common approaches and their negative impacts</span></span>

<span data-ttu-id="c7775-134">下面是一些最常用的密码管理实践，但调查结果警示我们注意其负面影响。</span><span class="sxs-lookup"><span data-stu-id="c7775-134">These are some of the most commonly used password management practices, but research warns us about the negative impacts of them.</span></span>
  
### <a name="password-expiration-requirements-for-users"></a><span data-ttu-id="c7775-135">用户密码过期要求</span><span class="sxs-lookup"><span data-stu-id="c7775-135">Password expiration requirements for users</span></span>

<span data-ttu-id="c7775-136">密码过期要求弊大于利，因为这些要求强制用户选择可预测的密码（即由彼此间紧密联系的有序单词和数字构成的密码）。</span><span class="sxs-lookup"><span data-stu-id="c7775-136">Password expiration requirements do more harm than good, because these requirements make users select predictable passwords, composed of sequential words and numbers which are closely related to each other.</span></span> <span data-ttu-id="c7775-137">在这类情况下，可能会根据上一个密码预测出下一个密码。</span><span class="sxs-lookup"><span data-stu-id="c7775-137">In these cases, the next password can be predicted based on the previous password.</span></span> <span data-ttu-id="c7775-138">密码过期要求没有提供任何控制优势，因为网络罪犯总是会在盗用凭据后立即使用这些凭据。</span><span class="sxs-lookup"><span data-stu-id="c7775-138">Password expiration requirements offer no containment benefits because cyber criminals almost always use credentials as soon as they compromise them.</span></span>
  
### <a name="requiring-long-passwords"></a><span data-ttu-id="c7775-139">要求使用长密码</span><span class="sxs-lookup"><span data-stu-id="c7775-139">Requiring long passwords</span></span>

<span data-ttu-id="c7775-140">密码长度要求（大于约 10 个字符）可能会导致出现可预测且不必要的用户行为。</span><span class="sxs-lookup"><span data-stu-id="c7775-140">Password length requirements (greater than about 10 characters) can result in user behavior that is predictable and undesirable.</span></span> <span data-ttu-id="c7775-141">例如，必须具有 16 个字符密码的用户可能会选择 **fourfourfourfour** 或 **passwordpassword** 等满足字符长度但很容易被猜出的重复模式。</span><span class="sxs-lookup"><span data-stu-id="c7775-141">For example, users who are required to have a 16-character password may choose repeating patterns like **fourfourfourfour** or **passwordpassword** that meet the character length requirement but aren't hard to guess.</span></span> <span data-ttu-id="c7775-142">此外，长度要求使得用户更可能采取其他不安全的做法，例如记下其密码、重复使用密码或将密码不加密地存储在其文档中。</span><span class="sxs-lookup"><span data-stu-id="c7775-142">Additionally, length requirements increase the chances that users will adopt other insecure practices, such as writing their passwords down, re-using them, or storing them unencrypted in their documents.</span></span> <span data-ttu-id="c7775-143">为鼓励用户考虑使用唯一密码，我们建议保持合理的 8 字符最低长度要求。</span><span class="sxs-lookup"><span data-stu-id="c7775-143">To encourage users to think about a unique password, we recommend keeping a reasonable 8-character minimum length requirement.</span></span> 
  
### <a name="requiring-the-use-of-multiple-character-sets"></a><span data-ttu-id="c7775-144">需要使用多字符集</span><span class="sxs-lookup"><span data-stu-id="c7775-144">Requiring the use of multiple character sets</span></span>

<span data-ttu-id="c7775-145">密码复杂性要求会缩减密钥空间，导致用户以可预测的方式行动，因此弊大于利。</span><span class="sxs-lookup"><span data-stu-id="c7775-145">Password complexity requirements reduce key space and cause users to act in predictable ways, doing more harm than good.</span></span> <span data-ttu-id="c7775-146">大多数系统都会强制实施一定程度的密码复杂性要求。</span><span class="sxs-lookup"><span data-stu-id="c7775-146">Most systems enforce some level of password complexity requirements.</span></span> <span data-ttu-id="c7775-147">例如，密码需要使用来自下面所有三个类别的字符：</span><span class="sxs-lookup"><span data-stu-id="c7775-147">For example, passwords need characters from all three of the following categories:</span></span>
  
- <span data-ttu-id="c7775-148">大写字符</span><span class="sxs-lookup"><span data-stu-id="c7775-148">uppercase characters</span></span>

- <span data-ttu-id="c7775-149">小写字符</span><span class="sxs-lookup"><span data-stu-id="c7775-149">lowercase characters</span></span>

- <span data-ttu-id="c7775-150">非字母数字字符</span><span class="sxs-lookup"><span data-stu-id="c7775-150">non-alphanumeric characters</span></span>

<span data-ttu-id="c7775-151">大多数用户都会使用相似的模式，例如第一个位置使用大写字母，最后一位使用符号，倒数第二位使用数字。</span><span class="sxs-lookup"><span data-stu-id="c7775-151">Most people use similar patterns, for example, a capital letter in the first position, a symbol in the last, and a number in the last 2.</span></span> <span data-ttu-id="c7775-152">而网络罪犯知道这一点，因此他们在运行字典攻击时会进行最常见的替换，例如“$”替换为“s”、“@”替换为“a”，“1”替换为“l”。</span><span class="sxs-lookup"><span data-stu-id="c7775-152">Cyber criminals know this, so they run their dictionary attacks using the most common substitutions, "$" for "s", "@" for "a," "1" for "l".</span></span> <span data-ttu-id="c7775-153">强制用户选择大写、大小、数字、特殊字符的组合会产生负面影响。</span><span class="sxs-lookup"><span data-stu-id="c7775-153">Forcing your users to choose a combination of upper, lower, digits, special characters has a negative effect.</span></span> <span data-ttu-id="c7775-154">某些复杂性要求甚至会阻止用户使用安全易记的密码，并迫使他们采用安全性更低、更难记住的密码。</span><span class="sxs-lookup"><span data-stu-id="c7775-154">Some complexity requirements even prevent users from using secure and memorable passwords, and force them into coming up with less secure and less memorable passwords.</span></span>
  
## <a name="successful-patterns"></a><span data-ttu-id="c7775-155">成功的模式</span><span class="sxs-lookup"><span data-stu-id="c7775-155">Successful Patterns</span></span>

<span data-ttu-id="c7775-156">相比之下，下面是鼓励密码多样性的一些建议。</span><span class="sxs-lookup"><span data-stu-id="c7775-156">In contrast, here are some recommendations in encouraging password diversity.</span></span>
  
### <a name="ban-common-passwords"></a><span data-ttu-id="c7775-157">禁用常见密码</span><span class="sxs-lookup"><span data-stu-id="c7775-157">Ban common passwords</span></span>

<span data-ttu-id="c7775-158">创建密码时，应对用户采用的最重要的密码要求是禁用常见密码，以使你的组织更不容易受到蛮力密码攻击。</span><span class="sxs-lookup"><span data-stu-id="c7775-158">The most important password requirement you should put on your users when creating passwords is to ban the use of common passwords to reduce your organization's susceptibility to brute force password attacks.</span></span> <span data-ttu-id="c7775-159">常见的用户密码包括 **abdcefg**、**password** 和 **monkey**。</span><span class="sxs-lookup"><span data-stu-id="c7775-159">Common user passwords include, **abdcefg**, **password**, **monkey**.</span></span>
  
### <a name="educate-users-to-not-re-use-organization-passwords-anywhere-else"></a><span data-ttu-id="c7775-160">指导用户不要在任何其他位置重复使用组织密码</span><span class="sxs-lookup"><span data-stu-id="c7775-160">Educate users to not re-use organization passwords anywhere else</span></span>

<span data-ttu-id="c7775-161">要传达给组织内部用户的最重要的消息之一是不要在任何其他位置重复使用其组织密码。</span><span class="sxs-lookup"><span data-stu-id="c7775-161">One of the most important messages to get across to users in your organization is to not re-use their organization password anywhere else.</span></span> <span data-ttu-id="c7775-162">在外部网站使用组织密码会大大增加网络罪犯盗用其密码的可能性。</span><span class="sxs-lookup"><span data-stu-id="c7775-162">The use of organization passwords in external websites greatly increases the likelihood that cyber criminals will compromise these passwords.</span></span>
  
### <a name="enforce-multi-factor-authentication-registration"></a><span data-ttu-id="c7775-163">强制进行多重身份验证注册</span><span class="sxs-lookup"><span data-stu-id="c7775-163">Enforce Multi-Factor Authentication registration</span></span>

<span data-ttu-id="c7775-164">请确保你的用户更新联系人和安全信息，例如备用电子邮件地址、电话号码或注册接收推送通知的设备，以便他们能够应对安全挑战并收到安全事件通知。</span><span class="sxs-lookup"><span data-stu-id="c7775-164">Make sure your users update contact and security information, like an alternate email address, phone number, or a device registered for push notifications, so they can respond to security challenges and be notified of security events.</span></span> <span data-ttu-id="c7775-165">更新后的联系人和安全信息可帮助用户在忘记自身密码时或者其他人试图接管其帐户时验证他们的身份。</span><span class="sxs-lookup"><span data-stu-id="c7775-165">Updated contact and security information helps users verify their identity if they ever forget their password, or if someone else tries to take over their account.</span></span> <span data-ttu-id="c7775-166">它还在登录尝试或密码更改等安全事件的情况下提供一个带外通知渠道。</span><span class="sxs-lookup"><span data-stu-id="c7775-166">It also provides an out of band notification channel in the case of security events such as login attempts or changed passwords.</span></span> 
  
<span data-ttu-id="c7775-167">要了解详细信息，请参阅[设置多重身份验证](../security-and-compliance/set-up-multi-factor-authentication.md)</span><span class="sxs-lookup"><span data-stu-id="c7775-167">To learn more, see [Set up multi-factor authentication](../security-and-compliance/set-up-multi-factor-authentication.md).</span></span>
  
### <a name="enable-risk-based-multi-factor-authentication"></a><span data-ttu-id="c7775-168">启用基于风险的多重身份验证</span><span class="sxs-lookup"><span data-stu-id="c7775-168">Enable risk-based multi-factor authentication</span></span>

<span data-ttu-id="c7775-169">基于风险的多重身份验证可确保在我们的系统检测到可疑活动时，它能迫使用户确保其自身是合法的帐户所有者。</span><span class="sxs-lookup"><span data-stu-id="c7775-169">Risk-based multi-factor authentication ensures that when our system detects suspicious activity, it can challenge the user to ensure that they are the legitimate account owner.</span></span> 
  
## <a name="want-to-know-more-recommended-reading"></a><span data-ttu-id="c7775-170">希望了解更多信息？</span><span class="sxs-lookup"><span data-stu-id="c7775-170">Want to know more?</span></span> <span data-ttu-id="c7775-171">推荐阅读</span><span class="sxs-lookup"><span data-stu-id="c7775-171">Recommended reading</span></span>

- <span data-ttu-id="c7775-172">[Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008)（强大的 Web 密码是否有用？）</span><span class="sxs-lookup"><span data-stu-id="c7775-172">[Do Strong Web Passwords Accomplish Anything?](https://go.microsoft.com/fwlink/p/?linkid=861008)</span></span>

- <span data-ttu-id="c7775-173">[Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014)（密码组合和有限努力的用户）</span><span class="sxs-lookup"><span data-stu-id="c7775-173">[Password Portfolios and the Finite-Effort User](https://go.microsoft.com/fwlink/p/?linkid=861014)</span></span>

- <span data-ttu-id="c7775-174">[Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015)（通过阅读用户的思维来阻止安全性较弱的密码）</span><span class="sxs-lookup"><span data-stu-id="c7775-174">[Preventing Weak Passwords by Reading Users' Minds](https://go.microsoft.com/fwlink/p/?linkid=861015)</span></span>

- <span data-ttu-id="c7775-175">[Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016)（选择安全的密码）</span><span class="sxs-lookup"><span data-stu-id="c7775-175">[Choosing Secure Passwords](https://go.microsoft.com/fwlink/p/?linkid=861016)</span></span>

- <span data-ttu-id="c7775-176">[Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018)（是时候重新思考强制密码更改了）</span><span class="sxs-lookup"><span data-stu-id="c7775-176">[Time to rethink mandatory password changes](https://go.microsoft.com/fwlink/p/?linkid=861018)</span></span>

- <span data-ttu-id="c7775-177">[Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)（2015 最差密码）</span><span class="sxs-lookup"><span data-stu-id="c7775-177">[Worst Passwords of 2015](https://go.microsoft.com/fwlink/p/?linkid=861020)</span></span>

- <span data-ttu-id="c7775-178">[Download files from the web](https://go.microsoft.com/fwlink/p/?linkid=861029)（下载 Web 中的文件）</span><span class="sxs-lookup"><span data-stu-id="c7775-178">[Download files from the web](https://go.microsoft.com/fwlink/p/?linkid=861029)</span></span>
