---
title: Contoso Corporation 的信息保护
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 09/18/2018
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企业版中的信息保护功能来保护其在云中的数字资产。
ms.openlocfilehash: 2f6619aa3c6051696644b055e6c766525ad3a26d
ms.sourcegitcommit: eb1a77e4cc4e8f564a1c78d2ef53d7245fe4517a
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/28/2018
ms.locfileid: "26865945"
---
# <a name="information-protection-for-the-contoso-corporation"></a><span data-ttu-id="c5d31-103">Contoso Corporation 的信息保护</span><span class="sxs-lookup"><span data-stu-id="c5d31-103">Information protection for the Contoso Corporation</span></span>

<span data-ttu-id="c5d31-104">**摘要：** 了解 Contoso 如何使用 Microsoft 365 企业版中的信息保护功能来保护其在云中的数字资产。</span><span class="sxs-lookup"><span data-stu-id="c5d31-104">**Summary:** Understand how Contoso uses information protection features in Microsoft 365 Enterprise to secure their digital assets in the cloud.</span></span>

<span data-ttu-id="c5d31-p101">Contoso 在信息安全和保护方面非常严谨。例如，在描述产品设计和专有制造技术时，其知识产权的泄露或破坏将使他们在竞争中处于劣势。</span><span class="sxs-lookup"><span data-stu-id="c5d31-p101">Contoso is serious about their information security and protection. For example, leakage or destruction of their intellectual property describing product designs and proprietary manufacturing techniques would place them at a competitive disadvantage.</span></span>

<span data-ttu-id="c5d31-107">在将敏感和最有价值的数字资产转移到云之前，他们将确保本地信息分类和保护要求在 Microsoft 365 企业版基于云的服务中得到支持和实现。</span><span class="sxs-lookup"><span data-stu-id="c5d31-107">Before moving their sensitive and most valuable digital assets to the cloud, they made sure that their on-premises information classification and protection requirements were supported and implemented in the cloud-based services of Microsoft 365 Enterprise.</span></span>

## <a name="contosos-data-security-classification"></a><span data-ttu-id="c5d31-108">Contoso 的数据安全分类</span><span class="sxs-lookup"><span data-stu-id="c5d31-108">Contoso's data security classification</span></span>

<span data-ttu-id="c5d31-109">Contoso 执行数据分析，并确定以下级别。</span><span class="sxs-lookup"><span data-stu-id="c5d31-109">Contoso performed an analysis of their data and determined the following levels.</span></span>

