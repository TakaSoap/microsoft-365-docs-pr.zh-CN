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
ms.openlocfilehash: 8288438eed0f658d8058125bc90315e9a2626c08
ms.sourcegitcommit: 7f307b4f583b602f11f69adae46d7f3bf6982c65
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 05/06/2020
ms.locfileid: "44066577"
---
# <a name="federal-information-processing-standard-fips-publication-140-2"></a>联邦信息处理标准（FIPS）发布140-2

## <a name="fips-140-2-standard-overview"></a>FIPS 140-2 标准概述

联邦信息处理标准（FIPS）发布140-2 是一项美国政府标准，定义了信息技术产品中的加密模块的最低安全要求，如信息技术管理改革法案1996的5131节中所定义。

[加密模块验证程序](https://csrc.nist.gov/Projects/cryptographic-module-validation-program)（CMVP）（美国国家标准和技术协会（NIST）和加拿大中心网络安全（CCCS）的联合努力将加密模块验证为加密模块标准（即 FIPS 140-2）和相关 FIPS 加密标准的*安全要求*。 FIPS 140-2 安全要求涵盖了与加密模块的设计和实现相关的11个方面。 NIST 信息技术实验室运行一个相关的程序来验证模块中的 FIPS 批准的加密算法。

## <a name="microsofts-approach-to-fips-140-2-validation"></a>Microsoft 对 FIPS 140-2 验证的方法

Microsoft 保持积极的承诺来满足140-2 的要求，由于标准是在2001中开始，因此已验证了加密模块。 Microsoft 验证其在美国国家标准和技术协会（NIST）[加密模块验证程序](https://csrc.nist.gov/Projects/cryptographic-module-validation-program)（CMVP）下的加密模块。 多个 Microsoft 产品（包括许多云服务）使用这些加密模块。

有关 Microsoft Windows 加密模块的技术信息、每个模块的安全策略以及 CMVP 证书详细信息的目录，请参阅[windows 和 Windows SERVER FIPS 140-2 内容](https://aka.ms/AA6ehud)。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内的云服务

当前 CMVP FIPS 140-2 实施指南排除了云服务本身的 FIPS 140-2 验证;云服务提供商可以选择为构成云服务的计算元素获取并运行 FIPS 140 验证的加密模块。 Microsoft online services 包括已验证 FIPS 140-2 的组件，其中包括：

- [Azure 与 Azure 政府](https://docs.microsoft.com/azure/azure-government/documentation-government-plan-security)
- [Dynamics 365 和 Dynamics 365 政府](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-in-microsoft-dynamics-365)
- [Office 365、Office 365 U.S. Government 和 Office 365 U.S. Government Defense](https://docs.microsoft.com/microsoft-365/compliance/office-365-encryption-risks-and-protections)

## <a name="frequently-asked-questions"></a>常见问题

**"FIPS 140 验证" 和 "FIPS 140 兼容" 的区别是什么？**

"FIPS 140 已验证" 表示加密模块或嵌入模块的产品已由 CMVP 进行了验证（"认证"），以满足 FIPS 140-2 的要求。 "FIPS 140 合规" 是 IT 产品的一项行业术语，它依赖于 FIPS 140 验证的加密功能产品。

**Microsoft 何时执行 FIPS 140 验证？**

用于启动模块验证的节奏将与 Windows 10 和 Windows Server 的功能更新进行对齐。 随着软件行业的发展，操作系统的发布频率更高，每月软件更新。 Microsoft undertakes 针对功能版本的验证，但在两个版本之间进行搜索，以最大限度地减少对加密模块所做的更改。

**FIPS 140 验证中包括哪些计算机？**

Microsoft 在运行 Windows 10 和 Windows Server 的硬件配置的代表性示例上验证加密模块。 当环境使用硬件时，通常接受此 FIPS 140-2 验证，这与用于验证过程的示例类似。

**NIST 网站上列出了许多模块。如何知道哪一项适用于我的机构？**

如果需要使用通过 FIPS 140-2 验证的加密模块，则需要验证您使用的版本是否出现在验证列表中。 CMVP 和 Microsoft 维护由产品版本组织的经验证的加密模块的列表，以及有关标识 Windows 系统上安装了哪些模块的说明。 有关将系统配置为合规性的详细信息，请参阅[Windows 和 Windows SERVER FIPS 140-2 内容](https://aka.ms/AA6ehud)。

**"在 FIPS 模式中运行时" 对证书的平均含义是什么？**

此警告会通知读者必须遵循必需的配置和安全规则，以一致地使用其 FIPS 140-2 安全策略的方式使用加密模块。 每个模块都有其自己的安全策略，即它将在其上运行的安全规则的确切说明，并采用经批准的加密算法、加密密钥管理和身份验证技术。 在每个模块的安全策略中定义安全规则。 有关详细信息，包括指向通过 CMVP 验证的每个模块的安全策略的链接，请参阅[windows 和 Windows SERVER FIPS 140-2 内容](https://aka.ms/AA6ehud)。

**FedRAMP 是否需要 FIPS 140-2 验证？**

是的，联邦风险和授权管理程序（FedRAMP）依赖于由[NIST SP 800-53 修订版 4](https://nvd.nist.gov/800-53/Rev4/)定义的控制基准，其中包括[SC-13 加密保护](https://nvd.nist.gov/800-53/Rev4/control/SC-13)，即使用 FIPS 验证的加密加密或经 NSA 核准的加密技术。

**Microsoft Azure 如何支持 FIPS 140-2？**

Azure 内置了硬件、商业可用操作系统（Linux 和 Windows）以及特定于 Azure 的 Windows 版本的组合。 通过 Microsoft[安全开发生命周期](https://www.microsoft.com/securityengineering/sdl/)（SDL），所有 Azure 服务均使用 fips 140-2 批准的数据安全算法，因为在超大规模云运行时，操作系统使用 fips 140-2 批准的算法。

**我是否可以在我的机构的认证过程中使用 Microsoft 对 FIPS 140-2 的遵守？**

若要符合 FIPS 140-2，必须将系统配置为在 FIPS 认可的操作模式下运行，其中包括确保加密模块仅使用 FIPS 认可的算法。 有关将系统配置为合规性的详细信息，请参阅[Windows 和 Windows SERVER FIPS 140-2 内容](https://aka.ms/AA6ehud)。

**FIPS 140-2 和通用标准之间的关系是什么？**

这两个不同的安全标准具有不同但互补的用途。 FIPS 140-2 专门为验证软件和硬件加密模块而设计，而通用标准旨在评估 IT 软件和硬件产品中的安全功能。 通用标准评估通常依靠 FIPS 140-2 验证，以确保正确实现基本加密功能。

## <a name="resources"></a>资源

- [FIPS Pub 140-2 加密模块的安全要求](https://csrc.nist.gov/publications/fips/fips140-2/fips1402.pdf)
- [NIST 加密模块验证程序](https://csrc.nist.gov/groups/STM/cmvp/index.html)
- [Windows、Windows Server 和 FIPS 140-2](https://docs.microsoft.com/windows/security/threat-protection/fips-140-validation)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
