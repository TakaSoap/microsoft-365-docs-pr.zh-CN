---
title: 个人编号法案（日本）
description: Microsoft 商业云服务符合日本关于保护个人编号数据隐私的个人编号法案标准。
keywords: Microsoft 365, 合规性, 产品/服务
localization_priority: Priority
ms.prod: Microsoft-365-enterprise
ms.topic: article
ms.author: robmazz
author: robmazz
manager: laurawi
audience: itpro
ms.collection: M365-security-compliance
hideEdit: true
ms.openlocfilehash: c6637db6b73bdc83972d90c938efede0b70938ad
ms.sourcegitcommit: b2197dbf723d11992bbad568a84df3ef3cff421d
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/04/2019
ms.locfileid: "39218711"
---
# <a name="compliance-offering-my-number-act-japan"></a>合规性产品：个人编号法案（日本）

## <a name="about-the-my-number-act"></a>关于个人编号法案

日本政府颁发了个人编号法案（[日语版](https://elaws.e-gov.go.jp/search/elawsSearch/elaws_search/lsg0500/viewContents?lawId=425AC0000000027_20180627_430AC0000000066)和[英语版](https://www.ppc.go.jp/files/pdf/en3.pdf)），于 2016 年 1 月生效。 该法案对日本的每一位居民（无论是日本人还是外籍人士）分配了一个由 12 个数字组成的唯一编号，它被称为个人编号或社保及纳税编号。 向每个人分配一个可通用的编号（就像美国社会保险号一样）的目的在于简化和加快纳税流程，同时简化和加快退休金、医疗保险和失业保障等社会福利的落实。

还根据《个人信息保护法》（[日语版](https://www.ppc.go.jp/personal/preparation/)和[英语版](https://www.ppc.go.jp/en/legal/)）设立了个人信息保障委员会 (PPC)，它充当中央数据保护机构。 PPC 的职责是监督和监控个人编号法案的遵从情况，它颁发了[个人编号指南](https://www.ppc.go.jp/legal/policy/faq/)（日语版），目的是确保各大组织根据法律规定适当处理并充分保护个人编号数据等个人数据。

## <a name="microsoft-and-the-my-number-act"></a>Microsoft 与个人编号法案

为帮助我们的日本客户保护个人数据的隐私，Microsoft 通过 [Microsoft 联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)以合同的形式承诺，我们范围内的商业云服务已实施技术和组织安全保障来帮助我们的客户遵守个人编号法案。这意味着日本客户可在保证自己可遵守日本法律要求的情况下，放心地部署 Microsoft 商业云服务。

个人信息保障委员会 (PPC) 发布的[问答文件](https://www.ppc.go.jp/legal/policy/faq/)（日语版）规定了适当处理和保护个人信息的指导方针。 它规定，如果第三方在自身协议内保证 (a) 其不处理个人数据且 (b) 其建立了适当的访问控制系统，则该第三方不被视为处理个人数据。 个人编号法案规定了当数据传输给第三方时需履行的义务，但 PPC 问答文件[第 3-12 问](https://www.ppc.go.jp/legal/policy/faq/)部分解释了如果第三方并未“处理”（即无权访问）个人数据，则这些义务不适用。

Microsoft 商业云服务在 [Microsoft 联机服务条款](https://www.microsoftvolumelicensing.com/DocumentSearch.aspx?Mode=3&DocumentTypeId=31)中解答了这些要求，该条款中规定包含个人编号数据的客户数据的所有权和责任属于客户，而非属于 Microsoft。 因此，客户必须实施适当的控制措施来保护客户数据中包含的个人编号数据。

Microsoft 无权访问其云服务中存储的个人编号数据，因此无需签订有关处理个人编号数据的“外包”合同。 如果客户希望 Microsoft 访问包含个人编号数据的客户数据，则客户必须在作出此等要求之前就每一种情况与 Microsoft 订立附加外包合同。

联机服务条款还指明，Microsoft 承诺仅使用客户数据来向客户提供服务，不将其用于任何广告或类似商业目的，并且 Microsoft 已实施可靠的访问控制系统。

而对于安全性顾虑，Microsoft 商业云服务符合[云安全认证（金牌）](offering-cs-mark-gold-japan.md) (Cloud Security Mark (Gold)) 标准，这是面向云服务提供商的第一项安全认证。

因此，Microsoft 商业云服务支持个人编号法案要求，且未在客户法案下规定任何附加义务，例如向单个所有者征求对个人数据的同意。

## <a name="microsoft-in-scope-cloud-services"></a>Microsoft 范围内的云服务

- [Azure](https://gallery.technet.microsoft.com/Overview-of-Azure-c1be3942)
- [Dynamics 365](https://download.microsoft.com/download/E/1/9/E1977163-7A86-4812-AC18-C03ADC958AAF/Microsoft_Dynamics_365_Cloud_Service_Compliance_Datasheet.pdf)
- Intune
- [Office 365](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=9f756cce-b15d-45a9-94d7-6a583dee4401&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_Compliance_Guides)

## <a name="how-to-implement"></a>如何实现

- [Microsoft 安全策略](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=231213ea-9954-41fd-a757-ae62f3721dc7&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)：Microsoft 如何应对其云服务中的个人和组织信息的安全性。

- [Office 365 中隐私](https://servicetrust.microsoft.com/ViewPage/TrustDocuments?command=Download&downloadType=Document&downloadId=a1b48a5b-bcb1-4c19-9277-952c0df87113&docTab=6d000410-c9e9-11e7-9a91-892aae8839ad_FAQ_and_White_Papers)：Microsoft 如何将强有力的隐私保护构建到 Office 365 中。

- [Office 365 中的管理访问权限](https://docs.microsoft.com/office365/SecurityCompliance/office-365-administrative-access-controls-overview)：Microsoft 如何管理对 Office 365 客户数据的管理访问权限。

- [Office 365 中的审计和报告](https://docs.microsoft.com/office365/SecurityCompliance/office-365-auditing-and-reporting-overview)：了解客户可用来跟踪其租户中的用户和管理活动的功能。

- [Office 365 中的数据保留](https://docs.microsoft.com/office365/SecurityCompliance/office-365-data-retention-deletion-and-destruction-overview)：了解有关客户数据在被删除后将保留多长时间的数据处理策略。

## <a name="frequently-asked-questions"></a>常见问题解答

**谁最终负责根据个人编号法案保护个人数据？**

PPC 问答文件的[第 3-13 问部分](https://www.ppc.go.jp/legal/policy/faq/)（日语版）指明，由于个人数据的所有权属于 Microsoft 客户，因此这些客户必须采取适当的安全措施（例如控制管理员密码）来保护个人信息和个人编号数据。

## <a name="resources"></a>资源

- [Azure Compliance and the Japan Security and Privacy Requirements](https://gallery.technet.microsoft.com/Azure-Compliance-and-the-53409748)（Azure 合规性和日本安全及隐私要求）
- [Microsoft 隐私](https://privacy.microsoft.com/zh-CN/)
- [Microsoft 隐私声明](https://privacy.microsoft.com/privacystatement)
- [Privacy considerations in the cloud](https://download.microsoft.com/download/0/9/D/09DE47F6-F9E5-4C14-B9E8-E8119A130ACC/Privacy_considerations_in_the_cloud.pdf)（云端隐私保护的注意事项）
- [Microsoft 信任中心内的合规性](https://www.microsoft.com/trust-center/compliance/compliance-overview)

## <a name="download-the-offering-backgrounder"></a>下载产品/服务背景信息

需要此产品/服务的背景信息文档？ 请下载 [PDF](https://download.microsoft.com/download/0/E/C/0EC14DDA-6041-4841-A180-199870B136C4/MyNumberAct-Compliance.pdf)。
