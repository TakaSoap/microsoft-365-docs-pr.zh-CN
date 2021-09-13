---
title: Upload应用程序二进制文件
description: 如何开始使用 M365 测试基础
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: how-to
ms.date: 07/06/2021
ms.service: virtual-desktop
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 38c21f69680d6e9d6a3231c8bf2dc44f15e057f6
ms.sourcegitcommit: d08fe0282be75483608e96df4e6986d346e97180
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 09/12/2021
ms.locfileid: "59200874"
---
# <a name="step-3-upload-your-binaries-dependencies-and-scripts"></a>步骤 3：Upload二进制文件、依赖项和脚本

在此选项卡上，将上载单个 zip 包，其中包含用于运行测试套件的二进制文件、依赖项和脚本。

## <a name="upload-package-zip-file"></a>Upload包 zip 文件

![Upload二进制文件。](Media/AddBinaries.png)

  - 上载的依赖项可以包括测试框架、脚本引擎或将访问以运行应用程序或测试用例的数据。 例如，你可以上载 Selenium 和 Webdriver 安装程序来帮助运行基于浏览器的测试。
  - 最佳做法是确保脚本活动保持模块化，即 
    - 脚本 ```Install``` 仅执行安装操作。
    - 脚本 ```Launch``` 仅启动应用程序。
    - ```Close```脚本仅关闭应用程序。
    - 可选 ```Uninstall``` 脚本仅卸载应用程序。

**目前，该门户仅支持 PowerShell 脚本。**


## <a name="next-steps"></a>后续步骤 

前进到下一篇文章，转到步骤 4： **设置测试任务**。
> [!div class="nextstepaction"]
> [回去](uploadApplication.md)
> [!div class="nextstepaction"]
> [后续步骤](testtask.md)

