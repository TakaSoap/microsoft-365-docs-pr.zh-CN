---
title: 美国出口管理条例（EAR）
description: Microsoft 云服务可帮助客户遵守美国出口管理条例（EAR），以满足其合规性要求并管理出口控制风险。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: None
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
titleSuffix: Microsoft Compliance
ms.openlocfilehash: ae28d96416f46a45c0d271b9c291040c2e9d8b31
ms.sourcegitcommit: 0ad0092d9c5cb2d69fc70c990a9b7cc03140611b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/19/2019
ms.locfileid: "40804125"
---
# <a name="us-export-administration-regulations-ear"></a>美国出口管理条例（EAR）

## <a name="about-the-ear"></a>关于 EAR

美国商业部门通过[行业和安全性（BIS）部门](https://www.bis.doc.gov/)强制实施出口管理条例（EAR）。 该 EAR 广泛控制并实施对大部分商业商品、软件和技术的导出和重新导出的控制，包括可用于商业和军事目的以及某些防御项目的 "双重使用" 项目。

BIS 指南包含：在将数据或软件上载到云或在用户节点之间传输时，客户（而不是云提供商）是有责任确保这些数据或软件的传输、存储和访问权限的 "导出程序"符合 EAR。

[根据 BIS](https://www.bis.doc.gov/index.php/documents/regulation-docs/412-part-734-scope-of-the-export-administration-regulations/file)，*出口*指将受保护的技术或技术数据传输到外部目标或其发布到美国的外国个人（也称为 "*出口出口*"）。 广泛的 EAR 控制：

- 从美国出口。
- 重新导出或 retransfers 美国原始项目和某些外接一些项目，这些项目的*minimis*部分是我们的原始内容。
- 对其他国家/地区的人员进行转让或披露。

受 EAR 制约的项目可在商业控制列表（CCL）中找到，其中每个项目都分配有一个唯一的 "[导出控制分类号码（ECCN）](https://www.bis.doc.gov/index.php/licensing/commerce-control-list-classification/export-control-classification-number-eccn)"。 未在 CCL 中列出的项目被指定为 EAR99，并且大多数 EAR99 商业产品将不需要导出许可证。 但是，根据目标、最终用户或项目的最终用途，即使 EAR99 项目也可能需要 BIS 导出许可证。

2016年6月发布的[最终规则](https://www.federalregister.gov/documents/2016/06/03/2016-12734/revisions-to-definitions-in-the-export-administration-regulations)阐明了，如果使用 FIPS 140-2 验证的加密模块对未分类的技术数据和软件进行端到端加密，并且未在军事版禁运国家/地区或在俄罗斯联合中有意存储它们，则该规则也不会应用于这些未分类技术数据和软件的传输和存储。

## <a name="microsoft-and-the-ear"></a>Microsoft 和 EAR

Microsoft 技术、产品和服务受美国出口管理条例（EAR）的约束。 虽然没有适用于 EAR 的合规性认证，Microsoft Azure、Microsoft Azure 政府和 Microsoft Office 365 政府（GCCHigh 和 DoD 环境）提供了重要特性和工具，可帮助符合 EAR 管理导出的符合条件的客户。控制风险并满足其合规性要求。

强制实施 EAR 的美国商业部门将客户，而不是云服务提供商（如 Microsoft）视为 exporters 其自己的客户数据。 尽管大多数客户数据不会被视为 EAR 出口控制的 "技术" 或 "技术数据"，但 Microsoft 范围内云服务的结构可帮助客户管理和显著降低他们所面临的潜在出口控制风险。 Microsoft 通常（但不专门）建议将其政府云服务用于符合条件的客户。 通过适当的规划，客户可以使用以下工具和他们自己的内部过程来帮助确保完全遵守美国出口控制。

- **数据位置上的控件**。 客户可以查看其数据的存储位置，并可访问强健的工具来限制其存储。 因此，他们可能会确保其数据存储在美国，并最大限度地减少美国境外的受控制技术或技术数据的转移。 此外，客户数据不存储在不相容的位置，与 EAR prohibitions 在数据 "特意存储" 的位置保持一致：没有任何25组 D:5 国家/地区或俄语联合中的任何一个。
- **端到端加密**。 通过对 EAR 中指定的物理存储位置利用端到端加密安全港，Microsoft in 范围内的云服务提供了可帮助防止出口控制风险的加密功能。 它们还为客户提供了多种用于在传输和 rest 中[加密数据的选项](https://aka.ms/Azure-Encryption-Overview)，以及在加密选项之间进行选择的灵活性。
- **用于防止未经授权的导出的工具和协议**。 加密的使用还有助于防止在 EAR 中出现可能被认为的出口（或被视为重新导出），因为即使非美国人员有权访问加密数据，也不会发现数据在加密时无法读取或理解的情况。因此，不存在受控制数据的 "释放"。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure 与 Azure 政府](https://aka.ms/AzureCompliance)
- [Office 365 政府版（GCC-高和 DoD）](https://aka.ms/Office-365-Export-Controls)
- Intune

## <a name="how-to-implement"></a>如何实现

我们对美国出口控制和指南的概述，这些客户在 EAR 下评估其义务。

- [Azure](https://aka.ms/Azure-Export-Controls)
- [Office 365](https://aka.ms/Office-365-Export-Controls)

## <a name="frequently-asked-questions"></a>常见问题解答

**在使用 Microsoft 云服务时，应如何遵守导出控制？**

在 EAR 中，当数据上传到云服务器（如 Microsoft 云）时，拥有数据的客户（而不是云服务提供商）被视为是导出者。 因此，数据所有者（即 Microsoft 客户）必须仔细评估其对 Microsoft 云的使用如何 implicate 我们的导出控制措施，并确定是否需要使用或存储的任何数据可能受 EAR 控制，如果是，则应用哪些控件。 了解有关[Azure](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)和[Office 365](https://query.prod.cms.rt.microsoft.com/cms/api/am/binary/RE1s5kI)云服务如何帮助客户确保其完全符合美国出口控件的详细信息。

**Microsoft 技术、产品和服务是否受 EAR 的制约？**

大多数 Microsoft 技术、产品和服务都可以：

- 不受 EAR 的制约，因此不在商业控制列表中，也没有 ECCN;
- 或者，它们是由 Microsoft 提供的 EAR99 或5D992 大宗市场，可以由 Microsoft 进行自我分类，并且可以将其导出到非禁运国家/地区，而无需许可证（NLR）。

也就是说，已为几个 Microsoft 产品分配了可能需要也可能不需要许可证的 ECCN。 咨询 EAR 或法律顾问，以确定适用于出口目的的相应许可证类型和符合条件的国家/地区。

**Arm 管理法规（ITAR）中的 EAR 和国际流量之间有何区别？**

包含最广泛应用程序的主要美国出口控制是由美国商业部门管理的 EAR。 该 EAR 适用于同时具有商业和军事应用程序的双重使用项目，以及与纯商业应用程序相关的项。

美国还具有独立且更多的专用出口控制法规（如 ITAR），可控制最敏感的项目和技术。 由美国国家/州部门管理，对许多军事、国防和智能项目（也称为 "防御文章"）的导出、临时导入、重新导出和传输施加了控制措施（也称为 "防御文章"），包括相关技术数据。

## <a name="resources"></a>资源

- [导出 Microsoft 产品：概述](https://www.microsoft.com/exporting/overview.aspx)
- [导出 Microsoft 产品： FAQ](https://www.microsoft.com/exporting/faq.aspx)
- [导出 Microsoft 产品：产品查找](https://www.microsoft.com/exporting/exporting-information.aspx)
- [对加密的导出限制](https://docs.microsoft.com/windows/uwp/security/export-restrictions-on-cryptography)
- [Microsoft 和 FIPS 140-2](offering-fips-140-2.md)
- [Microsoft 和 ITAR](offering-itar.md)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
