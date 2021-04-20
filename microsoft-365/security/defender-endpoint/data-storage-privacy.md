---
title: Microsoft Defender for Endpoint 数据存储和隐私
description: 了解 Microsoft Defender for Endpoint 如何处理它收集的隐私和数据。
keywords: Microsoft Defender for Endpoint， Microsoft Defender for Endpoint， 数据存储和隐私， 存储， 隐私， 许可， 地理位置， 数据保留， 数据
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
ms.technology: mde
ms.openlocfilehash: 2b191c4a24ce170d23fc3d9e43293cc7bbe59e80
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51892813"
---
# <a name="microsoft-defender-for-endpoint-data-storage-and-privacy"></a><span data-ttu-id="86290-104">Microsoft Defender for Endpoint 数据存储和隐私</span><span class="sxs-lookup"><span data-stu-id="86290-104">Microsoft Defender for Endpoint data storage and privacy</span></span>

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

<span data-ttu-id="86290-105">**适用于：**</span><span class="sxs-lookup"><span data-stu-id="86290-105">**Applies to:**</span></span>
- [<span data-ttu-id="86290-106">Microsoft Defender for Endpoint</span><span class="sxs-lookup"><span data-stu-id="86290-106">Microsoft Defender for Endpoint</span></span>](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [<span data-ttu-id="86290-107">Microsoft 365 Defender</span><span class="sxs-lookup"><span data-stu-id="86290-107">Microsoft 365 Defender</span></span>](https://go.microsoft.com/fwlink/?linkid=2118804)

><span data-ttu-id="86290-108">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="86290-108">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="86290-109">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="86290-109">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

<span data-ttu-id="86290-110">本部分涵盖有关 Defender for Endpoint 的隐私和数据处理的一些最常见的问题。</span><span class="sxs-lookup"><span data-stu-id="86290-110">This section covers some of the most frequently asked questions regarding privacy and data handling for Defender for Endpoint.</span></span>
> [!NOTE]
> <span data-ttu-id="86290-111">本文档介绍与 Defender for Endpoint 相关的数据存储和隐私详细信息。</span><span class="sxs-lookup"><span data-stu-id="86290-111">This document explains the data storage and privacy details related to Defender for Endpoint.</span></span> <span data-ttu-id="86290-112">有关适用于终结点的 Defender 以及其他产品和服务（如 Microsoft Defender 防病毒和 Windows 10） [的信息](https://go.microsoft.com/fwlink/?linkid=827576)，请参阅 Microsoft 隐私声明。</span><span class="sxs-lookup"><span data-stu-id="86290-112">For more information related to Defender for Endpoint and other products and services like Microsoft Defender Antivirus and Windows 10, see [Microsoft Privacy Statement](https://go.microsoft.com/fwlink/?linkid=827576).</span></span> <span data-ttu-id="86290-113">有关详细信息，请参阅 [Windows 10](https://go.microsoft.com/fwlink/?linkid=827577) 隐私常见问题解答。</span><span class="sxs-lookup"><span data-stu-id="86290-113">See also [Windows 10 privacy FAQ](https://go.microsoft.com/fwlink/?linkid=827577) for more information.</span></span>


## <a name="what-data-does-microsoft-defender-for-endpoint-collect"></a><span data-ttu-id="86290-114">Microsoft Defender for Endpoint 会收集哪些数据？</span><span class="sxs-lookup"><span data-stu-id="86290-114">What data does Microsoft Defender for Endpoint collect?</span></span>

<span data-ttu-id="86290-115">Microsoft Defender for Endpoint 将在特定于服务的客户专用和隔离租户中收集并存储已配置设备的信息，以用于管理、跟踪和报告目的。</span><span class="sxs-lookup"><span data-stu-id="86290-115">Microsoft Defender for Endpoint will collect and store information from your configured devices in a customer dedicated and segregated tenant specific to the service for administration, tracking, and reporting purposes.</span></span> 

<span data-ttu-id="86290-116">收集的信息包括文件数据 (如文件名、大小和哈希) 、进程数据 (正在运行的进程、哈希) 、注册表数据、网络连接数据 (主机 IP 和端口) 以及设备详细信息 (例如设备标识符、名称和操作系统版本) 。</span><span class="sxs-lookup"><span data-stu-id="86290-116">Information collected includes file data (such as file names, sizes, and hashes), process data (running processes, hashes), registry data, network connection data (host IPs and ports), and device details (such as device identifiers, names, and the operating system version).</span></span>

<span data-ttu-id="86290-117">Microsoft 在 Microsoft Azure 中安全地存储此数据，并依据 Microsoft 隐私做法和 [Microsoft 信任中心策略进行维护](https://go.microsoft.com/fwlink/?linkid=827578)。</span><span class="sxs-lookup"><span data-stu-id="86290-117">Microsoft stores this data securely in Microsoft Azure and maintains it in accordance with Microsoft privacy practices and [Microsoft Trust Center policies](https://go.microsoft.com/fwlink/?linkid=827578).</span></span>

<span data-ttu-id="86290-118">此数据使 Defender for Endpoint 能够：</span><span class="sxs-lookup"><span data-stu-id="86290-118">This data enables Defender for Endpoint to:</span></span>
- <span data-ttu-id="86290-119">主动识别组织中 IA (攻击) IA</span><span class="sxs-lookup"><span data-stu-id="86290-119">Proactively identify indicators of attack (IOAs) in your organization</span></span>
- <span data-ttu-id="86290-120">如果检测到可能的攻击，生成警报</span><span class="sxs-lookup"><span data-stu-id="86290-120">Generate alerts if a possible attack was detected</span></span>
- <span data-ttu-id="86290-121">为安全操作提供与来自网络的威胁信号相关的设备、文件和 URL 的视图，使你可以调查和探索网络上是否存在安全威胁。</span><span class="sxs-lookup"><span data-stu-id="86290-121">Provide your security operations with a view into devices, files, and URLs related to threat signals from your network, enabling you to investigate and explore the presence of security threats on the network.</span></span>

<span data-ttu-id="86290-122">Microsoft 不会将你的数据用于广告。</span><span class="sxs-lookup"><span data-stu-id="86290-122">Microsoft does not use your data for advertising.</span></span>

## <a name="data-protection-and-encryption"></a><span data-ttu-id="86290-123">数据保护和加密</span><span class="sxs-lookup"><span data-stu-id="86290-123">Data protection and encryption</span></span>
<span data-ttu-id="86290-124">Defender for Endpoint 服务利用基于 Microsoft Azure 基础结构的一流数据保护技术。</span><span class="sxs-lookup"><span data-stu-id="86290-124">The Defender for Endpoint service utilizes state of the art data protection technologies which are based on Microsoft Azure infrastructure.</span></span> 

<span data-ttu-id="86290-125">我们的服务需要处理与数据保护相关的各个方面。</span><span class="sxs-lookup"><span data-stu-id="86290-125">There are various aspects relevant to data protection that our service takes care of.</span></span> <span data-ttu-id="86290-126">加密是最关键之一，它包括静态数据加密、进行中的加密和密钥保管库的密钥管理。</span><span class="sxs-lookup"><span data-stu-id="86290-126">Encryption is one of the most critical and it includes data encryption at rest, encryption in flight, and key management with Key Vault.</span></span> <span data-ttu-id="86290-127">有关 Defender for Endpoint 服务使用的其他技术详细信息，请参阅 [Azure 加密概述](https://docs.microsoft.com/azure/security/security-azure-encryption-overview)。</span><span class="sxs-lookup"><span data-stu-id="86290-127">For more information on other technologies used by the Defender for Endpoint service, see [Azure encryption overview](https://docs.microsoft.com/azure/security/security-azure-encryption-overview).</span></span> 

<span data-ttu-id="86290-128">在所有方案中，至少使用 256 位 [AES 加密对数据进行](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) 加密。</span><span class="sxs-lookup"><span data-stu-id="86290-128">In all scenarios, data is encrypted using 256-bit [AES encryption](https://en.wikipedia.org/wiki/Advanced_Encryption_Standard) at the minimum.</span></span>


## <a name="data-storage-location"></a><span data-ttu-id="86290-129">数据存储位置</span><span class="sxs-lookup"><span data-stu-id="86290-129">Data storage location</span></span>

<span data-ttu-id="86290-130">Defender for Endpoint 在欧盟、英国或美国的 Microsoft Azure 数据中心中运行。</span><span class="sxs-lookup"><span data-stu-id="86290-130">Defender for Endpoint operates in the Microsoft Azure datacenters in the European Union, the United Kingdom, or in the United States.</span></span> <span data-ttu-id="86290-131">该服务收集的客户数据存储在： () 预配期间标识的租户地理位置; (b) 如果 Defender for Endpoint 使用另一个 Microsoft 联机服务处理此类数据，即其他联机服务的数据存储规则定义的地理位置。</span><span class="sxs-lookup"><span data-stu-id="86290-131">Customer data collected by the service may be stored in: (a) the geo-location of the tenant as identified during provisioning or, (b) if Defender for Endpoint uses another Microsoft online service to process such data, the geolocation as defined by the data storage rules of that other online service.</span></span>

<span data-ttu-id="86290-132">假名形式的客户数据也可以存储在美国的中央存储和处理系统中。</span><span class="sxs-lookup"><span data-stu-id="86290-132">Customer data in pseudonymized form may also be stored in the central storage and processing systems in the United States.</span></span>

<span data-ttu-id="86290-133">配置后，你无法更改数据存储的位置。</span><span class="sxs-lookup"><span data-stu-id="86290-133">Once configured, you cannot change the location where your data is stored.</span></span> <span data-ttu-id="86290-134">这提供了一种便捷方式，通过主动选择数据将驻留的地理位置来最大程度地降低合规性风险。</span><span class="sxs-lookup"><span data-stu-id="86290-134">This provides a convenient way to minimize compliance risk by actively selecting the geographic locations where your data will reside.</span></span> 

## <a name="is-my-data-isolated-from-other-customer-data"></a><span data-ttu-id="86290-135">我的数据是否与其他客户数据隔离？</span><span class="sxs-lookup"><span data-stu-id="86290-135">Is my data isolated from other customer data?</span></span>
<span data-ttu-id="86290-136">可以，数据通过访问身份验证和基于客户标识符的逻辑分离进行隔离。</span><span class="sxs-lookup"><span data-stu-id="86290-136">Yes, your data is isolated through access authentication and logical segregation based on customer identifier.</span></span> <span data-ttu-id="86290-137">每个客户只能访问从其自己的组织收集的数据和 Microsoft 提供的一般数据。</span><span class="sxs-lookup"><span data-stu-id="86290-137">Each customer can only access data collected from its own organization and generic data that Microsoft provides.</span></span>

## <a name="how-does-microsoft-prevent-malicious-insider-activities-and-abuse-of-high-privilege-roles"></a><span data-ttu-id="86290-138">Microsoft 如何防止恶意内部活动和高特权角色的滥用？</span><span class="sxs-lookup"><span data-stu-id="86290-138">How does Microsoft prevent malicious insider activities and abuse of high privilege roles?</span></span>

<span data-ttu-id="86290-139">根据设计，Microsoft 开发人员和管理员具有足够的权限来履行分配的职责，以运营并改进服务。</span><span class="sxs-lookup"><span data-stu-id="86290-139">Microsoft developers and administrators have, by design, been given sufficient privileges to carry out their assigned duties to operate and evolve the service.</span></span> <span data-ttu-id="86290-140">Microsoft 部署了预防、检测以及反应控件的组合，包括以下机制，以帮助防止未经授权的开发人员和/或管理活动：</span><span class="sxs-lookup"><span data-stu-id="86290-140">Microsoft deploys combinations of preventive, detective, and reactive controls including the following mechanisms to help protect against unauthorized developer and/or administrative activity:</span></span>

- <span data-ttu-id="86290-141">对敏感数据的严格访问控制</span><span class="sxs-lookup"><span data-stu-id="86290-141">Tight access control to sensitive data</span></span>
- <span data-ttu-id="86290-142">显著增强恶意活动的独立检测的控件组合</span><span class="sxs-lookup"><span data-stu-id="86290-142">Combinations of controls that greatly enhance independent detection of malicious activity</span></span>
- <span data-ttu-id="86290-143">多个级别的监视、日志记录和报告</span><span class="sxs-lookup"><span data-stu-id="86290-143">Multiple levels of monitoring, logging, and reporting</span></span>

<span data-ttu-id="86290-144">此外，Microsoft 对某些操作人员执行后台验证检查，并限制根据后台验证级别对应用程序、系统和网络基础结构的访问。</span><span class="sxs-lookup"><span data-stu-id="86290-144">Additionally, Microsoft conducts background verification checks of certain operations personnel, and limits access to applications, systems, and network infrastructure in proportion to the level of background verification.</span></span> <span data-ttu-id="86290-145">当运营人员在履行职责时需要访问客户的帐户或相关信息时，他们会遵循正式的流程。</span><span class="sxs-lookup"><span data-stu-id="86290-145">Operations personnel follow a formal process when they are required to access a customer’s account or related information in the performance of their duties.</span></span>

<span data-ttu-id="86290-146">Microsoft Azure 政府数据中心中部署的服务的数据访问权限仅授予经过筛选和批准以处理符合某些政府法规和要求（如 FedRAMP、NIST 800.171 (DIB) 、ITAR、IRS 1075、DoD L4 和 CJIS）的操作人员。</span><span class="sxs-lookup"><span data-stu-id="86290-146">Access to data for services deployed in Microsoft Azure Government data centers is only granted to operating personnel who have been screened and approved to handle data that is subject to certain government regulations and requirements, such as FedRAMP, NIST 800.171 (DIB), ITAR, IRS 1075, DoD L4, and CJIS.</span></span>


## <a name="is-data-shared-with-other-customers"></a><span data-ttu-id="86290-147">数据是否与其他客户共享？</span><span class="sxs-lookup"><span data-stu-id="86290-147">Is data shared with other customers?</span></span>
<span data-ttu-id="86290-148">否。</span><span class="sxs-lookup"><span data-stu-id="86290-148">No.</span></span> <span data-ttu-id="86290-149">客户数据与其他客户隔离，不共享。</span><span class="sxs-lookup"><span data-stu-id="86290-149">Customer data is isolated from other customers and is not shared.</span></span> <span data-ttu-id="86290-150">但是，有关由 Microsoft 处理产生的数据（不包含任何特定于客户的数据）的见解可能会与其他客户共享。</span><span class="sxs-lookup"><span data-stu-id="86290-150">However, insights on the data resulting from Microsoft processing, and which don’t contain any customer-specific data, might be shared with other customers.</span></span> <span data-ttu-id="86290-151">每个客户只能访问从其自己的组织收集的数据和 Microsoft 提供的一般数据。</span><span class="sxs-lookup"><span data-stu-id="86290-151">Each customer can only access data collected from its own organization and generic data that Microsoft provides.</span></span>

## <a name="how-long-will-microsoft-store-my-data-what-is-microsofts-data-retention-policy"></a><span data-ttu-id="86290-152">Microsoft 将存储我的数据多久？</span><span class="sxs-lookup"><span data-stu-id="86290-152">How long will Microsoft store my data?</span></span> <span data-ttu-id="86290-153">什么是 Microsoft 的数据保留策略？</span><span class="sxs-lookup"><span data-stu-id="86290-153">What is Microsoft’s data retention policy?</span></span>
<span data-ttu-id="86290-154">**在服务载入时**</span><span class="sxs-lookup"><span data-stu-id="86290-154">**At service onboarding**</span></span><br>
<span data-ttu-id="86290-155">你可以为数据选择数据保留策略。</span><span class="sxs-lookup"><span data-stu-id="86290-155">You can choose the data retention policy for your data.</span></span> <span data-ttu-id="86290-156">这将确定适用于终结点的 Window Defender 存储你的数据多久。</span><span class="sxs-lookup"><span data-stu-id="86290-156">This determines how long Window Defender for Endpoint will store your data.</span></span> <span data-ttu-id="86290-157">可以灵活地选择一个月到六个月，以满足公司的法规合规性需求。</span><span class="sxs-lookup"><span data-stu-id="86290-157">There’s a flexibility of choosing in the range of one month to six months to meet your company’s regulatory compliance needs.</span></span>

<span data-ttu-id="86290-158">**在合同终止或到期时**</span><span class="sxs-lookup"><span data-stu-id="86290-158">**At contract termination or expiration**</span></span><br>
<span data-ttu-id="86290-159">当许可证在宽限期或暂停模式下时，你的数据将保留，并且将可供你使用。</span><span class="sxs-lookup"><span data-stu-id="86290-159">Your data will be kept and will be available to you while the license is under grace period or suspended mode.</span></span> <span data-ttu-id="86290-160">在此期限结束时，该数据将从 Microsoft 系统中清除，使其不可恢复，不得晚于合同终止或到期的 180 天。</span><span class="sxs-lookup"><span data-stu-id="86290-160">At the end of this period, that data will be erased from Microsoft’s systems to make it unrecoverable, no later than 180 days from contract termination or expiration.</span></span>

<span data-ttu-id="86290-161">**高级搜寻数据**</span><span class="sxs-lookup"><span data-stu-id="86290-161">**Advanced Hunting data**</span></span><br>
<span data-ttu-id="86290-162">高级搜寻是一种基于查询的威胁搜寻工具，可用于浏览多达 30 天的原始数据。</span><span class="sxs-lookup"><span data-stu-id="86290-162">Advanced hunting is a query-based threat-hunting tool that lets you explore up to 30 days of raw data.</span></span>


## <a name="can-microsoft-help-us-maintain-regulatory-compliance"></a><span data-ttu-id="86290-163">Microsoft 可以帮助我们维护法规合规性吗？</span><span class="sxs-lookup"><span data-stu-id="86290-163">Can Microsoft help us maintain regulatory compliance?</span></span>

<span data-ttu-id="86290-164">Microsoft 为客户提供有关 Microsoft 安全与合规计划的详细信息，包括审核报告和合规性包，帮助客户根据自己的法律和法规要求评估适用于 Endpoint 服务的 Defender。</span><span class="sxs-lookup"><span data-stu-id="86290-164">Microsoft provides customers with detailed information about Microsoft's security and compliance programs, including audit reports and compliance packages, to help customers assess Defender for Endpoint services against their own legal and regulatory requirements.</span></span> <span data-ttu-id="86290-165">Defender for Endpoint 已获得许多认证，包括 ISO、SOC、FedRAMP High 和 PCI，并继续获得其他特定于国家、区域和行业的认证。</span><span class="sxs-lookup"><span data-stu-id="86290-165">Defender for Endpoint has achieved a number of certifications including ISO, SOC, FedRAMP High, and PCI and continues to pursue additional national, regional and industry-specific certifications.</span></span>

<span data-ttu-id="86290-166">通过为客户提供合规、独立验证的服务，Microsoft 可以让客户更轻松地实现基础结构和所运行的应用程序的合规性。</span><span class="sxs-lookup"><span data-stu-id="86290-166">By providing customers with compliant, independently verified services, Microsoft makes it easier for customers to achieve compliance for the infrastructure and applications they run.</span></span>

<span data-ttu-id="86290-167">有关 Defender for Endpoint 认证报告详细信息，请参阅 [Microsoft 信任中心](https://servicetrust.microsoft.com/)。</span><span class="sxs-lookup"><span data-stu-id="86290-167">For more information on the Defender for Endpoint certification reports, see [Microsoft Trust Center](https://servicetrust.microsoft.com/).</span></span> 

><span data-ttu-id="86290-168">想要体验适用于终结点的 Defender？</span><span class="sxs-lookup"><span data-stu-id="86290-168">Want to experience Defender for Endpoint?</span></span> [<span data-ttu-id="86290-169">注册免费试用版。</span><span class="sxs-lookup"><span data-stu-id="86290-169">Sign up for a free trial.</span></span>](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-datastorage-belowfoldlink) 
