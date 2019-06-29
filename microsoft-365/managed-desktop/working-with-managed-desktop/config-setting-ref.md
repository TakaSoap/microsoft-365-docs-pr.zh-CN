---
title: Microsoft 托管桌面的可配置设置参考
description: 在 Microsoft 托管桌面中设置可配置设置的类别
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.collection: M365-modern-desktop
ms.openlocfilehash: da8f88251f6d1ae3185641dd408b29aa41cd7ea9
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390409"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>可配置的设置参考-Microsoft 托管桌面

本主题列出了客户可以使用 Microsoft 托管桌面配置的设置类别。 每个设置类别都包含有关要求、最佳实践以及如何自定义设置类别的信息。 

## <a name="desktop-background-picture"></a>桌面背景图片
您可以为组织中的 Microsoft 托管桌面设备自定义桌面背景图片。 您可以使用它来应用公司品牌或营销材料。 

### <a name="requirements"></a>要求

必须满足桌面背景图片的以下要求:
- 图片文件格式-.jpg、jpeg 或 .png
- 文件位置-主机位于受信任的安全 http (https) 位置。 
- 不允许-不支持 Http 和文件共享 (unc) 位置。 

### <a name="customize-and-deploy-desktop-background-picture"></a>自定义和部署桌面背景图片

**添加自定义桌面背景图片**
1. 登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)
2. 在 "**设置**" 下, 选择 "**可配置**"。
3. 在**可配置**的工作区中, 选择 "**桌面背景图片**"。 
4. 输入要使用的图片的位置。 
5. 选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。 

## <a name="browser-start-pages"></a>浏览器起始页
当用户启动 Microsoft Edge 时, 浏览器起始页在各个选项卡中打开。 如果您想让用户轻松打开一组经常使用的网站, 请为每个网站添加一个浏览器起始页。 

### <a name="requirements"></a>要求

您必须为您的浏览器起始页提供 intranet 或 Internet 站点的完全限定域名 (FQDN)。 如果配置了内部网站, 请让用户知道, 仅当在 office 中连接到内部网络或使用 VPN 连接进行连接时, 才允许访问这些网站。 

### <a name="customize-and-deploy-browser-start-pages"></a>自定义和部署浏览器起始页

**添加浏览器起始页**
1. 登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)
2. 在 "**设置**" 下, 选择 "**可配置**"。
3. 在**可配置**的工作区中, 选择 "**浏览器起始页**"。 
4. 选择 "**添加起始页**"。
5. 在 "**添加浏览器起始页**" 中, 输入要使用的网站的 URL, 然后选择 "**添加起始页**"。 
6. 对其他浏览器启动页重复步骤1-5。 
7. 选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。

## <a name="enterprise-mode-site-list-location"></a>企业模式网站列表位置

如果您具有与 Microsoft Edge 存在兼容性问题的特定网站和应用程序, 则可以使用企业模式网站列表, 以使用 Internet Explorer 11 自动打开网站。 此外, 如果您知道 intranet 网站不能与 Microsoft Edge 正常运行, 则可以将所有 intranet 网站设置为自动使用 Internet Explorer 11 打开。 使用企业模式意味着您可以继续将 Microsoft Edge 用作默认浏览器, 同时确保您的应用程序继续在 Internet Explorer 11 上工作。 有关企业模式网站列表的详细信息, 请参阅[企业模式和企业模式网站列表](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode)。 

您可以指定 https://位置, 也可以指定在其中承载企业模式网站列表的内部共享的位置。 

### <a name="requirements"></a>要求

