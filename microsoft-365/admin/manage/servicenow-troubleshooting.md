---
title: 疑难解答 Microsoft 365 支持与 ServiceNow 集成
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
ms.localizationpriority: medium
ms.collection:
- M365-subscription-management
- Adm_TOC
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow 的作用域认证应用程序安装和配置指南。
ms.openlocfilehash: bac3981b728ac997839e7ac99a9411a8da244add
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63324937"
---
# <a name="troubleshooting-microsoft-365-support-integration-with-servicenow"></a>疑难解答 Microsoft 365 支持与 ServiceNow 集成

| \#  | 问题  | 诊断操作     |
|-----|--------------------------------|----------------------|
| 1   | 无法查看"**Microsoft 365支持**"选项卡                                                                                                                                                                                    | 使用筛选器  &gt; xmiomsm365assit \_\_验证当前视图和"系统日志\_全部"                        |
| 2   | 选择 **Microsoft 推荐的解决方案** ，但收到错误"Please contact your ServiceNow admin and ask them to complete the setup steps for the app."                                                                      | 检查表单顶部的错误消息&gt;和使用筛选器 xmiomsm365assit \_\_\_的系统日志全部     |
| 3   | 选择 **Microsoft 推荐的解决方案** ，但收到错误"Please contact your ServiceNow admin and ask them to complete the final set up step for the app."                                                                | 检查表单顶部的错误消息&gt;和使用筛选器 xmiomsm365assit \_\_\_的系统日志全部     |
| 4   | 在搜索框中键入问题并选择 **Microsoft 建议** 的解决方案，但收到错误"请联系你的 ServiceNow 管理员，并要求他们完成应用的设置步骤。"                                   | 检查表单顶部的错误消息&gt;和使用筛选器 xmiomsm365assit \_\_\_的系统日志全部     |
| 5   | 在搜索框中键入问题并选择 **Microsoft 建议** 的解决方案，但收到错误"请联系你的 ServiceNow 管理员，并要求他们完成应用的最终设置步骤。"                                 | 检查表单顶部的错误消息&gt;和使用筛选器 xmiomsm365assit \_\_\_的系统日志全部     |
| 6    | 选择 **"联系 Microsoft 支持** 人员"，但收到错误"Please contact your ServiceNow admin and ask them to complete the setup steps for the app."                                                                       | 检查表单顶部的错误消息&gt;和使用筛选器 xmiomsm365assit \_\_\_的系统日志全部     |
| 7    | 选择 **"联系 Microsoft 支持** 人员"，但收到错误"请联系你的 ServiceNow 管理员，并要求他们完成应用的最终设置步骤"。                                                                 | 检查表单顶部的错误消息&gt;和使用筛选器 xmiomsm365assit \_\_\_的系统日志全部     |
| 8    | 选择 **"联系 Microsoft 支持** 人员"，但收到错误"{EmailAddress} 不是有效的Microsoft 365帐户。 您需要Microsoft 365管理员权限才能打开服务请求。 在应用中，链接管理员帐户。" | 检查表单顶部的错误消息&gt;和使用筛选器 xmiomsm365assit \_\_\_的系统日志全部     |
| 9    | 选择 **Microsoft 建议的解决方案** ，但没有任何显示                                                                                                                                                            | 检查 **系统日志 – 出站 HTTP 日志** login.microsoftonline.com 筛选器 connector.rave.microsoft.com |
| 10   | 选择 **Microsoft 推荐的解决方案** ，但收到错误"请联系应用支持人员"。                                                                                                                                     | 检查表单顶部的错误消息&gt;和使用筛选器 xmiomsm365assit \_\_\_的系统日志全部     |
| 11  | 在搜索框中键入问题，然后选择 **Microsoft 建议的解决方案** ，但不显示任何内容                                                                                                                             | 检查 **系统日志 – 出站 HTTP 日志** login.microsoftonline.com 筛选器 connector.rave.microsoft.com |
| 12   | 在搜索框中键入问题，然后选择 **Microsoft 建议的解决方案** ，但收到错误"请联系应用支持人员"。                                                                                                      | 检查表单顶部的错误消息&gt;和使用筛选器 xmiomsm365assit \_\_\_的系统日志全部     |
| 13  | 用户选择" **联系 Microsoft 支持** 人员"，但不执行任何操作                                                                                                                                                            | 检查 **系统日志 – 出站 HTTP 日志** login.microsoftonline.com 筛选器 connector.rave.microsoft.com |
| 14   | 重新打开事件后看不到 Microsoft 建议的解决方案                                                                                                                                                      | 使用 **筛选器** &gt; xmiomsm365assit \_\_\_检查系统日志全部                                              |
| 15   | 重新打开已转移到 Microsoft 支持人员的事件时看不到 Microsoft 案例                                                                                                                            | 使用 **筛选器** &gt; xmiomsm365assit \_\_\_检查系统日志全部                                              |
| 16  | 无法保存票证详细信息，收到错误"无法保存票证详细信息。 请联系应用支持人员。"                                                                                                                          | 检查表单顶部的错误消息                                                                            |
