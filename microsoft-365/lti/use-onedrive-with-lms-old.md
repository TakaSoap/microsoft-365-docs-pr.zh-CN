---
title: 使用 OneDrive Learning 工具互操作性
ms.author: v-cichur
author: cichur
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
localization_priority: Normal
ROBOTS: NOINDEX, NOFOLLOW
description: 使用新的 OneDrive Learning 互操作性应用创建和评级作业、构建和选择课程内容，并实时协作处理文件。
ms.openlocfilehash: 0e437ed4b05b9968ee1e853f668787eed5351fb5
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256936"
---
# <a name="use-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="62adf-103">将 Microsoft OneDrive LTI 与 Canvas 一同使用</span><span class="sxs-lookup"><span data-stu-id="62adf-103">Use Microsoft OneDrive LTI with Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="62adf-104">某些信息与预发布的产品有关，在商业发布之前可能有重大修改。</span><span class="sxs-lookup"><span data-stu-id="62adf-104">Some information relates to prereleased product which may be substantially modified before it's commercially released.</span></span> <span data-ttu-id="62adf-105">Microsoft 对此处所提供的信息不作任何明示或默示的保证。</span><span class="sxs-lookup"><span data-stu-id="62adf-105">Microsoft makes no warranties, express or implied, with respect to the information provided here.</span></span>

## <a name="integrate-with-canvas"></a><span data-ttu-id="62adf-106">与 Canvas 集成</span><span class="sxs-lookup"><span data-stu-id="62adf-106">Integrate with Canvas</span></span>

<span data-ttu-id="62adf-107">执行此集成的人应是 Canvas 的管理员和 Microsoft 365 管理员。</span><span class="sxs-lookup"><span data-stu-id="62adf-107">The person who performs this integration should be an admin of Canvas and an admin of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="62adf-108">使用租户管理员Microsoft Azure登录租户门户。</span><span class="sxs-lookup"><span data-stu-id="62adf-108">Sign in to the Microsoft Azure portal with the tenant admin account.</span></span> <span data-ttu-id="62adf-109">Azure 租户管理员还应具有组管理员角色。</span><span class="sxs-lookup"><span data-stu-id="62adf-109">The Azure tenant administrator should also have the Group administrator role.</span></span>

    ![突出显示的组管理员](../media/lti-media/lti-group-admin.png)

