---
title: 管理精确数据匹配架构
f1.keywords:
- NOCSH
ms.author: chrfox
author: chrfox
manager: laurawi
audience: Admin
ms.topic: how-to
ms.service: O365-seccomp
ms.date: ''
localization_priority: Normal
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何编辑或删除精确数据匹配架构。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 7fb535f08b178cf934ec7586579a00725747a3ce
ms.sourcegitcommit: 8410a49995a084e4cc9b3f7286c8d506b7a85d79
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 11/11/2021
ms.locfileid: "60914738"
---
# <a name="manage-your-exact-data-match-schema"></a>管理精确数据匹配架构

## <a name="editing-the-schema-for-edm-based-classification-manually"></a>手动编辑基于 EDM 的分类的架构

如果要更改 EDM 架构，例如edm.xml文件，例如更改用于基于 EDM 的分类的字段，请按照以下步骤操作：

> [!TIP]
> 你可以更改 EDM 架构和敏感信息表源文件，以利用 **可配置的匹配**。 配置后，EDM 在对某个项目进行求值时将忽略大小写差异和某些分隔符。 这使你能够更轻松地定义 xml 架构和敏感数据文件。 若要了解更多信息，请参阅 [使用 caseInsensitive 和 ignoredDelimiters 字段](sit-get-started-exact-data-match-create-schema.md#using-the-caseinsensitive-and-ignoreddelimiters-fields)。

1. 编辑edm.xml **文件** (创建基于准确数据匹配的敏感信息类型的架构 [中讨论的文件](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)。

2. 使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。

3. 要更新数据库架构，请逐一运行下列 cmdlet：

      ```powershell
      $edmSchemaXml=Get-Content .\\edm.xml -Encoding Byte -ReadCount 0
      Set-DlpEdmSchema -FileData $edmSchemaXml -Confirm:$true
      ```

      系统将提示你进行确认，如下所示：

      > 确认
      >
      > 是否确实要执行此操作？
      >
      > 将更新数据存储“patientrecords”的 EDM 架构。
      >
      > \[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：

      > [!TIP]
      > 若想更改但不进行确认，请在步骤 3 中改用此 cmdlet：Set-DlpEdmSchema -FileData $edmSchemaXml

      > [!NOTE]
      > 为 EDMSchema 更新新增内容可能需要10-60 分钟。 必须先完成更新，然后才能执行使用新增功能的步骤。-->

## <a name="removing-the-schema-for-edm-based-classification-manually"></a>手动删除基于 EDM 的分类的架构

如果要删除用于基于 EDM 的分类的架构，请按照以下步骤操作：

1. 使用[连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell) 中的步骤连接到安全与合规中心。

2. 运行以下 PowerShell cmdlet，使用 patientrecords 存储作为示例来使用要删除的 (来将"患者记录"的数据存储名称) ：

      ```powershell
      Remove-DlpEdmSchema -Identity 'patientrecords'
      ```

      系统将提示你进行确认：

      > 确认
      >
      > 是否确实要执行此操作？
      >
      > 将删除数据存储“patientrecords”的 EDM 架构。
      >
      > \[Y\] 是 \[A\] 全部是 \[N\] 否 \[L\] 全部否 \[?\] 帮助（默认为“Y”）：

      > [!TIP]
      >  若想更改但不进行确认，请在步骤 2 中改用此 cmdlet：Remove-DlpEdmSchema -Identity patientrecords -Confirm:$false

### <a name="edit-or-delete-the-edm-schema-with-the-wizard"></a>使用向导编辑或删除 EDM 架构

1. 打开 **合规**  >  **中心数据分类**  >  **精确数据匹配**。

2. 选择 **"EDM 架构"。**

3. 选择要编辑的 EDM SIT。

4. 从 **飞出控件中选择"编辑 EDM** 架构"或"删除 **EDM** 架构"。

> [!IMPORTANT]
> 若要删除已经关联某一 EDM 敏感信息类型的架构，必须先删除此 EDM 敏感信息类型，然后才能删除架构。