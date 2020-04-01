---
title: " 与 Microsoft 365 服务和应用程序的安全信息和事件管理（SIEM）服务器集成"
f1.keywords:
- NOCSH
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/18/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 获取与 Microsoft 365 云服务和应用程序的安全信息和事件管理（SIEM）服务器集成的概述
ms.openlocfilehash: a4ef144d02ebf0481481861c3dfa60a43b4f3ace
ms.sourcegitcommit: a7b2cd892cb65a61ee246268e1af2f8b9e526f6b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2020
ms.locfileid: "43081216"
---
# <a name="security-information-and-event-management-siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="09201-103">与 Microsoft 365 服务和应用程序的安全信息和事件管理（SIEM）服务器集成</span><span class="sxs-lookup"><span data-stu-id="09201-103">Security Information and Event Management (SIEM) server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="09201-104">总结</span><span class="sxs-lookup"><span data-stu-id="09201-104">Summary</span></span>

<span data-ttu-id="09201-105">您的组织是使用还是计划获取安全信息和事件管理（SIEM）服务器？</span><span class="sxs-lookup"><span data-stu-id="09201-105">Is your organization using or planning to get a Security Information and Event Management (SIEM) server?</span></span> <span data-ttu-id="09201-106">您可能想知道它是如何与 Microsoft 365 或 Office 365 集成的。</span><span class="sxs-lookup"><span data-stu-id="09201-106">You might be wondering how it integrates with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="09201-107">本文提供了可用于将 SIEM 服务器与 Microsoft 365 服务和应用程序相集成的资源的列表。</span><span class="sxs-lookup"><span data-stu-id="09201-107">This article provides a list of resources you can use to integrate your SIEM server with Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="09201-108">如果你还没有 SIEM 服务器并且正在浏览你的选项，请考虑使用**[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**。</span><span class="sxs-lookup"><span data-stu-id="09201-108">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="09201-109">我是否需要 SIEM 服务器？</span><span class="sxs-lookup"><span data-stu-id="09201-109">Do I need a SIEM server?</span></span>

<span data-ttu-id="09201-110">您是否需要 SIEM 服务器取决于多个因素，例如组织的安全要求和数据所在的位置。</span><span class="sxs-lookup"><span data-stu-id="09201-110">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="09201-111">Microsoft 365 包括各种安全功能，这些功能可满足许多组织的安全需要，而无需其他服务器（如 SIEM 服务器）。</span><span class="sxs-lookup"><span data-stu-id="09201-111">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="09201-112">某些组织具有需要使用 SIEM 服务器的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="09201-112">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="09201-113">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="09201-113">Here are some examples:</span></span>

- <span data-ttu-id="09201-114">*Fabrikam*在本地有一些内容和应用程序，而有些在云中（它们具有混合云部署）。</span><span class="sxs-lookup"><span data-stu-id="09201-114">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="09201-115">若要在其所有内容和应用程序中获取安全报告，Fabrikam 已实现 SIEM 服务器。</span><span class="sxs-lookup"><span data-stu-id="09201-115">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span>

- <span data-ttu-id="09201-116">*Contoso*是一种具有特别严格的安全要求的金融服务组织。</span><span class="sxs-lookup"><span data-stu-id="09201-116">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="09201-117">他们已将 SIEM 服务器添加到其环境中，以充分利用他们所需的额外安全保护。</span><span class="sxs-lookup"><span data-stu-id="09201-117">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="09201-118">SIEM server 与 Microsoft 365 的集成</span><span class="sxs-lookup"><span data-stu-id="09201-118">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="09201-119">SIEM 服务器可以接收来自各种 Microsoft 365 服务和应用程序的数据。</span><span class="sxs-lookup"><span data-stu-id="09201-119">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="09201-120">下表列出了几个 Microsoft 365 服务和应用程序，以及 SIEM 服务器输入和资源，以了解详细信息。</span><span class="sxs-lookup"><span data-stu-id="09201-120">The following table lists several Microsoft 365 services and applications, along with SIEM server inputs and resources to learn more.</span></span>

||||
|---|---|---|
|<span data-ttu-id="09201-121">**Microsoft 365 服务或应用程序**</span><span class="sxs-lookup"><span data-stu-id="09201-121">**Microsoft 365 Service or Application**</span></span>|<span data-ttu-id="09201-122">**SIEM 服务器输入/方法**</span><span class="sxs-lookup"><span data-stu-id="09201-122">**SIEM server inputs/methods**</span></span>|<span data-ttu-id="09201-123">**了解详细信息的资源**</span><span class="sxs-lookup"><span data-stu-id="09201-123">**Resources to learn more**</span></span>|
|[<span data-ttu-id="09201-124">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="09201-124">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)|<span data-ttu-id="09201-125">审核日志</span><span class="sxs-lookup"><span data-stu-id="09201-125">Audit logs</span></span>|[<span data-ttu-id="09201-126">SIEM 与 Office 365 高级威胁防护的集成</span><span class="sxs-lookup"><span data-stu-id="09201-126">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md)|
|[<span data-ttu-id="09201-127">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="09201-127">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/)|<span data-ttu-id="09201-128">Azure 中托管的 HTTPS 终结点</span><span class="sxs-lookup"><span data-stu-id="09201-128">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="09201-129">REST API</span><span class="sxs-lookup"><span data-stu-id="09201-129">REST API</span></span>|[<span data-ttu-id="09201-130">将警报拉入 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="09201-130">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem)|
|[<span data-ttu-id="09201-131">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="09201-131">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)|<span data-ttu-id="09201-132">日志集成</span><span class="sxs-lookup"><span data-stu-id="09201-132">Log integration</span></span>|[<span data-ttu-id="09201-133">SIEM 与 Microsoft Cloud App Security 的集成</span><span class="sxs-lookup"><span data-stu-id="09201-133">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem)|
|

> [!TIP]
> <span data-ttu-id="09201-134">请看一下[Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)。</span><span class="sxs-lookup"><span data-stu-id="09201-134">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview).</span></span> <span data-ttu-id="09201-135">Azure Sentinel 附带有 Microsoft 解决方案连接器。</span><span class="sxs-lookup"><span data-stu-id="09201-135">Azure Sentinel comes with connectors for Microsoft solutions.</span></span> <span data-ttu-id="09201-136">这些连接器可用于 "开箱即用" 并提供实时集成。</span><span class="sxs-lookup"><span data-stu-id="09201-136">These connectors are available "out of the box" and provide for real-time integration.</span></span> <span data-ttu-id="09201-137">您可以将 Azure Sentinel 与 Microsoft 威胁防护解决方案和 Microsoft 365 服务（包括 Office 365、Azure AD、Azure ATP、Microsoft 云应用安全性等）结合使用。</span><span class="sxs-lookup"><span data-stu-id="09201-137">You can use Azure Sentinel with your Microsoft Threat Protection solutions and Microsoft 365 services, including Office 365, Azure AD, Azure ATP, Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="09201-138">必须打开审核日志记录</span><span class="sxs-lookup"><span data-stu-id="09201-138">Audit logging must be turned on</span></span>

