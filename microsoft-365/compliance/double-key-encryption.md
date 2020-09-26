---
title: " (DKE) 的双重密钥加密"
description: DKE 使您能够保护高度敏感的数据，同时保持对密钥的完全控制。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 09/22/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 39d7933014f1dc71f8c94e467954d36ede4fb451
ms.sourcegitcommit: 1423e08a02d30f0a2b993fb99325c3f499c31787
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/25/2020
ms.locfileid: "48277529"
---
# <a name="double-key-encryption-for-microsoft-365"></a><span data-ttu-id="55495-103">适用于 Microsoft 365 的双重密钥加密</span><span class="sxs-lookup"><span data-stu-id="55495-103">Double Key Encryption for Microsoft 365</span></span>

> <span data-ttu-id="55495-104">*适用于：针对 Microsoft 365 的双重密钥加密， [microsoft 365 合规性](https://www.microsoft.com/microsoft-365/business/compliance-management)， [Azure 信息保护](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="55495-104">*Applies to: Double Key Encryption for Microsoft 365, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="55495-105">*说明： [Azure 信息保护统一标签客户端 For Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="55495-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="55495-106">*服务说明： [Microsoft 365 合规性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="55495-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="55495-107">双密钥加密 (DKE) 将两个键一起使用，以访问受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="55495-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="55495-108">Microsoft 在 Microsoft Azure 中存储一个密钥，并保留另一个密钥。</span><span class="sxs-lookup"><span data-stu-id="55495-108">Microsoft stores one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="55495-109">您可以使用双重密钥加密服务来维护对某个密钥的完全控制。</span><span class="sxs-lookup"><span data-stu-id="55495-109">You maintain full control of one of your keys using the Double Key Encryption service.</span></span> <span data-ttu-id="55495-110">您可以使用 Azure 信息保护统一标记客户端对高度敏感的内容应用保护。</span><span class="sxs-lookup"><span data-stu-id="55495-110">You apply protection using The Azure Information Protection unified labeling client to your highly sensitive content.</span></span>

<span data-ttu-id="55495-111">双密钥加密支持云和本地部署。</span><span class="sxs-lookup"><span data-stu-id="55495-111">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="55495-112">这些部署有助于确保在任何位置存储受保护的数据时，加密的数据保持不透明。</span><span class="sxs-lookup"><span data-stu-id="55495-112">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="55495-113">有关默认的基于云的租户根密钥的详细信息，请参阅 [规划和实现 Azure 信息保护租户密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="55495-113">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

## <a name="when-your-organization-should-adopt-dke"></a><span data-ttu-id="55495-114">您的组织应采用 DKE</span><span class="sxs-lookup"><span data-stu-id="55495-114">When your organization should adopt DKE</span></span>

<span data-ttu-id="55495-115">双密钥加密适用于受最严格的保护要求的敏感数据。</span><span class="sxs-lookup"><span data-stu-id="55495-115">Double Key Encryption is intended for your most sensitive data that is subject to the strictest protection requirements.</span></span> <span data-ttu-id="55495-116">DKE 并非适用于所有数据。</span><span class="sxs-lookup"><span data-stu-id="55495-116">DKE is not intended for all data.</span></span> <span data-ttu-id="55495-117">通常情况下，将使用双密钥加密来保护您的总体数据的一部分。</span><span class="sxs-lookup"><span data-stu-id="55495-117">In general, you'll be using Double Key Encryption to protect only a very small part of your overall data.</span></span> <span data-ttu-id="55495-118">在部署之前，应努力确定要与此解决方案一起涵盖的正确数据。</span><span class="sxs-lookup"><span data-stu-id="55495-118">You should do due diligence in identifying the right data to cover with this solution before you deploy.</span></span> <span data-ttu-id="55495-119">在某些情况下，您可能需要缩小范围，并对大部分数据（如 Microsoft 管理的密钥或 BYOK 的 Microsoft 信息保护）使用其他解决方案。</span><span class="sxs-lookup"><span data-stu-id="55495-119">In some cases, you might need to narrow your scope and make use of other solutions for the majority of your data such as Microsoft Information Protection with Microsoft-managed keys or BYOK.</span></span> <span data-ttu-id="55495-120">这些解决方案足以满足不受增强的保护和法规要求的文档。</span><span class="sxs-lookup"><span data-stu-id="55495-120">These solutions are sufficient for documents that aren't subject to enhanced protections and regulatory requirements.</span></span> <span data-ttu-id="55495-121">此外，这些解决方案使您能够使用最强大的 Office 365 服务;您不能与 DKE 加密内容一起使用的服务。</span><span class="sxs-lookup"><span data-stu-id="55495-121">Also, these solutions enable you to use the most powerful Office 365 services; services that you can't use with DKE encrypted content.</span></span> <span data-ttu-id="55495-122">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-122">For example:</span></span>

- <span data-ttu-id="55495-123">传输规则，包括需要查看附件的反恶意软件和垃圾邮件</span><span class="sxs-lookup"><span data-stu-id="55495-123">Transport rules including anti-malware and spam that require visibility into the attachment</span></span>
- <span data-ttu-id="55495-124">Microsoft Delve</span><span class="sxs-lookup"><span data-stu-id="55495-124">Microsoft Delve</span></span>
- <span data-ttu-id="55495-125">电子数据展示</span><span class="sxs-lookup"><span data-stu-id="55495-125">eDiscovery</span></span>
- <span data-ttu-id="55495-126">内容搜索和索引</span><span class="sxs-lookup"><span data-stu-id="55495-126">Content search and indexing</span></span>
- <span data-ttu-id="55495-127">Office Web Apps 包括共同创作功能</span><span class="sxs-lookup"><span data-stu-id="55495-127">Office Web Apps including co-authoring functionality</span></span>

<span data-ttu-id="55495-128">任何未与 DKE 集成在 MIP SDK 中的外部应用程序或服务将无法对加密数据执行操作。</span><span class="sxs-lookup"><span data-stu-id="55495-128">Any external applications or services that are not integrated with DKE through the MIP SDK will be unable to perform actions on the encrypted data.</span></span>

<span data-ttu-id="55495-129">Microsoft Information Protection SDK 1.7 + 支持双密钥加密;与我们的 SDK 集成的应用程序将能够通过适当的权限和集成来导致此数据的原因。</span><span class="sxs-lookup"><span data-stu-id="55495-129">The Microsoft Information Protection SDK 1.7+ supports Double Key Encryption; applications that integrate with our SDK will be able to reason over this data with sufficient permissions and integrations in place.</span></span>

<span data-ttu-id="55495-130">我们建议组织使用 Microsoft 信息保护功能 (分类和标签) 保护其大部分敏感数据，并仅将 DKE 用于其任务关键型数据。</span><span class="sxs-lookup"><span data-stu-id="55495-130">We recommend organizations use Microsoft Information protection capabilities (classification and labeling) to protect most of their sensitive data and only use DKE for their mission-critical data.</span></span> <span data-ttu-id="55495-131">双密钥加密尤其适用于高度管控行业（如金融服务业和医疗保健行业）中的极其敏感的数据。</span><span class="sxs-lookup"><span data-stu-id="55495-131">Double Key Encryption is particularly relevant for extremely sensitive data in highly regulated industries such as Financial services and Healthcare.</span></span>

<span data-ttu-id="55495-132">如果您的组织有以下任一要求，您可以使用 DKE 帮助保护您的内容：</span><span class="sxs-lookup"><span data-stu-id="55495-132">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="55495-133">您希望确保 *只有* 在所有情况下都可以对受保护的内容进行解密。</span><span class="sxs-lookup"><span data-stu-id="55495-133">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="55495-134">您不希望 Microsoft 能够单独访问受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="55495-134">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="55495-135">您有管理法规要求，可在地理边界内保留密钥。</span><span class="sxs-lookup"><span data-stu-id="55495-135">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="55495-136">您为数据加密和解密而保留的所有密钥都将保留在您的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="55495-136">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="55495-137">DKE 的系统和许可要求</span><span class="sxs-lookup"><span data-stu-id="55495-137">System and licensing requirements for DKE</span></span>

<span data-ttu-id="55495-138">Microsoft 365 E5 和 Office 365 E5 提供了**适用于 microsoft 365 的双重密钥加密**。</span><span class="sxs-lookup"><span data-stu-id="55495-138">**Double Key Encryption for Microsoft 365** comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="55495-139">如果你没有 Microsoft 365 E5 许可证，你可以注册 [试用版](https://aka.ms/M365E5ComplianceTrial)。</span><span class="sxs-lookup"><span data-stu-id="55495-139">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="55495-140">有关这些许可证的详细信息，请参阅 [适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="55495-140">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="55495-141">**Azure 信息保护**。</span><span class="sxs-lookup"><span data-stu-id="55495-141">**Azure Information Protection**.</span></span> <span data-ttu-id="55495-142">DKE 使用灵敏度标签，需要 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="55495-142">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

<span data-ttu-id="55495-143">通过 Office 桌面应用程序中的灵敏度功能区，最终用户可以使用 DKE 敏感度标签。</span><span class="sxs-lookup"><span data-stu-id="55495-143">DKE sensitivity labels are made available to end-users through the sensitivity ribbon in Office Desktop Apps.</span></span> <span data-ttu-id="55495-144">在要保护和使用受保护文档的每台客户端计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="55495-144">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="55495-145">**适用于企业版的 Microsoft Office 应用** 版本12711或更高版本 (Windows 上的 Word、PowerPoint 和 Excel) 的桌面版本。</span><span class="sxs-lookup"><span data-stu-id="55495-145">**Microsoft Office Apps for enterprise** version \*.12711 or later (Desktop versions of Word, PowerPoint, and Excel) on Windows.</span></span>

<span data-ttu-id="55495-146">**Azure 信息保护统一标签客户端** 版本2.7.93.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="55495-146">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="55495-147">从 [Microsoft 下载中心](https://www.microsoft.com/download/details.aspx?id=53018)下载并安装统一的标签客户端。</span><span class="sxs-lookup"><span data-stu-id="55495-147">Download and install the Unified Labeling client from the [Microsoft download center](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="55495-148">用于存储和查看受 DKE 保护的内容的受支持的环境</span><span class="sxs-lookup"><span data-stu-id="55495-148">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="55495-149">**支持的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="55495-149">**Supported applications**.</span></span> <span data-ttu-id="55495-150">Windows 上[的适用于企业客户端的 Microsoft 365 应用程序](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)，包括 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="55495-150">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="55495-151">**在线内容支持**。</span><span class="sxs-lookup"><span data-stu-id="55495-151">**Online content support**.</span></span> <span data-ttu-id="55495-152">支持在 Microsoft SharePoint 和 OneDrive for Business 中联机存储的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="55495-152">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="55495-153">您可以通过电子邮件共享加密内容，但不能联机查看加密的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="55495-153">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="55495-154">相反，您必须使用本地计算机上的桌面应用程序查看受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="55495-154">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="overview-of-deploying-dke"></a><span data-ttu-id="55495-155">部署 DKE 概述</span><span class="sxs-lookup"><span data-stu-id="55495-155">Overview of deploying DKE</span></span>

<span data-ttu-id="55495-156">您将按照以下常规步骤设置 DKE。</span><span class="sxs-lookup"><span data-stu-id="55495-156">You'll follow these general steps to set up DKE.</span></span> <span data-ttu-id="55495-157">完成这些步骤后，最终用户将能够使用双密钥加密来保护高度敏感的数据。</span><span class="sxs-lookup"><span data-stu-id="55495-157">Once you've completed these steps, your end users will be able to protect your highly sensitive data with Double Key Encryption.</span></span>

1. <span data-ttu-id="55495-158">部署 DKE 服务，如本文中所述。</span><span class="sxs-lookup"><span data-stu-id="55495-158">Deploy the DKE service as described in this article.</span></span>

2. <span data-ttu-id="55495-159">创建带双密钥加密的标签。</span><span class="sxs-lookup"><span data-stu-id="55495-159">Create a label with Double Key Encryption.</span></span> <span data-ttu-id="55495-160">导航到 [Microsoft 365 合规性中心](https://compliance.microsoft.com) 下的信息保护，并创建带双密钥加密的新标签。</span><span class="sxs-lookup"><span data-stu-id="55495-160">Navigate to Information protection under the [Microsoft 365 compliance center](https://compliance.microsoft.com) and create a new label with Double Key Encryption.</span></span> <span data-ttu-id="55495-161">请参阅 [使用敏感度标签限制对内容的访问，以应用加密](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels)。</span><span class="sxs-lookup"><span data-stu-id="55495-161">See [Restrict access to content by using sensitivity labels to apply encryption](https://docs.microsoft.com/microsoft-365/compliance/encryption-sensitivity-labels).</span></span>

3. <span data-ttu-id="55495-162">使用双密钥加密标签。</span><span class="sxs-lookup"><span data-stu-id="55495-162">Use Double Key Encryption labels.</span></span> <span data-ttu-id="55495-163">通过在 Microsoft Office 中的 "敏感度" 功能区中选择 "双密钥加密" 标签来保护数据。</span><span class="sxs-lookup"><span data-stu-id="55495-163">Protect data by selecting the Double Key Encrypted label from the Sensitivity ribbon in Microsoft Office.</span></span>

<span data-ttu-id="55495-164">有几种方法可以完成一些部署双密钥加密的步骤。</span><span class="sxs-lookup"><span data-stu-id="55495-164">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="55495-165">本文提供了详细说明，以便让经验较少的管理员能够成功部署服务。</span><span class="sxs-lookup"><span data-stu-id="55495-165">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="55495-166">如果你愿意，可以选择使用自己的方法。</span><span class="sxs-lookup"><span data-stu-id="55495-166">If you're comfortable doing so, you can choose to use your own methods.</span></span>

## <a name="deploy-dke"></a><span data-ttu-id="55495-167">部署 DKE</span><span class="sxs-lookup"><span data-stu-id="55495-167">Deploy DKE</span></span>

<span data-ttu-id="55495-168">本文和部署视频使用 Azure 作为 DKE 服务的部署目标。</span><span class="sxs-lookup"><span data-stu-id="55495-168">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="55495-169">如果要部署到其他位置，则需要提供自己的值。</span><span class="sxs-lookup"><span data-stu-id="55495-169">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="55495-170">观看 " [双重密钥加密部署" 视频](https://youtu.be/vDWfHN_kygg) ，以查看本文中的概念的分步概述。</span><span class="sxs-lookup"><span data-stu-id="55495-170">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see a step-by-step overview of the concepts in this article.</span></span> <span data-ttu-id="55495-171">完成该视频需要18分钟左右。</span><span class="sxs-lookup"><span data-stu-id="55495-171">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="55495-172">您将按照这些常规步骤为您的组织设置双密钥加密。</span><span class="sxs-lookup"><span data-stu-id="55495-172">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="55495-173">安装 DKE 服务的必备软件</span><span class="sxs-lookup"><span data-stu-id="55495-173">Install software prerequisites for the DKE service</span></span>](#install-software-prerequisites-for-the-dke-service)
1. [<span data-ttu-id="55495-174">克隆双密钥加密 GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="55495-174">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="55495-175">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="55495-175">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="55495-176">生成测试键</span><span class="sxs-lookup"><span data-stu-id="55495-176">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="55495-177">生成项目</span><span class="sxs-lookup"><span data-stu-id="55495-177">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="55495-178">部署 DKE 服务并发布密钥存储区</span><span class="sxs-lookup"><span data-stu-id="55495-178">Deploy the DKE service and publish the key store</span></span>](#deploy-the-dke-service-and-publish-the-key-store)
1. [<span data-ttu-id="55495-179">验证部署</span><span class="sxs-lookup"><span data-stu-id="55495-179">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="55495-180">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="55495-180">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="55495-181">使用 DKE 创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="55495-181">Create sensitivity labels using DKE</span></span>](#create-sensitivity-labels-using-dke)
1. [<span data-ttu-id="55495-182">在客户端中启用 DKE</span><span class="sxs-lookup"><span data-stu-id="55495-182">Enable DKE in your client</span></span>](#enable-dke-in-your-client)
1. [<span data-ttu-id="55495-183">将受保护的文件从 HYOK 标签迁移到 DKE 标签</span><span class="sxs-lookup"><span data-stu-id="55495-183">Migrate protected files from HYOK labels to DKE labels</span></span>](#migrate-protected-files-from-hyok-labels-to-dke-labels)

<span data-ttu-id="55495-184">完成后，您可以使用 DKE 对文档和文件进行加密。</span><span class="sxs-lookup"><span data-stu-id="55495-184">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="55495-185">有关信息，请参阅 [将敏感度标签应用于 Office 中的文件和电子邮件](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。</span><span class="sxs-lookup"><span data-stu-id="55495-185">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites-for-the-dke-service"></a><span data-ttu-id="55495-186">安装 DKE 服务的必备软件</span><span class="sxs-lookup"><span data-stu-id="55495-186">Install software prerequisites for the DKE service</span></span>

<span data-ttu-id="55495-187">在要安装 DKE 服务的计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="55495-187">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="55495-188">**.Net Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="55495-188">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="55495-189">从 [下载 .Net Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)下载并安装 SDK。</span><span class="sxs-lookup"><span data-stu-id="55495-189">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="55495-190">**Visual Studio Code**。</span><span class="sxs-lookup"><span data-stu-id="55495-190">**Visual Studio Code**.</span></span> <span data-ttu-id="55495-191">从下载 Visual Studio Code [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="55495-191">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="55495-192">安装完成后，运行 Visual Studio Code 并选择 " **查看** \> **扩展**"。</span><span class="sxs-lookup"><span data-stu-id="55495-192">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="55495-193">安装这些扩展。</span><span class="sxs-lookup"><span data-stu-id="55495-193">Install these extensions.</span></span>

- <span data-ttu-id="55495-194">Visual Studio Code 的 c #</span><span class="sxs-lookup"><span data-stu-id="55495-194">C# for Visual Studio Code</span></span>

- <span data-ttu-id="55495-195">NuGet 包管理器</span><span class="sxs-lookup"><span data-stu-id="55495-195">NuGet Package Manager</span></span>

<span data-ttu-id="55495-196">**Git 资源**。</span><span class="sxs-lookup"><span data-stu-id="55495-196">**Git resources**.</span></span> <span data-ttu-id="55495-197">下载并安装以下各项之一。</span><span class="sxs-lookup"><span data-stu-id="55495-197">Download and install one of the following.</span></span>

- [<span data-ttu-id="55495-198">Git</span><span class="sxs-lookup"><span data-stu-id="55495-198">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="55495-199">GitHub 桌面</span><span class="sxs-lookup"><span data-stu-id="55495-199">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="55495-200">GitHub 企业</span><span class="sxs-lookup"><span data-stu-id="55495-200">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="55495-201">**OpenSSL** 您必须安装了 [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) ，才能在部署 DKE 后 [生成测试密钥](#generate-test-keys) 。</span><span class="sxs-lookup"><span data-stu-id="55495-201">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="55495-202">请确保您从环境变量路径中正确调用了它。</span><span class="sxs-lookup"><span data-stu-id="55495-202">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="55495-203">例如，有关详细信息，请参阅 "将安装目录添加到路径" [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) 。</span><span class="sxs-lookup"><span data-stu-id="55495-203">For example, see "Add the installation directory to PATH" at [https://www.osradar.com/install-openssl-windows/](https://www.osradar.com/install-openssl-windows/) for details.</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="55495-204">克隆 DKE GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="55495-204">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="55495-205">Microsoft 提供 GitHub 存储库中的 DKE 源文件。</span><span class="sxs-lookup"><span data-stu-id="55495-205">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="55495-206">克隆存储库，以在本地为组织的使用生成项目。</span><span class="sxs-lookup"><span data-stu-id="55495-206">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="55495-207">DKE GitHub 存储库位于 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="55495-207">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="55495-208">以下说明适用于缺乏的 git 或 Visual Studio Code users：</span><span class="sxs-lookup"><span data-stu-id="55495-208">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="55495-209">在浏览器中，转到： [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="55495-209">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

2. <span data-ttu-id="55495-210">在屏幕右侧，选择 " **代码**"。</span><span class="sxs-lookup"><span data-stu-id="55495-210">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="55495-211">您的 UI 版本可能会显示 " **克隆" 或 "下载** " 按钮。</span><span class="sxs-lookup"><span data-stu-id="55495-211">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="55495-212">然后，在出现的下拉列表中，选择 "复制" 图标将 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="55495-212">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="55495-213">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-213">For example:</span></span>

   ![从 GitHub 克隆双密钥加密服务存储库](../media/dke-clone.png)

3. <span data-ttu-id="55495-215">在 Visual Studio Code 中，选择 " **查看** \> **命令选项板** "，然后选择 " **Git： Clone**"。</span><span class="sxs-lookup"><span data-stu-id="55495-215">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="55495-216">若要跳转到列表中的选项，请开始键入 `git: clone` 以筛选条目，然后从下拉列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="55495-216">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="55495-217">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-217">For example:</span></span>

   ![Visual Studio Code GIT： Clone 选项](../media/dke-vscode-clone.png)

4. <span data-ttu-id="55495-219">在文本框中，粘贴从 Git 复制的 URL，然后 **从 GitHub 中**选择 "复制"。</span><span class="sxs-lookup"><span data-stu-id="55495-219">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="55495-220">在出现的 " **选择文件夹** " 对话框中，浏览并选择存储库的位置。</span><span class="sxs-lookup"><span data-stu-id="55495-220">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="55495-221">在提示符下，选择 " **打开**"。</span><span class="sxs-lookup"><span data-stu-id="55495-221">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="55495-222">存储库将在 Visual Studio Code 中打开，并在左下角显示当前 Git 分支。</span><span class="sxs-lookup"><span data-stu-id="55495-222">The repository opens in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="55495-223">分支应为 **master**。</span><span class="sxs-lookup"><span data-stu-id="55495-223">The branch should be **master**.</span></span>

    <span data-ttu-id="55495-224">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-224">For example:</span></span>

   ![Visual Studio Code master 分支](../media/dke-vscode-master.png)

6. <span data-ttu-id="55495-226">从分支列表中选择 "word **母版** "。</span><span class="sxs-lookup"><span data-stu-id="55495-226">Select the word **master** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="55495-227">选择主分支可确保您具有用于生成项目的正确文件。</span><span class="sxs-lookup"><span data-stu-id="55495-227">Selecting the master branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="55495-228">如果不选择正确的分支，部署将会失败。</span><span class="sxs-lookup"><span data-stu-id="55495-228">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="55495-229">现在，你已在本地设置了 DKE 源存储库。</span><span class="sxs-lookup"><span data-stu-id="55495-229">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="55495-230">接下来，修改您的组织的 [应用程序设置](#modify-application-settings) 。</span><span class="sxs-lookup"><span data-stu-id="55495-230">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="55495-231">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="55495-231">Modify application settings</span></span>

<span data-ttu-id="55495-232">若要部署 DKE 服务，必须修改以下类型的应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="55495-232">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="55495-233">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="55495-233">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="55495-234">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="55495-234">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="55495-235">您可以在 appsettings.js的文件中修改应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="55495-235">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="55495-236">此文件位于本地克隆的 DoubleKeyEncryptionService 存储库中的 DoubleKeyEncryptionService\src\customer-key-store。</span><span class="sxs-lookup"><span data-stu-id="55495-236">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="55495-237">例如，在 Visual Studio Code 中，可以按下图所示浏览到文件。</span><span class="sxs-lookup"><span data-stu-id="55495-237">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![为 DKE 查找文件上的 appsettings.js。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="55495-239">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="55495-239">Key access settings</span></span>

<span data-ttu-id="55495-240">选择是否使用电子邮件或角色授权。</span><span class="sxs-lookup"><span data-stu-id="55495-240">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="55495-241">DKE 一次仅支持其中一种身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="55495-241">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="55495-242">**电子邮件授权**。</span><span class="sxs-lookup"><span data-stu-id="55495-242">**Email authorization**.</span></span> <span data-ttu-id="55495-243">允许您的组织仅基于电子邮件地址授权访问密钥。</span><span class="sxs-lookup"><span data-stu-id="55495-243">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="55495-244">**角色授权**。</span><span class="sxs-lookup"><span data-stu-id="55495-244">**Role authorization**.</span></span> <span data-ttu-id="55495-245">允许您的组织根据 Active Directory 组授权对密钥的访问，并要求 web 服务可以查询 LDAP。</span><span class="sxs-lookup"><span data-stu-id="55495-245">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="55495-246">**使用电子邮件授权设置 DKE 的密钥访问设置**</span><span class="sxs-lookup"><span data-stu-id="55495-246">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="55495-247">打开文件 \*\* 上\*\* 的 "appsettings.js" 并找到相应的 `AuthorizedEmailAddress` 设置。</span><span class="sxs-lookup"><span data-stu-id="55495-247">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="55495-248">添加要授权的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="55495-248">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="55495-249">用双引号和逗号分隔多个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="55495-249">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="55495-250">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-250">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="55495-251">找到 `LDAPPath` 设置并删除 `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` 双引号之间的文本。</span><span class="sxs-lookup"><span data-stu-id="55495-251">Locate the `LDAPPath` setting and remove the text `If you use role authorization (AuthorizedRoles) then this is the LDAP path.` between the double quotes.</span></span> <span data-ttu-id="55495-252">将双引号括起来。</span><span class="sxs-lookup"><span data-stu-id="55495-252">Leave the double quotes in place.</span></span> <span data-ttu-id="55495-253">完成后，设置应如下所示。</span><span class="sxs-lookup"><span data-stu-id="55495-253">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="55495-254">找到 `AuthorizedRoles` 设置并删除整行。</span><span class="sxs-lookup"><span data-stu-id="55495-254">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="55495-255">此图显示了为电子邮件授权正确设置格式的文件 \*\* 上的appsettings.js\*\* 。</span><span class="sxs-lookup"><span data-stu-id="55495-255">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![对文件显示电子邮件授权方法的 appsettings.js](../media/dke-email-accesssetting.png)

<span data-ttu-id="55495-257">**使用角色授权设置 DKE 的密钥访问设置**</span><span class="sxs-lookup"><span data-stu-id="55495-257">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="55495-258">打开文件 \*\* 上\*\* 的 "appsettings.js" 并找到相应的 `AuthorizedRoles` 设置。</span><span class="sxs-lookup"><span data-stu-id="55495-258">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="55495-259">添加要授权的 Active Directory 组名称。</span><span class="sxs-lookup"><span data-stu-id="55495-259">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="55495-260">用双引号和逗号分隔多个组名称。</span><span class="sxs-lookup"><span data-stu-id="55495-260">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="55495-261">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-261">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="55495-262">找到 `LDAPPath` 设置并添加 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="55495-262">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="55495-263">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-263">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="55495-264">找到 `AuthorizedEmailAddress` 设置并删除整行。</span><span class="sxs-lookup"><span data-stu-id="55495-264">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="55495-265">此图显示了为角色授权正确设置文件格式的 **appsettings.js** 。</span><span class="sxs-lookup"><span data-stu-id="55495-265">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![对显示角色授权方法的文件 appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="55495-267">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="55495-267">Tenant and key settings</span></span>

<span data-ttu-id="55495-268">DKE 租户和关键设置位于 " **appsettings.js"** 文件中。</span><span class="sxs-lookup"><span data-stu-id="55495-268">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="55495-269">**为 DKE 配置租户和密钥设置**</span><span class="sxs-lookup"><span data-stu-id="55495-269">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="55495-270">打开文件 \*\* 上\*\* 的 "appsettings.js"。</span><span class="sxs-lookup"><span data-stu-id="55495-270">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="55495-271">找到 `ValidIssuers` 设置并 `<tenantid>` 将其替换为你的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="55495-271">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="55495-272">你可以转到 Azure 门户并查看 [租户属性](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)，以找到你的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="55495-272">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="55495-273">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-273">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="55495-274">找到 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="55495-274">Locate the `JwtAudience`.</span></span> <span data-ttu-id="55495-275">`<yourhostname>`将替换为将运行 DKE 服务的计算机的主机名。</span><span class="sxs-lookup"><span data-stu-id="55495-275">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="55495-276">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-276">For example:</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="55495-277">的值 `JwtAudience` 必须与您的主机的名称 *完全*匹配。</span><span class="sxs-lookup"><span data-stu-id="55495-277">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="55495-278">在调试时，您可以使用 **localhost： 5001** 。</span><span class="sxs-lookup"><span data-stu-id="55495-278">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="55495-279">但是，在完成调试后，请务必将此值更新到服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="55495-279">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="55495-280">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="55495-280">`TestKeys:Name`.</span></span> <span data-ttu-id="55495-281">输入密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="55495-281">Enter a name for your key.</span></span> <span data-ttu-id="55495-282">例如：`TestKey1`</span><span class="sxs-lookup"><span data-stu-id="55495-282">For example: `TestKey1`</span></span>
- <span data-ttu-id="55495-283">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="55495-283">`TestKeys:Id`.</span></span> <span data-ttu-id="55495-284">创建一个 GUID 并输入它作为 `TestKeys:ID` 值。</span><span class="sxs-lookup"><span data-stu-id="55495-284">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="55495-285">例如，`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`。</span><span class="sxs-lookup"><span data-stu-id="55495-285">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="55495-286">您可以使用 [联机 Guid 生成器](https://guidgenerator.com/) 等网站随机生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="55495-286">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="55495-287">此图像显示 **appsettings.js上**的租户和密钥设置的正确格式。</span><span class="sxs-lookup"><span data-stu-id="55495-287">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="55495-288">`LDAPPath` 配置了角色授权。</span><span class="sxs-lookup"><span data-stu-id="55495-288">`LDAPPath` is configured for role authorization.</span></span>

![在 appsettings.js的文件中显示 DKE 的正确租户和密钥设置。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="55495-290">生成测试键</span><span class="sxs-lookup"><span data-stu-id="55495-290">Generate test keys</span></span>

<span data-ttu-id="55495-291">定义应用程序设置后，即可生成公用和专用测试密钥。</span><span class="sxs-lookup"><span data-stu-id="55495-291">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="55495-292">生成密钥：</span><span class="sxs-lookup"><span data-stu-id="55495-292">To generate keys:</span></span>

1. <span data-ttu-id="55495-293">从 Windows "开始" 菜单中，运行 OpenSSL 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="55495-293">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

2. <span data-ttu-id="55495-294">转到要在其中保存测试密钥的文件夹。</span><span class="sxs-lookup"><span data-stu-id="55495-294">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="55495-295">您通过完成此任务中的步骤创建的文件存储在同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="55495-295">The files you create by completing the steps in this task are stored in the same folder.</span></span>

3. <span data-ttu-id="55495-296">生成新的测试密钥。</span><span class="sxs-lookup"><span data-stu-id="55495-296">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

4. <span data-ttu-id="55495-297">生成私钥。</span><span class="sxs-lookup"><span data-stu-id="55495-297">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

5. <span data-ttu-id="55495-298">生成公钥。</span><span class="sxs-lookup"><span data-stu-id="55495-298">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

6. <span data-ttu-id="55495-299">在文本编辑器中，打开 " **pubkeyonly**"。</span><span class="sxs-lookup"><span data-stu-id="55495-299">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="55495-300">将 **pubkeyonly** 文件中除第一行和最后一行之外的所有内容复制到 `PublicPem` "文件中的 **appsettings.js** " 部分。</span><span class="sxs-lookup"><span data-stu-id="55495-300">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

7. <span data-ttu-id="55495-301">在文本编辑器中，打开 " **privkeynopass**"。</span><span class="sxs-lookup"><span data-stu-id="55495-301">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="55495-302">将 **privkeynopass** 文件中除第一行和最后一行之外的所有内容复制到 `PrivatePem` "文件中的 **appsettings.js** " 部分。</span><span class="sxs-lookup"><span data-stu-id="55495-302">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

8. <span data-ttu-id="55495-303">删除和部分中的所有空格和换行符 `PublicPem` `PrivatePem` 。</span><span class="sxs-lookup"><span data-stu-id="55495-303">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="55495-304">复制此内容时，请不要删除任何 PEM 数据。</span><span class="sxs-lookup"><span data-stu-id="55495-304">When you copy this content, do not delete any of the PEM data.</span></span>

9. <span data-ttu-id="55495-305">在 Visual Studio Code 中，浏览到 **Startup.cs** 文件。</span><span class="sxs-lookup"><span data-stu-id="55495-305">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="55495-306">此文件位于本地克隆的 DoubleKeyEncryptionService 存储库中的 DoubleKeyEncryptionService\src\customer-key-store\。</span><span class="sxs-lookup"><span data-stu-id="55495-306">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

10. <span data-ttu-id="55495-307">找到以下行：</span><span class="sxs-lookup"><span data-stu-id="55495-307">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

11. <span data-ttu-id="55495-308">将这些行替换为以下文本：</span><span class="sxs-lookup"><span data-stu-id="55495-308">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="55495-309">最终结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="55495-309">The end results should look similar to the following.</span></span>

   ![用于公共预览的 startup.cs 文件](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="55495-311">现在，你已准备好 [生成 DKE 项目](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="55495-311">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="55495-312">生成项目</span><span class="sxs-lookup"><span data-stu-id="55495-312">Build the project</span></span>

<span data-ttu-id="55495-313">使用以下说明在本地生成 DKE 项目：</span><span class="sxs-lookup"><span data-stu-id="55495-313">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="55495-314">在 Visual Studio Code 中，在 DKE 服务存储库中，选择 " **查看** \> **命令组件面板** "，然后在提示符处键入 **build** 。</span><span class="sxs-lookup"><span data-stu-id="55495-314">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

2. <span data-ttu-id="55495-315">从列表中选择 " **任务：运行生成任务**"。</span><span class="sxs-lookup"><span data-stu-id="55495-315">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="55495-316">如果找不到任何生成任务，请选择 " **配置生成任务** 并为 .net core 创建一个"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="55495-316">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![为 .NET 配置缺少的生成任务](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="55495-318">**从模板中选择 "创建 tasks.js"**。</span><span class="sxs-lookup"><span data-stu-id="55495-318">Choose **Create tasks.json from template**.</span></span>

      ![从 DKE 的模板创建对文件的 tasks.js](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="55495-320">从模板类型列表中，选择 " **.Net Core**"。</span><span class="sxs-lookup"><span data-stu-id="55495-320">From the list of template types, select **.NET Core**.</span></span>

      ![为 DKE 选择正确的模板](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="55495-322">在 "生成" 部分，找到 **customerkeystore** 文件的路径。</span><span class="sxs-lookup"><span data-stu-id="55495-322">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="55495-323">如果没有，则添加以下行：</span><span class="sxs-lookup"><span data-stu-id="55495-323">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

   4. <span data-ttu-id="55495-324">再次运行生成。</span><span class="sxs-lookup"><span data-stu-id="55495-324">Run the build again.</span></span>

3. <span data-ttu-id="55495-325">确认输出窗口中没有红色错误。</span><span class="sxs-lookup"><span data-stu-id="55495-325">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="55495-326">如果出现红色错误，请检查控制台输出。</span><span class="sxs-lookup"><span data-stu-id="55495-326">If there are red errors, check the console output.</span></span> <span data-ttu-id="55495-327">确保您已正确完成上述所有步骤，并且存在正确的生成版本。</span><span class="sxs-lookup"><span data-stu-id="55495-327">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

4. <span data-ttu-id="55495-328">选择 " **运行** \> **启动调试** " 以调试进程。</span><span class="sxs-lookup"><span data-stu-id="55495-328">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="55495-329">如果系统提示您选择环境，请选择 " **.net core**"。</span><span class="sxs-lookup"><span data-stu-id="55495-329">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="55495-330">.NET core 调试器通常会启动到 `https://localhost:5001` 。</span><span class="sxs-lookup"><span data-stu-id="55495-330">The .NET core debugger typically launches to `https://localhost:5001`.</span></span> <span data-ttu-id="55495-331">若要查看测试项，请转到 `https://localhost:5001` 并追加一个正斜杠 (/) 和键的名称。</span><span class="sxs-lookup"><span data-stu-id="55495-331">To view your test key, go to `https://localhost:5001` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="55495-332">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-332">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="55495-333">该项应以 JSON 格式显示。</span><span class="sxs-lookup"><span data-stu-id="55495-333">The key should display in JSON format.</span></span>

<span data-ttu-id="55495-334">你的设置现已完成。</span><span class="sxs-lookup"><span data-stu-id="55495-334">Your setup is now complete.</span></span> <span data-ttu-id="55495-335">在发布密钥库之前，在 appsettings.js的 JwtAudience 设置中，确保主机名的值与您的应用程序服务主机名称完全匹配。</span><span class="sxs-lookup"><span data-stu-id="55495-335">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="55495-336">您可能已将其更改为 localhost 以对生成进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="55495-336">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="deploy-the-dke-service-and-publish-the-key-store"></a><span data-ttu-id="55495-337">部署 DKE 服务并发布密钥存储区</span><span class="sxs-lookup"><span data-stu-id="55495-337">Deploy the DKE service and publish the key store</span></span>

<span data-ttu-id="55495-338">对于生产部署，请在第三方云中部署该服务或 [发布到本地系统](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli)。</span><span class="sxs-lookup"><span data-stu-id="55495-338">For production deployments, deploy the service either in a third-party cloud or [publish to an on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&preserve-view=true&tabs=netcore-cli).</span></span>

<span data-ttu-id="55495-339">您可能更喜欢部署密钥的其他方法。</span><span class="sxs-lookup"><span data-stu-id="55495-339">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="55495-340">选择最适合您的组织的方法。</span><span class="sxs-lookup"><span data-stu-id="55495-340">Select the method that works best for your organization.</span></span>

<span data-ttu-id="55495-341">对于试点部署，您可以在 Azure 中部署并立即开始。</span><span class="sxs-lookup"><span data-stu-id="55495-341">For pilot deployments, you can deploy in Azure and get started right away.</span></span>

<span data-ttu-id="55495-342">**创建 Azure Web 应用程序实例以托管你的 DKE 部署**</span><span class="sxs-lookup"><span data-stu-id="55495-342">**To create an Azure Web App instance to host your DKE deployment**</span></span>

<span data-ttu-id="55495-343">若要发布密钥存储，您将创建一个 Azure 应用服务实例以托管您的 DKE 部署。</span><span class="sxs-lookup"><span data-stu-id="55495-343">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="55495-344">接下来，你将生成的密钥发布到 Azure。</span><span class="sxs-lookup"><span data-stu-id="55495-344">Next, you'll publish your generated keys to Azure.</span></span>

1. <span data-ttu-id="55495-345">在浏览器中，登录到[Microsoft Azure 门户](https://ms.portal.azure.com)，然后转到 "**应用程序服务**" "  >  **添加**"。</span><span class="sxs-lookup"><span data-stu-id="55495-345">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

2. <span data-ttu-id="55495-346">选择订阅和资源组，并定义实例详细信息。</span><span class="sxs-lookup"><span data-stu-id="55495-346">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="55495-347">输入要安装 DKE 服务的计算机的主机名。</span><span class="sxs-lookup"><span data-stu-id="55495-347">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="55495-348">请确保它与在 [**appsettings.json**](#tenant-and-key-settings) file 中为 JwtAudience 设置定义的名称相同。</span><span class="sxs-lookup"><span data-stu-id="55495-348">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="55495-349">您为名称提供的值也是 WebAppInstanceName。</span><span class="sxs-lookup"><span data-stu-id="55495-349">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="55495-350">对于 " **发布**"、"选择 **代码**" 和 " **运行时堆栈**"，选择 " **.net Core 3.1**"。</span><span class="sxs-lookup"><span data-stu-id="55495-350">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="55495-351">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-351">For example:</span></span>

   ![添加应用服务](../media/dke-azure-add-app-service.png)

3. <span data-ttu-id="55495-353">在页面底部，选择 " **审阅 + 创建**"，然后选择 " **添加**"。</span><span class="sxs-lookup"><span data-stu-id="55495-353">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

4. <span data-ttu-id="55495-354">执行下列操作之一以发布生成的密钥：</span><span class="sxs-lookup"><span data-stu-id="55495-354">Do one of the following to publish your generated keys:</span></span>

    - [<span data-ttu-id="55495-355">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="55495-355">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="55495-356">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="55495-356">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="55495-357">通过 Visual Studio 2019 或更高版本发布</span><span class="sxs-lookup"><span data-stu-id="55495-357">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="55495-358">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="55495-358">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="55495-359">转到 `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`。</span><span class="sxs-lookup"><span data-stu-id="55495-359">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="55495-360">例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="55495-360">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

2. <span data-ttu-id="55495-361">在密钥存储的基本代码中，转到 " **customer-key-store\src\customer-key-store** " 文件夹，并验证此文件夹是否包含 **customerkeystore** 文件。</span><span class="sxs-lookup"><span data-stu-id="55495-361">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

3. <span data-ttu-id="55495-362">运行： **dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="55495-362">Run: **dotnet publish**</span></span>

     <span data-ttu-id="55495-363">"输出" 窗口显示部署发布的目录。</span><span class="sxs-lookup"><span data-stu-id="55495-363">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="55495-364">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="55495-364">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

4. <span data-ttu-id="55495-365">将发布目录中的所有文件发送到 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="55495-365">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="55495-366">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="55495-366">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

5. <span data-ttu-id="55495-367">将您创建的 .zip 文件拖放到您在上面打开的 ZipDeployUI 网站上。</span><span class="sxs-lookup"><span data-stu-id="55495-367">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="55495-368">例如：https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="55495-368">For example: https://dkeservice.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="55495-369">DKE 已部署，您可以浏览到已创建的测试键。</span><span class="sxs-lookup"><span data-stu-id="55495-369">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="55495-370">继续验证下面的 [部署](#validate-your-deployment) 。</span><span class="sxs-lookup"><span data-stu-id="55495-370">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="55495-371">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="55495-371">Publish via FTP</span></span>

1. <span data-ttu-id="55495-372">连接到您在 [上面](#deploy-the-dke-service-and-publish-the-key-store)创建的应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="55495-372">Connect to the App Service you created [above](#deploy-the-dke-service-and-publish-the-key-store).</span></span>

    <span data-ttu-id="55495-373">在浏览器中，转到： **Azure portal**  >  **App Service**  >  **部署中心**  >  的**手动部署**  >  **FTP**  >  **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="55495-373">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

2. <span data-ttu-id="55495-374">将显示的连接字符串复制到本地文件。</span><span class="sxs-lookup"><span data-stu-id="55495-374">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="55495-375">您将使用这些字符串连接到 Web 应用服务，并通过 FTP 上载文件。</span><span class="sxs-lookup"><span data-stu-id="55495-375">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="55495-376">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-376">For example:</span></span>

   ![从 FTP 仪表板复制连接字符串](../media/dke-ftp-dashboard.png)

3. <span data-ttu-id="55495-378">在密钥存储的基本代码中，转到 **customer-key-store\src\customer-key-store 目录**。</span><span class="sxs-lookup"><span data-stu-id="55495-378">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

4. <span data-ttu-id="55495-379">验证此目录是否包含 **customerkeystore** 文件。</span><span class="sxs-lookup"><span data-stu-id="55495-379">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

5. <span data-ttu-id="55495-380">运行： **dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="55495-380">Run: **dotnet publish**</span></span>

    <span data-ttu-id="55495-381">输出包含部署发布的目录。</span><span class="sxs-lookup"><span data-stu-id="55495-381">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="55495-382">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="55495-382">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

6. <span data-ttu-id="55495-383">将发布目录中的所有文件发送到 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="55495-383">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="55495-384">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="55495-384">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

7. <span data-ttu-id="55495-385">从你的 FTP 客户端，使用复制的连接信息连接到应用服务。</span><span class="sxs-lookup"><span data-stu-id="55495-385">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="55495-386">将您在上一步中创建的 .zip 文件上载到 Web 应用程序的根目录。</span><span class="sxs-lookup"><span data-stu-id="55495-386">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="55495-387">DKE 已部署，您可以浏览到已创建的测试键。</span><span class="sxs-lookup"><span data-stu-id="55495-387">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="55495-388">接下来， [验证您的部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="55495-388">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="55495-389">验证部署</span><span class="sxs-lookup"><span data-stu-id="55495-389">Validate your deployment</span></span>

<span data-ttu-id="55495-390">使用上述方法之一部署 DKE 后，请验证部署和密钥存储设置。</span><span class="sxs-lookup"><span data-stu-id="55495-390">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="55495-391">以</span><span class="sxs-lookup"><span data-stu-id="55495-391">Run:</span></span>

<span data-ttu-id="55495-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span><span class="sxs-lookup"><span data-stu-id="55495-392">src\customer-key-store\scripts\key_store_tester.ps1 dkeserviceurl/mykey</span></span>

<span data-ttu-id="55495-393">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-393">For example:</span></span>

<span data-ttu-id="55495-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span><span class="sxs-lookup"><span data-stu-id="55495-394">key_store_tester.ps1 https://mydkeservice.com/mykey</span></span>

<span data-ttu-id="55495-395">确保输出中不显示任何错误。</span><span class="sxs-lookup"><span data-stu-id="55495-395">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="55495-396">准备好后， [注册你的密钥存储](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="55495-396">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="55495-397">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="55495-397">Register your key store</span></span>

<span data-ttu-id="55495-398">以下步骤使您能够注册 DKE 服务。</span><span class="sxs-lookup"><span data-stu-id="55495-398">The following steps enable you to register your DKE service.</span></span> <span data-ttu-id="55495-399">注册 DKE 服务是部署 DKE 之前的最后一步，您可以开始创建标签。</span><span class="sxs-lookup"><span data-stu-id="55495-399">Registering your DKE service is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="55495-400">注册 DKE 服务的步骤：</span><span class="sxs-lookup"><span data-stu-id="55495-400">To register the DKE service:</span></span>

1. <span data-ttu-id="55495-401">在浏览器中，打开 [Microsoft Azure 门户](https://ms.portal.azure.com/)，并转到 " **所有服务** \> **标识** \> **应用注册**"。</span><span class="sxs-lookup"><span data-stu-id="55495-401">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="55495-402">选择 " **新建注册**"，并输入有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="55495-402">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="55495-403">从显示的选项中选择一个帐户类型。</span><span class="sxs-lookup"><span data-stu-id="55495-403">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="55495-404">如果您使用的是具有非自定义域的 Microsoft Azure （如 **onmicrosoft.com**），请选择 " **仅限 Microsoft-单个租户) 中的组织目录中的帐户" (。**</span><span class="sxs-lookup"><span data-stu-id="55495-404">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="55495-405">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-405">For example:</span></span>

   ![新应用注册](../media/dke-app-registration.png)

4. <span data-ttu-id="55495-407">在页面底部，选择 " **注册** " 以创建新的应用注册。</span><span class="sxs-lookup"><span data-stu-id="55495-407">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="55495-408">在新的应用注册中，在左窗格中的 " **管理**" 下，选择 " **身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="55495-408">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="55495-409">选择 " **添加平台**"。</span><span class="sxs-lookup"><span data-stu-id="55495-409">Select **Add a platform**.</span></span>

7. <span data-ttu-id="55495-410">在 " **配置平台** " 弹出菜单上，选择 " **Web**"。</span><span class="sxs-lookup"><span data-stu-id="55495-410">On the **Configure platforms** popup, select **Web**.</span></span>

8. <span data-ttu-id="55495-411">在 " **重定向 uri**" 下，输入您的双密钥加密服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="55495-411">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="55495-412">输入应用服务 URL，包括主机名和域。</span><span class="sxs-lookup"><span data-stu-id="55495-412">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="55495-413">例如：https://mydkeservicetest.com</span><span class="sxs-lookup"><span data-stu-id="55495-413">For example: https://mydkeservicetest.com</span></span>

    - <span data-ttu-id="55495-414">输入的 URL 必须与部署 DKE 服务的主机名相匹配。</span><span class="sxs-lookup"><span data-stu-id="55495-414">The URL you enter must match the hostname where your DKE service is deployed.</span></span>
    - <span data-ttu-id="55495-415">如果您正在使用 Visual Studio 进行本地测试，请使用 **https://localhost:5001** 。</span><span class="sxs-lookup"><span data-stu-id="55495-415">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="55495-416">在所有情况下，方案都必须是 **https**。</span><span class="sxs-lookup"><span data-stu-id="55495-416">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="55495-417">确保主机名与应用服务主机名完全匹配。</span><span class="sxs-lookup"><span data-stu-id="55495-417">Ensure the hostname exactly matches your App Service hostname.</span></span> <span data-ttu-id="55495-418">您可能已将其更改为 `localhost` ，以排除生成故障。</span><span class="sxs-lookup"><span data-stu-id="55495-418">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="55495-419">在 **appsettings.js上**，此值是您为设置的主机名 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="55495-419">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

9. <span data-ttu-id="55495-420">在 " **隐式授予**" 下，选中 " **ID 令牌** " 复选框。</span><span class="sxs-lookup"><span data-stu-id="55495-420">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

10. <span data-ttu-id="55495-421">选择“**保存**”以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="55495-421">Select **Save** to save your changes.</span></span>

11. <span data-ttu-id="55495-422">在左窗格中，选择 " **公开 API**"，然后选择 "应用程序 ID URI" 旁边的 " **设置**"。</span><span class="sxs-lookup"><span data-stu-id="55495-422">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

12. <span data-ttu-id="55495-423">在 " **公开一个 API** " 页上的 " **此 Api 定义的作用域** " 中，选择 " **添加范围**"。</span><span class="sxs-lookup"><span data-stu-id="55495-423">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="55495-424">在新作用域中：</span><span class="sxs-lookup"><span data-stu-id="55495-424">In the new scope:</span></span>

    1. <span data-ttu-id="55495-425">将范围名称定义为 **user_impersonation**。</span><span class="sxs-lookup"><span data-stu-id="55495-425">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="55495-426">选择可以同意的管理员和用户。</span><span class="sxs-lookup"><span data-stu-id="55495-426">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="55495-427">定义所需的任何剩余值。</span><span class="sxs-lookup"><span data-stu-id="55495-427">Define any remaining values required.</span></span>

    4. <span data-ttu-id="55495-428">选择“添加作用域”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55495-428">Select **Add scope**.</span></span>

    5. <span data-ttu-id="55495-429">选择顶部的 " **保存** " 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="55495-429">Select **Save** at the top to save your changes.</span></span>

13. <span data-ttu-id="55495-430">仍在 " **公开 API** " 页上的 " **授权客户端应用程序** " 区域中，选择 " **添加客户端应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="55495-430">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="55495-431">在新的客户端应用程序中：</span><span class="sxs-lookup"><span data-stu-id="55495-431">In the new client application:</span></span>

    1. <span data-ttu-id="55495-432">将客户端 ID 定义为 **d3590ed6-52b3-4102-aeff-aad2292ab01c**。</span><span class="sxs-lookup"><span data-stu-id="55495-432">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="55495-433">此值是 Microsoft Office 客户端 ID，它使 Office 能够获取密钥存储的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="55495-433">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="55495-434">在 " **授权范围**" 下，选择 " **user_impersonation** " 范围。</span><span class="sxs-lookup"><span data-stu-id="55495-434">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="55495-435">选择“添加应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="55495-435">Select **Add application**.</span></span>

    4. <span data-ttu-id="55495-436">选择顶部的 " **保存** " 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="55495-436">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="55495-437">现已注册你的 DKE 服务。</span><span class="sxs-lookup"><span data-stu-id="55495-437">Your DKE service is now registered.</span></span> <span data-ttu-id="55495-438">继续操作，方法是 [使用 DKE 创建标签](#create-sensitivity-labels-using-dke)。</span><span class="sxs-lookup"><span data-stu-id="55495-438">Continue by [creating labels using DKE](#create-sensitivity-labels-using-dke).</span></span>

## <a name="create-sensitivity-labels-using-dke"></a><span data-ttu-id="55495-439">使用 DKE 创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="55495-439">Create sensitivity labels using DKE</span></span>

<span data-ttu-id="55495-440">在 Microsoft 365 合规性中心中，创建一个新的敏感度标签，并按您自己的方式应用加密。</span><span class="sxs-lookup"><span data-stu-id="55495-440">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="55495-441">选择 " **使用双密钥加密** "，并输入密钥的终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="55495-441">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="55495-442">例如：</span><span class="sxs-lookup"><span data-stu-id="55495-442">For example:</span></span>

![在 Microsoft 365 合规性中心中选择 "使用双重密钥加密"](../media/dke-use-dke.png)

<span data-ttu-id="55495-444">您添加的任何 DKE 标签将为适用于企业的 Microsoft 365 应用程序的最新版本中的用户显示。</span><span class="sxs-lookup"><span data-stu-id="55495-444">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="55495-445">客户端可能需要长达24小时才能使用新标签进行刷新。</span><span class="sxs-lookup"><span data-stu-id="55495-445">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="55495-446">在客户端中启用 DKE</span><span class="sxs-lookup"><span data-stu-id="55495-446">Enable DKE in your client</span></span>

<span data-ttu-id="55495-447">如果你是 Office 预览体验成员，则会为你启用 DKE。</span><span class="sxs-lookup"><span data-stu-id="55495-447">If you're an Office Insider, DKE is enabled for you.</span></span> <span data-ttu-id="55495-448">否则，请添加以下注册表项，为客户端启用 DKE：</span><span class="sxs-lookup"><span data-stu-id="55495-448">Otherwise, enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```

## <a name="migrate-protected-files-from-hyok-labels-to-dke-labels"></a><span data-ttu-id="55495-449">将受保护的文件从 HYOK 标签迁移到 DKE 标签</span><span class="sxs-lookup"><span data-stu-id="55495-449">Migrate protected files from HYOK labels to DKE labels</span></span>

<span data-ttu-id="55495-450">如果需要，在完成 DKE 设置后，您可以使用 HYOK 标签将受保护的内容迁移到 DKE 标签。</span><span class="sxs-lookup"><span data-stu-id="55495-450">If you want, once you're finished setting up DKE, you can migrate content that you've protected using HYOK labels to DKE labels.</span></span> <span data-ttu-id="55495-451">若要迁移，您将使用 AIP 扫描程序。</span><span class="sxs-lookup"><span data-stu-id="55495-451">To migrate, you'll use the AIP scanner.</span></span> <span data-ttu-id="55495-452">若要开始使用扫描程序，请参阅 [什么是 Azure 信息保护统一标记扫描程序？](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)。</span><span class="sxs-lookup"><span data-stu-id="55495-452">To get started using the scanner, see [What is the Azure Information Protection unified labeling scanner?](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner).</span></span>

<span data-ttu-id="55495-453">如果不迁移内容，HYOK 受保护的内容将保持不受影响。</span><span class="sxs-lookup"><span data-stu-id="55495-453">If you don't migrate content, your HYOK protected content will remain unaffected.</span></span>
