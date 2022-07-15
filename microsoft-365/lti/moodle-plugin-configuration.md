---
title: Moodle LMS プラグインを設定して構成する
ms.author: danismith
author: DaniEASmith
manager: serdars
ms.reviewer: amitman
audience: admin
ms.topic: article
ms.service: o365-administration
f1.keywords:
- CSH
ms.collection: M365-modern-desktop
ms.localizationpriority: medium
description: Moodle LMS プラグインを設定して構成することで、Moodle と Microsoft Teams を統合する準備を整えます。
ms.openlocfilehash: b1188878c8d0af5041bf25bb566dc0707f4e5ad4
ms.sourcegitcommit: 5e5c2c1f7c321b5eb1c5b932c03bdd510005de13
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/15/2022
ms.locfileid: "66823182"
---
# <a name="set-up-the-moodle-lms-plugins"></a>Moodle LMS プラグインを設定する

この記事では、Moodle LMS プラグインをインストールして構成し、Moodle エクスペリエンスに Microsoft Teams を組み込む方法について説明します。

## <a name="prerequisites"></a>前提条件

Microsoft Teams で動作するようにインストール済みの Moodle を設定するための前提条件を次に示します。

* Moodle 管理者の資格情報。
* Azure AD 管理者の資格情報。
* 新しいリソースを作成できる Azure サブスクリプション。

## <a name="1-install-the-microsoft-365-moodle-plugins"></a>1. Microsoft 365 Moodle プラグインをインストールする

