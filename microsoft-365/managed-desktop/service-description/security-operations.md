---
title: Microsoft 托管桌面中的安全操作
description: 安全操作中心提供的服务和过程
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 600755c15ce6da94481ef4d84732991e5006cce1
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50908158"
---
# <a name="security-operations-in-microsoft-managed-desktop"></a><span data-ttu-id="300c2-104">Microsoft 托管桌面中的安全操作</span><span class="sxs-lookup"><span data-stu-id="300c2-104">Security operations in Microsoft Managed Desktop</span></span>

<span data-ttu-id="300c2-105">Microsoft 托管桌面安全操作中心 (SOC) 信息安全人员联系合作伙伴，以确保桌面环境安全。</span><span class="sxs-lookup"><span data-stu-id="300c2-105">The Microsoft Managed Desktop Security Operations Center (SOC) partners with your information security staff to keep your desktop environment secure.</span></span> <span data-ttu-id="300c2-106">我们团队通过专家分析接收和响应托管设备上的所有安全警报，并根据需要推动安全事件响应活动。</span><span class="sxs-lookup"><span data-stu-id="300c2-106">Our team receives and responds to all security alerts on managed devices with expert analysis and, when needed, we drive security incident response activities.</span></span> <span data-ttu-id="300c2-107">有关使用 SOC 的信息，请查看管理门户中的操作文档。</span><span class="sxs-lookup"><span data-stu-id="300c2-107">For more information about working with the SOC, review operational documentation at your Admin portal.</span></span>

<span data-ttu-id="300c2-108">SOC 提供 Microsoft 全职员工 24/7/365 的覆盖范围，这些员工具有当前和新出现的威胁环境方面的专业知识，包括通过软件、网络或人为对手的常见攻击方法。</span><span class="sxs-lookup"><span data-stu-id="300c2-108">The SOC offers 24/7/365 coverage from Microsoft full-time employees with expertise in the current and emerging threat landscape, including common attack methods through software, network, or human adversaries.</span></span>

<span data-ttu-id="300c2-109">SOC 提供以下服务：</span><span class="sxs-lookup"><span data-stu-id="300c2-109">The SOC provides these services:</span></span>
- <span data-ttu-id="300c2-110">对检测到的事件做出快速准确的响应，并分析数据以确定对设备或环境的影响并评估总体风险</span><span class="sxs-lookup"><span data-stu-id="300c2-110">Quick and accurate response to detected events, with analysis of data to identify the impact and assess the overall risk to a device or your environment</span></span>
- <span data-ttu-id="300c2-111">用于保护你的环境免受已知或可疑泄露的设备管理和隔离操作，通过防止传播来降低风险</span><span class="sxs-lookup"><span data-stu-id="300c2-111">Device management and isolation actions to protect your environment from known or suspected compromises, reducing risk by preventing spread</span></span>
- <span data-ttu-id="300c2-112">推动安全事件响应流程，确保与安全团队及时准确地沟通</span><span class="sxs-lookup"><span data-stu-id="300c2-112">Driving the security incident response process, ensuring timely and accurate communication with your security team</span></span>
- <span data-ttu-id="300c2-113">基于威胁和漏洞数据的分析和建议，以在被利用之前识别和解决风险</span><span class="sxs-lookup"><span data-stu-id="300c2-113">Analysis and recommendations based on threat and vulnerability data to identify and address risks before they're exploited</span></span>
- <span data-ttu-id="300c2-114">跨托管设备的高级搜寻，用于标识已知威胁和潜在威胁的指示器和实体</span><span class="sxs-lookup"><span data-stu-id="300c2-114">Advanced hunting across the managed devices to identify indicators and entities for both known and potential threats</span></span>

## <a name="processes"></a><span data-ttu-id="300c2-115">进程</span><span class="sxs-lookup"><span data-stu-id="300c2-115">Processes</span></span>

