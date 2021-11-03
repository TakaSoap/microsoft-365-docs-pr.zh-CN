---
title: 攻击模拟培训的有效负载自动化
ms.author: chrisda
author: chrisda
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何使用负载自动化 (负载收集) 在 Microsoft Defender for Office 365 计划 2 中收集和启动攻击模拟培训的自动模拟。
ms.technology: mdo
ms.openlocfilehash: 0e090b79c8e04de5f0e9e81449d805d2b124bc59
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60717447"
---
# <a name="payload-automations-for-attack-simulation-training"></a>攻击模拟培训的有效负载自动化

**适用于 Microsoft** [Defender for Office 365计划 2](defender-for-office-365.md)

在 Microsoft 365 E5 或 Microsoft Defender for Office 365 计划 2 的攻击模拟培训中，负载自动化 _(_ 也称为负载收集) 从组织中用户报告的实际网络钓鱼邮件收集信息。 尽管组织中这些邮件的数量可能较低，但您可以指定在网络钓鱼攻击中查找的条件 (例如，收件人、社交工程技术、发件人信息等) 。 攻击模拟培训随后将模拟攻击中使用的消息和负载，以向目标用户自动启动无害模拟。

若要创建负载自动化，请执行以下步骤：

1. 在 Microsoft 365 Defender门户中 <https://security.microsoft.com/> ，转到"电子邮件&**协作** \> **攻击模拟** \> **培训负载自动化"** 选项卡。

   若要直接转到" **负载自动化"** 选项卡，请使用 <https://security.microsoft.com/attacksimulator?viewid=payloadautomation> 。

2. 在" **负载自动化"** 选项卡上，选择 ![ "创建模拟图标"。](../../media/m365-cc-sc-create-icon.png) **创建模拟**。

   ![在攻击门户中攻击模拟培训中的负载自动化选项卡上创建Microsoft 365 Defender按钮。](../../media/attack-sim-training-sim-automations-create.png)

3. 将打开创建向导。 本文的其余部分介绍了页面及其包含的设置。

> [!NOTE]
> 在模拟创建向导期间的任何时间点，都可以单击 **"保存并** 关闭"以保存进度，并稍后继续配置模拟。 不完整的模拟 **在模拟选项卡** 上 **具有****状态值** 草稿。通过选择模拟并单击"编辑模拟图标"，你可以从你离开 ![ 的地方继续。](../../media/m365-cc-sc-edit-icon.png) **编辑** simulation.## 名称和描述模拟。

## <a name="automation-name"></a>自动化名称

在 **"自动化名称"** 页上，配置以下设置：

- **名称**：输入模拟的唯一描述性名称。
- **说明**：输入模拟的可选详细说明。

完成后，单击“**下一步**”。

## <a name="run-conditions"></a>运行条件

在 **"运行条件** "页上，选择实际钓鱼攻击的条件，以确定是否将运行自动化。

每个条件只能使用一次。 多个条件使用 AND 逻辑 (\<Condition1\> 和 \<Condition2\>) 。

![添加条件图标。](../../media/m365-cc-sc-create-icon.png) **添加条件**。

- **否。活动的目标用户数**：配置以下设置：
  - **等于**、 **小于**、 **大于**、 **小于或等于**、或 **大于或等于**。
  - **输入值**：网络钓鱼活动的目标用户数。
- **使用特定网络钓鱼技术的活动**：选择可用值之一：
  - **凭据获取**
  - **恶意软件附件**
  - **附件中的链接**
  - **链接到恶意软件**
  - **按 URL 的驱动器**
- **特定发件人域**：输入发件人电子邮件域 (例如，contoso.com) 。
- **特定发件人名称**：输入发件人名称值。
- **特定发件人电子邮件**：输入发件人电子邮件地址。
- **特定用户和组收件人**：开始键入用户或组的名称或电子邮件地址。 出现时，选择它。

若要在添加条件后删除条件，请单击 ![删除图标。](../../media/m365-cc-sc-delete-icon.png).

完成后，单击“**下一步**”。

## <a name="review-automation"></a>查看自动化

在 **"查看自动化** "页上，你可以查看有效负载自动化的详细信息。

可以在每个部分中选择“**编辑**”来修改该部分中的设置。 或者，可以单击“**返回**”或选择向导中的特定页面。

完成后，请单击“**提交**”。
