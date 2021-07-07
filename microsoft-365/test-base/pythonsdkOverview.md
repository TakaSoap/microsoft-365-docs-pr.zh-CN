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
ms.openlocfilehash: c7f2d4b7b600e84b2ed35cce320dcb7d7191ecfc
ms.sourcegitcommit: b0f464b6300e2977ed51395473a6b2e02b18fc9e
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 07/07/2021
ms.locfileid: "53322527"
---
# <a name="test-base-sdk-for-python"></a><span data-ttu-id="cf793-103">适用于 Python 的测试基础 SDK</span><span class="sxs-lookup"><span data-stu-id="cf793-103">Test Base SDK for Python</span></span>

## <a name="overview"></a><span data-ttu-id="cf793-104">概述</span><span class="sxs-lookup"><span data-stu-id="cf793-104">Overview</span></span>
<span data-ttu-id="cf793-105">测试基础 SDK 可用于与 Azure 测试基础资源交互。</span><span class="sxs-lookup"><span data-stu-id="cf793-105">The Test Base SDK can be used to interact with the Azure test base resource.</span></span> <span data-ttu-id="cf793-106"> (即管理应用程序包，包括创建包、编辑包和删除) </span><span class="sxs-lookup"><span data-stu-id="cf793-106">(i.e. manage your application package, include create package, edit package and delete package)</span></span>

<span data-ttu-id="cf793-107">借助 SDK，可以获得的测试摘要和分析结果包括：scriptExecution、reliability、memoryUtilization、cpuUtilization、memoryRegression、cpuRegression。</span><span class="sxs-lookup"><span data-stu-id="cf793-107">With the SDK, the test summary and Analysis Result which can be gotten include : scriptExecution, reliability, memoryUtilization, cpuUtilization, memoryRegression, cpuRegression.</span></span>

<span data-ttu-id="cf793-108">使用测试基础 SDK，可以在 CI/CD 管道中集成测试基础。</span><span class="sxs-lookup"><span data-stu-id="cf793-108">With the Test Base SDK, you can integrate test base in your CI/CD pipeline.</span></span>

## <a name="client-library"></a><span data-ttu-id="cf793-109">客户端库</span><span class="sxs-lookup"><span data-stu-id="cf793-109">Client Library</span></span>

<span data-ttu-id="cf793-110">使用管道安装测试基包。</span><span class="sxs-lookup"><span data-stu-id="cf793-110">Install the test base package with pip.</span></span>

~~~
pip install  Microsoft.Testbase
~~~
 
## <a name="example"></a><span data-ttu-id="cf793-111">示例</span><span class="sxs-lookup"><span data-stu-id="cf793-111">Example</span></span>
