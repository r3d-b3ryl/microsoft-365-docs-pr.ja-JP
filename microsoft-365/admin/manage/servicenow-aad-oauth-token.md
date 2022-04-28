---
title: Azure AD認証トークンとの統合をサポートMicrosoft 365構成する
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
ms.openlocfilehash: d3991355779228cf1562e23ddd0e97cb37225a43
ms.sourcegitcommit: e50c13d9be3ed05ecb156d497551acf2c9da9015
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 04/27/2022
ms.locfileid: "65093748"
---
# <a name="configure-microsoft-365-support-integration-with-azure-ad-auth-token"></a>Azure AD認証トークンとの統合をサポートMicrosoft 365構成する

## <a name="prerequisites-azure-ad-auth-token"></a>前提条件 (Azure AD認証トークン)

これらの前提条件は、Microsoft 365サポート統合を設定するために必要です。

1. \[AAD管理者\]Microsoft 365 テナントの下にAzure AD送信用アプリケーションを作成します。

    1. Microsoft 365 テナント資格情報を使用して Azure Portal にログオンし、[アプリの登録 ページ](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)に移動して新しいアプリケーションを作成します。

    2. **この組織ディレクトリ内のアカウントのみ ({Microsoft-365-tenant-name} のみ – シングル テナント)** を選択し、[登録] を選択 **します**。

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. **[認証]** に移動し、[**プラットフォームの追加]** を選択します。 **Web** オプションを選択し、リダイレクト URL を入力します。`https://{your-servicenow-instance``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[AAD管理者\]Microsoft 365 テナントの下に、Azure AD Application for Rest API を作成します。

    1. Microsoft 365 テナント資格情報を使用して [Azure Portal](https://portal.azure.com/) にログオンし、アプリの登録 ページに移動して新しいアプリケーションを作成します。

    1. **この組織ディレクトリ内のアカウントのみ {(Microsoft-365-tenant-name} のみ – シングル テナント)** を選択します。

        :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image22.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image22.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[AAD管理者\]Microsoft 365 テナントの下に、Azure AD Application for Rest ユーザーを作成します。

    1. Microsoft 365 テナント資格情報を使用して [Azure Portal](https://portal.azure.com/) にログオンし、アプリの登録 ページに移動して新しいアプリケーションを作成します。

    1. **この組織ディレクトリ内のアカウントのみ {(Microsoft-365-tenant-name} のみ – シングル テナント)** を選択します。

        :::image type="content" source="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" lightbox="../../media/ServiceNow-guide/ServiceNow-guide-image23.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[ServiceNow 管理者\] は、ServiceNow で送信 OAuth プロバイダーを設定します。

    スコープが **グローバル** に設定されていない場合は、**設定&gt;開発者&gt;アプリケーション** に移動して **グローバル** に切り替えます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. **System OAuth &gt; アプリケーション レジストリ** に移動します。

1. **サードパーティの OAuth プロバイダー オプションへのConnect** を使用して、次の値を入力して新しいアプリケーションを作成します。

    - クライアント ID: これは、前提条件 (Azure AD認証トークン) 手順 \#1 で作成されたアプリケーションのクライアント ID です。

    - クライアント シークレット: これは、前提条件 (Azure AD認証トークン) 手順 \#1 で作成されたアプリケーションのクライアント シークレット値です。

    - 既定の許可の種類: クライアント資格情報

    - トークン URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - リダイレクト URL: `https://{service-now-instance-name``}.service-now.com/oauth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin\] ServiceNow で OIDC プロバイダーを構成するには、 [オンライン ドキュメントを参照してください](https://docs.servicenow.com/bundle/quebec-platform-administration/page/administer/security/task/add-OIDC-entity.html)。

    スコープが **グローバル** に設定されていない場合は、**開発者&gt;アプリケーション設定&gt;** 移動し、**グローバル** に切り替えます。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. **System OAuth &gt; アプリケーション レジストリ** に移動します。

1. [**新規**] を選択し、[**新しいオープン ID Connect プロバイダーの作成**] を選択します。

