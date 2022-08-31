---
title: ユーザーの代わりにMicrosoft 365 Defender API にアクセスするアプリを作成する
description: ユーザーの代わりにMicrosoft 365 Defender API にアクセスする方法について説明します。
keywords: access, ユーザーに代わって, API, アプリケーション, ユーザー, アクセス トークン, トークン,
search.product: eADQiWindows 10XVcnh
ms.service: microsoft-365-security
ms.subservice: m365d
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
ms.custom: api
ms.openlocfilehash: b7fa369729873b21b3e775b3b3fdb2e26c9130f6
ms.sourcegitcommit: 10e6abe740e27000e223378eb17d657a47555fa8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/31/2022
ms.locfileid: "67479446"
---
# <a name="create-an-app-to-access-microsoft-365-defender-apis-on-behalf-of-a-user"></a>ユーザーの代わりにMicrosoft 365 Defender API にアクセスするアプリを作成する

[!INCLUDE [Microsoft 365 Defender rebranding](../includes/microsoft-defender.md)]

**適用対象:**

- Microsoft 365 Defender

> [!IMPORTANT]
> 一部の情報は、市販される前に大幅に変更される可能性があるプレリリース製品に関するものです。 Microsoft は、ここに記載された情報に関して、明示または黙示を問わず、いかなる保証も行いません。

このページでは、1 人のユーザーに代わってMicrosoft 365 Defenderにプログラムでアクセスするアプリケーションを作成する方法について説明します。

ユーザーが定義されていないMicrosoft 365 Defenderにプログラムでアクセスする必要がある場合 (たとえば、バックグラウンド アプリやデーモンを作成している場合)、[ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリの作成に関するページを](api-create-app-web.md)参照してください。 大規模な組織や顧客のグループにサービスを提供している場合など、複数のテナントにアクセス権を提供する必要がある場合は、「[Microsoft 365 Defender API へのパートナー アクセス権を持つアプリを作成する」を](api-partner-access.md)参照してください。必要なアクセスの種類がわからない場合は、「[作業の開始](api-access.md)」を参照してください。

Microsoft 365 Defenderは、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API は、ワークフローを自動化し、Microsoft 365 Defenderの機能を利用するのに役立ちます。 この API アクセスには、OAuth2.0 認証が必要です。 詳細については、「 [OAuth 2.0 承認コード フロー」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)参照してください。

一般に、これらの API を使用するには、次の手順を実行する必要があります。

- Azure Active Directory (Azure AD) アプリケーションを作成します。
- このアプリケーションを使用してアクセス トークンを取得します。
- トークンを使用して、Microsoft 365 Defender API にアクセスします。

この記事では、次の方法について説明します。

- Azure AD アプリケーションを作成する
- Microsoft 365 Defenderへのアクセス トークンを取得する
- トークンを検証する

> [!NOTE]
> ユーザーの代わりにMicrosoft 365 Defender API にアクセスする場合は、適切なアプリケーションのアクセス許可とユーザーのアクセス許可が必要です。

> [!TIP]
> ポータルでアクションを実行する権限がある場合は、API でアクションを実行する権限があります。

## <a name="create-an-app"></a>アプリを作成する

