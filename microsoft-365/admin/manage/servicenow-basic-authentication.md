---
title: ServiceNow - Basic Authentication とのサポート統合を構成する
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
# <a name="configure-support-integration-with-servicenow---basic-authentication"></a>ServiceNow - Basic Authentication とのサポート統合を構成する

## <a name="prerequisites-basic-authentication"></a>前提条件 (基本認証)

これらの前提条件は、**Microsoft 365サポート統合** を設定するために必要です。

1. \[AAD管理者\]Microsoft 365 テナントの下にAzure ADアプリケーションを作成します。

    1. Microsoft 365 テナント資格情報を使用して Azure Portal にログオンし、[アプリの登録 ページ](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)に移動して新しいアプリケーションを作成します。

    1. **この組織ディレクトリ内のアカウントのみ ({Microsoft-365-tenant-name} のみ – シングル テナント)** を選択し、[登録] を選択 **します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. **[認証]** に移動し、[**プラットフォームの追加]** を選択します。 **Web** オプションを選択し、リダイレクト URL を入力します。`https://{your-servicenow-instance``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[ServiceNow 管理者\] は、ServiceNow で送信 OAuth プロバイダーを設定します。

    スコープが **グローバル** に設定されていない場合は、**開発者&gt;アプリケーション設定&gt;** 移動し、**グローバル** に切り替えます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. **System OAuth &gt; アプリケーション レジストリ** に移動します。

1. **サードパーティの OAuth プロバイダー オプションにConnect** を使用し、次の値を入力して、新しいアプリケーションを作成します。

    - クライアント ID: これは、手順 \#1 で作成したアプリケーションのクライアント ID です。

    - クライアント シークレット: これは、手順 \#1 で作成したアプリケーションのクライアント シークレットの値です。

    - 既定の許可の種類: クライアント資格情報

    - トークン URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - リダイレクト URL: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow 管理者\] は、受信 OAuth プロバイダーを設定します。

    スコープが **グローバル** に設定されていない場合は、**開発者&gt;アプリケーションを設定&gt;** して **グローバル** に切り替えます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. **System OAuth &gt; アプリケーション レジストリ** に移動します。

1. **[外部クライアント用に OAuth API エンドポイントを作成する**] オプションを使用して、新しいアプリケーションを作成します。 受信 OAuth プロバイダーに名前を付け、他のすべてのフィールドに既定値を付けます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image7.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image7.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 統合ユーザーを作成します。

    統合ユーザーを指定する必要があります。 既存の統合ユーザーがない場合、またはこの統合専用の統合ユーザーを作成する場合は、 **組織 &gt; ユーザー** に移動して新しいユーザーを作成します。

    新しい統合ユーザーを作成する場合は、 **Web サービスアクセスのみ** オプションをオンにします。 また、このユーザーに **incidentmanager\_** ロールを付与する必要もあります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image8.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image8.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[オプション\]: サービスの IP アドレスが統合をサポートMicrosoft 365許可する

会社が独自のポリシーでインターネット アクセスを制限している場合は、受信 API アクセスと送信 API アクセスの両方に対して以下の IP アドレスを許可することで、Microsoft 365サポート統合のサービスのネットワーク アクセスを有効にします。

- 52.149.152.32

- 40.83.232.243

- 40.83.114.39

- 13.76.138.31

- 13.79.229.170

- 20.105.151.142

> [!NOTE]
> このターミナル コマンドは、Microsoft 365サポート統合のためにサービスのすべてのアクティブ IP を一覧表示します。`nslookup`` connector.rave.microsoft.com`

## <a name="configure-the-microsoft-365-support-integration-application"></a>Microsoft 365 サポート統合アプリケーションを構成する

Microsoft 365サポート統合アプリケーションは、Microsoft 365サポートで設定できます。

ServiceNow インスタンスとサポートMicrosoft 365間の統合を設定するには、次の手順が必要です。

1. \[ServiceNow Admin\] スコープを **Microsoft 365サポート統合** に切り替えます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="グラフィカル ユーザー インターフェイス、テーブルの説明が自動的に生成される":::

1. \[ServiceNow 管理者\]**は、Microsoft 365サポート&gt;設定** に移動して統合ワークフローを開きます。

    > [!NOTE]
    > "xmiomsm365assis" スコープ 'xmiomsm365assis\_\_\_' からの "oauthentity\_" に対する読み取り操作がテーブルのクロススコープ アクセス ポリシーのために拒否されました"というエラーが表示された場合は、テーブル アクセス ポリシーが原因で発生しました。 **すべてのアプリケーション スコープ&gt;で読み取り可能** かどうかを確認し、テーブルの認証\_性を確認する必要があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image10.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image10.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow 管理者\] が **[同意する** ] を選択して続行します。

    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-1.png" lightbox="../../media/ServiceNow-guide/snowbasic-1.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 環境とセットアップの種類を構成します。

    このインストールがテスト環境にある場合は、[これはテスト環境] オプションを選択します。 セットアップ後にこのオプションをすぐに無効にでき、すべてのテストが後で完了します。
    インスタンスで受信接続の基本認証が許可されている場合は、[はい] を選択します。それ以外の場合は、[AADを使用した高度なセットアップ](servicenow-aad-oauth-token.md)を参照してください。 :::image type="content" source="../../media/ServiceNow-guide/snowbasic-2.png" lightbox="../../media/ServiceNow-guide/snowbasic-2.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] Microsoft 365テナント ドメインを入力します。

    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-3.png" lightbox="../../media/ServiceNow-guide/snowbasic-3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow 管理者\] 送信設定を構成します。
    1. Azure Active Directory (AAD) アプリを登録します。
    1. 前提条件セクションの手順を完了したら、[完了] をクリック **します**。 それ以外の場合は、ウィザードの指示に従って、AADで必要なアプリケーションの登録を作成します。
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-4.png" lightbox="../../media/ServiceNow-guide/snowbasic-4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. ServiceNow OAuth アプリを登録します。
    1. 前提条件セクションの手順を完了したら、新しく作成した OAuth アプリケーションの登録を選択し、[次へ] をクリックします。 それ以外の場合は、指示に従って ServiceNow でエンティティを作成し、新しいアプリケーション登録を選択します。
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-5.png" lightbox="../../media/ServiceNow-guide/snowbasic-5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow 管理者\] 受信設定を構成します。
    1. 受信 OAuth API エンドポイントを構成します。
    1. 前提条件セクションの手順を完了したら、新しく作成した OAuth アプリケーションの登録を選択し、[完了] をクリックします。 それ以外の場合は、指示に従ってエンティティを作成し、新しい REST エンドポイント登録を選択します。
     
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-6.png" lightbox="../../media/ServiceNow-guide/snowbasic-6.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. 統合ユーザーを構成します。
    1. 前提条件セクションの手順を完了したら、新しく作成した統合ユーザーを選択し、[次へ] をクリックします。 それ以外の場合は、指示に従って ServiceNow でエンティティを作成し、新しい統合ユーザーを選択します。
    
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-7.png" lightbox="../../media/ServiceNow-guide/snowbasic-7.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::


1. \[Microsoft 365 テナント管理者\]Microsoft 365 管理 ポータルで統合を完了します。

    次の情報が正しいことを確認します。 現時点では、[ **次へ** ] を選択しないでください。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image17.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image17.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. **Microsoft 365 管理 ポータル&gt;設定&gt;組織の設定&gt;組織プロファイル** に移動します。

1. サポート統合設定を構成します。

    **[内部サポート ツール** > **ServiceNow**] > [**基本情報**] タブを選択し、[アプリケーション ID] に **[送信アプリ ID**] の値 **を入力して[認証トークン] フィールドを発行** します。 この送信アプリ ID は、手順 6 - 前提条件 [(基本認証) 手順 1 で作成された統合を完了します\#](#prerequisites-basic-authentication)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [ **リポジトリ]** タブで、[ **新しいリポジトリ** ] を選択し、次の設定で更新します。

    - リポジトリ: 手順 6 の **リポジトリ ID** の値 – 統合を完了します。

    - エンドポイント: 手順 6 の **エンドポイント** 値 – 統合を完了します。

    - 認証の種類: **[基本認証**] を選択します。

    - クライアント ID: 手順 6 の **クライアント ID** 値 – 統合を完了します。

    - クライアント シークレット: 前提条件 (基本認証) 手順 \#3 で作成された受信 OAuth プロバイダーのシークレット。

    - 更新トークンの有効期限: 864000

    - 残りのユーザー名: 手順 6 の **ユーザー名** の値 – 統合を完了します。

    - Rest user password: [前提条件 (基本認証) 手順 \#4](#prerequisites-basic-authentication) で作成された統合ユーザーのパスワード。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image19.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image19.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. ServiceNow に戻るします。

1. **[次へ**] を選択して統合を完了します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image20.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image20.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーション、Web サイトの説明が自動的に生成される":::

1. \[ServiceNow 管理者\] が接続をテストする 前の手順を完了したら、[ **接続のテスト**] をクリックします。
    :::image type="content" source="../../media/ServiceNow-guide/snowbasic-8.png" lightbox="../../media/ServiceNow-guide/snowbasic-8.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    Microsoft 365サポート統合アプリは、統合が機能していることを確認するためにテストを実行します。 構成に問題がある場合は、エラー メッセージで修正する必要がある内容が説明されます。 それ以外の場合は、アプリケーションの準備が整います。
     :::image type="content" source="../../media/ServiceNow-guide/snowbasic-9.png" lightbox="../../media/ServiceNow-guide/snowbasic-9.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 既存のユーザーに対する Microsoft サポート統合を有効にします。

    Microsoft 365サポート統合は、次のいずれかのロールを持つユーザーに対して有効になります。

    - xmiomsm365assis.insightsuser\_\_\_\_

    - xmiomsm365assis.administrator\_\_\_

1. \[省略可能\] [ロールを持つユーザー x_mioms_m365_assis.administrator link] アカウントMicrosoft 365 管理リンクします。

    x_mioms_m365_assis.administrator ロールを持ち、別のMicrosoft 365 アカウントを使用してMicrosoft 365サポート ケースを管理しているユーザーは、Microsoft 365サポート >リンク アカウントに移動して、Microsoft 365管理者メールを設定する必要があります。
    
    :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image21.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::
