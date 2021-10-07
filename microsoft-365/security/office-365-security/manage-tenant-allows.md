---
title: 在租户允许/阻止列表中管理允许
f1.keywords:
- NOCSH
ms.author: dansimp
author: dansimp
manager: dansimp
ms.date: ''
audience: ITPro
ms.topic: how-to
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- M365-security-compliance
description: 管理员可以了解如何在安全门户的租户允许/阻止列表中配置允许。
ms.technology: mdo
ms.prod: m365-security
ms.openlocfilehash: 411fc860ad59c214000936486d3c0456c732df19
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60190313"
---
# <a name="add-allows-in-the-tenant-allowblock-list"></a>在租户允许/阻止列表中添加允许

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender-for-office.md)]

**适用对象**
- [Exchange Online Protection](exchange-online-protection-overview.md)
- [Microsoft Defender for Office 365 计划 1 和计划 2](defender-for-office-365.md)
- [Microsoft 365 Defender](../defender/microsoft-365-defender.md)

允许不能直接添加到租户允许/阻止列表。 使用管理员提交过程将 URL、文件和/或发件人允许添加到租户允许/阻止列表。 Microsoft 不允许管理员添加直接允许，但确定阻止了哪些内容，并提供了允许。 在大多数情况下，添加 允许为系统提供一些时间，并自然地允许（如果需要）。 在某些情况下，Microsoft 会管理你的允许。

## <a name="add-allows-using-the-submissions-portal"></a>添加允许使用提交门户 

允许文件的提交部分中的文件、URL 和Microsoft 365 Defender。 

1. 在 Microsoft 365 Defender 门户中，转到"电子邮件 **&协作** \> **提交"。**

2. 在 **"提交"** 页上，确认已选择" **已提交进行分析"** 选项卡，然后单击 ![ "广告图标"。](../../media/m365-cc-sc-create-icon.png) **提交到 Microsoft 进行分析**。

3. 使用 **"提交给 Microsoft 审阅** "飞出页面将发件人、文件或 URL 标记为误报。 

4. 在"**选择提交** 到 Microsoft 的原因"部分，选择"不应被阻止 (**误报) 。** 

5. 启用" **允许类似此选项的邮件** "。 

6. 从 **"删除后** "下拉列表中，指定您希望允许选项工作多久。

7. 完成后，单击"提交 **"** 按钮。

> [!div class="mx-imgBorder"]
> ![误报提交示例。](../../media/admin-submission-allow-messages.png)

## <a name="create-spoofed-sender-allow-entries-using-microsoft-365-defender"></a>创建欺骗性发件人允许使用Microsoft 365 Defender

**注意**:

- 仅 _明确_ 允许或阻止欺骗用户和域对中定义的发送基础结构的组合。
- 为域对配置允许或阻止条目时，来自该域对的邮件将不再显示在欺骗智能见解中。
- 欺骗性发件人的条目永不过期。
- 欺骗同时支持允许和阻止。 URL 仅支持允许。

1. In the Microsoft 365 Defender portal， go to **Policies & rules** Threat \> **Policies** \> **Rules** section \> **Tenant Allow/Block Lists**.

2. 在" **租户允许/阻止列表"** 页上，选择" **欺骗"** 选项卡，然后单击"阻止 ![ 图标"。](../../media/m365-cc-sc-create-icon.png) **添加** 。

3. 在出现的 **"添加新域对** "飞出中，配置以下设置：
   - **使用通配符添加新域对**：每行输入一个域对，最多输入 20 个域对。 有关欺骗性发件人条目的语法的详细信息，请参阅 [管理租户允许/阻止列表](tenant-allow-block-list.md)。
   - **欺骗类型**：选择下列值之一：
     - **内部**：欺骗性发件人位于组织所属的域中， ([接受的) 。](/exchange/mail-flow-best-practices/manage-accepted-domains/manage-accepted-domains)
     - **外部**：欺骗性发件人位于外部域中。
   - **操作**：选择 **"允许"** 或"**阻止"。**

4. 完成后，单击“**添加**”。

## <a name="add-spoofed-sender-allow-entries-using-powershell"></a>使用 PowerShell 添加欺骗性发件人允许条目

若要在租户允许/阻止列表中添加欺骗性发件人条目，请使用以下语法：

```powershell
New-TenantAllowBlockListSpoofItems -SpoofedUser <Domain | EmailAddress | *> -SendingInfrastructure <Domain | IPAddress/24> -SpoofType <External | Internal> -Action <Allow | Block>
```

有关语法和参数的详细信息，请参阅 [New-TenantAllowBlockListSpoofItems](/powershell/module/exchange/new-tenantallowblocklistspoofitems)。

## <a name="related-articles"></a>相关文章

- [管理员提交](admin-submission.md)
- [报告误报和漏报](report-false-positives-and-false-negatives.md)