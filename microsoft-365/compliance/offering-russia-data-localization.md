---
title: 俄语个人数据本地化要求
description: 了解如何收集个人数据、俄语公民的个人数据记录、systematization、累积、存储、澄清和提取操作在位于俄罗斯的 Microsoft 服务和数据库中执行。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 70e36d4f11f7fc1a5870f41a32351cf7078bdc68
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44065767"
---
# <a name="russian-personal-data-localization-requirements"></a><span data-ttu-id="385ef-104">俄语个人数据本地化要求</span><span class="sxs-lookup"><span data-stu-id="385ef-104">Russian Personal Data Localization Requirements</span></span>

<span data-ttu-id="385ef-105">到2015年9月1日的组织（被视为个人数据操作员的组织），必须确保在收集个人数据时，俄罗斯公民的个人数据记录、systematization、累积、存储、说明（更新、更改）和提取通过位于俄罗斯（"个人数据本地化要求"）中的数据库执行。<sup>1</sup></span><span class="sxs-lookup"><span data-stu-id="385ef-105">As of September 1, 2015, organizations, that are considered personal data operators, must ensure when collecting personal data, that Russian citizens’ personal data recording, systematization, accumulation, storage, clarification (updating, changing) and extraction are performed through the databases located in Russia ('personal data localization requirement').<sup>1</sup></span></span>

