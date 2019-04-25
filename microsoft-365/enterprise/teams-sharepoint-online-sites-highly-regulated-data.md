---
title: 针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站
author: JoeDavies-MSFT
ms.author: josephd
manager: laurawi
ms.date: 04/03/2019
ms.audience: ITPro
ms.topic: article
ms.service: o365-solutions
localization_priority: Priority
ms.collection:
- M365-security-compliance
- Strat_O365_Enterprise
ms.custom: ''
description: 创建安全的 SharePoint Online 团队网站或 Microsoft Teams 团队以存储最有价值和最敏感的数字资产。
ms.openlocfilehash: 4342ba5e5d1c83ed0c9d26100afd86afa1e62723
ms.sourcegitcommit: 81273a9df49647286235b187fa2213c5ec7e8b62
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/23/2019
ms.locfileid: "32289803"
---
# <a name="microsoft-teams-and-sharepoint-online-sites-for-highly-regulated-data"></a>针对高度管控数据的 Microsoft Teams 和 SharePoint Online 网站

*此方案适用于 Microsoft 365 企业版的 E3 和 E5 版本*

Microsoft 365 企业版包含一整套基于云的服务，使用户可以创建、存储和保护高度管控的数据。这包括符合以下条件的数据：

- 受地区法规约束。
- 组织最有价值的数据，例如商业机密、财务或人力资源信息以及组织策略。

满足此业务需求的 Microsoft 365 企业版基于云的解决方案要求用户执行以下操作：

- 在 SharePoint Online 团队网站或 Microsoft Teams 团队的“文件”**** 选项卡中存储数字资产（文档、幻灯片组、电子表格等）。
- 锁定网站或团队以防止：
   - 通过组成员身份仅访问特定用户帐户组之外的所有用户帐户，其中包括可以访问 SharePoint Online 团队网站以及拥有权限级别的用户帐户以及可以管理它的用户帐户。
   - 网站成员向其他用户授予访问权限。
   - 非网站成员请求访问网站。
- 为 SharePoint Online 网站或团队配置 Office 365 保留标签，将此作为在站点或团队中的文档上定义保留策略的默认方式。
- 阻止用户向组织外发送文件。
- 加密网站或团队中最敏感的数字资产。
- 添加对最敏感的数字资产的权限，这样，即使它们在网站外共享，打开资产仍需要具有权限的用户帐户的有效凭据。

下表将此解决方案的要求映射到 Microsoft 365 企业版的功能。

|||
|:-------|:-----|
| **要求** | **Microsoft 365 企业版 功能** |
| 存储数字资产 | SharePoint Online 团队网站和 Office 365 团队 |
| 锁定网站 | Azure AD 组和 SharePoint Online 团队网站权限 |
| 标记网站的数字资产 | Office 365 保留标签 |
| 阻止向组织外发送文件的用户 | Office 365 中的数据丢失防护 (DLP) 策略 |
| 加密网站的所有数字资产 | 企业移动性 + 安全性 (EMS) 中的 Azure 信息保护子标签 |
| 向网站的数字资产添加权限 | EMS 中的 Azure 信息保护子标签 |
|||

此解决方案要求已经部署：

- [标识](identity-infrastructure.md)以及基础架构的[信息保护](infoprotect-infrastructure.md)阶段的步骤 1 和 2。 
- 对于 SharePoint Online 团队网站中的高度管控数据：[SharePoint Online](sharepoint-online-onedrive-workload.md)。
- 对于 Microsoft Teams 团队中的高度管控数据：[Microsoft Teams](teams-workload.md)。

以下各阶段将指导你完成针对高度管控数据的 SharePoint Online 网站和团队的设计、配置和驱动采用。

若要了解 Contoso Corporation（虚构但具代表性的跨国组织）如何为其研究团队设计 SharePoint Online 网站，请参阅此[示例配置](contoso-sharepoint-online-site-for-highly-confidential-assets.md)。

>[!Note]
>高度管控数据的团队要求首先为高度管控数据创建一个 SharePoint Online 团队网站。然后，创建一个使用 SharePoint Online 团队网站的 Office 365 组的新团队。有关详细信息，请参阅第 2 阶段的步骤 4。
>

## <a name="identity-and-device-access-prerequisites"></a>身份识别和设备访问先决条件

若要保护对团队或 SharePoint Online 网站的访问，请确保已配置[身份识别和设备访问策略](identity-access-policies.md)以及[建议的 SharePoint Online 访问策略](sharepoint-file-access-policies.md)。

## <a name="phase-1-design"></a>第 1 阶段：设计

