---
title: 部署受 Microsoft 365 Defender 支持的服务
description: 了解 Microsoft 安全服务，可通过 Microsoft 365 Defender 集成、其许可要求和部署过程
keywords: 部署， 许可证， 受支持的服务， 预配， 配置 Microsoft 365 Defender， M365， 许可证资格， Microsoft Defender for Endpoint， Microsoft Defender for Office 365， Microsoft Defender for Identity， Microsoft Cloud App Security， MCAS， E5， A5， EMS
search.product: eADQiWindows 10XVcnh
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: lomayor
author: lomayor
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.technology: m365d
ms.openlocfilehash: 4e1b36423974e46a485727f7e1f158dc6163d834
ms.sourcegitcommit: a8d8cee7df535a150985d6165afdfddfdf21f622
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/21/2021
ms.locfileid: "51935673"
---
# <a name="deploy-supported-services"></a><span data-ttu-id="46ceb-104">部署支持的服务</span><span class="sxs-lookup"><span data-stu-id="46ceb-104">Deploy supported services</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]


<span data-ttu-id="46ceb-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="46ceb-105">**Applies to:**</span></span>
- <span data-ttu-id="46ceb-106">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46ceb-106">Microsoft 365 Defender</span></span>

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

<span data-ttu-id="46ceb-107">[Microsoft 365 Defender](microsoft-365-defender.md)集成了各种 Microsoft 安全服务，以提供针对复杂攻击的集中检测、防护和调查功能。</span><span class="sxs-lookup"><span data-stu-id="46ceb-107">[Microsoft 365 Defender](microsoft-365-defender.md) integrates various Microsoft security services to provide centralized detection, prevention, and investigation capabilities against sophisticated attacks.</span></span> <span data-ttu-id="46ceb-108">本文介绍受支持的服务、其许可要求、与部署一个或多个服务相关的优点和限制，以及指向如何单独完全部署它们的链接。</span><span class="sxs-lookup"><span data-stu-id="46ceb-108">This article describes the supported services, their licensing requirements, the advantages and limitations associated with deploying one or more services, and links to how you can fully deploy them individually.</span></span>

