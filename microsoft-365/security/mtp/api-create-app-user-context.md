---
title: ユーザーの代わりに Microsoft 365 Defender API にアクセスするアプリを作成する
description: ユーザーの代わりに Microsoft 365 Defender API にアクセスする方法について説明します。
keywords: access, onhalf of user, api, application, user, access token, token,
search.product: eADQiWindows 10XVcnh
ms.prod: microsoft-365-enterprise
ms.mktglfcycl: deploy
ms.sitesec: library
ms.pagetype: security
f1.keywords:
- NOCSH
ms.author: macapara
author: mjcaparas
ms.localizationpriority: medium
manager: dansimp
audience: ITPro
ms.collection: M365-security-compliance
ms.topic: conceptual
search.appverid:
- MOE150
- MET150
ms.openlocfilehash: f1c0caea9ff7810f79026c789241a4f250ec5303
ms.sourcegitcommit: d6b1da2e12d55f69e4353289e90f5ae2f60066d0
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 12/19/2020
ms.locfileid: "49719418"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>ユーザーの代わりに Microsoft 365 Defender API にアクセスするアプリを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、製品のリリース前に大幅に変更される可能性があるプレリリース製品に関連しています。 Microsoft makes no warranties, express or implied, with respect to the information provided here.

このページでは、1 人のユーザーの代わりに Microsoft 365 Defender にプログラムでアクセスするアプリケーションを作成する方法について説明します。

定義されたユーザーなしで Microsoft 365 Defender にプログラムでアクセスする必要がある場合 (たとえば、バックグラウンド アプリやデーモンを作成している場合)、「ユーザーなしで [Microsoft 365 Defender](api-create-app-web.md)にアクセスするアプリを作成する」を参照してください。 大規模な組織や顧客のグループにサービスを提供している場合など、複数のテナントへのアクセスを提供する必要がある場合は [、「Microsoft 365 Defender](api-partner-access.md)API へのパートナー アクセスを持つアプリを作成する」を参照してください。必要なアクセスの種類が不明な場合は、「開始する」を [参照してください](api-access.md)。

Microsoft 365 Defender は、一連のプログラム API を通じてデータとアクションの多くを公開します。 これらの API は、ワークフローを自動化し、Microsoft 365 Defender の機能を利用するのに役立ちます。 この API アクセスには OAuth2.0 認証が必要です。 詳細については [、「OAuth 2.0 認証コード フロー」を参照してください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)。

一般に、これらの API を使用するには、次の手順を実行する必要があります。

- Azure Active Directory (Azure AD) アプリケーションを作成します。
- このアプリケーションを使用してアクセス トークンを取得します。
- トークンを使用して Microsoft 365 Defender API にアクセスします。

この記事では、次の方法について説明します。

- Azure AD アプリケーションを作成する
- Microsoft 365 Defender へのアクセス トークンを取得する
- トークンを検証する

> [!NOTE]
> ユーザーの代わりに Microsoft 365 Defender API にアクセスする場合は、適切なアプリケーションのアクセス許可とユーザーのアクセス許可が必要です。

> [!TIP]
> ポータルでアクションを実行するアクセス許可がある場合は、API でアクションを実行するアクセス許可を持っている。

## <a name="create-an-app"></a>アプリを作成する

