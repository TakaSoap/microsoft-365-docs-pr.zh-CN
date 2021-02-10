---
title: 在 Office 365 GCC High 和 DoD 中禁用 TLS 1.0 和 1.1
description: 讨论 Microsoft 如何在 Microsoft 365 的 GCC High 和 DoD 环境中禁用对 TLS 1.1 和 1.0 的支持。
author: workshay
manager: laurawi
localization_priority: Normal
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: shmehta
appliesto:
- Office 365 Business
ms.openlocfilehash: 006f81ee5b17baca4f42a78c5a87a59e8e90648f
ms.sourcegitcommit: a1846b1ee2e4fa397e39c1271c997fc4cf6d5619
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/09/2021
ms.locfileid: "50166437"
---
# <a name="disabling-tls-10-and-11-in-office-365-gcc-high-and-dod"></a>在 Office 365 GCC High 和 DoD 中禁用 TLS 1.0 和 1.1

## <a name="summary"></a>摘要

为了符合联邦风险和授权管理计划 (FedRAMP) 的最新合规性标准，我们针对 GCC High 和 DoD 环境在 Microsoft 365 中禁用传输层安全性 (TLS) 版本 1.1 和 1.0。 此更改之前是通过 Microsoft 支持部门在准备在 Office 365 中强制使用 [TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)而宣布的。

数据的安全性非常重要，我们承诺实现可能影响服务使用的更改的透明度。

尽管 [Microsoft TLS 1.0](https://support.microsoft.com/help/3117336) 实现没有已知的安全漏洞，但我们仍致力于遵守 FedRAMP 合规性标准。 因此，我们在 2020 年 1 月 15 日禁用了 GCC High 和 DoD 环境中 Office 365 中的 TLS 1.1 和 1.0。 若要了解如何删除 TLS 1.1 和 1.0 依赖项，请参阅以下白皮书：

[解决 TLS 1.0 问题](https://www.microsoft.com/download/details.aspx?id=55266)

必须改为使用 TLS 版本 1.2。 有关详细信息，请参阅准备在 Office 365 中强制使用[TLS 1.2。](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)

对于 SharePoint 和 OneDrive，需要更新和配置 .NET 以支持 TLS 1.2。 有关信息，请参阅[如何在客户端上启用 TLS 1.2。](https://docs.microsoft.com/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

## <a name="more-information"></a>详细信息

从 2020 年 1 月 15 日开始，GCC High 和 DoD 环境中 Office 365 将弃用 TLS 1.1 和 1.0。

到 2020 年 1 月 15 日，客户端服务器和浏览器服务器的所有组合都应使用 TLS 版本 1.2 (或更高版本) 以确保可以建立所有连接，而不会与 Office 365 服务发生问题。 这可能需要更新客户端服务器和浏览器服务器的某些组合。

如果在 2020 年 1 月 15 日之前未更新到 TLS 版本 1.2 (或更高版本) ，则尝试连接到 Office 365 时将遇到问题。 此外，在解决方案中，你 (更新到 TLS 1.2) 或更高版本。

我们知道以下客户端无法使用 TLS 1.2：

- Android 4.3 和更低的版本
- Firefox 版本 5.0 及更低版本
- Internet Explorer 8 Windows 7 和早期版本上的 Internet Explorer 8–10
- Internet Explorer 10 Windows Phone 8.0 上
- Safari 6.0.4/OS X 10.8.4 及更早版本

我们建议您更新客户端，以确保保持对 Office 365 GCC High 和 DoD 的不间断访问。

虽然当前对 Microsoft Online 服务连接的分析显示，大多数服务和终结点很少看到 TLS 1.1 和 1.0 用法，但我们提供了此更改的通知，以便你可以在必要时更新任何受影响的客户端或服务器，然后再结束对 TLS 1.1 和 1.0 的支持。 如果要将任何本地基础结构用于混合方案或 Active Directory 联合身份验证服务 (AD FS) ，请确保该基础结构可以支持使用 TLS 1.2 (或更高版本) 的入站和出站连接。

除了使用无法使用 TLS 1.2 的列出的客户端时可能会遇到的中断之外，删除 TLS 1.1 和 1.0 将阻止你使用以下 Microsoft 产品：

- Lync 电话

## <a name="references"></a>参考

以下支持文章介绍了可帮助确保您的客户端使用 TLS 1.2 的指南和参考：

[准备在 Office 365 中强制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)
