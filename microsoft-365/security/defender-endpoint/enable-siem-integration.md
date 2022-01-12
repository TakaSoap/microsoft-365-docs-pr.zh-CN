---
title: 在 Microsoft Defender for Endpoint 中启用 SIEM 集成
description: 启用 SIEM 集成以在 SIEM 解决方案的安全信息和事件 (接收) 检测。
keywords: 启用 siem 连接器， siem， 连接器， 安全信息和事件
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
ms.technology: mde
ms.openlocfilehash: 3faecae3965cfc51104a707eaa82f375ba169f84
ms.sourcegitcommit: c6a97f2a5b7a41b74ec84f2f62fabfd65d8fd92a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/12/2022
ms.locfileid: "61935629"
---
# <a name="enable-siem-integration-in-microsoft-defender-for-endpoint"></a>在 Microsoft Defender for Endpoint 中启用 SIEM 集成

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft Defender for Endpoint 计划 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint 计划 2](https://go.microsoft.com/fwlink/?linkid=2154037)

> 希望体验 Microsoft Defender for Endpoint？ [注册免费试用版](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-enablesiem-abovefoldlink)。

> [!IMPORTANT]
> Microsoft Defender for Endpoint SIEM REST API 将于 2022 年 3 月 1 日停用，作为 Microsoft Defender for Endpoint Alert API 和 Microsoft 365 Defender 事件 API，替换它可提供更丰富的元数据，包括警报最新状态、与警报相关的证据实体、分析员输入的评论，以及支持更新状态 assignedTo、 以编程方式分类和确定字段。 **立即生效，将不支持新客户载入 SIEM REST API。**

在 SIEM (启用安全信息和事件) ，以便你可以从 SIEM 中拉取Microsoft 365 Defender。 使用 SIEM 解决方案或直接连接到检测 REST API 拉取检测。

> [!NOTE]
>
> - [Microsoft Defender 终结点警报](alerts.md) 由一个或多个检测组成。
> - [Microsoft Defender for Endpoint Detection](api-portal-mapping.md) 由设备上发生的可疑事件及其相关的警报详细信息组成。
> - Microsoft Defender for Endpoint 警报 API 是警报使用的最新 API，包含每个警报的相关证据的详细列表。 有关详细信息，请参阅[警报方法和属性和](alerts.md)[列表警报](get-alerts.md)。

## <a name="prerequisites"></a>先决条件

- 激活该设置的用户必须有权在 Azure Active Directory (AAD) 。 这是具有以下角色的人：

  - 安全管理员和全局管理员之一
  - 云 应用程序管理员
  -  应用程序管理员
  - 服务主体的所有者

- 在初始激活期间，将显示一个弹出屏幕以输入凭据。 请确保允许此网站的弹出窗口。

## <a name="enabling-siem-integration"></a>启用 SIEM 集成

1. 在导航窗格中，选择 **"设置** \>  \> **终结点 API** \> **SIEM"。**

   :::image type="content" source="../../media/enable-siemnew.png" lightbox="../../media/enable-siemnew.png" alt-text="来自菜单 1 的 SIEM 设置图像。":::

   > [!TIP]
   > 如果在尝试启用 SIEM 连接器应用程序时遇到错误，请检查浏览器的弹出窗口阻止程序设置。 启用该功能时，它可能会阻止打开的新窗口。

2. 选择 **启用 SIEM 集成**。 这会使用预填充的值激活 **SIEM** 连接器访问详细信息部分，并且应用程序在租户租户Azure Active Directory (Azure AD) 创建。

    > [!WARNING]
    > 客户端密码只显示一次。 请确保将其副本放在安全的位置。

    :::image type="content" alt-text="来自菜单 2 的 SIEM 设置图像。" source="images/siem_details.png" lightbox="images/siem_details.png":::

3. 选择你在组织使用的 SIEM 类型。

   > [!NOTE]
   > 如果选择 HP ArcSight，将需要保存以下两个配置文件：
   >
   > - WDATP-connector.jsonparser.properties
   > - WDATP-connector.properties

   如果你想要通过编程访问直接连接到检测 REST API，请选择通用 **API**。

4. 复制各个值或选择 **"将详细信息保存到文件** "以下载包含所有值的文件。

5. 选择 **"生成令牌** "，获取访问令牌和刷新令牌。

   > [!NOTE]
   > 你将需要每 90 天生成一个新的刷新令牌。

6. 按照为 Microsoft Defender for [Endpoint Azure AD](/microsoft-365/security/defender-endpoint/exposed-apis-create-app-webapp)应用注册的说明操作，并为其分配正确的权限以读取警报。

你现在可以继续配置 SIEM 解决方案，或者通过编程访问连接到检测 REST API。 配置 SIEM 解决方案时，你需要使用令牌，以允许它接收来自Microsoft 365 Defender。

## <a name="integrate-microsoft-defender-for-endpoint-with-ibm-qradar"></a>将 Microsoft Defender for Endpoint 与 IBM QRadar 集成

你可以将 IBM QRadar 配置为从 Microsoft Defender for Endpoint 收集检测。 有关详细信息，请参阅 [IBM 知识库](https://www.ibm.com/docs/en/qsip/7.3.2?topic=quick-start-guide)。

## <a name="see-also"></a>另请参阅

- [配置 HP ArcSight 以拉取 Microsoft Defender 进行终结点检测](configure-arcsight.md)
- [适用于终结点检测字段的 Microsoft Defender](api-portal-mapping.md)
- [使用 REST API 拉取 Microsoft Defender 的终结点检测](pull-alerts-using-rest-api.md)
- [SIEM 工具集成问题疑难解答](troubleshoot-siem.md)
