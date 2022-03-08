---
title: ServiceNow とのサポート統合を構成する - 基本認証
f1.keywords:
- NOCSH
ms.author: efrene
author: efrene
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
ms.openlocfilehash: 23fab410b17cea9635c63b0ed0e4225d158dfdc8
ms.sourcegitcommit: bdd6ffc6ebe4e6cb212ab22793d9513dae6d798c
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 03/08/2022
ms.locfileid: "63323851"
---
# <a name="configure-support-integration-with-servicenow---basic-authentication"></a>ServiceNow とのサポート統合を構成する - 基本認証

## <a name="prerequisites-basic-authentication"></a>前提条件 (基本認証)

これらの前提条件は、サポート統合のMicrosoft 365 **必要です**。

1. \[AAD管理者\]テナントAzure AD下にアプリケーションをMicrosoft 365します。

    1. テナント資格情報を使用して Azure Portal にMicrosoft 365し、[アプリの登録] ページに移動して[](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)新しいアプリケーションを作成します。

    1. [ **この組織ディレクトリ内のアカウントのみ] ({Microsoft-365-tenant-name} のみ – シングル テナント)** を選択し、[登録] を選択 **します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [認証] **に移動し** 、[プラットフォーム **の追加] を選択します**。 [ **Web] オプションを** 選択し、リダイレクト URL を入力します。 `https://{your-servicenow-instance``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[ServiceNow 管理者\] ServiceNow で送信 OAuth プロバイダーを設定します。

    スコープがグローバルに設定されていない **場合は、[****&gt;開発者アプリケーション] 設定に&gt;** 移動し、[グローバル] に切り替 **えます**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. [System **OAuth アプリケーション レジストリ &gt; ] に移動します**。

1. サードパーティの **OAuth** プロバイダー オプションにConnectして、次の値を入力して、新しいアプリケーションを作成します。

    - クライアント ID: これは、手順 1 で作成したアプリケーションのクライアント \#ID です。

    - クライアント シークレット: これは、手順 1 で作成したアプリケーションのクライアント シークレット値 \#です。

    - 既定の付与の種類: クライアント資格情報

    - トークン URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - リダイレクト URL: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 受信 OAuth プロバイダーをセットアップします。

    スコープがグローバルに設定されていない **&gt;場合は、開発者向けアプリケーションの設定グローバル&gt;****に切り** 替えます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. [System **OAuth アプリケーション レジストリ &gt; ] に移動します**。

1. [外部クライアント用に OAuth API エンドポイントを作成する] オプションを **使用して、新しいアプリケーションを作成** します。 受信 OAuth プロバイダーに名前を付け、他のすべてのフィールドに既定値を指定します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image7.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image7.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 統合ユーザーを作成します。

    統合ユーザーを指定する必要があります。 既存の統合ユーザー **&gt;** がいない場合、またはこの統合用に作成する場合は、[組織ユーザー] に移動して新しいユーザーを作成します。

    新しい統合ユーザーを作成する場合は、[Web サービスアクセス **のみ] オプションを確認** します。 また、このユーザーに **incidentmanager ロールを付与する\_必要** があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image8.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image8.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[OPTIONAL\] サービスの IP アドレスをサポート統合Microsoft 365許可する

会社が独自のポリシーでインターネット アクセスを制限している場合は、以下の IP アドレスを受信 API アクセスと送信 API アクセスの両方に許可することで、Microsoft 365 サポート統合のサービスのネットワーク アクセスを有効にしてください。

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> このターミナル コマンドは、サポート統合をサポートするサービスのすべてのMicrosoft 365一覧表示します。`nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>統合アプリケーションMicrosoft 365を構成する

サポートMicrosoft 365統合アプリケーションは、サポートの下でMicrosoft 365できます。

これらの手順は、ServiceNow インスタンスとサービス サポート間の統合をMicrosoft 365です。

1. \[ServiceNow Admin\] スコープをサポート統合Microsoft 365 **切り替えます**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="グラフィカル ユーザー インターフェイス、テーブルの説明が自動的に生成される":::

