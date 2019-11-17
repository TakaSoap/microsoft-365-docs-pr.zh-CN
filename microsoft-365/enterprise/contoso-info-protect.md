---
title: Contoso Corporation 的信息保护
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 10/02/2019
audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 了解 Contoso 如何使用 Microsoft 365 企业版中的信息保护功能来保护其在云中的数字资产。
ms.openlocfilehash: f5893414a0aab3d0ab89eb180f0c907d4379194c
ms.sourcegitcommit: 9ee873c6a2f738a0c99921e036894b646742e706
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/15/2019
ms.locfileid: "38673198"
---
# <a name="information-protection-for-the-contoso-corporation"></a>Contoso Corporation 的信息保护

Contoso 在信息安全和保护方面非常严谨。例如，在描述产品设计和专有制造技术时，其知识产权的泄露或破坏将使他们在竞争中处于劣势。

在将敏感和最有价值的数字资产转移到云之前，他们将确保本地信息分类和保护要求在 Microsoft 365 企业版基于云的服务中得到支持和实现。

## <a name="contosos-data-security-classification"></a>Contoso 的数据安全分类

Contoso 执行数据分析，并确定以下级别。

||||
|:-------|:-----|:-----|
| **1 级：基准** | **2 级：敏感** | **3 级：高度管控** |
| 数据已加密，并且仅供已通过身份验证的用户使用。 <BR> <BR> 向存储在本地和基于云的存储空间和工作负载（例如 Office 365）中的所有数据提供。驻留在服务中和在服务与客户端设备之间传输时，数据处于加密状态。 <BR><BR> 1 级数据的示例为正常的业务通信（电子邮件）和供管理、销售和支持工作人员使用的文件。 | 1 级再加上强身份验证和数据丢失防护。 <BR> <BR> 强身份验证包括具有短信验证的 Azure 多重身份验证 (MFA)。 数据丢失防护可确保敏感或关键信息不会在 Microsoft 云外部传播。 <BR><BR> 2 级数据的示例包括财务和法律信息，以及新产品的研发数据。 | 2 级再加上最高级别的加密、身份验证和审核。 <BR> <BR>  对静态和云中的数据采用最高级别的加密，遵循区域法规，并结合具有智能卡以及精细审核和警报的 MFA。 <BR> <BR> 3 级数据的示例是客户和合作伙伴的个人身份信息、产品工程规范以及专有的制造技术。  |
||||

## <a name="contosos-information-policies"></a>Contoso 的信息策略
下表列出了 Contoso 的信息策略。

|||||
|:-------|:-----|:-----|:-----|
|  | **访问** | **数据保留** | **信息保护** |
| 业务价值较低（1 级：基准） | 允许所有人员访问  | 6 个月 | 使用加密。 |
| 业务价值中等（2 级：敏感） | 允许 Contoso 员工、分包商和合作伙伴访问 <BR> <BR> 使用 MFA、传输层安全性 (TLS) 和移动应用管理 (MAM)。 | 2 年  | 使用哈希值实现数据完整性。  |
| 高业务价值（3 级：高度管控） | 允许工程设计和制造中的执行人员和潜在客户访问。 <BR> <BR> 仅限托管网络设备的权限管理系统 (RMS)。  | 7 年  | 使用数字签名实现不可否认性。  |
|||||

## <a name="contosos-path-to-information-protection-with-microsoft-365-enterprise"></a>使用 Microsoft 365 企业版的 Contoso 信息保护路径

Contoso 使用以下步骤为 Microsoft 365 企业版准备其信息保护要求：

1. 标识要保护的信息

   Contoso 对其现有数字资产进行了广泛审查，这些资产位于本地 SharePoint 网站和文件共享中，并对每一个资产都进行了分类。

2. 确定数据级别的访问策略、保留策略和信息保护策略

   Contoso 基于数据级别确定了详细的策略要求，这些要求被用于保护现有数字资产，因为它们被转移到了云中。

3. 创建了敏感度标签以及它们对不同级别信息的设置

   Contoso 为其数据级别创建了敏感度标签，其中包含加密、权限和水印等高度管控标签。