<span data-ttu-id="09201-139">在配置 SIEM server 集成之前，请确保已启用审核日志记录。</span><span class="sxs-lookup"><span data-stu-id="09201-139">Make sure that audit logging is turned on before you configure SIEM server integration.</span></span>

- <span data-ttu-id="09201-140">对于 SharePoint Online、OneDrive for business 和 Azure Active Directory，[审核日志记录在安全 & 合规性中心中打开](../../compliance/turn-audit-log-search-on-or-off.md)。</span><span class="sxs-lookup"><span data-stu-id="09201-140">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](../../compliance/turn-audit-log-search-on-or-off.md).</span></span>

- <span data-ttu-id="09201-141">有关 Exchange Online，请参阅[管理邮箱审核](../../compliance/enable-mailbox-auditing.md)。</span><span class="sxs-lookup"><span data-stu-id="09201-141">For Exchange Online, see [Manage mailbox auditing](../../compliance/enable-mailbox-auditing.md).</span></span>

## <a name="more-resources"></a><span data-ttu-id="09201-142">更多资源</span><span class="sxs-lookup"><span data-stu-id="09201-142">More resources</span></span>

[<span data-ttu-id="09201-143">在 Azure 安全中心集成安全解决方案</span><span class="sxs-lookup"><span data-stu-id="09201-143">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="09201-144">将 Microsoft Graph 安全性 API 警报与 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="09201-144">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)
