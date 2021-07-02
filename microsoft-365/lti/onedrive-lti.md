---
title: 使用 Microsoft OneDrive Learning 工具互操作性
ms.author: heidip
author: MicrosoftHeidi
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
description: 使用新的 Microsoft OneDrive Learning 互操作性应用创建和评级作业、构建和选择课程内容，并实时协作处理文件。
ms.openlocfilehash: 985a316bac689b9bc6c53ab65782d548fcad0db8
ms.sourcegitcommit: a4c93a4c7d7db08fe3b032b58d5c7dbbb9476e90
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/02/2021
ms.locfileid: "53256946"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a><span data-ttu-id="ff79b-103">将 Microsoft OneDrive LTI 与 Canvas 集成</span><span class="sxs-lookup"><span data-stu-id="ff79b-103">Integrate Microsoft OneDrive LTI with Canvas</span></span>

<span data-ttu-id="ff79b-104">将 Microsoft OneDrive LTI 与 Canvas 集成的过程有两个步骤。</span><span class="sxs-lookup"><span data-stu-id="ff79b-104">Integrating Microsoft OneDrive LTI with Canvas is a two step process.</span></span> <span data-ttu-id="ff79b-105">第一步在 Canvas Microsoft OneDrive，第二步使 Microsoft OneDrive LTI 在 Canvas 课程内可用。</span><span class="sxs-lookup"><span data-stu-id="ff79b-105">The first step enables Microsoft OneDrive in Canvas, and the second step makes the Microsoft OneDrive LTI available within Canvas courses.</span></span>

## <a name="recommended-browser-settings"></a><span data-ttu-id="ff79b-106">建议的浏览器设置</span><span class="sxs-lookup"><span data-stu-id="ff79b-106">Recommended browser settings</span></span>

- <span data-ttu-id="ff79b-107">应启用 Cookie Microsoft OneDrive。</span><span class="sxs-lookup"><span data-stu-id="ff79b-107">Cookies should be enabled for Microsoft OneDrive.</span></span>
- <span data-ttu-id="ff79b-108">不应阻止弹出窗口进行Microsoft OneDrive。</span><span class="sxs-lookup"><span data-stu-id="ff79b-108">Popups should not be blocked for Microsoft OneDrive.</span></span>

> [!NOTE]
> - <span data-ttu-id="ff79b-109">默认情况下，Cookie 不会在 Chrome 浏览器隐身模式下启用，并且需要启用。</span><span class="sxs-lookup"><span data-stu-id="ff79b-109">Cookies are not enabled by default in the Chrome browser incognito mode, and will need to be enabled.</span></span>
> - <span data-ttu-id="ff79b-110">Microsoft OneDriveLTI 在专用模式下在专用Microsoft Edge运行。</span><span class="sxs-lookup"><span data-stu-id="ff79b-110">Microsoft OneDrive LTI works in the private mode in Microsoft Edge browser.</span></span> <span data-ttu-id="ff79b-111">确保您未阻止默认情况下 (启用的 cookie) 。</span><span class="sxs-lookup"><span data-stu-id="ff79b-111">Ensure that you have not blocked cookies (which are enabled by default).</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a><span data-ttu-id="ff79b-112">在画布Microsoft OneDrive LTI</span><span class="sxs-lookup"><span data-stu-id="ff79b-112">Enable Microsoft OneDrive LTI in Canvas</span></span>

> [!IMPORTANT]
> <span data-ttu-id="ff79b-113">执行此集成的人应是 Canvas 的管理员和 Microsoft 365 管理员。</span><span class="sxs-lookup"><span data-stu-id="ff79b-113">The person who performs this integration should be an administrator of Canvas and an administrator of the Microsoft 365 tenant.</span></span>

1. <span data-ttu-id="ff79b-114">登录到 Microsoft OneDrive <a href="https://onedrivelti.microsoft.com/admin" target="_blank">LTI 注册门户</a></span><span class="sxs-lookup"><span data-stu-id="ff79b-114">Sign into the <a href="https://onedrivelti.microsoft.com/admin" target="_blank">Microsoft OneDrive LTI Registration Portal</a></span></span>
1. <span data-ttu-id="ff79b-115">选择 **"管理员同意"** 按钮并接受权限。</span><span class="sxs-lookup"><span data-stu-id="ff79b-115">Select the **Admin Consent** button and accept the permissions.</span></span>
1. <span data-ttu-id="ff79b-116">选择" **新建 LTI 租户"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ff79b-116">Select the **Create new LTI Tenant** button.</span></span> <span data-ttu-id="ff79b-117">在"LTI 注册"页上，选择下拉列表中的" **画布** "，然后输入 Canvas 实例的基本 URL。</span><span class="sxs-lookup"><span data-stu-id="ff79b-117">On the LTI Registration page select **Canvas** in the dropdown and enter the base URL of your Canvas instance.</span></span>

