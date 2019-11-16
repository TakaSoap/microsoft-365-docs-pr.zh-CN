---
title: SIEM server 与 Microsoft 365 服务和应用程序的集成
ms.author: deniseb
author: denisebmsft
manager: dansimp
audience: ITPro
ms.topic: article
ms.date: 11/15/2019
ms.service: O365-seccomp
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.custom:
- Ent_Solutions
- SIEM
description: 阅读本文，了解 SIEM server 与 Microsoft 365 集成的概述。
ms.openlocfilehash: bea6141022fef1275a7e291217f698f52613f170
ms.sourcegitcommit: d8d001c03c28c10bea005d1c9b5f4a8f393af706
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/16/2019
ms.locfileid: "38677505"
---
# <a name="siem-server-integration-with-microsoft-365-services-and-applications"></a><span data-ttu-id="f9441-103">SIEM server 与 Microsoft 365 服务和应用程序的集成</span><span class="sxs-lookup"><span data-stu-id="f9441-103">SIEM server integration with Microsoft 365 services and applications</span></span>

## <a name="summary"></a><span data-ttu-id="f9441-104">Summary</span><span class="sxs-lookup"><span data-stu-id="f9441-104">Summary</span></span>

<span data-ttu-id="f9441-105">如果您的组织使用的是安全信息和事件管理（SIEM）服务器，或者您打算马上获取 SIEM 服务器，那么您可能会想知道如何将与 Microsoft 365 或 Office 365 集成。</span><span class="sxs-lookup"><span data-stu-id="f9441-105">If your organization is using a Security Information and Event Management (SIEM) server, or if you are planning to get a SIEM server soon, you might be wondering how that'll integrate with Microsoft 365 or Office 365.</span></span> <span data-ttu-id="f9441-106">本文提供了可用于设置 SIEM server 与 Microsoft 365 服务和应用程序集成的资源的列表。</span><span class="sxs-lookup"><span data-stu-id="f9441-106">This article provides a list of resources you can use to set up SIEM server integration with your Microsoft 365 services and applications.</span></span>

