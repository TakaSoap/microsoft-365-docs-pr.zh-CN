---
title: 可配置设置参考Microsoft 托管桌面
description: 设置环境中可配置设置的Microsoft 托管桌面
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 344fe8ff79976f2517e5b9b7e790193b5000803e
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150314"
---
# <a name="configurable-settings-reference---microsoft-managed-desktop"></a>可配置设置参考 - Microsoft 托管桌面

本主题列出了客户可以使用自定义设置Microsoft 托管桌面。 每个设置类别包括有关要求、最佳做法以及如何自定义设置类别的信息。 

## <a name="desktop-background-picture"></a>桌面背景图片
你可以为组织中设备Microsoft 托管桌面桌面背景图片。 可以使用它应用公司品牌或营销材料。 

### <a name="requirements"></a>要求

桌面背景图片必须满足以下要求：
- 图片文件格式 - .jpg、jpeg 或 .png
- 文件位置 - 受信任安全 http 上的主机 (https) 位置。 
- 不允许 - 不支持 http 和文件共享 (unc) 位置。 

### <a name="customize-and-deploy-desktop-background-picture"></a>自定义和部署桌面背景图片

**添加自定义桌面背景图片**
1. 登录到 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单
2. 查找"Microsoft 托管桌面"部分，选择 **"设置"。**
3. 在 **设置** 工作区中，选择 **"桌面背景图片"。** 
4. 输入想要使用的图片的位置。 
5. 选择 **"阶段** 部署"保存更改并将其部署到测试组。 

## <a name="browser-start-pages"></a>浏览器起始页
当用户启动浏览器起始页时，浏览器起始页在单个选项卡Microsoft Edge。 如果希望用户轻松打开他们经常使用的一组网站，请为每个网站添加浏览器起始页。 

### <a name="requirements"></a>要求

必须为浏览器起始页的 Intranet 或 Internet (FQDN) 完全限定域名。 如果配置了内部站点，请让用户知道，只有在办公室或通过 VPN 连接连接到内部网络时，才允许访问这些站点。 

### <a name="customize-and-deploy-browser-start-pages"></a>自定义和部署浏览器起始页

**添加浏览器起始页**
1. 登录到 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单
2. 查找"Microsoft 托管桌面"部分，选择 **"设置"。**
3. 在 **设置** 工作区中，选择 **"浏览器起始页"。** 
4. 选择 **"添加起始页"。**
5. 在 **"添加浏览器起始页**"上，输入要使用网站的 URL，然后选择"**添加起始页"。** 
6. 对其他浏览器起始页重复步骤 1-5。 
7. 选择 **"阶段** 部署"保存更改并将其部署到测试组。

## <a name="enterprise-mode-site-list-location"></a>Enterprise模式站点列表位置

如果你拥有你知道与 Microsoft Edge 存在兼容性问题的特定网站和应用，可以使用 Enterprise 模式站点列表，以便使用 Internet Explorer 11 自动打开网站。 此外，如果您知道 Intranet 站点无法正常使用 Microsoft Edge，可以将所有 Intranet 站点设置为使用 Internet Explorer 11 自动打开。 使用Enterprise模式意味着你可以继续使用 Microsoft Edge 作为默认浏览器，同时确保你的应用继续在 Internet Explorer 11 上工作。 有关企业模式站点列表详细信息，请参阅Enterprise[模式Enterprise站点列表。](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode) 

你可以指定 https:// 托管企业模式站点列表的内部共享的位置。 

### <a name="requirements"></a>要求

