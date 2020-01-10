---
title: 在管理门户中添加和验证管理员联系人
description: 告诉我们每个焦点区域的联系人。
keywords: Microsoft 托管桌面，Microsoft 365，服务，文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.openlocfilehash: 9233118a2112aae33a5b784b6495709cbd3345f5
ms.sourcegitcommit: ef658406da9d081e5e7a5f3aac8290c2f03f7aff
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/10/2020
ms.locfileid: "41004917"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>在管理门户中添加和验证管理员联系人

Microsoft 托管桌面服务与客户进行通信有几种方式。 为了简化通信并确保使用正确的人员进行检查，您需要提供一组管理员联系人。 Microsoft 托管桌面 IT 操作将与这些人员联系，以帮助解决你的租户问题。

> [!IMPORTANT]
> 您可能已经在管理门户中添加了这些联系人。 如果是这样，请立即花些时间仔细检查联系人列表是否准确，因为 Microsoft 托管桌面**必须**能够在发生严重事件时访问它们。

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Microsoft 托管桌面管理门户的 Azure Active Directory 访问

Microsoft 托管桌面管理门户要求访问门户的用户拥有以下 Azure Active Directory （AD）角色之一：
- 全局管理员
- Intune 服务管理员
- 全局读取者
- 服务支持管理员

全局管理员必须是在 Microsoft 托管桌面中注册您的组织的管理员。 在管理门户中，所有五个角色都具有相同的访问权限，以启动和查看任务。 有关在 Azure AD 中分配这些角色的详细信息，请参阅[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 

## <a name="admin-contact-areas-of-focus"></a>管理联系人焦点区域

管理员联系人应是可以回答问题并针对不同关注领域做出决定的最佳人员或组。 **Microsoft 托管桌面操作将与这些管理员联系人联系，以了解涉及客户存档的支持请求的问题。** 这些管理员联系人将接收支持请求更新和新邮件的通知。 这些领域包括：

焦点区域 | 有关的问题
--- | ---
应用程序打包 | 应用程序打包故障排除
设备 | 设备运行状况，使用 Microsoft 托管桌面设备进行故障排除
安全性 | Microsoft 托管桌面设备的安全问题故障排除
IT 技术支持人员 | 如果我们的支持人员在 Microsoft 托管桌面支持区域之外的最终用户票据上进行了干预 
其他 | 对于未被其他区域覆盖的问题

**你为这些联系人选择的任何人都需要了解有关 Microsoft 托管桌面环境的决策的知识和权威。** 在集成 Microsoft 托管桌面环境时，系统会提示你为本地帮助台和安全添加联系人。 

[提交支持请求](../service-description/support.md)时，需要管理员联系人。 您需要具有管理员联系人的支持请求的焦点区域。 

**添加管理员联系人**

1.  登录到[Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)。 

2.  在 "**支持**" 下，选择 "**管理联系人**"。 

    ![支持菜单，在所选顶部附近为管理员联系人](images/admincontacts.png)

3. 选择“添加”****。

    !["管理门户"、"添加" 按钮（位于 "导出" 和 "刷新" 的左侧）](images/adminadd.png)

4.  选择**焦点区域**并输入联系人的信息。 

    ![焦点区域的列表，如其他、应用程序和安全性](images/areaoffocus.png)

5. 对每个焦点区域重复此操作。 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft 托管桌面入门步骤

1. 在管理门户中添加和验证管理员联系人（本主题）
2. [调整条件访问](conditional-access.md)
3. [分配许可证](assign-licenses.md)
4. [在设备上安装 Intune 公司门户](company-portal.md)
5. [启用企业状态漫游](enterprise-state-roaming.md)
6. [设置 Microsoft 托管桌面设备](set-up-devices.md)
7. [让用户做好使用设备的准备](get-started-devices.md)
8. [将应用程序部署到设备](deploy-apps.md)
