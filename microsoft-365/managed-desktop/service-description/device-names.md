---
title: 设备名称
description: Microsoft 托管桌面如何管理设备名称
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
ms.openlocfilehash: adf4809e0d8dc29f170475435b19092abf2062fd
ms.sourcegitcommit: 55791ddab9ae484f76b30f0470eec8a4cf7b46d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/20/2021
ms.locfileid: "51893714"
---
# <a name="device-names"></a>设备名称

Microsoft 托管桌面使用 Windows Autopilot、Azure Active Directory 和 Microsoft Intune。 若要使这些服务无缝协作，设备需要一致的标准化名称。 Microsoft 托管桌面在注册设备 (*MMD-%RAND11*) 标准名称格式。 Windows Autopilot 分配这些名称。 有关 Autopilot 详细信息，请参阅 [Autopilot 首次运行体验和注册状态页面](../get-started/esp-first-run.md)。

## <a name="automated-name-changes"></a>自动更改名称

如果设备稍后重命名，Microsoft 托管桌面将自动将其重命名为标准化格式的新名称。 此过程每四小时执行一次。 在用户下次重新启动设备时，将发生名称更改。

> [!IMPORTANT]
> 如果你的环境依赖于特定设备名称 (例如，为了支持特定的网络配置) ，你应该调查在注册 Microsoft 托管桌面之前删除该依赖关系的选项。 如果必须保留名称依赖项，可以通过管理门户提交请求以禁用重命名功能并使用[](../working-with-managed-desktop/admin-support.md)所需的名称格式。