企业模式站点列表文件必须满足以下要求：
- 文件格式 - 满足文件要求的 XML [文件](/internet-explorer/ie11-deploy-guide/what-is-enterprise-mode#site-list-xml-file)
- 文件位置 - 内部 https 位置上的主机文件。 
- 不允许 - 不允许在内部文件共享（如 *//sharename）* 上承载

### <a name="best-practices"></a>最佳做法

提供这些最佳做法是帮助客户做出关于现代化 IT 基础结构的决策：
- **选择有限数量的网站**– Microsoft 托管桌面使用 Microsoft Edge 作为首选浏览器，以提高组织的整体安全性和用户的可用性。 此列表中的大多数网站适用于需要早期版本的浏览器（不会包含太多安全功能）的旧 Web 应用。 
- **考虑备用** – 考虑不需要较旧浏览器的不同站点或 Web 应用。 或者，请考虑更新网站，以便它可以使用较新的浏览器。 较新的浏览器使用最新的技术并帮助提高安全性。

### <a name="customize-and-deploy-enterprise-site-mode-list-location"></a>自定义和部署Enterprise模式列表位置

**添加企业站点模式列表位置**

1. 登录到 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单
2. 查找"Microsoft 托管桌面"部分，选择 **"设置"。**
3. 在 **设置** 工作区中，Enterprise **模式站点列表位置"。** 
4. 输入站点列表的 https 位置。 
5. 选择 **"阶段** 部署"保存更改并将其部署到测试组。

## <a name="trusted-sites"></a>受信任网站

受信任的站点允许您为不同网站自定义安全区域或网站可以使用的区域。 安全区域包括： 
- 区域 1 – 本地 Intranet 区域
- 区域 2 – 受信任的站点区域
- 区域 3 – Internet 区域
- 区域 4 – 受限制的站点区域

### <a name="requirements"></a>要求

提供每个受信任站点 (Intranet) Internet 站点的完全限定域名和 FQDN。 

### <a name="customize-and-deploy-trusted-sites"></a>自定义和部署受信任网站

**添加受信任网站**

1. 登录到 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单
2. 查找"Microsoft 托管桌面"部分，选择 **"设置"。**
3. 在 **设置** 工作区中，选择"**受信任的站点**"，然后选择"**添加受信任网站"。** 
4. 在 **"添加受信任网站**"上，输入 URL，选择安全区域，然后选择"**添加受信任网站"。** 
5. 对要添加的每个受信任网站重复步骤 1-4。 
6. 选择 **"阶段** 部署"保存更改并将其部署到测试组。

**删除受信任网站**

1. 登录到 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单
2. 查找"Microsoft 托管桌面"部分，选择 **"设置"。**
3. 在 **设置** 工作区中，选择 **"受信任的站点"。** 
4. 选择要删除的网站，然后选择"删除 **"。** 
5. 对要删除的每个受信任网站重复步骤 1-4。 
6. 选择 **"阶段** 部署"保存更改并将其部署到测试组。

## <a name="proxy"></a>代理
你可以管理组织的网络代理设置。 添加代理服务器和端口号，然后添加代理站点例外。 Microsoft 托管桌面包括服务运行所需的一组默认代理例外。 默认排除列表仅能由 Microsoft 托管桌面 修改。  有关详细信息，请参阅 Network [configuration for Microsoft 托管桌面](../get-ready/network.md)。 

添加到网站门户中的代理Microsoft 托管桌面添加到服务中包含的默认代理Microsoft 托管桌面例外。 

> [!NOTE]
> 更新默认代理例外列表始终比客户部署优先。 这意味着，如果存在默认代理例外列表的部署，则暂存在部署将暂停。  

### <a name="requirements"></a>要求

对于代理服务器和代理站点例外，必须满足以下要求：
- 必须是有效的服务器地址和端口号
- URL 必须是有效的 http 站点 

### <a name="customize-and-deploy-proxies"></a>自定义和部署代理

**添加单个代理站点异常**

1. 登录 ["Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并导航到 **"设备"** 菜单
2. 查找"Microsoft 托管桌面"部分，选择 **"设置"。**
3. 在 **设置** 工作区中，选择"代理 **"。** 
4. 输入 **代理服务器的地址** 和 **端口** 号，然后选择添加 **代理例外**。 
5. 输入有效 http 站点的 URL，然后选择"**添加代理异常"。** 
6. 对要添加的每个受信任网站重复步骤 1-5。 
7. 选择 **"阶段** 部署"保存更改并将其部署到测试组。

## <a name="additional-resources"></a>其他资源
- [可配置的设置概述](config-setting-overview.md) 
- [部署可配置设置](config-setting-deploy.md)