<span data-ttu-id="385ef-106">Microsoft Online Services 适用于组织（包括但不限于教育机构）（hereinafter 称为 "customer"），其中包括启用个人数据处理（如 Microsoft Azure、Microsoft 365、Dynamics 365 和 Power Platform）的数据处理中心（位于俄罗斯之外）提供（有关详细信息，请访问[Microsoft 信任中心](https://www.microsoft.com/trust-center)）。</span><span class="sxs-lookup"><span data-stu-id="385ef-106">Microsoft Online Services, available to the organizations (including but not limited to educational institutions) (hereinafter referred to as 'customer'), including those enabling personal data processing, – such as Microsoft Azure, Microsoft 365, Dynamics 365, and Power Platform – are provided from data processing centers, located outside of Russia (for more information visit the [Microsoft Trust Center](https://www.microsoft.com/trust-center)).</span></span>

<span data-ttu-id="385ef-107">根据信息的类型和内容，客户信息系统（包括那些使用 Microsoft 云产品的系统）处理的信息可能被视为个人数据信息系统（"PDIS"、"ISPD"）。</span><span class="sxs-lookup"><span data-stu-id="385ef-107">Based on the type and content of information, processed by customer information systems, such systems, including those using Microsoft cloud products, may be deemed a personal data information system ('PDIS', 'ISPD').</span></span> <span data-ttu-id="385ef-108">如果客户希望在系统中使用通过其体系结构和所处理的信息类型限定为 PDIS 的 Microsoft Online Services，Microsoft 会邀请其客户考虑其他一些可用的解决方案，如下所示。</span><span class="sxs-lookup"><span data-stu-id="385ef-108">In cases where the customer would like to use Microsoft Online Services, in a system, that qualifies as PDIS through its architecture and types of information processed, Microsoft invites its customers to consider amongst other things available solutions, specified below.</span></span> <span data-ttu-id="385ef-109">以下提供的所有方案均可供客户作为标准商业产品的附加选项。</span><span class="sxs-lookup"><span data-stu-id="385ef-109">All the scenarios provided below are available for customers as an additional option to standard business offerings.</span></span>

<span data-ttu-id="385ef-110">应注意的是，它是客户，作为 PDIS 的个人数据运营商，负责遵守合规性，并应针对个人数据本地化进行分析和评估适用的法律要求，并以独立的方式决定，以确保 PDIS 中的个人数据处理符合俄语个人数据法律。<sup>2</sup></span><span class="sxs-lookup"><span data-stu-id="385ef-110">It should be noted, that it is the customer, as personal data operator of PDIS, who is in charge of compliance and shall analyze and assess applicable legal requirements for personal data localization and, at its own discretion, independently determine sufficient measures to ensure, that personal data processing in PDIS complies with the Russian personal data law.<sup>2</sup></span></span>

## <a name="subscribing-to-microsoft-online-services"></a><span data-ttu-id="385ef-111">订阅 Microsoft Online Services</span><span class="sxs-lookup"><span data-stu-id="385ef-111">Subscribing to Microsoft Online Services</span></span>

### <a name="microsoft-id-management"></a><span data-ttu-id="385ef-112">Microsoft ID 管理</span><span class="sxs-lookup"><span data-stu-id="385ef-112">Microsoft ID Management</span></span>

<span data-ttu-id="385ef-113">Microsoft 邀请客户考虑通过 Microsoft 云解决方案提供商（CSP）合作伙伴订阅 Microsoft Online Services （Microsoft Azure、Microsoft 365、Dynamics 365 和 Power Platform）。</span><span class="sxs-lookup"><span data-stu-id="385ef-113">Microsoft invites customers to consider subscribing to Microsoft Online Services – Microsoft Azure, Microsoft 365, Dynamics 365, and Power Platform – via a Microsoft Cloud Solution Provider (CSP) partner.</span></span> <span data-ttu-id="385ef-114">有关详细信息，请参阅此[CSP 合作伙伴列表](https://pinpoint.microsoft.com/search?type=services&campaign=691)。</span><span class="sxs-lookup"><span data-stu-id="385ef-114">See this [list of CSP partners](https://pinpoint.microsoft.com/search?type=services&campaign=691) for more information.</span></span>

### <a name="managing-user-identity-and-access-for-microsoft-online-services"></a><span data-ttu-id="385ef-115">管理 Microsoft Online Services 的用户标识和访问权限</span><span class="sxs-lookup"><span data-stu-id="385ef-115">Managing User Identity and Access for Microsoft Online Services</span></span>

<span data-ttu-id="385ef-116">对于 microsoft Azure 等 Microsoft Online Services，Microsoft 365、Dynamics 365 和 Power Platform 用户验证和访问管理是通过[Azure Active Directory （AAD）](https://azure.microsoft.com/services/active-directory/)执行的。</span><span class="sxs-lookup"><span data-stu-id="385ef-116">For Microsoft Online Services such as Microsoft Azure, Microsoft 365, Dynamics 365 and Power Platform user verification and access management are performed through [Azure Active Directory (AAD)](https://azure.microsoft.com/services/active-directory/).</span></span> <span data-ttu-id="385ef-117">请注意，对于 microsoft 云服务（如 Windows Server Active Directory （AD）或任何其他 ID 管理系统），Microsoft 客户使用本地标识管理系统，客户有机会通过 Azure AD Connect 将此类系统与 Azure Active Directory （AAD）进行快速集成。</span><span class="sxs-lookup"><span data-stu-id="385ef-117">Note that cases where a Microsoft customer uses a local identification management system for Microsoft cloud services (such as the Windows Server Active Directory (AD) or any other ID management system), the customer has an opportunity to swiftly integrate such system with the Azure Active Directory (AAD) through Azure AD Connect.</span></span> <span data-ttu-id="385ef-118">有关详细信息，请参阅[AZURE AD Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/)选项。</span><span class="sxs-lookup"><span data-stu-id="385ef-118">See the [Azure AD Connect](https://docs.microsoft.com/azure/active-directory/cloud-provisioning/) option for more information.</span></span> <span data-ttu-id="385ef-119">Microsoft 客户还可以考虑使用第三方供应商的应用程序和解决方案来管理其用户，并将其本地标识系统与 Azure AD 集成。</span><span class="sxs-lookup"><span data-stu-id="385ef-119">Microsoft customers may also consider using applications and solutions of third-party vendors for managing their users and integrate their local identification system with the Azure AD.</span></span>

## <a name="questions-and-support"></a><span data-ttu-id="385ef-120">问题和支持</span><span class="sxs-lookup"><span data-stu-id="385ef-120">Questions and support</span></span>

<span data-ttu-id="385ef-121">有关技术和帐单方面的问题，请参阅下面的 Microsoft 支持资源。</span><span class="sxs-lookup"><span data-stu-id="385ef-121">For technical and billing questions, refer to the Microsoft Support resources below.</span></span> <span data-ttu-id="385ef-122">有关其他问题或说明，请与 Microsoft[隐私团队](https://support.microsoft.com/gp/privacy-page)联系。</span><span class="sxs-lookup"><span data-stu-id="385ef-122">For additional questions or clarifications contact the Microsoft [privacy team](https://support.microsoft.com/gp/privacy-page).</span></span>

### <a name="microsoft-azure"></a><span data-ttu-id="385ef-123">Microsoft Azure</span><span class="sxs-lookup"><span data-stu-id="385ef-123">Microsoft Azure</span></span>

- <span data-ttu-id="385ef-124">**网站**： [Microsoft Azure 支持](https://aka.ms/GetAzureSupport)</span><span class="sxs-lookup"><span data-stu-id="385ef-124">**Website**: [Microsoft Azure support](https://aka.ms/GetAzureSupport)</span></span>
- <span data-ttu-id="385ef-125">免费**电话**： 8 800 200 8001</span><span class="sxs-lookup"><span data-stu-id="385ef-125">**Toll Free**: 8 800 200 8001</span></span>
- <span data-ttu-id="385ef-126">**本地呼叫**： 495 916 7171</span><span class="sxs-lookup"><span data-stu-id="385ef-126">**Local Call**: 495 916 7171</span></span>
- <span data-ttu-id="385ef-127">**在线支持**：通过[Azure 门户](https://portal.azure.com)提交查询</span><span class="sxs-lookup"><span data-stu-id="385ef-127">**Online support**: Submit queries via [Azure Portal](https://portal.azure.com)</span></span>

### <a name="microsoft-365"></a><span data-ttu-id="385ef-128">Microsoft 365</span><span class="sxs-lookup"><span data-stu-id="385ef-128">Microsoft 365</span></span>

- <span data-ttu-id="385ef-129">免费**电话**： 8 10 800 2548 1044</span><span class="sxs-lookup"><span data-stu-id="385ef-129">**Toll Free**: 8 10 800 2548 1044</span></span>
- <span data-ttu-id="385ef-130">**本地呼叫**： 499 922 8623</span><span class="sxs-lookup"><span data-stu-id="385ef-130">**Local Call**: 499 922 8623</span></span>
- <span data-ttu-id="385ef-131">**在线支持**：通过[管理中心](https://portal.office.com/)提交查询</span><span class="sxs-lookup"><span data-stu-id="385ef-131">**Online support**: Submit queries via [Admin Center](https://portal.office.com/)</span></span>

### <a name="dynamics-365"></a><span data-ttu-id="385ef-132">Dynamics 365</span><span class="sxs-lookup"><span data-stu-id="385ef-132">Dynamics 365</span></span>

- <span data-ttu-id="385ef-133">免费**电话**： 8 10 800 2548 1044</span><span class="sxs-lookup"><span data-stu-id="385ef-133">**Toll Free**: 8 10 800 2548 1044</span></span>
- <span data-ttu-id="385ef-134">**本地呼叫**： 499 922 8623</span><span class="sxs-lookup"><span data-stu-id="385ef-134">**Local Call**: 499 922 8623</span></span>
- <span data-ttu-id="385ef-135">**在线支持**：通过[Dynamics 支持门户](https://dynamics.microsoft.com/support/)提交查询</span><span class="sxs-lookup"><span data-stu-id="385ef-135">**Online support**: Submit queries via [Dynamics Support portal](https://dynamics.microsoft.com/support/)</span></span>

### <a name="power-platform"></a><span data-ttu-id="385ef-136">Power Platform</span><span class="sxs-lookup"><span data-stu-id="385ef-136">Power Platform</span></span>

- <span data-ttu-id="385ef-137">免费**电话**： 8 10 800 2548 1044</span><span class="sxs-lookup"><span data-stu-id="385ef-137">**Toll Free**: 8 10 800 2548 1044</span></span>
- <span data-ttu-id="385ef-138">**本地呼叫**： 499 922 8623</span><span class="sxs-lookup"><span data-stu-id="385ef-138">**Local Call**: 499 922 8623</span></span>
- <span data-ttu-id="385ef-139">**在线支持**：通过[电源平台支持](https://docs.microsoft.com/power-platform/admin/get-help-support)提交查询</span><span class="sxs-lookup"><span data-stu-id="385ef-139">**Online support**: Submit queries via [Power Platform Support](https://docs.microsoft.com/power-platform/admin/get-help-support)</span></span>

> [!NOTE]
> <span data-ttu-id="385ef-140"><sup>1</sup>联邦法律号</span><span class="sxs-lookup"><span data-stu-id="385ef-140"><sup>1</sup> Federal Law No.</span></span> <span data-ttu-id="385ef-141">242-FZ （edition of edition 12.31.2014） ' On the 在将修正案输入到特定法律行为中。关于阐明了在信息和电信网络中的个人数据处理过程07.21.2014</span><span class="sxs-lookup"><span data-stu-id="385ef-141">242-FZ (edition dated 12.31.2014) 'On entering amendments into certain legislative acts of the Russian Federation about clarifying the procedure for personal data processing in information and telecommunication networks' dated 07.21.2014</span></span> <br>
> <span data-ttu-id="385ef-142"><sup>2</sup>联邦法律号</span><span class="sxs-lookup"><span data-stu-id="385ef-142"><sup>2</sup> Federal Law No.</span></span> <span data-ttu-id="385ef-143">152-FZ 的个人数据，从07.27 到。</span><span class="sxs-lookup"><span data-stu-id="385ef-143">152-FZ on Personal data as of 07.27.</span></span> <span data-ttu-id="385ef-144">2006</span><span class="sxs-lookup"><span data-stu-id="385ef-144">2006</span></span><br>
