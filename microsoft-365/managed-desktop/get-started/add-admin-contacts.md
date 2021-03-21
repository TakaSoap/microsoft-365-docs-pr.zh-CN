---
title: 在管理门户中添加和验证管理员联系人
description: 告诉我们要针对每个焦点区域与谁联系。
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: 18823db8ca8d4bfa82b8ab6265ee8a0902a13e79
ms.sourcegitcommit: 27b2b2e5c41934b918cac2c171556c45e36661bf
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/19/2021
ms.locfileid: "50925888"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>在管理门户中添加和验证管理员联系人

Microsoft 托管桌面服务可以多种方式与客户进行通信。 为了简化通信并确保我们正在与合适的人员联系，你需要提供一组管理员联系人。 Microsoft 托管桌面 IT 运营部门将联系这些人员，帮助解决租户的问题。

> [!IMPORTANT]
> 你可能已经在管理门户中添加了这些联系人。 如果是这样，请立即仔细检查联系人列表是否准确，因为发生严重事件时，Microsoft 托管桌面必须能够联系他们。 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Microsoft 托管桌面管理门户的 Azure Active Directory 访问权限

Microsoft 托管桌面管理门户要求访问该门户的用户具有以下 Azure Active Directory (AD) 角色之一：
- 全局管理员
- Intune 服务管理员
- 全局读取者
- 服务支持管理员

全局管理员必须是在 Microsoft 托管桌面中注册组织的人。 这五个角色在管理门户中具有相同的访问权限，可以启动和查看任务。 有关在 Azure AD 中分配这些角色的信息，请参阅 [Azure Active Directory](/azure/active-directory/users-groups-roles/directory-assign-admin-roles)中的管理员角色权限。 

## <a name="admin-contact-areas-of-focus"></a>管理员重点关注的联系人区域

管理员联系人应该是可以回答问题并针对不同关注领域做出决策的最佳人员或组。 **对于涉及客户提交的支持请求的问题，Microsoft 托管桌面操作将联系这些管理员联系人。** 这些管理员联系人将收到支持请求更新和新邮件的通知。 这些方面包括：

焦点区域 | 有关
--- | ---
应用打包 | 应用打包疑难解答
设备 | 设备运行状况，Microsoft 托管桌面设备疑难解答
安全性 | Microsoft 托管桌面设备的安全问题疑难解答
IT 技术支持 | 如果支持人员在 Microsoft 托管桌面支持区域之外接管用户票证 
其他 | 对于其他方面未涵盖的问题

**为这些联系人选择的任何人都需要具备针对 Microsoft 托管桌面环境做出决策的知识和权威。** 当你载入 Microsoft 托管桌面环境时，系统将提示你为本地支持人员和安全添加联系人。 

提交支持请求时 [需要管理员联系人](../service-description/support.md)。 你需要有一个管理员联系人来联系支持请求的重点关注区域。 

**添加管理员联系人**

1.  登录到 [Microsoft 托管桌面管理门户](https://aka.ms/mwaasportal)。 

2.  在 **"支持"** 下，**选择"管理员联系人"。** 

    ![支持菜单，顶部附近的管理员联系人已选定](../../media/admincontacts.png)

3. 选择“**添加**”。

    ![管理门户的"添加"按钮，在"导出"和"刷新"左侧](../../media/adminadd.png)

4.  选择 **一个焦点区域** ，然后输入联系人的信息。 

    ![焦点区域列表，例如"其他"、"应用"和"安全"](../../media/areaoffocus.png)

5. 对每个焦点区域重复上述步骤。 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>Microsoft 托管桌面入门步骤

1. 在管理门户中添加和验证管理员 (本主题) 
2. [调整条件访问](conditional-access.md)
3. [分配许可证](assign-licenses.md)
4. [在设备上安装 Intune 公司门户](company-portal.md)
5. [启用企业状态漫游](enterprise-state-roaming.md)
6. [设置 Microsoft 托管桌面设备](set-up-devices.md)
7. [为用户做好使用设备的准备](get-started-devices.md)
8. [将应用部署到设备](deploy-apps.md)