企业模式网站列表文件必须满足以下要求:
- 文件格式-符合[文件要求](https://docs.microsoft.com/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)的 XML 文件
- 文件位置-主机文件位于内部 https 位置。 
- 不允许-不允许在内部文件共享 (如 *//sharename*) 上托管

### <a name="best-practices"></a>最佳做法

提供了这些最佳实践, 以帮助客户确定其 IT 基础结构的现代化:
- **选择有限数量的网站**– Microsoft 托管桌面使用 microsoft Edge 作为首选浏览器, 以提高组织的整体安全性和用户的可用性。 此列表中的大多数网站都适用于需要较旧版本的浏览器的旧版 web 应用程序, 这些应用程序不会包含任意多个安全功能。 
- **请考虑使用替代**–考虑使用不同的网站或 web 应用程序, 而无需使用较早的浏览器。 或者, 考虑更新网站, 以便它可以使用较新的浏览器。 较新的浏览器使用最新技术并帮助提高安全性。

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>自定义和部署企业网站模式列表位置

**添加企业网站模式列表位置**

1.  登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)
2.  在 "**设置**" 下, 选择 "**可配置**"。
3.  在**可配置**的工作区中, 选择 "**企业模式站点列表位置**"。 
4.  为您的网站列表输入 https 位置。 
5.  选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。

## <a name="trusted-sites"></a>受信任网站

受信任的网站允许您自定义不同网站的安全区域或网站可使用的位置。 安全区域包括: 
- 区域1–本地 Intranet 区域
- 区域2–受信任的站点区域
- 区域3– Internet 区域
- 区域4–受限制的站点区域

### <a name="requirements"></a>要求

为每个受信任的站点提供 intranet 或 Internet 站点的完全限定域名 (FQDN)。 

### <a name="customize-and-deploy-trusted-sites"></a>自定义和部署受信任的网站

**添加受信任的网站**

1. 登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)
2. 在 "**设置**" 下, 选择 "**可配置**"。
3. 在**可配置**的工作区中, 选择 "**受信任的站点**", 然后选择 "**添加可信站点**" 
4. 在 "**添加受信任站点**" 中, 输入 URL, 选择安全区域, 然后选择 "**添加受信任的站点**"。 
5. 对要添加的每个受信任站点重复步骤1-4。 
6. 选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。

**删除受信任的网站**

1. 登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)
2. 在 "**设置**" 下, 选择 "**可配置**"。
3. 在**可配置**的工作区中, 选择 "**受信任站点**"。 
4. 选择要删除的网站, 然后选择 "**删除**"。 
5. 对要删除的每个受信任站点重复步骤1-4。 
6. 选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。

## <a name="proxy"></a>代理
您可以管理您的组织的网络代理设置。 添加代理服务器和端口号, 然后添加代理站点例外。 Microsoft 托管桌面包括一组用于运行服务所需的默认代理异常。 默认的排除列表仅可由 Microsoft 托管桌面服务进行修改。  有关详细信息, 请参阅[Microsoft 托管桌面的网络配置](../get-ready/network.md)。 

在 Microsoft 托管桌面门户中添加的代理站点例外将添加到 Microsoft Managed Desktop service 中包含的默认代理例外。 

> [!NOTE]
> 更新默认代理例外列表始终优先于客户部署。 这意味着, 如果为默认代理例外列表部署, 则将暂停暂存部署。  

### <a name="requirements"></a>要求

对于代理服务器和代理站点例外, 必须满足以下要求:
- 必须是有效的服务器地址和端口号
- Url 必须是有效的 http 站点 

### <a name="customize-and-deploy-proxies"></a>自定义和部署代理

**添加单个代理站点例外**

1. 登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)
2. 在 "**设置**" 下, 选择 "**可配置**"。
3. 在**可配置**的工作区中, 选择 "**代理**"。 
4. 输入代理服务器的**地址**和**端口号**, 然后选择 "**添加代理例外**"。 
5. 输入有效的 http 站点的 URL, 然后选择 "**添加代理例外**"。 
6. 对要添加的每个受信任站点重复步骤1-5。 
7. 选择 "**暂存部署**" 以保存所做的更改, 并将其部署到测试组。

## <a name="additional-resources"></a>其他资源
- [可配置的设置概述](config-setting-overview.md) 
- [部署可配置的设置](config-setting-deploy.md)
