---
title: 在Microsoft Defender 商业版中查看或编辑策略
description: 了解如何在Microsoft Defender 商业版中查看、编辑、创建和删除下一代保护策略
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/15/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
- m365-initiative-defender-business
ms.openlocfilehash: 6f8ad1bd1f77bd3e53a1686674984155a7dc8525
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64665087"
---
# <a name="view-or-edit-policies-in-microsoft-defender-for-business"></a>在Microsoft Defender 商业版中查看或编辑策略

> [!IMPORTANT]
> Microsoft Defender 商业版从 2022 年 3 月 1 日开始向[Microsoft 365 商业高级版](../../business-premium/index.md)客户推出。 Defender for Business 作为独立订阅处于预览状态，将逐步推出给 [在此处注册](https://aka.ms/mdb-preview) 以请求该订阅的客户和 IT 合作伙伴。 预览版包括 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的一些信息涉及到预租产品/服务，这些产品/服务在商业发布之前可能会进行重大修改。 Microsoft 不会对此处提供的信息作出明示或暗示的保证。 

在Microsoft Defender 商业版中，安全设置是通过应用于设备的策略配置的。 为了帮助简化设置和配置体验，Defender for Business 包含预配置的策略，以帮助在加入公司设备后立即保护这些设备。 可以使用默认策略、编辑策略或创建自己的策略。

**本文介绍如何**：

- [获取默认策略的概述](#default-policies-in-defender-for-business)

- [查看现有策略](#view-your-existing-policies)

- [编辑现有策略](#edit-an-existing-policy)

- [创建新策略](#create-a-new-policy)

>
> **有空吗？**
> 请对<a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender 商业版进行简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="default-policies-in-defender-for-business"></a>Defender for Business 中的默认策略

在 Defender for Business 中，有两种保护公司设备的主要策略类型：

- **下一代保护策略**，用于确定如何配置Microsoft Defender 防病毒和其他威胁防护功能

- **防火墙策略**，该策略确定允许哪些网络流量流向和流出公司的设备


## <a name="view-your-existing-policies"></a>查看现有策略

1. 转到Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) ，然后登录。 

2. 在导航窗格中，选择 **"设备配置**"。 策略由操作系统 (组织，例如 **Windows客户** 端) 和策略类型 (，如 **下一代保护** 和 **防火墙**) 。 

3. 选择操作系统选项卡 (例如 **，Windows客户** 端) ，然后查看 **下一代保护** 和 **防火墙** 类别下的策略列表。 

4. 若要查看有关策略的更多详细信息，请选择其名称。 将打开一个侧窗格，该窗格提供有关该策略的详细信息，例如，哪些设备受该策略保护。

## <a name="edit-an-existing-policy"></a>编辑现有策略

1. 转到Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) ，然后登录。 

2. 在导航窗格中，选择 **"设备配置**"。 策略由操作系统 (组织，例如 **Windows客户** 端) 和策略类型 (，如 **下一代保护** 和 **防火墙**) 。 

3. 选择操作系统选项卡 (例如 **，Windows客户** 端) ，然后查看 **下一代保护** 和 **防火墙** 类别下的策略列表。 

4. 若要编辑策略，请选择其名称，然后选择 **"编辑**"。

5. 在" **常规信息** "选项卡上，查看信息。 如有必要，可以编辑说明。 然后选择“**下一步**”。

6. 在 **"设备组** "选项卡上，确定应接收此策略的设备组。  

   - 若要保持所选设备组的状态，请选择 **"下一步**"。
   - 若要从策略中删除设备组，请选择 **"删除**"。
   - 若要设置新的设备组，请选择 **"新建组**"，然后设置设备组。  (若要获取有关此任务的帮助，请参阅 Microsoft Defender 商业版.) [中的设备组](mdb-create-edit-device-groups.md)
   - 若要将策略应用到另一个设备组，请选择 **"使用现有组**"。

   指定哪些设备组应接收策略后，选择 **"下一步**"。

7. 在" **配置设置"** 选项卡上，查看设置。 如有必要，可以编辑策略的设置。 若要获取有关此任务的帮助，请参阅以下文章： 

   - [了解下一代配置设置](mdb-next-gen-configuration-settings.md)   
   - [防火墙设置](mdb-firewall.md)

   指定下一代保护设置后，选择 **"下一步**"。

8. 在 **"查看策略** "选项卡上，查看常规信息、目标设备和配置设置。 

   - 通过选择 **"编辑**"进行任何所需的更改。
   - 准备好继续操作后，选择 **"更新"策略**。

## <a name="create-a-new-policy"></a>创建新策略

1. 转到Microsoft 365 Defender门户 ([https://security.microsoft.com](https://security.microsoft.com)) ，然后登录。 

2. 在导航窗格中，选择 **"设备配置**"。 策略由操作系统 (组织，例如 **Windows客户** 端) 和策略类型 (，如 **下一代保护** 和 **防火墙**) 。 

3. 选择操作系统选项卡 (例如 **，Windows客户** 端) ，然后查看 **下一代保护** 策略的列表。 

4. 在 **"下一代保护** "或" **防火墙**"下，选择 **"+ 添加**"。

5. 在" **常规信息** "选项卡上，执行以下步骤：

   1. 指定名称和说明。 此信息将帮助你和你的团队稍后确定策略。
   2. 查看策略顺序，并在必要时对其进行编辑。  (有关详细信息，请参阅 Policy [order](mdb-policy-order.md).) 
   3. 选择“**下一步**”。 

7. 在 **"设备组"** 选项卡上，创建新的设备组，或使用现有组。 策略通过设备组分配给设备。 下面是需要记住的一些事项：

   - 最初，你可能只有默认设备组，其中包括公司中人员用于访问公司数据和电子邮件的设备。 可以保留和使用默认设备组。
   - 创建新的设备组，以应用具有与默认策略不同的特定设置的策略。 
   - 设置设备组时，请指定某些条件，例如操作系统版本。 符合条件的设备包括在该设备组中，除非排除它们。 
   - 所有设备组（包括你定义的默认设备组和自定义设备组）都存储在Azure Active Directory (Azure AD) 中。

   若要了解有关设备组的详细信息，请 [参阅 Defender for Business 中的设备组](mdb-create-edit-device-groups.md)。

8. 在 **"配置设置"** 选项卡上，指定策略的设置，然后选择 **"下一步**"。 有关各个设置的详细信息，请参阅[Microsoft Defender 商业版的配置设置](mdb-next-gen-configuration-settings.md)。

9. 在 **"查看策略** "选项卡上，查看常规信息、目标设备和配置设置。 

   - 通过选择 **"编辑**"进行任何所需的更改。
   - 准备好继续操作后，选择 **"创建策略**"。


## <a name="next-steps"></a>后续步骤

选择以下一个或多个任务：

- [管理设备](mdb-manage-devices.md)

- [在Microsoft Defender 商业版中创建新策略](mdb-create-new-policy.md)

- [在Microsoft Defender 商业版中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解Microsoft Defender 商业版中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)