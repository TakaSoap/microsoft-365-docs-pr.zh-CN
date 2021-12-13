---
title: 在 Microsoft Defender for Business 中创建新策略
description: 了解如何在 Microsoft Defender for Business 中创建新的安全策略
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 663ecf1b998658829e604fd5c9160b4bf0cd09ae
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61421098"
---
# <a name="create-a-new-policy-in-microsoft-defender-for-business-preview"></a>在 Microsoft Defender for Business 预览版中 (策略) 

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向联机内容的链接，这些链接可能介绍 Microsoft Defender for Business 预览版中未包含 (一些) 。

Microsoft Defender for Business (预览) 包括默认策略，这些策略使用推荐设置保护公司设备，自第一天开始。 例如，**你具有使用** 建议的安全设置构建的下一代保护策略和防火墙策略。 但不限于默认策略。 也可以创建新策略，如本文中所述。

> [!TIP]
> 如果要编辑现有策略，请参阅在 Microsoft Defender for Business 中查看或[编辑策略 (预览) 。 ](mdb-view-edit-policies.md)

## <a name="create-a-new-policy"></a>创建新策略

1. 转到 Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () ，然后登录。 

2. 在导航窗格中，选择"**设备配置"。** 策略按操作系统策略 (，Windows **客户端**) 策略类型 (如下一代保护和防火墙) 。   

3. 选择操作系统选项卡 (例如，Windows客户端) ，然后查看下一代保护 **策略** 的列表。 

4. 在 **"下一代保护"或****"防火墙"下**，选择 **"+ 添加"。**

5. 在" **常规信息"** 选项卡上，执行以下步骤：

   1. 指定名称和说明。 此信息将帮助你和团队稍后识别策略。
   2. 查看策略顺序，并在必要时编辑它。  (有关详细信息，请参阅策略 [顺序](mdb-policy-order.md).) 
   3. 选择“**下一步**”。 

7. 在 **"设备组"** 选项卡上，创建新设备组或使用现有组。 策略通过设备组分配给设备。 以下是需要记住的一些内容：

   - 最初，你可能只有默认设备组，其中包括公司中人员用于访问公司数据和电子邮件的设备。 你可以保留和使用默认设备组。
   - 创建新的设备组，以应用具有与默认策略不同的特定设置的策略。 
   - 设置设备组时，请指定某些条件，如操作系统版本。 符合条件的设备包含在该设备组中，除非你排除它们。 
   - 所有设备组（包括定义的默认和自定义设备组）都存储在Azure Active Directory (Azure AD) 。

   若要了解有关设备组的信息，请参阅 。 

8. 在"**配置设置"** 选项卡上，指定策略的设置，然后选择"下一步 **"。** 有关各个设置的详细信息，请参阅 Microsoft [Defender for Business (预览版) 。 ](mdb-next-gen-configuration-settings.md)

9. 在 **"查看策略"** 选项卡上，查看常规信息、目标设备和配置设置。 

   - 通过选择"编辑"进行任何所需的 **更改**。
   - 准备好继续时，选择"创建 **策略"。**

## <a name="next-steps"></a>后续步骤

选择以下一个或多个任务：

- [开始使用 Defender for Business (预览) ](mdb-get-started.md)

- [查看或编辑策略](mdb-view-edit-policies.md)

- [管理设备](mdb-manage-devices.md)

- [查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)