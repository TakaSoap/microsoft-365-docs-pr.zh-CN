---
title: 管理多地理位置环境
ms.reviewer: adwood
ms.author: mikeplum
author: MikePlumleyMSFT
manager: pamgreen
audience: ITPro
ms.topic: article
ms.service: o365-solutions
f1.keywords:
- NOCSH
ms.custom:
- seo-marvel-apr2020
- admindeeplinkSPO
ms.collection:
- Strat_SP_gtc
- SPO_Content
ms.localizationpriority: medium
description: 管理员可以了解如何在多地理位置SharePoint OneDrive和启用服务。
ms.openlocfilehash: 126b5de915fba7168b3895bbb05ccef6dcad749b
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63312049"
---
# <a name="administering-a-multi-geo-environment"></a>管理多地理位置环境

下文描述了 Microsoft 365 服务在多地理位置环境中的工作方式。

## <a name="administrator-experience"></a>管理员体验

管理SharePoint中心左侧导航中具有"地理位置<a href="https://go.microsoft.com/fwlink/?linkid=2185076" target="_blank"></a>"选项卡，其中显示地理位置地图，可在其中查看和管理地理位置。 使用此页面添加或删除租户的地理位置。

## <a name="audit-log-search"></a>审核日志搜索

可以从 Microsoft 365 审核日志搜索页中找到所有附属位置的统一[审核日志](https://support.office.com/article/0d4d0f35-390b-4518-800e-0c7ec95e946c)。 你可以查看跨地理位置的所有审核日志条目，例如，NAM 和 EUR 用户的活动将显示在一个组织视图中，然后你可以应用现有筛选器，查看特定用户的活动。

> [!NOTE]
> Exchange管理员审核事件仅适用于默认位置。

## <a name="bcs-secure-store-apps"></a>BCS、安全存储、应用

BCS、安全存储和应用在每个附属位置都具有单独的实例，因此，SharePoint Online 管理员应从每个附属位置单独管理和配置这些服务。

## <a name="compliance-admin-center"></a>合规性管理中心

多地理位置租户有一个中央合规中心：Microsoft 365[合规性管理中心](https://compliance.microsoft.com/)。

## <a name="ediscovery"></a>电子数据展示

默认情况下，电子数据展示管理员或多地理位置租户的管理员将只能在该租户的中心位置执行电子数据展示。 Office 365 全局管理员必须分配电子数据展示管理者权限，以允许其他人员执行电子数据展示，并在其适用的合规性安全筛选器中分配“Region”参数，以便将要进行电子数据展示的区域指定为附属位置，否则，不会对该附属位置执行任何电子数据展示。 若要针对区域配置合规性安全筛选器，请参阅[配置 Office 365 多地理位置电子数据展示](multi-geo-ediscovery-configuration.md)。

## <a name="exchange-mailboxes"></a>Exchange 邮箱

如果更改了用户的 PDL，则会自动转移用户的 Exchange 邮箱。 创建新邮箱时，如果没有为用户的 PDL 设置值，则会将新邮箱预配到用户的 PDL 或中心位置。

## <a name="information-protection-ip-data-loss-prevention-dlp-policy"></a>信息保护 (DLP) 策略 (IP) 数据丢失防护

可以在“安全性和合规性”中心内为 OneDrive for Business、SharePoint 和 Exchange 设置 IP DLP 策略，并根据需要将策略的适用范围设置为整个租户或适用的用户。 例如：如果你希望为附属位置中的某个用户选择策略，请选择将策略应用于特定 OneDrive，并输入用户的 OneDrive url。 有关创建 DLP 的一般指南，请参阅[数据丢失防护策略概述](https://support.office.com/article/1966b2a7-d1e2-4d92-ab61-42efbb137f5e)。

DLP 策略将基于每个地理位置的适用性自动同步。

在 UI 中，无法为地理位置中的所有用户实施信息保护和数据丢失防护策略，你必须为策略选择适用的帐户，或将策略全局应用于所有帐户。

## <a name="microsoft-power-apps"></a>Microsoft Power Apps

Power Apps位置创建的位置将使用位于租户中心位置的终点。 Microsoft Power Apps不是多地理位置服务。 

## <a name="power-automate"></a>Power Automate

为附属位置创建的流程将使用位于租户的默认地理位置中的终结点。  Power Automate不是多地理位置服务。 

## <a name="sharepoint-storage-quota"></a>SharePoint 存储配额

默认情况下，多地理位置环境中的所有地理位置具有相同的可用租户存储配额。  也可通过为特定地理位置分配特定配额来管理存储配额。 有关详细信息，请参阅 [多地理位置环境中的 SharePoint 存储配额](sharepoint-multi-geo-storage-quota.md)。

## <a name="sharing"></a>共享

管理员可以为他们的每个位置设置和管理共享策略。 每个OneDrive中的SharePoint网站和网站将仅遵守相应的特定于地理位置的共享设置。 （例如，你可以为中心位置允许[外部共享](https://support.office.com/article/C8A462EB-0723-4B0B-8D0A-70FEAFE4BE85)，但不能为附属位置允许外部共享，反之亦然。）请注意，共享设置不允许配置地理位置之间的共享限制。

## <a name="stream"></a>Stream

在一对一聊天中上传到 Stream 的视频存储在OneDrive用户的视频中。 会议录制存储在每个OneDrive与会者的会议室中。

## <a name="taxonomy"></a>分类

我们支持跨 [地理位置的企业](/sharepoint/managed-metadata) 托管元数据的统一分类，主机托管在公司的中心位置。 我们建议你通过中心位置管理全局分类，并仅向附属位置分类中添加特定于位置的术语。 全局分类术语将同步到附属位置。

有关附加详细信息及开发人员指南，请参阅[管理多地理位置租户中的元数据](/sharepoint/dev/solution-guidance/multigeo-managedmetadata)。

## <a name="user-profile-application"></a>用户配置文件应用程序

每个地理位置都有一个[用户配置文件应用程序](/sharepoint/manage-user-profiles)。 每个用户的配置文件信息都托管在其地理位置中，并可供该地理位置的管理员使用。

如果你有自定义配置文件属性，建议跨地区使用同一配置文件架构并在所有地理位置或所需的位置填充自定义配置文件属性。 有关如何以编程方式填充用户配置文件数据的指导，请参阅[批量用户配置文件更新 API](/sharepoint/dev/solution-guidance/bulk-user-profile-update-api-for-sharepoint-online)。

有关附加信息及开发人员指南，请参阅[在多地理位置租户中使用用户配置文件](/sharepoint/dev/solution-guidance/multigeo-userprofileexperience)。

## <a name="yammer"></a>Yammer

Yammer不是多地理位置工作负载。 Yammer中存储Yammer线程将放置在租户的中心位置。 Yammer推出文件存储更改，将在Yammer中存储SharePoint。 Yammer中存储SharePoint文件将SharePoint组关联的Yammer网站。 SharePoint组网站基于 PDL 逻辑，如SharePoint[和组所述](multi-geo-capabilities-in-onedrive-and-sharepoint-online-in-microsoft-365.md#sharepoint-sites-and-groups)。
