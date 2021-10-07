---
title: 多地理位置环境中的用户体验
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.collection:
- SPO_Content
- Strat_SP_gtc
f1.keywords:
- NOCSH
ms.custom: seo-marvel-apr2020
ms.localizationpriority: medium
description: 了解 Microsoft 365 多地理位置环境中的 SharePoint、OneDrive 和 Exchange 用户体验。
ms.openlocfilehash: eff55ba327e1484b5aa3fd344f904c0e11f8f954
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60177143"
---
# <a name="user-experience-in-a-multi-geo-environment"></a>多地理位置环境中的用户体验

下面是用户将在 OneDrive 多地理位置配置中看到的内容：

## <a name="exchange-mailbox"></a>Exchange 邮箱

用户的 Exchange 邮箱预配到首选数据位置，并在 PDL 更改后自动重新定位。 用户通常可以在多地理位置环境中使用 Outlook 和 Outlook 网页版，用户体验没有变化。

## <a name="hub-sites"></a>中心网站

SharePoint 中心网站增强了员工的内容发现和参与能力，同时还能完整、一致地表示项目、部门或地区。 在多地理位置环境中，附属位置中的网站可以与中心网站轻松关联，无论中心网站的地理位置如何。 用户可以通过一种搜索体验，跨中心网站搜索并获取结果，无论网站的地理位置如何。

## <a name="microsoft-365-app-launcher"></a>Microsoft 365 应用启动器

应用启动器可感知多地理位置，并将每个磁贴定向到工作负荷的相应地理位置。 SharePoint 和 OneDrive 磁贴将用户指向与用户的已预配地理位置对应的位置。 也就是说，用户在中心位置有 OneDrive，用户的 SharePoint 磁贴会将他们指向中心位置中的 SP 主页，但组网站会在与用户 PDL 对应的位置中进行预配。 

## <a name="office-applications"></a>Office 应用程序

Office Word、Excel 和 PowerPoint 等应用程序将自动检测每个用户登录OneDrive的正确地理位置。 用户无需输入 OneDrive 或 SharePoint 网站的地理位置专用 URL。

## <a name="onedrive-sync-app"></a>OneDrive 同步应用

OneDrive 同步应用 (版本 17.3.6943.0625 及更高版本) 将自动为用户检测正确的 OneDrive 地理位置。 同步应用支持包括同步基于组的网站（无论其地理位置如何）的能力。 请注意，多地理位置不支持 Groove 同步客户端。 

## <a name="onedrive-location"></a>OneDrive位置

用户将在首选OneDrive预配其数据配置。 如果用户导航到包含错误地理位置 (的 OneDrive URL（如上一地理位置) 中的书签）时，他们会自动重定向到相应地理位置中的 OneDrive。

## <a name="onedrive-ios-and-android"></a>OneDrive iOS 和 Android 

OneDrive iOS 和 Android 移动应用将向你显示你的 OneDrive 文件和与你共享的文件，无论你的地理位置如何。从 OneDrive 移动应用搜索将显示来自所有地理位置的相关结果。请下载这些应用的最新版本。

有关详细信息，请参阅使用 [iOS 上的 OneDrive](https://support.office.com/article/08d5c5b2-ccc6-40eb-a244-fe3597a3c247) 和[使用适用于 Android 的 OneDrive](https://support.office.com/article/eee1d31c-792d-41d4-8132-f9621b39eb36)。

## <a name="onedrive-mobile-client"></a>OneDrive 移动客户端 

OneDrive 移动客户端可感知多地理位置，并显示来自所有地理位置的相关内容和结果。

## <a name="search"></a>搜索

每个地理位置都有自己的搜索索引和搜索中心。 当用户搜索时，查询将发送到所有地理位置，并合并返回的结果，然后进行排名，以便用户获得统一的结果。 用户从所有地理位置获取结果，而不考虑自己的地理位置。 请参阅[配置搜索OneDrive Multi-Geo](configure-search-for-multi-geo.md)了解具体信息。

支持下列搜索客户端：

-   OneDrive

-   Delve

-   SharePoint 主页

-   搜索中心

-   使用 SharePoint 搜索 API 的自定义搜索应用程序

## <a name="sharepoint-home"></a>SharePoint 主页 

In SharePoint Multi-Geo your SharePoint your SharePoint hosted in the location where the user resides as determined by their OneDrive location. 例如，如果用户拥有在欧洲附属OneDrive托管的用户，则其SharePoint主页将呈现自欧洲。 SharePoint 主页包括与用户相关的所有内容，无论它们的地理位置如何。 

**关注的网站、网站新闻、最近访问的网站、经常访问的网站和推荐网站**

只要用户有权访问上述内容，就会看到所有这些组件，无论内容托管地理位置如何。 

**“特别推荐”链接**

管理员可以酌情将 SharePoint 主页中的“特别推荐”链接配置为各个地理位置。 这样一来，管理员可以在每个地区的 SP 主页中提供适合此地区用户的“特别推荐”链接。 

## <a name="sharepoint-mobile-client"></a>SharePoint 移动客户端 

SharePoint 移动客户端可感知多地理位置，并显示来自所有地理位置的相关内容和结果。

## <a name="sharing"></a>共享

“人员选取器”体验面向所有用户，无论他们的地理位置如何。 这样，一个用户可以与同一地理位置或租户内其他任何地理位置中的其他用户共享。 来自不同地理位置的内容将在用户的 OneDrive、Word、Excel、PowerPoint 和 Office.com 的"共享我"视图中显示，并且无论托管在哪个地理位置，均可使用单一 Sign-On 体验访问。 

## <a name="teams-experience"></a>Teams 体验

Teams是一项多地理位置服务。 用户可看到 OneDrive 文件和最近查看的文件，无论他们的地理位置如何。 “@提及”适用于所有地理位置中的用户。

## <a name="user-profiles"></a>用户个人资料

用户配置文件信息在用户的地理位置中进行管控。选择用户时，你将被定向到用户的相应地理位置，从中你将看到他们的完整配置文件详情。

如果 Delve 已关闭，你将看到 SharePoint 中的经典配置文件体验，该体验无法感知多地理位置。


