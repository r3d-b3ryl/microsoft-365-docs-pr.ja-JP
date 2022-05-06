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
>この記事は、リモート ユーザーの最適化Microsoft 365対処する一連の記事の一部です。

>- VPN 分割トンネリングを使用してリモート ユーザーのMicrosoft 365接続を最適化する方法の概要については、「[概要: Microsoft 365の VPN 分割トンネリング」を](microsoft-365-vpn-split-tunnel.md)参照してください。
>- VPN 分割トンネリングの実装に関する詳細なガイダンスについては、「[Microsoft 365用の VPN 分割トンネリングの実装」を](microsoft-365-vpn-implement-split-tunnel.md)参照してください。
>- VPN 分割トンネリングのシナリオの詳細な一覧については、「[Microsoft 365の一般的な VPN 分割トンネリング シナリオ」を](microsoft-365-vpn-common-scenarios.md)参照してください。
>- VPN 分割トンネリング環境でのTeamsメディア トラフィックのセキュリティ保護に関するガイダンスについては、「VPN 分割トンネリング[のメディア トラフィックTeamsセキュリティ保護](microsoft-365-vpn-securing-teams.md)する」を参照してください。
>- 中国のユーザーに対Microsoft 365世界規模のテナント パフォーマンスを最適化する方法については、「中国ユーザー[のパフォーマンスの最適化Microsoft 365」を参照してください](microsoft-365-networking-china.md)。

Microsoft 365ライブ イベント トラフィック (これには、Teams生成されたライブ イベントへの出席者と、Teams、ストリーム、またはYammerを介して外部エンコーダーで生成されたものが含まれます)、オンデマンド ストリーム トラフィックは現在、[サービスの URL/IP リスト](urls-and-ip-address-ranges.md)で **既定** と **最適化** に分類されています。 これらのエンドポイントは、他のサービスでも使用できる CDN でホストされているため、 **既定** として分類されます。 お客様は一般に、この種類のトラフィックをプロキシし、このようなエンドポイントで通常行われるセキュリティ要素を適用することを好みます。

多くのお客様は、VPN インフラストラクチャ経由で大量の待機時間に依存するトラフィックをルーティングするのではなく、ユーザーをローカル インターネット接続から直接 Stream/Live イベントに接続するために必要な URL/IP データを要求しています。 通常、これは、専用の名前空間とエンドポイントの正確な IP 情報の両方を使用しないと不可能です。これは、**既定** として分類されたMicrosoft 365 エンドポイントには提供されません。

次の手順を使用して、強制トンネル VPN を使用してクライアントから Stream/Live Events サービスの直接接続を有効にします。 このソリューションは、自宅からの作業シナリオによりネットワーク トラフィックが多いときに、VPN 経由でライブ イベント トラフィックをルーティングしないようにするオプションを顧客に提供することを目的としています。 可能であれば、検査中のプロキシを介してサービスにアクセスすることをお勧めします。

>[!NOTE]
>このソリューションを使用すると、提供された IP アドレスに解決されず、VPN を通過するサービス要素が存在する場合がありますが、ストリーミング データなどの大量のトラフィックの大部分が必要です。 このオフロードによってキャッチされるライブ イベント/ストリームの範囲外に他の要素がある場合がありますが、直接移動する前に FQDN _と_ IP の両方を満たす必要があるため、制限する必要があります。

>[!IMPORTANT]
>お客様は、ライブ イベントのパフォーマンス向上よりも VPN をバイパスするトラフィックが増えるリスクを比較検討することをお勧めします。

Teamsライブ イベントとストリームの強制トンネル例外を実装するには、次の手順を適用する必要があります。

## <a name="1-configure-external-dns-resolution"></a>1. 外部 DNS 解決を構成する

クライアントでは、次のホスト名を IP アドレスに解決できるように、外部の再帰的 DNS 解決を使用できる必要があります。

- \*.azureedge.net
- \*.media.azure.net
- \*.bmc.cdn.office.net

**\*.azureedge.net** は Stream イベントに使用されます ([Microsoft Streamでライブ ストリーミング用のエンコーダーを構成する - Microsoft Stream |Microsoft Docs](/stream/live-encoder-setup))。