||||
|:-------|:-----|:-----|
| <span data-ttu-id="c5d31-110">**1 级：基准**</span><span class="sxs-lookup"><span data-stu-id="c5d31-110">**Level 1: Baseline**</span></span> | <span data-ttu-id="c5d31-111">**2 级：敏感**</span><span class="sxs-lookup"><span data-stu-id="c5d31-111">**Level 2: Sensitive**</span></span> | <span data-ttu-id="c5d31-112">**3 级：高度管控**</span><span class="sxs-lookup"><span data-stu-id="c5d31-112">**Level 3: Highly regulated**</span></span> |
| <span data-ttu-id="c5d31-113">数据已加密，并且仅供已通过身份验证的用户使用</span><span class="sxs-lookup"><span data-stu-id="c5d31-113">Data is encrypted and available only to authenticated users</span></span> <BR> <BR> <span data-ttu-id="c5d31-p102">向存储在本地和基于云的存储空间和工作负载（例如 Office 365）中的所有数据提供。驻留在服务中和在服务与客户端设备之间传输时，数据处于加密状态。</span><span class="sxs-lookup"><span data-stu-id="c5d31-p102">Provided for all data stored on premises and in cloud-based storage and workloads, such as Office 365. Data is encrypted while it resides in the service and in transit between the service and client devices.</span></span> <BR><BR> <span data-ttu-id="c5d31-116">1 级数据的示例为正常的业务通信（电子邮件）和供管理、销售和支持工作人员使用的文件。</span><span class="sxs-lookup"><span data-stu-id="c5d31-116">Examples of Level 1 data are normal business communications (email) and files for administrative, sales, and support workers.</span></span> | <span data-ttu-id="c5d31-117">1 级再加上强身份验证和数据丢失防护：</span><span class="sxs-lookup"><span data-stu-id="c5d31-117">Level 1 plus strong authentication and data loss protection:</span></span> <BR> <BR> <span data-ttu-id="c5d31-p103">强身份验证包括具有 SMS 验证的多重身份验证。数据丢失防护确保敏感或关键的信息不会在本地网络以外出现。
</span><span class="sxs-lookup"><span data-stu-id="c5d31-p103">Strong authentication includes multi-factor authentication with SMS validation. Data loss prevention ensures that sensitive or critical information does not travel outside the on-premises network.</span></span> <BR><BR> <span data-ttu-id="c5d31-120">2 级数据的示例包括财务和法律信息，以及新产品的研发数据。</span><span class="sxs-lookup"><span data-stu-id="c5d31-120">Examples of Level 2 data are financial and legal information and research and development data for new products.</span></span> | <span data-ttu-id="c5d31-121">2 级再加上最高级别的加密、身份验证和审核。</span><span class="sxs-lookup"><span data-stu-id="c5d31-121">Level 2 plus the highest levels of encryption, authentication, and auditing.</span></span> <BR> <BR>  <span data-ttu-id="c5d31-122">对静态和云中的数据采用最高级别的加密，遵循区域法规，并结合具有智能卡以及精细审核和警报的多重身份验证。</span><span class="sxs-lookup"><span data-stu-id="c5d31-122">The highest levels of encryption for data at rest and in the cloud, compliant with regional regulations, combined with multi-factor authentication with smart cards and granular auditing and alerting.</span></span> <BR> <BR> <span data-ttu-id="c5d31-123">3 级数据的示例是客户和合作伙伴的个人身份信息、产品工程规范以及专有的制造技术。</span><span class="sxs-lookup"><span data-stu-id="c5d31-123">Examples of Level 3 data are customer and partner personally identifiable information, product engineering specifications, and proprietary manufacturing techniques.</span></span>  |
||||

## <a name="contosos-information-policies"></a><span data-ttu-id="c5d31-124">Contoso 的信息策略</span><span class="sxs-lookup"><span data-stu-id="c5d31-124">Contoso's information policies</span></span>
<span data-ttu-id="c5d31-125">下表列出了 Contoso 的信息策略。</span><span class="sxs-lookup"><span data-stu-id="c5d31-125">The following table lists Contoso's information policies.</span></span>

