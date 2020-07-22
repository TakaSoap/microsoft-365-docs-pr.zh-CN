---
title: 双密钥加密（DKE）
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
ms.openlocfilehash: 47fc4bc47831970ef7a7f2087cf6c86b6fefb8c2
ms.sourcegitcommit: fe20f5ed07f38786c63df0f73659ca472e69e478
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/21/2020
ms.locfileid: "45201657"
---
# <a name="double-key-encryption-dke"></a><span data-ttu-id="1a759-103">双密钥加密（DKE）</span><span class="sxs-lookup"><span data-stu-id="1a759-103">Double Key Encryption (DKE)</span></span>

> <span data-ttu-id="1a759-104">*适用于： [Microsoft 365 合规性](https://www.microsoft.com/microsoft-365/business/compliance-management)、 [Azure 信息保护](https://azure.microsoft.com/pricing/details/information-protection)*</span><span class="sxs-lookup"><span data-stu-id="1a759-104">*Applies to: [Microsoft 365 Compliance](https://www.microsoft.com/microsoft-365/business/compliance-management), [Azure Information Protection](https://azure.microsoft.com/pricing/details/information-protection)*</span></span>
>
> <span data-ttu-id="1a759-105">*说明： [Azure 信息保护统一标签客户端 For Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span><span class="sxs-lookup"><span data-stu-id="1a759-105">*Instructions for: [Azure Information Protection unified labeling client for Windows](https://docs.microsoft.com/azure/information-protection/faqs.md#whats-the-difference-between-the-azure-information-protection-classic-and-unified-labeling-clients)*</span></span>
>
> <span data-ttu-id="1a759-106">*服务说明： [Microsoft 365 合规性](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span><span class="sxs-lookup"><span data-stu-id="1a759-106">*Service description for: [Microsoft 365 Compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)*</span></span>

<span data-ttu-id="1a759-107">此使用双重密钥加密（DKE）的公共预览版本，您可以使用 Azure 信息保护统一标记客户端来保护高度敏感的内容，同时保持对密钥的完全控制。</span><span class="sxs-lookup"><span data-stu-id="1a759-107">This public preview version of Double Key Encryption (DKE) enables you to use the Azure Information Protection Unified Labeling Client to protect highly sensitive content while maintaining full control of your key.</span></span>

<span data-ttu-id="1a759-108">双密钥加密需要两个密钥一起使用，以访问受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="1a759-108">Double Key Encryption requires two keys, used together, to access protected content.</span></span> <span data-ttu-id="1a759-109">在 Microsoft Azure 中存储一个密钥，并保留另一个密钥。</span><span class="sxs-lookup"><span data-stu-id="1a759-109">You store one key in Microsoft Azure, and you hold the other key.</span></span>

<span data-ttu-id="1a759-110">双密钥加密支持云和本地部署。</span><span class="sxs-lookup"><span data-stu-id="1a759-110">Double Key Encryption supports both cloud and on-premises deployments.</span></span> <span data-ttu-id="1a759-111">这些部署有助于确保在任何位置存储受保护的数据时，加密的数据保持不透明。</span><span class="sxs-lookup"><span data-stu-id="1a759-111">These deployments help to ensure that encrypted data remains opaque wherever you store the protected data.</span></span>

<span data-ttu-id="1a759-112">有关默认的基于云的租户根密钥的详细信息，请参阅[规划和实现 Azure 信息保护租户密钥](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key)。</span><span class="sxs-lookup"><span data-stu-id="1a759-112">For more information about the default, cloud-based tenant root keys, see [Planning and implementing your Azure Information Protection tenant key](https://docs.microsoft.com/azure/information-protection/plan-implement-tenant-key).</span></span>

<span data-ttu-id="1a759-113">双密钥加密类似于需要银行密钥和客户密钥才能获得访问权限的安全放盒。</span><span class="sxs-lookup"><span data-stu-id="1a759-113">Double Key Encryption is similar to a safety deposit box that requires both a bank key and a customer key to gain access.</span></span> <span data-ttu-id="1a759-114">若要解密受保护的内容，您必须同时使用 Microsoft 托管密钥和客户保留密钥。</span><span class="sxs-lookup"><span data-stu-id="1a759-114">To decrypt protected content, you must use both the Microsoft managed key and the customer-held key.</span></span>

<span data-ttu-id="1a759-115">下面的视频演示如何将双密钥加密用于保护内容。</span><span class="sxs-lookup"><span data-stu-id="1a759-115">The following video shows how Double Key Encryption works to secure your content.</span></span>

<span data-ttu-id="1a759-116">如果您的组织有以下任一要求，您可以使用 DKE 帮助保护您的内容：</span><span class="sxs-lookup"><span data-stu-id="1a759-116">If your organizations have any of the following requirements, you can use DKE to help secure your content:</span></span>

- <span data-ttu-id="1a759-117">您希望确保*只有*在所有情况下都可以对受保护的内容进行解密。</span><span class="sxs-lookup"><span data-stu-id="1a759-117">You want to ensure that *only you* can ever decrypt protected content, under all circumstances.</span></span>
- <span data-ttu-id="1a759-118">您不希望 Microsoft 能够单独访问受保护的数据。</span><span class="sxs-lookup"><span data-stu-id="1a759-118">You don't want Microsoft to have access to protected data on its own.</span></span>
- <span data-ttu-id="1a759-119">您有管理法规要求，可在地理边界内保留密钥。</span><span class="sxs-lookup"><span data-stu-id="1a759-119">You have regulatory requirements to hold keys within a geographical boundary.</span></span> <span data-ttu-id="1a759-120">数据加密和解密的所有客户保留密钥都将保留在您的数据中心中。</span><span class="sxs-lookup"><span data-stu-id="1a759-120">All customer-held keys for data encryption and decryption are maintained in your data center.</span></span>

> [!VIDEO https://msit.microsoftstream.com/embed/video/f466a1ff-0400-a936-221c-f1eab45dc756]

## <a name="system-and-licensing-requirements-for-dke"></a><span data-ttu-id="1a759-121">DKE 的系统和许可要求</span><span class="sxs-lookup"><span data-stu-id="1a759-121">System and licensing requirements for DKE</span></span>

<span data-ttu-id="1a759-122">Microsoft 365 E5 和 Office 365 E5 中提供了 Microsoft 365 的双重密钥加密的公开预览版本。</span><span class="sxs-lookup"><span data-stu-id="1a759-122">This public preview release of Double Key Encryption for Microsoft 365 is available as part of Microsoft 365 E5 and Office 365 E5.</span></span> <span data-ttu-id="1a759-123">如果你没有 Microsoft 365 E5 许可证，你可以注册[试用版](https://aka.ms/M365E5ComplianceTrial)。</span><span class="sxs-lookup"><span data-stu-id="1a759-123">If you don’t have a Microsoft 365 E5 license, you can sign up for a [trial](https://aka.ms/M365E5ComplianceTrial).</span></span> <span data-ttu-id="1a759-124">有关这些许可证的详细信息，请参阅[适用于安全 & 合规性的 Microsoft 365 许可指南](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。</span><span class="sxs-lookup"><span data-stu-id="1a759-124">For more information about these licenses, see [Microsoft 365 licensing guidance for security & compliance](https://docs.microsoft.com/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance).</span></span>

<span data-ttu-id="1a759-125">**Office 预览体验成员**若要使用公共预览版，您必须是 Office 预览体验成员计划的成员。</span><span class="sxs-lookup"><span data-stu-id="1a759-125">**Office Insider** To use the public preview, you must be a member of the Office Insider program.</span></span> <span data-ttu-id="1a759-126">若要加入 Office 预览体验成员，请转到 [https://insider.office.com](https://insider.office.com) 。</span><span class="sxs-lookup"><span data-stu-id="1a759-126">To join Office Insider, go to [https://insider.office.com](https://insider.office.com).</span></span> <span data-ttu-id="1a759-127">一旦成为你的成员，请为你的组织选择正确的部署方法，准备环境以部署 Office 有问必答版内部版本。</span><span class="sxs-lookup"><span data-stu-id="1a759-127">Once you're a member, prepare your environment to deploy Office Insider builds by choosing the right deployment method for your organization.</span></span> <span data-ttu-id="1a759-128">有关说明，请参阅[部署 Office 预览体验成员内部版本](https://insider.office.com/business/deploy)入门。</span><span class="sxs-lookup"><span data-stu-id="1a759-128">For instructions, see [Getting started on deploying Office Insider builds](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="1a759-129">**Azure 信息保护**。</span><span class="sxs-lookup"><span data-stu-id="1a759-129">**Azure Information Protection**.</span></span> <span data-ttu-id="1a759-130">DKE 使用灵敏度标签，需要 Azure 信息保护。</span><span class="sxs-lookup"><span data-stu-id="1a759-130">DKE works with sensitivity labels and requires Azure Information Protection.</span></span>

## <a name="supported-environments-for-storing-and-viewing-dke-protected-content"></a><span data-ttu-id="1a759-131">用于存储和查看受 DKE 保护的内容的受支持的环境</span><span class="sxs-lookup"><span data-stu-id="1a759-131">Supported environments for storing and viewing DKE-protected content</span></span>

<span data-ttu-id="1a759-132">**支持的应用程序**。</span><span class="sxs-lookup"><span data-stu-id="1a759-132">**Supported applications**.</span></span> <span data-ttu-id="1a759-133">Windows 上[的适用于企业客户端的 Microsoft 365 应用程序](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product)，包括 Word、Excel 和 PowerPoint。</span><span class="sxs-lookup"><span data-stu-id="1a759-133">[Microsoft 365 Apps for enterprise](https://www.microsoft.com/microsoft-365/business/microsoft-365-apps-for-enterprise-product) clients on Windows, including Word, Excel, and PowerPoint.</span></span>

<span data-ttu-id="1a759-134">**在线内容支持**。</span><span class="sxs-lookup"><span data-stu-id="1a759-134">**Online content support**.</span></span> <span data-ttu-id="1a759-135">支持在 Microsoft SharePoint 和 OneDrive for Business 中联机存储的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-135">Documents and files stored online in both Microsoft SharePoint and OneDrive for Business are supported.</span></span> <span data-ttu-id="1a759-136">您可以通过电子邮件共享加密内容，但不能联机查看加密的文档和文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-136">You can share encrypted content by email, but you can't view encrypted documents and files online.</span></span> <span data-ttu-id="1a759-137">相反，您必须使用本地计算机上的桌面应用程序查看受保护的内容。</span><span class="sxs-lookup"><span data-stu-id="1a759-137">Instead, you must view protected content using the desktop apps on your local computer.</span></span>

## <a name="about-this-public-preview-article"></a><span data-ttu-id="1a759-138">关于此公共预览版文章</span><span class="sxs-lookup"><span data-stu-id="1a759-138">About this public preview article</span></span>

<span data-ttu-id="1a759-139">有几种方法可以完成一些部署双密钥加密的步骤。</span><span class="sxs-lookup"><span data-stu-id="1a759-139">There are several ways you can complete some of the steps to deploy Double Key Encryption.</span></span> <span data-ttu-id="1a759-140">本文提供了详细说明，以便让经验较少的管理员能够成功部署服务。</span><span class="sxs-lookup"><span data-stu-id="1a759-140">This article provides detailed instructions so that less experienced admins successfully deploy the service.</span></span> <span data-ttu-id="1a759-141">如果你熟悉本文中所述的部署方法共享的常见技术（如 git），则可以选择使用自己的方法。</span><span class="sxs-lookup"><span data-stu-id="1a759-141">If you're experienced with the common technologies, such as git, shared by the deployment methods described in this article, you can choose to use your own methods.</span></span>

<span data-ttu-id="1a759-142">对于公共预览版，我们提供了有关如何将双重密钥加密服务部署到 Azure 的分步说明。</span><span class="sxs-lookup"><span data-stu-id="1a759-142">For public preview, we've included step-by-step instructions on how to deploy the Double Key Encryption service to Azure.</span></span> <span data-ttu-id="1a759-143">此方案不是您在生产中可能要执行的操作。</span><span class="sxs-lookup"><span data-stu-id="1a759-143">This scenario isn't something you'd likely do in production.</span></span> <span data-ttu-id="1a759-144">使用 Azure 进行公共预览是一种快速部署方法，可让你立即开始使用双密钥加密。</span><span class="sxs-lookup"><span data-stu-id="1a759-144">For public preview using Azure is a quick way to deploy that lets you get started using Double Key Encryption right away.</span></span>

<span data-ttu-id="1a759-145">您可以选择在需要的任何位置部署服务，无论它是在网络本地还是其他提供商。</span><span class="sxs-lookup"><span data-stu-id="1a759-145">You can choose to deploy the service wherever you want, whether it's locally on your network or with another provider.</span></span> <span data-ttu-id="1a759-146">您需要使用适合于该位置的方法发布密钥存储。</span><span class="sxs-lookup"><span data-stu-id="1a759-146">You'll need to publish the key store using methods appropriate for that location.</span></span>

## <a name="deploy-double-key-encryption"></a><span data-ttu-id="1a759-147">部署双密钥加密</span><span class="sxs-lookup"><span data-stu-id="1a759-147">Deploy Double Key Encryption</span></span>

<span data-ttu-id="1a759-148">您将按照这些常规步骤为您的组织设置双密钥加密。</span><span class="sxs-lookup"><span data-stu-id="1a759-148">You'll follow these general steps to set up Double Key Encryption for your organization.</span></span> <span data-ttu-id="1a759-149">本文中的示例使用 Azure 作为 DKE 服务的部署目标。</span><span class="sxs-lookup"><span data-stu-id="1a759-149">The example in this article uses Azure as the deployment destination for the DKE service.</span></span> <span data-ttu-id="1a759-150">如果要部署到其他位置，则需要提供自己的值。</span><span class="sxs-lookup"><span data-stu-id="1a759-150">If you're deploying to another location, you'll need to provide your own values.</span></span>

1. [<span data-ttu-id="1a759-151">安装必备软件</span><span class="sxs-lookup"><span data-stu-id="1a759-151">Install software prerequisites</span></span>](#install-software-prerequisites)
1. [<span data-ttu-id="1a759-152">克隆双密钥加密 GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="1a759-152">Clone the Double Key Encryption GitHub repository</span></span>](#clone-the-dke-github-repository)
1. [<span data-ttu-id="1a759-153">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="1a759-153">Modify application settings</span></span>](#modify-application-settings)
1. [<span data-ttu-id="1a759-154">生成测试键</span><span class="sxs-lookup"><span data-stu-id="1a759-154">Generate test keys</span></span>](#generate-test-keys)
1. [<span data-ttu-id="1a759-155">生成项目</span><span class="sxs-lookup"><span data-stu-id="1a759-155">Build the project</span></span>](#build-the-project)
1. [<span data-ttu-id="1a759-156">发布密钥存储</span><span class="sxs-lookup"><span data-stu-id="1a759-156">Publish the key store</span></span>](#publish-the-key-store)
1. [<span data-ttu-id="1a759-157">验证部署</span><span class="sxs-lookup"><span data-stu-id="1a759-157">Validate your deployment</span></span>](#validate-your-deployment)
1. [<span data-ttu-id="1a759-158">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="1a759-158">Register your key store</span></span>](#register-your-key-store)
1. [<span data-ttu-id="1a759-159">创建敏感度标签</span><span class="sxs-lookup"><span data-stu-id="1a759-159">Create sensitivity labels</span></span>](#create-labels-using-dke)

<span data-ttu-id="1a759-160">完成后，您可以使用 DKE 对文档和文件进行加密。</span><span class="sxs-lookup"><span data-stu-id="1a759-160">When you're done, you can encrypt documents and files using DKE.</span></span> <span data-ttu-id="1a759-161">有关信息，请参阅[将敏感度标签应用于 Office 中的文件和电子邮件](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)。</span><span class="sxs-lookup"><span data-stu-id="1a759-161">For information, see [Apply sensitivity labels to your files and email in Office](https://support.microsoft.com/office/2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9).</span></span>

### <a name="install-software-prerequisites"></a><span data-ttu-id="1a759-162">安装必备软件</span><span class="sxs-lookup"><span data-stu-id="1a759-162">Install software prerequisites</span></span>

<span data-ttu-id="1a759-163">双密钥加密有两种类型的软件先决条件</span><span class="sxs-lookup"><span data-stu-id="1a759-163">There are two types of software prerequisites for Double Key Encryption</span></span>

- [<span data-ttu-id="1a759-164">双密钥加密服务先决条件</span><span class="sxs-lookup"><span data-stu-id="1a759-164">Double Key Encryption service prerequisites</span></span>](#double-key-encryption-service-prerequisites)
- [<span data-ttu-id="1a759-165">客户端计算机的双密钥加密先决条件</span><span class="sxs-lookup"><span data-stu-id="1a759-165">Double Key Encryption prerequisites for client computers</span></span>](#double-key-encryption-prerequisites-for-client-computers)

#### <a name="double-key-encryption-service-prerequisites"></a><span data-ttu-id="1a759-166">双密钥加密服务先决条件</span><span class="sxs-lookup"><span data-stu-id="1a759-166">Double Key Encryption service prerequisites</span></span>

<span data-ttu-id="1a759-167">在要安装 DKE 服务的计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="1a759-167">Install these prerequisites on the computer where you want to install the DKE service.</span></span>

<span data-ttu-id="1a759-168">**.Net Core 3.1 SDK**。</span><span class="sxs-lookup"><span data-stu-id="1a759-168">**.NET Core 3.1 SDK**.</span></span> <span data-ttu-id="1a759-169">从[下载 .Net Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1)下载并安装 SDK。</span><span class="sxs-lookup"><span data-stu-id="1a759-169">Download and install the SDK from [Download .NET Core 3.1](https://dotnet.microsoft.com/download/dotnet-core/3.1).</span></span>

<span data-ttu-id="1a759-170">**Visual Studio Code**。</span><span class="sxs-lookup"><span data-stu-id="1a759-170">**Visual Studio Code**.</span></span> <span data-ttu-id="1a759-171">从下载 Visual Studio Code [https://code.visualstudio.com/](https://code.visualstudio.com) 。</span><span class="sxs-lookup"><span data-stu-id="1a759-171">Download Visual Studio Code from [https://code.visualstudio.com/](https://code.visualstudio.com).</span></span> <span data-ttu-id="1a759-172">安装完成后，运行 Visual Studio Code 并选择 "**查看** \> **扩展**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-172">Once installed, run Visual Studio Code and select **View** \> **Extensions**.</span></span> <span data-ttu-id="1a759-173">安装这些扩展。</span><span class="sxs-lookup"><span data-stu-id="1a759-173">Install these extensions.</span></span>

- <span data-ttu-id="1a759-174">Visual Studio Code 的 c #</span><span class="sxs-lookup"><span data-stu-id="1a759-174">C# for Visual Studio Code</span></span>

- <span data-ttu-id="1a759-175">NuGet 包管理器</span><span class="sxs-lookup"><span data-stu-id="1a759-175">NuGet Package Manager</span></span>

<span data-ttu-id="1a759-176">**Microsoft Office 预览体验成员**。</span><span class="sxs-lookup"><span data-stu-id="1a759-176">**Microsoft Office Insider**.</span></span> <span data-ttu-id="1a759-177">设置至少一个[部署方法](https://insider.office.com/business/deploy)。</span><span class="sxs-lookup"><span data-stu-id="1a759-177">Set up at least one [deployment method](https://insider.office.com/business/deploy).</span></span>

<span data-ttu-id="1a759-178">**Git 资源**。</span><span class="sxs-lookup"><span data-stu-id="1a759-178">**Git resources**.</span></span> <span data-ttu-id="1a759-179">下载并安装以下各项之一。</span><span class="sxs-lookup"><span data-stu-id="1a759-179">Download and install one of the following.</span></span>

- [<span data-ttu-id="1a759-180">Git</span><span class="sxs-lookup"><span data-stu-id="1a759-180">Git</span></span>](https://git-scm.com/downloads)

- [<span data-ttu-id="1a759-181">GitHub 桌面</span><span class="sxs-lookup"><span data-stu-id="1a759-181">GitHub Desktop</span></span>](https://desktop.github.com/)

- [<span data-ttu-id="1a759-182">GitHub 企业</span><span class="sxs-lookup"><span data-stu-id="1a759-182">GitHub Enterprise</span></span>](https://github.com/enterprise)

<span data-ttu-id="1a759-183">**OpenSSL**您必须安装了[OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) ，才能在部署 DKE 后[生成测试密钥](#generate-test-keys)。</span><span class="sxs-lookup"><span data-stu-id="1a759-183">**OpenSSL** You must have [OpenSSL](https://slproweb.com/products/Win32OpenSSL.html) installed to [generate test keys](#generate-test-keys) after you deploy DKE.</span></span> <span data-ttu-id="1a759-184">请确保您从环境变量路径中正确调用了它。</span><span class="sxs-lookup"><span data-stu-id="1a759-184">Make sure you're invoking it correctly from your environment variables path.</span></span> <span data-ttu-id="1a759-185">例如，有关详细信息，请参阅 "将安装目录添加到路径" https://www.osradar.com/install-openssl-windows/ 。</span><span class="sxs-lookup"><span data-stu-id="1a759-185">For example, see "Add the installation directory to PATH" at https://www.osradar.com/install-openssl-windows/ for details.</span></span>

#### <a name="double-key-encryption-prerequisites-for-client-computers"></a><span data-ttu-id="1a759-186">客户端计算机的双密钥加密先决条件</span><span class="sxs-lookup"><span data-stu-id="1a759-186">Double Key Encryption prerequisites for client computers</span></span>

<span data-ttu-id="1a759-187">在要保护和使用受保护文档的每台客户端计算机上安装这些必备组件。</span><span class="sxs-lookup"><span data-stu-id="1a759-187">Install these prerequisites on each client computer where you want to protect and consume protected documents.</span></span>

<span data-ttu-id="1a759-188">**Microsoft Office** 12711 版或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1a759-188">**Microsoft Office** version \*.12711 or later.</span></span>

<span data-ttu-id="1a759-189">**Azure 信息保护统一标签客户端**版本2.7.93.0 或更高版本。</span><span class="sxs-lookup"><span data-stu-id="1a759-189">**Azure Information Protection Unified Labeling Client** versions 2.7.93.0 or later.</span></span> <span data-ttu-id="1a759-190">从[Microsoft](https://www.microsoft.com/download/details.aspx?id=53018)下载并安装统一的标记客户端。</span><span class="sxs-lookup"><span data-stu-id="1a759-190">Download and install the Unified Labeling client from [Microsoft](https://www.microsoft.com/download/details.aspx?id=53018).</span></span>

### <a name="clone-the-dke-github-repository"></a><span data-ttu-id="1a759-191">克隆 DKE GitHub 存储库</span><span class="sxs-lookup"><span data-stu-id="1a759-191">Clone the DKE GitHub repository</span></span>

<span data-ttu-id="1a759-192">Microsoft 提供 GitHub 存储库中的 DKE 源文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-192">Microsoft supplies the DKE source files in a GitHub repository.</span></span> <span data-ttu-id="1a759-193">克隆存储库，以在本地为组织的使用生成项目。</span><span class="sxs-lookup"><span data-stu-id="1a759-193">You clone the repository to build the project locally for your organization's use.</span></span> <span data-ttu-id="1a759-194">DKE GitHub 存储库位于 [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService) 。</span><span class="sxs-lookup"><span data-stu-id="1a759-194">The DKE GitHub repository is located at [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService).</span></span>

<span data-ttu-id="1a759-195">以下说明适用于缺乏的 git 或 Visual Studio Code users：</span><span class="sxs-lookup"><span data-stu-id="1a759-195">The following instructions are intended for inexperienced git or Visual Studio Code users:</span></span>

1. <span data-ttu-id="1a759-196">在浏览器中，转到：[https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span><span class="sxs-lookup"><span data-stu-id="1a759-196">In your browser, go to: [https://github.com/Azure-Samples/DoubleKeyEncryptionService](https://github.com/Azure-Samples/DoubleKeyEncryptionService)</span></span>

1. <span data-ttu-id="1a759-197">在屏幕右侧，选择 "**代码**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-197">Towards the right side of the screen, select **Code**.</span></span> <span data-ttu-id="1a759-198">您的 UI 版本可能会显示 "**克隆" 或 "下载**" 按钮。</span><span class="sxs-lookup"><span data-stu-id="1a759-198">Your version of the UI might show a **Clone or download** button.</span></span> <span data-ttu-id="1a759-199">然后，在出现的下拉列表中，选择 "复制" 图标将 URL 复制到剪贴板。</span><span class="sxs-lookup"><span data-stu-id="1a759-199">Then, in the dropdown that appears, select the copy icon to copy the URL to your clipboard.</span></span>

    <span data-ttu-id="1a759-200">例如：</span><span class="sxs-lookup"><span data-stu-id="1a759-200">For example:</span></span>

    :::image type="content" source="../media/dke-clone.png" alt-text="从 GitHub 克隆双密钥加密服务存储库":::

3. <span data-ttu-id="1a759-202">在 Visual Studio Code 中，选择 "**查看** \> **命令选项板**"，然后选择 " **Git： Clone**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-202">In Visual Studio Code, select **View** \> **Command Palette** and select **Git: Clone**.</span></span> <span data-ttu-id="1a759-203">若要跳转到列表中的选项，请开始键入 `git: clone` 以筛选条目，然后从下拉列表中进行选择。</span><span class="sxs-lookup"><span data-stu-id="1a759-203">To jump to the option in the list, start typing `git: clone` to filter the entries and then select it from the drop-down.</span></span> <span data-ttu-id="1a759-204">例如：</span><span class="sxs-lookup"><span data-stu-id="1a759-204">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-clone.png" alt-text="Visual Studio Code GIT： Clone 选项":::

4. <span data-ttu-id="1a759-206">在文本框中，粘贴从 Git 复制的 URL，然后**从 GitHub 中**选择 "复制"。</span><span class="sxs-lookup"><span data-stu-id="1a759-206">In the text box, paste the URL that you copied from Git and select **Clone from GitHub**.</span></span>

5. <span data-ttu-id="1a759-207">在出现的 "**选择文件夹**" 对话框中，浏览并选择存储库的位置。</span><span class="sxs-lookup"><span data-stu-id="1a759-207">In the **Select Folder** dialog that appears, browse to and select a location to store the repository.</span></span> <span data-ttu-id="1a759-208">在提示符下，选择 "**打开**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-208">At the prompt, select **Open**.</span></span>

    <span data-ttu-id="1a759-209">存储库在 Visual Studio Code 中打开，并在左下角显示当前 Git 分支。</span><span class="sxs-lookup"><span data-stu-id="1a759-209">The repository is opened in Visual Studio Code, and displays the current Git branch at the bottom left.</span></span> <span data-ttu-id="1a759-210">当前分支应为 "**主控形状**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-210">Your current branch should be **master**.</span></span>

    <span data-ttu-id="1a759-211">例如：</span><span class="sxs-lookup"><span data-stu-id="1a759-211">For example:</span></span>

    :::image type="content" source="../media/dke-vscode-master.png" alt-text="Visual Studio Code master 分支":::

6. <span data-ttu-id="1a759-213">选择 "word**母版"，** 然后从分支列表中选择 " **public_preview** "。</span><span class="sxs-lookup"><span data-stu-id="1a759-213">Select the word **master,** and then select **public_preview** from the list of branches.</span></span> 

   > [!IMPORTANT]
   > <span data-ttu-id="1a759-214">选择 "public_preview" 分支可确保您具有用于生成项目的正确文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-214">Selecting the public_preview branch ensures that you have the correct files to build the project.</span></span> <span data-ttu-id="1a759-215">如果不选择正确的分支，部署将会失败。</span><span class="sxs-lookup"><span data-stu-id="1a759-215">If you do not choose the correct branch your deployment will fail.</span></span>

<span data-ttu-id="1a759-216">现在，你已在本地设置了 DKE 源存储库。</span><span class="sxs-lookup"><span data-stu-id="1a759-216">You now have your DKE source repository set up locally.</span></span> <span data-ttu-id="1a759-217">接下来，修改您的组织的[应用程序设置](#modify-application-settings)。</span><span class="sxs-lookup"><span data-stu-id="1a759-217">Next, [modify application settings](#modify-application-settings) for your organization.</span></span>

### <a name="modify-application-settings"></a><span data-ttu-id="1a759-218">修改应用程序设置</span><span class="sxs-lookup"><span data-stu-id="1a759-218">Modify application settings</span></span>

<span data-ttu-id="1a759-219">若要部署 DKE 服务，必须修改以下类型的应用程序设置：</span><span class="sxs-lookup"><span data-stu-id="1a759-219">To deploy the DKE service, you must modify the following types of application settings:</span></span>

- [<span data-ttu-id="1a759-220">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="1a759-220">Key access settings</span></span>](#key-access-settings)
- [<span data-ttu-id="1a759-221">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="1a759-221">Tenant and key settings</span></span>](#tenant-and-key-settings)

<span data-ttu-id="1a759-222">您可以在 appsettings.js的文件中修改应用程序设置。</span><span class="sxs-lookup"><span data-stu-id="1a759-222">You modify application settings in the appsettings.json file.</span></span> <span data-ttu-id="1a759-223">此文件位于本地克隆的 DoubleKeyEncryptionService 存储库中的 DoubleKeyEncryptionService\src\customer-key-store。</span><span class="sxs-lookup"><span data-stu-id="1a759-223">This file is located in the DoubleKeyEncryptionService repo you cloned locally under DoubleKeyEncryptionService\src\customer-key-store.</span></span> <span data-ttu-id="1a759-224">例如，在 Visual Studio Code 中，可以按下图所示浏览到文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-224">For example, in Visual Studio Code, you can browse to the file as shown in the following picture.</span></span>

:::image type="content" source="../media/dke-appsettingsjson.png" alt-text="为 DKE 查找文件上的 appsettings.js。":::

#### <a name="key-access-settings"></a><span data-ttu-id="1a759-226">密钥访问设置</span><span class="sxs-lookup"><span data-stu-id="1a759-226">Key access settings</span></span>

<span data-ttu-id="1a759-227">选择是否使用电子邮件或角色授权。</span><span class="sxs-lookup"><span data-stu-id="1a759-227">Choose whether to use email or role authorization.</span></span> <span data-ttu-id="1a759-228">DKE 一次仅支持其中一种身份验证方法。</span><span class="sxs-lookup"><span data-stu-id="1a759-228">DKE supports only one of these authentication methods at a time.</span></span>

- <span data-ttu-id="1a759-229">**电子邮件授权**。</span><span class="sxs-lookup"><span data-stu-id="1a759-229">**Email authorization**.</span></span> <span data-ttu-id="1a759-230">允许您的组织仅基于电子邮件地址授权访问密钥。</span><span class="sxs-lookup"><span data-stu-id="1a759-230">Allows your organization to authorize access to keys based on email addresses only.</span></span>

- <span data-ttu-id="1a759-231">**角色授权**。</span><span class="sxs-lookup"><span data-stu-id="1a759-231">**Role authorization**.</span></span> <span data-ttu-id="1a759-232">允许您的组织根据 Active Directory 组授权对密钥的访问，并要求 web 服务可以查询 LDAP。</span><span class="sxs-lookup"><span data-stu-id="1a759-232">Allows your organization to authorize access to keys based on Active Directory groups, and requires that the web service can query LDAP.</span></span>

<span data-ttu-id="1a759-233">若要设置 DKE 的密钥访问设置，请执行以下操作：</span><span class="sxs-lookup"><span data-stu-id="1a759-233">To set key access settings for DKE:</span></span>

1. <span data-ttu-id="1a759-234">在 " **appsettings.js的**文件" 中，仅定义以下设置之一：</span><span class="sxs-lookup"><span data-stu-id="1a759-234">In the **appsettings.json** file, define only one of these settings:</span></span>

   - <span data-ttu-id="1a759-235">若要获取电子邮件授权，请找到**AuthorizedEmailAddresses**设置。</span><span class="sxs-lookup"><span data-stu-id="1a759-235">For email authorization, locate the **AuthorizedEmailAddresses** setting.</span></span> <span data-ttu-id="1a759-236">添加要授权的电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1a759-236">Add the email address that you want to authorize.</span></span> <span data-ttu-id="1a759-237">用双引号和逗号分隔多个电子邮件地址。</span><span class="sxs-lookup"><span data-stu-id="1a759-237">Separate multiple email addresses with double quotes and commas.</span></span> <span data-ttu-id="1a759-238">例如： **"AuthorizedEmailAddresses" "： [" email1@company.com "、" email2@company.com "、email3@company.com]**</span><span class="sxs-lookup"><span data-stu-id="1a759-238">For example: **" ‘AuthorizedEmailAddresses’ ": ["email1@company.com", "email2@company.com ", email3@company.com]**</span></span>

   :::image type="content" source="../media/dke-email-accesssetting.png" alt-text="对显示电子邮件授权方法的文件appsettings.js":::

   - <span data-ttu-id="1a759-240">若要获取角色授权，请找到**AuthorizedRoles**设置。</span><span class="sxs-lookup"><span data-stu-id="1a759-240">For role authorization, locate the **AuthorizedRoles** setting.</span></span> <span data-ttu-id="1a759-241">使用要授权的 ActiveDirectory 组名称进行定义。</span><span class="sxs-lookup"><span data-stu-id="1a759-241">Define with the ActiveDirectory group names you want to authorize.</span></span> <span data-ttu-id="1a759-242">例如： **"AuthorizedRoles"： ["group1"、"组 2"、"group3"]**</span><span class="sxs-lookup"><span data-stu-id="1a759-242">For example: **"AuthorizedRoles": ["group1", "group2", "group3"]**</span></span>

   :::image type="content" source="../media/dke-role-accesssetting.png" alt-text="对显示角色授权方法的文件appsettings.js":::

2. <span data-ttu-id="1a759-244">删除与所选的授权方法不相关的设置。</span><span class="sxs-lookup"><span data-stu-id="1a759-244">Remove the setting that isn't relevant for your chosen authorization method.</span></span>

#### <a name="tenant-and-key-settings"></a><span data-ttu-id="1a759-245">租户和密钥设置</span><span class="sxs-lookup"><span data-stu-id="1a759-245">Tenant and key settings</span></span>

<span data-ttu-id="1a759-246">DKE 租户和关键设置位于文件和**startup.cs**文件的**appsettings.js**中。</span><span class="sxs-lookup"><span data-stu-id="1a759-246">DKE tenant and key settings are located in the **appsettings.json** file and the **startup.cs** file.</span></span>

<span data-ttu-id="1a759-247">在 " **appsettings.js的**文件" 中，修改以下值：</span><span class="sxs-lookup"><span data-stu-id="1a759-247">In the **appsettings.json** file, modify the following values:</span></span>

- <span data-ttu-id="1a759-248">**ValidIssuers**。</span><span class="sxs-lookup"><span data-stu-id="1a759-248">**ValidIssuers**.</span></span> <span data-ttu-id="1a759-249">`<tenantid>`将替换为租户 GUID。</span><span class="sxs-lookup"><span data-stu-id="1a759-249">Replace `<tenantid>` with your tenant GUID.</span></span>
- <span data-ttu-id="1a759-250">**JwtAudience**。</span><span class="sxs-lookup"><span data-stu-id="1a759-250">**JwtAudience**.</span></span> <span data-ttu-id="1a759-251">`<yourhostname>`将替换为将运行 DKE 服务的计算机的主机名。</span><span class="sxs-lookup"><span data-stu-id="1a759-251">Replace `<yourhostname>` with the hostname of the machine where the DKE service will run.</span></span>

  > [!IMPORTANT]
  > <span data-ttu-id="1a759-252">JwtAudience 的值必须与主机的名称*完全*匹配。</span><span class="sxs-lookup"><span data-stu-id="1a759-252">The value for JwtAudience must match the name of your host *exactly*.</span></span> <span data-ttu-id="1a759-253">调试时，您可以使用**localhost： 5000** 。</span><span class="sxs-lookup"><span data-stu-id="1a759-253">You may use **localhost:5000** while debugging.</span></span> <span data-ttu-id="1a759-254">但是，在完成调试后，请务必将此值更新到服务器的主机名。</span><span class="sxs-lookup"><span data-stu-id="1a759-254">However, When you're done debugging, make sure to update this value to the server's hostname.</span></span>

- <span data-ttu-id="1a759-255">**LDAPPath**。</span><span class="sxs-lookup"><span data-stu-id="1a759-255">**LDAPPath**.</span></span> <span data-ttu-id="1a759-256">设置值，如下所示：</span><span class="sxs-lookup"><span data-stu-id="1a759-256">Set the value as follows:</span></span>

  - <span data-ttu-id="1a759-257">如果使用的是角色授权，请输入 LDAP 域。</span><span class="sxs-lookup"><span data-stu-id="1a759-257">If you're using role authorization, enter the LDAP domain.</span></span>
  - <span data-ttu-id="1a759-258">如果使用的是电子邮件授权，请将此值留空。</span><span class="sxs-lookup"><span data-stu-id="1a759-258">If you're using email authorization, leave this value empty.</span></span>

   <span data-ttu-id="1a759-259">有关详细信息，请参阅[主要访问设置](#key-access-settings)。</span><span class="sxs-lookup"><span data-stu-id="1a759-259">For more information, see [Key access settings](#key-access-settings).</span></span>

- <span data-ttu-id="1a759-260">**TestKeys： Name**。</span><span class="sxs-lookup"><span data-stu-id="1a759-260">**TestKeys:Name**.</span></span> <span data-ttu-id="1a759-261">输入密钥的名称。</span><span class="sxs-lookup"><span data-stu-id="1a759-261">Enter a name for your key.</span></span> <span data-ttu-id="1a759-262">示例： **TestKey1**</span><span class="sxs-lookup"><span data-stu-id="1a759-262">Example: **TestKey1**</span></span>
- <span data-ttu-id="1a759-263">**TestKeys： Id**。创建一个 GUID 并将其输入为**TestKeys： ID**值。</span><span class="sxs-lookup"><span data-stu-id="1a759-263">**TestKeys:Id**. Create a GUID and enter it as the **TestKeys:ID** value.</span></span> <span data-ttu-id="1a759-264">例如， **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**。</span><span class="sxs-lookup"><span data-stu-id="1a759-264">For example, **DCE1CC21-FF9B-4424-8FF4-9914BD19A1BE**.</span></span> <span data-ttu-id="1a759-265">您可以使用[联机 Guid 生成器](https://guidgenerator.com/)等网站随机生成 GUID。</span><span class="sxs-lookup"><span data-stu-id="1a759-265">You can use a site like [Online GUID Generator](https://guidgenerator.com/) to randomly generate a GUID.</span></span>

### <a name="generate-test-keys"></a><span data-ttu-id="1a759-266">生成测试键</span><span class="sxs-lookup"><span data-stu-id="1a759-266">Generate test keys</span></span>

<span data-ttu-id="1a759-267">定义应用程序设置后，即可生成公用和专用测试密钥。</span><span class="sxs-lookup"><span data-stu-id="1a759-267">Once you have your application settings defined, you're ready to generate public and private test keys.</span></span>

<span data-ttu-id="1a759-268">生成密钥：</span><span class="sxs-lookup"><span data-stu-id="1a759-268">To generate keys:</span></span>

1. <span data-ttu-id="1a759-269">从 Windows "开始" 菜单中，运行 OpenSSL 命令提示符。</span><span class="sxs-lookup"><span data-stu-id="1a759-269">From the Windows Start menu, run the OpenSSL Command Prompt.</span></span>

1. <span data-ttu-id="1a759-270">转到要在其中保存测试密钥的文件夹。</span><span class="sxs-lookup"><span data-stu-id="1a759-270">Change to the folder where you want to save the test keys.</span></span> <span data-ttu-id="1a759-271">您通过完成此任务中的步骤创建的文件存储在同一个文件夹中。</span><span class="sxs-lookup"><span data-stu-id="1a759-271">The files you create by completing the steps in this task are stored in the same folder.</span></span>

1. <span data-ttu-id="1a759-272">生成新的测试密钥。</span><span class="sxs-lookup"><span data-stu-id="1a759-272">Generate the new test key.</span></span>

   ```dos
   openssl req -x509 -newkey rsa:2048 -keyout key.pem -out cert.pem -days 365
   ```

2. <span data-ttu-id="1a759-273">生成私钥。</span><span class="sxs-lookup"><span data-stu-id="1a759-273">Generate the private key.</span></span>

   ```dos
   openssl rsa -in key.pem -out privkeynopass.pem
   ```

1. <span data-ttu-id="1a759-274">生成公钥。</span><span class="sxs-lookup"><span data-stu-id="1a759-274">Generate the public key.</span></span>

   ```dos
   openssl rsa -in key.pem -pubout > pubkeyonly.pem
   ```

1. <span data-ttu-id="1a759-275">在文本编辑器中，打开 " **pubkeyonly**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-275">In a text editor, open **pubkeyonly.pem**.</span></span> <span data-ttu-id="1a759-276">将**pubkeyonly**文件中的所有内容（第一行和最后一行除外）复制到文件**appsettings.js**的**PublicPem**部分。</span><span class="sxs-lookup"><span data-stu-id="1a759-276">Copy all of the content in the **pubkeyonly.pem** file, except the first and last lines, into the **PublicPem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="1a759-277">在文本编辑器中，打开 " **privkeynopass**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-277">In a text editor, open **privkeynopass.pem**.</span></span> <span data-ttu-id="1a759-278">将**privkeynopass**文件中的所有内容（第一行和最后一行除外）复制到文件**appsettings.js**的**PrivatePem**部分。</span><span class="sxs-lookup"><span data-stu-id="1a759-278">Copy all of the content in the **privkeynopass.pem** file, except the first and last lines, into the **PrivatePem** section of the **appsettings.json** file.</span></span>

1. <span data-ttu-id="1a759-279">在 " **PublicPem** " 和 " **PrivatePem** " 部分中，删除所有空格和换行符。</span><span class="sxs-lookup"><span data-stu-id="1a759-279">Remove all blank spaces and newlines in both the **PublicPem** and **PrivatePem** sections.</span></span>

    > [!IMPORTANT]
    > <span data-ttu-id="1a759-280">复制此内容时，请不要删除任何 PEM 数据。</span><span class="sxs-lookup"><span data-stu-id="1a759-280">When you copy this content, do not delete any of the PEM data.</span></span>

1. <span data-ttu-id="1a759-281">打开**Startup.cs**文件，并找到以下行：</span><span class="sxs-lookup"><span data-stu-id="1a759-281">Open the **Startup.cs** file, and locate the following lines:</span></span>

   ```c#
        #if USE_TEST_KEYS
        #error !!!!!!!!!!!!!!!!!!!!!! Use of test keys is only supported for testing,
        DO NOT USE  FOR PRODUCTION !!!!!!!!!!!!!!!!!!!!!!!!!!!!!
        services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
        #endif
   ```

1. <span data-ttu-id="1a759-282">将这些行替换为以下文本：</span><span class="sxs-lookup"><span data-stu-id="1a759-282">Replace these lines with the following text:</span></span>

   ```csharp
   services.AddSingleton<ippw.IKeyStore, ippw.TestKeyStore>();
   ```

   <span data-ttu-id="1a759-283">最终结果应如下图所示。</span><span class="sxs-lookup"><span data-stu-id="1a759-283">The end results should look similar to the following picture.</span></span>

   :::image type="content" source="../media/dke-startupcs-usetestkeys.png" alt-text="用于公共预览的 startup.cs 文件":::

<span data-ttu-id="1a759-285">现在，你已准备好[生成 DKE 项目](#build-the-project)。</span><span class="sxs-lookup"><span data-stu-id="1a759-285">Now you're ready to [build your DKE project](#build-the-project).</span></span>

### <a name="build-the-project"></a><span data-ttu-id="1a759-286">生成项目</span><span class="sxs-lookup"><span data-stu-id="1a759-286">Build the project</span></span>

<span data-ttu-id="1a759-287">使用以下说明在本地生成 DKE 项目：</span><span class="sxs-lookup"><span data-stu-id="1a759-287">Use the following instructions to build the DKE project locally:</span></span>

1. <span data-ttu-id="1a759-288">在 Visual Studio Code 中，在 DKE 服务存储库中，选择 "**查看** \> **命令组件面板**"，然后在提示符处键入**build** 。</span><span class="sxs-lookup"><span data-stu-id="1a759-288">In Visual Studio Code, in the DKE service repository, select **View** \> **Command Palette** and then type **build** at the prompt.</span></span>

1. <span data-ttu-id="1a759-289">从列表中选择 "**任务：运行生成任务**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-289">From the list, choose **Tasks: Run build task**.</span></span>

   <span data-ttu-id="1a759-290">如果找不到任何生成任务，请选择 "**配置生成任务**并为 .net core 创建一个"，如下所示。</span><span class="sxs-lookup"><span data-stu-id="1a759-290">If there are no build tasks found, select **Configure Build Task** and create one for .NET core as follows.</span></span>

   :::image type="content" source="../media/dke-configurebuildtask.png" alt-text="为 .NET 配置缺少的生成任务":::

   1. <span data-ttu-id="1a759-292">**从模板中选择 "创建 tasks.js"**。</span><span class="sxs-lookup"><span data-stu-id="1a759-292">Choose **Create tasks.json from template**.</span></span>

   :::image type="content" source="../media/dke-createtasksjsonfromtemplate.png" alt-text="从 DKE 的模板创建对文件的 tasks.js":::

   2. <span data-ttu-id="1a759-294">从模板类型列表中，选择 " **.Net Core**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-294">From the list of template types, select **.NET Core**.</span></span>

   :::image type="content" source="../media/dke-tasksjsontemplate.png" alt-text="从 DKE 的模板创建对文件的 tasks.js":::

   3. <span data-ttu-id="1a759-296">在 "生成" 部分，找到**customerkeystore**文件的路径。</span><span class="sxs-lookup"><span data-stu-id="1a759-296">In the build section, locate the path to the **customerkeystore.csproj** file.</span></span> <span data-ttu-id="1a759-297">如果没有，则添加以下行：</span><span class="sxs-lookup"><span data-stu-id="1a759-297">If it's not there, add the following line:</span></span>

      ```json
      "${workspaceFolder}/src/customer-key-store/customerkeystore.csproj",
      ```

  4. <span data-ttu-id="1a759-298">再次运行生成。</span><span class="sxs-lookup"><span data-stu-id="1a759-298">Run the build again.</span></span>

1. <span data-ttu-id="1a759-299">确认输出窗口中没有红色错误。</span><span class="sxs-lookup"><span data-stu-id="1a759-299">Verify that there are no red errors in the output window.</span></span>

   <span data-ttu-id="1a759-300">如果出现红色错误，请检查控制台输出。</span><span class="sxs-lookup"><span data-stu-id="1a759-300">If there are red errors, check the console output.</span></span> <span data-ttu-id="1a759-301">确保您已正确完成上述所有步骤，并且存在正确的生成版本。</span><span class="sxs-lookup"><span data-stu-id="1a759-301">Ensure that you completed all the previous steps correctly and the correct build versions are present.</span></span>

1. <span data-ttu-id="1a759-302">**运行** \>**启动调试**以调试进程。</span><span class="sxs-lookup"><span data-stu-id="1a759-302">**Run** \> **Start Debugging** to debug the process.</span></span> <span data-ttu-id="1a759-303">如果系统提示您选择环境，请选择 " **.net core**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-303">If you're prompted to select an environment, select **.NET core**.</span></span>

<span data-ttu-id="1a759-304">.NET core 调试器通常会启动到 **https://localhost:5001** 。</span><span class="sxs-lookup"><span data-stu-id="1a759-304">The .NET core debugger typically launches to **https://localhost:5001**.</span></span> <span data-ttu-id="1a759-305">若要查看测试项，请转到 **https://localhost:5001** ，并追加一个正斜杠（/）和键的名称。</span><span class="sxs-lookup"><span data-stu-id="1a759-305">To view your test key, go to **https://localhost:5001**, and append a forward slash (/) and the name of your key.</span></span>

<span data-ttu-id="1a759-306">例如：**https://localhost:5001/TestKey1**</span><span class="sxs-lookup"><span data-stu-id="1a759-306">For example: **https://localhost:5001/TestKey1**</span></span>

<span data-ttu-id="1a759-307">该项应以 JSON 格式显示。</span><span class="sxs-lookup"><span data-stu-id="1a759-307">The key should display in JSON format.</span></span>

<span data-ttu-id="1a759-308">你的设置现已完成。</span><span class="sxs-lookup"><span data-stu-id="1a759-308">Your setup is now complete.</span></span> <span data-ttu-id="1a759-309">在发布密钥库之前，在 appsettings.js的 JwtAudience 设置中，确保主机名的值与您的应用程序服务主机名称完全匹配。</span><span class="sxs-lookup"><span data-stu-id="1a759-309">Before you publish the keystore, in appsettings.json, for the JwtAudience setting, ensure the value for hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="1a759-310">您可能已将其更改为 localhost 以对生成进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="1a759-310">You may have changed it to localhost to troubleshoot the build.</span></span>

### <a name="publish-the-key-store"></a><span data-ttu-id="1a759-311">发布密钥存储</span><span class="sxs-lookup"><span data-stu-id="1a759-311">Publish the key store</span></span>

<span data-ttu-id="1a759-312">以下步骤介绍如何创建 Azure 应用服务实例以托管 DKE 部署，以及如何将生成的密钥发布到 Azure。</span><span class="sxs-lookup"><span data-stu-id="1a759-312">The following steps describe how to create an Azure App Service instance to host your DKE deployment, and how to publish your generated keys to Azure.</span></span>

<span data-ttu-id="1a759-313">创建 Azure Web 应用程序实例以托管你的 DKE 部署：</span><span class="sxs-lookup"><span data-stu-id="1a759-313">To create an Azure Web App instance to host your DKE deployment:</span></span>

1. <span data-ttu-id="1a759-314">在浏览器中，登录到[Microsoft Azure 门户](https://ms.portal.azure.com)，然后转到 "**应用程序服务**" "  >  **添加**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-314">In your browser, sign in to the [Microsoft Azure portal](https://ms.portal.azure.com), and go to **App Services** > **Add**.</span></span>

1. <span data-ttu-id="1a759-315">选择订阅和资源组，并定义实例详细信息。</span><span class="sxs-lookup"><span data-stu-id="1a759-315">Select your subscription and resource group and define your instance details.</span></span>

    - <span data-ttu-id="1a759-316">输入要安装 DKE 服务的计算机的主机名。</span><span class="sxs-lookup"><span data-stu-id="1a759-316">Enter the hostname of the computer where you want to install the DKE service.</span></span> <span data-ttu-id="1a759-317">请确保它与在[**appsettings.json**](#tenant-and-key-settings) file 中为 JwtAudience 设置定义的名称相同。</span><span class="sxs-lookup"><span data-stu-id="1a759-317">Make sure it's the same name as the one defined for the JwtAudience setting in the [**appsettings.json**](#tenant-and-key-settings) file.</span></span> <span data-ttu-id="1a759-318">您为名称提供的值也是 WebAppInstanceName。</span><span class="sxs-lookup"><span data-stu-id="1a759-318">The value you provide for the name is also the WebAppInstanceName.</span></span>

    - <span data-ttu-id="1a759-319">对于 "**发布**"、"选择**代码**" 和 "**运行时堆栈**"，选择 " **.net Core 3.1**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-319">For **Publish**, select **code**, and for **Runtime stack**, select **.NET Core 3.1**.</span></span>

    <span data-ttu-id="1a759-320">例如：</span><span class="sxs-lookup"><span data-stu-id="1a759-320">For example:</span></span>

    :::image type="content" source="../media/dke-azure-add-app-service.png" alt-text="添加应用服务":::

1. <span data-ttu-id="1a759-322">在页面底部，选择 "**审阅 + 创建**"，然后选择 "**添加**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-322">At the bottom of the page, select **Review + create**, and then select **Add**.</span></span>

1. <span data-ttu-id="1a759-323">执行以下操作之一，将生成的密钥发布到 Azure：</span><span class="sxs-lookup"><span data-stu-id="1a759-323">Do one of the following to publish your generated keys to Azure:</span></span>

    - [<span data-ttu-id="1a759-324">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="1a759-324">Publish via ZipDeployUI</span></span>](#publish-via-zipdeployui)
    - [<span data-ttu-id="1a759-325">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="1a759-325">Publish via FTP</span></span>](#publish-via-ftp)
    - [<span data-ttu-id="1a759-326">通过 Visual Studio 2019 或更高版本发布</span><span class="sxs-lookup"><span data-stu-id="1a759-326">Publish via Visual Studio 2019 or later</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/)
    - [<span data-ttu-id="1a759-327">发布到本地系统</span><span class="sxs-lookup"><span data-stu-id="1a759-327">Publish to an on-premises system</span></span>](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)

    > [!NOTE]
    > <span data-ttu-id="1a759-328">您可能更喜欢部署密钥的其他方法。</span><span class="sxs-lookup"><span data-stu-id="1a759-328">You may prefer other methods to deploy your keys.</span></span> <span data-ttu-id="1a759-329">选择最适合您的组织的方法。</span><span class="sxs-lookup"><span data-stu-id="1a759-329">Select the method that works best for your organization.</span></span>

    > [!TIP]
    > <span data-ttu-id="1a759-330">[ASP .net 文档](https://docs.microsoft.com/aspnet/core/)中介绍了如何[通过 Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/)和[本地系统](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli)发布。</span><span class="sxs-lookup"><span data-stu-id="1a759-330">[Publishing via Visual Studio](https://docs.microsoft.com/aspnet/core/tutorials/) and to an [on-premises system](https://docs.microsoft.com/aspnet/core/tutorials/publish-to-iis?view=aspnetcore-3.1&tabs=netcore-cli) is described in the [ASP .NET documentation](https://docs.microsoft.com/aspnet/core/).</span></span> <span data-ttu-id="1a759-331">如果使用其中一种方法，请在单独的选项卡中打开说明，以便在完成后可以轻松地返回此处。</span><span class="sxs-lookup"><span data-stu-id="1a759-331">If you use one of these methods, open the instructions in a separate tab so that you can return here easily when you're done.</span></span>

#### <a name="publish-via-zipdeployui"></a><span data-ttu-id="1a759-332">通过 ZipDeployUI 发布</span><span class="sxs-lookup"><span data-stu-id="1a759-332">Publish via ZipDeployUI</span></span>

1. <span data-ttu-id="1a759-333">转到 `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`。</span><span class="sxs-lookup"><span data-stu-id="1a759-333">Go to `https://<WebAppInstanceName>.scm.azurewebsites.net/ZipDeployUI`.</span></span>

    <span data-ttu-id="1a759-334">例如：https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="1a759-334">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

1. <span data-ttu-id="1a759-335">在密钥存储的基本代码中，转到 " **customer-key-store\src\customer-key-store** " 文件夹，并验证此文件夹是否包含**customerkeystore**文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-335">In the codebase for the key store, go to the **customer-key-store\src\customer-key-store** folder, and verify that this folder contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="1a759-336">运行： **dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="1a759-336">Run: **dotnet publish**</span></span>

     <span data-ttu-id="1a759-337">"输出" 窗口显示部署发布的目录。</span><span class="sxs-lookup"><span data-stu-id="1a759-337">The output window displays the directory where the publish was deployed.</span></span>

    <span data-ttu-id="1a759-338">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="1a759-338">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="1a759-339">将发布目录中的所有文件发送到 .zip 文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-339">Send all files in the publish directory to a .zip file.</span></span> <span data-ttu-id="1a759-340">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="1a759-340">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="1a759-341">将您创建的 .zip 文件拖放到您在上面打开的 ZipDeployUI 网站上。</span><span class="sxs-lookup"><span data-stu-id="1a759-341">Drag and drop the .zip file you create to the ZipDeployUI site you opened above.</span></span> <span data-ttu-id="1a759-342">例如：https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span><span class="sxs-lookup"><span data-stu-id="1a759-342">For example: https://customerkeystoreforpublicpreview.scm.azurewebsites.net/ZipDeployUI</span></span>

<span data-ttu-id="1a759-343">DKE 已部署，您可以浏览到已创建的测试键。</span><span class="sxs-lookup"><span data-stu-id="1a759-343">DKE is deployed and you can browse to the test keys you've created.</span></span> <span data-ttu-id="1a759-344">继续验证下面的[部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="1a759-344">Continue to [Validate your deployment](#validate-your-deployment) below.</span></span>

#### <a name="publish-via-ftp"></a><span data-ttu-id="1a759-345">通过 FTP 发布</span><span class="sxs-lookup"><span data-stu-id="1a759-345">Publish via FTP</span></span>

1. <span data-ttu-id="1a759-346">连接到您在[上面](#publish-the-key-store)创建的应用程序服务。</span><span class="sxs-lookup"><span data-stu-id="1a759-346">Connect to the App Service you created [above](#publish-the-key-store).</span></span>

    <span data-ttu-id="1a759-347">在浏览器中，转到： **Azure portal**  >  **App Service**  >  **部署中心**  >  的**手动部署**  >  **FTP**  >  **仪表板**。</span><span class="sxs-lookup"><span data-stu-id="1a759-347">In your browser, go to: **Azure portal** > **App Service** > **Deployment Center** > **Manual Deployment** > **FTP** > **Dashboard**.</span></span>

1. <span data-ttu-id="1a759-348">将显示的连接字符串复制到本地文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-348">Copy the connection strings displayed to a local file.</span></span> <span data-ttu-id="1a759-349">您将使用这些字符串连接到 Web 应用服务，并通过 FTP 上载文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-349">You'll use these strings to connect to the Web App Service and upload files via FTP.</span></span>

    <span data-ttu-id="1a759-350">例如：</span><span class="sxs-lookup"><span data-stu-id="1a759-350">For example:</span></span>

    :::image type="content" source="../media/dke-ftp-dashboard.png" alt-text="从 FTP 仪表板复制连接字符串":::

1. <span data-ttu-id="1a759-352">在密钥存储的基本代码中，转到**customer-key-store\src\customer-key-store 目录**。</span><span class="sxs-lookup"><span data-stu-id="1a759-352">In the codebase for the key storage, go to the **customer-key-store\src\customer-key-store directory**.</span></span>

1. <span data-ttu-id="1a759-353">验证此目录是否包含**customerkeystore**文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-353">Verify that this directory contains the **customerkeystore.csproj** file.</span></span>

1. <span data-ttu-id="1a759-354">运行： **dotnet 发布**</span><span class="sxs-lookup"><span data-stu-id="1a759-354">Run: **dotnet publish**</span></span>

    <span data-ttu-id="1a759-355">输出包含部署发布的目录。</span><span class="sxs-lookup"><span data-stu-id="1a759-355">The output contains the directory where the publish was deployed.</span></span>

    <span data-ttu-id="1a759-356">例如：`customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span><span class="sxs-lookup"><span data-stu-id="1a759-356">For example: `customer-key-store\src\customer-key-store\bin\Debug\netcoreapp3.1\publish\`</span></span>

1. <span data-ttu-id="1a759-357">将发布目录中的所有文件发送到 zip 文件。</span><span class="sxs-lookup"><span data-stu-id="1a759-357">Send all files in the publish directory to a zip file.</span></span> <span data-ttu-id="1a759-358">创建 .zip 文件时，请确保目录中的所有文件都位于 .zip 文件的根级别。</span><span class="sxs-lookup"><span data-stu-id="1a759-358">When creating the .zip file, make sure that all files in the directory are at the root level of the .zip file.</span></span>

1. <span data-ttu-id="1a759-359">从你的 FTP 客户端，使用复制的连接信息连接到应用服务。</span><span class="sxs-lookup"><span data-stu-id="1a759-359">From your FTP client, use the connection information you copied to connect to your App Service.</span></span> <span data-ttu-id="1a759-360">将您在上一步中创建的 .zip 文件上载到 Web 应用程序的根目录。</span><span class="sxs-lookup"><span data-stu-id="1a759-360">Upload the .zip file you created in the previous step to the root directory of your Web App.</span></span>

<span data-ttu-id="1a759-361">DKE 已部署，您可以浏览到已创建的测试键。</span><span class="sxs-lookup"><span data-stu-id="1a759-361">DKE is deployed and you can browse to the test keys you'd created.</span></span> <span data-ttu-id="1a759-362">接下来，[验证您的部署](#validate-your-deployment)。</span><span class="sxs-lookup"><span data-stu-id="1a759-362">Next, [Validate your deployment](#validate-your-deployment).</span></span>

### <a name="validate-your-deployment"></a><span data-ttu-id="1a759-363">验证部署</span><span class="sxs-lookup"><span data-stu-id="1a759-363">Validate your deployment</span></span>

<span data-ttu-id="1a759-364">使用上述方法之一部署 DKE 后，请验证部署和密钥存储设置。</span><span class="sxs-lookup"><span data-stu-id="1a759-364">After deploying DKE using one of the methods described above, validate the deployment and the key store settings.</span></span>

<span data-ttu-id="1a759-365">以</span><span class="sxs-lookup"><span data-stu-id="1a759-365">Run:</span></span>

<span data-ttu-id="1a759-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span><span class="sxs-lookup"><span data-stu-id="1a759-366">src\customer-key-store\scripts\key_store_tester.ps1 mykeystoreurl/mykey</span></span>

<span data-ttu-id="1a759-367">例如：</span><span class="sxs-lookup"><span data-stu-id="1a759-367">For example:</span></span>

<span data-ttu-id="1a759-368">key_store_tester.ps1https://mycustomerkeystore.com/mykey</span><span class="sxs-lookup"><span data-stu-id="1a759-368">key_store_tester.ps1 https://mycustomerkeystore.com/mykey</span></span>

<span data-ttu-id="1a759-369">确保输出中不显示任何错误。</span><span class="sxs-lookup"><span data-stu-id="1a759-369">Ensure that no errors appear in the output.</span></span> <span data-ttu-id="1a759-370">准备好后，[注册你的密钥存储](#register-your-key-store)。</span><span class="sxs-lookup"><span data-stu-id="1a759-370">When you're ready, [register your key store](#register-your-key-store).</span></span>

## <a name="register-your-key-store"></a><span data-ttu-id="1a759-371">注册密钥存储</span><span class="sxs-lookup"><span data-stu-id="1a759-371">Register your key store</span></span>

<span data-ttu-id="1a759-372">以下步骤使您能够注册密钥存储区。</span><span class="sxs-lookup"><span data-stu-id="1a759-372">The following steps enable you to register your key store.</span></span> <span data-ttu-id="1a759-373">注册密钥存储是部署 DKE 之前的最后一步，您可以开始创建标签。</span><span class="sxs-lookup"><span data-stu-id="1a759-373">Registering your key store is the last step in deploying DKE before you can start creating labels.</span></span>

<span data-ttu-id="1a759-374">注册密钥存储区：</span><span class="sxs-lookup"><span data-stu-id="1a759-374">To register your key store:</span></span>

1. <span data-ttu-id="1a759-375">在浏览器中，打开[Microsoft Azure 门户](https://ms.portal.azure.com/)，并转到 "**所有服务** \> **标识** \> **应用注册**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-375">In your browser, open the [Microsoft Azure portal](https://ms.portal.azure.com/), and go to **All Services** \> **Identity** \> **App Registrations**.</span></span>

2. <span data-ttu-id="1a759-376">选择 "**新建注册**"，并输入有意义的名称。</span><span class="sxs-lookup"><span data-stu-id="1a759-376">Select **New registration**, and enter a meaningful name.</span></span>

3. <span data-ttu-id="1a759-377">从显示的选项中选择一个帐户类型。</span><span class="sxs-lookup"><span data-stu-id="1a759-377">Select an account type from the options displayed.</span></span>

    <span data-ttu-id="1a759-378">如果使用的是具有非自定义域的 Microsoft Azure （如**onmicrosoft.com**），请选择 "**仅限此组织目录中的帐户（仅限 Microsoft-单一租户）"。**</span><span class="sxs-lookup"><span data-stu-id="1a759-378">If you're using Microsoft Azure with a non-custom domain, such as **onmicrosoft.com**, select **Accounts in this organizational directory only (Microsoft only - Single tenant).**</span></span>

    <span data-ttu-id="1a759-379">例如：</span><span class="sxs-lookup"><span data-stu-id="1a759-379">For example:</span></span>

    :::image type="content" source="../media/dke-app-registration.png" alt-text="新应用注册":::

4. <span data-ttu-id="1a759-381">在页面底部，选择 "**注册**" 以创建新的应用注册。</span><span class="sxs-lookup"><span data-stu-id="1a759-381">At the bottom of the page, select **Register** to create the new App Registration.</span></span>

5. <span data-ttu-id="1a759-382">在新的应用注册中，在左窗格中的 "**管理**" 下，选择 "**身份验证**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-382">In your new App Registration, in the left pane, under **Manage**, select **Authentication**.</span></span>

6. <span data-ttu-id="1a759-383">选择 "**添加平台**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-383">Select **Add a platform**.</span></span>
 
7. <span data-ttu-id="1a759-384">在 "**配置平台**" 弹出菜单中选择 " **Web**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-384">On the **Configure platforms** popup select **Web**.</span></span>
 
8. <span data-ttu-id="1a759-385">在 "**重定向 uri** " 下，输入您的双密钥加密服务的 URI。</span><span class="sxs-lookup"><span data-stu-id="1a759-385">Under **Redirect URIs** enter the URI of your double key encryption service.</span></span> <span data-ttu-id="1a759-386">输入应用服务 URL，包括主机名和域。</span><span class="sxs-lookup"><span data-stu-id="1a759-386">Enter the App Service URL, including both the hostname and domain.</span></span>

    <span data-ttu-id="1a759-387">例如：https://mycustomerkeystoretest.com</span><span class="sxs-lookup"><span data-stu-id="1a759-387">For example: https://mycustomerkeystoretest.com</span></span>

    - <span data-ttu-id="1a759-388">输入的 URL 必须与用于部署密钥存储的主机名称相匹配。</span><span class="sxs-lookup"><span data-stu-id="1a759-388">The URL you enter must match the hostname where your key store is deployed.</span></span>
    - <span data-ttu-id="1a759-389">如果您正在使用 Visual Studio 进行本地测试，请使用 **https://localhost:5001** 。</span><span class="sxs-lookup"><span data-stu-id="1a759-389">If you're testing locally with Visual Studio, use **https://localhost:5001**.</span></span>
    - <span data-ttu-id="1a759-390">在所有情况下，方案都必须是**https**。</span><span class="sxs-lookup"><span data-stu-id="1a759-390">In all cases, the scheme must be **https**.</span></span>

    <span data-ttu-id="1a759-391">确保主机名与应用服务主机名称完全匹配。</span><span class="sxs-lookup"><span data-stu-id="1a759-391">Ensure the hostname exactly matches your App Service host name.</span></span> <span data-ttu-id="1a759-392">您可能已将其更改为 localhost 以对生成进行故障排除。</span><span class="sxs-lookup"><span data-stu-id="1a759-392">You may have changed it to localhost to troubleshoot the build.</span></span> <span data-ttu-id="1a759-393">在 appsettings.js上，这是您标识为 JwtAudience 设置的值的主机名。</span><span class="sxs-lookup"><span data-stu-id="1a759-393">In appsettings.json, this is the hostname you identified as the value for the JwtAudience setting.</span></span>

6. <span data-ttu-id="1a759-394">在 "**隐式授予**" 下，选中 " **ID 令牌**" 复选框。</span><span class="sxs-lookup"><span data-stu-id="1a759-394">Under **Implicit grant**, select the **ID tokens** checkbox.</span></span>

1. <span data-ttu-id="1a759-395">选择“**保存**”以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1a759-395">Select **Save** to save your changes.</span></span>

7. <span data-ttu-id="1a759-396">在左窗格中，选择 "**公开 API**"，然后选择 "应用程序 ID URI" 旁边的 "**设置**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-396">On the left pane, select **Expose an API**, then next to Application ID URI, select **Set**.</span></span>

9. <span data-ttu-id="1a759-397">在 "**公开一个 API** " 页上的 "**此 Api 定义的作用域**" 中，选择 "**添加范围**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-397">Still on the **Expose an API** page, in the **Scopes defined by this API** area, select **Add a scope**.</span></span> <span data-ttu-id="1a759-398">在新作用域中：</span><span class="sxs-lookup"><span data-stu-id="1a759-398">In the new scope:</span></span>

    1. <span data-ttu-id="1a759-399">将范围名称定义为**user_impersonation**。</span><span class="sxs-lookup"><span data-stu-id="1a759-399">Define the scope name as **user_impersonation**.</span></span>

    2. <span data-ttu-id="1a759-400">选择可以同意的管理员和用户。</span><span class="sxs-lookup"><span data-stu-id="1a759-400">Select the administrators and users who can consent.</span></span>

    3. <span data-ttu-id="1a759-401">定义所需的任何剩余值。</span><span class="sxs-lookup"><span data-stu-id="1a759-401">Define any remaining values required.</span></span>

    4. <span data-ttu-id="1a759-402">选择 "**添加范围"。**</span><span class="sxs-lookup"><span data-stu-id="1a759-402">Select **Add scope.**</span></span>

    <span data-ttu-id="1a759-403">选择顶部的 "**保存**" 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1a759-403">Select **Save** at the top to save your changes.</span></span>

10. <span data-ttu-id="1a759-404">仍在 "**公开 API** " 页上的 "**授权客户端应用程序**" 区域中，选择 "**添加客户端应用程序**"。</span><span class="sxs-lookup"><span data-stu-id="1a759-404">Still on the **Expose an API** page, in the **Authorized client applications** area, select **Add a client application**.</span></span>

    <span data-ttu-id="1a759-405">在新的客户端应用程序中：</span><span class="sxs-lookup"><span data-stu-id="1a759-405">In the new client application:</span></span>

    1. <span data-ttu-id="1a759-406">将客户端 ID 定义为**d3590ed6-52b3-4102-aeff-aad2292ab01c**。</span><span class="sxs-lookup"><span data-stu-id="1a759-406">Define the Client ID as **d3590ed6-52b3-4102-aeff-aad2292ab01c**.</span></span> <span data-ttu-id="1a759-407">此值是 Microsoft Office 客户端 ID，它使 Office 能够获取密钥存储的访问令牌。</span><span class="sxs-lookup"><span data-stu-id="1a759-407">This value is the Microsoft Office client ID, and enables Office to obtain an access token for your key store.</span></span>

    2. <span data-ttu-id="1a759-408">在 "**授权范围**" 下，选择 " **user_impersonation** " 范围。</span><span class="sxs-lookup"><span data-stu-id="1a759-408">Under **Authorized scopes**, select the **user_impersonation** scope.</span></span>

    3. <span data-ttu-id="1a759-409">选择“添加应用程序”\*\*\*\*。</span><span class="sxs-lookup"><span data-stu-id="1a759-409">Select **Add application**.</span></span>

    4. <span data-ttu-id="1a759-410">选择顶部的 "**保存**" 以保存所做的更改。</span><span class="sxs-lookup"><span data-stu-id="1a759-410">Select **Save** at the top to save your changes.</span></span>

<span data-ttu-id="1a759-411">您的 DKE 密钥存储现已注册。</span><span class="sxs-lookup"><span data-stu-id="1a759-411">Your DKE key store is now registered.</span></span> <span data-ttu-id="1a759-412">继续操作，方法是[使用 DKE 创建标签](#create-labels-using-dke)。</span><span class="sxs-lookup"><span data-stu-id="1a759-412">Continue  by [creating labels using DKE](#create-labels-using-dke).</span></span>

## <a name="create-labels-using-dke"></a><span data-ttu-id="1a759-413">使用 DKE 创建标签</span><span class="sxs-lookup"><span data-stu-id="1a759-413">Create labels using DKE</span></span>

<span data-ttu-id="1a759-414">注册密钥存储后，请在 Microsoft 365 合规性中心中设置灵敏度标签，并对这些标签应用双重密钥加密。</span><span class="sxs-lookup"><span data-stu-id="1a759-414">Once you've registered your key store, set up sensitivity labels in the Microsoft 365 compliance center and apply double key encryption to those labels.</span></span>

<span data-ttu-id="1a759-415">在 "标签创建" UI 中，选择 "**使用双密钥加密**" 选项并输入密钥的终结点 URL。</span><span class="sxs-lookup"><span data-stu-id="1a759-415">In the label creation UI, select the **Use Double Key Encryption** option and enter the endpoint URL for your key.</span></span>

<span data-ttu-id="1a759-416">例如：</span><span class="sxs-lookup"><span data-stu-id="1a759-416">For example:</span></span>

:::image type="content" source="../media/dke-use-dke.png" alt-text="在 Microsoft 365 合规性中心中选择 "使用双重密钥加密"":::

<span data-ttu-id="1a759-418">您添加的任何 DKE 标签将为适用于企业的 Microsoft 365 应用程序的最新版本中的用户显示。</span><span class="sxs-lookup"><span data-stu-id="1a759-418">Any DKE labels you add will start appearing for users in the latest versions of Microsoft 365 Apps for enterprise.</span></span>

> [!NOTE]
> <span data-ttu-id="1a759-419">客户端可能需要长达24小时才能使用新标签进行刷新。</span><span class="sxs-lookup"><span data-stu-id="1a759-419">It may take up to 24 hours for the clients to refresh with the new labels.</span></span>

### <a name="enable-dke-in-your-client"></a><span data-ttu-id="1a759-420">在客户端中启用 DKE</span><span class="sxs-lookup"><span data-stu-id="1a759-420">Enable DKE in your client</span></span>

<span data-ttu-id="1a759-421">如果 Microsoft Office 中的灵敏度功能区下未显示您的 DKE 标签，则您的客户端可能未启用 DKE。</span><span class="sxs-lookup"><span data-stu-id="1a759-421">If your DKE labels don't appear under the Sensitivity ribbon in Microsoft Office, your client may not have DKE enabled.</span></span>

<span data-ttu-id="1a759-422">通过添加以下注册表项为你的客户端启用 DKE：</span><span class="sxs-lookup"><span data-stu-id="1a759-422">Enable DKE for your client by adding the following registry keys:</span></span>

```ini
    [HKEY_LOCAL_MACHINE\SOFTWARE\WOW6432Node\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001

    [HKEY_LOCAL_MACHINE\SOFTWARE\Microsoft\MSIPC\flighting]
    "DoubleKeyProtection"=dword:00000001
```