## <a name="supported-services"></a><span data-ttu-id="46ceb-109">支持的服务</span><span class="sxs-lookup"><span data-stu-id="46ceb-109">Supported services</span></span>
<span data-ttu-id="46ceb-110">A Microsoft 365 E5， E5 Security， A5， or A5 Security license or a5 A5 Security license or a valid combination of licenses provides access to the following supported services and授权你在 Microsoft 365 安全中心使用 Microsoft 365 Defender。</span><span class="sxs-lookup"><span data-stu-id="46ceb-110">A Microsoft 365 E5, E5 Security, A5, or A5 Security license or a valid combination of licenses provides access to the following supported services and entitles you to use Microsoft 365 Defender in Microsoft 365 security center.</span></span> [<span data-ttu-id="46ceb-111">请参阅许可要求</span><span class="sxs-lookup"><span data-stu-id="46ceb-111">See licensing requirements</span></span>](prerequisites.md#licensing-requirements)

| <span data-ttu-id="46ceb-112">支持的服务</span><span class="sxs-lookup"><span data-stu-id="46ceb-112">Supported service</span></span> | <span data-ttu-id="46ceb-113">说明</span><span class="sxs-lookup"><span data-stu-id="46ceb-113">Description</span></span> |
| ------ | ------ |
| <span data-ttu-id="46ceb-114">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="46ceb-114">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="46ceb-115">围绕强大的行为传感器、云分析和威胁智能构建的终结点保护套件</span><span class="sxs-lookup"><span data-stu-id="46ceb-115">Endpoint protection suite built around powerful behavioral sensors, cloud analytics, and threat intelligence</span></span> |
|<span data-ttu-id="46ceb-116">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="46ceb-116">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="46ceb-117">对应用中的应用和数据的高级Office 365，包括电子邮件和其他协作工具</span><span class="sxs-lookup"><span data-stu-id="46ceb-117">Advanced protection for your apps and data in Office 365, including email and other collaboration tools</span></span> |
| <span data-ttu-id="46ceb-118">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="46ceb-118">Microsoft Defender for Identity</span></span> | <span data-ttu-id="46ceb-119">使用关联的 Active Directory 信号防御高级威胁、泄露的标识和恶意预览体验成员</span><span class="sxs-lookup"><span data-stu-id="46ceb-119">Defend against advanced threats, compromised identities, and malicious insiders using correlated Active Directory signals</span></span> |
| <span data-ttu-id="46ceb-120">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="46ceb-120">Microsoft Cloud App Security</span></span> | <span data-ttu-id="46ceb-121">识别并防御 Microsoft 和第三方云服务中的网络威胁</span><span class="sxs-lookup"><span data-stu-id="46ceb-121">Identify and combat cyberthreats across your Microsoft and third-party cloud services</span></span> |

## <a name="deployed-services-and-functionality"></a><span data-ttu-id="46ceb-122">已部署的服务和功能</span><span class="sxs-lookup"><span data-stu-id="46ceb-122">Deployed services and functionality</span></span>
<span data-ttu-id="46ceb-123">Microsoft 365当你部署更多受支持的服务时，Defender 提供更好的可见性、关联和修正。</span><span class="sxs-lookup"><span data-stu-id="46ceb-123">Microsoft 365 Defender provides better visibility, correlation, and remediation as you deploy more supported services.</span></span>

### <a name="benefits-of-full-deployment"></a><span data-ttu-id="46ceb-124">完整部署的好处</span><span class="sxs-lookup"><span data-stu-id="46ceb-124">Benefits of full deployment</span></span>
<span data-ttu-id="46ceb-125">若要获得 Defender 的完整Microsoft 365，我们建议部署所有受支持的服务。</span><span class="sxs-lookup"><span data-stu-id="46ceb-125">To get the complete benefits of Microsoft 365 Defender, we recommend deploying all supported services.</span></span> <span data-ttu-id="46ceb-126">以下是完整部署的一些关键优势：</span><span class="sxs-lookup"><span data-stu-id="46ceb-126">Here are some of the key benefits of full deployment:</span></span>
- <span data-ttu-id="46ceb-127">根据来自所有可用传感器和特定于服务的分析功能发出的警报和事件信号来标识并关联事件</span><span class="sxs-lookup"><span data-stu-id="46ceb-127">Incidents are identified and correlated based on alerts and event signals from all available sensors and service-specific analysis capabilities</span></span>
- <span data-ttu-id="46ceb-128">AIR (自动调查和) 手册适用于各种实体类型，包括设备、邮箱和用户帐户</span><span class="sxs-lookup"><span data-stu-id="46ceb-128">Automated investigation and remediation (AIR) playbooks apply across various entity types, including devices, mailboxes, and user accounts</span></span>
- <span data-ttu-id="46ceb-129">可以针对设备、邮箱和其他实体的事件和实体数据查询更全面的高级搜寻架构</span><span class="sxs-lookup"><span data-stu-id="46ceb-129">A more comprehensive advanced hunting schema can be queried for event and entity data from devices, mailboxes, and other entities</span></span>

### <a name="limited-deployment-scenarios"></a><span data-ttu-id="46ceb-130">有限的部署方案</span><span class="sxs-lookup"><span data-stu-id="46ceb-130">Limited deployment scenarios</span></span>
<span data-ttu-id="46ceb-131">您部署的每个受支持的服务都提供一组极其丰富的原始信号和相关信息。</span><span class="sxs-lookup"><span data-stu-id="46ceb-131">Each supported service that you deploy provides an extremely rich set of raw signals as well as correlated information.</span></span> <span data-ttu-id="46ceb-132">尽管有限的部署不会导致 Microsoft 365 Defender 功能关闭，但它提供跨终结点、应用、数据和标识的全面可见性的能力会受到影响。</span><span class="sxs-lookup"><span data-stu-id="46ceb-132">While limited deployment doesn’t cause Microsoft 365 Defender functionality to turn off, its ability to provide comprehensive visibility across your endpoints, apps, data, and identities is affected.</span></span> <span data-ttu-id="46ceb-133">同时，任何修正功能仅适用于可通过已部署的服务管理的实体。</span><span class="sxs-lookup"><span data-stu-id="46ceb-133">At the same time, any remediation capabilities only apply to entities that can be managed by the services you’ve deployed.</span></span>

<span data-ttu-id="46ceb-134">下表列出了每个受支持的服务如何提供其他数据、通过关联数据获取其他见解的机会，以及更好的修正和响应功能。</span><span class="sxs-lookup"><span data-stu-id="46ceb-134">The table below lists how each supported service provides additional data, opportunities to obtain additional insight by correlating the data, and better remediation and response capabilities.</span></span>

| <span data-ttu-id="46ceb-135">服务</span><span class="sxs-lookup"><span data-stu-id="46ceb-135">Service</span></span> | <span data-ttu-id="46ceb-136">数据 (信号&相关信息) </span><span class="sxs-lookup"><span data-stu-id="46ceb-136">Data (signals & correlated info)</span></span> | <span data-ttu-id="46ceb-137">修正&响应范围</span><span class="sxs-lookup"><span data-stu-id="46ceb-137">Remediation & response scope</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="46ceb-138">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="46ceb-138">Microsoft Defender for Endpoint</span></span> | <span data-ttu-id="46ceb-139">- 终结点状态和原始事件</span><span class="sxs-lookup"><span data-stu-id="46ceb-139">- Endpoint states and raw events</span></span><br /><span data-ttu-id="46ceb-140">- 终结点检测和警报，包括防病毒、EDR、攻击面减少</span><span class="sxs-lookup"><span data-stu-id="46ceb-140">- Endpoint detections and alerts, including antivirus, EDR, attack surface reduction</span></span><br /><span data-ttu-id="46ceb-141">- 有关在终结点上观测到的文件和其他实体的信息</span><span class="sxs-lookup"><span data-stu-id="46ceb-141">- Info on files and other entities observed on endpoints</span></span> | <span data-ttu-id="46ceb-142">终结点</span><span class="sxs-lookup"><span data-stu-id="46ceb-142">Endpoints</span></span> |
|<span data-ttu-id="46ceb-143">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="46ceb-143">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="46ceb-144">- 邮件和邮箱状态以及原始事件</span><span class="sxs-lookup"><span data-stu-id="46ceb-144">- Mail and mailbox states and raw events</span></span><br /><span data-ttu-id="46ceb-145">- 电子邮件、附件和链接检测</span><span class="sxs-lookup"><span data-stu-id="46ceb-145">- Email, attachment, and link detections</span></span> | <span data-ttu-id="46ceb-146">- 邮箱</span><span class="sxs-lookup"><span data-stu-id="46ceb-146">- Mailboxes</span></span><br /><span data-ttu-id="46ceb-147">- Microsoft 365帐户</span><span class="sxs-lookup"><span data-stu-id="46ceb-147">- Microsoft 365 accounts</span></span> |
| <span data-ttu-id="46ceb-148">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="46ceb-148">Microsoft Defender for Identity</span></span> | <span data-ttu-id="46ceb-149">- Active Directory 信号，包括身份验证事件</span><span class="sxs-lookup"><span data-stu-id="46ceb-149">- Active Directory signals, including authentication events</span></span><br /><span data-ttu-id="46ceb-150">- 与标识相关的行为检测</span><span class="sxs-lookup"><span data-stu-id="46ceb-150">- Identity-related behavioral detections</span></span> | <span data-ttu-id="46ceb-151">身份</span><span class="sxs-lookup"><span data-stu-id="46ceb-151">Identities</span></span> |
| <span data-ttu-id="46ceb-152">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="46ceb-152">Microsoft Cloud App Security</span></span> | <span data-ttu-id="46ceb-153">- 检测卷影 IT (未) </span><span class="sxs-lookup"><span data-stu-id="46ceb-153">- Detection of unsanctioned cloud apps and services (shadow IT)</span></span><br /><span data-ttu-id="46ceb-154">- 向云应用公开数据</span><span class="sxs-lookup"><span data-stu-id="46ceb-154">- Exposure of data to cloud apps</span></span><br /><span data-ttu-id="46ceb-155">- 与云应用关联的威胁活动</span><span class="sxs-lookup"><span data-stu-id="46ceb-155">- Threat activity associated with cloud apps</span></span> | <span data-ttu-id="46ceb-156">云应用</span><span class="sxs-lookup"><span data-stu-id="46ceb-156">Cloud apps</span></span> |

## <a name="deploy-the-services"></a><span data-ttu-id="46ceb-157">部署服务</span><span class="sxs-lookup"><span data-stu-id="46ceb-157">Deploy the services</span></span>
<span data-ttu-id="46ceb-158">部署每个服务通常需要预配到租户和一些初始配置。</span><span class="sxs-lookup"><span data-stu-id="46ceb-158">Deploying each service typically requires provisioning to your tenant and some initial configuration.</span></span> <span data-ttu-id="46ceb-159">请参阅下表，了解如何部署其中每个服务。</span><span class="sxs-lookup"><span data-stu-id="46ceb-159">See the following table to understand how each of these services are deployed.</span></span>

| <span data-ttu-id="46ceb-160">服务</span><span class="sxs-lookup"><span data-stu-id="46ceb-160">Service</span></span> | <span data-ttu-id="46ceb-161">设置说明</span><span class="sxs-lookup"><span data-stu-id="46ceb-161">Provisioning instructions</span></span> | <span data-ttu-id="46ceb-162">初始配置</span><span class="sxs-lookup"><span data-stu-id="46ceb-162">Initial configuration</span></span> |
| ------ | ------ | ------ |
| <span data-ttu-id="46ceb-163">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="46ceb-163">Microsoft Defender for Endpoint</span></span> | [<span data-ttu-id="46ceb-164">Microsoft Defender for Endpoint 部署指南</span><span class="sxs-lookup"><span data-stu-id="46ceb-164">Microsoft Defender for Endpoint deployment guide</span></span>](../defender-endpoint/deployment-phases.md) | <span data-ttu-id="46ceb-165">*请参阅预配说明*</span><span class="sxs-lookup"><span data-stu-id="46ceb-165">*See provisioning instructions*</span></span> |
|<span data-ttu-id="46ceb-166">Microsoft Defender for Office 365</span><span class="sxs-lookup"><span data-stu-id="46ceb-166">Microsoft Defender for Office 365</span></span> | <span data-ttu-id="46ceb-167">*无，使用 Office 365*</span><span class="sxs-lookup"><span data-stu-id="46ceb-167">*None, provisioned with Office 365*</span></span> | [<span data-ttu-id="46ceb-168">配置 Microsoft Defender for Office 365 策略</span><span class="sxs-lookup"><span data-stu-id="46ceb-168">Configure Microsoft Defender for Office 365 policies</span></span>](/microsoft-365/security/office-365-security/defender-for-office-365#configure-atp-policies) |
| <span data-ttu-id="46ceb-169">Microsoft Defender for Identity</span><span class="sxs-lookup"><span data-stu-id="46ceb-169">Microsoft Defender for Identity</span></span> | [<span data-ttu-id="46ceb-170">快速入门：创建 Microsoft Defender for Identity 实例</span><span class="sxs-lookup"><span data-stu-id="46ceb-170">Quickstart: Create your Microsoft Defender for Identity instance</span></span>](/azure-advanced-threat-protection/install-atp-step1) | <span data-ttu-id="46ceb-171">*请参阅预配说明*</span><span class="sxs-lookup"><span data-stu-id="46ceb-171">*See provisioning instructions*</span></span> |
| <span data-ttu-id="46ceb-172">Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="46ceb-172">Microsoft Cloud App Security</span></span> | <span data-ttu-id="46ceb-173">*无*</span><span class="sxs-lookup"><span data-stu-id="46ceb-173">*None*</span></span> | [<span data-ttu-id="46ceb-174">快速入门：快速入门Microsoft Cloud App Security</span><span class="sxs-lookup"><span data-stu-id="46ceb-174">Quickstart: Get started with Microsoft Cloud App Security</span></span>](/cloud-app-security/getting-started-with-cloud-app-security) |

<span data-ttu-id="46ceb-175">部署支持的服务后，打开 defender [Microsoft 365 Defender。](m365d-enable.md)</span><span class="sxs-lookup"><span data-stu-id="46ceb-175">Once you’ve deployed the supported services, [turn on Microsoft 365 Defender](m365d-enable.md).</span></span>

## <a name="related-topics"></a><span data-ttu-id="46ceb-176">相关主题</span><span class="sxs-lookup"><span data-stu-id="46ceb-176">Related topics</span></span>

- [<span data-ttu-id="46ceb-177">Microsoft 365Defender 概述</span><span class="sxs-lookup"><span data-stu-id="46ceb-177">Microsoft 365 Defender overview</span></span>](microsoft-365-defender.md)
- [<span data-ttu-id="46ceb-178">打开 Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="46ceb-178">Turn on Microsoft 365 Defender</span></span>](m365d-enable.md)
- [<span data-ttu-id="46ceb-179">Microsoft Defender for Endpoint 概述</span><span class="sxs-lookup"><span data-stu-id="46ceb-179">Microsoft Defender for Endpoint overview</span></span>](../defender-endpoint/microsoft-defender-endpoint.md)
- [<span data-ttu-id="46ceb-180">Microsoft Defender for Office 365 概述</span><span class="sxs-lookup"><span data-stu-id="46ceb-180">Microsoft Defender for Office 365 overview</span></span>](../office-365-security/defender-for-office-365.md)
- [<span data-ttu-id="46ceb-181">Microsoft Cloud App Security 概述</span><span class="sxs-lookup"><span data-stu-id="46ceb-181">Microsoft Cloud App Security overview</span></span>](/cloud-app-security/what-is-cloud-app-security)
- [<span data-ttu-id="46ceb-182">Microsoft Defender for Identity 概述</span><span class="sxs-lookup"><span data-stu-id="46ceb-182">Microsoft Defender for Identity overview</span></span>](/azure-advanced-threat-protection/what-is-atp)
