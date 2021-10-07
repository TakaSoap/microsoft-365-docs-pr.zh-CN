---
title: 在Advanced eDiscovery中Microsoft 365
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-aed
- m365initiative-compliance
- m365solution-scenario
search.appverid:
- MOE150
- MET150
description: 本文介绍如何设置Advanced eDiscovery以便你可以开始创建和管理事例。 它还介绍了所需的 Microsoft 订阅和许可。 完成几个快速步骤后，Advanced eDiscovery即可使用。
ms.openlocfilehash: eb37c11f8773189a8090178bf65c909b09fa941f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60153002"
---
# <a name="set-up-microsoft-365-advanced-ediscovery"></a>设置Microsoft 365 Advanced eDiscovery

Advanced eDiscovery Microsoft 365 提供了端到端工作流，以保留、收集、审阅、分析和导出对组织内部和外部调查做出响应的数据。 部署 Advanced eDiscovery 不需要执行任何操作，但 IT 管理员和电子数据展示管理员必须完成一些先决条件任务，组织才能开始创建和使用 Advanced eDiscovery 事例来管理调查。

本文讨论设置项目所需的Advanced eDiscovery。

![设置项目Advanced eDiscovery。](../media/set-up-advanced-ediscovery.png)

这包括确保访问事例所需的适当许可Advanced eDiscovery并将保管人添加到事例，以及向法律和调查团队分配权限，以便他们可以访问和管理事例。

## <a name="step-1-verify-and-assign-appropriate-licenses"></a>步骤 1：验证并分配适当的许可证

用户Advanced eDiscovery需要相应的组织订阅和每用户许可。 有关许可要求列表，Advanced eDiscovery订阅[和许可](overview-ediscovery-20.md#subscriptions-and-licensing)。

## <a name="step-2-assign-ediscovery-permissions"></a>步骤 2：分配电子数据展示权限

若要Advanced eDiscovery或添加为 Advanced eDiscovery 的成员，必须为用户分配适当的权限。 具体而言，必须将用户添加为电子数据展示管理员角色组Microsoft 365 合规中心。 此角色组的成员可以创建和管理Advanced eDiscovery案例。 他们可以添加和删除成员、将保管人和内容位置保留、管理合法保留通知、创建和编辑与案例关联的搜索、将搜索结果添加到审阅集、分析审阅集内的数据以及从 Advanced eDiscovery 案例导出和下载。

完成以下步骤以将用户添加到电子数据展示管理员角色组：

1. 转到 <https://compliance.microsoft.com/permissions> ，然后使用组织中管理员帐户的Microsoft 365登录。

2. 在" **权限"** 页上，选择 **电子数据展示管理员角色** 组。

3. 在"电子数据展示管理器"飞出页面上，单击 **"电子** 数据展示管理器"部分 **旁边的"编辑** "。

4. 在编辑角色组向导中的"选择 **电子数据** 展示管理器"页上，单击"**选择电子数据展示管理器"。**

5. 单击 **"** 添加"，然后选中要添加到角色组的所有用户的复选框。

6. 单击 **"** 添加"添加所选用户，然后单击"完成 **"。**

7. 单击 **"** 保存"将用户添加到角色组，然后单击 **"关闭"** 以完成此步骤。

### <a name="more-information-about-the-ediscovery-manager-role-group"></a>有关电子数据展示管理员角色组详细信息

电子数据展示管理员角色组中有两个子组。 这些子组之间的差异基于作用域。

- **电子数据展示管理器**：可以查看和管理Advanced eDiscovery或是这些事例的成员。 如果另一个电子数据展示管理员创建了一个案例，但没有将第二个电子数据展示管理员添加为该案例的成员，则第二个电子数据展示管理员将无法在合规中心的 Advanced eDiscovery 页面上查看或打开该案例。 通常，可以将您组织中的大多数人员添加到电子数据展示管理员子组。

- **电子数据展示管理员**：可以执行电子数据展示管理员可以执行的所有案例管理任务。 此外，电子数据展示管理员可以：

  - 查看"高级电子数据展示"页面上列出的所有事例。
  
  - 在将自己添加为案例的成员之后管理组织内的任何案例。

  - 访问和导出组织中任意案例的大小写数据。

  由于访问权限的范围很广，组织应仅应该只有部分管理员是电子数据展示管理员子组的成员。

有关电子数据展示权限以及分配给电子数据展示管理员角色组的每个角色的说明，请参阅分配 [电子数据展示权限](assign-ediscovery-permissions.md)。

## <a name="step-3-configure-global-settings-for-advanced-ediscovery"></a>步骤 3：配置全局设置Advanced eDiscovery

在组织中人员开始创建和使用案例之前，要完成的最后一步是配置适用于组织中所有案例的全局设置。 目前，唯一的全局设置是律师 *-* 客户特权检测 (将来将有更多的全局设置) 。 此设置允许律师-客户特权模型在您分析审阅集内的数据时运行。 模型使用机器学习来确定文档是否包含本质上是合法的内容。 它还会将文档参与者与你在设置模型) 时提交的律师列表 (列表进行比较，以确定文档是否至少有一个参与者是律师。

有关设置和使用律师-客户特权检测模型的信息，请参阅在 Advanced eDiscovery[中设置律师-客户特权检测](attorney-privilege-detection.md)。

> [!NOTE]
> 这是一个可选步骤，可以随时执行。 不实现律师-客户特权检测模型不会阻止你创建和使用Advanced eDiscovery案例。

## <a name="next-steps"></a>后续步骤

设置Advanced eDiscovery后，就可以[创建案例](create-and-manage-advanced-ediscoveryv2-case.md)了。