---
title: 准备您的组织 Windows 10 Enterprise
description: 在 Microsoft 365 Enterprise 的一部分部署 Pc 上的 Windows 10 Enterprise 所需的步骤提供高级指导。
keywords: Microsoft 365 Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业部署
author: JoeDavies-MSFT
localization_priority: Normal
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: 21a4198c688e1865a029f18ff3ceeb2155d419e4
ms.sourcegitcommit: e491c4713115610cbe13d2fbd0d65e1a41c34d62
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 01/16/2019
ms.locfileid: "26865933"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>步骤 1： 准备您的组织 Windows 10 Enterprise

*本文适用于 Microsoft 365 企业版 E3 和 E5 版本*

![](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

之前升级到 Windows 10 Enterprise 设备，请考虑以下方面：

- **必须添加并验证您的域** <br>使用 Microsoft 365 订阅，您可以获取结束 onmicrosoft.com (例如，contoso.onmicrosoft.com) 在默认域的名称。大多数组织都喜欢使用一个或多个他们所拥有以便其电子邮件地址结尾自己的域名 （如 username@contoso.com) 中的域。若要使用您自己的域，您需要将其添加到 Microsoft 365 并确认您拥有。我们建议您将添加并立即验证您的域，以便它们准备好转每当您安装了 Microsoft 365 服务，如电子邮件和 Skype for Business。
- **您无需在这里添加用户** <br>若要使用 Microsoft 365 服务或安装 Microsoft 365 产品，用户需要 Microsoft 365 中的帐户和所需产品许可证。如何将用户添加到 Microsoft 365 取决于用户和当前具有 Active Directory 本地是否的数量。如果您没有 Active Directory （或具有 Active Directory 但不希望同步到 Microsoft 365），您可以直接向 Microsoft 365 添加用户并单独或批量分配许可证。<br>如果您有 Active Directory 部署，您可以[将其与 Microsoft 365 同步](identity-azure-ad-connect-health.md)在 Azure AD，由 Microsoft 365 云目录中创建用户帐户。使用此方法时，您可以创建用于管理 （如 SharePoint Online 网站集或文档） 的资源的权限的帐户的用户和安全组。将您的 Active Directory 与 Microsoft 365 同步时，不会将许可证分配给用户。
- **此时您无需对许可用户** <br>用户可以使用 Microsoft 365 服务或从 Microsoft 365 门户安装软件之前，需产品许可证。作为全局或用户管理管理员，您可以单独或批量直接分配 Microsoft 365 中的产品许可证。您可以使用[基于组的授权](identity-group-based-licensing.md)用户添加到特定组时自动分配许可证。 
- **您单独安装 Office 365 ProPlus** <br>获取 Microsoft 365 许可证不自动安装 Office 365 ProPlus 客户端计算机上。请参阅[第 4 阶段： Office 365 ProPlus](office365proplus-infrastructure.md)的详细信息。 

## <a name="set-windows-diagnostics-data-level"></a>设置 Windows 诊断数据级别

Microsoft 使用诊断数据来帮助保持的 Windows 设备安全通过识别恶意软件趋势和其他威胁和帮助我们改善 Windows 和 Microsoft 服务的质量。您必须确保最低级别的基本您的组织中的所有终结点上启用诊断服务。*默认情况下，此服务并将其设置为增强型级别。* 但是，最好以检查，并确保它们接收传感器数据。设置通过策略级别将覆盖设备级设置。 

**Windows 10 操作系统诊断数据级别**

您可以配置操作系统诊断数据设置使用您已使用，如组策略、 MDM，或 Windows 设置的管理工具。您可以手动更改设置使用注册表编辑器。设置您的诊断数据级别通过管理策略将覆盖任何设备级别的设置。

当您配置的管理策略下表中使用适当的值。

| 级别 | 数据收集 | 值 |
|:--- |:--- |:--- |
| 安全性 | 仅安全数据。 | 0 |
| Basic | 安全数据基本系统和质量数据。 | 1 |
| 增强 | 安全数据、 基本系统和质量数据和增强的见解和高级的可靠性数据。 | 2 |
| 完整 | 安全数据、 基本系统和质量数据、 增强的见解和高级的可靠性数据和完整的诊断数据。 | 3 |

您可以通过这些方法启用诊断数据：

* **Microsoft Intune** -如果您打算使用 Intune 管理您的设备，您可以创建配置策略，以通过配置<a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a>系统策略来启用诊断数据。配置策略设置的详细信息，请参阅[管理设置和您与 Microsoft Intune 策略的设备上的功能](https://aka.ms/intuneconfigpolicies)。
* **注册表编辑器**-您可以使用注册表编辑器手动启用您的组织中的每个设备上的诊断数据。另外，您可以编写脚本以编辑注册表。如果管理策略已存在，如组策略或 MDM，它将覆盖此注册表设置。
* **组策略**-如果您不打算注册 Intune 中的设备，可以使用组策略对象，设置您的组织的诊断数据级别。
* **命令提示符处**-您可以设置 Windows 10 诊断数据和服务自动启动命令提示符下使用。如果您要测试仅几个设备上的服务最佳此方法。启用服务为自动启动，使用此命令将不配置的诊断数据级别。如果您未配置使用管理工具的诊断数据级别，则服务增强级别都将使用默认操作。

请参阅[您的组织中配置 Windows 诊断数据](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization)以了解更多有关 Windows 诊断数据和如何启用它根据您选择的方法。

作为临时检查点，请查看对应于此步骤的[退出条件](windows10-exit-criteria.md#crit-windows10-step1)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![](./media/stepnumbers/Step2.png)| [为就地升级的现有设备部署 Windows 10 Enterprise](windows10-deploy-inplaceupgrade.md) |






