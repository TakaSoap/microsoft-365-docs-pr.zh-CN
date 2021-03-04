---
title: 防止数据丢失
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何管理设置数据丢失防护策略。
ms.openlocfilehash: 54cd508ef0b0cfcf8b71dc86a4903f77a5354c36
ms.sourcegitcommit: 355bd51ab6a79d5c36a4e4f57df74ae6873eba19
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/04/2021
ms.locfileid: "50422059"
---
# <a name="prevent-data-loss-with-dlp"></a>使用 DLP 防止数据丢失

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

数据丢失防护策略可帮助识别和保护企业敏感信息，如社会保险号码或医疗记录。 

## <a name="try-it"></a>试一试！

1. To get started， go to the [admin center，](https://admin.microsoft.com)and select **Setup**.
1. 向下滚动以 **设置数据丢失防护，** 然后选择"**查看**"，然后选择"**管理"。**
1. 若要编辑策略，请选择它 **，选择"** 编辑策略"，然后选择要更改的项。 例如，选择 **"位置** "可更改扫描内容。
1. 若要在 Microsoft Teams 中启用内容扫描，将切换开关切换到"打开 **"位置，** 然后选择"保存 **"。**
1. 若要编辑策略设置，请选择"编辑 **"。**
1. 您需要设置适用于检测到的少量和大量敏感内容的单独规则。 展开低音量规则。 选择 **"编辑规则"。**
1. 查看设置并根据需要调整设置。 例如，你可以选择自定义电子邮件 **文本和****自定义策略提示文本**。 选择“**保存**”。
1. 对卷规则重复。 选择 **"保存"，** 然后 **关闭**。
1. 若要创建新策略，请选择"**创建策略"。**
1. 你可以创建自定义策略或从模板开始。 例如，要创建 HIPAA 策略，请选择"医疗健康"模板，然后选择"HIPAA (**美国健康保险法案**) 。 选择“下一步”。
1. 输入策略的名称和说明。 选择“下一步”。
1. 选择要扫描的位置。 选择“下一步”。
1. 选择要受保护的内容类型。 选择“下一步”。
1. 选择在检测到敏感信息时要发生的情况。 选择“下一步”。
1. 自定义访问和覆盖权限。 选择“下一步”。
1. 选择您希望策略何时生效。 选择“下一步”。
1. 查看设置，然后选择"创建 **"。** 策略生效后，包含上述敏感信息的电子邮件将被阻止，并且尝试发送该信息的发件人将看到一条警告消息。