|||||
|:-------|:-----|:-----|:-----|
|  | <span data-ttu-id="c5d31-126">**访问**</span><span class="sxs-lookup"><span data-stu-id="c5d31-126">**Access**</span></span> | <span data-ttu-id="c5d31-127">**数据保留**</span><span class="sxs-lookup"><span data-stu-id="c5d31-127">**Data retention**</span></span> | <span data-ttu-id="c5d31-128">**信息保护**</span><span class="sxs-lookup"><span data-stu-id="c5d31-128">**Information protection**</span></span> |
| <span data-ttu-id="c5d31-129">1 级：业务价值较低（基准）</span><span class="sxs-lookup"><span data-stu-id="c5d31-129">Level 1: Low business value (Baseline)</span></span> | <span data-ttu-id="c5d31-130">允许所有人员访问</span><span class="sxs-lookup"><span data-stu-id="c5d31-130">Allow access to all</span></span>  | <span data-ttu-id="c5d31-131">6 个月</span><span class="sxs-lookup"><span data-stu-id="c5d31-131">6 months</span></span> | <span data-ttu-id="c5d31-132">使用加密</span><span class="sxs-lookup"><span data-stu-id="c5d31-132">Use encryption</span></span> |
| <span data-ttu-id="c5d31-133">2 级：业务价值中等（敏感）</span><span class="sxs-lookup"><span data-stu-id="c5d31-133">Level 2: Medium business value (Sensitive)</span></span> | <span data-ttu-id="c5d31-134">允许 Contoso 员工、分包商和合作伙伴访问</span><span class="sxs-lookup"><span data-stu-id="c5d31-134">Allow access to Contoso employees, subcontractors, and partners</span></span> <BR> <BR> <span data-ttu-id="c5d31-135">使用多重身份验证 (MFA)、传输层安全性 (TLS) 和移动应用管理 (MAM)</span><span class="sxs-lookup"><span data-stu-id="c5d31-135">Use multi-factor authentication (MFA), Transport Layer Security (TLS), and Mobile Application Management (MAM)</span></span> | <span data-ttu-id="c5d31-136">2 年</span><span class="sxs-lookup"><span data-stu-id="c5d31-136">2 years</span></span>  | <span data-ttu-id="c5d31-137">使用哈希值实现数据完整性</span><span class="sxs-lookup"><span data-stu-id="c5d31-137">Use hash values for data integrity</span></span>  |
| <span data-ttu-id="c5d31-138">3 级：高业务价值（高度管控）</span><span class="sxs-lookup"><span data-stu-id="c5d31-138">Level 3: High business value (Highly regulated)</span></span> | <span data-ttu-id="c5d31-139">允许工程设计和制造中的执行人员和潜在客户访问</span><span class="sxs-lookup"><span data-stu-id="c5d31-139">Allow access to executives and leads in engineering and manufacturing</span></span> <BR> <BR> <span data-ttu-id="c5d31-140">仅限托管网络设备的权限管理系统 (RMS)</span><span class="sxs-lookup"><span data-stu-id="c5d31-140">Rights Management System (RMS) with managed network devices only</span></span>  | <span data-ttu-id="c5d31-141">7 年</span><span class="sxs-lookup"><span data-stu-id="c5d31-141">7 years</span></span>  | <span data-ttu-id="c5d31-142">使用数字签名实现不可否认性</span><span class="sxs-lookup"><span data-stu-id="c5d31-142">Use digital signatures for non-repudiation</span></span>  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a><span data-ttu-id="c5d31-143">使用 Microsoft 365 企业版的 Contoso 信息保护路径</span><span class="sxs-lookup"><span data-stu-id="c5d31-143">Contoso’s path to information protection with Microsoft 365 Enterprise</span></span>

<span data-ttu-id="c5d31-144">Contoso 使用以下步骤为 Microsoft 365 企业版准备其信息保护要求：</span><span class="sxs-lookup"><span data-stu-id="c5d31-144">Contoso used the following steps to prepare Microsoft 365 Enterprise for their information protection requirements:</span></span>

1. <span data-ttu-id="c5d31-145">标识要保护的信息</span><span class="sxs-lookup"><span data-stu-id="c5d31-145">Identified what information to protect</span></span>

   <span data-ttu-id="c5d31-146">Contoso 对其现有数字资产进行了广泛审查，这些资产位于本地 SharePoint 网站和文件共享中，并对每一个资产都进行了分类。</span><span class="sxs-lookup"><span data-stu-id="c5d31-146">Contoso did an extensive review of their existing digital assets located on on-premises SharePoint sites and file shares and classified each one.</span></span>

2. <span data-ttu-id="c5d31-147">确定数据级别的访问策略、保留策略和信息保护策略</span><span class="sxs-lookup"><span data-stu-id="c5d31-147">Determined access, retention, and information protection policies for data levels</span></span>

   <span data-ttu-id="c5d31-148">Contoso 基于数据级别确定了详细的策略要求，这些要求被用于保护现有数字资产，因为它们被转移到了云中。</span><span class="sxs-lookup"><span data-stu-id="c5d31-148">Based on the data levels, Contoso determined detailed policy requirements, which were used to protect existing digital assets as they were moved to the cloud.</span></span>

