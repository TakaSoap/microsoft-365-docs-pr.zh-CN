---
title: Contoso Corporation 的信息保护
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用企业Microsoft 365中的信息保护功能，以确保其数字资产在云中的安全。
ms.openlocfilehash: 1dff2cadd5afa66b3b469a2debedddbb347db0e5
ms.sourcegitcommit: 07405a81513d1c63071a128b9d5070d3a3bfe1cd
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61122569"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Contoso Corporation 的信息保护

Contoso 非常关心其信息安全。 泄露或销毁描述其产品开发和专有制造技术的知识产权将使它们处于竞争劣势。

在将敏感的数字资产迁移到云之前，Contoso 已确保其本地信息分类和保护要求受 Microsoft 365 企业版基于云的服务支持。

## <a name="contoso-data-security-classification"></a>Contoso 数据安全分类

Contoso 对数据进行了分析，并确定了以下分类级别。

| 1 级：基准 | 2 级：敏感 | 3 级：高度管控 |
|:-------|:-----|:-----|
| 数据已加密，并且仅供已通过身份验证的用户使用。<BR> <BR> 为本地和基于云的存储和工作负载中存储的所有数据提供。 数据驻留在服务中以及服务与客户端设备之间传输时加密。 <BR><BR>1 级数据的示例为正常的业务通信（电子邮件）和供管理、销售和支持工作人员使用的文件。 | 1 级再加上强身份验证和数据丢失防护。<BR> <BR> 强身份验证包括Azure AD短信验证 (MFA) 多重身份验证。 数据丢失防护可确保敏感或关键信息不会在 Microsoft 云外部传输。<BR><BR>2 级数据的示例包括财务和法律信息，以及新产品的研发数据。 | 2 级再加上最高级别的加密、身份验证和审核。<BR><BR>对静态和云中的数据采用最高级别的加密，遵循区域法规，并结合具有智能卡以及精细审核和警报的 MFA。<BR> <BR>级别 3 数据的示例包括客户和合作伙伴个人信息、产品工程规范和专有制造技术。  |
||||

## <a name="contoso-information-policies"></a>Contoso 信息策略
下表列出了 Contoso 信息策略。


| 值 | Access | 数据保留 | 信息保护 |
|:-------|:-----|:-----|:-----|
| 业务价值较低（1 级：基准） | 允许访问全部。  | 6 个月 | 使用加密。 |
| 业务价值中等（2 级：敏感） | 允许 Contoso 员工、分包商和合作伙伴访问。 <BR><BR> 使用 MFA、传输层安全性 (TLS) 和移动应用管理 (MAM)。 | 2 年  | 使用哈希值实现数据完整性。  |
| 高业务价值（3 级：高度管控） | 允许工程设计和制造中的执行人员和潜在客户访问。 <BR> <BR> 仅限托管网络设备的权限管理系统 (RMS)。  | 7 年  | 使用数字签名实现不可否认性。  |
|||||

## <a name="the-contoso-path-to-information-protection-with-microsoft-365-for-enterprise"></a>Contoso 信息保护与企业Microsoft 365路径

Contoso 按照以下步骤为企业Microsoft 365信息保护要求做好准备：

1. 确定要保护的信息

   Contoso 对位于本地网站和文件共享中的现有数字SharePoint进行了广泛审查，并分类了每个资产。

2. 确定数据级别的访问、保留和信息保护策略

   Contoso 基于数据级别确定了详细的策略要求，这些要求被用于保护现有数字资产，因为它们被转移到了云中。

3. 为不同级别的信息创建敏感度标签及其设置

   Contoso 为其数据级别创建了敏感度标签，其中包含加密、权限和水印等高度管控标签。

4. 将数据从本地部署SharePoint网站和文件共享移动到其新的SharePoint网站

    迁移到新的 SharePoint 网站的文件继承了分配给该网站的默认保留标签。

5. 培训员工如何对新文档使用敏感度标签、如何在创建新的 SharePoint 网站时与 Contoso IT 进行交互，以及始终将数字资产存储在SharePoint网站上

    改变不良的工作人员信息存储习惯通常被视为云信息保护转换中最困难的部分。 Contoso IT 和管理需要让员工始终在云中标记和存储其数字资产，避免使用本地文件共享，并且不使用第三方云存储服务或 USB 驱动器。

## <a name="conditional-access-policies-for-information-protection"></a>用于信息保护的条件访问策略

作为推出 Exchange Online 和 SharePoint 的一SharePoint，Contoso 配置了以下一组条件访问策略，并应用于相应的组：

- [设备策略上的托管和非托管应用程序访问](../security/office-365-security/identity-access-policies.md)
- [Exchange Online 访问策略](../security/office-365-security/secure-email-recommended-policies.md)
- [SharePoint 访问策略](../security/office-365-security/sharepoint-file-access-policies.md)

下面是一组 Contoso 信息保护策略。

:::image type="content" alt-text="设备、Exchange Online和SharePoint条件访问策略。" source="../media/contoso-info-protect/contoso-info-protect-fig1.png" lightbox="../media/contoso-info-protect/contoso-info-protect-fig1.png":::

>[!Note]
>此外，Contoso 还配置了针对标识和登录的其他条件访问策略。 请参阅 [Contoso Corporation 的标识](contoso-identity.md#conditional-access-policies-for-zero-trust-identity-and-device-access)。
>

这些策略确保：

- 允许的应用以及它们可以对组织数据采取的操作由应用保护策略定义。
- 电脑和移动设备必须兼容。
- Exchange Online使用Office 365 OME (OME 加密) OME Exchange Online。
- SharePoint使用应用强制限制。
- SharePoint 使用访问控制策略来实现非托管设备的仅浏览器访问或阻止其访问。

## <a name="mapping-microsoft-365-for-enterprise-features-to-contoso-data-levels"></a>将Microsoft 365功能映射到 Contoso 数据级别

下表将 Contoso 数据级别映射到企业Microsoft 365信息保护功能。

| 级别 | Microsoft 365云服务 | Windows 10 和 Microsoft 365 企业应用版 | 安全性和合规性 |
|:-------|:-----|:-----|:-----|
| 1 级：基准  | SharePoint 和 Exchange Online 条件访问策略 <BR> SharePoint 网站上的权限 | 敏感度标签 <BR> BitLocker <BR> Windows 信息保护 | 设备条件访问策略和移动应用管理策略 |
| 2 级：敏感 | 1 级再加上： <BR> <BR> 敏感度标签 <BR> SharePoint 网站上的 Microsoft 365 保留标签 <BR> 用于 SharePoint 和 Exchange Online 的数据丢失防护 <BR> 独立 SharePoint 网站  | 1 级再加上： <BR> <BR> 数字资产上的敏感度标签  | 1 级 |
| 3 级：高度管控 | 2 级再加上： <BR><BR> 将你自己的密钥 (BYOK) 加密和保护商业机密信息 <BR> Azure Key Vault，用于与服务交互的业务线Microsoft 365应用程序 | 2 级 | 1 级 |
|||||

下面是生成的 Contoso 信息保护配置。

:::image type="content" alt-text="Contoso 生成的信息保护配置。" source="../media/contoso-info-protect/contoso-info-protect-fig2.png":::

## <a name="next-step"></a>后续步骤

了解 Contoso 如何使用[](contoso-security-summary.md)跨企业Microsoft 365安全功能进行标识和访问管理、威胁防护、信息保护和安全管理。

## <a name="see-also"></a>另请参阅

[安全性路线图](../security/office-365-security/security-roadmap.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)