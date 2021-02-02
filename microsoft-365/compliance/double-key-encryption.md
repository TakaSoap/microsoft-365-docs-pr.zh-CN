---
title: 双密钥加密(DKE)
description: DKE 使你能够保护高度敏感数据，同时保持对密钥的完全控制。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 01/29/2021
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: c10a10a5922755db2c901137c3dff8acee5b8445
ms.sourcegitcommit: c550c1b5b9e67398fd95bfb0256c4f5c7930b2be
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/01/2021
ms.locfileid: "50066855"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="33ee5-103">Microsoft 365 的双密钥加密</span><span class="sxs-lookup"><span data-stu-id="33ee5-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="33ee5-104">*适用于：Microsoft 365 的双密钥加密 [、Microsoft 365 合规性](https://www.microsoft.com/microsoft-365/business/compliance-management)[、Azure 信息保护](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="33ee5-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="33ee5-105">*说明： [适用于 Windows 的 Azure 信息保护统一标签客户端](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="33ee5-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="33ee5-106">*服务说明 [：Microsoft 365 合规性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="33ee5-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="33ee5-107">双密钥加密 (DKE) 使用两个密钥来访问受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="33ee5-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="33ee5-108">Microsoft 在 Microsoft Azure 中存储一个密钥，并且你持有另一个密钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="33ee5-109">使用双密钥加密服务维护对其中一个密钥的完全控制。</span><span class="sxs-lookup"><span data-stu-id="33ee5-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="33ee5-110">使用 Azure 信息保护统一标签客户端对高度敏感的内容应用保护。</span><span class="sxs-lookup"><span data-stu-id="33ee5-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="33ee5-111">双密钥加密支持云和本地部署。</span><span class="sxs-lookup"><span data-stu-id="33ee5-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="33ee5-112">这些部署有助于确保加密数据在存储受保护数据的位置都保持不透明。</span><span class="sxs-lookup"><span data-stu-id="33ee5-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="33ee5-113">有关默认的基于云的租户根密钥详细信息，请参阅规划和 [实现 Azure 信息保护租户密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="33ee5-114">组织何时应采用 DKE</span><span class="sxs-lookup"><span data-stu-id="33ee5-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="33ee5-115">双密钥加密适用于符合最严格保护要求的最敏感数据。</span><span class="sxs-lookup"><span data-stu-id="33ee5-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="33ee5-116">DKE 不用于所有数据。</span><span class="sxs-lookup"><span data-stu-id="33ee5-116">DKE is not intended for all data.</span></span> <span data-ttu-id="33ee5-117">通常，你将使用双密钥加密来保护整个数据的一小部分。</span><span class="sxs-lookup"><span data-stu-id="33ee5-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="33ee5-118">在部署之前，应谨慎确定此解决方案要涵盖的合适数据。</span><span class="sxs-lookup"><span data-stu-id="33ee5-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="33ee5-119">在某些情况下，可能需要缩小范围，并针对大多数数据使用其他解决方案，例如 Microsoft 信息保护与 Microsoft 托管密钥或 BYOK。</span><span class="sxs-lookup"><span data-stu-id="33ee5-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="33ee5-120">这些解决方案足以用于不受增强保护和法规要求限制的文档。</span><span class="sxs-lookup"><span data-stu-id="33ee5-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="33ee5-121">此外，这些解决方案还使您能够使用最强大的 Office 365 服务;不能与 DKE 加密内容一同使用的服务。</span><span class="sxs-lookup"><span data-stu-id="33ee5-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="33ee5-122">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-122">For example:</span></span>

- <span data-ttu-id="33ee5-123">需要查看附件的传输规则，包括反恶意软件和垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="33ee5-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="33ee5-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="33ee5-124">Microsoft Delve</span></span>
- <span data-ttu-id="33ee5-125">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="33ee5-125">eDiscovery</span></span>
- <span data-ttu-id="33ee5-126">内容搜索和索引</span><span class="sxs-lookup"><span data-stu-id="33ee5-126">Content search and indexing</span></span>
- <span data-ttu-id="33ee5-127">包括共同授权功能的 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="33ee5-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="33ee5-128">任何未通过 MIP SDK 与 DKE 集成的外部应用程序或服务将无法对加密数据执行操作。</span><span class="sxs-lookup"><span data-stu-id="33ee5-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="33ee5-129">Microsoft 信息保护 SDK 1.7+ 支持双密钥加密;与 SDK 集成的应用程序将能够通过足够的权限和集成来了解此数据。</span><span class="sxs-lookup"><span data-stu-id="33ee5-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="33ee5-130">我们建议组织使用 Microsoft 信息保护 (分类和标签) 来保护其大部分敏感数据，并且仅将 DKE 用于其任务关键型数据。</span><span class="sxs-lookup"><span data-stu-id="33ee5-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="33ee5-131">双密钥加密与高度管控行业（如金融服务和医疗保健）中的敏感数据相关。</span><span class="sxs-lookup"><span data-stu-id="33ee5-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="33ee5-132">如果你的组织有以下任一要求，可以使用 DKE 来帮助保护内容的安全：</span><span class="sxs-lookup"><span data-stu-id="33ee5-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="33ee5-133">您希望确保在任何情况下 *仅* 可以解密受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="33ee5-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="33ee5-134">你不希望 Microsoft 自行访问受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="33ee5-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="33ee5-135">您具有在地理边界内保留密钥的法规要求。</span><span class="sxs-lookup"><span data-stu-id="33ee5-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="33ee5-136">您保留用于数据加密和解密的所有密钥都维护在数据中心中。</span><span class="sxs-lookup"><span data-stu-id="33ee5-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="33ee5-137">DKE 的系统和许可要求</span><span class="sxs-lookup"><span data-stu-id="33ee5-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="33ee5-138">**Microsoft 365** 的双密钥加密随 Microsoft 365 E5 一起提供。</span><span class="sxs-lookup"><span data-stu-id="33ee5-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="33ee5-139">如果你没有 Microsoft 365 E5 许可证，可以[注册试用版。](https://aka.ms/M365E5ComplianceTrial)</span><span class="sxs-lookup"><span data-stu-id="33ee5-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="33ee5-140">有关这些许可证详细信息，请参阅 [Microsoft 365 安全与合规&指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="33ee5-141">**Azure 信息保护**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-141">**Azure Information Protection**.</span></span> <span data-ttu-id="33ee5-142">DKE 适用于敏感度标签，并且需要 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="33ee5-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="33ee5-143">DKE 敏感度标签通过 Office 桌面应用程序中的敏感度功能区提供给最终用户。</span><span class="sxs-lookup"><span data-stu-id="33ee5-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="33ee5-144">在要保护和使用受保护文档的每台客户端计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="33ee5-145">**Microsoft Office应用程序企业** 版 \*.12711 或更高版本 (Windows 上的 Word、PowerPoint 和 Excel) 桌面版。</span><span class="sxs-lookup"><span data-stu-id="33ee5-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="33ee5-146">**Azure 信息保护统一标签客户端** 版本 2.7.93.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="33ee5-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="33ee5-147">从 Microsoft 下载中心下载并安装统一 [标签客户端](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="33ee5-148">用于存储和查看受 DKE 保护的内容的支持环境</span><span class="sxs-lookup"><span data-stu-id="33ee5-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="33ee5-149">**支持的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-149">**Supported applications**.</span></span> <span data-ttu-id="33ee5-150">[Windows 上的 Microsoft 365](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) 企业应用版客户端，包括 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="33ee5-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="33ee5-151">**联机内容支持**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-151">**Online content support**.</span></span> <span data-ttu-id="33ee5-152">支持联机存储在 Microsoft SharePoint 和 OneDrive for Business 中的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="33ee5-153">可以通过电子邮件共享加密内容，但无法联机查看加密的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="33ee5-154">相反，你必须在本地计算机上使用桌面应用查看受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="33ee5-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="33ee5-155">部署 DKE 概述</span><span class="sxs-lookup"><span data-stu-id="33ee5-155">Overview of deploying DKE</span></span>

<span data-ttu-id="33ee5-156">按照这些常规步骤设置 DKE。</span><span class="sxs-lookup"><span data-stu-id="33ee5-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="33ee5-157">完成这些步骤后，最终用户可以使用双密钥加密来保护高度敏感数据。</span><span class="sxs-lookup"><span data-stu-id="33ee5-157">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="33ee5-158">部署 DKE 服务，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="33ee5-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="33ee5-159">使用双密钥加密创建标签。</span><span class="sxs-lookup"><span data-stu-id="33ee5-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="33ee5-160">导航到 [Microsoft 365 合规](https://compliance.microsoft.com) 中心下的信息保护，然后使用双密钥加密创建新标签。</span><span class="sxs-lookup"><span data-stu-id="33ee5-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="33ee5-161">请参阅 [使用敏感度标签应用加密来限制对内容的访问](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="33ee5-162">使用双密钥加密标签。</span><span class="sxs-lookup"><span data-stu-id="33ee5-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="33ee5-163">通过从"敏感度"功能区中选择"双密钥加密"标签来保护Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="33ee5-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="33ee5-164">有几种方法可以完成部署双密钥加密的一些步骤。</span><span class="sxs-lookup"><span data-stu-id="33ee5-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="33ee5-165">本文提供了详细说明，以便经验不足的管理员能够成功部署服务。</span><span class="sxs-lookup"><span data-stu-id="33ee5-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="33ee5-166">如果习惯这样做，可以选择使用自己的方法。</span><span class="sxs-lookup"><span data-stu-id="33ee5-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="33ee5-167">部署 DKE</span><span class="sxs-lookup"><span data-stu-id="33ee5-167">Deploy DKE</span></span>

<span data-ttu-id="33ee5-168">本文和部署视频使用 Azure 作为 DKE 服务的部署目标。</span><span class="sxs-lookup"><span data-stu-id="33ee5-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="33ee5-169">如果要部署到其他位置，则需要提供自己的值。</span><span class="sxs-lookup"><span data-stu-id="33ee5-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="33ee5-170">观看 [双密钥加密部署视频](https://youtu.be/vDWfHN_kygg) ，查看本文中概念的分步概述。</span><span class="sxs-lookup"><span data-stu-id="33ee5-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="33ee5-171">视频大约需要 18 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="33ee5-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="33ee5-172">按照这些常规步骤为组织设置双密钥加密。</span><span class="sxs-lookup"><span data-stu-id="33ee5-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="33ee5-173">安装 DKE 服务的必备软件</span><span class="sxs-lookup"><span data-stu-id="33ee5-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="33ee5-174">克隆双密钥加密 GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="33ee5-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="33ee5-175">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="33ee5-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="33ee5-176">生成测试密钥</span><span class="sxs-lookup"><span data-stu-id="33ee5-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="33ee5-177">生成项目</span><span class="sxs-lookup"><span data-stu-id="33ee5-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="33ee5-178">部署 DKE 服务并发布密钥存储</span><span class="sxs-lookup"><span data-stu-id="33ee5-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="33ee5-179">验证部署</span><span class="sxs-lookup"><span data-stu-id="33ee5-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="33ee5-180">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="33ee5-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="33ee5-181">使用 DKE 创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="33ee5-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="33ee5-182">在客户端中启用 DKE</span><span class="sxs-lookup"><span data-stu-id="33ee5-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="33ee5-183">将受保护的文件从 HYOK 标签迁移到 DKE 标签</span><span class="sxs-lookup"><span data-stu-id="33ee5-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="33ee5-184">完成后，可以使用 DKE 加密文档和文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="33ee5-185">有关信息，请参阅在 Office 中将敏感度标签 [应用于文件和电子邮件](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="33ee5-186">安装 DKE 服务的必备软件</span><span class="sxs-lookup"><span data-stu-id="33ee5-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="33ee5-187">在要安装 DKE 服务的计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="33ee5-188">**.NET Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="33ee5-189">从下载[.NET Core 3.1 下载并安装 SDK。](https://dotnet.microsoft.com/download/dotnet-core/3.1)</span><span class="sxs-lookup"><span data-stu-id="33ee5-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="33ee5-190">**Visual Studio代码**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-190">**Visual Studio Code**.</span></span> <span data-ttu-id="33ee5-191">从 Visual Studio 下载代码 [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="33ee5-192">安装完成后，运行Visual Studio代码并选择 **"查看** \> **扩展"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="33ee5-193">安装这些扩展。</span><span class="sxs-lookup"><span data-stu-id="33ee5-193">Install these extensions.</span></span>

- <span data-ttu-id="33ee5-194">C# Visual Studio代码</span><span class="sxs-lookup"><span data-stu-id="33ee5-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="33ee5-195">NuGet 程序包管理器</span><span class="sxs-lookup"><span data-stu-id="33ee5-195">NuGet Package Manager</span></span>

<span data-ttu-id="33ee5-196">**Git 资源**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-196">**Git resources**.</span></span> <span data-ttu-id="33ee5-197">下载并安装以下项之一。</span><span class="sxs-lookup"><span data-stu-id="33ee5-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="33ee5-198">Git</span><span class="sxs-lookup"><span data-stu-id="33ee5-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="33ee5-199">GitHub 桌面</span><span class="sxs-lookup"><span data-stu-id="33ee5-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="33ee5-200">GitHub 企业版</span><span class="sxs-lookup"><span data-stu-id="33ee5-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="33ee5-201">**OpenSSL** 部署 DKE 后，必须安装 [](#generate-test-keys) [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html)以生成测试密钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="33ee5-202">确保从环境变量路径正确调用它。</span><span class="sxs-lookup"><span data-stu-id="33ee5-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="33ee5-203">例如，有关详细信息，请参阅"将安装目录添加到 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) PATH"。</span><span class="sxs-lookup"><span data-stu-id="33ee5-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="33ee5-204">克隆 DKE GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="33ee5-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="33ee5-205">Microsoft 在 GitHub 存储库中提供 DKE 源文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="33ee5-206">克隆存储库以在本地生成项目供组织使用。</span><span class="sxs-lookup"><span data-stu-id="33ee5-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="33ee5-207">DKE GitHub 存储库位于 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="33ee5-208">以下说明适用于没有经验的 git 或 Visual Studio 代码用户：</span><span class="sxs-lookup"><span data-stu-id="33ee5-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="33ee5-209">在浏览器中， [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 转到：</span><span class="sxs-lookup"><span data-stu-id="33ee5-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="33ee5-210">在屏幕右侧，选择"**代码"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="33ee5-211">你的 UI 版本可能会显示"克隆 **"或"下载"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="33ee5-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="33ee5-212">然后，在出现的下拉列表中，选择复制图标以将 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="33ee5-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="33ee5-213">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-213">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33ee5-214">![从 GitHub 克隆双密钥加密服务存储库](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="33ee5-214">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="33ee5-215">在Visual Studio，选择 **"查看** \> **命令调色板**"，然后选择 **"Git： 克隆"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="33ee5-216">若要跳转到列表中的选项，请开始键入以筛选条目，然后从下拉列表 `git: clone` 中选择它。</span><span class="sxs-lookup"><span data-stu-id="33ee5-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="33ee5-217">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-217">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33ee5-218">![Visual Studio代码 GIT：Clone 选项](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="33ee5-218">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="33ee5-219">在文本框中，粘贴从 Git 复制的 URL，然后从 **GitHub 中选择"克隆"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="33ee5-220">在 **出现的"** 选择文件夹"对话框中，浏览到存储库并选择要存储存储库的位置。</span><span class="sxs-lookup"><span data-stu-id="33ee5-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="33ee5-221">在提示符下，选择"**打开"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="33ee5-222">存储库在Visual Studio中打开，并显示左下角的当前 Git 分支。</span><span class="sxs-lookup"><span data-stu-id="33ee5-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="33ee5-223">例如，分支应为 **主** 分支。</span><span class="sxs-lookup"><span data-stu-id="33ee5-223">For example,  The branch should be **main**.</span></span> <span data-ttu-id="33ee5-224">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-224">For example:</span></span>

   ![显示主分支的 Visual Studio 代码中的 DKE 存储库屏幕截图](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="33ee5-226">如果你不在主分支上，则需要选择它。</span><span class="sxs-lookup"><span data-stu-id="33ee5-226">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="33ee5-227">在Visual Studio代码中，选择分支 **，然后从** 显示的分支列表中选择主分支。</span><span class="sxs-lookup"><span data-stu-id="33ee5-227">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="33ee5-228">选择主分支可确保您具有用于生成项目的正确文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-228">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="33ee5-229">如果未选择正确的分支，部署将失败。</span><span class="sxs-lookup"><span data-stu-id="33ee5-229">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="33ee5-230">现在，你已在本地设置 DKE 源存储库。</span><span class="sxs-lookup"><span data-stu-id="33ee5-230">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="33ee5-231">接下来 [，修改组织](#modify-application-settings) 的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="33ee5-231">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="33ee5-232">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="33ee5-232">Modify application settings</span></span>

<span data-ttu-id="33ee5-233">若要部署 DKE 服务，必须修改以下类型的应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="33ee5-233">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="33ee5-234">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="33ee5-234">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="33ee5-235">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="33ee5-235">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="33ee5-236">修改文件上的appsettings.js设置。</span><span class="sxs-lookup"><span data-stu-id="33ee5-236">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="33ee5-237">此文件位于在 DoubleKeyEncryptionService\src\customer-key-store 下本地克隆的 DoubleKeyEncryptionService 存储库。</span><span class="sxs-lookup"><span data-stu-id="33ee5-237">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="33ee5-238">例如，在Visual Studio代码中，您可以浏览到该文件，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="33ee5-238">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![在文件上appsettings.jsDKE 的配置文件。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="33ee5-240">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="33ee5-240">Key access settings</span></span>

<span data-ttu-id="33ee5-241">选择是使用电子邮件还是角色授权。</span><span class="sxs-lookup"><span data-stu-id="33ee5-241">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="33ee5-242">DKE 一次仅支持其中一种身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="33ee5-242">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="33ee5-243">**电子邮件授权**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-243">**Email authorization**.</span></span> <span data-ttu-id="33ee5-244">允许组织仅根据电子邮件地址授权访问密钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-244">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="33ee5-245">**角色授权**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-245">**Role authorization**.</span></span> <span data-ttu-id="33ee5-246">允许组织根据 Active Directory 组授权访问密钥，并需要 Web 服务可以查询 LDAP。</span><span class="sxs-lookup"><span data-stu-id="33ee5-246">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="33ee5-247">**使用电子邮件授权为 DKE 设置密钥访问设置**</span><span class="sxs-lookup"><span data-stu-id="33ee5-247">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="33ee5-248">打开 **appsettings.js并** 找到 `AuthorizedEmailAddress` 该设置。</span><span class="sxs-lookup"><span data-stu-id="33ee5-248">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="33ee5-249">添加要授权的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="33ee5-249">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="33ee5-250">用双引号和逗号分隔多个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="33ee5-250">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="33ee5-251">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-251">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="33ee5-252">找到 `LDAPPath` 该设置并删除双引号 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 之间的文本。</span><span class="sxs-lookup"><span data-stu-id="33ee5-252">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="33ee5-253">保留双引号。</span><span class="sxs-lookup"><span data-stu-id="33ee5-253">Leave the double quotes in place.</span></span> <span data-ttu-id="33ee5-254">完成后，设置应如下所示。</span><span class="sxs-lookup"><span data-stu-id="33ee5-254">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="33ee5-255">找到 `AuthorizedRoles` 该设置并删除整行。</span><span class="sxs-lookup"><span data-stu-id="33ee5-255">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="33ee5-256">此 **图像显示appsettings.js** 正确设置格式的电子邮件授权文件上的名称。</span><span class="sxs-lookup"><span data-stu-id="33ee5-256">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![显示appsettings.js方法的文件的扩展名](../media/dke-email-accesssetting.png)

<span data-ttu-id="33ee5-258">**使用角色授权设置 DKE 的密钥访问设置**</span><span class="sxs-lookup"><span data-stu-id="33ee5-258">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="33ee5-259">打开 **appsettings.js并** 找到 `AuthorizedRoles` 该设置。</span><span class="sxs-lookup"><span data-stu-id="33ee5-259">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="33ee5-260">添加要授权的 Active Directory 组名称。</span><span class="sxs-lookup"><span data-stu-id="33ee5-260">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="33ee5-261">用双引号和逗号分隔多个组名称。</span><span class="sxs-lookup"><span data-stu-id="33ee5-261">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="33ee5-262">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-262">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="33ee5-263">找到 `LDAPPath` 该设置并添加 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="33ee5-263">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="33ee5-264">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-264">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="33ee5-265">找到 `AuthorizedEmailAddress` 该设置并删除整行。</span><span class="sxs-lookup"><span data-stu-id="33ee5-265">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="33ee5-266">此 **图显示了appsettings.js** 角色授权正确设置格式的文件上的名称。</span><span class="sxs-lookup"><span data-stu-id="33ee5-266">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.js显示角色授权方法的文件](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="33ee5-268">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="33ee5-268">Tenant and key settings</span></span>

<span data-ttu-id="33ee5-269">DKE 租户和密钥设置位于appsettings.js **文件中** 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-269">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="33ee5-270">**为 DKE 配置租户和密钥设置**</span><span class="sxs-lookup"><span data-stu-id="33ee5-270">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="33ee5-271">打开 **appsettings.js文件** 上的文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-271">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="33ee5-272">找到 `ValidIssuers` 该设置， `<tenantid>` 并替换为租户 ID。</span><span class="sxs-lookup"><span data-stu-id="33ee5-272">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="33ee5-273">可以通过访问 Azure 门户并查看租户属性找到[租户 ID。](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="33ee5-273">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="33ee5-274">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-274">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="33ee5-275">找到 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-275">Locate the `JwtAudience`.</span></span> <span data-ttu-id="33ee5-276">替换为 `<yourhostname>` 运行 DKE 服务的主机名。</span><span class="sxs-lookup"><span data-stu-id="33ee5-276">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="33ee5-277">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-277">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="33ee5-278">其值 `JwtAudience` 必须与主机的名称完全 *匹配*。</span><span class="sxs-lookup"><span data-stu-id="33ee5-278">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="33ee5-279">调试时可以使用 **localhost：5001。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-279">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="33ee5-280">但是，完成调试后，请确保将此值更新为服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="33ee5-280">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="33ee5-281">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="33ee5-281">`TestKeys:Name`.</span></span> <span data-ttu-id="33ee5-282">输入密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="33ee5-282">Enter a name for your key.</span></span> <span data-ttu-id="33ee5-283">例如：`TestKey1`</span><span class="sxs-lookup"><span data-stu-id="33ee5-283">For example: `TestKey1`</span></span>
- <span data-ttu-id="33ee5-284">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="33ee5-284">`TestKeys:Id`.</span></span> <span data-ttu-id="33ee5-285">创建 GUID 并输入为 `TestKeys:ID` 值。</span><span class="sxs-lookup"><span data-stu-id="33ee5-285">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="33ee5-286">例如，`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`。</span><span class="sxs-lookup"><span data-stu-id="33ee5-286">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="33ee5-287">可以使用在线 [GUID 生成器](https://guidgenerator.com/) 等网站随机生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="33ee5-287">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="33ee5-288">此图像显示租户和密钥设置在appsettings.js **中的正确格式**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-288">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="33ee5-289">`LDAPPath` 配置为进行角色授权。</span><span class="sxs-lookup"><span data-stu-id="33ee5-289">`LDAPPath` is configured for role authorization.</span></span>

![在文件上的策略中显示 DKE 的正确appsettings.js和密钥设置。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="33ee5-291">生成测试密钥</span><span class="sxs-lookup"><span data-stu-id="33ee5-291">Generate test keys</span></span>

<span data-ttu-id="33ee5-292">定义应用程序设置后，即可生成公钥和私钥测试密钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-292">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="33ee5-293">生成密钥：</span><span class="sxs-lookup"><span data-stu-id="33ee5-293">To generate keys:</span></span>

1. <span data-ttu-id="33ee5-294">从 Windows"开始"菜单运行 OpenSSL 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="33ee5-294">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="33ee5-295">更改为要保存测试密钥的文件夹。</span><span class="sxs-lookup"><span data-stu-id="33ee5-295">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="33ee5-296">通过完成此任务中的步骤创建的文件存储在同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="33ee5-296">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="33ee5-297">生成新的测试密钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-297">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="33ee5-298">生成私钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-298">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="33ee5-299">生成公钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-299">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="33ee5-300">在文本编辑器中，打开 **pubkeyonly.pem。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-300">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="33ee5-301">将 **pubkeyonly.pem** 文件（第一行和最后一行 `PublicPem` 除外）中appsettings.js **文件** 的内容。</span><span class="sxs-lookup"><span data-stu-id="33ee5-301">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="33ee5-302">在文本编辑器中，**打开nopass.pem。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-302">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="33ee5-303">将 **appsettings.js.pem** 文件（第一行和最后一行除外 `PrivatePem` **）中appsettings.js文件** 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-303">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="33ee5-304">删除和分区中所有空格和 `PublicPem` `PrivatePem` 新行。</span><span class="sxs-lookup"><span data-stu-id="33ee5-304">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="33ee5-305">复制此内容时，不要删除任何 PEM 数据。</span><span class="sxs-lookup"><span data-stu-id="33ee5-305">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="33ee5-306">在Visual Studio中，浏览 **到Startup.cs文件** 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-306">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="33ee5-307">此文件位于在 DoubleKeyEncryptionService\src\customer-key-store\下本地克隆的 DoubleKeyEncryptionService 存储库。</span><span class="sxs-lookup"><span data-stu-id="33ee5-307">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="33ee5-308">找到以下行：</span><span class="sxs-lookup"><span data-stu-id="33ee5-308">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="33ee5-309">将以下行替换为以下文本：</span><span class="sxs-lookup"><span data-stu-id="33ee5-309">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="33ee5-310">最终结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="33ee5-310">The end results should look similar to the following.</span></span>

    ![startup.cs预览的预览文件](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="33ee5-312">现在，你已准备好 [生成你的 DKE 项目](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-312">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="33ee5-313">生成项目</span><span class="sxs-lookup"><span data-stu-id="33ee5-313">Build the project</span></span>

<span data-ttu-id="33ee5-314">使用以下说明在本地生成 DKE 项目：</span><span class="sxs-lookup"><span data-stu-id="33ee5-314">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="33ee5-315">在Visual Studio代码的 DKE 服务存储库中，选择 **"查看** 命令调色板"， \> 然后在提示 **符** 处键入生成。</span><span class="sxs-lookup"><span data-stu-id="33ee5-315">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="33ee5-316">从列表中选择"**任务： 运行生成任务"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-316">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="33ee5-317">如果没有找到生成任务，请选择" **配置** 生成任务"，然后为 .NET 核心创建一个，如下所示。</span><span class="sxs-lookup"><span data-stu-id="33ee5-317">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![为 .NET 配置缺少的生成任务](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="33ee5-319">Choose **Create tasks.json from template.**</span><span class="sxs-lookup"><span data-stu-id="33ee5-319">Choose **Create tasks.json from template**.</span></span>

      ![根据 DKE 的tasks.js创建对文件进行创建](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="33ee5-321">从模板类型列表中，选择 **.NET Core。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-321">From the list of template types, select **.NET Core**.</span></span>

      ![为 DKE 选择正确的模板](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="33ee5-323">在生成部分中，找到 **customerkeystore.csproj 文件** 的路径。</span><span class="sxs-lookup"><span data-stu-id="33ee5-323">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="33ee5-324">如果不存在，请添加以下行：</span><span class="sxs-lookup"><span data-stu-id="33ee5-324">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="33ee5-325">再次运行生成。</span><span class="sxs-lookup"><span data-stu-id="33ee5-325">Run the build again.</span></span>

3. <span data-ttu-id="33ee5-326">确认输出窗口中没有红色错误。</span><span class="sxs-lookup"><span data-stu-id="33ee5-326">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="33ee5-327">如果存在红色错误，请检查控制台输出。</span><span class="sxs-lookup"><span data-stu-id="33ee5-327">If there are red errors, check the console output.</span></span> <span data-ttu-id="33ee5-328">确保您正确完成了上述所有步骤，并且存在正确的内部版本。</span><span class="sxs-lookup"><span data-stu-id="33ee5-328">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="33ee5-329">选择 \> **"运行开始调试**"以调试过程。</span><span class="sxs-lookup"><span data-stu-id="33ee5-329">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="33ee5-330">如果系统提示你选择环境，请选择 **.NET core。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-330">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="33ee5-331">.NET 核心调试程序通常启动到 `https://localhost:5001` 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-331">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="33ee5-332">若要查看测试密钥，请转到 / (/) 和你的密钥的名称并追加 `https://localhost:5001` 一个正斜杠。</span><span class="sxs-lookup"><span data-stu-id="33ee5-332">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="33ee5-333">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-333">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="33ee5-334">该键应该以 JSON 格式显示。</span><span class="sxs-lookup"><span data-stu-id="33ee5-334">The key should display in JSON format.</span></span>

<span data-ttu-id="33ee5-335">现在，你的设置已完成。</span><span class="sxs-lookup"><span data-stu-id="33ee5-335">Your setup is now complete.</span></span> <span data-ttu-id="33ee5-336">在发布 JwtAudience 设置的密钥appsettings.js，请确保主机名的值与 App Service 主机名完全匹配。</span><span class="sxs-lookup"><span data-stu-id="33ee5-336">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="33ee5-337">您可能已更改为 localhost 以对生成进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="33ee5-337">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="33ee5-338">部署 DKE 服务并发布密钥存储</span><span class="sxs-lookup"><span data-stu-id="33ee5-338">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="33ee5-339">对于生产部署，请部署第三方云中的服务或 [发布到本地系统](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-339">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="33ee5-340">你可能需要其他方法来部署密钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-340">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="33ee5-341">选择最适合贵组织的方法。</span><span class="sxs-lookup"><span data-stu-id="33ee5-341">Select the method that works best for your organization.</span></span>

<span data-ttu-id="33ee5-342">对于试点部署，可以在 Azure 中部署并立即开始。</span><span class="sxs-lookup"><span data-stu-id="33ee5-342">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="33ee5-343">**创建 Azure Web App 实例以托管 DKE 部署**</span><span class="sxs-lookup"><span data-stu-id="33ee5-343">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="33ee5-344">若要发布密钥存储，需要创建 Azure 应用服务实例来托管 DKE 部署。</span><span class="sxs-lookup"><span data-stu-id="33ee5-344">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="33ee5-345">接下来，将生成的密钥发布到 Azure。</span><span class="sxs-lookup"><span data-stu-id="33ee5-345">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="33ee5-346">在浏览器中，登录到 [Microsoft Azure 门户](https://ms.portal.azure.com)，然后转到 **"应用服务**  >  **添加"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-346">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="33ee5-347">选择订阅和资源组并定义实例详细信息。</span><span class="sxs-lookup"><span data-stu-id="33ee5-347">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="33ee5-348">输入要安装 DKE 服务的计算机的主机名。</span><span class="sxs-lookup"><span data-stu-id="33ee5-348">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="33ee5-349">请确保其名称与在文件上设置 JwtAudience 设置appsettings.js [**同**](#tenant-and-key-settings) 名。</span><span class="sxs-lookup"><span data-stu-id="33ee5-349">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="33ee5-350">您为名称提供的值也是 WebAppInstanceName。</span><span class="sxs-lookup"><span data-stu-id="33ee5-350">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="33ee5-351">对于 **"发布\*\*\*\*"、选择代码** 和运行时 **堆栈**，选择 **.NET Core 3.1。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-351">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="33ee5-352">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-352">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33ee5-353">![添加应用服务](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="33ee5-353">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="33ee5-354">在页面底部，选择"审阅 **+ 创建**"，然后选择"**添加"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-354">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="33ee5-355">执行以下操作之一以发布生成的密钥：</span><span class="sxs-lookup"><span data-stu-id="33ee5-355">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="33ee5-356">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="33ee5-356">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="33ee5-357">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="33ee5-357">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="33ee5-358">通过 Visual Studio 2019 或更高版本发布</span><span class="sxs-lookup"><span data-stu-id="33ee5-358">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="33ee5-359">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="33ee5-359">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="33ee5-360">转到 `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`。</span><span class="sxs-lookup"><span data-stu-id="33ee5-360">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="33ee5-361">例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="33ee5-361">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="33ee5-362">在密钥存储的代码库中，转到 **customer-key-store\src\customer-key-store** 文件夹，并验证此文件夹是否包含 **customerkeystore.csproj** 文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-362">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="33ee5-363">运行 **：dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="33ee5-363">Run: **dotnet publish**</span></span>

   <span data-ttu-id="33ee5-364">输出窗口显示部署发布的目录。</span><span class="sxs-lookup"><span data-stu-id="33ee5-364">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="33ee5-365">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="33ee5-365">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="33ee5-366">将发布目录中的所有文件发送到 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-366">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="33ee5-367">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="33ee5-367">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="33ee5-368">将创建的 .zip 文件拖放到上面打开的 ZipDeployUI 网站。</span><span class="sxs-lookup"><span data-stu-id="33ee5-368">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="33ee5-369">例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="33ee5-369">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="33ee5-370">DKE 已部署，你可以浏览到已创建的测试密钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-370">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="33ee5-371">继续 [验证以下部署](#validate-your-deployment) 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-371">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="33ee5-372">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="33ee5-372">Publish via FTP</span></span>

1. <span data-ttu-id="33ee5-373">连接到上面创建的应用 [服务](#deploy-the-dke-service-and-publish-the-key-store)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-373">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="33ee5-374">在浏览器中，转到 **：Azure 门户**  >  **应用服务**  >  **部署中心**  >  **手动部署**  >  **FTP**  >  **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-374">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="33ee5-375">将显示的连接字符串复制到本地文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-375">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="33ee5-376">你将使用这些字符串连接到 Web 应用服务，然后通过 FTP 上载文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-376">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="33ee5-377">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-377">For example:</span></span>

   ![从 FTP 仪表板复制连接字符串](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="33ee5-379">在密钥存储的代码库中，转到 **customer-key-store\src\customer-key-store 目录**。</span><span class="sxs-lookup"><span data-stu-id="33ee5-379">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="33ee5-380">验证此目录是否包含 **customerkeystore.csproj** 文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-380">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="33ee5-381">运行 **：dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="33ee5-381">Run: **dotnet publish**</span></span>

   <span data-ttu-id="33ee5-382">输出包含部署发布的目录。</span><span class="sxs-lookup"><span data-stu-id="33ee5-382">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="33ee5-383">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="33ee5-383">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="33ee5-384">将发布目录中的所有文件发送到 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="33ee5-384">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="33ee5-385">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="33ee5-385">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="33ee5-386">从 FTP 客户端，使用复制的连接信息连接到应用服务。</span><span class="sxs-lookup"><span data-stu-id="33ee5-386">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="33ee5-387">将上一步中创建的 .zip 文件上载到 Web 应用的根目录。</span><span class="sxs-lookup"><span data-stu-id="33ee5-387">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="33ee5-388">DKE 已部署，你可以浏览到已创建的测试密钥。</span><span class="sxs-lookup"><span data-stu-id="33ee5-388">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="33ee5-389">接下来， [验证部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-389">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="33ee5-390">验证部署</span><span class="sxs-lookup"><span data-stu-id="33ee5-390">Validate your deployment</span></span>

<span data-ttu-id="33ee5-391">使用上述方法之一部署 DKE 后，验证部署和密钥存储设置。</span><span class="sxs-lookup"><span data-stu-id="33ee5-391">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="33ee5-392">运行：</span><span class="sxs-lookup"><span data-stu-id="33ee5-392">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="33ee5-393">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-393">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="33ee5-394">确保输出中未出现任何错误。</span><span class="sxs-lookup"><span data-stu-id="33ee5-394">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="33ee5-395">准备就绪后，注册 [密钥存储](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-395">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="33ee5-396">键名称区分大小写。</span><span class="sxs-lookup"><span data-stu-id="33ee5-396">The key name is case sensitive.</span></span> <span data-ttu-id="33ee5-397">输入显示在文件上的appsettings.js名称。</span><span class="sxs-lookup"><span data-stu-id="33ee5-397">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="33ee5-398">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="33ee5-398">Register your key store</span></span>

<span data-ttu-id="33ee5-399">通过以下步骤注册 DKE 服务。</span><span class="sxs-lookup"><span data-stu-id="33ee5-399">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="33ee5-400">注册 DKE 服务是在开始创建标签之前部署 DKE 的最后一步。</span><span class="sxs-lookup"><span data-stu-id="33ee5-400">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="33ee5-401">注册 DKE 服务：</span><span class="sxs-lookup"><span data-stu-id="33ee5-401">To register the DKE service:</span></span>

1. <span data-ttu-id="33ee5-402">在浏览器中，打开 [Microsoft Azure 门户](https://ms.portal.azure.com/)，然后转到"**所有服务** \> **标识** \> **应用注册"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-402">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="33ee5-403">选择 **"新建注册**"，然后输入有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="33ee5-403">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="33ee5-404">从显示的选项中选择帐户类型。</span><span class="sxs-lookup"><span data-stu-id="33ee5-404">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="33ee5-405">如果你将 Microsoft Azure 与非自定义域（如 **onmicrosoft.com）** 一同使用，请选择仅 (Microsoft - 单个租户 **) 。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-405">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="33ee5-406">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-406">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="33ee5-407">![新应用注册](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="33ee5-407">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="33ee5-408">在页面底部，选择" **注册** "以创建新的应用注册。</span><span class="sxs-lookup"><span data-stu-id="33ee5-408">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="33ee5-409">在新的应用注册中，在左窗格中的"管理"**下，** 选择 **"身份验证"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-409">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="33ee5-410">选择 **"添加平台"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-410">Select **Add a platform**.</span></span>

7. <span data-ttu-id="33ee5-411">在"**配置平台"** 弹出窗口中，选择 **"Web"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-411">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="33ee5-412">在 **重定向 URI 下**，输入双密钥加密服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="33ee5-412">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="33ee5-413">输入应用服务 URL，包括主机名和域。</span><span class="sxs-lookup"><span data-stu-id="33ee5-413">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="33ee5-414">例如：https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="33ee5-414">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="33ee5-415">输入的 URL 必须与部署 DKE 服务的主机名匹配。</span><span class="sxs-lookup"><span data-stu-id="33ee5-415">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="33ee5-416">如果要在本地使用 Visual Studio 测试，请使用 **https://localhost:5001** 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-416">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="33ee5-417">在所有情况下，方案必须为 **https。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-417">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="33ee5-418">确保主机名与应用服务主机名完全匹配。</span><span class="sxs-lookup"><span data-stu-id="33ee5-418">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="33ee5-419">您可能已更改它以 `localhost` 对生成进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="33ee5-419">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="33ee5-420">在 **appsettings.js中**，此值是设置为的主机名 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="33ee5-420">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="33ee5-421">在 **"隐式授予**"下 **，选中"ID 令牌"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="33ee5-421">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="33ee5-422">选择“**保存**”以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="33ee5-422">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="33ee5-423">在左窗格中，**选择"公开 API"，** 然后在"应用程序 ID URI"旁边，选择"**设置"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-423">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="33ee5-424">仍在"**公开 API"页上**，在此 **API** 区域定义的"范围"中，选择 **"添加范围"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-424">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="33ee5-425">在新作用域中：</span><span class="sxs-lookup"><span data-stu-id="33ee5-425">In the new scope:</span></span>

    1. <span data-ttu-id="33ee5-426">将范围名称定义为 **user_impersonation。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-426">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="33ee5-427">选择可同意的管理员和用户。</span><span class="sxs-lookup"><span data-stu-id="33ee5-427">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="33ee5-428">定义所需的任何剩余值。</span><span class="sxs-lookup"><span data-stu-id="33ee5-428">Define any remaining values required.</span></span>

    4. <span data-ttu-id="33ee5-429">选择“添加作用域”。</span><span class="sxs-lookup"><span data-stu-id="33ee5-429">Select **Add scope**.</span></span>

    5. <span data-ttu-id="33ee5-430">选择 **顶部的** "保存"保存更改。</span><span class="sxs-lookup"><span data-stu-id="33ee5-430">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="33ee5-431">仍在"**公开 API"页上** 的"授权客户端 **应用程序**"区域中，选择"**添加客户端应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-431">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="33ee5-432">在新的客户端应用程序中：</span><span class="sxs-lookup"><span data-stu-id="33ee5-432">In the new client application:</span></span>

    1. <span data-ttu-id="33ee5-433">将客户端 ID 定义为 **d3590ed6-52b3-4102-aeff-aad2292ab01c。**</span><span class="sxs-lookup"><span data-stu-id="33ee5-433">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="33ee5-434">此值是Microsoft Office ID，使 Office 能够获取密钥存储的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="33ee5-434">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="33ee5-435">在 **"授权范围"** 下， **选择user_impersonation** 范围。</span><span class="sxs-lookup"><span data-stu-id="33ee5-435">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="33ee5-436">选择“添加应用程序”。</span><span class="sxs-lookup"><span data-stu-id="33ee5-436">Select **Add application**.</span></span>

    4. <span data-ttu-id="33ee5-437">选择 **顶部的** "保存"保存更改。</span><span class="sxs-lookup"><span data-stu-id="33ee5-437">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="33ee5-438">现在，已注册 DKE 服务。</span><span class="sxs-lookup"><span data-stu-id="33ee5-438">Your DKE service is now registered.</span></span> <span data-ttu-id="33ee5-439">继续使用 [DKE 创建标签](#create-sensitivity-labels-using-dke)。</span><span class="sxs-lookup"><span data-stu-id="33ee5-439">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="33ee5-440">使用 DKE 创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="33ee5-440">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="33ee5-441">在 Microsoft 365 合规中心中，创建新的敏感度标签并应用加密，就像否则一样。</span><span class="sxs-lookup"><span data-stu-id="33ee5-441">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="33ee5-442">选择 **"使用双密钥加密** "，然后输入密钥的终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="33ee5-442">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="33ee5-443">例如：</span><span class="sxs-lookup"><span data-stu-id="33ee5-443">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="33ee5-444">![选择 Microsoft 365 合规中心中的"使用双密钥加密"](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="33ee5-444">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="33ee5-445">你添加的任何 DKE 标签都将开始向最新版本的 Microsoft 365 企业应用版中的用户显示。</span><span class="sxs-lookup"><span data-stu-id="33ee5-445">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="33ee5-446">客户端可能需要 24 小时才能刷新新标签。</span><span class="sxs-lookup"><span data-stu-id="33ee5-446">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="33ee5-447">在客户端中启用 DKE</span><span class="sxs-lookup"><span data-stu-id="33ee5-447">Enable DKE in your client</span></span>

<span data-ttu-id="33ee5-448">如果你是 Office 预览体验成员，则启用 DKE。</span><span class="sxs-lookup"><span data-stu-id="33ee5-448">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="33ee5-449">否则，请通过添加以下注册表项来为客户端启用 DKE：</span><span class="sxs-lookup"><span data-stu-id="33ee5-449">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="33ee5-450">将受保护的文件从 HYOK 标签迁移到 DKE 标签</span><span class="sxs-lookup"><span data-stu-id="33ee5-450">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="33ee5-451">如果需要，完成 DKE 设置后，可以将使用 HYOK 标签保护的内容迁移到 DKE 标签。</span><span class="sxs-lookup"><span data-stu-id="33ee5-451">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="33ee5-452">若要迁移，请使用 AIP 扫描程序。</span><span class="sxs-lookup"><span data-stu-id="33ee5-452">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="33ee5-453">若要开始使用扫描程序，请参阅什么是[Azure 信息保护统一标签扫描程序？。](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)</span><span class="sxs-lookup"><span data-stu-id="33ee5-453">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="33ee5-454">如果不迁移内容，则 HYOK 保护的内容将不受影响。</span><span class="sxs-lookup"><span data-stu-id="33ee5-454">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
