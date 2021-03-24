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
description: 大致了解 SIEM 中的安全信息和事件 (SIEM) 与 Microsoft 365 云服务和应用程序的服务器集成
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: ee164000d9a8dc9469097917658a88efe5cdc08c
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51055508"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="2a79c-103">SIEM 安全信息和事件 (SIEM) Microsoft 365 服务和应用程序的服务器集成</span><span class="sxs-lookup"><span data-stu-id="2a79c-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

<span data-ttu-id="2a79c-104">**适用对象**</span><span class="sxs-lookup"><span data-stu-id="2a79c-104">**Applies to**</span></span>
- [<span data-ttu-id="2a79c-105">Exchange Online Protection</span><span class="sxs-lookup"><span data-stu-id="2a79c-105">Exchange Online Protection</span></span>](exchange-online-protection-overview.md)
- [<span data-ttu-id="2a79c-106">Microsoft Defender for Office 365 计划 1 和计划 2</span><span class="sxs-lookup"><span data-stu-id="2a79c-106">Microsoft Defender for Office 365 plan 1 and plan 2</span></span>](defender-for-office-365.md)
- [<span data-ttu-id="2a79c-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="2a79c-107">Microsoft 365 Defender</span></span>](../defender/microsoft-365-defender.md)

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

## <a name="summary"></a><span data-ttu-id="2a79c-108">摘要</span><span class="sxs-lookup"><span data-stu-id="2a79c-108">Summary</span></span>

<span data-ttu-id="2a79c-109">你的组织是使用还是计划使用 SIEM (获取安全信息和事件) ？</span><span class="sxs-lookup"><span data-stu-id="2a79c-109">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="2a79c-110">你可能想知道它如何与 Microsoft 365 或 Office 365 集成。</span><span class="sxs-lookup"><span data-stu-id="2a79c-110">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="2a79c-111">本文提供了可用于将 SIEM 服务器与 Microsoft 365 服务和应用程序集成的资源列表。</span><span class="sxs-lookup"><span data-stu-id="2a79c-111">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="2a79c-112">如果你还没有 SIEM 服务器，并且正在探索你的选项，请考虑 Microsoft **[Azure Sentinel](/azure/sentinel/overview)**。</span><span class="sxs-lookup"><span data-stu-id="2a79c-112">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="2a79c-113">是否需要 SIEM 服务器？</span><span class="sxs-lookup"><span data-stu-id="2a79c-113">Do I need a SIEM server?</span></span>

<span data-ttu-id="2a79c-114">是否需要 SIEM 服务器取决于许多因素，例如组织的安全要求和数据所在的位置。</span><span class="sxs-lookup"><span data-stu-id="2a79c-114">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="2a79c-115">Microsoft 365 包括各种安全功能，无需其他服务器（如 SIEM 服务器）即可满足许多组织的安全需求。</span><span class="sxs-lookup"><span data-stu-id="2a79c-115">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="2a79c-116">某些组织有需要使用 SIEM 服务器的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="2a79c-116">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="2a79c-117">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="2a79c-117">Here are some examples:</span></span>

- <span data-ttu-id="2a79c-118">*Fabrikam* 在本地具有一些内容和应用程序，一些位于云 (它们具有混合云部署) 。</span><span class="sxs-lookup"><span data-stu-id="2a79c-118">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="2a79c-119">为了跨所有内容和应用程序获取安全报告，Fabrikam 实施了 SIEM 服务器。</span><span class="sxs-lookup"><span data-stu-id="2a79c-119">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="2a79c-120">*Contoso* 是一家金融服务组织，其安全要求特别严格。</span><span class="sxs-lookup"><span data-stu-id="2a79c-120">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="2a79c-121">他们向环境添加了 SIEM 服务器，以充分利用其需要的额外安全保护。</span><span class="sxs-lookup"><span data-stu-id="2a79c-121">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="2a79c-122">SIEM 服务器与 Microsoft 365 集成</span><span class="sxs-lookup"><span data-stu-id="2a79c-122">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="2a79c-123">SIEM 服务器可以从各种 Microsoft 365 服务和应用程序接收数据。</span><span class="sxs-lookup"><span data-stu-id="2a79c-123">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="2a79c-124">下表列出了多个 Microsoft 365 服务和应用程序，以及 SIEM 服务器输入和资源以了解更多信息。</span><span class="sxs-lookup"><span data-stu-id="2a79c-124">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

****

|<span data-ttu-id="2a79c-125">Microsoft 365 服务或应用程序</span><span class="sxs-lookup"><span data-stu-id="2a79c-125">Microsoft 365 Service or Application</span></span>|<span data-ttu-id="2a79c-126">SIEM 服务器输入/方法</span><span class="sxs-lookup"><span data-stu-id="2a79c-126">SIEM server inputs/methods</span></span>|<span data-ttu-id="2a79c-127">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="2a79c-127">Resources to learn more</span></span>|
|---|---|---|
|[<span data-ttu-id="2a79c-128">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="2a79c-128">Microsoft Defender for Office 365</span></span>](defender-for-office-365.md)|<span data-ttu-id="2a79c-129">审核日志</span><span class="sxs-lookup"><span data-stu-id="2a79c-129">Audit logs</span></span>|[<span data-ttu-id="2a79c-130">SIEM 与 Microsoft Defender for Office 365 集成</span><span class="sxs-lookup"><span data-stu-id="2a79c-130">SIEM integration with Microsoft Defender for Office 365</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="2a79c-131">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="2a79c-131">Microsoft Defender for Endpoint</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="2a79c-132">托管在 Azure 中的 HTTPS 终结点</span><span class="sxs-lookup"><span data-stu-id="2a79c-132">HTTPS endpoint hosted in Azure</span></span> <p> <span data-ttu-id="2a79c-133">REST API</span><span class="sxs-lookup"><span data-stu-id="2a79c-133">REST API</span></span>|[<span data-ttu-id="2a79c-134">将警报拉取到 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="2a79c-134">Pull alerts to your SIEM tools</span></span>](../defender-endpoint/configure-siem.md)|
|[<span data-ttu-id="2a79c-135">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="2a79c-135">Microsoft Cloud App Security</span></span>](/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="2a79c-136">日志集成</span><span class="sxs-lookup"><span data-stu-id="2a79c-136">Log integration</span></span>|[<span data-ttu-id="2a79c-137">SIEM 与 Microsoft Cloud App Security 集成</span><span class="sxs-lookup"><span data-stu-id="2a79c-137">SIEM integration with Microsoft Cloud App Security</span></span>](/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="2a79c-138">查看 Azure [Sentinel](/azure/sentinel/overview)。</span><span class="sxs-lookup"><span data-stu-id="2a79c-138">Take a look at [Azure Sentinel](/azure/sentinel/overview).</span></span> <span data-ttu-id="2a79c-139">Azure Sentinel 附带适用于 Microsoft 解决方案的连接器。</span><span class="sxs-lookup"><span data-stu-id="2a79c-139">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="2a79c-140">这些连接器"开箱即用"可用，可提供实时集成。</span><span class="sxs-lookup"><span data-stu-id="2a79c-140">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="2a79c-141">可以将 Azure Sentinel 与 Microsoft 365 Defender 解决方案和 Microsoft 365 服务（包括 Office 365、Azure AD、Microsoft Defender for Identity、Microsoft Cloud App Security 等）一同使用。</span><span class="sxs-lookup"><span data-stu-id="2a79c-141">You can use Azure Sentinel with your Microsoft 365 Defender solutions and Microsoft 365 services, including Office 365, Azure AD, Microsoft Defender for Identity, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="2a79c-142">审核日志记录必须打开</span><span class="sxs-lookup"><span data-stu-id="2a79c-142">Audit logging must be turned on</span></span>

<span data-ttu-id="2a79c-143">在配置 SIEM 服务器集成之前，请确保审核日志记录已打开。</span><span class="sxs-lookup"><span data-stu-id="2a79c-143">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="2a79c-144">对于 SharePoint Online、OneDrive for Business 和 Azure Active Directory，审核日志记录在安全与合规& [启用](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="2a79c-144">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="2a79c-145">对于 Exchange Online，请参阅 [管理邮箱审核](../../compliance/enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="2a79c-145">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="2a79c-146">更多资源</span><span class="sxs-lookup"><span data-stu-id="2a79c-146">More resources</span></span>

[<span data-ttu-id="2a79c-147">在 Azure Defender 中集成安全解决方案</span><span class="sxs-lookup"><span data-stu-id="2a79c-147">Integrate security solutions in Azure Defender</span></span>](/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="2a79c-148">将 Microsoft Graph 安全性 API 警报与 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="2a79c-148">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](/graph/security-integration)