---
title: '在 Microsoft Defender for Business 预览版中查看 (编辑) '
description: '了解如何在 Microsoft Defender for Business 预览版中查看、编辑、创建和删除下一代 (策略) '
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
ms.openlocfilehash: aed09fd10f3381b4d167ea31e303fc2cbce7e8f3
ms.sourcegitcommit: 74f79aacb4ffcc6cb0e315239b1493324eabb449
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/14/2021
ms.locfileid: "61508331"
---
# <a name="view-or-edit-policies-in-microsoft-defender-for-business-preview"></a>在 Microsoft Defender for Business 预览版中查看 (编辑) 

> [!IMPORTANT]
> Microsoft Defender for Business 现在为预览版，将逐步向在此处注册以请求[](https://aka.ms/mdb-preview)它的客户和 IT 合作伙伴推出。 我们将于未来几周内载入一组初始客户和合作伙伴，并扩大预览版本，从而一般可用。 请注意，预览将启动 [一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 

在 Microsoft Defender for Business (预览) 中，安全设置通过策略进行配置。 在 Defender for Business 预览版中，有两种主要 (策略) ：

- **下一代保护** 策略 ，用于确定Microsoft Defender 防病毒和其他威胁防护功能的配置方式
- **防火墙** 策略 ，用于确定允许哪些网络流量流入和流出公司设备

**本文介绍如何：**

- [查看现有策略](#view-your-existing-policies)
- [编辑现有策略](#edit-an-existing-policy)

> [!TIP]
> 如果要添加新策略，请参阅创建新 [策略](mdb-create-new-policy.md)。

## <a name="view-your-existing-policies"></a>查看现有策略

1. 转到 Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () ，然后登录。 

2. 在导航窗格中，选择"**设备配置"。** 策略按操作系统策略 (，Windows **客户端**) 策略类型 (如下一代保护和 **防火墙) 。**  

3. 选择操作系统选项卡 (例如，Windows客户端) ，然后查看下一代保护和防火墙类别下 **的策略** 列表。  

4. 若要查看有关策略的更多详细信息，请选择其名称。 将打开一个侧窗格，该窗格提供有关该策略的详细信息，例如受该策略保护的设备。

## <a name="edit-an-existing-policy"></a>编辑现有策略

1. 转到 Microsoft 365 Defender门户 [https://security.microsoft.com](https://security.microsoft.com) () ，然后登录。 

2. 在导航窗格中，选择"**设备配置"。** 策略按操作系统策略 (，Windows **客户端**) 策略类型 (如下一代保护和 **防火墙) 。**  

3. 选择操作系统选项卡 (例如，Windows客户端) ，然后查看下一代保护和防火墙类别下 **的策略** 列表。  

4. 若要编辑策略，请选择其名称，然后选择"编辑 **"。**

5. 在" **常规信息"** 选项卡上，查看信息。 如有必要，可以编辑说明。 然后选择“**下一步**”。

6. 在 **"设备组"** 选项卡上，确定哪些设备组应接收此策略。  

   - 若要使所选设备组保持为选中状态，请选择"下一 **步"。**
   - 若要从策略中删除设备组，请选择"删除 **"。**
   - 若要设置新设备组，请选择" **创建新组**"，然后设置设备组。  (若要获取有关此任务的帮助，请参阅 Microsoft Defender for Business 中的设备组 ([预览版) ](mdb-create-edit-device-groups.md).) 
   - 若要将策略应用于其他设备组，请选择"**使用现有组"。**

   指定应接收策略的设备组后，选择"下一步 **"。**

7. 在" **配置设置"** 选项卡上，查看设置。 如有必要，可以编辑策略的设置。 若要获取有关此任务的帮助，请参阅以下文章： 

   - [了解下一代配置设置](mdb-next-gen-configuration-settings.md)   
   - [防火墙设置](mdb-firewall.md)

   指定下一代保护设置后，选择"下一步 **"。**

8. 在 **"查看策略"** 选项卡上，查看常规信息、目标设备和配置设置。 

   - 通过选择"编辑"进行任何所需的 **更改**。
   - 准备好继续时，选择"更新 **策略"。**


## <a name="next-steps"></a>后续步骤

选择以下一个或多个任务：

- [管理设备](mdb-manage-devices.md)

- [在 Microsoft Defender for Business 预览版中 (策略) ](mdb-create-new-policy.md)

- [在 Microsoft Defender for Business 预览版中查看 (事件) ](mdb-view-manage-incidents.md)

- [在 Microsoft Defender for Business 预览版中响应 (缓解) ](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)