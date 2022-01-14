---
title: 启用企业状态漫游
description: ''
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 0050bd38dc62adfd36f7c7f71e47a3a72039f6b0
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034709"
---
# <a name="enable-enterprise-state-roaming"></a>启用企业状态漫游

[Enterprise状态漫游](/azure/active-directory/devices/enterprise-state-roaming-overview)允许用户将用户和应用程序设置数据安全地同步到云。 这意味着无论登录哪个设备，Windows具有相同的体验。 例如，如果将其中一个Microsoft 托管桌面设备替换为新的设备，则其外观和行为与上一个设备完全相同。 Enterprise状态漫游是 Microsoft 托管桌面 服务的可选功能，你可以为用户配置该功能，并且不会作为 Microsoft 托管桌面 的一部分进行包含或Microsoft 托管桌面。

若要启用Enterprise状态漫游，请按照启用Enterprise[状态漫游中的步骤Azure Active Directory。](/azure/active-directory/devices/enterprise-state-roaming-enable)

>[!NOTE]
>如果你启用Enterprise状态漫游，你的首选语言列表将覆盖在设备设置期间选择的语言。 虽然用户可以轻松修复此问题，但最初可能会导致本地化体验不一致。 在Enterprise之前，确定状态漫游是否适合你的用户。

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用 Microsoft 托管桌面

1. [在管理门户中添加和验证管理员联系人](add-admin-contacts.md)
2. [调整条件访问](conditional-access.md)
3. [分配许可证](assign-licenses.md)
4. [部署 Intune 公司门户](company-portal.md)
5. 本主题Enterprise启用 (状态漫游) 
6. [设置设备](set-up-devices.md)
7. [让用户做好使用设备的准备](get-started-devices.md)
8. [部署应用](deploy-apps.md)
