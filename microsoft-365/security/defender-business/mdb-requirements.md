---
title: Microsoft Defender 商业版
description: Microsoft Defender 商业版许可证、硬件和软件要求
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 04/01/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 9fd082160640c239424ec75ff58c695a0175d630
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634924"
---
# <a name="microsoft-defender-for-business-requirements"></a>Microsoft Defender 商业版要求

> [!IMPORTANT]
> Microsoft Defender 商业版 2022 年 3 [Microsoft 365 商业高级版](../../business-premium/index.md) 1 开始向客户推出。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

本文介绍Microsoft Defender 商业版。

## <a name="what-to-do"></a>需执行的操作

1. [查看要求并确保满足这些要求](#review-the-requirements)。

2. [继续执行下一步](#next-steps)。

>
> **有空吗？**
> 请参加<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">我们的简短调查，了解Microsoft Defender 商业版</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="review-the-requirements"></a>查看要求

下表列出了配置和使用 Microsoft Defender 商业版。 <br/><br/>

| 要求 | 说明 |
|:---|:---|
| 订阅 | Microsoft 365 商业高级版 <br/>--- 或 ---<br/>Microsoft Defender 商业版 (独立版;当前处于预览) 。 <br/><br/> 请参阅[如何获取Microsoft Defender 商业版](get-defender-business.md)。<br/><br/>请注意，如果你有多个订阅，则优先使用最高订阅。 例如，如果你已Microsoft Defender for Endpoint计划 2 (订阅或试用订阅) ，Microsoft Defender 商业版 Defender for Endpoint Plan 2 优先。 在这种情况下，你将看不到 Defender for Business 体验。  |
| 数据中心版 | 以下数据中心位置之一： <br/>- 欧盟 <br/>- 英国 <br/>- 美国 |
| 用户帐户 | 用户帐户是在用户帐户Microsoft 365 管理中心 () [https://admin.microsoft.com](https://admin.microsoft.com)<br/><br/>Microsoft Defender 商业版许可证分配在Microsoft 365 管理中心<br/><br/>若要获取有关此任务的帮助，请参阅 [添加用户和分配许可证](../../admin/add-users/add-users.md)。 |
| 权限  | 若要注册Microsoft Defender 商业版，你必须是全局管理员。<br/><br/>若要访问Microsoft 365 Defender门户，用户必须分配有以下角色[Azure AD](mdb-roles-permissions.md)之一： <br/>- 安全读者<br/>- 安全管理员<br/>- 全局管理员<br/><br/>若要了解更多信息，请参阅角色[和Microsoft Defender 商业版](mdb-roles-permissions.md)。 |
| 浏览器要求 | Microsoft Edge 或 Google Chrome |
| 操作系统 | 若要在 Microsoft Defender 商业版中管理设备，设备必须运行以下操作系统之一： <br/>- Windows 10 商业版或更高版本 <br/>- Windows 10 Professional或更高版本 <br/>- Windows 10 企业版或更高版本 <br/><br/>确保已安装 [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) 。 <br/><br/>如果你已在管理设备或Microsoft Intune (Microsoft Endpoint Manager) ，你可以将这些设备载入 Defender for Business。 |

> [!NOTE]
> [Azure Active Directory (Azure AD) ](/azure/active-directory/fundamentals/active-directory-whatis)用于管理用户权限和设备组。 Azure AD包含在 Defender for Business 订阅中。 
> - 如果你在开始试用Microsoft 365没有订阅，Azure AD激活过程中将预配你的订阅。 
> - 如果你在启动 Defender for Business Microsoft 365有其他订阅，可以使用现有的 Azure AD 服务。 
> - 如果你在启动 [Defender for Business Microsoft 365 商业高级版](../../business/index.yml)时使用的是应用，可以选择在 Microsoft Intune 中管理设备。 

## <a name="next-steps"></a>后续步骤

继续：

- [步骤 2：分配角色和Microsoft Defender 商业版](mdb-roles-permissions.md) 
 