Moodle と Microsoft Teams の統合には、[Microsoft 365 Moodle プラグインセット](https://moodle.org/plugins/browse.php?list=set&id=72)オープンソースが搭載されています。

### <a name="requisite-applications-and-plugins"></a>必要なアプリケーションとプラグイン

次の項目をダウンロードしてインストールします。

1. [現在安定しているバージョンの Moodle](https://download.moodle.org/releases/latest/)。

    > [!IMPORTANT]
    > 既存の Moodle サイトがない場合は、Azure リポジトリの [Moodle に](https://github.com/azure/moodle) 移動し、Moodle インスタンスをすばやくデプロイし、ニーズに合わせてカスタマイズします。

1. Moodle [OpenID Connect](https://moodle.org/plugins/auth_oidc) と [Microsoft 365 Integration](https://moodle.org/plugins/local_o365) プラグインをダウンロードしてローカル コンピューターに保存します。

    > [!NOTE]
    > Teams の統合には、OpenID Connect プラグインと Microsoft 365 統合プラグインのインストールが必要です。
    >
    > また、 [Microsoft 365 Teams テーマ](https://moodle.org/plugins/theme_boost_o365teams) プラグインをインストールすることをお勧めします。

### <a name="microsoft-365-moodle-plugins"></a>Microsoft 365 Moodle プラグイン

#### <a name="install-plugins"></a>プラグインをインストールする

1. プラグインをダウンロードして抽出し、対応するフォルダーにアップロードします。
    * OpenID Connect プラグイン (auth_oidc) を **oidc** という名前のフォルダーに展開し、Moodle ドキュメント ルートの **認証** フォルダーにアップロードします。
    * Microsoft 365 Integration プラグイン (local_o365) を **o365** という名前のフォルダーに抽出し、Moodle ドキュメント ルートの **ローカル** フォルダーにアップロードします。
1. 管理者として Moodle サイトにサインインし、[ **サイト管理**] を選択します。
1. インストールする新しいプラグインが検出されると、Moodle は新しいプラグインのインストール ページにリダイレクトする必要があります。 これが発生しない場合は、[**サイト管理**] ページの [**全般**] タブで **[通知**] を選択すると、このアクションによってプラグインのインストールがトリガーされます。
1. 新しいプラグインがインストールされると、Moodle によって、インストールされているプラグインのすべての新しい構成を含むページが表示されます。 既定の設定を適用することで、このページを安全にスキップできます。 プラグインは、次の手順で構成されます。

## <a name="2-enable-the-openid-connect-authentication-plugin"></a>2. OpenID Connect 認証プラグインを有効にする

Moodle プラグインが Microsoft サービスと通信するには、OpenID Connect 認証プラグインをオンにして構成する必要があります。

1. **[サイト管理** > **プラグイン認証**] に移動し、[**認証** の > **管理**] を選択します。
1. **OpenID Connect** 認証プラグインを見つけて *、目のアイコン* を選択してオンにします。
1. プラグインの **[設定] を** 選択して、 **承認** エンドポイントと **トークン** エンドポイントを確認します。
    1. 既定値は次のようになります。
        1. 承認エンドポイント: ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. トークン エンドポイント: ``https://login.microsoftonline.com/common/oauth2/token``.
1. 後で使用できるように **リダイレクト URI を** 記録します。

    > [!NOTE]
    > すべての Moodle ユーザーが OpenID Connect 認証プラグインを認証方法として使用する必要はありません。ただし、他の認証方法を使用する場合は、Teams の所有権やメンバーシップの同期など、Teams 統合で特定の機能を使用するには、その Moodle アカウントを対応する Microsoft アカウントに *接続* する必要があります。

## <a name="3-configure-the-connection-between-the-microsoft-365-plugins-and-microsoft-services"></a>3. Microsoft 365 プラグインと Microsoft サービス間の接続を構成する

Microsoft 365 プラグインと Microsoft サービスが連携する前に、接続を構成する必要があります。

> [!NOTE]
> 統合の構成中は、プロセス全体を通じてこの一連のページに戻る必要があるため、Microsoft 365 Moodle Integration 構成ページを別のブラウザー タブで開いたままにします。

### <a name="the-teams-for-moodle-set-up-process"></a>Teams for Moodle のセットアップ プロセス

1. Azure アプリを作成する
    1. **サイト管理** > **プラグイン****のローカル プラグイン** > に移動し、**Microsoft 365 統合** を選択します。 これにより、Microsoft 365 統合構成ページが開きます。

    1. Microsoft 365 統合構成ページで、[ **セットアップ** ] タブを選択します。

    1. **[PowerShell スクリプトのダウンロード**] ボタンを選択し、ZIP フォルダーとしてローカル コンピューターに保存します。

        > [!NOTE]
        > スクリプトを実行すると、Microsoft 365 テナントに新しい Azure AD アプリケーションが作成されます。このアプリケーションは、必要な応答 URL とアクセス許可を設定し、必要なアクセス許可を与え、およびを返します`AppID``Key`。
        >
        > PowerShell スクリプトは、Windows 操作システムでのみ機能します。

    1. ZIP ファイルから PowerShell スクリプトを次のように準備します。
        1. ファイルをダウンロードして展開します `Moodle-AzureAD-Powershell.zip` 。
        1. 抽出されたフォルダーを開きます。
        1. ファイルを `Moodle-AzureAD-Script.ps1` 右クリックし、[ **プロパティ**] を選択します。
        1. プロパティ ウィンドウの [**全般**] タブで、ウィンドウの`Unblock`下部にある **[セキュリティ**] 属性の横にあるチェック ボックスをオンにします。
        1. **[OK]** をクリックします。
        1. 抽出されたフォルダーにディレクトリ パスをコピーします。

    1. PowerShell を管理者として実行します。
        1. Windows で、[スタート] を選択 **します**。
        1. 種類 `PowerShell`。
        1. **Windows PowerShell** を右クリックします。
        1. [ **管理者として実行]** を選択します。

    1. ディレクトリへのパスを入力`cd .../.../Moodle-AzureAD-Powershell``.../...`して、解凍されたディレクトリに移動します。

    1. PowerShell スクリプトを実行します。
        1. `./Moodle-AzureAD-Script.ps1` を入力します。
        1. メッセージが表示されたら、ポップアップ ウィンドウで Microsoft 365 管理者アカウントにサインインします。
        1. 質問されたら、Azure AD アプリケーションの名前 (Moodle プラグインや Moodle プラグインなど) を入力します。
        1. メッセージが表示されたら、Moodle サーバーの URL を入力します。
        1. メッセージが表示されたら、OpenID Connect 認証プラグインの構成ページからコピーした応答 URL を入力します。 これは基本的に、Moodle サイトの URL で、次に `\auth\oidc\`.
        1. プロセスのポップアップ ウィンドウで、Microsoft 365 アカウントにもう一度サインインするように求められる場合があります。 これは、組織のアプリに追加されたアクセス許可に管理者の同意を提供するためです。
        1. スクリプトの実行が完了したら、スクリプトによって生成された **アプリケーション ID (`AppID`)** と **Application Key(`Key`)** をコピーして保存します。

1. Moodle で Azure アプリの詳細を設定する
    1. OpenID Connect 認証プラグインの構成ページに戻ります。
    1. `AppID`[**アプリケーション ID**] ボックス`Key`に値を貼り付け、[**キー**] ボックスに値を貼り付けて、[**変更の保存]** を選択します。

1. Microsoft プラグインと Microsoft サービス間の接続を構成する
    1. Microsoft 365 統合構成ページで、[ **セットアップ** ] タブを選択します。
    1. [ **接続方法の選択]** で [ **アプリケーション アクセス**] を選択し、もう一度 [ **変更の保存]** を選択します。
    1. ページが更新されると、別の新しいセクション **管理同意&追加情報** が表示されます。
        1. [**同意の提供] リンク管理** 選択し、Microsoft 365 グローバル管理者の資格情報を入力し、[**同意]** を選択してアクセス許可を付与します。
        1. **Azure AD テナント** フィールドの横にある [**検出**] ボタンを選択します。
        1. **OneDrive for Business URL** の横にある [**検出**] ボタンを選択します。
        1. フィールドが設定されたら、もう一度 [ **変更の保存]** ボタンを選択します。

    1. [ **更新]** ボタンを選択してインストールを確認します。 この段階でエラーが報告されない場合は、Microsoft プラグインが Microsoft Graph API を介して Microsoft サーバーと通信できることを意味します。

1. ユーザーとコースの同期を構成する
    1. Moodle サーバーと Azure AD の間でユーザーを同期します。 環境に応じて、この段階でさまざまなオプションを選択できます。 次の手順をお試しください。
        1. Microsoft 365 統合構成ページで、[ **同期設定]** タブを選択します。

        1. [ **Azure AD でユーザーを同期** する] 設定で、環境に適用されるチェック ボックスをオンにします。 次のオプションを選択する必要があります。  
            ✔ Azure AD でユーザーのアカウントを Moodle に作成します。
           ✔ Azure AD のユーザーに対して、Moodle のすべてのアカウントを更新します。

        1. [ **ユーザー作成の制限** ] セクションで、Moodle に同期される Azure AD ユーザーを制限するフィルターを設定できます。

        > [!NOTE]
        > ユーザー同期を有効にする必要はありません。ただし、Moodle ユーザーと Microsoft 365 アカウントの接続がはるかに簡単になります。
        >
        > ユーザー同期は、Azure AD スケジュールされたタスク **でユーザーを同期** することによって実行されます。

    1. **[コース同期**] セクションで、[**コース同期のカスタマイズ**] オプションを選択して、既存の Moodle コースの一部または全部の Teams の自動作成を有効にすることができます。

        > [!NOTE]
        > コース同期は、 **Sync Moodle コースを Microsoft Teams** のスケジュールされたタスクに実行することによって実行されます。

    1. 変更を保存します。

    1. 同期構成を検証するには、スケジュールされたタスクを初めて手動で実行し、**サイト管理** > **サーバー** > **タスク** > の **スケジュールされたタスク** に移動する必要があります。

        1. 下にスクロールし、 **タスク [ユーザーと Azure AD の同期** ] を見つけて、[ **今すぐ実行**] を選択します。
            1. これにより、ユーザー同期オプションに従って Azure AD ユーザーが Moodle サイトに同期されます。
        1. 次に、 **Microsoft Teams タスクに Moodle コースを同期し** 、[ **今すぐ実行**] を選択します。
            1. このタスクでは、同期オプションがオンになっているすべての Moodle コースのグループが作成され、 **コースでチームの所有者** が見つかる場合は Teams も作成されます。
            1. また、このタスクでは、コースに登録されている Moodle ユーザーが所有者またはメンバーとして Teams に同期されます。
                1. チーム **の所有者** は、チームの所有者である Moodle ユーザーです。
                    1. は Microsoft 365 アカウントに接続されています。AND
                    2. はコースに登録され、AND
                    3. には、 `local/o365:teamowner` コース コンテキストの機能があります。
                1. 同様に、チーム **メンバー** は Moodle ユーザーです。
                    1. は Microsoft 365 アカウントに接続されています。AND
                    2. はコースに登録され、AND
                    3. には、 `local/o365:teamember` コース コンテキストの機能があります。
                1. 既定の *教師* ロールには `local/o365:teamowner` 機能があり、既定の *学生* ロールには機能があります `local/o365:teammember` 。

    > [!NOTE]
    > スケジュールされたタスクは、頻繁に実行するように構成する必要がある [Moodle Cron](https://docs.moodle.org/400/en/Cron) によってトリガーされます。 スケジュールされた各タスクには、カスタマイズできる既定のスケジュールを設定できます。
    >
    > * **Azure AD とユーザーを同期** するタスクの既定のスケジュールは、毎分です。
    > * **ムードル コースを Microsoft Teams に同期する** タスクの既定のスケジュールは、Moodle サーバーの既定のタイム ゾーンで毎日午前 1 時です。

プラグインのインストールと構成が完了したら、次のことができます。

* [Moodle Assistant Bot を Azure にデプロイします](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure)。
* [Teams クラスに Moodle タブを追加します](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app)。
* [Teams のクラスと会議を Moodle LMS に追加します](teams-classes-meetings-with-moodle.md)。

## <a name="extra-moodle-plugin-documentation"></a>追加の Moodle プラグインのドキュメント

Moodle の Microsoft 365 統合ガイドとリリース ノートを確認する場合は、次のリソースを参照してください。

* [Moodle Docs に関する Microsoft 365 統合ドキュメント](https://docs.moodle.org/400/en/Microsoft_365)。
