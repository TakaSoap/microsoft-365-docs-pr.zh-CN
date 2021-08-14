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
localization_priority: Normal
ms.collection: TestBase-M365
ms.custom: ''
ms.reviewer: mapatel
f1.keywords: NOCSH
ms.openlocfilehash: 64c47566959cbe83088ac7855f8f3cd6a8473d2ad86d5ab2957fbbdf41d10bf7
ms.sourcegitcommit: a1b66e1e80c25d14d67a9b46c79ec7245d88e045
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 08/05/2021
ms.locfileid: "53852955"
---
# <a name="test-base-sdk-for-python"></a>适用于 Python 的测试基础 SDK

## <a name="overview"></a>概述
测试基础 SDK 可用于与 Azure 测试基础资源交互。  (即管理应用程序包，包括创建包、编辑包和删除) 

借助 SDK，可以获得的测试摘要和分析结果包括：scriptExecution、reliability、memoryUtilization、cpuUtilization、memoryRegression、cpuRegression。

使用测试基础 SDK，可以在 CI/CD 管道中集成测试基础。

## <a name="client-library"></a>客户端库

使用管道安装测试基包。

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a>示例
