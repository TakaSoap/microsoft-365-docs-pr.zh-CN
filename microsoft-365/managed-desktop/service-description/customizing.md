---
title: 服务计划的例外情况
description: 如何请求标准服务计划的例外
keywords: Microsoft 托管桌面, Microsoft 365, 服务, 文档
ms.service: m365-md
author: tiaraquan
ms.localizationpriority: medium
ms.collection: M365-modern-desktop
ms.author: tiaraquan
manager: dougeby
ms.topic: article
ms.openlocfilehash: 8069a899b9992a0e8b941b6ac53cd2f230a6174a
ms.sourcegitcommit: 559df2c86a7822463ce0597140537bab260c746a
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 02/15/2022
ms.locfileid: "62825175"
---
# <a name="exceptions-to-the-service-plan"></a>服务计划的例外情况

Microsoft 托管桌面提供了一个精心设计的设备列表、标准设备[](device-policies.md)设置、应用程序要求和某些可配置设置[](../working-with-managed-desktop/config-setting-overview.md)，所有这些设置都旨在为用户提供安全、高效且令人愉悦的体验。

最好始终使用所提供的服务。 但是，我们意识到服务的一些详细信息可能并不完全符合贵组织的需求。 如果您觉得需要通过某种方式更改服务，则按照以下过程请求这些更改非常重要。

## <a name="types-of-exceptions"></a>异常类型

例外情况是，对基本配置进行Microsoft 托管桌面更改。 示例范围从 USB 端口配置到部署新设备驱动程序。 我们按如下所示对各种例外进行分组：

| 异常类型 | 说明 |
| ----- | ----- |
| 工作效率软件 | 用户所需的前台软件，受应用程序 [要求限制](mmd-app-requirements.md)。 |
| VPN &代理 | 用于保护、监视或更改设备或网络行为的软件。 |
| 数字体验监视 | 用于跟踪用户设备上要报告给 IT 的数据的软件。 |
| 硬件或软件驱动程序 | 受应用程序要求限制的设备 [驱动程序](mmd-app-requirements.md)。 |
| 策略 | Windows 10托管Microsoft 365 企业应用版或设置。 |
| 设备 | 不在设备列表中的Microsoft 托管桌面[设备](device-list.md)。 |
| 其他 | 任何其他区域未涵盖的内容。 |

## <a name="request-an-exception"></a>请求异常

通过管理门户Microsoft 托管桌面更改请求提交请求。 请务必包含以下详细信息：

| 更改请求详细信息 | Description |
| ----- | ----- |
| 免除类型 | 它是哪种类型的异常？  (上表[) ](#types-of-exceptions) |
| 要求 | 异常的特定业务需求是什么？ |
| 建议 | 你的业务正在请求哪种解决方案？ |
| 日程表 | 您希望此异常持续多久？ |

## <a name="how-we-assess-an-exception-request"></a>如何评估异常请求

查看异常请求时，我们将按以下顺序评估这些因素：

1. 某些要部署到Microsoft 托管桌面的应用程序和策略不会更新。 您的请求不得影响这些应用程序和策略。 有关详细信息，请参阅设备 [配置](device-policies.md)。
2. 用户完成工作所需的受限工作效率软件可能会获得批准。
3. 如果我们可以使用 Microsoft 技术满足你的要求，我们很可能会批准你请求的异常迁移期为 3 到 12 个月。 迁移时间取决于项目的范围。
4. 如果我们使用 Microsoft 技术无法满足您的要求，我们很可能会批准你的请求，除非它违反了关键条件之 [一](#key-conditions)。  

这些原则可确保Microsoft 托管桌面模板的偏差时始终满足您的需求。

## <a name="key-conditions"></a>关键条件

我们查看例外以确保它们不会违反以下任何条件：

- 异常不得对系统安全性产生不利影响。
- 维护异常不得使运行或支持产生Microsoft 托管桌面成本。
- 异常不得影响系统稳定性，例如，导致内核模式崩溃或挂起。
- 更改不得限制我们运营该服务或与核心技术Microsoft 托管桌面冲突。
- 例外情况不能涉及个性化用户体验，例如更改"开始"菜单任务栏。

这些条件将来可能会更改。 如果我们进行此类更改，我们将在这些条件生效之前提前 30 天发出通知。  如果Microsoft 托管桌面提供满足已批准例外的替代方法，Microsoft 托管桌面通知客户Microsoft 托管桌面它支持异常的方式。

## <a name="revoking-approval-for-an-exception"></a>撤销对异常的审批

批准和部署请求的异常后，我们可能会发现违反最初批准更改时未明显的关键条件的问题。 在这种情况下，我们可能需要撤销对异常的批准。

如果必须撤销对例外的审批，我们将使用管理门户Microsoft 托管桌面通知。 从我们第一次通知你开始，你有 90 天的时间来删除例外，然后例外的设备不再受Microsoft 托管桌面限制。

我们将根据严格的时间线向您发送多个通知。 但是，严重事件或威胁可能要求我们更改有关异常的决策的日程表。 未经你的 *同意，* 我们不会删除例外。 但是，任何具有已撤销例外的设备将不再受到我们的服务级别协议的约束。 下表是我们将向您发送的通知时间线：

| 通知类型 | 说明 |
| ----- | ----- |
| 第一次通知 | 我们将在第一次通知中提供以下信息： <ul><li>有关我们撤销它的原因的信息。</li><li>我们建议你采取的操作。</li><li>这些操作的期限。</li><Li>若要对决定进行裁定，请遵循的步骤。</li></ul> <br>此通知在必须从所有设备中删除异常前提前 90 天发生。 |
| 第二次 (30 天后)  | 我们提供了第二次通知，其中包括第一次通知中提供的相同信息。 |
| 第三次 (第一次通知后 60)  | 我们提供了第三次通知，其中包括第一次通知中提供的相同信息。 |
| 最终通知 (90 天截止时间前的一周)  | 我们提供了第四个通知，其中包括第一个通知中提供的相同信息。 |
| 首次通知后 90 天| Microsoft 托管桌面服务级别协议不再适用于具有已撤销异常的任何设备。 你随时都可以对决定进行质询，并提供要考虑的其他信息，包括升级、配置更改或软件更改。 |
