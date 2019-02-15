---
title: Microsoft 托管桌面的可配置设置
description: 关于 Microsoft 托管桌面的可配置设置的信息
keywords: microsoft 托管桌面、microsoft 365、服务、文档、设置、可配置的设置
ms.service: m365-md
author: trudyha
ms.localizationpriority: normal
ms.date: 2/14/2019
ms.openlocfilehash: 54d986f37b3981200bdead30a2c232143b9dd49d
ms.sourcegitcommit: 59bc66eaa2575bad8ecb34d45b1172cda23a729b
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/14/2019
ms.locfileid: "30051083"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>可配置的设置-Microsoft 托管桌面

microsoft 托管桌面部署应用于由 Microsoft 托管桌面管理的所有设备的设置和策略。有关详细信息, 请参阅[设备配置](../service-description/device-policies.md)。

Microsoft 托管桌面中的可配置设置为 IT 管理员提供了一种自定义和部署对其组织和业务需求而言独有的设置的方法。这些设置是对由 Microsoft 托管桌面管理的设备配置设置和策略的补充。  

可配置的设置更改在云中进行, 并在定义的部署环中应用于 Microsoft 托管桌面设备。此过程类似于 Microsoft 托管桌面如何管理对设备 configuruation 设置和由该服务所定义和管理的策略所做的更改。通过使用 Microsoft 托管桌面用于部署更改的相同过程, 你将继续使用新式 IT 管理实践向前移动你的组织。

## <a name="when-to-use-configurable-settings"></a>何时使用可配置的设置？

有几次使用可配置的设置。 

**载入过程**– microsoft 托管桌面建议您在集成 Microsoft 托管桌面服务时, 或在你板载的设备 (20 或更多) 时自定义可配置的设置。设置类别是在 Microsoft 托管桌面管理门户中配置的。在载入并拥有对管理门户的访问权限后, 可以确定要为组织自定义的设置类别, 进行更改, 暂存部署, 然后部署所做的更改。

**维护设置**-定期查看您的设置并进行必要的更新。您可能需要进行更改以支持您的业务更改。   

## <a name="setting-categories"></a>设置类别

以下是可以自定义的可配置设置类别:
- [桌面背景图片](config-setting-ref.md#desktop-background-picture)–自定义 Microsoft 托管桌面设备的桌面背景图片。 
- [浏览器起始页](config-setting-ref.md#browser-start-pages)–添加要与 Microsoft Edge 一起使用的起始页。请参阅浏览器起始页
- [企业模式网站列表](config-setting-ref.md#enterprise-mode-site-list-location)-添加网站及其兼容性模式。列表中的网站将在 Internet Explorer 中启动。 
- [受信任的站点](config-setting-ref.md#trusted-sites)–添加受信任的站点并为每个站点设置安全区域。 
- [代理站点例外](config-setting-ref.md#proxy)–设置代理服务器地址编号和端口号, 并添加代理站点例外。

可以自行自定义和部署每个设置类别。您可以同时将更改部署到多个设置类别, 但是, 一次只能将一个更改部署到一个设置类别。

例如：
- 您可以同时将对桌面背景图片和受信任网站的更改部署为自己的部署。 
- 无法同时将两个部署部署到浏览器起始页。最近的部署将停止仍在进行的早期部署。

## <a name="configurable-setting-process"></a>可配置的设置过程

整个过程如下所示。 

**步骤 1-规划**-了解可配置的设置, 并决定要为组织配置哪些设置类别。规划与您的内部更改管理过程相符合您的用户的通信。例如, 如果要添加浏览器起始页, 请让你的用户知道, 在部署后, 他们将在其浏览器中添加一组新的起始页。  

**步骤 2-配置和暂存部署**-在 Microsoft 托管桌面管理门户中更改可配置的设置。暂存更改, 以便它们可以部署。请记住让你的用户了解这些更改, 以及更改将如何更改其设备体验。   

在 Microsoft 托管桌面管理门户中配置和暂存更改。有关详细信息, 请参阅[自定义可配置设置](config-setting-ref.md)。 

**第3步-传达更改**传达有关即将到来的用户更改的信息。对于每个部署, 完成属于更改管理过程的通信。您应清楚地传达影响用户工作方式或他们在设备上将看到的内容的任何更改。

**步骤 4-部署更改**–部署更改 (从测试环开始)。通过测试环, 可以在将更改部署到较大的设备组之前, 使用较少的设备验证和解决任何问题。如果遇到任何问题, 您可以还原更改、更新设置并暂存新的部署。Microsoft 托管桌面建议您遵循结构化方法并按以下顺序将其部署到环: Test、First、Fast 和广义。   

所有可配置的设置均使用 Microsoft 托管桌面管理门户进行管理。有关详细信息, 请参阅[部署更改](config-setting-deploy.md)。 

**步骤 5-跟踪更改**–跟踪部署状态更改的进度。对于每个设置, 您可以执行以下操作:
- **跟踪进度**–在部署更改后跟踪状态。状态将更改为 "**正在进行中**", 然后**完成**或**失败**。如果部署失败, 将自动为 Microsoft 托管桌面操作打开支持请求, 以调查问题。  
- **请参阅已部署版本**–每个部署的更改都有版本号。
- **还原**更改–还原更改将停止当前部署, 并将所有响铃还原为所有已部署到所有环的最后更改。您正在回滚到上一个已知良好的设置值。
- **Validatie cahnges** -部署完成后, 验证更改是否按预期应用。  

如果部署失败, 或者您无法还原更改, 请使用 Microsoft 托管桌面操作[打开支持请求](admin-support.md)。 

有关详细信息, 请参阅[部署和跟踪可配置的设置](config-setting-deploy.md)。

## <a name="additional-resources"></a>其他资源
- [可配置的设置参考](config-setting-ref.md) 
- [部署可配置的设置](config-setting-deploy.md) 