---
title: 创建用于攻击模拟培训的有效负载
ms.author: daniha
author: danihalfin
manager: dansimp
audience: ITPro
ms.topic: how-to
ms.prod: microsoft-365-enterprise
localization_priority: Normal
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
description: 了解如何在 Microsoft Defender for Office 365 中创建自定义的攻击负载以实现攻击模拟培训。
ms.openlocfilehash: a8366e6cbf703ef1e1a14e216ada71200668cd14
ms.sourcegitcommit: ee39faf3507d0edc9497117b3b2854955c959c6c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/10/2020
ms.locfileid: "49616268"
---
# <a name="create-a-custom-payload-for-attack-simulation-training"></a>创建用于攻击模拟培训的自定义负载

Microsoft 为各种社会工程技术提供可靠的有效负载目录，以与您的攻击模拟培训进行配对。 但是，您可能希望创建可更好地为组织工作的自定义负载。 下面介绍如何通过 Microsoft Defender for Office 365 在攻击模拟培训中创建有效负载。

[!INCLUDE [Prerelease information](../includes/prerelease.md)]

您可以通过单击 "[专用 **负载**" 选项卡](https://security.microsoft.com/attacksimulator?viewid=payload)或在 [模拟创建向导](attack-simulation-training.md#selecting-a-payload)中的 "**创建有效负载**" 来创建有效负载。

向导中的第一步将选择有效负载类型。 **目前仅提供电子邮件**。

接下来，选择一种关联的技术。 有关 [选择社会工程技术](attack-simulation-training.md#selecting-a-social-engineering-technique)的技巧，请参阅更多详细信息。

在下一步中，为你的有效负载命名。 （可选）您可以为其提供说明。

## <a name="configure-payload"></a>配置有效负载

现在是时候生成有效负载了。 在 " **发件人详细信息** " 部分中输入发件人的姓名、电子邮件和电子邮件的主题。 从提供的列表中选择一个仿冒 URL。 此 URL 稍后将嵌入到邮件正文中。

> [!TIP]
> 您可以为有效负载的发件人选择内部电子邮件，这将使有效负载显示为来自公司的其他员工。 这将提高对有效负载的敏感程度，并帮助员工对内部威胁的风险进行培训。

可用于创建有效负载的 rtf 文本编辑器。 您还可以导入事先创建的电子邮件。 在构造电子邮件的正文时，利用 **动态标记** 将电子邮件个性化到目标中。 单击 " **仿冒链接** "，将之前选择的仿冒 URL 添加到电子邮件正文中。

![在 Microsoft Defender for Office 365 的有效负载创建中突出显示的仿冒链接和动态标记](../../media/attack-sim-preview-payload-email-body.png)

> [!TIP]
> 若要节省时间，请切换到 **替换电子邮件中包含仿冒链接的所有链接** 的选项。

根据需要构建完有效负载后，单击 " **下一步**"。

## <a name="adding-indicators"></a>添加指示器

指示器将帮助员工通过攻击模拟了解他们可以在未来的攻击中查找的线索。 若要开始，请单击 " **添加指示器**"。

从下拉列表中选择要使用的指示器。 此列表为 curated，包含出现在网络钓鱼电子邮件中的最常见线索。 选择后，请确保指示器位置已设置为 **来自电子邮件的正文** ，然后单击 " **选择文本**"。 突出显示此指示器显示的有效部分，然后单击 " **选择**"。

![要添加到攻击模拟培训中的指标的邮件正文中突出显示的文本](../../media/attack-sim-preview-select-text.png)

添加用于描述指示器的自定义说明，并在指示器预览框架内单击以查看指示器预览。 完成后，单击 " **添加**"。 重复这些步骤，直到您在有效负载中覆盖了所有指示器。

## <a name="review-payload"></a>查看有效负载

你已经完成了你的有效负载的构建。 现在是时候查看详细信息并查看有效负载的预览。 预览将包含您创建的所有指示器。 您可以从此步骤中编辑有效负载的每个部分。 满足后， **提交** 有效负载。

> [!IMPORTANT]
> 你创建的负载将把 **租户** 设置为其源。 在选择有效负载时，请确保未筛选出 **租户** 。