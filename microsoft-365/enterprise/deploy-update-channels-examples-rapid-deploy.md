---
title: 最新版本的广泛部署示例
author: kelleyvice-msft
f1.keywords:
- NOCSH
ms.author: kvice
manager: laurawi
ms.date: 07/21/2020
audience: ITPro
ms.topic: article
ms.service: o365-solutions
ms.localizationpriority: medium
ms.collection:
- Strat_O365_Enterprise
- M365-subscription-management
ms.custom: ''
description: 部署最新版本的组织如何使用 Windows 10 和 Microsoft 365 应用的频道。
ms.openlocfilehash: 6b0226a226742a89dc65ca0d32792db03c77e465
ms.sourcegitcommit: d4b867e37bf741528ded7fb289e4f6847228d2c5
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/06/2021
ms.locfileid: "60193083"
---
# <a name="example-of-broad-deployment-for-the-latest-releases"></a>最新版本的广泛部署示例

此频道配置示例适用于使用最新版本的快速部署来满足这些业务优先级的组织：

- 使用 Microsoft 应用和服务来确保业务连续性。
- 使用 Microsoft 的最新功能和修补程序，最大限度地提高设备、服务和数据安全性。
- 使用 Microsoft 的最新功能最大限度地提高用户的工作效率。

这些目标转化为IT任务，即在快速生产部署和早期审查之间找到平衡，并在广泛部署之前与用户和设备的代表性子集一起进行功能验证。

我们的示例组织在欧洲、非洲、亚洲和美洲各地的大楼中有5000名员工。 组织中 70% 的员工使用 Microsoft 365 E3，其余的员工则使用 Microsoft 365 E5。

>[!Note]
>此示例旨在向你展示如何使用部署阶段和组，它们可用于多种类型和规模的组织。
>

此组织的 IT 基础结构： 

- 很大程度上是同质的，Windows、Microsoft 365 应用版和 Microsoft 云服务占安装基础的60%。 经过多年的努力简化 IT 基础设施，一些旧版系统仍然存在。
- 由经验丰富的员工负责维护，其任务是在发布版本中遵循 Microsoft 的做法，保持用户及其设备的高效性和安全性。

## <a name="deployment-and-update-stages"></a>部署和更新阶段

根据最新版本的快速部署目标，此示例组织使用两步部署过程。

1. **使用预览或试点部署：** 与早期采用者、IT 人员、拥有代表配置的用户，和培训人员一起验证和迭代。 

   在新功能推出到组织的其余部分之前，早期采用者、IT 职员、和拥有代表配置的用户可与其他应用和设备验证功能。

   更改管理员在大范围推出新功能前，会提前了解新功能，并可以计划消息传递和推出。

   在大范围推出前，培训人员可规划新内部课程或为新功能更新现有课程。

2. **生产部署** 按区域、部门或其他部署方法向所有剩余用户推出。

## <a name="deployment-configuration-for-windows-10"></a>为 Windows 10 部署配置

总体目标是在一组代表用户验证发布预览频道更改后，广泛部署最新的半年频道版本。

了解更多关于 Windows 10 部署方法和策略的信息，请参阅[Windows 10 部署](/windows/deployment/)。

| 阶段 | 频道 | 部署组 |
|:-------|:-------|:-----|
| 试点 |  **发布预览频道**  <ul><li>目的：将功能更新部署到 IT 人员和早期采用者，用于验证代表设备和配置（语言、第三方应用）。 </li><li> 状态：对商业客户完全兼容和支持，不会与支持的协议对立。 </li></ul> | **Win10ReleasePreviewChannel**（示例名称） <br><br> 成员是包含以下内容的组： <ul><li> 跨部门和位置的 Windows 应用爱好者 </li><li> 配置需要验证的职员 </li><li> IT 管理员和 IT 部署职员 </li><li> 更换经理 </li><li> 内部培训人员 </li></ul> |
| 生产 |  **半年频道**  <ul><li>目的：将最新功能更新广泛部署到组织的其他部分。 </li><li> 状态：完全兼容和支持。 </li></ul> | **Win10SemiAnnualChannel**（示例名称） <br><br> 成员是不在 Win10ReleasePreviewChannel 组的所有用户。 |
||||

此组织采用的最佳做法是，采用与部署半年频道版本（如 Windows 更新网站或 Windows Server Update Services）相同的方式部署发布预览频道有效负载，并且对两个频道更新采用相同的策略。

正在进行的更新进程：

1. 发布预览频道更改将部署到 Win10ReleasePreviewChannel （示例名称）部署组。
2. Win10ReleasePreviewChannel 组成员确认发布预览频道更改对IT部署人员有用，他们可以向 Microsoft 提供反馈，并等待下一个发布预览频道更改进行其他验证。
3. 半年频道功能更改将部署到 Win10SemiAnnualChannel 部署组。 

>[!Note]
>虽然半年频道是推荐频道，但是你的IT部门应利用管理工具决定何时在他们的内部部署并推出最新的半年频道。
>

## <a name="deployment-configuration-for-microsoft-365-apps"></a>为 Microsoft 365 应用版部署配置

总体目标是一组代表用户验证当前频道（预览版）更改后，广泛部署最新的当前频道版本。

了解更多 Microsoft 365 应用版部署方法和策略的信息，请参阅[Microsoft 365 应用版部署](/deployoffice/plan-office-365-proplus)。 

| 阶段 | 频道 | 部署组 |
|:-------|:-------|:-----|
| 试点 |  **当前频道（预览）** <ul><li> 目的：{让组中的代表性的用户一窥 Microsoft 365 应用版的新功能} 在使用当前频道（预览）用户测试并进入生产状态后立即部署功能更新。 </li><li> 状态：完全兼容和支持。</li><li> 频率：每月更新 2-3 次。 </li></ul> | **AppsCurrentChannelPreview**（示例名称） <br><br> 成员是包含以下内容的组： <ul><li> 跨部门和位置的 Office 应用爱好者 </li><li> 配置需要验证的职员 </li><li> IT 管理员和 IT 部署职员 </li><li> 更换经理 </li><li> 内部培训人员 </li></ul>|
| 生产 | **当前频道** <ul><li> 目的：将最新功能更新广泛部署到组织的其他部分。 </li><li> 状态：完全兼容和支持。 </li></ul> |  **AppsCurrentChannel** （示例名称） <br><br> 成员是所有不在 AppsCurrentChannelPreview 组的用户。 |
|||

正在进行的更新进程：

1. 当前频道 (预览) 更改将部署到 AppsCurrentChannelPreview 部署组。
2. AppsCurrentChannelPreview 组成员确认当前频道（预览版）的更改对IT部署人员有用，他们可以向 Microsoft 提供反馈，并等待下一个当前频道（预览版）版本进行其他验证。
3. 当前通道更改将部署到 AppsCurrentChannel 部署组。 

## <a name="visual-summary"></a>视觉摘要

这些是此示例组织使用的产品、频道和部署组。 

![用于广泛部署最新版本的部署组。](../media/deploy-update-channels-examples-rapid-deploy/group-summary.png)

## <a name="see-also"></a>另请参阅

[部署和更新频道示例配置](deploy-update-channels-examples.md)

[Microsoft 365 企业版概述](microsoft-365-overview.md)

[测试实验室指南](m365-enterprise-test-lab-guides.md)