---
title: VPN 环境中 Stream 和实时事件的特殊注意事项
ms.author: kvice
author: kelleyvice-msft
manager: scotv
ms.date: 3/3/2022
audience: Admin
ms.topic: conceptual
ms.service: o365-administration
ms.localizationpriority: medium
search.appverid:
- MET150
ms.collection:
- Ent_O365
- Strat_O365_Enterprise
- remotework
f1.keywords:
- NOCSH
description: VPN 环境中 Stream 和实时事件的特殊注意事项
ms.openlocfilehash: eb2e57b844f06bc3b1e005aa1095794b176bba94
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: zh-CN
ms.lasthandoff: 03/08/2022
ms.locfileid: "63330814"
---
# <a name="special-considerations-for-stream-and-live-events-in-vpn-environments"></a>VPN 环境中 Stream 和实时事件的特殊注意事项

>[!NOTE]
>本文是一组文章的一部分，这些文章Microsoft 365远程用户的优化。

>- 有关使用 VPN 拆分隧道优化远程Microsoft 365连接的概述，请参阅[概述：适用于远程用户的 VPN 拆分Microsoft 365](microsoft-365-vpn-split-tunnel.md)。
>- 有关实现 VPN 拆分隧道的详细指南，请参阅[实现 VPN 拆分隧道Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)。
>- 有关 VPN 拆分隧道方案的详细列表，请参阅公用 VPN 拆分隧道[方案Microsoft 365](microsoft-365-vpn-common-scenarios.md)。
>- 有关在 VPN 拆分隧道Teams保护媒体流量的指南，请参阅 [Securing Teams media traffic for VPN split tunneling](microsoft-365-vpn-securing-teams.md)。
>- 有关为中国用户Microsoft 365全球租户性能的信息，请参阅Microsoft 365[中国用户的性能优化](microsoft-365-networking-china.md)。

Microsoft 365 实时事件流量 (这包括 Teams 制作的活动参与者，以及使用外部编码器通过 Teams、Stream 或 Yammer) 生成的事件，按需流流量当前在服务的 [URL/IP](urls-and-ip-address-ranges.md) 列表中被分类为默认与优化。  这些终结点被归类为 **默认** 终结点，因为它们托管在其他服务也可能使用的 CDN 上。 客户通常倾向于代理此类流量，并应用通常在此类终结点上执行的任何安全元素。

许多客户都要求输入将用户直接从本地 Internet 连接连接到 Stream/Live 事件所需的 URL/IP 数据，而不是通过 VPN 基础结构路由高容量和延迟敏感的流量。 通常，如果没有专用命名空间和终结点的准确 IP 信息（未为分类为"默认"的 Microsoft 365提供此信息，则不可能 **实现此操作**。

使用以下步骤为使用强制隧道 VPN 的客户端直接连接 Stream/Live Events 服务。 此解决方案旨在为客户提供一个选项，以避免由于在家工作方案导致网络流量较高时通过 VPN 路由实时事件流量。 如果可能，建议通过检查代理访问服务。

>[!NOTE]
>使用此解决方案时，可能存在未解析为提供的 IP 地址并因此遍历 VPN 的服务元素，但应大量流量（如流式数据）。 此卸载可能会捕获 Live 事件/Stream 范围之外的其他元素，但应限制这些元素，因为它们在直接传输之前必须满足 _FQDN 和_ IP 匹配。

>[!IMPORTANT]
>建议客户通过实时事件的性能提升权衡发送更多流量绕过 VPN 的风险。

若要为 Live 事件和 Stream Teams强制隧道例外，应应用以下步骤：

## <a name="1-configure-external-dns-resolution"></a>1. 配置外部 DNS 解析

客户端需要外部的递归 DNS 解析可用，以便以下主机名可以解析为 IP 地址。

- \*.azureedge.net
- \*.media.azure.net
- \*.bmc.cdn.office.net

**\*.azureedge.net** 用于 Stream 事件 ([配置 Microsoft Stream 中的实时流式传输的编码器 - Microsoft Stream |Microsoft Docs](/stream/live-encoder-setup)) 。

**\*.media.azure.net** 和 **\*.bmc.cdn.office.net** 用于 Teams 生成的实时事件 (快速启动事件，RTMP-In 支持的事件 [路线图 ID 84960]) 从 Teams 客户端计划。

 其中某些终结点与 Stream/Live 事件之外的其他元素共享，建议不要仅使用这些 FQDN 配置 VPN 卸载，即使从技术上说，VPN 解决方案 (例如它适用于 FQDN 而非 IP) 。