3. <span data-ttu-id="c5d31-149">创建了 Azure 信息保护标签以及它们对不同级别信息的设置</span><span class="sxs-lookup"><span data-stu-id="c5d31-149">Created Azure Information Protection labels and their settings for the different levels of information</span></span>

   <span data-ttu-id="c5d31-p104">Contoso 修改了默认的 Azure 信息保护标签，其中的标题与它们的数据级别相匹配，并配置了“敏感”和“高度管控”标签，以通过 Azure 云密钥进行加密。他们为特定类型的商业机密数据创建了“高度管控”标签的子标签，并限制了他们对特定研发小组的访问。Contoso 还将 Azure 信息保护客户端部署到了所有 Windows 电脑和设备。</span><span class="sxs-lookup"><span data-stu-id="c5d31-p104">Contoso modified the default Azure Information Protection labels with the titles that match their data levels and configured the Sensitive and Highly regulated labels to encrypt with Azure cloud key. They created sub-labels of the Highly regulated label for specific types of trade secret data and confined their access to specific research and development groups. Contoso also deployed the Azure Information Protection client to all Windows PCs and devices.</span></span>

4. <span data-ttu-id="c5d31-153">为敏感和高度管控数据创建了受保护的 SharePoint Online 网站，同时包含锁定访问权限的权限</span><span class="sxs-lookup"><span data-stu-id="c5d31-153">Created protected SharePoint Online sites for sensitive and highly regulated data with permissions that lock down access</span></span>

   <span data-ttu-id="c5d31-p105">敏感和高度管控网站均配置为[独立网站](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites)，其中默认的 SharePoint Online 团队网站权限自定义到 Azure AD 组。敏感和高度管控的 SharePoint Online 网站也配置了默认 Office 365标签。高度管控的 SharePoint Online 网站中存储的文件受作用域内策略的 Azure 信息保护 (AIP) 子标签的保护。有关详细信息，请参阅[针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站](teams-sharepoint-online-sites-highly-regulated-data.md)方案。</span><span class="sxs-lookup"><span data-stu-id="c5d31-p105">Both sensitive and highly regulated sites were configured as [isolated sites](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites), in which the default SharePoint Online team site permissions were customized to Azure AD groups. Sensitive and highly regulated SharePoint Online sites were also configured with a default Office 365 label. Files stored in highly regulated SharePoint Online sites are protected with an Azure Information Protection (AIP) sub-label of a scoped policy. For more information, see the [Microsoft Teams and SharePoint Online sites for highly regulated data](teams-sharepoint-online-sites-highly-regulated-data.md) scenario.</span></span>

5.  <span data-ttu-id="c5d31-158">将数据从本地 SharePoint 网站和文件共享转移到新的 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="c5d31-158">Moved data from on-premises SharePoint sites and file shares to their new SharePoint Online sites</span></span>

    <span data-ttu-id="c5d31-159">迁移到新的 SharePoint Online 网站的文件继承了分配给该网站的默认 Office 365 标签。</span><span class="sxs-lookup"><span data-stu-id="c5d31-159">The files migrated to the new SharePoint Online sites inherited the default Office 365 labels assigned to the site.</span></span>

6.  <span data-ttu-id="c5d31-160">培训员工如何在新文档中使用 Azure 信息保护标签，如何在创建新的 SharePoint Online 网站时与 Contoso IT 进行交互，以及如何始终在 SharePoint Online 网站上存储数字资产。</span><span class="sxs-lookup"><span data-stu-id="c5d31-160">Trained employees on how to use Azure Information Protection labels for new documents, how to interact with Contoso IT when creating new SharePoint Online sites, and to always store digital assets on SharePoint Online sites</span></span>

    <span data-ttu-id="c5d31-161">Contoso IT 和管理被视为云信息保护过渡中最困难的部分，需要改变组织员工的不良信息存储习惯，以始终标记其数字资产，绝不使用本地文件共享。</span><span class="sxs-lookup"><span data-stu-id="c5d31-161">Considered the hardest part of the information protection transition for the cloud, Contoso IT and management needed to change the bad information storage habits of the organization’s employees to always label their digital assets and never use on-premises file shares.</span></span>

