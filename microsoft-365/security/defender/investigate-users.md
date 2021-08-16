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
ms.openlocfilehash: cc09593c7a8ceef04d0a61cc9bd7d5624943b28f
ms.sourcegitcommit: a0185d6b0dd091db6e1e1bfae2f68ab0e3cf05e5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/13/2021
ms.locfileid: "58247126"
---
# <a name="investigate-users-in-microsoft-365-defender"></a>调查用户Microsoft 365 Defender

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**适用于：**

- Microsoft 365 Defender

事件调查的一部分可能包括用户帐户。 从"事件 **"** 和"用户"事件 **&"事件***>">***开始**。 

:::image type="content" source="../../media/investigate-incidents/incident-users.png" alt-text="事件的用户页面示例":::

若要获取事件的用户帐户的快速摘要，请选择用户帐户名称旁边的选中标记。 下面是一个示例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-pane.png" alt-text="事件门户中事件的用户帐户摘要窗格Microsoft 365 Defender示例":::

> [!NOTE]
> "用户"Azure Active Directory (Azure AD) 以及组，帮助你了解与用户关联的组和权限。

在此飞出页面中，你可以查看用户威胁信息，包括任何当前事件、活动警报和风险级别以及用户曝光、帐户、设备等。

此外，你可以直接在 Microsoft 365 Defender 门户中采取措施来解决受到威胁的用户，确认用户受到威胁或要求他们重新登录。

从此处，可以选择" **转到用户页面** "以查看用户帐户的详细信息。 下面是一个示例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details.png" alt-text="事件门户中事件的用户帐户Microsoft 365 Defender示例":::

您还可以通过从"用户"页上的列表中选择用户帐户的名称来 **查看此页面。**

Microsoft 365 Defender门户用户页面合并来自 Microsoft Defender for Endpoint、Microsoft Defender for Identity 和 Microsoft Cloud App Security (的信息，具体取决于你拥有哪些) 。 

此页面显示特定于用户帐户安全风险的信息。 这包括一个分数，可帮助评估风险以及导致用户的整体风险的最新事件和警报。

在此页中，你可以执行以下附加操作： 

- 将用户帐户标记为已泄露
- 要求用户重新登录
- 暂停用户帐户
- 请参阅Azure Active Directory (Azure AD) 用户帐户设置
- 查看用户帐户拥有的文件
- 查看与该用户共享的文件。 

下面是一个示例。

:::image type="content" source="../../media/investigate-users/incidents-ss-user-details-actions.png" alt-text="事件门户中事件用户帐户Microsoft 365 Defender示例":::


<!--
You can access this page from multiple areas in the Microsoft 365 Defender portal. You can access this page from a specific incident in the **Users** tab. Some alerts might include users as a specific affected asset. You can also search for users.  

Learn more about how to investigate users and potential risk [in this Cloud App Security tutorial](/cloud-app-security/tutorial-ueba#:~:text=To%20identify%20who%20your%20riskiest,user%20page%20to%20investigate%20them).

--> 

## <a name="next-steps"></a>后续步骤

如果需要处理内事件，请继续执行 [调查](investigate-incidents.md)。

## <a name="see-also"></a>另请参阅

- [事件概述](incidents-overview.md)
- [确定事件优先级](incident-queue.md)
- [管理事件](manage-incidents.md)