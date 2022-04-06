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
ms.openlocfilehash: 2de0e67c78ac558f4bdc2648790e49fad86e3178
ms.sourcegitcommit: 33bc25167812b31c51cf096c728e3a5854e94f1c
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/01/2022
ms.locfileid: "64595038"
---
# <a name="support-for-double-byte-character-set-release-notes"></a>双字节字符集支持发行说明

 Microsoft 365 信息保护现可为以下语言提供双字节字符集语言支持：

- 简体中文
- 繁体中文
- 韩语
- 日语

此支持适用于敏感信息类型和关键字词典，并将在数据丢失防护（适用于 Exchange Online、SharePoint Online、OneDrive for Business 和 Teams）、通信合规性、Office 应用中的自动标签和 Microsoft Defender for Cloud Apps 中有所体现。

## <a name="known-issues"></a>已知问题

- 当附加到电子邮件的文本文件采用不带字节顺序标记 (BOM) 的 UTF-8 格式时，通信合规性策略不会检测到该电子邮件。

- 如果针对策略条件“邮件包含其中任意字词”输入了一句话，则通信合规性策略无法检测到值。 如果将该策略中指定的文本写为一个词，则可以检测到；但是，如果将其写在句子中间，则不会检测到。

- 将字典指定为类型信息的通信合规性策略不会检测 Teams 私人聊天和频道聊天。

- 通信合规性在此阶段不支持以下条件（我们计划在将来修复这些问题）： 
  - “邮件包含其中任意字词”
  - “邮件不包含其中任意字词”
  - “附件包含其中任意字词”
  - “附件包含其中任意字词”

- 数据丢失防护策略可在运行 Catalina 10.15 及更高版本的 macOS 设备（预览版）上强制执行，但以下所述的东亚语言（包括日语）的条件除外。
  - 不检测全角数字，例如使用内置模板（如日本银行帐号）
  - 不检测没有分隔符的数字
  - 对于敏感信息类型，不检测使用半角空格分隔的关键字。 例如：将日语单词设置为敏感信息类型，如果其位于句子中，则不检测字典
  - 不检测包含英语和日语（東京2020）的单词

相反，建议使用可检测邮件和附件中的模式的关键字字典创建自定义敏感信息类型 (SIT)，并将此自定义 SIT 作为通信合规性策略条件。
