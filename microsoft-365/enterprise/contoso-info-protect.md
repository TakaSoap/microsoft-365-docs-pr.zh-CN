---
title: Contoso Corporation 的信息保护
author: JoeDavies-MSFT
f1.keywords:
- NOCSH
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企业版中的信息保护功能来保护其在云中的数字资产。
ms.openlocfilehash: 137e6ff499ba8fb119c696dba9337307876ee0c2
ms.sourcegitcommit: 47c45bd81afdc4867ff2980ced3df31dbad92b84
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/16/2020
ms.locfileid: "44268406"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="0315f-103">Contoso Corporation 的信息保护</span><span class="sxs-lookup"><span data-stu-id="0315f-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="0315f-p101">Contoso 在信息安全和保护方面非常严谨。例如，在描述产品设计和专有制造技术时，其知识产权的泄露或破坏将使他们在竞争中处于劣势。</span><span class="sxs-lookup"><span data-stu-id="0315f-p101">Contoso is serious about their information security and protection. For example, leakage or destruction of their intellectual property describing product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="0315f-106">在将敏感和最有价值的数字资产转移到云之前，他们将确保本地信息分类和保护要求在 Microsoft 365 企业版基于云的服务中得到支持和实现。</span><span class="sxs-lookup"><span data-stu-id="0315f-106">Before moving their sensitive and most valuable digital assets to the cloud, they made sure that their on-premises information classification and protection requirements were supported and implemented in the cloud-based services of Microsoft 365 Enterprise.</span></span>

## <a name="contosos-data-security-classification"></a><span data-ttu-id="0315f-107">Contoso 的数据安全分类</span><span class="sxs-lookup"><span data-stu-id="0315f-107">Contoso's data security classification</span></span>

<span data-ttu-id="0315f-108">Contoso 执行数据分析，并确定以下级别。</span><span class="sxs-lookup"><span data-stu-id="0315f-108">Contoso performed an analysis of their data and determined the following levels.</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="0315f-109">**1 级：基准**</span><span class="sxs-lookup"><span data-stu-id="0315f-109">**Level 1: Baseline**</span></span> | <span data-ttu-id="0315f-110">**2 级：敏感**</span><span class="sxs-lookup"><span data-stu-id="0315f-110">**Level 2: Sensitive**</span></span> | <span data-ttu-id="0315f-111">**3 级：高度管控**</span><span class="sxs-lookup"><span data-stu-id="0315f-111">**Level 3: Highly regulated**</span></span> |
| <span data-ttu-id="0315f-112">数据已加密，并且仅供已通过身份验证的用户使用。</span><span class="sxs-lookup"><span data-stu-id="0315f-112">Data is encrypted and available only to authenticated users.</span></span> <BR> <BR> <span data-ttu-id="0315f-p102">向存储在本地和基于云的存储空间和工作负载（例如 Office 365）中的所有数据提供。驻留在服务中和在服务与客户端设备之间传输时，数据处于加密状态。</span><span class="sxs-lookup"><span data-stu-id="0315f-p102">Provided for all data stored on-premises and in cloud-based storage and workloads, such as Office 365. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR> <span data-ttu-id="0315f-115">1 级数据的示例为正常的业务通信（电子邮件）和供管理、销售和支持工作人员使用的文件。</span><span class="sxs-lookup"><span data-stu-id="0315f-115">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="0315f-116">1 级再加上强身份验证和数据丢失防护。</span><span class="sxs-lookup"><span data-stu-id="0315f-116">Level 1 plus strong authentication and data loss protection.</span></span> <BR> <BR> <span data-ttu-id="0315f-117">强身份验证包括具有短信验证的 Azure 多重身份验证 (MFA)。</span><span class="sxs-lookup"><span data-stu-id="0315f-117">Strong authentication includes Azure Multi-Factor Authentication (MFA) with SMS validation.</span></span> <span data-ttu-id="0315f-118">数据丢失防护可确保敏感或关键信息不会在 Microsoft 云外部传播。</span><span class="sxs-lookup"><span data-stu-id="0315f-118">Data loss prevention ensures that sensitive or critical information does not travel outside the Microsoft cloud.</span></span> <BR><BR> <span data-ttu-id="0315f-119">2 级数据的示例包括财务和法律信息，以及新产品的研发数据。</span><span class="sxs-lookup"><span data-stu-id="0315f-119">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="0315f-120">2 级再加上最高级别的加密、身份验证和审核。</span><span class="sxs-lookup"><span data-stu-id="0315f-120">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span> <BR> <BR>  <span data-ttu-id="0315f-121">对静态和云中的数据采用最高级别的加密，遵循区域法规，并结合具有智能卡以及精细审核和警报的 MFA。</span><span class="sxs-lookup"><span data-stu-id="0315f-121">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with MFA with smart cards and granular auditing and alerting.</span></span> <BR> <BR> <span data-ttu-id="0315f-122">3 级数据的示例是客户和合作伙伴的个人身份信息、产品工程规范以及专有的制造技术。</span><span class="sxs-lookup"><span data-stu-id="0315f-122">Examples of Level 3 data are customer and partner personally identifiable information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contosos-information-policies"></a><span data-ttu-id="0315f-123">Contoso 的信息策略</span><span class="sxs-lookup"><span data-stu-id="0315f-123">Contoso's information policies</span></span>
<span data-ttu-id="0315f-124">下表列出了 Contoso 的信息策略。</span><span class="sxs-lookup"><span data-stu-id="0315f-124">The following table lists Contoso's information policies.</span></span>

