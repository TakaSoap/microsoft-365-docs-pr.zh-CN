---
title: 了解Microsoft 365本地扫描程序的数据丢失防护
f1.keywords:
- CSH
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: ITPro
ms.topic: conceptual
f1_keywords:
- ms.o365.cc.DLPLandingPage
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MET150
description: Microsoft 365 本地扫描仪的数据丢失防护扩展了对文件活动的监视以及针对这些文件的安全操作，可扩展到本地文件共享和 SharePoint 文件夹和文档库。通过 Azure 信息保护 （AIP） 扫描仪扫描和保护文件
ms.openlocfilehash: c696d4c4e8504d07ce69554c6ff52f264b8ba491
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60207339"
---
# <a name="learn-about-the-microsoft-365-data-loss-prevention-on-premises-scanner"></a>了解本地扫描程序Microsoft 365数据丢失防护

Microsoft 本地扫描仪的 Microsoft 数据丢失防护是 Microsoft 365 数据丢失防护 （DLP） 套件的一部分，可用于在 Microsoft 365 服务中发现和保护敏感项目。 有关 Microsoft 所有 DLP 产品/服务的更多信息，请参阅[数据丢失防护概述](dlp-learn-about-dlp.md)。

**DLP 本地扫描仪** 会对文件共享和 SharePoint 文档库以及文件夹中的本地数据（如果泄露）进行爬网，这些敏感项目可能给组织带来风险或带来合规性策略冲突的风险。 通过此操作，可了解确保正确使用和保护敏感项目所需的可见性和控制，还有助于防止可能泄露到其的风险行为。 DLP 本地扫描仪通过使用 [内置](sensitive-information-type-entity-definitions.md) 或 [自定义敏感信息类型](create-a-custom-sensitive-information-type.md) 检测敏感信息， [标签](sensitivity-labels.md) 或文件属性。 [活动资源管理器](data-classification-activity-explorer.md) 中显示有关用户使用敏感项目的信息，并且通过 [DLP 策略对](create-test-tune-dlp-policy.md)。

## <a name="the-dlp-on-premises-scanner-relies-on-azure-information-protection-scanner"></a>DLP 本地扫描仪依赖于 Azure 信息保护扫描仪

DLP 本地扫描仪依靠完整实施 Azure 信息保护 （AIP） 扫描仪来监视、标记和保护敏感项目。 如果不熟悉 AIP 扫描仪，强烈建议自己熟悉它。 请参阅以下文章：

- [什么是 Azure 信息保护](/azure/information-protection/what-is-information-protection)
- [什么是 Azure 信息保护统一标签扫描仪](/azure/information-protection/deploy-aip-scanner)
- [安装和部署 Azure 信息保护统一标签扫描仪的要求](/azure/information-protection/deploy-aip-scanner-prereqs)
- [教程：安装 Azure 信息保护 （AIP） 统一标签扫描仪](/azure/information-protection/tutorial-install-scanner)
- [配置和安装 Azure 信息保护统一标记扫描器](/azure/information-protection/deploy-aip-scanner-configure-install)
- [Azure 信息保护统一标签客户端 - 版本发布历史记录和支持策略](/azure/information-protection/rms-client/unifiedlabelingclient-version-release-history)

## <a name="dlp-on-premises-scanner-actions"></a>DLP 本地扫描仪操作

DLP 本地扫描仪通过以下四种方法之一来检测文件：

- 敏感信息类型
- 敏感度标签
- 文件扩展名
- 仅 Office 文件的自定义文档属性 

如果检测到的文件存在泄露或合规性策略冲突的风险，DLP 本地扫描仪可能会执行以下四项操作之一。

|操作 |说明  |
|---------|---------|
|**阻止这些用户访问存储在本地扫描仪中的文件 - 每个人** | 强制执行后，此操作将阻止访问除内容所有者、最后一次修改项目的账户和管理员之外的所有账户。为此，可在文件级别删除 NTFS/SharePoint 权限的所有账户，除了文件所有者、存储库所有者（在内容扫描作业中的[设置存储库所有者](/azure/information-protection/deploy-aip-scanner-configure-install#use-a-data-loss-prevention-dlp-policy-public-preview)设置中设置）、最后一次修改者（只能在 SharePoint 中标识）和管理员。也会向扫描仪帐户授予该文件的 FC 权限。|
|**阻止这些用户访问存储在本地扫描仪中的文件 - 阻止组织范围的（公共）访问**    |强制使用时，此操作从文件访问控制列表 （ACL） 中删除 **_Everyone_*_、_*_NT AUTHORITY\经过身份验证的用户_*_和 _*_Domain Users_** SIDs。 只有已明确授予文件或父文件夹权限的用户和组才能访问该文件。|
|**设置对文件的权限**|强制使用时，此操作会强制文件继承其父文件夹的权限。 默认情况下，只有在父文件夹的权限比文件上已有的权限更加严格时，才强制实施此操作。 例如，如果文件的 ACL 设置为仅允许 **_特定用户_*_，并且父文件夹配置为允许 _*_域用户_*_ 组，则该文件不会继承父文件夹权限。可通过选择 _*"继承"来覆盖此行为，即使父权限在管理** 限制。|
|**从不正确的位置删除文件**|强制安装后，此操作用 .txt 扩展名替换原始文件，将原始文件的副本隔离文件夹中。 

## <a name="whats-different-in-the-on-premises-scanner"></a>本地扫描仪中的不同功能

在深入研究本地扫描仪之前，有必要了解一些额外的概念。

### <a name="aip-repositories-and-content-scan-jobs"></a>AIP 存储库和内容扫描作业

必须创建 AIP 内容扫描作业，并确定托管要由 DLP 引擎评估的文件的存储库。 请确保在已创建的 AIP 内容扫描作业中启用 DLP 规则。

### <a name="policy-tips"></a>策略提示

[策略](use-notifications-and-policy-tips.md) 在本地扫描仪中不可用。


### <a name="viewing-dlp-on-premises-scanner-events"></a>查看 DLP 本地扫描仪事件

在 M365 合规中心、活动资源管理器或 [DLP 本地扫描仪](data-classification-activity-explorer.md)。 

## <a name="next-steps"></a>后续步骤

现在已了解 DLP 本地扫描仪，接着将执行以下步骤：

1. [开始使用 DLP 本地扫描仪](dlp-on-premises-scanner-get-started.md)
2. [使用 DLP 本地扫描仪](dlp-on-premises-scanner-use.md)

## <a name="see-also"></a>另请参阅

- [Microsoft 本地扫描仪数据丢失防护入门](dlp-on-premises-scanner-get-started.md)
- [使用 Microsoft 本地扫描仪的数据丢失防护](dlp-on-premises-scanner-use.md)
- [了解数据丢失防护](dlp-learn-about-dlp.md)
- [创建、测试和优化 DLP 策略](create-test-tune-dlp-policy.md)
- [活动资源管理器入门](data-classification-activity-explorer.md)