---
title: 应用程序控制
description: 如何使用应用程序控件和信任应用程序
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
audience: ITpro
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 108c4d3d64f503d2221aed9df9724faee85b2998
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825465"
---
# <a name="app-control"></a>应用程序控制

应用控制是一种可选的安全Microsoft 托管桌面，用于限制在客户端设备上执行代码。

此控制降低了恶意软件或恶意脚本的风险。 该控件要求只有经客户批准的发布者列表签名的代码才能运行。 此控件有许多安全优势，但它主要用于保护数据和标识免受基于客户端的漏洞攻击。

Microsoft 托管桌面创建支持核心生产力方案的基本策略，从而简化应用控制策略的管理。 你可以将信任扩展到特定于环境中应用和脚本的其他签名者。

任何安全技术都需要在用户体验、安全性和成本之间实现平衡。 应用控制可降低环境中恶意软件的威胁，但会给用户带来后果，并针对 IT 管理员执行进一步的操作。

| 其他安全和职责 | 说明 |
| ------ | ------ |
| 其他安全性 | 应用控制策略不信任的应用或脚本被阻止在设备上运行。 |
| 其他责任 | <ul><li>你负责测试你的应用，以确定应用程序控制策略是否会阻止它们。</li><li>如果应用 (或将被) ，你负责确定所需的签名者详细信息。 必须通过管理门户请求更改。</li></ul>
| Microsoft 托管桌面责任 | <ul><li>Microsoft 托管桌面支持核心 Microsoft 产品（如 Microsoft 365 应用版、Windows、Teams、OneDrive 等）的基本策略。</li><li>Microsoft 托管桌面你的受信任签名者并将更新的策略部署到你的设备。</li></ul>

## <a name="managing-trust-in-applications"></a>在应用程序中管理信任

Microsoft 托管桌面一个信任 Microsoft 技术核心组件的基本策略。 然后 *，通过* 告知用户已信任哪些应用和脚本Microsoft 托管桌面添加对你自己的应用程序和脚本的信任。

### <a name="base-policy"></a>基本策略

Microsoft 托管桌面与 Microsoft 网络安全专家协作，创建和维护标准策略。 此标准策略：

- 启用通过应用程序部署Microsoft Intune。
- 阻止危险活动，如代码编译或不受信任的文件执行。

基本策略采用以下方法限制软件执行：

- 将允许由管理员运行的文件运行。
- 将允许 *运行不在用户* 可写入目录中的位置中的文件。
- 文件由受信任的 [签名人签名](#signer-requests)。
- 大多数由 Microsoft 签名的文件都将运行，但一些文件将被阻止以防止执行代码编译等高风险操作。

如果用户（而非管理员）已经将应用或脚本添加到设备 (即，它位于用户可写的目录) 中，我们不允许执行它。 如果管理员已允许应用或脚本，我们将允许执行。

我们的策略将停止在下列情况下执行应用：

- 如果用户被欺骗试图安装恶意软件。
- 如果用户运行的应用中存在漏洞，则尝试安装恶意软件。
- 如果用户有意尝试运行未经授权的应用或脚本。

### <a name="signer-requests"></a>签名者请求

通过提交签名者请求，通知我们你信任的软件发布者 *提供哪些应用*。 通过执行此操作，我们可以：

- 将此信任信息添加到基线应用程序控制策略中。
- 允许使用该发布者的证书签名的任何软件在设备上运行。

## <a name="audit-and-enforced-policies"></a>审核和强制策略

Microsoft 托管桌面使用Microsoft Intune策略提供应用控制：

### <a name="audit-policy"></a>审核策略

此策略创建日志以记录应用或脚本是否将被强制策略阻止。

审核策略不强制执行应用控制规则。 它们用于测试目的，以确定应用程序是否需要发布者豁免。 它会在事件 (中记录 8003 或 8006) 警告，而不是阻止执行或安装指定的应用或脚本。

### <a name="enforced-policy"></a>强制策略

此策略阻止不受信任的应用和脚本运行，并且只要应用或脚本被阻止，就会创建日志。 强制执行的策略会阻止标准用户执行存储在用户可写入目录中的应用或脚本。

测试组中设备应用了审核策略，以验证任何应用程序是否会导致问题。 "第一 (、快速"和"广泛") 使用强制策略。 这些组的用户将无法运行不受信任的应用或脚本。
