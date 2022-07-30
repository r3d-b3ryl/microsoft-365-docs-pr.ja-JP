---
title: Open LMS 用の Moodle LMS プラグインを設定して構成する
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
description: Moodle LMS プラグインを設定して構成することで、Open LMS とMicrosoft Teamsを統合する準備を整えます。
ms.openlocfilehash: dbc85e8643159552e3e9bf340deef1856b542aab
ms.sourcegitcommit: 2f6a7410e9919f753a759c1ada441141e18f06fd
ms.translationtype: MT
ms.contentlocale: ja-JP
ms.lasthandoff: 07/30/2022
ms.locfileid: "67085973"
---
# <a name="set-up-and-configure-the-moodle-lms-plugins-for-open-lms"></a>Open LMS 用の Moodle LMS プラグインを設定して構成する

この記事では、Microsoft Teamsを Open LMS エクスペリエンスと統合するために、Moodle LMS プラグインをインストールして構成する方法について説明します。

## <a name="prerequisites"></a>前提条件

インストール済みの Open LMS を設定して構成して、Microsoft Teamsを操作するには:

- [Moodle OpenID Connect](https://moodle.org/plugins/auth_oidc) と [Microsoft 365 統合](https://moodle.org/plugins/local_o365)プラグインがアクティブであることを確認します。

## <a name="configure-the-connection-between-the-microsoft-365-plugins-and-microsoft-services"></a>Microsoft 365 プラグインと Microsoft サービス間の接続を構成する

Microsoft 365 プラグインと Microsoft サービスが連携する前に、接続を構成する必要があります。

> [!NOTE]
> 統合の構成中は、プロセス全体を通じてこれらのページに戻る必要があるため、Microsoft 365 統合構成ページを別のブラウザー タブで開いたままにします。

### <a name="enable-the-openid-connect-authentication-plugin"></a>OpenID Connect 認証プラグインを有効にする

Moodle プラグインが Microsoft サービスと通信するには、OpenID Connect 認証プラグインをオンにして構成する必要があります。

1. **[サイト管理** > **プラグイン認証**] に移動し、[**認証** の > **管理**] を選択します。
1. **OpenID Connect** 認証プラグインを見つけて *、目のアイコン* を選択してオンにします。
1. プラグインの **[設定] を** 選択して、 **承認** エンドポイントと **トークン** エンドポイントを確認します。
    1. 既定値は次のようになります。
        1. 承認エンドポイント: ``https://login.microsoftonline.com/common/oauth2/authorize``.
        1. トークン エンドポイント: ``https://login.microsoftonline.com/common/oauth2/token``.
1. 後で使用できるように **リダイレクト URI を** 記録します。

> [!NOTE]
> すべての Open LMS ユーザーが OpenID Connect 認証プラグインを認証方法として使用する必要はありません。ただし、他の認証方法を使用する場合は、Teams の所有権やメンバーシップの同期など、Teams 統合の特定の機能を使用するには、Open LMS アカウントを対応する Microsoft アカウントに *接続* する必要があります。

### <a name="requisites"></a>前提 条件

PowerShell スクリプトを使用して、Azure AD で Open LMS をアプリケーションとして登録します。 スクリプトでは、次の項目がプロビジョニングされます。

- Microsoft 365 Moodle プラグインによって使用される、Microsoft 365 テナント用の新しい Azure AD アプリケーション。
- Microsoft 365 テナントのアプリは、プロビジョニングされたアプリに必要な応答 URL とアクセス許可を設定し、次の値を`AppID``Key`返します。
- Windows 以外のオペレーティング システムでは、手動プロセスに従って Open LMS インスタンスを Azure に登録する必要があります。 詳細については、以下の *重要な* アラート セクションを参照してください。

> [!IMPORTANT]
> Open LMS インスタンスを手動で登録する方法の詳細については、「 [Open LMS インスタンスをアプリケーションとして登録する」を参照してください](https://docs.moodle.org/400/en/Microsoft_365#Azure_App_Creation_and_Configuration)。
>
> アプリを登録したら、すべての Azure アプリのアクセス許可が適用されていることを確認します。 詳細については、 [Azure アプリのアクセス許可](https://docs.moodle.org/400/en/Microsoft_365#Azure_app_permissions)に関するページを参照してください。

### <a name="register-application-in-azure-using-powershell"></a>PowerShell を使用して Azure にアプリケーションを登録する

#### <a name="step-1-create-azure-app"></a>手順 1: Azure アプリを作成する

1. **サイト管理** > **プラグイン****のローカル プラグイン** > に移動し、**Microsoft 365 統合** を選択します。 これにより、Microsoft 365 統合構成ページが開きます。

1. Microsoft 365 統合構成ページで、[ **セットアップ** ] タブを選択します。

1. **[PowerShell スクリプトのダウンロード**] ボタンを選択し、ZIP フォルダーとしてローカル コンピューターに保存します。

    > [!NOTE]
    > スクリプトを実行すると、Microsoft 365 テナントに新しい Azure AD アプリケーションが作成されます。このアプリケーションは、必要な応答 URL とアクセス許可を設定し、必要なアクセス許可を与え、およびを返します`AppID``Key`。
    >
    > このスクリプトは、Windows 以外のオペレーティング システムでは PowerShell では機能しません。

1. ZIP ファイルから PowerShell スクリプトを次のように準備します。
    1. ファイルをダウンロードして展開します `Moodle-AzureAD-Powershell.zip` 。
    1. 抽出されたフォルダーを開きます。
    1. ファイルを `Moodle-AzureAD-Script.ps1` 右クリックし、[ **プロパティ**] を選択します。
    1. プロパティ ウィンドウの [**全般**] タブで、ウィンドウの`Unblock`下部にある **[セキュリティ**] 属性の横にあるチェック ボックスをオンにします。
    1. [**OK**] を選択します。
    1. 抽出されたフォルダーにディレクトリ パスをコピーします。

1. PowerShell を管理者として実行します。
    1. Windows で、スタート メニューを開きます。
    1. 種類 `PowerShell`。
    1. **Windows PowerShell** を右クリックします。
    1. [ **管理者として実行]** を選択します。

1. ディレクトリへのパスを入力`cd .../.../Moodle-AzureAD-Powershell``.../...`して、解凍されたディレクトリに移動します。

1. PowerShell スクリプトを実行します。
    1. `./Moodle-AzureAD-Script.ps1` を入力します。
    1. メッセージが表示されたら、ポップアップ ウィンドウで Microsoft 365 管理者アカウントにサインインします。
    1. メッセージが表示されたら、Azure AD アプリケーションの名前を入力します。 たとえば、LMS、Moodle、または Moodle プラグインを開きます。
    1. 確認メッセージが表示されたら、Open LMS サーバーの URL を入力します。
    1. メッセージが表示されたら、OpenID Connect 認証プラグインの構成ページからコピーした応答 URL を入力します。 これは、Open LMS サイトの URL の後に続く `\auth\oidc\`URL です。
    1. プロセスのポップアップ ウィンドウで、Microsoft 365 アカウントにもう一度サインインするように求められる場合があります。 これは、組織のアプリに追加されたアクセス許可に管理者の同意を提供するためです。
    1. スクリプトの実行が完了したら、スクリプトによって生成された **アプリケーション ID (`AppID`)** と **Application Key(`Key`)** をコピーして保存します。

#### <a name="step-2-set-azure-app-details-in-openid-connect"></a>手順 2: OpenID Connect で Azure アプリの詳細を設定する

1. OpenID Connect 認証プラグインの構成ページに戻ります。
1. `AppID`[**アプリケーション ID**] ボックス`Key`に値を貼り付け、[**キー**] ボックスに値を貼り付けて、[**変更の保存]** を選択します。

#### <a name="step-3-configure-connection-between-microsoft-plugins-and-microsoft-services"></a>手順 3: Microsoft プラグインと Microsoft サービス間の接続を構成する

1. Microsoft 365 統合構成ページで、[ **セットアップ** ] タブを選択します。
1. [ **接続方法の選択]** で [ **アプリケーション アクセス**] を選択し、もう一度 [ **変更の保存]** を選択します。
1. ページが更新されると、別の新しいセクション **管理同意&追加情報** が表示されます。
    1. [**同意の提供] リンク管理** 選択し、Microsoft 365 グローバル管理者の資格情報を入力し、[**同意]** を選択してアクセス許可を付与します。
    1. **Azure AD テナント** フィールドの横にある [**検出**] ボタンを選択します。
    1. **OneDrive for Business URL** の横にある [**検出**] ボタンを選択します。
    1. フィールドが設定されたら、もう一度 [ **変更の保存]** ボタンを選択します。
1. [ **更新]** ボタンを選択してインストールを確認します。 この段階でエラーが報告されない場合は、Microsoft プラグインが Microsoft Graph API を介して Microsoft サーバーと通信できることを意味します。

#### <a name="step-4-configure-user-and-course-synchronization"></a>手順 4: ユーザーとコースの同期を構成する

1. Open LMS サーバーと Azure AD の間でユーザーを同期します。 環境に応じて、この段階でさまざまなオプションを選択できます。 次の手順をお試しください。

    1. Microsoft 365 統合構成ページで、[ **同期設定]** タブを選択します。

    1. [ **Azure AD でユーザーを同期** する] 設定で、環境に適用されるチェック ボックスをオンにします。 次のオプションを選択する必要があります。  
        ✔ Azure AD のユーザーの Open LMS でアカウントを作成します。
       ✔ Azure AD のユーザー向けに Open LMS のすべてのアカウントを更新します。

    1. [ **ユーザー作成の制限** ] セクションで、Open LMS に同期される Azure AD ユーザーを制限するフィルターを設定できます。

        > [!NOTE]
        > ユーザー同期を有効にする必要はありません。ただし、Open LMS ユーザーと Microsoft 365 アカウントの接続がはるかに簡単になります。
        >
        > ユーザー同期は、Azure AD スケジュールされたタスク **でユーザーを同期** することによって実行されます。

1. **[コース同期**] セクションで、[**コース同期のカスタマイズ**] オプションを選択して、既存の Open LMS コースの一部またはすべてを Teams の自動作成を有効にすることができます。

    > [!NOTE]
    > コース同期は、スケジュールされたタスクに **対して Sync Moodle コースMicrosoft Teams** 実行することによって実行されます。

1. 変更を保存します。

1. 同期構成を検証するには、スケジュールされたタスクを初めて手動で実行する必要があります。 **サイト管理** > **サーバー** > **タスク** > **のスケジュールされたタスク** に移動します。

    1. 下にスクロールし、 **タスク [ユーザーと Azure AD の同期** ] を見つけて、[ **今すぐ実行**] を選択します。
        1. これにより、ユーザー同期オプションに従って Azure AD ユーザーが Open LMS サイトに同期されます。
    1. 次に、[ **Sync Moodle courses to Microsoft Teams** タスク] を見つけて、[ **今すぐ実行**] を選択します。
        1. このタスクは、同期オプションがオンになっているすべての Open LMS コースのグループを作成し、チーム **の所有者** がコースで見つかる場合は Teams も作成します。
        1. また、このタスクでは、コースに登録されている Open LMS ユーザーを所有者またはメンバーとして Teams に同期します。
            1. チーム **の所有者** は、次のすべての条件を満たす Open LMS ユーザーです。
                1. は Microsoft 365 アカウントに接続されています。
                2. はコースに登録されます。
                3. には、 `local/o365:teamowner` コース コンテキストの機能があります。
            1. 同様に、チーム **メンバー** は、次のすべての条件を満たす Open LMS ユーザーです。
                1. は Microsoft 365 アカウントに接続されています。
                2. はコースに登録されます。
                3. には、 `local/o365:teamember` コース コンテキストの機能があります。
            1. 既定の *教師* ロールには `local/o365:teamowner` 機能があり、既定の *学生* ロールには機能があります `local/o365:teammember` 。

> [!NOTE]
> スケジュールされたタスクは、頻繁に実行するように構成する必要がある [Moodle Cron](https://docs.moodle.org/400/en/Cron) によってトリガーされます。 スケジュールされた各タスクには既定のスケジュールを設定でき、カスタマイズできます。
>
> - **Azure AD とユーザーを同期** するタスクの既定のスケジュールは、毎分です。
> - **Microsoft Teams タスクへの Moodle コースの同期** の既定のスケジュールは、Open LMS サーバーの既定のタイム ゾーンで毎日午前 1 時です。

プラグインのインストールと構成が完了したら、次のことができます。

- [Teams クラスと会議を Open LMS に追加します](open-lms-teams-classes-and-meetings.md)。
- [Moodle Assistant Bot を Azure にデプロイします](/microsoftteams/install-moodle-integration#step-3-deploy-the-moodle-assistant-bot-to-azure)。
- [Teams クラスに Moodle タブを追加します](/microsoftteams/install-moodle-integration#step-4-deploy-your-microsoft-teams-app)。

## <a name="extra-moodle-plugin-documentation"></a>追加の Moodle プラグインのドキュメント

Open LMS の Microsoft 365 統合ガイドとリリース ノートを確認する場合は、次のリソースを参照してください。

- [Moodle Docs に関する Microsoft 365 統合ドキュメント](https://docs.moodle.org/400/en/Microsoft_365)。
