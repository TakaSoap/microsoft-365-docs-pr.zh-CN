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
localization_priority: Normal
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用企业Microsoft 365中的信息保护功能，以确保其数字资产在云中的安全。
ms.openlocfilehash: 3bd778708e30253e53cc465e89f7b783141771de
ms.sourcegitcommit: 956176ed7c8b8427fdc655abcd1709d86da9447e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2021
ms.locfileid: "51051492"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="8020e-103">Contoso Corporation 的信息保护</span><span class="sxs-lookup"><span data-stu-id="8020e-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="8020e-104">Contoso 非常关心其信息安全。</span><span class="sxs-lookup"><span data-stu-id="8020e-104">Contoso is serious about their information security.</span></span> <span data-ttu-id="8020e-105">泄露或销毁描述其产品开发和专有制造技术的知识产权将使它们处于竞争劣势。</span><span class="sxs-lookup"><span data-stu-id="8020e-105">Leakage or destruction of intellectual property that describes their product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="8020e-106">在将敏感的数字资产迁移到云之前，Contoso 已确保本地信息分类和保护要求受 Microsoft 365 企业版基于云的服务支持。</span><span class="sxs-lookup"><span data-stu-id="8020e-106">Before moving their sensitive digital assets to the cloud, Contoso made sure that their on-premises information classification and protection requirements were supported by the cloud-based services of Microsoft 365 for enterprise.</span></span>

## <a name="contoso-data-security-classification"></a><span data-ttu-id="8020e-107">Contoso 数据安全分类</span><span class="sxs-lookup"><span data-stu-id="8020e-107">Contoso data security classification</span></span>

<span data-ttu-id="8020e-108">Contoso 对数据进行了分析，并确定了以下分类级别。</span><span class="sxs-lookup"><span data-stu-id="8020e-108">Contoso performed an analysis of their data and determined the following classification levels.</span></span>

| <span data-ttu-id="8020e-109">1 级：基准</span><span class="sxs-lookup"><span data-stu-id="8020e-109">Level 1: Baseline</span></span> | <span data-ttu-id="8020e-110">2 级：敏感</span><span class="sxs-lookup"><span data-stu-id="8020e-110">Level 2: Sensitive</span></span> | <span data-ttu-id="8020e-111">3 级：高度管控</span><span class="sxs-lookup"><span data-stu-id="8020e-111">Level 3: Highly regulated</span></span> |
|:-------|:-----|:-----|
| <span data-ttu-id="8020e-112">数据已加密，并且仅供已通过身份验证的用户使用。</span><span class="sxs-lookup"><span data-stu-id="8020e-112">Data is encrypted and available only to authenticated users.</span></span><BR> <BR> <span data-ttu-id="8020e-113">为本地和基于云的存储和工作负载中存储的所有数据提供。</span><span class="sxs-lookup"><span data-stu-id="8020e-113">Provided for all data stored on-premises and in cloud-based storage and workloads.</span></span> <span data-ttu-id="8020e-114">数据驻留在服务中以及服务与客户端设备之间传输时加密。</span><span class="sxs-lookup"><span data-stu-id="8020e-114">Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR><span data-ttu-id="8020e-115">1 级数据的示例为正常的业务通信（电子邮件）和供管理、销售和支持工作人员使用的文件。</span><span class="sxs-lookup"><span data-stu-id="8020e-115">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="8020e-116">1 级再加上强身份验证和数据丢失防护。</span><span class="sxs-lookup"><span data-stu-id="8020e-116">Level 1 plus strong authentication and data loss protection.</span></span><BR> <BR> <span data-ttu-id="8020e-117">强身份验证包括 Azure AD 多重 (身份验证) MFA 短信验证。</span><span class="sxs-lookup"><span data-stu-id="8020e-117">Strong authentication includes Azure AD Multi-Factor Authentication (MFA) with SMS validation.</span></span> <span data-ttu-id="8020e-118">数据丢失防护可确保敏感或关键信息不会在 Microsoft 云外部传输。</span><span class="sxs-lookup"><span data-stu-id="8020e-118">Data loss prevention ensures that sensitive or critical information doesn't travel outside the Microsoft cloud.</span></span><BR><BR><span data-ttu-id="8020e-119">2 级数据的示例包括财务和法律信息，以及新产品的研发数据。</span><span class="sxs-lookup"><span data-stu-id="8020e-119">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="8020e-120">2 级再加上最高级别的加密、身份验证和审核。</span><span class="sxs-lookup"><span data-stu-id="8020e-120">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span><BR><BR><span data-ttu-id="8020e-121">对静态和云中的数据采用最高级别的加密，遵循区域法规，并结合具有智能卡以及精细审核和警报的 MFA。</span><span class="sxs-lookup"><span data-stu-id="8020e-121">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with MFA with smart cards and granular auditing and alerting.</span></span><BR> <BR><span data-ttu-id="8020e-122">级别 3 数据的示例包括客户和合作伙伴个人信息、产品工程规范和专有制造技术。</span><span class="sxs-lookup"><span data-stu-id="8020e-122">Examples of Level 3 data are customer and partner personal information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contoso-information-policies"></a><span data-ttu-id="8020e-123">Contoso 信息策略</span><span class="sxs-lookup"><span data-stu-id="8020e-123">Contoso information policies</span></span>
<span data-ttu-id="8020e-124">下表列出了 Contoso 信息策略。</span><span class="sxs-lookup"><span data-stu-id="8020e-124">The following table lists the Contoso information policies.</span></span>


