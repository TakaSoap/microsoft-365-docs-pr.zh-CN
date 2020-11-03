---
title: Microsoft 托管桌面中的安全操作
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 5698e2a88adf3d2bae84a82e0e001132293e36be
ms.sourcegitcommit: 815229e39a0f905d9f06717f00dc82e2a028fa7c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2020
ms.locfileid: "48847712"
---
# <a name="security-operations-in-microsoft-managed-desktop"></a><span data-ttu-id="9cfed-103">Microsoft 托管桌面中的安全操作</span><span class="sxs-lookup"><span data-stu-id="9cfed-103">Security operations in Microsoft Managed Desktop</span></span>

<span data-ttu-id="9cfed-104">Microsoft 托管桌面安全操作中心 (SOC) 合作伙伴与您的信息安全人员保持安全，以确保您的桌面环境安全。</span><span class="sxs-lookup"><span data-stu-id="9cfed-104">The Microsoft Managed Desktop Security Operations Center (SOC) partners with your information security staff to keep your desktop environment secure.</span></span> <span data-ttu-id="9cfed-105">我们的团队使用专家分析在托管设备上接收和响应所有安全警报，并在需要时推动安全事件响应活动。</span><span class="sxs-lookup"><span data-stu-id="9cfed-105">Our team receives and responds to all security alerts on managed devices with expert analysis and, when needed, we drive security incident response activities.</span></span> <span data-ttu-id="9cfed-106">有关使用 SOC 的详细信息，请参阅管理门户的操作文档。</span><span class="sxs-lookup"><span data-stu-id="9cfed-106">For more information about working with the SOC, review operational documentation at your Admin portal.</span></span>

<span data-ttu-id="9cfed-107">SOC 在 Microsoft 全职员工中提供24/7/365 的覆盖范围，其中包含当前和新兴威胁环境的专业技能，包括通过软件、网络或人类 adversaries 的常见攻击方法。</span><span class="sxs-lookup"><span data-stu-id="9cfed-107">The SOC offers 24/7/365 coverage from Microsoft full-time employees with expertise in the current and emerging threat landscape, including common attack methods through software, network, or human adversaries.</span></span>

<span data-ttu-id="9cfed-108">SOC 提供以下服务：</span><span class="sxs-lookup"><span data-stu-id="9cfed-108">The SOC provides these services:</span></span>
- <span data-ttu-id="9cfed-109">对检测到的事件的快速且准确的响应，并分析数据以确定影响并评估设备或环境的总体风险</span><span class="sxs-lookup"><span data-stu-id="9cfed-109">Quick and accurate response to detected events, with analysis of data to identify the impact and assess the overall risk to a device or your environment</span></span>
- <span data-ttu-id="9cfed-110">设备管理和隔离操作，以保护您的环境免受已知或可疑的威胁，通过阻止传播降低风险</span><span class="sxs-lookup"><span data-stu-id="9cfed-110">Device management and isolation actions to protect your environment from known or suspected compromises, reducing risk by preventing spread</span></span>
- <span data-ttu-id="9cfed-111">推动安全事件响应流程，以确保与安全团队及时准确地进行通信</span><span class="sxs-lookup"><span data-stu-id="9cfed-111">Driving the security incident response process, ensuring timely and accurate communication with your security team</span></span>
- <span data-ttu-id="9cfed-112">基于威胁和漏洞数据的分析和建议，以在风险被利用之前识别和解决风险</span><span class="sxs-lookup"><span data-stu-id="9cfed-112">Analysis and recommendations based on threat and vulnerability data to identify and address risks before they're exploited</span></span>
- <span data-ttu-id="9cfed-113">跨托管设备的高级搜寻，以确定已知和潜在威胁的指标和实体</span><span class="sxs-lookup"><span data-stu-id="9cfed-113">Advanced hunting across the managed devices to identify indicators and entities for both known and potential threats</span></span>

## <a name="processes"></a><span data-ttu-id="9cfed-114">进程</span><span class="sxs-lookup"><span data-stu-id="9cfed-114">Processes</span></span>

