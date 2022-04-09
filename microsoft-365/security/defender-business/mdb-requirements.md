---
title: Microsoft Defender 商业版的要求
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
ms.openlocfilehash: dd30af8003e6c5bc6a4348efe16626d2d45317f1
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747064"
---
# <a name="microsoft-defender-for-business-requirements"></a>Microsoft Defender 商业版要求

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

本文介绍Microsoft Defender 商业版的要求。

## <a name="what-to-do"></a>需执行的操作

1. [查看这些要求，并确保满足这些要求](#review-the-requirements)。

2. [继续执行后续步骤](#next-steps)。

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="review-the-requirements"></a>查看要求

下表列出了配置和使用Microsoft Defender 商业版的基本要求。 <br/><br/>

| 要求 | 说明 |
|:---|:---|
| 订阅 | Microsoft 365 商业高级版 <br/>--- 或 ---<br/>Microsoft Defender 商业版 (独立;目前为预览版) 。 <br/><br/> 请参阅[如何获取Microsoft Defender 商业版](get-defender-business.md)。<br/><br/>请注意，如果有多个订阅，则最高订阅优先。 例如，如果已购买Microsoft Defender for Endpoint计划 2 (或试用订阅) ，并且Microsoft Defender 商业版，则 Defender for Endpoint Plan 2 优先。 在这种情况下，你将看不到 Defender for Business 体验。  |
| 数据中心版 | 以下数据中心位置之一： <br/>- 欧盟 <br/>- 英国 <br/>- 美国 |
| 用户帐户 | 用户帐户是在Microsoft 365 管理中心 () [https://admin.microsoft.com](https://admin.microsoft.com) 中创建的<br/><br/>Microsoft 365 管理中心中分配了Microsoft Defender 商业版许可证<br/><br/>若要获取有关此任务的帮助，请参阅 [“添加用户”并分配许可证](../../admin/add-users/add-users.md)。 |
| 权限  | 若要注册Microsoft Defender 商业版，必须是全局管理员。<br/><br/>若要访问Microsoft 365 Defender门户，用户必须在[分配Azure AD中](mdb-roles-permissions.md)具有以下角色之一： <br/>- 安全读取器<br/>- 安全管理员<br/>- 全局管理员<br/><br/>若要了解详细信息，请参阅[Microsoft Defender 商业版中的角色和权限](mdb-roles-permissions.md)。 |
| 浏览器要求 | Microsoft Edge或 Google Chrome |
| 操作系统 | 若要管理Microsoft Defender 商业版中的设备，设备必须运行以下操作系统之一： <br/>- Windows 10 商业版或更高版本 <br/>- Windows 10 Professional或更高版本 <br/>- Windows 10 企业版或更高版本 <br/><br/>确保安装了 [KB5006738](https://support.microsoft.com/topic/october-26-2021-kb5006738-os-builds-19041-1320-19042-1320-and-19043-1320-preview-ccbce6bf-ae00-4e66-9789-ce8e7ea35541) 。 <br/><br/>如果已在Microsoft Intune (或Microsoft Endpoint Manager) 中管理设备，则可以将这些设备载入 Defender for Business。 |

> [!NOTE]
> [Azure Active Directory (Azure AD) ](/azure/active-directory/fundamentals/active-directory-whatis)用于管理用户权限和设备组。 Azure AD包含在 Defender for Business 订阅中。 
> - 如果在开始试用之前没有Microsoft 365订阅，则在激活过程中将为你预配Azure AD。 
> - 如果在启动 Defender for Business 试用版时确实有另一个Microsoft 365订阅，则可以使用现有的Azure AD服务。 
> - 如果在开始 Defender for Business 试用版时使用[Microsoft 365 商业高级版](../../business/index.yml)，则可以选择在Microsoft Intune中管理设备。 

## <a name="next-steps"></a>后续步骤

继续执行[步骤 2：在Microsoft Defender 商业版中分配角色和权](mdb-roles-permissions.md)限。
 