---
title: 重试内容搜索以解决内容位置错误
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
audience: Admin
ms.topic: troubleshooting
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在调查期间，可以使用"重试"按钮解决内容位置错误的内容搜索。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 3c433dfa6bf842f1d62350e3b518177d1bdca6d7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60192159"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>重试内容搜索以解决内容位置错误

在安全与合规中心内使用内容搜索搜索大量邮箱时，可能会收到类似于错误的搜索错误：

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

这些错误 (CS001-002、CS003-002、CS008-009、CS012-002 和 CS0XX-0XX) 形式的其他错误指示内容搜索无法搜索特定内容位置;本示例中，未搜索两个邮箱。 这些错误显示在内容搜索的状态详细信息飞出页上。

## <a name="cause-of-content-location-errors"></a>内容位置错误的原因

在搜索大量邮箱时，搜索将分布在 Microsoft 数据中心的数千台服务器上。 在任一时间，特定服务器可能处于重新启动状态或正在向冗余副本进行故障处理。 在这两种情况下，内容搜索检索数据的请求都将退出。在上一示例中，失败的邮箱的错误是搜索超时的结果。

## <a name="resolving-content-location-errors"></a>解决内容位置错误

重新启动搜索通常会导致不同服务器上出现类似的错误。 单击显示在搜索结果页面顶部的 **"** 重试"按钮，而不是重新启动搜索。

![单击"重试"按钮可解决内容位置错误。](../media/retrycontentsearch3.png)

这将导致仅重试失败的邮箱的搜索。 重试搜索时，将保留成功返回的其他结果。

## <a name="tips-to-avoid-content-location-errors"></a>使用技巧以避免内容位置错误

以下是导致内容位置错误的其他一些原因以及一些提示，可帮助你在搜索大量邮箱时避免这些错误。

- 被搜索的邮箱可能由于用户活动而繁忙。 在这种情况下，搜索服务可能会限制自身以防止邮箱变得不可用。 若要避免这种情况，请尝试在非营业时间运行搜索。

- 搜索查询可能从邮箱检索太多内容。 如果可能，请尝试使用关键字、日期范围和搜索条件缩小搜索范围。

- 使用关键字列表 创建搜索查询时，关键字或 [关键字短语过多](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-searches)。 当您运行使用关键字列表的搜索查询时，该服务实际上对关键字列表中的每一行运行单独的搜索，以便可以生成统计信息。 如果在搜索查询中使用关键字列表，请最大程度地减少关键字列表中的行数或将数字关键字划分为较小的列表，并为每个关键字列表创建不同的搜索。

  > [!NOTE]
  > 为了帮助减少由大型关键字列表导致的问题，现在搜索查询的关键字列表中最多只能有 20 行。

- 同时对同一邮箱执行的搜索过多。 如果可能，请尝试对任意一个邮箱一次运行一个搜索。

- 在一次搜索中搜索过多邮箱。 搜索大量邮箱时，内容位置错误的可能性会增加。 如果可能，请尝试运行多个搜索，以便每个搜索包括组织中邮箱的子集。

- 正在对邮箱执行所需的维护。 尽管此原因不常出现，但在收到内容位置错误后稍等一下，然后重试搜索。
