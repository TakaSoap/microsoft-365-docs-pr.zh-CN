---
title: 提交文件供 Microsoft 分析
description: 了解如何将文件提交到 Microsoft 进行恶意软件分析、如何跟踪提交和争议检测。
ms.reviewer: ''
keywords: 安全性，示例提交帮助，恶意软件文件，病毒文件，木马文件，提交，发送给 Microsoft，提交示例，病毒，木马，蠕虫，未检测，不检测，电子邮件 microsoft，电子邮件恶意软件，我认为这是恶意软件，我认为这是一个病毒，在那里我可以发送病毒，这是病毒，MSE，不检测，没有签名，没有检测，可疑文件， MMPC， Microsoft 恶意软件防护中心， 研究人员， 分析师， WDSI， 安全智能
ms.prod: m365-security
ms.mktglfcycl: secure
ms.sitesec: library
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
search.appverid: met150
ms.technology: m365d
ms.openlocfilehash: df2ab2b2019bb76af49f00d2751cdc76848705d1
ms.sourcegitcommit: 85ce5fd0698b6f00ea1ea189634588d00ea13508
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/06/2022
ms.locfileid: "64663591"
---
# <a name="submit-files-for-analysis"></a>提交文件以供分析

如果你有一个文件，你怀疑可能是恶意软件或被错误地检测到，你可以将其提交给我们进行分析。 本页提供了有关提交文件进行分析的一些常见问题的解答。

## <a name="how-do-i-send-a-malware-file-to-microsoft"></a>如何实现向 Microsoft 发送恶意软件文件？

可以向我们发送您认为可能是恶意软件的文件或通过 [示例提交门户](https://www.microsoft.com/wdsi/filesubmission)错误地检测到的文件。

我们从许多源接收大量示例。 我们的分析按文件检测的数量和提交类型确定优先级。 可以通过提供有关所用产品的详细信息以及你在找到文件时正在执行的操作来帮助我们完成快速分析。

登录后，你将能够跟踪提交。

## <a name="can-i-send-a-sample-by-email"></a>是否可以通过电子邮件发送示例？

否，我们仅通过 [示例提交门户接受提交](https://www.microsoft.com/wdsi/filesubmission)。

## <a name="can-i-submit-a-sample-without-signing-in"></a>是否可以在不登录的情况下提交示例？

否。 如果你是企业客户，则需要登录，以便我们可以适当地确定提交优先级。 如果当前遇到病毒爆发或安全相关事件，应联系指定的 Microsoft 支持专业人员，或转到[Microsoft 支持部门](https://support.microsoft.com/)以立即获得帮助。

## <a name="what-is-the-software-assurance-id-said"></a> (说) 软件保障 ID 是什么？

[SAID)  (软件保障 ID ](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx) 用于企业客户跟踪支持权利。 提交门户接受并保留 SAID 信息，并允许具有有效 SAID 的客户提交更高的优先级。

### <a name="how-do-i-dispute-the-detection-of-my-program"></a>如何实现对检测我的程序提出异议？

以软件开发人员身份[提交有关文件](https://www.microsoft.com/wdsi/filesubmission)。 等待提交最终确定。

如果对我们提交的决定不满意，请使用提交结果随附的开发人员联系表单访问 Microsoft。 如有必要，我们将使用你提供的信息进行进一步调查。

我们鼓励所有软件供应商和开发人员了解 [Microsoft 如何识别恶意软件和不需要的软件](criteria.md)。

## <a name="how-do-i-track-or-view-past-sample-submissions"></a>如何实现跟踪或查看过去的示例提交？

可以通过提交 [历史记录页跟踪提交](https://www.microsoft.com/wdsi/submissionhistory)。

## <a name="what-does-the-submission-status-mean"></a>提交状态意味着什么？

每个提交都显示为以下状态类型之一：

* 已提交 - 已收到文件

* 正在进行 - 分析师已开始检查文件

* 已关闭 - 分析师已做出最终决定

可以在 [提交历史记录页](https://www.microsoft.com/wdsi/submissionhistory)上查看提交给我们的任何文件的状态。

## <a name="how-does-microsoft-prioritize-submissions"></a>Microsoft 如何确定提交优先级

处理提交需要专门的分析师资源。 由于我们定期收到大量提交，因此我们根据优先级处理这些提交。 以下因素影响我们确定提交优先级：

* 可能会影响大量计算机的常见文件是优先级的。

* 经过身份验证的客户，尤其是具有有效 [软件保障 ID (SAID) ](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)的企业客户，优先使用。

* 被 SAID 持有者标记为高优先级的提交会立即得到关注。

甚至在分析师开始处理你的案例之前，系统会立即扫描你的提交，以便你做出最新决定。 请注意，同一文件可能已由分析师处理。 若要检查确定的更新，请在提交详细信息页上选择"重新扫描"。
