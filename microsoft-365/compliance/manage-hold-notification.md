---
title: 管理保留通知
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用高级电子数据展示中的通信工作流跟踪合法保留通知的状态，并在必要时更新并重新发送它们。
ms.openlocfilehash: 8852bfd1651e1855d276b60ba6fac35c378d4631
ms.sourcegitcommit: 6d672eb8287526a9db90df5fa85bc4984a7047d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/26/2020
ms.locfileid: "42280110"
---
# <a name="manage-hold-notifications"></a>管理保留通知

启动合法保留通知工作流后，可以使用高级电子数据展示中的通信工作流来跟踪通信的状态。 "通信" 选项卡包含高级电子数据展示事例中所有通知的列表。 您可以查看详细信息，如已分配的保管人数量或已确认通知。

## <a name="monitor-acknowledgments"></a>监视器确认

从 "**通信**" 选项卡中选择通信之后，可以查看已确认保留通知的保管人列表。 

1. 在合规性中心中，转到**电子数据展示 > 高级电子数据展示**。

2. 选择一个事例，然后单击 "**通信**" 选项卡。

3. 选择一种通信以显示 "**保管人通信**" 弹出页面。

与所选通信关联的保管人列表显示在 "通信" 飞出页面上。 此页面还显示见解以及收到的确认数和未完成的确认数。 此页面还显示了哪些保管人已发送确认，告知他们收到了保留通知。

## <a name="re-send-a-hold-notice"></a>重新发送保留通知

有时，保管人会在日常工作中失去对电子邮件的跟踪。 或者，对于长期运行的诉讼案例，保管人可以与您或其他人联系，并请求您重新发送通知。 在管理法律封存通知的通信工作流时，您可能需要重新发送通知，使其返回到 "用户邮箱的顶端"。

若要将保留通知重新发送给管理员，请执行以下操作：

1. 在 "高级电子数据展示" 中，选择一个事例，然后单击 "**通信**" 选项卡。

2. 选择一种通信以显示 "**保管人通信**" 弹出页面。

3. 单击 "**更多 > 重新发送保留通知**"。

4. 在 "**重新发送保留通知**" 弹出页面上，选择您要重新发送通知的保管人，并键入一个可选原因。

5. 单击 "**重新发送**" 以将通知发送给所选的保管人。

如果管理员尚未确认保留通知，则会重新启动提醒和升级工作流。 如果管理员已确认保留通知，则保管人将收到原始保留通知的副本。

> [!NOTE]
> 您只能将合法保留通知重新发送给分配给该通信的保管人。 

## <a name="update-preservation-requirements"></a>更新保留要求
  
在这种情况下，可能需要保管人来保留比以前所指示的更多或少的数据。 在电子数据展示术语中，需要使用更新后的内容重新发布保留通知。

若要更新初始保留通知的内容，请执行以下操作：

1. 在 "高级电子数据展示" 中，选择一个事例，然后单击 "**通信**" 选项卡。

2. 选择要更新的保留通知，然后单击 "**保管人通信**" 弹出页面上的 "**编辑**"。

3. 在 "**编辑通信**向导" 中，单击向导左窗格中的 "**定义门户内容**"，然后更新通知的内容。

4. 单击“**保存**”。

重新颁发通知将发送给分配到合法保留通知的所有保管人。 此外，如果启用了提醒或上报通知，则会重新启动这些通知类型的工作流。

## <a name="update-legal-hold-notifications-and-settings"></a>更新合法保留通知和设置

当您更新发布、发布、重新颁发、提醒或上报通知的内容或设置时，这些更改将应用于工作流生成的所有未来通信。

## <a name="more-information"></a>更多信息

- [向事例添加保管人](add-custodians-to-case.md)

- [创建合法保留通知](create-hold-notification.md)

- [确认保留通知](acknowledge-hold-notification.md)