| <span data-ttu-id="8020e-125">值</span><span class="sxs-lookup"><span data-stu-id="8020e-125">Value</span></span> | <span data-ttu-id="8020e-126">Access</span><span class="sxs-lookup"><span data-stu-id="8020e-126">Access</span></span> | <span data-ttu-id="8020e-127">数据保留</span><span class="sxs-lookup"><span data-stu-id="8020e-127">Data retention</span></span> | <span data-ttu-id="8020e-128">信息保护</span><span class="sxs-lookup"><span data-stu-id="8020e-128">Information protection</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="8020e-129">业务价值较低（1 级：基准）</span><span class="sxs-lookup"><span data-stu-id="8020e-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="8020e-130">允许访问全部。</span><span class="sxs-lookup"><span data-stu-id="8020e-130">Allow access to all.</span></span>  | <span data-ttu-id="8020e-131">6 个月</span><span class="sxs-lookup"><span data-stu-id="8020e-131">6 months</span></span> | <span data-ttu-id="8020e-132">使用加密。</span><span class="sxs-lookup"><span data-stu-id="8020e-132">Use encryption.</span></span> |
| <span data-ttu-id="8020e-133">业务价值中等（2 级：敏感）</span><span class="sxs-lookup"><span data-stu-id="8020e-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="8020e-134">允许 Contoso 员工、分包商和合作伙伴访问。</span><span class="sxs-lookup"><span data-stu-id="8020e-134">Allow access to Contoso employees, subcontractors, and partners.</span></span> <BR><BR> <span data-ttu-id="8020e-135">使用 MFA、传输层安全性 (TLS) 和移动应用管理 (MAM)。</span><span class="sxs-lookup"><span data-stu-id="8020e-135">Use MFA, Transport Layer Security (TLS), and Mobile Application Management (MAM).</span></span> | <span data-ttu-id="8020e-136">2 年</span><span class="sxs-lookup"><span data-stu-id="8020e-136">2 years</span></span>  | <span data-ttu-id="8020e-137">使用哈希值实现数据完整性。</span><span class="sxs-lookup"><span data-stu-id="8020e-137">Use hash values for data integrity.</span></span>  |
| <span data-ttu-id="8020e-138">高业务价值（3 级：高度管控）</span><span class="sxs-lookup"><span data-stu-id="8020e-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="8020e-139">允许工程设计和制造中的执行人员和潜在客户访问。</span><span class="sxs-lookup"><span data-stu-id="8020e-139">Allow access to executives and leads in engineering and manufacturing.</span></span> <BR> <BR> <span data-ttu-id="8020e-140">仅限托管网络设备的权限管理系统 (RMS)。</span><span class="sxs-lookup"><span data-stu-id="8020e-140">Rights Management System (RMS) with managed network devices only.</span></span>  | <span data-ttu-id="8020e-141">7 年</span><span class="sxs-lookup"><span data-stu-id="8020e-141">7 years</span></span>  | <span data-ttu-id="8020e-142">使用数字签名实现不可否认性。</span><span class="sxs-lookup"><span data-stu-id="8020e-142">Use digital signatures for non-repudiation.</span></span>  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a><span data-ttu-id="8020e-143">Contoso 信息保护与企业Microsoft 365路径</span><span class="sxs-lookup"><span data-stu-id="8020e-143">The Contoso path to information protection with Microsoft 365 for enterprise</span></span>