|||||
|:-------|:-----|:-----|:-----|
|  | <span data-ttu-id="0315f-125">**访问**</span><span class="sxs-lookup"><span data-stu-id="0315f-125">**Access**</span></span> | <span data-ttu-id="0315f-126">**数据保留**</span><span class="sxs-lookup"><span data-stu-id="0315f-126">**Data retention**</span></span> | <span data-ttu-id="0315f-127">**信息保护**</span><span class="sxs-lookup"><span data-stu-id="0315f-127">**Information protection**</span></span> |
| <span data-ttu-id="0315f-128">业务价值较低（1 级：基准）</span><span class="sxs-lookup"><span data-stu-id="0315f-128">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="0315f-129">允许所有人员访问</span><span class="sxs-lookup"><span data-stu-id="0315f-129">Allow access to all</span></span>  | <span data-ttu-id="0315f-130">6 个月</span><span class="sxs-lookup"><span data-stu-id="0315f-130">6 months</span></span> | <span data-ttu-id="0315f-131">使用加密。</span><span class="sxs-lookup"><span data-stu-id="0315f-131">Use encryption.</span></span> |
| <span data-ttu-id="0315f-132">业务价值中等（2 级：敏感）</span><span class="sxs-lookup"><span data-stu-id="0315f-132">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="0315f-133">允许 Contoso 员工、分包商和合作伙伴访问</span><span class="sxs-lookup"><span data-stu-id="0315f-133">Allow access to Contoso employees, subcontractors, and partners</span></span> <BR> <BR> <span data-ttu-id="0315f-134">使用 MFA、传输层安全性 (TLS) 和移动应用管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="0315f-134">Use MFA, Transport Layer Security (TLS), and Mobile Application Management (MAM).</span></span> | <span data-ttu-id="0315f-135">2 年</span><span class="sxs-lookup"><span data-stu-id="0315f-135">2 years</span></span>  | <span data-ttu-id="0315f-136">使用哈希值实现数据完整性。</span><span class="sxs-lookup"><span data-stu-id="0315f-136">Use hash values for data integrity.</span></span>  |
| <span data-ttu-id="0315f-137">高业务价值（3 级：高度管控）</span><span class="sxs-lookup"><span data-stu-id="0315f-137">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="0315f-138">允许工程设计和制造中的执行人员和潜在客户访问。</span><span class="sxs-lookup"><span data-stu-id="0315f-138">Allow access to executives and leads in engineering and manufacturing.</span></span> <BR> <BR> <span data-ttu-id="0315f-139">仅限托管网络设备的权限管理系统 (RMS)。</span><span class="sxs-lookup"><span data-stu-id="0315f-139">Rights Management System (RMS) with managed network devices only.</span></span>  | <span data-ttu-id="0315f-140">7 年</span><span class="sxs-lookup"><span data-stu-id="0315f-140">7 years</span></span>  | <span data-ttu-id="0315f-141">使用数字签名实现不可否认性。</span><span class="sxs-lookup"><span data-stu-id="0315f-141">Use digital signatures for non-repudiation.</span></span>  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a><span data-ttu-id="0315f-142">使用 Microsoft 365 企业版的 Contoso 信息保护路径</span><span class="sxs-lookup"><span data-stu-id="0315f-142">Contoso’s path to information protection with Microsoft 365 Enterprise</span></span>

