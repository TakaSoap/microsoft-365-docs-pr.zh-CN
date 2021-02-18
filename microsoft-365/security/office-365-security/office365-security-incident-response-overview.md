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
description: 此解决方案会告知你在 Microsoft 365 中最常见的网络安全攻击可能是什么，以及如何响应它们
ms.custom:
- seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: d37fb232b717485c40218fd8a3c3117ba9b8322b
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50287637"
---
# <a name="security-incident-response"></a><span data-ttu-id="0ff88-103">安全事件响应</span><span class="sxs-lookup"><span data-stu-id="0ff88-103">Security Incident Response</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

<span data-ttu-id="0ff88-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="0ff88-104">**Applies to**</span></span>
- [<span data-ttu-id="0ff88-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="0ff88-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="0ff88-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="0ff88-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="0ff88-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="0ff88-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

 <span data-ttu-id="0ff88-108">**摘要：** 此解决方案将告知你 Office 365 中最常见的网络安全攻击的指示器、如何主动确认任何给定的攻击以及如何响应它。</span><span class="sxs-lookup"><span data-stu-id="0ff88-108">**Summary:** This solution tells you what the indicators are for the most common cybersecurity attacks in Office 365, how to positively confirm any given attack, and how to respond to it.</span></span>

## <a name="learn-how-to-respond-to-cyberattacks"></a><span data-ttu-id="0ff88-109">了解如何响应网络攻击</span><span class="sxs-lookup"><span data-stu-id="0ff88-109">Learn how to respond to cyberattacks</span></span>

<span data-ttu-id="0ff88-110">并非所有网络攻击都可以被阻止。</span><span class="sxs-lookup"><span data-stu-id="0ff88-110">Not all cyberattacks can be thwarted.</span></span> <span data-ttu-id="0ff88-111">攻击者不断寻找防御策略中的新漏洞，或者他们利用旧漏洞。</span><span class="sxs-lookup"><span data-stu-id="0ff88-111">Attackers are constantly looking for new weaknesses in your defensive strategy or they are exploiting old ones.</span></span> <span data-ttu-id="0ff88-112">了解如何识别攻击可让你更快地响应它，从而缩短安全事件的持续时间。</span><span class="sxs-lookup"><span data-stu-id="0ff88-112">Knowing how to recognize an attack allows you to respond to it faster, which shortens the duration of the security incident.</span></span>

<span data-ttu-id="0ff88-113">本系列文章可帮助你了解 Microsoft 365 中的特定攻击类型可能的外观，并为你提供可采取响应的步骤。</span><span class="sxs-lookup"><span data-stu-id="0ff88-113">This series of article helps you understand what a particular type of attack might look like in Microsoft 365 and gives you steps you can take to respond.</span></span> <span data-ttu-id="0ff88-114">它们是快速了解的入口点：</span><span class="sxs-lookup"><span data-stu-id="0ff88-114">They are quick entry points to understanding:</span></span>

- <span data-ttu-id="0ff88-115">攻击是什么及其工作方式。</span><span class="sxs-lookup"><span data-stu-id="0ff88-115">What the attack is and how it works.</span></span>

- <span data-ttu-id="0ff88-116">IOC (泄露) ，用于查找和如何查找它们。</span><span class="sxs-lookup"><span data-stu-id="0ff88-116">What signs, called indicators of compromise (IOC), to look for and how to look for them.</span></span>

- <span data-ttu-id="0ff88-117">如何主动确认攻击。</span><span class="sxs-lookup"><span data-stu-id="0ff88-117">How to positively confirm the attack.</span></span>

- <span data-ttu-id="0ff88-118">今后为减少攻击和更好地保护组织而采取的步骤。</span><span class="sxs-lookup"><span data-stu-id="0ff88-118">Steps to take to cut off the attack and better protect your organization in the future.</span></span>

- <span data-ttu-id="0ff88-119">指向有关每种攻击类型的深入信息的链接。</span><span class="sxs-lookup"><span data-stu-id="0ff88-119">Links to in-depth information on each attack type.</span></span>

<span data-ttu-id="0ff88-120">每月在此处查看一次，因为随着时间的推移将添加更多文章。</span><span class="sxs-lookup"><span data-stu-id="0ff88-120">Check back here monthly as more articles will be added over time.</span></span>

## <a name="detect-and-remediate-articles"></a><span data-ttu-id="0ff88-121">检测和修正文章</span><span class="sxs-lookup"><span data-stu-id="0ff88-121">Detect and remediate articles</span></span>

- [<span data-ttu-id="0ff88-122">检测和修正 Office 365 中的非法授权</span><span class="sxs-lookup"><span data-stu-id="0ff88-122">Detect and Remediate Illicit Consent Grants in Office 365</span></span>](detect-and-remediate-illicit-consent-grants.md)

- [<span data-ttu-id="0ff88-123">在 Office 365 中检测并修正 Outlook 规则和自定义窗体注入攻击</span><span class="sxs-lookup"><span data-stu-id="0ff88-123">Detect and Remediate Outlook Rules and Custom Forms Injections Attacks in Office 365</span></span>](detect-and-remediate-outlook-rules-forms-attack.md)

## <a name="incident-response-articles"></a><span data-ttu-id="0ff88-124">事件响应文章</span><span class="sxs-lookup"><span data-stu-id="0ff88-124">Incident response articles</span></span>

- [<span data-ttu-id="0ff88-125">响应 Office 365 中遭到入侵的电子邮件帐户</span><span class="sxs-lookup"><span data-stu-id="0ff88-125">Responding to a Compromised Email Account in Office 365</span></span>](responding-to-a-compromised-email-account.md)

## <a name="secure-microsoft-365-like-a-cybersecurity-pro"></a><span data-ttu-id="0ff88-126">像网络安全专家那样保护 Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="0ff88-126">Secure Microsoft 365 like a cybersecurity pro</span></span>

<span data-ttu-id="0ff88-127">你的 Microsoft 365 订阅附带了一组强大的安全功能，可用于保护你的数据和用户。</span><span class="sxs-lookup"><span data-stu-id="0ff88-127">Your Microsoft 365 subscription comes with a powerful set of security capabilities that you can use to protect your data and your users.</span></span>  <span data-ttu-id="0ff88-128">使用 Microsoft 365 安全路线图 - 前 [30 天、90](security-roadmap.md) 天及之后的主要优先级，实施 Microsoft 建议的最佳方案来保护 Microsoft 365 组织。</span><span class="sxs-lookup"><span data-stu-id="0ff88-128">Use the [Microsoft 365 security roadmap - Top priorities for the first 30 days, 90 days, and beyond](security-roadmap.md) to implement Microsoft recommended best practices for securing your Microsoft 365 organization.</span></span>

- <span data-ttu-id="0ff88-129">需要在前 30 天完成的任务。</span><span class="sxs-lookup"><span data-stu-id="0ff88-129">Tasks to accomplish in the first 30 days.</span></span>  <span data-ttu-id="0ff88-130">这些任务会对你的用户产生直接影响并且影响很小。</span><span class="sxs-lookup"><span data-stu-id="0ff88-130">These have immediate affect and are low-impact to your users.</span></span>

- <span data-ttu-id="0ff88-131">需要在 90 天内完成的任务。</span><span class="sxs-lookup"><span data-stu-id="0ff88-131">Tasks to accomplish in 90 days.</span></span> <span data-ttu-id="0ff88-132">它们需要多花一点时间来计划和实现，但会大大改善你的安全状况</span><span class="sxs-lookup"><span data-stu-id="0ff88-132">These take a bit more time to plan and implement but greatly improve your security posture</span></span>

- <span data-ttu-id="0ff88-133">90 天后。</span><span class="sxs-lookup"><span data-stu-id="0ff88-133">Beyond 90 days.</span></span> <span data-ttu-id="0ff88-134">这些增强功能基于前 90 天的工作构建。</span><span class="sxs-lookup"><span data-stu-id="0ff88-134">These enhancements build in your first 90 days work.</span></span>
