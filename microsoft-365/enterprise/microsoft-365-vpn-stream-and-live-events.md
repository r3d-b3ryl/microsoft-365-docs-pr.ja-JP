---
title: VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項
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
description: VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項
ms.openlocfilehash: eb2e57b844f06bc3b1e005aa1095794b176bba94
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63331192"
---
# <a name="special-considerations-for-stream-and-live-events-in-vpn-environments"></a>VPN 環境での Stream イベントとライブ イベントに関する特別な考慮事項

>[!NOTE]
>この記事は、リモート ユーザーの最適化に関するMicrosoft 365の一部です。

>- VPN スプリット トンネリングを使用してリモート ユーザー Microsoft 365接続を最適化する方法の概要については、「[Overview: VPN split tunneling for remoteing for remote」を参照](microsoft-365-vpn-split-tunnel.md)Microsoft 365。
>- VPN スプリット トンネリングの実装に関する詳細なガイダンスについては、「VPN スプリット トンネリングの実装」を参照[Microsoft 365。](microsoft-365-vpn-implement-split-tunnel.md)
>- VPN スプリット トンネリングのシナリオの詳細な一覧については、「VPN スプリット トンネリングの一般的なシナリオ」を参照[Microsoft 365。](microsoft-365-vpn-common-scenarios.md)
>- VPN スプリット トンネリング環境でのTeamsメディア トラフィックのセキュリティ保護に関するガイダンスについては、「VPN スプリット トンネリングTeamsメディア トラフィックのセキュリティ[保護」を参照してください](microsoft-365-vpn-securing-teams.md)。
>- 中国のユーザーに対するMicrosoft 365のパフォーマンスの最適化の詳細については、「中国のユーザー Microsoft 365[パフォーマンスの最適化」を参照してください](microsoft-365-networking-china.md)。

Microsoft 365 ライブ イベント トラフィック (これには、Teams が生成されたライブ イベントへの出席者、および Teams、Stream、または Yammer 経由で外部エンコーダーで生成されたイベントが含まれます)、オンデマンド ストリーム トラフィックは現在、サービスの [URL/IP](urls-and-ip-address-ranges.md) リストの Default とオプティマイズに分類されています。 これらのエンドポイントは、他のサービスでも使用される可能性がある CDN 上でホストされているので、Default に分類されます。 お客様は一般に、この種類のトラフィックをプロキシし、このようなエンドポイントで通常行われるセキュリティ要素を適用することを好む。

多くのお客様は、VPN インフラストラクチャを介して大ボリュームおよび待機時間に敏感なトラフィックをルーティングするのではなく、ローカル インターネット接続から直接ユーザーを Stream/Live イベントに接続するために必要な URL/IP データを要求しています。 通常、これは、専用の名前空間とエンドポイントの正確な IP 情報の両方なしでは使用できません。これは、既定として分類された Microsoft 365 エンドポイントには提供 **されません**。

強制トンネル VPN を使用するクライアントからの Stream/Live イベント サービスの直接接続を有効にするには、次の手順を使用します。 このソリューションは、在宅作業のシナリオのためにネットワーク トラフィックが多い一方で、VPN を使用して Live Events トラフィックをルーティングしないようにするオプションを顧客に提供することを目的とします。 可能であれば、検査プロキシを介してサービスにアクセスする必要があります。

>[!NOTE]
>このソリューションを使用すると、提供された IP アドレスに解決されないサービス要素が VPN を通過する場合がありますが、ストリーミング データのような大量トラフィックの大部分は必要です。 このオフロードによってキャッチされる Live Events/Stream のスコープ外には他の要素が含まれる場合がありますが、直接行く前に _FQDN と_ IP 一致の両方を満たす必要がある場合は、これらを制限する必要があります。

>[!IMPORTANT]
>お客様は、ライブ イベントのパフォーマンス向上を超え、VPN をバイパスするトラフィックを多く送信するリスクを量り取る必要があります。

ライブ イベントとストリームの強制トンネルTeams実装するには、次の手順を適用する必要があります。

## <a name="1-configure-external-dns-resolution"></a>1. 外部 DNS 解決を構成する

