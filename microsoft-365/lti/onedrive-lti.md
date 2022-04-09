---
title: 将 Microsoft OneDrive LTI 与 Canvas 集成
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
description: 使用新的 Microsoft OneDrive Learning Tools Interoperability App for Canvas 创建和评分分配、生成和策划课程内容，以及实时协作处理文件。
ms.openlocfilehash: ce02be23d98d1dc54ae02a21f9bf1678d06c3d8f
ms.sourcegitcommit: dd5fc139affb4cba4089cbdb2c478968b680699a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 04/09/2022
ms.locfileid: "64747217"
---
# <a name="integrate-microsoft-onedrive-lti-with-canvas"></a>将 Microsoft OneDrive LTI 与 Canvas 集成

将 Microsoft OneDrive LTI 与 Canvas 集成是一个两步过程。 第一步在 Canvas 中启用Microsoft OneDrive，第二步使Microsoft OneDrive LTI 在 Canvas 课程中可用。

## <a name="recommended-browser-settings"></a>建议的浏览器设置

- 应为Microsoft OneDrive启用 Cookie。
- 不应为Microsoft OneDrive阻止弹出窗口。

> [!NOTE]
> - 默认情况下，Chrome 浏览器隐身模式下未启用 Cookie，需要启用。
> - Microsoft OneDrive LTI 在Microsoft Edge浏览器的专用模式下工作。 确保未阻止默认启用的 cookie () 。

## <a name="enable-microsoft-onedrive-lti-in-canvas"></a>在画布中启用Microsoft OneDrive LTI

> [!IMPORTANT]
> 执行此集成的人员应是 Canvas 管理员和Microsoft 365租户的管理员。

1. 登录<a href="https://onedrivelti.microsoft.com/admin" target="_blank">到 Microsoft OneDrive LTI 注册门户</a>
1. 选择 **“管理员同意** ”按钮并接受权限。

> [!CAUTION]
> 如果未执行此步骤，以下步骤将给你一个错误，并且一旦收到错误，你将无法执行此步骤一小时。

3. 选择 **“新建 LTI 租户** ”按钮。 在“LTI 注册”页上，在下拉列表中选择 **“画布** ”，然后输入画布实例的基 URL。

> [!NOTE]
> 例如 https://contoso.test.instructure.com，如果画布实例为 ] (https://contoso.test.instructure.com)，则应输入完整的 URL。

:::image type="content" source="media/OneDrive-LTI-07.png" alt-text="LTI 租户管理页，其中包含用于选择 LTI 使用者平台的下拉字段和 URL 文本字段。":::

4. 通过选择右侧的图标 (“ **复制** ”按钮来复制 JSON，该图标显示两个页面彼此) 。 这将用于在 Canvas 中生成密钥。

:::image type="content" source="media/OneDrive-LTI-08.png" alt-text="显示复制按钮的图像，该按钮将复制显示的 JSON 文本，并使其可用于画布中的密钥生成。":::

5. 以管理员身份登录画布实例，并从页面左侧的菜单中选择 **开发人员密钥** 。 从下拉列表中，通过从页面右上角的下拉列表中选择 **LTI 密钥** 来创建开发人员密钥。

:::image type="content" source="media/OneDrive-LTI-14.png" alt-text="显示左侧导航栏的屏幕截图，其中选择了开发人员密钥，并从页面右侧的下拉列表中选择了 LTI 键条目。":::

6. 在“配置”页上的 **“方法** ”下拉列表中，选择 **“粘贴 JSON** ”作为方法，并将在步骤 4 中复制的 JSON 文本粘贴到显示的文本字段中。

    > [!TIP]
    > **可选步骤：** 如果你学校的教育工作者希望自己控制哪些链接出现在他们课程的导航中，你可以修改 ``default`` 复制的 JSON 中的参数。 参数 ``default`` 将自动设置为 ``enabled`` ;但是，更改 ``default`` 参数以 ``disabled`` 允许教师选择自己的课程导航。
    >
    > 有关教师如何修改其课程导航链接的详细信息，请[参阅如何实现管理课程导航链接？](https://community.canvaslms.com/t5/Instructor-Guide/How-do-I-manage-Course-Navigation-links/ta-p/1020)

7. 保存密钥，并在画布中处于 **关闭** 状态。 **打开** 密钥并复制在 **“详细信息**”列中提供的密钥，以便在下一步中使用。

:::image type="content" source="media/OneDrive-LTI-19.png" alt-text="具有处于关闭状态的键集的画布页。需要打开该密钥，并且需要从此页上的详细信息列复制密钥。":::

8. 返回到Microsoft OneDrive LTI 注册门户，并将密钥粘贴到 **Canvas 客户端 ID** 字段中。 准备好后选择 **“下一步** ”。

:::image type="content" source="media/OneDrive-LTI-20.png" alt-text="LTI 租户注册页，其中显示了应将密钥复制到的 JSON 文本和文本框。":::

9. 查看并保存所做的更改。 成功注册时将显示一条消息。
10. 也可以通过在主页上选择 **“查看 LTI 租户** ”按钮来查看注册详细信息。

## <a name="enable-microsoft-onedrive-lti-in-canvas-courses"></a>在画布课程中启用Microsoft OneDrive LTI

画布管理员可以为所有课程启用Microsoft OneDrive LTI。 如果特定课程 (中需要Microsoft OneDrive LTI，而并非所有课程) ，则课程教师需要在课程设置中执行相同的步骤。

1. 以管理员身份登录并转到 **设置** 部分。
2. 转到 **“应用** ”部分，然后选择“ **查看应用配置** ”按钮。
3. 选择 **“添加应用** ”按钮。
4. 在 **“配置类型** ”下拉列表中，选择 **“按客户端 ID** ”选项。
5. 粘贴之前在 **客户端 ID** 字段中生成的开发人员密钥的值，然后选择“ **提交** ”按钮。

:::image type="content" source="media/OneDrive-LTI-31.png" alt-text="“添加应用”页，显示“配置类型”下拉菜单下的“按客户端 ID”选项。":::

## <a name="collaboration-settings-for-microsoft-onedrive-lti-in-canvas-courses"></a>画布课程中Microsoft OneDrive LTI 的协作设置

> [!NOTE]
> 要使协作适用于教师和学生，不应启用协作设置。 若要确保未启用设置，请执行以下步骤。

1. 以管理员身份登录并转到 **设置** 部分。
1. 转到 **“功能选项”** 部分，然后转到“ **课程** ”部分。
1. 将 **外部协作工具** 功能设置为未启用。

> [!NOTE]
> 可将协作分配给各个学生和学生组。 默认情况下，分配给单个学生的工作原理。 若要能够将协作分配给学生组，请执行以下步骤：

1. 以管理员身份登录并转到“ **开发人员密钥”** 部分。
1. 找到170000000000710值的键并将其设置为 **“打开**”。