4. 为敏感和高度管控数据创建了受保护的 SharePoint 网站，同时包含锁定访问权限的权限

   敏感和高度管控网站均配置为[独立网站](https://docs.microsoft.com/office365/enterprise/isolated-sharepoint-online-team-sites)，其中默认的 SharePoint Online 团队网站权限是自定义的。 敏感和高度管控的 SharePoint 网站还配置了相应的保留标签。 存储在高度管控 SharePoint 网站中的文件受高度管控标签的敏感度子标签保护。 有关详细信息，请参阅方案：[用于高度管控数据的 SharePoint 网站](teams-sharepoint-online-sites-highly-regulated-data.md)。

5.  将数据从本地 SharePoint 网站和文件共享转移到新的 SharePoint 网站

    迁移到新的 SharePoint 网站的文件继承了分配给该网站的默认保留标签。

6.  培训员工如何对新文档使用敏感度标签，如何在创建新的 SharePoint 网站时与 Contoso IT 进行交互，以及如何始终在 SharePoint 网站上存储数字资产

    考虑到云信息保护过渡中最困难的部分，Contoso IT 和管理层需要改变组织员工的不良信息存储习惯，以始终在云中标记和存储其数字资产，避免使用本地文件共享，并且绝不使用第三方云存储设备或 U 盘。

## <a name="conditional-access-policies-for-information-protection"></a>用于信息保护的条件访问策略

与身份标识和移动设备管理基础结构结合使用，并作为他们推出 Exchange Online 和 SharePoint 的一部分，Contoso 配置了以下一组条件访问策略，并将其应用到相应的组：

- [设备策略上的托管和非托管应用程序访问](identity-access-policies.md)
- [Exchange Online 访问策略](secure-email-recommended-policies.md)
- [SharePoint 访问策略](sharepoint-file-access-policies.md)

此处是 Contoso 最终得到的信息保护策略集。

![设备、Exchange Online 和 SharePoint 条件访问策略](./media/contoso-info-protect/contoso-info-protect-fig1.png)

>[!Note]
>此外，Contoso 还配置了针对标识和登录的其他条件访问策略。 请参阅 [Contoso Corporation 的标识](contoso-identity.md#conditional-access-policies-for-identity-and-device-access)。
>

这些策略确保：

- 应用保护政策定义哪些应用程序是允许的，以及它们可以使用组织数据执行哪些操作。
- 电脑和移动设备必须兼容。
- Exchange Online 使用 Exchange Online 的 Office 365 邮件加密。
- SharePoint 使用应用强制的限制。
- SharePoint 使用访问控制策略来实现非托管设备的仅浏览器访问或阻止其访问。

## <a name="mapping-microsoft-365-enterprise-features-to-contosos-data-levels"></a>将 Microsoft 365 企业版功能映射到 Contoso 的数据级别

下表展示了 Contoso 的数据级别与 Microsoft 365 企业版中的信息保护功能的对应关系。

|||||
|:-------|:-----|:-----|:-----|
| | **Office 365** | **Windows 10 和 Office 365 专业增强版** | **EMS** |
| 1 级：基准  | SharePoint 和 Exchange Online 条件访问策略 <BR> SharePoint 网站上的权限 | 敏感度标签 <BR> BitLocker <BR> Windows 信息保护 | 设备条件访问策略和移动应用管理策略 |
| 2 级：敏感 | 1 级再加上： <BR> <BR> 敏感度标签 <BR> SharePoint 网站上的 Office 365 保留标签 <BR> 用于 SharePoint 和 Exchange Online 的 Office 365 数据丢失防护 <BR> 独立 SharePoint 网站  | 1 级再加上： <BR> <BR> 数字资产上的敏感度标签  | 1 级 |
| 3 级：高度管控 | 2 级再加上： <BR><BR> 针对商业机密信息的自带密钥 (BYOK) 加密和保护 <BR> 将 Azure Key Vault 用于与 Office 365 服务交互的业务线应用程序 | 2 级 | 1 级 |
|||||

此处是 Contoso 最终得到的信息保护配置。

![Contoso 最终得到的信息保护配置](./media/contoso-info-protect/contoso-info-protect-fig2.png)

## <a name="next-step"></a>后续步骤

[请参阅](contoso-security-summary.md) Contoso 如何使用安全功能跨 Microsoft 365 企业版实现身份识别和访问管理、威胁防护、信息保护以及安全管理。

## <a name="see-also"></a>另请参阅

[Microsoft 365 企业版信息保护](infoprotect-infrastructure.md)

[部署指南](deploy-microsoft-365-enterprise.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)


