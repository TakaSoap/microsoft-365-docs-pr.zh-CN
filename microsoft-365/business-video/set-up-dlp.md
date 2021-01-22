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
ROBOTS: NOINDEX, NOFOLLOW
ms.collection:
- M365-subscription-management
- Adm_O365
ms.custom:
- AdminSurgePortfolio
- adminvideo
- okr_smb
monikerRange: o365-worldwide
search.appverid:
- BCS160
- MET150
- MOE150
description: 了解如何管理设置的数据丢失防护策略。
ms.openlocfilehash: e963cf85fee887b6e91c6e54b00aaa9e5174e3b6
ms.sourcegitcommit: 855719ee21017cf87dfa98cbe62806763bcb78ac
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/22/2021
ms.locfileid: "49927954"
---
# <a name="prevent-data-loss-with-dlp"></a>使用 DLP 防止数据丢失

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE3TGvL?autoplay=false]

数据丢失防护策略可帮助识别和保护企业敏感信息，如社会保险号或医疗记录。 

## <a name="try-it"></a>试一试！

1. 若要开始，请转到管理 [中心](https://admin.microsoft.com)，然后选择"**设置"。**
1. 向下滚动以 **设置数据丢失防护，****然后选择"查看**"，然后 **管理**。
1. 若要编辑策略，请选择它，选择"编辑 **策略**"，然后选择要更改的策略。 例如，选择 **"位置** "可更改扫描内容。
1. 若要启用 Microsoft Teams 中内容的扫描，将切换开关切换到"打开 **"位置，** 然后选择"**保存"。**
1. 若要编辑策略设置，请选择"编辑 **"。**
1. 需要设置适用于检测到的少量和大量敏感内容的单独规则。 展开低音量规则。 选择 **"编辑规则"。**
1. 查看设置并根据需要调整设置。 例如，你可以选择自定义电子邮件 **文本和****自定义策略提示文本**。 选择 **“保存”**。
1. 对高音量规则重复执行。 选择 **"保存**"，然后 **关闭**。
1. 若要创建新策略，请选择"**创建策略"。**
1. 你可以创建自定义策略或从模板开始。 例如，若要创建 HIPAA 策略，请选择"医疗健康"模板，然后选择 **HIPAA (美国健康保险) 。** 选择“**下一步**”。
1. 输入策略的名称和说明。 选择“**下一步**”。
1. 选择要扫描的位置。 选择“**下一步**”。
1. 选择要保护的内容类型。 选择“**下一步**”。
1. 选择在检测到敏感信息时要发生的情况。 选择“**下一步**”。
1. 自定义访问和替代权限。 选择“**下一步**”。
1. 选择您希望策略生效时间。 选择“**下一步**”。
1. 查看你的设置，然后选择"创建 **"。** 策略生效后，包含描述的敏感信息的电子邮件将被阻止，并且尝试发送该信息的发件人将看到一条警告消息。