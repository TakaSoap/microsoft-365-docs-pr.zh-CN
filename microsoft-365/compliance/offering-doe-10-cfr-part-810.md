---
title: 美国 DoE 10 CFR Part 810
description: 根据美国 DoE 10 CFR Part 810 的出口控制要求，客户可以使用 Azure 政府。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: None
ms.prod: microsoft-365-enterprise
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
ms.openlocfilehash: a809ae91bbe1302ae4087b3a430dea87e2c913a1
ms.sourcegitcommit: 74ef7179887eedc696c975a82c865b2d4b3808fd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/09/2020
ms.locfileid: "47415692"
---
# <a name="us-doe-10-cfr-part-810"></a>美国 DoE 10 CFR Part 810

## <a name="microsoft-and-doe-10-cfr-part-810"></a>Microsoft 和 DoE 10 CFR Part 810

Microsoft Azure 政府可以通过两个授权帮助客户支持符合美国的美国能源部门 (DoE) 10 CFR Part 810 的出口控制要求：

- FedRAMP 高的临时授权，以 (P-ATO) 颁发的联合授权板 (JAB) 
- 来自国防部门 (DoD) 国防信息系统代理商的第4级和第5级临时授权

FedRAMP 提供了适当的基准，以确保 Azure 政府提供核心基础结构和虚拟化技术以及使用严格 NIST 控件设计的计算、存储和网络等服务。 这些帮助可满足客户数据分离要求，并帮助实现与客户的本地环境的安全连接。

此外，Azure 政府是一种物理上独立于 Azure 云的美国政府社区云。 它提供了有关美国政府特定的后台筛选要求的其他保证，包括限制对信息和系统的访问，以在 Azure 操作人员中对美国公民进行筛选的特定控件。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内云服务

- [Azure 政府](https://aka.ms/AzureCompliance)
- Intune

## <a name="how-to-implement"></a>如何实现

- [NERC CIP 标准 & 云计算](https://aka.ms/AzureNERC)：用于电子设施和注册实体的指南在 Azure 或 azure 政府上部署工作负荷。

## <a name="about-doe-10-cfr-part-810"></a>关于 DoE 10 CFR Part 810

美国的美国能源 (DoE) 导出控制法规 [10 CFR part 810](https://www.govinfo.gov/content/pkg/FR-2015-02-23/pdf/2015-03479.pdf) 管理未经分类的核技术和协助的出口。 它有助于确保从美国出口的核技术将仅用于 peaceful 目的。 修订后的部件 810 (最终规则) 在3月2015生效，并由 [国家核安全管理](https://www.energy.gov/nnsa/national-nuclear-security-administration)进行管理。 第810.6 节说明必须提供特定的 DoE 授权，这两个方面的协助和转换均为 "通常授权" 的敏感核技术，以及那些需要特定授权 (的技术，如扩充和重型产品) 等敏感核技术的协助。

## <a name="frequently-asked-questions"></a>常见问题解答

**美国核法规委员会的 10 CFR Part 110 规章是否适用于 Azure 政府？**

不正确。 [美国核规章委员会](https://www.nrc.gov/) (NRC) 规定了核设施的导出和导入，以及[10 CFR part 110](https://www.nrc.gov/reading-rm/doc-collections/cfr/part110/)的相关设备和材料的[导出和导入](https://www.nrc.gov/about-nrc/ip/export-import.html)。 NRC 不会控制与属于 DoE 司法辖区的这些项目相关的核技术和协助。 因此，NRC 10 CFR Part 110 规章不适用于 Azure 政府。

**如何提供我遵守 DoE 10 CFR Part 810 的证据？**

如果您的组织将数据部署到 Azure 政府，则可以依靠 Azure 政府 FedRAMP 高 P-ATO 作为以适当限制的方式处理数据的证据。 但是，您需要负责获取自己的系统的 DoE 授权，包括云服务的使用。

**对 Azure 政府部署的数据进行分类有哪些责任？**

向 Azure 政府部署数据的客户负责自己的安全分类过程。 对于使用 DoE export 控件的客户数据，分类系统会被未分类控制的核信息 (UCNI) 由 [美国的原子能源法案](https://www.epa.gov/laws-regulations/summary-atomic-energy-act)中的148节建立的控件。

## <a name="resources"></a>资源

- [Azure 云服务和美国出口控制](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=c24c11f2-2cd4-444a-9160-19762855ad3a&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)
- [Microsoft 与 FedRAMP](offering-fedramp.md)
- [Microsoft 和 DoD](offering-dod-disa-l2-l4-l5.md)
- [Microsoft 政府云](https://www.microsoft.com/enterprise/government)
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)
