---
title: 在 Office 365 和 Office 365 GCC 中准备 TLS 1.2
description: 在停止对 TLS 1.0 和 1.1 的支持后，如何让 Office 365 和 Office 365 GCC 中的所有客户端-服务器和浏览器-服务器组合准备好使用 TLS 1.2。
author: kccross
manager: laurawi
ms.localizationpriority: medium
search.appverid:
- MET150
audience: ITPro
ms.service: O365-seccomp
ms.topic: article
ms.author: shmehta
ms.reviewer: krowley
appliesto:
- Office 365 Business
ms.openlocfilehash: 2ae758ef9e5c36b2406527e2a10c43f57986ea1f
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60159750"
---
# <a name="preparing-for-tls-12-in-office-365-and-office-365-gcc"></a>在 Office 365 和 Office 365 GCC 中准备 TLS 1.2

## <a name="summary"></a>摘要

为了向我们的客户提供一流的加密，Microsoft 计划在 Office 365 和 Office 365 GCC 中弃用传输层安全 (TLS) 版本 1.0 和 1.1。 我们知道您的数据的安全性非常重要，并且我们承诺对可能影响使用 TLS 服务的更改保持透明公开。

[Microsoft TLS 1.0 实现](https://support.microsoft.com/help/3117336/schannel-implementation-of-tls-1-0-in-windows-security-status-update-n)没有已知安全漏洞。 但是，由于未来的潜在协议降级攻击和其他 TLS 漏洞，我们将停止在 Microsoft Office 365 和 Office 365 GCC 中提供 TLS 1.0 和 1.1 支持。

有关如何删除 TLS 1.0 和 1.1 依赖项的信息，请参阅以下白皮书：[解决 TLS 1.0 问题](https://www.microsoft.com/download/details.aspx?id=55266)。

升级到 TLS 1.2 后，请确保 Azure Front Door 支持你使用加密套件。 Microsoft 365 Azure 前端在加密套件支持方面稍有不同。 有关详细信息，请参阅 Azure Front Door 支持的当前密码套件[是什么？。](/azure/frontdoor/front-door-faq#what-are-the-current-cipher-suites-supported-by-azure-front-door-)

## <a name="more-information"></a>更多信息

自 2020 年 1 月起，我们已经开始弃用 TLS 1.0 和 1.1。 不支持通过 TLS 1.0 或 1.1 在我们的 DoD 或 GCC High 实例中连接到 Office 365 的任何客户端、设备或服务。 对于 Office 365 商业客户，TLS 1.0 和 1.1 的弃用将于 2020 年 10 月 15 日开始，并持续数周和数月推出。

我们建议所有客户端-服务器和浏览器-服务器组合使用 TLS1.2（或更高版本）以保持与 Office 365 服务的连接。 你可能必须更新某些客户端-服务器和浏览器-服务器组合。

  > [!NOTE]
  > 对于 SMTP 入站邮件流，在 TLS 1.0 和 1.1 弃用后，我们将仅接受 TLS 1.2 连接。 但是，我们将继续接受未加密的 SMTP 连接，该连接没有任何 TLS。 尽管我们不建议在没有任何加密的情况下进行电子邮件传输。 

你需要更新通过 TLS 1.0 或 TLS 1.1 调用 Microsoft 365 API 的应用程序，以使用 TLS 1.2。 .NET 4.5 默认为 TLS 1.1。 若要更新 .NET 配置，请参阅如何在客户端上启用[TLS (TLS) 1.2。](/mem/configmgr/core/plan-design/security/enable-tls-1-2-client)

以下是已知的无法使用 TLS 1.2 的客户端。 更新这些客户端以确保对服务的访问不会间断。

- Android 4.3 和更低的版本
- Firefox 版本 5.0 及更低版本
- Windows 7 上的 Internet Explorer 8-10 及更早版本
- Windows Phone 8 上的 Internet Explorer 10
- Safari 6.0.4/OS X10.8.4 及更早版本

### <a name="tls-12-for-microsoft-teams-rooms-and-surface-hub"></a>适用于 Microsoft Teams Rooms 和 Surface Hub 的 TLS 1.2

自 2018 年 12 月以来，Microsoft Teams Room（以前称为 Skype Room System V2 SRS V2）就一直支持 TLS 1.2。 我们建议 Room 设备安装 Microsoft Teams Rooms 应用版本 4.0.64.0 或更高版本。 有关更多信息，请参阅[发行说明](/microsoftteams/room-systems/srs2-release-note)。 更改是向后和向前兼容的。

2019 年 5 月，Surface Hub 发布了 TLS 1.2 支持。

对 Microsoft Teams Rooms 和 Surface Hub 产品的 TLS 1.2 支持还要求更改以下服务器端代码：

- Skype for Business Online 服务器更改已于 2019 年 4 月上线。 现在，Skype for Business Online 支持使用 TLS 1.2 连接 Microsoft Teams Room 和 Surface Hub 设备。
- Skype for Business Server 客户必须安装累积更新 (CU) 才能对 Teams Rooms Systems 和 Surface Hub 使用 TLS 1.2。

  - 对于 Skype for Business Server 2015，CU9 已于 2019 年 5 月发布。
  - 对于 Skype for Business Server 2019，CU1 先前计划于 2019 年 4 月发布，但推迟到 2019 年 6 月。

  > [!NOTE]
  > 在为 Skype for Business Server 安装特定的 CU 之前，Skype for Business 本地客户不应禁用 TLS 1.0 / 1.1。

如果您正在使用混合式场景的本地基础架构或 Active Directory 联合身份验证服务，确保该基础架构同时支持使用 TLS 1.2 的进站和出站连接。

## <a name="references"></a>参考

以下资源提供帮助确保客户端正在使用 TLS 1.2 或更高版本及禁用 TLS 1.0 和 1.1 的指导。

- 对于连接到 Office 365 的 Windows 7 客户端，请确保 TLS 1.2 是 Windows WinHTTP 中的默认安全协议。 有关更多信息，请参阅 [KB 3140245 - 更新以在 Windows 的 WinHTTP 中启用 TLS 1.1 和 TLS 1.2 作为默认安全协议](https://support.microsoft.com/help/3140245/update-to-enable-tls-1-1-and-tls-1-2-as-a-default-secure-protocols-in)。
- [受 TLS 密码套件支持Office 365](/microsoft-365/compliance/technical-reference-details-about-encryption#tls-cipher-suites-supported-by-office-365)
- 要通过删除 TLS 1.0 和 1.1 依赖项解决 TLS 使用弱点问题，请参阅 [Microsoft TLS 1.2 支持](https://cloudblogs.microsoft.com/microsoftsecure/2017/06/20/tls-1-2-support-at-microsoft/)。
- [新的 IIS 功能](https://cloudblogs.microsoft.com/microsoftsecure/2017/09/07/new-iis-functionality-to-help-identify-weak-tls-usage/)可更加方便地在 [Windows Server 2012 R2](https://support.microsoft.com/help/4025335/windows-8-1-windows-server-2012-r2-update-kb4025335) 和 [Windows Server 2016](https://support.microsoft.com/help/4025334/windows-10-update-kb4025334) 上查找通过使用弱安全协议连接服务的客户端。
- 获取有关如何解决 [TLS 1.0 问题的信息](https://www.microsoft.com/download/details.aspx?id=55266)。
- 有关安全性方法的一般信息，请转到[Office 365 信任中心](https://www.microsoft.com/trustcenter/cloudservices/office365)。
- 若要标识 SMTP 客户端使用的 TLS 版本，请参阅安全与合规中心中的 [SMTP 身份验证客户端&报告](../security/office-365-security/mfi-smtp-auth-clients-report.md)。
- [准备 TLS 1.0/1.1 弃用 - Office 365 Skype for Business](https://techcommunity.microsoft.com/t5/Skype-for-Business-Blog/Preparing-for-TLS-1-0-1-1-Deprecation-O365-Skype-for-Business/ba-p/222247)
- [Exchange Server TLS 指南，第 1 部分：为 TLS 1.2 做好准备](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-1-getting-ready-for-tls-1-2/ba-p/607649)
- [Exchange Server TLS 指南，第 2 部分：启用 TLS 1.2 并识别不使用它的客户端](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-2-enabling-tls-1-2-and/ba-p/607761)
- [Exchange Server TLS 指南，第 3 部分：关闭 TLS 1.0/1.1](https://techcommunity.microsoft.com/t5/exchange-team-blog/exchange-server-tls-guidance-part-3-turning-off-tls-1-0-1-1/ba-p/607898)
- [在 Office Online Server 中启用 TLS 1.1 和 TLS 1.2 支持](/officeonlineserver/enable-tls-1-1-and-tls-1-2-support-in-office-online-server)
