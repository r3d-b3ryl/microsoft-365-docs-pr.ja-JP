---
title: Moodle プラグインを設定して構成する
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
description: Moodle プラグインを設定して構成することで、Moodle とMicrosoft Teamsを統合する準備を整えます。
ms.openlocfilehash: 4fadcd4c52b1389aee51149e9d5313c7821ab10d
ms.sourcegitcommit: f181e110cdb983788a86f30d5bb018e53c83e64d
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 06/13/2022
ms.locfileid: "66057791"
---
# <a name="set-up-the-moodle-plugin"></a>Moodle プラグインを設定する

この記事では、Moodle のエクスペリエンスにMicrosoft Teamsを組み込むために、Moodle LMS プラグインをインストールして構成する方法について説明します。

## <a name="prerequisites"></a>前提条件

Moodle をインストールするための前提条件を次に示します。

* Moodle 管理者の資格情報。
* Azure AD 管理者の資格情報。
* 新しいリソースを作成できる Azure サブスクリプション。

## <a name="1-install-the-microsoft-365-moodle-plugins"></a>1. Microsoft 365 Moodle プラグインをインストールする

Microsoft Teamsでの Moodle の統合は、[オープンソース Microsoft 365 Moodle プラグインセット](https://moodle.org/plugins/browse.php?list=set&id=72)によって強化されます。

### <a name="requisite-applications-and-plugins"></a>必要なアプリケーションとプラグイン

Microsoft 365 Moodle プラグインのインストールに進む前に、次の項目をインストールしてダウンロードします。

1. [現在安定しているバージョンの Moodle](https://download.moodle.org/releases/latest/)。
1. Moodle [OpenID Connect](https://moodle.org/plugins/auth_oidc)と [Microsoft 365 Integration](https://moodle.org/plugins/local_o365) プラグインをダウンロードしてローカル コンピューターに保存します。

    > [!NOTE]
    > Teams統合には、OpenID Connect プラグインとMicrosoft 365統合プラグインのインストールが必要です。
    >
    > [Microsoft 365 Teamsテーマ](https://moodle.org/plugins/theme_boost_o365teams) プラグインをお勧めします。

### <a name="microsoft-365-moodle-plugins"></a>Microsoft 365 Moodle プラグイン

#### <a name="install-plugins"></a>プラグインをインストールする

1. プラグインをダウンロードして抽出し、対応するフォルダーにアップロードします。 たとえば、OpenID Connect プラグイン (auth_oidc) を **oidc** という名前のフォルダーに抽出し、Moodle ドキュメント ルートの **認証** フォルダーにアップロードします。
2. 管理者として Moodle サイトにサインインし、[ **サイト管理**] を選択します。
3. インストールする新しいプラグインが検出されると、Moodle は新しいプラグインのインストール ページにリダイレクトする必要があります。 これが発生しない場合は、[**サイト管理**] ページの [**全般**] タブで **[通知**] を選択すると、プラグインのインストールがトリガーされます。

    > [!IMPORTANT]
    >
    > * プロセス全体を通じてこのページのセットに戻る必要があるため、Microsoft 365 Moodle Plugins 構成ページを別のブラウザー タブで開いたままにします。  
    >
    > * 既存の Moodle サイトがない場合は、Azure リポジトリの [Moodle に](https://github.com/azure/moodle) 移動し、Moodle インスタンスをすばやくデプロイしてニーズに合わせてカスタマイズします。

#### <a name="enable-the-openid-connect-authentication-plugin"></a>OpenID Connect認証プラグインを有効にする

1. **[サイト管理** > **プラグイン認証**] に移動し、[**認証** の > **管理**] を選択します。
1. **OpenID Connect** 認証プラグインを見つけて *、目のアイコン* を選択して有効にします。
1. プラグイン **の設定** を選択して、**承認** エンドポイントと **トークン** エンドポイントを確認します。
    1. 既定値は次のようになります。
        1. 承認エンドポイント: ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. トークン エンドポイント: ``https://login.microsoftonline.com/common/oauth2/token``.
1. 後で使用できるように **リダイレクト URI を** 記録します。

## <a name="2-configure-the-connection-between-the-microsoft-365-plugins-and-azure-ad"></a>2. Microsoft 365 プラグインと Azure AD 間の接続を構成する

Microsoft 365 プラグインと Azure AD 間の接続を構成する必要があります。

### <a name="requisites"></a>前提 条件

PowerShell スクリプトを使用して、Azure AD で Moodle をアプリケーションとして登録します。 スクリプトでは、次の項目がプロビジョニングされます。

* Microsoft 365 Moodle プラグインによって使用される、Microsoft 365 テナント用の新しい Azure AD アプリケーション。
* Microsoft 365 テナントのアプリは、プロビジョニングされたアプリに必要な応答 URL とアクセス許可を設定し、`AppID`次の値を`Key`返します。

生成された `AppID` `Key` [Microsoft 365 Moodle Plugins] セットアップ ページを使用して、Azure AD を使用して Moodle サーバー サイトを構成します。

> [!IMPORTANT]
> * Moodle インスタンスを手動で登録する方法の詳細については、「 [Moodle インスタンスをアプリケーションとして登録する」を参照してください](https://docs.moodle.org/400/en/Microsoft_365#Azure_App_Creation_and_Configuration)。

### <a name="the-teams-for-moodle-set-up-process"></a>Moodle のセットアップ プロセスのTeams

1. Microsoft 365統合プラグイン ページで、[**セットアップ]** タブを選択します。

1. **[PowerShell スクリプトのダウンロード**] ボタンを選択し、ZIP フォルダーとしてローカル コンピューターに保存します。

1. ZIP ファイルから PowerShell スクリプトを次のように準備します。

    1. ファイルをダウンロードして展開します `Moodle-AzureAD-Powershell.zip` 。
    1. 抽出されたフォルダーを開きます。
    1. ファイルを `Moodle-AzureAD-Script.ps1` 右クリックし、[ **プロパティ**] を選択します。
    1. プロパティ ウィンドウの [**全般**] タブで、ウィンドウの`Unblock`下部にある **[セキュリティ**] 属性の横にあるチェック ボックスをオンにします。
    1. **[OK]** を選択します。
    1. 抽出されたフォルダーにディレクトリ パスをコピーします。

1. PowerShell を管理者として実行します。

    1. [開始] を選択します。
    1. PowerShell と入力します。
    1. **Windows PowerShell** を右クリックします。
    1. [ **管理者として実行]** を選択します。

1. ディレクトリへのパスを入力`cd .../.../Moodle-AzureAD-Powershell``.../...`して、解凍されたディレクトリに移動します。

1. PowerShell スクリプトを実行します。

    1. `Set-ExecutionPolicy -ExecutionPolicy RemoteSigned -Scope CurrentUser` を入力します。
    1. `./Moodle-AzureAD-Script.ps1` を入力します。
    1. ポップアップ ウィンドウでMicrosoft 365管理者アカウントにサインインします。
    1. Azure AD アプリケーションの名前 (Moodle プラグインや Moodle プラグインなど) を入力します。
    1. Moodle サーバーの URL を入力します。
    1. スクリプトによって生成された **アプリケーション ID (`AppID`)** と **Application Key(`Key`)** をコピーして保存します。

1. プラグイン管理ページの **サイト管理** > **プラグイン** > **認証** > **OpenID Connect** に戻ります。

1. `AppID`[**アプリケーション ID**] ボックス`Key`に値を貼り付け、[**キー**] ボックスに値を貼り付けて、[**変更の保存]** を選択します。

1. **サイト管理** > **プラグイン****のローカル プラグイン** > に移動し、**Microsoft 365統合** を選択します。

1. [ **接続方法の選択]** で [ **アプリケーション アクセス**] を選択し、もう一度 [ **変更の保存]** を選択します。

1. ページが更新されると、別の新しいセクション **管理者の同意&追加情報** が表示されます。
    1. [**管理者の同意の提供**] リンクを選択し、Microsoft 365グローバル管理者の資格情報を入力し、[**同意]** を選択してアクセス許可を付与します。
    1. **Azure AD テナント** フィールドの横にある [**検出**] ボタンを選択します。
    1. **OneDrive for Business URL** の横にある [**検出**] ボタンを選択します。
    1. フィールドが設定されたら、もう一度 [ **変更の保存]** ボタンを選択します。

1. [ **更新]** ボタンを選択してインストールを確認し、[ **変更の保存]** を選択します。

1. Moodle サーバーと Azure AD の間でユーザーを同期します。 環境に応じて、この段階でさまざまなオプションを選択できます。 次の手順をお試しください。
    1. **[同期設定] タブ** に切り替えます。

    1. [ **ユーザーと Azure AD の同期** ] セクションで、環境に適用するチェック ボックスをオンにします。 次のオプションを選択する必要があります。  

        ✔ Azure AD でユーザーのアカウントを Moodle に作成します。
        
        ✔ Azure AD のユーザーに対して、Moodle のすべてのアカウントを更新します。
        

    1. [ **ユーザー作成の制限** ] セクションで、Moodle に同期される Azure AD ユーザーを制限するフィルターを設定できます。
    1. **[コース同期**] セクションで、[**コース同期のカスタマイズ**] オプションを選択して、既存の Moodle コースの一部または全部のグループとTeamsの自動作成を有効にすることができます。

1. [cron](https://docs.moodle.org/400/en/Cron) タスクを検証し、初めて手動で実行するには、**サイト管理** > **サーバー** > **タスク** > **のスケジュールされたタスク** に移動します。

    1. 下にスクロールし、 **タスク [ユーザーと Azure AD の同期** ] を見つけて、[ **今すぐ実行**] を選択します。
        1. これにより、AAD ユーザーが Moodle サイトに同期されます。
    1. 次に、タスクを **Microsoft Teamsする Sync Moodle コースを** 見つけて、[**今すぐ実行**] を選択します。
        1. このタスクはグループを作成し、所有者が見つかった場合はTeamsします。
        1. ユーザーがコース コンテキストで機能を持っている `local/o365:teamowner` 場合、ユーザーはチームの所有者です。 ユーザーがコース コンテキストで機能を持っている `local/o365:teammember` 場合、ユーザーはチーム メンバーです。  
        1. 既定の *教師* ロールには 、既定の`local/o365:teamowner" capability`*学生* ロールには機能があります`local/o365:teammember`。

    > [!NOTE]
    >
    > Moodle [Cron](https://docs.moodle.org/400/en/Scheduled_tasks) は、タスク スケジュールに従って実行されます。 既定のスケジュールは、サーバーのローカル タイム ゾーンの 1 日 1:00 AM に 1 回です。 ただし、すべての同期を維持するために cron をより頻繁に実行する必要があります。

1. **[サイト管理** > **プラグイン****] ローカル プラグイン** >  > **Microsoft 365 [統合** > **Teams 設定**] タブに移動します。

1. [**Check Moodle settings]** ボタンをクリックすると、Teams統合が機能するために必要なすべての構成が更新されます。
        

プラグインのインストールと構成が完了したら、次のことができます。

* [Moodle Assistant Bot を Azure にデプロイします](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure)。
* [Teams クラスに Moodle タブを追加します](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app)。
* [Teamsクラスと会議を Moodle LMS に追加します](teams-classes-meetings-with-moodle.md)。

## <a name="extra-moodle-plugin-documentation"></a>追加の Moodle プラグインのドキュメント

Moodle のMicrosoft 365統合ガイドとリリース ノートを確認する場合は、次のリソースを参照してください。

* [Moodle Docs の統合ドキュメントをMicrosoft 365します](https://docs.moodle.org/400/en/Microsoft_365)。
