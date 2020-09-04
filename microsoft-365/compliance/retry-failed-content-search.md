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
localization_priority: Normal
ms.collection: ''
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 在调查过程中，可以使用 "重试" 按钮来解析包含内容位置错误的内容搜索。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: b3aed9c1d2d1fe3c40adb64b4854ef359f931bcb
ms.sourcegitcommit: 9ce9001aa41172152458da27c1c52825355f426d
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/03/2020
ms.locfileid: "47357552"
---
# <a name="retry-a-content-search-to-resolve-a-content-location-error"></a>重试内容搜索以解决内容位置错误

当您在安全与合规中心中使用内容搜索来搜索大量邮箱时，可能会收到类似于错误的搜索错误：

```text
Error


The search on the following locations failed:

User1@contoso.com: Problem in processing the request. Please try again later. If you keep getting this error, contact your admin. (CS008-009)

User2@contoso.com: Application error occurred. Please try again later. (CS012-002)
```

这些错误 (CS001-002、CS003-002、CS008-009、CS012-002 和的其他) 错误的错误代码，这表示内容搜索无法搜索特定的内容位置;在此示例中，未搜索两个邮箱。 这些错误显示在内容搜索的 "状态详细信息" 飞出页面上。

## <a name="cause-of-content-location-errors"></a>内容位置错误的原因

搜索大量邮箱时，会在 Microsoft 数据中心的数千台服务器之间分发搜索。 在任意时刻，特定服务器可能处于重新启动状态或在故障转移到冗余副本的过程中。 在上述任一情况下，内容搜索检索数据的请求都将超时。在上面的示例中，失败的邮箱的错误是搜索超时的结果。

## <a name="resolving-content-location-errors"></a>解决内容位置错误

重新启动搜索通常会在不同的服务器上产生类似的错误。 请单击 "搜索结果" 页顶部显示的 " **重试** " 按钮，而不是重新启动搜索。

![单击 "重试" 按钮解决内容位置错误](../media/retrycontentsearch3.png)

这将导致仅对失败的邮箱重试搜索。 当您重试搜索时，将保留已成功返回的其他结果。

## <a name="tips-to-avoid-content-location-errors"></a>避免内容位置错误的提示

以下是内容位置错误的一些其他原因，以及一些提示，可帮助您在搜索大量邮箱时避免出现这些错误。

- 正在搜索的邮箱可能因用户活动而繁忙。 在这种情况下，搜索服务可能会对自身进行限制以阻止邮箱变得不可用。 若要避免这种情况，请尝试在非工作时间运行搜索。

- 搜索查询可能会从邮箱中检索过多的内容。 如果可能，请尝试使用关键字、日期范围和搜索条件来缩小搜索范围。

- 使用 [关键字列表](view-keyword-statistics-for-content-search.md#get-keyword-statistics-for-content-searches)创建搜索查询时，关键字或关键字短语过多。 当您运行使用关键字列表的搜索查询时，该服务实质上会对关键字列表中的每一行运行单独的搜索，以便可以生成统计信息。 如果要在搜索查询中使用关键字列表，请最大限度地减少关键字列表中的行数，或将数字关键字分成较小的列表，并为每个关键字列表创建不同的搜索。

  > [!NOTE]
  > 为了帮助减少由大型关键字列表导致的问题，您现在限制为搜索查询的关键字列表中的最多20行。

- 同时对同一邮箱执行的搜索过多。 如果可能，请尝试一次在任何一个邮箱上运行一次搜索。

- 在一次搜索中搜索的邮箱过多。 搜索大量邮箱时，会增加内容位置错误的可能性。 如果可能，请尝试运行多个搜索，以便每个搜索都包含组织中的一部分邮箱。

- 对邮箱执行必需的维护。 尽管此原因可能很少发生，请在收到内容位置错误后稍等片刻，然后重试搜索。
