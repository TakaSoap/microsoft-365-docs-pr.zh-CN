---
title: Office for Mac 中的网络请求
ms.author: kvice
author: kelleyvice-msft
manager: laurawi
ms.date: 11/9/2018
audience: ITPro
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection: Ent_O365
f1.keywords:
- CSH
ms.custom:
- Adm_O365_Setup
- seo-marvel-apr2020
search.appverid: MOM160
ms.assetid: afdae969-4046-44b9-9adb-f1bab216414b
description: 本文介绍应用程序尝试Office for Mac终结点和 URL，以及提供的服务。
ms.openlocfilehash: 37071b0aaf9e6f172d99a10cb4a1506f1627ef03
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177071"
---
# <a name="network-requests-in-office-for-mac"></a>Office for Mac 中的网络请求

Office for Mac应用程序在 macOS 平台上提供本机应用体验。 每个应用都设计为适用于各种方案，包括当网络访问不可用时状态。 当计算机连接到网络时，应用程序会自动连接到一系列基于 Web 的服务以提供增强功能。 以下信息描述了应用程序尝试到达的终结点和 URL，以及提供的服务。 此信息在解决网络配置问题和为网络代理服务器设置策略时很有用。 本文中的详细信息旨在补充 Office 365 [URL](urls-and-ip-address-ranges.md)和地址范围文章，其中包括运行 Microsoft Windows 的计算机的Windows。 除非另有说明，否则本文中的信息也适用于 Office 2019 for Mac 和 Office 2016 for Mac，可从零售商店或批量许可协议进行一次购买。 

  
本文中的大多数内容是详细介绍该终结点提供的服务或功能的网络 URL、类型和说明的表。 每个 Office应用在其服务和终结点使用情况方面可能有所不同。 下表定义了以下应用：
  
- W：Word
- P：PowerPoint
- X：Excel
- O：Outlook
- N：OneNote
   
URL 类型定义如下：
  
- ST：静态 - URL 硬编码到客户端应用程序中。
    
- SS：Semi-Static - URL 作为网页或重定向器的一部分进行编码。
    
- CS：配置服务 - URL 作为 Office Configuration Service 的一部分返回。

    
## <a name="office-for-mac-default-configuration"></a>Office for Mac默认配置

 **安装和更新**
  
以下网络终结点用于从 Microsoft Office for Mac下载 内容分发网络 (CDN) 。
  
|**URL**|**类型**|**说明**|
|:-----|:-----|:-----|
|```https://go.microsoft.com/fwlink/```  <br/> |ST  <br/> |Microsoft 365安装门户将服务转发到最新的安装程序包。  <br/> |
|```https://officecdn-microsoft-com.akamaized.net/```  <br/> |SS  <br/> |安装程序包在内容分发网络。  <br/> |
|```https://officecdn.microsoft.com/```  <br/> |SS  <br/> |安装程序包在内容分发网络。  <br/> |
|```https://officeci-mauservice.azurewebsites.net/```  <br/> |ST  <br/> |Microsoft AutoUpdate 的管理控制终结点  <br/> |
   
 **首次应用启动**
  