若要针对高度管控数据创建 SharePoint Online 网站或团队，必须首先确定其用途。例如，制造业组织的研发部门需要 SharePoint Online 网站来存储现有产品的当前设计规范，以及需要一个用于协作研发新产品的位置。只允许研发部门的成员和选定的管理人员访问该网站。

该目的将推动基本配置项的确定，例如：

- SharePoint Online 权限集和 SharePoint 组的集合
- 访问组、Azure AD 安全组及其要添加到 SharePoint 组的成员的集合
- 要分配到网站的 Office 365 保留标签以及标签的 DLP 策略集合
- 用户应用到网站中存储的高度敏感数据资产的 Azure 信息保护子标签的设置

确定后，使用这些设置在第 2 阶段中配置网站。 

### <a name="step-1-an-isolated-sharepoint-online-site"></a>步骤 1：独立 SharePoint Online 网站

SharePoint Online 团队网站的锁定版本称为独立网站。与私有团队网站的默认设置不同，独立网站配置为阻止：

- 访问非指定组成员。
- 请求访问权限。
- 未经授权向指定组的当前成员授予访问权限。
- 访问组成员管理网站。

除非由网站的 SharePoint 管理员操作，否则包含高度管控资产的 SharePoint Online 团队网站的安全性不会改变。

