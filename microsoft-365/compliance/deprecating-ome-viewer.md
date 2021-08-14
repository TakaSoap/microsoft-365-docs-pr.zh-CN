---
title: 弃用邮件加密查看器应用
f1.keywords:
- NOCSH
ms.author: krowley
author: kccross
manager: laurawi
ms.date: 6/29/2018
audience: Admin
ms.topic: article
ms.service: O365-seccomp
localization_priority: Normal
search.appverid:
- MET150
- MOE150
ms.assetid: 6336cabb-b06e-402f-9e85-8bb9eb4ce68f
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 2018 Office 365 邮件加密 (OME) Viewer 应用已从 Android 和 Apple 应用商店中删除。
ms.openlocfilehash: dc12eaa783c43fb80fb8ecbe984ecbcd0cda315f33b2cd1d3bc65e8932d77bda
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53892083"
---
# <a name="deprecating-message-encryption-viewer-app"></a>弃用邮件加密查看器应用

2018 年 8 月 15 日，我们Office 365 邮件加密 (Android 和 Apple) OME 查看器移动应用。 要求Office 365 邮件加密查看器应用读取在 Apple 和 Android 手机上使用以前版本的 OME 加密的电子邮件和附件。 除了删除 OME 查看器应用外，我们不会对以前版本的 OME 进行任何其他更改。
  
## <a name="changes-from-august-2018"></a>2018 年 8 月更改

正如 2017 年 9 月发布的公告，我们发布了[新版本的 Office 365 邮件加密](https://aka.ms/ome2017)以便用户可以向组织内部或外部的任何人发送加密和受保护的邮件，而无需使用移动应用。 此后，我们添加了其他功能：
  
- [仅加密模板](https://aka.ms/encryptonly)

- [用于解密附件的控件](https://techcommunity.microsoft.com/t5/Security-Privacy-and-Compliance/Admin-control-for-attachments-now-available-in-Office-365/ba-p/204007)

通过此更改，用户将不再能够从 8 月 1 Office 365 邮件加密查看器下载新版移动应用。 因此，邮件收件人可能无法在某些 Android 和 Apple 移动设备上读取使用以前版本的 OME 加密的邮件。 但是，他们仍然能够在个人计算机上读取这些消息， (桌面浏览器) 。 已下载应用的用户将继续能够使用它。
  
## <a name="why-this-change-was-made"></a>为何进行此更改

新版本的 OME 不再需要移动应用来读取受保护的电子邮件和附件。 使用新的 OME 功能的客户可以查看受保护的邮件，Outlook和非客户可以在浏览器中查看受保护的邮件。
  
要求用户下载移动应用是客户查看受保护邮件的另一障碍。 新功能Office 365 邮件加密提供更好的移动体验。
  
## <a name="can-i-still-use-the-previous-version-of-office-365-message-encryption"></a>我能否仍使用早期版本的 Office 365 邮件加密

目前不会弃用早期版本的 Office 365 邮件加密，但是，我们对新版本的 Office 365 邮件加密 进行了重大增强，从而可以更轻松地加密和权限保护任何人和任何设备的敏感数据，包括用户直接在 Outlook (桌面、移动和 Web) 中读取受保护邮件的能力。 
  
## <a name="what-do-i-need-to-do-to-prepare-for-this-change"></a>我需要做什么来准备此更改

如果组织当前向需要 OME 查看器应用的收件人发送加密附件，应更新文档和培训资源。
  
我们建议更新现有Exchange邮件流规则以使用当前版本的 OME，以便您的组织可以利用新增和改进的功能。 设置新的 OME 功能后，收件人无需 OME 查看器应用在移动设备上读取加密邮件。
  
Microsoft 建议你在组织合理时制定移动到新 OME 功能的计划。 有关说明，请参阅[设置新的Office 365 邮件加密功能](set-up-new-message-encryption-capabilities.md)。 若要详细了解新功能如何首先工作，[请参阅Office 365 邮件加密。](ome.md)
  

