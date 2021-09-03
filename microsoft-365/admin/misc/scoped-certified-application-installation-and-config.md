---
title: Microsoft 365 ServiceNow 構成ガイドとの統合をサポートする
f1.keywords:
- NOCSH
ms.author: pebaum
author: pebaum
manager: scotv
audience: Admin
ms.topic: article
ms.service: o365-administration
localization_priority: Normal
ms.collection:
- M365-subscription-management
ms.custom: AdminSurgePortfolio
ROBOTS: NOINDEX, NOFOLLOW
search.appverid:
- MET150
description: ServiceNow のスコープ認定アプリケーションのインストールと構成ガイド。
ms.openlocfilehash: f21353aa54cfee3b85a6e9d846aa4fce37cc13f5
ms.sourcegitcommit: 8ef23d275d7209a705295e2b117d4382b20ad4f7
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 09/02/2021
ms.locfileid: "58866723"
---
# <a name="microsoft-365-support-integration-with-servicenow-configuration-guide"></a>Microsoft 365 ServiceNow 構成ガイドとの統合をサポートする

[概要](#overview) 

[ServiceNow 環境でのアプリケーションの依存関係](#application-dependencies-in-servicenow-environments)

[構成手順](#configuration-instructions)

[Whoサポート統合をMicrosoft 365できますか?](#who-can-set-up-microsoft-365-support-integration)

[サポート統合に使用できるMicrosoft 365機能は何ですか?](#what-features-are-available-in-microsoft-365-support-integration) 

[ServiceNow Microsoft 365認証との統合をサポートする方法を設定する](#set-up-microsoft-365-support-integration-with-servicenow-basic-authentication)

[AAD OAuth トークンMicrosoft 365サポート統合のセットアップ](#set-up-microsoft-365-support-integration-with-aad-oauth-token)

[サポート統合Microsoft 365のセットアップのみインサイトする](#set-up-microsoft-365-support-integration-for-insights-only) 

[構成のテスト](#testing-the-configuration) 

[トラブルシューティング](#troubleshooting) 

## <a name="overview"></a>概要

Microsoft 365サポート統合を使用すると、ヘルプMicrosoft 365、サービス正常性を ServiceNow と統合できます。 Microsoft 推奨ソリューションを使用して、Microsoft の既知および報告された問題を調査し、インシデントを解決し、タスクを完了し、必要に応じて Microsoft の人間支援サポートにエスカレートすることができます。

## <a name="application-dependencies-in-servicenow-environments"></a>ServiceNow 環境でのアプリケーションの依存関係

必要なアクセス許可:

- oauth \_ エンティティ

- oauth \_ エンティティ \_ プロファイル

サポートMicrosoft 365インストールされた後、2 つの Application Cross-Scope アクセスが作成されました。 何らかの理由で正常に作成されない場合は、手動で作成します。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image1.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

## <a name="configuration-instructions"></a>構成手順

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image2.png" alt-text="ダイアグラムの説明が自動的に生成される":::

サポート統合をMicrosoft 365するには、次の方法を実行します。

- 送信 API 呼び出Microsoft Azure Active Directory両方の認証を行うアプリケーションを、Microsoft Azure Active Directory (AAD) に登録します。

- 送信データ フローと受信データ フローの両方に対して Microsoft AAD アプリケーションを使用して ServiceNow エンティティを作成します。

- ServiceNow インスタンスを Microsoft サポートと統合するには、ポータルMicrosoft 365 管理します。

## <a name="who-can-set-up-microsoft-365-support-integration"></a>Whoサポート統合をMicrosoft 365設定できますか?

- AAD アプリケーションを作成する権限を持つユーザー。

- ServiceNow 管理者。

- テナント内のヘルプデスク管理者またはサービス要求Microsoft 365します。

## <a name="what-features-are-available-in-microsoft-365-support-integration"></a>サポート統合に使用できるMicrosoft 365機能は何ですか?

サポート統合用に構成をMicrosoft 365前に、次の質問に対する回答を確認してください。

**質問#1** ServiceNow 環境では、受信 Web サービス呼び出しに対して基本認証 (ServiceNow ユーザー資格情報を使用したアクセス) が許可されていますか?

**質問#2** 複数のテナントがある場合は、ServiceNow 環境と統合された 1 つのテナントを使用して、サポート統合Microsoft 365計画していますか?

上記の質問に対する回答に応じて、次の表に、使用可能な機能と、サポート統合の設定方法Microsoft 365示します。 各機能の説明については、「サポート[統合Microsoft 365参照してください](https://store.servicenow.com/sn_appstore_store.do#!/store/application/6d05c93f1b7784507ddd4227cc4bcb9f)。

|質問#1回答|質問#2回答|利用できる機能は何ですか?|構成手順|
|--- |--- |--- |--- |
|はい|はい|サービス正常性インシデント <br/>推奨されるソリューション </br>Microsoft サービス要求|[ServiceNow Microsoft 365認証との統合をサポートする方法を設定する](#set-up-microsoft-365-support-integration-with-servicenow-basic-authentication)|
|はい|いいえ|サービス正常性インシデント <br/>推奨されるソリューション </br>Microsoft サービス要求||
|いいえ|はい|サービス正常性インシデント <br/>推奨されるソリューション </br>Microsoft サービス要求|[AAD OAuth トークンMicrosoft 365サポート統合のセットアップ](#set-up-microsoft-365-support-integration-with-aad-oauth-token)|
|いいえ|いいえ|サービス正常性インシデント <br/>推奨されるソリューション|[サポート統合Microsoft 365のセットアップのみインサイトする](#set-up-microsoft-365-support-integration-for-insights-only) |

## <a name="set-up-microsoft-365-support-integration-with-servicenow-basic-authentication"></a>ServiceNow Microsoft 365認証との統合をサポートする方法を設定する

### <a name="prerequisites-basic-authentication"></a>前提条件 (基本認証)

一部の前提条件は、統合をサポートするためにMicrosoft 365必要です。

1. \[AAD アプリケーションを作成できるユーザー テナントの下に \] AAD アプリケーションMicrosoft 365します。

    1. テナント資格情報を[使用して Azure Portal](https://portal.azure.com/) Microsoft 365ログオンします。

    1. [アプリの登録] ページに移動し、新しいアプリケーションを作成します。

        [ **この組織ディレクトリ内のアカウントのみ] を選択します ({microsoft-365-tenant-name} のみ – シングル テナント** です。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. リダイレクト URL の追加: `https://{your-servicenow-instance}.service-now.com/oauth_redirect.do` .

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. アプリケーションのクライアント ID を取得し、アプリ シークレットを作成します。

2. \[ServiceNow 管理者であるユーザー ServiceNow で \] 送信 OAuth プロバイダーを設定します。

    1. スコープがグローバルに設定されていない場合は、開発者設定を開き、グローバル  >    >  に **切り替えます**。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

    1. [System **OAuth アプリケーション**  >  **レジストリ] に移動します**。

    1. サード パーティの OAuth プロバイダーにアクセスする方法を選択して、Connect値を使用して新しい **アプリケーションを作成します**。

    - クライアント ID: 手順 1 で作成したアプリケーションの \# クライアント ID

    - クライアント シークレット: 手順 1 で作成したアプリケーションのアプリ \# シークレット

    - 既定の付与の種類: クライアント資格情報

    - トークン URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - リダイレクト URL: https://{service-now-instance-name}.service-now.com/auth_redirect.do

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

3. \[ServiceNow 管理者であるユーザー \] 受信 OAuth プロバイダーを設定します。

    1. スコープがグローバルに設定されていない場合は、開発者設定を開き、グローバル  >    >  に **切り替えます**。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

    1. [System **OAuth アプリケーション**  >  **レジストリ] に移動します**。

    1. [外部クライアント用に OAuth API エンドポイントを作成する] **を選択して、新しいアプリケーションを作成します**。 受信 OAuth プロバイダーに名前を付け、他のフィールドを既定値のままにします。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image7.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

4. \[ServiceNow 管理者であるユーザー 統合 \] ユーザーを作成します。

    統合ユーザーを指定する必要があります。 既存の統合ユーザーがいなかったり、この統合に固有のユーザーを作成する場合は、[組織ユーザー]に移動して新しいユーザー  >  を作成します。

    新しい統合ユーザーを作成する場合は、[Web サービス アクセスのみ] **チェック ボックスをオンにします**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image8.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

### <a name="optional-allow-the-services-ips-of-microsoft-365-support-integration"></a>\[オプション \] サービスの IPs をサポート統合Microsoft 365許可する

会社が独自のポリシーでインターネット アクセスを制限している場合は、以下の IP アドレスを受信 API アクセスと送信 API アクセスの両方に許可することで、Microsoft 365 サポート統合のサービスに対するネットワーク アクセスを有効にしてください。

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> このターミナル コマンドは、サポート統合をサポートするサービスのすべてのMicrosoft 365一覧表示します。`nslookup connector.rave.microsoft.com`

### <a name="set-up-microsoft-365-support-integration-application"></a>サポート統合Microsoft 365のセットアップ

サポートMicrosoft 365統合アプリケーションは、サポートの下でMicrosoft 365できます。

これらの手順は、ServiceNow インスタンスとサービス サポート間の統合をMicrosoft 365です。

1. \[ServiceNow 管理者であるユーザー スコープをサポート統合 \] Microsoft 365切り替えます。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="グラフィカル ユーザー インターフェイス、テーブルの説明が自動的に生成される":::

2. \[ServiceNow 管理者であるユーザー 統合フローを開 \] Microsoft 365セットアップ>**サポート** に移動します。

    > [!NOTE]
    > "スコープ \_ 'x \_ mioms \_ m365 \_ assis' からの 'oauth エンティティに対する読み取り操作' というエラーがテーブルのクロススコープ アクセス ポリシーによって拒否された場合、テーブル アクセス ポリシーが原因で発生しました。 [読み取り可能なすべての **アプリケーション スコープ]**  >  **がテーブル** oauth エンティティに対してチェックされている必要 \_ があります。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image10.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

3. \[ServiceNow 管理者であるユーザー 同意 \] に **同意** する同意を選択する

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

4. \[ServiceNow 管理者であるユーザー \] 送信 OAuth プロバイダーを設定します。

    前提条件 (基本認証 [)](#prerequisites-basic-authentication) 手順 2 で作成された送信 OAuth プロバイダーの OAuth プロファイルを選択し、[ \# 次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

5. \[ServiceNow 管理者であるユーザー \] 受信 OAuth プロバイダーを設定します。

- [現在の **手順をスキップする] のチェックを外します**。

- [外部 **OIDC 認証トークン] のチェックを外します**。

- 前提条件 (基本認証) 手順 3 で作成 [した OAuth クライアント](#prerequisites-basic-authentication) を選択し、[ \# 次へ] を **選択します**。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image13.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

6. \[ServiceNow 管理者であるユーザー \] 受信呼び出し統合ユーザーを設定します。

- [現在の **手順をスキップする] のチェックを外します**。

- 前提条件 (基本認証) 手順 4 で作成 [した](#prerequisites-basic-authentication) 統合ユーザーを選択し、[ \# 次へ] を **選択します**。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image14.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

7. \[ServiceNow 管理者であるユーザー リポジトリ \] ID を設定します。

リポジトリ ID を指定し、[次へ] を **選択します**。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

8. \[ServiceNow 管理者であるユーザー アプリケーション \] の設定を設定します。

次の設定を選択し、[次へ] を **選択します**。

- SSO と Microsoft 365: ServiceNow インスタンスが SSO として設定されているかどうかを確認し、Microsoft 365チェックを外します。

- Microsoft 365メール: サポート ケースの作成時にMicrosoft 365された管理者ユーザー Microsoft 365メール。

- テスト環境: このチェック ボックスをオンにして、Microsoft サポート エージェントが問題に対処するために連絡を取るのを避けるためのテスト フェーズを示します。 サポート統合を使用して正式に進む準備ができたらMicrosoft 365チェックを外します。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

9. \[テナントのヘルプデスク管理者またはサービス要求管理者であるMicrosoft 365 \] 統合を完了します。

    1. 以下の情報を確認して、正しいか確認してください。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image17.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

    1. [組織の設定Microsoft 365 [管理ポータル](https://admin.microsoft.com/)  >  **設定**  >  **組織**  >  **のプロファイル] に移動します**。

    1. サポート統合設定を設定します。

        1. [基本情報] タブで、[内部サポート ツール Service **Now]** を選択し、[手順 - 6 完了] ページの [アプリケーション ID] の値として「送信アプリ **ID」** と入力します。これは、前提条件 [(基本認証)](#prerequisites-basic-authentication)手順 1 で作成されました。 \#

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

        1. [リポジトリ] **タブで**、[リポジトリの追加] **を選択** して、次の設定で新しいリポジトリを作成します。

        - リポジトリ: ページ **ステップ -** 6 からのリポジトリ ID の値 統合を完了します。

        - Endpoint: **Page Step** - 6 Complete the Endpoint value from page Step - 6 Complete the integration.

        - 認証の種類: [ **基本認証] を選択します**。

        - クライアント ID: ページ **ステップ -** 6 からのクライアント ID の値 統合を完了します。

        - クライアント シークレット: 前提条件 (基本認証 [)](#prerequisites-basic-authentication) 手順 3 で作成された受信 OAuth プロバイダーの \# シークレット。

        - 更新トークンの有効期限: 864000

        - ユーザー名の残り: **[手順] -** [6] ページの [ユーザー名] の値統合を完了します。

        - ユーザーの残りのパスワード: 前提条件 (基本認証 [)](#prerequisites-basic-authentication) 手順 4 で作成された統合ユーザー \# のパスワード。

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image19.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

        1. 戻って、統合を保存するボタンを選択します。

    1. [次 **へ] を** 選択して統合を完了します。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image20.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーション、Web サイトの説明が自動的に生成される":::

10. \[ServiceNow 管理者であるユーザー 既存のユーザー Microsoft 365 \] サポート統合を有効にする。

Microsoft 365サポート統合が有効になっているのは、次のいずれかの役割を持つユーザーのみです。

- x \_ mioms \_ m365 \_ assis.insights \_ ユーザー

- x \_ mioms \_ m365 \_ assis.administrator

> [!NOTE]
> 役割 x \_ mioms m365 assis.insights ユーザー ロールを持つユーザーは、 \_ \_ \_ サービス正常性インシデント、推奨されるソリューションを参照できます。 ロール x \_ mioms \_ m365 assis.administrator を持つユーザーは、サポートを受Microsoft 365 \_ できます。

11. \[オプション \] \[ 役割を持つユーザー x_mioms_m365_assis.administrator \] リンク Microsoft 365 管理 アカウントです。

ユーザーが役割 x \_ mioms \_ m365 assis.administrator を持ち、Microsoft 365 サポート ケースを管理するために異なる Microsoft 365 アカウントを使用している場合は、Microsoft 365 サポート \_ > リンク アカウントに移動して、Microsoft 365 管理者メールを設定する必要があります。

 :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

## <a name="set-up-microsoft-365-support-integration-with-aad-oauth-token"></a>AAD OAuth トークンMicrosoft 365サポート統合のセットアップ

### <a name="prerequisites-aad-oauth-token"></a>前提条件 (AAD OAuth トークン)

これらの前提条件の手順は、サポート統合の設定Microsoft 365必要です。

1. \[AAD アプリケーションを作成できるユーザー テナントの下に送信用 \] AAD アプリケーションをMicrosoft 365します。

    1. テナント資格情報[を使用して Azure Portal](https://portal.azure.com/) Microsoft 365ログオンします。

    1. [アプリの登録 **] ページに移動し** 、新しいアプリケーションを作成します。

        [ **この組織ディレクトリ内のアカウントのみ] を選択します ({microsoft-365-tenant-name} のみ – シングル テナント** です。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. リダイレクト URL の追加: `https://{your-servicenow-instance}.service-now.com/auth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. アプリケーションのクライアント ID を取得し、アプリ シークレットを作成します。

2. \[AAD アプリケーションを作成できるユーザー は、ユーザーのテナントの下に AAD アプリケーション \] for Rest API をMicrosoft 365します。

    1. テナント資格情報を[使用して Azure Portal](https://portal.azure.com/) Microsoft 365ログオンします。

    1. [アプリの **登録] に移動し** 、新しいアプリケーションを作成します。

        [ **この組織ディレクトリ内のアカウントのみ] を選択します ({microsoft-365-tenant-name} のみ – シングル テナント** です。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image22.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. アプリケーションのクライアント ID を取得し、アプリ シークレットを作成します。

3. \[AAD アプリケーションを作成できるユーザー は、ユーザーのテナントの下に \] AAD アプリケーションを作成Microsoft 365します。

    1. テナント資格情報を[使用して Azure Portal](https://portal.azure.com/) Microsoft 365ログオンします。

    1. [アプリの登録 **] ページに移動し** 、新しいアプリケーションを作成します。
        
        [ **この組織ディレクトリ内のアカウントのみ] を選択します ({microsoft-365-tenant-name} のみ – シングル テナント** です。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. アプリケーションのクライアント ID を取得し、アプリ シークレットを作成します。

4. \[ServiceNow 管理者であるユーザー ServiceNow で \] 送信 OAuth プロバイダーを設定します。

    1. スコープがグローバルに設定されていない場合は、開発者設定を開き、グローバル  >    >  に **切り替えます**。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

    1. [System **OAuth アプリケーション**  >  **レジストリ] に移動します**。

    1. サードパーティの OAuth プロバイダーにアクセスする方法を選択してConnectを使用して、新しい **アプリケーションを作成します**。

        - クライアント ID: 前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) の手順 1 で作成されたアプリケーションのクライアント \# ID。

        - クライアント シークレット: 前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) の手順 1 で作成されたアプリケーションのアプリ シークレット \# 。

        - 既定の付与の種類: クライアント資格情報。

        - トークン URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

        - リダイレクト URL:

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

5. \[ServiceNow 管理者であるユーザー ServiceNow で OIDC プロバイダーを構成 \] するには、オンライン ドキュメントを [参照してください](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

    1. スコープがグローバルに設定されていない場合は、開発者設定を開き、グローバル  >    >  に **切り替えます**。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

    1. [System **OAuth アプリケーション**  >  **レジストリ] に移動します**。

    1. [**新しい**  >  **Open ID を作成する] を選択Connectプロバイダーです**。

    1. **[OAuth OIDC プロバイダーの** 構成] で、[検索] を選択し、[oidc プロバイダーの構成.list] の下で、次の値を使用して新しい OIDC プロバイダー構成 \_ \_ を作成します。

    - OIDC プロバイダー: Contoso Azure

    - OIDC メタデータ URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim: **appId**

    - ユーザー フィールド: **ユーザー ID**

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image24.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

    1. [次の値で ID トークンを確認する **OIDC** プロバイダーを構成する] を選択して、新しいアプリケーションを作成します。

    - 名前: contoso \_ アプリケーション \_ の受信 \_ API

    - クライアント ID: 前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) の手順 2 で作成されたアプリケーションのクライアント \# ID。

    - クライアント シークレット: 前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) の手順 2 で作成されたアプリケーションのアプリ \# シークレット。

    - OAuth OIDC プロバイダーの構成: 最後の手順で作成した OIDC プロバイダー。

    - リダイレクト URL:  
        `https://{service-now-instance-name}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image25.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

6. \[ServiceNow 管理者であるユーザー統合 \] ユーザーの作成。

    統合ユーザー **がない**  >  **場合** は、[組織ユーザー] に移動して新しいユーザーを作成します。 User ID の **値は** 、ステップ前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) 3 で作成されたアプリケーション クライアント ID \# です。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image26.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

### <a name="optional-allow-the-services-ips-of-microsoft-365-support-integration"></a>\[オプション \] サービスの IPs をサポート統合Microsoft 365許可する

会社が独自のポリシーを使用してインターネット アクセスを制限している場合は、次の IP アドレスを受信 API アクセスと送信 API アクセスの両方に許可することで、Microsoft 365 サポート統合のサービスのネットワーク アクセスを有効にしてください。

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> このターミナル コマンドは *、nslookup* Microsoft 365をサポートするサービスのすべてのアクティブな CONNECTOR.RAVE.MICROSOFT.COM

### <a name="set-up-microsoft-365-support-integration"></a>サポート統合Microsoft 365設定する

サポートMicrosoft 365統合アプリケーションは、セットアップのサポートの下でセットアップMicrosoft 365できます。

これらの手順は、ServiceNow インスタンスとサービス サポート間の統合Microsoft 365必要です。

1. \[ServiceNow 管理者であるユーザー スコープをサポート統合 \] Microsoft 365切り替えます。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="グラフィカル ユーザー インターフェイス、テーブルの説明が自動的に生成される":::

2. \[ServiceNow 管理者であるユーザー 統合フローを開 \] Microsoft 365セットアップ>**サポート** に移動します。

> [!NOTE]
> "スコープ \_ 'x \_ mioms \_ m365 \_ assis' からの 'oauth エンティティに対する読み取り操作' というエラーがテーブルのクロススコープ アクセス ポリシーによって拒否された場合、テーブル アクセス ポリシーが原因で発生しました。 [読み取り可能なすべての **アプリケーション スコープ]**  >  **がテーブル** oauth エンティティに対してチェックされている必要 \_ があります。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image27.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

3. \[ServiceNow 管理者であるユーザーが同意 \] に **同意** する場合は、[同意する] を選択します。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

4. \[ServiceNow 管理者であるユーザー \] 送信 OAuth プロバイダーを設定します。

前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) の手順 4 で作成された送信 OAuth プロバイダーの OAuth プロファイルを選択し、[次 \# へ] を **選択します**。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

5. \[ServiceNow 管理者であるユーザー \] 受信 OAuth プロバイダーを設定します。

    1. [現在の **手順をスキップする] のチェックを外します**。

    1. [外部 **OIDC 認証トークン] を確認します**。

    1. 前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) の手順 5 で作成した OAuth クライアントを選択し、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image28.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

6. \[ServiceNow 管理者であるユーザー 受信呼び出し統合 \] ユーザーを設定します。

    1. [現在の **手順をスキップする] のチェックを外します**。

    1. 前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) の手順 3 で作成されたアプリケーションのクライアント ID を入力し、[ \# 次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image39.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

7. \[ServiceNow 管理者であるユーザー \] リポジトリ ID を設定します。

    リポジトリ ID を指定し、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

8. \[ServiceNow 管理者であるユーザー [アプリケーションの設定 \] ] 設定。

    次の設定を選択します。

    1. SSO と Microsoft 365: ServiceNow インスタンスがテナントと一緒に SSO をMicrosoft 365します。それ以外の場合はチェックを外します。

    1. Microsoft 365メール: サポート ケースの作成時Microsoft 365問い合わせ先の管理者ユーザー Microsoft 365メール。

    1. テスト環境: このチェック ボックスをオンにして、Microsoft サポート エージェントが問題に対処するために連絡を取るのを避けるためのテスト フェーズを示します。 サポート統合を使用して正式に進む準備ができたらMicrosoft 365チェックを外します。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

    1. [**次へ**] を選択します。

9. \[テナントのヘルプデスク管理者またはサービス要求管理者であるMicrosoft 365 \] 統合を完了します。

    1. 次の情報を確認して、正しいか確認してください。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image40.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. [組織の設定Microsoft 365 [管理ポータル](https://admin.microsoft.com)  >  **設定**  >  **組織**  >  **のプロファイル] に移動します**。

    1. サポート統合設定を設定します。

        1. [基本情報] タブで、内部サポート ツールとして [今すぐサービス] を選択し、[ステップ - 6 統合の完了] ページの [アプリケーション ID の値として送信アプリ **ID]** と入力します。これは、前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token)の手順 1 で作成されました。 \#

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. [リポジトリ **] タブで** 、[リポジトリの **追加] を選択** して、次の情報を含む新しいリポジトリを作成します。

    - リポジトリ: [ステップ - 6 統合の完了] ページのリポジトリ **ID** 値を使用します。

    - Endpoint: **Step** - 6 Complete the integration page の Endpoint 値。

    - 認証の種類: **[AAD Auth] を選択します**。

    - クライアント ID: ステップ - 6 [統合の完了] ページの [クライアント **ID]** の値 。これは、前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) ステップ 2 で作成されたアプリケーションのクライアント ID です \# 。

    - 残りのユーザー名: [ステップ - 6 統合の完了] ページの [ユーザー名] の値 (前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token)ステップ 3 で作成されたアプリケーションのクライアント **ID** です \# 。

    - ユーザーパスワードの保存: 前提条件 [(AAD OAuth トークン)](#prerequisites-aad-oauth-token) の手順 3 で作成されたアプリケーションのアプリ シークレット \# 。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image31.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

    1. 戻って、統合を保存するボタンを選択します。

    1. [次 **へ] を** 選択して統合を完了します。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image32.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

10. \[ServiceNow 管理者であるユーザー 既存のユーザー Microsoft 365 \] サポート統合を有効にする。

Microsoft 365の統合は、次の役割を持つユーザーにのみ有効になります。

- x \_ mioms \_ m365 \_ assis.insights \_ ユーザー

- x \_ mioms \_ m365 \_ assis.administrator

> [!NOTE]
> 役割 x \_ mioms \_ m365 \_ assis.insights ユーザーは、 \_ サービス正常性インシデント、推奨されるソリューションを確認できます。 ロール x \_ mioms \_ m365 assis.administrator を持つユーザーは、サポートを受Microsoft 365 \_ できます。

11. **\[オプション \] \[ 役割を持つユーザー x_mioms_m365_assis.administrator \] リンク Microsoft 365 管理 アカウント**

ユーザーが "x \_ mioms \_ m365 assis.administrator" という役割を持ち、Microsoft サポート ケースを管理するために異なる Microsoft 365 アカウントを使用している場合は、Microsoft 365 サポート > リンク アカウントに移動して \_ 、Microsoft 365 管理者メールを設定する必要があります。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

## <a name="set-up-microsoft-365-support-integration-for-insights-only"></a>サポート統合Microsoft 365のセットアップのみインサイトする

### <a name="prerequisites-insights-only"></a>前提条件 (インサイトのみ)

これらの前提条件の手順は、統合をサポートするためにMicrosoft 365必要です。

1. \[AAD アプリケーションを作成できるユーザー テナントの下に \] AAD アプリケーションMicrosoft 365します。

    1. テナント資格情報を[使用して Azure Portal](https://portal.azure.com/) Microsoft 365ログオンします。

    1. [アプリの登録 **] ページに移動し** 、新しいアプリケーションを作成します。

        [ **この組織ディレクトリ内のアカウントのみ] を選択します ({microsoft-365-tenant-name} のみ – シングル テナント** です。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. リダイレクト URL の追加: `https://{your-servicenow-instance}.service-now.com/auth_redirect.do`

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. アプリケーションのクライアント ID を取得し、アプリ シークレットを作成します。

1. \[ServiceNow 管理者であるユーザー ServiceNow で \] 送信 OAuth プロバイダーを設定します。

    1. スコープがグローバルに設定されていない場合は、開発者設定を開き、グローバル  >    >  に **切り替えます**。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

    1. [System **OAuth アプリケーション**  >  **レジストリ] に移動します**。

    1. サードパーティの OAuth プロバイダーにアクセスする方法を選択してConnectを使用して、新しい **アプリケーションを作成します**。

    - クライアント ID: 前提条件[(インサイトのみ) で作成されたアプリケーションの](#prerequisites-insights-only)クライアント ID  \# 1

    - クライアント シークレット: 前提条件[(インサイトのみ) で作成されたアプリケーションの](#prerequisites-insights-only)アプリ シークレット \# 手順 1

    - 既定の付与の種類: クライアント資格情報

    - トークン URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - リダイレクト URL: `https://{servicenow-instance-name}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image6.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

### <a name="set-up-microsoft-365-support-integration"></a>サポート統合Microsoft 365設定する

サポートMicrosoft 365統合アプリケーションは、[セットアップ] の [サポート **]** でMicrosoft 365できます。

ServiceNow インスタンスと Microsoft サポートの間の統合をセットアップするには、次の手順が必要です。

1. \[ServiceNow 管理者であるユーザー スコープをサポート統合 \] Microsoft 365切り替えます。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image9.png" alt-text="グラフィカル ユーザー インターフェイス、テーブルの説明が自動的に生成される":::

2. \[ServiceNow 管理者であるユーザー 統合フローを開 \] Microsoft 365セットアップ>**サポート** に移動します。

> [!NOTE]
> "スコープ \_ 'x \_ mioms \_ m365 \_ assis' からの 'oauth エンティティに対する読み取り操作' というエラーがテーブルのクロススコープ アクセス ポリシーによって拒否された場合、テーブル アクセス ポリシーが原因で発生しました。 [読み取り可能なすべての **アプリケーション スコープ]**  >  **がテーブル** oauth エンティティに対してチェックされている必要 \_ があります。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image27.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

3. \[ServiceNow 管理者であるユーザーが同意 \] に **同意** する場合は、[同意する] を選択します。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image11.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

4. \[ServiceNow 管理者であるユーザー \] 送信 OAuth プロバイダーを設定します。

[送信 OAuth プロバイダー] で [OAuth プロファイル] を選択し、[次へ] を **選択します**。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image12.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

5. \[ServiceNow 管理者であるユーザーは、 \] 受信 OAuth プロバイダーをスキップします。

    [現在 **の手順をスキップする] を** オンにし、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image33.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

6. \[ServiceNow 管理者であるユーザーは、統合 \] ユーザーをスキップします。

    [現在 **の手順をスキップする] をオン** にし、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image34.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

7. \[ServiceNow 管理者であるユーザー リポジトリ \] ID を設定します。

リポジトリ ID を指定し、[次へ] を **選択します**。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image15.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

8. \[ServiceNow 管理者であるユーザー [アプリケーションの設定 \] ] 設定。

    適切な設定を選択し、[次へ] を **選択します**。

    - SSO と Microsoft 365: ServiceNow インスタンスがテナントと一緒に SSO として設定Microsoft 365します。それ以外の場合はチェックを外します。

    - Microsoft 365 管理メール: サポート ケースMicrosoft 365するときに、管理者ユーザー Microsoft 365メールを送信します。

    - テスト環境: このチェック ボックスをオンにして、Microsoft サポート エージェントが問題に対処するために連絡を取るのを避けるためのテスト フェーズを示します。 サポート統合を使用して正式に進む準備ができたらMicrosoft 365チェックを外します。

    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image16.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

9. \[テナントのヘルプデスク管理者またはサービス要求管理者であるMicrosoft 365 \] 統合を完了します。

    1. ここで情報を確認して、正しいか確認してください。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image35.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. [組織の設定Microsoft 365 [管理ポータル](https://admin.microsoft.com)  >  **設定**  >  **組織**  >  **のプロファイル] に移動します**。

        1. セットアップ フローに表示される情報を使用して、サポート統合設定を設定します。

        1. [基本情報 **] タブで**、内部サポート ツールとして [今すぐサービス] を選択し、OAuth トークンを発行するアプリケーション ID として「送信アプリ **ID」** と入力します。

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image18.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

        1. [リポジトリ **] タブで** 、[リポジトリの **追加] を選択** して、次の情報を含む新しいリポジトリを作成します。

        - リポジトリ: [ **ステップ -** 6 統合の完了] ページのリポジトリ ID 値。

        - Endpoint: **Step** - 6 Complete the integration page の Endpoint 値。

        - 認証の種類: **[AAD Auth] を選択します**。

        - クライアント ID: 無視などのランダムな **値** です。

        - 残りのユーザー名: 無視などのランダムな **値** です。

        - ユーザー パスワードの保存: 無視などのランダムな **値** です。

            :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image36.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

        1. 戻って、統合を保存するボタンを選択します。

    1. [次 **へ] を** 選択して統合を完了します。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image37.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

10. \[ServiceNow 管理者であるユーザー 既存のユーザー Microsoft 365 \] サポート統合を有効にする。

Microsoft 365の統合は、次のユーザー ロールでのみ有効になります。

- x \_ mioms \_ m365 \_ assis.insights \_ ユーザー

- x \_ mioms \_ m365 \_ assis.administrator

> [!NOTE] 
> ロール x_mioms_m365_assis.insights_user を持つユーザーは、[サービス正常性インシデント] [推奨されるソリューション] を表示できます。 ロール x_mioms_m365_assis.administrator を持つユーザーは、サポートを受Microsoft 365できます。 [インサイトのみ] を使用すると、管理者にロールを割りx_mioms_m365_assisする必要があります。

## <a name="testing-the-configuration"></a>構成のテスト

アプリケーションで外部システムとの正常な通信が必要な場合は、接続をテストして構成を正常に行う方法の概要を説明します。

サポート統合の構成をテストする手順Microsoft 365次に示します。

1. 管理者として ServiceNow ポータルにログオンします。

2. インシデントを開きます。

3. [サポート] **Microsoft 365に集中** し、[サポート] タブMicrosoft 365 インサイトを選択して **、推奨** されるソリューションが正常に取得されたかどうかを判断します。

:::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image38.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーション、Web サイトの説明が自動的に生成される":::

##  <a name="troubleshooting"></a>トラブルシューティング

|#|問題|診断アクション|
|--- |--- |--- |
|1|[サポート]**タブMicrosoft 365表示** できない|現在のビューとシステム ログ **すべてフィルター**  >  **を使用** して確認x_mioms_m365_assit|
|2|[Microsoft **推奨ソリューション]** を選択しますが、「ServiceNow 管理者に問い合わせ、アプリのセットアップ手順を完了してください」というエラーが表示されます。|フォームの上部にあるエラー メッセージを確認し、**フィルター** を使用して  >  **システム** ログすべてx_mioms_m365_assit|
|3|[Microsoft **推奨ソリューション]** を選択しますが、「ServiceNow 管理者に問い合わせ、アプリの最終的なセットアップ 手順を完了してください」というエラーが表示されます。|フォームの上部にあるエラー メッセージを確認し、**フィルター** を使用して  >  **システム** ログすべてx_mioms_m365_assit|
|4 |検索ボックスに問題を入力し **、[Microsoft** 推奨ソリューション] を選択しますが、「ServiceNow 管理者に問い合わせ、アプリのセットアップ手順を完了してください」というエラーが表示されます。|フォームの上部にあるエラー メッセージを確認し、**フィルター** を使用して  >  **システム** ログすべてx_mioms_m365_assit|
|5 |検索ボックスに「問題」と入力し **、[Microsoft** 推奨ソリューション] を選択しますが、「ServiceNow 管理者に問い合わせ、アプリの最終的なセットアップ 手順を完了してください」というエラーが表示されます。|フォームの上部にあるエラー メッセージを確認し、**フィルター** を使用して  >  **システム** ログすべてx_mioms_m365_assit|
|6 |[Microsoft **サポートに問** い合わせ] を選択しますが、「ServiceNow 管理者に問い合わせ、アプリのセットアップ手順を完了してください」というエラーが表示されます。|フォームの上部にあるエラー メッセージを確認し、**フィルター** を使用して  >  **システム** ログすべてx_mioms_m365_assit|
|7 |[Microsoft **サポートに問** い合わせ] を選択しますが、「ServiceNow 管理者に問い合わせ、アプリの最終的なセットアップ 手順を完了してください」というエラーが表示されます。|フォームの上部にあるエラー メッセージを確認し、**フィルター** を使用して  >  **システム** ログすべてx_mioms_m365_assit|
|8 |[Microsoft **サポートに問い合** わせ] を選択しますが、"{EmailAddress} は管理者アカウントMicrosoft 365取得します。 サービス要求をMicrosoft 365するには、管理者特権が必要です。 アプリで、管理者アカウントをリンクします。|フォームの上部にあるエラー メッセージを確認し、**フィルター** を使用して  >  **システム** ログすべてx_mioms_m365_assit|
|9 |Microsoft 推奨 **ソリューションを選択します** が、何も表示されません|[ **システム ログの確認] - フィルターログとフィルター処理** を使用 login.microsoftonline.com HTTP ログ connector.rave.microsoft.com|
|10 |[Microsoft **推奨ソリューション] を選択** しますが、「アプリのサポートに問い合わせください」というエラーが表示されます。|フォームの上部にあるエラー メッセージを確認し、**フィルター** を使用して  >  **システム** ログすべてx_mioms_m365_assit|
|11 |検索ボックスに問題を入力し、[Microsoft 推奨ソリューション] **を選択します** が、何も表示されません|[ **システム ログの確認] - フィルターログとフィルター処理** を使用 login.microsoftonline.com HTTP ログ connector.rave.microsoft.com|
|12 |検索ボックスに「問題」と入力し **、[Microsoft 推奨** ソリューション] を選択しますが、「アプリのサポートに問い合わせください」というエラーが表示されます。|フォームの上部にあるエラー メッセージを確認し、**フィルター** を使用して  >  **システム** ログすべてx_mioms_m365_assit|
|13|ユーザーが **[Microsoft サポートに問い合わせ] を** 選択しますが、何も起こりません|[ **システム ログの確認] - フィルターログとフィルター処理** を使用 login.microsoftonline.com HTTP ログ connector.rave.microsoft.com|
|14 |インシデントを再度開いた後に Microsoft 推奨ソリューションを表示できない|[**システム ログ]**  >  **フィルター を使用して**[すべて] をx_mioms_m365_assit|
|15 |Microsoft サポートに転送されたインシデントを再度開くと、Microsoft ケースが表示されません|[**システム ログ]**  >  **フィルター を使用して**[すべて] をx_mioms_m365_assit|
|16 |チケットの詳細を保存できません。エラー "チケットの詳細を保存できません。 アプリのサポートにお問い合わせください。|フォームの上部にあるエラー メッセージを確認する|
