---
title: 使用通信编辑器
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
description: 在设置内容格式时，使用通信编辑器更改文本和合并字段变量。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 49751b3b5dccace1a77e29145e389b45168f441554adbdfa89d0aeb02219a48f
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53801406"
---
# <a name="use-the-communications-editor"></a>使用通信编辑器

定义门户内容、合法保留通知和相关提醒/升级的内容时，可以使用通信编辑器设置内容的格式并动态自定义内容。

## <a name="rich-text-editor"></a>格式文本编辑器

通信编辑器允许用户使用编辑器选项自定义文本。 例如，用户可以更改字体类型、创建项目符号列表、突出显示内容等。

## <a name="merge-field-variables"></a>合并域变量

您可以使用通信编辑器中的电子邮件合并变量将自定义保管人属性嵌入通信的正文文本中。 发送到保管人时，合并域将填充相应的字段。 例如，当发送到保管人 John Smith 时，合并域 [Custodian Name] 将用相应的名称进行转换。

You can use email merge fields by selecting the **Merge field** icons on the top of the rich-text editor control. 占位符将基于用户光标的位置添加。

### <a name="list-of-merge-field-variables"></a>合并域变量列表

<br>

****

|字段名|字段详细信息|
|---|---|
|显示名称|保管人的名字和姓氏。|
|Acknowledgment 链接|用于记录每个保管人确认的自定义链接。|
|门户链接|保管人合规性门户的自定义链接。|
|颁发官|指定颁发机构主管的电子邮件地址。|
|颁发日期|通知的发布日期为 UTC () 。|
|