> [!TIP]
> <span data-ttu-id="f9441-107">如果你还没有 SIEM 服务器并且正在浏览你的选项，请考虑使用**[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**。</span><span class="sxs-lookup"><span data-stu-id="f9441-107">If you don't have a SIEM server yet and are exploring your options, consider **[Microsoft Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)**.</span></span>

## <a name="do-i-need-a-siem-server"></a><span data-ttu-id="f9441-108">我是否需要 SIEM 服务器？</span><span class="sxs-lookup"><span data-stu-id="f9441-108">Do I need a SIEM server?</span></span>

<span data-ttu-id="f9441-109">您是否需要 SIEM 服务器取决于多个因素，例如组织的安全要求和数据所在的位置。</span><span class="sxs-lookup"><span data-stu-id="f9441-109">Whether you need a SIEM server depends on many factors, such as your organization's security requirements and where your data resides.</span></span> <span data-ttu-id="f9441-110">Microsoft 365 包括各种安全功能，这些功能可满足许多组织的安全需要，而无需其他服务器（如 SIEM 服务器）。</span><span class="sxs-lookup"><span data-stu-id="f9441-110">Microsoft 365 includes a wide variety of security features that meet many organizations' security needs without additional servers, such as a SIEM server.</span></span> <span data-ttu-id="f9441-111">某些组织具有需要使用 SIEM 服务器的特殊情况。</span><span class="sxs-lookup"><span data-stu-id="f9441-111">Some organizations have special circumstances that require the use of a SIEM server.</span></span> <span data-ttu-id="f9441-112">下面是一些示例：</span><span class="sxs-lookup"><span data-stu-id="f9441-112">Here are some examples:</span></span>

- <span data-ttu-id="f9441-113">*Fabrikam*在本地有一些内容和应用程序，而有些在云中（它们具有混合云部署）。</span><span class="sxs-lookup"><span data-stu-id="f9441-113">*Fabrikam* has some content and applications on premises, and some in the cloud (they have a hybrid cloud deployment).</span></span> <span data-ttu-id="f9441-114">若要在其所有内容和应用程序中获取安全报告，Fabrikam 已实现 SIEM 服务器。</span><span class="sxs-lookup"><span data-stu-id="f9441-114">To get security reports across all their content and applications, Fabrikam has implemented a SIEM server.</span></span> 

- <span data-ttu-id="f9441-115">*Contoso*是一种具有特别严格的安全要求的金融服务组织。</span><span class="sxs-lookup"><span data-stu-id="f9441-115">*Contoso* is a financial services organization that has particularly stringent security requirements.</span></span> <span data-ttu-id="f9441-116">他们已将 SIEM 服务器添加到其环境中，以充分利用他们所需的额外安全保护。</span><span class="sxs-lookup"><span data-stu-id="f9441-116">They have added a SIEM server to their environment to take advantage of the extra security protection they require.</span></span>

## <a name="siem-server-integration-with-microsoft-365"></a><span data-ttu-id="f9441-117">SIEM server 与 Microsoft 365 的集成</span><span class="sxs-lookup"><span data-stu-id="f9441-117">SIEM server integration with Microsoft 365</span></span>

<span data-ttu-id="f9441-118">SIEM 服务器可以接收来自各种 Microsoft 365 服务和应用程序的数据。</span><span class="sxs-lookup"><span data-stu-id="f9441-118">A SIEM server can receive data from a wide variety of Microsoft 365 services and applications.</span></span> <span data-ttu-id="f9441-119">下表列出了几个 Microsoft 365 服务和应用程序以及 SIEM 服务器输入和资源，以详细了解 SIEM server 集成。</span><span class="sxs-lookup"><span data-stu-id="f9441-119">The following table lists several Microsoft 365 services and applications along with SIEM server inputs, and resources to learn more about SIEM server integration.</span></span> 

| <span data-ttu-id="f9441-120">Microsoft 365 服务或应用程序</span><span class="sxs-lookup"><span data-stu-id="f9441-120">Microsoft 365 Service or Application</span></span> | <span data-ttu-id="f9441-121">SIEM 服务器输入</span><span class="sxs-lookup"><span data-stu-id="f9441-121">SIEM server inputs</span></span> | <span data-ttu-id="f9441-122">了解详细信息的资源</span><span class="sxs-lookup"><span data-stu-id="f9441-122">Resources to learn more</span></span> |
| --- | --- | --- |
| [<span data-ttu-id="f9441-123">Office 365 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="f9441-123">Office 365 Advanced Threat Protection</span></span>](office-365-atp.md)  | <span data-ttu-id="f9441-124">审核日志</span><span class="sxs-lookup"><span data-stu-id="f9441-124">Audit logs</span></span> | [<span data-ttu-id="f9441-125">SIEM 与 Office 365 高级威胁防护的集成</span><span class="sxs-lookup"><span data-stu-id="f9441-125">SIEM integration with Office 365 Advanced Threat Protection</span></span>](siem-integration-with-office-365-ti.md) |
| [<span data-ttu-id="f9441-126">Microsoft Defender 高级威胁防护</span><span class="sxs-lookup"><span data-stu-id="f9441-126">Microsoft Defender Advanced Threat Protection</span></span>](https://docs.microsoft.com/windows/security/threat-protection/) | <span data-ttu-id="f9441-127">Azure 中托管的 HTTPS 终结点</span><span class="sxs-lookup"><span data-stu-id="f9441-127">HTTPS endpoint hosted in Azure</span></span> <br/><span data-ttu-id="f9441-128">REST API</span><span class="sxs-lookup"><span data-stu-id="f9441-128">REST API</span></span>| [<span data-ttu-id="f9441-129">将警报拉入 SIEM 工具</span><span class="sxs-lookup"><span data-stu-id="f9441-129">Pull alerts to your SIEM tools</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/configure-siem) |
| [<span data-ttu-id="f9441-130">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f9441-130">Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security) | <span data-ttu-id="f9441-131">日志集成</span><span class="sxs-lookup"><span data-stu-id="f9441-131">Log integration</span></span> | [<span data-ttu-id="f9441-132">SIEM 与 Microsoft Cloud App Security 的集成</span><span class="sxs-lookup"><span data-stu-id="f9441-132">SIEM integration with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/siem) |

> [!TIP]
> <span data-ttu-id="f9441-133">查看[Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview)，它附带了许多连接器（适用于 Microsoft 解决方案），现成且提供了实时集成（包括 Microsoft 威胁防护解决方案）和 microsoft 365 源（包括 Office 365、azure AD、azure ATP 和 Microsoft 云应用安全性等）。</span><span class="sxs-lookup"><span data-stu-id="f9441-133">Take a look at [Azure Sentinel](https://docs.microsoft.com/azure/sentinel/overview), which comes with a number of connectors for Microsoft solutions, available out of the box and providing real-time integration, including Microsoft Threat Protection solutions, and Microsoft 365 sources, including Office 365, Azure AD, Azure ATP, and Microsoft Cloud App Security, and more.</span></span>

### <a name="audit-logging-must-be-turned-on"></a><span data-ttu-id="f9441-134">必须打开审核日志记录</span><span class="sxs-lookup"><span data-stu-id="f9441-134">Audit logging must be turned on</span></span>

<span data-ttu-id="f9441-135">在配置 SIEM server 集成之前，请确保审核日志记录已打开。</span><span class="sxs-lookup"><span data-stu-id="f9441-135">Make sure audit logging is turned on before you configure SIEM server integration.</span></span> 

- <span data-ttu-id="f9441-136">对于 SharePoint Online、OneDrive for business 和 Azure Active Directory，[审核日志记录在安全 & 合规性中心中打开](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off)。</span><span class="sxs-lookup"><span data-stu-id="f9441-136">For SharePoint Online, OneDrive for Business, and Azure Active Directory, [audit logging is turned on in the Security & Compliance Center](https://docs.microsoft.com/office365/securitycompliance/turn-audit-log-search-on-or-off).</span></span>

- <span data-ttu-id="f9441-137">对于 Exchange Online，[审核日志记录是使用 Windows PowerShell 打开](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing)的。</span><span class="sxs-lookup"><span data-stu-id="f9441-137">For Exchange Online, [audit logging is turned on with Windows PowerShell](https://docs.microsoft.com/office365/securitycompliance/enable-mailbox-auditing).</span></span>
 
## <a name="additional-resources"></a><span data-ttu-id="f9441-138">其他资源</span><span class="sxs-lookup"><span data-stu-id="f9441-138">Additional resources</span></span>

[<span data-ttu-id="f9441-139">在 Azure 安全中心集成安全解决方案</span><span class="sxs-lookup"><span data-stu-id="f9441-139">Integrate security solutions in Azure Security Center</span></span>](https://docs.microsoft.com/azure/security-center/security-center-partner-integration#exporting-data-to-a-siem)

[<span data-ttu-id="f9441-140">将 Microsoft Graph 安全性 API 警报与 SIEM 集成</span><span class="sxs-lookup"><span data-stu-id="f9441-140">Integrate Microsoft Graph Security API alerts with a SIEM</span></span>](https://docs.microsoft.com/graph/security-integration)