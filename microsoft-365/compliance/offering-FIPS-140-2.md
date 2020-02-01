---
title: 联邦信息处理标准（FIPS）发布140-2
description: Microsoft 证明其加密模块符合美国联邦信息处理标准。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
f1.keywords:
- NOCSH
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: 700c5c9892d5cd04f3f56bf1f3d498cf5d2467af
ms.sourcegitcommit: 1c91b7b24537d0e54d484c3379043db53c1aea65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/29/2020
ms.locfileid: "41602389"
---
# <a name="federal-information-processing-standard-fips-publication-140-2"></a><span data-ttu-id="80d51-104">联邦信息处理标准（FIPS）发布140-2</span><span class="sxs-lookup"><span data-stu-id="80d51-104">Federal Information Processing Standard (FIPS) Publication 140-2</span></span>

## <a name="fips-140-2-standard-overview"></a><span data-ttu-id="80d51-105">FIPS 140-2 标准概述</span><span class="sxs-lookup"><span data-stu-id="80d51-105">FIPS 140-2 standard overview</span></span>

<span data-ttu-id="80d51-106">联邦信息处理标准（FIPS）发布140-2 是一项美国政府标准，定义了信息技术产品中的加密模块的最低安全要求，如信息的第5131节中所定义。技术管理改革法案1996。</span><span class="sxs-lookup"><span data-stu-id="80d51-106">The Federal Information Processing Standard (FIPS) Publication 140-2 is a U.S. government standard that defines minimum security requirements for cryptographic modules in information technology products, as defined in Section 5131 of the Information Technology Management Reform Act of 1996.</span></span>

