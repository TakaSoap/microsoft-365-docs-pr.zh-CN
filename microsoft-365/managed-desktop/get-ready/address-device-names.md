---
title: 地址设备名称依赖关系
description: 删除对设备名称的依赖或请求异常
ms.service: m365-md
author: jaimeo
f1.keywords:
- NOCSH
ms.author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
manager: laurawi
ms.topic: article
audience: Admin
ms.openlocfilehash: 8c82acb5306e3add7c41fd4e6f7e313782d47574
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893716"
---
# <a name="address-device-name-dependency"></a>地址设备名称依赖关系

Microsoft 托管桌面注册设备时应用标准化名称格式，如果以后更改名称，将自动重命名设备。 有关详细信息，请参阅设备 [名称](../service-description/device-names.md)。

> [!IMPORTANT]
> 如果你的环境依赖于特定设备 (例如，为了支持特定的网络配置) ，你应该调查在注册到 Microsoft 托管桌面 之前删除该依赖关系的选项。 如果必须保留名称依赖项，可以通过管理门户提交请求以禁用重命名功能并使用[](../working-with-managed-desktop/admin-support.md)所需的名称格式。