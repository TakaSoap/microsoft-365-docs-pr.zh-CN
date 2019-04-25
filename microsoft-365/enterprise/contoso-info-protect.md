---
title: Contoso Corporation 的信息保护
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/10/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企业版中的信息保护功能来保护其在云中的数字资产。
ms.openlocfilehash: f0869dfd661ae4dbaed74fdfd660c863deb20175
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32276108"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="408d8-103">Contoso Corporation 的信息保护</span><span class="sxs-lookup"><span data-stu-id="408d8-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="408d8-104">**摘要：** 了解 Contoso 如何使用 Microsoft 365 企业版中的信息保护功能来保护其在云中的数字资产。</span><span class="sxs-lookup"><span data-stu-id="408d8-104">**Summary:** Understand how Contoso uses information protection features in Microsoft 365 Enterprise to secure their digital assets in the cloud.</span></span>

<span data-ttu-id="408d8-p101">Contoso 在信息安全和保护方面非常严谨。例如，在描述产品设计和专有制造技术时，其知识产权的泄露或破坏将使他们在竞争中处于劣势。</span><span class="sxs-lookup"><span data-stu-id="408d8-p101">Contoso is serious about their information security and protection. For example, leakage or destruction of their intellectual property describing product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="408d8-107">在将敏感和最有价值的数字资产转移到云之前，他们将确保本地信息分类和保护要求在 Microsoft 365 企业版基于云的服务中得到支持和实现。</span><span class="sxs-lookup"><span data-stu-id="408d8-107">Before moving their sensitive and most valuable digital assets to the cloud, they made sure that their on-premises information classification and protection requirements were supported and implemented in the cloud-based services of Microsoft 365 Enterprise.</span></span>

## <a name="contosos-data-security-classification"></a><span data-ttu-id="408d8-108">Contoso 的数据安全分类</span><span class="sxs-lookup"><span data-stu-id="408d8-108">Contoso's data security classification</span></span>

<span data-ttu-id="408d8-109">Contoso 执行数据分析，并确定以下级别。</span><span class="sxs-lookup"><span data-stu-id="408d8-109">Contoso performed an analysis of their data and determined the following levels.</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="408d8-110">**1 级：基准**</span><span class="sxs-lookup"><span data-stu-id="408d8-110">**Level 1: Baseline**</span></span> | <span data-ttu-id="408d8-111">**2 级：敏感**</span><span class="sxs-lookup"><span data-stu-id="408d8-111">**Level 2: Sensitive**</span></span> | <span data-ttu-id="408d8-112">**3 级：高度管控**</span><span class="sxs-lookup"><span data-stu-id="408d8-112">**Level 3: Highly regulated**</span></span> |
| <span data-ttu-id="408d8-113">数据已加密，并且仅供已通过身份验证的用户使用</span><span class="sxs-lookup"><span data-stu-id="408d8-113">Data is encrypted and available only to authenticated users</span></span> <BR> <BR> <span data-ttu-id="408d8-p102">向存储在本地和基于云的存储空间和工作负载（例如 Office 365）中的所有数据提供。驻留在服务中和在服务与客户端设备之间传输时，数据处于加密状态。</span><span class="sxs-lookup"><span data-stu-id="408d8-p102">Provided for all data stored on premises and in cloud-based storage and workloads, such as Office 365. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR> <span data-ttu-id="408d8-116">1 级数据的示例为正常的业务通信（电子邮件）和供管理、销售和支持工作人员使用的文件。</span><span class="sxs-lookup"><span data-stu-id="408d8-116">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="408d8-117">1 级再加上强身份验证和数据丢失防护：</span><span class="sxs-lookup"><span data-stu-id="408d8-117">Level 1 plus strong authentication and data loss protection:</span></span> <BR> <BR> <span data-ttu-id="408d8-p103">强身份验证包括具有 SMS 验证的多重身份验证。数据丢失防护确保敏感或关键的信息不会在本地网络以外出现。
</span><span class="sxs-lookup"><span data-stu-id="408d8-p103">Strong authentication includes multi-factor authentication with SMS validation. Data loss prevention ensures that sensitive or critical information does not travel outside the on-premises network.</span></span> <BR><BR> <span data-ttu-id="408d8-120">2 级数据的示例包括财务和法律信息，以及新产品的研发数据。</span><span class="sxs-lookup"><span data-stu-id="408d8-120">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="408d8-121">2 级再加上最高级别的加密、身份验证和审核。</span><span class="sxs-lookup"><span data-stu-id="408d8-121">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span> <BR> <BR>  <span data-ttu-id="408d8-122">对静态和云中的数据采用最高级别的加密，遵循区域法规，并结合具有智能卡以及精细审核和警报的多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="408d8-122">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with multi-factor authentication with smart cards and granular auditing and alerting.</span></span> <BR> <BR> <span data-ttu-id="408d8-123">3 级数据的示例是客户和合作伙伴的个人身份信息、产品工程规范以及专有的制造技术。</span><span class="sxs-lookup"><span data-stu-id="408d8-123">Examples of Level 3 data are customer and partner personally identifiable information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contosos-information-policies"></a><span data-ttu-id="408d8-124">Contoso 的信息策略</span><span class="sxs-lookup"><span data-stu-id="408d8-124">Contoso's information policies</span></span>
<span data-ttu-id="408d8-125">下表列出了 Contoso 的信息策略。</span><span class="sxs-lookup"><span data-stu-id="408d8-125">The following table lists Contoso's information policies.</span></span>