1. \[ServiceNow Admin [\]サポート Microsoft 365 **] に移動&gt;して**、統合ワークフローを開きます。

    > [!NOTE]
    > "スコープ 'xmiomsm365assis\_\_' からの 'oauthentity\_\_' に対する読み取り操作が、テーブルのクロススコープ アクセス ポリシーのために拒否されました」というエラーが表示される場合は、テーブル アクセス ポリシーが原因で発生しました。 [読み取り可能なすべての **アプリケーション スコープ &gt; ] が** テーブルの oauthentity に対してチェックされている必要\_があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image10.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image10.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin Select\] **Agree to continue** .

    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-1.png" lightbox="../../media/ServiceNow-guide/snowbasic-1.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 環境とセットアップの種類を構成します。

    このインストールがテスト環境にインストールされている場合は、[これはテスト環境です] オプションを選択します。 セットアップ後にこのオプションをすばやく無効にし、すべてのテストを後で完了できます。
    インスタンスで受信接続の基本認証が許可されている場合は、[はい] を選択します。それ以外の場合は、[高度なセットアップと接続] [AAD。](servicenow-aad-oauth-token.md) :::image type="content" source="../../media/ServiceNow-guide/snowbasic-2.png" lightbox="../../media/ServiceNow-guide/snowbasic-2.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] テナント ドメインMicrosoft 365入力します。

    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-3.png" lightbox="../../media/ServiceNow-guide/snowbasic-3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin 送信\] 設定を構成します。
    1. アプリのAzure Active Directory (AAD) を登録します。
    1. [前提条件] セクションの手順を完了したら、[完了] をクリック **します**。 それ以外の場合は、ウィザードの指示に従って、アプリケーションに必要なアプリケーション登録を作成AAD。
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-4.png" lightbox="../../media/ServiceNow-guide/snowbasic-4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. ServiceNow OAuth アプリを登録します。
    1. [前提条件] セクションの手順を完了したら、新しく作成した OAuth アプリケーションの登録を選択し、[次へ] をクリックします。 それ以外の場合は、手順に従って ServiceNow でエンティティを作成し、新しいアプリケーション登録を選択します。
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-5.png" lightbox="../../media/ServiceNow-guide/snowbasic-5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin 受信\] 設定を構成します。
    1. 受信 OAuth API エンドポイントを構成します。
    1. [前提条件] セクションの手順を完了したら、新しく作成した OAuth アプリケーションの登録を選択し、[完了] をクリックします。 それ以外の場合は、指示に従ってエンティティを作成し、新しい REST エンドポイント登録を選択します。
     
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-6.png" lightbox="../../media/ServiceNow-guide/snowbasic-6.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. 統合ユーザーを構成します。
    1. [前提条件] セクションの手順を完了したら、新しく作成した統合ユーザーを選択し、[次へ] をクリックします。 それ以外の場合は、手順に従って ServiceNow でエンティティを作成し、新しい統合ユーザーを選択します。
    
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-7.png" lightbox="../../media/ServiceNow-guide/snowbasic-7.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::


1. \[Microsoft 365テナント管理者\]ポータルの統合をMicrosoft 365 管理します。

    以下の情報が正しいか確認します。 この時点で [ **次へ]** を選択しない。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image17.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image17.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. [ポータル] **Microsoft 365 管理組織設定&gt;&gt;に&gt;移動します**。

1. サポート統合設定を構成します。

    [内部サポート **ツールServiceNow]** > **[** > 基本情報] タブを選択し、[認証トークンを発行するアプリケーション ID] フィールドに [送信アプリ **ID**] の値 **を入力** します。 この送信アプリ ID は、手順 6 – 前提条件 (基本認証) の手順 1 で作成された統合 [を \#完了します](#prerequisites-basic-authentication)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [リポジトリ **] タブで** 、[新しい **リポジトリ] を選択** し、次の設定で更新します。

    - リポジトリ: 手順 6 のリポジトリ **ID** 値 – 統合を完了します。

    - エンドポイント: 手順 6 の **Endpoint** 値 – 統合を完了します。

    - 認証の種類: [ **基本認証] を選択します**。

    - クライアント ID: 手順 6 のクライアント **ID** の値 – 統合を完了します。

    - クライアント シークレット: 前提条件 (基本認証) \#手順 3 で作成された受信 OAuth プロバイダーのシークレット。

    - 更新トークンの有効期限: 864000

    - 残りのユーザー名: **手順** 6 の [ユーザー名] の値 – 統合を完了します。

    - ユーザーの残りのパスワード: 前提条件 (基本認証 [) \#手順 4](#prerequisites-basic-authentication) で作成された統合ユーザーのパスワード。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image19.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image19.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. ServiceNow に戻る。

1. [次 **へ] を** 選択して統合を完了します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image20.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image20.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーション、Web サイトの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 接続のテスト 前の手順を完了した後、[接続のテスト] **をクリックします**。
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-8.png" lightbox="../../media/ServiceNow-guide/snowbasic-8.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    統合Microsoft 365アプリはテストを実行して、統合が機能しているのを確認します。 構成に問題がある場合は、修正する必要がある内容を説明するエラー メッセージが表示されます。 それ以外の場合は、アプリケーションの準備ができました。
     :::image type="content" source="../../media/ServiceNow-guide/snowbasic-9.png" lightbox="../../media/ServiceNow-guide/snowbasic-9.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 既存のユーザーに対する Microsoft サポート統合を有効にする。

    Microsoft 365の役割のいずれかを持つユーザーに対して、サポート統合が有効になっている場合。

    - xmiomsm365assis.insightsuser\_\_\_\_

    - xmiomsm365assis.administrator\_\_\_

1. \[OPTIONAL\] [役割を持つユーザー x_mioms_m365_assis.administrator リンク] アカウントMicrosoft 365 管理リンクします。

    ユーザーが役割 x_mioms_m365_assis.administrator を持ち、Microsoft 365 サポート ケースを管理するために異なる Microsoft 365 アカウントを使用している場合は、Microsoft 365 サポート > リンク アカウントに移動して、Microsoft 365 管理者メールを設定する必要があります。
    
    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::
