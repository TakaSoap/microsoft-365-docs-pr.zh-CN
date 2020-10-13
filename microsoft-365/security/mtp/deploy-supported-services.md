---
title: 部署 Microsoft 威胁防护支持的服务
description: 了解可以通过 Microsoft 威胁防护、其许可要求和部署过程集成的 Microsoft 安全服务
keywords: 部署、许可证、受支持的服务、设置、配置 Microsoft 威胁防护、M365、许可证资格、Microsoft Defender ATP、MDATP、Office 365 ATP、Azure ATP、Microsoft 云应用安全性、MCAS、高级威胁防护、E5、A5、EMS
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: 4e4036e1a1ee0ccf807dc5299b9842911f140478
ms.sourcegitcommit: de600339b08951d6dd3933288a8da2327a4b6ef3
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/13/2020
ms.locfileid: "48430807"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="8c680-104">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="8c680-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="8c680-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="8c680-105">**Applies to:**</span></span>
- <span data-ttu-id="8c680-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8c680-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="8c680-107">[Microsoft 威胁防护](microsoft-threat-protection.md) 集成了各种 Microsoft 安全服务，以提供针对复杂攻击的集中式检测、预防和调查功能。</span><span class="sxs-lookup"><span data-stu-id="8c680-107">[Microsoft Threat Protection](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="8c680-108">本文介绍了受支持的服务、其许可要求、与部署一个或多个服务相关的优势和限制，以及如何单独完全部署它们的链接。</span><span class="sxs-lookup"><span data-stu-id="8c680-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="8c680-109">支持的服务</span><span class="sxs-lookup"><span data-stu-id="8c680-109">Supported services</span></span>
<span data-ttu-id="8c680-110">Microsoft 365 E5、E5 Security、A5 或 A5 安全许可证或有效的许可证组合提供对以下受支持服务的访问权限，并允许您在 Microsoft 365 安全中心中使用 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="8c680-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span> [<span data-ttu-id="8c680-111">请参阅许可要求</span><span class="sxs-lookup"><span data-stu-id="8c680-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="8c680-112">支持的服务</span><span class="sxs-lookup"><span data-stu-id="8c680-112">Supported service</span></span> | <span data-ttu-id="8c680-113">说明</span><span class="sxs-lookup"><span data-stu-id="8c680-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="8c680-114">每个租户</span><span class="sxs-lookup"><span data-stu-id="8c680-114">Microsoft Defender ATP</span></span> | <span data-ttu-id="8c680-115">围绕功能强大的行为传感器、云分析和威胁智能构建的 Endpoint protection 套件</span><span class="sxs-lookup"><span data-stu-id="8c680-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
| <span data-ttu-id="8c680-116">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8c680-116">Office 365 ATP</span></span> | <span data-ttu-id="8c680-117">Office 365 中的应用和数据的高级保护，包括电子邮件和其他协作工具</span><span class="sxs-lookup"><span data-stu-id="8c680-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="8c680-118">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="8c680-118">Azure ATP</span></span> | <span data-ttu-id="8c680-119">使用关联的 Active Directory 信号防御高级威胁、已泄露身份和恶意预览体验</span><span class="sxs-lookup"><span data-stu-id="8c680-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="8c680-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8c680-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="8c680-121">跨你的 Microsoft 和第三方云服务识别和打击威胁</span><span class="sxs-lookup"><span data-stu-id="8c680-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="8c680-122">部署的服务和功能</span><span class="sxs-lookup"><span data-stu-id="8c680-122">Deployed services and functionality</span></span>
<span data-ttu-id="8c680-123">当您部署更受支持的服务时，Microsoft 威胁防护可提供更好的可见性、关联和修正。</span><span class="sxs-lookup"><span data-stu-id="8c680-123">Microsoft Threat Protection provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="8c680-124">完整部署的好处</span><span class="sxs-lookup"><span data-stu-id="8c680-124">Benefits of full deployment</span></span>
<span data-ttu-id="8c680-125">若要获得 Microsoft 威胁防护的全部优点，建议部署所有受支持的服务。</span><span class="sxs-lookup"><span data-stu-id="8c680-125">To get the complete benefits of Microsoft Threat Protection, we recommend deploying all supported services.</span></span> <span data-ttu-id="8c680-126">以下是完整部署的一些主要优点：</span><span class="sxs-lookup"><span data-stu-id="8c680-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="8c680-127">根据来自所有可用传感器和特定于服务的分析功能的警报和事件信号确定和关联事件</span><span class="sxs-lookup"><span data-stu-id="8c680-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="8c680-128">自动调查和修正 (空气) 行动手册适用于各种实体类型，包括设备、邮箱和用户帐户</span><span class="sxs-lookup"><span data-stu-id="8c680-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="8c680-129">可以查询更全面的高级搜寻架构，以获取来自设备、邮箱和其他实体的事件和实体数据</span><span class="sxs-lookup"><span data-stu-id="8c680-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="8c680-130">有限的部署方案</span><span class="sxs-lookup"><span data-stu-id="8c680-130">Limited deployment scenarios</span></span>
<span data-ttu-id="8c680-131">您部署的每个受支持的服务都提供了一组极其丰富的原始信号以及关联信息。</span><span class="sxs-lookup"><span data-stu-id="8c680-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="8c680-132">虽然有限的部署不会导致禁用 Microsoft 威胁防护功能，但其在终结点、应用、数据和标识之间提供全面可见性的能力将受到影响。</span><span class="sxs-lookup"><span data-stu-id="8c680-132">While limited deployment doesn’t cause Microsoft Threat Protection functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="8c680-133">同时，任何修正功能仅适用于可由您部署的服务管理的实体。</span><span class="sxs-lookup"><span data-stu-id="8c680-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="8c680-134">下表列出了每个受支持的服务如何提供其他数据、通过关联数据获取更多洞察力的机会以及更好的补救措施和响应功能。</span><span class="sxs-lookup"><span data-stu-id="8c680-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="8c680-135">服务</span><span class="sxs-lookup"><span data-stu-id="8c680-135">Service</span></span> | <span data-ttu-id="8c680-136">数据 (信号 & 相关信息) </span><span class="sxs-lookup"><span data-stu-id="8c680-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="8c680-137">修正 & 响应作用域</span><span class="sxs-lookup"><span data-stu-id="8c680-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="8c680-138">每个租户</span><span class="sxs-lookup"><span data-stu-id="8c680-138">Microsoft Defender ATP</span></span> | <span data-ttu-id="8c680-139">-终结点状态和原始事件</span><span class="sxs-lookup"><span data-stu-id="8c680-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="8c680-140">-终结点检测和警报，包括防病毒、EDR、攻击面减少</span><span class="sxs-lookup"><span data-stu-id="8c680-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="8c680-141">-有关在终结点上观测到的文件和其他实体的信息</span><span class="sxs-lookup"><span data-stu-id="8c680-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="8c680-142">终结点</span><span class="sxs-lookup"><span data-stu-id="8c680-142">Endpoints</span></span> |
| <span data-ttu-id="8c680-143">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8c680-143">Office 365 ATP</span></span> | <span data-ttu-id="8c680-144">-邮件和邮箱状态以及原始事件</span><span class="sxs-lookup"><span data-stu-id="8c680-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="8c680-145">-电子邮件、附件和链接检测</span><span class="sxs-lookup"><span data-stu-id="8c680-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="8c680-146">-邮箱</span><span class="sxs-lookup"><span data-stu-id="8c680-146">- Mailboxes</span></span><br /><span data-ttu-id="8c680-147">-Microsoft 365 帐户</span><span class="sxs-lookup"><span data-stu-id="8c680-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="8c680-148">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="8c680-148">Azure ATP</span></span> | <span data-ttu-id="8c680-149">-Active Directory 信号，包括身份验证事件</span><span class="sxs-lookup"><span data-stu-id="8c680-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="8c680-150">-与标识相关的行为检测</span><span class="sxs-lookup"><span data-stu-id="8c680-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="8c680-151">身份</span><span class="sxs-lookup"><span data-stu-id="8c680-151">Identities</span></span> |
| <span data-ttu-id="8c680-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8c680-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="8c680-153">-Unsanctioned 云应用和服务的检测 (隐藏它) </span><span class="sxs-lookup"><span data-stu-id="8c680-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="8c680-154">-将数据暴露给云应用</span><span class="sxs-lookup"><span data-stu-id="8c680-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="8c680-155">-与云应用程序关联的威胁活动</span><span class="sxs-lookup"><span data-stu-id="8c680-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="8c680-156">云应用</span><span class="sxs-lookup"><span data-stu-id="8c680-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="8c680-157">部署服务</span><span class="sxs-lookup"><span data-stu-id="8c680-157">Deploy the services</span></span>
<span data-ttu-id="8c680-158">部署每个服务通常需要预配到租户和一些初始配置。</span><span class="sxs-lookup"><span data-stu-id="8c680-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="8c680-159">请参阅下表了解每个服务的部署方式。</span><span class="sxs-lookup"><span data-stu-id="8c680-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="8c680-160">服务</span><span class="sxs-lookup"><span data-stu-id="8c680-160">Service</span></span> | <span data-ttu-id="8c680-161">预配说明</span><span class="sxs-lookup"><span data-stu-id="8c680-161">Provisioning instructions</span></span> | <span data-ttu-id="8c680-162">初始配置</span><span class="sxs-lookup"><span data-stu-id="8c680-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="8c680-163">每个租户</span><span class="sxs-lookup"><span data-stu-id="8c680-163">Microsoft Defender ATP</span></span> | [<span data-ttu-id="8c680-164">Microsoft Defender ATP 部署指南</span><span class="sxs-lookup"><span data-stu-id="8c680-164">Microsoft Defender ATP deployment guide</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/deployment-phases) | <span data-ttu-id="8c680-165">*请参阅预配说明*</span><span class="sxs-lookup"><span data-stu-id="8c680-165">*See provisioning instructions*</span></span> |
| <span data-ttu-id="8c680-166">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="8c680-166">Office 365 ATP</span></span> | <span data-ttu-id="8c680-167">*无，使用 Office 365 预配*</span><span class="sxs-lookup"><span data-stu-id="8c680-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="8c680-168">配置 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="8c680-168">Configure ATP policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="8c680-169">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="8c680-169">Azure ATP</span></span> | [<span data-ttu-id="8c680-170">快速入门：创建 Azure ATP 实例</span><span class="sxs-lookup"><span data-stu-id="8c680-170">Quickstart: Create your Azure ATP instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="8c680-171">*请参阅预配说明*</span><span class="sxs-lookup"><span data-stu-id="8c680-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="8c680-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="8c680-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="8c680-173">*无*</span><span class="sxs-lookup"><span data-stu-id="8c680-173">*None*</span></span> | [<span data-ttu-id="8c680-174">快速入门： Microsoft 云应用安全入门</span><span class="sxs-lookup"><span data-stu-id="8c680-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="8c680-175">部署受支持的服务后， [打开 Microsoft 威胁防护](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="8c680-175">Once you’ve deployed the supported services, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="8c680-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="8c680-176">Related topics</span></span>

- [<span data-ttu-id="8c680-177">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="8c680-177">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="8c680-178">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="8c680-178">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="8c680-179">Microsoft Defender ATP 概述</span><span class="sxs-lookup"><span data-stu-id="8c680-179">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="8c680-180">Office 365 ATP 概述</span><span class="sxs-lookup"><span data-stu-id="8c680-180">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="8c680-181">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="8c680-181">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="8c680-182">Azure ATP 概述</span><span class="sxs-lookup"><span data-stu-id="8c680-182">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