|||||
|:-------|:-----|:-----|:-----|
|  | <span data-ttu-id="408d8-126">**访问**</span><span class="sxs-lookup"><span data-stu-id="408d8-126">**Access**</span></span> | <span data-ttu-id="408d8-127">**数据保留**</span><span class="sxs-lookup"><span data-stu-id="408d8-127">**Data retention**</span></span> | <span data-ttu-id="408d8-128">**信息保护**</span><span class="sxs-lookup"><span data-stu-id="408d8-128">**Information protection**</span></span> |
| <span data-ttu-id="408d8-129">业务价值较低（1 级：基准）</span><span class="sxs-lookup"><span data-stu-id="408d8-129">Low business value (Level 1: Baseline)</span></span> | <span data-ttu-id="408d8-130">允许所有人员访问</span><span class="sxs-lookup"><span data-stu-id="408d8-130">Allow access to all</span></span>  | <span data-ttu-id="408d8-131">6 个月</span><span class="sxs-lookup"><span data-stu-id="408d8-131">6 months</span></span> | <span data-ttu-id="408d8-132">使用加密</span><span class="sxs-lookup"><span data-stu-id="408d8-132">Use encryption</span></span> |
| <span data-ttu-id="408d8-133">业务价值中等（2 级：敏感）</span><span class="sxs-lookup"><span data-stu-id="408d8-133">Medium business value (Level 2: Sensitive)</span></span> | <span data-ttu-id="408d8-134">允许 Contoso 员工、分包商和合作伙伴访问</span><span class="sxs-lookup"><span data-stu-id="408d8-134">Allow access to Contoso employees, subcontractors, and partners</span></span> <BR> <BR> <span data-ttu-id="408d8-135">使用多重身份验证 (MFA)、传输层安全性 (TLS) 和移动应用管理 (MAM)</span><span class="sxs-lookup"><span data-stu-id="408d8-135">Use multi-factor authentication (MFA), Transport Layer Security (TLS), and Mobile Application Management (MAM)</span></span> | <span data-ttu-id="408d8-136">2 年</span><span class="sxs-lookup"><span data-stu-id="408d8-136">2 years</span></span>  | <span data-ttu-id="408d8-137">使用哈希值实现数据完整性</span><span class="sxs-lookup"><span data-stu-id="408d8-137">Use hash values for data integrity</span></span>  |
| <span data-ttu-id="408d8-138">高业务价值（3 级：高度管控）</span><span class="sxs-lookup"><span data-stu-id="408d8-138">High business value (Level 3: Highly regulated)</span></span> | <span data-ttu-id="408d8-139">允许工程设计和制造中的执行人员和潜在客户访问</span><span class="sxs-lookup"><span data-stu-id="408d8-139">Allow access to executives and leads in engineering and manufacturing</span></span> <BR> <BR> <span data-ttu-id="408d8-140">仅限托管网络设备的权限管理系统 (RMS)</span><span class="sxs-lookup"><span data-stu-id="408d8-140">Rights Management System (RMS) with managed network devices only</span></span>  | <span data-ttu-id="408d8-141">7 年</span><span class="sxs-lookup"><span data-stu-id="408d8-141">7 years</span></span>  | <span data-ttu-id="408d8-142">使用数字签名实现不可否认性</span><span class="sxs-lookup"><span data-stu-id="408d8-142">Use digital signatures for non-repudiation</span></span>  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a><span data-ttu-id="408d8-143">使用 Microsoft 365 企业版的 Contoso 信息保护路径</span><span class="sxs-lookup"><span data-stu-id="408d8-143">Contoso’s path to information protection with Microsoft 365 Enterprise</span></span>

