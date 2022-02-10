---
title: Microsoft 托管桌面中的应用
description: 介绍如何处理应用，包括如何打包、部署和支持它们。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: ce43080c284c4c15be5a8799f70a43de611ff9ba
ms.sourcegitcommit: cafca45069819a44c7cf8c67f6c1e105de1b3393
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/10/2022
ms.locfileid: "62520435"
---
# <a name="apps-in-microsoft-managed-desktop"></a>Microsoft 托管桌面中的应用

<!--This topic is the target for 2 "Learn more" links in the Admin Portal (aka.ms/app-overview;app-package); also target for link from Online resources (aka.ms/app-overviewmmd-app-prep) do not delete.-->

<!--Applications: supported/onboard/deployment -->

## <a name="apps-generally"></a>应用一般

Microsoft 包括某些关键应用，以及Microsoft 365 E3注册所需的 E5 或 E5 Microsoft 托管桌面。 但是，即使我们提供这些应用，你仍然具有某些责任和操作需要完成。

您还可以通过 公司门户 自助服务，或者使用 Microsoft Intune 管道向用户部署其他非 Microsoft 应用。

## <a name="apps-provided-by-microsoft"></a>Microsoft 提供的应用

Microsoft 托管桌面 许可证包含 Microsoft 365 应用版 for Enterprise Standard Suite (Word、Excel、PowerPoint、Outlook、Publisher、Access、Access 等 Microsoft 365 应用版 中的 64 位版本应用。Teams、OneNote.) 

默认情况下，Microsoft Project和Visio即点即用版本不包含，但您可以请求添加这些版本。 有关这些应用详细信息，请参阅在 Microsoft Project 设备上Visio [Microsoft Microsoft 托管桌面安装](../get-started/project-visio.md)。

### <a name="what-microsoft-does-to-support-the-apps-we-provide"></a>Microsoft 为支持我们提供的应用而做哪些工作

Microsoft 将为部署、更新和支持包含的 Microsoft 365 企业应用版 服务。 默认情况下，不包括Microsoft Project Visio *即* 点即用版本。 但是，Microsoft 托管桌面将提供部署组，以允许 IT 管理员管理许可证，并为组织适当地部署这些应用程序。 Microsoft 将支持这些应用程序的用户通过Microsoft 托管桌面支持渠道。

### <a name="what-you-need-to-do-to-support-the-apps-we-provide"></a>需要执行哪些工作来支持我们提供的应用

对于这些应用，仍需要执行某些操作：

| 任务 | 说明 |
| ------ | ------ |
| 分配许可证 | 你负责获取适当的许可证并将其分配给用户进行Microsoft 365 企业应用版。 |
| 将用户添加到安全组 | 如果您使用的是 Microsoft Project 或 Visio，则 IT 管理员必须将这些用户添加到相应的部署组。 IT 管理员还负责在用户离开公司时回收这些用户的许可证。 |
| 部署Microsoft 365加载项 | 如果你需要任何应用的任何加载项，Microsoft 365 企业应用版部署它们，就像在 32 应用中Windows一样。

## <a name="apps-you-provide"></a>你提供的应用

你可能拥有业务操作所需的其他应用。 这些应用只能Microsoft 托管桌面部署管道部署到Microsoft Intune设备。 有关应用程序部署详细信息，请按照将应用部署到Microsoft 托管桌面[中的步骤操作](../get-started/deploy-apps.md)。

### <a name="preparing-your-own-apps-for-inclusion-in-microsoft-managed-desktop"></a>准备自己的应用以包含在Microsoft 托管桌面

查看应用，检查：

- 任何应用均不受禁止或具有受限行为，如Microsoft 托管桌面[要求中所述](../service-description/mmd-app-requirements.md)。
- 应用必须已准备好通过管理Microsoft Intune。 有关详细信息，请参阅使用 [Windows 10 部署应用Microsoft Intune](/intune/apps-windows-10-app-deploy)将[应用添加到Microsoft Intune](/intune/apps-add)。
- 其他预打包要求，如提供许可证密钥、与许可条款的协议以及预先设置服务器连接。

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
1. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看 [来宾帐户的先决条件](guest-accounts.md)。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. [准备用户对数据的访问权限](authentication.md)。
1. 本文 (准备) 。
1. [准备映射的驱动器](mapped-drives.md)。
1. [准备打印资源](printing.md)。
1. 地址 [设备名称](address-device-names.md)。
