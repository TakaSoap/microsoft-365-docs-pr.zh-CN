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
ms.localizationpriority: medium
ROBOTS: NOINDEX, NOFOLLOW
description: 使用新的工具互操作性应用创建作业并评分、生成和选择课程内容，并实时协作处理Microsoft OneDrive Learning文件。
ms.openlocfilehash: d8243580b32b8ba3b42297d1d5ec4183f7eee7d7
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60173171"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>将 Microsoft OneDrive LTI 与 Canvas 集成

> [!IMPORTANT]
> 某些信息与预发行产品相关，在商业发行之前可能会对其进行重大修改。 Microsoft 对此处所提供的信息不作任何明示或默示的保证。

将 Microsoft OneDrive LTI 与 Canvas 集成的过程有两个步骤。 第一步在 Canvas Microsoft OneDrive，第二步使 Microsoft OneDrive LTI 在 Canvas 课程内可用。

## <a name="recommended-browser-settings"></a>建议的浏览器设置

- 应为用户启用 cookie Microsoft OneDrive。
- 不应阻止弹出窗口进行Microsoft OneDrive。

> [!NOTE]
> - 默认情况下，Cookie 不会在 Chrome 浏览器隐身模式下启用，并且需要启用。
> - Microsoft OneDriveLTI 在专用模式下在专用Microsoft Edge运行。 确保您未阻止默认情况下 (启用的 cookie) 。

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>在画布Microsoft OneDrive LTI

> [!IMPORTANT]
> 执行此集成的人应是 Canvas 的管理员和 Microsoft 365 管理员。

1. 登录到 Microsoft OneDrive <a href="https://onedrivelti.microsoft.com/admin" target="_blank">LTI 注册门户</a>
1. 选择 **"管理员同意"** 按钮并接受权限。

> [!CAUTION]
> 如果未执行此步骤，则以下步骤将出现错误，一旦获得错误，你将无法在一小时内执行此步骤。

3. 选择" **新建 LTI 租户"** 按钮。 在"LTI 注册"页上，选择下拉列表中的" **画布** "，然后输入 Canvas 实例的基本 URL。

> [!NOTE]
> 例如，如果 Canvas 实例为 https://contoso.test.instructure.com ] (，则应该输入 https://contoso.test.instructure.com) 完整的 URL。

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="LTI 租户管理页面，包含用于选择 LTI 使用者平台的下拉列表字段和 URL 文本字段。":::

4. 通过选择"复制"按钮复制JSON (右侧显示两个页面的右侧图标，其中两个页面彼此) 。 这将用于在 Canvas 中生成密钥。

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="显示复制按钮的图像，该按钮将复制显示的 JSON 文本，并可在 Canvas 中生成密钥。":::

5. 以管理员角色登录到 Canvas 实例，然后从页面左侧的菜单中选择"开发人员密钥"。 从下拉列表中，通过从页面右上角的下拉列表选择 **LTI 密钥** 来创建开发人员密钥。

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="显示左侧导航栏（选择&quot;开发工具&quot;，并且从页面右侧下拉列表选择 LTI 键条目）的屏幕截图。":::

6. On the Configure page， in the **Method** dropdown， select **Paste JSON** as the method and paste the JSON text you copied in Step 5 in the text field that appears.
7. 保存密钥，它以 Off 状态在 Canvas **中** 可用。 打开该 **键** 并复制"详细信息"列中给定的键，以用于下一步。

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="键设置为关闭状态中的&quot;画布&quot;页。需要将其打开，并且需要从此页面的详细信息列中复制密钥。":::

8. 返回到"Microsoft OneDrive LTI 注册门户"，然后将密钥粘贴到 **"Canvas 客户端 ID"** 字段中。 准备就绪 **后** ，选择"下一步"。

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="LTI 租户注册页面，其中显示 JSON 文本和密钥应复制到的文本框。":::

9. 查看并保存更改。 成功注册时将显示一条消息。
10. 还可通过选择主页上的"查看 **LTI** 租户"按钮来查看注册详细信息。

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>在画布Microsoft OneDrive启用 LTI

Canvas 管理员可以针对所有课程Microsoft OneDrive LTI。 如果Microsoft OneDrive特定课程需要 LTI (而不是所有课程) ，则课程教师需要按照课程设置中的相同步骤操作。

1. 以管理员角色登录并转到 **设置部分。**
2. 转到"应用 **"部分** 并选择" **查看应用配置"** 按钮。
3. 选择" **添加应用"** 按钮。
4. 在" **配置类型"** 下拉列表中，选择" **按客户端 ID"** 选项。
5. 粘贴之前在"客户端 **ID"** 字段中生成的开发人员密钥的值，然后选择"提交 **"** 按钮。

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="&quot;添加应用&quot;页，显示&quot;配置类型&quot;下拉菜单下的&quot;按客户端 ID&quot;选项。":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>Canvas 课程设置 LTI Microsoft OneDrive协作工具

> [!NOTE]
> 为了使协作适用于教师和学生，不应启用协作设置。 若要确保未启用该设置，请按照以下步骤操作。

1. 以管理员角色登录并转到 **设置部分。**
1. 转到 **"功能选项** "部分，然后转到"课程 **"** 部分。
1. 将 **"外部协作工具** "功能设置为未启用。

> [!NOTE]
> 可以将协作分配给单个学生和学生组。 默认情况下，向单个学生分配工作。 若要能够将协作分配给学生组，请按照以下步骤操作：

1. 以管理员角色登录并转到 **"开发人员密钥"** 部分。
1. 查找值为 170000000000710的键，并设置为 **On。**
