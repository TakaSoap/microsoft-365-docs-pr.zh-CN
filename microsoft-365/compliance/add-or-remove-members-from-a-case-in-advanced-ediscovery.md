---
title: 向事例添加成员或从事例中删除成员
f1.keywords:
- NOCSH
ms.author: markjjo
author: markjjo
manager: laurawi
ms.date: ''
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection: M365-security-compliance
search.appverid:
- MOE150
- MET150
ms.assetid: ''
description: 了解如何在管理案例时添加或删除可以访问Advanced eDiscovery的成员。
ms.custom: seo-marvel-mar2020
ms.openlocfilehash: 8e239622add6965a280e9c2b01bc00d9f2b9b0d5
ms.sourcegitcommit: 317fab13e84b2867087a6ba0a593313ecf43bbed
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/15/2021
ms.locfileid: "60364659"
---
# <a name="add-or-remove-members-from-a-case"></a>向事例添加成员或从事例中删除成员

可添加或删除成员，管理可以访问此案例的人。 但是，在成员可以访问 Advanced eDiscovery case (并执行) 情况下的任务之前，必须将用户添加到 Microsoft 365 合规中心 中"权限"页上的"电子数据展示管理员"角色组中。  有关详细信息，请参阅[分配电子数据展示权限](./assign-ediscovery-permissions.md)。

1. 在 **高级电子数据** 页面上，转到你想要将成员添加到的大小写。

2. 单击 **“设置”** 选项卡，然后在 **“访问和权限”** 图块中单击 **“选择”**。

3. 在 **管理成员**， **添加** 以将成员添加到案例。 您还可以选择通过单击"管理角色组"下的"  **添加** "将角色组 **添加到案例**。

4. 在可添加为案例成员的人或角色组列表中，选中要添加的人名或角色组名称旁边的复选框。

   > [!NOTE]
   > 向案例添加角色组时，只能添加作为成员的角色组。

5. 选择要添加为案例成员的人或角色组后，单击"添加 **"。**

6. 在 **管理此案例** 弹出页面中， **保存** 以保存新的案例成员列表。

> [!IMPORTANT]
> 如果在已添加为案例成员的角色组中添加或删除角色，则角色组将自动删除为案例 (或者该角色组是) 成员的任何情况。 这样做的原因是保护组织避免无意中向案件的成员提供其他权限。 同样，如果删除了某个角色组，则它将从它作为成员的所有事例中删除。 有关详细信息，请参阅[分配电子数据展示权限](assign-ediscovery-permissions.md#adding-role-groups-as-members-of-ediscovery-cases)。

## <a name="removing-members-from-a-case"></a>从案例中删除成员

只有 [电子数据展示管理员可以](assign-ediscovery-permissions.md) 从案例中删除成员。 即使您被分配到电子数据展示管理员角色组或最初创建了该案例，您也将无法从案例中删除自己或其他成员，除非您也是电子数据展示管理员。 若要将自己或其他成员从案例中删除，请联系您组织的电子数据展示管理员。
