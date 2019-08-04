---
title: 在 Microsoft 托管桌面管理门户中添加管理员联系人
description: 告诉我们每个焦点区域的联系人。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.date: 09/24/2018
ms.collection: M365-modern-desktop
ms.openlocfilehash: 68f5d5cb46d4aa643b1b09f9204b24dea3d77eb1
ms.sourcegitcommit: 427c6459614d58f6ef7c74354ae1816423e22323
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/28/2019
ms.locfileid: "35390529"
---
# <a name="add-admin-contacts-in-microsoft-managed-desktop-admin-portal"></a>在 Microsoft 托管桌面管理门户中添加管理员联系人

Microsoft 托管桌面服务与客户进行通信有几种方式。 为了简化通信并确保我们使用最佳联系人进行检查, 您需要提供一组管理员联系人。 Microsoft 托管桌面 IT 操作将与这些人员联系, 以帮助解决你的租户问题。 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Microsoft 托管桌面管理门户的 Azure Active Directory 访问

Microsoft 托管桌面管理门户要求访问门户的用户拥有以下 Azure Active Directory (AD) 角色之一:
- 全局管理员
- Intune 服务管理员
- 记帐管理员
- 服务支持管理员

全局管理员必须是要在 Microsoft 托管桌面中注册客户的全局管理员。 在管理门户中, 所有五个角色都具有相同的访问权限, 以启动和查看任务。 有关在 Azure AD 中分配这些角色的详细信息, 请参阅[Azure Active Directory 中的管理员角色权限](https://docs.microsoft.com/azure/active-directory/users-groups-roles/directory-assign-admin-roles)。 

## <a name="admin-contact-focus-areas"></a>管理员联系人焦点区域

管理员联系人应是可以回答问题并针对不同的重点领域做出决定的最佳人员或组。 Microsoft 托管桌面操作将与这些管理员联系人联系, 以了解涉及客户存档的支持请求的问题。 这些管理员联系人将接收支持请求更新和新邮件的通知。 这些领域包括:

焦点区域 | 有关的问题
--- | ---
应用 | 应用程序打包故障排除
设备 | 设备运行状况, 使用 Microsoft 托管桌面设备进行故障排除
安全性 | Microsoft 托管桌面设备的安全问题故障排除
IT 技术支持人员 | 在 Microsoft 托管桌面支持 MMD 支持区域之外的最终用户票证的情况下 
Other | 对于未被其他区域覆盖的问题

你为这些联系人选择的任何人都需要了解有关 Microsoft 托管桌面环境的决策的知识和权威。 在集成 Microsoft 托管桌面环境时, 系统会提示你为本地帮助台和安全添加联系人。 

[提交支持请求](../working-with-managed-desktop/support.md)时, 需要管理员联系人。 您需要具有管理员联系人的支持请求的焦点区域。 

**添加管理员联系人**

1.  登录到[Microsoft 托管桌面管理门户](http://aka.ms/mwaasportal)。 

2.  在 "**支持**" 下, 选择 "**管理联系人**"。 

    ![支持菜单、管理员联系人](images/admincontacts.png)

3. 选择“添加”****。

    ![管理门户添加按钮](images/adminadd.png)

4.  选择**焦点区域**并输入联系人的信息。 

    ![焦点区域的列表](images/areaoffocus.png)

5. 对每个焦点区域重复此操作。 

