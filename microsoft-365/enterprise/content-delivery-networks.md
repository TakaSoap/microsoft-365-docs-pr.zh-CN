---
title: 内容分发网络
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/15/2020
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom: Adm_O365
search.appverid:
- MET150
- MOE150
- BCS160
ms.assetid: 0140f704-6614-49bb-aa6c-89b75dcd7f1f
description: 使用此信息可了解 Office 365 如何使用内容交付网络 (CDN) 以提高性能。
ms.openlocfilehash: 1a963d14df14e8644072a159e35c8590f953dae6
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50911092"
---
# <a name="content-delivery-networks-cdns"></a>内容分发网络 (CDN)

*本文适用于 Microsoft 365 企业版和 Office 365 企业版。*

CDN 有助于使 Office 365 对最终用户保持快速和可靠。 Office 365 等云服务使用 CDN 缓存距离请求它们更近的浏览器的静态资产，以加快下载速度并减少感知的最终用户延迟。 本主题中的信息将帮助您了解内容交付网络 (CDN) Office 365 如何使用它们。

## <a name="what-exactly-is-a-cdn"></a>什么是 CDN？

CDN 是按地理位置分布的网络，由数据中心中的代理和文件服务器组成，这些服务器由高速主干网连接。 CDN 用于减少网站或服务中一组指定文件和对象的延迟和加载时间。 CDN 可能有数千个终结点，用于为来自任何位置的传入请求提供最佳服务。

CDN 通常用于为网站或服务（如 javascript 文件、图标和图像）提供快速的通用内容下载，还可以提供对用户内容（如 SharePoint Online 文档库中的文件、流式媒体文件和自定义代码）的私有访问。

CDN 由大多数企业云服务使用。 Office 365 等云服务拥有数百万客户下载混合的专有内容 (如电子邮件) 和常规内容 (如图标) 一次。 将每个人都使用的图像（如图标）尽可能靠近用户计算机会更有效。 每个云服务构建 CDN 数据中心并不可行，这些数据中心将此类通用内容存储在每个都市区，甚至全球每个主要 Internet 中心，因此其中一些 CDN 是共享的。

## <a name="how-do-cdns-make-services-work-faster"></a>CDN 如何使服务更快地工作？

一次又一次地下载常见对象（如网站图像和图标）可能会占用网络带宽，网络带宽可以更好地用于下载重要的个人内容，如电子邮件或文档。 由于 Office 365 使用包含 CDN 的体系结构，因此可以从距离客户端计算机更近的服务器下载图标、脚本和其他常规内容，从而加快下载速度。 这意味着可以更快地访问存储在 Office 365 数据中心中的个人内容。

CDN 通过多种方式帮助提高云服务性能：

