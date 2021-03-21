---
title: 双密钥加密(DKE)
description: 通过 DKE，你可以保护高度敏感的数据，同时保持对密钥的完全控制。
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
ms.openlocfilehash: 10b29220e49dcb5fda8b1f7d18e52e10513fc599
ms.sourcegitcommit: 30c3054004ddc9d6059c11d55577552aa2464810
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2021
ms.locfileid: "50939653"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="050f2-103">Microsoft 365 的双密钥加密</span><span class="sxs-lookup"><span data-stu-id="050f2-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="050f2-104">*适用于：Microsoft 365 的双密钥加密 [、Microsoft 365 合规性](https://www.microsoft.com/microsoft-365/business/compliance-management) [、Azure 信息保护](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="050f2-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="050f2-105">*说明： [适用于 Windows 的 Azure 信息保护统一标记客户端](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="050f2-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="050f2-106">*服务说明 [：Microsoft 365 合规性](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="050f2-106">*Service description for: [Microsoft 365 Compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="050f2-107">双密钥加密 (DKE) 使用两个密钥来访问受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="050f2-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="050f2-108">Microsoft 在 Microsoft Azure 中存储一个密钥，你持有另一个密钥。</span><span class="sxs-lookup"><span data-stu-id="050f2-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="050f2-109">使用双密钥加密服务维护对其中一个密钥的完全控制。</span><span class="sxs-lookup"><span data-stu-id="050f2-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="050f2-110">使用 Azure 信息保护统一标记客户端对高度敏感的内容应用保护。</span><span class="sxs-lookup"><span data-stu-id="050f2-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="050f2-111">双密钥加密支持云和本地部署。</span><span class="sxs-lookup"><span data-stu-id="050f2-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="050f2-112">这些部署有助于确保加密数据在存储受保护数据的位置都保持不透明。</span><span class="sxs-lookup"><span data-stu-id="050f2-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="050f2-113">有关默认的基于云的租户根密钥详细信息，请参阅规划和 [实现 Azure 信息保护租户密钥](/azure/information-protection/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="050f2-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="050f2-114">组织何时应采用 DKE</span><span class="sxs-lookup"><span data-stu-id="050f2-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="050f2-115">双密钥加密适用于符合最严格的保护要求的最敏感数据。</span><span class="sxs-lookup"><span data-stu-id="050f2-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="050f2-116">DKE 并非适用于所有数据。</span><span class="sxs-lookup"><span data-stu-id="050f2-116">DKE is not intended for all data.</span></span> <span data-ttu-id="050f2-117">通常，你将使用双密钥加密来保护整个数据的一小部分。</span><span class="sxs-lookup"><span data-stu-id="050f2-117">In general, you'll be using Double Key Encryption to protect only a small part of your overall data.</span></span> <span data-ttu-id="050f2-118">在部署之前，应谨慎确定要在此解决方案中涵盖的合适数据。</span><span class="sxs-lookup"><span data-stu-id="050f2-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="050f2-119">在某些情况下，你可能需要缩小范围，并针对你的大多数数据使用其他解决方案，例如 Microsoft 信息保护（包含 Microsoft 托管的密钥）或 BYOK。</span><span class="sxs-lookup"><span data-stu-id="050f2-119">In some cases, you might need to narrow your scope and make use of other solutions for most your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="050f2-120">这些解决方案足以用于不受增强的保护和法规要求的文档。</span><span class="sxs-lookup"><span data-stu-id="050f2-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="050f2-121">此外，这些解决方案还使您能够使用最强大的 Office 365 服务;不能与 DKE 加密内容一同使用的服务。</span><span class="sxs-lookup"><span data-stu-id="050f2-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="050f2-122">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-122">For example:</span></span>

- <span data-ttu-id="050f2-123">需要查看附件的传输规则，包括反恶意软件和垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="050f2-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="050f2-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="050f2-124">Microsoft Delve</span></span>
- <span data-ttu-id="050f2-125">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="050f2-125">eDiscovery</span></span>
- <span data-ttu-id="050f2-126">内容搜索和索引</span><span class="sxs-lookup"><span data-stu-id="050f2-126">Content search and indexing</span></span>
- <span data-ttu-id="050f2-127">包括共同授权功能的 Office Web Apps</span><span class="sxs-lookup"><span data-stu-id="050f2-127">Office Web Apps including coauthoring functionality</span></span>

<span data-ttu-id="050f2-128">任何未通过 MIP SDK 与 DKE 集成的外部应用程序或服务将无法对加密数据执行操作。</span><span class="sxs-lookup"><span data-stu-id="050f2-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="050f2-129">Microsoft 信息保护 SDK 1.7+ 支持双密钥加密;与 SDK 集成的应用程序将能够通过足够的权限和集成来了解此数据。</span><span class="sxs-lookup"><span data-stu-id="050f2-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="050f2-130">我们建议组织使用 Microsoft 信息保护功能 (分类和标记) 保护大部分敏感数据，并仅将 DKE 用于任务关键型数据。</span><span class="sxs-lookup"><span data-stu-id="050f2-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="050f2-131">双密钥加密与高度管控行业（如金融服务和医疗保健）中的敏感数据相关。</span><span class="sxs-lookup"><span data-stu-id="050f2-131">Double Key Encryption is relevant for sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="050f2-132">如果你的组织有以下任一要求，可以使用 DKE 来帮助保护内容的安全：</span><span class="sxs-lookup"><span data-stu-id="050f2-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="050f2-133">您希望确保在任何情况下 *仅可以* 解密受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="050f2-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="050f2-134">你不希望 Microsoft 自行访问受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="050f2-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="050f2-135">您具有在地理边界内保留密钥的法规要求。</span><span class="sxs-lookup"><span data-stu-id="050f2-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="050f2-136">您保留用于数据加密和解密的所有密钥都在你的数据中心进行维护。</span><span class="sxs-lookup"><span data-stu-id="050f2-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="050f2-137">DKE 的系统和许可要求</span><span class="sxs-lookup"><span data-stu-id="050f2-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="050f2-138">**Microsoft 365 的** 双密钥加密随 Microsoft 365 E5 一起提供。</span><span class="sxs-lookup"><span data-stu-id="050f2-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5.</span></span> <span data-ttu-id="050f2-139">如果你没有 Microsoft 365 E5 许可证，可以[注册试用版。](https://aka.ms/M365E5ComplianceTrial)</span><span class="sxs-lookup"><span data-stu-id="050f2-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="050f2-140">有关这些许可证详细信息，请参阅 [Microsoft 365](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)安全与合规&指南。</span><span class="sxs-lookup"><span data-stu-id="050f2-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="050f2-141">**Azure 信息保护**。</span><span class="sxs-lookup"><span data-stu-id="050f2-141">**Azure Information Protection**.</span></span> <span data-ttu-id="050f2-142">DKE 使用敏感度标签，并且需要 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="050f2-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="050f2-143">DKE 敏感度标签通过 Office 桌面应用程序中的敏感度功能区提供给最终用户。</span><span class="sxs-lookup"><span data-stu-id="050f2-143">DKE sensitivity labels are made available to end users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="050f2-144">在要保护和使用受保护文档的每台客户端计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="050f2-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="050f2-145">**Microsoft Office Windows 上的** 桌面版 Word、PowerPoint 和 Excel (2009 企业应用版) 更高版本。</span><span class="sxs-lookup"><span data-stu-id="050f2-145">**Microsoft Office Apps for enterprise** version 2009 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="050f2-146">**Azure 信息保护统一标签客户端** 版本 2.7.93.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="050f2-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="050f2-147">从 Microsoft 下载中心下载并安装统 [一标签客户端](https://www.microsoft.com/download/details.aspx?id=53018)。</span><span class="sxs-lookup"><span data-stu-id="050f2-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="050f2-148">用于存储和查看受 DKE 保护的内容的支持的环境</span><span class="sxs-lookup"><span data-stu-id="050f2-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="050f2-149">**支持的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="050f2-149">**Supported applications**.</span></span> <span data-ttu-id="050f2-150">[Windows 上的 Microsoft 365](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) 企业应用版客户端，包括 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="050f2-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="050f2-151">**联机内容支持**。</span><span class="sxs-lookup"><span data-stu-id="050f2-151">**Online content support**.</span></span> <span data-ttu-id="050f2-152">可以在 Microsoft SharePoint 和 OneDrive for Business 中联机存储受双密钥加密保护的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-152">You can store documents and files protected with Double Key Encryption online in both Microsoft SharePoint and OneDrive for Business.</span></span> <span data-ttu-id="050f2-153">在上载到这些位置之前，必须通过受支持的应用程序使用 DKE 标记和保护文档和文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-153">You must label and protect documents and files with DKE by supported applications before you upload to these locations.</span></span> <span data-ttu-id="050f2-154">可以通过电子邮件共享加密内容，但无法联机查看加密文档和文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-154">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="050f2-155">相反，必须使用本地计算机上受支持的桌面应用程序和客户端查看受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="050f2-155">Instead, you must view protected content using the supported desktop applications and clients on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="050f2-156">部署 DKE 的概述</span><span class="sxs-lookup"><span data-stu-id="050f2-156">Overview of deploying DKE</span></span>

<span data-ttu-id="050f2-157">你将按照这些常规步骤设置 DKE。</span><span class="sxs-lookup"><span data-stu-id="050f2-157">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="050f2-158">完成这些步骤后，最终用户可以使用双密钥加密来保护高度敏感的数据。</span><span class="sxs-lookup"><span data-stu-id="050f2-158">Once you've completed these steps, your end users will can protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="050f2-159">部署 DKE 服务，如本文所述。</span><span class="sxs-lookup"><span data-stu-id="050f2-159">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="050f2-160">使用双密钥加密创建标签。</span><span class="sxs-lookup"><span data-stu-id="050f2-160">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="050f2-161">导航到 [Microsoft 365](https://compliance.microsoft.com) 合规中心下的信息保护，然后使用双密钥加密创建新标签。</span><span class="sxs-lookup"><span data-stu-id="050f2-161">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="050f2-162">请参阅 [使用敏感度标签应用加密来限制对内容的访问](./encryption-sensitivity-labels.md)。</span><span class="sxs-lookup"><span data-stu-id="050f2-162">See [Restrict access to content by using sensitivity labels to apply encryption](./encryption-sensitivity-labels.md).</span></span>

3. <span data-ttu-id="050f2-163">使用双密钥加密标签。</span><span class="sxs-lookup"><span data-stu-id="050f2-163">Use Double Key Encryption labels.</span></span> <span data-ttu-id="050f2-164">通过从"敏感度"功能区中选择"双密钥加密"标签来保护Microsoft Office。</span><span class="sxs-lookup"><span data-stu-id="050f2-164">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="050f2-165">有几种方法可以完成部署双密钥加密的一些步骤。</span><span class="sxs-lookup"><span data-stu-id="050f2-165">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="050f2-166">本文提供了详细说明，以便经验不足的管理员能够成功部署服务。</span><span class="sxs-lookup"><span data-stu-id="050f2-166">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="050f2-167">如果习惯这样做，可以选择使用自己的方法。</span><span class="sxs-lookup"><span data-stu-id="050f2-167">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="050f2-168">部署 DKE</span><span class="sxs-lookup"><span data-stu-id="050f2-168">Deploy DKE</span></span>

<span data-ttu-id="050f2-169">本文和部署视频使用 Azure 作为 DKE 服务的部署目标。</span><span class="sxs-lookup"><span data-stu-id="050f2-169">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="050f2-170">如果要部署到其他位置，则需要提供自己的值。</span><span class="sxs-lookup"><span data-stu-id="050f2-170">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="050f2-171">观看 [双密钥加密部署](https://youtu.be/vDWfHN_kygg) 视频，查看本文中概念的分步概述。</span><span class="sxs-lookup"><span data-stu-id="050f2-171">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="050f2-172">视频需要大约 18 分钟才能完成。</span><span class="sxs-lookup"><span data-stu-id="050f2-172">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="050f2-173">你将按照这些常规步骤为组织设置双密钥加密。</span><span class="sxs-lookup"><span data-stu-id="050f2-173">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="050f2-174">安装 DKE 服务的必备软件</span><span class="sxs-lookup"><span data-stu-id="050f2-174">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="050f2-175">克隆双密钥加密 GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="050f2-175">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="050f2-176">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="050f2-176">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="050f2-177">生成测试密钥</span><span class="sxs-lookup"><span data-stu-id="050f2-177">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="050f2-178">生成项目</span><span class="sxs-lookup"><span data-stu-id="050f2-178">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="050f2-179">部署 DKE 服务并发布密钥存储</span><span class="sxs-lookup"><span data-stu-id="050f2-179">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="050f2-180">验证部署</span><span class="sxs-lookup"><span data-stu-id="050f2-180">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="050f2-181">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="050f2-181">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="050f2-182">使用 DKE 创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="050f2-182">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="050f2-183">在客户端中启用 DKE</span><span class="sxs-lookup"><span data-stu-id="050f2-183">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="050f2-184">将受保护的文件从 HYOK 标签迁移到 DKE 标签</span><span class="sxs-lookup"><span data-stu-id="050f2-184">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="050f2-185">完成后，可以使用 DKE 加密文档和文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-185">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="050f2-186">有关信息，请参阅 [向 Office 中的文件和电子邮件应用敏感度标签](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。</span><span class="sxs-lookup"><span data-stu-id="050f2-186">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="050f2-187">安装 DKE 服务的必备软件</span><span class="sxs-lookup"><span data-stu-id="050f2-187">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="050f2-188">在要安装 DKE 服务的计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="050f2-188">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="050f2-189">**.NET Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="050f2-189">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="050f2-190">从下载 [.NET Core 3.1 下载并安装](https://dotnet.microsoft.com/download/dotnet-core/3.1)SDK。</span><span class="sxs-lookup"><span data-stu-id="050f2-190">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="050f2-191">**Visual Studio代码**。</span><span class="sxs-lookup"><span data-stu-id="050f2-191">**Visual Studio Code**.</span></span> <span data-ttu-id="050f2-192">从 Visual Studio代码 [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="050f2-192">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="050f2-193">安装完成后，运行Visual Studio代码并选择 **查看** \> **扩展**。</span><span class="sxs-lookup"><span data-stu-id="050f2-193">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="050f2-194">安装这些扩展。</span><span class="sxs-lookup"><span data-stu-id="050f2-194">Install these extensions.</span></span>

- <span data-ttu-id="050f2-195">C#代码Visual Studio代码</span><span class="sxs-lookup"><span data-stu-id="050f2-195">C# for Visual Studio Code</span></span>

- <span data-ttu-id="050f2-196">NuGet 程序包管理器</span><span class="sxs-lookup"><span data-stu-id="050f2-196">NuGet Package Manager</span></span>

<span data-ttu-id="050f2-197">**Git 资源**。</span><span class="sxs-lookup"><span data-stu-id="050f2-197">**Git resources**.</span></span> <span data-ttu-id="050f2-198">下载并安装以下项之一。</span><span class="sxs-lookup"><span data-stu-id="050f2-198">Download and install one of the following.</span></span>

- [<span data-ttu-id="050f2-199">Git</span><span class="sxs-lookup"><span data-stu-id="050f2-199">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="050f2-200">GitHub 桌面</span><span class="sxs-lookup"><span data-stu-id="050f2-200">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="050f2-201">GitHub 企业版</span><span class="sxs-lookup"><span data-stu-id="050f2-201">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="050f2-202">**OpenSSL** 部署 DKE [后，必须安装 OpenSSL](https://slproweb.com/products/Win32OpenSSL.html)以生成测试密钥。 [](#generate-test-keys)</span><span class="sxs-lookup"><span data-stu-id="050f2-202">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="050f2-203">请确保从环境变量路径正确调用它。</span><span class="sxs-lookup"><span data-stu-id="050f2-203">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="050f2-204">例如，有关详细信息，请参阅 中的"将安装目录添加到 [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) PATH"。</span><span class="sxs-lookup"><span data-stu-id="050f2-204">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="050f2-205">克隆 DKE GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="050f2-205">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="050f2-206">Microsoft 在 GitHub 存储库中提供 DKE 源文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-206">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="050f2-207">克隆存储库以在本地生成项目供组织使用。</span><span class="sxs-lookup"><span data-stu-id="050f2-207">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="050f2-208">DKE GitHub 存储库位于 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="050f2-208">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="050f2-209">以下说明适用于没有经验的 git 或 Visual Studio Code 用户：</span><span class="sxs-lookup"><span data-stu-id="050f2-209">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="050f2-210">在浏览器中，转到 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) ：。</span><span class="sxs-lookup"><span data-stu-id="050f2-210">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="050f2-211">在屏幕右侧，选择"代码 **"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-211">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="050f2-212">你的 UI 版本可能会显示克隆 **或下载** 按钮。</span><span class="sxs-lookup"><span data-stu-id="050f2-212">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="050f2-213">然后，在出现的下拉列表中，选择复制图标以将 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="050f2-213">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="050f2-214">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-214">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="050f2-215">![从 GitHub 克隆双密钥加密服务存储库](../media/dke-clone.png)</span><span class="sxs-lookup"><span data-stu-id="050f2-215">![Clone the Double Key Encryption service repository from GitHub](../media/dke-clone.png)</span></span>

3. <span data-ttu-id="050f2-216">在Visual Studio代码"中，选择 **"查看** \> **命令调色板**"，然后选择 **"Git： 克隆"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-216">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="050f2-217">若要跳转到列表中的选项，请开始键入以筛选 `git: clone` 条目，然后从下拉列表中选择它。</span><span class="sxs-lookup"><span data-stu-id="050f2-217">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="050f2-218">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-218">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="050f2-219">![Visual Studio代码 GIT：Clone 选项](../media/dke-vscode-clone.png)</span><span class="sxs-lookup"><span data-stu-id="050f2-219">![Visual Studio Code GIT:Clone option](../media/dke-vscode-clone.png)</span></span>

4. <span data-ttu-id="050f2-220">在文本框中，粘贴从 Git 复制的 URL，然后选择"从 **GitHub 克隆"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-220">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="050f2-221">在出现的 **"选择** 文件夹"对话框中，浏览到存储库并选择存储位置。</span><span class="sxs-lookup"><span data-stu-id="050f2-221">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="050f2-222">在提示符下，选择"打开 **"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-222">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="050f2-223">存储库在代码Visual Studio打开，在左下角显示当前 Git 分支。</span><span class="sxs-lookup"><span data-stu-id="050f2-223">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="050f2-224">例如，分支应为 **主**。</span><span class="sxs-lookup"><span data-stu-id="050f2-224">For example,  The branch should be **main**.</span></span> <span data-ttu-id="050f2-225">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-225">For example:</span></span>

   ![显示主分支Visual Studio代码中的 DKE 存储库的屏幕截图](../media/dke-vscode-main-branch.jpg)

6. <span data-ttu-id="050f2-227">如果你不在主分支上，则需要选择它。</span><span class="sxs-lookup"><span data-stu-id="050f2-227">If you're not on the main branch, you'll need to select it.</span></span> <span data-ttu-id="050f2-228">在Visual Studio代码"中，选择 **分支，然后** 从显示的分支列表中选择"主"。</span><span class="sxs-lookup"><span data-stu-id="050f2-228">In Visual Studio Code, select the branch and choose **main** from the list of branches that displays.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="050f2-229">选择主分支可确保你拥有用于生成项目的正确文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-229">Selecting the main branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="050f2-230">如果不选择正确的分支，部署将失败。</span><span class="sxs-lookup"><span data-stu-id="050f2-230">If you don't choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="050f2-231">现在，你已在本地设置 DKE 源存储库。</span><span class="sxs-lookup"><span data-stu-id="050f2-231">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="050f2-232">接下来 [，修改组织](#modify-application-settings) 的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="050f2-232">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="050f2-233">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="050f2-233">Modify application settings</span></span>

<span data-ttu-id="050f2-234">若要部署 DKE 服务，必须修改以下类型的应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="050f2-234">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="050f2-235">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="050f2-235">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="050f2-236">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="050f2-236">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="050f2-237">修改"打开"appsettings.js中的应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="050f2-237">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="050f2-238">此文件位于在 DoubleKeyEncryptionService\src\customer-key-store 下本地克隆的 DoubleKeyEncryptionService 存储库。</span><span class="sxs-lookup"><span data-stu-id="050f2-238">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="050f2-239">例如，在Visual Studio代码中，您可以浏览到文件，如下图所示。</span><span class="sxs-lookup"><span data-stu-id="050f2-239">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![在文件上appsettings.jsDKE 的配置文件。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="050f2-241">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="050f2-241">Key access settings</span></span>

<span data-ttu-id="050f2-242">选择是使用电子邮件还是角色授权。</span><span class="sxs-lookup"><span data-stu-id="050f2-242">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="050f2-243">DKE 一次仅支持其中一种身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="050f2-243">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="050f2-244">**电子邮件授权**。</span><span class="sxs-lookup"><span data-stu-id="050f2-244">**Email authorization**.</span></span> <span data-ttu-id="050f2-245">允许组织仅根据电子邮件地址授予对密钥的访问权限。</span><span class="sxs-lookup"><span data-stu-id="050f2-245">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="050f2-246">**角色授权**。</span><span class="sxs-lookup"><span data-stu-id="050f2-246">**Role authorization**.</span></span> <span data-ttu-id="050f2-247">允许组织根据 Active Directory 组授予对密钥的访问权限，并需要 Web 服务可以查询 LDAP。</span><span class="sxs-lookup"><span data-stu-id="050f2-247">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="050f2-248">**使用电子邮件授权设置 DKE 的关键访问设置**</span><span class="sxs-lookup"><span data-stu-id="050f2-248">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="050f2-249">打开 **"appsettings.js"** 文件并找到 `AuthorizedEmailAddress` 设置。</span><span class="sxs-lookup"><span data-stu-id="050f2-249">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="050f2-250">添加要授权的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="050f2-250">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="050f2-251">使用双引号和逗号分隔多个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="050f2-251">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="050f2-252">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-252">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="050f2-253">找到 `LDAPPath` 设置并删除双 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 引号之间的文本。</span><span class="sxs-lookup"><span data-stu-id="050f2-253">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="050f2-254">将双引号留在位。</span><span class="sxs-lookup"><span data-stu-id="050f2-254">Leave the double quotes in place.</span></span> <span data-ttu-id="050f2-255">完成后，设置应如下所示。</span><span class="sxs-lookup"><span data-stu-id="050f2-255">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="050f2-256">找到 `AuthorizedRoles` 设置并删除整行。</span><span class="sxs-lookup"><span data-stu-id="050f2-256">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="050f2-257">此 **图像显示appsettings.js** 格式正确的文件格式的电子邮件授权。</span><span class="sxs-lookup"><span data-stu-id="050f2-257">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![显示appsettings.js方法的 on 文件](../media/dke-email-accesssetting.png)

<span data-ttu-id="050f2-259">**使用角色授权设置 DKE 的关键访问设置**</span><span class="sxs-lookup"><span data-stu-id="050f2-259">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="050f2-260">打开 **"appsettings.js"** 文件并找到 `AuthorizedRoles` 设置。</span><span class="sxs-lookup"><span data-stu-id="050f2-260">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="050f2-261">添加要授权 Active Directory 组的名称。</span><span class="sxs-lookup"><span data-stu-id="050f2-261">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="050f2-262">用双引号和逗号分隔多个组名称。</span><span class="sxs-lookup"><span data-stu-id="050f2-262">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="050f2-263">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-263">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="050f2-264">找到 `LDAPPath` 设置并添加 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="050f2-264">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="050f2-265">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-265">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="050f2-266">找到 `AuthorizedEmailAddress` 设置并删除整行。</span><span class="sxs-lookup"><span data-stu-id="050f2-266">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="050f2-267">此图显示了 **appsettings.js** 角色授权正确设置格式的文件上的名称。</span><span class="sxs-lookup"><span data-stu-id="050f2-267">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![appsettings.js显示角色授权方法的文件](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="050f2-269">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="050f2-269">Tenant and key settings</span></span>

<span data-ttu-id="050f2-270">DKE 租户和密钥设置位于appsettings.js **on** 文件中。</span><span class="sxs-lookup"><span data-stu-id="050f2-270">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="050f2-271">**为 DKE 配置租户和密钥设置**</span><span class="sxs-lookup"><span data-stu-id="050f2-271">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="050f2-272">打开 **appsettings.json** 文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-272">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="050f2-273">找到 `ValidIssuers` 设置，并 `<tenantid>` 替换为租户 ID。</span><span class="sxs-lookup"><span data-stu-id="050f2-273">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="050f2-274">可以通过访问 Azure 门户并查看租户属性 找到[租户 ID。](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)</span><span class="sxs-lookup"><span data-stu-id="050f2-274">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="050f2-275">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-275">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="050f2-276">找到 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="050f2-276">Locate the `JwtAudience`.</span></span> <span data-ttu-id="050f2-277">将 `<yourhostname>` 替换为将运行 DKE 服务的主机名。</span><span class="sxs-lookup"><span data-stu-id="050f2-277">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="050f2-278">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-278">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="050f2-279">的值 `JwtAudience` 必须与主机的名称 *完全匹配*。</span><span class="sxs-lookup"><span data-stu-id="050f2-279">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="050f2-280">调试时可以使用 **localhost：5001。**</span><span class="sxs-lookup"><span data-stu-id="050f2-280">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="050f2-281">但是，完成调试后，请确保将此值更新为服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="050f2-281">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="050f2-282">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="050f2-282">`TestKeys:Name`.</span></span> <span data-ttu-id="050f2-283">输入密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="050f2-283">Enter a name for your key.</span></span> <span data-ttu-id="050f2-284">例如：`TestKey1`</span><span class="sxs-lookup"><span data-stu-id="050f2-284">For example: `TestKey1`</span></span>
- <span data-ttu-id="050f2-285">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="050f2-285">`TestKeys:Id`.</span></span> <span data-ttu-id="050f2-286">创建一个 GUID，并输入它作为 `TestKeys:ID` 值。</span><span class="sxs-lookup"><span data-stu-id="050f2-286">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="050f2-287">例如，`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`。</span><span class="sxs-lookup"><span data-stu-id="050f2-287">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="050f2-288">可以使用联机 [GUID 生成器](https://guidgenerator.com/) 等站点随机生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="050f2-288">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="050f2-289">此图像在 上显示租户和密钥appsettings.js **格式**。</span><span class="sxs-lookup"><span data-stu-id="050f2-289">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="050f2-290">`LDAPPath` 配置为进行角色授权。</span><span class="sxs-lookup"><span data-stu-id="050f2-290">`LDAPPath` is configured for role authorization.</span></span>

![在"打开"文件中显示 DKE 的正确租户appsettings.js密钥设置。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="050f2-292">生成测试密钥</span><span class="sxs-lookup"><span data-stu-id="050f2-292">Generate test keys</span></span>

<span data-ttu-id="050f2-293">定义应用程序设置后，即可生成公钥和专用测试密钥。</span><span class="sxs-lookup"><span data-stu-id="050f2-293">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="050f2-294">生成密钥：</span><span class="sxs-lookup"><span data-stu-id="050f2-294">To generate keys:</span></span>

1. <span data-ttu-id="050f2-295">从 Windows"开始"菜单中，运行 OpenSSL 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="050f2-295">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="050f2-296">更改为要保存测试密钥的文件夹。</span><span class="sxs-lookup"><span data-stu-id="050f2-296">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="050f2-297">通过完成此任务中的步骤创建的文件存储在同一文件夹中。</span><span class="sxs-lookup"><span data-stu-id="050f2-297">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="050f2-298">生成新的测试密钥。</span><span class="sxs-lookup"><span data-stu-id="050f2-298">Generate the new test key.</span></span>

   ```console
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="050f2-299">生成私钥。</span><span class="sxs-lookup"><span data-stu-id="050f2-299">Generate the private key.</span></span>

   ```console
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="050f2-300">生成公钥。</span><span class="sxs-lookup"><span data-stu-id="050f2-300">Generate the public key.</span></span>

   ```console
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="050f2-301">在文本编辑器中，打开 **pubkeyonly.pem**。</span><span class="sxs-lookup"><span data-stu-id="050f2-301">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="050f2-302">将 **pubkeyonly.pem** 文件中除第一行和最后一行之外的所有内容复制到"on"appsettings.js`PublicPem` **部分中** 。</span><span class="sxs-lookup"><span data-stu-id="050f2-302">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="050f2-303">在文本编辑器中，打开 **"管理程序""nopass.pem"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-303">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="050f2-304">将 **管理密钥nopass.pem** 文件（第一行和最后一行除外）中的内容复制到"on"appsettings.js`PrivatePem` **部分中** 。</span><span class="sxs-lookup"><span data-stu-id="050f2-304">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="050f2-305">删除 和 部分的所有空格和 `PublicPem` `PrivatePem` 新行。</span><span class="sxs-lookup"><span data-stu-id="050f2-305">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="050f2-306">复制此内容时，请勿删除任何 PEM 数据。</span><span class="sxs-lookup"><span data-stu-id="050f2-306">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="050f2-307">在Visual Studio代码中，浏览到 **Startup.cs** 文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-307">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="050f2-308">此文件位于在 DoubleKeyEncryptionService\src\customer-key-store\ 下本地克隆的 DoubleKeyEncryptionService 存储库。</span><span class="sxs-lookup"><span data-stu-id="050f2-308">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="050f2-309">找到以下行：</span><span class="sxs-lookup"><span data-stu-id="050f2-309">Locate the following lines:</span></span>

    ```csharp
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
    ```

11. <span data-ttu-id="050f2-310">将以下行替换为以下文本：</span><span class="sxs-lookup"><span data-stu-id="050f2-310">Replace these lines with the following text:</span></span>

    ```csharp
    services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
    ```

    <span data-ttu-id="050f2-311">最终结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="050f2-311">The end results should look similar to the following.</span></span>

    ![用于公共预览的 startup.cs 文件](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="050f2-313">现在，你已准备好生成 [DKE 项目](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="050f2-313">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="050f2-314">生成项目</span><span class="sxs-lookup"><span data-stu-id="050f2-314">Build the project</span></span>

<span data-ttu-id="050f2-315">使用以下说明在本地生成 DKE 项目：</span><span class="sxs-lookup"><span data-stu-id="050f2-315">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="050f2-316">在Visual Studio代码的 DKE 服务存储库中，选择"查看命令调色板"，然后在提示符 \> 下键入 build。</span><span class="sxs-lookup"><span data-stu-id="050f2-316">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="050f2-317">From the list， choose **Tasks： Run build task**.</span><span class="sxs-lookup"><span data-stu-id="050f2-317">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="050f2-318">如果没有找到生成任务，请选择" **配置生成任务"，** 然后为 .NET core 创建一个，如下所示。</span><span class="sxs-lookup"><span data-stu-id="050f2-318">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![为 .NET 配置缺少的生成任务](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="050f2-320">选择 **"从tasks.js上创建模板"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-320">Choose **Create tasks.json from template**.</span></span>

      ![从tasks.jsDKE 的模板创建文件扩展名](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="050f2-322">从模板类型列表中，选择 **".NET Core"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-322">From the list of template types, select **.NET Core**.</span></span>

      ![为 DKE 选择正确的模板](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="050f2-324">在生成部分中，找到 **customerkeystore.csproj 文件** 的路径。</span><span class="sxs-lookup"><span data-stu-id="050f2-324">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="050f2-325">如果不存在，请添加以下行：</span><span class="sxs-lookup"><span data-stu-id="050f2-325">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="050f2-326">再次运行生成。</span><span class="sxs-lookup"><span data-stu-id="050f2-326">Run the build again.</span></span>

3. <span data-ttu-id="050f2-327">确认输出窗口中没有红色错误。</span><span class="sxs-lookup"><span data-stu-id="050f2-327">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="050f2-328">如果存在红色错误，请检查控制台输出。</span><span class="sxs-lookup"><span data-stu-id="050f2-328">If there are red errors, check the console output.</span></span> <span data-ttu-id="050f2-329">确保您正确完成了上述所有步骤，并且存在正确的内部版本。</span><span class="sxs-lookup"><span data-stu-id="050f2-329">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="050f2-330">选择 **"** \> **运行开始调试** "以调试过程。</span><span class="sxs-lookup"><span data-stu-id="050f2-330">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="050f2-331">如果系统提示你选择环境，请选择 **.NET core**。</span><span class="sxs-lookup"><span data-stu-id="050f2-331">If you're prompted to select an environment, select **.NET core**.</span></span>

   <span data-ttu-id="050f2-332">.NET 核心调试程序通常启动到 `https://localhost:5001` 。</span><span class="sxs-lookup"><span data-stu-id="050f2-332">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="050f2-333">若要查看测试密钥，请转到 并追加一个正斜杠 `https://localhost:5001` (/) 和密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="050f2-333">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="050f2-334">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-334">For example:</span></span>

   ```https
   https://localhost:5001/TestKey1
   ```

   <span data-ttu-id="050f2-335">密钥应以 JSON 格式显示。</span><span class="sxs-lookup"><span data-stu-id="050f2-335">The key should display in JSON format.</span></span>

<span data-ttu-id="050f2-336">您的设置现已完成。</span><span class="sxs-lookup"><span data-stu-id="050f2-336">Your setup is now complete.</span></span> <span data-ttu-id="050f2-337">在发布密钥存储之前，在 appsettings.json 中，对于 JwtAudience 设置，请确保 hostname 的值与 App Service 主机名完全匹配。</span><span class="sxs-lookup"><span data-stu-id="050f2-337">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="050f2-338">您可能已更改为 localhost，以对生成进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="050f2-338">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="050f2-339">部署 DKE 服务并发布密钥存储</span><span class="sxs-lookup"><span data-stu-id="050f2-339">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="050f2-340">对于生产部署，请部署第三方云中的服务或发布到 [本地系统](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1)。</span><span class="sxs-lookup"><span data-stu-id="050f2-340">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](/aspnet/core/tutorials/publish-to-iis?preserve-view=true&tabs=netcore-cli&view=aspnetcore-3.1).</span></span>

<span data-ttu-id="050f2-341">你可能需要其他方法来部署密钥。</span><span class="sxs-lookup"><span data-stu-id="050f2-341">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="050f2-342">选择最适合贵组织的方法。</span><span class="sxs-lookup"><span data-stu-id="050f2-342">Select the method that works best for your organization.</span></span>

<span data-ttu-id="050f2-343">对于试点部署，可以在 Azure 中部署并立即开始。</span><span class="sxs-lookup"><span data-stu-id="050f2-343">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="050f2-344">**创建 Azure Web App 实例以托管 DKE 部署**</span><span class="sxs-lookup"><span data-stu-id="050f2-344">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="050f2-345">若要发布密钥存储，需要创建 Azure 应用服务实例来托管 DKE 部署。</span><span class="sxs-lookup"><span data-stu-id="050f2-345">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="050f2-346">接下来，将生成的密钥发布到 Azure。</span><span class="sxs-lookup"><span data-stu-id="050f2-346">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="050f2-347">在浏览器中，登录到 [Microsoft Azure 门户](https://ms.portal.azure.com)，然后转到应用 **服务**  >  **添加**。</span><span class="sxs-lookup"><span data-stu-id="050f2-347">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="050f2-348">选择订阅和资源组并定义实例详细信息。</span><span class="sxs-lookup"><span data-stu-id="050f2-348">Select your subscription and resource group and define your instance details.</span></span>

   - <span data-ttu-id="050f2-349">输入要安装 DKE 服务的计算机的主机名。</span><span class="sxs-lookup"><span data-stu-id="050f2-349">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="050f2-350">请确保该名称与为 on 文件上的 JwtAudience 设置appsettings.js [**的名称**](#tenant-and-key-settings) 。</span><span class="sxs-lookup"><span data-stu-id="050f2-350">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="050f2-351">您为名称提供的值也是 WebAppInstanceName。</span><span class="sxs-lookup"><span data-stu-id="050f2-351">The value you provide for the name is also the WebAppInstanceName.</span></span>

   - <span data-ttu-id="050f2-352">对于 **"发布"，\*\*\*\*选择"代码**"，对于 **"运行时堆栈**"，选择 **".NET Core 3.1"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-352">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

   <span data-ttu-id="050f2-353">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-353">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="050f2-354">![添加应用服务](../media/dke-azure-add-app-service.png)</span><span class="sxs-lookup"><span data-stu-id="050f2-354">![Add your App Service](../media/dke-azure-add-app-service.png)</span></span>

3. <span data-ttu-id="050f2-355">在页面底部，选择"审阅 **+ 创建**"，然后选择"添加 **"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-355">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="050f2-356">执行下列操作之一以发布生成的密钥：</span><span class="sxs-lookup"><span data-stu-id="050f2-356">Do one of the following to publish your generated keys:</span></span>

   - [<span data-ttu-id="050f2-357">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="050f2-357">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
   - [<span data-ttu-id="050f2-358">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="050f2-358">Publish via FTP</span></span>](#publish-via-ftp)
   - [<span data-ttu-id="050f2-359">通过 Visual Studio 2019 或更高版本发布</span><span class="sxs-lookup"><span data-stu-id="050f2-359">Publish via Visual Studio 2019 or later</span></span>](/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="050f2-360">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="050f2-360">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="050f2-361">转到 `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`。</span><span class="sxs-lookup"><span data-stu-id="050f2-361">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

   <span data-ttu-id="050f2-362">例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="050f2-362">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="050f2-363">在密钥存储的代码库中，转到 **customer-key-store\src\customer-key-store** 文件夹，并验证此文件夹是否包含 **customerkeystore.csproj** 文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-363">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="050f2-364">运行 **：dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="050f2-364">Run: **dotnet publish**</span></span>

   <span data-ttu-id="050f2-365">输出窗口显示部署发布的位置的目录。</span><span class="sxs-lookup"><span data-stu-id="050f2-365">The output window displays the directory where the publish was deployed.</span></span>

   <span data-ttu-id="050f2-366">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="050f2-366">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="050f2-367">将发布目录中的所有文件都发送到 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-367">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="050f2-368">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="050f2-368">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="050f2-369">将创建的 .zip 文件拖放到上面打开的 ZipDeployUI 网站。</span><span class="sxs-lookup"><span data-stu-id="050f2-369">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="050f2-370">例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="050f2-370">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="050f2-371">DKE 已部署，你可以浏览到已创建的测试密钥。</span><span class="sxs-lookup"><span data-stu-id="050f2-371">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="050f2-372">继续验证 [以下](#validate-your-deployment) 部署。</span><span class="sxs-lookup"><span data-stu-id="050f2-372">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="050f2-373">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="050f2-373">Publish via FTP</span></span>

1. <span data-ttu-id="050f2-374">连接到上面创建的应用 [服务](#deploy-the-dke-service-and-publish-the-key-store)。</span><span class="sxs-lookup"><span data-stu-id="050f2-374">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

   <span data-ttu-id="050f2-375">在浏览器中，转到 **：Azure 门户**  >  **应用服务**  >  **部署中心**  >  **手动部署**  >  **FTP**  >  **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="050f2-375">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="050f2-376">将显示的连接字符串复制到本地文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-376">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="050f2-377">你将使用这些字符串连接到 Web 应用服务，然后通过 FTP 上载文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-377">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

   <span data-ttu-id="050f2-378">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-378">For example:</span></span>

   ![从 FTP 仪表板复制连接字符串](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="050f2-380">在密钥存储的代码库中，转到 **customer-key-store\src\customer-key-store 目录**。</span><span class="sxs-lookup"><span data-stu-id="050f2-380">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="050f2-381">验证此目录是否包含 **customerkeystore.csproj** 文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-381">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="050f2-382">运行 **：dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="050f2-382">Run: **dotnet publish**</span></span>

   <span data-ttu-id="050f2-383">输出包含部署发布时所位于的目录。</span><span class="sxs-lookup"><span data-stu-id="050f2-383">The output contains the directory where the publish was deployed.</span></span>

   <span data-ttu-id="050f2-384">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="050f2-384">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="050f2-385">将发布目录中的所有文件都发送到 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="050f2-385">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="050f2-386">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="050f2-386">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="050f2-387">从 FTP 客户端，使用复制的连接信息连接到应用服务。</span><span class="sxs-lookup"><span data-stu-id="050f2-387">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="050f2-388">将上一步中创建的 .zip 文件上载到 Web 应用的根目录。</span><span class="sxs-lookup"><span data-stu-id="050f2-388">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="050f2-389">DKE 已部署，你可以浏览到已创建的测试密钥。</span><span class="sxs-lookup"><span data-stu-id="050f2-389">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="050f2-390">接下来， [验证部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="050f2-390">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="050f2-391">验证部署</span><span class="sxs-lookup"><span data-stu-id="050f2-391">Validate your deployment</span></span>

<span data-ttu-id="050f2-392">使用上述方法之一部署 DKE 后，验证部署和密钥存储设置。</span><span class="sxs-lookup"><span data-stu-id="050f2-392">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="050f2-393">运行：</span><span class="sxs-lookup"><span data-stu-id="050f2-393">Run:</span></span>

```powershell
src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey
```

<span data-ttu-id="050f2-394">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-394">For example:</span></span>

```powershell
key_store_tester.ps1 https://mydkeservice.com/mykey
```

<span data-ttu-id="050f2-395">确保输出中未出现任何错误。</span><span class="sxs-lookup"><span data-stu-id="050f2-395">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="050f2-396">准备就绪后，注册 [密钥存储](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="050f2-396">When you're ready, [register your key store](#register-your-key-store).</span></span>

<span data-ttu-id="050f2-397">键名称区分大小写。</span><span class="sxs-lookup"><span data-stu-id="050f2-397">The key name is case sensitive.</span></span> <span data-ttu-id="050f2-398">输入出现在 on 文件上的appsettings.js名称。</span><span class="sxs-lookup"><span data-stu-id="050f2-398">Enter the key name as it appears in the appsettings.json file.</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="050f2-399">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="050f2-399">Register your key store</span></span>

<span data-ttu-id="050f2-400">通过以下步骤注册 DKE 服务。</span><span class="sxs-lookup"><span data-stu-id="050f2-400">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="050f2-401">注册 DKE 服务是部署 DKE 的最后一步，然后才能开始创建标签。</span><span class="sxs-lookup"><span data-stu-id="050f2-401">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="050f2-402">注册 DKE 服务：</span><span class="sxs-lookup"><span data-stu-id="050f2-402">To register the DKE service:</span></span>

1. <span data-ttu-id="050f2-403">在浏览器中，打开 [Microsoft Azure 门户](https://ms.portal.azure.com/)，然后转到"所有 **服务** \> **标识** \> **应用注册"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-403">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="050f2-404">选择 **"新建注册**"，然后输入有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="050f2-404">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="050f2-405">从显示的选项中选择帐户类型。</span><span class="sxs-lookup"><span data-stu-id="050f2-405">Select an account type from the options displayed.</span></span>

   <span data-ttu-id="050f2-406">如果你将 Microsoft Azure 与非自定义域（如 **onmicrosoft.com）** 一同使用，请选择"仅 Microsoft (- 单租户 **) "。**</span><span class="sxs-lookup"><span data-stu-id="050f2-406">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

   <span data-ttu-id="050f2-407">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-407">For example:</span></span>

   > [!div class="mx-imgBorder"]
   > <span data-ttu-id="050f2-408">![新应用注册](../media/dke-app-registration.png)</span><span class="sxs-lookup"><span data-stu-id="050f2-408">![New App Registration](../media/dke-app-registration.png)</span></span>

4. <span data-ttu-id="050f2-409">在页面底部， **选择注册以** 创建新的应用注册。</span><span class="sxs-lookup"><span data-stu-id="050f2-409">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="050f2-410">在新的应用注册中，在左窗格中的"管理 **"** 下，选择"身份验证 **"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-410">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="050f2-411">选择 **"添加平台"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-411">Select **Add a platform**.</span></span>

7. <span data-ttu-id="050f2-412">在"**配置平台"** 弹出窗口中，选择 **"Web"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-412">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="050f2-413">在 **"重定向 URI"** 下，输入双密钥加密服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="050f2-413">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="050f2-414">输入应用服务 URL，包括主机名和域。</span><span class="sxs-lookup"><span data-stu-id="050f2-414">Enter the App Service URL, including both the hostname and domain.</span></span>

   <span data-ttu-id="050f2-415">例如：https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="050f2-415">For example: https://mydkeservicetest.com</span></span>

   - <span data-ttu-id="050f2-416">输入的 URL 必须与部署 DKE 服务的主机名匹配。</span><span class="sxs-lookup"><span data-stu-id="050f2-416">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
   - <span data-ttu-id="050f2-417">如果要在本地使用 Visual Studio 测试，请使用 **https://localhost:5001** 。</span><span class="sxs-lookup"><span data-stu-id="050f2-417">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
   - <span data-ttu-id="050f2-418">在所有情况下，方案都必须是 **https**。</span><span class="sxs-lookup"><span data-stu-id="050f2-418">In all cases, the scheme must be **https**.</span></span>

   <span data-ttu-id="050f2-419">确保主机名与应用服务主机名完全匹配。</span><span class="sxs-lookup"><span data-stu-id="050f2-419">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="050f2-420">你可能已更改它以 `localhost` 对生成进行疑难解答。</span><span class="sxs-lookup"><span data-stu-id="050f2-420">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="050f2-421">在 **appsettings.js中**，此值为 设置的主机名 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="050f2-421">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="050f2-422">在 **"隐式授予"** 下 **，选中"ID 令牌"** 复选框。</span><span class="sxs-lookup"><span data-stu-id="050f2-422">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="050f2-423">选择“**保存**”以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="050f2-423">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="050f2-424">在左窗格中，选择 **"公开 API"，** 然后在"应用程序 ID URI"旁边，选择"设置 **"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-424">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="050f2-425">仍在"**公开 API"页上** 的"此 **API** 定义的范围"区域中，选择"**添加范围"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-425">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="050f2-426">在新作用域中：</span><span class="sxs-lookup"><span data-stu-id="050f2-426">In the new scope:</span></span>

    1. <span data-ttu-id="050f2-427">将范围名称定义为 **user_impersonation**。</span><span class="sxs-lookup"><span data-stu-id="050f2-427">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="050f2-428">选择可同意的管理员和用户。</span><span class="sxs-lookup"><span data-stu-id="050f2-428">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="050f2-429">定义所需的任何剩余值。</span><span class="sxs-lookup"><span data-stu-id="050f2-429">Define any remaining values required.</span></span>

    4. <span data-ttu-id="050f2-430">选择“添加作用域”。</span><span class="sxs-lookup"><span data-stu-id="050f2-430">Select **Add scope**.</span></span>

    5. <span data-ttu-id="050f2-431">选择 **顶部的** "保存"保存更改。</span><span class="sxs-lookup"><span data-stu-id="050f2-431">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="050f2-432">仍在"**公开 API"页上** 的 **"授权客户端** 应用程序"区域中，选择"**添加客户端应用程序"。**</span><span class="sxs-lookup"><span data-stu-id="050f2-432">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="050f2-433">在新的客户端应用程序中：</span><span class="sxs-lookup"><span data-stu-id="050f2-433">In the new client application:</span></span>

    1. <span data-ttu-id="050f2-434">将客户端 ID 定义为 `d3590ed6-52b3-4102-aeff-aad2292ab01c` 。</span><span class="sxs-lookup"><span data-stu-id="050f2-434">Define the Client ID as `d3590ed6-52b3-4102-aeff-aad2292ab01c`.</span></span> <span data-ttu-id="050f2-435">此值是Microsoft Office ID，使 Office 能够获取密钥存储的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="050f2-435">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="050f2-436">在 **"授权范围"\*\*\*\*下，选择** user_impersonation范围。</span><span class="sxs-lookup"><span data-stu-id="050f2-436">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="050f2-437">选择“添加应用程序”。</span><span class="sxs-lookup"><span data-stu-id="050f2-437">Select **Add application**.</span></span>

    4. <span data-ttu-id="050f2-438">选择 **顶部的** "保存"保存更改。</span><span class="sxs-lookup"><span data-stu-id="050f2-438">Select **Save** at the top to save your changes.</span></span>

    5. <span data-ttu-id="050f2-439">重复这些步骤，但这次将客户端 ID 定义为 `c00e9d32-3c8d-4a7d-832b-029040e7db99` 。</span><span class="sxs-lookup"><span data-stu-id="050f2-439">Repeat these steps, but this time, define the client ID as `c00e9d32-3c8d-4a7d-832b-029040e7db99`.</span></span> <span data-ttu-id="050f2-440">此值为 Azure 信息保护统一标记客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="050f2-440">This value is the Azure Information Protection unified labeling client ID.</span></span> 

<span data-ttu-id="050f2-441">现在已注册 DKE 服务。</span><span class="sxs-lookup"><span data-stu-id="050f2-441">Your DKE service is now registered.</span></span> <span data-ttu-id="050f2-442">通过使用 [DKE 继续创建标签](#create-sensitivity-labels-using-dke)。</span><span class="sxs-lookup"><span data-stu-id="050f2-442">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="050f2-443">使用 DKE 创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="050f2-443">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="050f2-444">在 Microsoft 365 合规中心，创建一个新的敏感度标签，并像否则一样应用加密。</span><span class="sxs-lookup"><span data-stu-id="050f2-444">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="050f2-445">选择 **"使用双密钥加密** "，然后输入密钥的终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="050f2-445">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="050f2-446">例如：</span><span class="sxs-lookup"><span data-stu-id="050f2-446">For example:</span></span>

> [!div class="mx-imgBorder"]
> <span data-ttu-id="050f2-447">![选择 Microsoft 365 合规中心中的"使用双密钥加密"](../media/dke-use-dke.png)</span><span class="sxs-lookup"><span data-stu-id="050f2-447">![Select Use Double Key Encryption in the Microsoft 365 compliance center](../media/dke-use-dke.png)</span></span>

<span data-ttu-id="050f2-448">你添加的任何 DKE 标签都将开始在最新版本的 Microsoft 365 企业应用版中向用户显示。</span><span class="sxs-lookup"><span data-stu-id="050f2-448">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="050f2-449">客户端可能需要 24 小时才能刷新新标签。</span><span class="sxs-lookup"><span data-stu-id="050f2-449">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="050f2-450">在客户端中启用 DKE</span><span class="sxs-lookup"><span data-stu-id="050f2-450">Enable DKE in your client</span></span>

<span data-ttu-id="050f2-451">如果你是 Office 预览体验成员，则启用 DKE。</span><span class="sxs-lookup"><span data-stu-id="050f2-451">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="050f2-452">否则，请通过添加以下注册表项为客户端启用 DKE：</span><span class="sxs-lookup"><span data-stu-id="050f2-452">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```console
   [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001

   [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
   "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="050f2-453">将受保护的文件从 HYOK 标签迁移到 DKE 标签</span><span class="sxs-lookup"><span data-stu-id="050f2-453">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="050f2-454">如果需要，完成 DKE 设置后，可以将使用 HYOK 标签保护的内容迁移到 DKE 标签。</span><span class="sxs-lookup"><span data-stu-id="050f2-454">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="050f2-455">若要迁移，请使用 AIP 扫描程序。</span><span class="sxs-lookup"><span data-stu-id="050f2-455">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="050f2-456">若要开始使用扫描程序，请参阅什么是[Azure 信息保护统一标签扫描程序？。](/azure/information-protection/deploy-aip-scanner)</span><span class="sxs-lookup"><span data-stu-id="050f2-456">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="050f2-457">如果不迁移内容，HYOK 保护的内容将不受影响。</span><span class="sxs-lookup"><span data-stu-id="050f2-457">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
