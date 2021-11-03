---
title: 测试基本 API & SDK
description: 测试基本 API & SDK
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
ms.openlocfilehash: 9e2c52d23c0e0c949059dc37eee4c1a59b35964e
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/03/2021
ms.locfileid: "60704939"
---
# <a name="manage-your-resource-with-sdk--apis"></a>使用 SDK & API 管理资源
自动化是自动化和敏捷DevOps的一个关键方面。 您是否希望管理测试基础Microsoft 365资源、以编程方式获取测试结果并将其与 CI 工具集成？ 测试基本 API/SDK 可以帮助你实现所有这些目标以及更多目标！ 

通过这些 API/SDK，IT 专业人员和应用开发人员可以： 
- 管理测试基本帐户，包括创建、更新和载出。 
- 管理应用程序包，包括创建、更新、删除和下载程序包。 
- 获取测试摘要、详细的测试结果和分析结果。 分析结果包括 CPU 回归分析、CPU 使用率分析、内存回归分析和内存使用率分析。 
- 下载测试结果和测试执行视频录制。  

请查看下面的分步大纲，了解如何在 Test Base for Microsoft 365 service 中访问此新功能。

## <a name="a-step-by-step-example-of-test-base-account-creation-by-using-python-sdk"></a>使用 Python SDK 创建测试基础帐户的分步示例

1. 先决条件： 

- 安装以下所需组件： 

    [具有活动订阅的 Azure](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup) 帐户（如果你没有订阅）<br>
    [Python 2.7+ 或 3.6+](https://www.python.org/downloads)<br>
    [Azure Command-Line Interface (CLI) ](/cli/azure/install-azure-cli) <br>

- 使用控制台中的管道安装安装库包 

```
pip install azure-identity 
pip install azure-mgmt-testbase  
```

- 在开发环境中进行身份验证 

在本地调试和执行代码时，开发者通常使用自己的帐户对 Azure 服务的调用进行身份验证。 azure-identity 包支持通过 Azure CLI 进行身份验证以简化本地开发。 若要登录到 Azure CLI，请运行 ```az login ``` 。 在具有默认 Web 浏览器的系统中，Azure CLI 将启动浏览器以对用户进行身份验证。 

检查 [如何使用 Azure 服务对 Python 应用程序进行身份验证|Microsoft Docs](/azure/developer/python/azure-sdk-authenticate) [https://pypi.org/project/azure-identity/](https://pypi.org/project/azure-identity/) 和其他支持的身份验证方法。 

 - 使用所需的名称创建将在以下步骤中使用的资源组。 

2. 下面的代码段介绍了创建测试基础帐户（包括 

- 通过 Azure CLI 请求凭据以与 Azure 交互 
- 使用凭据和订阅 ID 初始化测试基础 SDK 客户端，以用于以后的操作 
- 从begin_create调用test_base_accounts帐户以创建测试基本帐户 

将代码复制到 Python 开发环境，将"subscription-id"替换为 Azure 订阅 ID，将"resource-group-name"替换为上面创建的资源组。 

 
```python

from azure.identity import AzureCliCredential
from azure.mgmt.testbase import TestBase
from azure.mgmt.testbase.models import TestBaseAccountResource
from azure.mgmt.testbase.models import TestBaseAccountSKU

# requesting token from Azure CLI for request
# For other authentication approaches, please see: https://pypi.org/project/azure-identity/
credential = AzureCliCredential()
subscription_id = "<subscription-id>"
resource_group = "<resource-group-name>"
testBaseAccount_name = "contoso-testbaseAccount"
testBaseAccount_location = "global"
sku_name = "S0"
sku_tier = "Standard"
sku_locations = {"global"}

# Create client
testBase_client = TestBase(credential, subscription_id)

# Create sku for test base account
sku = TestBaseAccountSKU(name=sku_name, tier=sku_tier, locations=sku_locations)

# Create test base account
parameters = TestBaseAccountResource(location=testBaseAccount_location, sku=sku)
testBaseAccount = testBase_client.test_base_accounts.begin_create(resource_group, testBaseAccount_name, parameters).result()
print("Create test base account:\n{}".format(testBaseAccount))

```


## <a name="learn-more"></a>了解详细信息 

请查看以下链接，了解有关 SDK & API 的更多详细信息。 

**Azure 订阅** 

- [具有活动订阅的 Azure 帐户](https://azure.microsoft.com/free/?utm_source=campaign&utm_campaign=python-dev-center&mktingSource=environment-setup) 

**Python SDK** 

- [测试基本 Python SDK 文档](/python/api/overview/azure/mgmt-testbase-readme?view=azure-python-preview)
- [测试基本 Python SDK 示例](https://aka.ms/testbase-sample-py) 
- [Python SDK 的 Azure 常规使用模式](/azure/developer/python/azure-sdk-overview#provision-and-manage-azure-resources-with-management-libraries) 

**REST API**  

- [REST API 文档](https://aka.ms/testbase-api)  
