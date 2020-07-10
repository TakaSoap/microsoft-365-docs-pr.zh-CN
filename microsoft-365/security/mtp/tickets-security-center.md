---
title: 在 Microsoft 365 安全中心中创建和跟踪 ServiceNow 票证
description: 了解如何从 Microsoft 365 安全中心创建和跟踪 ServiceNow 中的票证。
keywords: security、Microsoft 365、M365、安全分数、安全中心、ServiceNow、票证、任务
ms.prod: w10
ms.mktglfcycl: deploy
ms.localizationpriority: medium
f1.keywords:
- NOCSH
ms.author: ellevin
author: levinec
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
ms.topic: article
search.appverid:
- MOE150
- MET150
ms.custom:
- seo-marvel-apr2020
ms.openlocfilehash: 16ee37b1c7bf33c902db35af2d29744f42830ea7
ms.sourcegitcommit: 09a500a44d8723f8f2be87d9ad4ce7e453c5192b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/10/2020
ms.locfileid: "45094830"
---
# <a name="create-and-track-servicenow-tickets-in-the-microsoft-365-security-center"></a>在 Microsoft 365 安全中心中创建和跟踪 ServiceNow 票证

[Microsoft 365 安全中心](overview-security-center.md)已得到增强，能够在 ServiceNow 中以本机方式创建和跟踪票证。 [了解有关 ServiceNow 的详细信息](https://www.servicenow.com/)

在安全中心中，安全管理员可以直接向 ServiceNow 发送[Microsoft Secure 得分](microsoft-secure-score.md)改进操作，并创建一个票证。 可以创建事件管理和变更管理票证。 然后，可以在安全中心主页和 ServiceNow 中跟踪它们。

- [**了解先决条件、数据交换和疑难解答**](tickets.md)
- **在合规中心中管理 ServiceNow 票证** (即将推出) 

## <a name="connect-microsoft-365-security-center-to-servicenow"></a>将 Microsoft 365 安全中心连接到 ServiceNow

导航到 Microsoft 365 安全中心主页以查看 ServiceNow 连接卡。

![您是否使用 ServiceNow](../../media/do-you-use-servicenow-250.png)

选择 "连接到 ServiceNow" 以转到 "ServiceNow 设置" 页。 按照说明授权 Microsoft 365 连接器应用。

> [!NOTE]
> 在授权 Microsoft 365 安全中心和 ServiceNow 之间的连接之前，请确保使用您在安装步骤中创建的集成用户登录名和密码。 请勿使用你的个人凭据。

按照说明进行操作并授权连接后，请查看 Microsoft 365 安全中心连接页和 ServiceNow Microsoft 365 票证发放连接器应用程序体验中的连接状态。 现在，你已设置为开始创建任务！

### <a name="troubleshooting"></a>疑难解答

了解在连接过程中可能遇到的常见错误，以及如何在 "[疑难解答" 部分](tickets.md#troubleshooting)中对其进行缓解。

## <a name="create-a-task-and-share-it-to-servicenow"></a>创建一个任务并将其共享到 ServiceNow

建立集成后，基于特定[Microsoft 安全得分](microsoft-secure-score.md)改进操作创建 ServiceNow 任务。 转到 Microsoft 365 安全中心门户中安全得分的任何改进措施，并选择 "**共享**"。 其中一个下拉选项是 ServiceNow。

将生成一个任务，您可以在其中设置优先级并编辑名称、说明或截止日期。 填写所有必填字段后，将该任务发送到 ServiceNow。

在 ServiceNow 中，此任务显示为 Microsoft 365 安全性和配置更改请求。

## <a name="track-tickets"></a>跟踪票证

一旦创建了 ServiceNow 更改管理和事件管理票证，它们就会显示在 Microsoft 365 安全中心主页上的卡片上。 通过这些卡，您可以创建一个票证、查看所有票证或管理 ServiceNow 配置。

![ServiceNow 更改管理票证](../../media/change-management-375.png)  ![ServiceNow 事件管理票证](../../media/incident-management-375.png)

若要在 Microsoft 365 安全中心中重新设置或管理你的 ServiceNow 集成，请选择任一卡片上的 "**管理 servicenow 配置**"。 在此处，删除当前的 ServiceNow 连接并自定义票证状态名称。

借助 Microsoft 365 security center 中显示的 ServiceNow 票证，你的任务可以在某个位置进行跟踪，并在你的其他安全仪表板项目旁边进行操作。

## <a name="resources"></a>资源

- [了解先决条件、数据交换和疑难解答](tickets.md)
- [Microsoft 安全功能分数](microsoft-secure-score.md)