VPN 配置中不需要 FQDN，它们完全用于 PAC 文件与 IP 以直接发送相关流量。

## <a name="2-implement-pac-file-changes-where-required"></a>2. 在需要时 (PAC 文件) 

对于在 VPN 上利用 PAC 文件通过代理路由流量的组织，这通常使用 FQDN 实现。 但是，对于 Stream/Live **\*** 事件，提供的主机名包含通配符（如 .azureedge.net）也包含无法提供完整 IP 列表的其他元素。 因此，如果仅根据 DNS 通配符匹配直接发送请求，则到这些终结点的流量将被阻止，因为本文稍后的步骤 [3](#3-configure-routing-on-the-vpn-to-enable-direct-egress) 中没有通过它的直接路径的路由。

为了解决此问题，我们可以提供以下 IP，并结合使用它们和示例 PAC 文件中主机名，如步骤 [1 中所述](#1-configure-external-dns-resolution)。 PAC 文件检查 URL 是否与用于 Stream/Live 事件的 URL 匹配，如果匹配，则检查从 DNS 查找返回的 IP 是否与为服务提供的 IP 匹配。 如果 _两_ 者匹配，则直接路由流量。 如果 FQDN/IP (中的任一元素) 不匹配，则流量将发送到代理。 因此，配置可确保解析为 IP 和已定义命名空间作用域之外的 IP 的一切内容都将正常通过 VPN 遍历代理。

### <a name="gathering-the-current-lists-of-cdn-endpoints"></a>收集当前终结点CDN列表

实时事件使用多个CDN提供商流式传输给客户，以提供最佳覆盖范围、质量和复原能力。 目前，同时Azure CDN Microsoft 和 Verizon 进行下载。 随着时间的推移，可能会由于区域可用性等情况而更改此情况。 本文是让你能够及时了解 IP 范围最新信息的来源。

For Azure CDN from Microsoft， you can download the list [from Download Azure IP Ranges and Service Tags – Public Cloud from Official Microsoft Download Center](https://www.microsoft.com/download/details.aspx?id=56519) - you will need to look specifically for the service tag *AzureFrontdoor.Frontend* in the JSON;*addressPrefixes* 将显示 IPv4/IPv6 子网。 随着时间的推移，IP 可能会更改，但服务标记列表始终在被使用之前更新。

For Azure CDN from Verizon (Edgecast) you can find an exhaustive list using [https://docs.microsoft.com/rest/api/cdn/edge-nodes/list](/rest/api/cdn/edge-nodes/list) (click **Try It** ) - you will need to look specifically for the **高级版\_Verizon** section. 请注意，此 API 显示源和 (的所有边缘) 。 目前，API 没有用于区分源和任意播的机制。

若要在 PAC 文件中实现此操作，可以使用以下示例将 Microsoft 365 优化流量直接发送到 (推荐最佳做法) 通过 FQDN，关键流/实时事件流量通过 FQDN 和返回的 IP 地址的组合直接发送。 需要将 _占位符名称 Contoso_ 编辑为特定租户的名称， _其中 contoso_ 来自 contoso.onmicrosoft.com

#### <a name="example-pac-file"></a>示例 PAC 文件

下面是如何生成 PAC 文件的示例：

1. 将下面的脚本另存为本地 _Get-TLEPacFile.ps1。_
1. 转到 [Verizon URL](/rest/api/cdn/edge-nodes/list#code-try-0) 并下载生成的 JSON (将其复制到 cdnedgenodes.json) 
1. 将文件放入与脚本相同的文件夹中。
1. 在 PowerShell 窗口中，运行以下命令。 如果需要 SPO URL，请为其他内容更改租户名称。 这是类型 2，因此"优化"和"允许 (类型 1 为"仅) "。

   ```powershell
   .\Get-TLEPacFile.ps1 -Instance Worldwide -Type 2 -TenantName <contoso> -CdnEdgeNodesFilePath .\cdnedgenodes.json -FilePath TLE.pac
   ```

5. TLE.pac 文件将包含 IPv4/IPv6 (的所有命名空间和 IP) 。

##### <a name="get-tlepacfileps1"></a>Get-TLEPacFile.ps1

```powershell
# Copyright (c) Microsoft Corporation. All rights reserved.
# Licensed under the MIT License.

<#PSScriptInfo

.VERSION 1.0.4

.AUTHOR Microsoft Corporation

.GUID 7f692977-e76c-4582-97d5-9989850a2529

.COMPANYNAME Microsoft

.COPYRIGHT
Copyright (c) Microsoft Corporation. All rights reserved.
Licensed under the MIT License.

.TAGS PAC Microsoft Microsoft365 365

.LICENSEURI

.PROJECTURI http://aka.ms/ipurlws

.ICONURI

.EXTERNALMODULEDEPENDENCIES

.REQUIREDSCRIPTS

.EXTERNALSCRIPTDEPENDENCIES

.RELEASENOTES

#>

<#

.SYNOPSIS

Create a PAC file for Microsoft 365 prioritized connectivity

.DESCRIPTION

This script will access updated information to create a PAC file to prioritize Microsoft 365 Urls for
better access to the service. This script will allow you to create different types of files depending
on how traffic needs to be prioritized.

.PARAMETER Instance

The service instance inside Microsoft 365.

.PARAMETER ClientRequestId

The client request id to connect to the web service to query up to date Urls.

.PARAMETER DirectProxySettings

The direct proxy settings for priority traffic.

.PARAMETER DefaultProxySettings

The default proxy settings for non priority traffic.

.PARAMETER Type

The type of prioritization to give. Valid values are 1 and 2, which are 2 different modes of operation.
Type 1 will send Optimize traffic to the direct route. Type 2 will send Optimize and Allow traffic to
the direct route.

.PARAMETER Lowercase

Flag this to include lowercase transformation into the PAC file for the host name matching.

.PARAMETER TenantName

The tenant name to replace wildcard Urls in the webservice.

.PARAMETER ServiceAreas

The service areas to filter endpoints by in the webservice.

.PARAMETER FilePath

The file to print the content to.

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type1.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance China -Type 2 -DefaultProxySettings "PROXY 4.4.4.4:70" -FilePath type2.pac

.EXAMPLE

Get-TLEPacFile.ps1 -ClientRequestId b10c5ed1-bad1-445f-b386-b919946339a7 -Instance WorldWide -Lowercase -TenantName tenantName -ServiceAreas Sharepoint

#>

#Requires -Version 2

[CmdletBinding(SupportsShouldProcess=$True)]
Param (
    [Parameter(Mandatory = $false)]
    [ValidateSet('Worldwide', 'Germany', 'China', 'USGovDoD', 'USGovGCCHigh')]
    [String] $Instance = "Worldwide",

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [guid] $ClientRequestId = [Guid]::NewGuid().Guid,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DirectProxySettings = 'DIRECT',

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [String] $DefaultProxySettings = 'PROXY 10.10.10.10:8080',

    [Parameter(Mandatory = $false)]
    [ValidateRange(1, 2)]
    [int] $Type = 1,

    [Parameter(Mandatory = $false)]
    [switch] $Lowercase = $false,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $TenantName,

    [Parameter(Mandatory = $false)]
    [ValidateSet('Exchange', 'SharePoint', 'Common', 'Skype')]
    [string[]] $ServiceAreas,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $FilePath,

    [Parameter(Mandatory = $false)]
    [ValidateNotNullOrEmpty()]
    [string] $CdnEdgeNodesFilePath
)

##################################################################################################################
### Global constants
##################################################################################################################

$baseServiceUrl = "https://endpoints.office.com/endpoints/$Instance/?ClientRequestId={$ClientRequestId}"
$directProxyVarName = "direct"
$defaultProxyVarName = "proxyServer"
$bl = "`r`n"

##################################################################################################################
### Functions to create PAC files
##################################################################################################################

function Get-PacClauses
{
    param(
        [Parameter(Mandatory = $false)]
        [string[]] $Urls,

        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [String] $ReturnVarName
    )

    if (!$Urls)
    {
        return ""
    }

    $clauses =  (($Urls | ForEach-Object { "shExpMatch(host, `"$_`")" }) -Join "$bl        || ")

@"
    if($clauses)
    {
        return $ReturnVarName;
    }
"@
}

function Get-PacString
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [array[]] $MapVarUrls
    )

@"
// This PAC file will provide proxy config to Microsoft 365 services
//  using data from the public web service for all endpoints
function FindProxyForURL(url, host)
{
    var $directProxyVarName = "$DirectProxySettings";
    var $defaultProxyVarName = "$DefaultProxySettings";

$( if ($Lowercase) { "    host = host.toLowerCase();" })

$( ($MapVarUrls | ForEach-Object { Get-PACClauses -ReturnVarName $_.Item1 -Urls $_.Item2 }) -Join "$bl$bl" )

$( if (!$ServiceAreas -or $ServiceAreas.Contains('Skype')) { Get-TLEPacConfiguration })

    return $defaultProxyVarName;
}
"@ -replace "($bl){3,}","$bl$bl" # Collapse more than one blank line in the PAC file so it looks better.
}