1. **OAuth OIDC プロバイダー構成** で、**検索** を選択し、**oidcproviderconfiguration.list\_ の下に次の値を使用して新しい OIDC\_ プロバイダー構成** を作成します。

    - OIDC プロバイダー: **{TenantName\_} Azure** (例: Contoso Azure)

    - OIDC メタデータ URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/.well-known/openid-configuration`

    - UserClaim: **appid**

    - UserField: **ユーザー ID**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image24.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image24.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. 次の値で **ID トークンを確認する OIDC プロバイダーを構成する** を選択して、新しいアプリケーションを作成します。

    - 名前: **{TenantName\_}\_applicationinboundapi\_\_** (例: contosoapplicationinboundapi\_\_\_)

    - クライアント ID: 前提条件 (Azure AD認証トークン) 手順 \#3 で作成されたアプリケーションのクライアント ID。

    - クライアント シークレット: 前提条件 (Azure AD認証トークン) 手順 \#3 で作成されたアプリケーションのアプリ シークレット。

    - OAuth OIDC プロバイダーの構成: 前の手順で作成した OIDC プロバイダー

    - リダイレクト URL: `https://{service-now-instance-name}.service-now.com/oauth\_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image25.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image25.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow 管理者\] が統合ユーザーを作成します。

    統合ユーザーを指定する必要があります。 既存の統合ユーザーがない場合、またはこの統合専用の統合ユーザーを作成する場合は、 **組織 &gt; ユーザー** に移動して新しいユーザーを作成します。 **ユーザー ID** の値は、[前提条件 (Azure AD認証トークン)](#prerequisites-azure-ad-auth-token) で作成されたアプリケーション クライアント ID です。

    新しい統合ユーザーを作成する場合は、 **Web サービスアクセスのみ** オプションをオンにします。 また、このユーザーに **incidentmanager\_** ロールを付与する必要もあります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image26.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image26.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

## <a name="optional-allow-the-services-ip-addresses-to-microsoft-365-support-integration"></a>\[オプション\]: サービスの IP アドレスが統合をサポートMicrosoft 365許可する

会社が独自のポリシーでインターネット アクセスを制限している場合は、受信 API と送信 API アクセスの両方に対して以下の IP アドレスを許可することで、Microsoft 365サポート統合のサービスのネットワーク アクセスを有効にします。

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

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow 管理者\] は **、同意** プロンプトに同意を選択して続行します。

    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-1.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-1.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 環境とセットアップの種類を構成します。
    このインストールがテスト環境にある場合は、[これはテスト環境] オプションを選択します。 セットアップ後にこのオプションをすぐに無効にでき、すべてのテストが後で完了します。
    インスタンスで受信接続の基本認証が許可されている場合は、[はい] を選択し、 [Basic Auth セットアップ プロセス](servicenow-basic-authentication.md)を参照してください。 それ以外の場合 **は、[いいえ** ] を選択し、[ **セットアップの開始]** をクリックします。 
      :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-2.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-2.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] Microsoft 365テナント ドメインを入力します。
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-3.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow 管理者\] は、送信 OAuth プロバイダーを構成します。
    1. 送信 OAuth プロバイダーを構成します。
    1. 前提条件セクションの手順を完了したら、[完了] をクリックします。 それ以外の場合は、ウィザードの指示に従って、AADで必要なアプリケーションの登録を作成します。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-4.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    1. ServiceNow OAuth アプリを登録します。
    1. 前提条件セクションの手順を完了したら、新しく作成した OAuth アプリケーションの登録を選択し、[次へ] をクリックします。 それ以外の場合は、指示に従って ServiceNow でエンティティを作成し、新しいアプリケーション登録を選択します。
     :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-5.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow 管理者\] 受信設定を構成します。
    1. 受信AAD アプリを構成します。
    1. 前提条件セクションの手順を完了したら、[完了] をクリックして次の手順に進みます。 それ以外の場合は、指示に従って、受信接続のAADアプリ登録を作成します。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-6.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-6.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    1. ServiceNow 外部 OpenID Connect プロバイダー (OIDC プロバイダー) を構成します。
    1. 前提条件セクションの手順を完了したら、新しく作成したエンティティを選択し、[完了] をクリックします。 それ以外の場合は、指示に従って ServiceNow でエンティティを作成し、新しい外部 OIDC プロバイダー アプリの登録を選択します。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-7.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-7.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    1. 受信統合ユーザーのAADアプリ登録を構成します。
    1. 前提条件セクションの手順を完了したら、[完了] をクリックして次の手順に進みます。 それ以外の場合は、指示に従って、受信 REST ユーザー (統合ユーザー) のAADアプリ登録を作成します。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-8.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-8.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    1. 統合ユーザーを構成します。
    1. 前提条件セクションの手順を完了したら、新しく作成したエンティティを選択し、[次へ] をクリックします。 それ以外の場合は、指示に従って ServiceNow で統合ユーザーを作成し、エンティティを選択します。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-9.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-9.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[Microsoft 365 テナント管理者\]統合を完了します。

    次の情報が正しいことを確認します。 現時点では、[ **次へ** ] を選択しないでください。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image40.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image40.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. **Microsoft 365 管理 ポータル&gt;設定&gt;組織の設定&gt;組織プロファイル** に移動します。

    1. サポート統合設定を構成します。

    **[内部サポート ツール** > **ServiceNow**] > [**基本情報**] タブを選択し、[アプリケーション ID] に **[送信アプリ ID**] の値 **を入力して[認証トークン] フィールドを発行** します。 この送信アプリ ID は手順 6 で完了します。統合は、[前提条件 (Azure AD認証トークン)](#prerequisites-azure-ad-auth-token) で作成されました。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

    1. [ **リポジトリ]** タブで、[ **新しいリポジトリ** ] を選択し、次の設定で更新します。

    - リポジトリ: "手順 6 - 統合を完了する" の **リポジトリ ID** 値。

    - エンドポイント: "手順 6 - 統合を完了する" の **エンドポイント** 値。

    - 認証の種類: **[AAD認証**] を選択します。

    - クライアント ID: 手順 6 の **クライアント ID** 値 – 統合を完了します。

    - クライアント シークレット: 前提条件 (Azure AD認証トークン) 手順 \#2 で作成された受信 OAuth プロバイダーのシークレット。

    - 残りのユーザー名: 手順 6 の **ユーザー名** の値。 統合を完了します。これは、前提条件 (Azure AD認証トークン) 手順 \#3 で作成されたアプリケーションの **クライアント ID** です。

    - Rest ユーザー パスワード: 前提条件 (Azure AD認証トークン) 手順 \#3 で作成されたアプリケーションのアプリ シークレット。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image31.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image31.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

    1. ServiceNow に戻るします。

    1. **[次へ**] を選択して統合を完了します。

   :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-10.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-10.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::
    Microsoft 365サポート統合アプリは、統合が機能していることを確認するためにテストを実行します。 構成に問題がある場合は、エラー メッセージで修正する必要がある内容が説明されます。 それ以外の場合は、アプリケーションの準備が整います。
    :::image type="content" source="../../media/ServiceNow-guide/snowaadoauth-11.png" lightbox="../../media/ServiceNow-guide/snowaadoauth-11.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin\] 既存のユーザーに対する Microsoft サポート統合を有効にします。

    Microsoft 365サポート統合は、次のいずれかのロールを持つユーザーに対して有効になります。

    - xmiomsm365assis.insightsuser\_\_\_\_

    - xmiomsm365assis.administrator\_\_\_

1. \[OPTIONAL\] \[ロール xmiomsm365assis.administrator\_\_\_ link\] link Microsoft 365管理者アカウントを持つユーザー。

    いずれかのユーザーが xmiomsm365assis.administrator\_\_\_ ロールを持ち、異なるMicrosoft 365 アカウントを使用してMicrosoft 365サポート ケースを管理している場合は、Microsoft 365管理者メールを設定するためにリンク アカウントをサポート&gt;Microsoft 365に移動する必要があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image21.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image21.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::