首次启动客户端时，将联系以下Office 应用。 这些终结点为用户提供Office增强功能，并且无论许可证类型如何，都会联系 URL (包括批量许可证安装) 。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://config.edge.skype.com/```  <br/> |WXPON  <br/> |ST  <br/> |"飞行"配置 - 允许功能启动和实验。  <br/> |
|```https://ocos-office365-s2s.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |"正在测试"网络配置测试  <br/> |
|```https://client-office365-tas.msedge.net/```  <br/> |WXPON  <br/> |ST  <br/> |"正在测试"网络配置测试  <br/> |
|```https://officeclient.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office配置服务 - 服务终结点的主列表。  <br/> |
|```https://nexusrules.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office规则 遥测下载 - 通知客户端要上载到遥测服务的数据和事件。  <br/> |
|```https://mobile.pipe.aria.microsoft.com/```  <br/> |网络  <br/> |CS  <br/> |OneNote遥测服务  <br/> |
|```https://nexus.officeapps.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |Office遥测Upload报告 - 客户端上发生的"Heartbeart"和错误事件将上载到遥测服务。  <br/> |
|```https://templateservice.office.com/```  <br/> |WXP  <br/> |CS  <br/> |Office模板服务 - 为用户提供联机文档模板。  <br/> |
|```https://omextemplates.content.office.net/```  <br/> |WXP  <br/> |CS  <br/> |Office模板下载 - 存储 PNG 模板图像。  <br/> |
|```https://store.office.com/```  <br/> |WXP  <br/> |CS  <br/> |应用商店应用的Office配置。  <br/> |
|```https://odc.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |Office文档集成服务目录 (主领域发现中的服务和) 列表。  <br/> |
|```https://cdn.odc.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |家庭领域发现 v2 (15.40 及更高版本)   <br/> |
|```https://officecdn.microsoft.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft AutoUpdate 清单 - 检查是否有可用的更新  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |WXPO  <br/> |SS  <br/> |Microsoft Ajax JavaScript 库  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |用于配置Office的维基百科应用程序。  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |必应映射应用Office配置和资源。  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |用户Graph应用Office配置和资源。  <br/> |
|```https://www.onenote.com/```  <br/> |网络  <br/> |ST  <br/> |What's New content for OneNote.  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |网络  <br/> |ST  <br/> |新内容OneNote。  <br/> |
|```https://site-cdn.onenote.net/```  <br/> |网络  <br/> |SS  <br/> |What's New images for OneNote.  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |ST  <br/> |应用内支持服务。  <br/> |
|```https://prod-global-autodetect.acompli.net/```  <br/> |O  <br/> |ST  <br/> |电子邮件帐户检测服务。  <br/> |
|```https://autodiscover-s.outlook.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook自动发现  <br/> |
|```https://outlook.office365.com/```  <br/> |WXPO  <br/> |ST  <br/> |Outlook服务Microsoft 365终结点。  <br/> |
|```https://r1.res.office365.com/```  <br/> |O  <br/> |ST  <br/> |加载项Outlook图标。  <br/> |
   
> [!NOTE]
> Office配置服务充当所有客户端的自动发现Microsoft Office，而不仅是 Mac 客户端。 响应中返回的终结点是半静态的，该更改很少发生，但仍可能。 
  
 **登录**
  
登录基于云的存储时，将联系以下网络终结点。 根据你的帐户类型，可能会联系不同的服务。 例如：
  
- **MSA：Microsoft 帐户** - 通常用于消费者和零售方案 
    
- **OrgID：组织帐户** - 通常用于商业方案 
    
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://login.windows.net/```  <br/> |WXPON  <br/> |ST  <br/> |Windows授权服务  <br/> |
|```https://login.microsoftonline.com/```  <br/> |WXPON  <br/> |ST  <br/> |Microsoft 365OrgID (登录服务)   <br/> |
|```https://login.live.com/```  <br/> |WXPON  <br/> |ST  <br/> |MICROSOFT 帐户登录服务 (MSA)   <br/> |
|```https://auth.gfx.ms/```  <br/> |WXPON  <br/> |CS  <br/> |MICROSOFT 帐户登录服务帮助程序 (MSA)   <br/> |
|```https://secure.aadcdn.microsoftonline-p.com/```  <br/> |WXPON  <br/> |SS  <br/> |Microsoft 365OrgID (登录)   <br/> |
|```https://ocws.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |文档和位置存储定位器  <br/> |
|```https://roaming.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |MRU (文档) 最近使用过的库  <br/> |
   
