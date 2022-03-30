---
title: 提交文件供 Microsoft 分析
description: 了解如何将文件提交给 Microsoft 进行恶意软件分析、如何跟踪提交内容以及争议检测。
ms.reviewer: ''
keywords: 安全， 示例提交帮助， 恶意软件文件， 病毒文件， 特洛伊木马文件， 提交， 发送到 Microsoft， 提交样本， 病毒， 特洛伊木马， 蠕虫， 未检测， 未检测， 电子邮件， 电子邮件恶意软件， 我认为这是恶意软件， 我认为这是病毒， 我可以在哪里发送病毒， 是这种病毒， MSE， 不检测， 没有签名， 没有检测， 可疑文件， MMPC，Microsoft 恶意软件防护中心，研究人员，分析师，WDSI， 安全智能
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
ms.openlocfilehash: 78f1e00555d36880f24f05d213f42725f4ac0133
ms.sourcegitcommit: b3530441288b2bc44342e00e9025a49721796903
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/20/2022
ms.locfileid: "63680189"
---
# <a name="submit-files-for-analysis"></a>提交文件进行分析

如果您怀疑文件可能是恶意软件或检测不正确，您可以将其提交给我们进行分析。 此页面解答了有关提交文件进行分析的一些常见问题。

## <a name="how-do-i-send-a-malware-file-to-microsoft"></a>如何向 Microsoft 发送恶意软件文件？

你可以向我们发送你认为可能是恶意软件的文件，或者通过示例提交门户错误 [检测的文件](https://www.microsoft.com/en-us/wdsi/filesubmission)。

我们收到许多来源中的大量示例。 我们的分析按文件检测数和提交类型确定优先级。 您可以通过提供有关你使用的产品以及找到文件时所执行操作的详细信息来帮助我们完成快速分析。

登录后，你将能够跟踪提交。

## <a name="can-i-send-a-sample-by-email"></a>我能否通过电子邮件发送示例？

否，我们仅通过示例提交门户 [接受提交](https://www.microsoft.com/en-us/wdsi/filesubmission)。

## <a name="can-i-submit-a-sample-without-signing-in"></a>能否在不登录的情况下提交示例？

否。 如果你是企业客户，你需要登录，以便我们可以适当地确定你的提交优先级。 如果当前遇到病毒爆发或与安全相关的事件，请联系指定的 Microsoft 支持专业人员或转到 [Microsoft 支持](https://support.microsoft.com/) 部门，立即获得帮助。

## <a name="what-is-the-software-assurance-id-said"></a>"软件保障 ID" (") ？

[SAID (ID) ](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)供企业客户跟踪支持权利。 提交门户接受并保留"SAID"信息，并允许具有有效"确定"的客户提供更高优先级的提交。

### <a name="how-do-i-dispute-the-detection-of-my-program"></a>如何对检测我的程序存在争议？

[以软件](https://www.microsoft.com/en-us/wdsi/filesubmission) 开发人员文件格式提交文件。 等待你的提交有最终决定。

如果您对我们确定提交内容不满意，请使用提交结果中提供的开发人员联系人表单联系 Microsoft。 如有必要，我们将使用你提供的信息进行进一步调查。

我们鼓励所有软件供应商和开发人员阅读 [Microsoft 如何识别恶意软件和不需要的软件](criteria.md)。

## <a name="how-do-i-track-or-view-past-sample-submissions"></a>如何跟踪或查看过去的提交示例？

可以通过提交历史记录页面跟踪 [提交](https://www.microsoft.com/en-us/wdsi/submissionhistory)。

## <a name="what-does-the-submission-status-mean"></a>提交状态意味着什么？

每个提交都显示为以下状态类型之一：

* 已提交 - 已接收文件

* 正在进行 - 分析员已开始检查文件

* 已关闭 - 分析员已作出最终决定

可以在提交历史记录页面上查看提交给我们的任何 [文件的状态](https://www.microsoft.com/en-us/wdsi/submissionhistory)。

## <a name="how-does-microsoft-prioritize-submissions"></a>Microsoft 如何确定提交优先级

处理提交需要专门的分析员资源。 因为我们定期收到大量提交，所以我们根据优先级来处理它们。 以下因素影响我们确定提交优先级的优先级：

* 优先处理可能会影响大量计算机的流行文件。

* 经过身份验证的客户（尤其是具有有效 SOFTWARE [Assurance IDs (或) 的客户提供 ](https://www.microsoft.com/licensing/licensing-programs/software-assurance-default.aspx)优先服务。

* 由 SAID 持有者标记为高优先级的提交将被立即关注。

我们的系统会立即扫描你的提交，以在分析员开始处理你的案例之前提供最新决定。 请注意，分析员可能已经处理了相同的文件。 若要检查确定的更新，请选择提交详细信息页面上的"重新扫描"。
