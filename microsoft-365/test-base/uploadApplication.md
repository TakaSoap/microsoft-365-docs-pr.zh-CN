---
title: 上载包
description: 如何将应用程序、二进制文件和依赖项上传到测试库
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: troubleshooting
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 2bda97c9168f7d3162c07ece4629dad795645638
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60154130"
---
# <a name="step-2-uploading-a-package"></a>步骤 2：上载程序包

在"测试基础门户"页上，Upload左侧导航栏上的"新建程序包"选项，如下所示：

:::image type="content" alt-text="Upload一个新程序包。" source="Media/Upload-New-Package.png" lightbox="Media/Upload-New-Package.png":::

完成后，请按照以下步骤上载新程序包。

## <a name="enter-details-for-your-package"></a>输入程序包的详细信息

在"测试详细信息"选项卡上，键入程序包的名称、版本和其他请求的详细信息。

**可通过此仪表板** 完成开箱即用和功能测试。

以下步骤提供了如何填写程序包详细信息的指南：

1. 在 字段中输入要给定程序包 `Package name` 的名称。

    > [!NOTE]
    > 输入的程序包名称和版本组合在组织中必须是唯一的。 检查标记对此进行验证，如下所示。

    - 如果选择重复使用程序包的名称，版本号必须是唯一的 (也就是说，从不用于包含该特定名称的程序包) 。

    - 如果程序包名称 + 版本的组合未通过唯一性检查，你将看到一条错误消息，显示"程序包包含此程序包版本 *已存在"。*

    :::image type="content" alt-text="用于上传程序包说明的图像。" source="Media/Instructions.png":::

2. 在"程序包版本"字段中输入版本。

    :::image type="content" alt-text="程序包版本。" source="Media/ApplicationVersion.png":::

3. 选择要在此程序包上运行的测试类型。

      **Out-of-box (OOB)***测试执行程序包* 的安装、启动、*关闭* 和卸载。 安装后，在运行单个卸载之前，launch-close 例程将重复 30 次。

    此 OOB 测试提供了程序包上的标准化遥测，可跨内部版本Windows比较。

    功能 **测试** 将在程序包上执行 () 脚本。 脚本按上载顺序运行，特定脚本中的失败将停止后续脚本的执行。

    > [!NOTE]
    > **所有** 脚本最多运行 80 分钟。

4. 选择操作系统更新类型。

    - 通过"安全更新"，可以针对预发布每月安全更新中Windows增量改动测试程序包。
    - 利用"功能更新"，可以针对预览体验计划Windows预发布每两年功能更新版本测试Windows程序包。
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="操作系统更新类型。" source="Media/OSUpdateType.png":::

5. 选择操作系统版本 () 安全更新测试。

    在多选下拉列表中，选择操作系统版本 () Windows程序包的程序包。

    - 若要仅针对客户端Windows测试程序包，请从菜单Windows 11 操作系统版本。
    - 若要仅针对 Windows Server 操作系统测试程序包，请从Windows选择适用的服务器操作系统版本。
    - 若要仅针对 Windows 和 Windows Server 操作系统测试程序包，请从菜单列表中选择所有适用的操作系统。

    > [!NOTE]
    > 如果选择针对服务器和客户端 OSes 测试程序包，请确保程序包兼容，并且可在两个 OSes 上运行

    :::image type="content" alt-text="选择操作系统版本。" source="Media/OSVersion.png":::
    <!---
    Change to the correct picture
    -->

6. 选择功能更新测试的选项：

    - 在"选择预览体验成员频道"选项上，选择 作为应针对其测试 `Windows Insider Program Channel` 程序包的内部版本。

      我们目前使用预览体验成员 Beta 渠道中测试的内部版本。

    - 在"为 Insight 选择操作系统基线"选项上，Windows要用作比较测试结果基线的 OS 版本。

    > [!NOTE]
    > 目前我们不支持服务器 OSes 的功能更新测试
    <!---
    Note to actual note format for markdown
    -->
    <!---
    Change to the correct picture
    -->
    :::image type="content" alt-text="功能更新测试。" source="Media/FeatureUpdate.png":::

7. 完成的"测试详细信息"页应如下所示：

    :::image type="content" alt-text="查看测试详细信息。" source="Media/TestDetails.png":::

## <a name="next-steps"></a>后续步骤

我们的下一篇文章介绍了将二进制文件上传到服务。

> [!div class="nextstepaction"]
> [下一步](binaries.md)

<!---
Add button for next page
-->
