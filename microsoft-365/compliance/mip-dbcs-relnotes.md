---
title: 双字节字符集的 Microsoft 365 合规中心支持发行说明
ms.author: chrfox
author: chrfox
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: high
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 双字节字符集支持的发行说明。
ms.openlocfilehash: 3731e32594461df29a9cc5ec3f21bf3eb17ee79c
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190673"
---
# <a name="support-for-double-byte-character-set-release-notes"></a>双字节字符集支持发行说明

 Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持：

- 简体中文
- 繁体中文
- 韩语
- 日语

此支持适用于敏感信息类型和关键字词典，并将在数据丢失防护（适用于 Exchange Online、SharePoint Online、OneDrive for Business 和 Teams）、通信合规性、Office 应用中的自动标签和 Microsoft 云应用安全中有所体现。

## <a name="known-issues"></a>已知问题

- 当附加到电子邮件的文本文件采用不带字节顺序标记 (BOM) 的 UTF-8 格式时，通信合规性策略不会检测到该电子邮件。

- 如果针对策略条件“邮件包含其中任意字词”输入了一句话，则通信合规性策略无法检测到值。 如果将该策略中指定的文本写为一个词，则可以检测到；但是，如果将其写在句子中间，则不会检测到。

- 将字典指定为类型信息的通信合规性策略不会检测 Teams 私人聊天和频道聊天。

- 目前阶段不支持采用以下条件来确保通信合规性（我们计划以后修复这些问题）： 
  - “邮件包含其中任意字词”
  - “邮件不包含其中任意字词”
  - “附件包含其中任意字词”
  - “附件包含其中任意字词”

相反，建议使用可检测邮件和附件中的模式的关键字字典创建自定义敏感信息类型 (SIT)，并将此自定义 SIT 作为通信合规性策略条件。


