---
title: 适用于 Python 的测试基础 SDK
description: 有关了解 Test Base 的适用于 Python 的 SDK 的详细信息
search.appverid: MET150
author: mansipatel-usl
ms.author: mapatel
manager: rshastri
audience: Software-Vendor
ms.topic: article
ms.date: 07/06/2021
ms.service: virtual-desktop
ms.localizationpriority: medium
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 9a4f64afbf02853ccb68098995c0f05baf2c9b01
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60211761"
---
# <a name="test-base-sdk-for-python"></a>适用于 Python 的测试基础 SDK

## <a name="overview"></a>概述
测试基础 SDK 可用于与 Azure 测试基础资源交互。  (即管理应用程序包，包括创建包、编辑包和删除) 

借助 SDK，可以获得的测试摘要和分析结果包括：scriptExecution、可靠性、memoryUtilization、cpuUtilization、memoryRegression、cpuRegression。

使用测试基础 SDK，可以在 CI/CD 管道中集成测试基础。

## <a name="client-library"></a>客户端库

使用管道安装测试基包。

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>示例
