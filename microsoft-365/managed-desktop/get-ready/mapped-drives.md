---
title: 为 Microsoft 托管桌面准备映射的驱动器
description: 确保执行的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
ms.openlocfilehash: cd45d6155fc0e01f6a285f6182aa051281d160e0
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50922904"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备映射的驱动器

许多企业环境对映射驱动器都有旧要求，以允许其用户或团队共享和存储文件，或本地应用程序。 Microsoft 不建议将映射驱动器与 Microsoft 托管桌面一同使用。 相反，我们建议你使文件访问解决方案现代化，如下所示：
  
- 将单个用户使用的映射驱动器迁移到 OneDrive for Business。 
- 将团队用于共享文件的映射驱动器迁移到 SharePoint Online。 
- 现代化或替换任何使用本地文件共享的应用程序，以删除该要求。
  
现代化这些服务将提供最佳的 Microsoft 托管桌面用户体验。 Microsoft FastTrack Services 可帮助你使用 Microsoft 云服务现代化环境。 你可以检查你是否有资格使用符合条件的服务和计划中的 FastTrack 服务[](/fasttrack/m365-eligible-services-and-plans)，然后直接与他们联系以准备 Microsoft 托管桌面。 有关 FastTrack OneDrive for Business 或 SharePoint Online 迁移的背景，请参阅 [数据迁移](/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft 托管桌面上的映射驱动器
 
如果在某些用例中无法删除或替换映射的驱动器，应在 Microsoft 托管桌面管理门户中提交支持请求，以将其部署到 Microsoft 托管桌面用户。
    
对于此类请求，你必须在支持请求中提供以下详细信息： 

- 需要为 Microsoft 托管桌面设备映射的文件共享位置的所有 UNC 路径 
- 需要访问这些文件共享位置的用户组 
- 需要分配的任何特定驱动器号 (如果需要) 

例如：

| 驱动器号 | UNC 路径 | 用户组 |
|--------------|----------|------------|
| X：  | \\\server\share\Marketing | ContosoMarketing |

你完全有责任确保用户和组拥有和维护访问文件共享位置所需的正确权限，并确保本地文件服务仍然可访问。 此外，应尽快删除对此类文件共享的要求。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>在 Microsoft 托管桌面中部署映射的驱动器
 
请确保无法避免映射的驱动器，并且你已仔细查看要求，然后再提交任何服务请求。 然后按照以下步骤操作：

1. 导航到 [Microsoft Endpoint Manager 并选择](https://endpoint.microsoft.com/) "疑难解答 + 支持"，然后在 Microsoft 托管桌面部分下查找"服务请求"。  
2. 提交标题为"映射驱动器部署"的支持请求，并提供所有必需的文件共享详细信息。  
3. 当请求完成时，Microsoft 托管桌面 IT 运营部门将通过使用支持请求更新提供建议。 最初，此配置将仅部署到"测试"部署组的设备。  
4. 您必须测试并确认 Microsoft 托管桌面 IT 操作部署的配置是否按预期工作。 使用相同支持请求的详细信息中的"讨论"选项卡进行回复，以在测试完成后通知 Microsoft 托管桌面 IT 操作。  
5. 然后，Microsoft 托管桌面 IT 运营团队将配置部署到其他部署组。