**\*.media.azure.net** と **\*.bmc.cdn.office.net** は、Teams クライアントからスケジュールされたTeams生成されたライブ イベント (クイック スタート イベント、RTMP-Inサポートされているイベント [ロードマップ ID 84960]) に使用されます。

 これらのエンドポイントの中には、Stream/Live イベント以外の他の要素と共有されているものがあります。VPN ソリューションで技術的に可能な場合でも、これらの FQDN を使用して VPN オフロードを構成することはお勧めしません (たとえば、IP ではなく FQDN で動作する場合)。

FQDN は VPN 構成では必要ありません。これは、IP と組み合わせて PAC ファイルで使用して、関連するトラフィックを直接送信するためです。

## <a name="2-implement-pac-file-changes-where-required"></a>2. PAC ファイルの変更を実装する (必要な場合)

VPN 上で PAC ファイルを使用してプロキシ経由でトラフィックをルーティングする組織の場合、これは通常 FQDN を使用して実現されます。 ただし、Stream/Live イベントでは、指定されたホスト名に **.azureedge.net などの\*** ワイルドカードが含まれています。これには、完全な IP リストを提供できない他の要素も含まれます。 したがって、DNS ワイルドカード一致のみに基づいて要求が直接送信された場合、この記事の [後半の手順 3](#3-configure-routing-on-the-vpn-to-enable-direct-egress) . で直接パス経由のルートがないため、これらのエンドポイントへのトラフィックはブロックされます。

これを解決するために、次の IP を提供し、 [手順 1](#1-configure-external-dns-resolution) で説明したように PAC ファイルの例のホスト名と組み合わせて使用できます。 PAC ファイルは、URL が Stream/Live イベントに使用されているものと一致するかどうかを確認し、その URL が使用されている場合は、DNS ルックアップから返された IP がサービスに対して指定されたものと一致するかどうかを確認します。 _両方_ が一致する場合、トラフィックは直接ルーティングされます。 いずれかの要素 (FQDN/IP) が一致しない場合、トラフィックはプロキシに送信されます。 その結果、構成により、IP 名前空間と定義済み名前空間の両方の範囲外の IP に解決されるものはすべて、通常どおり VPN 経由でプロキシを通過するようになります。

### <a name="gathering-the-current-lists-of-cdn-endpoints"></a>CDN エンドポイントの現在のリストの収集

ライブ イベントでは、複数のCDN プロバイダーを使用して顧客にストリーミングし、最適なカバレッジ、品質、回復性を提供します。 現在、Microsoft と Verizon の両方のAzure CDNが使用されています。 時間の経過と共に、リージョンの可用性などの状況により、これが変更される可能性があります。 この記事は、IP 範囲を最新の状態に保つためのソースです。

Microsoft からAzure CDNの場合は、[Azure IP 範囲とサービス タグのダウンロード - パブリック クラウドから公式の Microsoft ダウンロード センターから](https://www.microsoft.com/download/details.aspx?id=56519)一覧をダウンロードできます。JSON の *AzureFrontdoor.Frontend* サービス タグを特に探す必要があります。*addressPrefixes* には、IPv4/IPv6 サブネットが表示されます。 時間の経過と共に IP は変更できますが、サービス タグリストは常に更新されてから使用されます。

Verizon (Edgecast) からのAzure CDNの場合は、(**[試してみる**] をクリック) を使用して [https://docs.microsoft.com/rest/api/cdn/edge-nodes/list](/rest/api/cdn/edge-nodes/list)完全な一覧を見つけることができます。**プレミアム\_Verizon** セクションを特に探す必要があります。 この API では、すべての Edgecast IP (配信元と Anycast) が表示されることに注意してください。 現在、API が配信元と Anycast を区別するメカニズムはありません。

これを PAC ファイルに実装するには、次の例を使用します。この例では、FQDN を介してトラフィックを最適化Microsoft 365ダイレクト (推奨されるベスト プラクティス) を送信し、FQDN と返された IP アドレスの組み合わせを介して重要な Stream/Live イベント トラフィックを直接送信できます。 Contoso のプレースホルダー名は、 _contoso_ _が contoso.onmicrosoft.com_ から取得した特定のテナントの名前に編集する必要があります。

#### <a name="example-pac-file"></a>PAC ファイルの例

PAC ファイルを生成する方法の例を次に示します。

1. 次のスクリプトを _Get-TLEPacFile.ps1としてローカル_ ハード ディスクに保存します。
1. [Verizon URL](/rest/api/cdn/edge-nodes/list#code-try-0) に移動し、結果の JSON をダウンロードします (cdnedgenodes.json などのファイルに貼り付けます)。
1. スクリプトと同じフォルダーにファイルを配置します。
1. PowerShell ウィンドウで、次のコマンドを実行します。 SPO URL が必要な場合は、別のテナント名を変更します。 これはタイプ 2 なので、 **最適化** と **許可** (種類 1 は最適化のみ)。

   ```powershell
   .\Get-TLEPacFile.ps1 -Instance Worldwide -Type 2 -TenantName <contoso> -CdnEdgeNodesFilePath .\cdnedgenodes.json -FilePath TLE.pac
   ```

5. TLE.pac ファイルには、すべての名前空間と IP (IPv4/IPv6) が含まれます。

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

スクリプトは、**AzureFrontDoor.Frontend** の [ダウンロード URL](https://www.microsoft.com/download/details.aspx?id=56519) とキーに基づいて Azure リストを自動的に解析するため、手動で取得する必要はありません。

ここでも、FQDN のみを使用して VPN オフロードを実行することはお勧めしません。関数内の FQDN と IP アドレスの **両方** を利用することで、このオフロードをライブ イベント/ストリームを含む一連のエンドポイントに適用できます。 関数の構造化方法により、FQDN に対して DNS 参照が実行され、クライアントによって直接一覧表示されたものと一致します。つまり、残りの名前空間の DNS 解決は変更されません。

ライブ イベントとストリームに関連しないエンドポイントをオフロードするリスクを制限する場合は、.azureedge.net ドメインを構成から削除 **\*** できます。このドメインの大部分は、すべてのAzure CDN顧客に使用される共有ドメインであるためです。 この欠点は、外部エンコーダーを使用するイベントは最適化されませんが、Teams内で生成/整理されるイベントは最適化されないことです。

## <a name="3-configure-routing-on-the-vpn-to-enable-direct-egress"></a>3. 直接エグレスを有効にする VPN でのルーティングを構成する

最後の手順では、VPN 構成に **CDN エンドポイントの現在のリストの収集** に関するページで説明されているライブ イベント IP のダイレクト ルートを追加して、強制トンネル経由で VPN にトラフィックが送信されないようにします。 Microsoft 365最適化エンドポイントに対してこれを行う方法の詳細については、「Microsoft 365用[の VPN 分割トンネリングを実装する](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)」の「[VPN 分割トンネリングの実装」セクションを参照](microsoft-365-vpn-implement-split-tunnel.md)してください。 このプロセスは、このドキュメントに記載されている Stream/Live イベント IP の場合とまったく同じです。

VPN 構成には、[CDN エンドポイントの現在のリストの収集](#gathering-the-current-lists-of-cdn-endpoints)から IP (FQDN ではない) のみを使用する必要があることに注意してください。

## <a name="faq"></a>よくあるご質問 (FAQ)

### <a name="will-this-send-all-my-traffic-to-the-service-direct"></a>これにより、すべてのトラフィックがサービスに直接送信されますか?

いいえ。これはライブ イベントまたは Stream ビデオ ダイレクトの待機時間に依存するストリーミング トラフィックを送信します。公開された IP に解決されない場合、他のトラフィックは VPN トンネルを引き続き使用します。

### <a name="do-i-need-to-use-the-ipv6-addresses"></a>IPv6 アドレスを使用する必要がありますか?

いいえ。接続は必要な場合にのみ IPv4 にできます。

### <a name="why-are-these-ips-not-published-in-the-microsoft-365-urlip-service"></a>これらの IP が Microsoft 365 URL/IP サービスで公開されないのはなぜですか?

Microsoft は、サービス内の情報の形式と種類を厳密に制御し、お客様がエンドポイント カテゴリに基づいてセキュリティで保護された最適なルーティングを実装するために情報を確実に使用できるようにします。

**既定の** エンドポイント カテゴリには、さまざまな理由で IP 情報が提供されません (既定のエンドポイントは、Microsoft の制御の範囲外である可能性があります。変更頻度が高すぎる場合や、他の要素と共有されているブロックになっている可能性があります)。 このため、既定のエンドポイントは、通常の Web トラフィックのように、FQDN 経由で検査プロキシに送信されるように設計されています。

この場合、上記のエンドポイントは、ライブ イベントや Stream 以外の Microsoft 以外の制御要素によって使用される可能性のある CDN であるため、トラフィックを直接送信すると、これらの IP に解決される他の要素もクライアントから直接送信されます。 現在のグローバル危機の固有の性質と、お客様の短期的なニーズを満たすために、Microsoft は、お客様が適切に使用できるように、上記の情報を提供しています。

Microsoft は、今後、ライブ イベント エンドポイントを Allow/Optimize エンドポイント カテゴリに含めることができるように、エンドポイントの再構成に取り組んでいます。

### <a name="do-i-only-need-to-allow-access-to-these-ips"></a>これらの IP へのアクセスのみを許可する必要がありますか?

いいえ。[URL/IP サービス](urls-and-ip-address-ranges.md)内のすべての **必須** マークされたエンドポイントへのアクセスは、サービスが動作するために不可欠です。 さらに、Stream (ID 41- 45) にマークされた任意のエンドポイントが必要です。

### <a name="what-scenarios-will-this-advice-cover"></a>このアドバイスはどのようなシナリオに対応しますか?

1. Teams アプリ内で生成されたライブ イベント
2. Stream ホステッド コンテンツの表示
3. 外部デバイス (エンコーダー) によって生成されたイベント

### <a name="does-this-advice-cover-presenter-traffic"></a>このアドバイスは発表者のトラフィックに関する情報ですか?

上記のアドバイスは、サービスを使用しているユーザーに対して行われるものではありません。 Teams内からプレゼンテーションを行うと、発表者のトラフィックが URL/IP サービス行 11 のオプティマイズ マークされた UDP エンドポイントに流れ、VPN オフロードに関する詳細なアドバイスについては、「[Microsoft 365用 VPN 分割トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)」の「[VPN 分割トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md#implement-vpn-split-tunneling)」セクションで説明されています。

### <a name="does-this-configuration-risk-traffic-other-than-live-events-amp-stream-being-sent-direct"></a>この構成では、ライブ イベント &amp; ストリーム以外のトラフィックが直接送信されるリスクがありますか?

はい。サービスの一部の要素に使用される共有 FQDN のため、これは避けられません。 このトラフィックは通常、検査を適用できる企業プロキシを介して送信されます。 VPN 分割トンネルのシナリオでは、FQDN と IP の両方を使用して、このリスクの範囲を最小限に抑えますが、引き続き存在します。 お客様は **、.azureedge.net ドメインを\*** オフロード構成から削除し、このリスクを最小限に抑えることができますが、これにより、Stream でサポートされるライブ イベント (Teamsスケジュールされた外部エンコーダー イベント、Teamsで生成されたYammerイベント、Yammerスケジュールされた外部エンコーダー イベント、Stream スケジュールされたイベント、または Stream からのオンデマンド表示) のオフロードが削除されます。 Teamsでスケジュールおよび生成されたイベントは影響を受けません。

## <a name="related-articles"></a>関連記事

[概要: Microsoft 365の VPN 分割トンネリング](microsoft-365-vpn-split-tunnel.md)

[Microsoft 365用の VPN 分割トンネリングの実装](microsoft-365-vpn-implement-split-tunnel.md)

[Microsoft 365の一般的な VPN 分割トンネリング シナリオ](microsoft-365-vpn-common-scenarios.md)

[VPN 分割トンネリングのための Teams メディア トラフィックのセキュリティ保護](microsoft-365-vpn-securing-teams.md)

[中国ユーザーのMicrosoft 365パフォーマンスの最適化](microsoft-365-networking-china.md)

[Microsoft 365 ネットワーク接続の原則](microsoft-365-network-connectivity-principles.md)

[Microsoft 365 ネットワーク接続の評価](assessing-network-connectivity.md)

[Microsoft 365ネットワークとパフォーマンスのチューニング](network-planning-and-performance.md)

[セキュリティ専門家と IT による、現代のユニークなリモート ワーク シナリオで最新のセキュリティ管理を実現するための代替的な方法 (Microsoft セキュリティ チーム ブログ)](https://www.microsoft.com/security/blog/2020/03/26/alternative-security-professionals-it-achieve-modern-security-controls-todays-unique-remote-work-scenarios/)

[Microsoft での VPN のパフォーマンス強化: Windows 10 の VPN プロファイルを使用して自動接続を許可する](https://www.microsoft.com/itshowcase/enhancing-remote-access-in-windows-10-with-an-automatic-vpn-profile)

[VPN で実行: Microsoft がリモート ワークの従業員をどのように接続させているか](https://www.microsoft.com/itshowcase/blog/running-on-vpn-how-microsoft-is-keeping-its-remote-workforce-connected/?elevate-lv)

[Microsoft グローバル ネットワーク](/azure/networking/microsoft-global-network)
