---
title: 防止数据丢失
f1.keywords:
- NOCSH
ms.author: kwekua
author: kwekua
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
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
ms.openlocfilehash: a2e22e11a60953b882c088dd9e51dcde77695252
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60188597"
---
# <a name="prevent-data-loss-with-dlp"></a>使用 DLP 防止数据丢失

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

数据丢失防护策略可帮助识别和保护企业敏感信息，如社会保险号或医疗记录。 

## <a name="try-it"></a>试一试！

1. To get started， go to the [admin center](https://admin.microsoft.com)， and select **Setup**.
1. 向下滚动到 **"设置数据丢失防护"，** 然后选择"**查看**"，然后选择"管理 **"。**
1. 若要编辑策略，请选择它，选择" **编辑策略**"，然后选择要更改的项。 例如，选择 **"位置** "可更改扫描内容。
1. 若要启用内容扫描Microsoft Teams，将切换开关切换到 **开** 位置，**然后选择保存。**
1. 若要编辑策略设置，请选择"编辑 **"。**
1. 需要设置适用于检测到的少量和大量敏感内容的单独规则。 展开你的低音量规则。 选择 **"编辑规则"。**
1. 查看设置并根据需要调整设置。 例如，可以选择"自定义电子邮件 **文本"和**"**自定义策略提示文本"。** 选择“**保存**”。
1. 对高卷规则重复。 选择 **"保存"，** 然后选择"**关闭"。**
1. 若要创建新策略，请选择"**创建策略"。**
1. 你可以创建自定义策略或从模板开始。 例如，若要创建 HIPAA 策略，请选择"医疗与健康"模板，然后选择"美国健康保险法案 (**HIPAA) "。** 选择“**下一步**”。
1. 输入策略的名称和说明。 选择“**下一步**”。
1. 选择要扫描的位置。 选择“**下一步**”。
1. 选择要保护的内容类型。 选择“**下一步**”。
1. 选择在检测到敏感信息时要发生的情况。 选择“**下一步**”。
1. 自定义访问和替代权限。 选择“**下一步**”。
1. 选择您希望策略生效时间。 选择“**下一步**”。
1. 查看你的设置， **然后选择创建**。 策略生效后，包含描述的敏感信息的电子邮件将被阻止，并且尝试发送该信息的发件人将看到一条警告消息。