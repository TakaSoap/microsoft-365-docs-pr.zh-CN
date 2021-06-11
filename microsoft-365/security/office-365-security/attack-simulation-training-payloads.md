---
title: 创建攻击模拟培训的有效负载
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: m365-security
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-defender-office365
description: 管理员可以了解如何在 Microsoft Defender for Office 365 中为攻击模拟培训创建自定义负载。
ms.technology: mdo
ms.openlocfilehash: ac7963b71c466e8dfdc513a2563776cd4e10af95
ms.sourcegitcommit: 337e8d8a2fee112d799edd8a0e04b3a2f124f900
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/10/2021
ms.locfileid: "52878756"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>创建用于攻击模拟培训的自定义负载

**适用于 Microsoft** [Defender for Office 365计划 2](defender-for-office-365.md)

Microsoft 为各种社交工程技术提供了可靠的有效负载目录，以与攻击模拟培训配对。 但是，你可能希望创建更适用于你的组织的自定义有效负载。 本文介绍如何在 Microsoft Defender for Office 365 攻击模拟培训中创建负载。

可以通过在专用"有效负载"选项卡或模拟创建向导中单击"创建有效负载"[来创建有效负载](attack-simulation-training.md#selecting-a-payload)。 [  ](https://security.microsoft.com/attacksimulator?viewid=payload)

向导的第一步将让你选择有效负载类型。 **目前，只有电子邮件可用**。

接下来，选择一种关联的技术。 有关技术的详细信息，请参阅 [选择社交工程技术](attack-simulation-training.md#selecting-a-social-engineering-technique)。

在下一步中，将有效负载命名。 （可选）您可以为它提供说明。

## <a name="configure-payload"></a>配置有效负载

现在，可以生成有效负载了。 在"发件人详细信息"部分输入发件人的姓名、电子邮件地址和 **电子邮件主题** 。 从提供的列表中选择网络钓鱼 URL。 此 URL 稍后将嵌入到邮件正文中。

> [!TIP]
> 你可以为有效负载的发件人选择内部电子邮件，这会使有效负载显示为来自公司的另一名员工。 这将提高有效负载的易读性，并且有助于引导员工了解内部威胁的风险。

格式文本编辑器可用于创建有效负载。 还可以导入预先创建的电子邮件。 创建电子邮件正文时，请利用动态标记将电子邮件个性化到目标。 单击 **"网络钓鱼"** 链接，将以前选择的网络钓鱼 URL 添加到邮件正文中。

![在 Microsoft Defender for Office 365 的有效负载创建中突出显示的网络钓鱼链接和Office 365](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> 为了节省时间，请切换为将电子邮件中所有链接 **替换为网络钓鱼链接 的选项**。

完成有效负载生成后，单击"下一 **步"。**

## <a name="adding-indicators"></a>添加指示器

指示器可帮助员工完成攻击模拟，了解他们可以在将来的攻击中查找的线索。 若要开始，请单击"**添加指示器"。**

从下拉列表中选择一个希望使用的指示器。 此列表是为包含网络钓鱼电子邮件中最常见的线索而提供的。 选择后，请确保将指示器放置设置为 **"从电子邮件正文"，** 然后单击"选择 **文本"。** 突出显示显示此指示器的有效负载部分，然后单击"选择 **"。**

![要添加到攻击模拟培训中的指示器的邮件正文中的突出显示文本](../../media/attack-sim-preview-select-text.png)

添加用于描述指示器的自定义说明，然后单击指示器预览框架以查看指示器预览。 完成后，单击"添加 **"。** 重复这些步骤，直到负载中涵盖所有指示器。

## <a name="review-payload"></a>查看有效负载

你已完成有效负载的生成。 现在，该查看详细信息并查看有效负载预览了。 预览将包括你创建的所有指示器。 你可以从此步骤编辑负载的每个部分。 一旦满足，你可以 **提交** 负载。

> [!IMPORTANT]
> 你创建的负载将具有 **租户** 作为源。 选择有效负载时，请确保不要筛选出"租户 **"。**

## <a name="related-links"></a>相关链接

[开始使用攻击模拟培训](attack-simulation-training-get-started.md)

[创建网络钓鱼攻击模拟](attack-simulation-training.md)

[通过攻击模拟培训获得见解](attack-simulation-training-insights.md)