1. グローバル管理者ロール [を持](https://portal.azure.com) つユーザーとして Azure **にサインイン** します。

2. Azure **Active Directory アプリの**  >  **登録新規登録**  >  **に移動します**。

   ![Microsoft Azure の画像とアプリケーション登録へのナビゲーション](../../media/atp-azure-new-app2.png)

3. In the form, choose a name for your application and enter the following information for the redirect URI, then select **Register**.

   ![[アプリケーションの作成] ウィンドウの画像](../../media/nativeapp-create2.PNG)

   - **アプリケーションの種類:** パブリック クライアント
   - **リダイレクト URI:**https://portal.azure.com

4. アプリケーション ページで **、[API アクセス** 許可の追加] アクセス許可 API を選択し、組織で > を使用して  >    >  **、「Microsoft Threat Protection」** と入力し **、[Microsoft Threat Protection] を選択します**。 これで、アプリは Microsoft 365 Defender にアクセスできます。

   > [!TIP]
   > *Microsoft Threat Protection* は Microsoft 365 Defender の元の名前であり、元のリストには表示されません。 表示するには、テキスト ボックスに名前を書き込む必要があります。

   ![API アクセス許可の選択の画像](../../media/apis-in-my-org-tab.PNG)

   - 委任 **されたアクセス許可を選択します**。 シナリオに関連するアクセス許可 **(Incident.Read** など) を選択し、[アクセス許可の追加 **] を選択します**。

   ![API アクセスと API の選択の画像](../../media/request-api-permissions-delegated.PNG)

    > [!NOTE]
    > シナリオに関連するアクセス許可を選択する必要があります。 *すべてのインシデントの読み取り* は単なる例です。 必要なアクセス許可を確認するには、呼び出す API の **[** アクセス許可] セクションを参照してください。
    >
    > たとえば、高度な [クエリを実行するには、[](api-advanced-hunting.md)高度なクエリの実行] 権限を選択します。デバイス [を分離するには、[](https://docs.microsoft.com/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)コンピューターの分離] アクセス許可を選択します。

5. [管理者 **の同意を付与する] を選択します**。 アクセス許可を追加する度に、そのアクセス許可を有効にするための **管理者** の同意を付与するを選択する必要があります。

   ![アクセス許可の付与の画像](../../media/grant-consent-delegated.PNG)

6. アプリケーション ID とテナント ID を安全な場所に記録します。 アプリケーション ページの [概要] **に** 一覧表示されます。

   ![作成されたアプリ ID の画像](../../media/app-and-tenant-ids.png)

## <a name="get-an-access-token"></a>アクセス トークンを取得する

Azure Active Directory トークンについて詳しくは、Azure Active Directory のチュートリアル [AD覧ください](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)。

### <a name="get-an-access-token-using-powershell"></a>PowerShell を使用してアクセス トークンを取得する

```PowerShell
if(!(Get-Package adal.ps)) { Install-Package -Name adal.ps } # Install the ADAL.PS package in case it's not already present

$tenantId = '' # Paste your directory (tenant) ID here.
$clientId = '' # Paste your application (client) ID here.
$redirectUri = '' # Paste your app's redirection URI

$authority = "https://login.windows.net/$tenantId"
$resourceUrl = 'https://api.security.microsoft.com'

$response = Get-ADALToken -Resource $resourceUrl -ClientId $cleintId -RedirectUri $redirectUri -Authority $authority -PromptBehavior:Always
$response.AccessToken | clip

$response.AccessToken
```

## <a name="validate-the-token"></a>トークンを検証する

1. トークンをコピーして [JWT に貼り付](https://jwt.ms) け、デコードします。
1. デコードされたトークン内 *のロール* クレームに必要なアクセス許可が含まれている必要があります。

次の図では、アプリから取得したデコードされたトークンと、アクセス許可 ```Incidents.Read.All``` ```Incidents.ReadWrite.All``` を ```AdvancedHunting.Read.All``` 確認できます。

![トークン検証の画像](../../media/webapp-decoded-token.png)

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>トークンを使用して Microsoft 365 Defender API にアクセスする

1. 使用する API (インシデントまたは高度な検索) を選択します。 詳細については、「サポートされている [Microsoft 365 Defender API」を参照してください](api-supported.md)。
2. 送信する http 要求で、承認ヘッダーを 、承認スキームである `"Bearer" <token>` *Bearer、* 検証済みトークンであるトークンに設定します。
3. トークンは 1 時間以内に期限切れになります。 この間は、同じトークンを使用して複数の要求を送信できます。

次の例は、C# を使用してインシデントの一覧を取得する要求を送信 **する方法を示しています**。

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [Microsoft 365 Defender API へのアクセス](api-access.md)
- ["Hello world" アプリを作成する](api-hello-world.md)
- [ユーザーなしで Microsoft 365 Defender にアクセスするアプリを作成する](api-create-app-web.md)
- [マルチテナント パートナーが Microsoft 365 Defender API にアクセスできるアプリを作成する](api-partner-access.md)
- [API の制限とライセンスについて](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [ユーザー サインインと API アクセスの OAuth 2.0 承認](https://docs.microsoft.com/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
