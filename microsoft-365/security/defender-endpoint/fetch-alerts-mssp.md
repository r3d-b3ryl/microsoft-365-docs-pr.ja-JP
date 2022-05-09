---
title: MSSP カスタマー テナントからアラートをフェッチする
description: 顧客テナントからアラートをフェッチする方法について説明します
keywords: マネージド セキュリティ サービス プロバイダー、mssp、構成、統合
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
ms.technology: mde
ms.custom: api
ms.openlocfilehash: e2ac36689f9f41badb2f4216198d8818e568778b
ms.sourcegitcommit: 986ea76ecaceb5fe6b9616e553003e3c5b0df2e7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 01/25/2022
ms.locfileid: "62214179"
---
# <a name="fetch-alerts-from-mssp-customer-tenant"></a>MSSP カスタマー テナントからアラートをフェッチする

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]

**適用対象:**
- [Microsoft Defender for Endpoint Plan 1](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft 365 Defender](https://go.microsoft.com/fwlink/?linkid=2118804)

> [!NOTE]
> このアクションは、MSSP によって実行されます。

アラートをフェッチするには、次の 2 つの方法があります。

- SIEM メソッドの使用
- API の使用

## <a name="fetch-alerts-into-your-siem"></a>SIEM にアラートをフェッチする

SIEM システムにアラートをフェッチするには、次の手順を実行する必要があります。

- 手順 1: サード パーティ製アプリケーションを作成する
- 手順 2: 顧客のテナントからトークンにアクセスして更新する
- 手順 3: アプリケーションをMicrosoft 365 Defenderで許可する

### <a name="step-1-create-an-application-in-azure-active-directory-azure-ad"></a>手順 1: Azure Active Directoryでアプリケーションを作成する (Azure AD)

アプリケーションを作成し、顧客のMicrosoft 365 Defenderテナントからアラートをフェッチするアクセス許可を付与する必要があります。

1. [Azure AD ポータル](https://aad.portal.azure.com/)にサインインします。

2. **アプリの登録Azure Active Directory**\>選択 **します。**

3. [ **新規登録**] をクリックします。

4. 次の値を指定します。

    - 名前: \<Tenant_name\> SIEM MSSP コネクタ (Tenant_nameをテナント表示名に置き換えます)

    - サポートされているアカウントの種類: この組織のディレクトリ内のアカウントのみ
    - リダイレクト URI: [Web] を選択して入力します `https://<domain_name>/SiemMsspConnector`(<domain_name>をテナント名に置き換えます)

5. **[登録]** をクリックします。 アプリケーションは、所有しているアプリケーションの一覧に表示されます。

6. アプリケーションを選択し、[ **概要**] をクリックします。

7. **[アプリケーション (クライアント) ID**] フィールドの値を安全な場所にコピーします。次の手順で必要になります。

8. 新しいアプリケーション パネルで [ **証明書&シークレット** ] を選択します。

9. [ **新しいクライアント シークレット**] をクリックします。

    - 説明: キーの説明を入力します。
    - 有効期限: **[1 年間]** を選択する

10. [ **追加]** をクリックし、クライアント シークレットの値を安全な場所にコピーします。次の手順で必要になります。

### <a name="step-2-get-access-and-refresh-tokens-from-your-customers-tenant"></a>手順 2: 顧客のテナントからトークンにアクセスして更新する

このセクションでは、PowerShell スクリプトを使用して顧客のテナントからトークンを取得する方法について説明します。 このスクリプトでは、前の手順のアプリケーションを使用して、OAuth 承認コード Flowを使用してアクセス トークンと更新トークンを取得します。

資格情報を指定した後、アプリケーションが顧客のテナントにプロビジョニングされるように、アプリケーションに同意を付与する必要があります。

1. 新しいフォルダーを作成し、名前を付けます。 `MsspTokensAcquisition`

2. [LoginBrowser.psm1 モジュールを](https://github.com/shawntabrizi/Microsoft-Authentication-with-PowerShell-and-MSAL/blob/master/Authorization%20Code%20Grant%20Flow/LoginBrowser.psm1)ダウンロードし、フォルダーに`MsspTokensAcquisition`保存します。

    > [!NOTE]
    > 30 行目で、 `authorzationUrl` `authorizationUrl`.

3. 次のコンテンツを含むファイルを作成し、フォルダーに名前 `MsspTokensAcquisition.ps1` を付けて保存します。

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
4. フォルダーで管理者特権の PowerShell コマンド プロンプトを `MsspTokensAcquisition` 開きます。

5. 次のコマンドを実行します。`Set-ExecutionPolicy -ExecutionPolicy Bypass`

6. 次のコマンドを入力します。 `.\MsspTokensAcquisition.ps1 -clientId <client_id> -secret <app_key> -tenantId <customer_tenant_id>`

    - 前の手順で取得した **アプリケーション (クライアント) ID に** 置き換えます\<client_id\>。
    - 前の手順で作成した **クライアント シークレット** に置き換えます\<app_key\>。
    - 顧客の **テナント ID に** 置き換えます\<customer_tenant_id\>。

7. 資格情報と同意を入力するように求められます。 ページ リダイレクトを無視します。

8. PowerShell ウィンドウには、アクセス トークンと更新トークンが表示されます。 更新トークンを保存して SIEM コネクタを構成します。

### <a name="step-3-allow-your-application-on-microsoft-365-defender"></a>手順 3: アプリケーションをMicrosoft 365 Defenderで許可する

Microsoft 365 Defenderで作成したアプリケーションを許可する必要があります。

アプリケーションを許可するには、 **ポータル システム設定の管理** アクセス許可が必要です。 それ以外の場合は、アプリケーションを許可するように顧客に要求する必要があります。

1. に移動します `https://security.microsoft.com?tid=<customer_tenant_id>` (顧客のテナント ID に置き換えます \<customer_tenant_id\> 。

2. [**設定** \> **エンドポイント** \> **API SIEM] を**\>クリックします。

3. **[MSSP**] タブを選択します。

4. 最初の手順から **アプリケーション ID と****テナント ID を入力します**。

5. [ **アプリケーションの承認]** をクリックします。

これで、SIEM に関連する構成ファイルをダウンロードし、Microsoft 365 Defender API に接続できます。 詳細については、「 [SIEM ツールにアラートをプルする」を参照してください](configure-siem.md)。

- ArcSight 構成ファイル /Splunk Authentication Properties ファイルで、シークレット値を設定してアプリケーション キーを手動で書き込みます。
- ポータルで更新トークンを取得する代わりに、前の手順のスクリプトを使用して更新トークンを取得します (または、他の方法で取得します)。

## <a name="fetch-alerts-from-mssp-customers-tenant-using-apis"></a>API を使用して MSSP 顧客のテナントからアラートをフェッチする

REST API を使用してアラートをフェッチする方法については、「 [MSSP カスタマー テナントからアラートをフェッチする](fetch-alerts-mssp.md)」を参照してください。

## <a name="see-also"></a>関連項目

- [ポータルへの MSSP アクセスを許可する](grant-mssp-access.md)
- [MSSP カスタマー ポータルにアクセスする](access-mssp-portal.md)
- [アラート通知を構成する](configure-mssp-notifications.md)
