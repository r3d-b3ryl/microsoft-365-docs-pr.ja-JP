---
title: Microsoft 365正常性インシデントと推奨ソリューションの統合のみをサポートする
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
ms.openlocfilehash: 427b4b20b33d83676e2cbebbfb6dcd627bcd51fe
ms.sourcegitcommit: bf3965b46487f6f8cf900dd9a3af8b213a405989
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 11/02/2021
ms.locfileid: "60661920"
---
# <a name="microsoft-365-support-integration-for-service-health-incidents-and-recommended-solutions-only"></a>Microsoft 365正常性インシデントと推奨ソリューションの統合のみをサポートする

この構成では、ServiceNow インスタンスを介して Microsoft サポートを使用してケースを作成できない。 このオプションでは、ServiceNow インスタンスで使用可能なサービス正常性インシデント情報とおすすめソリューションのみを提供します。

## <a name="prerequisites-service-health-incidents-and-recommended-solutions-only"></a>前提条件 (サービス正常性インシデントと推奨されるソリューションのみ)

これらの前提条件は、サポート統合のMicrosoft 365 **必要です**。

1. \[AAD管理者 \] テナントのAAD送信用のアプリケーションを作成Microsoft 365します。

    1. テナント資格情報を使用して Azure Portal Microsoft 365ログオンし、[アプリの登録] ページで新しい[アプリケーションを作成します](https://portal.azure.com/?Microsoft_AAD_RegisteredApps=true#blade/Microsoft_AAD_RegisteredApps/ApplicationsListBlade)。

    2. [ **この組織ディレクトリ内のアカウントのみ] ({Microsoft-365-tenant-name}** のみ - シングル テナント) を選択し、[登録] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image3.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image3.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [認証] **に移動し** 、[プラットフォームの **追加] を選択します**。 **[Web] オプションを** 選択し、リダイレクト URL を入力します。`https://{your-servicenow-instance``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image4.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image4.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. アプリケーション クライアント ID を取得し、クライアント シークレットを作成し、その値を取得します。

1. \[ServiceNow 管理者 \] ServiceNow で送信 OAuth プロバイダーを設定します。

    スコープがグローバルに設定されていない場合 **は、[開発者** アプリケーション] 設定 **&gt; に &gt;** 移動し、[グローバル] に **切り替えます**。

    :::image type="content" source="../../media/ServiceNow-guide/Servicenow-guide-image5.png" lightbox="../../media/ServiceNow-guide/Servicenow-guide-image5.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、チャット、またはテキスト メッセージ説明が自動的に生成される":::

1. [System **OAuth &gt; アプリケーション レジストリ] に移動します**。

1. サード パーティの **OAuth** プロバイダー オプションConnectを使用して新しいアプリケーションを作成し、次の値を入力します。

    - クライアント ID: これは、前提条件 (インサイトのみ) の手順 1 で作成されたアプリケーションのクライアント \# ID です。

    - クライアント シークレット: これは、前提条件 (インサイトのみ) の手順 1 で作成されたアプリケーションのクライアント シークレット値 \# です。

    - 既定の付与の種類: クライアント資格情報

    - トークン URL: `https://login.microsoftonline.com/{microsoft-365-tenant-name}/oauth2/token`

    - リダイレクト URL: `https://{service-now-instance-name``}.service-now.com/auth_redirect.do`

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image6.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image6.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

## <a name="configure-the-microsoft-365-support-integration-application"></a>サポート統合アプリケーションMicrosoft 365構成する

サポートMicrosoft 365統合アプリケーションは、サポートの下でMicrosoft 365できます。

これらの手順は、ServiceNow インスタンスとサービス サポート間の統合をMicrosoft 365です。

1. \[ServiceNow Admin \] スコープをサポート統合Microsoft 365 **に切り替えます**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image9.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image9.png" alt-text="グラフィカル ユーザー インターフェイス、テーブルの説明が自動的に生成される":::

1. \[ServiceNow Admin \] [サポート **Microsoft 365] に移動 &gt; して**、統合ワークフローを開きます。

    > [!NOTE]
    > "スコープ \_ 'x \_ mioms \_ m365 \_ assis' からの 'oauth エンティティに対する読み取り操作' というエラーがテーブルのクロススコープ アクセス ポリシーによって拒否された場合、テーブル アクセス ポリシーが原因で発生しました。 [読み取り可能なすべての **アプリケーション スコープ] &gt; がテーブル** oauth エンティティに対してチェックされている必要 \_ があります。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image27.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image27.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin \] Select **Agree to continue.**

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image11.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image11.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin \] 送信 OAuth プロバイダーを設定します。

    送信 OAuth プロバイダーの OAuth プロファイルを選択し、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image12.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image12.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. \[ServiceNow Admin \] 受信 OAuth プロバイダーをスキップします。

    [現在 **の手順をスキップする] を** オンにし、[次へ] を **選択します**。

