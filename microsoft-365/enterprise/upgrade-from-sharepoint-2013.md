---
title: 从 2013 SharePoint升级
ms.author: serdars
author: serdarsoysal
manager: serdars
ms.date: 11/10/2021
audience: ITPro
ms.topic: conceptual
ms.prod: sharepoint-server-itpro
ms.collection:
- Ent_O365
search.appverid:
- MET150
f1.keywords:
- NOCSH
description: 查找从 SharePoint Server 2013 和 SharePoint Foundation 2013 升级的信息和资源。 对两者的支持将于 2023 年 4 月 11 日结束。
ms.openlocfilehash: 05f545b67d60d6bcc45587049e49a5f5c1f6d654
ms.sourcegitcommit: 16e3a6e6df253de1153e46d058941cd9a2bbf2b2
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/10/2021
ms.locfileid: "60889853"
---
# <a name="upgrading-from-sharepoint-2013"></a>从 2013 SharePoint升级

2013 Microsoft SharePoint Server和 SharePoint Foundation 2013 将于 **2023** 年 4 月 11 日停止提供支持。 本文提供的资源可帮助你将现有 SharePoint Server 数据迁移到 Microsoft 365 中的 SharePoint Online 或升级本地 SharePoint 2013 环境。 在本文的其余部分，我们将使用 SharePoint 2013 来引用 SharePoint Server 2013 和 SharePoint Foundation 2013。

## <a name="what-is-end-of-support"></a>停止 *提供支持的是什么*？

大多数 Microsoft 产品都有一个支持生命周期，在此期间它们获取新功能、Bug 修复、安全修补程序等。 在支持终止日期后，产品不会停止工作，但 Microsoft 不再提供：

- 针对可能会出现的问题的技术支持。

- 对可能会影响服务器稳定性和可用性的问题进行 Bug 修复。

- 针对可能导致服务器易受安全漏洞的漏洞进行安全修复。

- 时区更新。

这意味着不会为产品服务提供进一步的更新、修补程序或修补程序 (包括安全修补程序/修补程序) 。 Microsoft 支持将完全将支持工作转移到更新版本。

> [!NOTE]
> 从初始版本开始，软件生命周期通常持续 5 年主要支持，并且可能持续 5 年的额外扩展支持。 [Microsoft 解决方案](https://go.microsoft.com/fwlink/?linkid=841249)提供商可以帮助你升级到该软件的下一版本，或迁移到 Microsoft 365 (或两) 。 确保您还了解关键基础技术的停止支持日期，尤其是要与 Microsoft SQL Server 一SharePoint。 有关详细信息，请参阅固定 [生命周期策略](https://support.microsoft.com/help/14085)。

## <a name="plan-ahead"></a>提前规划

Check the dates that support ends on the Product Lifecycle site for [SharePoint Server 2013](/lifecycle/products/sharepoint-server-2013) and [SharePoint Foundation 2013](/lifecycle/products/sharepoint-foundation-2013). 请牢记这些日期，规划升级或迁移。 请记住， *产品不会在列出的日期* 停止工作。 但是，由于该日期之后将不再修补安装，因此你需要计划顺利过渡到产品的下一个版本。 下表列出了可用的选项。

|停止提供支持产品|Good|更好|最好|
|---|---|---|---|
|SharePoint Server 2013<BR>SharePoint Foundation 2013|升级到 SharePoint Server 2016 或 2019|升级到 SharePoint Server 订阅版|迁移到SharePoint Microsoft 365

## <a name="whats-next"></a>下一步做什么？

我们建议迁移到 SharePoint Microsoft 365，以利用 Microsoft 365 中的最新协作、智能和安全Microsoft 365。 新式体验功能Microsoft 365设计得令人信服、灵活且性能高。

如果需要维护本地 SharePoint 部署，我们建议采用混合部署，以便你可以迁移尽可能多的 SharePoint 功能，SharePoint Microsoft 365。 请参阅[SharePoint](/sharepoint/hybrid/hybrid)混合，了解和规划混合实现。

### <a name="migrate-to-sharepoint-in-microsoft-365"></a>迁移到SharePoint Microsoft 365

您可以使用 spMT SharePoint迁移 (迁移) 将网站和内容迁移到 SharePoint Microsoft 365。 我们具有一个广泛的内容库，可帮助您提前规划、执行迁移以及解决您遇到的任何问题。 [迁移SharePoint概述](/sharepointmigration/introducing-the-sharepoint-migration-tool)是一个很好的起点。

### <a name="upgrade-to-sharepoint-server-subscription-edition"></a>升级到 SharePoint Server 订阅版

即使没有从 SharePoint 2013 升级到 Subscription Edition 的直接路径，这仍然是第二个最佳选择。 主要原因在于，SharePoint Server Subscription Edition 引入了一个持续更新模型，无需今后发布 SharePoint Server 的新主要版本。

若要升级到 Subscription Edition，必须运行 SharePoint Server 2016 或 2019。 由于也不存在从 SharePoint 2013 到 2019 的直接路径，因此最佳选择是先升级到 2016，然后再升级到 Subscription Edition。 请参阅下面的链接以了解有关订阅版本的详细信息并规划升级到订阅版本：

- [升级到 SharePoint Server 2016](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [升级到 SharePoint Server 订阅版](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-subscription-edition)

即使您需要维护本地 SharePoint 部署，我们建议您使用 SharePoint 混合实现将部分网站或内容迁移到[Microsoft 365，](/sharepoint/hybrid/hybrid)以开始利用 Microsoft 365 中的新式协作体验、安全性和合规性功能。  

### <a name="upgrade-to-sharepoint-server-2016-or-2019"></a>升级到 SharePoint Server 2016 或 2019

如果SharePoint 2013 年停止提供支持后维护本地 SharePoint 部署，则 SharePoint Server 2016 和 2019 都受支持平台。 但是， **这两个版本将于 2026** 年 7 月 14 日终止支持。 这意味着您需要在 2013 年支持日期结束后的 3 年内规划另一次升级。 以下是两种产品的支持生命周期页面：

- [SharePointServer 2016 支持生命周期日期](/lifecycle/products/sharepoint-server-2016)
- [SharePoint Server 2019支持生命周期日期](/lifecycle/products/sharepoint-server-2019)

若要了解更多信息并规划升级，请参阅以下文章：

- [升级到 SharePoint Server 2016](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2016)
- [升级到 SharePoint Server 2019](/sharepoint/upgrade-and-update/upgrade-to-sharepoint-server-2019)

即使您需要维护本地 SharePoint 部署，我们建议您使用 SharePoint 混合实现将部分网站或内容迁移到[Microsoft 365，](/sharepoint/hybrid/hybrid)以开始利用 Microsoft 365 中的新式协作体验、安全性和合规性功能。  