<span data-ttu-id="80d51-107">[加密模块验证程序](https://csrc.nist.gov/Projects/cryptographic-module-validation-program)（CMVP）（美国国家标准和技术协会（NIST）和加拿大中心网络安全（CCCS）的联合努力将加密模块验证为加密模块标准（即 FIPS 140-2）和相关 FIPS 加密标准的*安全要求*。</span><span class="sxs-lookup"><span data-stu-id="80d51-107">The [Cryptographic Module Validation Program](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) (CMVP), a joint effort of the U.S. National Institute of Standards and Technology (NIST) and the Canadian Centre for Cyber Security (CCCS), validates cryptographic modules to the *Security Requirements for Cryptographic Modules* standard (i.e., FIPS 140-2) and related FIPS cryptography standards.</span></span> <span data-ttu-id="80d51-108">FIPS 140-2 安全要求涵盖了与加密模块的设计和实现相关的11个方面。</span><span class="sxs-lookup"><span data-stu-id="80d51-108">The FIPS 140-2 security requirements cover 11 areas related to the design and implementation of a cryptographic module.</span></span> <span data-ttu-id="80d51-109">NIST 信息技术实验室运行一个相关的程序来验证模块中的 FIPS 批准的加密算法。</span><span class="sxs-lookup"><span data-stu-id="80d51-109">The NIST Information Technology Laboratory operates a related program that validates the FIPS approved cryptographic algorithms in the module.</span></span>

## <a name="microsofts-approach-to-fips-140-2-validation"></a><span data-ttu-id="80d51-110">Microsoft 对 FIPS 140-2 验证的方法</span><span class="sxs-lookup"><span data-stu-id="80d51-110">Microsoft’s approach to FIPS 140-2 validation</span></span>

<span data-ttu-id="80d51-111">Microsoft 保持积极的承诺来满足140-2 的要求，由于标准是在2001中开始，因此已验证了加密模块。</span><span class="sxs-lookup"><span data-stu-id="80d51-111">Microsoft maintains an active commitment to meeting the 140-2 requirements, having validated cryptographic modules since the standard’s inception in 2001.</span></span> <span data-ttu-id="80d51-112">Microsoft 验证其在美国国家标准和技术协会（NIST）[加密模块验证程序](https://csrc.nist.gov/Projects/cryptographic-module-validation-program)（CMVP）下的加密模块。</span><span class="sxs-lookup"><span data-stu-id="80d51-112">Microsoft validates its cryptographic modules under the National Institute of Standards and Technology (NIST) [Cryptographic Module Validation Program](https://csrc.nist.gov/Projects/cryptographic-module-validation-program) (CMVP).</span></span> <span data-ttu-id="80d51-113">多个 Microsoft 产品（包括许多云服务）使用这些加密模块。</span><span class="sxs-lookup"><span data-stu-id="80d51-113">Multiple Microsoft products, including many cloud services, use these cryptographic modules.</span></span>

<span data-ttu-id="80d51-114">有关 Microsoft Windows 加密模块的技术信息、每个模块的安全策略以及 CMVP 证书详细信息的目录，请参阅[windows 和 Windows SERVER FIPS 140-2 内容](https://aka.ms/AA6ehud)。</span><span class="sxs-lookup"><span data-stu-id="80d51-114">For technical information on Microsoft Windows cryptographic modules, the security policy for each module, and the catalog of CMVP certificate details, see the [Windows and Windows Server FIPS 140-2 content](https://aka.ms/AA6ehud).</span></span>

## <a name="microsoft-in-scope-cloud-services"></a><span data-ttu-id="80d51-115">Microsoft 范围内云服务</span><span class="sxs-lookup"><span data-stu-id="80d51-115">Microsoft in-scope cloud services</span></span>

<span data-ttu-id="80d51-116">当前 CMVP FIPS 140-2 实施指南排除了云服务本身的 FIPS 140-2 验证;云服务提供商可以选择为构成云服务的计算元素获取并运行 FIPS 140 验证的加密模块。</span><span class="sxs-lookup"><span data-stu-id="80d51-116">While the current CMVP FIPS 140-2 implementation guidance precludes a FIPS 140-2 validation for a cloud service itself; cloud service providers can choose to obtain and operate FIPS 140 validated cryptographic modules for the computing elements that comprise their cloud service.</span></span> <span data-ttu-id="80d51-117">Microsoft online services 包括已验证 FIPS 140-2 的组件，其中包括：</span><span class="sxs-lookup"><span data-stu-id="80d51-117">Microsoft online services that include components, which have been FIPS 140-2 validated include, among others:</span></span>

- [<span data-ttu-id="80d51-118">Azure 与 Azure 政府</span><span class="sxs-lookup"><span data-stu-id="80d51-118">Azure and Azure Government</span></span>](https://docs.microsoft.com/azure/azure-government/documentation-government-plan-security)
- [<span data-ttu-id="80d51-119">Dynamics 365 和 Dynamics 365 政府</span><span class="sxs-lookup"><span data-stu-id="80d51-119">Dynamics 365 and Dynamics 365 Government</span></span>](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-microsoft-dynamics-365)
- [<span data-ttu-id="80d51-120">Office 365、Office 365 美国政府版和 Office 365 美国政府版防御</span><span class="sxs-lookup"><span data-stu-id="80d51-120">Office 365, Office 365 U.S. Government, and Office 365 U.S. Government Defense</span></span>](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections)

## <a name="frequently-asked-questions"></a><span data-ttu-id="80d51-121">常见问题解答</span><span class="sxs-lookup"><span data-stu-id="80d51-121">Frequently asked questions</span></span>

<span data-ttu-id="80d51-122">**"FIPS 140 验证" 和 "FIPS 140 兼容" 的区别是什么？**</span><span class="sxs-lookup"><span data-stu-id="80d51-122">**What is the difference between “FIPS 140 Validated” and “FIPS 140 compliant”?**</span></span>

<span data-ttu-id="80d51-123">"FIPS 140 已验证" 表示加密模块或嵌入模块的产品已由 CMVP 进行了验证（"认证"），以满足 FIPS 140-2 的要求。</span><span class="sxs-lookup"><span data-stu-id="80d51-123">“FIPS 140 Validated” means that the cryptographic module, or a product that embeds the module has been validated (“certified”) by the CMVP as meeting the FIPS 140-2 requirements.</span></span> <span data-ttu-id="80d51-124">"FIPS 140 合规" 是 IT 产品的一项行业术语，它依赖于 FIPS 140 验证的加密功能产品。</span><span class="sxs-lookup"><span data-stu-id="80d51-124">“FIPS 140 compliant” is an industry term for IT products that rely on FIPS 140 Validated products for cryptographic functionality.</span></span>

<span data-ttu-id="80d51-125">**Microsoft 何时执行 FIPS 140 验证？**</span><span class="sxs-lookup"><span data-stu-id="80d51-125">**When does Microsoft undertake a FIPS 140 validation?**</span></span>

<span data-ttu-id="80d51-126">用于启动模块验证的节奏将与 Windows 10 和 Windows Server 的功能更新进行对齐。</span><span class="sxs-lookup"><span data-stu-id="80d51-126">The cadence for starting a module validation aligns with the feature updates of Windows 10 and Windows Server.</span></span> <span data-ttu-id="80d51-127">随着软件行业的发展，操作系统的发布频率更高，每月软件更新。</span><span class="sxs-lookup"><span data-stu-id="80d51-127">As the software industry evolved, operating systems are released more frequently, with monthly software updates.</span></span> <span data-ttu-id="80d51-128">Microsoft undertakes 针对功能版本的验证，但在两个版本之间进行搜索，以最大限度地减少对加密模块所做的更改。</span><span class="sxs-lookup"><span data-stu-id="80d51-128">Microsoft undertakes validation for feature releases, but in between releases, seeks to minimize the changes to the cryptographic modules.</span></span>

<span data-ttu-id="80d51-129">**FIPS 140 验证中包括哪些计算机？**</span><span class="sxs-lookup"><span data-stu-id="80d51-129">**Which computers are included in a FIPS 140 validation?**</span></span>

<span data-ttu-id="80d51-130">Microsoft 在运行 Windows 10 和 Windows Server 的硬件配置的代表性示例上验证加密模块。</span><span class="sxs-lookup"><span data-stu-id="80d51-130">Microsoft validates cryptographic modules on a representative sample of hardware configurations running Windows 10 and Windows Server.</span></span> <span data-ttu-id="80d51-131">当环境使用硬件时，通常接受此 FIPS 140-2 验证，这与用于验证过程的示例类似。</span><span class="sxs-lookup"><span data-stu-id="80d51-131">It is common industry practice to accept this FIPS 140-2 validation when an environment uses hardware, which is similar to the samples used for the validation process.</span></span>

<span data-ttu-id="80d51-132">**NIST 网站上列出了许多模块。如何知道哪一项适用于我的机构？**</span><span class="sxs-lookup"><span data-stu-id="80d51-132">**There are many modules listed on the NIST website. How do I know which one applies to my agency?**</span></span>

<span data-ttu-id="80d51-133">如果需要使用通过 FIPS 140-2 验证的加密模块，则需要验证您使用的版本是否出现在验证列表中。</span><span class="sxs-lookup"><span data-stu-id="80d51-133">If you are required to use cryptographic modules validated through FIPS 140-2, you need to verify that the version you use appears on the validation list.</span></span> <span data-ttu-id="80d51-134">CMVP 和 Microsoft 维护由产品版本组织的经验证的加密模块的列表，以及有关标识 Windows 系统上安装了哪些模块的说明。</span><span class="sxs-lookup"><span data-stu-id="80d51-134">The CMVP and Microsoft maintain a list of validated cryptographic modules, organized by product release, along with instructions for identifying which modules are installed on a Windows system.</span></span> <span data-ttu-id="80d51-135">有关将系统配置为合规性的详细信息，请参阅[Windows 和 Windows SERVER FIPS 140-2 内容](https://aka.ms/AA6ehud)。</span><span class="sxs-lookup"><span data-stu-id="80d51-135">For more information on configuring systems to be compliant, see the [Windows and Windows Server FIPS 140-2 content](https://aka.ms/AA6ehud).</span></span>

<span data-ttu-id="80d51-136">**"在 FIPS 模式下运行时" 对证书的意义是什么？**</span><span class="sxs-lookup"><span data-stu-id="80d51-136">**What does "When operated in FIPS mode" mean on a certificate?**</span></span>

<span data-ttu-id="80d51-137">此警告会通知读者必须遵循必需的配置和安全规则，以一致地使用其 FIPS 140-2 安全策略的方式使用加密模块。</span><span class="sxs-lookup"><span data-stu-id="80d51-137">This caveat informs the reader that required configuration and security rules must be followed to use the cryptographic module in a way that is consistent with its FIPS 140-2 security policy.</span></span> <span data-ttu-id="80d51-138">每个模块都有其自己的安全策略，即它将在其上运行的安全规则的确切说明，并采用经批准的加密算法、加密密钥管理和身份验证技术。</span><span class="sxs-lookup"><span data-stu-id="80d51-138">Each module has its own security policy — a precise specification of the security rules under which it will operate — and employs approved cryptographic algorithms, cryptographic key management, and authentication techniques.</span></span> <span data-ttu-id="80d51-139">在每个模块的安全策略中定义安全规则。</span><span class="sxs-lookup"><span data-stu-id="80d51-139">The security rules are defined in the security policy for each module.</span></span> <span data-ttu-id="80d51-140">有关详细信息，包括指向通过 CMVP 验证的每个模块的安全策略的链接，请参阅[windows 和 Windows SERVER FIPS 140-2 内容](https://aka.ms/AA6ehud)。</span><span class="sxs-lookup"><span data-stu-id="80d51-140">For more information, including links to the security policy for each module validated through the CMVP, see the [Windows and Windows Server FIPS 140-2 content](https://aka.ms/AA6ehud).</span></span>

<span data-ttu-id="80d51-141">**FedRAMP 是否需要 FIPS 140-2 验证？**</span><span class="sxs-lookup"><span data-stu-id="80d51-141">**Does FedRAMP require FIPS 140-2 validation?**</span></span>

<span data-ttu-id="80d51-142">是的，联邦风险和授权管理程序（FedRAMP）依赖于由[NIST SP 800-53 修订版 4](https://nvd.nist.gov/800-53/Rev4/)定义的控制基准，其中包括[SC-13 加密保护](https://nvd.nist.gov/800-53/Rev4/control/SC-13)，即使用 FIPS 验证的加密加密或经 NSA 核准的加密技术。</span><span class="sxs-lookup"><span data-stu-id="80d51-142">Yes, the Federal Risk and Authorization Management Program (FedRAMP) relies on control baselines defined by the [NIST SP 800-53 Revision 4](https://nvd.nist.gov/800-53/Rev4/), including [SC-13 Cryptographic Protection](https://nvd.nist.gov/800-53/Rev4/control/SC-13) mandating the use of FIPS-validated cryptography or NSA-approved cryptography.</span></span>

<span data-ttu-id="80d51-143">**Microsoft Azure 如何支持 FIPS 140-2？**</span><span class="sxs-lookup"><span data-stu-id="80d51-143">**How does Microsoft Azure support FIPS 140-2?**</span></span>

<span data-ttu-id="80d51-144">Azure 内置了硬件、商业可用操作系统（Linux 和 Windows）以及特定于 Azure 的 Windows 版本的组合。</span><span class="sxs-lookup"><span data-stu-id="80d51-144">Azure is built with a combination of hardware, commercially available operating systems (Linux and Windows), and Azure-specific version of Windows.</span></span> <span data-ttu-id="80d51-145">通过 Microsoft[安全开发生命周期](https://www.microsoft.com/securityengineering/sdl/)（SDL），所有 Azure 服务均使用 fips 140-2 批准的数据安全算法，因为在超大规模云运行时，操作系统使用 fips 140-2 批准的算法。</span><span class="sxs-lookup"><span data-stu-id="80d51-145">Through the Microsoft [Security Development Lifecycle](https://www.microsoft.com/securityengineering/sdl/) (SDL), all Azure services use FIPS 140-2 approved algorithms for data security because the operating system uses FIPS 140-2 approved algorithms while operating at a hyper scale cloud.</span></span>

<span data-ttu-id="80d51-146">**我是否可以在我的机构的认证过程中使用 Microsoft 对 FIPS 140-2 的遵守？**</span><span class="sxs-lookup"><span data-stu-id="80d51-146">**Can I use Microsoft’s adherence to FIPS 140-2 in my agency’s certification process?**</span></span>

<span data-ttu-id="80d51-147">若要符合 FIPS 140-2，必须将系统配置为在 FIPS 认可的操作模式下运行，其中包括确保加密模块仅使用 FIPS 认可的算法。</span><span class="sxs-lookup"><span data-stu-id="80d51-147">To comply with FIPS 140-2, your system must be configured to run in a FIPS approved mode of operation, which includes ensuring that a cryptographic module uses only FIPS-approved algorithms.</span></span> <span data-ttu-id="80d51-148">有关将系统配置为合规性的详细信息，请参阅[Windows 和 Windows SERVER FIPS 140-2 内容](https://aka.ms/AA6ehud)。</span><span class="sxs-lookup"><span data-stu-id="80d51-148">For more information on configuring systems to be compliant, see the [Windows and Windows Server FIPS 140-2 content](https://aka.ms/AA6ehud).</span></span>

<span data-ttu-id="80d51-149">**FIPS 140-2 和通用标准之间的关系是什么？**</span><span class="sxs-lookup"><span data-stu-id="80d51-149">**What is the relationship between FIPS 140-2 and Common Criteria?**</span></span>

<span data-ttu-id="80d51-150">这两个不同的安全标准具有不同但互补的用途。</span><span class="sxs-lookup"><span data-stu-id="80d51-150">These are two separate security standards with different, but complementary, purposes.</span></span> <span data-ttu-id="80d51-151">FIPS 140-2 专门为验证软件和硬件加密模块而设计，而通用标准旨在评估 IT 软件和硬件产品中的安全功能。</span><span class="sxs-lookup"><span data-stu-id="80d51-151">FIPS 140-2 is designed specifically for validating software and hardware cryptographic modules, while the Common Criteria is designed to evaluate security functions in IT software and hardware products.</span></span> <span data-ttu-id="80d51-152">通用标准评估通常依靠 FIPS 140-2 验证，以确保正确实现基本加密功能。</span><span class="sxs-lookup"><span data-stu-id="80d51-152">Common Criteria evaluations often rely on FIPS 140-2 validations to provide assurance that basic cryptographic functionality is implemented properly.</span></span>

## <a name="resources"></a><span data-ttu-id="80d51-153">资源</span><span class="sxs-lookup"><span data-stu-id="80d51-153">Resources</span></span>

- [<span data-ttu-id="80d51-154">FIPS Pub 140-2 加密模块的安全要求</span><span class="sxs-lookup"><span data-stu-id="80d51-154">FIPS Pub 140-2 Security Requirements for Cryptographic Modules</span></span>](https://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf)
- [<span data-ttu-id="80d51-155">NIST 加密模块验证程序</span><span class="sxs-lookup"><span data-stu-id="80d51-155">NIST Cryptographic Module Validation Program</span></span>](https://csrc.nist.gov/groups/STM/cmvp/index.html)
- [<span data-ttu-id="80d51-156">Windows、Windows Server 和 FIPS 140-2</span><span class="sxs-lookup"><span data-stu-id="80d51-156">Windows, Windows Server, and FIPS 140-2</span></span>](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)
- [<span data-ttu-id="80d51-157">Microsoft 信任中心内的合规性</span><span class="sxs-lookup"><span data-stu-id="80d51-157">Compliance on the Microsoft Trust Center</span></span>](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a><span data-ttu-id="80d51-158">下载产品/服务背景信息</span><span class="sxs-lookup"><span data-stu-id="80d51-158">Download the offering backgrounder</span></span>

<span data-ttu-id="80d51-159">需要此产品/服务的背景信息文档？</span><span class="sxs-lookup"><span data-stu-id="80d51-159">Do you need the backgrounder document for this offering?</span></span> <span data-ttu-id="80d51-160">请下载 [PDF](https://download.microsoft.com/download/B/7/2/B7226B91-1A56-41E4-AC01-43FCFEE50B7F/FIPS_Compliance_Backgrounder.pdf)。</span><span class="sxs-lookup"><span data-stu-id="80d51-160">Download the [PDF](https://download.microsoft.com/download/B/7/2/B7226B91-1A56-41E4-AC01-43FCFEE50B7F/FIPS_Compliance_Backgrounder.pdf).</span></span>