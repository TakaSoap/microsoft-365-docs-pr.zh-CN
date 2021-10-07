---
title: 应用程序控制
description: 如何使用应用程序控件和信任应用程序
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 1a3b976accf1f86a96100efb9a890adab4ec3698
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60201549"
---
# <a name="app-control"></a>应用程序控制

应用控制是应用中的可选Microsoft 托管桌面，用于限制在客户端设备上执行代码。 此控制通过要求只有经客户批准的发布者列表签名的代码才能运行，从而降低恶意软件或恶意脚本的风险。 此控件有许多安全优势，但它主要用于保护数据和标识免受基于客户端的漏洞攻击。

Microsoft 托管桌面创建支持核心生产力方案的基本策略，从而简化应用控制策略的管理。 你可以将信任扩展到特定于环境中应用和脚本的其他签名者。 


任何安全技术都需要在用户体验、安全性和成本之间实现平衡。 应用控制可降低环境中恶意软件的威胁，但会给用户带来后果，并针对 IT 管理员执行进一步的操作。

**其他安全性：**

应用控制策略不信任的应用或脚本被阻止在设备上运行。

**其他责任：**

- 你负责测试你的应用，以确定应用程序控制策略是否会阻止它们。
- 如果应用 (或将被) ，你负责确定所需的签署人详细信息，并通过管理门户请求更改。

**Microsoft 托管桌面职责：**

- Microsoft 托管桌面支持核心 Microsoft 产品（如 M365 应用、Windows、Teams、OneDrive 等）的基本策略。
- Microsoft 托管桌面你的受信任签署人并将更新的策略部署到你的设备。


## <a name="managing-trust-in-applications"></a>在应用程序中管理信任

Microsoft 托管桌面一个信任 Microsoft 技术核心组件的基本策略。 然后 *，通过* 通知用户已信任哪些应用程序Microsoft 托管桌面脚本添加信任。

### <a name="base-policy"></a>基本策略

Microsoft 托管桌面与 Microsoft 网络安全专家协作，创建和维护标准策略，该策略允许通过 Microsoft Intune 部署大多数应用，同时阻止危险活动，如代码编译或执行不受信任的文件。

基本策略采用以下方法限制软件执行：

- 将允许由管理员运行的文件运行。
- 将允许 *运行不在用户* 可写入目录中的位置中的文件。
- 文件由受信任的 [签名者签名](#signer-requests)。
- 大多数由 Microsoft 签名的文件都将运行，但一些文件将被阻止以防止执行代码编译等高风险操作。


如果管理员外的用户可能已经将应用或脚本添加到设备 (即，它位于用户可写的目录) 中，则除非管理员明确允许，否则我们不允许其执行。 如果用户被欺骗试图安装恶意软件，如果用户运行应用中的漏洞尝试安装恶意软件，或者用户有意尝试运行未经授权的应用或脚本，我们的策略将停止执行。

### <a name="signer-requests"></a>签名者请求

通过提交签名者请求，通知我们你信任的软件发布者 *提供哪些应用*。 通过执行此操作，我们将该信任信息添加到基线应用程序控制策略中，并允许使用该发布者证书签名的任何软件在你的设备上运行。

## <a name="audit-and-enforced-policies"></a>审核和强制策略

Microsoft 托管桌面两Microsoft Intune策略来提供应用控制：

### <a name="audit-policy"></a>审核策略
此策略创建日志以记录应用或脚本是否将被强制策略阻止。 审核策略不强制执行应用控制规则，旨在用于测试目的，以确定应用程序是否需要发布者豁免。 它会在事件 (中记录 8003 或 8006) 警告，而不是阻止执行或安装指定的应用或脚本。

### <a name="enforced-policy"></a>强制策略
此策略阻止不受信任的应用和脚本运行，并且每当应用或脚本被阻止时创建日志。 强制执行的策略会阻止标准用户执行存储在用户可写入目录中的应用或脚本。

测试组中设备应用了审核策略，以便你可以使用它们验证任何应用程序是否会导致问题。 First、Fast 和 Broad (组) 使用强制策略，因此这些组的用户将无法运行不受信任的应用或脚本。