- <span data-ttu-id="9cfed-115">Microsoft 托管桌面安全操作由与 Microsoft 的 [网络防御运营中心](https://www.microsoft.com/msrc/cdoc)合作的全时 microsoft 员工组成。</span><span class="sxs-lookup"><span data-stu-id="9cfed-115">Microsoft Managed Desktop Security Operations is staffed by full-time Microsoft employees in partnership with  Microsoft’s [Cyber Defense Operations Center](https://www.microsoft.com/msrc/cdoc).</span></span> 
- <span data-ttu-id="9cfed-116">我们的 SOC 使用来自我们公司（内部和外部）的集体信号来保护你的设备--甚至来自 Microsoft 托管桌面尚未看到的东西。</span><span class="sxs-lookup"><span data-stu-id="9cfed-116">Our SOC uses collective signals from across our company, both internal and external, to protect your devices--even from things we have not yet seen in Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="9cfed-117">Microsoft 安全解决方案对应于许多 cybersecurity 保护标准。</span><span class="sxs-lookup"><span data-stu-id="9cfed-117">Microsoft security solutions align to many cybersecurity protection standards.</span></span> <span data-ttu-id="9cfed-118">SOC 操作基于美国国家标准和技术计算机安全事件响应处理指南 (NIST 800-61 r2) 。</span><span class="sxs-lookup"><span data-stu-id="9cfed-118">SOC operations are based on the National Institute of Standards and Technology Computer Security Incident Response Handling Guide (NIST 800-61 r2).</span></span>
- <span data-ttu-id="9cfed-119">此过程允许正确收集信息和证据，以供分析和文档和恢复后深入了解通过以下阶段更好地保护环境的方法：</span><span class="sxs-lookup"><span data-stu-id="9cfed-119">The process allows for proper collection of information and evidence, for analysis and documentation and post-recovery insights into ways to better defend your environment through these phases:</span></span>
    - <span data-ttu-id="9cfed-120">准备、检测和分析</span><span class="sxs-lookup"><span data-stu-id="9cfed-120">Preparation, detection, and analysis</span></span>
    - <span data-ttu-id="9cfed-121">内嵌</span><span class="sxs-lookup"><span data-stu-id="9cfed-121">Containment</span></span>
    - <span data-ttu-id="9cfed-122">Eradication</span><span class="sxs-lookup"><span data-stu-id="9cfed-122">Eradication</span></span>
    - <span data-ttu-id="9cfed-123">恢复流程</span><span class="sxs-lookup"><span data-stu-id="9cfed-123">Recovery</span></span>
    - <span data-ttu-id="9cfed-124">事件后活动</span><span class="sxs-lookup"><span data-stu-id="9cfed-124">Post-incident activity</span></span>
- <span data-ttu-id="9cfed-125">Microsoft 托管桌面客户有资格注册 Microsoft 威胁专家服务。</span><span class="sxs-lookup"><span data-stu-id="9cfed-125">Microsoft Managed Desktop customers are eligible to enroll in the Microsoft Threat Experts service.</span></span> <span data-ttu-id="9cfed-126">使用此服务的 SOC 与可以更好地了解影响组织的复杂威胁，包括警报查询、潜在的受损设备、可疑网络连接的根本原因以及有关持续的高级威胁市场活动的其他威胁智能。</span><span class="sxs-lookup"><span data-stu-id="9cfed-126">The SOC liaises with this service to understand better the complex threats affecting your organization, including alert inquiries, potentially compromised devices, root cause of a suspicious network connection, and additional threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="9cfed-127">有关详细信息，请参阅 [Microsoft 威胁专家](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。</span><span class="sxs-lookup"><span data-stu-id="9cfed-127">For more information, see [Microsoft Threat Experts](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).</span></span>
- <span data-ttu-id="9cfed-128">SOC 的威胁和漏洞管理过程使用 Microsoft 的一些服务来帮助通知组织的建议，以防范威胁。</span><span class="sxs-lookup"><span data-stu-id="9cfed-128">SOC’s Threat and Vulnerability Management process uses some of Microsoft’s services to help inform recommendations for your organization to protect against threats.</span></span> <span data-ttu-id="9cfed-129">SOC 使用 Microsoft Defender for Endpoint Security Center 中的数据以及来自 Microsoft 内部和外部的相关漏洞数据源，以发现漏洞和错误配置并提供可操作的报告。</span><span class="sxs-lookup"><span data-stu-id="9cfed-129">The SOC consumes data from your Microsoft Defender for Endpoint Security Center and from relevant vulnerability data sources within and outside of Microsoft to discover vulnerabilities and misconfigurations and provide actionable reporting.</span></span>
