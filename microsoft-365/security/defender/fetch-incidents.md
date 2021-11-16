---
title: インシデントMicrosoft 365 Defenderフェッチ
description: 顧客テナントからインシデントMicrosoft 365 Defender取得する方法について学習する
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
search.product: eADQiWindows 10XVcnh
search.appverid: met150
ms.prod: m365-security
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: article
ms.technology: m365d
ms.custom: api
ms.openlocfilehash: 1ea39bfce5303360165a56d6361908d1014d370f
ms.sourcegitcommit: e110f00dc6949a7a1345187375547beeb64225b2
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/06/2021
ms.locfileid: "60805029"
---
# <a name="fetch-microsoft-365-defender-incidents"></a>インシデントMicrosoft 365 Defenderフェッチ 

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)


> [!NOTE]
> このアクションは MSSP によって実行されます。

アラートを取得するには、次の 2 つの方法があります。

- SIEM メソッドの使用
- API の使用

## <a name="fetch-incidents-into-your-siem"></a>SIEM にインシデントをフェッチする

SIEM システムにインシデントをフェッチするには、次の手順を実行する必要があります。

- 手順 1: サード パーティ製アプリケーションを作成する
- 手順 2: 顧客のテナントからアクセストークンと更新トークンを取得する
- 手順 3: アプリケーションのインストールを許可Microsoft 365 Defender

### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>手順 1: アプリケーションを作成する (Azure Active Directory) (Azure AD)

アプリケーションを作成し、顧客のテナントからアラートを取得するためのアクセス許可を付与Microsoft 365 Defenderがあります。