<span data-ttu-id="0315f-143">Contoso 使用以下步骤为 Microsoft 365 企业版准备其信息保护要求：</span><span class="sxs-lookup"><span data-stu-id="0315f-143">Contoso used the following steps to prepare Microsoft 365 Enterprise for their information protection requirements:</span></span>

1. <span data-ttu-id="0315f-144">标识要保护的信息</span><span class="sxs-lookup"><span data-stu-id="0315f-144">Identified what information to protect</span></span>

   <span data-ttu-id="0315f-145">Contoso 对其现有数字资产进行了广泛审查，这些资产位于本地 SharePoint 网站和文件共享中，并对每一个资产都进行了分类。</span><span class="sxs-lookup"><span data-stu-id="0315f-145">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each one.</span></span>

2. <span data-ttu-id="0315f-146">确定数据级别的访问策略、保留策略和信息保护策略</span><span class="sxs-lookup"><span data-stu-id="0315f-146">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="0315f-147">Contoso 基于数据级别确定了详细的策略要求，这些要求被用于保护现有数字资产，因为它们被转移到了云中。</span><span class="sxs-lookup"><span data-stu-id="0315f-147">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="0315f-148">创建了敏感度标签以及它们对不同级别信息的设置</span><span class="sxs-lookup"><span data-stu-id="0315f-148">Created sensitivity labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="0315f-149">Contoso 为其数据级别创建了敏感度标签，其中包含加密、权限和水印等高度管控标签。</span><span class="sxs-lookup"><span data-stu-id="0315f-149">Contoso created sensitivity labels for their data levels, with their highly regulated label that includes encryption, permissions, and watermarks.</span></span>

4.  <span data-ttu-id="0315f-150">将数据从本地 SharePoint 网站和文件共享转移到新的 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="0315f-150">Moved data from on-premises SharePoint sites and file shares to their new SharePoint sites</span></span>

    <span data-ttu-id="0315f-151">迁移到新的 SharePoint 网站的文件继承了分配给该网站的默认保留标签。</span><span class="sxs-lookup"><span data-stu-id="0315f-151">The files migrated to the new SharePoint sites inherited the default retention labels assigned to the site.</span></span>

5.  <span data-ttu-id="0315f-152">培训员工如何对新文档使用敏感度标签，如何在创建新的 SharePoint 网站时与 Contoso IT 进行交互，以及如何始终在 SharePoint 网站上存储数字资产</span><span class="sxs-lookup"><span data-stu-id="0315f-152">Trained employees on how to use sensitivity labels for new documents, how to interact with Contoso IT when creating new SharePoint sites, and to always store digital assets on SharePoint sites</span></span>

    <span data-ttu-id="0315f-153">考虑到云信息保护过渡中最困难的部分，Contoso IT 和管理层需要改变组织员工的不良信息存储习惯，以始终在云中标记和存储其数字资产，避免使用本地文件共享，并且绝不使用第三方云存储设备或 U 盘。</span><span class="sxs-lookup"><span data-stu-id="0315f-153">Considered the hardest part of the information protection transition for the cloud, Contoso IT and management needed to change the bad information storage habits of the organization’s employees to always label and store their digital assets in the cloud, refrain from using on-premises file shares, and never use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="0315f-154">用于信息保护的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="0315f-154">Conditional Access policies for information protection</span></span>

<span data-ttu-id="0315f-155">与身份标识和移动设备管理基础结构结合使用，并作为他们推出 Exchange Online 和 SharePoint 的一部分，Contoso 配置了以下一组条件访问策略，并将其应用到相应的组：</span><span class="sxs-lookup"><span data-stu-id="0315f-155">In conjunction with their identity and mobile device management infrastructure and as part of their rollout of Exchange Online and SharePoint, Contoso configured the following set of Conditional Access policies and applied them to the appropriate groups:</span></span>

