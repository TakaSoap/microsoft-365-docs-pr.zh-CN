---
title: Office 365 GCC DoD 的其他网络安全要求
ms.author: dzazzo
author: dzazzo
manager: dzazzo
ms.date: 05/19/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Strat_O365_Enterprise
ms.custom: Adm_O365
search.appverid:
- OGA150m
- OGC150
- OGD150
- MOE150
ms.assetid: ''
description: 摘要：Office 365 GCC高和 DoD 具有其他网络安全要求
hideEdit: true
ms.openlocfilehash: f4c03d364e84d89a1b12e4d858ab46eb3be6ae5e
ms.sourcegitcommit: be929f79751c0c52dfa6bd98a854432a0c63faf0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/14/2021
ms.locfileid: "52926555"
---
# <a name="additional-network-security-requirements-for-office-365-gcc-high-and-dod"></a><span data-ttu-id="1073d-103">Office 365 GCC High和DOD的额外网络安全要求。</span><span class="sxs-lookup"><span data-stu-id="1073d-103">Additional network security requirements for Office 365 GCC High and DOD</span></span>

<span data-ttu-id="1073d-104">*本文适用于 Office 365 GCC、Office 365 DOD、Microsoft 365 GCC High 和 Microsoft 365 DOD。*</span><span class="sxs-lookup"><span data-stu-id="1073d-104">*This article applies to Office 365 GCC High, Office 365 DOD, Microsoft 365 GCC High, and Microsoft 365 DOD.*</span></span>

<span data-ttu-id="1073d-105">Office 365 GCC高和 DOD 是满足美国政府及其供应商和承包商需求的安全云环境。</span><span class="sxs-lookup"><span data-stu-id="1073d-105">Office 365 GCC High and DOD are secure cloud environments to meet the needs of the United States Government and its suppliers and contractors.</span></span>  <span data-ttu-id="1073d-106">对于允许服务访问的外部终结点，这些云环境具有其他网络限制。</span><span class="sxs-lookup"><span data-stu-id="1073d-106">These cloud environments have additional network restrictions on which external endpoints the services are permitted to access.</span></span>

<span data-ttu-id="1073d-107">GCC计划使用联合身份或混合共存的高和 DOD 客户可能需要 Microsoft 允许入站和/或出站访问现有本地部署。</span><span class="sxs-lookup"><span data-stu-id="1073d-107">GCC High and DOD customers planning to use federated identities or hybrid coexistence may require Microsoft to permit inbound and/or outbound access to your existing on-premises deployments.</span></span>  <span data-ttu-id="1073d-108">这些活动的示例包括：</span><span class="sxs-lookup"><span data-stu-id="1073d-108">Examples of these activities include:</span></span>

* <span data-ttu-id="1073d-109">将联合身份 (Active Directory 联合身份验证服务或类似支持的 STS) </span><span class="sxs-lookup"><span data-stu-id="1073d-109">Use of federated identities (with Active Directory Federation Services or similar supported STS)</span></span>
* <span data-ttu-id="1073d-110">与本地部署或本地部署Exchange Server Skype for Business共存</span><span class="sxs-lookup"><span data-stu-id="1073d-110">Hybrid coexistence with an on-premises Exchange Server or Skype for Business deployment</span></span>
* <span data-ttu-id="1073d-111">从本地系统迁移现有用户内容</span><span class="sxs-lookup"><span data-stu-id="1073d-111">Migration of existing user content from an on-premises system</span></span>

<span data-ttu-id="1073d-112">若要允许服务与本地终结点通信，你必须向工程团队发送Office 365更改的电子邮件。</span><span class="sxs-lookup"><span data-stu-id="1073d-112">To permit the service to communicate with your on-premises endpoints, you **must** send an email to Office 365 engineering for network changes.</span></span>

> [!WARNING]
> <span data-ttu-id="1073d-113">由于需要安全 **与** 合规控制和部署管道，所有请求的 SLA 都为三周，无法加快。</span><span class="sxs-lookup"><span data-stu-id="1073d-113">All requests have a **three-week** SLA and cannot be expedited due to the required security and compliance controls and deployment pipelines.</span></span>  <span data-ttu-id="1073d-114">这包括初始载入网络请求，以及迁移到服务后的任何更改。</span><span class="sxs-lookup"><span data-stu-id="1073d-114">This includes initial onboarding network requests as well as any changes after you have migrated to the service.</span></span>  <span data-ttu-id="1073d-115">确保你的网络团队知道此时间线，并包括在你的规划周期中。</span><span class="sxs-lookup"><span data-stu-id="1073d-115">Make sure that your network teams are aware of this timeline and include it in their planning cycles.</span></span>

<span data-ttu-id="1073d-116">使用以下信息[Office 365 政府版 Allow-List](mailto:o365gwlt@microsoft.com)电子邮件发送到请求：</span><span class="sxs-lookup"><span data-stu-id="1073d-116">Send an email to [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com) with the following information:</span></span>

