---
title: 在设备上使用Microsoft 365 商业高级版
description: 了解 Microsoft 365 商业高级版
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: how-to
ms.date: 03/08/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 2cc874580dad24e1b3d5349d6075956a9e518704
ms.sourcegitcommit: adea59259a5900cad5de29ddf46d1ca9e9e1c82f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/04/2022
ms.locfileid: "64634638"
---
# <a name="device-groups-in-microsoft-365-business-premium"></a>设备组中Microsoft 365 商业高级版

Microsoft 365 商业高级版通过安全机制提供终结点Microsoft Defender 商业版。 设备保护策略通过称为设备组的某些集合应用于设备。 

**本文介绍**：  

- [什么是设备组](#whats-a-device-group)
- [如何创建新设备组](#how-do-i-create-a-new-device-group)

## <a name="whats-a-device-group"></a>什么是设备组？

设备组是因某些指定条件（如操作系统版本）而分组在一起的设备的集合。 符合条件的设备包含在该设备组中，除非你排除它们。 

借助你的订阅，你具有可以使用的默认设备组。 默认设备组包括已载入 Defender for Business 的所有设备。 但是，还可以创建新的设备组，以将具有特定设置的设备保护策略分配给特定设备。 

所有设备组（包括默认设备组和定义的任何自定义设备组）都存储在[Azure Active Directory (Azure AD) 。](/azure/active-directory/fundamentals/active-directory-whatis)

## <a name="how-do-i-create-a-new-device-group"></a>如何实现创建新设备组？

可以在创建或编辑设备保护策略的过程中创建新的设备组。 

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 在导航窗格中，选择" **设备配置"**。 

3. 执行以下操作之一：

    1. 选择现有策略，然后选择"编辑 **"**。
    
    2. 选择 **" + 添加** "以创建新策略。

    > [!TIP]
    > 若要获取有关创建或编辑策略的帮助，请参阅在策略视图中查看或[编辑Microsoft Defender 商业版](m365bp-view-edit-create-mdb-policies.md)。

4. 在" **常规信息"** 步骤中，查看信息，如有必要进行编辑，然后选择"下一步 **"**。

5. 选择 **" + 创建新组"**。 

6. 指定设备组的名称和说明，然后选择"下一步 **"**。

7. 选择要包括在组中的设备，然后选择"创建 **组"**。

8. 在 **"设备组"** 步骤中，查看策略的设备组列表。 如果需要，请从列表中删除组。 然后选择“**下一步**”。

9. 在" **配置设置"** 页上，根据需要查看和编辑设置，然后选择"下一步 **"**。 有关这些设置详细信息，请参阅了解 Microsoft Defender 商业版 [中的下一代配置设置](../security/defender-business/mdb-next-gen-configuration-settings.md)。

10. 在" **查看策略"步骤** 中，查看所有设置，进行任何所需的编辑，然后选择" **创建** 策略"或" **更新策略"**。


