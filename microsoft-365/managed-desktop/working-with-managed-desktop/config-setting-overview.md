---
title: 可配置Microsoft 托管桌面
description: 有关可配置设置的信息Microsoft 托管桌面
keywords: Microsoft 托管桌面、Microsoft 365、服务、文档、设置、可配置设置
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 910bd8d37853ce70acb6379599b0259446b0752e
ms.sourcegitcommit: 2c3b737e71038f843ef9e9ff4d5b99d6110b8ec5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/28/2022
ms.locfileid: "62265663"
---
# <a name="configurable-settings---microsoft-managed-desktop"></a>可配置的设置 - Microsoft 托管桌面

Microsoft 托管桌面部署应用于由设备管理的所有设备的设置和Microsoft 托管桌面。 有关详细信息，请参阅设备 [配置](../service-description/device-policies.md)。

it 中的可配置Microsoft 托管桌面为 IT 管理员提供了一种自定义和部署其组织和业务需求所特有的设置的方法。 这些设置是设备配置设置和策略之外，由 Microsoft 托管桌面。  

在云中进行可配置的设置更改。 它们适用于定义的部署Microsoft 托管桌面的设备。 此过程类似于管理Microsoft 托管桌面定义和管理的设备配置设置和策略的更改的方式。 通过使用与部署更改Microsoft 托管桌面相同的过程，您可以使用现代 IT 管理实践继续推进组织。

## <a name="when-to-use-configurable-settings"></a>何时使用可配置设置？

在下列方案中使用可配置设置：

| 应用场景 | 说明 |
| ------ | ------ |
| 载入过程 | Microsoft 托管桌面在载入 Microsoft 托管桌面 服务时，或者当你在 (20 台或更多的设备上载入大量设备时，) 。 <br><br>在管理门户中配置Microsoft 托管桌面类别。 载入并有权访问管理门户后，你可以决定要为组织自定义哪些设置类别。 After， make the changes， stage a deployment， and then deploy your changes. |
| 维护设置 | 定期查看你的设置，并进行所需的更新。 你可能需要进行更改以支持业务中的更改。 |

## <a name="setting-categories"></a>设置类别

以下是可自定义的可配置设置类别：

| 类别 | 说明 |
| ------ | ------ |
| [桌面背景图片](config-setting-ref.md#desktop-background-picture) | 自定义桌面设备Microsoft 托管桌面图片。 |
| [浏览器起始页](config-setting-ref.md#browser-start-pages) | 添加起始页以用于Microsoft Edge。 |
| [Enterprise模式站点列表](config-setting-ref.md#enterprise-mode-site-list-location) | 添加站点及其兼容性模式。 该列表上的网站将在Internet Explorer。 |
| [受信任的站点](config-setting-ref.md#trusted-sites) | 添加受信任的站点并设置每个站点的安全区域。 |
| [代理站点异常](config-setting-ref.md#proxy) | 设置代理服务器地址号和端口号，并添加代理站点例外。 |

可以自定义和部署每个设置类别。 可以同时部署对多个设置类别的更改。 但是，一次只能将一个更改部署到设置类别。

例如：

- 你可以同时将更改部署到桌面背景图片和受信任的站点，每个更改都作为它们自己的部署。
- 不能同时将两个部署部署到浏览器起始页。 最新部署将停止仍在进行中的早期部署。

## <a name="configurable-setting-process"></a>可配置的设置过程

Microsoft 托管桌面组织使用可配置设置时，建议遵循如下流程：

| 步骤  | 流程 |
| ------ | ------ |
| **步骤 1：规划** | <ol type="1"><li>了解可配置的设置，并决定要为组织配置的设置类别。</li> <li>当您希望将更改部署到每个组时，请创建日程表。</li> <li>规划与符合内部变更管理流程的用户的通信。 例如，如果要添加浏览器起始页，请通知用户部署后，浏览器中将包含一组新的起始页。</li></ol> |
| **步骤 2：配置和阶段部署** | <ol type="1"><li>在管理门户中更改Microsoft 托管桌面设置。</li><li>将更改阶段，以便它们已准备好进行部署。</li> <li>请记住，告知用户更改以及更改将如何更改其设备体验。</li><li>在管理门户中配置Microsoft 托管桌面更改。 有关详细信息，请参阅自定义 [可配置设置](config-setting-ref.md)。</li></ol>|
| **步骤 3：传达更改** | <ol type="1"><li>向用户传达有关即将进行的更改的信息。</li> <li>对于每个部署，完成属于变更管理流程的通信。 你应该清楚地传达影响用户工作方式的任何更改，或者他们将在设备上看到的信息。</li></ol> |
| **步骤 4：部署更改** | 部署更改，从测试组开始。 通过测试组，可以在将更改部署到较大的设备组之前，验证和排查设备较少的组中任何问题。 <br><br>如果遇到任何问题，可以还原更改、更新设置和阶段新部署。 Microsoft 托管桌面遵循结构化方法，并按以下顺序部署到组：Test、First、Fast 和 Broad。 <br><br>所有可配置设置均使用管理Microsoft 托管桌面管理门户进行管理。 有关详细信息，请参阅部署 [更改](config-setting-deploy.md)。 |
| **步骤 5：跟踪更改** | 在"部署状态"部分跟踪更改的进度。 对于每个设置，你可以： <ul><li>**跟踪进度：**  部署更改后跟踪状态。 状态将更改为"正在进行 **"**，然后 **更改为"完成**"或"失败 **"**。 如果部署失败，将自动打开支持请求，Microsoft 托管桌面操作调查问题。</li> <li>**请参阅部署的版本：** 每个部署的更改都有一个版本号。</li><li>**还原更改：** 还原更改将停止当前部署。 它将所有组恢复为部署到所有组的最后一次更改。 你将回滚到上一个已知良好的设置值。</li><li>**验证更改：** 部署完成后，验证更改是否如预期一样应用。</li></ul> |

如果部署失败，或者无法还原更改，请通过"操作"[](admin-support.md)打开Microsoft 托管桌面请求。

有关详细信息，请参阅部署 [和跟踪可配置设置](config-setting-deploy.md)。

## <a name="additional-resources"></a>其他资源

- [可配置设置参考](config-setting-ref.md)
- [部署可配置设置](config-setting-deploy.md)
