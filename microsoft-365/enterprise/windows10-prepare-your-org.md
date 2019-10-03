---
title: 为 Windows 10 企业版准备组织
description: 提供了在 Microsoft 365 企业版中将 Windows 10 企业版部署到电脑上所需步骤的高级别指南。
keywords: Microsoft 365，Microsoft 365 企业版，Microsoft 365 文档，Windows 10 企业版，部署
author: JoeDavies-MSFT
localization_priority: Normal
ms.collection: M365-modern-desktop
audience: microsoft-business
ms.prod: microsoft-365-enterprise
ms.topic: article
ms.date: 06/01/2018
ms.author: josephd
ms.openlocfilehash: aafd629b4efcfa1307a25bf8e340236f183998b5
ms.sourcegitcommit: 8bcd76e5c8749a5670fbc3356957a089454c03d1
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 10/02/2019
ms.locfileid: "37370239"
---
# <a name="step-1-prepare-your-organization-for-windows-10-enterprise"></a>步骤1：为 Windows 10 企业版准备组织

*本文适用于 Microsoft 365 企业版的 E3 和 E5 版本*

![阶段 3：Windows 10 企业版](./media/deploy-foundation-infrastructure/win10enterprise_icon-small.png)

将设备升级到 Windows 10 企业版之前，请考虑以下事项：

- **必须添加和验证你的域** <br>
  使用 Microsoft 365 订阅时，将获取一个以 onmicrosoft.com 结尾的默认域名（例如，contoso.onmicrosoft.com）。 大多数组织更愿意使用自己拥有的一个或多个域，以便其电子邮件地址以其自己的域名结尾（如 username@contoso.com）。 若要使用你自己的域，你需要将其添加到 Microsoft 365 并验证你拥有它。 我们建议你立即添加和验证你的域，以便在你设置 Microsoft 365 服务（如电子邮件和 Skype for Business）时，他们随时可以转到。
- **此时不需要添加用户** <br>
  若要使用 Microsoft 365 服务或安装 Microsoft 365 产品，用户需要 Microsoft 365 中的帐户，并且他们需要产品许可证。 如何向 Microsoft 365 添加用户取决于用户数以及当前是否具有本地 Active Directory。 如果没有 Active Directory （或者您有 Active Directory 但不想将其同步到 Microsoft 365），则可以直接将用户添加到 Microsoft 365 并分配许可证（单独或批量）。 <br>
  如果您具有本地 Active Directory，则可以将[其与 microsoft 365 同步](identity-add-user-accounts.md#identity-sync)，以在 Azure AD 中创建用户帐户（Microsoft 365 使用的云目录）。 使用此方法，您可以为用户和用于管理对资源的权限的安全组（如 SharePoint Online 网站集或文档）创建帐户。 将 Active Directory 与 Microsoft 365 同步将不会向用户分配许可证。
- **你现在不需要许可用户** <br>
  在用户可以使用 Microsoft 365 服务或从 Microsoft 365 门户安装软件之前，他们需要产品许可证。 作为全局或用户管理管理员，您可以直接在 Microsoft 365 中单独或批量分配产品许可证。 您还可以使用[基于组的许可](identity-use-group-management.md#identity-group-license)，在将用户添加到特定组时自动分配许可证。 
- **您单独安装 Office 365 专业增强版** <br>
  获取 Microsoft 365 许可证不会自动在客户端计算机上安装 Office 365 专业增强版。 有关详细信息，请参阅[第4阶段： Office 365 专业增强版](office365proplus-infrastructure.md)。 

## <a name="set-windows-diagnostics-data-level"></a>设置 Windows 诊断数据级别

Microsoft 使用诊断数据，通过识别恶意软件趋势和其他威胁，帮助我们提高 Windows 和 Microsoft 服务的质量，从而帮助保持 Windows 设备的安全。 您必须确保在组织中的所有终结点上以最低级别的基本级别启用诊断服务。 *默认情况下，启用此服务并将其设置为增强级别。* 但是，最好检查并确保它们接收传感器数据。 通过策略设置级别将覆盖设备级别设置。 

**Windows 10 操作系统诊断数据级别**

您可以使用已在使用的管理工具（如组策略、MDM 或 Windows 预配）配置操作系统诊断数据设置。 您还可以使用注册表编辑器手动更改设置。 通过管理策略设置诊断数据级别将覆盖任何设备级别设置。

配置管理策略时，请使用下表中的相应值。

| Level | 收集的数据 | 值 |
|:--- |:--- |:--- |
| 安全性 | 仅安全数据。 | 0 |
| 基本 | 安全数据和基本系统和质量数据。 | 1 |
| 有所 | 安全数据、基本系统和质量数据以及增强的见解和高级可靠性数据。 | 双面 |
| 完整 | 安全数据、基本系统和质量数据、增强的真知灼见和高级可靠性数据以及完整的诊断数据。 | 第三章 |

您可以通过以下任一方法来启用诊断数据：

* **Microsoft Intune** -如果您计划使用 Intune 管理设备，则可以通过配置<a href="https://docs.microsoft.com/windows/client-management/mdm/policy-csp-system#system-allowtelemetry" target="blank">SystemAllowTelemetry</a>系统策略来创建配置策略来启用诊断数据。 有关设置配置策略的详细信息，请参阅[使用 Microsoft Intune 策略管理设备上的设置和功能](https://aka.ms/intuneconfigpolicies)。
* **注册表编辑器**-您可以使用注册表编辑器在组织中的每台设备上手动启用诊断数据。 或者，也可以编写脚本来编辑注册表。 如果管理策略已存在（如组策略或 MDM），它将覆盖此注册表设置。
* **组策略**-如果您不打算在 Intune 中注册设备，则可以使用组策略对象来设置您的组织的诊断数据级别。
* **命令提示符**-您可以将 Windows 10 诊断数据和服务设置为自动以命令提示符启动。 如果只在几个设备上测试服务，则此方法最适用。 使用此命令使服务自动启动时，将不会配置诊断数据级别。 如果您未使用管理工具配置诊断数据级别，则该服务将使用默认的 "增强" 级别运行。

请参阅在[组织中配置 windows 诊断数据](https://docs.microsoft.com/windows/configuration/configure-windows-diagnostic-data-in-your-organization)，了解有关 Windows 诊断数据的详细信息以及如何根据您选择的方法启用它。

作为临时检查点，请查看对应于此步骤的[退出条件](windows10-exit-criteria.md#crit-windows10-step1)。

## <a name="next-step"></a>后续步骤

|||
|:-------|:-----|
|![第 2 步](./media/stepnumbers/Step2.png)| [将适用于现有设备的 Windows 10 企业版部署为就地升级](windows10-deploy-inplaceupgrade.md) |






