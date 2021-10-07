---
title: Microsoft 托管桌面中的应用
description: 介绍如何处理应用，包括如何打包、部署和支持它们。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: e3ac937a4ff98d853ad16ef4ae5854da70fa4d99
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60213957"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft 托管桌面中的应用

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->
 
## <a name="apps-generally"></a>应用一般

Microsoft 包括某些关键应用，以及Microsoft 365 E3加入应用所需的 E5 或 Microsoft 托管桌面。 但是，即使我们提供这些应用，你仍然具有某些责任和操作需要完成。

此外，还可以向用户部署其他非 Microsoft 应用，以便通过 公司门户 或所需的后台安装进行自助服务，所有这些应用Microsoft Intune部署的管道。 

## <a name="apps-provided-by-microsoft"></a>Microsoft 提供的应用

Microsoft 托管桌面 许可证包含 Microsoft 365 企业应用版 Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Teams 和 OneNote.) 即点即用版本的 Microsoft Project 和 Visio 中的 64 位版本，但您可以请求添加它们。  有关这些应用详细信息，请参阅在 Microsoft Project 设备上Visio [Microsoft Microsoft 托管桌面安装](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft 为支持我们提供的应用而做哪些工作

Microsoft 将为包含的 Microsoft 365 企业应用版 应用提供部署、更新和支持的完整服务。 默认情况下不包含 Microsoft Project 和 Visio 即点即用版本，但Microsoft 托管桌面 将提供部署组，让 IT 管理员能够管理许可证并为组织适当地部署这些应用程序。 Microsoft 将支持这些应用程序的用户通过Microsoft 托管桌面支持渠道。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>需要执行哪些工作来支持我们提供的应用

对于这些应用，仍需要执行某些操作：

- **分配** 许可证 - 你负责获取适当的许可证并将其分配给用户进行Microsoft 365 企业应用版。
- **将用户添加到安全组**- 如果使用 Microsoft Project 或 Visio，则 IT 管理员必须将这些用户添加到相应的部署组。 IT 管理员还负责在用户离开公司时回收这些用户的许可证。
- **Deploy Microsoft 365 Add-ons** - If you need any Add-ons for any of the Microsoft 365 企业应用版 apps， deploy them centrally like any other Windows 32 app. 

## <a name="apps-you-provide"></a>你提供的应用

你可能拥有业务操作所需的其他应用。 这些应用只能Microsoft 托管桌面部署管道部署到Microsoft Intune设备。 有关应用程序部署详细信息，请按照将应用部署到Microsoft 托管桌面[中的步骤操作](../get-started/deploy-apps.md)。

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>准备自己的应用以包含在Microsoft 托管桌面
查看应用，检查：

- 任何应用都不被禁止或具有受限行为，如Microsoft 托管桌面[要求中所述](../service-description/mmd-app-requirements.md)。
- 应用必须已准备好通过管理Microsoft Intune。 有关本主题的详细信息，请参阅Windows 10[应用部署和](/intune/apps-windows-10-app-deploy)Microsoft Intune应用[Microsoft Intune。](/intune/apps-add)
- 其他预打包要求，如提供许可证密钥、与许可条款的协议以及预先设置服务器连接。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
2. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看 [来宾帐户的先决条件](guest-accounts.md)。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. [准备用户对数据的访问权限](authentication.md)。
1. 本文 (准备) 。
1. [准备映射的驱动器](mapped-drives.md)。
1. [准备打印资源](printing.md)。
1. 地址 [设备名称](address-device-names.md)。
