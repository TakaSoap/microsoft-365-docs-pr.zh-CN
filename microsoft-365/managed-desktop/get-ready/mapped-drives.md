---
title: 为 Microsoft 托管桌面准备映射的驱动器
description: 确保用户可以访问映射驱动器上的数据的重要步骤
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 5767b83a249922b0d980d26a132ffb99649a6833
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034913"
---
#  <a name="prepare-mapped-drives-for-microsoft-managed-desktop"></a>为 Microsoft 托管桌面准备映射的驱动器

许多企业环境对映射驱动器具有旧要求，以允许其用户或团队共享和存储文件，或本地应用程序。 Microsoft 不建议将映射的驱动器与 Microsoft 托管桌面。 相反，我们建议你使文件访问解决方案现代化，如下所示：
  
- 将单个用户使用的映射驱动器迁移到OneDrive for Business。 
- 将团队用于共享文件的映射驱动器迁移到 SharePoint Online。 
- 现代化或替换任何使用本地文件共享的应用程序，以删除该要求。
  
现代化这些服务将能提供最佳用户体验，Microsoft 托管桌面。 Microsoft FastTrack 服务可帮助你使用 Microsoft 云服务现代化环境。 你可以检查你是否有资格使用符合条件的服务和FastTrack服务，然后直接与他们联系以准备[](/fasttrack/m365-eligible-services-and-plans)Microsoft 托管桌面。 有关迁移或FastTrack OneDrive for Business迁移SharePoint，请参阅数据[迁移](/fasttrack/o365-data-migration)。

## <a name="mapped-drives-on-microsoft-managed-desktop"></a>驱动器上的映射Microsoft 托管桌面
 
如果在某些用例中无法删除或替换映射的驱动器，应在 Microsoft 托管桌面 管理门户中提交支持请求，以将其部署到 Microsoft 托管桌面 用户。
    
对于此类请求，你必须在支持请求中提供以下详细信息： 

- 需要为设备映射的文件共享位置的所有 UNC Microsoft 托管桌面路径 
- 需要访问这些文件共享位置的用户组 
- 需要分配的任何特定驱动器号 (如果需要) 

例如：

| 驱动器号 | UNC 路径 | 用户组 |
|--------------|----------|------------|
| X:  | \\\server\share\Marketing | ContosoMarketing |

你完全有责任确保用户和组拥有和维护访问文件共享位置所需的正确权限，并确保本地文件服务仍然可访问。 此外，应尽快删除对此类文件共享的要求。

### <a name="to-have-mapped-drives-deployed-in-microsoft-managed-desktop"></a>在映像中部署映射Microsoft 托管桌面
 
请确保无法避免映射的驱动器，并且你已仔细查看要求，然后再提交任何服务请求。 然后按照以下步骤操作：

1. 导航到[Microsoft Endpoint Manager](https://endpoint.microsoft.com/)并选择"疑难解答 + 支持"，然后在"服务请求"部分下Microsoft 托管桌面请求"。  
2. 提交标题为"映射驱动器部署"的支持请求，并提供所有必需的文件共享详细信息。  
3. Microsoft 托管桌面请求完成时，IT 运营部门将通过使用支持请求更新提供建议。 最初，此配置将仅部署到"测试"部署组的设备。  
4. 您必须测试并确认由 IT 运营部门Microsoft 托管桌面的配置是否按预期工作。 使用相同支持请求的详细信息中的"讨论"选项卡进行回复，以Microsoft 托管桌面测试完成后通知 IT 运营部门。  
5. Microsoft 托管桌面 IT 运营团队随后将配置部署到其他部署组。 

## <a name="steps-to-get-ready-for-microsoft-managed-desktop"></a>准备使用Microsoft 托管桌面

1. 查看 [托管桌面应用](prerequisites.md)。
2. 运行 [准备情况评估工具](readiness-assessment-tool.md)。
1. 购买 [公司门户](../get-started/company-portal.md)。
1. 查看 [来宾帐户的先决条件](guest-accounts.md)。
1. 检查 [网络配置](network.md)。
1. [准备证书和网络配置文件](certs-wifi-lan.md)。
1. [准备用户对数据的访问权限](authentication.md)。
1. [准备应用](apps.md)。
1. 准备映射驱动器 (本文) 。
1. [准备打印资源](printing.md)。
1. 地址 [设备名称](address-device-names.md)。