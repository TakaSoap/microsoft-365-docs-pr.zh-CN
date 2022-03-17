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
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
search.appverid:
- MOE150
- MET150
description: 了解如何编辑或删除精确数据匹配架构。
ms.custom: seo-marvel-apr2020
ms.openlocfilehash: 8e06cb25db0a8c616b5b692a423d9827e8918dc9
ms.sourcegitcommit: 3fb76db6b34e24569417f4c8a41b99f46a780389
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/17/2022
ms.locfileid: "63525189"
---
# <a name="manage-your-exact-data-match-schema"></a>管理精确数据匹配架构

## <a name="editing-the-schema-for-edm-based-classification-manually"></a>手动编辑基于 EDM 的分类的架构

如果要更改 EDM 架构，例如edm.xml文件，例如更改用于基于 EDM **** 的分类的字段，请按照以下步骤操作：

> [!TIP]
> 您可以更改 EDM 架构和敏感信息表源文件，以利用 **可配置的匹配**。 配置后，EDM 在对某个项目进行求值时将忽略大小写差异和某些分隔符。 这使你能够更轻松地定义 xml 架构和敏感数据文件。 若要了解更多信息，请参阅 [使用 caseInsensitive 和 ignoredDelimiters 字段](sit-get-started-exact-data-match-create-schema.md#using-the-caseinsensitive-and-ignoreddelimiters-fields)。

1. 编辑 **edm.xml文件** (创建基于准确数据匹配的敏感信息类型的架构 [中讨论的文件](sit-get-started-exact-data-match-create-schema.md#create-the-schema-for-exact-data-match-based-sensitive-information-types)。

2. [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

3. 若要更新数据库架构，请运行以下命令：

      ```powershell
      Set-DlpEdmSchema -FileData ([System.IO.File]::ReadAllBytes('.\\edm.xml')) -Confirm:$true
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
      > 如果希望更改在未确认的情况下发生，请不要 `-Confirm:$true` 在步骤 3 中使用。

      > [!NOTE]
      > 为 EDMSchema 更新新增内容可能需要10-60 分钟。 更新必须完成，然后才能执行使用这些新增操作的步骤。

## <a name="removing-the-schema-for-edm-based-classification-manually"></a>手动删除基于 EDM 的分类的架构

如果要删除用于基于 EDM 的分类的架构，请按照以下步骤操作：

1. [连接到安全与合规中心 PowerShell](/powershell/exchange/connect-to-scc-powershell)。

2. 运行以下命令，使用 patientrecords 存储作为示例，将"患者记录"的数据存储名称 (要删除的数据存储名称) ：

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
      > 如果希望更改在未经确认的情况下进行，请不要在 `-Confirm:$true` 步骤 2 中使用它。

### <a name="edit-or-delete-the-edm-schema-with-the-wizard"></a>使用向导编辑或删除 EDM 架构

1. 打开 **合规性中心** \> **数据分类** \> **精确数据匹配**。

2. 选择 **"EDM 架构"**。

3. 选择要编辑的 EDM SIT。

4. 从 **飞出控件中选择** "编辑 **EDM** 架构"或"删除 EDM 架构"。

> [!IMPORTANT]
> 若要删除已经关联某一 EDM 敏感信息类型的架构，必须先删除此 EDM 敏感信息类型，然后才能删除架构。
