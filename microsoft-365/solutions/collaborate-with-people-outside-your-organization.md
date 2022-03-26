---
title: 与组织外部人员进行协作
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- SPO_Content
- M365-collaboration
- m365solution-securecollab
- m365solution-scenario
- m365initiative-externalcollab
ms.custom:
- seo-marvel-apr2020
- seo-marvel-jun2020
ms.localizationpriority: medium
f1.keywords: NOCSH
recommendations: false
description: 了解如何配置Microsoft 365应用程序Teams、OneDrive和SharePoint组织外部人员进行协作。
ms.openlocfilehash: 65511cbafdc1f5a666c11e1bef7fefd6e6852ee3
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712765"
---
# <a name="collaborating-with-people-outside-your-organization"></a>与组织外部人员进行协作

Microsoft 365中的外部共享功能为组织内部人员提供了与合作伙伴、供应商、客户以及目录中没有帐户的其他人进行协作的机会。 可以与组织外部人员共享整个团队、频道或网站，也可以只共享单个文件。

与组织外部人员协作包括以下主要组件：

- **启用共享** - 配置跨 Azure Active Directory、Teams、Microsoft 365 组和 SharePoint 的共享控件，以允许组织达到希望的共享级别。
- **配置组织** 关系 - 如果使用共享通道，则必须在 Azure Active Directory 中配置跨租户访问设置，以允许每个要协作的组织进行 B2B 直接连接访问。  (这些组织还必须配置与租户的组织关系) 
- 启用 **其他** 安全性 - 虽然基本共享功能可以配置为要求组织外部人员进行身份验证，Microsoft 365 提供了许多其他安全性和合规性功能，以帮助您在外部共享时保护数据和维护管理策略。

阅读[设置安全协作与Microsoft 365和](/microsoft-365/solutions/setup-secure-collaboration-with-teams)Microsoft Teams，了解外部共享如何与整体Microsoft 365协作指南。

## <a name="enable-sharing"></a>启用共享

默认情况下，会启用使用来宾访问或匿名访问与组织外部人员共享，但必须通过在组织中配置组织关系来Azure AD。 大多数来宾共享方案无需进一步配置即可工作。 若要确认你使用的方案的设置或启用新方案，请从以下选项中进行选择：

- [协作处理文档](collaborate-on-documents.md) - 了解如何配置Microsoft 365以允许与组织外部人员共享和协作 (来宾和未经身份验证的用户) 文件和文件夹。
- [在网站中协作](collaborate-in-site.md) - 了解如何配置Microsoft 365以启用与来宾SharePoint网站共享。
- [以团队方式协作](collaborate-as-team.md) - 了解如何配置Microsoft 365以在 Teams 中启用来宾Teams。
- [通过渠道与外部参与者协作](/microsoft-365/solutions/collaborate-teams-direct-connect) ，以在共享频道中与组织外部人员协作。

有关跨组织提供的来宾共享设置的全面Microsoft 365，请参阅Microsoft 365[来宾共享设置参考](microsoft-365-guest-settings.md)。

## <a name="enable-additional-security"></a>启用其他安全性

启用要用于与组织外部人员共享的方案后，请考虑其他安全措施来帮助保护内容，防止意外或有意不当共享。

- [与未经身份验证的用户](best-practices-anonymous-sharing.md) 共享文件和文件夹的最佳实践 - 了解与未经身份验证的用户共享的最佳方案。
- [限制意外曝光](share-limit-accidental-exposure.md) - 了解如何减少意外与组织外部人员共享敏感内容的可能性。
- [创建安全的来宾](create-secure-guest-sharing-environment.md)共享环境 - 了解 Microsoft 365 中提供的工具，以帮助确保以安全的方式与组织外部人员共享，并满足管理要求。

## <a name="collaborate-with-partner-companies"></a>与合作伙伴公司协作

当你处理涉及来自另一个组织的来宾的大型项目时，请考虑共享频道。 由于共享频道不使用来宾帐户，因此另一个组织中用户可以直接访问共享频道，而无需单独登录组织。

如果你有经常更改来宾的供应商关系，可以使用 Azure Active Directory 中的权利管理来简化来宾管理并允许合作伙伴公司共同承担该责任。 有关详细信息 [，请参阅使用托管来宾创建 B2B Extranet](b2b-extranet.md) 。

## <a name="limit-sharing"></a>限制共享

如果网站中的某些共享功能Microsoft 365管理策略冲突，请参阅限制共享Microsoft 365了解限制[](microsoft-365-limit-sharing.md)共享的选项。

## <a name="related-topics"></a>相关主题

[文件协作简介Microsoft 365](/sharepoint/intro-to-file-collaboration)

[规划与 SharePoint 中的文件Microsoft 365](/sharepoint/deploy-file-collaboration)