## <a name="conditional-access-policies-for-information-protection"></a><span data-ttu-id="c5d31-162">用于信息保护的条件访问策略</span><span class="sxs-lookup"><span data-stu-id="c5d31-162">Conditional access policies for information protection</span></span>

<span data-ttu-id="c5d31-163">与身份标识和移动设备管理基础结构结合使用，并作为他们推出 Exchange Online 和 SharePoint Online 的一部分，Contoso 配置了以下一组条件访问策略，并将其应用到相应的 Azure AD 组：</span><span class="sxs-lookup"><span data-stu-id="c5d31-163">In conjunction with their identity and mobile device management infrastructure and as part of their rollout of Exchange Online and SharePoint Online, Contoso configured the following set of conditional access policies and applied them to the appropriate Azure AD groups:</span></span>

- [<span data-ttu-id="c5d31-164">设备策略上的托管和非托管应用程序访问</span><span class="sxs-lookup"><span data-stu-id="c5d31-164">Managed and unmanaged application access on devices policies</span></span>](identity-access-policies.md)
- [<span data-ttu-id="c5d31-165">Exchange Online 访问策略</span><span class="sxs-lookup"><span data-stu-id="c5d31-165">Exchange Online access policies</span></span>](secure-email-recommended-policies.md)
- [<span data-ttu-id="c5d31-166">SharePoint Online 访问策略</span><span class="sxs-lookup"><span data-stu-id="c5d31-166">SharePoint Online access policies</span></span>](sharepoint-file-access-policies.md)

<span data-ttu-id="c5d31-167">图 1 显示 Contoso 信息保护策略的结果集。</span><span class="sxs-lookup"><span data-stu-id="c5d31-167">Figure 1 shows Contoso's resulting set of policies for information protection.</span></span>

![](./media/contoso-info-protect/contoso-info-protect-fig1.png)

<span data-ttu-id="c5d31-168">**图 1：设备、Exchange Online 和 SharePoint Online 的条件访问策略**</span><span class="sxs-lookup"><span data-stu-id="c5d31-168">**Figure 1: Device, Exchange Online, and SharePoint Online conditional access policies**</span></span>
 
>[!Note]
><span data-ttu-id="c5d31-p106">此外，Contoso 还配置了其他条件访问策略用于标识和登录。请参阅 [Contoso Corporation 的标识](contoso-identity.md)。</span><span class="sxs-lookup"><span data-stu-id="c5d31-p106">Contoso also configured additional conditional access policies for identity and sign-in. See [Identity for the Contoso Corporation](contoso-identity.md).</span></span>
>

<span data-ttu-id="c5d31-171">这些策略确保：</span><span class="sxs-lookup"><span data-stu-id="c5d31-171">These policies ensure that:</span></span>

- <span data-ttu-id="c5d31-172">应用保护政策定义哪些应用程序是允许的，以及它们可以使用组织数据执行哪些操作。</span><span class="sxs-lookup"><span data-stu-id="c5d31-172">App protection policies define which apps are allowed and the actions they can take with your organization data.</span></span>
- <span data-ttu-id="c5d31-173">电脑和移动设备必须兼容。</span><span class="sxs-lookup"><span data-stu-id="c5d31-173">PCs and mobile devices must be compliant.</span></span>
- <span data-ttu-id="c5d31-174">Exchange Online 使用 Exchange Online 的 Office 365 邮件加密。</span><span class="sxs-lookup"><span data-stu-id="c5d31-174">Exchange Online uses Office 365 message encryption for Exchange Online.</span></span>
- <span data-ttu-id="c5d31-175">SharePoint Online 使用应用强制的限制。</span><span class="sxs-lookup"><span data-stu-id="c5d31-175">SharePoint Online uses app enforced restrictions.</span></span>
- <span data-ttu-id="c5d31-176">SharePoint Online 使用访问控制策略进行仅浏览器访问并阻止非托管设备的访问。</span><span class="sxs-lookup"><span data-stu-id="c5d31-176">SharePoint Online uses access control policies for browser-only access and to block access for unmanaged devices.</span></span>

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a><span data-ttu-id="c5d31-177">将 Microsoft 365 企业版功能映射到 Contoso 的数据级别</span><span class="sxs-lookup"><span data-stu-id="c5d31-177">Mapping Microsoft 365 Enterprise features to Contoso's data levels</span></span>

