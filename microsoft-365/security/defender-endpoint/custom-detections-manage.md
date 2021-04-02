---
title: 在 Microsoft Defender ATP 中查看和管理自定义检测规则
ms.reviewer: ''
description: 了解如何查看和管理自定义检测规则
keywords: 自定义检测， 查看， 管理， 警报， 编辑， 按需运行， 检测规则， 高级搜寻， 智能寻线， 查询， 响应操作， mdatp， microsoft defender atp
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: maccruz
author: schmurky
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.openlocfilehash: b36521ada55fa3d60538beb981d487b153e7b1f9
ms.sourcegitcommit: 582555d2b4ef5f2e2494ffdeab2c1d49e5d6b724
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2021
ms.locfileid: "51498757"
---
# <a name="view-and-manage-custom-detection-rules"></a>查看和管理自定义检测规则

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

>想要体验适用于终结点的 Defender？ [注册免费试用版。](https://www.microsoft.com/microsoft-365/windows/microsoft-defender-atp?ocid=docs-wdatp-assignaccess-abovefoldlink)

管理现有的 [自定义检测规则](custom-detection-rules.md) ，以确保它们有效地找到威胁并采取措施。 了解如何查看规则列表、检查其以前的运行，并查看它们触发的警报。 您还可以按需运行规则并对其进行修改。

## <a name="required-permissions"></a>所需权限

若要创建或管理自定义检测， [你的](user-roles.md#create-roles-and-assign-the-role-to-an-azure-active-directory-group) 角色需要具有 **管理安全设置** 权限。

## <a name="view-existing-rules"></a>查看现有规则

若要查看所有现有的自定义检测规则，**请导航到**"设置""  >  **自定义检测"。** 该页列出了包含以下运行信息的所有规则：

- **上次运行**- 上次运行规则以检查查询匹配并生成警报时
- **上次运行状态**— 规则是否成功运行
- **下一** 次运行 - 下一个计划运行
- **状态**— 规则是已打开还是关闭

## <a name="view-rule-details-modify-rule-and-run-rule"></a>查看规则详细信息、修改规则并运行规则

若要查看有关自定义检测规则的综合信息，请从设置自定义检测中的规则  >  **列表中选择规则的名称**。 有关所选规则的页面将显示以下信息：

- 有关规则的常规信息，包括警报的详细信息、运行状态和范围
- 触发的警报列表
- 触发的操作列表

![自定义检测规则页](images/atp-custom-detection-rule-details.png)<br>
*自定义检测规则页*

您还可以从此页对规则执行以下操作：

- **运行** 立即运行规则。 此操作还会重置下次运行的时间间隔。
- **编辑** 在不更改查询的情况下修改规则
- **修改查询**— 在高级搜寻中编辑查询
- **打开**  / **关闭**- 启用规则或阻止其运行
- **删除**- 关闭并删除规则

>[!TIP]
>若要快速查看信息并针对表中的项目采取操作，请使用表格左侧的选择列 [&#10003;] 。

## <a name="related-topics"></a>相关主题
- [自定义检测概述](overview-custom-detections.md)
- [创建检测规则](custom-detection-rules.md)
- [高级搜寻概述](advanced-hunting-overview.md)
- [查看和组织警报](alerts-queue.md)
