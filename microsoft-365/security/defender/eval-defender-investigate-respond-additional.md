---
title: 尝试Microsoft 365 Defender环境中使用事件响应功能
description: 在威胁检测中Microsoft 365 Defender事件响应功能，确定事件的优先级并管理事件、自动调查和使用高级搜寻。
keywords: Microsoft 365 Defender试用版，请尝试Microsoft 365 Defender、Microsoft 365 Defender Microsoft 365 Defender评估实验室Microsoft 365 Defender 试点， 网络安全， 高级永久性威胁， 企业安全， 设备， 设备， 标识， 用户， 数据， 应用程序， 事件， 自动调查和修正， 高级搜寻
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.localizationpriority: medium
ms.author: dansimp
author: dansimp
ms.date: 07/09/2021
manager: dansimp
audience: ITPro
ms.collection:
- M365-security-compliance
- m365solution-scenario
- m365solution-evalutatemtp
ms.custom: admindeeplinkDEFENDER
ms.topic: conceptual
ms.technology: m365d
ms.openlocfilehash: 0ad2fc9a1566e7816b3ff806b7d07ac29347cc89
ms.sourcegitcommit: d32654bdfaf08de45715dd362a7d42199bdc1ee7
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/23/2022
ms.locfileid: "63754772"
---
# <a name="try-microsoft-365-defender-incident-response-capabilities-in-a-pilot-environment"></a>尝试Microsoft 365 Defender环境中使用事件响应功能

**适用于：**
- Microsoft 365 Defender

本文是使用试验环境对 Microsoft 365 Defender 事件进行调查和响应过程中的第 2 步（第 [2](eval-defender-investigate-respond.md) 步）。 有关此过程详细信息，请参阅 [概述](eval-defender-investigate-respond.md) 文章。

对模拟攻击[执行事件](eval-defender-investigate-respond-simulate-attack.md)响应后，下面是一些Microsoft 365 Defender功能：

