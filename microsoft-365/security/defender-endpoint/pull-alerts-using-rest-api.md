---
title: REST API を使用したエンドポイント検出用の Microsoft Defender のプル
description: SIEM REST API を使用して MICROSOFT Defender for Endpoint API エンドポイントを呼び出して JSON 形式で検出をプルする方法について説明します。
keywords: 検出、プル検出、rest api、要求、応答
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
localization_priority: Normal
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: mde
ms.custom: api
ms.openlocfilehash: 29aa8008dc3674760e4e720f155d6df82068ab55
ms.sourcegitcommit: 4740e69326eb7f8302eec7bab5bd516d498e4492
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/16/2021
ms.locfileid: "59402180"
---
# <a name="pull-microsoft-defender-for-endpoint-detections-using-siem-rest-api"></a>SIEM REST API を使用したエンドポイント検出用の Microsoft Defender のプル

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/p/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> Defender for Endpoint を試す場合は、 [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-pullalerts-abovefoldlink)


[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

> [!NOTE]
>
> - [Microsoft Defender for Endpoint Alert は](alerts.md) 、1 つ以上の検出から構成されます。
> - [Microsoft Defender for Endpoint Detection は](api-portal-mapping.md) 、デバイスで発生した疑わしいイベントとその関連するアラートの詳細から構成されます。
> s-The Microsoft Defender for Endpoint Alert API は、アラートの使用に関する最新の API であり、各アラートに関連する証拠の詳細な一覧を含む。 詳細については、「Alert メソッドと[プロパティ」および「List alerts」](alerts.md)[を参照してください](get-alerts.md)。

Microsoft Defender for Endpoint は、API から検出を引き出す OAuth 2.0 プロトコルをサポートしています。

一般に、OAuth 2.0 プロトコルは 4 種類のフローをサポートします。

- 承認の付与フロー
- 暗黙的フロー
- クライアント資格情報フロー
- リソース所有者フロー

OAuth 仕様の詳細については [、「OAuth Web サイト」を参照してください](http://www.oauth.net)。

Microsoft Defender for  Endpoint では、承認許可フローとクライアント資格情報フローがサポートされ、認証サーバーとして Azure Active Directory (AAD) を使用してプル検出へのアクセスを取得できます。

承認 _付与フローは、_ ユーザー資格情報を使用して承認コードを取得し、アクセス トークンを取得するために使用されます。

クライアント _資格情報フローでは、_ クライアント資格情報を使用して Microsoft Defender for Endpoint エンドポイント URL に対する認証を行います。 このフローは、OAuth クライアントがユーザー資格情報を必要としない API への要求を作成するシナリオに適しています。

Microsoft Defender for Endpoint API の次のメソッドを使用して、JSON 形式で検出をプルします。

> [!NOTE]
> Microsoft Defender セキュリティ センター同様のアラート検出を 1 つのアラートにマージします。 この API は、設定したクエリ パラメーターに基づいて生の形式でアラート検出をプルし、独自のグループ化とフィルター処理を適用できます。

## <a name="before-you-begin"></a>はじめに

- 検出をプルするために Microsoft Defender for Endpoint エンドポイントを呼び出す前に、デバイス (AAD) で SIEM 統合アプリケーションAzure Active Directory必要があります。 詳細については [、「Enable SIEM integration in Microsoft Defender for Endpoint」を参照してください](enable-siem-integration.md)。

- Azure アプリケーション登録の次の値をメモしてください。サービスまたはデーモンアプリ内に OAuth フローを構成するにはこれらの値が必要です。
  - アプリケーション ID (アプリケーションで一意)
  - アプリ キー、またはシークレット (アプリケーションで一意)
  - アプリの OAuth 2.0 のトークン エンドポイント
    - この値は、Azure 管理ポータルでアプリのページの下部にある **[エンドポイントの表示]** をクリックすると表示されます。エンドポイントは `https://login.microsoftonline.com/{tenantId}/oauth2/token` のようになります。

## <a name="get-an-access-token"></a>アクセス トークンを取得する

エンドポイントへの呼び出しを作成する前に、アクセス トークンを取得する必要があります。

アクセス トークンを使用して、保護されたリソース (Microsoft Defender for Endpoint での検出) にアクセスします。

アクセス トークンを取得するには、トークン発行エンドポイントに対して POST 要求を実行する必要があります。 要求の例を次に示します。

```http
POST /72f988bf-86f1-41af-91ab-2d7cd011db47/oauth2/token HTTP/1.1
Host: login.microsoftonline.com
Content-Type: application/x-www-form-urlencoded

resource=https%3A%2F%2Fgraph.windows.net&client_id=35e0f735-5fe4-4693-9e68-3de80f1d3745&client_secret=IKXc6PxB2eoFNJ%2FIT%2Bl2JZZD9d9032VXz6Ul3D2WyUQ%3D&grant_type=client_credentials
```

応答には、アクセス トークンと有効期限の情報が含まれます。

```json
{
  "token_type": "Bearer",
  "expires_in": 3599,
  "ext_expires_in": 0,
  "expires_on": 1488720683,
  "not_before": 1488720683,
  "resource": "https://graph.windows.net",
  "access_token":"eyJ0eXaioJJOIneiowiouqSuzNiZ345FYOVkaJL0625TueyaJasjhIjEnbMlWqP..."
}
```

Defender for Endpoint API への要求 *access_tokenフィールドの* 値を使用できます。

## <a name="request"></a>要求

アクセス トークンを使用すると、アプリは Microsoft Defender for Endpoint API に対して認証された要求を行います。 アプリで各要求の Authorization ヘッダーにアクセス トークンを追加する必要があります。

### <a name="request-syntax"></a>要求構文

メソッド|要求 URI
---|---
取得|地域に適用可能な URI を使用します。 <p> **EU の場合**: `https://wdatp-alertexporter-eu.windows.com/api/alerts` <p> **米国の場合**: `https://wdatp-alertexporter-us.windows.com/api/alerts` <p> **英国の場合**: `https://wdatp-alertexporter-uk.windows.com/api/alerts`

### <a name="request-header"></a>要求ヘッダー

ヘッダー|種類|説明|
---|---|---
Authorization|string|必須。 Azure ADベアラー トークンという形式の **アクセス トークンです** &lt;  &gt; 。|

### <a name="request-parameters"></a>要求パラメーター

オプションのクエリ パラメーターを使用して、応答で返されるデータ量を指定および制御します。 パラメーターを指定せずにこのメソッドを呼び出した場合、過去 2 時間の組織のすべての通知が応答に含まれます。

名前|値|説明
---|---|---
sinceTimeUtc|DateTime|フィールドに基づいて、取得される下限時間のアラートを定義します。 <p> `LastProcessedTimeUtc` <p> 時間範囲は次の値です。sinceTimeUtc 時刻から現在の時刻までです。 <p> **注**: 指定しない場合、過去 2 時間に生成されたアラートはすべて取得されます。
untilTimeUtc|DateTime|取得される上限時間のアラートを定義します。 <p> 時間範囲は、次の場合に `sinceTimeUtc` 指定 `untilTimeUtc` します。 <p> **注**: 指定しない場合、既定値は現在の時刻になります。
前|文字列|次の時間範囲のアラートを引き `(current_time - ago)` 出 `current_time` します。 <p> 値は ISO **8601 期間形式に従って** 設定する必要があります <p> 例: `ago=PT10M` 過去 10 分間に受信したアラートをプルします。
limit|int|取得するアラートの数を定義します。 最新のアラートは、定義された番号に基づいて取得されます。<p> **注**: 指定しない場合、時間範囲内で使用可能なすべてのアラートが取得されます。
machinegroups|文字列|アラートをプルするデバイス グループを指定します。 <p> **注**: 指定しない場合、すべてのデバイス グループからのアラートが取得されます。 <p> 例: <br><br> `https://wdatp-alertexporter-eu.securitycenter.windows.com/api/alerts/?machinegroups=UKMachines&machinegroups=FranceMachines`
DeviceCreatedMachineTags|文字列|レジストリからの単一のデバイス タグ。
CloudCreatedMachineTags|文字列|このページで作成されたデバイス Microsoft Defender セキュリティ センター。

### <a name="request-example"></a>要求の例

次の例は、組織内のすべての検出を取得する方法を示しています。

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts
Authorization: Bearer <your access token>
```

次の例は、2016-09-12 00:00:00 以降の最後の 20 件の検出を取得する要求を示しています。

```http
GET  https://wdatp-alertexporter-eu.windows.com/api/alerts?limit=20&sinceTimeUtc=2016-09-12T00:00:00.000
Authorization: Bearer <your access token>
```

## <a name="response"></a>応答

戻り値は、JSON 形式のアラート オブジェクトの配列です。

戻り値の例を次に示します。

```json
[
{
        "AlertTime": "2020-09-30T14:09:20.35743Z",
        "ComputerDnsName": "mymachine1.domain.com",
        "AlertTitle": "Suspicious File Activity",
        "Category": "Malware",
        "Severity": "High",
        "AlertId": "da637370718981685665_16349121",
        "Actor": "",
        "LinkToWDATP": "https://securitycenter.windows.com/alert/da637370718981685665_16349121",
        "IocName": "",
        "IocValue": "",
        "CreatorIocName": "",
        "CreatorIocValue": "",
        "Sha1": "aabbccddee1122334455aabbccddee1122334455",
        "FileName": "cmdParent.exe",
        "FilePath": "C:\\WINDOWS\\SysWOW64\\boo3\\qwerty",
        "IpAddress": "",
        "Url": "",
        "IoaDefinitionId": "b20af1d2-5990-4672-87f1-acc2a8ff7725",
        "UserName": "",
        "AlertPart": 0,
        "FullId": "da637370718981685665_16349121:R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY=",
        "LastProcessedTimeUtc": "2020-09-30T14:11:44.0779765Z",
        "ThreatCategory": "",
        "ThreatFamily": "",
        "ThreatName": "",
        "RemediationAction": "",
        "RemediationIsSuccess": null,
        "Source": "EDR",
        "Md5": "854b85cbff2752fcb88606bca76f83c6",
        "Sha256": "",
        "WasExecutingWhileDetected": null,
        "UserDomain": "",
        "LogOnUsers": "",
        "MachineDomain": "domain.com",
        "MachineName": "mymachine1",
        "InternalIPv4List": "",
        "InternalIPv6List": "",
        "FileHash": "aabbccddee1122334455aabbccddee1122334455",
        "DeviceID": "deadbeef000040830ee54503926f556dcaf82bb0",
        "MachineGroup": "",
        "Description": "Test Alert",
        "DeviceCreatedMachineTags": "",
        "CloudCreatedMachineTags": "",
        "CommandLine": "",
        "IncidentLinkToWDATP": "https://securitycenter.windows.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ReportID": 1053729833,
        "LinkToMTP": "https://security.microsoft.com/alert/da637370718981685665_16349121",
        "IncidentLinkToMTP": "https://security.microsoft.com/incidents/byalert?alertId=da637370718981685665_16349121&source=SIEM",
        "ExternalId": "31DD0A845DDA4059FDEDE031014645350AECABD3",
        "IocUniqueId": "R4xEdgAvDb2LQl3BgHoA3NYqKmRSiIAG7dpxAJCYZhY="
}
]
```

## <a name="code-examples"></a>コード例

### <a name="get-access-token"></a>アクセス トークンの取得

次のコード例は、Microsoft Defender for Endpoint SIEM API を呼び出すアクセス トークンを取得する方法を示しています。

```csharp
AuthenticationContext context = new AuthenticationContext(string.Format("https://login.microsoftonline.com/{0}", tenantId));
ClientCredential clientCredentials = new ClientCredential(clientId, clientSecret);
AuthenticationResult authenticationResult = context.AcquireTokenAsync(detectionsResource, clientCredentials).GetAwaiter().GetResult();
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#Paste below your Tenant ID, App ID and App Secret (App key).
$tenantId = '' ### Paste your tenant ID here
$appId = '' ### Paste your Application ID here
$appSecret = '' ### Paste your Application secret here

$resourceAppIdUri = 'https://graph.windows.net'
$oAuthUri = "https://login.microsoftonline.com/$tenantId/oauth2/token"
$authBody = [Ordered] @{
    resource = "$resourceAppIdUri"
    client_id = "$appId"
    client_secret = "$appSecret"
    grant_type = 'client_credentials'
}

#call API
$authResponse = Invoke-RestMethod -Method Post -Uri $oAuthUri -Body $authBody -ErrorAction Stop
$authResponse
Out-File -FilePath "$scriptDir\LatestSIEM-token.txt" -InputObject $authResponse.access_token
```

```Bash
tenantId='' ### Paste your tenant ID here
appId='' ### Paste your Application ID here
appSecret='' ### Paste your Application secret here
resourceAppIdUri='https://graph.windows.net'
oAuthUri="https://login.microsoftonline.com/$tenantId/oauth2/token"
scriptDir=$(pwd)

apiResponse=$(curl -s X POST "$oAuthUri" -d "resource=$resourceAppIdUri&client_id=$appId&client_secret=$appSecret&\
        grant_type=client_credentials"|cut -d "{" -f2|cut -d "}" -f1)
IFS=","
apiResponseArr=($apiResponse)
IFS=":"
tokenArr=(${apiResponseArr[6]})
echo ${tokenArr[1]}|cut -d "\"" -f2|cut -d "\"" -f1 >> $scriptDir/LatestSIEM-token.txt
```

### <a name="use-token-to-connect-to-the-detections-endpoint"></a>トークンを使用して検出エンドポイントに接続する

次のコード例は、Defender for Endpoint SIEM API を呼び出してアラートを取得するためにアクセス トークンを使用する方法を示しています。

```csharp
HttpClient httpClient = new HttpClient();
httpClient.DefaultRequestHeaders.Authorization = new AuthenticationHeaderValue(authenticationResult.AccessTokenType, authenticationResult.AccessToken);
HttpResponseMessage response = httpClient.GetAsync("https://wdatp-alertexporter-eu.windows.com/api/alert").GetAwaiter().GetResult();
string detectionsJson = response.Content.ReadAsStringAsync().Result;
Console.WriteLine("Got detections list: {0}", detectionsJson);
```

```PowerShell
#Get current working directory
$scriptDir = Split-Path -Path $MyInvocation.MyCommand.Definition -Parent

#run the script Get-Token.ps1  - make sure you are running this script from the same folder of Get-SIEMToken.ps1
$token = Get-Content "$scriptDir\LatestSIEM-token.txt"

#Get Alert from the last xx hours 200 in this example. Make sure you have alerts in that time frame.
$dateTime = (Get-Date).ToUniversalTime().AddHours(-200).ToString("o")

#test SIEM API
$url = 'https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#Set the WebRequest headers
$headers = @{
    'Content-Type' = 'application/json'
    Accept = 'application/json'
    Authorization = "Bearer $token"
}

#Send the webrequest and get the results.
$response = Invoke-WebRequest -Method Get -Uri $url -Headers $headers -ErrorAction Stop
$response
Write-Host

#Extract the alerts from the results. This works for SIEM API:
$alerts =  $response.Content|ConvertFrom-Json|ConvertTo-Json

#Get string with the execution time. We concatenate that string to the output file to avoid overwrite the file
$dateTimeForFileName = Get-Date -Format o|foreach {$_ -replace ":", "."}

#Save the result as json and as csv
$outputJsonPath = "$scriptDir\Latest Alerts $dateTimeForFileName.json"
$outputCsvPath = "$scriptDir\Latest Alerts $dateTimeForFileName.csv"

Out-File -FilePath $outputJsonPath -InputObject $alerts
Get-Content -Path $outputJsonPath -Raw|ConvertFrom-Json|Select-Object -ExpandProperty value|Export-CSV $outputCsvPath -NoTypeInformation
```

```Bash
#Get current working directory
scriptDir=$(pwd)

#get the token
token=$(<$scriptDir/LatestSIEM-token.txt)

#test the SIEM API, get alerts since 1/1/2020
url='https://wdatp-alertexporter-us.windows.com/api/alerts?limit=20&sinceTimeUtc=2020-01-01T00:00:00.000'

#send web requst to API and echo JSON content
apiResponse=$(curl -s X GET "$url" -H "Content-Type: application/json" -H "Accept: application/json"\
         -H "Authorization: Bearer $token"|cut -d "[" -f2|cut -d "]" -f1)
echo "If you see Alert info in JSON format, congratulations you accessed the MDATP SIEM API!"
echo
echo $apiResponse
```

## <a name="error-codes"></a>エラー コード

Microsoft Defender for Endpoint REST API は、無効な要求によって引き起こされた次のエラー コードを返します。

HTTP エラー コード|説明
---|---
401|不正な形式の要求または無効なトークン。
403|承認されていない例外 - テナント管理者によって管理されていないドメインまたはテナントの状態が削除されます。
500|サービスのエラー。

## <a name="related-topics"></a>関連項目

- [エンドポイント向け Microsoft Defender で SIEM 統合を有効にする](enable-siem-integration.md)
- [エンドポイント検出用の Microsoft Defender をプルする ArcSight の構成](configure-arcsight.md)
- [SIEM ツールへの検出のプル](configure-siem.md)
- [Microsoft Defender for Endpoint Detection フィールド](api-portal-mapping.md)
- [SIEM ツール統合に関する問題のトラブルシューティング](troubleshoot-siem.md)
