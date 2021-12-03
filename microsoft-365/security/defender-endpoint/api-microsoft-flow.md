---
title: Microsoft Defender for Endpoint Flow连接器
ms.reviewer: ''
description: 使用 Microsoft Defender for Endpoint Flow 连接器自动实现安全性，并创建在租户上出现新警报时触发的流。
keywords: 流， 受支持的 api， api， Microsoft 流， 查询， 自动化
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
MS.technology: mde
ms.custom: api
ms.openlocfilehash: 8c3ed9023df1cb7256265a116303fd6988677de4
ms.sourcegitcommit: 348f3998a029a876a9dcc031f808e9e350804f22
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 12/03/2021
ms.locfileid: "61300474"
---
# <a name="microsoft-power-automate-formerly-microsoft-flow-and-azure-functions"></a>Microsoft Power Automate (以前Microsoft Flow) 和 Azure Functions

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)。

自动执行安全过程是每个新式安全操作中心的标准要求。 缺少专业网络防御者会强制 SOC 以最有效的方式工作，自动化是一项必须完成的工作。 Microsoft Power Automate支持专为这一点构建的不同连接器。 您可以几分钟内生成端到端过程自动化。

Microsoft Defender API 具有官方 Power Automate 连接器，具有许多功能。

:::image type="content" alt-text="编辑凭据的图像1。" source="images/api-flow-0.png":::

> [!NOTE]
> 有关高级连接器许可先决条件的更多详细信息，请参阅 Premium [Connectors 的许可](/power-automate/triggers-introduction#licensing-for-premium-connectors)。


## <a name="usage-example"></a>用法示例

以下示例演示如何创建一个Flow在租户上出现新警报时触发的警报。

1. 登录到[Microsoft Power Automate。](https://flow.microsoft.com)

2. Go to **My flows** \> **New** \> **Automated-from blank**.

    :::image type="content" alt-text="编辑凭据 2 的图像。" source="images/api-flow-1.png":::

3. 为用户选择名称Flow搜索"Microsoft Defender ATP 触发器"作为触发器，然后选择新的警报触发器。

    :::image type="content" alt-text="编辑凭据的图像3。" source="images/api-flow-2.png":::

现在，你Flow发生新警报时触发的警报。

:::image type="content" alt-text="编辑凭据的图像4。" source="images/api-flow-3.png":::

现在只需选择下一步。
例如，如果警报的严重性为"高"，你可以隔离设备，并发送关于该设备的电子邮件。
警报触发器仅提供警报 ID 和计算机 ID。 可以使用连接器展开这些实体。

### <a name="get-the-alert-entity-using-the-connector"></a>使用连接器获取 Alert 实体

1. 选择 **"Microsoft Defender ATP"** 作为新步骤。

2. 选择 **警报 - 获取单个警报 API。**

3. 将上 **一步** 中的警报 ID 设置为 **Input**。

    :::image type="content" alt-text="编辑凭据的图像5。" source="images/api-flow-4.png" lightbox="images/api-flow-4.png":::

### <a name="isolate-the-device-if-the-alerts-severity-is-high"></a>如果警报严重性为高，则隔离设备

1. 将 **Condition** 添加为新步骤。

2. 检查警报严重性 **是否等于"高** "。

   如果是，请添加 **Microsoft Defender ATP - 使用** 计算机 ID 和注释隔离计算机操作。

    :::image type="content" alt-text="编辑凭据的图像6。" source="images/api-flow-5.png" lightbox="images/api-flow-5.png":::

3. 添加有关警报和隔离的电子邮件的新步骤。 有多个电子邮件连接器非常易于使用，例如Outlook Gmail。

4. 保存流。

还可以创建运行 **高级** 搜寻查询等的计划流！

## <a name="related-topic"></a>相关主题
- [适用于终结点的 Microsoft Defender API](apis-intro.md)