> [!NOTE]
> 对于基于订阅的许可证和零售许可证，登录将激活产品，并启用对云资源（如 OneDrive）的访问。 对于批量许可证安装，默认情况下) 仍提示用户登录 (，但这仅对云资源的访问权限是必需的，因为产品已激活。 
  
 **产品激活**
  
以下网络终结点适用于Microsoft 365订阅和零售许可证激活。 具体来说，这不适用于批量许可证安装。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://ols.officeapps.live.com/```  <br/> |WXPON  <br/> |CS  <br/> |Office 许可服务  <br/> |
   
 **新增内容**
  
以下网络终结点仅适用于Microsoft 365订阅。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://contentstorage.osi.office.net/```  <br/> |WXPO  <br/> |SS  <br/> |新增 JSON 页面内容。  <br/> |
   
 **研究工具**
  
以下网络终结点仅适用于Microsoft 365订阅。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |研究 Web 服务  <br/> |
|```https://cdn.entity.osi.office.net/```  <br/> |W  <br/> |CS  <br/> |研究静态内容  <br/> |
|```https://www.bing.com/```  <br/> |W  <br/> |CS  <br/> |研究内容提供程序  <br/> |
   
 **智能查找**
  
以下网络终结点适用于订阅Microsoft 365零售/批量许可证激活。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://uci.officeapps.live.com/```  <br/> |WXPN  <br/> |CS  <br/> |InsightsWeb 服务  <br/> |
|```https://ajax.googleapis.com/```  <br/> |WXPN  <br/> |CS  <br/> |JQuery 库  <br/> |
|```https://cdnjs.cloudflare.com/```  <br/> |WXPN  <br/> |CS  <br/> |支持 JavaScript 库  <br/> |
|```https://www.bing.com/```  <br/> |WXPN  <br/> |CS  <br/> |Insights内容提供程序  <br/> |
|```https://tse1.mm.bing.net/```  <br/> |WXPN  <br/> |CS  <br/> |Insights内容提供程序  <br/> |
   
 **PowerPoint 设计器**
  
以下网络终结点仅适用于Microsoft 365订阅。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://pptsgs.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPoint设计器 Web 服务  <br/> |
   
 **PowerPoint 快速启动**
  
以下网络终结点仅适用于Microsoft 365订阅。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://pptcts.officeapps.live.com/```  <br/> |P  <br/> |CS  <br/> |PowerPointQuickStarter Web 服务  <br/> |
   
 **发送笑脸/笑脸**
  
以下网络终结点适用于订阅Microsoft 365零售/批量许可证激活。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://sas.office.microsoft.com/```  <br/> |WXPON  <br/> |CS  <br/> |发送笑脸服务  <br/> |
   
 **联系支持人员**
  
以下网络终结点适用于订阅Microsoft 365零售/批量许可证激活。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://powerlift-frontdesk.acompli.net/```  <br/> |O  <br/> |CS  <br/> |联系支持服务  <br/> |
|```https://acompli.helpshift.com/```  <br/> |O  <br/> |CS  <br/> |应用内支持服务  <br/> |
   
 **另存为 PDF**
  
以下网络终结点适用于订阅Microsoft 365零售/批量许可证激活。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://wordcs.officeapps.live.com/```  <br/> |W  <br/> |CS  <br/> |Word 文档转换服务 (PDF)   <br/> |
   
 **Office应用 (加载项)**
  
以下网络终结点适用于Microsoft 365应用加载项受信任时Office订阅和零售/批量许可证激活。
  
|**URL**|**应用**|**类型**|**说明**|
|:-----|:-----|:-----|:-----|
|```https://store.office.com/```  <br/> |WXPO  <br/> |CS  <br/> |Office 应用存储配置  <br/> |
|```https://wikipedia.firstpartyapps.oaspapps.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia 应用程序资源  <br/> |
|```https://excelbingmap.firstpartyapps.oaspapps.com/```  <br/> |X  <br/> |SS  <br/> |必应映射应用资源  <br/> |
|```https://peoplegraph.firstpartyapps.oaspapps.com```  <br/> |X  <br/> |SS  <br/> |人员Graph应用资源  <br/> |
|```https://o15.officeredir.microsoft.com/```  <br/> |WPX  <br/> |SS  <br/> |Office重定向服务  <br/> |
|```https://appsforoffice.microsoft.com/```  <br/> |WXP  <br/> |SS  <br/> |OfficeJavaScript 库  <br/> |
|```https://telemetry.firstpartyapps.oaspapps.com/```  <br/> |WX  <br/> |SS  <br/> |适用于应用程序遥测和报告Office服务  <br/> |
|```https://ajax.microsoft.com/```  <br/> |W  <br/> |SS  <br/> |Microsoft Ajax JavaScript 库  <br/> |
|```https://ajax.aspnetcdn.com/```  <br/> |X  <br/> |SS  <br/> |Microsoft Ajax JavaScript 库  <br/> |
|```https://c.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |OfficeJavaScript 库  <br/> |
|```https://c1.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |支持资源  <br/> |
|```https://cs.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |支持资源  <br/> |
|```https://c.bing.com/```  <br/> |WPXO  <br/> |SS  <br/> |支持资源  <br/> |
|```https://*.cdn.optimizely.com/```  <br/> |WPXO  <br/> |SS  <br/> |JavaScript 库  <br/> |
|```https://errors.client.optimizely.com/```  <br/> |WPX  <br/> |SS  <br/> |错误报告  <br/> |
|```https://*-contentstorage.osi.office.net/```  <br/> |WPXO  <br/> |SS  <br/> |字体资源  <br/> |
|```https://nexus.ensighten.com/```  <br/> |WPXO  <br/> |SS  <br/> |遥测服务  <br/> |
|```https://browser.pipe.aria.microsoft.com/```  <br/> |WPXO  <br/> |SS  <br/> |遥测报告  <br/> |
|```https://*.vo.msecnd.net/```  <br/> |WPXO  <br/> |SS  <br/> |Microsoft Store资源库  <br/> |
|```https://*.wikipedia.org/```  <br/> |W  <br/> |SS  <br/> |维基百科页面资源  <br/> |
|```https://upload.wikimedia.org/```  <br/> |W  <br/> |SS  <br/> |维基百科媒体资源  <br/> |
|```https://wikipedia.firstpartyappssandbox.oappseperate.com/```  <br/> |W  <br/> |SS  <br/> |Wikipedia 沙盒框架  <br/> |
|```https://*.virtualearth.net/```  <br/> |X  <br/> |SS  <br/> |地图模板  <br/> |
   
 **安全链接**
  
以下网络终结点仅适用于 Office 订阅Microsoft 365应用程序。
  
|**URL**|**类型**|**说明**|
|:-----|:-----|:-----|
|```https://*.oscs.protection.outlook.com/```  <br/> |CS  <br/> |Microsoft 保险箱 Link Service  <br/> |
   
 **崩溃报告**
  
以下网络终结点适用于所有 Office 应用程序，Microsoft 365订阅和零售/批量许可证激活。 当进程意外崩溃时，将生成报告并发送到 Watson 服务。
  
|**URL**|**类型**|**说明**|
|:-----|:-----|:-----|
|```https://watson.microsoft.com/```  <br/> |ST  <br/> |Microsoft 错误报告服务  <br/> |
|```https://officeci.azurewebsites.net/```  <br/> |ST  <br/> |Office协作Insights服务  <br/> |
   
## <a name="options-for-reducing-network-requests-and-traffic"></a>用于减少网络请求和流量的选项

默认配置Office for Mac在功能方面和使计算机保持最新状态方面提供最佳用户体验。 在某些情况下，你可能希望阻止应用程序联系网络终结点。 本节讨论执行此操作的选项。
  
 ### <a name="disabling-cloud-sign-in-and-office-add-ins"></a>禁用云Sign-In Office Add-Ins
  
批量许可客户可能有关于将文档保存至基于云的存储的严格策略。 可以设置以下每个应用程序首选项以禁用 MSA/OrgID 登录，并访问Office外接程序。
  
- ```defaults write com.microsoft.Word UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Excel UseOnlineContent -integer 0```

- ```defaults write com.microsoft.Powerpoint UseOnlineContent -integer 0```

如果用户尝试访问 Sign-In 函数，将看到网络连接不存在的错误。 由于此首选项还会阻止联机产品激活，因此它应仅用于批量许可证安装。 具体而言，使用此首选项Office访问以下终结点：
  
- ```https://odc.officeapps.live.com```
    
- ```https://*.firstpartyapps.oaspapps.com```
    
- 上面"登录"部分中列出的所有终结点。
    
- 上面"智能查找"部分中列出的所有终结点。
    
- 上面"产品激活"部分中列出的所有终结点。
    
- 上面"Office应用 (加载项"部分) 所有终结点。
    