- [<span data-ttu-id="0315f-156">设备策略上的托管和非托管应用程序访问</span><span class="sxs-lookup"><span data-stu-id="0315f-156">Managed and unmanaged application access on devices policies</span></span>](identity-access-policies.md)
- [<span data-ttu-id="0315f-157">Exchange Online 访问策略</span><span class="sxs-lookup"><span data-stu-id="0315f-157">Exchange Online access policies</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="0315f-158">SharePoint 访问策略</span><span class="sxs-lookup"><span data-stu-id="0315f-158">SharePoint access policies</span></span>](sharepoint-file-access-policies.md)

<span data-ttu-id="0315f-159">此处是 Contoso 最终得到的信息保护策略集。</span><span class="sxs-lookup"><span data-stu-id="0315f-159">Here is Contoso's resulting set of policies for information protection.</span></span>

![设备、Exchange Online 和 SharePoint 条件访问策略](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
><span data-ttu-id="0315f-161">此外，Contoso 还配置了针对标识和登录的其他条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="0315f-161">Contoso also configured additional Conditional Access policies for identity and sign-in.</span></span> <span data-ttu-id="0315f-162">请参阅 [Contoso Corporation 的标识](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="0315f-162">See [Identity for the Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>
>

<span data-ttu-id="0315f-163">这些策略确保：</span><span class="sxs-lookup"><span data-stu-id="0315f-163">These policies ensure that:</span></span>

- <span data-ttu-id="0315f-164">应用保护政策定义哪些应用程序是允许的，以及它们可以使用组织数据执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="0315f-164">Apps are allowed and the actions they can take with your organization data are defined by app protection policies.</span></span>
- <span data-ttu-id="0315f-165">电脑和移动设备必须兼容。</span><span class="sxs-lookup"><span data-stu-id="0315f-165">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="0315f-166">Exchange Online 使用 Exchange Online 的 Office 365 邮件加密。</span><span class="sxs-lookup"><span data-stu-id="0315f-166">Exchange Online uses Office 365 message encryption for Exchange Online.</span></span>
- <span data-ttu-id="0315f-167">SharePoint 使用应用强制的限制。</span><span class="sxs-lookup"><span data-stu-id="0315f-167">SharePoint uses app enforced restrictions.</span></span>
- <span data-ttu-id="0315f-168">SharePoint 使用访问控制策略来实现非托管设备的仅浏览器访问或阻止其访问。</span><span class="sxs-lookup"><span data-stu-id="0315f-168">SharePoint uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a><span data-ttu-id="0315f-169">将 Microsoft 365 企业版功能映射到 Contoso 的数据级别</span><span class="sxs-lookup"><span data-stu-id="0315f-169">Mapping Microsoft 365 Enterprise features to Contoso's data levels</span></span>

<span data-ttu-id="0315f-170">下表展示了 Contoso 的数据级别与 Microsoft 365 企业版中的信息保护功能的对应关系。</span><span class="sxs-lookup"><span data-stu-id="0315f-170">The following table maps Contoso's data levels to information protection features in Microsoft 365 Enterprise.</span></span>

|||||
|:-------|:-----|:-----|:-----|
| | <span data-ttu-id="0315f-171">**Office 365**</span><span class="sxs-lookup"><span data-stu-id="0315f-171">**Office 365**</span></span> | <span data-ttu-id="0315f-172">**Windows 10 和 Microsoft 365 企业应用版**</span><span class="sxs-lookup"><span data-stu-id="0315f-172">**Windows 10 and Microsoft 365 Apps for enterprise**</span></span> | <span data-ttu-id="0315f-173">**EMS**</span><span class="sxs-lookup"><span data-stu-id="0315f-173">**EMS**</span></span> |
| <span data-ttu-id="0315f-174">1 级：基准</span><span class="sxs-lookup"><span data-stu-id="0315f-174">Level 1: Baseline</span></span>  | <span data-ttu-id="0315f-175">SharePoint 和 Exchange Online 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="0315f-175">SharePoint and Exchange Online Conditional Access policies</span></span> <BR> <span data-ttu-id="0315f-176">SharePoint 网站上的权限</span><span class="sxs-lookup"><span data-stu-id="0315f-176">Permissions on SharePoint sites</span></span> | <span data-ttu-id="0315f-177">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="0315f-177">Sensitivity labels</span></span> <BR> <span data-ttu-id="0315f-178">BitLocker</span><span class="sxs-lookup"><span data-stu-id="0315f-178">BitLocker</span></span> <BR> <span data-ttu-id="0315f-179">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="0315f-179">Windows Information Protection</span></span> | <span data-ttu-id="0315f-180">设备条件访问策略和移动应用管理策略</span><span class="sxs-lookup"><span data-stu-id="0315f-180">Device Conditional Access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="0315f-181">2 级：敏感</span><span class="sxs-lookup"><span data-stu-id="0315f-181">Level 2: Sensitive</span></span> | <span data-ttu-id="0315f-182">1 级再加上：</span><span class="sxs-lookup"><span data-stu-id="0315f-182">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="0315f-183">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="0315f-183">Sensitivity labels</span></span> <BR> <span data-ttu-id="0315f-184">SharePoint 网站上的 Microsoft 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="0315f-184">Microsoft 365 retention labels on SharePoint sites</span></span> <BR> <span data-ttu-id="0315f-185">用于 SharePoint 和 Exchange Online 的数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="0315f-185">Data Loss Prevention for SharePoint and Exchange Online</span></span> <BR> <span data-ttu-id="0315f-186">独立 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="0315f-186">Isolated SharePoint sites</span></span>  | <span data-ttu-id="0315f-187">1 级再加上：</span><span class="sxs-lookup"><span data-stu-id="0315f-187">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="0315f-188">数字资产上的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="0315f-188">Sensitivity labels on digital assets</span></span>  | <span data-ttu-id="0315f-189">1 级</span><span class="sxs-lookup"><span data-stu-id="0315f-189">Level 1</span></span> |
| <span data-ttu-id="0315f-190">3 级：高度管控</span><span class="sxs-lookup"><span data-stu-id="0315f-190">Level 3: Highly regulated</span></span> | <span data-ttu-id="0315f-191">2 级再加上：</span><span class="sxs-lookup"><span data-stu-id="0315f-191">Level 2 plus:</span></span> <BR><BR> <span data-ttu-id="0315f-192">针对商业机密信息的自带密钥 (BYOK) 加密和保护</span><span class="sxs-lookup"><span data-stu-id="0315f-192">Bring Your Own Key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="0315f-193">将 Azure Key Vault 用于与 Microsoft 365 服务交互的业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="0315f-193">Azure Key Vault for line of business applications that interact with Microsoft 365 services</span></span> | <span data-ttu-id="0315f-194">2 级</span><span class="sxs-lookup"><span data-stu-id="0315f-194">Level 2</span></span> | <span data-ttu-id="0315f-195">1 级</span><span class="sxs-lookup"><span data-stu-id="0315f-195">Level 1</span></span> |
|||||

<span data-ttu-id="0315f-196">此处是 Contoso 最终得到的信息保护配置。</span><span class="sxs-lookup"><span data-stu-id="0315f-196">Here is Contoso's resulting information protection configuration.</span></span>

![Contoso 最终得到的信息保护配置](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a><span data-ttu-id="0315f-198">后续步骤</span><span class="sxs-lookup"><span data-stu-id="0315f-198">Next step</span></span>

<span data-ttu-id="0315f-199">[请参阅](contoso-security-summary.md) Contoso 如何使用安全功能跨 Microsoft 365 企业版实现身份识别和访问管理、威胁防护、信息保护以及安全管理。</span><span class="sxs-lookup"><span data-stu-id="0315f-199">[See](contoso-security-summary.md) how Contoso has used the security features across Microsoft 365 Enterprise for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="0315f-200">另请参阅</span><span class="sxs-lookup"><span data-stu-id="0315f-200">See also</span></span>

[<span data-ttu-id="0315f-201">Microsoft 365 企业版信息保护</span><span class="sxs-lookup"><span data-stu-id="0315f-201">Information protection for Microsoft 365 Enterprise</span></span>](infoprotect-infrastructure.md)

[<span data-ttu-id="0315f-202">部署指南</span><span class="sxs-lookup"><span data-stu-id="0315f-202">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="0315f-203">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="0315f-203">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)


