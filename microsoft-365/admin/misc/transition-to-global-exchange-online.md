---
title: 更新 MX 记录以转换到全局 Exchange Online 服务
f1.keywords:
- CSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
description: 了解如何从德国 Microsoft 云Exchange Online全球 Exchange Online服务
ms.openlocfilehash: 8de64e30205b07a0c20a8ae4f7cdedbf6cc6824f
ms.sourcegitcommit: 628f195cbe3c00910f7350d8b09997a675dde989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/21/2020
ms.locfileid: "48644851"
---
# <a name="update-your-mx-records-to-transition-to-the-global-exchange-online-service"></a><span data-ttu-id="b2439-103">更新 MX 记录以转换到全局 Exchange Online 服务</span><span class="sxs-lookup"><span data-stu-id="b2439-103">Update your MX records to transition to the global Exchange Online service</span></span>

1. <span data-ttu-id="b2439-104">登录到管理 [Microsoft 365，](https://admin.microsoft.com)**然后转到"设置**  >  **域"**</span><span class="sxs-lookup"><span data-stu-id="b2439-104">Sign in to [Microsoft 365 admin portal](https://admin.microsoft.com), and go to **Settings** > **Domains**</span></span>

2. <span data-ttu-id="b2439-105">状态将显示在每个域的右侧。</span><span class="sxs-lookup"><span data-stu-id="b2439-105">Status will be shown on the right side for each domain.</span></span> <span data-ttu-id="b2439-106">如果组织的域指向德国 Microsoft 云Exchange Online，则需要更新 MX 记录。</span><span class="sxs-lookup"><span data-stu-id="b2439-106">If your organization’s domains point to Microsoft Cloud Germany Exchange Online, you'll need to update your MX record.</span></span>

3. <span data-ttu-id="b2439-107">单击域，然后单击检测到 **的 DNS 错误，单击此处查看**。</span><span class="sxs-lookup"><span data-stu-id="b2439-107">Click the domain, then click **DNS errors detected, click here to view**.</span></span>

4. <span data-ttu-id="b2439-108">此页面将包含说明如何修复 MX 记录的说明。</span><span class="sxs-lookup"><span data-stu-id="b2439-108">This page will have instructions to show you how to fix the MX record.</span></span> <span data-ttu-id="b2439-109">如果域的注册[机构使用域](../setup/add-domain.md#registrars-with-domain-connect)连接，可以单击顶部的"修复我的记录"。</span><span class="sxs-lookup"><span data-stu-id="b2439-109">If your domain’s registrar uses [Domain Connect](../setup/add-domain.md#registrars-with-domain-connect), you can click “Fix my records” on top.</span></span> <span data-ttu-id="b2439-110">否则，你可以按照向导中的链接，分步 **说明注册** 机构。</span><span class="sxs-lookup"><span data-stu-id="b2439-110">Otherwise you can follow the link in the wizard to **step-by-step instructions** for your registrar.</span></span>