若要重新为用户建立完整功能，请设置首选项"2"或删除它。
  
> [!NOTE]
> 此首选项要求Office for Mac版本 15.25 [160726] 或更高版本。 
  
### <a name="telemetry"></a>遥测
  
Office for Mac定期将遥测信息发送回 Microsoft。 数据将上载到"Nexus"终结点。 遥测数据可帮助工程团队评估每个项目运行状况和任何意外Office 应用。 遥测分为两类：
  
- **检测** 信号包含版本和许可证信息。 此数据将在应用启动后立即发送。 
    
- **用法** 包含有关如何使用应用和非致命错误的信息。 此数据每 60 分钟发送一次。 
    
Microsoft 非常重视你的隐私。 可以在 上了解 Microsoft 的数据收集策略 [https://privacy.microsoft.com](https://privacy.microsoft.com) 。 若要阻止应用程序发送"使用情况"遥测，可以调整 **SendAllTelemetryEnabled** 首选项。 首选项是按应用程序设置的，可以通过 macOS 配置文件进行设置，也可以从终端手动设置： 
  
```defaults write com.microsoft.Word SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Excel SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Powerpoint SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Outlook SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.onenote.mac SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.autoupdate2 SendAllTelemetryEnabled -bool FALSE```

```defaults write com.microsoft.Office365ServiceV2 SendAllTelemetryEnabled -bool FALSE```

检测信号遥测始终发送且无法禁用。
  
### <a name="crash-reporting"></a>崩溃报告
  
发生致命应用程序错误时，应用程序将意外终止，并上载故障报告到"Watson"服务。 崩溃报告由调用堆栈组成，这是应用程序在处理导致崩溃的步骤列表。 这些步骤可帮助工程团队确定失败的确切功能及其原因。
  
在某些情况下，文档的内容将导致应用程序崩溃。 如果应用将文档标识为原因，它将询问用户是否还可以随调用堆栈一起发送文档。 用户可以对此问题做出明智的选择。 IT 管理员可能对文档传输有严格的要求，并代表用户决定从不发送文档。 以下首选项可以设置为阻止发送文档，以及禁止向用户显示提示：
  
```defaults write com.microsoft.errorreporting IsAttachFilesEnabled -bool FALSE```

> [!NOTE]
> 如果将 **SendAllTelemetryEnabled** 设置为 **FALSE，** 则禁用该进程的所有崩溃报告。 若要启用故障报告而不发送使用情况遥测，可以设置以下首选项： ```defaults write com.microsoft.errorreporting IsMerpEnabled -bool TRUE``` 
  
### <a name="updates"></a>更新
  
Microsoft 会Office for Mac定期发布更新 (通常每月发布一) 。 我们强烈建议用户和 IT 管理员使计算机保持最新，以确保安装了最新的安全修补程序。 当 IT 管理员希望严格控制和管理计算机更新时，可以设置以下首选项以防止 AutoUpdate 过程自动检测和提供产品更新：
  
```defaults write com.microsoft.autoupdate2 HowToCheck -string 'Manual'```

### <a name="blocking-requests-with-a-firewallproxy"></a>使用防火墙/代理阻止请求
  
如果组织阻止通过防火墙或代理服务器对 URL 的请求，请确保将本文档中列出的 URL 配置为允许，或阻止以 40X 响应 (例如 403 或 404) 。 40X 响应将允许 Office 应用程序正常接受无法访问资源，并且提供更快的用户体验，而不是直接放弃连接，这反过来会导致客户端重试。
  
如果代理服务器需要身份验证，407 响应将返回到客户端。 为了获得最佳体验，请确保使用的是 Office for Mac 版本 15.27 或更高版本，因为它们包含使用 NTLM 和 Kerberos 服务器的特定修补程序。
  
  
## <a name="see-also"></a>另请参阅

[Office 365 URL 和 IP 地址范围](urls-and-ip-address-ranges.md)

