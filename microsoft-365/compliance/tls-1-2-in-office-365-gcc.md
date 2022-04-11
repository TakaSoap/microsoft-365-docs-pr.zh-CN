---
title: 在 Microsoft 365 GCC High 和 DoD 中禁用 TLS 1.0 和 1.1
description: 讨论 Microsoft 如何在 Microsoft 365 的 GCC High 和 DoD 环境中禁用对 TLS 1.1 和 1.0 的支持。
author: kccross
manager: laurawi
ms.localizationpriority: medium
search.appverid:
- MET150
audience: ITPro
ms.collection: M365-security-compliance
ms.service: information-protection
ms.topic: article
ms.reviewer: krowley
ms.author: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: bad0dc997f2c564670858d2ac35b2cd3177e0578
ms.sourcegitcommit: 9ba00298cfa9ae293e4a57650965fdb3e8ffe07b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/11/2022
ms.locfileid: "64760374"
---
# <a name="disabling-tls-10-and-11-in-microsoft-365-gcc-high-and-dod"></a>在 Microsoft 365 GCC High 和 DoD 中禁用 TLS 1.0 和 1.1

## <a name="summary"></a>摘要

为了遵守联邦风险和授权管理计划 (FedRAMP) 的最新符合性标准，我们将针对GCC高和 DoD 环境禁用传输层安全 (TLS Microsoft 365) 版本 1.1 和 1.0。 此前，在准备在Office 365[强制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365) 时，Microsoft 支持部门宣布了这一更改。

数据的安全性非常重要，我们致力于对可能会影响服务使用情况的更改保持透明度。

尽管 [Microsoft TLS 1.0 实现](https://support.microsoft.com/help/3117336) 没有已知的安全漏洞，但我们仍然致力于 FedRAMP 符合性标准。 因此，我们于 2020 年 1 月 15 日在 GCC High 和 DoD 环境中禁用了 Microsoft 365 中的 TLS 1.1 和 1.0。 有关如何删除 TLS 1.1 和 1.0 依赖项的信息，请参阅以下白皮书：

[解决 TLS 1.0 问题](https://www.microsoft.com/download/details.aspx?id=55266)

## <a name="more-information"></a>更多信息

从 2020 年 1 月 15 日开始，GCC高和 DoD 环境中Microsoft 365将禁用 TLS 1.1 和 1.0。

到 2020 年 1 月 15 日，客户端服务器和浏览器服务器的所有组合都应使用 TLS 版本 1.2 (或更高版本) ，以确保可以建立所有连接，而无需Microsoft 365。 这可能需要更新客户端服务器和浏览器服务器的某些组合。

对于SharePoint和OneDrive，需要更新和配置 .NET 以支持 TLS 1.2。 有关信息，请参阅 [如何在客户端上启用 TLS 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。

必须更新客户端计算机，以确保保持对 Office 365 GCC High 和 DoD 的不间断访问。

需要更新通过 TLS 1.0 或 TLS 1.1 调用Microsoft 365 API 的应用程序，以使用 TLS 1.2。 .NET 4.5 默认为 TLS 1.1。 若要更新 .NET 配置，请参阅 [如何在客户端上启用传输层安全 (TLS) 1.2](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)。 有关详细信息，请参阅[准备在 Office 365 中强制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。

我们知道以下客户端应用程序不能使用 TLS 1.2：

- Android 4.3 和更低的版本
- Firefox 版本 5.0 及更低版本
- Windows 7 上的 Internet Explorer 8-10 及更早版本
- Windows Phone 8.0 上的 Internet Explorer 10
- Safari 6.0.4/OS X 10.8.4 及更早版本

尽管当前对 Microsoft Online 服务连接的分析显示，大多数服务和终结点很少看到 TLS 1.1 和 1.0 使用情况，但我们将通知此更改，以便你可以在支持 TLS 1.1 和 1.0 之前根据需要更新任何受影响的客户端或服务器。 如果将任何本地基础结构用于混合方案或Active Directory 联合身份验证服务 (AD FS) ，请确保基础结构可以支持使用 TLS 1.2 (或更高版本) 的入站和出站连接。

除了使用无法使用 TLS 1.2 的列出客户端时可能会遇到的中断之外，删除 TLS 1.1 和 1.0 将阻止你使用以下 Microsoft 产品：

- Lync 手机

## <a name="references"></a>References

有关帮助确保客户端使用 TLS 1.2 的指导和参考，请参阅[准备在 Office 365 中强制使用 TLS 1.2](https://support.microsoft.com/help/4057306/preparing-for-tls-1-2-in-office-365)。
