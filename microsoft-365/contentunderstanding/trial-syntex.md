---
title: 运行 Microsoft SharePoint Syntex
ms.author: chucked
author: chuckedmonson
manager: pamgreen
ms.reviewer: lauris; jaeccles
ms.date: ''
audience: admin
ms.topic: article
ms.prod: microsoft-365-enterprise
ms.collection:
- enabler-strategic
- m365initiative-syntex
ms.custom:
- Adopt
- admindeeplinkMAC
search.appverid: ''
ms.localizationpriority: medium
description: 了解如何在组织中计划和运行SharePoint Syntex试用计划。
ms.openlocfilehash: 74b44c14140f26e0744aac73fd948e58d9d33e24
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60156374"
---
# <a name="run-a-trial-of-microsoft-sharepoint-syntex"></a>运行 Microsoft SharePoint Syntex

本文介绍如何设置和运行试用计划，以在SharePoint Syntex部署服务。 它还建议试用的最佳实践。

## <a name="sign-up-for-a-trial"></a>注册试用版

试用版SharePoint Syntex 300 个用户 30 天的访问权限。

> [!NOTE]
> 试用版中最多包含 300 个用户，以确保自动添加 100 万 AI Builder 信用额度。 You do not have to include 300 users for a trial to succeed.

可以从以下来源之一获取试用版：

- 产品[SharePoint Syntex页面](https://www.microsoft.com/microsoft-365/enterprise/sharepoint-syntex?activetab=pivot:overviewtab)

- Microsoft 365 管理中心[](https://admin.microsoft.com)
    1. 登录到 [Microsoft 365 管理中心](https://admin.microsoft.com)。
    2. 转到计费  >  <a href="https://go.microsoft.com/fwlink/p/?linkid=868433" target="_blank">**购买服务**</a>。
    3. 向下滚动到“**加载项**”部分。
    4. 在"SharePoint Syntex"磁贴上，选择"详细信息 **"。**
    5. 选择“**获取免费试用版**”。
    6. 若要确认试用版，请按照其余向导步骤操作。

你必须是全局Microsoft 365或帐单管理员才能激活试用版。

### <a name="who-should-be-involved-in-a-trial"></a>Who应涉及试用版

|角色|活动|
|---|---|
|Microsoft 365全局管理员或帐单管理员|激活试用版并分配许可证|
|Microsoft 365全局管理员或SharePoint管理员|配置SharePoint Syntex和创建内容中心|
|业务用户|模型生成和测试|

### <a name="before-you-activate-a-trial"></a>激活试用版之前

若要成功规划SharePoint Syntex，请考虑以下因素：

- 最有意义的测试在"实际"方案和数据上完成。
- 每个租户只能SharePoint Syntex一次试用版。

测试或演示租户可以用作"试运行"，以演练激活步骤和管理控制。 但是，最好评估在生产租户上构建的模型。

若要在生产租户上最大化试用版的价值，规划和业务参与至关重要。 您应参与一个或多个业务领域，以确定三到六个用例，这些用例可能会由 SharePoint Syntex。 这些用例应：

- 包括可以通过表单处理或文档理解模型解决的方案。
- 明确了解任何提取的元数据的用途;例如，通过使用视图格式化或Power Automate。 尽管SharePoint Syntex文档分类和提取元数据，但要量化的值是此元数据所支持的值。
- 基于定义的一组数据;例如，特定SharePoint或库。 一个SharePoint Syntex一点就是通用模型可以应用于所有组织内容。 更准确的视图是构建模型以帮助解决目标位置的特定业务问题。

所有这些用例可能不适合SharePoint Syntex。 质量试验的目标是不证明SharePoint Syntex满足所有方案。 相反，该试用版应帮助你更好地了解产品的价值。

对于每个计划用例，确定作为相关内容或流程的主题专家的用户。 创建SharePoint Syntex模型侧重于内容中的域专家，而不是 IT 专业人员或开发人员资源。

## <a name="activate-a-trial"></a>激活试用版

启动试用版时，需要：

- 将许可证分配给相关用户。
- 执行[其他设置SharePoint Syntex。](set-up-content-understanding.md)
  - 您可能需要创建 [其他内容中心](create-a-content-center.md)。

激活试用版后，可以创建模型并处理文件。 请参阅 [模型创建指南](create-a-content-center.md)。

## <a name="during-a-trial"></a>试用期间

试用期有限，因此最好首先关注SharePoint Syntex模型是否可以对文档进行分类，并提取定义的用例的元数据。 试用期结束后，可以评估元数据的利用方式。

## <a name="after-a-trial"></a>试用后

根据试验结果，可以决定是否继续生产SharePoint Syntex。

### <a name="proceed-to-production-use"></a>继续生产使用

为了确保服务的连续性，需要购买所需数量的许可证，并将这些许可证分配给用户。 在试用期结束时没有完整许可证的试用用户将无法充分利用SharePoint Syntex。

你可能必须估计表单处理的预期使用，并规划预期 AI 生成器信用额度。 有关帮助，请参阅 [估计适合你的 AI 生成器容量](https://powerapps.microsoft.com/ai-builder-calculator/)。

### <a name="dont-proceed-to-production-use"></a>不要继续生产使用

如果你在试用后不购买许可证：

- 无法创建新模型。
- 运行模型的库将不再自动对文件或提取模型进行分类。
- 任何以前已分类的文件或提取的元数据都不受影响。
- 内容中心和任何文档理解模型不会自动删除。 如果你决定将来购买许可证，这些许可证将仍然可供使用。
- 表单处理模型将存储在 Dataverse (之前名为 Common Data Service [CDS]) 默认 Power Platform 环境的实例中。 这些可以与将来许可一SharePoint Syntex Power Platform 中的 AI 生成器功能一起使用。

## <a name="see-also"></a>另请参阅

[Microsoft SharePoint Syntex采用：入门](adoption-getstarted.md)
