---
title: Auth トークンMicrosoft 365サポート統合Azure AD構成する
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
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
description: ServiceNow のスコープ認定アプリケーションのインストールと構成ガイド。
ms.openlocfilehash: f8bc7ee4647bf14521b9d29f616539acb95e7495
ms.sourcegitcommit: 7fd1bcbd8246501029837e3ea92adea64c3406e1
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 02/01/2022
ms.locfileid: "62295228"
---
# <a name="configure-microsoft-365-support-integration-with-azure-ad-auth-token"></a>Auth トークンMicrosoft 365サポート統合Azure AD構成する

## <a name="prerequisites-azure-ad-auth-token"></a>前提条件 (Azure AD認証トークン)

これらの前提条件は、サポート統合のMicrosoft 365必要です。

1. \[AAD管理者\][Azure AD] テナントの下に[送信用アプリケーションMicrosoft 365作成します。

    1. テナント資格情報を使用して Azure Portal にMicrosoft 365し、[アプリの登録] ページに移動して[](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)新しいアプリケーションを作成します。

    2. [ **この組織ディレクトリ内のアカウントのみ] ({Microsoft-365-tenant-name} のみ – シングル テナント)** を選択し、[登録] を選択 **します**。

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [認証] **に移動し** 、[プラットフォーム **の追加] を選択します**。 [ **Web] オプションを** 選択し、リダイレクト URL を入力します。 `https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[AAD管理者\]テナントの下Azure ADアプリケーション for Rest API をMicrosoft 365します。

    1. テナント資格情報を[使用して Azure Portal](https://portal.azure.com/) にMicrosoft 365し、[アプリの登録] ページに移動して新しいアプリケーションを作成します。

    1. [ **この組織ディレクトリ内のアカウントのみ{(Microsoft-365-tenant-name} のみ - シングル テナント) を選択します**。

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image22.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image22.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[AAD管理者\]テナントのAzure ADで、Rest ユーザー用アプリケーションをMicrosoft 365します。

    1. テナント資格情報を[使用して Azure Portal](https://portal.azure.com/) にMicrosoft 365し、[アプリの登録] ページに移動して新しいアプリケーションを作成します。

    1. [ **この組織ディレクトリ内のアカウントのみ{(Microsoft-365-tenant-name} のみ - シングル テナント) を選択します**。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" lightbox="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[ServiceNow 管理者\] ServiceNow で送信 OAuth プロバイダーを設定します。

    スコープがグローバルに設定されていない **&gt;場合は、開発者アプリケーションに移動設定グローバル&gt;** に切り替 **えます**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. [System **OAuth アプリケーション レジストリ &gt; ] に移動します**。

1. [サード パーティの **OAuth** プロバイダー Connectを使用して新しいアプリケーションを作成し、次の値を入力します。

    - クライアント ID: これは、前提条件 (Auth トークン) の手順 1 でAzure ADアプリケーション\#のクライアント ID です。

    - クライアント シークレット: これは、前提条件 (Auth トークン) ステップ 1 で作成Azure ADクライアント \#シークレット値です。

    - 既定の付与の種類: クライアント資格情報

    - トークン URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - リダイレクト URL: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin ServiceNow\] で OIDC プロバイダーを構成するには、オンライン ドキュメントを [参照してください](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

    スコープがグローバルに設定されていない場合 **は、[****&gt;開発者アプリケーション] 設定に&gt;** 移動し、[グローバル] に切り替 **えます**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. [System **OAuth アプリケーション レジストリ &gt; ] に移動します**。

1. [**新規] を** 選択し、[新しい Open ID を作成する] **Connect選択します**。

1. **[OAuth OIDC プロバイダー構成**] で、[検索] を選択し、次の値を使用して **oidcproviderconfiguration.list\_\_** の下に新しい OIDC プロバイダー構成を作成します。

    - OIDC プロバイダー: **{TenantName\_} Azure** (例: Contoso Azure)

    - OIDC メタデータ URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim: **appId**

    - UserField: **ユーザー ID**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image24.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image24.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. [次の値で ID トークンを確認する **OIDC** プロバイダーを構成する] を選択して、新しいアプリケーションを作成します。

    - 名前: **{TenantName\_}\_applicationinboundapi\_\_** (例: contosoapplicationinboundapi\_\_\_)

    - クライアント ID: 前提条件 (Auth トークン) ステップ 2 でAzure ADアプリケーションのクライアント \#ID。

    - クライアント シークレット: 前提条件 (Auth トークン) ステップ 2 でAzure ADアプリケーションのアプリ シークレット\#。

    - OAuth OIDC プロバイダーの構成: 前の手順で作成した OIDC プロバイダー

    - リダイレクト URL: `https://{service-now-instance-name}.service-now.com/oauth\_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image25.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image25.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin 統合\] ユーザーの作成。

    統合ユーザーを指定する必要があります。 既存の統合ユーザー **&gt;** がいない場合、またはこの統合用に作成する場合は、[組織ユーザー] に移動して新しいユーザーを作成します。 User ID の値 **は、前提条件** (認証トークン) で作成 [Azure ADクライアント ID です](#prerequisites-azure-ad-auth-token)。

    新しい統合ユーザーを作成する場合は、[Web サービス アクセス **のみ] オプションを確認** します。 また、このユーザーに **incidentmanager ロールを付与する\_必要** があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image26.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image26.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPTIONAL\] サービスの IP アドレスをサポート統合Microsoft 365許可する

会社が独自のポリシーでインターネット アクセスを制限している場合は、以下の IP アドレスを受信 API アクセスと送信 API アクセスの両方に許可することで、Microsoft 365 サポート統合のサービスに対するネットワーク アクセスを有効にしてください。

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> このターミナル コマンドは、サポート統合をサポートするサービスのすべてのMicrosoft 365一覧表示します。`nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>サポート統合アプリケーションMicrosoft 365構成する

サポートMicrosoft 365統合アプリケーションは、サポートの下でMicrosoft 365できます。

これらの手順は、ServiceNow インスタンスとサービス サポート間の統合をMicrosoft 365です。

1. \[ServiceNow Admin\] スコープをサポート統合Microsoft 365 **切り替えます**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="グラフィカル ユーザー インターフェイス、テーブルの説明が自動的に生成される":::

1. \[ServiceNow Admin 統合ワークフロー\]を開 **Microsoft 365サポート &gt; セットアップ** に移動します。

    > [!NOTE]
    > "スコープ 'xmiomsm365assis\_\_' からの 'oauthentity\_\_' に対する読み取り操作が、テーブルのクロススコープ アクセス ポリシーのために拒否されました」というエラーが表示される場合は、テーブル アクセス ポリシーが原因で発生しました。 [読み取り可能なすべての **アプリケーション スコープ &gt; ] が** テーブルの oauthentity に対してチェックされている必要\_があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] Select **Agree** to the consent prompt to continue.

    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-1.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-1.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 環境とセットアップの種類を構成します。
    このインストールがテスト環境にインストールされている場合は、[これはテスト環境です] オプションを選択します。 セットアップ後にこのオプションをすばやく無効にし、すべてのテストを後で完了できます。
    インスタンスで受信接続の基本認証が許可されている場合は、[はい] を選択し、[ [基本認証] セットアップ プロセスを参照します](servicenow-basic-authentication.md)。 それ以外の場合は、[ **いいえ] を選択し** 、[セットアップの開始 **] をクリックします**。 
      :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-2.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-2.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] テナント ドメインMicrosoft 365入力します。
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-3.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin 送信\] OAuth プロバイダーを構成します。
    1. 送信 OAuth プロバイダーを構成します。
    1. [前提条件] セクションの手順を完了したら、[完了] をクリックします。 それ以外の場合は、ウィザードの指示に従って、アプリケーションに必要なアプリケーション登録を作成AAD。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-4.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    1. ServiceNow OAuth アプリを登録します。
    1. [前提条件] セクションの手順を完了したら、新しく作成した OAuth アプリケーションの登録を選択し、[次へ] をクリックします。 それ以外の場合は、手順に従って ServiceNow でエンティティを作成し、新しいアプリケーション登録を選択します。
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-5.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin 受信\] 設定を構成します。
    1. 受信アプリを構成AADします。
    1. [前提条件] セクションの手順を完了したら、[完了] をクリックして次の手順に進みます。 それ以外の場合は、指示に従って、受信AADアプリ登録を作成します。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-6.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-6.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    1. ServiceNow 外部 OpenID プロバイダー (OIDC プロバイダー) Connect構成します。
    1. [前提条件] セクションの手順を完了したら、新しく作成したエンティティを選択し、[完了] をクリックします。 それ以外の場合は、手順に従って ServiceNow でエンティティを作成し、新しい外部 OIDC プロバイダー アプリ登録を選択します。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-7.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-7.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    1. 受信統合ユーザー AADアプリ登録を構成します。
    1. [前提条件] セクションの手順を完了したら、[完了] をクリックして次の手順に進みます。 それ以外の場合は、指示に従って、受信 REST ユーザー AADアプリ登録 (統合ユーザー) を作成します。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-8.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-8.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    1. 統合ユーザーを構成します。
    1. [前提条件] セクションの手順を完了したら、新しく作成したエンティティを選択し、[次へ] をクリックします。 それ以外の場合は、手順に従って ServiceNow で統合ユーザーを作成し、エンティティを選択します。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-9.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-9.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[Microsoft 365テナント管理者\]統合を完了します。

    以下の情報が正しいか確認します。 この時点で [ **次へ]** を選択しない。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image40.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image40.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. [ポータル] **Microsoft 365 管理組織設定&gt;&gt;に&gt;移動します**。

    1. サポート統合設定を構成します。

    [内部サポート **ツールServiceNow]** > **[** > 基本情報] タブを選択し、[認証トークンを発行するアプリケーション ID] フィールドに [送信アプリ **ID**] の値 **を入力** します。 この送信アプリ ID は、手順 6 – [必須コンポーネント] ([認証トークン] ) で作成された統合Azure AD[完了します](#prerequisites-azure-ad-auth-token)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. [リポジトリ **] タブで** 、[新しい **リポジトリ] を選択** し、次の設定で更新します。

    - リポジトリ: " **手順** 6 - 統合を完了する" のリポジトリ ID 値。

    - Endpoint: **"Step** 6 – Complete the Integration" の Endpoint 値。

    - 認証の種類: [**認証AAD選択します**。

    - クライアント ID: 手順 6 のクライアント **ID** の値 – 統合を完了します。

    - クライアント シークレット: 前提条件 (Azure AD認証トークン) \#の手順 2 で作成された受信 OAuth プロバイダーのシークレット。

    - 残りのユーザー名: 手順 6 の [ユーザー名] の値 ( [前提条件] (Azure AD 認証トークン) \#の手順 3 で作成されたアプリケーションのクライアント **ID** である統合を完了します。

    - Rest ユーザー パスワード: 前提条件 (Auth トークン) ステップ 3 で作成Azure ADアプリケーションのアプリ シークレット\#。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image31.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image31.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

    1. ServiceNow に戻る。

    1. [次 **へ] を** 選択して統合を完了します。

   :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-10.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-10.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    サポートMicrosoft 365アプリはテストを実行して、統合が機能しているのを確認します。 構成に問題がある場合は、修正する必要がある内容を説明するエラー メッセージが表示されます。 それ以外の場合は、アプリケーションの準備ができました。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-11.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-11.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 既存のユーザーに対する Microsoft サポート統合を有効にする。

    Microsoft 365の役割のいずれかを持つユーザーに対してサポート統合が有効になります。

    - xmiomsm365assis.insightsuser\_\_\_\_

    - xmiomsm365assis.administrator\_\_\_

1. \[OPTIONAL\] \[役割 xmiomsm365assis.administrator\_\_\_ リンクを持つユーザー は、\]管理者アカウントMicrosoft 365リンクします。

    ユーザーが役割 xmiomsm365assis.administrator\_&gt;\_\_ を持ち、Microsoft 365 サポート ケースを管理するために異なる Microsoft 365 アカウントを使用している場合は、Microsoft 365 サポート リンク アカウントに移動して Microsoft 365 管理者メールを設定する必要があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::
