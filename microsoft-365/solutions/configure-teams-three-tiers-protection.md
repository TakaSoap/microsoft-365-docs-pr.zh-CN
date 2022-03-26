---
title: 使用三层文件共享安全性配置 Teams
f1.keywords: NOCSH
ms.author: mikeplum
author: MikePlumleyMSFT
manager: serdars
audience: ITPro
ms.topic: conceptual
ms.service: O365-seccomp
ms.localizationpriority: high
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- M365-security-compliance
- m365solution-securecollab
- m365solution-scenario
ms.custom:
- Ent_Architecture
- seo-marvel-jun2020
ms.assetid: 1d51bd87-17bf-457c-b698-61821de3afa0
recommendations: false
description: 了解如何使用三层保护配置 Teams 以实现更好的文件共享安全性，从而平衡安全性和易于协作。
ms.openlocfilehash: 116675ac6736e1761286226a8bf724915627574f
ms.sourcegitcommit: 46456ca009c9d50622e57e24269be74986184654
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/22/2022
ms.locfileid: "63712712"
---
# <a name="configure-teams-with-three-tiers-of-protection"></a>配置具有三层保护的 Teams

本系列中的文章为如何在 Microsoft Teams 中配置团队及其关联 SharePoint 网站以实现通过轻松协作权衡安全性的文件保护提供了相关建议。

本文定义四个不同的配置，从具有最开放共享策略的公共团队开始。每一个附加配置意味着保护有意义的步骤，同时将团队中存储的文件的访问权限和协作功能减少到相关团队成员数量。 

本文中的配置符合 Microsoft 针对数据、标识和设备的三层保护的建议：

- 基线保护

- 敏感保护

- 高度敏感保护

有关这些保护层以及针对每层建议的功能的详细信息，请参阅[面向企业架构师的 Microsoft 云图解](./cloud-architecture-models.md)。


## <a name="three-tiers-at-a-glance"></a>三个层级概览

下表总结了各层的配置。 使用这些配置作为起点建议并调整网站配置，以满足组织的需求。 可能不需要每一层。

|-|基准（公共）|基准（专用）|敏感|高度敏感|
|:-----|:-----|:-----|:-----|:-----|
|专用或公用团队|公开|Private|Private|Private|
|谁可以访问？|组织中的每个人（包括 B2B 用户）。|仅限团队成员。 其他人可以请求访问关联的网站。|仅限团队成员。|仅限团队成员。|
|专用频道|所有者和成员可以创建专用频道|所有者和成员可以创建专用频道|仅所有者可创建专用频道|仅所有者可创建专用频道|
|共享频道|所有者和成员可以创建共享频道|所有者和成员可以创建共享频道|仅所有者可以创建共享频道|仅所有者可以创建共享频道|
|网站级别来宾访问|**新来宾和现有来宾**（默认值）。|**新来宾和现有来宾**（默认值）。|**新来宾和现有来宾** 或 **仅组织中的人员** 取决于团队需求。|**新来宾和现有来宾** 或 **仅组织中的人员** 取决于团队需求。|
|网站共享设置|**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**。|**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**。|**网站所有者和成员以及拥有编辑权限的人员可共享文件和文件夹，但只有网站所有者才可共享网站**。|**仅网站所有者可以共享文件、文件夹和网站**。<br>访问请求 **关闭**。|
|网站级别未托管设备的访问|**从桌面版应用程序、移动应用程序和 web 完全访问**（默认值）。|**从桌面版应用程序、移动应用程序和 web 完全访问**（默认值）。|**允许限制性的 web 访问**。|**阻止访问**。|
|默认共享链接类型|**仅组织内部人员**|**仅组织内部人员**|**特定人员**|**现有访问权限者**|
|敏感度标签|无|无|敏感度标签用于对团队进行分类并控制来宾共享和未托管设备访问。|敏感度标签用于对团队进行分类并控制来宾共享和未托管设备访问。 还可在文件上使用标签对文件进行加密。|

