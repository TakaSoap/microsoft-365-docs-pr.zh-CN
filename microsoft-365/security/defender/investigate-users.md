---
title: 调查用户Microsoft 365 Defender
description: 调查用户的事件在 Microsoft 365 Defender 门户。
keywords: 安全， 恶意软件， Microsoft 365， M365， 安全中心， 监视， 报告， 标识， 数据， 设备， 应用， 事件， 分析， 响应
ms.prod: m365-security
ms.mktglfcycl: deploy
localization_priority: Normal
f1.keywords:
- NOCSH
ms.author: josephd
author: JoeDavies-MSFT
manager: dansimp
ms.date: ''
audience: ITPro
ms.collection:
- M365-security-compliance
- m365initiative-m365-defender
ms.topic: article
search.appverid: met150
ms.custom: seo-marvel-jun2020
ms.technology: m365d
ms.openlocfilehash: d7decb3e566f8bb0abf4a3aec12e2e3a43ae3511
ms.sourcegitcommit: 6a73f0f0c0360fc015d9c0d0af26fb6926d9477d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/30/2021
ms.locfileid: "58746431"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>调查用户Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

事件调查的一部分可能包括用户帐户。 从事件 **和** 警报事件 _ _ 用户 **&事件的用户** 选项卡 \> ***\>* 开始**。

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的用户页面示例。":::

若要获取事件的用户帐户的快速摘要，请选择用户帐户名称旁边的选中标记。 下面是一个示例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="事件门户中事件的用户帐户摘要窗格Microsoft 365 Defender示例":::

> [!NOTE]
> "用户"Azure Active Directory (Azure AD) 以及组，帮助你了解与用户关联的组和权限。

在此飞出页面中，你可以查看用户威胁信息，包括任何当前事件、活动警报和风险级别以及用户曝光、帐户、设备等。

此外，你可以直接在 Microsoft 365 Defender 门户中采取措施来解决受损用户的问题，确认用户受到威胁或要求他们重新登录。

从此处，可以选择" **转到用户页面** "以查看用户帐户的详细信息。 下面是一个示例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="事件门户中事件的用户帐户Microsoft 365 Defender示例":::

您还可以通过从"用户"页上的列表中选择用户帐户的名称来 **查看此页面。**

通过选择"组"下的号码，可以看到用户的组 **成员身份**。

:::image type="content" source="../../media/investigate-users/user-group-membership.png" alt-text="用户门户中用户的组成员身份Microsoft 365 Defender示例":::

通过选择"经理 **"** 下的图标，可以看到用户位于组织树中。

"Microsoft 365 Defender门户用户页面将 Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 Microsoft Cloud App Security (信息组合在一起，具体取决于你拥有哪些) 。

此页面显示特定于用户帐户安全风险的信息。 这包括一个分数，可帮助评估风险以及导致用户的整体风险的最新事件和警报。

在此页中，你可以执行以下附加操作：

- 将用户帐户标记为已泄露
- 要求用户重新登录
- 暂停用户帐户
- 请参阅Azure Active Directory (Azure AD) 用户帐户设置
- 查看用户帐户拥有的文件
- 查看与该用户共享的文件。

下面是一个示例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="针对用户门户中事件的用户帐户Microsoft 365 Defender示例":::

<!--
You can access this page from multiple areas in the Microsoft 365 Defender portal. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

-->

## <a name="view-lateral-movement-paths"></a>查看横向移动路径

通过选择"横向移动路径"选项卡，你可以查看完全动态且可单击的地图，该地图可直观呈现此用户之间可用于访问和访问网络的横向移动路径。

该地图提供了攻击者在计算机或用户之间为入侵敏感帐户而必须在这两个用户之间拥有多少跃点的列表，如果用户具有敏感帐户，则可以看到直接连接的资源和帐户数。

如果在过去两天内未检测到实体的潜在横向移动路径，则图形不显示。 使用"查看其他日期"选择其他日期，以查看为此实体发现的以前的横向移动路径图。 横向移动路径报告始终可用于提供有关发现的可能的横向移动路径的信息，并可以按时间进行自定义。

:::image type="content" source="../../media/investigate-users/lateral-movement-path.png" alt-text="用户门户中用户的横向移动Microsoft 365 Defender示例":::

有关详细信息，请参阅横向 [移动路径](/defender-for-identity/use-case-lateral-movement-path)。

## <a name="next-steps"></a>后续步骤

如果需要处理内事件，请继续执行 [调查](investigate-incidents.md)。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [确定事件优先级](incident-queue.md)
- [管理事件](manage-incidents.md)