##################################################################################################################
### Functions to get and filter endpoints
##################################################################################################################

function Get-TLEPacConfiguration {
    param ()
    $PreBlock = @"
    // Don't Proxy Teams Live Events traffic

    if(shExpMatch(host, "*.azureedge.net")
    || shExpMatch(host, "*.bmc.cdn.office.net")
    || shExpMatch(host, "*.media.azure.net"))
    {
        var resolved_ip = dnsResolveEx(host);

"@
    $TLESb = New-Object 'System.Text.StringBuilder'
    $TLESb.Append($PreBlock) | Out-Null

    if (![string]::IsNullOrEmpty($CdnEdgeNodesFilePath) -and (Test-Path -Path $CdnEdgeNodesFilePath)) {
        $CdnData = Get-Content -Path $CdnEdgeNodesFilePath -Raw -ErrorAction SilentlyContinue | ConvertFrom-Json | Select-Object -ExpandProperty value | 
            Where-Object { $_.name -eq 'Premium_Verizon'} | Select-Object -First 1 -ExpandProperty properties | 
            Select-Object -ExpandProperty ipAddressGroups
        $CdnData | Select-Object -ExpandProperty ipv4Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
        $CdnData | Select-Object -ExpandProperty ipv6Addresses | ForEach-Object {
            if ($TLESb.Length -eq $PreBlock.Length) {
                $TLESb.Append("        if(") | Out-Null
            }
            else {
                $TLESb.AppendLine() | Out-Null
                $TLESb.Append("        || ") | Out-Null
            }
            $TLESb.Append("isInNetEx(resolved_ip, `"$($_.BaseIpAddress)/$($_.prefixLength)`")") | Out-Null
        }
    }
    $AzureIPsUrl = Invoke-WebRequest -Uri "https://www.microsoft.com/en-us/download/confirmation.aspx?id=56519" -UseBasicParsing -ErrorAction SilentlyContinue  | 
            Select-Object -ExpandProperty Links | Select-Object -ExpandProperty href | 
            Where-Object { $_.EndsWith('.json') -and $_ -match 'ServiceTags' } | Select-Object -First 1
    if ($AzureIPsUrl) {
        Invoke-RestMethod -Uri $AzureIPsUrl -ErrorAction SilentlyContinue | Select-Object -ExpandProperty values | 
            Where-Object { $_.name -eq 'AzureFrontDoor.Frontend' } | Select-Object -First 1 -ExpandProperty properties |
            Select-Object -ExpandProperty addressPrefixes | ForEach-Object {
                if ($TLESb.Length -eq $PreBlock.Length) {
                    $TLESb.Append("        if(") | Out-Null
                }
                else {
                    $TLESb.AppendLine() | Out-Null
                    $TLESb.Append("        || ") | Out-Null
                }
                $TLESb.Append("isInNetEx(resolved_ip, `"$_`")") | Out-Null
            }
    }
    if ($TLESb.Length -gt $PreBlock.Length) {
        $TLESb.AppendLine(")") | Out-Null
        $TLESb.AppendLine("        {") | Out-Null
        $TLESb.AppendLine("            return $directProxyVarName;") | Out-Null
        $TLESb.AppendLine("        }") | Out-Null
    }
    else {
        $TLESb.AppendLine("        // no addresses found for service via script") | Out-Null
    }
    $TLESb.AppendLine("    }") | Out-Null
    return $TLESb.ToString()
}

function Get-Regex
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $Fqdn
    )

    return "^" + $Fqdn.Replace(".", "\.").Replace("*", ".*").Replace("?", ".?") + "$"
}