2. <span data-ttu-id="62adf-111">登录到 Microsoft OneDrive [LTI 门户](https://odltiappnl.azurewebsites.net/admin)。</span><span class="sxs-lookup"><span data-stu-id="62adf-111">Sign in to the Microsoft [OneDrive LTI portal](https://odltiappnl.azurewebsites.net/admin).</span></span>

3. <span data-ttu-id="62adf-112">接受权限以完成登录。</span><span class="sxs-lookup"><span data-stu-id="62adf-112">Accept the permissions to complete the sign-in.</span></span>

    ![接受权限](../media/lti-media/lti-permissions.png)

4. <span data-ttu-id="62adf-114">选择 **"添加 LTI 租户"。**</span><span class="sxs-lookup"><span data-stu-id="62adf-114">Select **Add LTI Tenant**.</span></span>

     ![添加 LTI 租户](../media/lti-media/lti-add-tenant.png)

5. <span data-ttu-id="62adf-116">从 **下拉列表中选择 LTI 消费者\*\*\*\*平台作为画布**。</span><span class="sxs-lookup"><span data-stu-id="62adf-116">Select **LTI Consumer Platform** as **Canvas** from the dropdown.</span></span>

6. <span data-ttu-id="62adf-117">选择 **"画布基 URL"，** 然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="62adf-117">Select **Canvas Base URL** and then select **Next**.</span></span>

    ![选择"画布"并添加基 URL](../media/lti-media/lti-canvas-base-url.png)

   <span data-ttu-id="62adf-119">下一个屏幕将显示对你有机密的字段。</span><span class="sxs-lookup"><span data-stu-id="62adf-119">The next screen shows fields that are confidential to you.</span></span>

7. <span data-ttu-id="62adf-120">Select **Next** from ？？</span><span class="sxs-lookup"><span data-stu-id="62adf-120">Select **Next** from ??</span></span> <span data-ttu-id="62adf-121">page.</span><span class="sxs-lookup"><span data-stu-id="62adf-121">page.</span></span> <span data-ttu-id="62adf-122">审阅者可以在此处填写空白吗？</span><span class="sxs-lookup"><span data-stu-id="62adf-122">CAN REVIEWERS FILL IN THE BLANK HERE?</span></span>

8. <span data-ttu-id="62adf-123">在 **显示** 机密信息的屏幕上选择"下一步"。</span><span class="sxs-lookup"><span data-stu-id="62adf-123">Select **Next** in the screen that shows information that's confidential to you.</span></span>

   <span data-ttu-id="62adf-124">Azure 门户的最终屏幕显示添加 Canvas 实例的以下步骤。</span><span class="sxs-lookup"><span data-stu-id="62adf-124">The final screen of the Azure portal shows the next steps for adding your Canvas instance.</span></span>

9. <span data-ttu-id="62adf-125">从此屏幕复制开发人员密钥。</span><span class="sxs-lookup"><span data-stu-id="62adf-125">Copy the Developer Keys from this screen.</span></span> <span data-ttu-id="62adf-126">你将在创建 Canvas 实例时使用。</span><span class="sxs-lookup"><span data-stu-id="62adf-126">You'll use when you create the Canvas instance.</span></span>

## <a name="add-the-canvas-instance"></a><span data-ttu-id="62adf-127">添加 Canvas 实例</span><span class="sxs-lookup"><span data-stu-id="62adf-127">Add the Canvas instance</span></span>

1. <span data-ttu-id="62adf-128">在 Canvas 实例中，取消选择 **"管理员**  >  **开发人员密钥"。**</span><span class="sxs-lookup"><span data-stu-id="62adf-128">In your Canvas instance, deselect **Admin** > **Developer Keys**.</span></span>

2. <span data-ttu-id="62adf-129">在 **"开发人员密钥"下拉列表中选择"LTI** **密钥"。**</span><span class="sxs-lookup"><span data-stu-id="62adf-129">Choose **LTI Key** in the dropdown on **Developer Key**.</span></span>

   ![获取 LTI 开发人员密钥](../media/lti-media/lti-developer-keys.png)

3. <span data-ttu-id="62adf-131">在此处粘贴开发人员密钥。</span><span class="sxs-lookup"><span data-stu-id="62adf-131">Paste the developer keys here.</span></span>

     ![粘贴开发人员密钥](../media/lti-media/lti-developer-keys.png)

   <span data-ttu-id="62adf-133">密钥在 **OFF** 模式下创建</span><span class="sxs-lookup"><span data-stu-id="62adf-133">The key gets created in **OFF** mode</span></span>

   ![在关闭模式下创建的开发人员密钥](../media/lti-media/lti-copy-developer-keys.png)

4. <span data-ttu-id="62adf-135">复制突出显示的文本。</span><span class="sxs-lookup"><span data-stu-id="62adf-135">Copy the highlighted text.</span></span>
    <span data-ttu-id="62adf-136">在 LTI 门户中，Microsoft OneDrive客户端 ID。</span><span class="sxs-lookup"><span data-stu-id="62adf-136">This serves as Client ID in Microsoft OneDrive LTI portal.</span></span>

5. <span data-ttu-id="62adf-137">将文本粘贴到 LTI 门户Microsoft OneDrive"客户端 **ID"** 字段中，然后选择"下一 **步"。**</span><span class="sxs-lookup"><span data-stu-id="62adf-137">Paste the text into the **Client ID** field in Microsoft OneDrive LTI portal, and then select **Next**.</span></span>

6. <span data-ttu-id="62adf-138">选择“**保存**”。</span><span class="sxs-lookup"><span data-stu-id="62adf-138">Select **Save**.</span></span>

7. <span data-ttu-id="62adf-139">通过选择查看 **LTI 租户查看设置**。</span><span class="sxs-lookup"><span data-stu-id="62adf-139">View the settings by selecting **View LTI Tenants**.</span></span>
