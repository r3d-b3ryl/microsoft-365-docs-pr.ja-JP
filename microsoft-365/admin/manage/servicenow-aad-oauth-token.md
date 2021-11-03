---
title: OAuth トークンMicrosoft 365サポート統合AAD構成する
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
ms.openlocfilehash: b32f2e4edea590a6002e1568b5a65a2d8c71f703
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661975"
---
# <a name="configure-microsoft-365-support-integration-with-aad-oauth-token"></a>OAuth トークンMicrosoft 365サポート統合AAD構成する

## <a name="prerequisites-aad-oauth-token"></a>前提条件 (AAD OAuth トークン)

これらの前提条件は、サポート統合のMicrosoft 365必要です。

1. \[AAD管理者 \] テナントのAAD送信用のアプリケーションを作成Microsoft 365します。

    1. テナント資格情報を使用して Azure Portal にMicrosoft 365し、[アプリの登録][](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)ページに移動して新しいアプリケーションを作成します。

    2. [ **この組織ディレクトリ内のアカウントのみ] ({Microsoft-365-tenant-name}** のみ – シングル テナント) を選択し、[登録] を **選択します**。

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [認証] **に移動し** 、[プラットフォームの **追加] を選択します**。 **[Web] オプションを** 選択し、リダイレクト URL を入力します。`https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[AADAdmin \] Rest API 用のAADアプリケーションを、テナントの下にMicrosoft 365します。

    1. テナント資格情報を[使用して Azure Portal](https://portal.azure.com/)にMicrosoft 365し、[アプリの登録] ページに移動して新しいアプリケーションを作成します。

    1. [ **この組織ディレクトリ内のアカウントのみ{(Microsoft-365-tenant-name}** のみ - シングル テナント) を選択します。

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image22.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image22.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[AAD管理者 \] ユーザーテナントのAADの下に Rest ユーザー用のアプリケーションをMicrosoft 365します。

    1. テナント資格情報を[使用して Azure Portal](https://portal.azure.com/)にMicrosoft 365し、[アプリの登録] ページに移動して新しいアプリケーションを作成します。

    1. [ **この組織ディレクトリ内のアカウントのみ{(Microsoft-365-tenant-name}** のみ - シングル テナント) を選択します。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" lightbox="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[ServiceNow 管理者 \] ServiceNow で送信 OAuth プロバイダーを設定します。

    スコープがグローバルに設定されていない場合は、開発者アプリケーションに移動し、設定 **&gt; &gt; に** 切り替 **えます**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. [System **OAuth &gt; アプリケーション レジストリ] に移動します**。

1. [サード パーティの **OAuth** プロバイダー Connectを使用して新しいアプリケーションを作成し、次の値を入力します。

    - クライアント ID: これは、前提条件 (OAuth トークン) の手順 1 でAADアプリケーションのクライアント ID \# です。

    - クライアント シークレット: これは、前提条件 (OAuth トークン) ステップ 1 で作成AADクライアント シークレット値 \# です。

    - 既定の付与の種類: クライアント資格情報

    - トークン URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - リダイレクト URL: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin \] ServiceNow で OIDC プロバイダーを構成するには、オンライン ドキュメントを [参照してください](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

    スコープがグローバルに設定されていない場合 **は、[開発者** アプリケーション] 設定 **&gt; に &gt;** 移動し、[グローバル] に **切り替えます**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. [System **OAuth &gt; アプリケーション レジストリ] に移動します**。

1. [**新規] を** 選択し、[新しい Open ID を作成する **] Connectします**。

1. **[OAuth OIDC プロバイダーの** 構成] で、[検索] を選択し **、[oidc プロバイダーの構成] の下に新しい OIDC プロバイダー構成を作成します。 \_ \_ 次** の値を指定します。 

    - OIDC プロバイダー: **{テナント \_ 名} Azure** (例: Contoso Azure)

    - OIDC メタデータ URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim: **appId**

    - UserField: **ユーザー ID**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image24.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image24.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. [次の値で ID トークンを確認する **OIDC** プロバイダーを構成する] を選択して、新しいアプリケーションを作成します。

    - 名前: **{Tenant \_ Name} \_ アプリケーション \_ の \_ 受信 API** (例: contoso \_ アプリケーション \_ の受信 \_ API)

    - クライアント ID: 前提条件 (OAuth トークン) の手順 2 でAADアプリケーションのクライアント \# ID。

    - クライアント シークレット: 前提条件 (OAuth トークン) ステップ 2 でAADアプリケーションのアプリ \# シークレット。

    - OAuth OIDC プロバイダーの構成: 前の手順で作成した OIDC プロバイダー

    - リダイレクト URL: `https://{service-now-instance-name}.service-now.com/oauth\_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image25.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image25.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin \] 統合ユーザーの作成。

    統合ユーザーを指定する必要があります。 既存の統合ユーザーがいない場合、またはこの統合用に作成する場合は、[組織ユーザー] に移動して **新 &gt;** しいユーザーを作成します。 User ID の値 **は、前提条件 (OAuth** トークン) ステップ [ \# 3](#prerequisites-aad-oauth-token)でAADアプリケーション クライアント ID です。

    新しい統合ユーザーを作成する場合は、[Web サービス アクセス **のみ] オプションを確認** します。 また、このユーザーにインシデント マネージャーの役割 **を付与 \_ する必要** があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image26.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image26.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPTIONAL \] サービスの IP アドレスをサポート統合Microsoft 365許可する

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

