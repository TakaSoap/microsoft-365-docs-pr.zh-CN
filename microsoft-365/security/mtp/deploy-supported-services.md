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
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: b19907517f94cc8b6dbf041cccf56f1d8e232f2f
ms.sourcegitcommit: 0df099d2e1028bbba8b6371dc5fcd021dddc902b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/03/2020
ms.locfileid: "42374200"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="f3d5d-104">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="f3d5d-104">Deploy supported services</span></span>

<span data-ttu-id="f3d5d-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="f3d5d-105">**Applies to:**</span></span>
- <span data-ttu-id="f3d5d-106">Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f3d5d-106">Microsoft Threat Protection</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="f3d5d-107">[Microsoft 威胁防护](microsoft-threat-protection.md)集成了各种 Microsoft 安全服务，以提供针对复杂攻击的集中式检测、预防和调查功能。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-107">[Microsoft Threat Protection](microsoft-threat-protection.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="f3d5d-108">本文介绍了受支持的服务、其许可要求、与部署一个或多个服务相关的优势和限制，以及如何单独完全部署它们的链接。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="f3d5d-109">支持的服务</span><span class="sxs-lookup"><span data-stu-id="f3d5d-109">Supported services</span></span>
<span data-ttu-id="f3d5d-110">[Microsoft 365 e5、E5 security、a5 或 A5 安全或有效的许可证组合](prerequisites.md#licensing-requirements)可提供对以下受支持服务的访问权限，并使您能够在 microsoft 365 安全中心中使用 Microsoft 威胁防护。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-110">A [Microsoft 365 E5, E5 Security, A5, or A5 Security or a valid combination of licenses](prerequisites.md#licensing-requirements) provides access to the following supported services and entitles you to use Microsoft Threat Protection in Microsoft 365 security center.</span></span>

| <span data-ttu-id="f3d5d-111">支持的服务</span><span class="sxs-lookup"><span data-stu-id="f3d5d-111">Supported service</span></span> | <span data-ttu-id="f3d5d-112">说明</span><span class="sxs-lookup"><span data-stu-id="f3d5d-112">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="f3d5d-113">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f3d5d-113">Microsoft Defender ATP</span></span> | <span data-ttu-id="f3d5d-114">围绕功能强大的行为传感器、云分析和威胁智能构建的 Endpoint protection 套件</span><span class="sxs-lookup"><span data-stu-id="f3d5d-114">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
| <span data-ttu-id="f3d5d-115">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f3d5d-115">Office 365 ATP</span></span> | <span data-ttu-id="f3d5d-116">Office 365 中的应用和数据的高级保护，包括电子邮件和其他协作工具</span><span class="sxs-lookup"><span data-stu-id="f3d5d-116">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="f3d5d-117">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="f3d5d-117">Azure ATP</span></span> | <span data-ttu-id="f3d5d-118">使用关联的 Active Directory 信号防止高级威胁、已泄露身份和恶意预览体验</span><span class="sxs-lookup"><span data-stu-id="f3d5d-118">Safeguard against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="f3d5d-119">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f3d5d-119">Microsoft Cloud App Security</span></span> | <span data-ttu-id="f3d5d-120">跨你的 Microsoft 和第三方云服务识别和 combats 威胁</span><span class="sxs-lookup"><span data-stu-id="f3d5d-120">Identifies and combats cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="f3d5d-121">部署的服务和功能</span><span class="sxs-lookup"><span data-stu-id="f3d5d-121">Deployed services and functionality</span></span>
<span data-ttu-id="f3d5d-122">当您部署更受支持的服务时，Microsoft 威胁防护可提供更好的可见性、关联和修正。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-122">Microsoft Threat Protection provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="f3d5d-123">完整部署的好处</span><span class="sxs-lookup"><span data-stu-id="f3d5d-123">Benefits of full deployment</span></span>
<span data-ttu-id="f3d5d-124">若要获得 Microsoft 威胁防护的全部优点，建议部署所有受支持的服务。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-124">To get the complete benefits of Microsoft Threat Protection, we recommend deploying all supported services.</span></span> <span data-ttu-id="f3d5d-125">以下是完整部署的一些主要优点：</span><span class="sxs-lookup"><span data-stu-id="f3d5d-125">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="f3d5d-126">根据来自所有可用传感器和特定于服务的分析功能的警报和事件信号确定和关联事件</span><span class="sxs-lookup"><span data-stu-id="f3d5d-126">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="f3d5d-127">自动化调查和修正（空气）行动手册适用于各种实体类型，包括设备、邮箱和用户帐户</span><span class="sxs-lookup"><span data-stu-id="f3d5d-127">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="f3d5d-128">可以查询更全面的高级搜寻架构，以获取来自设备、邮箱和其他实体的事件和实体数据</span><span class="sxs-lookup"><span data-stu-id="f3d5d-128">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="f3d5d-129">有限的部署方案</span><span class="sxs-lookup"><span data-stu-id="f3d5d-129">Limited deployment scenarios</span></span>
<span data-ttu-id="f3d5d-130">您部署的每个受支持的服务都提供了一组极其丰富的原始信号以及关联信息。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-130">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="f3d5d-131">虽然有限的部署不会导致禁用 Microsoft 威胁防护功能，但其在终结点、应用、数据和标识之间提供全面可见性的能力将受到影响。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-131">While limited deployment doesn’t cause Microsoft Threat Protection functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="f3d5d-132">同时，任何修正功能仅适用于可由您部署的服务管理的实体。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-132">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="f3d5d-133">下表列出了每个受支持的服务如何提供其他数据、通过关联数据获取更多洞察力的机会以及更好的补救措施和响应功能。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-133">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="f3d5d-134">服务</span><span class="sxs-lookup"><span data-stu-id="f3d5d-134">Service</span></span> | <span data-ttu-id="f3d5d-135">数据（信号 & 相关信息）</span><span class="sxs-lookup"><span data-stu-id="f3d5d-135">Data (signals & correlated info)</span></span> | <span data-ttu-id="f3d5d-136">修正 & 响应作用域</span><span class="sxs-lookup"><span data-stu-id="f3d5d-136">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="f3d5d-137">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f3d5d-137">Microsoft Defender ATP</span></span> | <span data-ttu-id="f3d5d-138">-终结点状态和原始事件</span><span class="sxs-lookup"><span data-stu-id="f3d5d-138">- Endpoint states and raw events</span></span><br /><span data-ttu-id="f3d5d-139">-终结点检测和警报，包括防病毒、EDR、攻击面减少</span><span class="sxs-lookup"><span data-stu-id="f3d5d-139">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="f3d5d-140">-有关在终结点上观测到的文件和其他实体的信息</span><span class="sxs-lookup"><span data-stu-id="f3d5d-140">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="f3d5d-141">点</span><span class="sxs-lookup"><span data-stu-id="f3d5d-141">Endpoints</span></span> |
| <span data-ttu-id="f3d5d-142">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f3d5d-142">Office 365 ATP</span></span> | <span data-ttu-id="f3d5d-143">-邮件和邮箱状态以及原始事件</span><span class="sxs-lookup"><span data-stu-id="f3d5d-143">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="f3d5d-144">-电子邮件、附件和链接检测</span><span class="sxs-lookup"><span data-stu-id="f3d5d-144">- Email, attachment, and link detections</span></span> | <span data-ttu-id="f3d5d-145">-邮箱</span><span class="sxs-lookup"><span data-stu-id="f3d5d-145">- Mailboxes</span></span><br /><span data-ttu-id="f3d5d-146">-Office 365 帐户</span><span class="sxs-lookup"><span data-stu-id="f3d5d-146">- Office 365 accounts</span></span> |
| <span data-ttu-id="f3d5d-147">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="f3d5d-147">Azure ATP</span></span> | <span data-ttu-id="f3d5d-148">-Active Directory 信号，包括身份验证事件</span><span class="sxs-lookup"><span data-stu-id="f3d5d-148">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="f3d5d-149">-与标识相关的行为检测</span><span class="sxs-lookup"><span data-stu-id="f3d5d-149">- Identity-related behavioral detections</span></span> | <span data-ttu-id="f3d5d-150">标识</span><span class="sxs-lookup"><span data-stu-id="f3d5d-150">Identities</span></span> |
| <span data-ttu-id="f3d5d-151">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f3d5d-151">Microsoft Cloud App Security</span></span> | <span data-ttu-id="f3d5d-152">-Unsanctioned 云应用程序 & 服务的检测（隐藏它）</span><span class="sxs-lookup"><span data-stu-id="f3d5d-152">- Detection of unsanctioned cloud apps & services (shadow IT)</span></span><br /><span data-ttu-id="f3d5d-153">-将数据暴露给云应用</span><span class="sxs-lookup"><span data-stu-id="f3d5d-153">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="f3d5d-154">-与云应用程序关联的威胁活动</span><span class="sxs-lookup"><span data-stu-id="f3d5d-154">- Threat activity associated cloud apps</span></span> | <span data-ttu-id="f3d5d-155">云应用</span><span class="sxs-lookup"><span data-stu-id="f3d5d-155">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="f3d5d-156">部署服务</span><span class="sxs-lookup"><span data-stu-id="f3d5d-156">Deploy the services</span></span>
<span data-ttu-id="f3d5d-157">部署每个服务通常需要预配到租户和一些初始配置。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-157">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="f3d5d-158">请参阅下表了解每个服务的部署方式。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-158">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="f3d5d-159">服务</span><span class="sxs-lookup"><span data-stu-id="f3d5d-159">Service</span></span> | <span data-ttu-id="f3d5d-160">预配说明</span><span class="sxs-lookup"><span data-stu-id="f3d5d-160">Provisioning instructions</span></span> | <span data-ttu-id="f3d5d-161">初始配置</span><span class="sxs-lookup"><span data-stu-id="f3d5d-161">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="f3d5d-162">Microsoft Defender ATP</span><span class="sxs-lookup"><span data-stu-id="f3d5d-162">Microsoft Defender ATP</span></span> | [<span data-ttu-id="f3d5d-163">验证授权设置并完成 Microsoft Defender ATP 设置</span><span class="sxs-lookup"><span data-stu-id="f3d5d-163">Validate licensing provisioning and complete set up for Microsoft Defender ATP</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/licensing) | <span data-ttu-id="f3d5d-164">*请参阅预配说明*</span><span class="sxs-lookup"><span data-stu-id="f3d5d-164">*See provisioning instructions*</span></span> |
| <span data-ttu-id="f3d5d-165">Office 365 ATP</span><span class="sxs-lookup"><span data-stu-id="f3d5d-165">Office 365 ATP</span></span> | <span data-ttu-id="f3d5d-166">*无，使用 Office 365 预配*</span><span class="sxs-lookup"><span data-stu-id="f3d5d-166">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="f3d5d-167">配置 ATP 策略</span><span class="sxs-lookup"><span data-stu-id="f3d5d-167">Configure ATP policies</span></span>](https://docs.microsoft.com/microsoft-365/security/office-365-security/office-365-atp#configure-atp-policies) |
| <span data-ttu-id="f3d5d-168">Azure ATP</span><span class="sxs-lookup"><span data-stu-id="f3d5d-168">Azure ATP</span></span> | [<span data-ttu-id="f3d5d-169">快速入门：创建 Azure ATP 实例</span><span class="sxs-lookup"><span data-stu-id="f3d5d-169">Quickstart: Create your Azure ATP instance</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="f3d5d-170">*请参阅预配说明*</span><span class="sxs-lookup"><span data-stu-id="f3d5d-170">*See provisioning instructions*</span></span> |
| <span data-ttu-id="f3d5d-171">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="f3d5d-171">Microsoft Cloud App Security</span></span> | <span data-ttu-id="f3d5d-172">*无*</span><span class="sxs-lookup"><span data-stu-id="f3d5d-172">*None*</span></span> | [<span data-ttu-id="f3d5d-173">快速入门： Microsoft 云应用安全入门</span><span class="sxs-lookup"><span data-stu-id="f3d5d-173">Quickstart: Get started with Microsoft Cloud App Security</span></span>](https://docs.microsoft.com/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="f3d5d-174">部署受支持的服务后，[打开 Microsoft 威胁防护](mtp-enable.md)。</span><span class="sxs-lookup"><span data-stu-id="f3d5d-174">Once you’ve deployed the supported services, [turn on Microsoft Threat Protection](mtp-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="f3d5d-175">相关主题</span><span class="sxs-lookup"><span data-stu-id="f3d5d-175">Related topics</span></span>

- [<span data-ttu-id="f3d5d-176">Microsoft 威胁防护概述</span><span class="sxs-lookup"><span data-stu-id="f3d5d-176">Microsoft Threat Protection overview</span></span>](microsoft-threat-protection.md)
- [<span data-ttu-id="f3d5d-177">打开 Microsoft 威胁防护</span><span class="sxs-lookup"><span data-stu-id="f3d5d-177">Turn on Microsoft Threat Protection</span></span>](mtp-enable.md)
- [<span data-ttu-id="f3d5d-178">Microsoft Defender ATP 概述</span><span class="sxs-lookup"><span data-stu-id="f3d5d-178">Microsoft Defender ATP overview</span></span>](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/microsoft-defender-advanced-threat-protection)
- [<span data-ttu-id="f3d5d-179">Office 365 ATP 概述</span><span class="sxs-lookup"><span data-stu-id="f3d5d-179">Office 365 ATP overview</span></span>](../office-365-security/office-365-atp.md)
- [<span data-ttu-id="f3d5d-180">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="f3d5d-180">Microsoft Cloud App Security overview</span></span>](https://docs.microsoft.com/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="f3d5d-181">Azure ATP 概述</span><span class="sxs-lookup"><span data-stu-id="f3d5d-181">Azure ATP overview</span></span>](https://docs.microsoft.com/azure-advanced-threat-protection/what-is-atp)
