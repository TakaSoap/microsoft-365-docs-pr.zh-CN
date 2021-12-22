---
title: 'Microsoft Defender for Business 预览版 (的要求) '
description: Microsoft Defender for Business (预览) 许可证、硬件和软件要求
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/21/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 253386571d96c5d2b0e4a4f85896e28eec400f8f
ms.sourcegitcommit: 1a3b79b3dff13a4895dfa4090a22bce2fcd0942b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/22/2021
ms.locfileid: "61597563"
---
# <a name="microsoft-defender-for-business-preview-requirements"></a>Microsoft Defender for Business (预览) 要求

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求[](https://aka.ms/mdb-preview)它的客户和 IT 合作伙伴推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

本文介绍了 Microsoft Defender for Business 预览版 (的要求) 。

## <a name="what-to-do"></a>需执行的操作

1. [查看要求并确保满足这些要求](#review-the-requirements)。

2. [继续执行下一步](#next-steps)。

## <a name="review-the-requirements"></a>查看要求

下表列出了配置和使用 Microsoft Defender for Business 预览版 (的基本) 。 <br/><br/>

| 要求 | 说明 |
|:---|:---|
| 订阅 | Microsoft Defender for Business (预览版！) 。 请参阅[如何获取 Microsoft Defender for Business (预览) 。 ](get-defender-business.md)<br/><br/>**无需拥有另一个 Microsoft 365 订阅来试用 Microsoft Defender for Business** (预览) 。 |
| 数据中心版 | 以下数据中心位置之一： <br/>- 欧盟 <br/>- 英国 <br/>- 美国 |
| 用户帐户 | 创建用户帐户<br/><br/>Microsoft Defender for Business (预览) 许可证已分配 <br/><br/>若要获取有关此内容的帮助，请参阅 [添加用户和分配许可证](../../admin/add-users/add-users.md)。 |
| 权限  | 若要注册 Microsoft Defender for Business (预览) ，你必须是全局管理员。<br/><br/>若要访问Microsoft 365 Defender门户，用户必须分配有以下角色[Azure AD](mdb-roles-permissions.md)之一： <br/>- 安全读者<br/>- 安全管理员<br/>- 全局管理员<br/><br/>若要了解的详细信息，请参阅 Microsoft Defender for Business 中的角色和权限[ (预览) 。 ](mdb-roles-permissions.md) |
| 浏览器要求 | Microsoft Edge 或 Google Chrome |
| 操作系统 | 若要在 Microsoft Defender for Business (预览版) 中管理设备，你的设备必须运行 Windows 10 Professional/Enterprise 或更高版本 ([KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541)) 。 <br/><br/>如果你已在 Microsoft Intune (或 Microsoft Endpoint Manager) 中管理设备，或者如果你使用的是非 Microsoft 设备管理解决方案，你的设备必须运行[Microsoft Defender for Endpoint](../defender-endpoint/minimum-requirements.md)中支持的操作系统之一。 |
| 与 Microsoft Endpoint Manager  |  **在预览版中，可以使用** 本地脚本载入设备，这不需要与Microsoft Endpoint Manager。 但是，如果你计划使用 Microsoft Endpoint Manager、组策略、System Center Configuration Manager 或移动设备管理的可下载程序包手动将设备载入 Defender for Business (预览版) ，则必须满足以下要求： <br/><br/>设备必须在应用[KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) Windows 10 11 Professional/Enterprise (运行) 。 <br/><br/>Microsoft Defender for [Endpoint](/mem/intune/protect/mde-security-integration)的安全管理必须满足先决条件。<br/>- Azure AD配置此配置，以在公司的设备和设备之间创建Azure AD。 <br/>- Defender for Business (预览) 必须在 Microsoft Endpoint Manager 中启用安全管理。<br/><br/>设备必须能够连接到以下 URL：<br/>- `enterpriseregistration.windows.net` (注册Azure AD) <br/>- `login.microsoftonline.com` (注册Azure AD) <br/>- `*.dm.microsoft.com` (通配符 (*) 支持用于注册、签入和报告以及随着服务扩展而更改的云服务终结点)  |

> [!NOTE]
> [Azure Active Directory (Azure AD) ](/azure/active-directory/fundamentals/active-directory-whatis)用于管理用户权限和设备组。 Azure AD包含在 Defender for Business 预览版 (预览版) 订阅中。 
> - 如果在开始试用之前Microsoft 365订阅，Azure AD激活过程中预配此订阅。 
> - 如果在启动 Defender for Business Microsoft 365预览版试用版时， (其他) 订阅，可以使用现有 Azure AD 服务。 
> - 如果你在启动 Defender for [Business](../../business/index.yml) Microsoft 365 商业高级版预览版 () 使用) ，可以选择在 Microsoft Intune 中管理设备。 

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 2：在 Microsoft Defender for Business 预览版中 (角色) ](mdb-roles-permissions.md) 
 
