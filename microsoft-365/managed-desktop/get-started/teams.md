---
title: Microsoft Teams
description: 团队如何安装在设备上并在以后更新
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、应用程序、业务线应用程序、LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: ea2ef7637a8d360e3b598aec4852425d977ae4ec
ms.sourcegitcommit: dffb9b72acd2e0bd286ff7e79c251e7ec6e8ecae
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/17/2020
ms.locfileid: "47950907"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[团队](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) 是组织的 [邮件应用程序](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) ，它还提供了实时协作和通信、会议以及文件和应用共享的工作区。

## <a name="initial-deployment"></a>初始部署

大多数硬件供应商尚未将团队作为其图像的一部分包括在内，因此 Microsoft 托管桌面将使用 Microsoft Intune 将团队部署到你的设备。 所有托管设备都安装了 [团队 .msi 程序包](https://docs.microsoft.com/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) ，以确保登录到设备的所有用户都可以使用 Microsoft 团队。 程序包首次安装完成后，团队会自动启动并向桌面添加快捷方式。

### <a name="microsoft-intune-changes"></a>Microsoft Intune 更改

Microsoft 托管桌面为 Microsoft 团队添加了 Azure AD 组织中的两个应用程序。 将它们部署到适用于设备的64位或32位客户端：  

- 新式工作区–团队内计算机范围的安装程序 x64  
- 新式工作区-团队内计算机范围的安装程序 x32

## <a name="updates"></a>更新

团队遵循来自 Microsoft 365 应用程序的单独更新路径，并且桌面客户端会自动更新自身。 团队每隔几小时检查一次更新，下载这些更新，然后在无提示安装更新之前等待计算机处于空闲状态。  

"团队" 产品组不允许管理员控制更新，因此 Microsoft 托管桌面使用 [标准的自动更新通道](https://docs.microsoft.com/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。

### <a name="manually-updating-teams"></a>手动更新团队

单个用户也可以通过**Check for updates**   在应用程序右上角的 " **配置文件**" 下拉菜单中选择 "检查更新" 来下载更新   。 如果有可用的更新，则会在计算机处于空闲状态时下载并以静默方式安装它。

## <a name="delivery-optimization-of-updates"></a>更新的传递优化

团队更新的传递优化在默认情况下处于启用状态，并且不需要管理员或用户执行任何操作。 