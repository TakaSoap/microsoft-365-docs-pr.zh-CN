---
title: 可配置Microsoft 托管桌面
description: 有关可配置设置的信息Microsoft 托管桌面
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、设置、可配置设置
ms.service: m365-md
author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: a83181d6b0fa33b0eb432627530099b316ebb617
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60150350"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>可配置的设置 - Microsoft 托管桌面

Microsoft 托管桌面部署应用于由设备管理的所有设备的设置Microsoft 托管桌面。 有关详细信息，请参阅设备 [配置](../service-description/device-policies.md)。

it admins Microsoft 托管桌面 settings in it admins to customize and deploy settings that are unique to their organization and business needs. 这些设置是设备配置设置和策略之外，由 Microsoft 托管桌面。  

可配置的设置更改在云中进行，并应用于Microsoft 托管桌面部署组内的设备。 此过程类似于管理Microsoft 托管桌面定义和管理的设备配置设置和策略的更改的方式。 通过使用与部署更改Microsoft 托管桌面相同的过程，您可以使用现代 IT 管理实践继续推进组织。

## <a name="when-to-use-configurable-settings"></a>何时使用可配置设置？

有几次可以使用可配置设置。 

载入过程 **–** Microsoft 托管桌面建议你在载入 Microsoft 托管桌面 服务时或当你在 (20 台或更多的设备上载入大量设备时自定义可配置) 。 在管理门户中配置Microsoft 托管桌面类别。 载入并有权访问管理门户后，可以决定要为组织自定义哪些设置类别，进行更改，部署阶段，然后部署更改。

**维护设置** - 定期查看设置并进行所需更新。 你可能需要进行更改以支持业务中的更改。   

## <a name="setting-categories"></a>设置类别

你可以自定义以下可配置设置类别：
- [桌面背景图片](config-setting-ref.md#desktop-background-picture)– 自定义桌面设备Microsoft 托管桌面图片。 
- [浏览器起始页](config-setting-ref.md#browser-start-pages)– 添加要用于浏览器Microsoft Edge。 请参阅浏览器起始页
- [Enterprise模式站点列表](config-setting-ref.md#enterprise-mode-site-list-location)– 添加站点及其兼容性模式。 该列表上的网站将在Internet Explorer。 
- [受信任的站点](config-setting-ref.md#trusted-sites) – 添加受信任的站点并设置每个站点的安全区域。 
- [代理站点例外](config-setting-ref.md#proxy) – 设置代理服务器地址号和端口号，并添加代理站点例外。

可以自定义和部署每个设置类别。 您可以同时部署对多个设置类别的更改，但是，一次只能将一个更改部署到一个设置类别。

例如：
- 你可以同时将更改部署到桌面背景图片和受信任的站点，每个更改都作为它们自己的部署。 
- 不能同时将两个部署部署到浏览器起始页。 最新部署将停止仍在进行中的早期部署。

## <a name="configurable-setting-process"></a>可配置的设置过程

Microsoft 托管桌面利用组织的可配置设置时，建议遵循以下类似过程：

**步骤 1 - 计划** - 了解可配置的设置，并决定要为组织配置的设置类别。 为希望将更改部署到每个组的时间创建日程表。 规划与符合内部变更管理流程的用户的通信。 例如，如果要添加浏览器起始页，请告知用户部署后，浏览器中将包含一组新的起始页。  

**步骤 2 - 配置和阶段部署**- 在管理门户中更改Microsoft 托管桌面设置。 将更改阶段，以便它们已准备好进行部署。 请记住，让用户了解更改以及更改将如何更改其设备体验。   

在管理门户中配置和Microsoft 托管桌面更改。 有关详细信息，请参阅自定义 [可配置设置](config-setting-ref.md)。 

**步骤 3 - 传达更改** 向用户传达有关即将进行的更改的信息。 对于每个部署，完成属于变更管理流程的通信。 你应该清楚地传达影响用户工作方式的任何更改，或者他们将在设备上看到的信息。

**步骤 4 - 部署更改** – 部署更改，从测试组开始。 通过测试组，可以在将更改部署到较大的设备组之前，验证和排查设备较少的组中任何问题。 如果遇到任何问题，可以还原更改、更新设置和阶段新部署。 Microsoft 托管桌面遵循结构化方法，并按以下顺序部署到组：Test、First、Fast 和 Broad。   

所有可配置设置均使用管理Microsoft 托管桌面管理门户进行管理。 有关详细信息，请参阅部署 [更改](config-setting-deploy.md)。 

**步骤 5 - 跟踪更改** - 跟踪部署状态更改的进度。 对于每个设置，你可以：
- **跟踪进度** – 部署更改后跟踪状态。 状态将更改为"正在进行 **"，** 然后是 **"完成"** 或"失败 **"。** 如果部署失败，将自动打开支持请求，Microsoft 托管桌面操作调查问题。  
- **请参阅部署的版本** - 每个部署的更改都有一个版本号。
- **还原更改** – 还原更改将停止当前部署，并恢复所有组为部署到所有组的最后更改。 你将回滚到上一个已知良好的设置值。
- **验证更改** - 部署完成后，验证更改已如预期应用。  

如果部署失败，或者无法还原更改，请通过"操作"打开[](admin-support.md)Microsoft 托管桌面请求。 

有关详细信息，请参阅部署 [和跟踪可配置设置](config-setting-deploy.md)。

## <a name="additional-resources"></a>其他资源
- [可配置设置参考](config-setting-ref.md) 
- [部署可配置设置](config-setting-deploy.md) 