[具有安全隔离的团队](secure-teams-security-isolation.md)是高度敏感选项的变体，为一个团队使用唯一敏感度标签，从而提供更高的安全性。 可以使用此标签来加密文件，只有该团队成员才能读取它们。

基线保护包括公共和私人团队。 组织中的任何人均可发现和访问公共团队。 只有团队成员可以发现和访问私人团队。 这两种配置都将共享 SharePoint 网站的共享限制为团队所有者，以帮助进行权限管理。

敏感和高度敏感保护团队是私有团队，在该团队中对关联站点的共享和访问请求受到限制，并且敏感度标签用于设置有关来宾共享、设备访问和内容加密策略。

## <a name="sensitivity-labels"></a>敏感度标签

敏感层和高度敏感层使用敏感度标签来帮助保护团队和其文件。 若要实现这些层，必须启用 [用于保护 Microsoft Teams、Office 365 和 SharePoint 网站中内容的敏感度标签](../compliance/sensitivity-labels-teams-groups-sites.md)。

虽然基线层不需要敏感度标签，但请考虑创建“常规”标签，然后要求标记所有团队。 这将有助于确保用户在创建团队时就敏感度做出有意识的选择。 如果计划部署敏感或高度敏感层，建议创建一个“常规”标签，该标签可用于基线团队和不敏感的文件。

如果不熟悉敏感度标签，建议阅读[敏感度标签](../compliance/get-started-with-sensitivity-labels.md)以开始使用。 

如果已经在组织中推出了敏感度标签，请考虑敏感和高度敏感层中所使用的标签如何与整体标签策略配合使用。 

## <a name="sharing-the-sharepoint-site"></a>共享 SharePoint 网站

每个团队都有存储文档的关联 SharePoint 网站。 （这是团队渠道中的“**文件**”选项卡。）SharePoint 网站保留自己的权限管理，但关联到团队权限。 团队所有者被包含为网站所有者，而团队成员被包含为关联网站中的站点成员。

生成的权限允许：

- 团队所有者管理网站，并对网站内容拥有完全控制权。
- 团队成员在网站上创建和编辑文件。 

默认情况下，团队所有者和成员可以与团队外部的人员共享网站本身，而无需将其实际添加到团队中。 建议不要使用此方法，因为这会让用户管理变得复杂，并可能会导致非团队成员的人员能够在团队拥有者不知情的情况下存取团队文件。 为了防止这种情况，从基线保护级别开始，我们建议仅允许所有者直接共享站点。

尽管团队没有只读权限选项，但 SharePoint 网站有这项权限。如果你的合作伙伴组利益干系人需要能够查看团队文件但是不进行编辑，则考虑直接将其添加至具有“读取”权限的 SharePoint 网站。

## <a name="sharing-files-and-folders"></a>共享文件和文件夹

默认情况下，团队所有者和成员都可以与团队外部的人员共享文件和文件夹。 如果允许来宾共享，则其中可能包括组织外部人员。 在所有三个层中，我们都会更新默认共享链接类型，有助于避免意外的过度共享。 在高度敏感层中，我们仅将这种共享限制为团队所有者。

## <a name="sharing-with-people-outside-your-organization"></a>与组织外部用户共享

如果需要与组织外部的人员共享 Teams 内容，有两个选项:

- **来宾共享** - 来宾共享使用 Azure AD B2B 协作，使用户能够与组织外部的人员共享文件、文件夹、网站、组和团队。 这些人通过使用目录中的来宾帐户访问共享资源。
- **共享频道** - 共享通道使用 Azure AD B2B 直接连接，这允许用户与其他 Azure AD 组织中的人员共享组织中的资源。 这些人通过使用自己的工作或学校帐户访问 Teams 中的共享频道。 组织中未创建任何来宾帐户。

根据具体情况，来宾共享和共享频道都很有用。 请参阅 [规划外部协作](plan-external-collaboration.md)，了解有关每个方案的详细信息以及如何确定在特定情况下要使用的协议。

如果计划使用来宾共享，建议配置 [SharePoint 和 OneDrive 与 Azure AD B2B](/sharepoint/sharepoint-azureb2b-integration-preview) 集成，以获得最佳的共享和管理体验。

