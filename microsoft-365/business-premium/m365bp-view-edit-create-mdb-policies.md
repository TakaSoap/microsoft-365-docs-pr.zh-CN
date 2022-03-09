---
title: 查看或编辑设备保护策略
description: 查看、编辑、创建和删除设备保护策略Microsoft 365 商业高级版
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/08/2022
ms.prod: m365-security
ms.technology: mdb
localization_priority: Normal
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 95bce75fdee629a40907afda04999c6abf1c0e5b
ms.sourcegitcommit: a9266e4e7470e8c1e8afd31fef8d266f7849d781
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/09/2022
ms.locfileid: "63406502"
---
# <a name="view-and-edit-your-device-protection-policies"></a>查看和编辑设备保护策略

在Microsoft 365 商业高级版中，托管设备的安全设置通过设备保护策略进行配置。 为了帮助简化设置和配置体验，你具有预配置的策略，可在载入组织设备后帮助保护这些设备。 可以使用默认策略、编辑策略或创建自己的策略。

**本文介绍如何**：

- 大致了解默认策略
- 查看现有策略
- 编辑现有策略
- 创建新策略

## <a name="default-device-protection-policies"></a>默认设备保护策略

Microsoft 365 商业高级版包括两种主要类型的策略来保护组织的设备：

- **下一代保护** 策略，用于确定Microsoft Defender 防病毒和其他威胁防护功能的配置方式

- **防火墙** 策略，可确定允许哪些网络流量流入和流出组织设备

这些策略是 Microsoft Defender for Business 的一部分，包含在你的 Microsoft 365 商业高级版 订阅中。

## <a name="view-your-existing-device-protection-policies"></a>查看现有设备保护策略

1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。 

2. 在导航窗格中，选择" **设备配置"**。 策略按操作系统策略 (，Windows **客户端**) 策略类型 (如下一代保护和防火墙) 。  

3. 选择操作系统选项卡 (例如，Windows客户端) ，然后查看  下一代保护和防火墙类别下 **的策略** 列表。 

4. 若要查看有关策略的更多详细信息，请选择其名称。 将打开一个侧窗格，该窗格提供有关该策略的详细信息，例如受该策略保护的设备。

## <a name="edit-an-existing-device-protection-policy"></a>编辑现有设备保护策略

1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。 

2. 在导航窗格中，选择" **设备配置"**。 策略按操作系统策略 (，Windows **客户端**) 策略类型 (如下一代保护和防火墙) 。  

3. 选择操作系统选项卡 (例如，Windows客户端) ，然后查看  下一代保护和防火墙类别下 **的策略** 列表。 

4. 若要编辑策略，请选择其名称，然后选择"编辑 **"**。

5. 在" **常规信息"** 选项卡上，查看信息。 如有必要，可以编辑说明。 然后选择“**下一步**”。

6. 在 **"设备组"** 选项卡上，确定哪些设备组应接收此策略。  

   - 若要使所选设备组保持为选中状态，请选择"下一 **步"**。
   - 若要从策略中删除设备组，请选择"删除 **"**。
   - 若要设置新设备组，请选择" **创建新组**"，然后设置设备组。  (若要获取有关此任务的帮助，请参阅 [Microsoft 365 商业高级版](m365bp-device-groups-mdb.md).) 
   - 若要将策略应用于其他设备组，请选择" **使用现有组"**。

   指定应接收策略的设备组后，选择"下一步 **"**。

7. 在" **配置设置"** 选项卡上，查看设置。 如有必要，可以编辑策略的设置。 若要获取有关此任务的帮助，请参阅以下文章： 

   - [了解下一代配置设置](../security/defender-business/mdb-next-gen-configuration-settings.md)   
   - [防火墙设置](../security/defender-business/mdb-firewall.md)

   指定下一代保护设置后，选择"下一步 **"**。

8. 在 **"查看策略"** 选项卡上，查看常规信息、目标设备和配置设置。 

   - 通过选择"编辑"进行所需的 **任何更改**。
   - 准备好继续时，选择"更新 **策略"**。

## <a name="create-a-new-device-protection-policy"></a>创建新的设备保护策略

1. 转到 Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) ，然后登录。 

2. 在导航窗格中，选择" **设备配置"**。 策略按操作系统策略 (，Windows **客户端**) 策略类型 (如下一代保护和防火墙) 。  

3. 选择操作系统选项卡 (例如，Windows客户端) ，然后查看  下一代保护 **策略** 的列表。 

4. 在" **下一代保护** "或 **"防火墙"下，** 选择" **+ 添加"**。

5. 在" **常规信息"** 选项卡上，执行以下步骤：

   1. 指定名称和说明。 此信息将帮助你和团队稍后识别策略。
   2. 查看策略顺序，并在必要时编辑它。  (有关详细信息，请参阅 Policy [order](../security/defender-business/mdb-policy-order.md).) 
   3. 选择 **下一步**。 

7. 在 **"设备组"** 选项卡上，创建新设备组或使用现有组。 策略通过设备组分配给设备。 以下是需要记住的一些内容：

   - 最初，你可能只有默认设备组，其中包括组织中人员用于访问组织数据和电子邮件的设备。 你可以保留和使用默认设备组。
   - 创建新的设备组，以应用具有与默认策略不同的特定设置的策略。 
   - 设置设备组时，请指定某些条件，如操作系统版本。 符合条件的设备包含在该设备组中，除非你排除它们。 
   - 所有设备组（包括定义的默认和自定义设备组）都存储在Azure Active Directory (Azure AD) 。

   若要了解有关设备组的信息，请参阅 [Microsoft Defender for Business 中的设备组](../security/defender-business/mdb-create-edit-device-groups.md)。

8. 在" **配置设置"** 选项卡上，指定策略的设置，然后选择"下一步 **"**。 有关各个设置详细信息，请参阅 [了解 Microsoft Defender for Business](../security/defender-business/mdb-next-gen-configuration-settings.md) 中的下一代配置设置。

9. 在 **"查看策略"** 选项卡上，查看常规信息、目标设备和配置设置。 

   - 通过选择"编辑"进行所需的 **任何更改**。
   - 准备好继续操作后，选择" **创建策略"**。


## <a name="next-steps"></a>后续步骤

[设备组中Microsoft 365 商业高级版](m365bp-device-groups-mdb.md)