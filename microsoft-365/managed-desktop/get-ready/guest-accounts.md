---
title: 来宾帐户的先决条件
description: 来宾帐户的配置准则以及如何对其进行调整
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: jaimeo
ms.localizationpriority: normal
ms.collection: M365-modern-desktop
ms.author: jaimeo
manager: laurawi
ms.topic: article
ms.openlocfilehash: d8953e9f451daa02671a1e1544f2dfe6649ab1b3
ms.sourcegitcommit: fcc1b40732f28f075d95faffc1655473e262dd95
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/14/2020
ms.locfileid: "49073192"
---
# <a name="prerequisites-for-guest-accounts"></a>来宾帐户的先决条件

Microsoft 托管桌面需要 Azure AD 组织中的以下设置，以供来宾帐户访问。 可以在 " **外部标识/外部协作** " 下的 [Azure 门户](https://portal.azure.com)中调整这些设置：

-   **来宾邀请者角色中的管理员和用户可以邀请** 设置为 **"是"**
-   对于 " **协作限制** "，选择以下任一选项：
    -   如果选择 " **允许将邀请发送到任何域 (最包含的)** ，则不需要其他配置。
    -   如果选择 " **拒绝向指定域发出邀请** "，请确保未在目标域中列出 Microsoft.com。
    -   如果选择 **"仅允许对指定域的邀请" (最严格)** ，请 *确保 Microsoft.com 列* 在目标域中。

如果设置了与这些设置进行交互的限制，请确保排除 Azure Active Directory **新式 Workplace Service 帐户** 。 例如，如果您有一个条件访问策略来阻止来宾帐户访问 Intune 门户，则从该策略中排除 **新式的 Workplace Service 帐户** 组。

