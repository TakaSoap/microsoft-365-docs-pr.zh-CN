---
title: 近重复检测 - 电子数据展示
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
description: 在分析文档中的大小写数据时，使用近重复检测对文本类似的文档Advanced eDiscovery。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: cbd01bd38f45a397a82a8db3774997349f4eec88
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193203"
---
# <a name="near-duplicate-detection-in-advanced-ediscovery"></a>几乎重复检测Advanced eDiscovery

请考虑要审阅的一组文档，其中一个子集基于同一模板并且主要具有相同的样本语言，并且存在一些差异。 如果审阅者可以识别此子集，彻底审阅其中一个子集，并查看其余部分的差异，则他们不会错过任何唯一的信息，而只是花时间阅读所有文档涵盖内容所花时间的一小部分。 近似重复检测组将文本类似的文档整理到一起，以便帮助你提高审阅流程的效率。

## <a name="how-does-it-work"></a>它的工作原理

运行近似重复检测时，系统会对每一份包含文本的文档展开分析。 然后，系统会将每份文档相互比对，以确定其相似性是否大于设置阈值。 如果是，则这些文档将被组合在一起。 对所有文档进行比对和分组后，每一组会有一份文档被标记为“核心文档”；在审阅文档时，可以先查看“核心文档”，然后查看位于相同近似重复集内的其他文件。重点关注核心文档和正在审阅的文档之间的差异。