<span data-ttu-id="408d8-144">Contoso 使用以下步骤为 Microsoft 365 企业版准备其信息保护要求：</span><span class="sxs-lookup"><span data-stu-id="408d8-144">Contoso used the following steps to prepare Microsoft 365 Enterprise for their information protection requirements:</span></span>

1. <span data-ttu-id="408d8-145">标识要保护的信息</span><span class="sxs-lookup"><span data-stu-id="408d8-145">Identified what information to protect</span></span>

   <span data-ttu-id="408d8-146">Contoso 对其现有数字资产进行了广泛审查，这些资产位于本地 SharePoint 网站和文件共享中，并对每一个资产都进行了分类。</span><span class="sxs-lookup"><span data-stu-id="408d8-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each one.</span></span>

2. <span data-ttu-id="408d8-147">确定数据级别的访问策略、保留策略和信息保护策略</span><span class="sxs-lookup"><span data-stu-id="408d8-147">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="408d8-148">Contoso 基于数据级别确定了详细的策略要求，这些要求被用于保护现有数字资产，因为它们被转移到了云中。</span><span class="sxs-lookup"><span data-stu-id="408d8-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="408d8-149">创建了敏感度标签以及它们对不同级别信息的设置</span><span class="sxs-lookup"><span data-stu-id="408d8-149">Created Azure Information Protection labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="408d8-150">Contoso 为其数据级别创建了敏感度标签：敏感和高度管控标签，包括加密、权限和水印。</span><span class="sxs-lookup"><span data-stu-id="408d8-150">Contoso created sensitivity labels for their data levels, with sensitive and highly regulated label including encryption, permissions, and watermarks.</span></span>

4. <span data-ttu-id="408d8-151">为敏感和高度管控数据创建了受保护的 SharePoint Online 网站，同时包含锁定访问权限的权限</span><span class="sxs-lookup"><span data-stu-id="408d8-151">Created protected SharePoint Online sites for sensitive and highly regulated data with permissions that lock down access</span></span>

   <span data-ttu-id="408d8-152">敏感和高度管控网站均配置为[独立网站](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites)，其中默认的 SharePoint Online 团队网站权限自定义到 Azure Active Directory (Azure AD) 组。</span><span class="sxs-lookup"><span data-stu-id="408d8-152">Both sensitive and highly regulated sites were configured as [isolated sites](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites), in which the default SharePoint Online team site permissions were customized to Azure Active Directory (Azure AD) groups.</span></span> <span data-ttu-id="408d8-153">敏感和高度管控的 SharePoint Online 网站也配置了相应的保留标签。</span><span class="sxs-lookup"><span data-stu-id="408d8-153">Sensitive and highly regulated SharePoint Online sites were also configured with a corrresponding retention label.</span></span> <span data-ttu-id="408d8-154">高度管控 SharePoint Online 网站中存储的文件受高度管控敏感度标签的保护。</span><span class="sxs-lookup"><span data-stu-id="408d8-154">Files stored in highly regulated SharePoint Online sites are protected with the Highly Regulated sensitivity label.</span></span> <span data-ttu-id="408d8-155">有关详细信息，请参阅[针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站](teams-sharepoint-online-sites-highly-regulated-data.md)应用场景。</span><span class="sxs-lookup"><span data-stu-id="408d8-155">For more information, see the [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md) scenario.</span></span>

