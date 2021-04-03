---
title: Microsoft 托管桌面中的应用
description: 介绍如何处理应用，包括如何打包、部署和支持它们。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: d970ac1a28c62703f648e4fbf6f66e2f825a6188
ms.sourcegitcommit: 53acc851abf68e2272e75df0856c0e16b0c7e48d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/02/2021
ms.locfileid: "51574615"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft 托管桌面中的应用

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>应用一般

Microsoft 包括某些关键应用以及参与 Microsoft 托管桌面所需的 Microsoft 365 E3 或 E5 许可证。 但是，即使我们提供这些应用，你仍具有某些责任和操作需要完成。

还可通过公司门户或所需的后台安装（全部使用 Microsoft Intune 的部署管道）向用户部署其他非 Microsoft 应用进行自助服务。 如果你拥有专业知识，你可以迁移自己所需的应用;或者，Microsoft 咨询服务 (MCS) 或非 Microsoft 供应商将乐于帮助你完成打包和迁移项目。 有关使用 MCS 的信息，请参阅使用 [Microsoft 咨询服务](apps-MCS.md)。


## <a name="apps-provided-by-microsoft"></a>Microsoft 提供的应用

Microsoft 托管桌面许可证包含 Microsoft 365 企业应用标准套件 (Word、Excel、PowerPoint、Outlook、Publisher、Access、Skype for Business 和 One ) Note 中的 64 位版本的应用程序。默认情况下，Microsoft Project 和 Visio 的即点即用版本不包含在内。但你可以请求添加它们。 有关这些应用的信息，请参阅在 Microsoft 托管桌面设备上安装 Microsoft Project 或[Microsoft Visio。](../get-started/project-visio.md)

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft 为支持我们提供的应用而做哪些工作

Microsoft 将为包含的 Microsoft 365 企业应用版应用提供部署、更新和支持的完整服务。 默认情况下不包括 Microsoft Project 和 Visio 的即点即用版本，但 Microsoft 托管桌面将提供部署组，允许 IT 管理员管理许可证并为组织适当地部署这些应用程序。 Microsoft 将通过 Microsoft 托管桌面支持渠道支持这些应用程序的用户。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>需要执行哪些工作来支持我们提供的应用

对于这些应用，仍需要执行某些操作：

- **分配许可证** - 你负责为 Microsoft 365 企业应用版的用户获取和分配相应的许可证。
- **将用户添加到安全组** - 如果使用的是 Microsoft Project 或 Visio，则 IT 管理员必须将这些用户添加到相应的部署组。 IT 管理员还负责在用户离开公司时回收这些用户的许可证。
- **部署 Microsoft 365** 加载项 - 如果你需要任何 Microsoft 365 企业应用版应用的任何加载项，请像任何其他 Windows 32 应用一样集中部署它们。 

## <a name="apps-you-provide"></a>你提供的应用

你可能拥有业务操作所需的其他应用。 这些应用只能使用 Microsoft Intune 的部署管道部署到 Microsoft 托管桌面设备。 如果应用需要它，你可以将其打包为供应商 (该供应商可能是非 Microsoft 供应商或 Microsoft 咨询服务 (MCS) ) 或者如果您具有方法，您可以自己打包它们。 然后，将这些程序包添加到 Microsoft 托管桌面门户，并将其分配给 Azure Active Directory 组以触发部署。 

如果你当前使用 Microsoft Endpoint Configuration Manager 部署应用，Microsoft 托管桌面可以向您提供一个查询来评估你的应用，并发现哪些应用已准备好迁移到 Microsoft Intune 以及哪些可能需要一些调整。


### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>准备你自己的应用以包含在 Microsoft 托管桌面中
查看应用，检查：

- 如 Microsoft 托管桌面应用要求中所述，任何应用均不受禁止或 [具有受限行为](../service-description/mmd-app-requirements.md)。
- 应用必须已准备好由 Microsoft Intune 管理。 有关本主题的详细信息，请参阅使用[Microsoft Intune 的 Windows 10](/intune/apps-windows-10-app-deploy)应用部署和[将应用添加到 Microsoft Intune。](/intune/apps-add)
- 其他预打包要求，如提供许可证密钥、与许可条款的协议以及预先设置服务器连接。

### <a name="decide-how-to-package-apps"></a>确定如何打包应用

一些独立的软件发布者可能要求在集中部署应用之前将其打包。 "打包"意味着应用的安装程序使用许可证密钥、远程服务器位置或桌面快捷方式等设置进行配置，以便可以在后台安装应用。

有三个选项可以打包应用： 


- 你可以自己打包应用
- 你可以与非 Microsoft 供应商合作
- 你可以与 MCS 合作打包应用。 与 Microsoft 客户代表合作。 有关详细信息，请参阅使用 [Microsoft 咨询服务](apps-MCS.md)。



## <a name="deploying-apps"></a>部署应用

无论使用哪种方法打包应用，完成后，你都已准备好按照将应用部署到 [Microsoft 托管桌面设备中的步骤操作](../get-started/deploy-apps.md)。


## <a name="steps-to-get-ready"></a>准备步骤

1. 查看 [Microsoft 托管桌面的先决条件](prerequisites.md)。
2. 使用 [准备情况评估工具](readiness-assessment-tool.md)。
3. [来宾帐户的先决条件](guest-accounts.md)
4. [Microsoft 托管桌面的网络配置](network.md)
5. [为 Microsoft 托管桌面准备证书和网络配置文件](certs-wifi-lan.md)
6. [为 Microsoft 托管桌面准备本地资源访问权限](authentication.md)
7. [Microsoft 托管桌面](apps.md) 应用程序中 (本文) 
8. [为 Microsoft 托管桌面准备映射的驱动器](mapped-drives.md)
9. [为 Microsoft 托管桌面准备打印资源](printing.md)