* <span data-ttu-id="1073d-117">**To**： [Office 365 政府版 Allow-List Requests](mailto:o365gwlt@microsoft.com)</span><span class="sxs-lookup"><span data-stu-id="1073d-117">**To**: [Office 365 Government Allow-List Requests](mailto:o365gwlt@microsoft.com)</span></span>
* <span data-ttu-id="1073d-118">**From**：租户管理员 - 发送电子邮件 **必须与** 租户中的全局管理员联系人匹配</span><span class="sxs-lookup"><span data-stu-id="1073d-118">**From**: A tenant administrator - the send email **must** match a Global Administrator contact in your tenant</span></span>
* <span data-ttu-id="1073d-119">**电子邮件主题**：Office 365 GCC高网络请求 - contoso.onmicrosoft.us (替换为租户名称) </span><span class="sxs-lookup"><span data-stu-id="1073d-119">**Email subject**: Office 365 GCC High Network Request - contoso.onmicrosoft.us (replace with your tenant name)</span></span>

<span data-ttu-id="1073d-120">邮件正文应包含以下数据：</span><span class="sxs-lookup"><span data-stu-id="1073d-120">The body of your message should include the following data:</span></span>

* <span data-ttu-id="1073d-121">你的Microsoft Online Services租户名称 (例如，contoso.onmicrosoft.com、fabrikam.onmicrosoft.us) </span><span class="sxs-lookup"><span data-stu-id="1073d-121">Your Microsoft Online Services tenant name (for example, contoso.onmicrosoft.com, fabrikam.onmicrosoft.us)</span></span>
* <span data-ttu-id="1073d-122">与 Microsoft 通信的电子邮件通讯组列表，用于与网络更改和/或跟踪无效子网相关的后续通信</span><span class="sxs-lookup"><span data-stu-id="1073d-122">An email distribution list that Microsoft will communicate with for on-going communications related to network changes and/or follow up for invalid subnets</span></span>
* <span data-ttu-id="1073d-123">指示是否计划Microsoft Teams内部部署实现混合共存</span><span class="sxs-lookup"><span data-stu-id="1073d-123">Indicate whether you plan to use Microsoft Teams hybrid coexistence with your on-premises deployments</span></span>
* <span data-ttu-id="1073d-124">联合身份系统可从外部访问的 URL (例如，sts.contoso.com) CIDR 表示法中的 (IP 地址范围。</span><span class="sxs-lookup"><span data-stu-id="1073d-124">Federated identity system externally accessible URL (for example, sts.contoso.com) and IP address range in CIDR notation (for example,.</span></span> <span data-ttu-id="1073d-125">10.1.1.0/28) </span><span class="sxs-lookup"><span data-stu-id="1073d-125">10.1.1.0/28)</span></span>
* <span data-ttu-id="1073d-126">CIDR 表示法中的本地 PKI 证书吊销列表 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="1073d-126">On-Premises PKI Certificate Revocation List URL and IP address range in CIDR notation</span></span>
* <span data-ttu-id="1073d-127">使用 CIDR 表示法Exchange Server本地部署的可从外部访问的 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="1073d-127">Externally accessible URL and IP address range for Exchange Server on-premises deployment in CIDR notation</span></span>
* <span data-ttu-id="1073d-128">使用 CIDR 表示法Skype for Business本地部署的可从外部访问的 URL 和 IP 地址范围</span><span class="sxs-lookup"><span data-stu-id="1073d-128">Externally accessible URL and IP address range for Skype for Business on-premises deployment in CIDR notation</span></span>

<span data-ttu-id="1073d-129">出于安全性和合规性原因，请牢记对请求的以下限制：</span><span class="sxs-lookup"><span data-stu-id="1073d-129">For security and compliance reasons, keep in mind the following restrictions on your request:</span></span>

* <span data-ttu-id="1073d-130">每个租户有四个子网限制</span><span class="sxs-lookup"><span data-stu-id="1073d-130">There is a four subnet limitation per tenant</span></span>
* <span data-ttu-id="1073d-131">子网必须用 CIDR 表示法 (例如，10.1.1.0/28) </span><span class="sxs-lookup"><span data-stu-id="1073d-131">Subnets must be in CIDR Notation (for example, 10.1.1.0/28)</span></span>
* <span data-ttu-id="1073d-132">子网范围不能大于/24</span><span class="sxs-lookup"><span data-stu-id="1073d-132">Subnet ranges cannot be larger than /24</span></span>
* <span data-ttu-id="1073d-133">我们 **不允许** 请求允许访问商业云服务 (商业Office 365 Google G-Suite、Amazon Web Services 等) </span><span class="sxs-lookup"><span data-stu-id="1073d-133">We **cannot** accommodate requests to allow access to commercial cloud services (commercial Office 365, Google G-Suite, Amazon Web Services, etc.)</span></span>

<span data-ttu-id="1073d-134">一旦 Microsoft 收到并批准你的请求，将会有一个为期三周的 SLA 用于实施，并且无法加速。</span><span class="sxs-lookup"><span data-stu-id="1073d-134">Once your request has been received and approved by Microsoft, there is a three-week SLA for implementation and cannot be expedited.</span></span>  <span data-ttu-id="1073d-135">当我们收到你的请求时，你将收到初始确认，完成确认后，你将收到最终确认。</span><span class="sxs-lookup"><span data-stu-id="1073d-135">You will receive an initial acknowledgment when we’ve received your request and a final acknowledgment once it has been completed.</span></span>