5.  <span data-ttu-id="408d8-156">将数据从本地 SharePoint 网站和文件共享转移到新的 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="408d8-156">Moved data from on-premises SharePoint sites and file shares to their new SharePoint Online sites</span></span>

    <span data-ttu-id="408d8-157">迁移到新的 SharePoint Online 网站的文件继承了分配给该网站的默认保留标签。</span><span class="sxs-lookup"><span data-stu-id="408d8-157">The files migrated to the new SharePoint Online sites inherited the default Office 365 labels assigned to the site.</span></span>

6.  <span data-ttu-id="408d8-158">培训员工如何在新文档中使用敏感度标签，如何在创建新的 SharePoint Online 网站时与 Contoso IT 进行交互，以及如何始终在 SharePoint Online 网站上存储数字资产。</span><span class="sxs-lookup"><span data-stu-id="408d8-158">Trained employees on how to use Azure Information Protection labels for new documents, how to interact with Contoso IT when creating new SharePoint Online sites, and to always store digital assets on SharePoint Online sites</span></span>

    <span data-ttu-id="408d8-159">Contoso IT 和管理被视为云信息保护过渡中最困难的部分，需要改变组织员工的不良信息存储习惯，以始终在云中存储和标记其数字资产，避免使用本地文件共享，并且绝不使用第三方云存储设备或 U 盘。</span><span class="sxs-lookup"><span data-stu-id="408d8-159">Considered the hardest part of the information protection transition for the cloud, Contoso IT and management needed to change the bad information storage habits of the organization’s employees to always store and label their digital assets in the cloud, refrain from using on-premises file shares, and never use third-party cloud storage services or USB drives.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="408d8-160">用于信息保护的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="408d8-160">Conditional access policies for information protection</span></span>

<span data-ttu-id="408d8-161">与身份标识和移动设备管理基础结构结合使用，并作为他们推出 Exchange Online 和 SharePoint Online 的一部分，Contoso 配置了以下一组条件访问策略，并将其应用到相应的 Azure AD 组：</span><span class="sxs-lookup"><span data-stu-id="408d8-161">In conjunction with their identity and mobile device management infrastructure and as part of their rollout of Exchange Online and SharePoint Online, Contoso configured the following set of conditional access policies and applied them to the appropriate Azure AD groups:</span></span>

- [<span data-ttu-id="408d8-162">设备策略上的托管和非托管应用程序访问</span><span class="sxs-lookup"><span data-stu-id="408d8-162">Managed and unmanaged application access on devices policies</span></span>](identity-access-policies.md)
- [<span data-ttu-id="408d8-163">Exchange Online 访问策略</span><span class="sxs-lookup"><span data-stu-id="408d8-163">Exchange Online access policies</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="408d8-164">SharePoint Online 访问策略</span><span class="sxs-lookup"><span data-stu-id="408d8-164">SharePoint Online access policies</span></span>](sharepoint-file-access-policies.md)

<span data-ttu-id="408d8-165">图 1 显示 Contoso 信息保护策略的结果集。</span><span class="sxs-lookup"><span data-stu-id="408d8-165">Figure 1 shows Contoso's resulting set of policies for information protection.</span></span>

![](./media/contoso-info-protect/contoso-info-protect-fig1.png)

<span data-ttu-id="408d8-166">**图 1：设备、Exchange Online 和 SharePoint Online 的条件访问策略**</span><span class="sxs-lookup"><span data-stu-id="408d8-166">**Figure 1: Device, Exchange Online, and SharePoint Online conditional access policies**</span></span>
 
