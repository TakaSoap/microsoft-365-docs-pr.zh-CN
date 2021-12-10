---
title: Microsoft Defender for Business 的要求
description: Microsoft Defender for Business 许可证、硬件和软件要求
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/08/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 43ff9e7957e5ec26f3242266c8393bdefdb3240f
ms.sourcegitcommit: 0ee2dabe402d44fecb6856af98a2ef7720d25189
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/09/2021
ms.locfileid: "61374894"
---
# <a name="microsoft-defender-for-business-requirements"></a>Microsoft Defender for Business 要求

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向可能介绍 Microsoft Defender for Business 预览版中未包含的一些 (内容) 。

本文介绍了 Microsoft Defender for Business 的要求。

## <a name="what-to-do"></a>需执行的操作

1. [查看要求并确保满足这些要求](#review-the-requirements)。

2. [继续执行下一步](#next-steps)。

## <a name="review-the-requirements"></a>查看要求

下表列出了配置和使用 Microsoft Defender for Business 的基本要求。 <br/><br/>

| 要求 | 说明 |
|:---|:---|
| 订阅 | Microsoft Defender for Business (预览版！) 。 请参阅[如何获取 Microsoft Defender for Business。](get-defender-business.md)<br/><br/>无需拥有另一个 Microsoft 365 订阅来试用 Microsoft Defender for Business。 |
| 数据中心版 | 以下数据中心位置之一： <br/>- 欧盟 <br/>- 英国 <br/>- 美国 |
| Azure Active Directory (Azure AD) | Azure AD权限和设备组需要此权限。 Azure AD包含在 Defender for Business 订阅中。 若要了解更多信息，请参阅[什么是Azure AD？](/azure/active-directory/fundamentals/active-directory-whatis) |
| 用户帐户 | 创建用户帐户<br/><br/>Microsoft Defender for Business 许可证已分配 <br/><br/>若要获取有关此内容的帮助，请参阅 [添加用户和分配许可证](../../admin/add-users/add-users.md)。 |
| 权限  | 若要访问Microsoft 365 Defender门户，用户必须分配有以下[角色Azure AD](mdb-roles-permissions.md)之一： <br/>- 安全读者<br/>- 安全管理员<br/>- 全局管理员<br/><br/>若要了解更多信息，请参阅 [Microsoft Defender for Business 中的角色和权限](mdb-roles-permissions.md)。 |
| 浏览器要求 | Microsoft Edge 或 Google Chrome |
| 操作系统 | 若要在 Microsoft Defender for Business 中管理设备，你的设备必须运行 Windows 10 Professional/Enterprise 或更高版本 ([KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)) 。 <br/><br/>如果你已在 Microsoft Intune (或 Microsoft Endpoint Manager) 中管理设备，或者如果你使用的是非 Microsoft 设备管理解决方案，你的设备必须运行[Microsoft Defender for Endpoint](../defender-endpoint/minimum-requirements.md)中支持的操作系统之一。 |
| 与 Microsoft Endpoint Manager  |  **在预览版中，可以使用本地脚本载入设备。在这种情况下，与此处列出的Microsoft Endpoint Manager集成的先决条件不是必需的**。 但是，如果你计划使用适用于 Microsoft Endpoint Manager、组策略、System Center Configuration Manager 或移动设备管理的可下载程序包手动将设备载入 Defender for Business，则必须满足以下要求： <br/><br/>设备必须运行 11 Windows 10或 11 Professional/Enterprise ([KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)) 。 <br/><br/>Microsoft Defender for [Endpoint](/mem/intune/protect/mde-security-integration)的安全管理必须满足先决条件。<br/>- Azure AD必须配置为在公司的设备和设备之间创建Azure AD。 <br/>- Defender for Business 必须在 Microsoft Endpoint Manager 中启用安全管理。<br/><br/>设备必须能够连接到以下 URL：<br/>- `enterpriseregistration.windows.net` (注册Azure AD) <br/>- `login.microsoftonline.com` (注册Azure AD) <br/>- `*.dm.microsoft.com` (通配符 (*) 支持用于注册、签入和报告以及随着服务扩展而更改的云服务终结点)  |


## <a name="next-steps"></a>后续步骤

继续：

- [步骤 2：在 Microsoft Defender for Business 中分配角色和权限](mdb-roles-permissions.md) 
 