- CDN 将部分网络和文件下载负担从云服务中转移，通过减少为静态资产请求提供服务的需求，释放云服务资源，从而提供用户内容和其他服务。
- CDN 旨在通过实现高性能网络和文件服务器，以及利用更新的网络协议（如 [HTTP/2）](https://en.wikipedia.org/wiki/HTTP/2) 和高效压缩和请求多路复用来提供低延迟文件访问。
- CDN 网络使用许多全局分布式终结点，尽可能向用户提供内容。

## <a name="the-office-365-cdn"></a>The Office 365 CDN

内置的 Office 365 内容交付网络 (CDN) 允许 Office 365 管理员通过缓存距离请求它们的浏览器更近的静态资产，为组织的 SharePoint Online 页面提供更好的性能，这有助于加快下载速度并降低延迟。 Office 365 CDN 使用 [HTTP/2](https://en.wikipedia.org/wiki/HTTP/2) 协议来提高压缩和下载速度。

> [!NOTE]
> Office 365 CDN 仅适用于全球生产 (云中的) 租户。 美国政府、中国德国云中的租户当前不支持 Office 365 CDN。

Office 365 CDN 由多个 CDN 组成，用户可以在多个位置（即 _源_）托管静态资产，并从全局高速网络提供这些资产。 可以添加 **公共** 源、**私有** 源或同时添加这两种源，具体取决于想要托管在 Office 365 CDN 中的内容种类。

![Office 365 CDN 概念图](../media/O365-CDN/o365-cdn-flow-transparent.svg "Office 365 CDN 概念图")

Office 365 内的 **公共** 源中的内容可供匿名访问，并且任何具有托管资产 URL 的人员均可访问它。 由于对公共源中内容的访问属于匿名访问，因此只能使用它们缓存非敏感的常规内容，如 javascript 文件、脚本、图标和图片。 默认情况下，使用 Office 365 CDN 下载常规资源资产（如公共源中的 Office 365 客户端应用程序）。

 Office 365 CDN 中的专用源提供对用户内容（如 SharePoint Online 文档库、网站和专有图像）的专用访问权限。 使用动态生成的令牌保护为私有源中内容的访问提供保护，以便只有有权访问原始文档库或存储位置的用户才能访问它。 Office 365 CDN 中的私有源只能用于 SharePoint Online 内容，并且用户只能通过 SharePoint Online 租户重定向访问资产。

Office 365 CDN 服务被归入 SharePoint Online 订阅。

有关如何使用 Office 365 CDN 的详细信息，请参阅将 Office 365 内容交付网络与 [SharePoint Online 一同使用](use-microsoft-365-cdn-with-spo.md)。

若要观看提供有关使用 Office 365 CDN 的概念和 HOWTO 信息的一系列简短视频，请访问 SharePoint 开发人员模式和做法 [YouTube 频道](https://aka.ms/sppnp-videos)。

## <a name="other-microsoft-cdns"></a>其他 Microsoft CDN

虽然不是 Office 365 CDN 的一部分，但可以在 Office 365 租户中使用这些 CDN 来访问 Office 365 CDN 范围内 SharePoint 开发库、自定义代码和其他用途。

### <a name="azure-cdn"></a>Azure CDN

>[!NOTE]
>从 2020 年第 3 季度开始，SharePoint Online 将在 Azure CDN 上开始缓存视频，以支持改进的视频播放和可靠性。 热门视频将流式传输自距离用户最近的 CDN 终结点。 此数据将保留在 Microsoft 365 合规性边界内。 这是所有租户的免费服务，不需要任何客户操作进行配置。

可以使用 Azure **CDN** 部署自己的 CDN 实例，以托管自定义 Web 部件、库和其他资源资产，从而可以将访问密钥应用到 CDN 存储，并更好地控制 CDN 配置。 使用 Azure CDN 并非免费，需要 Azure 订阅。

若要详细了解如何配置 Azure CDN 实例，请参阅 [快速入门：将 Azure 存储帐户](/azure/cdn/cdn-create-a-storage-account-with-cdn)与 Azure CDN 集成。

有关如何使用 Azure CDN 托管 SharePoint Web 部件的示例，请参阅将 SharePoint 客户端[Web 部件部署到 Azure CDN。](/sharepoint/dev/spfx/web-parts/get-started/deploy-web-part-to-cdn)

有关 Azure CDN PowerShell 模块的信息，请参阅[使用 PowerShell 管理 Azure CDN。](/azure/cdn/cdn-manage-powershell)

### <a name="microsoft-ajax-cdn"></a>Microsoft Ajax CDN

Microsoft **的 Ajax CDN** 是一个只读 CDN，它提供许多受欢迎的开发库，包括 jQuery (及其所有其他库) 、ASP.NET Ajax、Bootstrap、Knockout.js 和其他库。
  
若要在项目中包括这些脚本，只需将对这些公开可用的库的任何引用替换为对 CDN 地址的引用，而不是将其包括在项目本身中。 例如，使用以下代码链接到 jQuery：

``` html
<script src=https://ajax.aspnetcdn.com/ajax/jquery-2.1.1.js> </script>
```

有关如何使用 Microsoft Ajax CDN 的详细信息，请参阅 [Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)。

## <a name="how-does-office-365-use-content-from-a-cdn"></a>Office 365 如何使用 CDN 中的内容？

无论你为 Office 365 租户配置了哪个 CDN，基本数据检索过程都是相同的。

1. 你的客户端 (浏览器或 Office 客户端应用程序) Office 365 请求数据。

2. Office 365 将数据直接返回到客户端，或者，如果数据是 CDN 托管的一组内容的一部分，则将您的客户端重定向到 CDN URL。

    a. 如果数据已缓存在公用 _源中，_ 则客户端会直接从最近的 CDN 位置将数据下载到客户端。

    b. 如果数据已缓存在专用 _源中_ ，CDN 服务将检查 Office 365 用户帐户对源的权限。 如果您具有权限，SharePoint Online 将动态生成由 CDN 中的资产路径和两个访问令牌组成的自定义 URL，并返回客户端的自定义 URL。 然后，你的客户端使用自定义 URL 直接从最近的 CDN 位置将数据下载到你的客户端。

3. 如果数据未缓存在 CDN 上，CDN 节点会从 Office 365 请求数据，然后在客户端下载数据后缓存一段时间的数据。

CDN 会指出距离用户浏览器最近的数据中心，然后使用重定向从该数据中心下载请求的数据。 CDN 重定向速度很快，可节省用户大量下载时间。

## <a name="how-should-i-set-up-my-network-so-that-cdns-work-best-with-office-365"></a>如何设置我的网络，以便 CDN 最符合 Office 365？

最大程度地减少网络客户端和 CDN 终结点之间的延迟是确保最佳性能的关键考虑因素。 您可以使用管理 [Office 365](managing-office-365-endpoints.md) 终结点中概述的最佳实践，以确保网络配置允许客户端浏览器直接访问 CDN，而不是通过中央代理路由 CDN 流量，以避免引入不必要的延迟。

还可以阅读 [Office 365](./microsoft-365-network-connectivity-principles.md) 网络连接原则，了解优化 Office 365 网络性能背后的概念。

## <a name="is-there-a-list-of-all-the-cdns-that-office-365-uses"></a>是否有 Office 365 使用的所有 CDN 的列表？

Office 365 使用的 CDN 始终会发生变化，并且在许多情况下，如果一个 CDN 不可用，则配置了多个 CDN 合作伙伴。 Office 365 使用的主要 CDN 为：

|CDN  |Company  |用法  |链接  |
|---------|---------|---------|---------|
|Office 365 CDN     |Akamai         |公共源中的常规资产、私有源中的 SharePoint 用户内容         |[结合使用 Office 365 内容传送网络和 SharePoint Online](use-microsoft-365-cdn-with-spo.md)         |
|Azure CDN     |Microsoft         |自定义代码、SharePoint 框架解决方案         |[Microsoft Azure CDN](https://azure.microsoft.com/documentation/services/cdn/)         |
|Microsoft Ajax CDN (只读)      |Microsoft         |Ajax、jQuery、ASP.NET、Bootstrap、Knockout.js库。         |[Microsoft Ajax CDN](/aspnet/ajax/cdn/overview)         |

## <a name="what-performance-gains-does-a-cdn-provide"></a>CDN 提供哪些性能提升？

衡量直接从 Office 365 下载的数据与从特定 CDN 下载的数据之间的特定性能差异涉及许多因素，例如相对于租户的位置和最近的 CDN 终结点、CDN 在页面上提供的资产数量，以及网络延迟和带宽的暂时性变化。 但是，简单的 A/B 测试有助于显示特定文件的下载时间差异。

以下屏幕截图说明了 Office 365 中的本机文件位置与 [Microsoft Ajax](/aspnet/ajax/cdn/overview)内容交付网络上托管的相同文件之间的下载速度差异。 这些屏幕截图来自 11 开发人员工具Internet Explorer中的"网络"选项卡。  这些屏幕截图显示了热门库 jQuery 上的延迟。 若要显示此屏幕，Internet Explorer按 **F12** 并选择"网络"选项卡，该选项卡上标有Wi-Fi图标。
  
![F12 网络的屏幕截图](../media/930541fd-af9b-434a-ae18-7bda867be128.png)
  
此屏幕截图显示上载到 SharePoint Online 网站本身的母版页样式库的库。 上载库所花时间是 1.51 秒。
  
![加载时间为 1.51 秒的屏幕截图](../media/64225c79-fa53-480f-81cd-0d351674320e.png)
  
第二个屏幕截图显示了 Microsoft CDN 提供的相同文件。 这一次延迟约为 496 毫秒。 这是一项较大的改进，表明下载对象的总时间将持续一秒钟。
  
![加载时间为 469 毫秒的屏幕截图](../media/6a553cc3-25a0-42c1-aae7-4aebbc2eb4c3.png)

## <a name="is-my-data-safe"></a>我的数据是否安全？

我们非常小心保护运行你的业务的数据。 存储在 Office 365 CDN 中的数据在传输中和在其余时间都进行加密，并且 Office 365 SharePoint CDN 中数据的访问权限受 Office 365 用户权限和令牌授权保护。 对于 Office 365 SharePoint CDN 中数据的请求，必须 (从 Office 365 租户) 重定向至 office 365，否则不会生成授权令牌。

若要确保数据保持安全，建议不要将用户内容或其他敏感数据存储在公用 CDN 中。 由于对公用 CDN 中数据的访问是匿名的，因此公共 CDN 只能用于托管常规内容，如 Web 脚本文件、图标、图像和其他非敏感资产。

> [!NOTE]
> 第三方 CDN 提供商的隐私和合规性标准可能与 Office 365 信任中心概述的承诺不同。 通过 CDN 服务缓存的数据可能不符合 Microsoft 数据处理条款 (DPT) ，并且可能超出 Office 365 信任中心合规性边界。

有关 Office 365 CDN 提供程序的隐私和数据保护的详细信息，请访问以下内容：  

- 在 Microsoft 信任中心了解有关 Office 365 隐私和 [数据保护的信息](https://www.microsoft.com/trustcenter)
- 在 Akamai 隐私信任中心了解有关[Akamai](https://www.akamai.com/us/en/about/compliance/data-protection-at-akamai.jsp)隐私和数据保护的信息
- 在 Azure 信任中心了解有关 Azure 隐私和数据保护 [的信息](https://azure.microsoft.com/overview/trusted-cloud/)

## <a name="how-can-i-secure-my-network-with-all-these-3rd-party-services"></a>如何使用所有这些第三方服务保护网络？

利用一组广泛的合作伙伴服务，Office 365 可以扩展并满足可用性要求，并增强使用 Office 365 时用户体验。 Office 365 利用的第三方服务包括证书吊销列表;例如 crl.microsoft.com 或 sa.symcb.com CDN;例如 r3.res.outlook.com。 Office 365 生成的每个 CDN FQDN 都是 Office 365 的自定义 FQDN。 如果根据 Office 365 的请求发送到 FQDN，则你可以确保 CDN 提供程序控制该位置的 FQDN 和基础内容。
  
对于想要将发往 Microsoft 或 Office 365 数据中心的请求与发往第三方的请求隔离开的客户，我们已编写关于管理 [Office 365](https://support.office.com/article/99cab9d4-ef59-4207-9f2b-3728eb46bf9a)终结点的指南。

## <a name="is-there-a-list-of-all-the-fqdns-that-leverage-cdns"></a>是否有利用 CDN 的所有 FQ CDN 的列表？

FQDN 列表及其利用 CDN 如何随着时间的推移而更改。 请参阅已发布的 [Office 365 URL](./urls-and-ip-address-ranges.md) 和 IP 地址范围页面，了解使用 CDN 的最新 FQN。

您还可以使用 Office [365 IP 地址](microsoft-365-ip-web-service.md) 和 URL Web 服务请求当前 Office 365 URL 和格式设置为 CSV 或 JSON 的 IP 地址范围。

## <a name="can-i-use-my-own-cdn-and-cache-content-on-my-local-network"></a>我可以使用自己的 CDN 并在本地网络上缓存内容吗？

我们一直在寻找新方法来支持客户的需求，目前正在探索缓存代理解决方案和其他本地 CDN 解决方案的使用。

虽然这不是 Office 365 CDN 的一部分，但您也可以使用 **Azure CDN** 托管自定义 Web 部件、库和其他资源资产，从而允许你将访问密钥应用到 CDN 存储，并更好地控制 CDN 配置。 使用 Azure CDN 并非免费，需要 Azure 订阅。 若要详细了解如何配置 Azure CDN 实例，请参阅 [快速入门：将 Azure 存储帐户](/azure/cdn/cdn-create-a-storage-account-with-cdn)与 Azure CDN 集成。

## <a name="im-using-azure-expressroute-for-office-365-does-that-change-things"></a>我在使用适用于 Office 365 的 Azure ExpressRoute，这是否更改了情况？

[Azure ExpressRoute for Office 365](azure-expressroute.md) 提供与 Office 365 基础结构的专用连接，该连接与公共 Internet 隔离。 这意味着客户端仍然需要通过非 ExpressRoute 连接进行连接，以连接到未明确包含在 ExpressRoute 支持的服务列表中的 CDN 和其他 Microsoft 基础结构。 若要详细了解如何路由特定流量，例如发往 CDN 的请求，请参阅 [Office 365 网络流量管理](routing-with-expressroute.md)。

## <a name="can-i-use-cdns-with-sharepoint-server-on-premises"></a>能否将 CDN 与本地 SharePoint Server 一同使用？

仅在 SharePoint Online 上下文中使用 CDN 才有意义，应避免使用 SharePoint Server。 这是因为，如果服务器位于本地或地理位置靠近，那么地理位置的所有优势都不存在。 此外，如果与托管它的服务器存在网络连接，则无需 Internet 连接即可使用站点，因此无法检索 CDN 文件。 否则，如果你的网站所需的库和文件有一个可用且稳定的 CDN，你应该使用 CDN。
  
以下是可以用于返回的简短链接：[https://aka.ms/o365cdns]()
  
## <a name="see-also"></a>另请参阅

[Office 365 网络连接原则](./microsoft-365-network-connectivity-principles.md)

[评估 Office 365 网络连接](assessing-network-connectivity.md)

[管理 Office 365 终结点](managing-office-365-endpoints.md)

[Office 365 URL 和 IP 地址范围](./urls-and-ip-address-ranges.md)

[结合使用 Office 365 内容传送网络和 SharePoint Online](use-microsoft-365-cdn-with-spo.md)

[Microsoft 信任中心](https://www.microsoft.com/trustcenter)

[优化 Office 365 性能](tune-microsoft-365-performance.md)