>[!Note]
><span data-ttu-id="408d8-p105">此外，Contoso 还配置了其他条件访问策略用于标识和登录。请参阅 [Contoso Corporation 的标识](contoso-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="408d8-p105">Contoso also configured additional conditional access policies for identity and sign-in. See [Identity for the Contoso Corporation](contoso-identity.md).</span></span>
>

<span data-ttu-id="408d8-169">这些策略确保：</span><span class="sxs-lookup"><span data-stu-id="408d8-169">These policies ensure that:</span></span>

- <span data-ttu-id="408d8-170">应用保护政策定义哪些应用程序是允许的，以及它们可以使用组织数据执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="408d8-170">Apps are allowed and the actions they can take with your organization data are defined by app protection policies.</span></span>
- <span data-ttu-id="408d8-171">电脑和移动设备必须兼容。</span><span class="sxs-lookup"><span data-stu-id="408d8-171">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="408d8-172">Exchange Online 使用 Exchange Online 的 Office 365 邮件加密。</span><span class="sxs-lookup"><span data-stu-id="408d8-172">Exchange Online uses Office 365 message encryption for Exchange Online.</span></span>
- <span data-ttu-id="408d8-173">SharePoint Online 使用应用强制的限制。</span><span class="sxs-lookup"><span data-stu-id="408d8-173">SharePoint Online uses app enforced restrictions.</span></span>
- <span data-ttu-id="408d8-174">SharePoint Online 使用访问控制策略进行仅浏览器访问并阻止非托管设备的访问。</span><span class="sxs-lookup"><span data-stu-id="408d8-174">SharePoint Online uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a><span data-ttu-id="408d8-175">将 Microsoft 365 企业版功能映射到 Contoso 的数据级别</span><span class="sxs-lookup"><span data-stu-id="408d8-175">Mapping Microsoft 365 Enterprise features to Contoso's data levels</span></span>

<span data-ttu-id="408d8-176">下表显示 Contoso 的数据级别在 Microsoft 365 企业版信息保护功能中的映射。</span><span class="sxs-lookup"><span data-stu-id="408d8-176">The following table shows the mapping the Contoso's data levels to information protection features in Microsoft 365 Enterprise.</span></span>

|||||
|:-------|:-----|:-----|:-----|
| | <span data-ttu-id="408d8-177">**Office 365**</span><span class="sxs-lookup"><span data-stu-id="408d8-177">**Office 365**</span></span> | <span data-ttu-id="408d8-178">**Windows 10 和 Office 365 专业增强版**</span><span class="sxs-lookup"><span data-stu-id="408d8-178">**Windows 10 and Office 365 ProPlus**</span></span> | <span data-ttu-id="408d8-179">**EMS**</span><span class="sxs-lookup"><span data-stu-id="408d8-179">**EMS**</span></span> |
| <span data-ttu-id="408d8-180">1 级：基准</span><span class="sxs-lookup"><span data-stu-id="408d8-180">Level 1: Baseline</span></span>  | <span data-ttu-id="408d8-181">SharePoint Online 和 Exchange Online 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="408d8-181">SharePoint Online and Exchange Online conditional access policies</span></span> <BR> <span data-ttu-id="408d8-182">SharePoint Online 网站的权限</span><span class="sxs-lookup"><span data-stu-id="408d8-182">Permissions on SharePoint Online sites</span></span> | <span data-ttu-id="408d8-183">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="408d8-183">Sensitivity labels</span></span> <BR> <span data-ttu-id="408d8-184">BitLocker</span><span class="sxs-lookup"><span data-stu-id="408d8-184">BitLocker</span></span> <BR> <span data-ttu-id="408d8-185">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="408d8-185">Windows Information Protection</span></span> | <span data-ttu-id="408d8-186">设备条件访问策略和移动应用管理策略</span><span class="sxs-lookup"><span data-stu-id="408d8-186">Device conditional access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="408d8-187">2 级：敏感</span><span class="sxs-lookup"><span data-stu-id="408d8-187">Level 2: Sensitive</span></span> | <span data-ttu-id="408d8-188">1 级再加上：</span><span class="sxs-lookup"><span data-stu-id="408d8-188">Level 1: Baseline plus:</span></span> <BR> <BR> <span data-ttu-id="408d8-189">敏感度标签</span><span class="sxs-lookup"><span data-stu-id="408d8-189">Sensitivity labels</span></span> <BR> <span data-ttu-id="408d8-190">SharePoint Online 网站上的 Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="408d8-190">Office 365 labels on SharePoint Online sites</span></span> <BR> <span data-ttu-id="408d8-191">用于 SharePoint Online 和 Exchange Online 的 Office 365 数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="408d8-191">Office 365 Data Loss Prevention for SharePoint Online and Exchange Online</span></span> <BR> <span data-ttu-id="408d8-192">独立 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="408d8-192">Isolated SharePoint Online sites</span></span>  | <span data-ttu-id="408d8-193">1 级再加上：</span><span class="sxs-lookup"><span data-stu-id="408d8-193">Level 1: Baseline plus:</span></span> <BR> <BR> <span data-ttu-id="408d8-194">数字资产上的敏感度标签</span><span class="sxs-lookup"><span data-stu-id="408d8-194">Sensitivity labels on digital assets</span></span> <BR> <span data-ttu-id="408d8-195">Office 365 高级数据管理</span><span class="sxs-lookup"><span data-stu-id="408d8-195">Office 365 Advanced Data Governance</span></span> | <span data-ttu-id="408d8-196">1 级</span><span class="sxs-lookup"><span data-stu-id="408d8-196">Level 1 – Yellow</span></span> |
| <span data-ttu-id="408d8-197">3 级：高度管控</span><span class="sxs-lookup"><span data-stu-id="408d8-197">Level 3: Highly regulated</span></span> | <span data-ttu-id="408d8-198">2 级再加上：</span><span class="sxs-lookup"><span data-stu-id="408d8-198">Level 2: Highly sensitive plus:</span></span> <BR><BR> <span data-ttu-id="408d8-199">针对商业机密信息的自带密钥 (BYOK) 加密和保护</span><span class="sxs-lookup"><span data-stu-id="408d8-199">Bring Your Own Key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="408d8-200">将 Azure Key Vault 用于与 Office 365 服务交互的业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="408d8-200">Azure Key Vault for line of business applications that interact with Office 365 services</span></span> | <span data-ttu-id="408d8-201">2 级</span><span class="sxs-lookup"><span data-stu-id="408d8-201">Level: 2</span></span> | <span data-ttu-id="408d8-202">1 级</span><span class="sxs-lookup"><span data-stu-id="408d8-202">Level 1 – Yellow</span></span> |
|||||


## <a name="next-step"></a><span data-ttu-id="408d8-203">后续步骤</span><span class="sxs-lookup"><span data-stu-id="408d8-203">Next step</span></span>

<span data-ttu-id="408d8-204">[请参阅](contoso-security-summary.md) Contoso 如何使用安全功能跨 Microsoft 365 企业版实现身份识别和访问管理、威胁防护、信息保护以及安全管理。</span><span class="sxs-lookup"><span data-stu-id="408d8-204">[See](contoso-security-summary.md) how Contoso has used the security features across Microsoft 365 Enterprise for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="408d8-205">另请参阅</span><span class="sxs-lookup"><span data-stu-id="408d8-205">See also</span></span>

[<span data-ttu-id="408d8-206">Microsoft 365 企业版信息保护</span><span class="sxs-lookup"><span data-stu-id="408d8-206">Information protection for Microsoft 365 Enterprise</span></span>](infoprotect-infrastructure.md)

[<span data-ttu-id="408d8-207">部署指南</span><span class="sxs-lookup"><span data-stu-id="408d8-207">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="408d8-208">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="408d8-208">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)