function Match-RegexList
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $ToMatch,

        [Parameter(Mandatory = $false)]
        [string[]] $MatchList
    )

    if (!$MatchList)
    {
        return $false
    }
    foreach ($regex in $MatchList)
    {
        if ($regex -ne $ToMatch -and $ToMatch -match (Get-Regex $regex))
        {
            return $true
        }
    }
    return $false
}

function Get-Endpoints
{
    $url = $baseServiceUrl
    if ($TenantName)
    {
        $url += "&TenantName=$TenantName"
    }
    if ($ServiceAreas)
    {
        $url += "&ServiceAreas=" + ($ServiceAreas -Join ",")
    }
    return Invoke-RestMethod -Uri $url
}

function Get-Urls
{
    param(
        [Parameter(Mandatory = $false)]
        [psobject[]] $Endpoints
    )

    if ($Endpoints)
    {
        return $Endpoints | Where-Object { $_.urls } | ForEach-Object { $_.urls } | Sort-Object -Unique
    }
    return @()
}

function Get-UrlVarTuple
{
    param(
        [Parameter(Mandatory = $true)]
        [ValidateNotNullOrEmpty()]
        [string] $VarName,

        [Parameter(Mandatory = $false)]
        [string[]] $Urls
    )
    return New-Object 'Tuple[string,string[]]'($VarName, $Urls)
}

