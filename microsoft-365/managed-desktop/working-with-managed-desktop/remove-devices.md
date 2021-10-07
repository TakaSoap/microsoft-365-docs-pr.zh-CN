---
title: 删除设备
description: 从管理中删除Microsoft 托管桌面设备
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 7da1bac830df352e776d9a9f59dc33cf5a22b8ee
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60169871"
---
# <a name="remove-devices"></a>删除设备

可以使用管理门户从Microsoft 托管桌面管理中删除设备。 此操作是永久性的，但你可以按照注册步骤Microsoft 托管桌面注册[它们。](../get-started/register-devices-self.md)

删除设备时，将发生以下所有情况：

- 我们将设备从 Autopilot 中删除。
- 我们将设备从所有"现代工作区"设备组中删除。
- 我们将设备从管理门户 **的"设备** "边栏选项卡中删除。

删除设备时，还可以选择将其从 Azure AD Azure Active Directory (中删除) Microsoft Intune。
 
> [!CAUTION]
> 从 Azure AD 中删除与设备相关的对象Microsoft Intune永久。 如果删除对象，将无法从 Intune 和 Azure 门户查看或管理设备。 设备无法访问其公司的公司资源。 如果设备在删除后尝试登录，公司数据可能会被删除。

1. 在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)**中，选择** 左侧导航窗格中的"设备"。
2. 查找菜单 **Microsoft 托管桌面** 部分，**然后选择设备。**
3. 在Microsoft 托管桌面设备"工作区中，选择要删除的设备。
4. 选择 **"设备** 操作"，然后选择" **删除** 设备"，这将打开一个飞入以删除设备。
5. In the fly-in， review the selected devices and then select **Remove devices**. 如果要同时删除 Azure AD 和 Intune 对象，请选中此复选框。 设备删除可能需要几分钟才能完成。

> [!NOTE]
> 你无法删除正等待注册 **状态** 的设备。