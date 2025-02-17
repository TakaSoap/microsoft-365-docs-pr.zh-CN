---
title: 在 Microsoft Defender for Business 中管理防火墙策略的自定义规则
description: 自定义规则提供防火墙策略的例外。 可以使用自定义规则阻止或允许 Microsoft Defender for Business 中的特定连接
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 02/24/2022
ms.prod: m365-security
ms.technology: mdb
ms.localizationpriority: medium
ms.reviewer: inbadian, shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 161ce8a20500bdea7d2ccd2dd9cc8a387345de1c
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525870"
---
# <a name="manage-your-custom-rules-for-firewall-policies-in-microsoft-defender-for-business"></a>在 Microsoft Defender for Business 中管理防火墙策略的自定义规则

> [!IMPORTANT]
> 从 2022 年 3 [月](../../business-premium/index.md) 1 Microsoft 365 商业高级版 Microsoft Defender for Business 将推出给客户。 作为独立订阅的 Defender for Business 在预览版中，将逐步向在此处注册以请求它的客户和 IT 合作伙伴[](https://aka.ms/mdb-preview)推出。 预览 [包括一组初始方案](mdb-tutorials.md#try-these-preview-scenarios)，我们将定期添加功能。
> 
> 本文中的某些信息与预发布产品/服务相关，这些产品/服务在商业发行之前可能会进行重大修改。 Microsoft 对此处提供的信息不做出明示或暗示的担保。 


Microsoft Defender for Business 包括防火墙策略，可帮助保护设备免受不需要的网络流量的影响。 可以使用自定义规则定义防火墙策略的例外。 也就是说，您可以使用自定义规则阻止或允许特定连接。

若要了解有关防火墙策略和设置的信息，请参阅 [Microsoft Defender for Business 中的防火墙](mdb-firewall.md)。

**本文介绍如何**：

- [为防火墙策略创建自定义规则](#create-a-custom-rule-for-a-firewall-policy)
- [编辑防火墙策略的自定义规则](#edit-a-custom-rule-for-a-firewall-policy)
- [删除自定义规则](#delete-a-custom-rule)

>
> **有空吗？**
> 请参加有关 <a href="https://microsoft.qualtrics.com/jfe/form/SV_0JPjTPHGEWTQr4y" target="_blank">Microsoft Defender for Business 的简短调查</a>。 我们非常乐意听取你的宝贵意见！
>

## <a name="create-a-custom-rule-for-a-firewall-policy"></a>为防火墙策略创建自定义规则

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 转到 **EndpointsDevice** >  配置，然后查看策略列表。

3. 在" **防火墙** "部分，选择现有策略，或添加新策略。

4. 在" **配置设置"** 步骤中，查看设置。 对域网络 **、** 公共 **网络和专用网络** 进行所需的 **任何更改**。

5. 若要创建自定义规则，请按照以下步骤操作： 

   1. 在 **"自定义规则"** 下，选择 **"+ 添加规则"**。  (您最多可以有 150 个自定义规则。) 
   2. 在 **"创建新规则"** 飞出上，指定规则的名称和说明。
   3. 选择配置文件。  (选项包括 **域网络**、 **公用网络** 或 **专用** 网络。) 
   4. 在" **远程地址类型"列表中** ，选择 **"IP** "或" **应用程序文件路径"**。
   5. 在 **"值** "框中，指定适当的值。 根据在步骤 6d 中选定的内容，您可以指定 IP 地址、IP 地址范围或应用程序文件路径。  (防火墙 [设置。](mdb-firewall.md)) 
   6. 在" **创建新规则"** 飞出上，选择" **创建规则"**。 

6. 在" **配置设置"** 屏幕上，选择"下一 **步"**。

7. 在 **"查看策略"** 屏幕上，查看对防火墙策略设置所做的更改。 进行任何所需的更改，然后选择"创建 **策略"**。

## <a name="edit-a-custom-rule-for-a-firewall-policy"></a>编辑防火墙策略的自定义规则

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 转到 **EndpointsDevice** >  配置，然后查看策略列表。

3. 在" **防火墙** "部分，选择现有策略，或添加新策略。

4. 在 **"自定义** 规则"下，查看规则列表。

5. 选择一个规则，然后选择"编辑 **"**。 将打开其飞出区。

6. 若要编辑自定义规则，请按照以下步骤操作：

   1. 在 **"编辑规则** "飞出控件上，查看和编辑规则的名称和说明。
   2. 查看并编辑规则的个人资料（如有必要）。  (选项包括 **域网络**、 **公用网络** 或 **专用** 网络。) 
   3. 在" **远程地址类型"列表中** ，选择 **"IP** "或" **应用程序文件路径"**。
   4. 在 **"值** "框中，指定适当的值。 根据在步骤 6c 中选定的内容，您可以指定 IP 地址、IP 地址范围或应用程序文件路径。  (防火墙 [设置。](mdb-firewall.md)) 
   5. 将 **"启用规则****"设置为"打开**"可使规则处于活动状态。 或者，若要禁用规则，将开关设置为"关闭 **"**。
   6. 在" **编辑规则"** 飞出控件上，选择 **"更新规则"**。 

7. 在" **配置设置"** 屏幕上，选择"下一 **步"**。

8. 在 **"查看策略"** 屏幕上，查看对防火墙策略设置所做的更改。 进行任何所需的更改，然后选择"创建 **策略"**。

## <a name="delete-a-custom-rule"></a>删除自定义规则

1. 转到"Microsoft 365 Defender门户 () [https://security.microsoft.com](https://security.microsoft.com) 并登录。

2. 转到 **EndpointsDevice** >  配置，然后查看策略列表。

3. 在" **防火墙** "部分，选择现有策略，或添加新策略。

4. 在 **"自定义** 规则"下，查看规则列表。

5. 选择一个规则，然后选择"删除 **"**。 将打开其飞出区。

6. 在确认屏幕上，选择"删除 **"**。 

## <a name="next-steps"></a>后续步骤

- [在 Microsoft Defender for Business 中查看和管理事件](mdb-view-manage-incidents.md)

- [响应和缓解 Microsoft Defender for Business 中的威胁](mdb-respond-mitigate-threats.md)

- [查看操作中心中的修正操作](mdb-review-remediation-actions.md)