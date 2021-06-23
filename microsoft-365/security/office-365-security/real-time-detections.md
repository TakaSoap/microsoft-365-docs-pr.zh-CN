---
title: Microsoft Defender for Office 365 中的威胁资源管理器和实时Office 365
f1.keywords:
- NOCSH
ms.author: dansimp
author: MSFTTracyp
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 05/05/2021
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 使用资源管理器或实时检测高效调查和响应威胁。
ms.custom: seo-marvel-apr2020
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 4d0a9ba7ee40c8ad97df745a20d6b5b3314bb3d8
ms.sourcegitcommit: cd55fe6abe25b1e4f5fbe8295d3a99aebd97ce66
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/23/2021
ms.locfileid: "53083184"
---
# <a name="explorer-and-real-time-detections-basics"></a><span data-ttu-id="ecda3-103">资源管理器和实时检测基础知识</span><span class="sxs-lookup"><span data-stu-id="ecda3-103">Explorer and Real-time detections basics</span></span>

<span data-ttu-id="ecda3-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="ecda3-104">**Applies to**</span></span>
- [<span data-ttu-id="ecda3-105">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="ecda3-105">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="ecda3-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="ecda3-106">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="ecda3-107">本文内容：</span><span class="sxs-lookup"><span data-stu-id="ecda3-107">In this article:</span></span>

- [<span data-ttu-id="ecda3-108">资源管理器和实时检测之间的差异</span><span class="sxs-lookup"><span data-stu-id="ecda3-108">Differences between Explorer and Real-time detections</span></span>](#differences-between-explorer-and-real-time-detections)
- [<span data-ttu-id="ecda3-109">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="ecda3-109">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="ecda3-110">这是 **资源管理器 (（** 也称为威胁资源管理器) 、电子邮件安全性、资源管理器和实时检测）的 **3** 篇文章系列文章的一部分 (如工具之间的差异以及运行) 所需的权限。</span><span class="sxs-lookup"><span data-stu-id="ecda3-110">This is part of a **3-article series** on **Explorer (also known as Threat Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="ecda3-111">本系列中的其他两篇文章 [是资源管理器中](threat-hunting-in-threat-explorer.md) 的威胁搜寻和资源管理器 [中的电子邮件安全](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="ecda3-111">The other two articles in this series are [Threat hunting in Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="ecda3-112">本文介绍了资源管理器和实时检测报告以及所需的许可证和权限的区别。</span><span class="sxs-lookup"><span data-stu-id="ecda3-112">This article explains the difference between Explorer and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="ecda3-113">如果你的组织拥有适用于 Office 365 的 Microsoft [Defender，](defender-for-office-365.md)并且你 [](#required-licenses-and-permissions)拥有权限，可以使用资源管理器 **(** 也称为威胁资源管理器 **)** 或实时检测来检测和修正威胁。</span><span class="sxs-lookup"><span data-stu-id="ecda3-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Explorer** (also known as **Threat Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="ecda3-114">在Microsoft 365 Defender门户 <https://security.microsoft.com> () ，转到"电子邮件 **&协作**"，然后选择"**资源管理器**"或 **"实时检测"。**</span><span class="sxs-lookup"><span data-stu-id="ecda3-114">In the Microsoft 365 Defender portal (<https://security.microsoft.com>), go to **Email & collaboration**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<span data-ttu-id="ecda3-115">使用这些工具，你可以：</span><span class="sxs-lookup"><span data-stu-id="ecda3-115">With these tools, you can:</span></span>

- <span data-ttu-id="ecda3-116">查看由安全Microsoft 365检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="ecda3-116">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="ecda3-117">查看网络钓鱼 URL 并单击裁定数据。</span><span class="sxs-lookup"><span data-stu-id="ecda3-117">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="ecda3-118">从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="ecda3-118">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="ecda3-119">调查恶意电子邮件等。</span><span class="sxs-lookup"><span data-stu-id="ecda3-119">Investigate malicious email, and more.</span></span>

<span data-ttu-id="ecda3-120">有关详细信息，请参阅使用 [资源管理器的电子邮件安全性](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="ecda3-120">For more information, see [Email security with Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-explorer-and-real-time-detections"></a><span data-ttu-id="ecda3-121">资源管理器和实时检测之间的差异</span><span class="sxs-lookup"><span data-stu-id="ecda3-121">Differences between Explorer and Real-time detections</span></span>

- <span data-ttu-id="ecda3-122">*实时检测是* Defender for Office 365计划 1 中可用的报告工具。</span><span class="sxs-lookup"><span data-stu-id="ecda3-122">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="ecda3-123">*威胁资源管理器* 是一款威胁搜寻和修正工具，适用于 Office 365 计划 2。</span><span class="sxs-lookup"><span data-stu-id="ecda3-123">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="ecda3-124">实时检测报告允许你实时查看检测。</span><span class="sxs-lookup"><span data-stu-id="ecda3-124">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="ecda3-125">威胁资源管理器也这样做，但它提供给定攻击的其他详细信息（如突出显示攻击活动）并赋予安全运营团队修正威胁 (包括触发自动调查和响应[调查) 。](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="ecda3-125">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="ecda3-126">" *所有* 电子邮件"视图在威胁资源管理器中可用，但不包括在实时检测报告中。</span><span class="sxs-lookup"><span data-stu-id="ecda3-126">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="ecda3-127">威胁资源管理器中包含丰富的筛选功能和修正操作。</span><span class="sxs-lookup"><span data-stu-id="ecda3-127">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="ecda3-128">有关详细信息，请参阅[Microsoft Defender for Office 365 服务说明：跨 Defender for Office 365 计划的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="ecda3-128">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="ecda3-129">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="ecda3-129">Required licenses and permissions</span></span>

<span data-ttu-id="ecda3-130">你必须拥有[Microsoft Defender Office 365](defender-for-office-365.md)使用资源管理器或实时检测：</span><span class="sxs-lookup"><span data-stu-id="ecda3-130">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="ecda3-131">资源管理器仅包含在计划 2 Office 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="ecda3-131">Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="ecda3-132">实时检测报告包含在计划 1 的 Defender Office 365中。</span><span class="sxs-lookup"><span data-stu-id="ecda3-132">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="ecda3-133">安全运营团队需要为应受 Office 365 Defender 保护的所有用户分配许可证，并注意资源管理器和实时检测会显示许可用户的检测数据。</span><span class="sxs-lookup"><span data-stu-id="ecda3-133">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="ecda3-134">若要查看和使用资源管理器 *或* 实时检测，需要以下权限：</span><span class="sxs-lookup"><span data-stu-id="ecda3-134">To view and use Explorer *or* Real-time detections, you need the following permissions:</span></span>

- <span data-ttu-id="ecda3-135">在 Defender for Office 365：</span><span class="sxs-lookup"><span data-stu-id="ecda3-135">In Defender for Office 365:</span></span>
  - <span data-ttu-id="ecda3-136">组织管理</span><span class="sxs-lookup"><span data-stu-id="ecda3-136">Organization Management</span></span>
  - <span data-ttu-id="ecda3-137">安全 (可以在管理中心Azure Active Directory分配 <https://aad.portal.azure.com> () </span><span class="sxs-lookup"><span data-stu-id="ecda3-137">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="ecda3-138">安全读取者</span><span class="sxs-lookup"><span data-stu-id="ecda3-138">Security Reader</span></span>
- <span data-ttu-id="ecda3-139">在Exchange Online：</span><span class="sxs-lookup"><span data-stu-id="ecda3-139">In Exchange Online:</span></span>
  - <span data-ttu-id="ecda3-140">组织管理</span><span class="sxs-lookup"><span data-stu-id="ecda3-140">Organization Management</span></span>
  - <span data-ttu-id="ecda3-141">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="ecda3-141">View-Only Organization Management</span></span>
  - <span data-ttu-id="ecda3-142">仅查看收件人</span><span class="sxs-lookup"><span data-stu-id="ecda3-142">View-Only Recipients</span></span>
  - <span data-ttu-id="ecda3-143">合规性管理</span><span class="sxs-lookup"><span data-stu-id="ecda3-143">Compliance Management</span></span>

<span data-ttu-id="ecda3-144">若要详细了解角色和权限，请参阅以下文章：</span><span class="sxs-lookup"><span data-stu-id="ecda3-144">To learn more about roles and permissions, see the following articles:</span></span>

- [<span data-ttu-id="ecda3-145">Microsoft 365 Defender 门户中的权限</span><span class="sxs-lookup"><span data-stu-id="ecda3-145">Permissions in the Microsoft 365 Defender portal</span></span>](permissions-microsoft-365-security-center.md)
- [<span data-ttu-id="ecda3-146">Exchange Online 中的权限</span><span class="sxs-lookup"><span data-stu-id="ecda3-146">Permissions in Exchange Online</span></span>](/e/exchange/permissions-exo/permissions-exo)

## <a name="more-information"></a><span data-ttu-id="ecda3-147">更多信息</span><span class="sxs-lookup"><span data-stu-id="ecda3-147">More information</span></span>

- [<span data-ttu-id="ecda3-148">威胁资源管理器在电子邮件实体页面上收集电子邮件详细信息</span><span class="sxs-lookup"><span data-stu-id="ecda3-148">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="ecda3-149">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="ecda3-149">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="ecda3-150">查看在 SharePoint Online、OneDrive 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="ecda3-150">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="ecda3-151">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="ecda3-151">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="ecda3-152">Microsoft 威胁防护中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="ecda3-152">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)
