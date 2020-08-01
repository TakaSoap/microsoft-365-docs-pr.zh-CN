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
ms.openlocfilehash: e6311c0ad11d68c870b0c8185974b8913735e2a2
ms.sourcegitcommit: 126d22d8abd190beb7101f14bd357005e4c729f0
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/30/2020
ms.locfileid: "46530171"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备映射的驱动器

许多企业环境都具有对映射驱动器的旧版要求，以允许其用户或团队共享和存储文件，或用于本地应用程序。 Microsoft 不建议使用 Microsoft 托管桌面的映射驱动器。 相反，我们建议您将文件访问解决方案现代化，如下所示：
  
- 将单个用户使用的映射驱动器迁移到 OneDrive for Business。 
- 迁移团队使用的映射驱动器以将文件共享到 SharePoint Online。 
- 将使用本地文件共享的任何应用程序现代化或替换为删除该要求。
  
新式化这些服务将允许在 Microsoft 托管桌面中获得最佳的最终用户体验。 Microsoft FastTrack 服务可帮助你使用 Microsoft 云服务新式化你的环境。 您可以检查是否符合[符合条件的服务和计划](https://docs.microsoft.com/fasttrack/m365-eligible-services-and-plans)的 FastTrack 服务，然后直接与他们联系以准备好 Microsoft 托管桌面。 有关 FastTrack OneDrive for Business 或 SharePoint Online 迁移的背景，请参阅[数据迁移](https://docs.microsoft.com/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>Microsoft 托管桌面上的映射驱动器
 
如果无法删除或替换某些用例的映射驱动器，应在 Microsoft 托管桌面管理门户中提交支持请求，以将其部署到 Microsoft 托管桌面用户。
    
对于此类请求，必须在支持请求中提供以下详细信息： 

- 将需要为 Microsoft 托管桌面设备映射的文件共享位置的所有 UNC 路径 
- 需要访问这些文件共享位置的用户组 
- 任何需要分配的特定驱动器号（如有必要）

例如：

| 驱动器号 | UNC 路径 | 用户组 |
|--------------|----------|------------|
| 版  | \\\server\share\Marketing | ContosoMarketing |

确保用户和组拥有和维护访问文件共享位置的适当权限，并且仍可访问本地文件服务，这完全是您的责任。 此外，您还应尽快删除对此类文件共享的要求。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>在 Microsoft 托管桌面中部署映射驱动器
 
请确保无法避免映射的驱动器，并且在提交任何服务请求之前仔细查看了要求。 然后，按照以下步骤操作：

1. 导航到[Microsoft 托管桌面门户](https://aka.ms/mmdportal)。  
2. 通过 "**支持 > 支持请求**" 部分提交标题为 "映射驱动器部署" 的支持请求，并提供所有必需的文件共享详细信息。  
3. Microsoft 托管桌面 IT 操作将在请求完成时使用支持请求更新通知。 最初，此配置将仅部署到测试部署组中的设备。  
4. 您必须测试和确认由 Microsoft 托管桌面 IT 操作部署的配置是否按预期工作。 使用支持请求中的 "讨论" 选项卡进行答复，以在完成测试后通知 Microsoft 托管的桌面 IT 操作。  
5. Microsoft 托管桌面 IT 操作团队随后会将配置部署到其他部署组。 
