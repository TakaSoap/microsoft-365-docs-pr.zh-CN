---
title: Microsoft Teams
description: 如何在设备上安装 Teams 并随后进行更新
keywords: Microsoft 托管桌面， Microsoft 365， 服务， 文档， 应用， 业务线应用， LOB 应用
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
audience: ITPro
ms.openlocfilehash: 01a3adc7829bbb94f36649f69ba6ef15dbe6b3c2
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50920652"
---
# <a name="microsoft-teams"></a>Microsoft Teams

[Teams](https://www.microsoft.com/microsoft-365/microsoft-teams/group-chat-software) 是 [组织的消息传递](https://support.microsoft.com/office/microsoft-teams-basics-6d5f52e6-5306-4096-ac24-c3082b79eaf0) 应用，它还提供用于实时协作和通信、会议以及文件和应用共享的工作区。

## <a name="initial-deployment"></a>初始部署

大多数硬件供应商尚未将 Teams 作为映像的一部分，因此 Microsoft 托管桌面使用 Microsoft Intune 将 Teams 部署到你的设备。 所有托管设备都安装了 [Teams .msi](/MicrosoftTeams/msi-deployment#how-the-microsoft-teams-msi-package-works) 程序包，从而确保登录到设备的所有用户都准备好使用 Microsoft Teams。 程序包首次安装完成后，Teams 将自动启动，并将快捷方式添加到桌面。

### <a name="microsoft-intune-changes"></a>Microsoft Intune 更改

Microsoft 托管桌面将两个应用程序添加到 Microsoft Teams 的 Azure AD 组织。 它们部署到适用于设备的 64 位或 32 位客户端：  

- 现代工作场所 – Teams 计算机范围安装程序 x64  
- 现代工作场所 – Teams 计算机范围安装程序 x32

## <a name="updates"></a>更新

Teams 遵循 Microsoft 365 企业应用版中的单独更新路径，桌面客户端将自动更新自身。 Teams 每隔几小时检查一次更新，下载更新，然后等待计算机处于空闲状态，然后以无提示方式安装更新。  

Teams 产品组不允许管理员控制更新，因此 Microsoft 托管桌面使用 [标准自动更新频道](/microsoftteams/teams-client-update#can-admins-deploy-updates-instead-of-teams-auto-updating)。

### <a name="manually-updating-teams"></a>手动更新 Teams

单个用户还可以下载更新，具体操作是选择应用右上方的"配置文件"下拉菜单上的"检查    ****   更新"。 如果更新可用，它将在计算机空闲时下载并静默安装。

## <a name="delivery-optimization-of-updates"></a>更新的传递优化

Teams 更新的传递优化默认启用，不需要管理员或用户的操作。