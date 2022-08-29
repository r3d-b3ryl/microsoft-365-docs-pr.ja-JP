---
title: Microsoft Defender for Endpoint API を使用する
ms.reviewer: ''
description: ユーザーなしでMicrosoft Defender for Endpointにプログラムでアクセスできるようにネイティブ Windows アプリを設計する方法について説明します。
keywords: apis, graph api, サポートされている API, アクター, アラート, デバイス, ユーザー, ドメイン, IP, ファイル, 高度な捜索, クエリ
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
ms.openlocfilehash: c7adaa79ef98b0ccfc1c12e2f84b30c8cd5600fe
ms.sourcegitcommit: 217108c59be41b01963a393b4f16d137636fe6a8
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 08/12/2022
ms.locfileid: "67327906"
---
# <a name="use-microsoft-defender-for-endpoint-apis"></a>Microsoft Defender for Endpoint API を使用する

[!INCLUDE [Microsoft 365 Defender rebranding](../../includes/microsoft-defender.md)]


**適用対象:**
- [Microsoft Defender for Endpoint Plan 2](https://go.microsoft.com/fwlink/?linkid=2154037)
- [Microsoft Defender for Business](../defender-business/index.yml)

> [!IMPORTANT]
> 高度なハンティング機能は Defender for Business には含まれません。 [Microsoft Defender for Endpoint プラン 1 とMicrosoft Defender for Businessを比較する方法 2 を](../defender-business/compare-mdb-m365-plans.md#compare-microsoft-defender-for-business-to-microsoft-defender-for-endpoint-plans-1-and-2)参照してください。


> Microsoft Defender ATP を試してみたいですか? [無料試用版にサインアップしてください。](https://signup.microsoft.com/create-account/signup?products=7f379fee-c4f9-4278-b0a1-e4c8c2fcdf7e&ru=https://aka.ms/MDEp2OpenTrial?ocid=docs-wdatp-exposedapis-abovefoldlink)

[!include[Microsoft Defender for Endpoint API URIs for US Government](../../includes/microsoft-defender-api-usgov.md)]

[!include[Improve request performance](../../includes/improve-request-performance.md)]

このページでは、ユーザーに代わって Defender for Endpoint へのプログラムによるアクセスを取得するアプリケーションを作成する方法について説明します。

ユーザーなしでプログラムによるアクセス Microsoft Defender for Endpointが必要な場合は、「[アプリケーション コンテキストを使用したアクセス Microsoft Defender for Endpoint](exposed-apis-create-app-webapp.md)」を参照してください。

必要なアクセスが不明な場合は、 [概要ページ](apis-intro.md)を参照してください。

Microsoft Defender for Endpointは、一連のプログラム API を通じて、そのデータとアクションの多くを公開します。 これらの API を使用すると、作業フローを自動化し、Microsoft Defender for Endpoint機能に基づいてイノベーションを行います。 API アクセスには、OAuth2.0 認証が必要です。 詳細については、「 [OAuth 2.0 承認コード フロー」を](/azure/active-directory/develop/active-directory-v2-protocols-oauth-code)参照してください。

一般に、API を使用するには、次の手順を実行する必要があります。

- AAD アプリケーションを作成する
- このアプリケーションを使用してアクセス トークンを取得する
- トークンを使用して Defender for Endpoint API にアクセスする

このページでは、AAD アプリケーションを作成し、アクセス トークンを取得してMicrosoft Defender for Endpointし、トークンを検証する方法について説明します。

> [!NOTE]
> ユーザーの代わりに api Microsoft Defender for Endpointアクセスする場合は、正しいアプリケーションのアクセス許可とユーザーのアクセス許可が必要です。
> Microsoft Defender for Endpointに対するユーザーアクセス許可に慣れていない場合は、「[ロールベースのアクセス制御を使用したポータル アクセスの管理](rbac.md)」を参照してください。

> [!TIP]
> ポータルでアクションを実行する権限がある場合は、API でアクションを実行する権限があります。

## <a name="create-an-app"></a>アプリを作成する

1. **グローバル管理者** ロールを持つユーザー アカウントを使用して [Azure](https://portal.azure.com) にログオンします。

2. **Azure Active Directory** \> **アプリの登録** \> **新しい登録** に移動します。

   :::image type="content" source="images/atp-azure-new-app2.png" alt-text="Microsoft Azure portalの [アプリの登録] ページ" lightbox="images/atp-azure-new-app2.png":::

3. [**アプリケーションの登録**] ページが表示されたら、以下のアプリケーションの登録情報を入力します。
   - **名前** - アプリのユーザーに表示されるわかりやすいアプリケーション名を入力します。
   - **サポートされているアカウントの種類** - アプリケーションでサポートするアカウントを選択します。

     <br>

     |サポートされているアカウントの種類|説明|
     |---|---|
     |**この組織のディレクトリ内のアカウントのみ**|基幹業務 (LOB) アプリケーションを作成している場合は、このオプションを選択します。 アプリケーションをディレクトリに登録していない場合、このオプションは選択できません。 <p> このオプションは、Azure AD のシングルテナントにのみマッピングします。 <p> これは、ディレクトリの外部にアプリを登録している場合を除き、既定のオプションです。 アプリがディレクトリの外部に登録されている場合、既定のオプションは Azure AD マルチテナントと個人の Microsoft アカウントです。|
     |**組織のディレクトリ内のアカウント**|企業および教育機関のすべてのユーザーを対象とする場合は、このオプションを選択します。 <p> このオプションは、Azure AD のマルチテナントにのみマッピングします。 <p> アプリを Azure AD のシングルテナントとしてのみ登録した場合は、[**認証**] ブレードを使用して、Azure AD マルチテナントに更新し、シングルテナントに戻すことができます。|
     |**組織のディレクトリ内のアカウントと個人用 Microsoft アカウント**|最も広い範囲の顧客を対象とする場合は、このオプションを選択します。 <p> このオプションは、Azure AD マルチテナントと個人用 Microsoft アカウントにマッピングします。 <p> アプリを Azure AD マルチテナントと個人用 Microsoft アカウントとして登録した場合は、UI でこれを変更できません。 代わりに、アプリケーション マニフェスト エディターを使用して、サポートされているアカウントの種類を変更する必要があります。|

   - **リダイレクト URI (オプション)** - 構築しているアプリの種類として **Web** または **パブリック クライアント (モバイルとデスクトップ)** を選択し、アプリケーションのリダイレクト URI (または応答 URL) を入力します。

     - Web アプリケーションの場合は、アプリのベース URL を指定します。 たとえば、`http://localhost:31544` はローカル マシンで実行されている Web アプリの URL になる場合があります。 ユーザーはこの URL を使用して、Web クライアント アプリケーションにサインインします。

     - パブリック クライアント アプリケーションの場合は、トークンの応答を返す際に Azure AD が使用する URI を指定します。 `myapp://auth` などのアプリケーションに固有の値を入力します。

     Web アプリケーションまたはネイティブ アプリケーションの具体的な例を見るには、「[クイック スタート](/azure/active-directory/develop/#quickstarts)」を参照してください。

     終了したら、[**登録**] を選択します。

4. アプリケーションがMicrosoft Defender for Endpointにアクセスできるようにし、"アラートの読み取り" アクセス許可を割り当てます。

   - アプリケーション ページで、組織が **WindowsDefenderATP** の種類>使用する **API アクセス許可**\>の **追加アクセス許可** \> **API** を選択し、**WindowsDefenderATP** で選択します。

     > [!NOTE]
     > *WindowsDefenderATP* は元の一覧に表示されません。 テキスト ボックスに名前を書き始めて、表示されます。

     :::image type="content" alt-text="アクセス許可を追加します。" source="images/add-permission.png" lightbox="images/add-permission.png":::

   - [**委任されたアクセス許可**\>のアラート] を選択します **。[読み取り**] > [**アクセス許可の追加]** を選択します。

      :::image type="content" source="images/application-permissions-public-client.png" alt-text="アプリケーションの種類とアクセス許可ウィンドウ" lightbox="images/application-permissions-public-client.png":::

   > [!IMPORTANT]
   > 関連するアクセス許可を選択します。 アラートの読み取りは例にすぎません。

     例:

     - [高度なクエリを実行するには、[高度なクエリの](run-advanced-query-api.md)実行] アクセス許可 **を** 選択します。
     - [デバイスを分離](isolate-machine.md)するには、[**コンピューターのアクセス許可の分離**] を選択します。
     - 必要なアクセス許可を確認するには、呼び出したい API の **[アクセス許可]** セクションを表示します。

   - [ **同意の付与]** を選択します。

      > [!NOTE]
      > アクセス許可を追加するたびに、新しいアクセス許可を有効にするには **、[同意の付与** ] を選択する必要があります。

      :::image type="content" source="images/grant-consent.png" alt-text="[Grand admin consent]\(管理者の同意\) オプション" lightbox="images/grant-consent.png":::

5. アプリケーション ID とテナント ID を書き留めます。

    アプリケーション ページで、[ **概要]** に移動し、次の情報をコピーします。

    :::image type="content" source="images/app-and-tenant-ids.png" alt-text="作成されたアプリ ID"  lightbox="images/app-and-tenant-ids.png":::

## <a name="get-an-access-token"></a>アクセス トークンを取得する

AAD トークンの詳細については、 [Azure AD のチュートリアル](/azure/active-directory/develop/active-directory-v2-protocols-oauth-client-creds)を参照してください。

### <a name="using-c"></a>C の使用\#

- 以下のクラスをアプリケーションにコピー/貼り付けます。
- **AcquireUserTokenAsync** メソッドをアプリケーション ID、テナント ID、ユーザー名、パスワードと共に使用して、トークンを取得します。

    ```csharp
    namespace WindowsDefenderATP
    {
        using System.Net.Http;
        using System.Text;
        using System.Threading.Tasks;
        using Newtonsoft.Json.Linq;

        public static class WindowsDefenderATPUtils
        {
            private const string Authority = "https://login.microsoftonline.com";

            private const string WdatpResourceId = "https://api.securitycenter.microsoft.com";

            public static async Task<string> AcquireUserTokenAsync(string username, string password, string appId, string tenantId)
            {
                using (var httpClient = new HttpClient())
                {
                    var urlEncodedBody = $"resource={WdatpResourceId}&client_id={appId}&grant_type=password&username={username}&password={password}";

                    var stringContent = new StringContent(urlEncodedBody, Encoding.UTF8, "application/x-www-form-urlencoded");

                    using (var response = await httpClient.PostAsync($"{Authority}/{tenantId}/oauth2/token", stringContent).ConfigureAwait(false))
                    {
                        response.EnsureSuccessStatusCode();

                        var json = await response.Content.ReadAsStringAsync().ConfigureAwait(false);

                        var jObject = JObject.Parse(json);

                        return jObject["access_token"].Value<string>();
                    }
                }
            }
        }
    }
    ```

## <a name="validate-the-token"></a>トークンを検証する

正しいトークンを取得していることを確認します。

- 前の手順で取得したトークンを [JWT](https://jwt.ms) にコピー/貼り付けてデコードします。
- 必要なアプリのアクセス許可を持つ 'scp' 要求を取得したことを検証します。
- 次のスクリーンショットでは、チュートリアルでアプリから取得したデコードされたトークンを確認できます。

  :::image type="content" source="images/nativeapp-decoded-token.png" alt-text="トークン検証ページ" lightbox="images/nativeapp-decoded-token.png":::

## <a name="use-the-token-to-access-microsoft-defender-for-endpoint-api"></a>トークンを使用してMicrosoft Defender for Endpoint API にアクセスする

- 使用する API ([サポートされているMicrosoft Defender for Endpoint API) を選択します](exposed-apis-list.md)。
- 送信する HTTP 要求の Authorization ヘッダーを "Bearer {token}" に設定します (ベアラーは承認スキームです)。
- トークンの有効期限は 1 時間です (同じトークンを使用して複数の要求を送信できます)。

- **C# を使用して** アラートの一覧を取得する要求を送信する例:

    ```csharp
    var httpClient = new HttpClient();

    var request = new HttpRequestMessage(HttpMethod.Get, "https://api.securitycenter.microsoft.com/api/alerts");

    request.Headers.Authorization = new AuthenticationHeaderValue("Bearer", token);

    var response = httpClient.SendAsync(request).GetAwaiter().GetResult();

    // Do something useful with the response
    ```

## <a name="see-also"></a>関連項目

- [Microsoft Defender for Endpoint API](exposed-apis-list.md)
- [アプリケーション コンテキストを使用してMicrosoft Defender for Endpointにアクセスする](exposed-apis-create-app-webapp.md)
