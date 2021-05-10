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
ms.openlocfilehash: 7ab7b5731d121106d930868b03330d4ac7befd77
ms.sourcegitcommit: de5fce90de22ba588e75e1a1d2e87e03b9e25ec7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/10/2021
ms.locfileid: "52300106"
---
# <a name="threat-explorer-and-real-time-detections-basics"></a><span data-ttu-id="1f42b-103">威胁资源管理器和实时检测基础知识</span><span class="sxs-lookup"><span data-stu-id="1f42b-103">Threat Explorer and Real-time detections basics</span></span>

<span data-ttu-id="1f42b-104">本文内容：</span><span class="sxs-lookup"><span data-stu-id="1f42b-104">In this article:</span></span>

- [<span data-ttu-id="1f42b-105">威胁资源管理器和实时检测之间的差异</span><span class="sxs-lookup"><span data-stu-id="1f42b-105">Differences between Threat Explorer and Real-time detections</span></span>](#differences-between-threat-explorer-and-real-time-detections)<br/>
- [<span data-ttu-id="1f42b-106">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="1f42b-106">Required licenses and permissions</span></span>](#required-licenses-and-permissions)

> [!NOTE]
> <span data-ttu-id="1f42b-107">这是威胁资源管理器 (**资源管理器) 、** 电子邮件安全、资源管理器和实时检测基础知识的 **3** 篇文章系列中的一部分 **(如** 工具之间的差异以及操作它们所需的权限) 。</span><span class="sxs-lookup"><span data-stu-id="1f42b-107">This is part of a **3-article series** on **Threat Explorer (Explorer)**, **email security**, and **Explorer and Real-time detections basics** (such as differences between the tools, and permissions needed to operate them).</span></span> <span data-ttu-id="1f42b-108">本系列中的其他两篇文章是 [威胁](threat-hunting-in-threat-explorer.md) 资源管理器中的威胁搜寻和威胁 [资源管理器中的电子邮件安全](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="1f42b-108">The other two articles in this series are [Threat hunting in Threat Explorer](threat-hunting-in-threat-explorer.md) and [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

<span data-ttu-id="1f42b-109">本文介绍了威胁探索和实时检测报告，以及所需的许可证和权限的区别。</span><span class="sxs-lookup"><span data-stu-id="1f42b-109">This article explains the difference between threat exploration and real-time detections reporting, and the licenses and permissions that are required.</span></span>

<span data-ttu-id="1f42b-110">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="1f42b-110">**Applies to**</span></span>
- [<span data-ttu-id="1f42b-111">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="1f42b-111">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="1f42b-112">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="1f42b-112">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

<span data-ttu-id="1f42b-113">如果你的组织拥有适用于 Office 365 的 Microsoft [Defender，](defender-for-office-365.md)并且你拥有 [](#required-licenses-and-permissions)权限，可以使用称为资源管理器 **(** 的威胁资源管理器 **)** 或实时检测来检测和修正威胁。</span><span class="sxs-lookup"><span data-stu-id="1f42b-113">If your organization has [Microsoft Defender for Office 365](defender-for-office-365.md), and you have the [permissions](#required-licenses-and-permissions), you can use **Threat Explorer** (called **Explorer**) or **Real-time detections** to detect and remediate threats.</span></span>

<span data-ttu-id="1f42b-114">在安全 **&中心**，转到"**威胁** 管理"，**然后选择资源管理器**_或_**实时检测**。</span><span class="sxs-lookup"><span data-stu-id="1f42b-114">In the **Security & Compliance Center**, go to **Threat management**, and then choose **Explorer** _or_ **Real-time detections**.</span></span>

<br>

****

|<span data-ttu-id="1f42b-115">借助 Microsoft Defender for Office 365计划 2，你将看到：</span><span class="sxs-lookup"><span data-stu-id="1f42b-115">With Microsoft Defender for Office 365 Plan 2, you see:</span></span>|<span data-ttu-id="1f42b-116">借助 Microsoft Defender for Office 365 计划 1，可以看到：</span><span class="sxs-lookup"><span data-stu-id="1f42b-116">With Microsoft Defender for Office 365 Plan 1, you see:</span></span>|
|---|---|
|![威胁资源管理器](../../media/threatmgmt-explorer.png)|![实时检测](../../media/threatmgmt-realtimedetections.png)|
|

<span data-ttu-id="1f42b-119">使用这些工具，你可以：</span><span class="sxs-lookup"><span data-stu-id="1f42b-119">With these tools, you can:</span></span>

- <span data-ttu-id="1f42b-120">查看由安全Microsoft 365检测到的恶意软件。</span><span class="sxs-lookup"><span data-stu-id="1f42b-120">See malware detected by Microsoft 365 security features.</span></span>
- <span data-ttu-id="1f42b-121">查看网络钓鱼 URL 并单击裁定数据。</span><span class="sxs-lookup"><span data-stu-id="1f42b-121">View phishing URL and click verdict data.</span></span>
- <span data-ttu-id="1f42b-122">从资源管理器中的视图启动自动调查和响应过程。</span><span class="sxs-lookup"><span data-stu-id="1f42b-122">Start an automated investigation and response process from a view in Explorer.</span></span>
- <span data-ttu-id="1f42b-123">调查恶意电子邮件等。</span><span class="sxs-lookup"><span data-stu-id="1f42b-123">Investigate malicious email, and more.</span></span>

<span data-ttu-id="1f42b-124">有关详细信息，请参阅使用威胁 [资源管理器的电子邮件安全性](email-security-in-microsoft-defender.md)。</span><span class="sxs-lookup"><span data-stu-id="1f42b-124">For more information, see [Email security with Threat Explorer](email-security-in-microsoft-defender.md).</span></span>

## <a name="differences-between-threat-explorer-and-real-time-detections"></a><span data-ttu-id="1f42b-125">威胁资源管理器和实时检测之间的差异</span><span class="sxs-lookup"><span data-stu-id="1f42b-125">Differences between Threat Explorer and Real-time detections</span></span>

- <span data-ttu-id="1f42b-126">*实时检测是* Defender for Office 365计划 1 中可用的报告工具。</span><span class="sxs-lookup"><span data-stu-id="1f42b-126">*Real-time detections* is a reporting tool available in Defender for Office 365 Plan 1.</span></span> <span data-ttu-id="1f42b-127">*威胁资源管理器* 是一款威胁搜寻和修正工具，适用于 Office 365 计划 2。</span><span class="sxs-lookup"><span data-stu-id="1f42b-127">*Threat Explorer* is a threat hunting and remediation tool available in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="1f42b-128">实时检测报告允许你实时查看检测。</span><span class="sxs-lookup"><span data-stu-id="1f42b-128">The Real-time detections report allows you to view detections in real time.</span></span> <span data-ttu-id="1f42b-129">威胁资源管理器也这样做，但它提供给定攻击的其他详细信息（如突出显示攻击活动）并赋予安全运营团队修正威胁 (包括触发自动调查和响应[调查) 。](automated-investigation-response-office.md)</span><span class="sxs-lookup"><span data-stu-id="1f42b-129">Threat Explorer does this as well, but it provides additional details for a given attack, such as highlighting attack campaigns, and gives security operations teams the ability to remediate threats (including triggering an [Automated Investigation and Response investigation](automated-investigation-response-office.md)).</span></span>
- <span data-ttu-id="1f42b-130">" *所有* 电子邮件"视图在威胁资源管理器中可用，但不包括在实时检测报告中。</span><span class="sxs-lookup"><span data-stu-id="1f42b-130">An *All email* view is available in Threat Explorer, but not included in the Real-time detections report.</span></span>
- <span data-ttu-id="1f42b-131">威胁资源管理器中包含丰富的筛选功能和修正操作。</span><span class="sxs-lookup"><span data-stu-id="1f42b-131">Rich filtering capabilities and remediation actions are included in Threat Explorer.</span></span> <span data-ttu-id="1f42b-132">有关详细信息，请参阅[Microsoft Defender for Office 365 服务说明：跨 Defender for Office 365 计划的功能可用性](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans)。</span><span class="sxs-lookup"><span data-stu-id="1f42b-132">For more information, see [Microsoft Defender for Office 365 Service Description: Feature availability across Defender for Office 365 plans](/office365/servicedescriptions/office-365-advanced-threat-protection-service-description#feature-availability-across-advanced-threat-protection-atp-plans).</span></span>

## <a name="required-licenses-and-permissions"></a><span data-ttu-id="1f42b-133">所需的许可证和权限</span><span class="sxs-lookup"><span data-stu-id="1f42b-133">Required licenses and permissions</span></span>

<span data-ttu-id="1f42b-134">你必须拥有[Microsoft Defender Office 365](defender-for-office-365.md)使用资源管理器或实时检测：</span><span class="sxs-lookup"><span data-stu-id="1f42b-134">You must have [Microsoft Defender for Office 365](defender-for-office-365.md) to use either of Explorer or Real-time detections:</span></span>

- <span data-ttu-id="1f42b-135">但资源管理器仅包含在计划 2 Office 365 Defender 中。</span><span class="sxs-lookup"><span data-stu-id="1f42b-135">But Explorer is only included in Defender for Office 365 Plan 2.</span></span>
- <span data-ttu-id="1f42b-136">实时检测报告包含在计划 1 的 Defender Office 365中。</span><span class="sxs-lookup"><span data-stu-id="1f42b-136">The Real-time detections report is included in Defender for Office 365 Plan 1.</span></span>

<span data-ttu-id="1f42b-137">安全运营团队需要为应受 Office 365 Defender 保护的所有用户分配许可证，并注意资源管理器和实时检测会显示许可用户的检测数据。</span><span class="sxs-lookup"><span data-stu-id="1f42b-137">Security Operations teams need to assign licenses for all users who should be protected by Defender for Office 365 and be aware that Explorer and Real-time detections show detection data for licensed users.</span></span>

<span data-ttu-id="1f42b-138">若要查看和使用资源管理器 *或* 实时检测，必须具有以下项：</span><span class="sxs-lookup"><span data-stu-id="1f42b-138">To view and use Explorer *or* Real-time detections, you must have the following:</span></span>

- <span data-ttu-id="1f42b-139">对于安全与&中心：</span><span class="sxs-lookup"><span data-stu-id="1f42b-139">For the Security & Compliance Center:</span></span>

  - <span data-ttu-id="1f42b-140">组织管理</span><span class="sxs-lookup"><span data-stu-id="1f42b-140">Organization Management</span></span>
  - <span data-ttu-id="1f42b-141">安全 (可以在管理中心Azure Active Directory分配 <https://aad.portal.azure.com> () </span><span class="sxs-lookup"><span data-stu-id="1f42b-141">Security Administrator (this can be assigned in the Azure Active Directory admin center (<https://aad.portal.azure.com>)</span></span>
  - <span data-ttu-id="1f42b-142">安全读取者</span><span class="sxs-lookup"><span data-stu-id="1f42b-142">Security Reader</span></span>

- <span data-ttu-id="1f42b-143">例如Exchange Online：</span><span class="sxs-lookup"><span data-stu-id="1f42b-143">For Exchange Online:</span></span>

  - <span data-ttu-id="1f42b-144">组织管理</span><span class="sxs-lookup"><span data-stu-id="1f42b-144">Organization Management</span></span>
  - <span data-ttu-id="1f42b-145">仅查看组织管理</span><span class="sxs-lookup"><span data-stu-id="1f42b-145">View-Only Organization Management</span></span>
  - <span data-ttu-id="1f42b-146">仅查看收件人</span><span class="sxs-lookup"><span data-stu-id="1f42b-146">View-Only Recipients</span></span>
  - <span data-ttu-id="1f42b-147">合规性管理</span><span class="sxs-lookup"><span data-stu-id="1f42b-147">Compliance Management</span></span>

<span data-ttu-id="1f42b-148">若要详细了解角色和权限，请参阅以下资源：</span><span class="sxs-lookup"><span data-stu-id="1f42b-148">To learn more about roles and permissions, see the following resources:</span></span>

- [<span data-ttu-id="1f42b-149">安全与合规中心内的权限</span><span class="sxs-lookup"><span data-stu-id="1f42b-149">Permissions in the Security & Compliance Center</span></span>](permissions-in-the-security-and-compliance-center.md)
- [<span data-ttu-id="1f42b-150">Exchange Online 中的功能权限</span><span class="sxs-lookup"><span data-stu-id="1f42b-150">Feature permissions in Exchange Online</span></span>](/exchange/permissions-exo/feature-permissions)
- [<span data-ttu-id="1f42b-151">Exchange Online PowerShell</span><span class="sxs-lookup"><span data-stu-id="1f42b-151">Exchange Online PowerShell</span></span>](/powershell/exchange/exchange-online-powershell)

## <a name="more-information"></a><span data-ttu-id="1f42b-152">更多信息</span><span class="sxs-lookup"><span data-stu-id="1f42b-152">More information</span></span>
- [<span data-ttu-id="1f42b-153">威胁资源管理器在电子邮件实体页面上收集电子邮件详细信息</span><span class="sxs-lookup"><span data-stu-id="1f42b-153">Threat Explorer collect email details on the email entity page</span></span>](mdo-email-entity-page.md)
- [<span data-ttu-id="1f42b-154">查找和调查投递的恶意电子邮件</span><span class="sxs-lookup"><span data-stu-id="1f42b-154">Find and investigate malicious email that was delivered</span></span>](investigate-malicious-email-that-was-delivered.md)
- [<span data-ttu-id="1f42b-155">查看在 SharePoint Online、OneDrive 和 Microsoft Teams</span><span class="sxs-lookup"><span data-stu-id="1f42b-155">View malicious files detected in SharePoint Online, OneDrive, and Microsoft Teams</span></span>](mdo-for-spo-odb-and-teams.md)
- [<span data-ttu-id="1f42b-156">威胁防护状态报告</span><span class="sxs-lookup"><span data-stu-id="1f42b-156">Threat protection status report</span></span>](view-email-security-reports.md#threat-protection-status-report)
- [<span data-ttu-id="1f42b-157">Microsoft 威胁防护中的自动调查和响应</span><span class="sxs-lookup"><span data-stu-id="1f42b-157">Automated investigation and response in Microsoft Threat Protection</span></span>](automated-investigation-response-office.md)