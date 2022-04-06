---
title: 以用户身份查找并释放隔离的邮件
f1.keywords:
- NOCSH
ms.author: chrisda
author: chrisda
manager: dansimp
ms.date: ''
audience: Consumer/IW
ms.topic: how-to
ms.localizationpriority: high
search.appverid:
- MET150
- MEW150
ms.assetid: efff08ec-68ff-4099-89b7-266e3c4817be
ms.collection:
- M365-security-compliance
ms.custom:
- seo-marvel-apr2020
description: 用户可在 Exchange Online Protection （EOP）中了解如何查看和管理应该已提供给他们的隔离邮件。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 44b1d86d441be5582b8c4b3381a383b2e03417a1
ms.sourcegitcommit: b0c3ffd7ddee9b30fab85047a71a31483b5c649b
ms.translationtype: HT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/25/2022
ms.locfileid: "64471530"
---
# <a name="find-and-release-quarantined-messages-as-a-user-in-eop"></a>在 EOP 中以用户身份查找和释放已隔离邮件

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

无论是在有 Exchange Online 邮箱的 Microsoft 365 组织中，还是在没有 Exchange Online 邮箱的独立 Exchange Online Protection (EOP) 组织中，隔离功能都会隔离具有潜在危险或不需要的邮件。有关详细信息，请参与 [在 EOP 中隔离](quarantine-email-messages.md)。

作为普通用户(非管理员)，下表描述了作为已隔离邮件的收件人可用的 **默认** 功能:

