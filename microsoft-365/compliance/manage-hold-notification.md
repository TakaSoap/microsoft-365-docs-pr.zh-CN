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
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 使用 Advanced eDiscovery中的通信工作流跟踪法定保留通知的状态，并在必要时进行更新并重新发送。
ms.openlocfilehash: 276771b2a22f6db3e3d0620ee429a16626107bcc
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60200433"
---
# <a name="manage-hold-notifications"></a>管理保留通知

启动法定保留通知工作流后，可以使用 Advanced eDiscovery 中的通信工作流跟踪通信状态。 The Communications tab contains a list of all notifications within your Advanced eDiscovery case. 你可以看到详细信息，如已分配或已确认通知的保管人数量。

## <a name="monitor-acknowledgments"></a>监视确认

从"通信"选项卡 **中选择** 通信后，可以查看已确认保留通知的保管人列表。 

1. 在合规中心，转到"**电子数据展示> Advanced eDiscovery"。**

2. 选择一个案例，然后单击"通信 **"** 选项卡。

3. 选择用于显示 **保管人** 通信飞出页的通信。

与所选通信相关联的保管人列表显示在通信飞出页上。 此页面还显示见解，以及收到的确认数和未完成的确认数。 该页面还显示哪些保管人已发送他们收到保留通知的确认。

## <a name="re-send-a-hold-notice"></a>重新发送保留通知

有时，保管人会跟踪其日常工作中的电子邮件。 或者，对于长期运行的诉讼案例，保管人可以联系你或其他人并请求你重新发送通知。 管理合法保留通知的通信工作流时，可能需要重新发送通知以将其返回到"用户邮箱顶部"。

若要将保留通知重新发送给保管人：

1. 在Advanced eDiscovery中，选择一个案例，然后单击"通信 **"** 选项卡。

2. 选择用于显示 **保管人** 通信飞出页的通信。

3. 单击 **">重新发送保留通知"。**

4. 在 **"重新发送保留通知** "飞出页面上，选择要重新发送通知的保管人并键入可选原因。

5. 单击 **"重新发送** "将通知发送给选定的保管人。

如果保管人尚未确认保留通知，则重新启动提醒和上报工作流。 如果保管人已确认保留通知，则保管人将收到原始保留通知的副本。

> [!NOTE]
> 只能向分配给通信的保管人重新发送法定保留通知。 

## <a name="update-preservation-requirements"></a>更新保留要求
  
随着案例的进展，可能需要保管人保留比之前指示更多的或更少的数据。 就电子数据展示而言，您需要使用更新的内容重新发出保留通知。

更新初始保留通知的内容：

1. 在Advanced eDiscovery中，选择一个案例，然后单击"通信 **"** 选项卡。

2. 选择要更新的保留通知，然后单击保管 **人** 通信飞出页面上 **的** "编辑"。

3. 在"**编辑通信**"向导中，单击向导左窗格中的"定义门户内容"，然后更新通知的内容。

4. 单击“**保存**”。

重新颁发通知将发送给分配给法定保留通知的所有保管人。 此外，如果启用了提醒或上报通知，则这些类型的通知的工作流将重新启动。

## <a name="update-legal-hold-notifications-and-settings"></a>更新合法保留通知和设置

更新发布、发布、重新发布、提醒或上报通知的内容或设置时，这些更改将应用于工作流将来生成的所有通信。

## <a name="more-information"></a>更多信息

- [向事例添加保管人](add-custodians-to-case.md)

- [创建法定保留通知](create-hold-notification.md)

- [确认保留通知](acknowledge-hold-notification.md)
