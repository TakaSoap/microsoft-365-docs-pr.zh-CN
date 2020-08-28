---
title: 应用程序控制
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
manager: laurawi
audience: ITpro
ms.topic: article
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 32ed3f95ebb4299796c5ad3eb71802c949701b65
ms.sourcegitcommit: abf63669daf12993ad3353e4b578f41c8910b20f
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/27/2020
ms.locfileid: "47289123"
---
# <a name="app-control"></a>应用程序控制

应用程序控制是 Microsoft 托管桌面中的一种可选安全实践，用于限制客户端设备上的代码的执行。 此控件通过要求只有经客户核准的发布者签名的代码才能运行，从而缓解恶意软件或恶意脚本的风险。 此控制提供了很多安全优势，但它主要旨在保护基于客户端的攻击的数据和身份。

Microsoft 托管桌面通过创建启用核心生产力方案的基本策略简化了应用程序控制策略的管理。 您可以将信任扩展到特定于环境中的应用程序和脚本的其他签名人。 


任何安全技术都需要在用户体验、安全性和成本之间实现平衡。 应用程序控制可降低环境中恶意软件的威胁，但对用户和 IT 管理员的其他操作会产生后果。

**其他安全性：**

阻止应用程序控制策略所信任的应用程序或脚本无法在设备上运行。

**您的额外职责：**

- 您负责测试您的应用程序，以确定应用程序控件策略是否会阻止这些应用程序。
- 如果某个应用程序 (或将被) 阻止，您将负责标识所需的签名者详细信息，并通过管理门户请求更改。

**Microsoft 托管桌面职责：**

- Microsoft 托管桌面维护允许核心 Microsoft 产品（如 M365 应用程序、Windows、团队、OneDrive 等）的基本策略。
- Microsoft 托管桌面插入你的受信任签署人，并将更新的策略部署到你的设备。


## <a name="managing-trust-in-applications"></a>在应用程序中管理信任

Microsoft 托管桌面 curates 信任 Microsoft 技术的核心组件的基本策略。 然后，通过通知 Microsoft 托管桌面的已信任您自己的应用程序和脚本来 *添加* 信任。

### <a name="base-policy"></a>基本策略

Microsoft 托管桌面，与 Microsoft cybersecurity 专家协作，创建并维护一个标准策略，该策略允许在阻止代码编译或执行不受信任文件等危险活动时，通过 Microsoft Intune 部署大多数应用。

基本策略采用以下方法来限制软件执行：

- 管理员运行的文件将被允许运行。
- 将允许运行 *不* 在用户可写目录中的位置中的文件。
- 文件由 [受信任的签名人](#signer-requests)签署。
- Microsoft 签名的大多数文件都将运行，但某些文件会被阻止，以防止高风险操作（如代码编译）。


如果管理员之外的用户可能已将应用程序或脚本添加到设备 (也就是说，它位于用户可写入的目录) 中，我们将不允许它执行，除非管理员已明确允许它执行。 如果用户被欺骗尝试安装恶意软件，如果用户运行的应用程序中的某个漏洞尝试安装恶意软件，或者如果用户有意尝试运行未授权的应用程序或脚本，则策略将停止执行。

### <a name="signer-requests"></a>签名者请求

你将告知我们通过存档 *签名者请求*而信任的软件供应商提供的应用程序。 通过执行此操作，我们将此信任信息添加到基准应用程序控制策略中，并允许使用该发布者的证书签名的任何软件在您的设备上运行。

## <a name="audit-and-enforced-policies"></a>审核和强制实施策略

Microsoft 托管桌面使用两个 Microsoft Intune 策略来提供应用程序控制：

### <a name="audit-policy"></a>审核策略
此策略将创建日志，以记录强制策略是否会阻止应用程序或脚本。 审核策略不会强制实施应用程序控制规则，并用于测试目的，以确定应用程序是否需要发布服务器例外。 它会在事件查看器中记录警告 (8003 或8006事件) ，而不是阻止执行或安装指定的应用程序或脚本。

### <a name="enforced-policy"></a>强制策略
此策略阻止不受信任的应用程序和脚本运行，并在应用程序或脚本被阻止时创建日志。 强制策略阻止标准用户执行存储在用户可写目录中的应用程序或脚本。

测试组中的设备已应用审核策略，以便您可以使用它们来验证是否有任何应用程序将导致问题。 所有其他组 (的第一个、快速和广泛的) 使用强制性策略，因此这些组中的用户将无法运行不受信任的应用程序或脚本。