<span data-ttu-id="8020e-144">Contoso 按照以下步骤为企业Microsoft 365信息保护要求做好准备：</span><span class="sxs-lookup"><span data-stu-id="8020e-144">Contoso followed these steps to prepare Microsoft 365 for enterprise for their information-protection requirements:</span></span>

1. <span data-ttu-id="8020e-145">确定要保护的信息</span><span class="sxs-lookup"><span data-stu-id="8020e-145">Identify what information to protect</span></span>

   <span data-ttu-id="8020e-146">Contoso 对位于本地网站和文件共享中的现有数字SharePoint进行了广泛审查，并分类了每个资产。</span><span class="sxs-lookup"><span data-stu-id="8020e-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each asset.</span></span>

2. <span data-ttu-id="8020e-147">确定数据级别的访问、保留和信息保护策略</span><span class="sxs-lookup"><span data-stu-id="8020e-147">Determine access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="8020e-148">Contoso 基于数据级别确定了详细的策略要求，这些要求被用于保护现有数字资产，因为它们被转移到了云中。</span><span class="sxs-lookup"><span data-stu-id="8020e-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="8020e-149">为不同级别的信息创建敏感度标签及其设置</span><span class="sxs-lookup"><span data-stu-id="8020e-149">Create sensitivity labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="8020e-150">Contoso 为其数据级别创建了敏感度标签，其中包含加密、权限和水印等高度管控标签。</span><span class="sxs-lookup"><span data-stu-id="8020e-150">Contoso created sensitivity labels for their data levels, with their highly regulated label that includes encryption, permissions, and watermarks.</span></span>

4.  <span data-ttu-id="8020e-151">将数据从本地部署SharePoint网站和文件共享移动到其新的SharePoint网站</span><span class="sxs-lookup"><span data-stu-id="8020e-151">Move data from on-premises SharePoint sites and file shares to their new SharePoint sites</span></span>

    <span data-ttu-id="8020e-152">迁移到新的 SharePoint 网站的文件继承了分配给该网站的默认保留标签。</span><span class="sxs-lookup"><span data-stu-id="8020e-152">The files migrated to the new SharePoint sites inherited the default retention labels assigned to the site.</span></span>

5.  <span data-ttu-id="8020e-153">培训员工如何对新文档使用敏感度标签、如何在创建新的 SharePoint 网站时与 Contoso IT 进行交互，以及始终在 SharePoint 网站上存储数字资产</span><span class="sxs-lookup"><span data-stu-id="8020e-153">Train employees how to use sensitivity labels for new documents, how to interact with Contoso IT when creating new SharePoint sites, and to always store digital assets on SharePoint sites</span></span>

    <span data-ttu-id="8020e-154">改变不良的工作人员信息存储习惯通常被视为云信息保护转换中最困难的部分。</span><span class="sxs-lookup"><span data-stu-id="8020e-154">Changing bad worker information-storage habits is often considered the hardest part of the information protection transition for the cloud.</span></span> <span data-ttu-id="8020e-155">Contoso IT 和管理需要让员工始终在云中标记和存储其数字资产，避免使用本地文件共享，并且不使用第三方云存储服务或 USB 驱动器。</span><span class="sxs-lookup"><span data-stu-id="8020e-155">Contoso IT and management needed to get employees to always label and store their digital assets in the cloud, refrain from using on-premises file shares, and not use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="8020e-156">用于信息保护的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="8020e-156">Conditional Access policies for information protection</span></span>

<span data-ttu-id="8020e-157">作为推出 Exchange Online 和 SharePoint 的一SharePoint，Contoso 配置了以下一组条件访问策略，并应用于相应的组：</span><span class="sxs-lookup"><span data-stu-id="8020e-157">As part of their rollout of Exchange Online and SharePoint, Contoso configured the following set of Conditional Access policies and applied them to the appropriate groups:</span></span>

- [<span data-ttu-id="8020e-158">设备策略上的托管和非托管应用程序访问</span><span class="sxs-lookup"><span data-stu-id="8020e-158">Managed and unmanaged application access on devices policies</span></span>](../security/defender-365-security/identity-access-policies.md)
- [<span data-ttu-id="8020e-159">Exchange Online 访问策略</span><span class="sxs-lookup"><span data-stu-id="8020e-159">Exchange Online access policies</span></span>](../security/defender-365-security/secure-email-recommended-policies.md)
- [<span data-ttu-id="8020e-160">SharePoint 访问策略</span><span class="sxs-lookup"><span data-stu-id="8020e-160">SharePoint access policies</span></span>](../security/defender-365-security/sharepoint-file-access-policies.md)

