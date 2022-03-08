---
title: Microsoft 合规性管理器入门
f1.keywords:
- NOCSH
ms.author: chvukosw
author: chvukosw
manager: laurawi
audience: Admin
ms.topic: article
ms.service: O365-seccomp
ms.localizationpriority: medium
ms.collection:
- M365-security-compliance
- m365solution-compliancemanager
- m365initiative-compliance
ms.custom: admindeeplinkCOMPLIANCE
search.appverid:
- MOE150
- MET150
description: 设置 Microsoft 合规性管理器用户权限和角色，并配置操作自动化测试。 管理用户历史记录并筛选仪表板视图。
ms.openlocfilehash: 070c8fea309ea7c01b82be068acc40a7dcb830ff
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330477"
---
# <a name="get-started-with-compliance-manager"></a>合规性管理器入门

**本文内容：** 本文可帮助你设置合规性管理器。 了解如何访问 **合规性** 管理器 **、设置角色和权限** 以及配置 **改进操作自动测试**。 浏览 **合规性管理器仪表板** 并了解主要页面：改进操作页面、解决方案页面、评估页面和评估模板页面。

## <a name="who-can-access-compliance-manager"></a>Who可以访问合规性管理器

合规性管理器适用于具有 Office 365 和 Microsoft 365 许可证的组织，以及美国 政府社区云 (GCC) 中等、GCC 高和国防部 (DoD) 客户。 评估可用性和管理功能取决于您的许可协议。  [查看服务说明详细信息](/office365/servicedescriptions/microsoft-365-service-descriptions/microsoft-365-tenantlevel-services-licensing-guidance/microsoft-365-security-compliance-licensing-guidance)。

## <a name="before-you-begin"></a>准备工作

组织的Microsoft 365管理员可能是第一个访问合规性管理器的用户。 我们建议全局管理员登录并设置用户权限，如第一次访问合规性管理器时所述。

## <a name="sign-in"></a>登录

