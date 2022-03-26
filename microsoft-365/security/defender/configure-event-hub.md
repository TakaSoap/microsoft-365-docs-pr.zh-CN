---
title: 配置事件中心
description: 了解如何配置事件中心
keywords: 事件中心， 配置， 见解
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: m365-security-compliance
ms.custom: admindeeplinkDEFENDER
ms.topic: article
MS.technology: mde
ms.openlocfilehash: a842f9161aa823203354917326653b583e5fddb9
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754286"
---
# <a name="configure-your-event-hub"></a>配置事件中心

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**适用于：**
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

了解如何配置事件中心，以便它可以从事件中心Microsoft 365 Defender。

## <a name="set-up-the-required-resource-provider-in-the-event-hub-subscription"></a>在事件中心订阅中设置必需的资源提供程序

1. 登录到 [Azure 门户](https://portal.azure.com)。
1. 选择 **订阅** > **{ 选择事件中心将部署到 }** > **资源提供程序的订阅**。
1. 验证 **Microsoft.Insights** 已注册提供程序。 否则，请注册它。

:::image type="content" source="../../media/f893db7a7b1f7aa520e8b9257cc72562.png" alt-text="服务提供程序门户中的服务提供程序Microsoft Azure页" lightbox="../../media/f893db7a7b1f7aa520e8b9257cc72562.png":::

## <a name="set-up-azure-active-directory-app-registration"></a>设置Azure Active Directory应用注册

> ![注意]你必须具有管理员角色Azure Active Directory (AAD) 必须设置为允许非管理员注册应用。 还必须具有所有者或用户访问管理员角色才能为服务主体分配角色。 有关详细信息，请参阅 Microsoft Docs Azure AD门户&[服务主体创建 \| Microsoft 标识平台应用](/azure/active-directory/develop/howto-create-service-principal-portal)。

1. 创建新的注册 ( \>在应用注册新注册) 服务Azure Active Directory **创建** \> **服务主体。**

1. 只需使用 Name (填写表单，无需重定向 URI) 。

    :::image type="content" source="../../media/336bc84e6be23900c43232b4ef0c253c.png" alt-text="应用程序门户中的应用程序名称Microsoft Azure部分" lightbox="../../media/336bc84e6be23900c43232b4ef0c253c.png":::


    :::image type="content" source="../../media/06ac04c4ff713c2065cec2ef2f99a294.png" alt-text="Microsoft Azure门户中的概述信息部分" lightbox="../../media/06ac04c4ff713c2065cec2ef2f99a294.png":::

1. 通过单击"证书""密码" **创建&密码 新建** \> **客户端密码**：

    :::image type="content" source="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png" alt-text="客户端门户中的&quot;客户端Microsoft Azure部分" lightbox="../../media/d2ef88d3d2310d2c60c294b569cdf02e.png":::
    

> [!WARNING]
> **你将无法再次访问客户端密码，因此请确保保存它**。

## <a name="set-up-event-hub-namespace"></a>设置事件中心命名空间

1. 创建事件中心命名空间：

    转到 **"事件\>** 中心""添加"，然后选择定价层、吞吐量单位和自动 (要求标准定价，且在) 负载所需的功能下。 有关详细信息，请参阅定价 [- 事件\|中心Microsoft Azure](https://azure.microsoft.com/pricing/details/event-hubs/)

    > [!NOTE]
    > 可以使用现有的事件中心，但吞吐量和缩放是在命名空间级别设置的，因此建议将事件中心放在其自己的命名空间中。

   :::image type="content" source="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png" alt-text="活动门户中的事件Microsoft Azure部分" lightbox="../../media/ebc4ca37c342ad1da75c4aee4018e51a.png":::

1. 你还需要此事件中心命名空间的资源 ID。 转到 Azure 事件中心命名空间页面"属性 \> "。 复制"资源 ID"下的文本，并记录该文本Microsoft 365配置部分使用。

    :::image type="content" source="../../media/759498162a4e93cbf17c4130d704d164.png" alt-text="事件门户中的事件中心Microsoft Azure部分" lightbox="../../media/759498162a4e93cbf17c4130d704d164.png":::


1. 创建事件中心命名空间后，你需要将应用注册服务主体添加为读者、Azure 事件中心数据接收器以及将登录到 Microsoft 365 Defender 的用户作为参与者 (还可以在资源组或订阅级别) 中这样做。

    您可以在 IAM 事件中心 **命名空间**\>访问控制 **(添加) 角色** \>分配下 **进行验证：**

    :::image type="content" source="../../media/9c9c29137b90d5858920202d87680d16.png" alt-text="应用程序注册门户中的应用程序注册Microsoft Azure部分" lightbox="../../media/9c9c29137b90d5858920202d87680d16.png":::

## <a name="set-up-event-hub"></a>设置事件中心

**选项 1：**

可以在命名空间内创建事件中心，选择要导出 (表) 事件类型将写入此 **事件** 中心。

**选项 2：**

你可以将每个表导出到事件中心内的不同事件中心，而不是将所有事件类型 () 表导出到一个事件中心中 (每个事件类型一个事件中心) 。

在此选项中，Microsoft 365 Defender将创建事件中心。

> [!NOTE]
> 如果使用的事件中心命名空间不是事件中心群集的一部分，则只能选择最多 10 个事件类型 (Tables) 以在定义的每个导出 设置 中导出，因为每个事件中心命名空间的 Azure 限制为 10 个事件中心。

例如：

:::image type="content" source="../../media/005c1f6c10c34420d387f594987f9ffe.png" alt-text="事件门户中的事件Microsoft Azure部分" lightbox="../../media/005c1f6c10c34420d387f594987f9ffe.png":::

如果选择此选项，可以跳到"配置Microsoft 365 Defender[发送电子邮件表"](#configure-microsoft-365-defender-to-send-email-tables)部分。

通过选择事件中心 + 事件 **中心在命名空间** \> **内创建事件中心**。

分区计数允许通过并行率增加吞吐量，因此建议根据你期望的负载增加此数字。 建议使用默认邮件保留值和捕获值 1 和 Off。

:::image type="content" source="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png" alt-text="活动门户中的事件中心Microsoft Azure部分" lightbox="../../media/1db04b8ec02a6298d7cc70419ac6e6a9.png":::
 

对于这些事件中心 (命名空间) 您需要使用发送、侦听声明配置共享访问策略。 单击事件 **中心** \> **共享访问策略** \> **+** 添加，然后为它指定策略名称 (其他位置) 并检查 **发送** 和 **侦听**。

:::image type="content" source="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png" alt-text="Microsoft Azure门户中的&quot;共享访问策略&quot;页" lightbox="../../media/1867d13f46dc6a0f4cdae6cf00df24db.png":::

## <a name="configure-microsoft-365-defender-to-send-email-tables"></a>配置Microsoft 365 Defender发送电子邮件表

### <a name="set-up-microsoft-365-defender-send-email-tables-to-splunk-via-event-hub"></a>设置Microsoft 365 Defender事件中心将电子邮件表发送到 Splunk

1. 登录以<a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender</a>满足以下所有角色要求的帐户登录：

    - 要导出到的事件中心的 Event Hub *命名空间* 资源级别或更高级别的参与者角色。 如果没有此权限，在尝试保存设置时将看到导出错误。

    - 绑定到 Azure 和 Azure 的租户上的全局管理员Microsoft 365 Defender管理员角色。

      :::image type="content" source="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png" alt-text="设置门户的Microsoft 365 Defender页" lightbox="../../media/55d5b1c21dd58692fb12a6c1c35bd4fa.png":::

1. 单击" **原始数据导出 + \> 添加"**。

    现在，你将使用上面记录的数据。

    **名称**：此值是本地值，并且应该是适合您的环境的任何值。

    **将事件转发到事件中心**：选中此复选框。

    **事件中心资源 ID**：此值是在设置事件中心时记录的事件中心命名空间资源 ID。

    **事件中心名称**：如果在事件中心命名空间内创建了事件中心，请粘贴上面记录的事件中心名称。

    如果您选择允许Microsoft 365 Defender创建每个事件类型的事件 (表) ，请保留此字段为空。

    **事件类型**：选择要转发到事件中心，然后转发到自定义应用的高级搜寻表。 警报表来自Microsoft 365 Defender，设备表来自 Microsoft Defender for Endpoint (EDR) ，电子邮件表来自 Microsoft Defender for Office 365。 电子邮件事件记录所有电子邮件事务。 URL (保险箱 Links) ， Attachment (保险箱 Attachments) ， and Post Delivery Events (ZAP) are also recorded and can be joined to the Email Events on the NetworkMessageId field.

    :::image type="content" source="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png" alt-text="Microsoft Azure门户中的&quot;流式 API 设置&quot;页" lightbox="../../media/3b2ad64b6ef0f88cf0175f8d57ef8b97.png":::

1. 确保单击"提交 **"**。

### <a name="verify-that-the-events-are-being-exported-to-the-event-hub"></a>验证事件是否导出到事件中心

可以通过运行基本高级搜寻查询来验证事件是否正在发送到事件中心。 选择 **搜寻** \> **高级搜寻** \> **查询** 并输入以下查询：

```console
EmailEvents
|joinkind=fullouterEmailAttachmentInfoonNetworkMessageId
|joinkind=fullouterEmailUrlInfoonNetworkMessageId
|joinkind=fullouterEmailPostDeliveryEventsonNetworkMessageId
|whereTimestamp\>ago(1h)
|count
```

这将显示在上一小时加入所有其他表时收到的电子邮件数。 它还会显示是否看到可以导出到事件中心的事件。 如果此计数显示 0，则你将看不到进入事件中心的任何数据。

:::image type="content" source="../../media/c305e57dc6f72fa9eb035943f244738e.png" alt-text="企业门户中的高级Microsoft Azure页面" lightbox="../../media/c305e57dc6f72fa9eb035943f244738e.png":::

验证有要导出的数据后，可以查看"事件中心"页来验证邮件是否传入。 这最多可能需要一个小时。

1. 在 Azure 中，转到事件 **中心** \> 单击命名空间 \> **事件**\>中心 单击事件 **中心**。
1. Under **Overview**， scroll down and in the Messages graph you should see Incoming Messages. 如果你未看到任何结果，则你的自定义应用将没有任何消息要接收。

:::image type="content" source="../../media/e88060e315d76e74269a3fc866df047f.png" alt-text="Azure 门户中的Microsoft 365页面" lightbox="../../media/e88060e315d76e74269a3fc866df047f.png":::