请参阅[设计独立的 SharePoint Online 团队网站](https://docs.microsoft.com/office365/enterprise/design-an-isolated-sharepoint-online-team-site)，详细了解如何确定权限级别、SharePoint 组、访问组和组成员的集合。

### <a name="step-2-office-365-retention-labels-and-dlp-policies"></a>步骤 2：Office 365 保留标签和 DLP 策略

应用于 SharePoint Online 团队网站时，Office 365 保留标签提供对存储在网站上的所有数字资产进行分类的默认方法。
 
对于针对高度管控数据的 SharePoint Online，需要确定要使用的 Office 365 保留标签。

有关 Office 365 标签的设计注意事项，请参阅 [Office 365 分类和标签](https://docs.microsoft.com/office365/securitycompliance/secure-sharepoint-online-sites-and-files#office-365-retention-labels)。

为保护敏感信息并防止意外或故意泄露，可以使用 DLP 策略。有关详细信息，请参阅此[概述](https://docs.microsoft.com/office365/securitycompliance/data-loss-prevention-policies)。

对于针对高度管控数据的 SharePoint Online 网站，必须为分配给网站的 Office 365 保留标签配置 DLP 策略，在用户尝试与外部用户共享数字资产时进行阻止。 

### <a name="step-3-your-azure-information-protection-sub-label"></a>步骤 3：Azure 信息保护子标签

若要为最敏感的数字资产提供加密和一组权限，用户必须使用 Azure 信息保护客户端来应用 Azure 信息保护标签。若要为针对高度管控数据的 SharePoint Online 网站使用 Azure 信息保护标签，必须在范围策略中配置 Azure 信息保护子标签。 

子标签位于现有标签下。例如，可以在“高度机密”标签下创建一个“研发”子标签。范围策略是仅适用于用户子集的策略。对于针对高度管控数据的 SharePoint Online 网站，该范围是作为网站访问组的成员的用户集。

应用的子标签的设置随资产一起移动。即使在网站外部下载和共享，也只有具有权限的经过身份验证的用户帐户才能打开它。

### <a name="design-results"></a>设计结果

已确定以下内容：

- SharePoint 组集及权限级别
- 每个权限级别的访问组及其成员集
- 与标签关联的相应的 Office 365 保留标签和 DLP 策略
- 包含加密和权限的 Azure 信息保护子标签设置

## <a name="phase-2-configure"></a>第 2 阶段：配置

在此阶段中，将执行第 1 阶段中确定的设置并实现这些设置，以针对高度管控的数据创建 SharePoint Online 网站。

### <a name="step-1-create-and-configure-an-isolated-sharepoint-online-team-site"></a>步骤 1：创建和配置独立的 SharePoint Online 团队网站

使用[部署独立的 SharePoint Online 团队网站](https://docs.microsoft.com/office365/enterprise/deploy-an-isolated-sharepoint-online-team-site)中的说明执行以下操作：

- 为网站中使用的每个 SharePoint 权限级别创建并填充访问组。
- 创建并配置独立的团队网站。

### <a name="step-2-configure-the-site-for-an-office-365-retention-label-dlp-policy"></a>步骤 2：针对 Office 365 保留标签 DLP 策略配置网站

按照[使用 Office 365 标签和 DLP 保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-office-365-labels-and-dlp)中的说明执行以下操作：

- 识别或创建 Office 365 保留标签，然后将其应用到独立的 SharePoint Online 网站。
- 创建并配置 DLP 策略，用于在用户尝试于组织外部的 SharePoint Online 网站上共享数字资产时阻止用户。

### <a name="step-3-create-an-azure-information-protection-sub-label-for-the-site"></a>步骤 3：创建网站的 Azure 信息保护子标签

按照[使用 Azure 信息保护来保护 SharePoint Online 文件](https://docs.microsoft.com/office365/enterprise/protect-sharepoint-online-files-with-azure-information-protection)中的说明执行以下操作： 

- 在范围策略中创建并配置 Azure 信息保护子标签。
- 将 Azure 信息保护客户端部署到用户计算机。

### <a name="step-4-optional-create-a-team-for-the-highly-regulated-data"></a>步骤 4（可选）：针对高度管控数据创建团队

如果需要针对高度管控数据的团队，可以首先针对高度管控数据创建一个 SharePoint Online。创建初始私有 SharePoint Online 团队网站时，需要指定一个 Office 365 组名。

完全配置了针对高度管控数据的 SharePoint Online 网站后，使用以下步骤将其转换为针对高度管控数据的团队：

1. 登录 Office 365。
2. 在“Microsoft Office 主页”**** 选项卡上，单击“Teams”****。
3. 从“Microsoft Teams”**** 选项卡上的“加入或创建团队”**** 窗格中，单击“创建团队”****。
4. 在“创建团队”**** 窗格中，单击“从现有 Office 365 组创建团队”****。
5. 在 Office 365 组的列表中，选择针对高度管控数据的 SharePoint Online 网站对应的 Office 365 组的名称，然后单击“选择团队”****。

新团队的“文件”**** 选项卡列出了相应的 SharePoint Online 网站“文档”**** 区域的“常规”**** 文件夹的内容。若要查看团队的 SharePoint Online 网站的其余资源，请单击省略号，然后单击“在 SharePoint 中打开”****。

### <a name="configuration-results"></a>配置结果

已配置了以下内容：

- SharePoint Online 独立网站
- 分配给 SharePoint Online 独立网站的 Office 365 保留标签
- Office 365 保留标签的 DLP 策略
- 用户可以应用到加密资产和强制执行权限的网站中存储的最敏感数字资产的范围策略的 Azure 信息保护子标签
- 基于 SharePoint Online 网站的针对高度管控数据的团队（如果需要）

## <a name="phase-3-drive-user-adoption"></a>第 3 阶段：驱动用户采用

针对高度管控数据的 SharePoint Online 网站或团队只有在始终用于存储和访问敏感数字资产的情况下才能保护该数据。这是最困难的一个阶段，因为它依赖于用户改变他们的方式。 

例如，用于在 USB 驱动器或基于云的个人存储解决方案上存储敏感文件的管理人员现在必须将它们专门存储在针对高度管控数据的 SharePoint Online 网站或团队中。

### <a name="step-1-train-your-users"></a>步骤 1：培训用户

完成配置后，对作为网站访问组成员的一组用户培训以下内容：

- 有关使用新网站或团队保护重要资产的重要性以及高度管控数据泄露的后果，例如法律后果、管制罚款、勒索软件或失去竞争优势。
- 如何访问网站及其资产。
- 如何在网站上创建新文件和上传本地存储的新文件。
- DLP 策略如何阻止它们在外部共享文件。
- 如何使用 Azure 信息保护客户端对最敏感的数字资产标记已配置的子标签。
- 如果资产从网站或团队中泄露，Azure 信息保护子标签如何保护资产。

此培训应包括实践练习，让用户可以体验这些操作及其结果。

### <a name="step-2-conduct-periodic-reviews-of-usage-and-files"></a>步骤 2：定期审查使用情况和文件

在培训后的几周内，SharePoint Online 网站或团队的 SharePoint 管理员可以执行以下操作：

- 分析网站或团队的使用情况，并将其与预期使用情况进行比较。
- 验证是否使用 Azure 信息保护子标签正确标记了高度敏感的文件。

根据需要重新培训用户。

### <a name="user-adoption-results"></a>用户采用结果

敏感数字资产专门存储在针对高度管控数据的 SharePoint Online 网站或团队中，并且已对最敏感的资产应用了已配置的 Azure 信息保护子标签。

## <a name="see-also"></a>另请参阅

[部署指南](deploy-microsoft-365-enterprise.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)

[保护开发/测试环境中的 SharePoint Online 网站安全](https://docs.microsoft.com/office365/enterprise/secure-sharepoint-online-sites-in-a-dev-test-environment)