<span data-ttu-id="8020e-161">下面是一组 Contoso 信息保护策略。</span><span class="sxs-lookup"><span data-stu-id="8020e-161">Here's resulting set of Contoso policies for information protection.</span></span>

![设备、Exchange Online 和 SharePoint 条件访问策略](../media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
><span data-ttu-id="8020e-163">此外，Contoso 还配置了针对标识和登录的其他条件访问策略。</span><span class="sxs-lookup"><span data-stu-id="8020e-163">Contoso also configured additional Conditional Access policies for identity and sign-in.</span></span> <span data-ttu-id="8020e-164">请参阅 [Contoso Corporation 的标识](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。</span><span class="sxs-lookup"><span data-stu-id="8020e-164">See [Identity for the Contoso Corporation](contoso-identity.md#conditional-access-policies-for-identity-and-device-access).</span></span>
>

<span data-ttu-id="8020e-165">这些策略确保：</span><span class="sxs-lookup"><span data-stu-id="8020e-165">These policies ensure that:</span></span>

- <span data-ttu-id="8020e-166">允许的应用以及它们可以对组织数据采取的操作由应用保护策略定义。</span><span class="sxs-lookup"><span data-stu-id="8020e-166">Apps that are allowed and the actions they can take with the organization's data are defined by app protection policies.</span></span>
- <span data-ttu-id="8020e-167">电脑和移动设备必须兼容。</span><span class="sxs-lookup"><span data-stu-id="8020e-167">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="8020e-168">Exchange Online) OME Office 365 OME (OME Exchange Online。</span><span class="sxs-lookup"><span data-stu-id="8020e-168">Exchange Online uses Office 365 message encryption (OME) for Exchange Online.</span></span>
- <span data-ttu-id="8020e-169">SharePoint应用强制执行的限制。</span><span class="sxs-lookup"><span data-stu-id="8020e-169">SharePoint uses app-enforced restrictions.</span></span>
- <span data-ttu-id="8020e-170">SharePoint 使用访问控制策略来实现非托管设备的仅浏览器访问或阻止其访问。</span><span class="sxs-lookup"><span data-stu-id="8020e-170">SharePoint uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a><span data-ttu-id="8020e-171">将Microsoft 365功能映射到 Contoso 数据级别</span><span class="sxs-lookup"><span data-stu-id="8020e-171">Mapping Microsoft 365 for enterprise features to Contoso data levels</span></span>

<span data-ttu-id="8020e-172">下表将 Contoso 数据级别映射到企业Microsoft 365信息保护功能。</span><span class="sxs-lookup"><span data-stu-id="8020e-172">The following table maps Contoso data levels to information protection features in Microsoft 365 for enterprise.</span></span>

| <span data-ttu-id="8020e-173">Level</span><span class="sxs-lookup"><span data-stu-id="8020e-173">Level</span></span> | <span data-ttu-id="8020e-174">Microsoft 365云服务</span><span class="sxs-lookup"><span data-stu-id="8020e-174">Microsoft 365 cloud services</span></span> | <span data-ttu-id="8020e-175">Windows 10 和 Microsoft 365 企业应用版</span><span class="sxs-lookup"><span data-stu-id="8020e-175">Windows 10 and Microsoft 365 Apps for enterprise</span></span> | <span data-ttu-id="8020e-176">安全性和合规性</span><span class="sxs-lookup"><span data-stu-id="8020e-176">Security and compliance</span></span> |
|:-------|:-----|:-----|:-----|
| <span data-ttu-id="8020e-177">1 级：基准</span><span class="sxs-lookup"><span data-stu-id="8020e-177">Level 1: Baseline</span></span>  | <span data-ttu-id="8020e-178">SharePoint 和 Exchange Online 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="8020e-178">SharePoint and Exchange Online Conditional Access policies</span></span> <BR> <span data-ttu-id="8020e-179">SharePoint 网站上的权限</span><span class="sxs-lookup"><span data-stu-id="8020e-179">Permissions on SharePoint sites</span></span> | <span data-ttu-id="8020e-180">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="8020e-180">Sensitivity labels</span></span> <BR> <span data-ttu-id="8020e-181">BitLocker</span><span class="sxs-lookup"><span data-stu-id="8020e-181">BitLocker</span></span> <BR> <span data-ttu-id="8020e-182">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="8020e-182">Windows Information Protection</span></span> | <span data-ttu-id="8020e-183">设备条件访问策略和移动应用管理策略</span><span class="sxs-lookup"><span data-stu-id="8020e-183">Device Conditional Access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="8020e-184">2 级：敏感</span><span class="sxs-lookup"><span data-stu-id="8020e-184">Level 2: Sensitive</span></span> | <span data-ttu-id="8020e-185">1 级再加上：</span><span class="sxs-lookup"><span data-stu-id="8020e-185">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="8020e-186">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="8020e-186">Sensitivity labels</span></span> <BR> <span data-ttu-id="8020e-187">SharePoint 网站上的 Microsoft 365 保留标签</span><span class="sxs-lookup"><span data-stu-id="8020e-187">Microsoft 365 retention labels on SharePoint sites</span></span> <BR> <span data-ttu-id="8020e-188">用于 SharePoint 和 Exchange Online 的数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="8020e-188">Data Loss Prevention for SharePoint and Exchange Online</span></span> <BR> <span data-ttu-id="8020e-189">独立 SharePoint 网站</span><span class="sxs-lookup"><span data-stu-id="8020e-189">Isolated SharePoint sites</span></span>  | <span data-ttu-id="8020e-190">1 级再加上：</span><span class="sxs-lookup"><span data-stu-id="8020e-190">Level 1 plus:</span></span> <BR> <BR> <span data-ttu-id="8020e-191">数字资产上的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="8020e-191">Sensitivity labels on digital assets</span></span>  | <span data-ttu-id="8020e-192">1 级</span><span class="sxs-lookup"><span data-stu-id="8020e-192">Level 1</span></span> |
| <span data-ttu-id="8020e-193">3 级：高度管控</span><span class="sxs-lookup"><span data-stu-id="8020e-193">Level 3: Highly regulated</span></span> | <span data-ttu-id="8020e-194">2 级再加上：</span><span class="sxs-lookup"><span data-stu-id="8020e-194">Level 2 plus:</span></span> <BR><BR> <span data-ttu-id="8020e-195">将你自己的密钥 (BYOK) 加密和保护商业机密信息</span><span class="sxs-lookup"><span data-stu-id="8020e-195">Bring your own key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="8020e-196">Azure Key Vault，用于与服务交互的业务线Microsoft 365应用程序</span><span class="sxs-lookup"><span data-stu-id="8020e-196">Azure Key Vault for line-of-business applications that interact with Microsoft 365 services</span></span> | <span data-ttu-id="8020e-197">2 级</span><span class="sxs-lookup"><span data-stu-id="8020e-197">Level 2</span></span> | <span data-ttu-id="8020e-198">1 级</span><span class="sxs-lookup"><span data-stu-id="8020e-198">Level 1</span></span> |
|||||

<span data-ttu-id="8020e-199">下面是生成的 Contoso 信息保护配置。</span><span class="sxs-lookup"><span data-stu-id="8020e-199">Here's the resulting Contoso information-protection configuration.</span></span>

![Contoso 最终得到的信息保护配置](../media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a><span data-ttu-id="8020e-201">后续步骤</span><span class="sxs-lookup"><span data-stu-id="8020e-201">Next step</span></span>

<span data-ttu-id="8020e-202">了解 Contoso 如何使用[](contoso-security-summary.md)跨企业Microsoft 365安全功能进行标识和访问管理、威胁防护、信息保护和安全管理。</span><span class="sxs-lookup"><span data-stu-id="8020e-202">Learn how Contoso uses the [security features across Microsoft 365 for enterprise](contoso-security-summary.md) for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="8020e-203">另请参阅</span><span class="sxs-lookup"><span data-stu-id="8020e-203">See also</span></span>

[<span data-ttu-id="8020e-204">安全性路线图</span><span class="sxs-lookup"><span data-stu-id="8020e-204">Security roadmap</span></span>](../security/defender-365-security/security-roadmap.md)

[<span data-ttu-id="8020e-205">Microsoft 365 企业版概述</span><span class="sxs-lookup"><span data-stu-id="8020e-205">Microsoft 365 for enterprise overview</span></span>](microsoft-365-overview.md)

[<span data-ttu-id="8020e-206">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="8020e-206">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)