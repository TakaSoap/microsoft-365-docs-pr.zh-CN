---
title: 设置 Microsoft 365 商业高级版
description: 了解如何设置Microsoft 365 商业高级版
search.appverid: MET150
author: denisebmsft
ms.author: deniseb
manager: dansimp
audience: Admin
ms.topic: overview
ms.date: 03/01/2022
ms.service: o365-administration
localization_priority: Normal
ms.reviewer: shlomiakirav
f1.keywords: NOCSH
ms.collection:
- SMB
- M365-security-compliance
ms.openlocfilehash: 844dd03ae38eadaa86403b5ee7b2fc00a8840e17
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63318976"
---
# <a name="set-up-microsoft-365-business-premium"></a>设置 Microsoft 365 商业高级版

有几种选项可以设置和配置Microsoft 365 商业高级版。 可以执行下列操作：

- [对基本安装和配置使用引导式安装体验](#guided-process-for-basic-setup)
- [与合作伙伴（如云解决方案提供商Microsoft 云解决方案提供商 (）) ](#work-with-a-microsoft-partner)
- [手动完成安装过程](#manual-setup-and-configuration)


使用本文作为指南。

## <a name="guided-process-for-basic-setup"></a>基本设置的引导过程

Microsoft 365 商业高级版包括基本设置的引导过程。 任务包括连接到自定义域、添加用户、分配许可证、在Outlook安装 Outlook、查看数据保护设置和应用移动应用保护策略。 

若要了解引导式设置的工作原理，请观看以下视频： <br/><br/>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE471FJ?autoplay=false]

完成引导式设置后，需要完成其他步骤，以帮助确保正确设置和应用安全性和合规性功能。 这些步骤包括：

- [保护Windows设备](m365bp-secure-windows-devices.md)
- [部署Microsoft 365应用程序](../admin/setup/install-applications.md)
- [设置和配置新的 Defender for Business 功能](../security/defender-business/mdb-setup-configuration.md)

[详细了解引导式安装过程和设置页面之间的差异](../admin/setup/o365-setup-wizard-and-setup-page.md)。

> [!TIP]
> 请参阅以下部分，详细了解如何设置和配置Microsoft 365 商业高级版。


## <a name="work-with-a-microsoft-partner"></a>与 Microsoft 合作伙伴合作

Microsoft 提供了授权销售产品（包括产品/服务）的解决方案提供商Microsoft 365 商业高级版。 

若要查找您区域中的解决方案提供商，请执行以下步骤：

1. 转到 Microsoft **解决方案提供商** 页面 ([https://www.microsoft.com/solution-providers](https://www.microsoft.com/solution-providers)) 。
 
2. 在搜索框中，填写你的位置和公司大小。 

3. 在" **搜索产品、服务、技能、行业** "框中，输入 `Microsoft 365`，然后选择"开始 **"**。

4. 查看结果列表。 选择一个提供商，详细了解其专业知识及其提供的服务。

另请参阅 [查找合作伙伴或经销商](../admin/manage/find-your-partner-or-reseller.md)。

## <a name="manual-setup-and-configuration"></a>手动安装和配置

如果你想要手动完成设置和配置过程，请使用下表作为指南：

| 阶段  | 任务  | 了解详细信息的资源  |
|---------|---------|---------|
| **规划**     | 规划安装和配置过程  | [规划 Microsoft 365 商业版安装](../admin/setup/plan-your-setup.md)   |
|  | 查看要求 | [Microsoft 365 商业高级版要求](https://www.microsoft.com/microsoft-365/business/microsoft-365-business-premium?activetab=pivot:overviewtab) |
| **基本设置**     | 将自定义域与自定义域`rob@contoso.com`Microsoft 365 | [将域添加到 Microsoft 365](../admin/setup/add-domain.md) |
|      | 添加用户并分配许可证Microsoft 365      | [同时添加用户和分配许可证](../admin/add-users/add-users.md)        |
|  | 向将执行特定功能的用户分配管理员角色，例如： <br/>- 管理功能<br/>- 管理用户帐户<br/>- 管理设备<br/>- 查看或管理组织的安全性和合规性信息 | [了解管理员角色](../admin/add-users/about-admin-roles.md) <br/><br/> [分配管理员角色](../admin/add-users/assign-admin-roles.md)  |
|  | 安装Microsoft 365 应用版 (Word、Excel、PowerPoint 等)  | [安装 Office 应用程序](../admin/setup/install-applications.md) |
| **保护组织** | 请参阅前 10 天保护你的Microsoft 365订阅 |  [保护业务Microsoft 365的十大方法](../admin/security-and-compliance/secure-your-business-data.md) |
|  | 要求每个人在登录登录时使用附加验证Microsoft 365 | [设置多重身份验证](../admin/security-and-compliance/set-up-multi-factor-authentication.md) | 
| **保护电子邮件和内容** |  设置高级防钓鱼保护，以防止恶意基于模拟的网络钓鱼攻击和其他网络钓鱼攻击 | [保护电子邮件免受网络钓鱼攻击](../admin/security-and-compliance/secure-your-business-data.md) |
|   | 设置保险箱附件以保护组织免受恶意电子邮件附件的攻击 | [防范恶意附件和带附件保险箱文件](../admin/security-and-compliance/secure-your-business-data.md) |
|  | 设置保险箱链接，防止恶意网站 (电子邮件) 和Office URL | [设置保险箱链接](../admin/security-and-compliance/secure-your-business-data.md) |
|  | 设置数据丢失防护策略，防止共享敏感信息 | [设置合规性功能](../admin/security-and-compliance/set-up-compliance.md) |
| **管理和保护设备** | 保护组织的 Windows 设备 | [安全Windows设备](m365bp-secure-windows-devices.md) <br/><br/>[设置或编辑设备的应用程序Windows 10设置](../admin/devices/protection-settings-for-windows-10-devices.md) |
|   | 在Microsoft 365上保护应用的安全 | [设置 Android 或 iOS 设备的应用保护设置](../admin/devices/app-protection-settings-for-android-and-ios.md) |
|  | 设置适用于你的租户 (Microsoft Defender for Business)  | [Microsoft Defender for Business 概述](../security/defender-business/mdb-overview.md)<br/><br/>[使用向导设置 Defender for Business](../security/defender-business/mdb-use-wizard.md) |
| **文件存储和迁移内容** | 设置文件存储以及共享对组织如何工作 | [在文件中设置文件存储和Microsoft 365](../admin/setup/set-up-file-storage-and-sharing.md) |
| | 导入或迁移电子邮件和联系人 | [将电子邮件和联系人迁移到 Microsoft 365](../admin/setup/migrate-email-and-contacts-admin.md) |
|  | 移动每个人需要访问的公司文件SharePoint (SharePoint通常会替换文件共享或网络驱动器)  | [将文件移动到SharePoint](../admin/setup/files-to-sharepoint.md) |
|  | 将现有工作文件（如个人工作文件或敏感业务文件）移动到OneDrive | [将文件移动到OneDrive](../admin/setup/files-to-onedrive.md) |
| **培训管理员和安全团队** | 了解如何使用管理中心 | [Microsoft 365 管理中心概述](../admin/admin-overview/admin-center-overview.md) |
|  | 使用适用于管理员的免费培训Microsoft 365库 | [管理员培训视频库](../admin/admin-video-library.yml)  |
|  | 了解如何使用 Microsoft 365 Defender 门户 () [https://security.microsoft.com](https://security.microsoft.com) | [开始使用 Microsoft 365 Defender 门户](../security/defender-business/mdb-get-started.md) |

> [!TIP]
> 需要一些帮助？ 考虑获取 [Business Assist for Microsoft 365](https://support.microsoft.com/en-us/office/business-assist-for-microsoft-365-37deb8fe-61cc-4cf9-9ad1-1c8d93475070)

## <a name="see-also"></a>另请参阅

- [Microsoft Defender for Business (](../security/defender-business/mdb-overview.md)现在包含在 Microsoft 365 商业高级版！) 

- [商业版订阅和计费文档](../commerce/index.yml)

- Microsoft [MICROSOFT 365 LIGHTHOUSE](../lighthouse/m365-lighthouse-overview.md) (的) 

- [保护业务Microsoft 365的十大方法](../admin/security-and-compliance/secure-your-business-data.md)