Teams 来宾共享默认处于打开状态，但你可以通过使用敏感度标签在敏感层和高度敏感层中根据需要将其关闭。 默认情况下，共享频道处于打开状态，但需要为要与之协作的每个组织设置跨组织关系。 有关详细信息，请参阅 [与频道中的外部参与者进行协作](collaborate-teams-direct-connect.md)。

在高度敏感层，我们将敏感度标签配置为加密应用标签的文件。 如果需要来宾访问这些文件，必须在创建标签时必须授予他们权限。 共享频道中的外部参与者无法获得敏感度标签的权限，也无法访问通过敏感度标签加密的内容。

如果需要与组织外部的人员进行协作，强烈建议基线层和敏感层或高度敏感层启用来宾共享。 相比将文件作为附件发送到电子邮件中，Microsoft 365 的来宾共享功能提供了更为安全和可管理的共享体验。 用户使用不受管制的消费产品与合法的外部合作者共享时，还降低了影子 IT 的风险。

如果你定期与其他使用 Azure AD 的组织协作，则共享频道可能是一个不错的选择。 共享频道在其他组织的 Teams 客户端中无缝显示，并允许外部参与者使用其组织的常规用户帐户，而无需单独使用来宾帐户登录。

请参阅以下参考材料，为组织创建安全高效的来宾共享环境：

- [有关与未经认证用户共享文件和文件夹的最佳做法](best-practices-anonymous-sharing.md)
- [在与组织外人员共享文件时限制意外公开信息](share-limit-accidental-exposure.md)
- [创建安全的来宾共享环境](create-secure-guest-sharing-environment.md)

## <a name="access-from-unmanaged-devices"></a>非托管设备的访问

对于敏感层和高度敏感层，我们使用敏感度标签限制对 SharePoint 内容的访问。 Azure AD 条件访问提供很多用于确定用户如何访问 Microsoft 365 的选项，包括基于位置、风险、设备合规性和其他因素的限制。 建议阅读[什么是条件访问？](/azure/active-directory/conditional-access/overview)，并考虑哪些其他策略可能适用于你的组织。

请注意，来宾通常没有你组织管理的设备。如果允许来宾进入任何层，请考虑他们将使用哪些设备访问团队和网站并相应地设置非托管设备策略。

### <a name="control-device-access-across-microsoft-365"></a>控制跨 Microsoft 365 的设备访问

在敏感度标签中的非托管设备设置仅影响 SharePoint 访问。 如果要将非托管设备的控制范围扩展到 SharePoint 之外，可以改为 [为组织安装的所有应用和服务创建 Azure Active Directory 条件访问策略](/azure/active-directory/conditional-access/howto-conditional-access-policy-compliant-device)。 若要专门为 [Microsoft 365 服务](/azure/active-directory/conditional-access/concept-conditional-access-cloud-apps#office-365) 配置此策略，请在“**云应用或操作**”下选择“**Office 365**”云应用。

![Azure Active Directory 条件访问策略中 Office 365 云应用的屏幕截图。](/sharepoint/sharepointonline/media/azure-ca-office365-policy.png)

使用影响所有 Microsoft 365 服务的策略可以为用户带来更好的安全性和更好的体验。例如，当仅阻止访问 SharePoint 中非托管设备时，用户可以使用非托管设备访问团队中的聊天，但当用户尝试访问“**文件**”选项卡时将失去访问权限。使用 Office 365 云应用有助于避免 [服务依赖项](/azure/active-directory/conditional-access/service-dependencies) 的问题。

## <a name="next-step"></a>后续步骤

首先[配置基线保护级别](configure-teams-baseline-protection.md)。 如果需要，可在基线上添加[敏感保护](configure-teams-sensitive-protection.md)和[高度敏感保护](configure-teams-highly-sensitive-protection.md)。

## <a name="see-also"></a>另请参阅

[Microsoft Teams 中的安全性和合规性](/microsoftteams/security-compliance-overview)

[安全与合规中心警报策略](../compliance/alert-policies.md)
