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
localization_priority: Priority
ms.collection:
- M365-security-compliance
- SPO_Content
search.appverid:
- MOE150
- MET150
description: 已准备好实现敏感度标签以帮助保护组织的数据，但不确定从哪里开始？ 请阅读一些可帮助你使用标签的实用指导。
ms.openlocfilehash: 6707a61ae2fd9f7dddb7aa63927a53f1795b5127
ms.sourcegitcommit: 1883a103449d7b03d482228bd9ef39a7caf306cf
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/10/2020
ms.locfileid: "42583119"
---
# <a name="get-started-with-sensitivity-labels"></a>开始使用敏感度标签

如需了解什么是敏感度标签以及该标签如何帮助你保护组织数据，请参阅[了解敏感度标签](sensitivity-labels.md)。

如果你有 [Azure 信息保护](https://docs.microsoft.com/azure/information-protection/what-is-information-protection)，请确定是否需要将标签迁移到统一标签平台，以及要使用哪一个标签客户端：
- [如何确定我的租户是否在统一标签平台上？](https://docs.microsoft.com/azure/information-protection/faqs#how-can-i-determine-if-my-tenant-is-on-the-unified-labeling-platform)
- [选择要用于 Windows 计算机的标签客户端](https://docs.microsoft.com/azure/information-protection/rms-client/use-client#choose-which-labeling-client-to-use-for-windows-computers)

如果已准备好使用敏感度标签来开始保护组织的数据：

1. **创建应用程序。** 根据组织的分类法为不同敏感度级别的内容创建和命名敏感度标签。 使用对用户有意义的常用名称或术语。 如果尚未建立分类，请考虑以“个人”、“公共”、“常规”、“机密”和“高度机密”等标签名称开头。 可以使用子标签按类别对类似标签进行分组。 创建标签时，可使用工具提示文本帮助用户选择相应的标签。
    
    有关定义分类法的更多深入指南，请从“[服务信任门户](https://aka.ms/DataClassificationWhitepaper)”下载白皮书“数据分类和敏感度标签分类”。

2. **定义每个标签的用途。** 配置要与每个标签关联的保护设置。 例如，你可能希望较低灵敏度的内容（例如“常规”标签）仅应用页眉或页脚，而较高灵敏度的内容（例如“机密”标签）应该应用水印、加密和端点保护。

3. **发布标签。** 配置灵敏度标签后，使用标签策略发布它们。 确定应该应用标签的用户和组以及要使用的策略设置。 单个标签可重用，可将其定义一次，然后可将其包含在分配给不同用户的多个标签策略中。 例如，可以通过将标签策略分配给少数用户来试用灵敏度标签。 然后，当你准备在整个组织中推广标签时，可以为标签创建新的标签策略，这次指定所有用户。

部署和应用敏感度标签的基本流程如下：

![敏感度标签工作流关系图](../media/Sensitivity-label-flow.png)

## <a name="permissions-required-to-create-and-manage-sensitivity-labels"></a>创建和管理敏感度标签所需的权限

将要创建敏感度标签的合规团队成员需要 Microsoft 365 合规中心、Microsoft 365 安全中心或 Office 365 安全与合规中心的访问权限。 

默认情况下，你的租户的全局管理员有权访问这些管理中心，可向合规专员和其他人提供访问权限，而不为其提供租户管理员的所有权限。要获得这一委派的受限管理员访问权限，请转到其中一个管理中心的**权限**页面，然后将成员添加到**合规性数据管理员**、**合规性管理员**或**安全管理员**角色组。

如果不使用角色，可以创建新的角色组，然后将“**敏感度标签管理员**”或“**组织配置**”角色添加到此组。 有关说明，请参阅[向用户授予对 Office 365 安全与合规中心的访问权限](https://docs.microsoft.com/microsoft-365/security/office-365-security/grant-access-to-the-security-and-compliance-center)。

只有在创建和配置灵敏度标签及其标签策略时才需要这些权限。 在应用或服务中应用标这些签时不需要这些权限。

> [!NOTE]
> **敏感度标签阅读器**是目前正在向租户推出一个新角色，初始支持用于 PowerShell 标记 cmdlet，之后会支持用于管理员标记中心。

## <a name="common-scenarios-for-sensitivity-labels"></a>敏感度标签的常见场景

使用以下文档支持敏感度标签部署：

|我想...|文档|
|----------------|---------------|
|创建并发布有助于保护组织数据的敏感度标签|[创建和配置敏感度标签及其策略](create-sensitivity-labels.md)|
|使用敏感度标签加密文档和电子邮件，并限制谁可以访问该内容以及可以如何使用它 |[通过敏感度标签应用加密，从而限制对内容的访问](encryption-sensitivity-labels.md)|
|为标记为加密的文档启用 SharePoint（和 OneDrive）中的协作功能 | [启用 SharePoint 和 OneDrive（公共预览版）中 Office 文件的敏感度标签](sensitivity-labels-sharepoint-onedrive-files.md)
|管理 Office 应用的敏感度标签，以便在创建内容时对其进行标记 |[在 Office 应用中使用敏感度标签](sensitivity-labels-office-apps.md)|
|创建内容时，自动对用户应用敏感度标签或建议标签 | [将敏感度标签自动应用于内容](apply-sensitivity-label-automatically.md)|
|使用敏感度标签来保护 Teams和 SharePoint 中的内容 |[将敏感度标签与 Microsoft Teams、Office 365 组和 SharePoint 网站（公共预览版）配合使用](sensitivity-labels-teams-groups-sites.md)|
|发现、标记和保护本地数据存储中存储的文件 |[部署 Azure 信息保护扫描程序以自动分类和保护文件](https://docs.microsoft.com/azure/information-protection/deploy-aip-scanner)|
|发现、标记和保护云端数据存储中存储的文件|[发现、分类、标记和保护存储在云中的管控和敏感数据](https://docs.microsoft.com/cloud-app-security/best-practices#discover-classify-label-and-protect-regulated-and-sensitive-data-stored-in-the-cloud)|
|直观地显示敏感度标签的使用情况，以报告部署状态和精细调整标签配置|[使用标签分析查看标签使用情况](label-analytics.md)|


## <a name="end-user-documentation-for-sensitivity-labels"></a>敏感度标签的最终用户文档

最有效的最终用户文档将用作你为所选标签名称和配置提供的定制指南和说明。 但你可通过以下资源查看基本说明：   

- [将敏感度标签应用到 Office 中的文件和电子邮件](https://support.office.com/article/apply-sensitivity-labels-to-your-files-and-email-in-office-2f96e7cd-d5a4-403b-8bd7-4cc636bae0f9)
    - [Office 中敏感度标签的已知问题](https://support.office.com/en-us/article/known-issues-with-sensitivity-labels-in-office-b169d687-2bbd-4e21-a440-7da1b2743edc)

- [向 Office 中的文件和电子邮件自动应用或建议敏感度标签](https://support.office.com/article/automatically-apply-or-recommend-sensitivity-labels-to-your-files-and-emails-in-office-622e0d9c-f38c-470a-bcdb-9e90b24d71a1)
    - [有关自动应用或建议敏感度标签的已知问题](https://support.office.com/article/known-issues-with-automatically-applying-or-recommending-sensitivity-labels-451698ae-311b-4d28-83aa-a839a66f6efc)

- [Azure 信息保护统一标记用户指南](https://docs.microsoft.com/azure/information-protection/rms-client/clientv2-user-guide)


