---
title: Microsoft Defender for Business 中的设备组
description: 了解 Microsoft Defender for Business 中的设备组
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 12/10/2021
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 350228d45124ddf9f1c6e0b9e030ef125bc3ff2c
ms.sourcegitcommit: b1066b2a798568afdea9c09401d52fa38fe93546
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/13/2021
ms.locfileid: "61423883"
---
# <a name="device-groups-in-microsoft-defender-for-business-preview"></a>Microsoft Defender for Business 预览版中的 (组) 

> [!IMPORTANT]
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 本文包含指向联机内容的链接，这些链接可能介绍 Microsoft Defender for Business 预览版中未包含 (一些) 。

在 Microsoft Defender for Business (预览) 中，策略通过称为设备组的某些集合应用于设备。 

**本文介绍**：  

- [什么是设备组](#what-is-a-device-group)   
- [如何在 Defender for Business 中创建设备组](#create-a-new-device-group)

## <a name="what-is-a-device-group"></a>什么是设备组？

设备组是因某些指定条件（如操作系统版本）而分组在一起的设备的集合。 符合条件的设备包含在该设备组中，除非你排除它们。 在 Microsoft Defender for Business (预览) ，通过使用设备组将策略应用于设备。 

Defender for Business (预览) 包括可以使用的默认设备组。 默认设备组包括已载入 Defender for Business (预览版) 。 但是，还可以创建新的设备组，以将具有特定设置的策略分配给某些设备。 

所有设备组（包括默认设备组和定义的任何自定义设备组）都存储在[Azure Active Directory (Azure AD) 。](/azure/active-directory/fundamentals/active-directory-whatis)

## <a name="create-a-new-device-group"></a>创建新的设备组

目前，在 Defender for Business (预览版) 中，可以在创建或编辑策略的过程中创建新设备组，如以下过程所述： 

1. 转到"Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () 并登录。

2. 在导航窗格中，选择"**设备配置"。** 

3. 执行以下操作之一：

    1. 选择现有策略，然后选择"编辑 **"。**
    2. 选择 **" + 添加** "以创建新策略。

    > [!TIP]
    > 若要获取有关创建或编辑策略的帮助，请参阅在 [Microsoft Defender for Business 中查看或编辑策略](mdb-view-edit-policies.md)。

4. 在"**常规信息"** 步骤中，查看信息，如有必要进行编辑，然后选择"下一步 **"。**

5. 选择 **" + 创建新组"。** 

6. 指定设备组的名称和说明，然后选择"下一步 **"。**

7. 选择要包括在组中的设备，然后选择"创建 **组"。**

8. 在 **"设备组"** 步骤中，查看策略的设备组列表。 如果需要，请从列表中删除组。 然后选择“**下一步**”。

9. 在"**配置设置"** 页上，根据需要查看和编辑设置，然后选择"下一步 **"。** 有关这些设置详细信息，请参阅配置 [设置](mdb-next-gen-configuration-settings.md)。

10. 在"**查看策略"步骤** 中，查看所有设置，进行任何所需的编辑，然后选择"**创建** 策略"或"**更新策略"。**

## <a name="next-steps"></a>后续步骤

选择以下一个或多个任务：

- [查看或编辑策略](mdb-view-edit-policies.md)

- [创建新策略](mdb-create-new-policy.md)

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)

- [在 Microsoft Defender for Business 预览版中响应 (缓解) ](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)