1. ポータルにサインイン[Azure ADします](https://aad.portal.azure.com/)。

2. [アプリ \> **Azure Active Directory] を選択します**。

3. [新規 **登録] をクリックします**。

4. 次の値を指定します。

    - 名前: \<Tenant_name\> SIEM MSSP コネクタ (Tenant_name表示名に置き換える)

    - サポートされているアカウントの種類: この組織ディレクトリのアカウントのみ
    - リダイレクト URI: [Web] を選択して入力 `https://<domain_name>/SiemMsspConnector` します (<domain_name>テナント名に置き換えてください)

5. **[登録]** をクリックします。 アプリケーションは、所有するアプリケーションの一覧に表示されます。

6. アプリケーションを選択し、[概要] を **クリックします**。

7. [アプリケーション (クライアント **) ID]** フィールドの値を安全な場所にコピーすると、次の手順でこの値が必要になります。

8. 新 **しいアプリケーション パネル& [** 証明書の秘密] を選択します。

9. [新 **しいクライアント シークレット] をクリックします**。

    - 説明: キーの説明を入力します。
    - 有効期限: **[1 年間] を選択します。**

10. [ **追加]** をクリックし、クライアント シークレットの値を安全な場所にコピーします。次の手順でこれを行う必要があります。

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>手順 2: 顧客のテナントからアクセストークンと更新トークンを取得する

このセクションでは、PowerShell スクリプトを使用して顧客のテナントからトークンを取得する方法について説明します。 このスクリプトでは、前の手順のアプリケーションを使用して、OAuth 認証コード を使用してアクセス トークンと更新トークンを取得Flow。

資格情報を指定した後、アプリケーションが顧客のテナントにプロビジョニングされるので、アプリケーションに同意を与える必要があります。

1. 新しいフォルダーを作成し、名前を付きます `MsspTokensAcquisition` 。

2. [LoginBrowser.psm1 モジュールをダウンロードし](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1)、フォルダーに保存 `MsspTokensAcquisition` します。

    > [!NOTE]
    > 30 行目で、 に置き `authorzationUrl` 換える `authorizationUrl` 。

3. 次の内容のファイルを作成し、フォルダーに名前 `MsspTokensAcquisition.ps1` を付けて保存します。

    ```powershell
    param (
        [Parameter(Mandatory=$true)][string]$clientId,
        [Parameter(Mandatory=$true)][string]$secret,
        [Parameter(Mandatory=$true)][string]$tenantId
    )
    [Net.ServicePointManager]::SecurityProtocol = [Net.SecurityProtocolType]::Tls12

    # Load our Login Browser Function
    Import-Module .\LoginBrowser.psm1

    # Configuration parameters
    $login = "https://login.microsoftonline.com"
    $redirectUri = "https://SiemMsspConnector"
    $resourceId = "https://graph.windows.net"

    Write-Host 'Prompt the user for his credentials, to get an authorization code'
    $authorizationUrl = ("{0}/{1}/oauth2/authorize?prompt=select_account&response_type=code&client_id={2}&redirect_uri={3}&resource={4}" -f
                        $login, $tenantId, $clientId, $redirectUri, $resourceId)
    Write-Host "authorzationUrl: $authorizationUrl"

    # Fake a proper endpoint for the Redirect URI
    $code = LoginBrowser $authorizationUrl $redirectUri

    # Acquire token using the authorization code

    $Body = @{
        grant_type = 'authorization_code'
        client_id = $clientId
        code = $code
        redirect_uri = $redirectUri
        resource = $resourceId
        client_secret = $secret
    }

    $tokenEndpoint = "$login/$tenantId/oauth2/token?"
    $Response = Invoke-RestMethod -Method Post -Uri $tokenEndpoint -Body $Body
    $token = $Response.access_token
    $refreshToken= $Response.refresh_token

    Write-Host " ----------------------------------- TOKEN ---------------------------------- "
    Write-Host $token

    Write-Host " ----------------------------------- REFRESH TOKEN ---------------------------------- "
    Write-Host $refreshToken
    ```
4. フォルダーで管理者特権の PowerShell コマンド プロンプトを開 `MsspTokensAcquisition` きます。

5. 次のコマンドを実行します。`Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. 次のコマンドを入力します。 `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`

    - 前 \<client_id\> の手順 **で取得したアプリケーション (クライアント) ID** に置き換えてください。
    - 前 \<app_key\> の手順 **で作成した** クライアント シークレットに置き換える。
    - 顧客 \<customer_tenant_id\> のテナント ID **に置き換える**。

7. 資格情報と同意を入力する必要があります。 ページ リダイレクトを無視します。

8. PowerShell ウィンドウで、アクセス トークンと更新トークンを受け取ります。 SIEM コネクタを構成するには、更新トークンを保存します。

### <a name="step-3-allow-your-application-on-microsoft-365-defender"></a>手順 3: アプリケーションのインストールを許可Microsoft 365 Defender

アプリで作成したアプリケーションを許可するMicrosoft 365 Defender。

アプリケーションを許可するには、ポータル システム設定の **管理** 権限が必要です。 それ以外の場合は、アプリケーションを許可する顧客を要求する必要があります。

1. に移動 `https://security.microsoft.com?tid=<customer_tenant_id>` します ( \<customer_tenant_id\> 顧客のテナント ID に置き換えてください。

2. [**エンドポイント 設定** \>  \> **SIEM] を** \> **クリックします**。

3. **[MSSP] タブを選択** します。

4. 最初の **手順とテナント ID** からアプリケーション ID を **入力します**。

5. [アプリケーション **の承認] をクリックします**。

これで、SIEM に関連する構成ファイルをダウンロードし、その API にMicrosoft 365 Defenderできます。 詳細については、「SIEM ツールにアラート [をプルする」を参照してください](../defender-endpoint/configure-siem.md)。

- ArcSight 構成ファイル / Splunk Authentication Properties ファイルで、シークレット値を設定してアプリケーション キーを手動で記述します。
- ポータルで更新トークンを取得する代わりに、前の手順のスクリプトを使用して更新トークンを取得 (または他の方法で取得) します。

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>API を使用して MSSP 顧客のテナントからアラートを取得する

REST API を使用してアラートをフェッチする方法については、「REST API を使用 [してアラートをプルする」を参照してください](../defender-endpoint/pull-alerts-using-rest-api.md)。