> [!NOTE]
> <span data-ttu-id="ff79b-118">例如，如果 Canvas 实例为 https://contoso.test.instructure.com ] (https://contoso.test.instructure.com) ，则应该输入完整的 URL。</span><span class="sxs-lookup"><span data-stu-id="ff79b-118">If your Canvas instance is, for example, https://contoso.test.instructure.com](https://contoso.test.instructure.com), then the complete URL should be entered.</span></span>

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="LTI 租户管理页面，包含用于选择 LTI 使用者平台的下拉列表字段和 URL 文本字段。":::

4. <span data-ttu-id="ff79b-120">通过选择"复制"按钮复制JSON (右侧显示两个页面的右侧图标，其中两个页面彼此) 。</span><span class="sxs-lookup"><span data-stu-id="ff79b-120">Copy the JSON by selecting the **Copy** button (an icon on the right that shows two pages on top of one another).</span></span> <span data-ttu-id="ff79b-121">这将用于在 Canvas 中生成密钥。</span><span class="sxs-lookup"><span data-stu-id="ff79b-121">This will be used to generate the key in Canvas.</span></span>

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="显示复制按钮的图像，该按钮将复制显示的 JSON 文本，并可在 Canvas 中生成密钥。":::

5. <span data-ttu-id="ff79b-123">以管理员角色登录到 Canvas 实例，然后从页面左侧的菜单中选择"开发人员密钥"。</span><span class="sxs-lookup"><span data-stu-id="ff79b-123">Sign into your Canvas instance as the administrator and select **Developer Keys** from the menu on the left side of the page.</span></span> <span data-ttu-id="ff79b-124">从下拉列表中，通过从页面右上角的下拉列表选择 **LTI 密钥** 来创建开发人员密钥。</span><span class="sxs-lookup"><span data-stu-id="ff79b-124">From the dropdown, create a developer key by choosing **LTI Key** from the dropdown on the upper right of the page.</span></span>

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="显示左侧导航栏（选择&quot;开发工具&quot;，并且从页面右侧下拉列表选择 LTI 键条目）的屏幕截图。":::

6. <span data-ttu-id="ff79b-126">On the Configure page， in the **Method** dropdown， select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span><span class="sxs-lookup"><span data-stu-id="ff79b-126">On the Configure page, in the **Method** dropdown, select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.</span></span>
7. <span data-ttu-id="ff79b-127">保存密钥，它以 Off 状态在 Canvas **中** 可用。</span><span class="sxs-lookup"><span data-stu-id="ff79b-127">Save the key, and it becomes available in Canvas in an **Off** state.</span></span> <span data-ttu-id="ff79b-128">打开该 **键** 并复制"详细信息"列中给定的键，以用于下一步。</span><span class="sxs-lookup"><span data-stu-id="ff79b-128">Turn the key **On** and copy the key given in the **Details** column to be used in the next step.</span></span>

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="键设置为关闭状态中的 Canvas 页面。需要将其打开，并且需要从此页面的详细信息列中复制密钥。":::

8. <span data-ttu-id="ff79b-130">返回到"Microsoft OneDrive LTI 注册门户"，然后将密钥粘贴到 **"Canvas 客户端 ID"** 字段中。</span><span class="sxs-lookup"><span data-stu-id="ff79b-130">Return to the Microsoft OneDrive LTI Registration portal and paste the key in the **Canvas Client ID** field.</span></span> <span data-ttu-id="ff79b-131">准备就绪 **后** ，选择"下一步"。</span><span class="sxs-lookup"><span data-stu-id="ff79b-131">Select **Next** when you're ready.</span></span>

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="LTI 租户注册页面，其中显示 JSON 文本和密钥应复制到的文本框。":::

9. <span data-ttu-id="ff79b-133">查看并保存更改。</span><span class="sxs-lookup"><span data-stu-id="ff79b-133">Review and save your changes.</span></span> <span data-ttu-id="ff79b-134">成功注册时将显示一条消息。</span><span class="sxs-lookup"><span data-stu-id="ff79b-134">A message will be displayed on successful registration.</span></span>
10. <span data-ttu-id="ff79b-135">还可通过选择主页上的"查看 **LTI** 租户"按钮来查看注册详细信息。</span><span class="sxs-lookup"><span data-stu-id="ff79b-135">Your registration details can also be reviewed by selecting the **View LTI Tenants** button on the home page.</span></span>

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="ff79b-136">在画布Microsoft OneDrive启用 LTI</span><span class="sxs-lookup"><span data-stu-id="ff79b-136">Enable Microsoft OneDrive LTI in Canvas Courses</span></span>

