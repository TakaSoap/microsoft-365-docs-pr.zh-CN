---
title: 开始使用敏感度标签
f1.keywords:
- CSH
ms.author: cabailey
author: cabailey
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
- SPO_Content
- m365solution-mip
- m365initiative-compliance
search.appverid:
- MOE150
- MET150
description: 已准备好部署敏感度标签以帮助保护组织的数据，但不确定从哪里开始？ 请阅读一些可帮助你使用标签的实用指导。
ms.openlocfilehash: ff003d22df59023233705c216a1c5fdd3207931c
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61371216"
---
# <a name="get-started-with-sensitivity-labels"></a>开始使用敏感度标签

>*[Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。*

如需了解什么是敏感度标签以及该标签如何帮助你保护组织数据，请参阅[了解敏感度标签](sensitivity-labels.md)。

如果拥有 [Azure 信息保护](/azure/information-protection/what-is-information-protection)，并且仍然使用通过 Azure 门户管理的 Azure 信息保护标签，则必须将这些标签迁移到[统一标签平台](/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)。 对于 Windows 计算机，可以[选择将哪个标签客户端用于](/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)已发布的敏感度标签。

如果已准备好使用敏感度标签来开始保护组织的数据：

1. **创建应用程序。** 根据组织的分类法为不同敏感度级别的内容创建和命名敏感度标签。 使用对用户有意义的常用名称或术语。 如果尚未建立分类，请考虑以“个人”、“公共”、“常规”、“机密”和“高度机密”等标签名称开头。 可以使用子标签按类别对类似标签进行分组。 创建标签时，可使用工具提示文本帮助用户选择相应的标签。
    
    有关定义分类法的更多深入指南，请从“[服务信任门户](https://aka.ms/DataClassificationWhitepaper)”下载白皮书“数据分类和敏感度标签分类”。

2. **定义每个标签的用途。** 配置要与每个标签关联的保护设置。 例如，你可能希望较低灵敏度的内容（例如“常规”标签）仅应用页眉或页脚，而较高灵敏度的内容（例如“机密”标签）应该应用水印和加密。

3. **发布标签。** 配置灵敏度标签后，使用标签策略发布它们。 确定应该应用标签的用户和组以及要使用的策略设置。 单个标签可重用，可将其定义一次，然后可将其包含在分配给不同用户的多个标签策略中。 例如，可以通过将标签策略分配给少数用户来试用灵敏度标签。 然后，当你准备在整个组织中推广标签时，可以为标签创建新的标签策略，这次指定所有用户。


> 你可能可以自动创建默认标签，并且可以使用默认标签策略为你完成步骤 1-3。 详细信息请参阅 [Microsoft 信息保护的默认标签和策略](mip-easy-trials.md)。

部署和应用敏感度标签的基本流程如下：

![敏感度标签工作流关系图。](../media/Sensitivity-label-flow.png)

## <a name="subscription-and-licensing-requirements-for-sensitivity-labels"></a>灵敏度标签的订阅和许可要求

许多不同的订阅都支持灵敏度标签，并且用户的许可要求取决于你使用的功能。

若要查看许可用户以便受益于 Microsoft 365 合规性功能的选项，请参阅 [Microsoft 365 安全性与合规性许可指南](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。 对于敏感度标签，请参阅[信息保护：敏感度标签](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance#information-protection-sensitivity-labeling)部分和相关 [PDF 下载](https://go.microsoft.com/fwlink/?linkid=2139145)内容，以了解功能级别许可要求。

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>创建和管理敏感度标签所需的权限

将创建敏感度标签的合规性团队成员需要对Microsoft 365 合规中心的权限。

默认情况下，你的租户的全局管理员有权访问此管理中心，并可向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。要获得这一委派的受限管理员访问权限，请将用户添加到 **合规性数据管理员**、**合规性管理员** 或 **安全管理员** 角色组。 

如果不使用这些默认角色，则可以创建新的角色组，并将 **敏感度标签管理员** 或 **组织配置** 角色添加到此组。对于只读角色，请使用 **敏感度标签读取者**。 

有关将用户添加到默认角色或创建自己的角色组的说明，请参阅 [Microsoft 365 合规中心中的权限](microsoft-365-compliance-center-permissions.md)。

只有在创建和配置灵敏度标签及其标签策略时才需要这些权限。 在应用或服务中应用标这些签时不需要这些权限。 如果与敏感度标签相关的特定配置需要其他权限，则这些权限将在其各自的文档说明中列出。

## <a name="deployment-strategy-for-sensitivity-labels"></a>敏感度标签部署策略
为组织部署敏感度标签的成功策略是创建一个工作虚拟团队，该团队可识别和管理业务和技术要求、概念证明测试、内部检查点和审批以及针对生产环境的最终部署。

建议使用下一节中的表，确定映射到最有影响的业务需求的前一两个场景。 部署这些场景后，返回到列表，确定下一个或两个部署的优先级。

你将在 [Microsoft 信息保护和数据丢失防护的部署加速指南](https://microsoft.github.io/ComplianceCxE/dag/mip-dlp/)中找到有关其他常规部署的指南，这是来自[客户加速团队 (CAT)](https://microsoft.github.io/ComplianceCxE/) 站点的资源之一。

## <a name="common-scenarios-for-sensitivity-labels"></a>敏感度标签的常见场景

所有场景都要求[创建和配置灵敏度标签及其策略](create-sensitivity-labels.md)。

|我想...|文档|
|----------------|---------------|
|管理 Office 应用的敏感度标签，以便在创建内容时对其进行标记 — 包括在所有平台上支持手动标记 |[管理 Office 应用中的敏感度标签](sensitivity-labels-office-apps.md)|
|使用户能够使用 Office 应用、文件资源管理器和 PowerShell 标记和保护 Windows 计算机中的文件|[适用于 Windows 的 Azure 信息保护的统一标记客户端](/azure/information-protection/rms-client/aip-clientv2)|
|使用敏感度标签加密文档和电子邮件，并限制谁可以访问该内容以及可以如何使用它 |[通过敏感度标签应用加密，从而限制对内容的访问](encryption-sensitivity-labels.md)|
|在 Web 上为 Office 启用敏感度标签，支持协同创作、eDiscovery、数据丢失防护和搜索，即便是加密文档也可如此 | [启用 SharePoint 和 OneDrive 中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)
|文档加密后，在 Office 桌面应用中使用共同创作和自动保存 | [为使用敏感度标签加密的文件启用共同创作](sensitivity-labels-coauthoring.md)
|自动将敏感度标签应用于文档和电子邮件 | [将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)|
|使用敏感度标签来保护 Teams和 SharePoint 中的内容 |[将敏感度标签与 Microsoft Teams、Microsoft 365 组和 SharePoint 网站配合使用](sensitivity-labels-teams-groups-sites.md)|
|将敏感度标签应用于文档理解模型，以便自动对 SharePoint 库中标识的文档进行分类和保护 |[在 Microsoft SharePoint Syntex 中向模型应用保留标签](/microsoft-365/contentunderstanding/apply-a-sensitivity-label-to-a-model)|
|阻止或警告用户与特定的灵敏度标签共享文件或电子邮件 |[在 DLP 策略中使用敏感度标签作为条件](dlp-sensitivity-label-as-condition.md) |
|应用保留标签以保留或删除具有特定敏感度标签的文件或电子邮件|[自动应用保留标签来保留或删除内容](apply-retention-labels-automatically.md) |
|发现、标记和保护本地数据存储中存储的文件 |[部署 Azure 信息保护扫描程序以自动分类和保护文件](/azure/information-protection/deploy-aip-scanner)|
|发现、标记和保护云端数据存储中存储的文件|[发现、分类、标记和保护存储在云中的管控和敏感数据](/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|将敏感度标签扩展到 Power BI：启用此功能后，可以在 Power BI 中应用和查看标签，并在数据保存在服务之外时保护数据。|[如何在 Power BI 中应用敏感度标签](/power-bi/admin/service-security-sensitivity-label-overview)|
|监视和了解在我的组织中如何使用灵敏度标签|[了解数据分类](data-classification-overview.md)|
|将灵敏度标签扩展到第三方应用和服务|[Microsoft 信息保护 SDK](/information-protection/develop/overview#microsoft-information-protection-sdk)|
|将敏感度标签扩展到我的 Azure Purview 资产的内容中，如 Azure Blob 存储、Azure 文件存储、Azure Data Lake Storage 和多云数据源|[在 Azure Purview 中贴标签](/azure/purview/create-sensitivity-label) |


## <a name="end-user-documentation-for-sensitivity-labels"></a>敏感度标签的最终用户文档

最有效的最终用户文档将用作你为所选标签名称和配置提供的定制指南和说明。 可使用标签策略设置 **为用户提供指向自定义帮助页面的链接**，以指定本文档的内部链接。 用户可以通过 **灵敏度** 按钮来轻松访问它:

- 有关内置标签: **了解更多** 菜单选项。
- 有关 Azure 信息保护统一标签客户端: **帮助和反馈** 菜单选项 > Microsoft Azure 信息保护对话框中的 **了解更多** 链接。

为帮助提供自定义文档，请参阅以下页面并下载可用于帮助培训用户的内容：[敏感度标签的最终用户培训](https://microsoft.github.io/ComplianceCxE/enduser/sensitivity/)。 

此外，还可使用以下资源来获取基本说明：

- [在Office 的文件和电子邮件中应用敏感度标签](https://support.microsoft.com/en-us/office/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office 中敏感度标签的已知问题](https://support.microsoft.com/en-us/office/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [向 Office 中的文件和电子邮件自动应用或建议敏感度标签](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [有关自动应用或建议敏感度标签的已知问题](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Azure 信息保护统一标记用户指南](/azure/information-protection/rms-client/clientv2-user-guide)

如果你的敏感度标签对 PDF 文档应用了加密，则可以使用 Windows 或 Mac 上的 Microsoft Edge 来打开这些文档。 有关详细信息和备选阅读器，请参阅[受保护的 PDF 支持哪些 PDF 阅读器？](/azure/information-protection/rms-client/protected-pdf-readers#viewing-protected-pdfs-in-microsoft-edge-on-windows-or-mac)
