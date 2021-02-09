---
title: 安全事件响应
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: 04/27/2018
audience: ITPro
ms.topic: overview
ms.collection:
- o365_security_incident_response
- M365-security-compliance
localization_priority: Normal
search.appverid:
- MET150
description: 此解决方案将告知你在 Microsoft 365 中最常见的网络安全攻击可能是什么样，以及如何响应它们
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 8dd7a90255fdd3e083a5d7306cac2e9ca6411024
ms.sourcegitcommit: e920e68c8d0eac8b152039b52cfc139d478a67b3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50150179"
---
# <a name="security-incident-response"></a><span data-ttu-id="fc8c2-103">安全事件响应</span><span class="sxs-lookup"><span data-stu-id="fc8c2-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="fc8c2-104">**适用于**</span><span class="sxs-lookup"><span data-stu-id="fc8c2-104">**Applies to**</span></span>
- [<span data-ttu-id="fc8c2-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="fc8c2-105">Exchange Online Protection</span></span>](https://go.microsoft.com/fwlink/?linkid=2148611)
- [<span data-ttu-id="fc8c2-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="fc8c2-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](https://go.microsoft.com/fwlink/?linkid=2148715)
- [<span data-ttu-id="fc8c2-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="fc8c2-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

 <span data-ttu-id="fc8c2-108">**摘要：** 此解决方案将告知你 Office 365 中最常见的网络安全攻击的指示器、如何积极确认任何给定的攻击以及如何响应它。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="fc8c2-109">了解如何响应网络攻击</span><span class="sxs-lookup"><span data-stu-id="fc8c2-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="fc8c2-110">并非所有网络攻击都可以被阻止。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="fc8c2-111">攻击者不断在防御策略中寻找新的漏洞，或者他们利用旧的漏洞。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="fc8c2-112">了解如何识别攻击可使你更快地响应它，从而缩短安全事件的持续时间。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="fc8c2-113">本系列文章可帮助你了解 Microsoft 365 中的特定攻击类型可能的外观，并为你提供可采取响应的步骤。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="fc8c2-114">它们是快速了解的入口点：</span><span class="sxs-lookup"><span data-stu-id="fc8c2-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="fc8c2-115">攻击是什么及其工作方式。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="fc8c2-116">IOC (泄露) 、查找和如何查找的标志。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="fc8c2-117">如何积极确认攻击。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="fc8c2-118">为在将来切断攻击并更好地保护组织而要执行的步骤。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="fc8c2-119">指向每种攻击类型的深入信息的链接。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="fc8c2-120">每月查看一次，因为随着时间的推移将添加更多文章。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="fc8c2-121">检测和修正文章</span><span class="sxs-lookup"><span data-stu-id="fc8c2-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="fc8c2-122">检测和修正 Office 365 中的非法授权</span><span class="sxs-lookup"><span data-stu-id="fc8c2-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="fc8c2-123">在 Office 365 中检测并修正 Outlook 规则和自定义窗体注入攻击</span><span class="sxs-lookup"><span data-stu-id="fc8c2-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="fc8c2-124">事件响应文章</span><span class="sxs-lookup"><span data-stu-id="fc8c2-124">Incident response articles</span></span>

- [<span data-ttu-id="fc8c2-125">响应 Office 365 中遭到入侵的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="fc8c2-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="fc8c2-126">像网络安全专家那样保护 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="fc8c2-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="fc8c2-127">你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="fc8c2-128">使用 Microsoft 365 安全路线图 - 前 [30 天、前 90](security-roadmap.md) 天及以后的首要任务，实施 Microsoft 建议的最佳方案来保护 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="fc8c2-129">需要在前 30 天完成的任务。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="fc8c2-130">这些任务会对你的用户产生直接影响并且影响很小。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="fc8c2-131">需要在 90 天内完成的任务。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="fc8c2-132">它们需要多花一点时间来计划和实现，但会大大改善你的安全状况</span><span class="sxs-lookup"><span data-stu-id="fc8c2-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="fc8c2-133">90 天后。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-133">Beyond 90 days.</span></span> <span data-ttu-id="fc8c2-134">这些增强功能基于前 90 天的工作构建。</span><span class="sxs-lookup"><span data-stu-id="fc8c2-134">These enhancements build in your first 90 days work.</span></span>