- <span data-ttu-id="300c2-116">Microsoft 托管桌面安全操作由与 Microsoft 网络防御操作中心合作的全职 Microsoft 员工 [配备](https://www.microsoft.com/msrc/cdoc)。</span><span class="sxs-lookup"><span data-stu-id="300c2-116">Microsoft Managed Desktop Security Operations is staffed by full-time Microsoft employees in partnership with Microsoft’s [Cyber Defense Operations Center](https://www.microsoft.com/msrc/cdoc).</span></span> 
- <span data-ttu-id="300c2-117">我们的 SOC 使用来自公司内部和外部的集中信号来保护你的设备，甚至防止我们在 Microsoft 托管桌面中尚未看到的信息。</span><span class="sxs-lookup"><span data-stu-id="300c2-117">Our SOC uses collective signals from across our company, both internal and external, to protect your devices--even from things we have not yet seen in Microsoft Managed Desktop.</span></span>
- <span data-ttu-id="300c2-118">Microsoft 安全解决方案符合许多网络安全保护标准。</span><span class="sxs-lookup"><span data-stu-id="300c2-118">Microsoft security solutions align to many cybersecurity protection standards.</span></span> <span data-ttu-id="300c2-119">SOC 操作基于美国国家标准和技术协会计算机安全事件响应处理指南 (NIST 800-61 r2) 。</span><span class="sxs-lookup"><span data-stu-id="300c2-119">SOC operations are based on the National Institute of Standards and Technology Computer Security Incident Response Handling Guide (NIST 800-61 r2).</span></span>
- <span data-ttu-id="300c2-120">此过程允许正确收集信息和证据，以进行分析和记录，以及恢复后见解，以通过以下阶段更好地保护环境：</span><span class="sxs-lookup"><span data-stu-id="300c2-120">The process allows for proper collection of information and evidence, for analysis and documentation and post-recovery insights into ways to better defend your environment through these phases:</span></span>
    - <span data-ttu-id="300c2-121">准备、检测和分析</span><span class="sxs-lookup"><span data-stu-id="300c2-121">Preparation, detection, and analysis</span></span>
    - <span data-ttu-id="300c2-122">包含</span><span class="sxs-lookup"><span data-stu-id="300c2-122">Containment</span></span>
    - <span data-ttu-id="300c2-123">百年</span><span class="sxs-lookup"><span data-stu-id="300c2-123">Eradication</span></span>
    - <span data-ttu-id="300c2-124">恢复</span><span class="sxs-lookup"><span data-stu-id="300c2-124">Recovery</span></span>
    - <span data-ttu-id="300c2-125">事件后活动</span><span class="sxs-lookup"><span data-stu-id="300c2-125">Post-incident activity</span></span>
- <span data-ttu-id="300c2-126">Microsoft 托管桌面客户有资格注册 Microsoft 威胁专家服务。</span><span class="sxs-lookup"><span data-stu-id="300c2-126">Microsoft Managed Desktop customers are eligible to enroll in the Microsoft Threat Experts service.</span></span> <span data-ttu-id="300c2-127">SOC 通过此服务更好地了解影响组织的复杂威胁，包括警报查询、可能受到威胁的设备、可疑网络连接的根本原因，以及有关正在进行的高级永久性威胁活动的其他威胁情报。</span><span class="sxs-lookup"><span data-stu-id="300c2-127">The SOC liaises with this service to understand better the complex threats affecting your organization, including alert inquiries, potentially compromised devices, root cause of a suspicious network connection, and other threat intelligence regarding ongoing advanced persistent threat campaigns.</span></span> <span data-ttu-id="300c2-128">有关详细信息，请参阅 [Microsoft 威胁专家](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts)。</span><span class="sxs-lookup"><span data-stu-id="300c2-128">For more information, see [Microsoft Threat Experts](/windows/security/threat-protection/microsoft-defender-atp/microsoft-threat-experts).</span></span>
- <span data-ttu-id="300c2-129">SOC 的威胁和漏洞管理过程使用 Microsoft 的一些服务来帮助为组织提供建议，防止威胁。</span><span class="sxs-lookup"><span data-stu-id="300c2-129">SOC’s Threat and Vulnerability Management process uses some of Microsoft’s services to help inform recommendations for your organization to protect against threats.</span></span> <span data-ttu-id="300c2-130">SOC 使用来自适用于终结点安全中心的 Microsoft Defender 以及 Microsoft 内外的相关漏洞数据源的数据，以发现漏洞和错误配置并提供可操作的报告。</span><span class="sxs-lookup"><span data-stu-id="300c2-130">The SOC consumes data from your Microsoft Defender for Endpoint Security Center and from relevant vulnerability data sources within and outside of Microsoft to discover vulnerabilities and misconfigurations and provide actionable reporting.</span></span>