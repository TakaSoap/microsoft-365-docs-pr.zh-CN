---
title: 测试基上的功能测试
description: 有关如何使用现有自动化功能测试测试应用程序的详细信息
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: f64480d66cd91dc4b08f9694331cfe0d9c130ee4
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60191261"
---
# <a name="functional-testing"></a>功能测试

作为软件供应商，你现在可以使用你选择的测试框架（通过 M365 自助测试库门户）执行自定义功能测试。 

当我们最初启动该服务时，我们提供了开箱即用测试，这是一组通过标准化脚本驱动的预定义测试。 但是，这无法为许多独立软件供应商和 ISV (完全) 。 

因此，为了响应您的反馈，我们将为 ISV 提供上载自动功能测试的功能。

若要使用此功能，请按照以下步骤操作：

1. Upload文件 (一个包) 二进制文件、依赖项和.zip脚本。
2. 选择是否要在各种执行点 (虚拟机) 虚拟机。
3. 管理脚本的可用选项。
4. 选择何时在Windows虚拟机上应用更新。

下面重点介绍了上述步骤的详细说明：

**Upload功能测试包**

To get started， navigate to the Upload page， select Upload new application under Application catalog on the left-side navigation menu of the Test Base for M365 portal in Azure. 从该时间开始：

选项卡 1 - 输入基本信息。 提供应用程序的名称和版本。 在"测试类型"选项中，选择 ```Functional tests``` 。 

*请注意，默认情况下，"开箱即 (OOB) 选项是必需的。*


![选择功能测试选项卡。](Media/functional_testing_tab1.png)

选项卡 2 - Upload通过上传包含整个测试文件、二进制文件、依赖项、脚本等的 zip 文件来 (包) 。 

有关详细信息 aka.ms/usl-package-outline 请参阅 aka.ms/usl-package-outline。  (注意：开箱即用测试脚本和功能测试内容应放在相同的 zip 文件中) 。 目前，文件大小限制为 2GB。

选项卡 3 - 配置开箱即用和功能测试任务。 在此处，选择将安装、启动、关闭和卸载应用程序 (for Out-of-Box) 的 PowerShell 脚本的 () 路径，以及所有自定义脚本的 () 路径，以执行功能测试。 **(注意：用于卸载应用程序的脚本是可选的) 。**

目前，您可以上载 1 到 8 个脚本，用于功能测试。  (脚本，请对此文章添加好评论！) 

![Upload 8 个脚本的功能测试。](Media/functional_testing_tab3.png)

 (可选) 安装后配置重启。 某些应用程序需要在安装后重新启动。 

如果希望在执行该脚本后重新启动，请在"任务"选项卡中选择特定 ```Reboot After Execution``` 脚本。

选项卡 4 - 选择Windows更新时间：在选择任何脚本之前，Windows更新修补程序的应用完成。 建议您在应用程序安装Windows安装更新，以密切模仿实际的应用程序使用方案。

![可以在Windows脚本后安装该更新。](Media/functional_testing_tab4.png)

选项卡 5 - 查看并创建程序包。 完成上面列出的步骤后，选择 ```Create``` 以完成上传过程。

创建程序包后，你可以检查程序包的验证状态。

我们运行初始测试来安装、启动、关闭和卸载应用程序。 这使我们可以验证你的程序包能否安装在我们的服务上，并且没有错误。

验证过程最多可能需要 24 小时。 验证完成后，您可以在菜单中看到状态 ```Manage packages``` ，该状态可以是两个条目之一：

1. 验证成功：将针对所选操作系统内部版本Windows预发行版更新自动测试程序包。
或者
2. 验证失败：你将需要调查失败的原因、修复问题，然后重新上传你的程序包。

你还将通过 Azure 门户中的通知图标收到任一结果的通知。