|隔离原因：|查看|发布|删除|
|---|:---:|:---:|:---:|
|**反垃圾邮件策略**||||
|批量邮件|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|垃圾邮件|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|高可信度垃圾邮件|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|网络钓鱼|![复选标记。](../../media/checkmark.png)|![复选标记](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|高可信度网络钓鱼||||
|**反网络钓鱼策略**||||
|EOP 中的欺骗智能保护|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|Defender for Office 365 中的模拟用户保护|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|Defender for Office 365 中的模拟域保护|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|Defender for Office 365 中的邮箱智能保护|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|![复选标记。](../../media/checkmark.png)|
|**反恶意软件策略**||||
|包含隔离为恶意软件的附件的电子邮件。||||
|**Defender for Office 365 中的安全附件**||||
|将包含恶意附件的电子邮件隔离为恶意软件的安全附件策略。||||
|将恶意文件隔离为恶意软件的 SharePoint、OneDrive 以及 Microsoft Teams 的安全附件。||||
|**邮件流规则(传输规则)**||||
|隔离电子邮件的邮件流规则。||||

_隔离策略_ 根据在 [受支持功能](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features) 中隔离邮件的原因定义允许用户对已隔离邮件执行的操作。 默认的隔离策略会强制执行上表中所述的历史功能。 管理员可以创建并应用自定义隔离策略，这些策略为受支持功能中的用户定义限制少或多的功能。 有关详细信息，请参阅 [隔离策略](quarantine-policies.md)。

可以在 Microsoft 365 Defender 门户或来自隔离策略的隔离通知(如果管理员已设置)中查看并管理隔离邮件。

## <a name="what-do-you-need-to-know-before-you-begin"></a>开始前，有必要了解什么？

- 若要打开 Microsoft 365 Defender 门户，请转到 <https://security.microsoft.com>。 要直接转到“**隔离**”页，请使用 <https://security.microsoft.com/quarantine>。

- 管理员可以配置邮件在永久删除前的隔离期限（反垃圾邮件策略）。 隔离到期的邮件不可恢复。 有关详细信息，请参阅[在 EOP 中配置反垃圾邮件策略](configure-your-spam-filter-policies.md)。

- 默认情况下，为高可信度网络钓鱼、恶意软件隔离的或由邮件流规则隔离的邮件仅对管理员可用，且对用户不可见。 有关详细信息，请参阅 [在 EOP 中以管理员身份管理已隔离邮件和文件](manage-quarantined-messages-and-files.md)。

## <a name="view-your-quarantined-messages"></a>查看已隔离邮件

> [!NOTE]
> 查看已隔离邮件的能力由应用于隔离邮件类型的 [隔离策略](quarantine-policies.md) 控制(出于隔离原因，这可能是 [默认的隔离策略](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features))。

1. 在位于 <https://security.microsoft.com> 的 Microsoft 365 Defender 门户中，转到“**电子邮件和协作**”\>“**审阅**”\>“**隔离**”。 要直接转到“**隔离**”页，请使用 <https://security.microsoft.com/quarantine>。

2. 在“**隔离**”页上，可以通过单击可用的列标题对结果进行排序。 单击“**自定义列**”以更改显示的列。 默认值标有星号（<sup>\*</sup>）：

   - **接收时间**<sup>\*</sup>
   - **主题**<sup>\*</sup>
   - **发件人**<sup>\*</sup>
   - **隔离原因**<sup>\*</sup>
   - **释放状态**<sup>\*</sup>
   - **策略类型**<sup>\*</sup>
   - **到期时间**<sup>\*</sup>
   - **收件人**
   - **邮件 ID**
   - **策略名称**
   - **邮件大小**
   - **邮件方向**

   完成后，单击“**应用**”。

3. 要筛选结果，请单击“**筛选器**”。 在出现的 **筛选器** 中提供了以下筛选器：
   - **邮件 ID**：邮件的全局唯一标识符。
   - **发件人地址**
   - **收件人地址**
   - **主题**
   - **接收时间**：输入 **开始时间** 和 **结束时间**（日期）。
   - **过期**：按邮件的隔离到期时间筛选：
     - **今天**
     - **未来 2 天**
     - **未来 7 天**
     - **自定义**：输入 **开始时间** 和 **结束时间**（日期）。
   - **隔离原因**：
     - **大量邮件**
     - **垃圾邮件**
     - **网络钓鱼**：垃圾邮件筛选器裁定为 **网络钓鱼** 或反钓鱼保护隔离了邮件（[欺骗设置](set-up-anti-phishing-policies.md#spoof-settings) 或 [模拟保护](set-up-anti-phishing-policies.md#impersonation-settings-in-anti-phishing-policies-in-microsoft-defender-for-office-365)）。
     - **高可信度网络钓鱼**
   - **释放状态**：以下任何值：
     - **需要审查**
     - **已批准**
     - **已拒绝**
     - **已请求释放**
     - **已释放**
   - **策略类型**：按策略类型筛选邮件：
     - **反恶意软件策略**
     - **安全附件策略**
     - **反钓鱼策略**
     - **反垃圾邮件策略**

   完成后，单击“**应用**”。 要清除筛选器，请单击“![清除筛选器”图标](../../media/m365-cc-sc-clear-filters-icon.png)。 **清除筛选器**

4. 使用“**搜索**”框和相应的值来查找特定邮件。 不支持通配符。 可以按下面的值搜索：
   - 邮件 ID
   - 发件人电子邮件地址
   - 收件人电子邮件地址
   - 主题。 使用邮件的整个主题。 搜索不区分大小写。
   - 策略名称。 使用整个策略名称。 搜索不区分大小写。

   输入搜索条件后，按 Enter 筛选结果。

找到特定的已隔离邮件后，选择此邮件即可查看它的详细信息，并对它执行操作（例如，查看、释放、下载或删除邮件）。

### <a name="view-quarantined-message-details"></a>查看已隔离邮件的详细信息

从列表中选择已隔离邮件时，所显示的详细信息浮出控件中提供了以下信息。

:::image type="content" source="../../media/quarantine-user-message-details.png" alt-text="已隔离邮件的详细信息浮出控件" lightbox="../../media/quarantine-user-message-details.png":::

选择列表中的电子邮件后，可以在“详细信息”浮出控件窗格中看到以下邮件详细信息：

- **邮件 ID**：邮件的全局唯一标识符。
- **发件人地址**
- **接收时间**：收到邮件的日期/时间。
- **主题**
- **隔离原因**
- **策略类型**：策略的类型。 例如，**反垃圾邮件策略**。
- **收件人计数**
- **收件人**：如果邮件有多个收件人，需要单击“预览邮件”或“查看邮件头”，以查看完整的收件人列表。
- **到期时间**：邮件自动从隔离中永久删除的日期/时间。

要对邮件执行操作，请参阅下一部分。

> [!NOTE]
> 要保留在详细信息浮出控件中，但更改正在查看的已隔离邮件，请使用浮出控件顶部的向上和向下箭头。
>
> :::image type="content" source="../../media/quarantine-message-details-flyout-up-down-arrows.png" alt-text="已隔离邮件详细信息浮出控件中的向上和向下箭头" lightbox="../../media/quarantine-message-details-flyout-up-down-arrows.png":::

### <a name="take-action-on-quarantined-email"></a>对已隔离电子邮件执行操作

> [!NOTE]
> 对已隔离邮件执行操作的能力由应用于隔离邮件类型的[隔离策略](quarantine-policies.md) 控制(出于隔离原因，这可能是 [默认的隔离策略](quarantine-policies.md#step-2-assign-a-quarantine-policy-to-supported-features))。本节会介绍所有可用操作。

从列表中选择隔离邮件后，详细信息浮出控件中将提供以下操作：

:::image type="content" source="../../media/quarantine-user-message-details-flyout-actions.png" alt-text="隔离邮件详细信息浮出控件中的可用操作" lightbox="../../media/quarantine-user-message-details-flyout-actions.png":::

- ![释放电子邮件图标。](../../media/m365-cc-sc-check-mark-icon.png) **释放电子邮件**<sup>\*</sup>：将邮件传递到收件箱。

- ![查看邮件头图标。](../../media/m365-cc-sc-eye-icon.png) **查看邮件头**：选择此链接可查看邮件头文本。 **邮件头** 浮出控件随以下链接一起显示：
- **复制邮件头**：单击此链接可将邮件头（所有标题字段）复制到剪贴板。
- **Microsoft 邮件头分析器**：要深入分析标头字段和值，请单击此链接以转到邮件头分析器。 将邮件头粘贴到 **插入要分析的邮件头** 部分（CTRL+V 或右键单击并选择“**粘贴**”），然后单击“**分析邮件头**”。

单击“![更多操作图标](../../media/m365-cc-sc-more-actions-icon.png)”**更多操作** 后，可以执行以下操作：

- ![预览消息图标。](../../media/m365-cc-sc-eye-icon.png) **预览消息**：在显示的浮出控件中，选择下列选项卡之一：
  - “**源**”：显示禁用所有链接的 HTML 版邮件正文。
  - “**纯文本**”：以纯文本格式显示邮件正文。

- ![从隔离区中删除图标](../../media/m365-cc-sc-delete-icon.png) **从隔离区中删除**：在所显示的警告中单击“**是**”后，将立即删除该邮件，而不会发送给原始收件人。

- ![下载电子邮件图标。](../../media/m365-cc-sc-download-icon.png) **下载电子邮件**：在所显示的浮出控件中选择“**我了解下载此邮件所带来的风险**”，然后单击“**下载**”可使用 .eml 格式保存邮件的本地副本。

- ![阻止发件人图标。](../../media/m365-cc-sc-block-sender-icon.png) **阻止发件人**：将发件人添加到 **你的** 邮箱中的阻止发件人列表中。 有关详细信息，请参阅 [阻止邮件发件人](https://support.microsoft.com/office/b29fd867-cac9-40d8-aed1-659e06a706e4)。

<sup>\*</sup> 此选项不适用于已经释放的邮件（**已释放状态** 值为 **已释放**）。

如果没有释放或删除邮件，则将在默认隔离保持期到期（如 **过期** 列中所示）后删除。

> [!NOTE]
> 在移动设备上，说明文本在操作图标上不可用。
>
> :::image type="content" source="../../media/quarantine-user-message-details-flyout-mobile-actions.png" alt-text="已隔离邮件的详细信息，其中突出显示了可用操作" lightbox="../../media/quarantine-user-message-details-flyout-mobile-actions.png":::

>
> 下表汇总了按顺序排列的图标及其相应的说明：
>
> |图标|说明|
> |---:|---|
> |![释放电子邮件图标。](../../media/m365-cc-sc-check-mark-icon.png)|**释放电子邮件**|
> |![查看邮件头图标。](../../media/m365-cc-sc-eye-icon.png)|**查看邮件头**|
> |![预览邮件图标。](../../media/m365-cc-sc-eye-icon.png)|**预览邮件**|
> |![从隔离区中删除图标。](../../media/m365-cc-sc-delete-icon.png)|**从隔离区中删除**|
> |![阻止发件人图标。](../../media/m365-cc-sc-block-sender-icon.png)|**阻止发件人**|

#### <a name="take-action-on-multiple-quarantined-email-messages"></a>对多封已隔离电子邮件执行操作

当通过单击第一列左侧空白区域来选择列表中的多个已隔离邮件（最多 100 条）时，将显示“**批量操作**”下拉列表，你可以在其中执行以下操作：

:::image type="content" source="../../media/quarantine-user-message-bulk-actions.png" alt-text="隔离区中邮件的批量操作下拉列表" lightbox="../../media/quarantine-user-message-bulk-actions.png":::

- ![释放电子邮件图标。](../../media/m365-cc-sc-check-mark-icon.png) **释放邮件**：将邮件传递到收件箱。
- ![从隔离区中删除图标。](../../media/m365-cc-sc-delete-icon.png) **删除邮件**：在所显示警告中单击“**是**”后，将立即从隔离区中删除该邮件，而不会发送给原始收件人。
