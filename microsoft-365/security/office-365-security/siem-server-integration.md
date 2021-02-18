---
title: SIEM 服务器与 Microsoft 365 服务和应用程序的集成
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
- seo-marvel-apr2020
description: 大致了解 SIEM (SIEM) 与 Microsoft 365 云服务和应用程序集成的安全信息和事件管理
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: b4490d52cbd403bf4ce2cc3f3fb3c5a91c5646b9
ms.sourcegitcommit: 786f90a163d34c02b8451d09aa1efb1e1d5f543c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2021
ms.locfileid: "50290377"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="d87bb-103">SIEM (SIEM) Microsoft 365 服务和应用程序集成的安全信息和事件管理</span><span class="sxs-lookup"><span data-stu-id="d87bb-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="d87bb-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="d87bb-104">**Applies to**</span></span>
- [<span data-ttu-id="d87bb-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="d87bb-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="d87bb-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="d87bb-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](office-365-atp.md)
- [<span data-ttu-id="d87bb-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="d87bb-107">Microsoft 365 Defender</span></span>](../mtp/microsoft-threat-protection.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="d87bb-108">摘要</span><span class="sxs-lookup"><span data-stu-id="d87bb-108">Summary</span></span>

<span data-ttu-id="d87bb-109">组织是否正在使用或计划从 SIEM (获取安全信息和) 管理？</span><span class="sxs-lookup"><span data-stu-id="d87bb-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="d87bb-110">你可能想知道它如何与 Microsoft 365 或 Office 365 集成。</span><span class="sxs-lookup"><span data-stu-id="d87bb-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="d87bb-111">本文提供了可用于将 SIEM 服务器与 Microsoft 365 服务和应用程序集成的资源列表。</span><span class="sxs-lookup"><span data-stu-id="d87bb-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="d87bb-112">如果你还没有 SIEM 服务器并且正在探索你的选项，请考虑使用 Microsoft **[Azure Sentinel。](https://docs.microsoft.com/azure/sentinel/overview)**</span><span class="sxs-lookup"><span data-stu-id="d87bb-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="d87bb-113">是否需要 SIEM 服务器？</span><span class="sxs-lookup"><span data-stu-id="d87bb-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="d87bb-114">是否需要 SIEM 服务器取决于许多因素，例如组织的安全要求和数据所在的位置。</span><span class="sxs-lookup"><span data-stu-id="d87bb-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="d87bb-115">Microsoft 365 包括各种安全功能，无需其他服务器（如 SIEM 服务器）即可满足许多组织的安全需求。</span><span class="sxs-lookup"><span data-stu-id="d87bb-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="d87bb-116">某些组织具有需要使用 SIEM 服务器的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="d87bb-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="d87bb-117">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="d87bb-117">Here are some examples:</span></span>

- <span data-ttu-id="d87bb-118">*Fabrikam* 具有一些本地内容和应用程序，一些位于云 (它们具有混合云部署) 。</span><span class="sxs-lookup"><span data-stu-id="d87bb-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="d87bb-119">为了跨所有内容和应用程序获取安全报告，Fabrikam 实施了 SIEM 服务器。</span><span class="sxs-lookup"><span data-stu-id="d87bb-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="d87bb-120">*Contoso* 是一家对安全性要求特别严格的金融服务组织。</span><span class="sxs-lookup"><span data-stu-id="d87bb-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="d87bb-121">他们向环境添加了 SIEM 服务器，以利用他们需要额外的安全保护。</span><span class="sxs-lookup"><span data-stu-id="d87bb-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="d87bb-122">SIEM 服务器与 Microsoft 365 集成</span><span class="sxs-lookup"><span data-stu-id="d87bb-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="d87bb-123">SIEM 服务器可以从各种 Microsoft 365 服务和应用程序接收数据。</span><span class="sxs-lookup"><span data-stu-id="d87bb-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="d87bb-124">下表列出了多个 Microsoft 365 服务和应用程序，以及 SIEM 服务器输入和资源以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="d87bb-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="d87bb-125">Microsoft 365 服务或应用程序</span><span class="sxs-lookup"><span data-stu-id="d87bb-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="d87bb-126">SIEM 服务器输入/方法</span><span class="sxs-lookup"><span data-stu-id="d87bb-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="d87bb-127">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="d87bb-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="d87bb-128">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="d87bb-128">Microsoft Defender for Office 365</span></span>](office-365-atp.md)|<span data-ttu-id="d87bb-129">审核日志</span><span class="sxs-lookup"><span data-stu-id="d87bb-129">Audit logs</span></span>|[<span data-ttu-id="d87bb-130">SIEM 与 Microsoft Defender for Office 365 集成</span><span class="sxs-lookup"><span data-stu-id="d87bb-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="d87bb-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="d87bb-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="d87bb-132">托管在 Azure 中的 HTTPS 终结点</span><span class="sxs-lookup"><span data-stu-id="d87bb-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="d87bb-133">REST API</span><span class="sxs-lookup"><span data-stu-id="d87bb-133">REST API</span></span>|[<span data-ttu-id="d87bb-134">将警报拉取到 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="d87bb-134">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="d87bb-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="d87bb-135">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="d87bb-136">日志集成</span><span class="sxs-lookup"><span data-stu-id="d87bb-136">Log integration</span></span>|[<span data-ttu-id="d87bb-137">SIEM 与 Microsoft Cloud App Security 集成</span><span class="sxs-lookup"><span data-stu-id="d87bb-137">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="d87bb-138">查看 Azure [Sentinel](https://docs.microsoft.com/azure/sentinel/overview)。</span><span class="sxs-lookup"><span data-stu-id="d87bb-138">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="d87bb-139">Azure Sentinel 附带了 Microsoft 解决方案的连接器。</span><span class="sxs-lookup"><span data-stu-id="d87bb-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="d87bb-140">这些连接器"开箱即用"可用，可提供实时集成。</span><span class="sxs-lookup"><span data-stu-id="d87bb-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="d87bb-141">可以将 Azure Sentinel 与 Microsoft 365 Defender 解决方案和 Microsoft 365 服务（包括 Office 365、Azure AD、Microsoft Defender for Identity、Microsoft Cloud App Security 等）一同使用。</span><span class="sxs-lookup"><span data-stu-id="d87bb-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="d87bb-142">审核日志记录必须打开</span><span class="sxs-lookup"><span data-stu-id="d87bb-142">Audit logging must be turned on</span></span>

<span data-ttu-id="d87bb-143">在配置 SIEM 服务器集成之前，请确保审核日志记录已打开。</span><span class="sxs-lookup"><span data-stu-id="d87bb-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="d87bb-144">对于 SharePoint Online、OneDrive for Business 和 Azure Active Directory，审核日志记录在安全与合规中心 [&启用](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="d87bb-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="d87bb-145">对于 Exchange Online，请参阅["管理邮箱审核"。](../../compliance/enable-mailbox-auditing.md)</span><span class="sxs-lookup"><span data-stu-id="d87bb-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="d87bb-146">更多资源</span><span class="sxs-lookup"><span data-stu-id="d87bb-146">More resources</span></span>

[<span data-ttu-id="d87bb-147">在 Azure Defender 中集成安全解决方案</span><span class="sxs-lookup"><span data-stu-id="d87bb-147">Integrate security solutions in Azure Defender</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="d87bb-148">将 Microsoft Graph 安全性 API 警报与 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="d87bb-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