<span data-ttu-id="c5d31-178">下表显示 Contoso 的数据级别在 Microsoft 365 企业版信息保护功能中的映射。</span><span class="sxs-lookup"><span data-stu-id="c5d31-178">The following table shows the mapping the Contoso's data levels to information protection features in Microsoft 365 Enterprise.</span></span>

|||||
|:-------|:-----|:-----|:-----|
| | <span data-ttu-id="c5d31-179">**Office 365**</span><span class="sxs-lookup"><span data-stu-id="c5d31-179">**Office 365**</span></span> | <span data-ttu-id="c5d31-180">**Windows 10 和 Office 365 专业增强版**</span><span class="sxs-lookup"><span data-stu-id="c5d31-180">**Windows 10 and Office 365 ProPlus**</span></span> | <span data-ttu-id="c5d31-181">**EMS**</span><span class="sxs-lookup"><span data-stu-id="c5d31-181">**EMS**</span></span> |
| <span data-ttu-id="c5d31-182">1 级：基准</span><span class="sxs-lookup"><span data-stu-id="c5d31-182">Level 1: Baseline</span></span>  | <span data-ttu-id="c5d31-183">SharePoint Online 和 Exchange Online 条件访问策略</span><span class="sxs-lookup"><span data-stu-id="c5d31-183">SharePoint Online and Exchange Online conditional access policies</span></span> <BR> <span data-ttu-id="c5d31-184">SharePoint Online 网站的权限</span><span class="sxs-lookup"><span data-stu-id="c5d31-184">Permissions on SharePoint Online sites</span></span> | <span data-ttu-id="c5d31-185">Azure 信息保护客户端</span><span class="sxs-lookup"><span data-stu-id="c5d31-185">Azure Information Protection client</span></span> <BR> <span data-ttu-id="c5d31-186">BitLocker</span><span class="sxs-lookup"><span data-stu-id="c5d31-186">BitLocker</span></span> <BR> <span data-ttu-id="c5d31-187">Windows 信息保护</span><span class="sxs-lookup"><span data-stu-id="c5d31-187">Windows Information Protection</span></span> | <span data-ttu-id="c5d31-188">设备条件访问策略和移动应用管理策略</span><span class="sxs-lookup"><span data-stu-id="c5d31-188">Device conditional access policies and Mobile Application Management policies</span></span> |
| <span data-ttu-id="c5d31-189">2 级：高度敏感</span><span class="sxs-lookup"><span data-stu-id="c5d31-189">Level 2: Highly sensitive</span></span> | <span data-ttu-id="c5d31-190">1 级：基准再加上：</span><span class="sxs-lookup"><span data-stu-id="c5d31-190">Level 1: Baseline plus:</span></span> <BR> <BR> <span data-ttu-id="c5d31-191">Azure 信息保护标签</span><span class="sxs-lookup"><span data-stu-id="c5d31-191">Azure Information Protection labels</span></span> <BR> <span data-ttu-id="c5d31-192">SharePoint Online 网站上的 Office 365 标签</span><span class="sxs-lookup"><span data-stu-id="c5d31-192">Office 365 labels on SharePoint Online sites</span></span> <BR> <span data-ttu-id="c5d31-193">用于 SharePoint Online 和 Exchange Online 的 Office 365 数据丢失防护</span><span class="sxs-lookup"><span data-stu-id="c5d31-193">Office 365 Data Loss Prevention for SharePoint Online and Exchange Online</span></span> <BR> <span data-ttu-id="c5d31-194">独立 SharePoint Online 网站</span><span class="sxs-lookup"><span data-stu-id="c5d31-194">Isolated SharePoint Online sites</span></span>  | <span data-ttu-id="c5d31-195">1 级：基准再加上：</span><span class="sxs-lookup"><span data-stu-id="c5d31-195">Level 1: Baseline plus:</span></span> <BR> <BR> <span data-ttu-id="c5d31-196">数字资产上的 Azure 信息保护标签</span><span class="sxs-lookup"><span data-stu-id="c5d31-196">Azure Information Protection labels on digital assets</span></span> <BR> <span data-ttu-id="c5d31-197">Office 365 高级数据管理</span><span class="sxs-lookup"><span data-stu-id="c5d31-197">Office 365 Advanced Data Governance</span></span> | <span data-ttu-id="c5d31-198">1 级：基准</span><span class="sxs-lookup"><span data-stu-id="c5d31-198">Level 1: Baseline</span></span> |
| <span data-ttu-id="c5d31-199">3 级：高度管控</span><span class="sxs-lookup"><span data-stu-id="c5d31-199">Level 3: Highly regulated</span></span> | <span data-ttu-id="c5d31-200">2 级：高度敏感再加上：</span><span class="sxs-lookup"><span data-stu-id="c5d31-200">Level 2: Highly sensitive plus:</span></span> <BR><BR> <span data-ttu-id="c5d31-201">针对商业机密信息的自带密钥 (BYOK) 加密和保护</span><span class="sxs-lookup"><span data-stu-id="c5d31-201">Bring Your Own Key (BYOK) encryption and protection for trade secret information</span></span> <BR> <span data-ttu-id="c5d31-202">将 Azure Key Vault 用于与 Office 365 服务交互的业务线应用程序</span><span class="sxs-lookup"><span data-stu-id="c5d31-202">Azure Key Vault for line of business applications that interact with Office 365 services</span></span> | <span data-ttu-id="c5d31-203">2 级：高度敏感</span><span class="sxs-lookup"><span data-stu-id="c5d31-203">Level 2: Highly sensitive</span></span> | <span data-ttu-id="c5d31-204">1 级：基准</span><span class="sxs-lookup"><span data-stu-id="c5d31-204">Level 1: Baseline</span></span> |
|||||


