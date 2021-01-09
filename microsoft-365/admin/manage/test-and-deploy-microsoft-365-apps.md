---
title: 测试和部署 Microsoft 365 应用版
f1.keywords:
- NOCSH
ms.author: sirkkuw
author: Sirkkuw
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection: ''
ms.custom: AdminSurgePortfolio
search.appverid: MET150
ROBOTS: NOINDEX, NOFOLLOW
description: 在 Microsoft 365 管理中心的集成应用门户中查找、测试和部署适用于组织中用户和组的 Microsoft 和 Microsoft 合作伙伴应用。
ms.openlocfilehash: b0dc6277461ff03e8aae2e820543f8e5d9e2303c
ms.sourcegitcommit: 7d4aa58ae9fc893825b6e648fa3f072c3ac59628
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/09/2021
ms.locfileid: "49790186"
---
# <a name="test-and-deploy-microsoft-365-apps-in-the-microsoft-365-admin-center"></a>在 Microsoft 365 管理中心测试和部署 Microsoft 365 应用版

Microsoft 365 管理中心让你能够灵活地从单个位置部署 Microsoft 和 Microsoft 合作伙伴应用。 通过集成应用门户查找、测试和完全部署 Microsoft 和 Microsoft 合作伙伴购买和授权的应用，可为组织提供方便和好处，使业务服务定期更新并高效运行。  

有关为组织购买和许可 Microsoft 365 应用的其他信息，请参阅名为"从 Microsoft 365 管理中心管理和部署 [Microsoft 365](https://techcommunity.microsoft.com/t5/microsoft-365-blog/manage-and-deploy-microsoft-365-apps-from-the-microsoft-365/ba-p/1194324)应用版"的博客文章。
  
## <a name="manage-apps-in-the-integrated-apps-portal"></a>在集成应用门户中管理应用

通过选择 Microsoft 365 管理中心中的集成应用，你可以管理已购买和授权的 Microsoft 和 Microsoft 合作伙伴应用的测试和部署。 

1. 在管理中心的左侧导航中 **，选择"** 设置"，然后选择"**集成应用"。** 

2. 选择状态为 **更多****可用应用的应用**。

3. 选择 **"** 在页面顶部部署"，该邮件是指等待部署的消息。

    某些应用要求你先添加用户，然后才能选择"部署 **"。**

    a. 选择 **"添加用户"，** 选择"**完整** 部署"，然后选择"**整个组织**"或"**特定用户/组"。**

    特定用户/组可以是 Microsoft 365 组、安全组或分布式组。

    如果你希望等待 **将** 应用部署到整个组织，也可以选择"测试部署"。

    b. 选择 **"更新****"、"** 完成"，现在可以选择 **"概述"** 选项卡上的 **"部署**"。  

4. 查看应用信息，然后选择"部署 **"。** 

5. 在 **"** 部署完成 **"页上选择"** 完成"。 

    查看"概述"选项卡上的测试或完整 **部署** 的详细信息。

## <a name="find-published-apps-for-testing-and-full-deployment"></a>查找已发布的应用以进行测试和完整部署 

你可以查找、测试和完全部署尚未显示在"集成应用"页上的列表中的已发布应用。 通过从管理中心购买和许可应用，可以从单个位置将 Microsoft 和 Microsoft 合作伙伴应用添加到你的列表中。

1. 在管理中心的左侧导航中 **，选择"** 设置"，然后选择"**集成应用"。** 

2. 选择 **"获取** 应用列表上方的应用"。

3. 在 **"Microsoft 365** 应用发布应用"页上，选择想要部署的应用，选择"**立即获取"。**

4. 接受权限，然后选择"继续 **"。**

5. 选择 **"** 在页面顶部部署"，该邮件是指等待部署的消息。

    某些应用要求你先添加用户，然后才能选择"部署 **"。**

    a. 选择 **"添加用户"，** 选择"**完整** 部署"，然后选择"**整个组织**"或"**特定用户/组"。**

    特定用户/组可以是 Microsoft 365 组、安全组或分布式组。

    如果你希望等待 **将** 应用部署到整个组织，也可以选择"测试部署"。

    b. 选择 **"更新****、** 完成"，现在可以选择 **"概述"** 选项卡上的 **"部署**"。  

6. 查看应用信息，然后选择"部署 **"。** 

7. 在 **"** 部署完成 **"页上选择"** 完成"。 

    查看"概述"选项卡上的测试或完整 **部署** 的详细信息。

在 Microsoft 365 管理中心中，每个已部署的应用状态都符合部署类型的测试部署、完整部署或 **自定义** 以及你部署应用的日期。 

> [!NOTE]
> 如果应用以前从集成应用门户外的其他位置部署，则 **部署类型为****"自定义"。**

## <a name="unsupported-scenarios"></a>不受支持的方案

当前不支持从集成应用门户部署以下方案：

- 应用或外接程序链接到多个软件作为 SaaS (服务) 。
- SaaS 应用链接到应用和外接程序，但它没有关联的 AADid。
- 两个 SaaS 应用共享同一个 AADid，它们均链接到应用或外接程序。
  