1. **グローバル管理者** ロールを持つユーザーとして [Azure](https://portal.azure.com) にサインインします。

2. **Azure Active Directory** >  **に移動アプリの登録** > **新しい登録**。

   :::image type="content" source="../../media/atp-azure-new-app2.png" alt-text="Azure portalの [管理] ウィンドウの [新しい登録] オプション" lightbox="../../media/atp-azure-new-app2.png":::

3. フォームで、アプリケーションの名前を選択し、リダイレクト URI に次の情報を入力して、[ **登録**] を選択します。

   :::image type="content" source="../../media/nativeapp-create2.PNG" alt-text="Azure portalのアプリケーション登録ウィンドウ" lightbox="../../media/nativeapp-create2.PNG":::
   

   - **アプリケーションの種類:** パブリック クライアント
   - **リダイレクト URI:** https://portal.azure.com

4. アプリケーション ページで、組織が>**を使用する** **API アクセス許可** > **の追加アクセス許可** >  API を選択し、「**Microsoft Threat Protection」** と入力して、**Microsoft Threat Protection** を選択します。 これで、アプリはMicrosoft 365 Defenderにアクセスできるようになりました。

   > [!TIP]
   > *Microsoft Threat Protection* はMicrosoft 365 Defenderの以前の名前であり、元の一覧には表示されません。 テキスト ボックスに名前を書き込み始めて、その名前が表示されるのを確認する必要があります。

   :::image type="content" source="../../media/apis-in-my-org-tab.PNG" alt-text="Microsoft 365 Defender ポータルの組織の [API] ウィンドウ" lightbox="../../media/apis-in-my-org-tab.PNG":::

   - [ **委任されたアクセス許可]** を選択します。 シナリオに関連するアクセス許可 ( **Incident.Read** など) を選択し、[ **アクセス許可の追加]** を選択します。

     :::image type="content" source="../../media/request-api-permissions-delegated.PNG" alt-text="Microsoft 365 Defender ポータルの [委任されたアクセス許可] ウィンドウ" lightbox="../../media/request-api-permissions-delegated.PNG":::

    > [!NOTE]
    > シナリオに関連するアクセス許可を選択する必要があります。 *すべてのインシデントを読み取* るは、単なる例です。 必要なアクセス許可を確認するには、呼び出す API の **[アクセス許可]** セクションを参照してください。
    >
    > たとえば、 [高度なクエリを実行するには、[高度なクエリ](api-advanced-hunting.md)の実行] アクセス許可を選択します。 [デバイスを分離](/windows/security/threat-protection/microsoft-defender-atp/isolate-machine)するには、"マシンの分離" アクセス許可を選択します。

5. [ **管理者の同意を付与する]** を選択します。 アクセス許可を追加するたびに、[ **管理者の同意を付与** する] を選択して有効にする必要があります。

   :::image type="content" source="../../media/grant-consent-delegated.PNG" alt-text="Microsoft 365 Defender ポータルの [管理者の同意の付与] ウィンドウ" lightbox="../../media/grant-consent-delegated.PNG":::

6. アプリケーション ID とテナント ID を安全な場所に記録します。 アプリケーション ページの [ **概要]** に一覧表示されます。

   :::image type="content" source="../../media/app-and-tenant-ids.png" alt-text="Microsoft 365 Defender ポータルの [概要] ウィンドウ" lightbox="../../media/app-and-tenant-ids.png":::

## <a name="get-an-access-token"></a>アクセス トークンを取得する

Azure Active Directory トークンの詳細については、 [Azure AD のチュートリアル](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)を参照してください。

### <a name="get-an-access-token-on-behalf-of-a-user-using-powershell"></a>PowerShell を使用してユーザーに代わってアクセス トークンを取得する

委任されたアクセス許可を持つアクセス トークンを取得するには、MSAL.PS ライブラリを使用します。 次のコマンドを実行して、ユーザーの代わりにアクセス トークンを取得します。

```PowerShell
Install-Module -Name MSAL.PS # Install the MSAL.PS module from PowerShell Gallery

$TenantId = " " # Paste your directory (tenant) ID here.
$AppClientId="xxxxxxxx-xxxx-xxxx-xxxx-xxxxxxxxxxxx" # Paste your application (client) ID here.

$MsalParams = @{
   ClientId = $AppClientId
   TenantId = $TenantId
   Scopes   = 'https://graph.microsoft.com/User.Read.All','https://graph.microsoft.com/Files.ReadWrite'
}

$MsalResponse = Get-MsalToken @MsalParams
$AccessToken  = $MsalResponse.AccessToken
 
$AccessToken # Display the token in PS console
```
## <a name="validate-the-token"></a>トークンを検証する

1. トークンをコピーして [JWT](https://jwt.ms) に貼り付けてデコードします。
2. デコードされたトークン内の *ロール* 要求に必要なアクセス許可が含まれていることを確認します。

次の図では、アプリから取得したデコードされたトークンと、アクセス許可、および```AdvancedHunting.Read.All```アクセス許可を```Incidents.Read.All``````Incidents.ReadWrite.All```確認できます。

:::image type="content" source="../../media/defender-endpoint/webapp-decoded-token.png" alt-text="Microsoft 365 Defender ポータルの [デコードされたトークン] ウィンドウの [アクセス許可] セクション" lightbox="../../media/defender-endpoint/webapp-decoded-token.png":::

## <a name="use-the-token-to-access-the-microsoft-365-defender-api"></a>トークンを使用してMicrosoft 365 Defender API にアクセスする

1. 使用する API (インシデント、または高度な捜索) を選択します。 詳細については、「[サポートされているMicrosoft 365 Defender API」を参照してください](api-supported.md)。
2. 送信しようとしている http 要求で、承認ヘッダー `"Bearer" <token>`を 、承認スキームである *ベアラー* 、検証済み *トークンであるトークン* に設定します。
3. トークンの有効期限は 1 時間以内です。 この間に、同じトークンを使用して複数の要求を送信できます。

次の例は、 **C# を使用して** インシデントの一覧を取得する要求を送信する方法を示しています。

```C#
    var httpClient = new HttpClient();
    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.security.microsoft.com/api/incidents");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();
```

## <a name="related-articles"></a>関連記事

- [Microsoft 365 Defender API の概要](api-overview.md)
- [Microsoft 365 Defender API にアクセスする](api-access.md)
- ["Hello world" アプリを作成する](api-hello-world.md)
- [ユーザーなしでMicrosoft 365 Defenderにアクセスするアプリを作成する](api-create-app-web.md)
- [Microsoft 365 Defender API へのマルチテナント パートナー アクセス権を持つアプリを作成する](api-partner-access.md)
- [API の制限とライセンスについて学習する](api-terms.md)
- [エラー コードについて](api-error-codes.md)
- [ユーザー サインインと API アクセスに対する OAuth 2.0 承認](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)
