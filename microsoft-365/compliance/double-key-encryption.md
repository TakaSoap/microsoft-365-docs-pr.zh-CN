---
title: " (DKE) 的双重密钥加密"
description: DKE 使您能够保护高度敏感的数据，同时保持对密钥的完全控制。
author: kccross
ms.author: krowley
manager: laurawi
ms.date: 07/21/2020
ms.topic: conceptual
ms.service: information-protection
audience: Admin
ms.reviewer: esaggese
localization_priority: Normal
ms.collection:
- M365-security-compliance
ms.openlocfilehash: 0c66afa22c8712455a875bc8ca4ddcad1678e2e7
ms.sourcegitcommit: d39694d7b2c98350b0d568dfd03fa0ef44ed4c1d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/10/2020
ms.locfileid: "46601995"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="dad2f-103"> (DKE) 的双重密钥加密</span><span class="sxs-lookup"><span data-stu-id="dad2f-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="dad2f-104">*适用于：针对 Microsoft 365 公共预览版的双重密钥加密， [microsoft 365 合规性](https://www.microsoft.com/microsoft-365/business/compliance-management)， [Azure 信息保护](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="dad2f-104">*Applies to: Double Key Encryption for Microsoft 365 public preview, [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="dad2f-105">*说明： [Azure 信息保护统一标签客户端 For Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="dad2f-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="dad2f-106">*服务说明： [Microsoft 365 合规性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="dad2f-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="dad2f-107">双密钥加密 (DKE) 将两个键一起使用，以访问受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="dad2f-107">Double Key Encryption (DKE) uses two keys together to access protected content.</span></span> <span data-ttu-id="dad2f-108">在 Microsoft Azure 中存储一个密钥，并保留另一个密钥。</span><span class="sxs-lookup"><span data-stu-id="dad2f-108">You store one key in Microsoft Azure, and you hold the other key.</span></span> <span data-ttu-id="dad2f-109">Azure 信息保护统一标签客户端保护高度敏感的内容，同时保持对某个密钥的完全控制。</span><span class="sxs-lookup"><span data-stu-id="dad2f-109">The Azure Information Protection unified labeling client protects highly sensitive content while you maintain full control of one of your keys.</span></span>

<span data-ttu-id="dad2f-110">双密钥加密支持云和本地部署。</span><span class="sxs-lookup"><span data-stu-id="dad2f-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="dad2f-111">这些部署有助于确保在任何位置存储受保护的数据时，加密的数据保持不透明。</span><span class="sxs-lookup"><span data-stu-id="dad2f-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="dad2f-112">有关默认的基于云的租户根密钥的详细信息，请参阅[规划和实现 Azure 信息保护租户密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<!--
The following video shows how Double Key Encryption works to secure your content.

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]
-->

<span data-ttu-id="dad2f-113">如果您的组织有以下任一要求，您可以使用 DKE 帮助保护您的内容：</span><span class="sxs-lookup"><span data-stu-id="dad2f-113">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="dad2f-114">您希望确保*只有*在所有情况下都可以对受保护的内容进行解密。</span><span class="sxs-lookup"><span data-stu-id="dad2f-114">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="dad2f-115">您不希望 Microsoft 能够单独访问受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="dad2f-115">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="dad2f-116">您有管理法规要求，可在地理边界内保留密钥。</span><span class="sxs-lookup"><span data-stu-id="dad2f-116">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="dad2f-117">您为数据加密和解密而保留的所有密钥都将保留在您的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="dad2f-117">All of the keys that you hold for data encryption and decryption are maintained in your data center.</span></span>

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="dad2f-118">DKE 的系统和许可要求</span><span class="sxs-lookup"><span data-stu-id="dad2f-118">System and licensing requirements for DKE</span></span>

<span data-ttu-id="dad2f-119">Microsoft 365 E5 和 Office 365 E5 提供了适用于 Microsoft 365 的双重密钥加密。</span><span class="sxs-lookup"><span data-stu-id="dad2f-119">Double Key Encryption for Microsoft 365 comes with Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="dad2f-120">如果你没有 Microsoft 365 E5 许可证，你可以注册[试用版](https://aka.ms/M365E5ComplianceTrial)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-120">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="dad2f-121">有关这些许可证的详细信息，请参阅[适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-121">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="dad2f-122">**Office 预览体验成员**若要使用公共预览版，您必须是 Office 预览体验成员计划的成员。</span><span class="sxs-lookup"><span data-stu-id="dad2f-122">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="dad2f-123">若要加入 Office 预览体验成员，请转到 [https://insider.office.com](https://insider.office.com) 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-123">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="dad2f-124">一旦成为你的成员，请为你的组织选择正确的部署方法，准备环境以部署 Office 有问必答版内部版本。</span><span class="sxs-lookup"><span data-stu-id="dad2f-124">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="dad2f-125">有关说明，请参阅[部署 Office 预览体验成员内部版本](https://insider.office.com/business/deploy)入门。</span><span class="sxs-lookup"><span data-stu-id="dad2f-125">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="dad2f-126">**Azure 信息保护**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-126">**Azure Information Protection**.</span></span> <span data-ttu-id="dad2f-127">DKE 使用灵敏度标签，需要 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="dad2f-127">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="dad2f-128">用于存储和查看受 DKE 保护的内容的受支持的环境</span><span class="sxs-lookup"><span data-stu-id="dad2f-128">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="dad2f-129">**支持的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-129">**Supported applications**.</span></span> <span data-ttu-id="dad2f-130">Windows 上[的适用于企业客户端的 Microsoft 365 应用程序](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)，包括 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="dad2f-130">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="dad2f-131">**在线内容支持**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-131">**Online content support**.</span></span> <span data-ttu-id="dad2f-132">支持在 Microsoft SharePoint 和 OneDrive for Business 中联机存储的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-132">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="dad2f-133">您可以通过电子邮件共享加密内容，但不能联机查看加密的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-133">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="dad2f-134">相反，您必须使用本地计算机上的桌面应用程序查看受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="dad2f-134">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="dad2f-135">关于此公共预览版文章</span><span class="sxs-lookup"><span data-stu-id="dad2f-135">About this public preview article</span></span>

<span data-ttu-id="dad2f-136">有几种方法可以完成一些部署双密钥加密的步骤。</span><span class="sxs-lookup"><span data-stu-id="dad2f-136">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="dad2f-137">本文提供了详细说明，以便让经验较少的管理员能够成功部署服务。</span><span class="sxs-lookup"><span data-stu-id="dad2f-137">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="dad2f-138">如果你愿意，可以选择使用自己的方法。</span><span class="sxs-lookup"><span data-stu-id="dad2f-138">If you're comfortable doing so, you can choose to use your own methods.</span></span>

<span data-ttu-id="dad2f-139">本文包含有关如何将双重密钥加密服务部署到 Azure 的分步说明。</span><span class="sxs-lookup"><span data-stu-id="dad2f-139">This article includes step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="dad2f-140">此方案不是您在生产中可能要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="dad2f-140">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="dad2f-141">对于公共预览版，使用 Azure 是部署 DKE 的快速方法。</span><span class="sxs-lookup"><span data-stu-id="dad2f-141">For public preview, using Azure is a quick way to deploy DKE.</span></span> <span data-ttu-id="dad2f-142">通过将部署到 Azure，你可以立即开始使用双密钥加密。</span><span class="sxs-lookup"><span data-stu-id="dad2f-142">Deploying to Azure lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="dad2f-143">可以在网络上本地或使用其他提供程序部署该服务。</span><span class="sxs-lookup"><span data-stu-id="dad2f-143">You can deploy the service locally on your network or with another provider.</span></span> <span data-ttu-id="dad2f-144">您需要使用适合于该位置的方法发布密钥存储。</span><span class="sxs-lookup"><span data-stu-id="dad2f-144">You'll need to publish the key store using methods that are appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="dad2f-145">部署双密钥加密</span><span class="sxs-lookup"><span data-stu-id="dad2f-145">Deploy Double Key Encryption</span></span>

<span data-ttu-id="dad2f-146">本文和部署视频使用 Azure 作为 DKE 服务的部署目标。</span><span class="sxs-lookup"><span data-stu-id="dad2f-146">This article and the deployment video use Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="dad2f-147">如果要部署到其他位置，则需要提供自己的值。</span><span class="sxs-lookup"><span data-stu-id="dad2f-147">If you're deploying to another location, you'll need to provide your own values.</span></span>

<span data-ttu-id="dad2f-148">观看 "[双重密钥加密部署" 视频](https://youtu.be/vDWfHN_kygg)，以查看本文中概念的分步概述。</span><span class="sxs-lookup"><span data-stu-id="dad2f-148">Watch the [Double Key Encryption deployment video](https://youtu.be/vDWfHN_kygg) to see step-by-step overview of concepts in the article.</span></span> <span data-ttu-id="dad2f-149">完成该视频需要18分钟左右。</span><span class="sxs-lookup"><span data-stu-id="dad2f-149">The video takes about 18 minutes to complete.</span></span>

<span data-ttu-id="dad2f-150">您将按照这些常规步骤为您的组织设置双密钥加密。</span><span class="sxs-lookup"><span data-stu-id="dad2f-150">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span>

1. [<span data-ttu-id="dad2f-151">安装必备软件</span><span class="sxs-lookup"><span data-stu-id="dad2f-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="dad2f-152">克隆双密钥加密 GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="dad2f-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="dad2f-153">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="dad2f-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="dad2f-154">生成测试键</span><span class="sxs-lookup"><span data-stu-id="dad2f-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="dad2f-155">生成项目</span><span class="sxs-lookup"><span data-stu-id="dad2f-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="dad2f-156">发布密钥存储</span><span class="sxs-lookup"><span data-stu-id="dad2f-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="dad2f-157">验证部署</span><span class="sxs-lookup"><span data-stu-id="dad2f-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="dad2f-158">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="dad2f-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="dad2f-159">创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="dad2f-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="dad2f-160">完成后，您可以使用 DKE 对文档和文件进行加密。</span><span class="sxs-lookup"><span data-stu-id="dad2f-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="dad2f-161">有关信息，请参阅[将敏感度标签应用于 Office 中的文件和电子邮件](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="dad2f-162">安装必备软件</span><span class="sxs-lookup"><span data-stu-id="dad2f-162">Install software prerequisites</span></span>

<span data-ttu-id="dad2f-163">双密钥加密有两种类型的软件先决条件</span><span class="sxs-lookup"><span data-stu-id="dad2f-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="dad2f-164">双密钥加密服务先决条件</span><span class="sxs-lookup"><span data-stu-id="dad2f-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="dad2f-165">客户端计算机的双密钥加密先决条件</span><span class="sxs-lookup"><span data-stu-id="dad2f-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="dad2f-166">双密钥加密服务先决条件</span><span class="sxs-lookup"><span data-stu-id="dad2f-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="dad2f-167">在要安装 DKE 服务的计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="dad2f-168">**.Net Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="dad2f-169">从[下载 .Net Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)下载并安装 SDK。</span><span class="sxs-lookup"><span data-stu-id="dad2f-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="dad2f-170">**Visual Studio Code**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-170">**Visual Studio Code**.</span></span> <span data-ttu-id="dad2f-171">从下载 Visual Studio Code [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="dad2f-172">安装完成后，运行 Visual Studio Code 并选择 "**查看** \> **扩展**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="dad2f-173">安装这些扩展。</span><span class="sxs-lookup"><span data-stu-id="dad2f-173">Install these extensions.</span></span>

- <span data-ttu-id="dad2f-174">Visual Studio Code 的 c #</span><span class="sxs-lookup"><span data-stu-id="dad2f-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="dad2f-175">NuGet 包管理器</span><span class="sxs-lookup"><span data-stu-id="dad2f-175">NuGet Package Manager</span></span>

<span data-ttu-id="dad2f-176">**Microsoft Office 预览体验成员**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="dad2f-177">设置至少一个[部署方法](https://insider.office.com/business/deploy)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="dad2f-178">**Git 资源**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-178">**Git resources**.</span></span> <span data-ttu-id="dad2f-179">下载并安装以下各项之一。</span><span class="sxs-lookup"><span data-stu-id="dad2f-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="dad2f-180">Git</span><span class="sxs-lookup"><span data-stu-id="dad2f-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="dad2f-181">GitHub 桌面</span><span class="sxs-lookup"><span data-stu-id="dad2f-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="dad2f-182">GitHub 企业</span><span class="sxs-lookup"><span data-stu-id="dad2f-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="dad2f-183">**OpenSSL**您必须安装了[OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) ，才能在部署 DKE 后[生成测试密钥](#generate-test-keys)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="dad2f-184">请确保您从环境变量路径中正确调用了它。</span><span class="sxs-lookup"><span data-stu-id="dad2f-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="dad2f-185">例如，有关详细信息，请参阅 "将安装目录添加到路径" https://www.osradar.com/install-openssl-windows/ 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="dad2f-186">客户端计算机的双密钥加密先决条件</span><span class="sxs-lookup"><span data-stu-id="dad2f-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="dad2f-187">在要保护和使用受保护文档的每台客户端计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="dad2f-188">**Microsoft Office** 12711 版或更高版本。</span><span class="sxs-lookup"><span data-stu-id="dad2f-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="dad2f-189">**Azure 信息保护统一标签客户端**版本2.7.93.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="dad2f-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="dad2f-190">从[Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)下载并安装统一的标记客户端。</span><span class="sxs-lookup"><span data-stu-id="dad2f-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="dad2f-191">克隆 DKE GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="dad2f-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="dad2f-192">Microsoft 提供 GitHub 存储库中的 DKE 源文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="dad2f-193">克隆存储库，以在本地为组织的使用生成项目。</span><span class="sxs-lookup"><span data-stu-id="dad2f-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="dad2f-194">DKE GitHub 存储库位于 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="dad2f-195">以下说明适用于缺乏的 git 或 Visual Studio Code users：</span><span class="sxs-lookup"><span data-stu-id="dad2f-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="dad2f-196">在浏览器中，转到：[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="dad2f-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="dad2f-197">在屏幕右侧，选择 "**代码**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="dad2f-198">您的 UI 版本可能会显示 "**克隆" 或 "下载**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="dad2f-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="dad2f-199">然后，在出现的下拉列表中，选择 "复制" 图标将 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="dad2f-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="dad2f-200">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-200">For example:</span></span>

   ![从 GitHub 克隆双密钥加密服务存储库](../media/dke-clone.png)

3. <span data-ttu-id="dad2f-202">在 Visual Studio Code 中，选择 "**查看** \> **命令选项板**"，然后选择 " **Git： Clone**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="dad2f-203">若要跳转到列表中的选项，请开始键入 `git: clone` 以筛选条目，然后从下拉列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="dad2f-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="dad2f-204">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-204">For example:</span></span>

   ![Visual Studio Code GIT： Clone 选项](../media/dke-vscode-clone.png)

4. <span data-ttu-id="dad2f-206">在文本框中，粘贴从 Git 复制的 URL，然后**从 GitHub 中**选择 "复制"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="dad2f-207">在出现的 "**选择文件夹**" 对话框中，浏览并选择存储库的位置。</span><span class="sxs-lookup"><span data-stu-id="dad2f-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="dad2f-208">在提示符下，选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="dad2f-209">存储库在 Visual Studio Code 中打开，并在左下角显示当前 Git 分支。</span><span class="sxs-lookup"><span data-stu-id="dad2f-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="dad2f-210">分支应为**master**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-210">The branch should be **master**.</span></span>

    <span data-ttu-id="dad2f-211">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-211">For example:</span></span>

   ![Visual Studio Code master 分支](../media/dke-vscode-master.png)

6. <span data-ttu-id="dad2f-213">选择 "word**母版"，** 然后从分支列表中选择 " **public_preview** "。</span><span class="sxs-lookup"><span data-stu-id="dad2f-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span>

   > [!IMPORTANT]
   > <span data-ttu-id="dad2f-214">选择 "public_preview" 分支可确保您具有用于生成项目的正确文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="dad2f-215">如果不选择正确的分支，部署将会失败。</span><span class="sxs-lookup"><span data-stu-id="dad2f-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="dad2f-216">现在，你已在本地设置了 DKE 源存储库。</span><span class="sxs-lookup"><span data-stu-id="dad2f-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="dad2f-217">接下来，修改您的组织的[应用程序设置](#modify-application-settings)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="dad2f-218">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="dad2f-218">Modify application settings</span></span>

<span data-ttu-id="dad2f-219">若要部署 DKE 服务，必须修改以下类型的应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="dad2f-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="dad2f-220">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="dad2f-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="dad2f-221">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="dad2f-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="dad2f-222">您可以在 appsettings.js的文件中修改应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="dad2f-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="dad2f-223">此文件位于本地克隆的 DoubleKeyEncryptionService 存储库中的 DoubleKeyEncryptionService\src\customer-key-store。</span><span class="sxs-lookup"><span data-stu-id="dad2f-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="dad2f-224">例如，在 Visual Studio Code 中，可以按下图所示浏览到文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

![为 DKE 查找文件上的 appsettings.js。](../media/dke-appsettingsjson.png)

#### <a name="key-access-settings"></a><span data-ttu-id="dad2f-226">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="dad2f-226">Key access settings</span></span>

<span data-ttu-id="dad2f-227">选择是否使用电子邮件或角色授权。</span><span class="sxs-lookup"><span data-stu-id="dad2f-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="dad2f-228">DKE 一次仅支持其中一种身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="dad2f-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="dad2f-229">**电子邮件授权**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-229">**Email authorization**.</span></span> <span data-ttu-id="dad2f-230">允许您的组织仅基于电子邮件地址授权访问密钥。</span><span class="sxs-lookup"><span data-stu-id="dad2f-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="dad2f-231">**角色授权**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-231">**Role authorization**.</span></span> <span data-ttu-id="dad2f-232">允许您的组织根据 Active Directory 组授权对密钥的访问，并要求 web 服务可以查询 LDAP。</span><span class="sxs-lookup"><span data-stu-id="dad2f-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="dad2f-233">**使用电子邮件授权设置 DKE 的密钥访问设置**</span><span class="sxs-lookup"><span data-stu-id="dad2f-233">**To set key access settings for DKE using email authorization**</span></span>

1. <span data-ttu-id="dad2f-234">打开文件**上**的 "appsettings.js" 并找到相应的 `AuthorizedEmailAddress` 设置。</span><span class="sxs-lookup"><span data-stu-id="dad2f-234">Open the **appsettings.json** file and locate the `AuthorizedEmailAddress` setting.</span></span>

2. <span data-ttu-id="dad2f-235">添加要授权的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dad2f-235">Add the email address or addresses that you want to authorize.</span></span> <span data-ttu-id="dad2f-236">用双引号和逗号分隔多个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="dad2f-236">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="dad2f-237">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-237">For example:</span></span>

   ```json
   "AuthorizedEmailAddress": ["email1@company.com", "email2@company.com ", "email3@company.com"]
   ```

3. <span data-ttu-id="dad2f-238">找到 `LDAPPath` 设置并删除 `If role authorization is used then this is the LDAP path` 双引号之间的文本。</span><span class="sxs-lookup"><span data-stu-id="dad2f-238">Locate the `LDAPPath` setting and remove the text `If role authorization is used then this is the LDAP path` between the double quotes.</span></span> <span data-ttu-id="dad2f-239">将双引号括起来。</span><span class="sxs-lookup"><span data-stu-id="dad2f-239">Leave the double quotes in place.</span></span> <span data-ttu-id="dad2f-240">完成后，设置应如下所示。</span><span class="sxs-lookup"><span data-stu-id="dad2f-240">When you're finished, the setting should look like this.</span></span>

   ```json
   "LDAPPath": ""
   ```

4. <span data-ttu-id="dad2f-241">找到 `AuthorizedRoles` 设置并删除整行。</span><span class="sxs-lookup"><span data-stu-id="dad2f-241">Locate the `AuthorizedRoles` setting and delete the entire line.</span></span>

<span data-ttu-id="dad2f-242">此图显示了为电子邮件授权正确设置格式的文件**上的appsettings.js** 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-242">This image shows the **appsettings.json** file correctly formatted for email authorization.</span></span>

   ![对文件显示电子邮件授权方法的 appsettings.js](../media/dke-email-accesssetting.png)

<span data-ttu-id="dad2f-244">**使用角色授权设置 DKE 的密钥访问设置**</span><span class="sxs-lookup"><span data-stu-id="dad2f-244">**To set key access settings for DKE using role authorization**</span></span>

1. <span data-ttu-id="dad2f-245">打开文件**上**的 "appsettings.js" 并找到相应的 `AuthorizedRoles` 设置。</span><span class="sxs-lookup"><span data-stu-id="dad2f-245">Open the **appsettings.json** file and locate the `AuthorizedRoles` setting.</span></span>

2. <span data-ttu-id="dad2f-246">添加要授权的 Active Directory 组名称。</span><span class="sxs-lookup"><span data-stu-id="dad2f-246">Add the Active Directory group names you want to authorize.</span></span> <span data-ttu-id="dad2f-247">用双引号和逗号分隔多个组名称。</span><span class="sxs-lookup"><span data-stu-id="dad2f-247">Separate multiple group names with double quotes and commas.</span></span> <span data-ttu-id="dad2f-248">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-248">For example:</span></span>

   ```json
   "AuthorizedRoles": ["group1", "group2", "group3"]
   ```

3. <span data-ttu-id="dad2f-249">找到 `LDAPPath` 设置并添加 Active Directory 域。</span><span class="sxs-lookup"><span data-stu-id="dad2f-249">Locate the `LDAPPath` setting and add the Active Directory domain.</span></span> <span data-ttu-id="dad2f-250">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-250">For example:</span></span>

   ```json
   "LDAPPath": "contoso.com"
   ```

4. <span data-ttu-id="dad2f-251">找到 `AuthorizedEmailAddress` 设置并删除整行。</span><span class="sxs-lookup"><span data-stu-id="dad2f-251">Locate the `AuthorizedEmailAddress` setting and delete the entire line.</span></span>

<span data-ttu-id="dad2f-252">此图显示了为角色授权正确设置文件格式的**appsettings.js** 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-252">This image shows the **appsettings.json** file correctly formatted for role authorization.</span></span>

   ![对显示角色授权方法的文件 appsettings.js](../media/dke-role-accesssetting.png)

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="dad2f-254">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="dad2f-254">Tenant and key settings</span></span>

<span data-ttu-id="dad2f-255">DKE 租户和关键设置位于 " **appsettings.js"** 文件中。</span><span class="sxs-lookup"><span data-stu-id="dad2f-255">DKE tenant and key settings are located in the **appsettings.json** file.</span></span>

<span data-ttu-id="dad2f-256">**为 DKE 配置租户和密钥设置**</span><span class="sxs-lookup"><span data-stu-id="dad2f-256">**To configure tenant and key settings for DKE**</span></span>

1. <span data-ttu-id="dad2f-257">打开文件**上**的 "appsettings.js"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-257">Open the **appsettings.json** file.</span></span>

2. <span data-ttu-id="dad2f-258">找到 `ValidIssuers` 设置并 `<tenantid>` 将其替换为你的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="dad2f-258">Locate the `ValidIssuers` setting and replace `<tenantid>` with your tenant ID.</span></span> <span data-ttu-id="dad2f-259">你可以转到 Azure 门户并查看[租户属性](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties)，以找到你的租户 ID。</span><span class="sxs-lookup"><span data-stu-id="dad2f-259">You can locate your tenant ID by going to the Azure portal and viewing the [tenant properties](https://aad.portal.azure.com/#blade/Microsoft_AAD_IAM/ActiveDirectoryMenuBlade/Properties).</span></span> <span data-ttu-id="dad2f-260">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-260">For example:</span></span>

   ```json
   "ValidIssuers": [
     "https://sts.windows.net/9c99431e-b513-44be-a7d9-e7b500002d4b/"
   ]
   ```

<span data-ttu-id="dad2f-261">找到 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-261">Locate the `JwtAudience`.</span></span> <span data-ttu-id="dad2f-262">`<yourhostname>`将替换为将运行 DKE 服务的计算机的主机名。</span><span class="sxs-lookup"><span data-stu-id="dad2f-262">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span> <span data-ttu-id="dad2f-263">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-263">For example:</span></span>



  > [!IMPORTANT]
  > <span data-ttu-id="dad2f-264">的值 `JwtAudience` 必须与您的主机的名称*完全*匹配。</span><span class="sxs-lookup"><span data-stu-id="dad2f-264">The value for `JwtAudience` must match the name of your host *exactly*.</span></span> <span data-ttu-id="dad2f-265">在调试时，您可以使用**localhost： 5001** 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-265">You may use **localhost:5001** while debugging.</span></span> <span data-ttu-id="dad2f-266">但是，在完成调试后，请务必将此值更新到服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="dad2f-266">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="dad2f-267">`TestKeys:Name`.</span><span class="sxs-lookup"><span data-stu-id="dad2f-267">`TestKeys:Name`.</span></span> <span data-ttu-id="dad2f-268">输入密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="dad2f-268">Enter a name for your key.</span></span> <span data-ttu-id="dad2f-269">例如：`TestKey1`</span><span class="sxs-lookup"><span data-stu-id="dad2f-269">For example: `TestKey1`</span></span>
- <span data-ttu-id="dad2f-270">`TestKeys:Id`.</span><span class="sxs-lookup"><span data-stu-id="dad2f-270">`TestKeys:Id`.</span></span> <span data-ttu-id="dad2f-271">创建一个 GUID 并输入它作为 `TestKeys:ID` 值。</span><span class="sxs-lookup"><span data-stu-id="dad2f-271">Create a GUID and enter it as the `TestKeys:ID` value.</span></span> <span data-ttu-id="dad2f-272">例如，`DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`。</span><span class="sxs-lookup"><span data-stu-id="dad2f-272">For example, `DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE`.</span></span> <span data-ttu-id="dad2f-273">您可以使用[联机 Guid 生成器](https://guidgenerator.com/)等网站随机生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="dad2f-273">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

<span data-ttu-id="dad2f-274">此图像显示**appsettings.js上**的租户和密钥设置的正确格式。</span><span class="sxs-lookup"><span data-stu-id="dad2f-274">This image shows the correct format for tenant and keys settings in **appsettings.json**.</span></span> <span data-ttu-id="dad2f-275">`LDAPPath`配置了角色授权。</span><span class="sxs-lookup"><span data-stu-id="dad2f-275">`LDAPPath` is configured for role authorization.</span></span>

![在 appsettings.js的文件中显示 DKE 的正确租户和密钥设置。](../media/dke-appsettingsjson-tenantkeysettings.png)

### <a name="generate-test-keys"></a><span data-ttu-id="dad2f-277">生成测试键</span><span class="sxs-lookup"><span data-stu-id="dad2f-277">Generate test keys</span></span>

<span data-ttu-id="dad2f-278">定义应用程序设置后，即可生成公用和专用测试密钥。</span><span class="sxs-lookup"><span data-stu-id="dad2f-278">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="dad2f-279">生成密钥：</span><span class="sxs-lookup"><span data-stu-id="dad2f-279">To generate keys:</span></span>

1. <span data-ttu-id="dad2f-280">从 Windows "开始" 菜单中，运行 OpenSSL 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="dad2f-280">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="dad2f-281">转到要在其中保存测试密钥的文件夹。</span><span class="sxs-lookup"><span data-stu-id="dad2f-281">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="dad2f-282">您通过完成此任务中的步骤创建的文件存储在同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="dad2f-282">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="dad2f-283">生成新的测试密钥。</span><span class="sxs-lookup"><span data-stu-id="dad2f-283">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="dad2f-284">生成私钥。</span><span class="sxs-lookup"><span data-stu-id="dad2f-284">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="dad2f-285">生成公钥。</span><span class="sxs-lookup"><span data-stu-id="dad2f-285">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="dad2f-286">在文本编辑器中，打开 " **pubkeyonly**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-286">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="dad2f-287">将**pubkeyonly**文件中除第一行和最后一行之外的所有内容复制到 `PublicPem` "文件中的**appsettings.js** " 部分。</span><span class="sxs-lookup"><span data-stu-id="dad2f-287">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the `PublicPem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="dad2f-288">在文本编辑器中，打开 " **privkeynopass**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-288">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="dad2f-289">将**privkeynopass**文件中除第一行和最后一行之外的所有内容复制到 `PrivatePem` "文件中的**appsettings.js** " 部分。</span><span class="sxs-lookup"><span data-stu-id="dad2f-289">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the `PrivatePem` section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="dad2f-290">删除和部分中的所有空格和换行符 `PublicPem` `PrivatePem` 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-290">Remove all blank spaces and newlines in both the `PublicPem` and `PrivatePem` sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="dad2f-291">复制此内容时，请不要删除任何 PEM 数据。</span><span class="sxs-lookup"><span data-stu-id="dad2f-291">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="dad2f-292">在 Visual Studio Code 中，浏览到**Startup.cs**文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-292">In Visual Studio Code, browse to the **Startup.cs** file.</span></span> <span data-ttu-id="dad2f-293">此文件位于本地克隆的 DoubleKeyEncryptionService 存储库中的 DoubleKeyEncryptionService\src\customer-key-store\。</span><span class="sxs-lookup"><span data-stu-id="dad2f-293">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store\.</span></span>

2. <span data-ttu-id="dad2f-294">找到以下行：</span><span class="sxs-lookup"><span data-stu-id="dad2f-294">Locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

3. <span data-ttu-id="dad2f-295">将这些行替换为以下文本：</span><span class="sxs-lookup"><span data-stu-id="dad2f-295">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="dad2f-296">最终结果应如下所示。</span><span class="sxs-lookup"><span data-stu-id="dad2f-296">The end results should look similar to the following.</span></span>

   ![用于公共预览的 startup.cs 文件](../media/dke-startupcs-usetestkeys.png)

<span data-ttu-id="dad2f-298">现在，你已准备好[生成 DKE 项目](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-298">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="dad2f-299">生成项目</span><span class="sxs-lookup"><span data-stu-id="dad2f-299">Build the project</span></span>

<span data-ttu-id="dad2f-300">使用以下说明在本地生成 DKE 项目：</span><span class="sxs-lookup"><span data-stu-id="dad2f-300">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="dad2f-301">在 Visual Studio Code 中，在 DKE 服务存储库中，选择 "**查看** \> **命令组件面板**"，然后在提示符处键入**build** 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-301">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="dad2f-302">从列表中选择 "**任务：运行生成任务**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-302">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="dad2f-303">如果找不到任何生成任务，请选择 "**配置生成任务**并为 .net core 创建一个"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="dad2f-303">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   ![为 .NET 配置缺少的生成任务](../media/dke-configurebuildtask.png)

   1. <span data-ttu-id="dad2f-305">**从模板中选择 "创建 tasks.js"**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-305">Choose **Create tasks.json from template**.</span></span>

   ![从 DKE 的模板创建对文件的 tasks.js](../media/dke-createtasksjsonfromtemplate.png)

   2. <span data-ttu-id="dad2f-307">从模板类型列表中，选择 " **.Net Core**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-307">From the list of template types, select **.NET Core**.</span></span>

   ![从 DKE 的模板创建对文件的 tasks.js](../media/dke-tasksjsontemplate.png)

   3. <span data-ttu-id="dad2f-309">在 "生成" 部分，找到**customerkeystore**文件的路径。</span><span class="sxs-lookup"><span data-stu-id="dad2f-309">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="dad2f-310">如果没有，则添加以下行：</span><span class="sxs-lookup"><span data-stu-id="dad2f-310">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="dad2f-311">再次运行生成。</span><span class="sxs-lookup"><span data-stu-id="dad2f-311">Run the build again.</span></span>

1. <span data-ttu-id="dad2f-312">确认输出窗口中没有红色错误。</span><span class="sxs-lookup"><span data-stu-id="dad2f-312">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="dad2f-313">如果出现红色错误，请检查控制台输出。</span><span class="sxs-lookup"><span data-stu-id="dad2f-313">If there are red errors, check the console output.</span></span> <span data-ttu-id="dad2f-314">确保您已正确完成上述所有步骤，并且存在正确的生成版本。</span><span class="sxs-lookup"><span data-stu-id="dad2f-314">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

2. <span data-ttu-id="dad2f-315">选择 "**运行** \> **启动调试**" 以调试进程。</span><span class="sxs-lookup"><span data-stu-id="dad2f-315">Select **Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="dad2f-316">如果系统提示您选择环境，请选择 " **.net core**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-316">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="dad2f-317">.Net core 调试器通常会启动到 "'" https://localhost:5001 `. To view your test key, go to ` https://localhost:5001 ，并向其追加一个正斜杠 (/) 和键的名称。</span><span class="sxs-lookup"><span data-stu-id="dad2f-317">The .NET core debugger typically launches to \`\`https://localhost:5001`. To view your test key, go to `https://localhost:5001\` and append a forward slash (/) and the name of your key.</span></span> <span data-ttu-id="dad2f-318">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-318">For example:</span></span>

```https
https://localhost:5001/TestKey1
```

<span data-ttu-id="dad2f-319">该项应以 JSON 格式显示。</span><span class="sxs-lookup"><span data-stu-id="dad2f-319">The key should display in JSON format.</span></span>

<span data-ttu-id="dad2f-320">你的设置现已完成。</span><span class="sxs-lookup"><span data-stu-id="dad2f-320">Your setup is now complete.</span></span> <span data-ttu-id="dad2f-321">在发布密钥库之前，在 appsettings.js的 JwtAudience 设置中，确保主机名的值与您的应用程序服务主机名称完全匹配。</span><span class="sxs-lookup"><span data-stu-id="dad2f-321">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="dad2f-322">您可能已将其更改为 localhost 以对生成进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="dad2f-322">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="dad2f-323">发布密钥存储</span><span class="sxs-lookup"><span data-stu-id="dad2f-323">Publish the key store</span></span>

<span data-ttu-id="dad2f-324">若要发布密钥存储，您将创建一个 Azure 应用服务实例以托管您的 DKE 部署。</span><span class="sxs-lookup"><span data-stu-id="dad2f-324">To publish the key store, you'll create an Azure App Service instance to host your DKE deployment.</span></span> <span data-ttu-id="dad2f-325">接下来，你将生成的密钥发布到 Azure。</span><span class="sxs-lookup"><span data-stu-id="dad2f-325">Next, you'll publish your generated keys to Azure.</span></span>

<span data-ttu-id="dad2f-326">**创建 Azure Web 应用程序实例以托管你的 DKE 部署**</span><span class="sxs-lookup"><span data-stu-id="dad2f-326">**To create an Azure Web App instance to host your DKE deployment**</span></span>

1. <span data-ttu-id="dad2f-327">在浏览器中，登录到[Microsoft Azure 门户](https://ms.portal.azure.com)，然后转到 "**应用程序服务**" "  >  **添加**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-327">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="dad2f-328">选择订阅和资源组，并定义实例详细信息。</span><span class="sxs-lookup"><span data-stu-id="dad2f-328">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="dad2f-329">输入要安装 DKE 服务的计算机的主机名。</span><span class="sxs-lookup"><span data-stu-id="dad2f-329">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="dad2f-330">请确保它与在[**appsettings.json**](#tenant-and-key-settings) file 中为 JwtAudience 设置定义的名称相同。</span><span class="sxs-lookup"><span data-stu-id="dad2f-330">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="dad2f-331">您为名称提供的值也是 WebAppInstanceName。</span><span class="sxs-lookup"><span data-stu-id="dad2f-331">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="dad2f-332">对于 "**发布**"、"选择**代码**" 和 "**运行时堆栈**"，选择 " **.net Core 3.1**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-332">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="dad2f-333">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-333">For example:</span></span>

   ![添加应用服务](../media/dke-azure-add-app-service.png)

1. <span data-ttu-id="dad2f-335">在页面底部，选择 "**审阅 + 创建**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-335">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="dad2f-336">执行以下操作之一，将生成的密钥发布到 Azure：</span><span class="sxs-lookup"><span data-stu-id="dad2f-336">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="dad2f-337">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="dad2f-337">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="dad2f-338">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="dad2f-338">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="dad2f-339">通过 Visual Studio 2019 或更高版本发布</span><span class="sxs-lookup"><span data-stu-id="dad2f-339">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="dad2f-340">发布到本地系统</span><span class="sxs-lookup"><span data-stu-id="dad2f-340">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="dad2f-341">您可能更喜欢部署密钥的其他方法。</span><span class="sxs-lookup"><span data-stu-id="dad2f-341">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="dad2f-342">选择最适合您的组织的方法。</span><span class="sxs-lookup"><span data-stu-id="dad2f-342">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="dad2f-343">[ASP .net 文档](https://docs.microsoft.com/aspnet/core/)中介绍了如何[通过 Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/)和[本地系统](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)发布。</span><span class="sxs-lookup"><span data-stu-id="dad2f-343">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="dad2f-344">如果使用其中一种方法，请在单独的选项卡中打开说明，以便在完成后可以轻松地返回此处。</span><span class="sxs-lookup"><span data-stu-id="dad2f-344">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="dad2f-345">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="dad2f-345">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="dad2f-346">转到 `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`。</span><span class="sxs-lookup"><span data-stu-id="dad2f-346">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="dad2f-347">例如：https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="dad2f-347">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="dad2f-348">在密钥存储的基本代码中，转到 " **customer-key-store\src\customer-key-store** " 文件夹，并验证此文件夹是否包含**customerkeystore**文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-348">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="dad2f-349">运行： **dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="dad2f-349">Run: **dotnet publish**</span></span>

     <span data-ttu-id="dad2f-350">"输出" 窗口显示部署发布的目录。</span><span class="sxs-lookup"><span data-stu-id="dad2f-350">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="dad2f-351">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="dad2f-351">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="dad2f-352">将发布目录中的所有文件发送到 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-352">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="dad2f-353">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="dad2f-353">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="dad2f-354">将您创建的 .zip 文件拖放到您在上面打开的 ZipDeployUI 网站上。</span><span class="sxs-lookup"><span data-stu-id="dad2f-354">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="dad2f-355">例如：https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="dad2f-355">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="dad2f-356">DKE 已部署，您可以浏览到已创建的测试键。</span><span class="sxs-lookup"><span data-stu-id="dad2f-356">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="dad2f-357">继续验证下面的[部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-357">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="dad2f-358">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="dad2f-358">Publish via FTP</span></span>

1. <span data-ttu-id="dad2f-359">连接到您在[上面](#publish-the-key-store)创建的应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="dad2f-359">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="dad2f-360">在浏览器中，转到： **Azure portal**  >  **App Service**  >  **部署中心**  >  的**手动部署**  >  **FTP**  >  **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-360">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="dad2f-361">将显示的连接字符串复制到本地文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-361">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="dad2f-362">您将使用这些字符串连接到 Web 应用服务，并通过 FTP 上载文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-362">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="dad2f-363">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-363">For example:</span></span>

   ![从 FTP 仪表板复制连接字符串](../media/dke-ftp-dashboard.png)

1. <span data-ttu-id="dad2f-365">在密钥存储的基本代码中，转到**customer-key-store\src\customer-key-store 目录**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-365">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="dad2f-366">验证此目录是否包含**customerkeystore**文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-366">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="dad2f-367">运行： **dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="dad2f-367">Run: **dotnet publish**</span></span>

    <span data-ttu-id="dad2f-368">输出包含部署发布的目录。</span><span class="sxs-lookup"><span data-stu-id="dad2f-368">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="dad2f-369">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="dad2f-369">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="dad2f-370">将发布目录中的所有文件发送到 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="dad2f-370">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="dad2f-371">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="dad2f-371">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="dad2f-372">从你的 FTP 客户端，使用复制的连接信息连接到应用服务。</span><span class="sxs-lookup"><span data-stu-id="dad2f-372">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="dad2f-373">将您在上一步中创建的 .zip 文件上载到 Web 应用程序的根目录。</span><span class="sxs-lookup"><span data-stu-id="dad2f-373">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="dad2f-374">DKE 已部署，您可以浏览到已创建的测试键。</span><span class="sxs-lookup"><span data-stu-id="dad2f-374">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="dad2f-375">接下来，[验证您的部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-375">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="dad2f-376">验证部署</span><span class="sxs-lookup"><span data-stu-id="dad2f-376">Validate your deployment</span></span>

<span data-ttu-id="dad2f-377">使用上述方法之一部署 DKE 后，请验证部署和密钥存储设置。</span><span class="sxs-lookup"><span data-stu-id="dad2f-377">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="dad2f-378">运行：</span><span class="sxs-lookup"><span data-stu-id="dad2f-378">Run:</span></span>

<span data-ttu-id="dad2f-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span><span class="sxs-lookup"><span data-stu-id="dad2f-379">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="dad2f-380">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-380">For example:</span></span>

<span data-ttu-id="dad2f-381">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="dad2f-381">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="dad2f-382">确保输出中不显示任何错误。</span><span class="sxs-lookup"><span data-stu-id="dad2f-382">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="dad2f-383">准备好后，[注册你的密钥存储](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-383">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="dad2f-384">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="dad2f-384">Register your key store</span></span>

<span data-ttu-id="dad2f-385">以下步骤使您能够注册密钥存储区。</span><span class="sxs-lookup"><span data-stu-id="dad2f-385">The following steps enable you to register your key store.</span></span> <span data-ttu-id="dad2f-386">注册密钥存储是部署 DKE 之前的最后一步，您可以开始创建标签。</span><span class="sxs-lookup"><span data-stu-id="dad2f-386">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="dad2f-387">注册密钥存储区：</span><span class="sxs-lookup"><span data-stu-id="dad2f-387">To register your key store:</span></span>

1. <span data-ttu-id="dad2f-388">在浏览器中，打开[Microsoft Azure 门户](https://ms.portal.azure.com/)，并转到 "**所有服务** \> **标识** \> **应用注册**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-388">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="dad2f-389">选择 "**新建注册**"，并输入有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="dad2f-389">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="dad2f-390">从显示的选项中选择一个帐户类型。</span><span class="sxs-lookup"><span data-stu-id="dad2f-390">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="dad2f-391">如果您使用的是具有非自定义域的 Microsoft Azure （如**onmicrosoft.com**），请选择 "**仅限 Microsoft-单个租户) 中的组织目录中的帐户" (。**</span><span class="sxs-lookup"><span data-stu-id="dad2f-391">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="dad2f-392">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-392">For example:</span></span>

   ![新应用注册](../media/dke-app-registration.png)

4. <span data-ttu-id="dad2f-394">在页面底部，选择 "**注册**" 以创建新的应用注册。</span><span class="sxs-lookup"><span data-stu-id="dad2f-394">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="dad2f-395">在新的应用注册中，在左窗格中的 "**管理**" 下，选择 "**身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-395">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="dad2f-396">选择 "**添加平台**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-396">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="dad2f-397">在 "**配置平台**" 弹出菜单上，选择 " **Web**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-397">On the **Configure platforms** popup, select **Web**.</span></span>
 
8. <span data-ttu-id="dad2f-398">在 "**重定向 uri**" 下，输入您的双密钥加密服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="dad2f-398">Under **Redirect URIs**, enter the URI of your double key encryption service.</span></span> <span data-ttu-id="dad2f-399">输入应用服务 URL，包括主机名和域。</span><span class="sxs-lookup"><span data-stu-id="dad2f-399">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="dad2f-400">例如：https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="dad2f-400">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="dad2f-401">输入的 URL 必须与用于部署密钥存储的主机名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="dad2f-401">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="dad2f-402">如果您正在使用 Visual Studio 进行本地测试，请使用 **https://localhost:5001** 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-402">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="dad2f-403">在所有情况下，方案都必须是**https**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-403">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="dad2f-404">确保主机名与应用服务主机名称完全匹配。</span><span class="sxs-lookup"><span data-stu-id="dad2f-404">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="dad2f-405">您可能已将其更改为 `localhost` ，以排除生成故障。</span><span class="sxs-lookup"><span data-stu-id="dad2f-405">You may have changed it to `localhost` to troubleshoot the build.</span></span> <span data-ttu-id="dad2f-406">在**appsettings.js上**，此值是您为设置的主机名 `JwtAudience` 。</span><span class="sxs-lookup"><span data-stu-id="dad2f-406">In **appsettings.json**, this value is the hostname you set for `JwtAudience`.</span></span>

6. <span data-ttu-id="dad2f-407">在 "**隐式授予**" 下，选中 " **ID 令牌**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="dad2f-407">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="dad2f-408">选择“**保存**”以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="dad2f-408">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="dad2f-409">在左窗格中，选择 "**公开 API**"，然后选择 "应用程序 ID URI" 旁边的 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-409">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="dad2f-410">在 "**公开一个 API** " 页上的 "**此 Api 定义的作用域**" 中，选择 "**添加范围**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-410">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="dad2f-411">在新作用域中：</span><span class="sxs-lookup"><span data-stu-id="dad2f-411">In the new scope:</span></span>

    1. <span data-ttu-id="dad2f-412">将范围名称定义为**user_impersonation**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-412">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="dad2f-413">选择可以同意的管理员和用户。</span><span class="sxs-lookup"><span data-stu-id="dad2f-413">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="dad2f-414">定义所需的任何剩余值。</span><span class="sxs-lookup"><span data-stu-id="dad2f-414">Define any remaining values required.</span></span>

    4. <span data-ttu-id="dad2f-415">选择 "**添加范围"。**</span><span class="sxs-lookup"><span data-stu-id="dad2f-415">Select **Add scope.**</span></span>

    <span data-ttu-id="dad2f-416">选择顶部的 "**保存**" 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="dad2f-416">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="dad2f-417">仍在 "**公开 API** " 页上的 "**授权客户端应用程序**" 区域中，选择 "**添加客户端应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="dad2f-417">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="dad2f-418">在新的客户端应用程序中：</span><span class="sxs-lookup"><span data-stu-id="dad2f-418">In the new client application:</span></span>

    1. <span data-ttu-id="dad2f-419">将客户端 ID 定义为**d3590ed6-52b3-4102-aeff-aad2292ab01c**。</span><span class="sxs-lookup"><span data-stu-id="dad2f-419">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="dad2f-420">此值是 Microsoft Office 客户端 ID，它使 Office 能够获取密钥存储的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="dad2f-420">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="dad2f-421">在 "**授权范围**" 下，选择 " **user_impersonation** " 范围。</span><span class="sxs-lookup"><span data-stu-id="dad2f-421">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="dad2f-422">选择“添加应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="dad2f-422">Select **Add application**.</span></span>

    4. <span data-ttu-id="dad2f-423">选择顶部的 "**保存**" 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="dad2f-423">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="dad2f-424">您的 DKE 密钥存储现已注册。</span><span class="sxs-lookup"><span data-stu-id="dad2f-424">Your DKE key store is now registered.</span></span> <span data-ttu-id="dad2f-425">继续操作，方法是[使用 DKE 创建标签](#create-labels-using-dke)。</span><span class="sxs-lookup"><span data-stu-id="dad2f-425">Continue by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="dad2f-426">使用 DKE 创建标签</span><span class="sxs-lookup"><span data-stu-id="dad2f-426">Create labels using DKE</span></span>

<span data-ttu-id="dad2f-427">在 Microsoft 365 合规性中心中，创建一个新的敏感度标签，并按您自己的方式应用加密。</span><span class="sxs-lookup"><span data-stu-id="dad2f-427">In the Microsoft 365 compliance center, create a new sensitivity label and apply encryption as you would otherwise.</span></span> <span data-ttu-id="dad2f-428">选择 "**使用双密钥加密**"，并输入密钥的终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="dad2f-428">Select **Use Double Key Encryption** and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="dad2f-429">例如：</span><span class="sxs-lookup"><span data-stu-id="dad2f-429">For example:</span></span>

![在 Microsoft 365 合规性中心中选择 "使用双重密钥加密"](../media/dke-use-dke.png)

<span data-ttu-id="dad2f-431">您添加的任何 DKE 标签将为适用于企业的 Microsoft 365 应用程序的最新版本中的用户显示。</span><span class="sxs-lookup"><span data-stu-id="dad2f-431">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="dad2f-432">客户端可能需要长达24小时才能使用新标签进行刷新。</span><span class="sxs-lookup"><span data-stu-id="dad2f-432">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="dad2f-433">在客户端中启用 DKE</span><span class="sxs-lookup"><span data-stu-id="dad2f-433">Enable DKE in your client</span></span>

<span data-ttu-id="dad2f-434">通过添加以下注册表项为你的客户端启用 DKE：</span><span class="sxs-lookup"><span data-stu-id="dad2f-434">Enable DKE for your client by adding the following registry keys:</span></span>

```properties
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