1. \[ServiceNow Admin \] スコープをサポート統合Microsoft 365 **に切り替えます**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="グラフィカル ユーザー インターフェイス、テーブルの説明が自動的に生成される":::

1. \[ServiceNow Admin \] [サポート **Microsoft 365] に移動 &gt; して**、統合ワークフローを開きます。

    > [!NOTE]
    > "スコープ \_ 'x \_ mioms \_ m365 \_ assis' からの 'oauth エンティティに対する読み取り操作' というエラーがテーブルのクロススコープ アクセス ポリシーによって拒否された場合、テーブル アクセス ポリシーが原因で発生しました。 [読み取り可能なすべての **アプリケーション スコープ] &gt; がテーブル** oauth エンティティに対してチェックされている必要 \_ があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin \] Select **Agree** to the consent prompt to continue.

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin \] 送信 OAuth プロバイダーを設定します。

    前提条件 (OAuth トークン) ステップ [ \# 4](#prerequisites-aad-oauth-token)で作成された送信 OAuth プロバイダーの OAuth プロファイルAAD選択し、[次へ] を選択 **します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin \] 受信 OAuth プロバイダーをセットアップします。

    1. [現在の **手順をスキップする] のチェックを外します**。

    1. [外部 **OIDC 認証トークン] を確認します**。

    1. [前提条件] ([OAuth トークン] ステップ [ \# 5)](#prerequisites-aad-oauth-token)でAAD OAuth クライアントを選択し、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image28.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image28.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin \] 受信呼び出し統合ユーザーを設定します。

    1. [現在の **手順をスキップする] のチェックを外します**。

    1. [前提条件 **] ([OAuth** トークン] の手順 [ \# 3)](#prerequisites-aad-oauth-token)でAADアプリケーションのクライアント ID を入力し、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image39.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image39.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin \] リポジトリ ID を設定します。

    リポジトリ ID を指定し、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin \] アプリケーション のセットアップ 設定。

    次の設定を選択し、[次へ] を **選択します**。

    - SSO と Microsoft 365: ServiceNow インスタンスが SSO として設定されているかどうかを確認し、Microsoft 365チェックを外します。

    - Microsoft 365メール: サポート ケースの作成時にMicrosoft 365された管理者ユーザー Microsoft 365メール。

    - テスト環境: このチェック ボックスをオンにして、Microsoft サポート エージェントが問題に対処するために連絡を取るのを避けるためのテスト フェーズを示します。 サポート統合を使用して正式に進む準備ができたらMicrosoft 365チェックを外します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. \[Microsoft 365テナント管理者 \] 統合を完了します。

    以下の情報が正しいか確認します。 この時点で [ **次へ]** を選択しない。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image40.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image40.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [ポータル] **Microsoft 365 管理組織 &gt; 設定 &gt; に &gt; 移動します**。

1. サポート統合設定を構成します。

    [内部サポート **ツール ServiceNow]** > [基本情報] タブを選択し、[OAuth トークンを発行するアプリケーション ID] フィールドに [送信アプリ  >  **ID]** の値 **を入力** します。 この送信アプリ ID は、手順 6 - 前提条件 (OAuth トークン) の手順 1 で作成AAD統合を[ \# 完了します](#prerequisites-aad-oauth-token)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [リポジトリ **] タブで** 、[リポジトリの追加] **を選択** して、次の設定で新しいリポジトリを作成します。

    - リポジトリ: " **手順** 6 - 統合を完了する" のリポジトリ ID 値。

    - Endpoint: **"Step** 6 – Complete the Integration" の Endpoint 値。

    - 認証の種類: [**認証AAD選択します**。

    - クライアント ID: 手順 6 のクライアント **ID** の値 – 統合を完了します。

    - クライアント シークレット: 前提条件 (OAuth トークン) の手順 2 で作成AAD OAuth プロバイダーの \# シークレット。

    - 残りのユーザー名: 手順 6 の [ユーザー名] の値 ( [必須コンポーネント ] (AAD OAuth トークン) の手順 3 で作成されたアプリケーションのクライアント **ID** である統合を完了します \# 。

    - ユーザーパスワードの保存: 前提条件 (OAuth トークン) の手順 3 で作成AADアプリケーションのアプリ シークレット \# 。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image31.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image31.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. ServiceNow に戻る。

1. [次 **へ] を** 選択して統合を完了します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image32.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image32.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin \] 既存のユーザーに対する Microsoft サポート統合を有効にする。

    Microsoft 365の役割のいずれかを持つユーザーに対してサポート統合が有効になります。

    - x \_ mioms \_ m365 \_ assis.insights \_ ユーザー

    - x \_ mioms \_ m365 \_ assis.administrator

1. \[OPTIONAL \] \[ ロール x \_ mioms \_ m365 \_ assis.administrator リンクを持つユーザー link Microsoft 365 \] 管理者アカウント。

    ユーザーが役割 x \_ mioms \_ m365 \_ assis.administrator を持ち、Microsoft 365 サポート ケースを管理するために異なる Microsoft 365 アカウントを使用している場合は、Microsoft 365 サポート リンク アカウントに移動して Microsoft 365 管理者メール &gt; を設定する必要があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::