## <a name="next-step"></a><span data-ttu-id="c5d31-205">后续步骤</span><span class="sxs-lookup"><span data-stu-id="c5d31-205">Next step</span></span>

<span data-ttu-id="c5d31-206">[请参阅](contoso-security-summary.md) Contoso 如何使用安全功能跨 Microsoft 365 企业版实现身份识别和访问管理、威胁防护、信息保护以及安全管理。</span><span class="sxs-lookup"><span data-stu-id="c5d31-206">[See](contoso-security-summary.md) how Contoso has used the security features across Microsoft 365 Enterprise for identity and access management, threat protection, information protection, and security management.</span></span>

## <a name="see-also"></a><span data-ttu-id="c5d31-207">另请参阅</span><span class="sxs-lookup"><span data-stu-id="c5d31-207">See also</span></span>

[<span data-ttu-id="c5d31-208">Microsoft 365 企业版信息保护</span><span class="sxs-lookup"><span data-stu-id="c5d31-208">Information protection for Microsoft 365 Enterprise</span></span>](infoprotect-infrastructure.md)

[<span data-ttu-id="c5d31-209">部署指南</span><span class="sxs-lookup"><span data-stu-id="c5d31-209">Deployment guide</span></span>](deploy-microsoft-365-enterprise.md)

[<span data-ttu-id="c5d31-210">测试实验室指南</span><span class="sxs-lookup"><span data-stu-id="c5d31-210">Test lab guides</span></span>](m365-enterprise-test-lab-guides.md)