function Get-MapVarUrls
{
    Write-Verbose "Retrieving all endpoints for instance $Instance from web service."
    $Endpoints = Get-Endpoints

    if ($Type -eq 1)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -eq "Optimize" })
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -ne "Optimize" }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
    elseif ($Type -eq 2)
    {
        $directUrls = Get-Urls ($Endpoints | Where-Object { $_.category -in @("Optimize", "Allow")})
        $nonDirectPriorityUrls = Get-Urls ($Endpoints | Where-Object { $_.category -notin @("Optimize", "Allow") }) | Where-Object { Match-RegexList $_ $directUrls }
        return @(
            Get-UrlVarTuple -VarName $defaultProxyVarName -Urls $nonDirectPriorityUrls
            Get-UrlVarTuple -VarName $directProxyVarName -Urls $directUrls
        )
    }
}

##################################################################################################################
### Main script
##################################################################################################################

$content = Get-PacString (Get-MapVarUrls)

if ($FilePath)
{
    $content | Out-File -FilePath $FilePath -Encoding ascii
}
else
{
    $content
}
```

脚本将基于 **AzureFrontDoor.Frontend** 的下载 [URL](https://www.microsoft.com/download/details.aspx?id=56519) 和密钥自动分析 Azure 列表，因此无需手动获取。

同样，建议不要仅使用 FQDN 执行 VPN 卸载;利用 **函数** 中的 FQDN 和 IP 地址有助于将使用此卸载的范围限定为一组有限的终结点，包括 Live Events/Stream。 构建函数的方式将导致对直接匹配客户端列出的 FQDN（即剩余命名空间的 DNS 解析保持不变）执行 DNS 查找。

如果您希望限制卸载与 Live 事件和 Stream **\*** 不相关的终结点的风险，可以从配置中删除 .azureedge.net 域，此风险大部分位于此配置中，因为这是用于所有 Azure CDN 客户的共享域。 这样做的缺点是，使用外部编码器的任何事件将不会得到优化，而是在外部编码器内生成/Teams事件。

## <a name="3-configure-routing-on-the-vpn-to-enable-direct-egress"></a>3. 在 VPN 上配置路由以启用直接出口

最后一步是将收集 **CDN** 终结点的当前列表中描述的实时事件 IP 的直接路由添加到 VPN 配置中，以确保流量不会通过强制隧道发送到 VPN。 有关为优化终结点Microsoft 365的详细信息，请参阅为用户实现 VPN 拆分隧道的实现 [VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) 拆分[隧道](microsoft-365-vpn-implement-split-tunnel.md)Microsoft 365。 此过程与本文档中列出的 Stream/Live 事件 IP 完全相同。

请注意，只有 IP (FQDN) [收集 CDN 终结点](#gathering-the-current-lists-of-cdn-endpoints)的当前列表应用于 VPN 配置。

## <a name="faq"></a>常见问题

### <a name="will-this-send-all-my-traffic-to-the-service-direct"></a>这会将我的所有流量直接发送到服务吗？

否，这将发送实时事件或 Stream 视频直接的延迟敏感流流量，任何其他流量如果未解析到发布的 IP，将继续使用 VPN 隧道。

### <a name="do-i-need-to-use-the-ipv6-addresses"></a>是否需要使用 IPv6 地址？

否，连接只能是 IPv4（如果需要）。

### <a name="why-are-these-ips-not-published-in-the-microsoft-365-urlip-service"></a>为什么这些 IP 未发布到 Microsoft 365 URL/IP 服务？

Microsoft 对服务中信息的格式和类型进行严格控制，以确保客户能够可靠地使用该信息来实现基于终结点类别的安全和最佳路由。

由于多种原因，默认终结点类别未提供 IP 信息 (默认终结点可能超出 Microsoft 控制范围、可能更改过于频繁，或者可能位于与其他元素或) 共享的块中。 因此，默认终结点设计为通过 FQDN 发送到检查代理，如正常的 Web 流量。

在这种情况下，上述终结点可能是非 Microsoft 控制的元素（非实时事件或 Stream）使用的 CDN，因此直接发送流量也意味着解析为这些 IP 的任何其他内容也将从客户端直接发送。 鉴于当前全球危机的独特性质，为满足我们的客户的短期需求，Microsoft 已提供上述信息供客户根据情况使用。

Microsoft 正在努力重新配置实时事件终结点，以允许它们在将来包含在允许/优化终结点类别中。

### <a name="do-i-only-need-to-allow-access-to-these-ips"></a>是否仅需要允许访问这些 IP？

否，访问 [URL/IP](urls-and-ip-address-ranges.md) 服务中所有必需的标记终结点对于服务运行至关重要。 此外，任何标记为 Stream id (41-45) 可选终结点。

### <a name="what-scenarios-will-this-advice-cover"></a>此建议将涵盖哪些方案？

1. Teams App 内生成的实时事件
2. 查看 Stream 托管内容
3. 外部设备 (编码器) 生成的事件

### <a name="does-this-advice-cover-presenter-traffic"></a>此建议是否涵盖演示者流量？

它不一样，上述建议完全适用于使用服务的人。 从 Teams 内演示将看到演示者的流量流向 URL/IP 服务行 11 中列出的标记为优化的 UDP 终结点，其中详细 VPN 卸载建议如实现 [Microsoft 365 的 VPN](microsoft-365-vpn-implement-split-tunnel.md) 拆分隧道的实现 [VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) 拆分隧道一节所述。

### <a name="does-this-configuration-risk-traffic-other-than-live-events-amp-stream-being-sent-direct"></a>此配置是否对直接发送实时事件 &amp; 流外的流量有风险？

是，由于用于服务某些元素的共享 FQN，这无法避免。 此流量通常通过公司代理发送，该代理可以应用检查。 在 VPN 拆分隧道方案中，同时使用 FQDN 和 IP 将这种风险范围缩小到最小，但它仍然存在。 客户可以从卸载配置中删除 .azureedge.net 域，将此风险降至最低，但此操作将删除 Stream 支持的活动事件 (Teams 计划的外部编码器事件、Teams 中生成的 Yammer 事件、Yammer 计划的外部编码器事件以及 Stream 计划事件或 Stream) 中的按需查看。**\*** 在事件记录中安排和Teams事件不受影响。

## <a name="related-articles"></a>相关文章

[概述：用于服务器的 VPN 拆分Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[为用户实现 VPN 拆分Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[用于服务器的常见 VPN 拆分隧道Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[保护Teams VPN 拆分隧道的媒体流量](microsoft-365-vpn-securing-teams.md)

[Microsoft 365中国用户优化性能](microsoft-365-networking-china.md)

[Microsoft 365 网络连接原则](microsoft-365-network-connectivity-principles.md)

[评估 Microsoft 365 网络连接](assessing-network-connectivity.md)

[Microsoft 365网络和性能优化](network-planning-and-performance.md)

[安全专业人员和 IT 人员在当前独特的远程工作场景中实现新式安全控制的替代方法（Microsoft 安全团队博客）](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[增强 Microsoft 的 VPN 性能：使用 Windows 10 VPN 配置文件以允许自动打开连接](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[运行 VPN：Microsoft 如何让远程工作人员互联](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft 全球网络](/azure/networking/microsoft-global-network)