1. 转到"<a href="https://go.microsoft.com/fwlink/p/?linkid=2077149" target="_blank">Microsoft 365 合规中心</a>**"，然后使用全局** Microsoft 365帐户登录。
2. 选择 **左侧导航** 窗格中的"合规性管理器"。 你将到达合规性管理器 [仪表板](#understand-the-compliance-manager-dashboard)。

访问合规性管理器的直接链接是 [https://compliance.microsoft.com/compliancemanager](https://compliance.microsoft.com/compliancemanager)。

## <a name="set-user-permissions-and-assign-roles"></a>设置用户权限和分配角色

合规性管理器使用基于角色的访问控制 (RBAC) 权限模型。 只有分配了角色的用户才能访问合规性管理器，并且每个用户允许的操作受角色 [类型限制](#role-types)。

### <a name="where-to-set-permissions"></a>在何处设置权限

拥有组织的全局管理员角色的人可以设置合规性管理器的用户权限。 权限可以在用户和Microsoft 365 合规中心中设置Azure Active Directory (Azure AD) 。

> [!NOTE]
> 美国政府高级Community (GCC) 和国防部 (DoD) 环境的客户只能在 Azure AD 中为合规性管理器设置用户权限和Azure AD。 请参阅下文Azure AD说明和角色类型定义。

若要设置权限并分配角色Microsoft 365 合规中心，请按照以下步骤操作：

1. 转到"Microsoft 365 合规中心"，然后选择 <a href="https://go.microsoft.com/fwlink/p/?linkid=2173597" target="_blank">**"权限"**</a>。

2. 在" **合规中心"** 下拉列表下，选择" **角色"**。

3. 查找要添加一个或多个用户的角色组，并选中组名称左侧的框。  (请参阅 [下面的角色和相关函数列表](#role-types)。 角色组名称模仿角色名称) 

4. 在该组的飞出窗格中，选择"成员 **"** 标题下的 **"编辑** "。

5. 选择 **"选择成员"**。 将显示另一个弹出窗口。

6. 选择 **+ 添加** 以选择要添加到组的一个或多个用户。

7. 选中要添加的名称旁边的复选框，然后选择底部的 **"添加** "按钮。

8. 完成用户分配后，选择"完成"，然后选择"**保存**"，然后选择"关闭 **"**。

#### <a name="more-about-azure-ad"></a>有关Azure AD

若要分配角色并设置Azure AD，请参阅向具有此权限的用户分配管理员[Azure Active Directory](/azure/active-directory/fundamentals/active-directory-users-assign-role-azure-portal)。

具有 Azure AD 身份的用户Office 365或Microsoft 365订阅的用户将无法在 Microsoft 365 合规中心 中访问合规性管理器。 若要在访问合规性管理器方面寻求帮助 [，请联系 cmresearch@microsoft.com](mailto:cmresearch@microsoft.com)。

### <a name="role-types"></a>角色类型

下表显示了合规性管理器中每个角色允许的功能。 该表还显示每个角色[Azure AD](/azure/active-directory/roles/permissions-reference)映射到合规性管理器角色。 用户至少需要合规性管理器读者角色Azure AD全局读者角色，以访问合规性管理器。

| 用户可以： | 合规性管理器角色 | Azure AD角色 | 
| :------------- | :-------------: | :------------: |
| **读取但不编辑数据**| 合规性管理器读者  | Azure AD全局读者、安全读者 |
| **编辑数据**| 合规性管理器贡献 | 合规管理员 |
| **编辑测试结果**| 合规性管理器评估方 | 合规管理员 |
| **管理评估、模板和租户数据**| 合规性管理器管理 | 合规性管理员、合规性数据管理员、安全管理员  |
| **分配用户**| 全局管理员 | 全局管理员 |

## <a name="start-a-premium-assessments-trial"></a>启动高级评估试用版

合规性管理器高级评估试用版是快速设置与组织最相关的评估的一种很好的方法。 我们的 300 多个模板库对应于世界各地的政府法规和行业标准。
详细了解高级 [评估试用版](compliance-easy-trials-compliance-manager-assessments.md)。

你可以直接从合规性管理器启动试用版，然后按照以下步骤设置建议评估：

1. 在"合规性管理器 **概述"** 页上，选择" **开始试用"**。 你将输入试用激活向导，该向导将提问以帮助我们为组织推荐评估。

2. 在" **激活试用版"** 页面上，选择" **下** 一步"开始免费试用 90 天高级评估并继续创建评估。

3. 选择一个或多个确定组织的行业，然后选择"下一步 **"**。

4. 为组织的位置选择一个或多个区域，然后选择"下一步 **"**。

5. 在 **"选择评估**"屏幕上，选择"推荐模板"旁边的下拉箭头，查看我们认为适用于你的组织的评估列表。 选中要用于创建评估的模板旁边的框，然后选择"下一步 **"**。

6. 查看最终选择，然后选择 **"添加建议评估** "以创建新评估。

通过访问下面的"评估"页面 [部分了解有关评估入门](#assessments-page) 的详细信息。

## <a name="settings-for-automated-testing-and-user-history"></a>设置自动测试和用户历史记录

合规性管理器设置Microsoft 365 合规中心启用和禁用改进操作自动测试。 这些设置还允许您管理与改进操作关联的用户数据，包括将改进操作重新分配给其他用户的能力。  只有具有全局管理员或合规性管理器管理员角色的人才能访问合规性管理器设置。

> [!NOTE]
> 自动测试功能不适用于高GCC DoD 环境中的客户，因为这些环境中没有安全功能分数。 GCC高和 DoD 客户需要手动实施和测试其改进操作。

### <a name="set-up-automated-testing"></a>设置自动测试

合规性管理器检测到来自Microsoft 365订阅的其他合规性解决方案的信号，包括信息管理、信息保护、数据丢失防护、通信合规性和内部风险管理。 在每个改进操作的详细信息页面中，"测试"选项卡上的"测试逻辑"字段将显示其他解决方案中所需的内容，以便操作通过合规性分数并获得分数。

合规性管理器还可以检测来自补充改进操作的信号，这些改进操作也受 [Microsoft 安全分数监视](../security/defender/microsoft-secure-score.md)。 借助这些信号，合规性管理器可自动测试某些改进操作，从而最大限度地提高合规性活动的效率。 成功测试和实现改进操作后，你将收到完整分数，这可得到总合规性分数的积分。

在每个改进操作的详细信息页中

默认情况下，对使用合规性管理器的组织启用自动测试。 首次部署Microsoft 365或Office 365时，需要大约 7 天来完全收集数据，并纳入合规性分数中。 启用自动测试后，不会更新该操作的测试日期，但其测试状态将更新。 创建新评估后，分数将自动包含 Microsoft 控制分数和安全分数集成。

#### <a name="manage-automated-testing-settings"></a>管理自动测试设置

组织的全局管理员可以随时更改自动测试的设置。 您可以关闭常见改进操作自动化测试，或为单个操作启用它。 按照下面的说明更改自动测试设置。

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**设置**</a>中选择"Microsoft 365 合规中心"。

2. 在设置页上，选择合规性 **管理器**。

3. 从 **左侧导航栏中** 选择"自动测试"。

4. 选择适用的按钮以针对所有改进操作启用自动测试，针对所有操作将其关闭，或按单个操作打开。

5. 如果您选择" **启用每个改进操作"**，则列表将显示可供选择的所有可用改进操作。  选中要自动测试的任何操作旁边的框。

6. 选择 **"保存** "以保存设置。 You'll receive a confirmation message at the top of your screen that your selection was saved. 如果收到失败通知，请重试。

**注意：** 只有全局管理员可以打开或关闭所有操作自动更新。 合规性管理器管理员可以为单个操作（而不是全局性的所有操作）启用自动更新。

**了解详细信息**
- [详细了解持续监视如何增加合规性分数](compliance-score-calculation.md#how-compliance-manager-continuously-assesses-controls)。
- [详细了解如何为改进操作指定测试源](compliance-manager-improvement-actions.md#update-testing-source)。

### <a name="manage-user-history"></a>管理用户历史记录

管理 **用户历史记录** 设置可帮助您快速识别哪些用户已使用合规性管理器中的改进操作。 与改进操作关联的可识别用户数据包括完成的任何实施和测试工作、他们上载的文档以及他们输入的任何注释。 了解和检索此类数据对于组织自己的合规性需求可能是必需的。

用户历史记录设置还允许您将一个用户的所有改进操作重新分配给另一个用户。

**若要查找用户历史记录设置，请执行以下操作：**

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**设置**</a>中选择"Microsoft 365 合规中心"。

2. 在设置页上，选择合规性 **管理器**。

3. 从 **左侧导航栏中选择** "管理用户历史记录"。

" **管理用户历史记录** "页按电子邮件地址显示分配给改进操作的所有用户的列表。 通过 **键入** 特定用户的电子邮件地址，使用"搜索"按钮快速查找该用户。

在每个用户的电子邮件地址右侧，"选择"下拉菜单提供导出报告、重新分配改进操作或删除历史记录的选项。 有关每个选项的详细信息，请参阅下面的每个部分。

#### <a name="export-a-report-of-user-history-data"></a>导出用户历史记录数据报告

您可以导出一Excel一个包含当前分配给用户的改进操作列表的文件。  该报告还列出了该用户上载的任何证据文件。 此信息可帮助您重新分配开放改进操作。

该报告反映自创建日期起改进操作的状态。 这不是以前对状态或工作分配的所有更改的历史报告， (从改进操作页面[导出) 。](compliance-manager-improvement-actions.md#export-a-report)

**按照以下步骤按用户导出报告：**

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**设置**</a>中选择"Microsoft 365 合规中心"。

2. 在设置页上，选择合规性 **管理器**。

3. 从 **左侧导航中选择** "管理用户历史记录"。

4. 通过搜索列表电子邮件地址，或选择"搜索"并输入用户的电子邮件地址来查找目标用户。

5. 从" **选择"** 下拉菜单中，选择" **导出报告"**。

6. 生成Excel文件后，你可以打开它并将其保存到本地计算机。

#### <a name="reassign-improvement-actions-to-another-user"></a>将改进操作重新分配给其他用户

您可以将改进操作从一个用户重新分配到另一个用户。 重新分配操作时，文档上载历史记录不会更改，但最初上载文档的用户的名称不再显示在改进操作中。

**按照以下步骤将改进操作重新分配给其他用户：**

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**设置**</a>中选择"Microsoft 365 合规中心"。

2. 在设置页上，选择合规性 **管理器**。

3. 从 **左侧导航中选择** "管理用户历史记录"。

4. 通过搜索列表电子邮件地址或选择"搜索"并输入该用户的电子邮件地址来查找用户。

5. 从" **选择"** 下拉菜单中，选择" **重新分配改进操作"**。 将显示 **"重新分配改进操作** "飞出窗格。

6. 在 **"搜索用户** "字段中，输入要为其分配改进操作的用户的姓名或 *电子邮件地址*。

7. 在"将为其分配改进操作"下看到预期用户的名称时，请选择该用户，然后选择"分配 **操作"**。

8. 重新分配完成后，你将在飞出窗格中看到确认消息，确认之前用户的所有改进操作已重新分配到新用户。 如果收到重新分配失败通知，请关闭窗口并重试。 若要关闭飞出窗格，请选择"完成 **"**。

新接受者将收到已分配给改进操作的电子邮件。 电子邮件包含指向改进操作的详细信息页面的直接链接。

 > [!NOTE]
> 如果重新分配具有挂起更新的操作，如果在重新分配后接受更新，则指向重新分配电子邮件中的操作的直接链接将中断。 可以通过在接受更新后将操作重新分配给用户来解决此问题。 详细了解改进 [操作更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)。

#### <a name="delete-user-history"></a>删除用户历史记录

删除用户的历史记录将删除他们作为改进操作的所有者，并且会将其姓名从合规性管理器中的所有其他字段中删除。 删除用户的历史记录时，在分配新用户之前，他们拥有的改进操作不会显示"分配到"值。 上载到改进操作的任何文档 **都将显示已删除** 的用户，以更改已删除用户的名称。 删除用户历史记录是永久性的。

若要删除用户的历史记录，请按照以下步骤操作：

1. 在 <a href="https://go.microsoft.com/fwlink/p/?linkid=2174201" target="_blank">**设置**</a>中选择"Microsoft 365 合规中心"。

2. 在设置页上，选择合规性 **管理器**。

3. 从 **左侧导航中选择** "管理用户历史记录"。

4. 通过搜索列表电子邮件地址或选择"搜索"并输入该用户的电子邮件地址来查找用户。

5. 从" **选择"** 下拉菜单中，选择" **删除历史记录"**。

6. 将出现一个要求您确认永久删除用户历史记录的窗口。 若要继续删除，请选择" **删除历史记录"**。 若要在不删除历史记录的情况下保留，请选择"取消 **"**。

7. 你将返回到"管理用户历史记录"页，顶部会显示一条确认消息，指出该用户的历史记录已删除。

## <a name="understand-the-compliance-manager-dashboard"></a>了解合规性管理器仪表板

合规性管理器仪表板旨在为您提供当前合规性状况的概览。

:::image type="content" alt-text="合规性管理器 - 仪表板。" source="../media/compliance-manager-dashboard.png" lightbox="../media/compliance-manager-dashboard.png":::

### <a name="overall-compliance-score"></a>整体合规性分数

合规性分数特别推荐在最上面。 它根据完成解决关键数据保护标准和法规的改进操作可达到的分数来显示百分比。 Microsoft 操作 [中的分数](compliance-manager-assessments.md#microsoft-actions-tab)（管理我的 Microsoft）也计入合规性分数中。

首次访问合规性管理器时，初始分数基于Microsoft 365[基线](compliance-manager-assessments.md#data-protection-baseline-default-assessment)。 此基线评估可供所有组织使用，是一组包含常见行业法规和标准的控制措施。 合规性管理器可扫描Microsoft 365解决方案，并基于当前隐私和安全设置进行初始评估。 添加与组织相关的评估时，分数将变得更加有意义。

**了解更多信息**[：了解如何计算合规性分数](compliance-score-calculation.md)。

### <a name="key-improvement-actions"></a>关键性改进措施

本部分列出了你现在可以采取的最大改进措施，以对整体合规性分数产生最大正面影响。 选择 **"查看所有改进操作** "以转到您的改进操作页面。

### <a name="solutions-that-affect-your-score"></a>影响分数的解决方案

本节重点介绍包含可直接影响分数的改进操作的解决方案，以及这些解决方案中未完成的改进操作的数量。 选择 **"查看所有解决方案** "以访问您的解决方案页面。

### <a name="compliance-score-breakdown"></a>合规性分数细目

本部分以两种不同的方式为你提供分数的更详细视图：

- **类别**：显示数据保护类别（如"保护信息"或"管理设备"）中总分数的百分比。
- **评估**：显示管理特定合规性和数据保护标准、法规或法律（如 GDPR 或 NIST 800-53）评估的进度百分比。

### <a name="filtering-your-dashboard-view"></a>筛选仪表板视图

可以筛选仪表板视图，以便仅查看与特定法规和标准、解决方案、操作类型、评估组或数据保护类别相关的项目。 通过此方式筛选视图还将筛选仪表板上的分数，显示根据筛选条件在可能的总分数中已实现的分数。

应用筛选器：

1. 选择 **仪表板** 右上角的"筛选"。
2. 从"筛选器"飞出 **窗格中选择** 筛选条件，然后选择"应用 **"**。

应用筛选器后，你将看到实时调整的分数。 合规性分数百分比和细分信息以及改进操作和解决方案现在仅与筛选器条件涵盖的数据相关。 如果你注销合规性管理器，则你的已筛选视图在重新登录时保留。

若要删除筛选器：

- 在合规性 **分数上方的** "应用的筛选器"标题中，选择要删除的单个筛选器旁边的 **"X** ";或
- 选择 **仪表板** 右上角的"筛选器"，然后在"筛选器"飞出窗格中，选择"**清除筛选器"**。

## <a name="improvement-actions-page"></a>"改进操作"页

[改进操作](compliance-manager-improvement-actions.md) 是由组织管理的操作。 使用改进操作有助于集中您的合规性活动，并符合数据保护法规和标准。 每个改进操作都提供了详细的实施指南和链接，将你引导到适当的解决方案中。 可以将改进操作分配给贵组织的用户，以执行实施和测试工作。 您还可以在改进操作中存储文档、备注和记录状态更新。

### <a name="view-your-improvement-actions"></a>查看改进操作

合规性管理器仪表板显示关键改进操作。 若要查看所有改进操作，请选择仪表板上的"改进操作"选项卡，将您带到您的改进操作页面。 还可以在仪表板上的关键 **改进** 操作列表下方选择"查看所有改进操作"，以进入改进操作页面。

"改进操作"页显示组织管理的所有改进操作。 可在每项评估中查看由 Microsoft 管理的操作， ([Microsoft 行动](compliance-manager-assessments.md#microsoft-actions-tab)) 。

如果您的改进操作页上有一个很长的操作列表，则筛选视图可能会很有帮助。 选择 **操作** 列表右上角的"筛选"。 当" **筛选器** "飞出窗格出现时，从可用选项中选择条件。 您还可以通过在右上角选择"组"来自定义视图。 从下拉菜单中，选择以按组、解决方案、类别、操作类型或状态进行查看。

此页面的默认视图不会显示测试状态为"已通过"的改进 **操作**。 若要查看已通过测试的操作，请选中"筛选器 **"** 飞出窗格中的"通过"框。 仅测试状态为 **"已通过"的操作** 计入分数。 某些操作可能会显示挂起 **的更新标签。** 详细了解改进 [操作更新](compliance-manager-improvement-actions.md#accepting-updates-to-improvement-actions)。

"改进操作"页显示每个改进操作的以下数据点：

- **产品**：正在评估的产品。
- **已实现** 点数：完成操作在可用总数中实现的点数
- **法规**：与操作相关的法规或标准
- **组**：将操作分配到的组
- **解决方案**：可以执行该操作的解决方案
- **评估**：包含行动的评估
- **类别**：相关的数据保护类别 (，例如，保护信息、管理设备等) 
- **测试状态**：
  - **无** - 未记录状态更新
  - **未评估** - 测试尚未开始
  - **已通过** - 实现已成功测试
  - **风险较低失败** - 测试失败，风险低
  - **中风险失败** - 测试失败，中等风险
  - **高风险失败** - 测试失败，高风险
  - **超出范围** - 操作不在评估范围内，不会影响分数
  - **要检测** - 对于手动测试，指示已实现但未测试操作;对于自动测试，指示操作正在等待自动化结果
  - **无法检测到** - 无法确定自动状态
  - **部分测试** – 自动评分，表示部分分数
- **操作类型**：指示改进操作是技术操作，即它可以在解决方案或产品内实施，还是非技术操作，这将在技术解决方案之外实现
- **分配到：** 已分配此操作的人（如果适用）
- **测试** 源：指示操作的测试源是手动、自动还是从父项继承

**了解更多信息**[：了解如何分配和执行改进操作](compliance-manager-improvement-actions.md)。

## <a name="solutions-page"></a>"解决方案"页

"解决方案"页显示按解决方案组织的挣值和潜在点数的共享。 从此视图中查看剩余点和改进操作可帮助您了解哪些解决方案需要立即关注。

通过选择合规性管理器仪表板 **上的"解决方案** "选项卡查找解决方案页面。 还可以在仪表板右上角 **的**"解决方案"下方选择"查看影响分数的所有解决方案"。

### <a name="filtering-your-solutions-view"></a>筛选解决方案视图

筛选解决方案视图：

1. 选择 **评估** 列表左上角的"筛选"。
2. 在 **"筛选器** "飞出窗格中，在所需条件旁边放置一个检查 (法规、解决方案、操作类型、组、类别) 。
3. 选择" **应用"** 按钮。 筛选器窗格将关闭，并且你将看到已筛选视图。

您还可以通过从评估列表上方的"组"下拉菜单中选择分组类型，来修改视图以查看按组、产品或法规的评估。

### <a name="taking-action-from-the-solution-page"></a>从解决方案页面采取措施

"解决方案"页显示与改进操作有关的组织解决方案。 此表列出了每个解决方案对总体分数的贡献、该解决方案中实现和可能实现的分数，以及该解决方案中分组的可增加分数的剩余改进操作数。

可以通过两种方法从此屏幕采取措施：

1. 在预期解决方案行的"剩余操作" **列下，** 选择超链接编号。 你将看到改进操作屏幕的筛选视图，其中显示了该解决方案的未经测试的改进操作。

2. 在预期解决方案行的"打开解决方案" **列下，** 选择"打开 **"**。 你将在安全与合规中心Microsoft 365解决方案Office 365位置，你可以在这里采取建议的操作。

## <a name="assessments-page"></a>评估页面

评估页面列出了你 [为](compliance-manager-assessments.md) 组织设置的所有评估。 合规性分数分母由所有跟踪评估确定。 当你添加更多评估时，你将看到改进操作页上列出了更多改进操作，并且合规性分数分母增加。

页面 **顶部附近的** 已激活模板计数器显示在可供组织使用的模板总数中当前使用的活动评估模板的数量。 有关详细信息 [，请参阅模板](compliance-manager-templates.md#template-availability-and-licensing) 可用性和许可。

"评估"页汇总了有关每个评估的关键信息：

- **评估**：评估名称
- **状态**：
  - **完成** - 所有控件的状态为"已通过"，或至少有一个控件通过，其余控件处于"超出范围"
  - **不完整** – 至少一个控件的状态为"失败"
  - **无** - 所有控件均未经过测试
  - **进行** 中 - 改进操作具有任何其他状态，包括"正在进行"、"部分信用"或"未检测"
- **评估进度**：完成时完成的工作百分比，以成功测试的控制措施数为基准
- **改进操作**：满足控制措施实施要求已完成的操作数
- **Microsoft 操作**：满足 Microsoft 控件实现已完成操作的数量
- **组**：评估所属的组的名称
- **产品**：关联产品，Microsoft 365定义用于评估的产品
- **法规**：适用于评估的法规标准、策略或法律

### <a name="filtering-your-assessments-view"></a>筛选评估视图

筛选评估视图：

1. 选择 **评估** 列表左上角的"筛选"。
2. 在" **筛选器"** 飞出窗格中，检查所需的条件。
3. 选择" **应用"** 按钮。 筛选器窗格将关闭，并且你将看到已筛选视图。

您还可以通过从评估列表上方的"组"下拉菜单中选择分组类型，来修改视图以查看按组、产品或法规的评估。

### <a name="default-assessment"></a>默认评估

默认情况下，你将在评估页面上看到数据保护[](compliance-manager-assessments.md#data-protection-baseline-default-assessment)基线评估。 合规性管理器还提供了多个用于生成 [评估](compliance-manager-templates-list.md) 的预建模板。

## <a name="assessment-templates-page"></a>评估模板页

模板是用于在合规性管理器中创建评估的框架， 评估模板页面将显示模板和关键详细信息的列表。 该列表包括合规性管理器提供的模板，以及组织已修改或创建的任何模板。 你可以应用筛选器以根据认证、产品范围、国家/地区、行业和创建者来查找模板。

页面 **顶部附近的** 已激活模板计数器显示在可供组织使用的模板总数中当前使用的活动评估模板的数量。 有关详细信息 [，请参阅模板](compliance-manager-templates.md#template-availability-and-licensing) 可用性和许可。

Select a template from its row to bring up its details page， which contains a description of the template and further information about certification， scope， and controls details. 在此页中，可以选择相应的按钮来创建评估、将模板数据导出到Excel，或修改模板。

**了解更多信息**[：了解如何使用评估模板](compliance-manager-templates.md)。

## <a name="next-step"></a>后续步骤

通过设置评估 [自定义合规性管理器](compliance-manager-assessments.md)。