1. \[ServiceNow Admin \] 受信呼び出し統合ユーザーをスキップします。

    [現在 **の手順をスキップする] を** オンにし、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image34.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image34.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin \] リポジトリ ID を設定します。

    リポジトリ ID を指定し、[次へ] を **選択します**。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image15.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image15.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin \] アプリケーション のセットアップ 設定。

    これらの設定を選択し、[次へ] を **選択します**。

    - SSO と Microsoft 365: ServiceNow インスタンスが SSO として設定されているかどうかを確認し、Microsoft 365チェックを外します。

    - Microsoft 365メール: サポート ケースの作成時にMicrosoft 365された管理者ユーザー Microsoft 365メール。

    - テスト環境: このチェック ボックスをオンにして、Microsoft サポート エージェントが問題に対処するために連絡を取るのを避けるためのテスト フェーズを示します。 サポート統合を使用して正式に進む準備ができたらMicrosoft 365チェックを外します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image16.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image16.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーションの説明が自動的に生成される":::

1. \[Microsoft 365テナント管理者 \] 統合を完了します。

    以下の情報が正しいか確認します。 この時点で [ **次へ]** を選択しない。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image35.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image35.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [ポータル] **Microsoft 365 管理組織 &gt; 設定 &gt; に &gt; 移動します**。

1. サポート統合設定を構成します。

    [内部サポート **ツール ServiceNow]** > [基本情報] タブを選択し、[OAuth トークンを発行するアプリケーション ID] フィールドに [送信アプリ  >  **ID]** の値 **を入力** します。 この送信アプリ ID は、手順 6 – 前提条件 (インサイト のみ) の手順 1 で作成された統合[を \# 完了します](#prerequisites-service-health-incidents-and-recommended-solutions-only)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image18.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image18.png" alt-text="グラフィカル ユーザー インターフェイス、テキスト、アプリケーション、電子メールの説明が自動的に生成される":::

1. [リポジトリ **] タブで** 、[リポジトリの **追加] を選択** して、次の設定で新しいリポジトリを作成します。

    - リポジトリ: 手順 6 のリポジトリ **ID** 値 – 統合を完了します。

    - エンドポイント: 手順 6 の **Endpoint** 値 – 統合を完了します。

    - 認証の種類: [**認証AAD選択します**。

    - クライアント ID: ランダムな値 (例: 無視)。

    - Rest username: ランダムな値 (例: 無視)。

    - ユーザー パスワードの保存: ランダムな値 (例: 無視)。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image36.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image36.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. ServiceNow に戻る。

1. [次 **へ] を** 選択して統合を完了します。

    :::image type="content" source="../../media/ServiceNow-guide/servicenow-guide-image37.png" lightbox="../../media/ServiceNow-guide/servicenow-guide-image37.png" alt-text="グラフィカル ユーザー インターフェイス、アプリケーションの説明が自動的に生成される":::

1. \[ServiceNow Admin \] 既存のユーザーに対する Microsoft サポート統合を有効にする。

    Microsoft 365の役割のいずれかを持つユーザーに対してサポート統合が有効になります。

    - x \_ mioms \_ m365 \_ assis.insights \_ ユーザー

    - x \_ mioms \_ m365 \_ assis.administrator

    > [!NOTE]
    > 役割 x \_ mioms \_ m365 \_ assis.insights ユーザーは、 \_ サービス正常性インシデント、推奨されるソリューションを確認できます。 ロール x \_ mioms \_ m365 assis.administrator を持つユーザーは、サポートを受Microsoft 365 \_ できます。 [インサイトのみ] では、役割 x \_ mioms \_ m365 assis.administrator を割り当 \_ てる必要はありません。