クライアントは、次のホスト名を IP アドレスに解決するために、外部の再帰的な DNS 解決を利用できる必要があります。

- \*.azureedge.net
- \*.media.azure.net
- \*.bmc.cdn.office.net

**\*.azureedge.net** は Stream イベントに使用されます (Microsoft Stream でのライブ ストリーミング用にエンコーダーを構成 [する - Microsoft Stream |Microsoft Docs](/stream/live-encoder-setup))。

**\*.media.azure.net** **\*と .bmc.cdn.office.net** は、Teams が生成するライブ イベント (クイック スタート イベント、RTMP-In でサポートされているイベント [ロードマップ ID 84960]) に使用され、Teams クライアントからスケジュールされます。

 これらのエンドポイントの一部は、Stream/Live イベント以外の他の要素と共有されています。VPN ソリューションで技術的に可能な場合でも、これらの FQDN を使用して VPN オフロードを構成する必要があります (たとえば、IP ではなく FQDN で動作する場合)。

FQDN は VPN 構成では必要ありません。これらは純粋に関連するトラフィックを直接送信するために、AP と組み合わせて PAC ファイルで使用するために使用されます。

## <a name="2-implement-pac-file-changes-where-required"></a>2. PAC ファイルの変更を実装する (必要な場合)

VPN の実行中に PAC ファイルを使用してプロキシ経由でトラフィックをルーティングする組織の場合、これは通常、FQDN を使用して実現されます。 ただし、Stream/Live イベント **\*** では、提供されるホスト名には .azureedge.net などのワイルドカードが含まれています。また、完全な IP リストを提供できない他の要素も含まれます。 したがって、DNS ワイルドカードの一致に基づいて要求が直接送信される場合、この記事の後半の手順 [3](#3-configure-routing-on-the-vpn-to-enable-direct-egress) で直接パスを経由するルートが無い場合、これらのエンドポイントへのトラフィックはブロックされます。

これを解決するために、次の IP を提供し、手順 1 で説明した例の PAC ファイルのホスト名と組み合わせて [使用します](#1-configure-external-dns-resolution)。 PAC ファイルは、URL が Stream/Live イベントで使用される URL と一致する場合、その URL が一致する場合は、DNS 参照から返された IP がサービスに提供された IP と一致する場合も確認します。 両方 _が一_ 致する場合、トラフィックは直接ルーティングされます。 いずれかの要素 (FQDN/IP) が一致しない場合、トラフィックはプロキシに送信されます。 その結果、IP 名前空間と定義済み名前空間の両方のスコープ外の IP に解決される何でも、通常通り VPN 経由でプロキシを通過できます。

### <a name="gathering-the-current-lists-of-cdn-endpoints"></a>エンドポイントの現在のリストCDNする

ライブ イベントでは、複数のCDNプロバイダーを使用して顧客にストリーミングし、最適なカバレッジ、品質、復元性を提供します。 現在、Microsoft と verizon Azure CDNの両方が使用されています。 時間がたつ間に、地域の可用性などの状況により変更される可能性があります。 この記事は、IP 範囲を最新の状態に保つソースです。

Microsoft Azure CDNの場合は、公式 Microsoft ダウンロード センターから [Azure IP](https://www.microsoft.com/download/details.aspx?id=56519) 範囲とサービス タグをダウンロード - パブリック クラウドからリストをダウンロードできます。JSON の *サービス タグ AzureFrontdoor.Frontend* を特に探す必要があります。*addressPrefixes は* IPv4/IPv6 サブネットを表示します。 時間がたつ間に、AP は変更できますが、サービス タグリストは常に更新され、使用されます。

Verizon (Edgecast) [https://docs.microsoft.com/rest/api/cdn/edge-nodes/list](/rest/api/cdn/edge-nodes/list) のAzure CDNには、([試す] をクリック) を使用して網羅的なリストを見つける必要があります。特に プレミアム **Verizon セクションを\_** 検索する必要があります。 この API には、すべての Edgecast IPs (origin と Anycast) が表示されます。 現在、API がオリジンと Anycast を区別するメカニズムは提供されていない。

これを PAC ファイルに実装するには、次の例を使用して、FQDN を介して Microsoft 365 Optimize トラフィック ダイレクト (推奨されるベスト プラクティス) を送信し、FQDN と返される IP アドレスの組み合わせを介して重要な Stream/Live Events トラフィックを直接送信します。 Contoso の _プレースホルダー名_ は、contoso がユーザーの名前である特定のテナントの名前に編集する contoso.onmicrosoft.com

#### <a name="example-pac-file"></a>PAC ファイルの例

PAC ファイルを生成する方法の例を次に示します。

1. 以下のスクリプトをローカル のハード ディスク _に保存します_ Get-TLEPacFile.ps1。
1. [Verizon URL に移動し](/rest/api/cdn/edge-nodes/list#code-try-0)、結果の JSON をダウンロードします (cdnedgenodes.json のようなファイルにコピー貼り付け)
1. スクリプトと同じフォルダーにファイルを置きます。
1. PowerShell ウィンドウで、次のコマンドを実行します。 SPO URL が必要な場合は、別のテナント名を変更します。 これはタイプ 2 なので、 **オプティマイズ** と **許可** (Type 1 はオプティマイズのみ) です。

   ```powershell
   .\Get-TLEPacFile.ps1 -Instance Worldwide -Type 2 -TenantName <contoso> -CdnEdgeNodesFilePath .\cdnedgenodes.json -FilePath TLE.pac
   ```

5. TLE.pac ファイルには、すべての名前空間と IPs (IPv4/IPv6) が含まれる。

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

スクリプトは **AzureFrontDoor.Frontend** のダウンロード [URL](https://www.microsoft.com/download/details.aspx?id=56519) とキーオフに基づいて Azure リストを自動的に解析します。そのため、手動で取得する必要はありません。

繰り返しますが、FQDN を使用して VPN オフロードを実行する必要はありません。関数内 **の** FQDN と IP アドレスの両方を利用すると、このオフロードの使用を、Live イベント/ストリームを含む制限されたエンドポイントセットに範囲を設定するのに役立ちます。 関数の構造化方法により、クライアントによって直接一覧表示される FQDN に対して DNS 参照が実行されます。つまり、残りの名前空間の DNS 解決は変更されません。

Live Events および Stream **\*** に関連しないエンドポイントをオフロードするリスクを制限する場合は、このリスクの大部分が Azure CDN のお客様に使用される共有ドメインである構成から .azureedge.net ドメインを削除できます。 この欠点は、外部エンコーダーを使用するイベントは最適化されませんが、外部エンコーダー内で生成またはTeamsです。

## <a name="3-configure-routing-on-the-vpn-to-enable-direct-egress"></a>3. 直接出力を有効にするために VPN のルーティングを構成する

最後の手順では、「**CDN Endpoints** の現在のリストを VPN 構成に収集する」で説明されている Live イベントの直接ルートを追加し、トラフィックが強制的なトンネルを介して VPN に送信されなかることを確認します。 Microsoft 365 オプティマイズ エンドポイントに対してこれを行う方法の詳細については、「VPN スプリット トンネリング[](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)を実装する」の「[VPN](microsoft-365-vpn-implement-split-tunnel.md) スプリット トンネリングの実装」セクションMicrosoft 365。 このプロセスは、このドキュメントに記載されている Stream/Live イベントの AP でまったく同じです。

VPN 構成には、エンドポイントの現在のリストを収集する [](#gathering-the-current-lists-of-cdn-endpoints) (FQDN ではなく) CDNに注意してください。

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="will-this-send-all-my-traffic-to-the-service-direct"></a>これにより、すべてのトラフィックがサービスに直接送信されますか?

いいえ、これにより Live イベントまたはストリーム ビデオダイレクトの遅延に敏感なストリーミング トラフィックが送信されます。公開された AP に解決されない場合、他のトラフィックは引き続き VPN トンネルを使用します。

### <a name="do-i-need-to-use-the-ipv6-addresses"></a>IPv6 アドレスを使用する必要がありますか?

いいえ、接続は必要な場合にのみ IPv4 にできます。

### <a name="why-are-these-ips-not-published-in-the-microsoft-365-urlip-service"></a>これらの IP が URL/IP サービスのMicrosoft 365されない理由

Microsoft では、サービス内の情報の形式と種類に関する厳密な管理を行い、お客様が情報を確実に使用して、エンドポイント カテゴリに基づいて安全で最適なルーティングを実装できます。

[ **既定の** エンドポイント] カテゴリには、さまざまな理由で IP 情報が提供されません (既定のエンドポイントは Microsoft の制御の外部にある場合や、頻繁に変更される可能性がある、または他の要素と共有されるブロックに含まれます)。 このため、既定のエンドポイントは、通常の Web トラフィックのように、FQDN を介して検査プロキシに送信するように設計されています。

この場合、上記のエンドポイントは、Live イベントまたは Stream 以外の Microsoft 以外の制御要素によって使用される可能性のある CDN であり、トラフィックダイレクトを送信すると、これらの ID に解決されるその他の意味もクライアントから直接送信されます。 現在のグローバル危機の固有の性質と、お客様の短期的なニーズを満たすために、Microsoft は、お客様が適した状態で使用するために上記の情報を提供しました。

Microsoft は、今後の Allow/Optimize エンドポイント カテゴリに含まれるライブ イベント エンドポイントを再構成する作業を行っています。

### <a name="do-i-only-need-to-allow-access-to-these-ips"></a>これらの AP へのアクセスのみを許可する必要がありますか?

いいえ、サービスを運用するには、[URL/IP](urls-and-ip-address-ranges.md) サービス内のすべての必須マーク付きエンドポイントへのアクセスが不可欠です。 さらに、Stream (ID 41-45) のマークが付いている任意のオプション エンドポイントが必要です。

### <a name="what-scenarios-will-this-advice-cover"></a>このアドバイスでカバーされるシナリオは何ですか?

1. アプリ内で生成されるライブ Teamsイベント
2. ストリームホスト型コンテンツの表示
3. 外部デバイス (エンコーダー) によって生成されるイベント

### <a name="does-this-advice-cover-presenter-traffic"></a>このアドバイスは発表者のトラフィックをカバーしていますか?

そうではありません。上記のアドバイスは、サービスを利用する人のためのものです。 Teams 内から提示すると、発表者のトラフィックが URL/IP サービス行 11 に記載されているオプティマイズ マークされた UDP エンドポイントに流れ、[Microsoft 365](microsoft-365-vpn-implement-split-tunnel.md) の VPN スプリット トンネリングの実装の「[VPN](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling) スプリット トンネリングの実装」セクションで説明されている詳細な VPN オフロードアドバイスが表示されます。

### <a name="does-this-configuration-risk-traffic-other-than-live-events-amp-stream-being-sent-direct"></a>この構成では、ライブ イベント ストリーム以外のトラフィック &amp; が直接送信されるリスクがありますか?

はい、サービスの一部の要素で使用される共有 FQDN のため、これは避けできません。 通常、このトラフィックは、検査を適用できる企業プロキシ経由で送信されます。 VPN 分割トンネルのシナリオでは、FQDN と IPs の両方を使用すると、このリスクを最小限に抑えますが、それでも存在します。 お客様は、オフロード構成から .azureedge.net ドメインを削除し、このリスクを最小限に抑えますが、これにより、ストリームでサポートされるライブ イベント (Teams スケジュールされた外部エンコーダー イベント、Teams、Yammer スケジュールされた外部エンコーダー イベント、ストリームスケジュールされたイベントまたはストリームストリームからのオンデマンド表示で生成される Yammer イベント) のオフロードが削除されます。**\*** イベントがスケジュールされ、Teams影響を受けません。

## <a name="related-articles"></a>関連記事

[概要: VPN スプリット トンネリング (Microsoft 365](microsoft-365-vpn-split-tunnel.md)

[VPN スプリット トンネリングを実装するMicrosoft 365](microsoft-365-vpn-implement-split-tunnel.md)

[VPN スプリット トンネリングの一般的なシナリオ (Microsoft 365](microsoft-365-vpn-common-scenarios.md)

[VPN スプリット トンTeamsメディア トラフィックのセキュリティ保護](microsoft-365-vpn-securing-teams.md)

[Microsoft 365のパフォーマンスの最適化](microsoft-365-networking-china.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365とパフォーマンスの調整](network-planning-and-performance.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)
