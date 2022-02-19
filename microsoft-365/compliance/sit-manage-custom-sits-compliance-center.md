---
title: 在合规中心管理自定义敏感信息类型
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何在合规中心修改和删除自定义敏感信息类型。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 0efbb93096fc3c0b61a57319aa2d23a079f684d1
ms.sourcegitcommit: bb493f12701f6d6ee7d5e64b541adb87470bc7bc
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/18/2022
ms.locfileid: "62902569"
---
# <a name="manage-custom-sensitive-information-types-in-the-compliance-center"></a>在合规中心管理自定义敏感信息类型

本文将引导你完成修改和删除合规性中心中的现有自定义敏感信息类型的步骤。

## <a name="modify-custom-sensitive-information-types-in-the-compliance-center"></a>在合规中心内修改自定义敏感信息类型

1. 在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从要修改的列表中选择敏感信息类型，然后选择“**编辑**”。

2. 可以添加其他模式，其中包括唯一的主元素和支持元素、可信度、字符邻近度和 [**其他检查**](sit-regex-validators-additional-checks.md#sensitive-information-type-additional-checks)，或者编辑/删除现有的模式。

## <a name="remove-custom-sensitive-information-types-in-the-compliance-center"></a>移除合规中心中的自定义敏感信息类型 

> [!NOTE]
> 只能删除自定义敏感信息类型；不能删除内置敏感信息类型。

> [!IMPORTANT]
> 删除自定义敏感信息类型前，请先验证没有 DLP 策略或 Exchange 邮件流规则（亦称为“传输规则”）仍在引用此敏感信息类型。

1. 在“合规中心”中，转到“**数据分类**”\>“**敏感信息类型**”，然后从列表中选择要删除的敏感信息类型。

2. 在打开的浮出控件中，选择“**删除**”。