<span data-ttu-id="ff79b-137">Canvas 管理员可以针对所有课程Microsoft OneDrive LTI。</span><span class="sxs-lookup"><span data-stu-id="ff79b-137">A Canvas administrator can enable Microsoft OneDrive LTI for all courses.</span></span> <span data-ttu-id="ff79b-138">如果Microsoft OneDrive特定课程需要 LTI (而不是所有课程) ，则课程教师需要按照课程设置中的相同步骤操作。</span><span class="sxs-lookup"><span data-stu-id="ff79b-138">If Microsoft OneDrive LTI is needed in a specific course (and not all courses), the course educator needs to follow the same steps within the course settings.</span></span>

1. <span data-ttu-id="ff79b-139">以管理员角色登录并转到 **设置部分。**</span><span class="sxs-lookup"><span data-stu-id="ff79b-139">Sign in as an administrator and go to the **Settings** section.</span></span>
2. <span data-ttu-id="ff79b-140">转到"应用 **"部分** 并选择" **查看应用配置"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ff79b-140">Go to the **Apps** section and select the **View App Configurations** button.</span></span>
3. <span data-ttu-id="ff79b-141">选择" **添加应用"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ff79b-141">Select the **Add App** button.</span></span>
4. <span data-ttu-id="ff79b-142">在" **配置类型"** 下拉列表中，选择" **按客户端 ID"** 选项。</span><span class="sxs-lookup"><span data-stu-id="ff79b-142">In the **Configuration Type** dropdown, choose the **By Client ID** option.</span></span>
5. <span data-ttu-id="ff79b-143">粘贴之前在"客户端 **ID"** 字段中生成的开发人员密钥的值，然后选择"提交 **"** 按钮。</span><span class="sxs-lookup"><span data-stu-id="ff79b-143">Paste the value of the developer key generated previously in the **Client ID** field, and select the **Submit** button.</span></span>

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="&quot;添加应用&quot;页，显示&quot;配置类型&quot;下拉菜单下的&quot;按客户端 ID&quot;选项。":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a><span data-ttu-id="ff79b-145">Canvas 课程设置 LTI Microsoft OneDrive协作工具</span><span class="sxs-lookup"><span data-stu-id="ff79b-145">Collaboration Settings for Microsoft OneDrive LTI in Canvas Courses</span></span>

> [!NOTE]
> <span data-ttu-id="ff79b-146">为了使协作适用于教师和学生，不应启用协作设置。</span><span class="sxs-lookup"><span data-stu-id="ff79b-146">For collaboration to work for educators and students, you shouldn't enable the collaboration setting.</span></span> <span data-ttu-id="ff79b-147">若要确保未启用该设置，请按照以下步骤操作。</span><span class="sxs-lookup"><span data-stu-id="ff79b-147">To make sure the setting isn't enabled, follow the steps below.</span></span>

1. <span data-ttu-id="ff79b-148">以管理员角色登录并转到 **设置部分。**</span><span class="sxs-lookup"><span data-stu-id="ff79b-148">Sign in as an admin and go to the **Settings** section.</span></span>
1. <span data-ttu-id="ff79b-149">转到 **"功能选项** "部分，然后转到"课程 **"** 部分。</span><span class="sxs-lookup"><span data-stu-id="ff79b-149">Go to **Feature Options** section, and then go to the **Course** section.</span></span>
1. <span data-ttu-id="ff79b-150">将 **"外部协作工具** "功能设置为未启用。</span><span class="sxs-lookup"><span data-stu-id="ff79b-150">Set the **External Collaborations Tool** feature to be not enabled.</span></span>

> [!NOTE]
> <span data-ttu-id="ff79b-151">可以将协作分配给单个学生和学生组。</span><span class="sxs-lookup"><span data-stu-id="ff79b-151">Collaboration can be assigned to individual students and to groups of students.</span></span> <span data-ttu-id="ff79b-152">默认情况下，分配给单个学生有效。</span><span class="sxs-lookup"><span data-stu-id="ff79b-152">Assigning to individual students works by default.</span></span> <span data-ttu-id="ff79b-153">若要能够将协作分配给学生组，请按照以下步骤操作：</span><span class="sxs-lookup"><span data-stu-id="ff79b-153">To be able to assign collaboration to group of students, follow these steps:</span></span>

1. <span data-ttu-id="ff79b-154">以管理员角色登录并转到 **"开发人员密钥"** 部分。</span><span class="sxs-lookup"><span data-stu-id="ff79b-154">Login as admin and go to the **Developer Keys** section.</span></span>
1. <span data-ttu-id="ff79b-155">查找值为 1700000000000710 的键，并设置为 **"打开"。**</span><span class="sxs-lookup"><span data-stu-id="ff79b-155">Find the key with value 170000000000710 and set it to **On**.</span></span>
