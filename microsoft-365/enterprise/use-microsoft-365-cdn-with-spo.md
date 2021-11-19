---
title: 将 Office 365 内容分发网络 (CDN) 与 SharePoint Online 一同使用
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 07/13/2021
audience: ITPro
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- Ent_O365
- SPO_Content
f1.keywords:
- CSH
ms.custom:
- Adm_O365
- seo-marvel-apr2020
search.appverid:
- MET150
- SPO160
ms.assetid: bebb285f-1d54-4f79-90a5-94985afc6af8
description: 了解如何使用 Office 365 内容分发网络 (CDN) 来加快你的 SharePoint Online 资产的交付。
ms.openlocfilehash: ad4eb1df63e201e49ba0b4c56c9123a04e37c184
ms.sourcegitcommit: 1ef176c79a0e6dbb51834fe30807409d4e94847c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/19/2021
ms.locfileid: "61110159"
---
# <a name="use-the-office-365-content-delivery-network-cdn-with-sharepoint-online"></a>结合使用 Office 365 内容分发网络和 SharePoint Online

可以使用内置的 Office 365 内容分发网络 (CDN) 来托管静态资产，以便提高 SharePoint Online 页面的性能。 Office 365 CDN 将静态资产缓存到距离请求这些资产的浏览器更近的位置，这样可以加快下载速度并减少延迟，进而提高性能。 此外，Office 365 CDN[使用 HTTP/2](https://en.wikipedia.org/wiki/HTTP/2)协议改进压缩和 HTTP 管道传输。 Office 365 CDN 服务被归入 SharePoint Online 订阅。

> [!NOTE]
> 此Office 365 CDN仅适用于全球生产 (云中的) 租户。  美国政府、中国德国云中的租户当前不支持Office 365 CDN。

Office 365 CDN 由多个 CDN 组成，用户可以在多个位置（即 _源_）托管静态资产，并从全局高速网络提供这些资产。 可以添加 **公共** 源、**私有** 源或同时添加这两种源，具体取决于想要托管在 Office 365 CDN 中的内容种类。 有关 [公用源和专用](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate) 源之间区别的信息，请参阅选择每个源是公共源还是私有源。

![Office 365 CDN概念图。](../media/O365-CDN/o365-cdn-flow-transparent.png "Office 365 CDN概念图")

如果你已熟悉 CDN 的运行方式，则只需完成几个步骤，为租户Office 365 CDN启用 CDN。 本主题介绍如何。 请继续阅读，了解如何开始托管静态资产。

> [!TIP]
> 还有一些 Microsoft 托管的 CDN 可以与 Office 365 一起用于专用使用方案，但是本主题中未讨论这些 CDN，因为它们不在 Office 365 CDN 范围内。 有关详细信息，请参阅其他[Microsoft CDN。](content-delivery-networks.md#other-microsoft-cdns)

 **返回到适用于网络 [的网络规划和性能Office 365。](./network-planning-and-performance.md)**

## <a name="overview-of-working-with-the-office-365-cdn-in-sharepoint-online"></a>在 Office 365 CDN Online SharePoint概述

若要为Office 365 CDN设置服务，请按照以下基本步骤操作：

+ [规划部署Office 365 CDN](use-microsoft-365-cdn-with-spo.md#plan-for-deployment-of-the-office-365-cdn)

  + [确定要托管在应用程序上的静态](use-microsoft-365-cdn-with-spo.md#CDNAssets)CDN。
  + [确定要存储资产的位置](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)。 此位置可以是网站SharePoint库或文件夹，_称为源_。
  + [选择每个源应为公共源还是私有源](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)。 你可以添加公共和私有类型的多个源。

+ 使用 PowerShell 或 CDN Online CLI 设置和配置SharePoint客户端

  + [使用 CDN Online 命令行管理程序设置SharePoint配置命令行管理程序](use-microsoft-365-cdn-with-spo.md#CDNSetupinPShell)
  + [使用 PnP PowerShell CDN和配置应用程序](use-microsoft-365-cdn-with-spo.md#CDNSetupinPnPPosh)
  + [使用 CDN CLI 设置和配置Office 365](use-microsoft-365-cdn-with-spo.md#CDNSetupinCLI)

  完成此步骤后，您将具有：

  + 为CDN启用策略。
  + 添加了源，将每个源标识为公用或私有。

完成设置后，可以通过以下方式[Office 365 CDN管理安装程序](use-microsoft-365-cdn-with-spo.md#CDNManage)：

+ 添加、更新和删除资源
+ 添加和删除源
+ 配置CDN策略
+ 如有必要，禁用CDN

最后，[请参阅使用CDN资源](use-microsoft-365-cdn-with-spo.md#using-your-cdn-assets)，了解如何从公用源CDN源访问你的资产。

请参阅[Troubleshooting the Office 365 CDN](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting) for guidance on resolving common issues。

## <a name="plan-for-deployment-of-the-office-365-cdn"></a>规划部署Office 365 CDN

在部署 Office 365 CDN 租户Office 365，在规划过程中应考虑以下因素。

  + [确定要托管在主机上的静态CDN](use-microsoft-365-cdn-with-spo.md#CDNAssets)
  + [确定要存储资产的位置](use-microsoft-365-cdn-with-spo.md#CDNStoreAssets)
  + [选择每个源应为公共源还是专用源](use-microsoft-365-cdn-with-spo.md#CDNOriginChoosePublicPrivate)

<a name="CDNAssets"> </a>
### <a name="determine-which-static-assets-you-want-to-host-on-the-cdn"></a>确定要托管在应用程序上的静态CDN

通常，CDN 最适用于托管静态 _资产_ 或不经常更改的资产。 一个很好的经验法则是标识满足以下部分或所有条件的文件：

+ 嵌入页面的静态文件 (脚本和图像) 对页面加载时间有显著增量影响
+ 大型文件，如可执行文件和安装文件
+ 支持客户端代码的资源库

例如，在将 SharePoint Online 网站添加到 CDN 源时，重复请求的小文件（如网站图像和脚本）可以显著提高网站呈现性能并逐步减少 SharePoint Online 网站的负载。 可以从 CDN 下载安装可执行文件等较大文件，从而对性能产生积极的影响，并随后减少 SharePoint Online 网站的负载，即使它们未经常访问。

基于每个文件的性能改进取决于许多因素，包括客户端与最近的 CDN 终结点的邻近度、本地网络上暂时的情况等等。 许多静态文件非常小，可以在不到Office 365下载。 但是，网页可能包含许多嵌入式文件，其累积下载时间为几秒。 从网站中CDN这些文件可以显著缩短整个页面加载时间。 有关[示例，请参阅CDN性能](content-delivery-networks.md#what-performance-gains-does-a-cdn-provide)提升？

<a name="CDNStoreAssets"> </a>
### <a name="determine-where-you-want-to-store-your-assets"></a>确定要存储资产的位置

the CDN fetches your assets from a location called an _origin_. 源可以是 URL SharePoint访问的文档网站、文档库或文件夹。 当你为组织指定来源时，你具有极大的灵活性。 例如，可以指定多个源或一个要放入所有源资源CDN源。 你可以选择同时为组织提供公共源或专用源。 大多数组织都将选择实施这两者的组合。

你可以为源（如文件夹或文档库）创建新容器，并添加想要从文档库CDN。 如果你希望从 CDN 获得一组特定的资产，并且希望将 CDN 资产集限制为容器中的这些文件，则这是一个不错的方法。

您还可以将现有网站集、网站、库或文件夹配置为源，这样容器内的所有符合条件的资产都将从 CDN。 在将现有容器添加为源之前，请务必确保了解其内容和权限，以便不会无意中向匿名访问或未经授权的用户公开资产。

你可以定义 _CDN_ 策略以从源中排除CDN。 CDN策略按文件类型和网站分类等属性排除公用源或专用源中的资产，并应用于在策略中指定的 CdnType (private 或 public) 的所有源。 例如，如果添加由包含多个子网站的网站组成的专用源，您可以定义一个策略来排除标记为"机密"的网站，以便不会从 CDN提供应用了该分类的网站中的内容。 该策略将应用于已 _添加到_ 策略的所有私有源CDN。

请记住，源数量越大，对服务处理请求CDN的影响越大。 我们建议你尽可能限制源的数量。

<a name="CDNOriginChoosePublicPrivate"> </a>
### <a name="choose-whether-each-origin-should-be-public-or-private"></a>选择每个源应为公共源还是专用源

标识源时，指定应公开 _还是私有。_  对CDN源中资产的访问权限是匿名的，并且CDN源中的内容受动态生成的令牌保护，从而获得更高的安全性。 无论你选择哪个选项，Microsoft 都会在管理用户本身时，CDN繁重的工作。 此外，在设置组并识别CDN之后，你可以改变主意。

公共和专用选项都提供相似的性能提升，但每个选项都有独特的属性和优点。

**可** 匿名访问Office 365 CDN内部的公共源，并且拥有资产 URL 的任何人都可以访问托管资产。 由于对公共源中内容的访问属于匿名访问，因此只能使用它们缓存非敏感的常规内容，如 JavaScript 文件、脚本、图标和图片。

**库中** 的专用源Office 365 CDN用户内容（如 SharePoint Online 文档库、网站和专有图像）的专用访问权限。 对专用源中内容的访问受动态生成的令牌保护，因此只有对原始文档库或存储位置具有权限的用户才能访问它。 Office 365 CDN中的专用源只能用于 SharePoint Online 内容，并且你仅可以通过从 SharePoint Online 租户重定向来访问专用源中的资产。

可以在使用专用源中的CDN中阅读有关对私有源中资产的访问权限[的工作方式。](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

#### <a name="attributes-and-advantages-of-hosting-assets-in-public-origins"></a>在公共源中托管资产的属性和优点

+ 每个人都能匿名访问公用源中公开的资产。
    > [!IMPORTANT]
    > 不应将包含用户信息或被视为对组织敏感的资源放在公共源中。

+ 如果从公用源中删除某资产，缓存会继续保留此资产最多 30 天；但此 CDN 资产的链接会在 15 分钟内失效。

+ 如果将样式表（CSS 文件）托管到公用源，可以在代码内使用相对路径和 URI。 也就是说，可以引用背景图像和其他对象相对于调用它的资产的位置。

+ 虽然可以构造公用源的 URL，但应谨慎操作，并确保利用页面上下文属性并按照指南执行此操作。 这是因为，如果无法访问 CDN，URL 就不会在 SharePoint Online 中自动解析为相应组织，进而可能会导致链接失效和其他错误抛出。 URL 也可能会更改，这就是为什么它不应只硬编码为当前值的原因。

+ 公共源包括的默认文件类型为 .css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff 和 .woff2。 可以指定其他文件类型。

+ 您可以配置策略以排除由您指定的网站分类标识的资产。 例如，可以选择排除所有标记为“机密”或“受限”的资产，即使它们的文件类型受支持且位于公用源中，也不例外。

#### <a name="attributes-and-advantages-of-hosting-assets-in-private-origins"></a>在专用源中托管资产的属性和优点

+ 专用源只能用于 SharePoint Online 资产。

+ 只有用户有权访问容器，他们才能访问专用源中的资产。 禁止匿名访问这些资产。

+ 专用源中的资产必须从 SharePoint Online 租户引用。 直接访问私有CDN资产不起作用。

+ 如果从专用源中删除资产，资产在缓存中可能仍可用一小时;但是，在资产删除后 15 分钟内，CDN资产的链接失效。

+ 默认情况下，支持为专用源添加下列类型的文件：.gif、.ico、.jpeg、.jpg、.js 和 .png。 可以指定其他文件类型。

+ 与公用源一样，您可以配置策略以排除由您指定的网站分类标识的资产，即使您使用通配符将文件夹或文档库内的所有资产都包括其中。

有关为什么使用 Office 365 CDN、常规 CDN 概念和其他可以与 Office 365 租户一同使用的 Microsoft CDN 的信息，请参阅内容交付[网络](content-delivery-networks.md)。

### <a name="default-cdn-origins"></a>默认CDN源

除非另行指定，否则Office 365启用该参数时，将设置一些默认Office 365 CDN。 如果你最初选择不预配它们，可以在完成设置后添加这些源。 除非了解跳过默认源设置的后果，并且有特定原因需要这样做，否则在启用默认源时，应允许创建CDN。

默认私有CDN源：

+ \*/userphoto.aspx
+ \*/siteassets

默认公用CDN源：

+ \*/masterpage
+ \*/style 库
+ \*/clientsideassets

> [!NOTE]
> _clientsideassets_ 是 2017 年 12 月添加到 Office 365 CDN 服务的默认公用源。 必须存在此源，SharePoint 框架解决方案CDN工作。 如果在 2017 年 12 Office 365 CDN之前启用了该设置，或者如果在启用默认源时跳过了默认源CDN，可以手动添加此源。 有关详细信息，请参阅[我的客户端 Web 部件或SharePoint 框架解决方案无法工作](use-microsoft-365-cdn-with-spo.md#my-client-side-web-part-or-sharepoint-framework-solution-isnt-working)。

<a name="CDNSetupinPShell"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-the-sharepoint-online-management-shell"></a>使用 Office 365 CDN Online 命令行管理SharePoint设置和配置命令行管理程序

本节中的过程要求使用 SharePoint Online 命令行管理程序连接到 SharePoint Online。 有关说明，请参阅[Connect to SharePoint Online PowerShell](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)。

完成这些步骤以使用 CDN Online 命令行管理程序在 SharePoint Online 中设置和配置SharePoint资产。

<details>
  <summary>单击展开</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>允许组织使用Office 365 CDN

在更改租户策略设置CDN，应先检索租户中专用CDN配置Office 365状态。 连接命令行管理程序SharePoint租户：

```powershell
Connect-SPOService -Url https://contoso-admin.sharepoint.com
```

现在使用 **Get-SPOTenantCdnEnabled** cmdlet 从租户CDN状态设置：

```powershell
Get-SPOTenantCdnEnabled -CdnType <Public | Private>
```

指定 CdnType CDN状态将输出到屏幕。

使用 **Set-SPOTenantCdnEnabled** cmdlet 可让组织使用 Office 365 CDN。 你可以使组织同时使用公用源和/或私有源。 还可以配置CDN以在启用默认源时跳过其设置。 稍后始终可以添加这些源，如本主题中所述。

对于 Windows PowerShell Online SharePoint：

```powershell
Set-SPOTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

例如，若要使组织同时使用公用源和专用源，请键入以下命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true
```

若要使组织能够同时使用公用源和专用源，但跳过设置默认源，请键入以下命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

请参阅[默认](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)CDN源，了解启用 Office 365 CDN 时默认预配的源，以及跳过默认源设置的潜在影响。

若要使组织能够使用公用源，请键入以下命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $true
```

若要使组织能够使用专用源，请键入以下命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $true
```

有关此 cmdlet 详细信息，请参阅 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。

<a name="Office365CDNforSPOFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>更改要包括在可选列表中的文件类型Office 365 CDN (可选) 

> [!TIP]
> 使用 **Set-SPOTenantCdnPolicy** cmdlet 定义文件类型时，将覆盖当前定义的列表。 如果要向列表中添加其他文件类型，请首先使用 cmdlet 了解已允许的文件类型，将它们与新文件类型一起包括在列表中。

使用 **Set-SPOTenantCdnPolicy** cmdlet 可定义静态文件类型，这些静态文件类型可通过公共源和专用源在 CDN。 默认情况下，允许使用常见资源类型，例如 .css、.gif、.jpg 和 .js。

对于 Windows PowerShell Online SharePoint：

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

例如，若要使CDN .css 和 .png文件，请输入命令：

```powershell
Set-SPOTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

To see what file types are currently allowed by the CDN， use the **Get-SPOTenantCdnPolicies** cmdlet：

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

有关这些 cmdlet 的信息，请参阅[Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/)和[Get-SPOTenantCdnPolicies。](/powershell/module/sharepoint-online/)

<a name="Office365CDNforSPOSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>更改网站分类列表，以从"可选"Office 365 CDN (排除) 

> [!TIP]
> 使用 **Set-SPOTenantCdnPolicy** cmdlet 排除网站分类时，将覆盖当前定义的列表。 如果要排除其他网站分类，请首先使用 cmdlet 了解已排除的分类，然后将它们与新分类一起添加。

运行 **Set-SPOTenantCdnPolicy** cmdlet 可以排除不想通过 CDN 提供的网站分类。 默认情况下，不排除任何网站分类。

对于 Windows PowerShell Online SharePoint：

```powershell
Set-SPOTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications >"
```

若要了解当前限制的网站分类，请使用 **Get-SPOTenantCdnPolicies** cmdlet：

```powershell
Get-SPOTenantCdnPolicies -CdnType <Public | Private>
```

将返回的属性包括 _IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 和 _ExcludeIfNoScriptDisabled_。

_IncludeFileExtensions_ 属性包含文件扩展名的列表，该文件扩展名将CDN。

> [!NOTE]
> 默认文件扩展名在公用和专用之间有所不同。

_ExcludeRestrictedSiteClassifications_ 属性包含要从网站列表中排除CDN。 例如，您可以排除标记为"机密"的网站，以便网站中应用了该分类的内容不会从网站CDN。

_ExcludeIfNoScriptDisabled_ 属性根据网站级别的 _NoScript_ 属性CDN排除网站中的内容。 默认情况下 _，NoScript_ 属性设置为"为新式 **网站** 启用"和"**对经典** 网站 _禁用_"。 这取决于你的租户设置。

有关这些 cmdlet 的信息，请参阅[Set-SPOTenantCdnPolicy](/powershell/module/sharepoint-online/)和[Get-SPOTenantCdnPolicies。](/powershell/module/sharepoint-online/)

<a name="Office365CDNforSPOOriginPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>为资产添加来源

使用 **Add-SPOTenantCdnOrigin** cmdlet 定义源。 可以定义多个源。 源是 SharePoint 库或文件夹的 URL，其中包含要由 CDN 托管的资产。

> [!IMPORTANT]
> 不应将包含用户信息或被视为对组织敏感的资源放在公共源中。

```powershell
Add-SPOTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

path _的值是_ 包含资产的库或文件夹的相对路径。 除了相对路径之外，还可以使用通配符。 源支持在 URL 前加通配符。 这允许你创建跨多个站点的来源。 例如，若要将所有网站的 masterpages 文件夹中的所有资产作为公共源包含到 CDN，请键入以下命令：

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ 通配符修饰符 * 只能在路径的开头使用，并且将匹配指定 URL 下 **/** 的所有 URL 段。
+ 该路径可以指向文档库、文件夹或网站。 例如，路径 _*/site1_ 将匹配网站下的所有文档库。

你可以添加具有特定相对路径的原点。 不能使用完整路径添加原点。

此示例将网站集库的私有源添加到特定网站上：

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

此示例在网站集的网站资产库中添加 _folder1_ 文件夹的私有源：

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

如果路径中具有空格，可以使用双引号将路径括起来，或者将空格替换为 URL 编码 %20。 以下示例在网站集的网站资产库中添加文件夹 _1_ 文件夹的私有源：

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

有关此命令及其语法的信息，请参阅 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

> [!NOTE]
> 在专用源中，从源共享的资产必须已发布主要版本，然后才能从源CDN。

运行命令后，系统将跨数据中心同步配置。 这最多可能需要 15 分钟。

<a name="ExamplePublicOrigin"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>示例：为母版页和适用于 SharePoint Online 的样式库配置公共源

正常情况下，当你启用这些源时，默认情况下会Office 365 CDN。 但是，如果要手动启用它们，请按照以下步骤操作。

+ 使用 **Add-SPOTenantCdnOrigin** cmdlet 可以将样式库定义为公共源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ 使用 **Add-SPOTenantCdnOrigin** cmdlet 可以将母版页定义为公用源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

有关此命令及其语法的信息，请参阅 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

运行命令后，系统将跨数据中心同步配置。 这最多可能需要 15 分钟。

<a name="ExamplePrivateOrigin"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>示例：为 SharePoint Online 的网站资产、网站页面和发布图像配置专用源

+ 使用 **Add-SPOTenantCdnOrigin** cmdlet 将网站资产文件夹定义为专用源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ 使用 **Add-SPOTenantCdnOrigin** cmdlet 将网站页面文件夹定义为专用源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ 使用 **Add-SPOTenantCdnOrigin** cmdlet 将发布图像文件夹定义为私有源。

  ```powershell
  Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

有关此命令及其语法的信息，请参阅 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

运行命令后，系统将跨数据中心同步配置。 这最多可能需要 15 分钟。

<a name="ExamplePrivateOriginSiteCollection"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>示例：为 SharePoint Online 的网站集配置专用源

使用 **Add-SPOTenantCdnOrigin** cmdlet 将网站集定义为专用源。 例如：

```powershell
Add-SPOTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

有关此命令及其语法的信息，请参阅 [Add-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Add-SPOTenantCdnOrigin)。

运行命令后，系统将跨数据中心同步配置。 你可能会看到"_配置挂起_"消息，预计 SharePoint Online 租户连接到 CDN 服务。 这最多可能需要 15 分钟。

<a name="CDNManage"> </a>
### <a name="manage-the-office-365-cdn"></a>管理Office 365 CDN

设置网站集后CDN，可以在更新内容或更改需求时更改配置，如本节中所述。

<a name="Office365CDNforSPOaddremoveasset"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>添加、更新或删除资源Office 365 CDN

完成设置步骤后，可以随时添加新资产，并更新或删除现有资源。 只需对标识为源的文件夹或SharePoint库中的资产进行更改。 如果添加新资产，它将立即通过CDN可用。 但是，如果更新资源，则新副本最多需要 15 分钟才能传播，并可在 CDN。

如果需要检索源的位置，可以使用 **Get-SPOTenantCdnOrigins** cmdlet。 有关如何使用此 cmdlet 的信息，请参阅 [Get-SPOTenantCdnOrigins](/powershell/module/sharepoint-online/Get-SPOTenantCdnOrigins)。

<a name="Office365CDNforSPORemoveOriginPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>从源中删除Office 365 CDN

你可以删除对标识为SharePoint的文件夹或库的访问权限。 为此，请使用 **Remove-SPOTenantCdnOrigin** cmdlet。

```powershell
Remove-SPOTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

有关如何使用此 cmdlet 的信息，请参阅 [Remove-SPOTenantCdnOrigin](/powershell/module/sharepoint-online/Remove-SPOTenantCdnOrigin)。

<a name="Office365CDNforSPOModifyOrigin"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>修改源中的Office 365 CDN

无法修改已创建的源。 请删除原点，然后添加新源。 有关详细信息，请参阅从资源[中删除](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPosh)Office 365 CDN和[为资产添加源](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>禁用Office 365 CDN

使用 **Set-SPOTenantCdnEnabled** cmdlet 可禁用CDN配置。 如果同时为 cmdlet 启用了公用源CDN源，则需要运行 cmdlet 两次，如以下示例所示。

若要在命令行中禁止使用公用CDN，请输入以下命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Public -Enable $false
```

若要在应用程序内禁止使用专用CDN，请输入以下命令：

```powershell
Set-SPOTenantCdnEnabled -CdnType Private -Enable $false
```

有关此 cmdlet 详细信息，请参阅 [Set-SPOTenantCdnEnabled](/powershell/module/sharepoint-online/Set-SPOTenantCdnEnabled)。

</details>

<a name="CDNSetupinPnPPosh"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-by-using-pnp-powershell"></a>使用 PnP PowerShell Office 365 CDN和配置应用程序

本节中的过程要求使用 PnP PowerShell 连接到 SharePoint Online。 有关说明，请参阅 [PnP PowerShell 入门](https://github.com/SharePoint/PnP-PowerShell#getting-started)。

完成这些步骤以设置和配置CDN PnP PowerShell 在 SharePoint Online 中托管资产。

<details>
  <summary>单击展开</summary>

### <a name="enable-your-organization-to-use-the-office-365-cdn"></a>允许组织使用Office 365 CDN

在更改租户策略设置CDN，应先检索租户中专用CDN配置Office 365状态。 连接 PnP PowerShell 访问租户：

```powershell
Connect-PnPOnline -Url https://contoso-admin.sharepoint.com -UseWebLogin
```

现在，使用 **Get-PnPTenantCdnEnabled** cmdlet 从租户CDN状态设置：

```powershell
Get-PnPTenantCdnEnabled -CdnType <Public | Private>
```

指定 CdnType CDN状态将输出到屏幕。

使用 **Set-PnPTenantCdnEnabled** cmdlet 可让组织使用 Office 365 CDN。 你可以使组织同时使用公用源和/或私有源。 还可以配置CDN以在启用默认源时跳过其设置。 稍后始终可以添加这些源，如本主题中所述。

在 PnP PowerShell 中：

```powershell
Set-PnPTenantCdnEnabled -CdnType <Public | Private | Both> -Enable $true
```

例如，若要使组织同时使用公用源和专用源，请键入以下命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true
```

若要使组织能够同时使用公用源和专用源，但跳过设置默认源，请键入以下命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Both -Enable $true -NoDefaultOrigins
```

请参阅[默认](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)CDN源，了解启用 Office 365 CDN 时默认预配的源，以及跳过默认源设置的潜在影响。

若要使组织能够使用公用源，请键入以下命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $true
```

若要使组织能够使用专用源，请键入以下命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $true
```

有关此 cmdlet 详细信息，请参阅 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。

<a name="Office365CDNforPnPPoshFileType"> </a>
### <a name="change-the-list-of-file-types-to-include-in-the-office-365-cdn-optional"></a>更改要包括在可选列表中的文件类型Office 365 CDN (可选) 

> [!TIP]
> 使用 **Set-PnPTenantCdnPolicy** cmdlet 定义文件类型时，将覆盖当前定义的列表。 如果要向列表中添加其他文件类型，请首先使用 cmdlet 了解已允许的文件类型，将它们与新文件类型一起包括在列表中。

使用 **Set-PnPTenantCdnPolicy** cmdlet 可定义静态文件类型，这些静态文件类型可通过公共源和专用源在 CDN。 默认情况下，允许使用常见资源类型，例如 .css、.gif、.jpg 和 .js。

在 PnP PowerShell 中：

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType IncludeFileExtensions -PolicyValue "<Comma-separated list of file types >"
```

例如，若要使CDN .css 和 .png文件，请输入命令：

```powershell
Set-PnPTenantCdnPolicy -CdnType Private -PolicyType IncludeFileExtensions -PolicyValue "CSS,PNG"
```

To see what file types are currently allowed by the CDN， use the **Get-PnPTenantCdnPolicies** cmdlet：

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

有关这些 cmdlet 的信息，请参阅[Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy)和[Get-PnPTenantCdnPolicies。](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforPnPPoshSiteClassification"> </a>
### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn-optional"></a>更改网站分类列表，从"可选"Office 365 CDN (排除) 

> [!TIP]
> 使用 **Set-PnPTenantCdnPolicy** cmdlet 排除网站分类时，将覆盖当前定义的列表。 如果要排除其他网站分类，请首先使用 cmdlet 了解已排除的分类，然后将它们与新分类一起添加。

使用 **Set-PnPTenantCdnPolicy** cmdlet 可以排除不希望通过网站集CDN。 默认情况下，不排除任何网站分类。

在 PnP PowerShell 中：

```powershell
Set-PnPTenantCdnPolicy -CdnType <Public | Private> -PolicyType ExcludeRestrictedSiteClassifications  -PolicyValue "<Comma-separated list of site classifications>"
```

若要了解当前限制哪些网站分类，请使用 **Get-PnPTenantCdnPolicies** cmdlet：

```powershell
Get-PnPTenantCdnPolicies -CdnType <Public | Private>
```

将返回的属性包括 _IncludeFileExtensions_、 _ExcludeRestrictedSiteClassifications_ 和 _ExcludeIfNoScriptDisabled_。

_IncludeFileExtensions_ 属性包含文件扩展名的列表，该文件扩展名将CDN。

> [!NOTE]
> 默认文件扩展名在公用和专用之间有所不同。

_ExcludeRestrictedSiteClassifications_ 属性包含您希望从网站列表中排除CDN。 例如，您可以排除标记为"机密"的网站，以便网站中应用了该分类的内容将不会从网站CDN。

_ExcludeIfNoScriptDisabled_ 属性根据网站级别的 _NoScript_ 属性CDN排除网站中的内容。 默认情况下 _，NoScript_ 属性设置为"为新式 **网站** 启用"和"**对经典** 网站 _禁用_"。 这取决于你的租户设置。

有关这些 cmdlet 的信息，请参阅[Set-PnPTenantCdnPolicy](/powershell/module/sharepoint-pnp/set-pnptenantcdnpolicy)和[Get-PnPTenantCdnPolicies。](/powershell/module/sharepoint-pnp/get-pnptenantcdnpolicies)

<a name="Office365CDNforSPOOriginPnPPosh"> </a>
### <a name="add-an-origin-for-your-assets"></a>为资产添加来源

使用 **Add-PnPTenantCdnOrigin** cmdlet 定义源。 可以定义多个源。 源是 SharePoint 库或文件夹的 URL，其中包含要由 CDN 托管的资产。

> [!IMPORTANT]
> 不应将包含用户信息或被视为对组织敏感的资源放在公共源中。

```powershell
Add-PnPTenantCdnOrigin -CdnType <Public | Private> -OriginUrl <path>
```

path _的值是_ 包含资产的库或文件夹的相对路径。 除了相对路径之外，还可以使用通配符。 源支持在 URL 前加通配符。 这允许你创建跨多个站点的来源。 例如，若要将所有网站的 masterpages 文件夹中的所有资产作为公共源包含到 CDN，请键入以下命令：

```powershell
Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
```

+ 通配符修饰符 * 只能在路径的开头使用，并且将匹配指定 URL 下 **/** 的所有 URL 段。
+ 该路径可以指向文档库、文件夹或网站。 例如，路径 _*/site1_ 将匹配网站下的所有文档库。

你可以添加具有特定相对路径的原点。 不能使用完整路径添加原点。

此示例将网站资产库的私有源添加到特定网站上：

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

此示例在网站集的网站资产库中添加 _folder1_ 文件夹的私有源：

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder1
```

如果路径中具有空格，可以使用双引号将路径括起来，或者将空格替换为 URL 编码 %20。 以下示例在网站集的网站资产库中添加文件夹 _1_ 文件夹的私有源：

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/test/siteassets/folder%201
```

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl "sites/test/siteassets/folder 1"
```

有关此命令及其语法的信息，请参阅 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

> [!NOTE]
> 在专用源中，从源共享的资产必须已发布主要版本，然后才能从源CDN。

运行命令后，系统将跨数据中心同步配置。 这最多可能需要 15 分钟。

<a name="ExamplePublicOriginPnPPosh"> </a>
### <a name="example-configure-a-public-origin-for-your-master-pages-and-for-your-style-library-for-sharepoint-online"></a>示例：为母版页和适用于 SharePoint Online 的样式库配置公共源

正常情况下，当你启用这些源时，默认情况下会Office 365 CDN。 但是，如果要手动启用它们，请按照以下步骤操作。

+ 使用 **Add-PnPTenantCdnOrigin** cmdlet 将样式库定义为公共源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */style%20library
  ```

+ 使用 **Add-PnPTenantCdnOrigin** cmdlet 可以将母版页定义为公用源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Public -OriginUrl */masterpage
  ```

有关此命令及其语法的信息，请参阅 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

运行命令后，系统将跨数据中心同步配置。 这最多可能需要 15 分钟。

<a name="ExamplePrivateOriginPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-your-site-assets-site-pages-and-publishing-images-for-sharepoint-online"></a>示例：为 SharePoint Online 的网站资产、网站页面和发布图像配置专用源

+ 使用 **Add-PnPTenantCdnOrigin** cmdlet 将网站资产文件夹定义为专用源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */siteassets
  ```

+ 使用 **Add-PnPTenantCdnOrigin** cmdlet 将网站页面文件夹定义为专用源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */sitepages
  ```

+ 使用 **Add-PnPTenantCdnOrigin** cmdlet 将发布图像文件夹定义为私有源。

  ```powershell
  Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl */publishingimages
  ```

有关此命令及其语法的信息，请参阅 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

运行命令后，系统将跨数据中心同步配置。 这最多可能需要 15 分钟。

<a name="ExamplePrivateOriginSiteCollectionPnPPosh"> </a>
### <a name="example-configure-a-private-origin-for-a-site-collection-for-sharepoint-online"></a>示例：为 SharePoint Online 的网站集配置专用源

使用 **Add-PnPTenantCdnOrigin** cmdlet 将网站集定义为专用源。 例如：

```powershell
Add-PnPTenantCdnOrigin -CdnType Private -OriginUrl sites/site1/siteassets
```

有关此命令及其语法的信息，请参阅 [Add-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/add-pnptenantcdnorigin)。

运行命令后，系统将跨数据中心同步配置。 你可能会看到"_配置挂起_"消息，预计 SharePoint Online 租户连接到 CDN 服务。 这最多可能需要 15 分钟。

<a name="CDNManagePnPPosh"> </a>
### <a name="manage-the-office-365-cdn"></a>管理Office 365 CDN

设置网站集后CDN，可以在更新内容或更改需求时更改配置，如本节中所述。

<a name="Office365CDNforSPOaddremoveassetPnPPosh"> </a>
#### <a name="add-update-or-remove-assets-from-the-office-365-cdn"></a>添加、更新或删除资源Office 365 CDN

完成设置步骤后，可以随时添加新资产，并更新或删除现有资源。 只需对标识为源的文件夹或SharePoint库中的资产进行更改。 如果添加新资产，它将立即通过CDN可用。 但是，如果更新资源，则新副本最多需要 15 分钟才能传播，并可在 CDN。

如果需要检索源的位置，可以使用 **Get-PnPTenantCdnOrigin** cmdlet。 有关如何使用此 cmdlet 的信息，请参阅 [Get-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/get-pnptenantcdnorigin)。

<a name="Office365CDNforSPORemoveOriginPnPPosh"> </a>
#### <a name="remove-an-origin-from-the-office-365-cdn"></a>从源中删除Office 365 CDN

你可以删除对标识为SharePoint的文件夹或库的访问权限。 为此，请使用 **Remove-PnPTenantCdnOrigin** cmdlet。

```powershell
Remove-PnPTenantCdnOrigin -OriginUrl <path> -CdnType <Public | Private | Both>
```

有关如何使用此 cmdlet 的信息，请参阅 [Remove-PnPTenantCdnOrigin](/powershell/module/sharepoint-pnp/remove-pnptenantcdnorigin)。

<a name="Office365CDNforSPOModifyOriginPnPPosh"> </a>
#### <a name="modify-an-origin-in-the-office-365-cdn"></a>修改源中的Office 365 CDN

无法修改已创建的源。 请删除原点，然后添加新源。 有关详细信息，请参阅从资源[中删除](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPORemoveOriginPnPPosh)Office 365 CDN和[为资产添加源](use-microsoft-365-cdn-with-spo.md#Office365CDNforSPOOriginPnPPosh)。

<a name="Office365CDNforSPODisable"> </a>
#### <a name="disable-the-office-365-cdn"></a>禁用Office 365 CDN

使用 **Set-PnPTenantCdnEnabled** cmdlet 可禁用CDN配置。 如果同时为 cmdlet 启用了公用源CDN源，则需要运行 cmdlet 两次，如以下示例所示。

若要在命令行中禁止使用公用CDN，请输入以下命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Public -Enable $false
```

若要在应用程序内禁止使用专用CDN，请输入以下命令：

```powershell
Set-PnPTenantCdnEnabled -CdnType Private -Enable $false
```

有关此 cmdlet 详细信息，请参阅 [Set-PnPTenantCdnEnabled](/powershell/module/sharepoint-pnp/set-pnptenantcdnenabled)。

</details>

<a name="CDNSetupinCLI"> </a>
## <a name="set-up-and-configure-the-office-365-cdn-using-the-office-365-cli"></a>使用 Office 365 CLI 设置和配置 Office 365 CDN

本节中的过程要求你已安装 Office 365 [CLI](https://aka.ms/o365cli)。 接下来，使用登录Office 365连接到你的[租户](https://pnp.github.io/office365-cli/cmd/login/)。

完成这些步骤以设置和配置CDN CLI 在 SharePoint Online 中Office 365资产。

<details>
  <summary>单击展开</summary>

### <a name="enable-the-office-365-cdn"></a>启用Office 365 CDN

可以运行 [spo cdn set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-set/) 命令，在租户中管理 Office 365 CDN 的状态。

若要在租户中启用 Office 365 公用 CDN，请运行以下命令：

```cli
spo cdn set --type Public --enabled true
```

若要启用Office 365 SharePoint CDN，请执行：

```cli
spo cdn set --type Private --enabled true
```

#### <a name="view-the-current-status-of-the-office-365-cdn"></a>查看 Office 365 CDN 的当前状态

若要检查特定类型 Office 365 CDN是否已启用，请使用[spo cdn get](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-get/)命令。

若要检查 Office 365 公用 CDN 是否已启用，请运行以下命令：

```cli
spo cdn get --type Public
```

### <a name="view-the-office-365-cdn-origins"></a>查看Office 365 CDN源

若要查看当前配置的 Office 365 公用 CDN 源，请运行以下命令：

```cli
spo cdn origin list --type Public
```

请参阅[默认CDN](use-microsoft-365-cdn-with-spo.md#default-cdn-origins)源，了解启用默认设置源时预配Office 365 CDN。

### <a name="add-an-office-365-cdn-origin"></a>添加Office 365 CDN源

> [!IMPORTANT]
> 不应将视为对组织敏感的资源放在配置为公用源SharePoint文档库中。

运行 [spo cdn origin add](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-add/) 命令可以定义 CDN 源。 可以定义多个源。 源是 SharePoint 库或文件夹的 URL，其中包含要由 CDN 托管的资产。

```cli
spo cdn origin add --type [Public | Private] --origin <path>
```

`path`其中 是包含资产的文件夹的相对路径。 除了相对路径之外，还可以使用通配符。

若要将所有网站的母版页 **样式库中** 的所有资产作为公共源包含，请执行：

```cli
spo cdn origin add --type Public --origin */masterpage
```

若要配置特定网站集的专用源，请运行以下命令：

```cli
spo cdn origin add --type Private --origin sites/site1/siteassets
```

> [!NOTE]
> 添加 CDN 源后，最长可能需要 15 分钟，才能通过 CDN 服务检索文件。 可以运行 [spo cdn origin list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 命令，验证特定源是否已启用。

### <a name="remove-an-office-365-cdn-origin"></a>删除Office 365 CDN源

运行 [spo cdn origin remove](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-remove/) 命令可以删除指定类型 CDN 的 CDN 源。

要从配置中删除公用源CDN，请执行：

```cli
spo cdn origin remove --type Public --origin */masterpage
```

> [!NOTE]
> 删除CDN源不会影响存储在任何与源匹配的文档库中的文件。 如果已使用资产库的 url 引用SharePoint，SharePoint将自动切换回指向文档库的原始 URL。 但是，如果已使用公用 url CDN资源，则删除源将断开链接，并且你将需要手动更改它们。

### <a name="modify-an-office-365-cdn-origin"></a>修改Office 365 CDN源

无法修改现有 CDN 源。 而应运行 `spo cdn origin remove` 命令删除以前定义的 CDN 源，并运行 `spo cdn origin add` 命令添加新源。

### <a name="change-the-types-of-files-to-include-in-the-office-365-cdn"></a>更改要包括在文件包中的Office 365 CDN

默认情况下，CDN 中包含以下文件类型 _：.css、.eot、.gif、.ico、.jpeg、.jpg、.js、.map、.png、.svg、.ttf、.woff 和 .woff2。_ 如果需要在 CDN 中添加其他类型的文件，可以运行 [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 命令更改 CDN 配置。

> [!NOTE]
> 如果更改文件类型列表，也就是覆盖当前定义的列表。 若要添加其他文件类型，请先运行 [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-origin-list/) 命令，确定当前配置的文件类型。

若要将 _JSON_ 文件类型添加到公共文件中包含的文件类型的默认列表中，CDN：

```cli
spo cdn policy set --type Public --policy IncludeFileExtensions --value "CSS,EOT,GIF,ICO,JPEG,JPG,JS,MAP,PNG,SVG,TTF,WOFF,JSON"
```

### <a name="change-the-list-of-site-classifications-you-want-to-exclude-from-the-office-365-cdn"></a>更改要从 Office 365 CDN 中排除的网站分类列表

运行 [spo cdn policy set](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-set/) 命令可以排除不想通过 CDN 提供的网站分类。 默认情况下，不排除任何网站分类。

> [!NOTE]
> 如果更改已排除的网站分类列表，也就是覆盖当前定义的列表。 若要排除其他分类，请先运行 [spo cdn policy list](https://pnp.github.io/office365-cli/cmd/spo/cdn/cdn-policy-list/) 命令，确定当前配置的分类。

若要从公共网站中排除分类为 _HBI_ CDN，请执行

```cli
spo cdn policy set --type Public --policy ExcludeRestrictedSiteClassifications --value "HBI"
```

### <a name="disable-the-office-365-cdn"></a>禁用Office 365 CDN

若要禁用 Office 365 CDN，请运行 `spo cdn set` 命令。例如：

```cli
spo cdn set --type Public --enabled false
```

</details>

## <a name="using-your-cdn-assets"></a>使用CDN资产

现在，你已启用CDN配置的来源和策略，可以开始使用CDN资源。

本节将帮助您了解如何在 SharePoint 页面和内容中使用 CDN URL，以便 SharePoint 将公用源和专用源中的资产请求重定向到 CDN。

+ [更新指向资产CDN链接](use-microsoft-365-cdn-with-spo.md#updating-links-to-cdn-assets)
+ [使用公共源中的资产](use-microsoft-365-cdn-with-spo.md#using-assets-in-public-origins)
+ [使用专用源中的资产](use-microsoft-365-cdn-with-spo.md#using-assets-in-private-origins)

有关如何使用 CDN 托管客户端 Web 部件的信息，请参阅主题从 Office 365 CDN (Hello World 第[4](/sharepoint/dev/spfx/web-parts/get-started/hosting-webpart-from-office-365-cdn)部分托管) 。

> [!NOTE]
> 如果将 _ClientSideAssets_ 文件夹添加到专用CDN源列表中，CDN托管的自定义 Web 部件将无法呈现。 SPFX Web 部件使用的文件只能使用公共CDN ClientSideAssets 文件夹是公用文件夹的默认CDN。

### <a name="updating-links-to-cdn-assets"></a>更新指向资产CDN链接

若要使用已添加到源中的资源，只需使用指向原始文件的路径更新指向原始文件的链接。

+ 编辑包含已添加到源中的资产的链接的页面或内容。 如果要将链接更新到给定资产出现的任何位置，您也可以使用多种方法之一在输入站点或网站集中进行全局搜索和替换链接。
+ 对于指向源中资产的每个链接，请将路径替换为源中文件CDN路径。 可以使用相对路径。
+ 保存页面或内容。

例如，考虑已复制到 _文档库文件夹 /site/CDN_origins/public/ 的图像 /site/SiteAssets/images/image.png_ 。 若要使用CDN资源，请将图像文件位置的原始路径替换为原点的路径，以将新的 URL _/site/CDN_origins/public/image.png_。

如果要使用资产的完整 URL 而不是相对路径，请构建如下所示的链接：

`https://<TenantHostName>.sharepoint.com/sites/site/CDN_origins/public/image.png`

> [!NOTE]
> 通常，不应将 URL 直接硬编码为资源CDN。 但是，如果需要，你可以手动为公用源中的资产构建 URL。 有关详细信息，请参阅[Hardcoding CDN URL for public assets](use-microsoft-365-cdn-with-spo.md#constructing-cdn-urls-for-public-assets)。

若要了解如何验证是否正在从 CDN 提供资产，请参阅疑难解答中的如何确认 CDN 正在提供资产[Office 365 CDN。](use-microsoft-365-cdn-with-spo.md#CDNConfirm) [](use-microsoft-365-cdn-with-spo.md#CDNTroubleshooting)

### <a name="using-assets-in-public-origins"></a>使用公共源中的资产

SharePoint  Online 中的发布功能会自动将存储在公共源中的资产的 URL 重写为 CDN 等效项，以便资产从 CDN 服务而不是 SharePoint 提供。

如果你的源位于启用了发布功能的网站中，并且你想要卸载到 CDN 的资产位于以下类别之一，SharePoint 将自动重写源中资产的 URL，只要 CDN 策略未排除该资产。

下面概述了 SharePoint 发布功能自动重写的链接：

+ 经典发布页面 HTML 响应中的 IMG/LINK/CSS URL
  + 这包括作者在页面的 HTML 内容中添加的图像
+ 图片库幻灯片 Web 部件图像 URL
+ SPList REST API (RenderListDataAsStream) 结果中的图像字段
  + 使用新属性 _ImageFieldsToTryRewriteToCdnUrls_ 提供以逗号分隔的字段列表
  + 支持超链接字段和 PublishingImage 字段
+ SharePoint图像再现

下图说明了当用户收到SharePoint来自公共源的资产的页面的请求时，工作流。

![工作流图：从Office 365 CDN检索资源。](../media/O365-CDN/o365-cdn-public-steps-transparent.png "工作流：从Office 365 CDN检索资源")

> [!TIP]
> 如果要禁用页面上特定 URL 的自动重写，可以签出页面并添加查询字符串参数 **？NoAutoReWrites=true** 到要禁用的每个链接的末尾。

#### <a name="constructing-cdn-urls-for-public-assets"></a>为CDN构建 URL

如果未为公共源启用发布功能，或者资产不是 CDN 服务的自动重写功能支持的链接类型之一，您可以手动构造指向资产的 CDN 位置的 URL，并在你的内容中使用这些 URL。

> [!NOTE]
> 无法硬编码或构造CDN源中资产的 URL，因为生成形成 URL 的最后一节所需的访问令牌是在请求资源时生成的。 您可以构造公用网站的 URL CDN URL 不应硬编码，因为它可能会更改。

对于CDN资源，URL 格式将如下所示：

```http
https://publiccdn.sharepointonline.com/<TenantHostName>/sites/site/library/asset.png
```

将 **TenantHostName** 替换为租户名称。 示例：

```http
https://publiccdn.sharepointonline.com/contoso.sharepoint.com/sites/site/library/asset.png
```

> [!NOTE]
> 页面上下文属性应该用于构造前缀，而不是硬编码 https://publiccdn.sharepointonline.com " "。 URL 可能会更改，不应进行硬编码。 如果将显示模板与 Classic SharePoint Online 一同使用，可以在显示模板中将属性"window._spPageContextInfo.publicCdnBaseUrl"用于 URL 的前缀。 如果要为新式SPFx经典 Web 部件SharePoint可以使用属性"this.context.pageContext.legacyPageContext.publicCdnBaseUrl"。 这将提供前缀，以便如果更改，则你的实现将更新它。 例如，SPFx，可以使用属性"this.context.pageContext.legacyPageContext.publicCdnBaseUrl" + "/" + "host" + "/" + "relativeURL for the item"构建 URL。 请参阅[在客户端CDN](https://youtu.be/IH1RbQlbhIA) 1 性能系列的一部分[使用客户端代码](https://aka.ms/sppnp-perfvideos)


### <a name="using-assets-in-private-origins"></a>使用专用源中的资产

使用专用源中的资产不需要其他配置。 SharePoint Online 自动重写专用源中资产的 URL，因此将始终从应用程序请求CDN。 无法手动构建 URL CDN私有源中的资产，因为这些 URL 包含的令牌必须由 SharePoint Online 在请求资产时自动生成。

对专用源中的资产的访问权限受基于用户对源权限的动态生成的令牌的保护，以下各节介绍了一些注意事项。 用户必须至少具有 **对源** 的读取访问权限，CDN内容。

下图说明了当用户收到SharePoint页面（包含来自专用源的资产）的请求时，工作流。

![工作流图：从Office 365 CDN检索资源。](../media/O365-CDN/o365-cdn-private-steps-transparent.png "工作流：从Office 365 CDN源检索资源")

#### <a name="token-based-authorization-in-private-origins"></a>私有源中基于令牌的授权

对应用程序专用源中的资产Office 365 CDN由 SharePoint Online 生成的令牌授予。 对于已有权访问由源指定的文件夹或库的用户，系统会自动授予允许用户基于其权限级别访问文件的令牌。 这些访问令牌在生成后 30 到 90 分钟内有效，以帮助防止令牌重播攻击。

生成访问令牌后，SharePoint Online 会向包含两个授权参数的客户端返回自定义 URI， (边缘授权令牌 _)_ 和 _oat_ (源授权令牌) 。 每个令牌的结构都<纪元时间格式的过期时间>__<_安全签名>。_ 例如：

```http
https://privatecdn.sharepointonline.com/contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg?eat=1486154359_cc59042c5c55c90b26a2775323c7c8112718431228fe84d568a3795a63912840&oat=1486154359_7d73c2e3ba4b7b1f97242332900616db0d4ffb04312
```

> [!NOTE]
> 拥有令牌的任何人都可以访问 CDN。 但是，包含这些访问令牌的 URL 仅通过 HTTPS 共享，因此除非 URL 在令牌过期之前由最终用户显式共享，否则未经授权的用户无法访问资产。

#### <a name="item-level-permissions-are-not-supported-for-assets-in-private-origins"></a>私有源中的资产不支持项目级权限

需要注意的是，SharePoint Online 不支持私有源中的资产的项目级权限。 例如，对于位于 的文件，在 满足以下条件的情况下，用户 `https://contoso.sharepoint.com/sites/site1/library1/folder1/image1.jpg` 具有对文件的有效访问权限：

|用户  |权限  |有效访问  |
|---------|---------|---------|
|用户 1     |有权访问 folder1         |可以从image1.jpg访问CDN         |
|用户 2     |无法访问 folder1         |无法从image1.jpg访问CDN         |
|用户 3     |无权访问 folder1，但被授予了访问 image1.jpg Online SharePoint权限         |可以直接从 image1.jpg Online SharePoint资产，但不能从 CDN         |
|用户 4     |有权访问 folder1，但已明确拒绝访问 image1.jpg Online SharePoint         |无法从 SharePoint Online 访问资产，但可以从 CDN尽管被拒绝访问 SharePoint Online 中的文件         |

<a name="CDNTroubleshooting"></a>

## <a name="troubleshooting-the-office-365-cdn"></a>疑难解答Office 365 CDN

<a name="CDNConfirm"></a>

### <a name="how-do-i-confirm-that-assets-are-being-served-by-the-cdn"></a>如何确认资产由组织CDN？

向页面添加指向 CDN 资产的链接后，您可以通过浏览到页面、在图像呈现后右键单击图像并查看图像 URL，确认资产是否从 CDN 提供。

您还可以使用浏览器的开发人员工具查看页面上每个资产的 URL，或使用第三方网络跟踪工具。

> [!NOTE]
> 如果使用网络工具（如 Fiddler）在从 SharePoint 页面呈现资产外测试资产，则必须手动将引用器标头"Referer： "添加到 GET 请求，其中 URL 是 SharePoint Online 租户的根 `https://yourdomain.sharepoint.com` URL。

无法直接CDN Web 浏览器中测试 URL，因为必须有来自 SharePoint Online 的参考程序。 但是，如果您将CDN资源 URL 添加到 SharePoint 页面，然后在浏览器中打开该页面，则会看到页面上呈现的 CDN 资源。

有关在浏览器浏览器中使用开发人员工具Microsoft Edge，请参阅Microsoft Edge[工具。](/microsoft-edge/devtools-guide)

若要观看 SharePoint 开发人员模式和做法[YouTube](https://aka.ms/sppnp-videos)频道中托管的简短视频，演示如何验证 CDN 是否正常工作，请参阅验证[CDN 使用情况](https://www.youtube.com/watch?v=ClCtBAtGjE8&list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA&index=5)并确保最佳网络连接。

### <a name="why-are-assets-from-a-new-origin-unavailable"></a>为什么新源中的资产不可用？
新源中的资产不会立即可供使用，因为注册需要一段时间才能传遍 CDN 并且需要将资产从源上载到 CDN 存储。 资源在文件中可用CDN取决于资产数量和文件大小。

### <a name="my-client-side-web-part-or-sharepoint-framework-solution-isnt-working"></a>我的客户端 Web 部件或SharePoint 框架解决方案无法工作

为公用源Office 365 CDN时，CDN服务会自动创建这些默认源：

+ */MASTERPAGE
+ */STYLE 库
+ */CLIENTSIDEASSETS

如果缺少 */clientsideassets 源，SharePoint 框架解决方案将失败，并且不会生成警告或错误消息。 此源可能丢失，原因是CDN _-NoDefaultOrigins_ 参数设置为 **$true** 启用，或者源已手动删除。

可以通过以下 PowerShell 命令查看存在哪些源：

```powershell
Get-SPOTenantCdnOrigins -CdnType Public
```

或者，你可以检查以下Office 365 CLI：

```cli
spo cdn origin list
```

若要在 PowerShell 中添加源：：

```powershell
Add-SPOTenantCdnOrigin -CdnType Public -OriginUrl */CLIENTSIDEASSETS
```

若要在 CLI 中添加Office 365：

```cli
spo cdn origin add --origin */CLIENTSIDEASSETS
```

### <a name="what-powershell-modules-and-cli-shells-do-i-need-to-work-with-the-office-365-cdn"></a>我需要使用哪些 PowerShell 模块和 CLI shell 来使用Office 365 CDN？

可以选择使用 Office 365 CDN **Online 命令行** 管理程序 PowerShell 模块SharePoint或 OFFICE 365 **CLI。**

+ [SharePoint Online 命令行管理程序入门](/powershell/sharepoint/sharepoint-online/connect-sharepoint-online)
+ [安装 Office 365 CLI](https://pnp.github.io/office365-cli/user-guide/installing-cli/)

## <a name="see-also"></a>另请参阅

[内容分发网络](./content-delivery-networks.md)

[Office 365 网络计划和性能优化](./network-planning-and-performance.md)

[SharePoint性能系列 - Office 365 CDN视频系列](https://www.youtube.com/playlist?list=PLR9nK3mnD-OWMfr1BA9mr5oCw2aJXw4WA)
