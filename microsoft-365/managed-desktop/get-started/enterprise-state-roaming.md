---
title: 启用企业状态漫游
description: 本文介绍如何启用企业状态漫游
keywords: 'Microsoft 托管桌面, Microsoft 365, 服务, 文档'
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
---

# <a name="enable-enterprise-state-roaming"></a>启用企业状态漫游

[Enterprise状态漫游](/azure/active-directory/devices/enterprise-state-roaming-overview)允许用户将用户和应用程序设置数据安全地同步到云。 这意味着无论登录哪个设备，Windows具有相同的体验。 例如，如果你将其一个Microsoft 托管桌面设备替换为新设备，则其外观和行为与最后一个设备完全相同。

Enterprise状态漫游是 Microsoft 托管桌面 服务的可选功能，您可以为用户配置该功能。 它未作为托管项的一部分包含或Microsoft 托管桌面。

若要启用Enterprise状态漫游，请按照启用Enterprise[状态漫游中的步骤Azure Active Directory](/azure/active-directory/devices/enterprise-state-roaming-enable)。

>[!NOTE]
>如果你启用Enterprise状态漫游，你的首选语言列表将覆盖在设备设置期间选择的语言。 虽然用户可以轻松修复此问题，但最初可能会导致本地化体验不一致。 在Enterprise之前，确定状态漫游是否适合你的用户。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用 Microsoft 托管桌面

1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)。
2. [调整条件访问](conditional-access.md)。
3. [分配许可证](assign-licenses.md)。
4. [部署Intune 公司门户](company-portal.md)。
5. 启用Enterprise状态漫游 (本主题) 。
6. [设置设备](set-up-devices.md)。
7. [让用户做好使用设备的准备](get-started-devices.md)。
8. [部署应用](deploy-apps.md)。
