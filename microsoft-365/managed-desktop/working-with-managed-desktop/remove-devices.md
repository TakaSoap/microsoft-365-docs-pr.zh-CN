---
title: 删除设备
description: 从管理中删除Microsoft 托管桌面设备
ms.service: m365-md
author: tiaraquan
f1.keywords:
- NOCSH
ms.author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
manager: dougeby
ms.topic: article
audience: Admin
ms.openlocfilehash: 79694b6c33543acc00636676891ee336bce3f8f8
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62034925"
---
# <a name="remove-devices"></a>删除设备

可以使用管理门户Microsoft 托管桌面管理中删除设备。 此操作是永久性的，但你可以按照注册步骤Microsoft 托管桌面注册[它们。](../get-started/register-devices-self.md)

删除设备时，将发生以下所有情况：

- 我们将设备从 Autopilot 中删除。
- 我们将设备从所有"现代工作区"设备组中删除。
- 我们将设备从管理门户 **的"设备** "边栏选项卡中删除。

删除设备时，还可以选择从设备中删除Azure Active Directory (Azure AD) Microsoft Intune。
 
> [!CAUTION]
> 永久删除与设备相关的Azure AD Microsoft Intune对象。 如果删除对象，将无法从 Intune 和 Azure 门户查看或管理设备。 设备无法访问其公司的公司资源。 如果设备在删除后尝试登录，公司数据可能会被删除。

1. 在 [Microsoft Endpoint Manager](https://endpoint.microsoft.com/)**中，选择** 左侧导航窗格中的"设备"。
2. 查找菜单 **Microsoft 托管桌面** 部分，**然后选择设备。**
3. 在Microsoft 托管桌面设备"工作区中，选择要删除的设备。
4. 选择 **"设备** 操作"，然后选择" **删除** 设备"，这将打开一个飞入以删除设备。
5. In the fly-in， review the selected devices and then select **Remove devices**. 如果你还希望同时删除 Azure AD 和 Intune 对象，请选中此复选框。 设备删除可能需要几分钟才能完成。

> [!NOTE]
> 你无法删除正等待注册 **状态** 的设备。