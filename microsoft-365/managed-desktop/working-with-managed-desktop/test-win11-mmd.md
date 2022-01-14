---
title: 使用 Microsoft 托管桌面预览和测试 Windows 11
description: 如何获取Windows 11环境中使用
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.openlocfilehash: 7c5526e532f14fc00ed52a6d260c017d0a019bae
ms.sourcegitcommit: a6651b841f111ea2776cab88bf2c80f805fa8e09
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/13/2022
ms.locfileid: "62035458"
---
# <a name="preview-and-test-windows-11-with-microsoft-managed-desktop"></a>使用 Microsoft 托管桌面预览和测试 Windows 11

 如何注册并参与Windows 11环境中测试兼容性Microsoft 托管桌面计划。 有关通常Windows 11和Microsoft 托管桌面，请参阅Windows 11[和Microsoft 托管桌面。](../intro/win11-overview.md) 

## <a name="add-devices-to-the-windows-11-test-group"></a>向测试组Windows 11设备

根据请求，我们将创建适用于 (**工作区 - Windows 11** 预发布测试) 设备组，以测试Windows 11。 该组中的设备在可用时Windows 11新的Microsoft 托管桌面配置，并监视其可靠性问题。

你可以选择任何现有或新设备进行 Windows 11 测试，但由于预发布版本中缺陷或兼容性问题的风险增加，不应在此组中注册存储设备。 分配至此组时，将删除以前的设备组分配。

若要在预发布测试组中注册设备，请执行以下操作：

1. 与服务工程团队Microsoft 托管桌面新服务请求。
2. 对字段使用这些值：
    - 标题：Windows 11兼容性注册
    - 请求类型：更改请求
    - 类别：设备
    - 子类别：部署组分配
3. 在"说明"字段中，列出要用于测试Windows 11序列号。 请注意，指定的设备（如果有）尚未部署在 Microsoft 托管桌面 租户中。

## <a name="prioritize-applications-to-submit-to-test-base"></a>确定要提交到测试库的应用程序的优先级

业务关键应用程序是关闭环境中进行更多验证Windows 11候选。 我们可以帮助你根据使用情况和可靠性数据Windows 11应用优先进行测试。 若要请求我们的建议，请按照以下步骤操作：

1. 与服务工程团队Microsoft 托管桌面新服务请求。 如果你需要更多有关如何提交请求的信息，请参阅 [管理员支持](admin-support.md)。
2. 对字段使用这些值：
    - 标题：Windows 11测试基准候选项
    - 请求类型：信息请求
    - 类别：应用
    - 子类别：其他

## <a name="report-issues"></a>报告问题

如果你遇到Windows 11线或应用兼容性问题Microsoft 365，请将其报告给我们进行调查和修正。 若要报告问题，请按照以下步骤操作：

1. 与服务工程团队Microsoft 托管桌面新服务请求。
2. 对字段使用这些值：
    - 标题：Windows 11兼容性测试
    - 请求类型：事件
    - 类别：设备
    - 子类别：Windows/更新
3. 描述该行为以及它在生产环境中对业务的影响。

Microsoft 托管桌面根据对工作效率的影响，对预发布版本问题进行分类和处理。 虽然我们的服务说明未涵盖预发布版本的问题，但我们会与客户管理员协商，以确保在任意给定租户中开始迁移之前解决阻止用户工作效率的问题。
