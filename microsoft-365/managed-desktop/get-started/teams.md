---
title: Microsoft Teams
description: 如何在Teams设备上安装并随后进行更新
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、应用、业务线应用、LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 525dc7b89e302cdc076336daa7a98c6317855e73
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60212733"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software)是[组织的](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0)消息传递应用，它还提供用于实时协作和通信、会议以及文件和应用共享的工作区。

## <a name="initial-deployment"></a>初始部署

大多数硬件供应商尚未将 Teams作为映像的一Microsoft 托管桌面，因此，Teams使用 Microsoft Intune。 所有托管设备都Teams .msi程序包[](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works)，确保登录到设备的所有用户都Microsoft Teams使用。 程序包首次安装完成后，Teams自动启动，并将快捷方式添加到桌面。

### <a name="microsoft-intune-changes"></a>Microsoft Intune更改

Microsoft 托管桌面向 Azure AD 组织添加两个应用程序，Microsoft Teams。 它们部署到适用于设备的 64 位或 32 位客户端：  

- 现代工作场所 – Teams Machine Wide Installer x64  
- 现代工作区 – Teams Machine Wide Installer x32

## <a name="updates"></a>更新

Teams一个单独的更新路径，Microsoft 365 企业应用版桌面客户端自动更新自身。 Teams每隔几小时检查一次更新，下载这些更新，然后等待计算机处于空闲状态，然后再以无提示方式安装更新。  

the Teams product group doesn't allow admins to control updates， so Microsoft 托管桌面 uses the [standard automatic update channel](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating).

### <a name="manually-updating-teams"></a>手动更新Teams

单个用户还可以下载更新，具体操作是选择应用右上方的"配置文件"下拉菜单上的"检查    ****   更新"。 如果更新可用，它将在计算机空闲时下载并静默安装。

## <a name="delivery-optimization-of-updates"></a>更新的传递优化

默认情况下，Teams更新的传递优化是打开的，不需要管理员或用户的任何操作。