|功能 |说明 |
|:-------|:-----|
| [确定事件的优先级](#prioritize-incidents) | 使用事件队列的筛选和排序来确定接下来要处理的事件。 |
| [管理事件](#manage-incidents) | 修改事件属性以确保正确分配、添加标记和注释以及解决事件。 |
| [自动调查和响应](#examine-automated-investigation-and-response-with-the-action-center) | 使用自动调查和响应 (AIR) 功能，帮助你的安全运营团队更有效地应对威胁。 操作中心是事件和警报任务（如批准挂起的修正操作）的"单窗格"体验。 |
| [高级搜寻](#use-advanced-hunting) | 使用查询主动检查网络中事件并查找威胁指示器和实体。 在调查和修正事件期间，你还使用高级搜寻。 |


## <a name="prioritize-incidents"></a>确定事件优先级

在快速启动事件门户时&事件>**事件** 和事件Microsoft 365 Defender <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">队列</a>。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents.png" alt-text="&门户中的&quot;事件和警报Microsoft 365 Defender部分" lightbox="../../media/incidents-queue/incidents-ss-incidents.png":::


" **最近的事件和警报** "部分显示过去 24 小时内收到的警报数和创建的事件数的图。

若要检查事件列表，并区分事件在分配和调查方面的重要性，您可以： 

- Configure customizable columns (select **Choose columns**) to give you visibility into different characteristics of the incident or the impacted entities. 这可以帮助您就事件的优先顺序做出明智的决策进行分析。

- 使用筛选专注于特定方案或威胁。 对事件队列应用筛选器可帮助确定需要立即关注的事件。 

从默认事件队列中，选择"**筛选器**"以查看"筛选器"窗格，可以从中指定一组特定的事件。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-filters.png" alt-text="事件门户中&quot;事件&警报&quot;部分Microsoft 365 Defender窗格" lightbox="../../media/incidents-queue/incidents-ss-incidents-filters.png":::

有关详细信息，请参阅确定 [事件的优先级](incident-queue.md)。

## <a name="manage-incidents"></a>管理事件

可以从事件的“**管理事件**”窗格管理事件。 下面是一个示例。

:::image type="content" source="../../media/incidents-queue/incidents-ss-incidents-manage.png" alt-text="事件门户中&quot;事件&警报&quot;部分Microsoft 365 Defender窗格" lightbox="../../media/incidents-queue/incidents-ss-incidents-manage.png":::

可以从以下位置的"管理 **事件"链接显示** 此窗格：

- 事件队列中事件的属性窗格。
- **事件的** 摘要页。

以下是管理事件的方法：

- 编辑事件名称

  根据安全团队最佳做法更改自动分配的名称。
  
- 添加事件标记

  添加安全团队用于对事件进行分类的标记，稍后可进行筛选。
  
- 分配事件

  将其分配给用户帐户名称，稍后可进行筛选。
  
- 解决事件

  在修复事件后关闭该事件。
  
- 设置其分类并确定

  在解决事件时分类并选择威胁类型。
  
- 添加备注

  根据安全团队最佳做法，对进度、备注或其他信息使用注释。 完整的注释历史记录可从事件详细信息页的"注释和历史记录"选项获得。

有关详细信息，请参阅 [管理事件](manage-incidents.md)。

## <a name="examine-automated-investigation-and-response-with-the-action-center"></a>使用操作中心检查自动调查和响应

根据组织的自动调查和响应功能配置方式，自动执行修正操作，或仅在安全运营团队批准后执行修正操作。 所有操作（无论是挂起操作还是已完成操作）都列在操作[](m365d-action-center.md)中心中，其中列出了设备、电子邮件&协作内容和标识的挂起和已完成的修正操作。

下面是一个示例。

:::image type="content" source="../../media/m3d-action-center-unified.png" alt-text="企业门户中的统一Microsoft 365 Defender中心" lightbox="../../media/m3d-action-center-unified.png":::

从操作中心，可以选择挂起的操作，然后在飞出窗格中批准或拒绝它们。 下面是一个示例。

:::image type="content" source="../../media/air-actioncenter-itemselected.png" alt-text="在应用程序门户中显示批准或拒绝操作Microsoft 365 Defender窗格" lightbox="../../media/air-actioncenter-itemselected.png":::


尽快 (批准或拒绝) 挂起的操作，以便自动调查可以继续并及时完成。

有关详细信息，请参阅自动[调查和响应](m365d-autoir.md)[与操作中心](m365d-action-center.md)。

## <a name="use-advanced-hunting"></a>使用高级搜寻

> [!NOTE]
> 在我们演示高级搜寻模拟之前，请观看以下视频了解高级搜寻概念，查看可在门户中查找它的地方，并了解它如何帮助你执行安全操作。

<br>

> [!VIDEO https://www.microsoft.com/videoplayer/embed/RE4Bp7O]


如果可选的无文件 [PowerShell](eval-defender-investigate-respond-simulate-attack.md#simulate-an-attack-with-an-isolated-domain-controller-and-client-device-optional) 攻击模拟是已到达凭据访问阶段的真实攻击，可以在调查的任何时间点使用高级搜寻，使用已生成的警报和受影响的实体中已了解的内容主动搜索网络的事件和记录。 

例如，根据用户和 IP 地址重新重用 [ (SMB) ](eval-defender-investigate-respond-simulate-attack.md#alert-user-and-ip-address-reconnaissance-smb-source-microsoft-defender-for-identity) `IdentityDirectoryEvents` 警报中的信息，可以使用表查找所有 SMB 会话枚举事件，或使用表在 Microsoft Defender for Identity `IdentityQueryEvents` 数据的各种其他协议中查找更多发现活动。


### <a name="hunting-environment-requirements"></a>搜寻环境要求

此模拟需要单个内部邮箱和设备。 你还需要一个外部电子邮件帐户来发送测试邮件。

1. 验证租户是否已启用[Microsoft 365 Defender](m365d-enable.md#confirm-that-the-service-is-on)。
2. 确定用于接收电子邮件的目标邮箱。

   - 此邮箱必须受 Microsoft Defender 监视，Office 365

   - 要求 3 中的设备需要访问此邮箱

3. 配置测试设备：

    a. 确保使用的是 Windows 10版本 1903 或更高版本。

    b. 将测试设备加入测试域。

    c. [打开Windows Defender 防病毒](/windows/security/threat-protection/windows-defender-antivirus/configure-windows-defender-antivirus-features)。 如果无法启用Windows Defender 防病毒，请参阅[此疑难解答主题](/windows/security/threat-protection/microsoft-defender-atp/troubleshoot-onboarding#ensure-that-microsoft-defender-antivirus-is-not-disabled-by-a-policy)。

    d. [载入到 Microsoft Defender for Endpoint](/windows/security/threat-protection/microsoft-defender-atp/configure-endpoints)。

### <a name="run-the-simulation"></a>运行模拟

1. 从外部电子邮件帐户，将电子邮件发送到在搜寻环境要求部分的步骤 2 中标识的邮箱。 包括任何现有电子邮件筛选器策略允许的附件。 此文件不需要是恶意文件或可执行文件。 建议的文件类型<i>包括.pdf、</i>.exe(（) ） <i> </i> 或 Office 文档类型（如 Word 文件）。

2. 打开从设备发送的电子邮件，如搜寻环境要求部分的步骤 3 中的定义。 打开附件或将文件保存到设备。

#### <a name="go-hunting"></a>转到搜寻

1. 打开 <a href="https://go.microsoft.com/fwlink/p/?linkid=2077139" target="_blank">Microsoft 365 Defender 门户</a>。

2. 从导航窗格中，选择"搜寻 **>高级搜寻"**。

3. 生成一个查询，该查询从收集电子邮件事件开始。

   1. 选择 **"查询>新建"**。

   1. 在" **高级搜寻** "下的"电子邮件" **组中**，双击 **"EmailEvents"**。 您应在查询窗口中看到此内容。

      ```console
      EmailEvents
      ```

   1. 将查询的时间范围更改为最近 24 小时。 假设你运行上述模拟时发送的电子邮件是过去 24 小时发送的，否则请根据需要更改时间范围。

   1. 选择 **运行查询**。 根据你的试点环境，结果可能会有所不同。

      > [!NOTE]
      > 有关限制数据返回的筛选选项，请参阅下一步。

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-1.png" alt-text="高级搜寻门户中的Microsoft 365 Defender页" lightbox="../../media/advanced-hunting-incident-response-try-1.png":::

        > [!NOTE]
        > 高级搜寻将查询结果显示为表格数据。 还可以选择查看其他格式类型（如图表）的数据。

   1. 查看结果，并查看能否识别打开的电子邮件。 邮件最多可能需要两个小时才能显示在高级搜寻中。 若要缩小结果范围，可以将 **where** 条件添加到查询中，以仅查找"yahoo.com"为 SenderMailFromDomain 的电子邮件。 下面是一个示例。

      ```console
      EmailEvents
      | where SenderMailFromDomain == "yahoo.com"
      ```

   1. 单击查询中的结果行，以便可以检查记录。

      :::image type="content" source="../../media/advanced-hunting-incident-response-try-2.png" alt-text="搜索门户中高级搜寻页面的&quot;检查记录&quot;Microsoft 365 Defender部分" lightbox="../../media/advanced-hunting-incident-response-try-2.png":::

4. 现在，你已验证是否可以看到电子邮件，请为附件添加筛选器。 重点关注环境中具有附件的所有电子邮件。 对于此模拟，重点关注入站电子邮件，而不是从你的环境发送的电子邮件。 删除已添加的任何筛选器以查找邮件并添加"|其中 **AttachmentCount > 0** 和 **EmailDirection** == **"Inbound""**

   下面的查询将显示结果，其列表比针对所有电子邮件事件的初始查询短：

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   ```

5. 接下来，包含有关附件 (，例如：文件名、) 哈希结果集。 为此，请加入 **EmailAttachmentInfo** 表。 用于联接的常用字段是 **NetworkMessageId** 和 **RecipientObjectId**。

   以下查询还包括一个附加行"| **项目重命名 EmailTimestamp=Timestamp**"，有助于确定与电子邮件相关的时间戳与下一步将添加的文件操作相关的时间戳。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   ```

6. 接下来，使用 **EmailAttachmentInfo** 表中的 **SHA256** 值查找在终结点上发生的 **DeviceFileEvents** (文件操作) 哈希。 此处的常用字段是附件的 SHA256 哈希。

   生成的表现在包含终结点 (Microsoft Defender for Endpoint) 的详细信息，例如设备名称、在这种情况下 (已执行哪些操作、已筛选为仅包括 FileCreated) 事件和存储文件的位置。 还将包含与进程关联的帐户名称。

   ```console
   EmailEvents
   | where AttachmentCount > 0 and EmailDirection == "Inbound"
   | project-rename EmailTimestamp=Timestamp
   | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
   | join DeviceFileEvents on SHA256
   | where ActionType == "FileCreated"
   ```

   现在，你已创建一个查询，该查询将标识用户打开或保存附件的所有入站电子邮件。 您还可以优化此查询以筛选特定的发件人域、文件大小、文件类型等。

7. 函数是一种特殊类型的联接，它让你可以拉取关于文件的更多 TI 数据，如其普遍程度、签名者和颁发者信息等。若要获取有关文件的更多详细信息，请使用 **FileProfile ()** 函数扩充：

    ```console
    EmailEvents
    | where AttachmentCount > 0 and EmailDirection == "Inbound"
    | project-rename EmailTimestamp=Timestamp
    | join EmailAttachmentInfo on NetworkMessageId, RecipientObjectId
    | join DeviceFileEvents on SHA256
    | where ActionType == "FileCreated"
    | distinct SHA1
    | invoke FileProfile()
    ```

#### <a name="create-a-detection"></a>创建检测

创建一个查询来标识要在将来是否发生警报的信息后，可以从该查询创建自定义检测。

自定义检测将按照您设置的频率运行查询，并且查询结果将基于您选择的影响资产创建安全警报。 这些警报将关联到事件，并可以像其中一个产品生成任何其他安全警报一样进行会审。

1. 在查询页面上，删除在"开始"搜寻说明的步骤 7 中添加的第 7 行和第 8 行，然后单击" **创建检测规则"**。

   :::image type="content" source="../../media/advanced-hunting-incident-response-try-3.png" alt-text="搜索门户中高级搜寻页面的&quot;查询Microsoft 365 Defender部分" lightbox="../../media/advanced-hunting-incident-response-try-3.png":::

   > [!NOTE]
   > 如果单击 **"创建检测规则** "，并且查询中出现语法错误，将不会保存检测规则。 仔细检查查询以确保没有错误。

2. 使用允许安全团队了解警报的信息、生成警报的原因以及预期他们执行哪些操作，填写必填字段。

   :::image type="content" source="../../media/mtp/fig23.png" alt-text="警报门户中的警报Microsoft 365 Defender页" lightbox="../../media/mtp/fig23.png":::

   确保清楚填写字段，以帮助向下一位用户告知有关此检测规则警报的明智决定

3. 选择此警报中影响的实体。 在这种情况下，请选择"**设备和****邮箱"**。

   :::image type="content" source="../../media/mtp/fig24.png" alt-text="网站门户中的&quot;影响的实体Microsoft 365 Defender页面" lightbox="../../media/mtp/fig24.png":::

4. 确定触发警报时应执行哪些操作。 在这种情况下，请运行防病毒扫描，但可能会执行其他操作。

   :::image type="content" source="../../media/mtp/fig25.png" alt-text="Microsoft 365 Defender门户中的&quot;操作&quot;页" lightbox="../../media/mtp/fig25.png":::

5. 选择警报规则的范围。 由于此查询涉及设备，因此设备组根据 Microsoft Defender for Endpoint 上下文在此自定义检测中相关。 创建不包含设备作为受影响实体的自定义检测时，范围不适用。

   :::image type="content" source="../../media/mtp/fig26.png" alt-text="Microsoft 365 Defender门户中的&quot;范围&quot;页" lightbox="../../media/mtp/fig26.png":::


   对于此试点，你可能希望将此规则限制为生产环境中的测试设备的子集。

6. 选择“**创建**”。 然后，从 **导航面板中选择** "自定义检测规则"。

   :::image type="content" source="../../media/mtp/fig27a.png" alt-text="自定义检测规则门户中的Microsoft 365 Defender选项" lightbox="../../media/mtp/fig27a.png":::

   :::image type="content" source="../../media/mtp/fig27b.png" alt-text="在应用程序门户中显示检测规则和Microsoft 365 Defender详细信息的页面" lightbox="../../media/mtp/fig27b.png":::

   在此页中，可以选择将打开详细信息页面的检测规则。

   :::image type="content" source="../../media/mtp/fig28.png" alt-text="显示触发的警报详细信息的页面在 Microsoft 365 Defender 门户" lightbox="../../media/mtp/fig28.png":::


### <a name="expert-training-on-advanced-hunting"></a>高级搜寻方面的专家培训

**跟踪对手是** 一个针对新安全分析师和经验丰富的威胁情报人员的网络广播系列。 它将指导你完成高级搜寻的基础知识，一切都可以创建自己的复杂查询。 

请参阅 [获取高级搜寻方面的专家培训](advanced-hunting-expert-training.md) 以开始。

### <a name="navigation-you-may-need"></a>可能需要的导航

[创建Microsoft 365 Defender评估环境](eval-create-eval-environment.md)
