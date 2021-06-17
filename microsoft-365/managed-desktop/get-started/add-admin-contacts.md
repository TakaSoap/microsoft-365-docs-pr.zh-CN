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
ms.openlocfilehash: 65d7647e9000152d2eeb8d6bf36e8d45a0d4fa90
ms.sourcegitcommit: 34c06715e036255faa75c66ebf95c12a85f8ef42
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 06/17/2021
ms.locfileid: "52984696"
---
# <a name="add-and-verify-admin-contacts-in-the-admin-portal"></a>在管理门户中添加和验证管理员联系人

有多种方式可以Microsoft 托管桌面与客户进行通信。 为了简化通信并确保我们正在与合适的人员联系，你需要提供一组管理员联系人。 Microsoft 托管桌面IT 运营部门将联系这些人员，帮助解决租户的问题。

> [!IMPORTANT]
> 你可能已经在管理门户中添加了这些联系人。 如果是，请立即仔细检查联系人列表是否准确，因为Microsoft 托管桌面发生严重事件时必须能够联系他们。 

## <a name="azure-active-directory-access-for-microsoft-managed-desktop-admin-portal"></a>Azure Active Directory管理Microsoft 托管桌面的访问权限

Microsoft 托管桌面管理门户要求访问该门户的用户具有以下 AD Azure Active Directory (角色) 之一：
- 全局管理员
- Intune 服务管理员
- 全局读取者
- 服务支持管理员

全局管理员必须是在组织中注册Microsoft 托管桌面。 这五个角色在管理门户中具有相同的访问权限，可以启动和查看任务。 有关在 Azure AD 中分配这些角色的信息，请参阅管理员[角色权限Azure Active Directory。](/azure/active-directory/users-groups-roles/directory-assign-admin-roles) 

## <a name="admin-contact-areas-of-focus"></a>管理员重点关注的联系人区域

管理员联系人应该是可以回答问题并针对不同关注领域做出决策的最佳人员或组。 **Microsoft 托管桌面对于涉及客户提交的支持请求的问题，操作将联系这些管理员联系人。** 这些管理员联系人将收到支持请求更新和新邮件的通知。 这些方面包括：

焦点区域 | 有关
--- | ---
应用打包 | 应用打包疑难解答
设备 | 设备运行状况，Microsoft 托管桌面疑难解答
安全性 | 解决设备Microsoft 托管桌面安全问题
IT 技术支持 | 如果支持人员在支持区域外将用户票证Microsoft 托管桌面的情况 
其他 | 对于其他方面未涵盖的问题

**无论为这些联系人选择谁，都需要有知识和权威来针对您的Microsoft 托管桌面决策。** 当你载入Microsoft 托管桌面环境时，系统将提示你为本地支持人员和安全添加联系人。 

提交支持请求时 [需要管理员联系人](../service-description/support.md)。 你需要有一个管理员联系人来联系支持请求的重点关注区域。 

**添加管理员联系人**

1.  登录到[Microsoft Endpoint Manager](https://endpoint.microsoft.com)。 

2.  在 **"租户管理**"下，**查找**"Microsoft 托管桌面"部分，然后选择"**管理员联系人"。** 

3. 选择“**添加**”。

4.  选择 **一个焦点区域** ，然后输入联系人的信息。 

    ![焦点区域列表，例如"其他"、"应用"和"安全"](../../media/areaoffocus.png)

5. 对每个焦点区域重复上述步骤。 

## <a name="steps-to-get-started-with-microsoft-managed-desktop"></a>开始使用 Microsoft 托管桌面

1. 在管理门户中添加和验证管理员 (本主题) 
2. [调整条件访问](conditional-access.md)
3. [分配许可证](assign-licenses.md)
4. [在设备上安装 Intune 公司门户](company-portal.md)
5. [启用企业状态漫游](enterprise-state-roaming.md)
6. [设置 Microsoft 托管桌面设备](set-up-devices.md)
7. [为用户做好使用设备的准备](get-started-devices.md)
8. [将应用部署到设备](deploy-apps.md)
